# CTscSettings::ChildDeviceHasClassGuid(ulong,_GUID)

- ea: `0x140033f98`
- end: `0x14003409f`
- name: `?ChildDeviceHasClassGuid@CTscSettings@@AEAAEKU_GUID@@@Z`
- size: `263`
- prototype: `unsigned __int8(CTscSettings *__hidden this, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140033f98`
- `0x14003c398`
- `0x14003cbac`

## callees

- `0x140033f98`
- `0x140113322`
- `0x140113390`

## import_xrefs

- `ole32!CLSIDFromString` at `0x140034047`
- `ole32!CLSIDFromString` at `0x140034047`
- `CFGMGR32!CM_Get_Child` at `0x140033fd7`
- `CFGMGR32!CM_Get_Child` at `0x140033fd7`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x140034028`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x140034028`
- `CFGMGR32!CM_Get_Sibling` at `0x140034071`
- `CFGMGR32!CM_Get_Sibling` at `0x140034071`

## pseudocode

```c
unsigned __int8 __fastcall CTscSettings::ChildDeviceHasClassGuid(CTscSettings *this, DEVINST a2, struct _GUID *a3)
{
  char v5; // bl
  CONFIGRET i; // eax
  DEVNODE pdnDevInst; // [rsp+30h] [rbp-39h] BYREF
  ULONG pulRegDataType; // [rsp+34h] [rbp-35h] BYREF
  ULONG pulLength; // [rsp+38h] [rbp-31h] BYREF
  GUID pclsid; // [rsp+40h] [rbp-29h] BYREF
  OLECHAR Buffer[40]; // [rsp+50h] [rbp-19h] BYREF

  pdnDevInst = 0;
  pulRegDataType = 0;
  v5 = 0;
  for ( i = CM_Get_Child(&pdnDevInst, a2, 0); !i; i = CM_Get_Sibling(&pdnDevInst, pdnDevInst, 0) )
  {
    pclsid = *a3;
    if ( !CTscSettings::ChildDeviceHasClassGuid(this, pdnDevInst, &pclsid) )
    {
      pulLength = 78;
      if ( CM_Get_DevNode_Registry_PropertyW(pdnDevInst, 9u, &pulRegDataType, Buffer, &pulLength, 0) )
        continue;
      if ( pulRegDataType != 1 )
        continue;
      pclsid = 0;
      if ( CLSIDFromString(Buffer, &pclsid) < 0 || memcmp_0(&pclsid, a3, 0x10u) )
        continue;
    }
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x140033f98  mov     [rsp-8+arg_18], rbx
0x140033f9d  push    rbp
0x140033f9e  push    rsi
0x140033f9f  push    rdi
0x140033fa0  lea     rbp, [rsp-47h]
0x140033fa5  sub     rsp, 0B0h
0x140033fac  mov     rax, cs:__security_cookie
0x140033fb3  xor     rax, rsp
0x140033fb6  mov     [rbp+57h+var_20], rax
0x140033fba  mov     rdi, r8
0x140033fbd  mov     [rbp+57h+pdnDevInst], 0
0x140033fc4  mov     rsi, rcx
0x140033fc7  mov     [rbp+57h+pulRegDataType], 0
0x140033fce  xor     r8d, r8d; ulFlags
0x140033fd1  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x140033fd5  xor     bl, bl
0x140033fd7  call    cs:__imp_CM_Get_Child
0x140033fdd  test    eax, eax
0x140033fdf  jnz     loc_14003407E
0x140033fe5  movups  xmm0, xmmword ptr [rdi]
0x140033fe8  mov     edx, [rbp+57h+pdnDevInst]; unsigned int
0x140033feb  lea     r8, [rbp+57h+pclsid]; struct _GUID
0x140033fef  mov     rcx, rsi; this
0x140033ff2  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140033ff7  call    ?ChildDeviceHasClassGuid@CTscSettings@@AEAAEKU_GUID@@@Z; CTscSettings::ChildDeviceHasClassGuid(ulong,_GUID)
0x140033ffc  test    al, al
0x140033ffe  jnz     short loc_14003407C
0x140034000  mov     ecx, [rbp+57h+pdnDevInst]; dnDevInst
0x140034003  lea     rax, [rbp+57h+var_88]
0x140034007  mov     [rsp+0C0h+ulFlags], 0; ulFlags
0x14003400f  lea     r9, [rbp+57h+Buffer]; Buffer
0x140034013  lea     r8, [rbp+57h+pulRegDataType]; pulRegDataType
0x140034017  mov     [rsp+0C0h+pulLength], rax; pulLength
0x14003401c  mov     edx, 9; ulProperty
0x140034021  mov     [rbp+57h+var_88], 4Eh ; 'N'
0x140034028  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x14003402e  test    eax, eax
0x140034030  jnz     short loc_140034067
0x140034032  cmp     [rbp+57h+pulRegDataType], 1
0x140034036  jnz     short loc_140034067
0x140034038  xorps   xmm0, xmm0
0x14003403b  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14003403f  lea     rcx, [rbp+57h+Buffer]; lpsz
0x140034043  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140034047  call    cs:__imp_CLSIDFromString
0x14003404d  test    eax, eax
0x14003404f  js      short loc_140034067
0x140034051  mov     r8d, 10h; Size
0x140034057  lea     rcx, [rbp+57h+pclsid]; Buf1
0x14003405b  mov     rdx, rdi; Buf2
0x14003405e  call    memcmp_0
0x140034063  test    eax, eax
0x140034065  jz      short loc_14003407C
0x140034067  mov     edx, [rbp+57h+pdnDevInst]; dnDevInst
0x14003406a  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x14003406e  xor     r8d, r8d; ulFlags
0x140034071  call    cs:__imp_CM_Get_Sibling
0x140034077  jmp     loc_140033FDD
0x14003407c  mov     bl, 1
0x14003407e  mov     al, bl
0x140034080  mov     rcx, [rbp+57h+var_20]
0x140034084  xor     rcx, rsp; StackCookie
0x140034087  call    __security_check_cookie
0x14003408c  mov     rbx, [rsp+0C0h+arg_18]
0x140034094  add     rsp, 0B0h
0x14003409b  pop     rdi
0x14003409c  pop     rsi
0x14003409d  pop     rbp
0x14003409e  retn
```
