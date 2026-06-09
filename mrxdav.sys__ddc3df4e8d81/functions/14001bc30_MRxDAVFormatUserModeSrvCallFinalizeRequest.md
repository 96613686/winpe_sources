# MRxDAVFormatUserModeSrvCallFinalizeRequest

- ea: `0x14001bc30`
- end: `0x14001bddc`
- name: `MRxDAVFormatUserModeSrvCallFinalizeRequest`
- size: `428`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400018d4`
- `0x140001b64`
- `0x14001bc30`
- `0x14002609c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bc66`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bca2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bd49`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bda5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bc66`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bca2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bd49`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bda5`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeSrvCallFinalizeRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // edi
  _DWORD *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  ULONG_PTR v15; // rsi
  wchar_t *SecondaryBuffer; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v6, 59, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_qqq(v8, 60, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v9, a1, a2);
    }
  }
  v10 = *(_QWORD *)(a2 + 216);
  v11 = 0;
  v12 = 0;
  if ( v10 )
    v12 = *(_DWORD **)(v10 + 32);
  *(_DWORD *)(a3 + 48) = 5;
  *(_QWORD *)(a3 + 632) = 0;
  *(_DWORD *)(a3 + 640) = *v12;
  v13 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 8LL);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v13 + 2 * v14 + 2) );
  v15 = (unsigned int)(2 * v14 + 2);
  SecondaryBuffer = (wchar_t *)UMRxAllocateSecondaryBuffer(a1, v15);
  if ( SecondaryBuffer )
  {
    *(_QWORD *)(a3 + 632) = SecondaryBuffer;
    StringCbCopyW(SecondaryBuffer, v15, (STRSAFE_LPCWSTR)(v13 + 2));
  }
  else
  {
    v11 = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v11;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      WPP_SF_qD(v17, 61, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v18, -1073741670);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v20 = PsGetCurrentThreadId();
    WPP_SF_qD(v19, 62, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v20, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x14001bc30  push    rbx
0x14001bc32  push    rbp
0x14001bc33  push    rsi
0x14001bc34  push    rdi
0x14001bc35  push    r14
0x14001bc37  push    r15
0x14001bc39  sub     rsp, 38h
0x14001bc3d  mov     rbp, r8
0x14001bc40  mov     rdi, rdx
0x14001bc43  mov     r14, rcx
0x14001bc46  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bc4d  lea     r15, WPP_GLOBAL_Control
0x14001bc54  cmp     rbx, r15
0x14001bc57  jz      short loc_14001BCCF
0x14001bc59  test    dword ptr [rbx+2Ch], 4000h
0x14001bc60  jz      short loc_14001BC89
0x14001bc62  mov     rbx, [rbx+18h]
0x14001bc66  call    cs:__imp_PsGetCurrentThreadId
0x14001bc6d  nop     dword ptr [rax+rax+00h]
0x14001bc72  mov     edx, 3Bh ; ';'
0x14001bc77  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bc7e  mov     r9, rax
0x14001bc81  mov     rcx, rbx
0x14001bc84  call    WPP_SF_q
0x14001bc89  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bc90  cmp     rbx, r15
0x14001bc93  jz      short loc_14001BCCF
0x14001bc95  test    dword ptr [rbx+2Ch], 2000h
0x14001bc9c  jz      short loc_14001BCCF
0x14001bc9e  mov     rbx, [rbx+18h]
0x14001bca2  call    cs:__imp_PsGetCurrentThreadId
0x14001bca9  nop     dword ptr [rax+rax+00h]
0x14001bcae  mov     edx, 3Ch ; '<'
0x14001bcb3  mov     [rsp+68h+var_40], rdi
0x14001bcb8  mov     r9, rax
0x14001bcbb  mov     [rsp+68h+var_48], r14
0x14001bcc0  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bcc7  mov     rcx, rbx
0x14001bcca  call    WPP_SF_qqq
0x14001bccf  mov     rcx, [rdi+0D8h]
0x14001bcd6  xor     edi, edi
0x14001bcd8  mov     eax, edi
0x14001bcda  test    rcx, rcx
0x14001bcdd  jz      short loc_14001BCE3
0x14001bcdf  mov     rax, [rcx+20h]
0x14001bce3  mov     dword ptr [rbp+30h], 5
0x14001bcea  mov     [rbp+278h], rdi
0x14001bcf1  mov     eax, [rax]
0x14001bcf3  mov     [rbp+280h], eax
0x14001bcf9  mov     rax, [rcx+40h]
0x14001bcfd  mov     rbx, [rax+8]
0x14001bd01  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bd05  inc     rax
0x14001bd08  cmp     [rbx+rax*2+2], di
0x14001bd0d  jnz     short loc_14001BD05
0x14001bd0f  lea     eax, ds:2[rax*2]
0x14001bd16  mov     rcx, r14
0x14001bd19  mov     edx, eax
0x14001bd1b  mov     esi, eax
0x14001bd1d  call    UMRxAllocateSecondaryBuffer
0x14001bd22  test    rax, rax
0x14001bd25  jnz     short loc_14001BD76
0x14001bd27  mov     edi, 0C000009Ah
0x14001bd2c  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bd33  cmp     rbx, r15
0x14001bd36  jz      loc_14001BDCC
0x14001bd3c  test    dword ptr [rbx+2Ch], 2000h
0x14001bd43  jz      short loc_14001BD8C
0x14001bd45  mov     rbx, [rbx+18h]
0x14001bd49  call    cs:__imp_PsGetCurrentThreadId
0x14001bd50  nop     dword ptr [rax+rax+00h]
0x14001bd55  mov     edx, 3Dh ; '='
0x14001bd5a  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x14001bd62  mov     r9, rax
0x14001bd65  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bd6c  mov     rcx, rbx
0x14001bd6f  call    WPP_SF_qD
0x14001bd74  jmp     short loc_14001BD8C
0x14001bd76  lea     r8, [rbx+2]; pszSrc
0x14001bd7a  mov     [rbp+278h], rax
0x14001bd81  mov     rdx, rsi; cbDest
0x14001bd84  mov     rcx, rax; pszDest
0x14001bd87  call    StringCbCopyW
0x14001bd8c  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bd93  cmp     rbx, r15
0x14001bd96  jz      short loc_14001BDCC
0x14001bd98  test    dword ptr [rbx+2Ch], 4000h
0x14001bd9f  jz      short loc_14001BDCC
0x14001bda1  mov     rbx, [rbx+18h]
0x14001bda5  call    cs:__imp_PsGetCurrentThreadId
0x14001bdac  nop     dword ptr [rax+rax+00h]
0x14001bdb1  mov     edx, 3Eh ; '>'
0x14001bdb6  mov     dword ptr [rsp+68h+var_48], edi
0x14001bdba  mov     r9, rax
0x14001bdbd  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bdc4  mov     rcx, rbx
0x14001bdc7  call    WPP_SF_qD
0x14001bdcc  mov     eax, edi
0x14001bdce  add     rsp, 38h
0x14001bdd2  pop     r15
0x14001bdd4  pop     r14
0x14001bdd6  pop     rdi
0x14001bdd7  pop     rsi
0x14001bdd8  pop     rbp
0x14001bdd9  pop     rbx
0x14001bdda  retn
```
