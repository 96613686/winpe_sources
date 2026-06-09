# SafeModeDecryptNetBuffer(_VELAN *,NWIFI_MSDU_MPDU *,DOT11_MAC_STATE_ENTRY *,DOT11_80211E_CONTROL *)

- ea: `0x140010a04`
- end: `0x140010bfa`
- name: `?SafeModeDecryptNetBuffer@@YAJPEAU_VELAN@@PEAUNWIFI_MSDU_MPDU@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_80211E_CONTROL@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(struct _VELAN *, struct NWIFI_MSDU_MPDU *, struct DOT11_MAC_STATE_ENTRY *, struct DOT11_80211E_CONTROL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000eda8`

## callees

- `0x140010a04`
- `0x140011194`
- `0x14001aaac`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010a9e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010a9e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010b7c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010b7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010b8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010b8d`

## pseudocode

```c
__int64 __fastcall SafeModeDecryptNetBuffer(
        struct _VELAN *a1,
        struct NWIFI_MSDU_MPDU *a2,
        struct DOT11_MAC_STATE_ENTRY *a3,
        struct DOT11_80211E_CONTROL *a4)
{
  _NET_BUFFER_LIST *pNdisPacket; // r13
  struct _NET_BUFFER *FirstNetBuffer; // r15
  int v10; // ebp
  char *v11; // rax
  struct _NET_BUFFER_LIST *v12; // rcx
  struct SAFEMODE_DECRYPT_UNDO_CTX *v13; // rbx
  struct SAFEMODE_DECRYPT_UNDO_CTX *v14; // rdi
  unsigned __int16 v15; // r14
  struct DOT11_RMH_UNDO_LOG *v16; // r8
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  struct DOT11_MAC_STATE_ENTRY *v20; // [rsp+20h] [rbp-188h]
  struct DOT11_80211E_CONTROL *v21; // [rsp+28h] [rbp-180h]
  struct DOT11_80211E_CONTROL *v22; // [rsp+30h] [rbp-178h]
  struct DOT11_MAC_STATE_ENTRY *v23; // [rsp+38h] [rbp-170h]
  _QWORD v24[34]; // [rsp+40h] [rbp-168h] BYREF

