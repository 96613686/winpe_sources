# SnmpExtensionQuery

- ea: `0x180001a40`
- end: `0x180001b42`
- name: `SnmpExtensionQuery`
- size: `258`
- prototype: `BOOL __stdcall(BYTE bPduType, SnmpVarBindList *pVarBindList, AsnInteger32 *pErrorStatus, AsnInteger32 *pErrorIndex)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001a40`
- `0x180001dd4`
- `0x180002024`
- `0x180002d66`
- `0x180002da0`

## import_xrefs

- `snmpapi!SnmpUtilOidCpy` at `0x180001ae0`
- `snmpapi!SnmpUtilOidCpy` at `0x180001ae0`
- `snmpapi!SnmpUtilOidFree` at `0x180001ad0`
- `snmpapi!SnmpUtilOidFree` at `0x180001ad0`

## pseudocode

```c
BOOL __stdcall SnmpExtensionQuery(
        BYTE bPduType,
        SnmpVarBindList *pVarBindList,
        AsnInteger32 *pErrorStatus,
        AsnInteger32 *pErrorIndex)
{
  struct _MIB_ENTRIES *v8; // r9
  SnmpVarBind *i; // rbx
  AsnInteger32 v10; // eax
  AsnInteger32 v11; // eax
  _BYTE v13[304]; // [rsp+30h] [rbp-168h] BYREF

  memset_0(v13, 0, 0x128u);
  W3QueryStatisticsFromSharedMemory((struct _W3_STATISTICS_1 *)v13);
  for ( i = pVarBindList->list; i < &pVarBindList->list[(unsigned __int64)pVarBindList->len]; ++i )
  {
    v10 = ResolveVarBinding(&i->name, bPduType, v13, v8);
    *pErrorStatus = v10;
    if ( v10 == 2 && bPduType == 0xA1 )
    {
      *pErrorStatus = 0;
      SnmpUtilOidFree(&i->name);
      SnmpUtilOidCpy(&i->name, &pOidSrc);
      if ( pOidSrc.idLength )
        ++i->name.ids[pOidSrc.idLength - 1];
    }
    if ( *pErrorStatus )
      v11 = i - pVarBindList->list + 1;
    else
      v11 = 0;
    *pErrorIndex = v11;
  }
  return 1;
}

```

## disassembly

```asm
0x180001a40  push    rbx
0x180001a42  push    rsi
0x180001a43  push    rdi
0x180001a44  push    r14
0x180001a46  push    r15
0x180001a48  sub     rsp, 170h
0x180001a4f  mov     rax, cs:__security_cookie
0x180001a56  xor     rax, rsp
0x180001a59  mov     [rsp+198h+var_38], rax
0x180001a61  mov     r15, r9
0x180001a64  mov     rsi, r8
0x180001a67  mov     rdi, rdx
0x180001a6a  mov     r14b, cl
0x180001a6d  xor     edx, edx; Val
0x180001a6f  mov     r8d, 128h; Size
0x180001a75  lea     rcx, [rsp+198h+var_168]; void *
0x180001a7a  call    memset_0
0x180001a7f  lea     rcx, [rsp+198h+var_168]; struct _W3_STATISTICS_1 *
0x180001a84  call    ?W3QueryStatisticsFromSharedMemory@@YAIPEAU_W3_STATISTICS_1@@@Z; W3QueryStatisticsFromSharedMemory(_W3_STATISTICS_1 *)
0x180001a89  nop
0x180001a8a  mov     [rsp+198h+var_178], 0
0x180001a93  mov     rbx, [rdi]
0x180001a96  mov     [rsp+198h+var_178], rbx
0x180001a9b  mov     eax, [rdi+8]
0x180001a9e  shl     rax, 5
0x180001aa2  add     rax, [rdi]
0x180001aa5  cmp     rbx, rax
0x180001aa8  jnb     short loc_180001B1C
0x180001aaa  lea     r8, [rsp+198h+var_168]; void *
0x180001aaf  mov     dl, r14b; unsigned __int8
0x180001ab2  mov     rcx, rbx; pOidDst
0x180001ab5  call    ?ResolveVarBinding@@YAIPEAUSnmpVarBind@@EPEAXPEAU_MIB_ENTRIES@@@Z; ResolveVarBinding(SnmpVarBind *,uchar,void *,_MIB_ENTRIES *)
0x180001aba  mov     [rsi], eax
0x180001abc  cmp     eax, 2
0x180001abf  jnz     short loc_180001AFA
0x180001ac1  cmp     r14b, 0A1h
0x180001ac5  jnz     short loc_180001AFA
0x180001ac7  mov     dword ptr [rsi], 0
0x180001acd  mov     rcx, rbx; pOid
0x180001ad0  call    cs:__imp_SnmpUtilOidFree
0x180001ad6  lea     rdx, pOidSrc; pOidSrc
0x180001add  mov     rcx, rbx; pOidDst
0x180001ae0  call    cs:__imp_SnmpUtilOidCpy
0x180001ae6  mov     eax, cs:pOidSrc.idLength
0x180001aec  test    eax, eax
0x180001aee  jz      short loc_180001AFA
0x180001af0  lea     ecx, [rax-1]
0x180001af3  mov     rax, [rbx+4]
0x180001af7  inc     dword ptr [rax+rcx*4]
0x180001afa  cmp     dword ptr [rsi], 0
0x180001afd  jz      short loc_180001B0E
0x180001aff  mov     rax, rbx
0x180001b02  sub     rax, [rdi]
0x180001b05  sar     rax, 5
0x180001b09  inc     rax
0x180001b0c  jmp     short loc_180001B10
0x180001b0e  xor     eax, eax
0x180001b10  mov     [r15], eax
0x180001b13  add     rbx, 20h ; ' '
0x180001b17  jmp     loc_180001A96
0x180001b1c  jmp     short $+2
0x180001b1e  mov     eax, 1
0x180001b23  mov     rcx, [rsp+198h+var_38]
0x180001b2b  xor     rcx, rsp; StackCookie
0x180001b2e  call    __security_check_cookie
0x180001b33  add     rsp, 170h
0x180001b3a  pop     r15
0x180001b3c  pop     r14
0x180001b3e  pop     rdi
0x180001b3f  pop     rsi
0x180001b40  pop     rbx
0x180001b41  retn
```
