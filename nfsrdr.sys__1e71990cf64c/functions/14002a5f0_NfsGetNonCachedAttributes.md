# NfsGetNonCachedAttributes

- ea: `0x14002a5f0`
- end: `0x14002a9da`
- name: `NfsGetNonCachedAttributes`
- size: `1002`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400273f0`

## callees

- `0x14000fa80`
- `0x14000fb40`
- `0x140011f84`
- `0x140013ac0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140022220`
- `0x14002a5f0`
- `0x14002ddac`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `rpcxdr!OncRpcBuildCall` at `0x14002a709`
- `rpcxdr!OncRpcBuildCall` at `0x14002a709`
- `rpcxdr!OncRpcDestroy` at `0x14002a8f7`
- `rpcxdr!OncRpcDestroy` at `0x14002a909`
- `rpcxdr!OncRpcDestroy` at `0x14002a919`
- `rpcxdr!OncRpcDestroy` at `0x14002a980`
- `rpcxdr!OncRpcDestroy` at `0x14002a8f7`
- `rpcxdr!OncRpcDestroy` at `0x14002a909`
- `rpcxdr!OncRpcDestroy` at `0x14002a919`
- `rpcxdr!OncRpcDestroy` at `0x14002a980`

## pseudocode

```c
__int64 __fastcall NfsGetNonCachedAttributes(__int64 a1, _OWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r14
  __int128 v9; // xmm0
  unsigned int *v10; // rbx
  bool v11; // si
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int64 v15; // r8
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // edi
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // [rsp+50h] [rbp-79h] BYREF
  __int64 v25; // [rsp+58h] [rbp-71h] BYREF
  _QWORD v26[12]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-9h] BYREF
  int v28; // [rsp+D0h] [rbp+7h]

  v4 = *(_QWORD *)(a1 + 48);
  v25 = 0;
  v24 = 0;
  v9 = *(_OWORD *)(v4 + 1376);
  v28 = *(_DWORD *)(v4 + 1392);
  v27 = v9;
  memset(v26, 0, 0x54u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v10 = *(unsigned int **)(a1 + 32);
  v11 = v10[22] == 3;
  if ( !v10 )
    return 3221225662LL;
  v13 = a2[1];
  *(_OWORD *)&v26[1] = *a2;
  *(_OWORD *)&v26[5] = a2[2];
  LODWORD(v26[0]) = 1;
  v14 = *(_OWORD *)((char *)a2 + 60);
  *(_OWORD *)&v26[3] = v13;
  *(_OWORD *)&v26[7] = a2[3];
  *(_OWORD *)((char *)&v26[8] + 4) = v14;
  if ( (int)OncRpcBuildCall(&v25, v10 + 29, v10[20], v10[21], v10[22], 1, 68, v26) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v16 = -1073741670;
    goto LABEL_47;
  }
  LOBYTE(v15) = v11;
  XdrEncodeNfsFileHandleUnsafe(v25, a3, v15);
  v17 = v25;
  if ( *(int *)(v25 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v17 = v25;
    }
    v16 = *(_DWORD *)(v17 + 264);
    goto LABEL_46;
  }
  v16 = NfsSendWaitReply(v4, (unsigned int)&v24, 0, 0, (__int64)&v27, (__int64)(v10 + 18), v25, (__int64)&v24, 0);
  if ( v16 < 0 || !v24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
        (unsigned int)v16);
    goto LABEL_45;
  }
  v16 = OncRpcMapRpcStatusToNtStatus(v24);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_37;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, (unsigned int)v16);
LABEL_36:
    v18 = v24;
LABEL_37:
    OncRpcDestroy(v18);
LABEL_45:
    v17 = v25;
LABEL_46:
    OncRpcDestroy(v17);
