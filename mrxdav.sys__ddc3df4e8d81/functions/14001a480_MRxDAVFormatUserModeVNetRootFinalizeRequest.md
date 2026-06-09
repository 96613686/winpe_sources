# MRxDAVFormatUserModeVNetRootFinalizeRequest

- ea: `0x14001a480`
- end: `0x14001a6e4`
- name: `MRxDAVFormatUserModeVNetRootFinalizeRequest`
- size: `612`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400018d4`
- `0x140001b64`
- `0x140003378`
- `0x14001a480`
- `0x14002609c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a4ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a4f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a594`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a613`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a665`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a6a9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a4ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a4f4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a594`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a613`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a665`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a6a9`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeVNetRootFinalizeRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rbp
  _DWORD *v11; // rax
  __int64 v12; // rdi
  int v13; // ebx
  int v14; // edi
  __int64 v15; // rsi
  HANDLE v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  ULONG_PTR v19; // rsi
  wchar_t *SecondaryBuffer; // rax
  unsigned int v21; // edi
  __int64 v22; // rbx
  HANDLE v23; // rax
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rbx
  HANDLE v27; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v6, 78, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_qqq(v8, 79, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v9, a1, a2);
    }
  }
  v10 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 216) + 32LL) + 32LL);
  if ( v10 && (v11 = *(_DWORD **)(v10 + 32)) != 0 )
  {
    v12 = *(_QWORD *)(a2 + 224);
    *(_DWORD *)(a3 + 48) = 8;
    *(_DWORD *)(a3 + 648) = *v11;
    *(_DWORD *)(a3 + 640) = *(_DWORD *)(v12 + 80);
    *(_DWORD *)(a3 + 644) = *(_DWORD *)(v12 + 84);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v13 = *(_DWORD *)(v12 + 84);
      v14 = *(_DWORD *)(v12 + 80);
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = PsGetCurrentThreadId();
      WPP_SF_qLd(v15, 81, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v16, v14, v13);
    }
    v17 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 8LL);
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v17 + 2 * v18 + 2) );
    v19 = (unsigned int)(2 * v18 + 2);
    SecondaryBuffer = (wchar_t *)UMRxAllocateSecondaryBuffer(a1, v19);
    if ( SecondaryBuffer )
    {
      *(_QWORD *)(a3 + 632) = SecondaryBuffer;
      v21 = 0;
      StringCbCopyW(SecondaryBuffer, v19, (STRSAFE_LPCWSTR)(v17 + 2));
    }
    else
    {
      v21 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v21;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v23 = PsGetCurrentThreadId();
        WPP_SF_qD(v22, 82, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v23, -1073741670);
      }
    }
  }
  else
  {
    v21 = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v21;
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      WPP_SF_qD(v24, 80, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v25, -1073741811);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v27 = PsGetCurrentThreadId();
    WPP_SF_qD(v26, 83, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v27, v21);
  }
  return v21;
}

```

## disassembly

