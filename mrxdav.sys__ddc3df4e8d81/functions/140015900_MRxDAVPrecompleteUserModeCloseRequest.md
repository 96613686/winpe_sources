# MRxDAVPrecompleteUserModeCloseRequest

- ea: `0x140015900`
- end: `0x140015c1c`
- name: `MRxDAVPrecompleteUserModeCloseRequest`
- size: `796`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140001b64`
- `0x140015900`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001593c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001597d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400159d9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015a38`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015aef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015b3f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015ba2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015be2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001593c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001597d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400159d9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015a38`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015aef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015b3f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015ba2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140015be2`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeCloseRequest(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, int a5)
{
  int v8; // ebp
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rbx
  HANDLE v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdi
  unsigned int v18; // eax
  void *v19; // rdx
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rdx
  void *v23; // rdx
  __int64 v24; // rbx
  HANDLE v25; // rax
  void *v26; // rdx
  __int64 v27; // rbx
  HANDLE v28; // rax

  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 116, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqq(v11, 117, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v12, a1, a2);
    }
  }
  if ( a5 )
  {
    v13 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      WPP_SF_qqq(v14, 118, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v15, a1, a2);
    }
  }
  else
  {
    v13 = *(_QWORD *)(*(_QWORD *)(a2 + 72) + 32LL);
    if ( v13 )
      v13 = *(_QWORD *)(v13 + 136);
  }
  if ( *(_DWORD *)(a1 + 128) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v16 = a3[84];
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v17, 119, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v18, v16);
    }
    if ( !a5 && *(_DWORD *)(v13 + 20) )
    {
      _InterlockedExchange((volatile __int32 *)(v13 + 16), 1);
LABEL_22:
      *(_DWORD *)(v13 + 20) = 0;
    }
  }
  else if ( !a5 && *(_DWORD *)(v13 + 20) )
  {
    goto LABEL_22;
  }
  v19 = (void *)a3[82];
  if ( !v19 || (v8 = UMRxFreeSecondaryBuffer(a1, v19)) == 0 )
  {
    v23 = (void *)a3[84];
    if ( v23 )
    {
      v8 = UMRxFreeSecondaryBuffer(a1, v23);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v25 = PsGetCurrentThreadId();
          WPP_SF_qD(v24, 121, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v25, v8);
        }
      }
    }
    v26 = (void *)a3[85];
    if ( !v26 )
      goto LABEL_39;
    v8 = UMRxFreeSecondaryBuffer(a1, v26);
    if ( !v8 )
      goto LABEL_39;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 1;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_39;
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    v22 = 122;
    goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return 1;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    v22 = 120;
LABEL_38:
    WPP_SF_qD(v20, v22, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v21, v8);
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v28 = PsGetCurrentThreadId();
    WPP_SF_qD(v27, 123, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v28, v8);
  }
  return 1;
}

