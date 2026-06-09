# DafStartReadCeremonyData

- ea: `0x180009450`
- end: `0x180009574`
- name: `DafStartReadCeremonyData`
- size: `292`
- prototype: `__int64 __fastcall(struct _DAC_CLIENT_CONTEXT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001d38`
- `0x180002168`
- `0x180002f10`
- `0x180009450`

## import_xrefs

- `RPCRT4!Ndr64AsyncClientCall` at `0x180009529`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180009529`

## pseudocode

```c
__int64 __fastcall DafStartReadCeremonyData(struct _DAC_CLIENT_CONTEXT *a1, __int64 a2, void *a3)
{
  int v6; // ebx
  struct _DAC_ASYNC_USER_CONTEXT *v8[3]; // [rsp+40h] [rbp-18h] BYREF
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v8[0] = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( a1 && *((_WORD *)a1 + 4) == 3503 && a2 )
  {
    v6 = CreateAsyncUserContext((__int64)a1, 1u, a2, a3, &v9, (struct _RPC_ASYNC_STATE **)v8);
    if ( v6 < 0 )
      CleanupAsyncUserContext(a1, v9, v8);
    else
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo, 4u, 0);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009450  mov     rax, rsp
0x180009453  mov     [rax+10h], rbx
0x180009457  mov     [rax+18h], rsi
0x18000945b  mov     [rax+8], rcx
0x18000945f  push    rdi
0x180009460  sub     rsp, 50h
0x180009464  mov     rsi, r8
0x180009467  mov     rbx, rdx
0x18000946a  mov     rdi, rcx
0x18000946d  mov     qword ptr [rax-18h], 0
0x180009475  mov     dword ptr [rax+20h], 0
0x18000947c  lea     rax, WPP_GLOBAL_Control
0x180009483  mov     rcx, cs:WPP_GLOBAL_Control
0x18000948a  cmp     rcx, rax
0x18000948d  jz      short loc_1800094AA
0x18000948f  cmp     byte ptr [rcx+19h], 4
0x180009493  jb      short loc_1800094AA
0x180009495  mov     edx, 12h
0x18000949a  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x1800094a1  mov     rcx, [rcx+10h]
0x1800094a5  call    WPP_SF_s
0x1800094aa  test    rdi, rdi
0x1800094ad  jz      loc_18000955D
0x1800094b3  mov     eax, 0DAFh
0x1800094b8  cmp     [rdi+8], ax
0x1800094bc  jnz     loc_18000955D
0x1800094c2  test    rbx, rbx
0x1800094c5  jz      loc_18000955D
0x1800094cb  lea     rax, [rsp+58h+var_18]
0x1800094d0  mov     [rsp+58h+var_30], rax
0x1800094d5  lea     rax, [rsp+58h+arg_18]
0x1800094da  mov     [rsp+58h+var_38], rax
0x1800094df  mov     r9, rsi
0x1800094e2  mov     r8, rbx
0x1800094e5  mov     edx, 1
0x1800094ea  mov     rcx, rdi
0x1800094ed  call    ?CreateAsyncUserContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@W4DAC_CALLBACK_TYPE@@PEAX2PEAHPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CreateAsyncUserContext(_DAC_CLIENT_CONTEXT *,DAC_CALLBACK_TYPE,void *,void *,int *,_DAC_ASYNC_USER_CONTEXT * *)
0x1800094f2  mov     ebx, eax
0x1800094f4  test    eax, eax
0x1800094f6  js      short loc_180009546
0x1800094f8  mov     r9, [rsp+58h+var_18]
0x1800094fd  lea     rcx, [r9+90h]
0x180009504  lea     r8, [rcx+8]
0x180009508  lea     r10, [rdi+38h]
0x18000950c  mov     [rsp+58h+var_28], rcx
0x180009511  mov     [rsp+58h+var_30], r8
0x180009516  mov     [rsp+58h+var_38], r10
0x18000951b  xor     r8d, r8d; pReturnValue
0x18000951e  lea     edx, [r8+4]; nProcNum
0x180009522  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180009529  call    cs:__imp_Ndr64AsyncClientCall
0x18000952f  jmp     short loc_180009546
0x180009531  mov     ebx, eax
0x180009533  cmp     eax, 1
0x180009536  jl      short loc_180009541
0x180009538  movzx   ebx, ax
0x18000953b  or      ebx, 80010000h
0x180009541  mov     rdi, [rsp+58h+arg_0]
0x180009546  test    ebx, ebx
0x180009548  jns     short loc_180009562
0x18000954a  lea     r8, [rsp+58h+var_18]; struct _DAC_ASYNC_USER_CONTEXT **
0x18000954f  mov     edx, [rsp+58h+arg_18]; int
0x180009553  mov     rcx, rdi; struct _DAC_CLIENT_CONTEXT *
0x180009556  call    ?CleanupAsyncUserContext@@YAXPEAU_DAC_CLIENT_CONTEXT@@HPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CleanupAsyncUserContext(_DAC_CLIENT_CONTEXT *,int,_DAC_ASYNC_USER_CONTEXT * *)
0x18000955b  jmp     short loc_180009562
0x18000955d  mov     ebx, 80070057h
0x180009562  mov     eax, ebx
0x180009564  mov     rbx, [rsp+58h+arg_8]
0x180009569  mov     rsi, [rsp+58h+arg_10]
0x18000956e  add     rsp, 50h
0x180009572  pop     rdi
0x180009573  retn
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
