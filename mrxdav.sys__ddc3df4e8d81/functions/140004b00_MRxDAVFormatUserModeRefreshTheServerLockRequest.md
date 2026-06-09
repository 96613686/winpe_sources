# MRxDAVFormatUserModeRefreshTheServerLockRequest

- ea: `0x140004b00`
- end: `0x140004da6`
- name: `MRxDAVFormatUserModeRefreshTheServerLockRequest`
- size: `678`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400018d4`
- `0x140004b00`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140004b41`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004bc4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004c47`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004cbf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004d33`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004d6f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004b41`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004bc4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004c47`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004cbf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004d33`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004d6f`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeRefreshTheServerLockRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  ULONG_PTR v11; // rbp
  wchar_t *SecondaryBuffer; // rax
  unsigned int v13; // edi
  __int64 v14; // rbx
  HANDLE v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  ULONG_PTR v18; // rbp
  wchar_t *v19; // rax
  ULONG_PTR v20; // rdx
  size_t v21; // rbx
  wchar_t *v22; // rax
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // rbx
  HANDLE v26; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v6, 44, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId);
  }
  v8 = *(_QWORD *)(a2 + 216);
  v9 = -1;
  *(_DWORD *)(a3 + 48) = 12;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(*(_QWORD *)(v8 + 24) + 2 * v10) );
  v11 = (unsigned int)(2 * v10 + 2);
  SecondaryBuffer = (wchar_t *)UMRxAllocateSecondaryBuffer(a1, v11);
  if ( SecondaryBuffer )
  {
    *(_QWORD *)(a3 + 632) = SecondaryBuffer;
    StringCbCopyW(SecondaryBuffer, v11, *(STRSAFE_LPCWSTR *)(v8 + 24));
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(*(_QWORD *)(v8 + 32) + 2 * v17) );
    v18 = (unsigned int)(2 * v17 + 2);
    v19 = (wchar_t *)UMRxAllocateSecondaryBuffer(a1, v18);
    if ( v19 )
    {
      *(_QWORD *)(a3 + 640) = v19;
      StringCbCopyW(v19, v18, *(STRSAFE_LPCWSTR *)(v8 + 32));
      do
        ++v9;
      while ( *(_WORD *)(*(_QWORD *)(v8 + 16) + 2 * v9) );
      v20 = (unsigned int)(2 * v9 + 2);
      v21 = v20;
      v22 = (wchar_t *)UMRxAllocateSecondaryBuffer(a1, v20);
      if ( v22 )
      {
        *(_QWORD *)(a3 + 648) = v22;
        StringCbCopyW(v22, v21, *(STRSAFE_LPCWSTR *)(v8 + 16));
        *(_DWORD *)(a3 + 656) = *(_DWORD *)(v8 + 40);
        *(_DWORD *)(a3 + 660) = *(_DWORD *)(v8 + 44);
        *(_DWORD *)(a3 + 664) = *(_DWORD *)(v8 + 48);
        v13 = UMRxImpersonateClient(*(PSECURITY_CLIENT_CONTEXT *)(v8 + 56));
        if ( (v13 & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v13;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v24 = PsGetCurrentThreadId();
            WPP_SF_qD(v23, 48, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v24, v13);
          }
        }
        goto LABEL_27;
      }
      v13 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_27;
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      v16 = 47;
    }
    else
    {
      v13 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_27;
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      v16 = 46;
    }
    goto LABEL_10;
  }
  v13 = -1073741670;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v13;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v15 = PsGetCurrentThreadId();
    v16 = 45;
