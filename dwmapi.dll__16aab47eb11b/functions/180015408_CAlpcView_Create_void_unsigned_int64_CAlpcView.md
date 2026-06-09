# CAlpcView::Create(void *,unsigned __int64,CAlpcView * *)

- ea: `0x180015408`
- end: `0x18001550b`
- name: `?Create@CAlpcView@@SAJPEAX_KPEAPEAV1@@Z`
- size: `259`
- prototype: `__int64 __fastcall(void *, unsigned __int64, struct CAlpcView **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015224`

## callees

- `0x180003370`
- `0x18000c2b4`
- `0x180015408`

## import_xrefs

- `ntdll!NtAlpcDeletePortSection` at `0x1800154e6`
- `ntdll!NtAlpcDeletePortSection` at `0x1800154e6`
- `ntdll!NtAlpcDeleteSectionView` at `0x1800154fa`
- `ntdll!NtAlpcDeleteSectionView` at `0x1800154fa`
- `ntdll!NtAlpcCreatePortSection` at `0x180015450`
- `ntdll!NtAlpcCreatePortSection` at `0x180015450`
- `ntdll!NtAlpcCreateSectionView` at `0x180015470`
- `ntdll!NtAlpcCreateSectionView` at `0x180015470`

## pseudocode

```c
__int64 __fastcall CAlpcView::Create(void *a1, __int64 a2, struct CAlpcView **a3)
{
  int v5; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // edx
  const struct std::nothrow_t *v8; // rdx
  int v9; // ebx
  char *v10; // rax
  __int128 v11; // xmm1
  __m256i v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+88h] [rbp+30h] BYREF

  v13.m256i_i64[3] = a2;
  v14 = 0;
  memset(&v13, 0, 24);
  v5 = NtAlpcCreatePortSection(a1, 0, 0, a2, &v13.m256i_u64[1], &v14);
  if ( v5 >= 0 )
  {
    v9 = NtAlpcCreateSectionView(a1, 0, &v13);
    if ( v9 >= 0 )
    {
      v10 = (char *)operator new[](0x30u, v8);
      if ( v10 )
      {
        *(_QWORD *)v10 = a1;
        v6 = 0;
        *(_OWORD *)(v10 + 8) = *(_OWORD *)v13.m256i_i8;
        v11 = *(_OWORD *)&v13.m256i_u64[2];
        *((_QWORD *)v10 + 5) = 0;
        *(_OWORD *)(v10 + 24) = v11;
        *a3 = (struct CAlpcView *)v10;
        *(_OWORD *)&v13.m256i_u64[1] = 0;
        goto LABEL_9;
      }
      *a3 = 0;
      v6 = -2147024882;
      v7 = 613;
    }
    else
    {
      v6 = v9 | 0x10000000;
      v7 = 610;
    }
  }
  else
  {
    v6 = v5 | 0x10000000;
    v7 = 608;
  }
  DoStackCaptureDirect(v6, v7);
LABEL_9:
  if ( v13.m256i_i64[1] )
    NtAlpcDeletePortSection(a1, 0);
  if ( v13.m256i_i64[2] )
    NtAlpcDeleteSectionView(a1, 0);
  return v6;
}

```

## disassembly

```asm
0x180015408  push    rbp
0x18001540a  push    rbx
0x18001540b  push    rsi
0x18001540c  push    rdi
0x18001540d  mov     rbp, rsp
0x180015410  sub     rsp, 58h
0x180015414  lea     rax, [rbp+arg_8]
0x180015418  mov     [rbp+var_10], rdx
0x18001541c  mov     [rsp+58h+var_30], rax
0x180015421  mov     rsi, r8
0x180015424  lea     rax, [rbp+var_28+8]
0x180015428  mov     [rbp+arg_8], 0
0x180015430  xorps   xmm0, xmm0
0x180015433  mov     [rsp+58h+var_38], rax
0x180015438  mov     r9, rdx
0x18001543b  mov     qword ptr [rbp+var_28], 0
0x180015443  xor     r8d, r8d
0x180015446  xor     edx, edx
0x180015448  mov     rdi, rcx
0x18001544b  movdqu  [rbp+var_28+8], xmm0
0x180015450  call    cs:__imp_NtAlpcCreatePortSection
0x180015456  mov     ebx, eax
0x180015458  test    eax, eax
0x18001545a  jns     short loc_180015467
0x18001545c  bts     ebx, 1Ch
0x180015460  mov     edx, 260h
0x180015465  jmp     short loc_1800154D1
0x180015467  lea     r8, [rbp+var_28]
0x18001546b  xor     edx, edx
0x18001546d  mov     rcx, rdi
0x180015470  call    cs:__imp_NtAlpcCreateSectionView
0x180015476  mov     ebx, eax
0x180015478  test    eax, eax
0x18001547a  jns     short loc_180015487
0x18001547c  bts     ebx, 1Ch
0x180015480  mov     edx, 262h
0x180015485  jmp     short loc_1800154D1
0x180015487  mov     ecx, 30h ; '0'; unsigned __int64
0x18001548c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015491  test    rax, rax
0x180015494  jz      short loc_1800154C0
0x180015496  mov     [rax], rdi
0x180015499  xor     ebx, ebx
0x18001549b  movups  xmm0, [rbp+var_28]
0x18001549f  movups  xmmword ptr [rax+8], xmm0
0x1800154a3  movups  xmm1, xmmword ptr [rbp-18h]
0x1800154a7  mov     qword ptr [rax+28h], 0
0x1800154af  xorps   xmm0, xmm0
0x1800154b2  movups  xmmword ptr [rax+18h], xmm1
0x1800154b6  mov     [rsi], rax
0x1800154b9  movdqu  [rbp+var_28+8], xmm0
0x1800154be  jmp     short loc_1800154D8
0x1800154c0  mov     qword ptr [rsi], 0
0x1800154c7  mov     ebx, 8007000Eh
0x1800154cc  mov     edx, 265h; unsigned int
0x1800154d1  mov     ecx, ebx; int
0x1800154d3  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800154d8  mov     r8, qword ptr [rbp+var_28+8]
0x1800154dc  test    r8, r8
0x1800154df  jz      short loc_1800154EC
0x1800154e1  xor     edx, edx
0x1800154e3  mov     rcx, rdi
0x1800154e6  call    cs:__imp_NtAlpcDeletePortSection
0x1800154ec  mov     r8, [rbp+var_18]
0x1800154f0  test    r8, r8
0x1800154f3  jz      short loc_180015500
0x1800154f5  xor     edx, edx
0x1800154f7  mov     rcx, rdi
0x1800154fa  call    cs:__imp_NtAlpcDeleteSectionView
0x180015500  mov     eax, ebx
0x180015502  add     rsp, 58h
0x180015506  pop     rdi
0x180015507  pop     rsi
0x180015508  pop     rbx
0x180015509  pop     rbp
0x18001550a  retn
```