```

## disassembly

```asm
0x140015900  push    rbx
0x140015902  push    rbp
0x140015903  push    rsi
0x140015904  push    rdi
0x140015905  push    r13
0x140015907  push    r15
0x140015909  sub     rsp, 38h
0x14001590d  mov     r13, r8
0x140015910  mov     rdi, rdx
0x140015913  mov     r15, rcx
0x140015916  xor     ebp, ebp
0x140015918  mov     rbx, cs:WPP_GLOBAL_Control
0x14001591f  lea     rax, WPP_GLOBAL_Control
0x140015926  cmp     rbx, rax
0x140015929  jz      loc_1400159B1
0x14001592f  test    dword ptr [rbx+2Ch], 4000h
0x140015936  jz      short loc_14001595D
0x140015938  mov     rbx, [rbx+18h]
0x14001593c  call    cs:__imp_PsGetCurrentThreadId
0x140015943  nop     dword ptr [rax+rax+00h]
0x140015948  lea     edx, [rbp+74h]
0x14001594b  mov     rcx, rbx
0x14001594e  mov     r9, rax
0x140015951  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140015958  call    WPP_SF_q
0x14001595d  mov     rbx, cs:WPP_GLOBAL_Control
0x140015964  lea     rax, WPP_GLOBAL_Control
0x14001596b  cmp     rbx, rax
0x14001596e  jz      short loc_1400159B1
0x140015970  test    dword ptr [rbx+2Ch], 2000h
0x140015977  jz      short loc_1400159AA
0x140015979  mov     rbx, [rbx+18h]
0x14001597d  call    cs:__imp_PsGetCurrentThreadId
0x140015984  nop     dword ptr [rax+rax+00h]
0x140015989  mov     edx, 75h ; 'u'
0x14001598e  mov     [rsp+68h+var_40], rdi
0x140015993  mov     r9, rax
0x140015996  mov     [rsp+68h+var_48], r15
0x14001599b  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400159a2  mov     rcx, rbx
0x1400159a5  call    WPP_SF_qqq
0x1400159aa  lea     rax, WPP_GLOBAL_Control
0x1400159b1  cmp     [rsp+68h+arg_20], ebp
0x1400159b8  jz      loc_140015A78
0x1400159be  xor     esi, esi
0x1400159c0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400159c7  cmp     rbx, rax
0x1400159ca  jz      short loc_140015A0B
0x1400159cc  test    dword ptr [rbx+2Ch], 2000h
0x1400159d3  jz      short loc_140015A04
0x1400159d5  mov     rbx, [rbx+18h]
0x1400159d9  call    cs:__imp_PsGetCurrentThreadId
0x1400159e0  nop     dword ptr [rax+rax+00h]
0x1400159e5  lea     edx, [rsi+76h]
0x1400159e8  mov     [rsp+68h+var_40], rdi
0x1400159ed  mov     r9, rax
0x1400159f0  mov     [rsp+68h+var_48], r15
0x1400159f5  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400159fc  mov     rcx, rbx
0x1400159ff  call    WPP_SF_qqq
0x140015a04  lea     rax, WPP_GLOBAL_Control
0x140015a0b  cmp     [r15+80h], ebp
0x140015a12  jz      loc_140015A9C
0x140015a18  mov     rdi, cs:WPP_GLOBAL_Control
0x140015a1f  cmp     rdi, rax
0x140015a22  jz      short loc_140015A60
0x140015a24  test    dword ptr [rdi+2Ch], 2000h
0x140015a2b  jz      short loc_140015A60
0x140015a2d  mov     rbx, [r13+2A0h]
0x140015a34  mov     rdi, [rdi+18h]
0x140015a38  call    cs:__imp_PsGetCurrentThreadId
0x140015a3f  nop     dword ptr [rax+rax+00h]
0x140015a44  mov     edx, 77h ; 'w'
0x140015a49  mov     [rsp+68h+var_48], rbx
0x140015a4e  mov     r9, rax
0x140015a51  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140015a58  mov     rcx, rdi
0x140015a5b  call    WPP_SF_qS
0x140015a60  cmp     [rsp+68h+arg_20], ebp
0x140015a67  jnz     short loc_140015AAD
0x140015a69  cmp     [rsi+14h], ebp
0x140015a6c  jz      short loc_140015AAD
0x140015a6e  mov     eax, 1
0x140015a73  xchg    eax, [rsi+10h]
0x140015a76  jmp     short loc_140015AAA
0x140015a78  mov     rax, [rdi+48h]
0x140015a7c  mov     rsi, [rax+20h]
0x140015a80  lea     rax, WPP_GLOBAL_Control
0x140015a87  test    rsi, rsi
0x140015a8a  jz      loc_140015A0B
0x140015a90  mov     rsi, [rsi+88h]
0x140015a97  jmp     loc_140015A0B
0x140015a9c  cmp     [rsp+68h+arg_20], ebp
0x140015aa3  jnz     short loc_140015AAD
0x140015aa5  cmp     [rsi+14h], ebp
0x140015aa8  jz      short loc_140015AAD
0x140015aaa  mov     [rsi+14h], ebp
0x140015aad  mov     rdx, [r13+290h]
0x140015ab4  test    rdx, rdx
0x140015ab7  jz      short loc_140015B05
0x140015ab9  mov     rcx, r15
0x140015abc  call    UMRxFreeSecondaryBuffer
0x140015ac1  mov     ebp, eax
0x140015ac3  test    eax, eax
0x140015ac5  jz      short loc_140015B05
0x140015ac7  mov     rbx, cs:WPP_GLOBAL_Control
0x140015ace  lea     rdi, WPP_GLOBAL_Control
0x140015ad5  cmp     rbx, rdi
0x140015ad8  jz      loc_140015C09
0x140015ade  test    dword ptr [rbx+2Ch], 2000h
0x140015ae5  jz      loc_140015BC9
0x140015aeb  mov     rbx, [rbx+18h]
0x140015aef  call    cs:__imp_PsGetCurrentThreadId
0x140015af6  nop     dword ptr [rax+rax+00h]
0x140015afb  mov     edx, 78h ; 'x'
0x140015b00  jmp     loc_140015BB3
0x140015b05  mov     rdx, [r13+2A0h]
0x140015b0c  test    rdx, rdx
0x140015b0f  jz      short loc_140015B68
0x140015b11  mov     rcx, r15
0x140015b14  call    UMRxFreeSecondaryBuffer
0x140015b19  mov     ebp, eax
0x140015b1b  test    eax, eax
0x140015b1d  jz      short loc_140015B68
0x140015b1f  mov     rbx, cs:WPP_GLOBAL_Control
0x140015b26  lea     rdi, WPP_GLOBAL_Control
0x140015b2d  cmp     rbx, rdi
0x140015b30  jz      short loc_140015B6F
0x140015b32  test    dword ptr [rbx+2Ch], 2000h
0x140015b39  jz      short loc_140015B6F
0x140015b3b  mov     rbx, [rbx+18h]
0x140015b3f  call    cs:__imp_PsGetCurrentThreadId
0x140015b46  nop     dword ptr [rax+rax+00h]
0x140015b4b  mov     edx, 79h ; 'y'
0x140015b50  mov     dword ptr [rsp+68h+var_48], ebp
0x140015b54  mov     r9, rax
0x140015b57  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140015b5e  mov     rcx, rbx
0x140015b61  call    WPP_SF_qD
0x140015b66  jmp     short loc_140015B6F
0x140015b68  lea     rdi, WPP_GLOBAL_Control
0x140015b6f  mov     rdx, [r13+2A8h]
0x140015b76  test    rdx, rdx
0x140015b79  jz      short loc_140015BC9
0x140015b7b  mov     rcx, r15
0x140015b7e  call    UMRxFreeSecondaryBuffer
0x140015b83  mov     ebp, eax
0x140015b85  test    eax, eax
0x140015b87  jz      short loc_140015BC9
0x140015b89  mov     rbx, cs:WPP_GLOBAL_Control
0x140015b90  cmp     rbx, rdi
0x140015b93  jz      short loc_140015C09
0x140015b95  test    dword ptr [rbx+2Ch], 2000h
0x140015b9c  jz      short loc_140015BC9
0x140015b9e  mov     rbx, [rbx+18h]
0x140015ba2  call    cs:__imp_PsGetCurrentThreadId
0x140015ba9  nop     dword ptr [rax+rax+00h]
0x140015bae  mov     edx, 7Ah ; 'z'
0x140015bb3  mov     r9, rax
0x140015bb6  mov     dword ptr [rsp+68h+var_48], ebp
0x140015bba  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140015bc1  mov     rcx, rbx
0x140015bc4  call    WPP_SF_qD
0x140015bc9  mov     rbx, cs:WPP_GLOBAL_Control
0x140015bd0  cmp     rbx, rdi
0x140015bd3  jz      short loc_140015C09
0x140015bd5  test    dword ptr [rbx+2Ch], 4000h
0x140015bdc  jz      short loc_140015C09
0x140015bde  mov     rbx, [rbx+18h]
0x140015be2  call    cs:__imp_PsGetCurrentThreadId
0x140015be9  nop     dword ptr [rax+rax+00h]
0x140015bee  mov     edx, 7Bh ; '{'
0x140015bf3  mov     dword ptr [rsp+68h+var_48], ebp
0x140015bf7  mov     r9, rax
0x140015bfa  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140015c01  mov     rcx, rbx
0x140015c04  call    WPP_SF_qD
0x140015c09  mov     eax, 1
0x140015c0e  add     rsp, 38h
0x140015c12  pop     r15
0x140015c14  pop     r13
0x140015c16  pop     rdi
0x140015c17  pop     rsi
0x140015c18  pop     rbp
0x140015c19  pop     rbx
0x140015c1a  retn
```
