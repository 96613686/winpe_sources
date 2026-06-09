# IssueReparseForIrp

- ea: `0x18005a260`
- end: `0x18005a49f`
- name: `IssueReparseForIrp`
- size: `575`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x18005997c`
- `0x1800599f8`
- `0x180059df0`

## callees

- `0x18000ae68`
- `0x18000b7bc`
- `0x180011684`
- `0x18001a000`
- `0x18005a260`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005a2f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a2f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a3f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a30f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a30f`

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
0x18005a260  push    rbx
0x18005a262  push    rbp
0x18005a263  push    rsi
0x18005a264  push    rdi
0x18005a265  push    r12
0x18005a267  push    r13
0x18005a269  push    r14
0x18005a26b  push    r15
0x18005a26d  sub     rsp, 38h
0x18005a271  mov     rax, [rdx+78h]
0x18005a275  lea     r9, [rdx+88h]
0x18005a27c  mov     rbx, [rcx+0B8h]
0x18005a283  xor     r15d, r15d
0x18005a286  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005a28a  mov     [rdx+80h], rax
0x18005a291  mov     rax, [rdx+58h]
0x18005a295  mov     r8, rdi
0x18005a298  mov     r13, rdx
0x18005a29b  mov     [rdx+50h], r15d
0x18005a29f  mov     r14, rcx
0x18005a2a2  mov     esi, 0C0000001h
0x18005a2a7  inc     r8
0x18005a2aa  cmp     [rax+r8*2], r15w
0x18005a2af  jnz     short loc_18005A2A7
0x18005a2b1  mov     rax, rdi
0x18005a2b4  inc     rax
0x18005a2b7  cmp     [r9+rax*2], r15w
0x18005a2bc  jnz     short loc_18005A2B4
0x18005a2be  add     rax, r8
0x18005a2c1  lea     rbp, ds:4[rax*2]
0x18005a2c9  mov     eax, 0FFFFh
0x18005a2ce  cmp     rbp, rax
0x18005a2d1  jb      short loc_18005A2D6
0x18005a2d3  movzx   ebp, ax
0x18005a2d6  mov     rcx, [rbx+30h]
0x18005a2da  lea     r12, WPP_RECORDER_INITIALIZED
0x18005a2e1  cmp     [rcx+5Ah], bp
0x18005a2e5  jnb     loc_18005A3BE
0x18005a2eb  mov     rcx, [rcx+60h]; P
0x18005a2ef  xor     edx, edx; Tag
0x18005a2f1  call    cs:__imp_ExFreePoolWithTag
0x18005a2f8  nop     dword ptr [rax+rax+00h]
0x18005a2fd  movzx   r12d, bp
0x18005a301  mov     r8d, 70725753h; Tag
0x18005a307  mov     edx, r12d; NumberOfBytes
0x18005a30a  mov     ecx, 401h; PoolType
0x18005a30f  call    cs:__imp_ExAllocatePoolWithTag
0x18005a316  nop     dword ptr [rax+rax+00h]
0x18005a31b  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18005a322  mov     r15, rax
0x18005a325  jnz     short loc_18005A339
0x18005a327  test    rax, rax
0x18005a32a  jz      short loc_18005A339
0x18005a32c  mov     r8d, r12d; Size
0x18005a32f  xor     edx, edx; Val
0x18005a331  mov     rcx, rax; void *
0x18005a334  call    memset
0x18005a339  mov     rax, [rbx+30h]
0x18005a33d  mov     [rax+60h], r15
0x18005a341  xor     r15d, r15d
0x18005a344  mov     rax, [rbx+30h]
0x18005a348  cmp     [rax+60h], r15
0x18005a34c  jnz     short loc_18005A3AC
0x18005a34e  lea     r12, WPP_RECORDER_INITIALIZED
0x18005a355  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005a35c  jz      short loc_18005A38B
0x18005a35e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a365  cmp     [rcx+48h], r15w
0x18005a36a  jz      short loc_18005A38B
0x18005a36c  mov     rcx, [rcx+40h]
0x18005a370  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a377  lea     r9d, [r15+0Eh]
0x18005a37b  mov     [rsp+78h+var_58], rax
0x18005a380  lea     r8d, [r15+1]
0x18005a384  mov     dl, 5
0x18005a386  call    WPP_RECORDER_SF_
0x18005a38b  mov     dword ptr [r14+30h], 0C000009Ah
0x18005a393  mov     esi, 0C000009Ah
0x18005a398  mov     rcx, [rbx+30h]
0x18005a39c  mov     [rcx+5Ah], r15w
0x18005a3a1  mov     rcx, [rbx+30h]
0x18005a3a5  mov     [rcx+58h], r15w
0x18005a3aa  jmp     short loc_18005A3B7
0x18005a3ac  mov     [rax+5Ah], bp
0x18005a3b0  lea     r12, WPP_RECORDER_INITIALIZED
0x18005a3b7  lea     r9, [r13+88h]
0x18005a3be  mov     rax, [rbx+30h]
0x18005a3c2  mov     rcx, [rax+60h]; pszDest
0x18005a3c6  test    rcx, rcx
0x18005a3c9  jz      loc_18005A48B
0x18005a3cf  mov     [rsp+78h+var_58], r9
0x18005a3d4  lea     r8, aSS_0; "%s\\%s"
0x18005a3db  mov     r9, [r13+58h]
0x18005a3df  movzx   edx, bp; cbDest
0x18005a3e2  call    StringCbPrintfW
0x18005a3e7  mov     rdx, [rbx+30h]
0x18005a3eb  mov     rcx, [rdx+60h]; P
0x18005a3ef  test    eax, eax
0x18005a3f1  jns     short loc_18005A42A
0x18005a3f3  xor     edx, edx; Tag
0x18005a3f5  call    cs:__imp_ExFreePoolWithTag
0x18005a3fc  nop     dword ptr [rax+rax+00h]
0x18005a401  mov     rax, [rbx+30h]
0x18005a405  mov     esi, 0C000009Ah
0x18005a40a  mov     [rax+60h], r15
0x18005a40e  mov     rcx, [rbx+30h]
0x18005a412  mov     [rcx+5Ah], r15w
0x18005a417  mov     rcx, [rbx+30h]
0x18005a41b  mov     [rcx+58h], r15w
0x18005a420  mov     dword ptr [r14+30h], 0C000009Ah
0x18005a428  jmp     short loc_18005A48B
0x18005a42a  inc     rdi
0x18005a42d  cmp     [rcx+rdi*2], r15w
0x18005a432  jnz     short loc_18005A42A
0x18005a434  add     di, di
0x18005a437  mov     [rdx+58h], di
0x18005a43b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005a442  jz      short loc_18005A47A
0x18005a444  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a44b  cmp     [rcx+48h], r15w
0x18005a450  jz      short loc_18005A47A
0x18005a452  mov     rax, [rbx+30h]
0x18005a456  mov     r9d, 0Fh
0x18005a45c  mov     rcx, [rcx+40h]
0x18005a460  mov     rax, [rax+60h]
0x18005a464  mov     [rsp+78h+var_50], rax
0x18005a469  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a470  mov     [rsp+78h+var_58], rax
0x18005a475  call    WPP_RECORDER_SF_S
0x18005a47a  mov     esi, 104h
0x18005a47f  mov     qword ptr [r14+38h], 2
0x18005a487  mov     [r14+30h], esi
0x18005a48b  mov     eax, esi
0x18005a48d  add     rsp, 38h
0x18005a491  pop     r15
0x18005a493  pop     r14
0x18005a495  pop     r13
0x18005a497  pop     r12
0x18005a499  pop     rdi
0x18005a49a  pop     rsi
0x18005a49b  pop     rbp
0x18005a49c  pop     rbx
0x18005a49d  retn
```