LABEL_10:
    WPP_SF_qD(v14, v16, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v15, -1073741670);
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v26 = PsGetCurrentThreadId();
    WPP_SF_qD(v25, 49, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v26, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x140004b00  push    rbx
0x140004b02  push    rbp
0x140004b03  push    rsi
0x140004b04  push    rdi
0x140004b05  push    r12
0x140004b07  push    r13
0x140004b09  push    r14
0x140004b0b  push    r15
0x140004b0d  sub     rsp, 38h
0x140004b11  mov     rsi, r8
0x140004b14  mov     rdi, rdx
0x140004b17  mov     r14, rcx
0x140004b1a  mov     rbx, cs:WPP_GLOBAL_Control
0x140004b21  lea     r15, WPP_GLOBAL_Control
0x140004b28  lea     r13, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140004b2f  cmp     rbx, r15
0x140004b32  jz      short loc_140004B60
0x140004b34  test    dword ptr [rbx+2Ch], 4000h
0x140004b3b  jz      short loc_140004B60
0x140004b3d  mov     rbx, [rbx+18h]
0x140004b41  call    cs:__imp_PsGetCurrentThreadId
0x140004b48  nop     dword ptr [rax+rax+00h]
0x140004b4d  mov     edx, 2Ch ; ','
0x140004b52  mov     r8, r13
0x140004b55  mov     r9, rax
0x140004b58  mov     rcx, rbx
0x140004b5b  call    WPP_SF_q
0x140004b60  mov     rdi, [rdi+0D8h]
0x140004b67  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004b6b  mov     dword ptr [rsi+30h], 0Ch
0x140004b72  mov     rax, rbx
0x140004b75  xor     r12d, r12d
0x140004b78  mov     rcx, [rdi+18h]
0x140004b7c  inc     rax
0x140004b7f  cmp     [rcx+rax*2], r12w
0x140004b84  jnz     short loc_140004B7C
0x140004b86  lea     eax, ds:2[rax*2]
0x140004b8d  mov     rcx, r14
0x140004b90  mov     edx, eax
0x140004b92  mov     ebp, eax
0x140004b94  call    UMRxAllocateSecondaryBuffer
0x140004b99  test    rax, rax
0x140004b9c  jnz     short loc_140004BE2
0x140004b9e  mov     edi, 0C000009Ah
0x140004ba3  mov     rbx, cs:WPP_GLOBAL_Control
0x140004baa  cmp     rbx, r15
0x140004bad  jz      loc_140004D92
0x140004bb3  test    dword ptr [rbx+2Ch], 2000h
0x140004bba  jz      loc_140004D56
0x140004bc0  mov     rbx, [rbx+18h]
0x140004bc4  call    cs:__imp_PsGetCurrentThreadId
0x140004bcb  nop     dword ptr [rax+rax+00h]
0x140004bd0  mov     edx, 2Dh ; '-'
0x140004bd5  mov     [rsp+78h+var_58], 0C000009Ah
0x140004bdd  jmp     loc_140004D48
0x140004be2  mov     [rsi+278h], rax
0x140004be9  mov     rdx, rbp; cbDest
0x140004bec  mov     r8, [rdi+18h]; pszSrc
0x140004bf0  mov     rcx, rax; pszDest
0x140004bf3  call    StringCbCopyW
0x140004bf8  mov     rcx, [rdi+20h]
0x140004bfc  mov     rax, rbx
0x140004bff  inc     rax
0x140004c02  cmp     [rcx+rax*2], r12w
0x140004c07  jnz     short loc_140004BFF
0x140004c09  lea     eax, ds:2[rax*2]
0x140004c10  mov     rcx, r14
0x140004c13  mov     edx, eax
0x140004c15  mov     ebp, eax
0x140004c17  call    UMRxAllocateSecondaryBuffer
0x140004c1c  test    rax, rax
0x140004c1f  jnz     short loc_140004C5D
0x140004c21  mov     edi, 0C000009Ah
0x140004c26  mov     rbx, cs:WPP_GLOBAL_Control
0x140004c2d  cmp     rbx, r15
0x140004c30  jz      loc_140004D92
0x140004c36  test    dword ptr [rbx+2Ch], 2000h
0x140004c3d  jz      loc_140004D56
0x140004c43  mov     rbx, [rbx+18h]
0x140004c47  call    cs:__imp_PsGetCurrentThreadId
0x140004c4e  nop     dword ptr [rax+rax+00h]
0x140004c53  mov     edx, 2Eh ; '.'
0x140004c58  jmp     loc_140004BD5
0x140004c5d  mov     [rsi+280h], rax
0x140004c64  mov     rdx, rbp; cbDest
0x140004c67  mov     r8, [rdi+20h]; pszSrc
0x140004c6b  mov     rcx, rax; pszDest
0x140004c6e  call    StringCbCopyW
0x140004c73  mov     rax, [rdi+10h]
0x140004c77  inc     rbx
0x140004c7a  cmp     [rax+rbx*2], r12w
0x140004c7f  jnz     short loc_140004C77
0x140004c81  lea     eax, ds:2[rbx*2]
0x140004c88  mov     rcx, r14
0x140004c8b  mov     edx, eax
0x140004c8d  mov     ebx, eax
0x140004c8f  call    UMRxAllocateSecondaryBuffer
0x140004c94  test    rax, rax
0x140004c97  jnz     short loc_140004CD5
0x140004c99  mov     edi, 0C000009Ah
0x140004c9e  mov     rbx, cs:WPP_GLOBAL_Control
0x140004ca5  cmp     rbx, r15
0x140004ca8  jz      loc_140004D92
0x140004cae  test    dword ptr [rbx+2Ch], 2000h
0x140004cb5  jz      loc_140004D56
0x140004cbb  mov     rbx, [rbx+18h]
0x140004cbf  call    cs:__imp_PsGetCurrentThreadId
0x140004cc6  nop     dword ptr [rax+rax+00h]
0x140004ccb  mov     edx, 2Fh ; '/'
0x140004cd0  jmp     loc_140004BD5
0x140004cd5  mov     [rsi+288h], rax
0x140004cdc  mov     rdx, rbx; cbDest
0x140004cdf  mov     r8, [rdi+10h]; pszSrc
0x140004ce3  mov     rcx, rax; pszDest
0x140004ce6  call    StringCbCopyW
0x140004ceb  mov     r11d, [rdi+28h]
0x140004cef  mov     rdx, rsi
0x140004cf2  mov     [rsi+290h], r11d
0x140004cf9  mov     eax, [rdi+2Ch]
0x140004cfc  mov     [rsi+294h], eax
0x140004d02  mov     eax, [rdi+30h]
0x140004d05  mov     [rsi+298h], eax
0x140004d0b  mov     rcx, [rdi+38h]; ClientContext
0x140004d0f  call    UMRxImpersonateClient
0x140004d14  mov     edi, eax
0x140004d16  test    eax, eax
0x140004d18  jns     short loc_140004D56
0x140004d1a  mov     rbx, cs:WPP_GLOBAL_Control
0x140004d21  cmp     rbx, r15
0x140004d24  jz      short loc_140004D92
0x140004d26  test    dword ptr [rbx+2Ch], 2000h
0x140004d2d  jz      short loc_140004D56
0x140004d2f  mov     rbx, [rbx+18h]
0x140004d33  call    cs:__imp_PsGetCurrentThreadId
0x140004d3a  nop     dword ptr [rax+rax+00h]
0x140004d3f  mov     edx, 30h ; '0'
0x140004d44  mov     [rsp+78h+var_58], edi
0x140004d48  mov     r9, rax
0x140004d4b  mov     r8, r13
0x140004d4e  mov     rcx, rbx
0x140004d51  call    WPP_SF_qD
0x140004d56  mov     rbx, cs:WPP_GLOBAL_Control
0x140004d5d  cmp     rbx, r15
0x140004d60  jz      short loc_140004D92
0x140004d62  test    dword ptr [rbx+2Ch], 4000h
0x140004d69  jz      short loc_140004D92
0x140004d6b  mov     rbx, [rbx+18h]
0x140004d6f  call    cs:__imp_PsGetCurrentThreadId
0x140004d76  nop     dword ptr [rax+rax+00h]
0x140004d7b  mov     edx, 31h ; '1'
0x140004d80  mov     [rsp+78h+var_58], edi
0x140004d84  mov     r9, rax
0x140004d87  mov     r8, r13
0x140004d8a  mov     rcx, rbx
0x140004d8d  call    WPP_SF_qD
0x140004d92  mov     eax, edi
0x140004d94  add     rsp, 38h
0x140004d98  pop     r15
0x140004d9a  pop     r14
0x140004d9c  pop     r13
0x140004d9e  pop     r12
0x140004da0  pop     rdi
0x140004da1  pop     rsi
0x140004da2  pop     rbp
0x140004da3  pop     rbx
0x140004da4  retn
```
