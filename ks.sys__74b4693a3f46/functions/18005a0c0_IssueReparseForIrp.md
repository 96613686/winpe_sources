# IssueReparseForIrp

- ea: `0x18005a0c0`
- end: `0x18005a2ff`
- name: `IssueReparseForIrp`
- size: `575`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800597dc`
- `0x180059858`
- `0x180059c50`

## callees

- `0x18000ae68`
- `0x18000b7bc`
- `0x180010de4`
- `0x180019fc0`
- `0x18005a0c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005a151`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a255`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a151`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a255`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a16f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a16f`

## pseudocode

```c
__int64 __fastcall IssueReparseForIrp(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r8
  unsigned int v9; // esi
  __int64 v10; // rax
  unsigned __int64 v11; // rbp
  __int64 v12; // rcx
  PVOID PoolWithTag; // rax
  int v14; // edx
  PVOID v15; // r15
  __int64 v16; // rax
  wchar_t *v17; // rcx
  HRESULT v18; // eax
  int v19; // r8d
  __int64 v20; // rdx
  _WORD *v21; // rcx

  v2 = a2 + 136;
  v3 = *(_QWORD *)(a1 + 184);
  v4 = -1;
  *(_QWORD *)(a2 + 128) = *(_QWORD *)(a2 + 120);
  v5 = *(_QWORD *)(a2 + 88);
  v6 = -1;
  *(_DWORD *)(a2 + 80) = 0;
  v9 = -1073741823;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v2 + 2 * v10) );
  v11 = 2 * (v6 + v10) + 4;
  if ( v11 >= 0xFFFF )
    LOWORD(v11) = -1;
  v12 = *(_QWORD *)(v3 + 48);
  if ( *(_WORD *)(v12 + 90) < (unsigned __int16)v11 )
  {
    ExFreePoolWithTag(*(PVOID *)(v12 + 96), 0);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, (unsigned __int16)v11, 0x70725753u);
    v15 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, (unsigned __int16)v11);
    *(_QWORD *)(*(_QWORD *)(v3 + 48) + 96LL) = v15;
    v16 = *(_QWORD *)(v3 + 48);
    if ( *(_QWORD *)(v16 + 96) )
    {
      *(_WORD *)(v16 + 90) = v11;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v14) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          14,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
      }
      *(_DWORD *)(a1 + 48) = -1073741670;
      v9 = -1073741670;
      *(_WORD *)(*(_QWORD *)(v3 + 48) + 90LL) = 0;
      *(_WORD *)(*(_QWORD *)(v3 + 48) + 88LL) = 0;
    }
    v2 = a2 + 136;
  }
  v17 = *(wchar_t **)(*(_QWORD *)(v3 + 48) + 96LL);
  if ( v17 )
  {
    v18 = StringCbPrintfW(v17, (unsigned __int16)v11, L"%s\\%s", *(_QWORD *)(a2 + 88), v2);
    v20 = *(_QWORD *)(v3 + 48);
    v21 = *(_WORD **)(v20 + 96);
    if ( v18 >= 0 )
    {
      do
        ++v4;
      while ( v21[v4] );
      *(_WORD *)(v20 + 88) = 2 * v4;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_S(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          v19,
          15,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v3 + 48) + 96LL));
      v9 = 260;
      *(_QWORD *)(a1 + 56) = 2;
      *(_DWORD *)(a1 + 48) = 260;
    }
    else
    {
      ExFreePoolWithTag(v21, 0);
      v9 = -1073741670;
      *(_QWORD *)(*(_QWORD *)(v3 + 48) + 96LL) = 0;
      *(_WORD *)(*(_QWORD *)(v3 + 48) + 90LL) = 0;
      *(_WORD *)(*(_QWORD *)(v3 + 48) + 88LL) = 0;
      *(_DWORD *)(a1 + 48) = -1073741670;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18005a0c0  push    rbx
0x18005a0c2  push    rbp
0x18005a0c3  push    rsi
0x18005a0c4  push    rdi
0x18005a0c5  push    r12
0x18005a0c7  push    r13
0x18005a0c9  push    r14
0x18005a0cb  push    r15
0x18005a0cd  sub     rsp, 38h
0x18005a0d1  mov     rax, [rdx+78h]
0x18005a0d5  lea     r9, [rdx+88h]
0x18005a0dc  mov     rbx, [rcx+0B8h]
0x18005a0e3  xor     r15d, r15d
0x18005a0e6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005a0ea  mov     [rdx+80h], rax
0x18005a0f1  mov     rax, [rdx+58h]
0x18005a0f5  mov     r8, rdi
0x18005a0f8  mov     r13, rdx
0x18005a0fb  mov     [rdx+50h], r15d
0x18005a0ff  mov     r14, rcx
0x18005a102  mov     esi, 0C0000001h
0x18005a107  inc     r8
0x18005a10a  cmp     [rax+r8*2], r15w
0x18005a10f  jnz     short loc_18005A107
0x18005a111  mov     rax, rdi
0x18005a114  inc     rax
0x18005a117  cmp     [r9+rax*2], r15w
0x18005a11c  jnz     short loc_18005A114
0x18005a11e  add     rax, r8
0x18005a121  lea     rbp, ds:4[rax*2]
0x18005a129  mov     eax, 0FFFFh
0x18005a12e  cmp     rbp, rax
0x18005a131  jb      short loc_18005A136
0x18005a133  movzx   ebp, ax
0x18005a136  mov     rcx, [rbx+30h]
0x18005a13a  lea     r12, WPP_RECORDER_INITIALIZED
0x18005a141  cmp     [rcx+5Ah], bp
0x18005a145  jnb     loc_18005A21E
0x18005a14b  mov     rcx, [rcx+60h]; P
0x18005a14f  xor     edx, edx; Tag
0x18005a151  call    cs:__imp_ExFreePoolWithTag
0x18005a158  nop     dword ptr [rax+rax+00h]
0x18005a15d  movzx   r12d, bp
0x18005a161  mov     r8d, 70725753h; Tag
0x18005a167  mov     edx, r12d; NumberOfBytes
0x18005a16a  mov     ecx, 401h; PoolType
0x18005a16f  call    cs:__imp_ExAllocatePoolWithTag
0x18005a176  nop     dword ptr [rax+rax+00h]
0x18005a17b  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18005a182  mov     r15, rax
0x18005a185  jnz     short loc_18005A199
0x18005a187  test    rax, rax
0x18005a18a  jz      short loc_18005A199
0x18005a18c  mov     r8d, r12d; Size
0x18005a18f  xor     edx, edx; Val
0x18005a191  mov     rcx, rax; void *
0x18005a194  call    memset
0x18005a199  mov     rax, [rbx+30h]
0x18005a19d  mov     [rax+60h], r15
0x18005a1a1  xor     r15d, r15d
0x18005a1a4  mov     rax, [rbx+30h]
0x18005a1a8  cmp     [rax+60h], r15
0x18005a1ac  jnz     short loc_18005A20C
0x18005a1ae  lea     r12, WPP_RECORDER_INITIALIZED
0x18005a1b5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005a1bc  jz      short loc_18005A1EB
0x18005a1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a1c5  cmp     [rcx+48h], r15w
0x18005a1ca  jz      short loc_18005A1EB
0x18005a1cc  mov     rcx, [rcx+40h]
0x18005a1d0  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a1d7  lea     r9d, [r15+0Eh]
0x18005a1db  mov     [rsp+78h+var_58], rax
0x18005a1e0  lea     r8d, [r15+1]
0x18005a1e4  mov     dl, 5
0x18005a1e6  call    WPP_RECORDER_SF_
0x18005a1eb  mov     dword ptr [r14+30h], 0C000009Ah
0x18005a1f3  mov     esi, 0C000009Ah
0x18005a1f8  mov     rcx, [rbx+30h]
0x18005a1fc  mov     [rcx+5Ah], r15w
0x18005a201  mov     rcx, [rbx+30h]
0x18005a205  mov     [rcx+58h], r15w
0x18005a20a  jmp     short loc_18005A217
0x18005a20c  mov     [rax+5Ah], bp
0x18005a210  lea     r12, WPP_RECORDER_INITIALIZED
0x18005a217  lea     r9, [r13+88h]
0x18005a21e  mov     rax, [rbx+30h]
0x18005a222  mov     rcx, [rax+60h]; pszDest
0x18005a226  test    rcx, rcx
0x18005a229  jz      loc_18005A2EB
0x18005a22f  mov     [rsp+78h+var_58], r9
0x18005a234  lea     r8, aSS_0; "%s\\%s"
0x18005a23b  mov     r9, [r13+58h]
0x18005a23f  movzx   edx, bp; cbDest
0x18005a242  call    StringCbPrintfW
0x18005a247  mov     rdx, [rbx+30h]
0x18005a24b  mov     rcx, [rdx+60h]; P
0x18005a24f  test    eax, eax
0x18005a251  jns     short loc_18005A28A
0x18005a253  xor     edx, edx; Tag
0x18005a255  call    cs:__imp_ExFreePoolWithTag
0x18005a25c  nop     dword ptr [rax+rax+00h]
0x18005a261  mov     rax, [rbx+30h]
0x18005a265  mov     esi, 0C000009Ah
0x18005a26a  mov     [rax+60h], r15
0x18005a26e  mov     rcx, [rbx+30h]
0x18005a272  mov     [rcx+5Ah], r15w
0x18005a277  mov     rcx, [rbx+30h]
0x18005a27b  mov     [rcx+58h], r15w
0x18005a280  mov     dword ptr [r14+30h], 0C000009Ah
0x18005a288  jmp     short loc_18005A2EB
0x18005a28a  inc     rdi
0x18005a28d  cmp     [rcx+rdi*2], r15w
0x18005a292  jnz     short loc_18005A28A
0x18005a294  add     di, di
0x18005a297  mov     [rdx+58h], di
0x18005a29b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005a2a2  jz      short loc_18005A2DA
0x18005a2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2ab  cmp     [rcx+48h], r15w
0x18005a2b0  jz      short loc_18005A2DA
0x18005a2b2  mov     rax, [rbx+30h]
0x18005a2b6  mov     r9d, 0Fh
0x18005a2bc  mov     rcx, [rcx+40h]
0x18005a2c0  mov     rax, [rax+60h]
0x18005a2c4  mov     [rsp+78h+var_50], rax
0x18005a2c9  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a2d0  mov     [rsp+78h+var_58], rax
0x18005a2d5  call    WPP_RECORDER_SF_S
0x18005a2da  mov     esi, 104h
0x18005a2df  mov     qword ptr [r14+38h], 2
0x18005a2e7  mov     [r14+30h], esi
0x18005a2eb  mov     eax, esi
0x18005a2ed  add     rsp, 38h
0x18005a2f1  pop     r15
0x18005a2f3  pop     r14
0x18005a2f5  pop     r13
0x18005a2f7  pop     r12
0x18005a2f9  pop     rdi
0x18005a2fa  pop     rsi
0x18005a2fb  pop     rbp
0x18005a2fc  pop     rbx
0x18005a2fd  retn
```
