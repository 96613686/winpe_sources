# MRxDAVPrecompleteUserModeFsCtlRequest

- ea: `0x140011a20`
- end: `0x140011ee5`
- name: `MRxDAVPrecompleteUserModeFsCtlRequest`
- size: `1221`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140006900`
- `0x140011a20`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140011a5e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011a9f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011aff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011c18`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011c7d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011d22`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011d78`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011dce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011e24`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011e62`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011ea7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011a5e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011a9f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011aff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011c18`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011c7d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011d22`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011d78`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011dce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011e24`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011e62`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011ea7`
- `ntoskrnl!NtClose` at `0x140011c4d`
- `ntoskrnl!NtClose` at `0x140011c4d`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeFsCtlRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // rdi
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  _WORD *v17; // r9
  __int64 v18; // r8
  _WORD *v19; // rax
  __int64 v20; // rdx
  _WORD *v21; // rcx
  _QWORD *v22; // rbx
  int v23; // edi
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rdx
  void *v27; // rcx
  NTSTATUS v28; // edi
  __int64 v29; // rbx
  HANDLE v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rbx
  HANDLE v34; // rax
  __int64 v35; // rbx
  HANDLE v36; // rax

  v5 = *(_QWORD *)(a2 + 64);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 52, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqq(v11, 53, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v12, a1, a2);
    }
  }
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v14 = PsGetCurrentThreadId();
      WPP_SF_qqq(v13, 54, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v14, a1, a2);
    }
  }
  else
  {
    v15 = *(_DWORD *)(a3 + 2312);
    if ( v15 )
      memmove(*(void **)(a2 + 560), *(const void **)(a3 + 688), v15);
    *(_QWORD *)(a2 + 184) = *(unsigned int *)(a3 + 2312);
    if ( v5 )
    {
      v16 = *(_QWORD *)(v5 + 56);
      if ( v16 )
      {
        v17 = (_WORD *)(a3 + 7120);
        *(_DWORD *)(v16 + 16) = *(_DWORD *)(a3 + 7116);
        v18 = 2147483646;
        v19 = (_WORD *)(v16 + 20);
        v20 = 1024;
        do
        {
          if ( !v18 )
            break;
          if ( !*v17 )
            break;
          *v19++ = *v17++;
          --v18;
          --v20;
        }
        while ( v20 );
        v21 = v19 - 1;
        if ( v20 )
          v21 = v19;
        *v21 = 0;
      }
    }
  }
  if ( *(_DWORD *)(a3 + 664) == 67108991 )
  {
    v22 = *(_QWORD **)(a3 + 672);
    if ( v22 )
    {
      if ( *v22 )
      {
        v23 = UMRxFreeSecondaryBuffer(a1);
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
          {
            v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v25 = PsGetCurrentThreadId();
            v26 = 55;
LABEL_29:
            WPP_SF_qD(v24, v26, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v25, v23);
            goto LABEL_70;
          }
          goto LABEL_70;
        }
      }
      v27 = (void *)v22[1];
      if ( v27 )
      {
        v28 = NtClose(v27);
        if ( v28 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
          {
            v29 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v30 = PsGetCurrentThreadId();
            WPP_SF_qD(v29, 56, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v30, v28);
          }
        }
      }
    }
    if ( !a5 )
    {
      v31 = *(_QWORD *)(*(_QWORD *)(a2 + 72) + 32LL);
      v32 = v31 ? *(_QWORD *)(v31 + 136) : 0LL;
      if ( *(_DWORD *)(v32 + 20) )
      {
        if ( *(_DWORD *)(a1 + 128) )
          _InterlockedExchange((volatile __int32 *)(v32 + 16), 1);
        *(_DWORD *)(v32 + 20) = 0;
      }
    }
  }
  if ( *(_QWORD *)(a3 + 640) && (v23 = UMRxFreeSecondaryBuffer(a1)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      v26 = 57;
      goto LABEL_29;
    }
  }
  else if ( *(_QWORD *)(a3 + 656) && (v23 = UMRxFreeSecondaryBuffer(a1)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      v26 = 58;
      goto LABEL_29;
    }
  }
  else if ( *(_QWORD *)(a3 + 672) && (v23 = UMRxFreeSecondaryBuffer(a1)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      v26 = 59;
      goto LABEL_29;
    }
  }
  else if ( *(_QWORD *)(a3 + 688) && (v23 = UMRxFreeSecondaryBuffer(a1)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      v26 = 60;
      goto LABEL_29;
    }
  }
  else
  {
    v23 = *(_DWORD *)(a1 + 128);
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_70;
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v34 = PsGetCurrentThreadId();
        WPP_SF_qD(v33, 61, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v34, v23);
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v35 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v36 = PsGetCurrentThreadId();
      WPP_SF_q(v35, 62, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v36);
    }
  }