  v22 = a4;
  v23 = a3;
  memset(v24, 0, 0x108u);
  pNdisPacket = a2->MSDUCore.pNdisPacket;
  FirstNetBuffer = pNdisPacket->FirstNetBuffer;
  *(_OWORD *)&v24[1] = 0;
  v10 = DecryptMPDU(a1, a2->MPDUs, (struct DOT11_RMH_UNDO_LOG *)&v24[1], FirstNetBuffer, a3, a4);
  if ( v10 >= 0 )
  {
    LOWORD(v24[0]) = 1;
    v11 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
    if ( v11 )
    {
      *(_QWORD *)v11 = &Lookaside;
      v15 = 1;
      v13 = (struct SAFEMODE_DECRYPT_UNDO_CTX *)(v11 + 16);
      *((_DWORD *)v11 + 2) = 828994423;
      v14 = (struct SAFEMODE_DECRYPT_UNDO_CTX *)(v11 + 16);
      *((_WORD *)v11 + 8) = v24[0];
      v10 = 0;
      *(_OWORD *)(v11 + 24) = *(_OWORD *)&v24[1];
      while ( 1 )
      {
        FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        if ( v15 >= a2->usNumMPDUs || !FirstNetBuffer )
        {
          a2->MSDUCore.pvLookaheadBuf = (char *)a2->MSDUCore.pvLookaheadBuf + 8;
          a2->MSDUCore.uLookaheadBufSize -= 16;
          v17 = *(_QWORD *)&pNdisPacket->Context->ContextData[pNdisPacket->Context->Offset];
          v18 = *(_QWORD **)(v17 + 40);
          *(_QWORD *)(v17 + 40) = v18 + 3;
          *v18 = SafeModeDecryptCompletion;
          v18[1] = v13;
          v18[2] = 0;
          return (unsigned int)v10;
        }
        v16 = (struct DOT11_RMH_UNDO_LOG *)((char *)v13 + 16 * v15 + 8);
        v21 = v22;
        v20 = v23;
        *v16 = 0;
        v10 = DecryptMPDU(a1, &a2->MPDUs[v15], v16, FirstNetBuffer, v20, v21);
        if ( v10 < 0 )
          break;
        ++*(_WORD *)v13;
        ++v15;
      }
      if ( !v13 )
        return (unsigned int)v10;
    }
    else
    {
      v13 = (struct SAFEMODE_DECRYPT_UNDO_CTX *)v24;
      v14 = 0;
      v10 = -1073741670;
    }
    SafeModeDecryptCompletionHelper(v12, v13);
    if ( v13 == v14 )
    {
      if ( *((_QWORD *)v13 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 - 2), (char *)v13 - 16);
      else
        ExFreePoolWithTag((char *)v13 - 16, *((_DWORD *)v13 - 2));
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140010a04  push    rbx
0x140010a06  push    rbp
0x140010a07  push    rsi
0x140010a08  push    rdi
0x140010a09  push    r12
0x140010a0b  push    r13
0x140010a0d  push    r14
0x140010a0f  push    r15
0x140010a11  sub     rsp, 168h
0x140010a18  mov     rax, cs:__security_cookie
0x140010a1f  xor     rax, rsp
0x140010a22  mov     [rsp+1A8h+var_58], rax
0x140010a2a  mov     rbx, r8
0x140010a2d  mov     [rsp+1A8h+var_178], r9
0x140010a32  mov     rsi, rdx
0x140010a35  mov     [rsp+1A8h+var_170], rbx
0x140010a3a  mov     r12, rcx
0x140010a3d  xor     edx, edx; Val
0x140010a3f  mov     r8d, 108h; Size
0x140010a45  lea     rcx, [rsp+1A8h+var_168]; void *
0x140010a4a  mov     rdi, r9
0x140010a4d  call    memset
0x140010a52  mov     r13, [rsi+20h]
0x140010a56  lea     rdx, [rsi+30h]; struct NWIFI_MPDU *
0x140010a5a  xorps   xmm0, xmm0
0x140010a5d  mov     [rsp+1A8h+var_180], rdi; struct DOT11_80211E_CONTROL *
0x140010a62  lea     r8, [rsp+1A8h+var_160]; struct DOT11_RMH_UNDO_LOG *
0x140010a67  mov     [rsp+1A8h+var_188], rbx; struct DOT11_MAC_STATE_ENTRY *
0x140010a6c  mov     rcx, r12; struct _VELAN *
0x140010a6f  mov     r15, [r13+8]
0x140010a73  mov     r9, r15; struct _NET_BUFFER *
0x140010a76  movups  xmmword ptr [rsp+1A8h+var_160.pNdisBuffer], xmm0
0x140010a7b  call    ?DecryptMPDU@@YAJPEAU_VELAN@@PEAUNWIFI_MPDU@@PEAUDOT11_RMH_UNDO_LOG@@PEAU_NET_BUFFER@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_80211E_CONTROL@@@Z; DecryptMPDU(_VELAN *,NWIFI_MPDU *,DOT11_RMH_UNDO_LOG *,_NET_BUFFER *,DOT11_MAC_STATE_ENTRY *,DOT11_80211E_CONTROL *)
0x140010a80  mov     ebp, eax
0x140010a82  test    eax, eax
0x140010a84  js      loc_140010BD3
0x140010a8a  lea     rbx, Lookaside
0x140010a91  mov     edi, 1
0x140010a96  mov     rcx, rbx; Lookaside
0x140010a99  mov     [rsp+1A8h+var_168], di
0x140010a9e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140010aa5  nop     dword ptr [rax+rax+00h]
0x140010aaa  test    rax, rax
0x140010aad  jnz     short loc_140010AC0
0x140010aaf  lea     rbx, [rsp+1A8h+var_168]
0x140010ab4  xor     edi, edi
0x140010ab6  mov     ebp, 0C000009Ah
0x140010abb  jmp     loc_140010B5D
0x140010ac0  mov     [rax], rbx
0x140010ac3  movzx   r14d, di
0x140010ac7  lea     rbx, [rax+10h]
0x140010acb  mov     dword ptr [rax+8], 31697377h
0x140010ad2  movzx   eax, [rsp+1A8h+var_168]
0x140010ad7  mov     rdi, rbx
0x140010ada  mov     [rbx], ax
0x140010add  xor     ebp, ebp
0x140010adf  movups  xmm0, xmmword ptr [rsp+1A8h+var_160.pNdisBuffer]
0x140010ae4  movdqu  xmmword ptr [rbx+8], xmm0
0x140010ae9  mov     r15, [r15]
0x140010aec  cmp     r14w, [rsi+28h]
0x140010af1  jnb     loc_140010B9B
0x140010af7  test    r15, r15
0x140010afa  jz      loc_140010B9B
0x140010b00  movzx   ecx, r14w
0x140010b04  xorps   xmm0, xmm0
0x140010b07  mov     r8d, ecx
0x140010b0a  mov     r9, r15; struct _NET_BUFFER *
0x140010b0d  add     rcx, 2
0x140010b11  shl     r8, 4
0x140010b15  add     r8, 8
0x140010b19  add     r8, rbx; struct DOT11_RMH_UNDO_LOG *
0x140010b1c  lea     rax, [rcx+rcx*2]
0x140010b20  mov     rcx, r12; struct _VELAN *
0x140010b23  lea     rdx, [rsi+rax*8]; struct NWIFI_MPDU *
0x140010b27  mov     rax, [rsp+1A8h+var_178]
0x140010b2c  mov     [rsp+1A8h+var_180], rax; struct DOT11_80211E_CONTROL *
0x140010b31  mov     rax, [rsp+1A8h+var_170]
0x140010b36  mov     [rsp+1A8h+var_188], rax; struct DOT11_MAC_STATE_ENTRY *
0x140010b3b  movups  xmmword ptr [r8], xmm0
0x140010b3f  call    ?DecryptMPDU@@YAJPEAU_VELAN@@PEAUNWIFI_MPDU@@PEAUDOT11_RMH_UNDO_LOG@@PEAU_NET_BUFFER@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_80211E_CONTROL@@@Z; DecryptMPDU(_VELAN *,NWIFI_MPDU *,DOT11_RMH_UNDO_LOG *,_NET_BUFFER *,DOT11_MAC_STATE_ENTRY *,DOT11_80211E_CONTROL *)
0x140010b44  mov     ebp, eax
0x140010b46  test    eax, eax
0x140010b48  js      short loc_140010B58
0x140010b4a  mov     eax, 1
0x140010b4f  add     [rbx], ax
0x140010b52  add     r14w, ax
0x140010b56  jmp     short loc_140010AE9
0x140010b58  test    rbx, rbx
0x140010b5b  jz      short loc_140010BD3
0x140010b5d  mov     rdx, rbx; struct SAFEMODE_DECRYPT_UNDO_CTX *
0x140010b60  call    ?SafeModeDecryptCompletionHelper@@YAXPEAU_NET_BUFFER_LIST@@PEAUSAFEMODE_DECRYPT_UNDO_CTX@@@Z; SafeModeDecryptCompletionHelper(_NET_BUFFER_LIST *,SAFEMODE_DECRYPT_UNDO_CTX *)
0x140010b65  cmp     rbx, rdi
0x140010b68  jnz     short loc_140010BD3
0x140010b6a  lea     rcx, [rbx-10h]; P
0x140010b6e  mov     rax, [rcx]
0x140010b71  test    rax, rax
0x140010b74  jz      short loc_140010B8A
0x140010b76  mov     rdx, rcx; Entry
0x140010b79  mov     rcx, rax; Lookaside
0x140010b7c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010b83  nop     dword ptr [rax+rax+00h]
0x140010b88  jmp     short loc_140010BD3
0x140010b8a  mov     edx, [rcx+8]; Tag
0x140010b8d  call    cs:__imp_ExFreePoolWithTag
0x140010b94  nop     dword ptr [rax+rax+00h]
0x140010b99  jmp     short loc_140010BD3
0x140010b9b  add     qword ptr [rsi+18h], 8
0x140010ba0  add     dword ptr [rsi+10h], 0FFFFFFF0h
0x140010ba4  mov     rcx, [r13+10h]
0x140010ba8  movzx   eax, word ptr [rcx+0Ah]
0x140010bac  mov     rdx, [rax+rcx+10h]
0x140010bb1  mov     rcx, [rdx+28h]
0x140010bb5  lea     rax, [rcx+18h]
0x140010bb9  mov     [rdx+28h], rax
0x140010bbd  lea     rax, ?SafeModeDecryptCompletion@@YAXPEAU_NET_BUFFER_LIST@@PEAX1@Z; SafeModeDecryptCompletion(_NET_BUFFER_LIST *,void *,void *)
0x140010bc4  mov     [rcx], rax
0x140010bc7  mov     [rcx+8], rbx
0x140010bcb  mov     qword ptr [rcx+10h], 0
0x140010bd3  mov     eax, ebp
0x140010bd5  mov     rcx, [rsp+1A8h+var_58]
0x140010bdd  xor     rcx, rsp; StackCookie
0x140010be0  call    __security_check_cookie
0x140010be5  add     rsp, 168h
0x140010bec  pop     r15
0x140010bee  pop     r14
0x140010bf0  pop     r13
0x140010bf2  pop     r12
0x140010bf4  pop     rdi
0x140010bf5  pop     rsi
0x140010bf6  pop     rbp
0x140010bf7  pop     rbx
0x140010bf8  retn
```