```asm
0x14001a480  push    rbx
0x14001a482  push    rbp
0x14001a483  push    rsi
0x14001a484  push    rdi
0x14001a485  push    r12
0x14001a487  push    r13
0x14001a489  push    r14
0x14001a48b  push    r15
0x14001a48d  sub     rsp, 38h
0x14001a491  mov     r14, r8
0x14001a494  mov     rdi, rdx
0x14001a497  mov     r15, rcx
0x14001a49a  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a4a1  lea     r12, WPP_GLOBAL_Control
0x14001a4a8  cmp     rbx, r12
0x14001a4ab  jz      short loc_14001A521
0x14001a4ad  test    dword ptr [rbx+2Ch], 4000h
0x14001a4b4  jz      short loc_14001A4DD
0x14001a4b6  mov     rbx, [rbx+18h]
0x14001a4ba  call    cs:__imp_PsGetCurrentThreadId
0x14001a4c1  nop     dword ptr [rax+rax+00h]
0x14001a4c6  mov     edx, 4Eh ; 'N'
0x14001a4cb  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a4d2  mov     r9, rax
0x14001a4d5  mov     rcx, rbx
0x14001a4d8  call    WPP_SF_q
0x14001a4dd  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a4e4  cmp     rbx, r12
0x14001a4e7  jz      short loc_14001A521
0x14001a4e9  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a4ee  jnb     short loc_14001A521
0x14001a4f0  mov     rbx, [rbx+18h]
0x14001a4f4  call    cs:__imp_PsGetCurrentThreadId
0x14001a4fb  nop     dword ptr [rax+rax+00h]
0x14001a500  mov     edx, 4Fh ; 'O'
0x14001a505  mov     [rsp+78h+var_50], rdi
0x14001a50a  mov     r9, rax
0x14001a50d  mov     [rsp+78h+var_58], r15
0x14001a512  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a519  mov     rcx, rbx
0x14001a51c  call    WPP_SF_qqq
0x14001a521  mov     rax, [rdi+0D8h]
0x14001a528  xor     r13d, r13d
0x14001a52b  mov     rcx, [rax+20h]
0x14001a52f  mov     rbp, [rcx+20h]
0x14001a533  test    rbp, rbp
0x14001a536  jz      loc_14001A649
0x14001a53c  mov     rax, [rbp+20h]
0x14001a540  test    rax, rax
0x14001a543  jz      loc_14001A649
0x14001a549  mov     rdi, [rdi+0E0h]
0x14001a550  mov     dword ptr [r14+30h], 8
0x14001a558  mov     eax, [rax]
0x14001a55a  mov     [r14+288h], eax
0x14001a561  mov     eax, [rdi+50h]
0x14001a564  mov     [r14+280h], eax
0x14001a56b  mov     eax, [rdi+54h]
0x14001a56e  mov     [r14+284h], eax
0x14001a575  mov     rsi, cs:WPP_GLOBAL_Control
0x14001a57c  cmp     rsi, r12
0x14001a57f  jz      short loc_14001A5BE
0x14001a581  test    dword ptr [rsi+2Ch], 4000h
0x14001a588  jz      short loc_14001A5BE
0x14001a58a  mov     ebx, [rdi+54h]
0x14001a58d  mov     edi, [rdi+50h]
0x14001a590  mov     rsi, [rsi+18h]
0x14001a594  call    cs:__imp_PsGetCurrentThreadId
0x14001a59b  nop     dword ptr [rax+rax+00h]
0x14001a5a0  lea     edx, [r13+51h]
0x14001a5a4  mov     dword ptr [rsp+78h+var_50], ebx
0x14001a5a8  mov     r9, rax
0x14001a5ab  mov     dword ptr [rsp+78h+var_58], edi
0x14001a5af  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a5b6  mov     rcx, rsi
0x14001a5b9  call    WPP_SF_qLd
0x14001a5be  mov     rax, [rbp+40h]
0x14001a5c2  mov     rbx, [rax+8]
0x14001a5c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a5ca  inc     rax
0x14001a5cd  cmp     [rbx+rax*2+2], r13w
0x14001a5d3  jnz     short loc_14001A5CA
0x14001a5d5  lea     eax, ds:2[rax*2]
0x14001a5dc  mov     rcx, r15
0x14001a5df  mov     edx, eax
0x14001a5e1  mov     esi, eax
0x14001a5e3  call    UMRxAllocateSecondaryBuffer
0x14001a5e8  test    rax, rax
0x14001a5eb  jnz     short loc_14001A62E
0x14001a5ed  mov     edi, 0C000009Ah
0x14001a5f2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a5f9  cmp     rbx, r12
0x14001a5fc  jz      loc_14001A6D0
0x14001a602  test    dword ptr [rbx+2Ch], 2000h
0x14001a609  jz      loc_14001A690
0x14001a60f  mov     rbx, [rbx+18h]
0x14001a613  call    cs:__imp_PsGetCurrentThreadId
0x14001a61a  nop     dword ptr [rax+rax+00h]
0x14001a61f  mov     edx, 52h ; 'R'
0x14001a624  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x14001a62c  jmp     short loc_14001A67E
0x14001a62e  lea     r8, [rbx+2]; pszSrc
0x14001a632  mov     [r14+278h], rax
0x14001a639  mov     rdx, rsi; cbDest
0x14001a63c  mov     rcx, rax; pszDest
0x14001a63f  mov     edi, r13d
0x14001a642  call    StringCbCopyW
0x14001a647  jmp     short loc_14001A690
0x14001a649  mov     edi, 0C000000Dh
0x14001a64e  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a655  cmp     rbx, r12
0x14001a658  jz      short loc_14001A6D0
0x14001a65a  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a65f  jnb     short loc_14001A690
0x14001a661  mov     rbx, [rbx+18h]
0x14001a665  call    cs:__imp_PsGetCurrentThreadId
0x14001a66c  nop     dword ptr [rax+rax+00h]
0x14001a671  mov     edx, 50h ; 'P'
0x14001a676  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x14001a67e  mov     r9, rax
0x14001a681  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a688  mov     rcx, rbx
0x14001a68b  call    WPP_SF_qD
0x14001a690  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a697  cmp     rbx, r12
0x14001a69a  jz      short loc_14001A6D0
0x14001a69c  test    dword ptr [rbx+2Ch], 4000h
0x14001a6a3  jz      short loc_14001A6D0
0x14001a6a5  mov     rbx, [rbx+18h]
0x14001a6a9  call    cs:__imp_PsGetCurrentThreadId
0x14001a6b0  nop     dword ptr [rax+rax+00h]
0x14001a6b5  mov     edx, 53h ; 'S'
0x14001a6ba  mov     dword ptr [rsp+78h+var_58], edi
0x14001a6be  mov     r9, rax
0x14001a6c1  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a6c8  mov     rcx, rbx
0x14001a6cb  call    WPP_SF_qD
0x14001a6d0  mov     eax, edi
0x14001a6d2  add     rsp, 38h
0x14001a6d6  pop     r15
0x14001a6d8  pop     r14
0x14001a6da  pop     r13
0x14001a6dc  pop     r12
0x14001a6de  pop     rdi
0x14001a6df  pop     rsi
0x14001a6e0  pop     rbp
0x14001a6e1  pop     rbx
0x14001a6e2  retn
```