LABEL_70:
  *(_DWORD *)(a1 + 128) = v23;
  return 1;
}

```

## disassembly

```asm
0x140011a20  push    rbx
0x140011a22  push    rbp
0x140011a23  push    rsi
0x140011a24  push    rdi
0x140011a25  push    r12
0x140011a27  push    r13
0x140011a29  push    r14
0x140011a2b  sub     rsp, 30h
0x140011a2f  mov     rdi, [rdx+40h]
0x140011a33  mov     rsi, r8
0x140011a36  mov     r14, rdx
0x140011a39  mov     rbp, rcx
0x140011a3c  mov     rbx, cs:WPP_GLOBAL_Control
0x140011a43  lea     rax, WPP_GLOBAL_Control
0x140011a4a  cmp     rbx, rax
0x140011a4d  jz      loc_140011AD3
0x140011a53  bt      dword ptr [rbx+2Ch], 0Dh
0x140011a58  jnb     short loc_140011A81
0x140011a5a  mov     rbx, [rbx+18h]
0x140011a5e  call    cs:__imp_PsGetCurrentThreadId
0x140011a65  nop     dword ptr [rax+rax+00h]
0x140011a6a  mov     edx, 34h ; '4'
0x140011a6f  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011a76  mov     r9, rax
0x140011a79  mov     rcx, rbx
0x140011a7c  call    WPP_SF_q
0x140011a81  mov     rbx, cs:WPP_GLOBAL_Control
0x140011a88  lea     rax, WPP_GLOBAL_Control
0x140011a8f  cmp     rbx, rax
0x140011a92  jz      short loc_140011AD3
0x140011a94  bt      dword ptr [rbx+2Ch], 0Dh
0x140011a99  jnb     short loc_140011ACC
0x140011a9b  mov     rbx, [rbx+18h]
0x140011a9f  call    cs:__imp_PsGetCurrentThreadId
0x140011aa6  nop     dword ptr [rax+rax+00h]
0x140011aab  mov     edx, 35h ; '5'
0x140011ab0  mov     [rsp+68h+var_40], r14
0x140011ab5  mov     r9, rax
0x140011ab8  mov     [rsp+68h+var_48], rbp
0x140011abd  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011ac4  mov     rcx, rbx
0x140011ac7  call    WPP_SF_qqq
0x140011acc  lea     rax, WPP_GLOBAL_Control
0x140011ad3  xor     r12d, r12d
0x140011ad6  cmp     [rsp+68h+arg_20], r12d
0x140011ade  jz      short loc_140011B31
0x140011ae0  mov     rbx, cs:WPP_GLOBAL_Control
0x140011ae7  cmp     rbx, rax
0x140011aea  jz      loc_140011BBC
0x140011af0  bt      dword ptr [rbx+2Ch], 0Dh
0x140011af5  jnb     loc_140011BBC
0x140011afb  mov     rbx, [rbx+18h]
0x140011aff  call    cs:__imp_PsGetCurrentThreadId
0x140011b06  nop     dword ptr [rax+rax+00h]
0x140011b0b  lea     edx, [r12+36h]
0x140011b10  mov     [rsp+68h+var_40], r14
0x140011b15  mov     r9, rax
0x140011b18  mov     [rsp+68h+var_48], rbp
0x140011b1d  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011b24  mov     rcx, rbx
0x140011b27  call    WPP_SF_qqq
0x140011b2c  jmp     loc_140011BBC
0x140011b31  mov     eax, [rsi+908h]
0x140011b37  test    eax, eax
0x140011b39  jz      short loc_140011B51
0x140011b3b  mov     rdx, [rsi+2B0h]; Src
0x140011b42  mov     r8d, eax; Size
0x140011b45  mov     rcx, [r14+230h]; void *
0x140011b4c  call    memmove
0x140011b51  mov     eax, [rsi+908h]
0x140011b57  mov     [r14+0B8h], rax
0x140011b5e  test    rdi, rdi
0x140011b61  jz      short loc_140011BBC
0x140011b63  mov     rcx, [rdi+38h]
0x140011b67  test    rcx, rcx
0x140011b6a  jz      short loc_140011BBC
0x140011b6c  mov     eax, [rsi+1BCCh]
0x140011b72  lea     r9, [rsi+1BD0h]
0x140011b79  mov     [rcx+10h], eax
0x140011b7c  mov     r8d, 7FFFFFFEh
0x140011b82  lea     rax, [rcx+14h]
0x140011b86  mov     edx, 400h
0x140011b8b  test    r8, r8
0x140011b8e  jz      short loc_140011BAD
0x140011b90  movzx   ecx, word ptr [r9]
0x140011b94  test    cx, cx
0x140011b97  jz      short loc_140011BAD
0x140011b99  mov     [rax], cx
0x140011b9c  add     r9, 2
0x140011ba0  add     rax, 2
0x140011ba4  dec     r8
0x140011ba7  sub     rdx, 1
0x140011bab  jnz     short loc_140011B8B
0x140011bad  test    rdx, rdx
0x140011bb0  lea     rcx, [rax-2]
0x140011bb4  cmovnz  rcx, rax
0x140011bb8  mov     [rcx], r12w
0x140011bbc  cmp     dword ptr [rsi+298h], 400007Fh
0x140011bc6  jnz     loc_140011CE2
0x140011bcc  mov     rbx, [rsi+2A0h]
0x140011bd3  test    rbx, rbx
0x140011bd6  jz      loc_140011CA4
0x140011bdc  mov     rdx, [rbx]
0x140011bdf  test    rdx, rdx
0x140011be2  jz      short loc_140011C44
0x140011be4  mov     rcx, rbp
0x140011be7  call    UMRxFreeSecondaryBuffer
0x140011bec  mov     edi, eax
0x140011bee  test    eax, eax
0x140011bf0  jz      short loc_140011C44
0x140011bf2  mov     rbx, cs:WPP_GLOBAL_Control
0x140011bf9  lea     rax, WPP_GLOBAL_Control
0x140011c00  cmp     rbx, rax
0x140011c03  jz      loc_140011ECA
0x140011c09  bt      dword ptr [rbx+2Ch], 0Dh
0x140011c0e  jnb     loc_140011ECA
0x140011c14  mov     rbx, [rbx+18h]
0x140011c18  call    cs:__imp_PsGetCurrentThreadId
0x140011c1f  nop     dword ptr [rax+rax+00h]
0x140011c24  mov     edx, 37h ; '7'
0x140011c29  mov     r9, rax
0x140011c2c  mov     dword ptr [rsp+68h+var_48], edi
0x140011c30  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011c37  mov     rcx, rbx
0x140011c3a  call    WPP_SF_qD
0x140011c3f  jmp     loc_140011ECA
0x140011c44  mov     rcx, [rbx+8]; Handle
0x140011c48  test    rcx, rcx
0x140011c4b  jz      short loc_140011CA4
0x140011c4d  call    cs:__imp_NtClose
0x140011c54  nop     dword ptr [rax+rax+00h]
0x140011c59  mov     edi, eax
0x140011c5b  test    eax, eax
0x140011c5d  jz      short loc_140011CA4
0x140011c5f  mov     rbx, cs:WPP_GLOBAL_Control
0x140011c66  lea     rax, WPP_GLOBAL_Control
0x140011c6d  cmp     rbx, rax
0x140011c70  jz      short loc_140011CA4
0x140011c72  bt      dword ptr [rbx+2Ch], 0Dh
0x140011c77  jnb     short loc_140011CA4
0x140011c79  mov     rbx, [rbx+18h]
0x140011c7d  call    cs:__imp_PsGetCurrentThreadId
0x140011c84  nop     dword ptr [rax+rax+00h]
0x140011c89  mov     edx, 38h ; '8'
0x140011c8e  mov     dword ptr [rsp+68h+var_48], edi
0x140011c92  mov     r9, rax
0x140011c95  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011c9c  mov     rcx, rbx
0x140011c9f  call    WPP_SF_qD
0x140011ca4  cmp     [rsp+68h+arg_20], r12d
0x140011cac  jnz     short loc_140011CE2
0x140011cae  mov     rax, [r14+48h]
0x140011cb2  mov     rcx, [rax+20h]
0x140011cb6  test    rcx, rcx
0x140011cb9  jnz     short loc_140011CC0
0x140011cbb  mov     rcx, r12
0x140011cbe  jmp     short loc_140011CC7
0x140011cc0  mov     rcx, [rcx+88h]
0x140011cc7  cmp     [rcx+14h], r12d
0x140011ccb  jz      short loc_140011CE2
0x140011ccd  cmp     [rbp+80h], r12d
0x140011cd4  jz      short loc_140011CDE
0x140011cd6  mov     eax, 1
0x140011cdb  xchg    eax, [rcx+10h]
0x140011cde  mov     [rcx+14h], r12d
0x140011ce2  mov     rdx, [rsi+280h]
0x140011ce9  test    rdx, rdx
0x140011cec  jz      short loc_140011D38
0x140011cee  mov     rcx, rbp
0x140011cf1  call    UMRxFreeSecondaryBuffer
0x140011cf6  mov     edi, eax
0x140011cf8  test    eax, eax
0x140011cfa  jz      short loc_140011D38
0x140011cfc  mov     rbx, cs:WPP_GLOBAL_Control
0x140011d03  lea     rax, WPP_GLOBAL_Control
0x140011d0a  cmp     rbx, rax
0x140011d0d  jz      loc_140011ECA
0x140011d13  bt      dword ptr [rbx+2Ch], 0Dh
0x140011d18  jnb     loc_140011ECA
0x140011d1e  mov     rbx, [rbx+18h]
0x140011d22  call    cs:__imp_PsGetCurrentThreadId
0x140011d29  nop     dword ptr [rax+rax+00h]
0x140011d2e  mov     edx, 39h ; '9'
0x140011d33  jmp     loc_140011C29
0x140011d38  mov     rdx, [rsi+290h]
0x140011d3f  test    rdx, rdx
0x140011d42  jz      short loc_140011D8E
0x140011d44  mov     rcx, rbp
0x140011d47  call    UMRxFreeSecondaryBuffer
0x140011d4c  mov     edi, eax
0x140011d4e  test    eax, eax
0x140011d50  jz      short loc_140011D8E
0x140011d52  mov     rbx, cs:WPP_GLOBAL_Control
0x140011d59  lea     rax, WPP_GLOBAL_Control
0x140011d60  cmp     rbx, rax
0x140011d63  jz      loc_140011ECA
0x140011d69  bt      dword ptr [rbx+2Ch], 0Dh
0x140011d6e  jnb     loc_140011ECA
0x140011d74  mov     rbx, [rbx+18h]
0x140011d78  call    cs:__imp_PsGetCurrentThreadId
0x140011d7f  nop     dword ptr [rax+rax+00h]
0x140011d84  mov     edx, 3Ah ; ':'
0x140011d89  jmp     loc_140011C29
0x140011d8e  mov     rdx, [rsi+2A0h]
0x140011d95  test    rdx, rdx
0x140011d98  jz      short loc_140011DE4
0x140011d9a  mov     rcx, rbp
0x140011d9d  call    UMRxFreeSecondaryBuffer
0x140011da2  mov     edi, eax
0x140011da4  test    eax, eax
0x140011da6  jz      short loc_140011DE4
0x140011da8  mov     rbx, cs:WPP_GLOBAL_Control
0x140011daf  lea     rax, WPP_GLOBAL_Control
0x140011db6  cmp     rbx, rax
0x140011db9  jz      loc_140011ECA
0x140011dbf  bt      dword ptr [rbx+2Ch], 0Dh
0x140011dc4  jnb     loc_140011ECA
0x140011dca  mov     rbx, [rbx+18h]
0x140011dce  call    cs:__imp_PsGetCurrentThreadId
0x140011dd5  nop     dword ptr [rax+rax+00h]
0x140011dda  mov     edx, 3Bh ; ';'
0x140011ddf  jmp     loc_140011C29
0x140011de4  mov     rdx, [rsi+2B0h]
0x140011deb  test    rdx, rdx
0x140011dee  jz      short loc_140011E3A
0x140011df0  mov     rcx, rbp
0x140011df3  call    UMRxFreeSecondaryBuffer
0x140011df8  mov     edi, eax
0x140011dfa  test    eax, eax
0x140011dfc  jz      short loc_140011E3A
0x140011dfe  mov     rbx, cs:WPP_GLOBAL_Control
0x140011e05  lea     rax, WPP_GLOBAL_Control
0x140011e0c  cmp     rbx, rax
0x140011e0f  jz      loc_140011ECA
0x140011e15  bt      dword ptr [rbx+2Ch], 0Dh
0x140011e1a  jnb     loc_140011ECA
0x140011e20  mov     rbx, [rbx+18h]
0x140011e24  call    cs:__imp_PsGetCurrentThreadId
0x140011e2b  nop     dword ptr [rax+rax+00h]
0x140011e30  mov     edx, 3Ch ; '<'
0x140011e35  jmp     loc_140011C29
0x140011e3a  mov     edi, [rbp+80h]
0x140011e40  test    edi, edi
0x140011e42  jz      short loc_140011E89
0x140011e44  mov     rbx, cs:WPP_GLOBAL_Control
0x140011e4b  lea     rax, WPP_GLOBAL_Control
0x140011e52  cmp     rbx, rax
0x140011e55  jz      short loc_140011ECA
0x140011e57  bt      dword ptr [rbx+2Ch], 0Dh
0x140011e5c  jnb     short loc_140011E89
0x140011e5e  mov     rbx, [rbx+18h]
0x140011e62  call    cs:__imp_PsGetCurrentThreadId
0x140011e69  nop     dword ptr [rax+rax+00h]
0x140011e6e  mov     edx, 3Dh ; '='
0x140011e73  mov     dword ptr [rsp+68h+var_48], edi
0x140011e77  mov     r9, rax
0x140011e7a  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011e81  mov     rcx, rbx
0x140011e84  call    WPP_SF_qD
0x140011e89  mov     rbx, cs:WPP_GLOBAL_Control
0x140011e90  lea     rax, WPP_GLOBAL_Control
0x140011e97  cmp     rbx, rax
0x140011e9a  jz      short loc_140011ECA
0x140011e9c  bt      dword ptr [rbx+2Ch], 0Dh
0x140011ea1  jnb     short loc_140011ECA
0x140011ea3  mov     rbx, [rbx+18h]
0x140011ea7  call    cs:__imp_PsGetCurrentThreadId
0x140011eae  nop     dword ptr [rax+rax+00h]
0x140011eb3  mov     edx, 3Eh ; '>'
0x140011eb8  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011ebf  mov     r9, rax
0x140011ec2  mov     rcx, rbx
0x140011ec5  call    WPP_SF_q
0x140011eca  mov     [rbp+80h], edi
0x140011ed0  mov     eax, 1
0x140011ed5  add     rsp, 30h
0x140011ed9  pop     r14
0x140011edb  pop     r13
0x140011edd  pop     r12
0x140011edf  pop     rdi
0x140011ee0  pop     rsi
0x140011ee1  pop     rbp
0x140011ee2  pop     rbx
0x140011ee3  retn
```
