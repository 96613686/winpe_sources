# DafStartWriteCeremonyData

- ea: `0x1800096a0`
- end: `0x1800097d6`
- name: `DafStartWriteCeremonyData`
- size: `310`
- prototype: `__int64 __usercall@<rax>(struct _DAC_CLIENT_CONTEXT *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001d38`
- `0x180002168`
- `0x180002f10`
- `0x1800096a0`

## import_xrefs

- `RPCRT4!Ndr64AsyncClientCall` at `0x18000978e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000978e`

## pseudocode

```c
__int64 __fastcall DafStartWriteCeremonyData(struct _DAC_CLIENT_CONTEXT *a1, int a2, __int64 a3, __int64 a4, void *a5)
{
  int v9; // ebx
  __int64 v11; // [rsp+28h] [rbp-50h]
  int v12; // [rsp+40h] [rbp-38h] BYREF
  struct _DAC_ASYNC_USER_CONTEXT *v13[6]; // [rsp+48h] [rbp-30h] BYREF

  v13[0] = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( !a1 || *((_WORD *)a1 + 4) != 3503 )
    return (unsigned int)-2147024809;
  if ( !a2 )
  {
    if ( !a3 )
      goto LABEL_10;
    return (unsigned int)-2147024809;
  }
  if ( !a3 )
    return (unsigned int)-2147024809;
LABEL_10:
  if ( !a4 )
    return (unsigned int)-2147024809;
  v9 = CreateAsyncUserContext((__int64)a1, 2u, a4, a5, &v12, (struct _RPC_ASYNC_STATE **)v13);
  if ( v9 < 0 )
  {
    CleanupAsyncUserContext(a1, v12, v13);
  }
  else
  {
    LODWORD(v11) = a2;
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
      5u,
      0,
      v13[0],
      (char *)a1 + 56,
      v11,
      a3);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800096a0  mov     [rsp+arg_0], rcx
0x1800096a5  push    rbx
0x1800096a6  push    rsi
0x1800096a7  push    rdi
0x1800096a8  push    r14
0x1800096aa  sub     rsp, 58h
0x1800096ae  mov     rbx, r9
0x1800096b1  mov     rsi, r8
0x1800096b4  mov     r14d, edx
0x1800096b7  mov     rdi, rcx
0x1800096ba  mov     [rsp+78h+var_30], 0
0x1800096c3  mov     [rsp+78h+var_38], 0
0x1800096cb  lea     rax, WPP_GLOBAL_Control
0x1800096d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096d9  cmp     rcx, rax
0x1800096dc  jz      short loc_1800096F9
0x1800096de  cmp     byte ptr [rcx+19h], 4
0x1800096e2  jb      short loc_1800096F9
0x1800096e4  mov     edx, 14h
0x1800096e9  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x1800096f0  mov     rcx, [rcx+10h]
0x1800096f4  call    WPP_SF_s
0x1800096f9  test    rdi, rdi
0x1800096fc  jz      loc_1800097C5
0x180009702  mov     eax, 0DAFh
0x180009707  cmp     [rdi+8], ax
0x18000970b  jnz     loc_1800097C5
0x180009711  test    r14d, r14d
0x180009714  jz      short loc_180009724
0x180009716  test    rsi, rsi
0x180009719  jz      loc_1800097C5
0x18000971f  test    r14d, r14d
0x180009722  jnz     short loc_18000972D
0x180009724  test    rsi, rsi
0x180009727  jnz     loc_1800097C5
0x18000972d  test    rbx, rbx
0x180009730  jz      loc_1800097C5
0x180009736  lea     rax, [rsp+78h+var_30]
0x18000973b  mov     [rsp+78h+var_50], rax
0x180009740  lea     rax, [rsp+78h+var_38]
0x180009745  mov     [rsp+78h+var_58], rax
0x18000974a  mov     r9, [rsp+78h+arg_20]
0x180009752  mov     r8, rbx
0x180009755  mov     edx, 2
0x18000975a  mov     rcx, rdi
0x18000975d  call    ?CreateAsyncUserContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@W4DAC_CALLBACK_TYPE@@PEAX2PEAHPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CreateAsyncUserContext(_DAC_CLIENT_CONTEXT *,DAC_CALLBACK_TYPE,void *,void *,int *,_DAC_ASYNC_USER_CONTEXT * *)
0x180009762  mov     ebx, eax
0x180009764  test    eax, eax
0x180009766  js      short loc_1800097AE
0x180009768  lea     rcx, [rdi+38h]
0x18000976c  mov     [rsp+78h+var_48], rsi
0x180009771  mov     dword ptr [rsp+78h+var_50], r14d
0x180009776  mov     [rsp+78h+var_58], rcx
0x18000977b  mov     r9, [rsp+78h+var_30]
0x180009780  xor     r8d, r8d; pReturnValue
0x180009783  lea     edx, [r8+5]; nProcNum
0x180009787  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000978e  call    cs:__imp_Ndr64AsyncClientCall
0x180009794  jmp     short loc_1800097AE
0x180009796  mov     ebx, eax
0x180009798  cmp     eax, 1
0x18000979b  jl      short loc_1800097A6
0x18000979d  movzx   ebx, ax
0x1800097a0  or      ebx, 80010000h
0x1800097a6  mov     rdi, [rsp+78h+arg_0]
0x1800097ae  test    ebx, ebx
0x1800097b0  jns     short loc_1800097CA
0x1800097b2  lea     r8, [rsp+78h+var_30]; struct _DAC_ASYNC_USER_CONTEXT **
0x1800097b7  mov     edx, [rsp+78h+var_38]; int
0x1800097bb  mov     rcx, rdi; struct _DAC_CLIENT_CONTEXT *
0x1800097be  call    ?CleanupAsyncUserContext@@YAXPEAU_DAC_CLIENT_CONTEXT@@HPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CleanupAsyncUserContext(_DAC_CLIENT_CONTEXT *,int,_DAC_ASYNC_USER_CONTEXT * *)
0x1800097c3  jmp     short loc_1800097CA
0x1800097c5  mov     ebx, 80070057h
0x1800097ca  mov     eax, ebx
0x1800097cc  add     rsp, 58h
0x1800097d0  pop     r14
0x1800097d2  pop     rdi
0x1800097d3  pop     rsi
0x1800097d4  pop     rbx
0x1800097d5  retn
0x18000c036  push    rbp
0x18000c038  sub     rsp, 40h
0x18000c03c  mov     rbp, rdx
0x18000c03f  mov     rcx, [rcx]
0x18000c042  mov     ecx, [rcx]; ExceptionCode
0x18000c044  call    cs:__imp_I_RpcExceptionFilter
0x18000c04a  nop
0x18000c04b  add     rsp, 40h
0x18000c04f  pop     rbp
0x18000c050  retn
```
