# DafStartRemoveAssociation

- ea: `0x180009580`
- end: `0x18000968b`
- name: `DafStartRemoveAssociation`
- size: `267`
- prototype: `__int64 __fastcall(struct _DAC_CLIENT_CONTEXT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001d38`
- `0x180002168`
- `0x180002f10`
- `0x180009580`

## import_xrefs

- `RPCRT4!Ndr64AsyncClientCall` at `0x180009640`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180009640`

## pseudocode

```c
__int64 __fastcall DafStartRemoveAssociation(struct _DAC_CLIENT_CONTEXT *a1, __int64 a2, void *a3)
{
  int v6; // ebx
  struct _DAC_ASYNC_USER_CONTEXT *v8[3]; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+68h] [rbp+20h] BYREF

  v8[0] = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( a1 && *((_WORD *)a1 + 4) == 3503 && a2 )
  {
    v6 = CreateAsyncUserContext((__int64)a1, 5u, a2, a3, &v9, (struct _RPC_ASYNC_STATE **)v8);
    if ( v6 < 0 )
      CleanupAsyncUserContext(a1, v9, v8);
    else
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo, 0xBu, 0, v8[0], (char *)a1 + 56);
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
0x180009580  mov     rax, rsp
0x180009583  mov     [rax+10h], rbx
0x180009587  mov     [rax+18h], rsi
0x18000958b  mov     [rax+8], rcx
0x18000958f  push    rdi
0x180009590  sub     rsp, 40h
0x180009594  mov     rsi, r8
0x180009597  mov     rbx, rdx
0x18000959a  mov     rdi, rcx
0x18000959d  mov     qword ptr [rax-18h], 0
0x1800095a5  mov     dword ptr [rax+20h], 0
0x1800095ac  lea     rax, WPP_GLOBAL_Control
0x1800095b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095ba  cmp     rcx, rax
0x1800095bd  jz      short loc_1800095DA
0x1800095bf  cmp     byte ptr [rcx+19h], 4
0x1800095c3  jb      short loc_1800095DA
0x1800095c5  mov     edx, 1Eh
0x1800095ca  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x1800095d1  mov     rcx, [rcx+10h]
0x1800095d5  call    WPP_SF_s
0x1800095da  test    rdi, rdi
0x1800095dd  jz      loc_180009674
0x1800095e3  mov     eax, 0DAFh
0x1800095e8  cmp     [rdi+8], ax
0x1800095ec  jnz     loc_180009674
0x1800095f2  test    rbx, rbx
0x1800095f5  jz      short loc_180009674
0x1800095f7  lea     rax, [rsp+48h+var_18]
0x1800095fc  mov     [rsp+48h+var_20], rax
0x180009601  lea     rax, [rsp+48h+arg_18]
0x180009606  mov     [rsp+48h+var_28], rax
0x18000960b  mov     r9, rsi
0x18000960e  mov     r8, rbx
0x180009611  mov     edx, 5
0x180009616  mov     rcx, rdi
0x180009619  call    ?CreateAsyncUserContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@W4DAC_CALLBACK_TYPE@@PEAX2PEAHPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CreateAsyncUserContext(_DAC_CLIENT_CONTEXT *,DAC_CALLBACK_TYPE,void *,void *,int *,_DAC_ASYNC_USER_CONTEXT * *)
0x18000961e  mov     ebx, eax
0x180009620  test    eax, eax
0x180009622  js      short loc_18000965D
0x180009624  lea     rcx, [rdi+38h]
0x180009628  mov     [rsp+48h+var_28], rcx
0x18000962d  mov     r9, [rsp+48h+var_18]
0x180009632  xor     r8d, r8d; pReturnValue
0x180009635  lea     edx, [r8+0Bh]; nProcNum
0x180009639  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180009640  call    cs:__imp_Ndr64AsyncClientCall
0x180009646  jmp     short loc_18000965D
0x180009648  mov     ebx, eax
0x18000964a  cmp     eax, 1
0x18000964d  jl      short loc_180009658
0x18000964f  movzx   ebx, ax
0x180009652  or      ebx, 80010000h
0x180009658  mov     rdi, [rsp+48h+arg_0]
0x18000965d  test    ebx, ebx
0x18000965f  jns     short loc_180009679
0x180009661  lea     r8, [rsp+48h+var_18]; struct _DAC_ASYNC_USER_CONTEXT **
0x180009666  mov     edx, [rsp+48h+arg_18]; int
0x18000966a  mov     rcx, rdi; struct _DAC_CLIENT_CONTEXT *
0x18000966d  call    ?CleanupAsyncUserContext@@YAXPEAU_DAC_CLIENT_CONTEXT@@HPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CleanupAsyncUserContext(_DAC_CLIENT_CONTEXT *,int,_DAC_ASYNC_USER_CONTEXT * *)
0x180009672  jmp     short loc_180009679
0x180009674  mov     ebx, 80070057h
0x180009679  mov     eax, ebx
0x18000967b  mov     rbx, [rsp+48h+arg_8]
0x180009680  mov     rsi, [rsp+48h+arg_10]
0x180009685  add     rsp, 40h
0x180009689  pop     rdi
0x18000968a  retn
0x18000c058  push    rbp
0x18000c05a  sub     rsp, 30h
0x18000c05e  mov     rbp, rdx
0x18000c061  mov     rcx, [rcx]
0x18000c064  mov     ecx, [rcx]; ExceptionCode
0x18000c066  call    cs:__imp_I_RpcExceptionFilter
0x18000c06c  nop
0x18000c06d  add     rsp, 30h
0x18000c071  pop     rbp
0x18000c072  retn
```
