# MRxDAVPrecompleteUserModeSetFileInformationRequest

- ea: `0x140021a50`
- end: `0x140021c00`
- name: `MRxDAVPrecompleteUserModeSetFileInformationRequest`
- size: `432`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001680`
- `0x140001b64`
- `0x140021a50`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140021a97`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021af9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021b4c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021b90`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021bc8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021a97`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021af9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021b4c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021b90`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021bc8`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeSetFileInformationRequest(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        int a5)
{
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  void *v10; // rdx
  int v11; // ebp
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rdx
  void *v15; // rdx
  void *v16; // rdx
  int v17; // esi
  __int64 v18; // rbx
  HANDLE v19; // rax
  int v20; // edi
  __int64 v21; // rbx
  HANDLE v22; // rax

  if ( a5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qqq(v8, 86, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId, a1, a2);
  }
  v10 = (void *)a3[81];
  if ( v10 && (v11 = UMRxFreeSecondaryBuffer(a1, v10)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      v14 = 87;
LABEL_10:
      WPP_SF_qD(v12, v14, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v13, v11);
    }
  }
  else
  {
    v15 = (void *)a3[82];
    if ( v15 && (v11 = UMRxFreeSecondaryBuffer(a1, v15)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        v14 = 88;
        goto LABEL_10;
      }
    }
    else
    {
      v16 = (void *)a3[83];
      if ( v16 && (v17 = UMRxFreeSecondaryBuffer(a1, v16)) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        {
          v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v19 = PsGetCurrentThreadId();
          WPP_SF_qD(v18, 89, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v19, v17);
        }
      }
      else
      {
        v20 = *(_DWORD *)(a1 + 128);
        if ( v20
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        {
          v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v22 = PsGetCurrentThreadId();
          WPP_SF_qD(v21, 90, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v22, v20);
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140021a50  push    rbx
0x140021a52  push    rbp
0x140021a53  push    rsi
0x140021a54  push    rdi
0x140021a55  push    r12
0x140021a57  push    r14
0x140021a59  push    r15
0x140021a5b  sub     rsp, 30h
0x140021a5f  cmp     [rsp+68h+arg_20], 0
0x140021a67  lea     r12, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021a6e  mov     rsi, r8
0x140021a71  lea     r15, WPP_GLOBAL_Control
0x140021a78  mov     rbp, rdx
0x140021a7b  mov     rdi, rcx
0x140021a7e  jz      short loc_140021AC0
0x140021a80  mov     rbx, cs:WPP_GLOBAL_Control
0x140021a87  cmp     rbx, r15
0x140021a8a  jz      short loc_140021AC0
0x140021a8c  bt      dword ptr [rbx+2Ch], 0Dh
0x140021a91  jnb     short loc_140021AC0
0x140021a93  mov     rbx, [rbx+18h]
0x140021a97  call    cs:__imp_PsGetCurrentThreadId
0x140021a9e  nop     dword ptr [rax+rax+00h]
0x140021aa3  mov     edx, 56h ; 'V'
0x140021aa8  mov     [rsp+68h+var_40], rbp
0x140021aad  mov     r9, rax
0x140021ab0  mov     [rsp+68h+var_48], rdi
0x140021ab5  mov     r8, r12
0x140021ab8  mov     rcx, rbx
0x140021abb  call    WPP_SF_qqq
0x140021ac0  mov     rdx, [rsi+288h]
0x140021ac7  test    rdx, rdx
0x140021aca  jz      short loc_140021B13
0x140021acc  mov     rcx, rdi
0x140021acf  call    UMRxFreeSecondaryBuffer
0x140021ad4  mov     ebp, eax
0x140021ad6  test    eax, eax
0x140021ad8  jz      short loc_140021B13
0x140021ada  mov     rbx, cs:WPP_GLOBAL_Control
0x140021ae1  cmp     rbx, r15
0x140021ae4  jz      loc_140021BEB
0x140021aea  bt      dword ptr [rbx+2Ch], 0Dh
0x140021aef  jnb     loc_140021BEB
0x140021af5  mov     rbx, [rbx+18h]
0x140021af9  call    cs:__imp_PsGetCurrentThreadId
0x140021b00  nop     dword ptr [rax+rax+00h]
0x140021b05  mov     edx, 57h ; 'W'
0x140021b0a  mov     dword ptr [rsp+68h+var_48], ebp
0x140021b0e  jmp     loc_140021BDD
0x140021b13  mov     rdx, [rsi+290h]
0x140021b1a  test    rdx, rdx
0x140021b1d  jz      short loc_140021B5F
0x140021b1f  mov     rcx, rdi
0x140021b22  call    UMRxFreeSecondaryBuffer
0x140021b27  mov     ebp, eax
0x140021b29  test    eax, eax
0x140021b2b  jz      short loc_140021B5F
0x140021b2d  mov     rbx, cs:WPP_GLOBAL_Control
0x140021b34  cmp     rbx, r15
0x140021b37  jz      loc_140021BEB
0x140021b3d  bt      dword ptr [rbx+2Ch], 0Dh
0x140021b42  jnb     loc_140021BEB
0x140021b48  mov     rbx, [rbx+18h]
0x140021b4c  call    cs:__imp_PsGetCurrentThreadId
0x140021b53  nop     dword ptr [rax+rax+00h]
0x140021b58  mov     edx, 58h ; 'X'
0x140021b5d  jmp     short loc_140021B0A
0x140021b5f  mov     rdx, [rsi+298h]
0x140021b66  test    rdx, rdx
0x140021b69  jz      short loc_140021BA7
0x140021b6b  mov     rcx, rdi
0x140021b6e  call    UMRxFreeSecondaryBuffer
0x140021b73  mov     esi, eax
0x140021b75  test    eax, eax
0x140021b77  jz      short loc_140021BA7
0x140021b79  mov     rbx, cs:WPP_GLOBAL_Control
0x140021b80  cmp     rbx, r15
0x140021b83  jz      short loc_140021BEB
0x140021b85  bt      dword ptr [rbx+2Ch], 0Dh
0x140021b8a  jnb     short loc_140021BEB
0x140021b8c  mov     rbx, [rbx+18h]
0x140021b90  call    cs:__imp_PsGetCurrentThreadId
0x140021b97  nop     dword ptr [rax+rax+00h]
0x140021b9c  mov     edx, 59h ; 'Y'
0x140021ba1  mov     dword ptr [rsp+68h+var_48], esi
0x140021ba5  jmp     short loc_140021BDD
0x140021ba7  mov     edi, [rdi+80h]
0x140021bad  test    edi, edi
0x140021baf  jz      short loc_140021BEB
0x140021bb1  mov     rbx, cs:WPP_GLOBAL_Control
0x140021bb8  cmp     rbx, r15
0x140021bbb  jz      short loc_140021BEB
0x140021bbd  bt      dword ptr [rbx+2Ch], 0Dh
0x140021bc2  jnb     short loc_140021BEB
0x140021bc4  mov     rbx, [rbx+18h]
0x140021bc8  call    cs:__imp_PsGetCurrentThreadId
0x140021bcf  nop     dword ptr [rax+rax+00h]
0x140021bd4  mov     edx, 5Ah ; 'Z'
0x140021bd9  mov     dword ptr [rsp+68h+var_48], edi
0x140021bdd  mov     r9, rax
0x140021be0  mov     r8, r12
0x140021be3  mov     rcx, rbx
0x140021be6  call    WPP_SF_qD
0x140021beb  mov     eax, 1
0x140021bf0  add     rsp, 30h
0x140021bf4  pop     r15
0x140021bf6  pop     r14
0x140021bf8  pop     r12
0x140021bfa  pop     rdi
0x140021bfb  pop     rsi
0x140021bfc  pop     rbp
0x140021bfd  pop     rbx
0x140021bfe  retn
```
