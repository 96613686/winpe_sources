# RemoveDeviceEntry

- ea: `0x18000b560`
- end: `0x18000b73e`
- name: `RemoveDeviceEntry`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005850`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x18000b560`
- `0x18000b9b8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000b681`
- `RPCRT4!RpcBindingFree` at `0x18000b6f8`
- `RPCRT4!RpcBindingFree` at `0x18000b681`
- `RPCRT4!RpcBindingFree` at `0x18000b6f8`
- `RPCRT4!NdrClientCall3` at `0x18000b634`
- `RPCRT4!NdrClientCall3` at `0x18000b634`

## pseudocode

```c
__int64 __fastcall RemoveDeviceEntry(int a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int Pointer; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rax
  CLIENT_CALL_RETURN v8; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v11; // [rsp+88h] [rbp+20h]

  Binding = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  v4 = RpcBindForNfsClient(&Binding);
  Pointer = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return Pointer;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_20:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
        WPP_SF_d(v6[2], 88, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, Pointer);
      return Pointer;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v4);
LABEL_19:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  v11.Simple = 0;
  v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, Binding, a1, (int)v7 + 1, a2).Pointer;
  Pointer = (unsigned int)v8.Pointer;
  v11.Pointer = v8.Pointer;
  if ( LODWORD(v8.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        LODWORD(v8.Pointer));
    RpcBindingFree(&Binding);
    goto LABEL_19;
  }
  RpcBindingFree(&Binding);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000b560  mov     rax, rsp
0x18000b563  mov     [rax+8], rbx
0x18000b567  mov     [rax+10h], rsi
0x18000b56b  push    rdi
0x18000b56c  push    r14
0x18000b56e  push    r15
0x18000b570  sub     rsp, 50h
0x18000b574  mov     rsi, rdx
0x18000b577  mov     r14d, ecx
0x18000b57a  xor     r15d, r15d
0x18000b57d  mov     [rax+18h], r15
0x18000b581  lea     rdi, WPP_GLOBAL_Control
0x18000b588  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b58f  cmp     rcx, rdi
0x18000b592  jz      short loc_18000B5AE
0x18000b594  test    byte ptr [rcx+1Ch], 1
0x18000b598  jz      short loc_18000B5AE
0x18000b59a  lea     edx, [r15+53h]
0x18000b59e  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b5a5  mov     rcx, [rcx+10h]
0x18000b5a9  call    WPP_SF_
0x18000b5ae  lea     rcx, [rsp+68h+Binding]
0x18000b5b6  call    RpcBindForNfsClient
0x18000b5bb  mov     ebx, eax
0x18000b5bd  test    eax, eax
0x18000b5bf  jz      short loc_18000B5F8
0x18000b5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5c8  cmp     rcx, rdi
0x18000b5cb  jz      loc_18000B728
0x18000b5d1  test    byte ptr [rcx+1Ch], 2
0x18000b5d5  jz      loc_18000B705
0x18000b5db  mov     edx, 54h ; 'T'
0x18000b5e0  mov     r9d, eax
0x18000b5e3  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b5ea  mov     rcx, [rcx+10h]
0x18000b5ee  call    WPP_SF_d
0x18000b5f3  jmp     loc_18000B6FE
0x18000b5f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b5fc  inc     rax
0x18000b5ff  cmp     [rsi+rax*2], r15w
0x18000b604  jnz     short loc_18000B5FC
0x18000b606  inc     eax
0x18000b608  mov     [rsp+68h+arg_18], r15
0x18000b610  mov     [rsp+68h+var_38], rsi
0x18000b615  mov     [rsp+68h+var_40], eax
0x18000b619  mov     [rsp+68h+var_48], r14d
0x18000b61e  mov     r9, [rsp+68h+Binding]
0x18000b626  xor     r8d, r8d; pReturnValue
0x18000b629  lea     edx, [r8+2]; nProcNum
0x18000b62d  lea     rcx, pProxyInfo; pProxyInfo
0x18000b634  call    cs:__imp_NdrClientCall3
0x18000b63a  mov     rbx, rax
0x18000b63d  mov     [rsp+68h+arg_18], rax
0x18000b645  mov     [rsp+68h+var_20], eax
0x18000b649  test    eax, eax
0x18000b64b  jz      short loc_18000B679
0x18000b64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b654  cmp     rcx, rdi
0x18000b657  jz      short loc_18000B677
0x18000b659  test    byte ptr [rcx+1Ch], 2
0x18000b65d  jz      short loc_18000B677
0x18000b65f  mov     edx, 55h ; 'U'
0x18000b664  mov     r9d, eax
0x18000b667  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b66e  mov     rcx, [rcx+10h]
0x18000b672  call    WPP_SF_d
0x18000b677  jmp     short loc_18000B6F0
0x18000b679  lea     rcx, [rsp+68h+Binding]; Binding
0x18000b681  call    cs:__imp_RpcBindingFree
0x18000b687  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b68e  cmp     rcx, rdi
0x18000b691  jz      short loc_18000B6AE
0x18000b693  test    byte ptr [rcx+1Ch], 1
0x18000b697  jz      short loc_18000B6AE
0x18000b699  mov     edx, 57h ; 'W'
0x18000b69e  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b6a5  mov     rcx, [rcx+10h]
0x18000b6a9  call    WPP_SF_
0x18000b6ae  xor     eax, eax
0x18000b6b0  jmp     short loc_18000B72A
0x18000b6b2  mov     ebx, eax
0x18000b6b4  mov     [rsp+68h+var_20], eax
0x18000b6b8  lea     rdx, WPP_GLOBAL_Control
0x18000b6bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6c6  cmp     rcx, rdx
0x18000b6c9  jz      short loc_18000B6E9
0x18000b6cb  test    byte ptr [rcx+1Ch], 2
0x18000b6cf  jz      short loc_18000B6E9
0x18000b6d1  mov     edx, 56h ; 'V'
0x18000b6d6  mov     r9d, eax
0x18000b6d9  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b6e0  mov     rcx, [rcx+10h]
0x18000b6e4  call    WPP_SF_d
0x18000b6e9  lea     rdi, WPP_GLOBAL_Control
0x18000b6f0  lea     rcx, [rsp+68h+Binding]; Binding
0x18000b6f8  call    cs:__imp_RpcBindingFree
0x18000b6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b705  cmp     rcx, rdi
0x18000b708  jz      short loc_18000B728
0x18000b70a  test    byte ptr [rcx+1Ch], 2
0x18000b70e  jz      short loc_18000B728
0x18000b710  mov     edx, 58h ; 'X'
0x18000b715  mov     r9d, ebx
0x18000b718  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b71f  mov     rcx, [rcx+10h]
0x18000b723  call    WPP_SF_d
0x18000b728  mov     eax, ebx
0x18000b72a  mov     rbx, [rsp+68h+arg_0]
0x18000b72f  mov     rsi, [rsp+68h+arg_8]
0x18000b734  add     rsp, 50h
0x18000b738  pop     r15
0x18000b73a  pop     r14
0x18000b73c  pop     rdi
0x18000b73d  retn
0x18001217a  push    rbp
0x18001217c  sub     rsp, 40h
0x180012180  mov     rbp, rdx
0x180012183  mov     rax, [rcx]
0x180012186  mov     edx, [rax]
0x180012188  mov     dword ptr [rbp+40h], 0
0x18001218f  mov     dword ptr [rbp+40h], 0
0x180012196  mov     eax, [rbp+40h]
0x180012199  cmp     eax, 8
0x18001219c  jge     short loc_1800121C1
0x18001219e  movsxd  rcx, dword ptr [rbp+40h]
0x1800121a2  lea     rax, FatalExceptions
0x1800121a9  cmp     edx, [rax+rcx*4]
0x1800121ac  jnz     short loc_1800121B7
0x1800121ae  mov     dword ptr [rbp+44h], 0
0x1800121b5  jmp     short loc_1800121C8
0x1800121b7  mov     eax, [rbp+40h]
0x1800121ba  inc     eax
0x1800121bc  mov     [rbp+40h], eax
0x1800121bf  jmp     short loc_180012196
0x1800121c1  mov     dword ptr [rbp+44h], 1
0x1800121c8  mov     eax, [rbp+44h]
0x1800121cb  add     rsp, 40h
0x1800121cf  pop     rbp
0x1800121d0  retn
```
