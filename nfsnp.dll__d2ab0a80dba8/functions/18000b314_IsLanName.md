# IsLanName

- ea: `0x18000b314`
- end: `0x18000b526`
- name: `IsLanName`
- size: `530`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180005d70`
- `0x180007fd0`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x180008aa0`
- `0x18000b314`
- `0x18000b560`
- `0x18000b9b8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000b46c`
- `RPCRT4!RpcBindingFree` at `0x18000b4e6`
- `RPCRT4!RpcBindingFree` at `0x18000b46c`
- `RPCRT4!RpcBindingFree` at `0x18000b4e6`
- `RPCRT4!NdrClientCall3` at `0x18000b3ec`
- `RPCRT4!NdrClientCall3` at `0x18000b3ec`

## pseudocode

```c
__int64 __fastcall IsLanName(__int64 a1)
{
  int v2; // eax
  int Pointer; // ebx
  _UNKNOWN **v4; // rcx
  __int64 v5; // rax
  CLIENT_CALL_RETURN v6; // rax
  int v8; // [rsp+78h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+88h] [rbp+20h]

  v8 = 0;
  Binding = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, a1);
  v2 = RpcBindForNfsClient(&Binding);
  Pointer = v2;
  if ( v2 )
  {
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_26:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
        WPP_SF_d((TRACEHANDLE)v4[2], 0x43u, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, Pointer);
      return 0;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x3Eu, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v2);
LABEL_25:
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  v10.Simple = 0;
  v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 7u, 0, Binding, (int)v5 + 1, a1, &v8).Pointer;
  Pointer = (int)v6.Pointer;
  v10.Pointer = v6.Pointer;
  if ( LODWORD(v6.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x3Fu, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v6.Simple);
LABEL_24:
    RpcBindingFree(&Binding);
    goto LABEL_25;
  }
  if ( v8 != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x40u, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
    goto LABEL_24;
  }
  RpcBindingFree(&Binding);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x42u, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x18000b314  mov     rax, rsp
0x18000b317  mov     [rax+8], rbx
0x18000b31b  push    rsi
0x18000b31c  push    rdi
0x18000b31d  push    r14
0x18000b31f  sub     rsp, 50h
0x18000b323  mov     rsi, rcx
0x18000b326  xor     r14d, r14d
0x18000b329  mov     [rax+10h], r14d
0x18000b32d  mov     [rax+18h], r14
0x18000b331  lea     rdi, WPP_GLOBAL_Control
0x18000b338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b33f  cmp     rcx, rdi
0x18000b342  jz      short loc_18000B361
0x18000b344  test    byte ptr [rcx+1Ch], 1
0x18000b348  jz      short loc_18000B361
0x18000b34a  lea     edx, [r14+3Dh]
0x18000b34e  mov     r9, rsi
0x18000b351  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b358  mov     rcx, [rcx+10h]
0x18000b35c  call    WPP_SF_S
0x18000b361  lea     rcx, [rsp+68h+Binding]
0x18000b369  call    RpcBindForNfsClient
0x18000b36e  mov     ebx, eax
0x18000b370  test    eax, eax
0x18000b372  jz      short loc_18000B3AB
0x18000b374  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b37b  cmp     rcx, rdi
0x18000b37e  jz      loc_18000B516
0x18000b384  test    byte ptr [rcx+1Ch], 2
0x18000b388  jz      loc_18000B4F3
0x18000b38e  mov     edx, 3Eh ; '>'
0x18000b393  mov     r9d, eax
0x18000b396  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b39d  mov     rcx, [rcx+10h]
0x18000b3a1  call    WPP_SF_d
0x18000b3a6  jmp     loc_18000B4EC
0x18000b3ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b3af  inc     rax
0x18000b3b2  cmp     [rsi+rax*2], r14w
0x18000b3b7  jnz     short loc_18000B3AF
0x18000b3b9  inc     eax
0x18000b3bb  mov     [rsp+68h+arg_18], r14
0x18000b3c3  lea     rcx, [rsp+68h+arg_8]
0x18000b3c8  mov     [rsp+68h+var_38], rcx
0x18000b3cd  mov     [rsp+68h+var_40], rsi
0x18000b3d2  mov     [rsp+68h+var_48], eax
0x18000b3d6  mov     r9, [rsp+68h+Binding]
0x18000b3de  xor     r8d, r8d; pReturnValue
0x18000b3e1  lea     edx, [r8+7]; nProcNum
0x18000b3e5  lea     rcx, pProxyInfo; pProxyInfo
0x18000b3ec  call    cs:__imp_NdrClientCall3
0x18000b3f2  mov     rbx, rax
0x18000b3f5  mov     [rsp+68h+arg_18], rax
0x18000b3fd  mov     [rsp+68h+var_20], eax
0x18000b401  test    eax, eax
0x18000b403  jz      short loc_18000B434
0x18000b405  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b40c  cmp     rcx, rdi
0x18000b40f  jz      short loc_18000B42F
0x18000b411  test    byte ptr [rcx+1Ch], 2
0x18000b415  jz      short loc_18000B42F
0x18000b417  mov     edx, 3Fh ; '?'
0x18000b41c  mov     r9d, eax
0x18000b41f  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b426  mov     rcx, [rcx+10h]
0x18000b42a  call    WPP_SF_d
0x18000b42f  jmp     loc_18000B4DE
0x18000b434  cmp     [rsp+68h+arg_8], 1
0x18000b439  jz      short loc_18000B464
0x18000b43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b442  cmp     rcx, rdi
0x18000b445  jz      short loc_18000B462
0x18000b447  test    byte ptr [rcx+1Ch], 2
0x18000b44b  jz      short loc_18000B462
0x18000b44d  mov     edx, 40h ; '@'
0x18000b452  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b459  mov     rcx, [rcx+10h]
0x18000b45d  call    WPP_SF_
0x18000b462  jmp     short loc_18000B4DE
0x18000b464  lea     rcx, [rsp+68h+Binding]; Binding
0x18000b46c  call    cs:__imp_RpcBindingFree
0x18000b472  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b479  cmp     rcx, rdi
0x18000b47c  jz      short loc_18000B499
0x18000b47e  test    byte ptr [rcx+1Ch], 1
0x18000b482  jz      short loc_18000B499
0x18000b484  mov     edx, 42h ; 'B'
0x18000b489  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b490  mov     rcx, [rcx+10h]
0x18000b494  call    WPP_SF_
0x18000b499  mov     eax, 1
0x18000b49e  jmp     short loc_18000B518
0x18000b4a0  mov     ebx, eax
0x18000b4a2  mov     [rsp+68h+var_20], eax
0x18000b4a6  lea     rdx, WPP_GLOBAL_Control
0x18000b4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4b4  cmp     rcx, rdx
0x18000b4b7  jz      short loc_18000B4D7
0x18000b4b9  test    byte ptr [rcx+1Ch], 2
0x18000b4bd  jz      short loc_18000B4D7
0x18000b4bf  mov     edx, 41h ; 'A'
0x18000b4c4  mov     r9d, eax
0x18000b4c7  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b4ce  mov     rcx, [rcx+10h]
0x18000b4d2  call    WPP_SF_d
0x18000b4d7  lea     rdi, WPP_GLOBAL_Control
0x18000b4de  lea     rcx, [rsp+68h+Binding]; Binding
0x18000b4e6  call    cs:__imp_RpcBindingFree
0x18000b4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4f3  cmp     rcx, rdi
0x18000b4f6  jz      short loc_18000B516
0x18000b4f8  test    byte ptr [rcx+1Ch], 2
0x18000b4fc  jz      short loc_18000B516
0x18000b4fe  mov     edx, 43h ; 'C'
0x18000b503  mov     r9d, ebx
0x18000b506  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b50d  mov     rcx, [rcx+10h]
0x18000b511  call    WPP_SF_d
0x18000b516  xor     eax, eax
0x18000b518  mov     rbx, [rsp+68h+arg_0]
0x18000b51d  add     rsp, 50h
0x18000b521  pop     r14
0x18000b523  pop     rdi
0x18000b524  pop     rsi
0x18000b525  retn
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