LABEL_47:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        48,
        WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
        (unsigned int)v16);
    return (unsigned int)v16;
  }
  v19 = XdrDecodeInt(v18);
  v18 = v24;
  v21 = v19;
  v16 = *(_DWORD *)(v24 + 264);
  if ( v16 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_37;
    v23 = 44;
    goto LABEL_35;
  }
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, v19);
    v16 = MapNFSStatusToNtStatus(v21);
    goto LABEL_37;
  }
  LOBYTE(v20) = v11;
  XdrDecodeNfsFileAttributes(v24, a4, v20);
  v18 = v24;
  v16 = *(_DWORD *)(v24 + 264);
  if ( v16 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_37;
    v23 = 46;
LABEL_35:
    WPP_SF_(v22->AttachedDevice, v23, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_36;
  }
  OncRpcDestroy(v25);
  OncRpcDestroy(v24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14002a5f0  push    rbp
0x14002a5f2  push    rbx
0x14002a5f3  push    rsi
0x14002a5f4  push    rdi
0x14002a5f5  push    r12
0x14002a5f7  push    r13
0x14002a5f9  push    r14
0x14002a5fb  push    r15
0x14002a5fd  lea     rbp, [rsp-1Fh]
0x14002a602  sub     rsp, 0E8h
0x14002a609  mov     rax, cs:__security_cookie
0x14002a610  xor     rax, rsp
0x14002a613  mov     [rbp+57h+var_48], rax
0x14002a617  mov     r14, [rcx+30h]
0x14002a61b  mov     r15, r8
0x14002a61e  mov     [rbp+57h+var_C8], 0
0x14002a626  mov     rdi, rdx
0x14002a629  mov     [rbp+57h+var_D0], 0
0x14002a631  mov     rbx, rcx
0x14002a634  xor     edx, edx; Val
0x14002a636  lea     rcx, [rbp+57h+var_C0]; void *
0x14002a63a  mov     eax, [r14+570h]
0x14002a641  mov     r12, r9
0x14002a644  movups  xmm0, xmmword ptr [r14+560h]
0x14002a64c  mov     [rbp+57h+var_50], eax
0x14002a64f  xor     eax, eax
0x14002a651  mov     [rbp+57h+var_BC], eax
0x14002a654  movups  [rbp+57h+var_60], xmm0
0x14002a658  lea     r8d, [rax+54h]; Size
0x14002a65c  call    memset
0x14002a661  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a668  lea     r13, WPP_GLOBAL_Control
0x14002a66f  cmp     rcx, r13
0x14002a672  jz      short loc_14002A690
0x14002a674  mov     eax, [rcx+2Ch]
0x14002a677  test    al, 40h
0x14002a679  jz      short loc_14002A690
0x14002a67b  mov     rcx, [rcx+18h]
0x14002a67f  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a686  mov     edx, 27h ; '''
0x14002a68b  call    WPP_SF_
0x14002a690  mov     rbx, [rbx+20h]
0x14002a694  cmp     dword ptr [rbx+58h], 3
0x14002a698  setz    sil
0x14002a69c  test    rbx, rbx
0x14002a69f  jnz     short loc_14002A6AB
0x14002a6a1  mov     eax, 0C00000BEh
0x14002a6a6  jmp     loc_14002A9B9
0x14002a6ab  movaps  xmm0, xmmword ptr [rdi]
0x14002a6ae  lea     rax, [rbp+57h+var_C0]
0x14002a6b2  movaps  xmm1, xmmword ptr [rdi+10h]
0x14002a6b6  lea     rdx, [rbx+74h]
0x14002a6ba  movups  [rbp+57h+var_B8], xmm0
0x14002a6be  lea     rcx, [rbp+57h+var_C8]
0x14002a6c2  mov     [rsp+120h+var_E8], rax
0x14002a6c7  movaps  xmm0, xmmword ptr [rdi+20h]
0x14002a6cb  movups  [rbp+57h+var_98], xmm0
0x14002a6cf  mov     [rbp+57h+var_C0], 1
0x14002a6d6  movups  xmm0, xmmword ptr [rdi+3Ch]
0x14002a6da  mov     dword ptr [rsp+120h+var_F0], 44h ; 'D'
0x14002a6e2  movups  [rbp+57h+var_A8], xmm1
0x14002a6e6  mov     dword ptr [rsp+120h+var_F8], 1
0x14002a6ee  movaps  xmm1, xmmword ptr [rdi+30h]
0x14002a6f2  movups  [rbp+57h+var_88], xmm1
0x14002a6f6  movups  [rbp+57h+var_88+0Ch], xmm0
0x14002a6fa  mov     eax, [rbx+58h]
0x14002a6fd  mov     r9d, [rbx+54h]
0x14002a701  mov     r8d, [rbx+50h]
0x14002a705  mov     dword ptr [rsp+120h+var_100], eax
0x14002a709  call    cs:__imp_OncRpcBuildCall
0x14002a710  nop     dword ptr [rax+rax+00h]
0x14002a715  test    eax, eax
0x14002a717  jns     short loc_14002A74B
0x14002a719  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a720  cmp     rcx, r13
0x14002a723  jz      short loc_14002A741
0x14002a725  mov     eax, [rcx+2Ch]
0x14002a728  test    al, 1
0x14002a72a  jz      short loc_14002A741
0x14002a72c  mov     rcx, [rcx+18h]
0x14002a730  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a737  mov     edx, 28h ; '('
0x14002a73c  call    WPP_SF_
0x14002a741  mov     ebx, 0C000009Ah
0x14002a746  jmp     loc_14002A98C
0x14002a74b  mov     rcx, [rbp+57h+var_C8]
0x14002a74f  mov     r8b, sil
0x14002a752  mov     rdx, r15
0x14002a755  call    XdrEncodeNfsFileHandleUnsafe
0x14002a75a  mov     rcx, [rbp+57h+var_C8]
0x14002a75e  cmp     dword ptr [rcx+108h], 0
0x14002a765  jge     short loc_14002A79F
0x14002a767  mov     r9, cs:WPP_GLOBAL_Control
0x14002a76e  cmp     r9, r13
0x14002a771  jz      short loc_14002A794
0x14002a773  mov     eax, [r9+2Ch]
0x14002a777  test    al, 1
0x14002a779  jz      short loc_14002A794
0x14002a77b  mov     rcx, [r9+18h]
0x14002a77f  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a786  mov     edx, 29h ; ')'
0x14002a78b  call    WPP_SF_
0x14002a790  mov     rcx, [rbp+57h+var_C8]
0x14002a794  mov     ebx, [rcx+108h]
0x14002a79a  jmp     loc_14002A980
0x14002a79f  mov     [rsp+120h+var_E0], 0
0x14002a7a7  lea     rdx, [rbp+57h+var_D0]
0x14002a7ab  mov     [rsp+120h+var_E8], rdx
0x14002a7b0  lea     rax, [rbx+48h]
0x14002a7b4  mov     [rsp+120h+var_F0], rcx
0x14002a7b9  xor     r9d, r9d
0x14002a7bc  mov     [rsp+120h+var_F8], rax
0x14002a7c1  xor     r8d, r8d
0x14002a7c4  lea     rax, [rbp+57h+var_60]
0x14002a7c8  mov     rcx, r14
0x14002a7cb  mov     [rsp+120h+var_100], rax
0x14002a7d0  call    NfsSendWaitReply
0x14002a7d5  mov     ebx, eax
0x14002a7d7  test    eax, eax
0x14002a7d9  js      loc_14002A951
0x14002a7df  mov     r9, [rbp+57h+var_D0]
0x14002a7e3  test    r9, r9
0x14002a7e6  jz      loc_14002A951
0x14002a7ec  mov     rcx, r9
0x14002a7ef  call    OncRpcMapRpcStatusToNtStatus
0x14002a7f4  mov     ebx, eax
0x14002a7f6  test    eax, eax
0x14002a7f8  jns     short loc_14002A832
0x14002a7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a801  cmp     rcx, r13
0x14002a804  jz      loc_14002A8F4
0x14002a80a  mov     eax, [rcx+2Ch]
0x14002a80d  test    al, 1
0x14002a80f  jz      loc_14002A8F4
0x14002a815  mov     rcx, [rcx+18h]
0x14002a819  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a820  mov     edx, 2Bh ; '+'
0x14002a825  mov     r9d, ebx
0x14002a828  call    WPP_SF_d
0x14002a82d  jmp     loc_14002A8F0
0x14002a832  mov     rcx, r9
0x14002a835  call    XdrDecodeInt
0x14002a83a  mov     r9, [rbp+57h+var_D0]
0x14002a83e  mov     edi, eax
0x14002a840  mov     ebx, [r9+108h]
0x14002a847  test    ebx, ebx
0x14002a849  jns     short loc_14002A86D
0x14002a84b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a852  cmp     rcx, r13
0x14002a855  jz      loc_14002A8F4
0x14002a85b  mov     eax, [rcx+2Ch]
0x14002a85e  test    al, 1
0x14002a860  jz      loc_14002A8F4
0x14002a866  mov     edx, 2Ch ; ','
0x14002a86b  jmp     short loc_14002A8E0
0x14002a86d  test    edi, edi
0x14002a86f  jz      short loc_14002A8AB
0x14002a871  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a878  cmp     rcx, r13
0x14002a87b  jz      short loc_14002A8A0
0x14002a87d  mov     eax, [rcx+2Ch]
0x14002a880  test    al, 1
0x14002a882  jz      short loc_14002A8A0
0x14002a884  mov     rcx, [rcx+18h]
0x14002a888  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a88f  mov     edx, 2Dh ; '-'
0x14002a894  mov     r9d, edi
0x14002a897  call    WPP_SF_d
0x14002a89c  mov     r9, [rbp+57h+var_D0]
0x14002a8a0  mov     ecx, edi
0x14002a8a2  call    MapNFSStatusToNtStatus
0x14002a8a7  mov     ebx, eax
0x14002a8a9  jmp     short loc_14002A8F4
0x14002a8ab  mov     r8b, sil
0x14002a8ae  mov     rdx, r12
0x14002a8b1  mov     rcx, r9
0x14002a8b4  call    XdrDecodeNfsFileAttributes
0x14002a8b9  mov     r9, [rbp+57h+var_D0]
0x14002a8bd  mov     ebx, [r9+108h]
0x14002a8c4  test    ebx, ebx
0x14002a8c6  jns     short loc_14002A905
0x14002a8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a8cf  cmp     rcx, r13
0x14002a8d2  jz      short loc_14002A8F4
0x14002a8d4  mov     eax, [rcx+2Ch]
0x14002a8d7  test    al, 1
0x14002a8d9  jz      short loc_14002A8F4
0x14002a8db  mov     edx, 2Eh ; '.'
0x14002a8e0  mov     rcx, [rcx+18h]
0x14002a8e4  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a8eb  call    WPP_SF_
0x14002a8f0  mov     r9, [rbp+57h+var_D0]
0x14002a8f4  mov     rcx, r9
0x14002a8f7  call    cs:__imp_OncRpcDestroy
0x14002a8fe  nop     dword ptr [rax+rax+00h]
0x14002a903  jmp     short loc_14002A97C
0x14002a905  mov     rcx, [rbp+57h+var_C8]
0x14002a909  call    cs:__imp_OncRpcDestroy
0x14002a910  nop     dword ptr [rax+rax+00h]
0x14002a915  mov     rcx, [rbp+57h+var_D0]
0x14002a919  call    cs:__imp_OncRpcDestroy
0x14002a920  nop     dword ptr [rax+rax+00h]
0x14002a925  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a92c  cmp     rcx, r13
0x14002a92f  jz      short loc_14002A94D
0x14002a931  mov     eax, [rcx+2Ch]
0x14002a934  test    al, 40h
0x14002a936  jz      short loc_14002A94D
0x14002a938  mov     rcx, [rcx+18h]
0x14002a93c  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a943  mov     edx, 2Fh ; '/'
0x14002a948  call    WPP_SF_
0x14002a94d  xor     eax, eax
0x14002a94f  jmp     short loc_14002A9B9
0x14002a951  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a958  cmp     rcx, r13
0x14002a95b  jz      short loc_14002A97C
0x14002a95d  mov     eax, [rcx+2Ch]
0x14002a960  test    al, 1
0x14002a962  jz      short loc_14002A97C
0x14002a964  mov     rcx, [rcx+18h]
0x14002a968  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a96f  mov     edx, 2Ah ; '*'
0x14002a974  mov     r9d, ebx
0x14002a977  call    WPP_SF_d
0x14002a97c  mov     rcx, [rbp+57h+var_C8]
0x14002a980  call    cs:__imp_OncRpcDestroy
0x14002a987  nop     dword ptr [rax+rax+00h]
0x14002a98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a993  cmp     rcx, r13
0x14002a996  jz      short loc_14002A9B7
0x14002a998  mov     eax, [rcx+2Ch]
0x14002a99b  test    al, 1
0x14002a99d  jz      short loc_14002A9B7
0x14002a99f  mov     rcx, [rcx+18h]
0x14002a9a3  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002a9aa  mov     edx, 30h ; '0'
0x14002a9af  mov     r9d, ebx
0x14002a9b2  call    WPP_SF_d
0x14002a9b7  mov     eax, ebx
0x14002a9b9  mov     rcx, [rbp+57h+var_48]
0x14002a9bd  xor     rcx, rsp; StackCookie
0x14002a9c0  call    __security_check_cookie
0x14002a9c5  add     rsp, 0E8h
0x14002a9cc  pop     r15
0x14002a9ce  pop     r14
0x14002a9d0  pop     r13
0x14002a9d2  pop     r12
0x14002a9d4  pop     rdi
0x14002a9d5  pop     rsi
0x14002a9d6  pop     rbx
0x14002a9d7  pop     rbp
0x14002a9d8  retn
```
