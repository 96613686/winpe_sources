# MsQuicStreamProvideReceiveBuffers

- ea: `0x140029bb0`
- end: `0x140029eea`
- name: `MsQuicStreamProvideReceiveBuffers`
- size: `826`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000c440`
- `0x14000c4b8`
- `0x1400290b4`
- `0x1400296c8`
- `0x14002974c`
- `0x140029bb0`
- `0x14002d9dc`
- `0x14002da98`
- `0x1400337e4`
- `0x14003c980`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029ea9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140029e85`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140029e85`
- `ntoskrnl!ExQueryDepthSList` at `0x140029e59`
- `ntoskrnl!ExQueryDepthSList` at `0x140029e59`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140029c9c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140029c9c`

## pseudocode

```c
__int64 __fastcall MsQuicStreamProvideReceiveBuffers(__int64 a1, __int64 a2, int *a3)
{
  unsigned int v4; // r14d
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  _DWORD *v8; // rax
  __int64 v9; // rdi
  HANDLE CurrentThreadId; // rax
  char v11; // r12
  unsigned int v12; // r13d
  PSLIST_ENTRY v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r9
  _QWORD *v22; // rax
  __int64 v23; // r9
  _QWORD *v24; // rcx
  struct _SLIST_ENTRY *v25; // rsi
  __int64 v26; // rdi
  PVOID v27; // rcx
  PVOID P; // [rsp+20h] [rbp-10h] BYREF
  PVOID *p_P; // [rsp+28h] [rbp-8h]
  HANDLE v31; // [rsp+70h] [rbp+40h]
  HANDLE v32; // [rsp+88h] [rbp+58h]

  p_P = &P;
  v4 = a2;
  P = &P;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 28, a1);
  v6 = 0;
  if ( a1 && *(_DWORD *)a1 == 5 && a3 && v4 )
  {
    v7 = 0;
    v8 = a3;
    while ( *v8 )
    {
      ++v7;
      v8 += 4;
      if ( v7 >= v4 )
      {
        if ( (*(_BYTE *)(a1 + 92) & 8) != 0 )
          CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1434, "!Stream->Flags.HandleClosed");
        if ( (*(_BYTE *)(a1 + 92) & 0x40) != 0 )
          CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1435, "!Stream->Flags.Freed");
        v9 = *(_QWORD *)(a1 + 72);
        if ( (*(_BYTE *)(v9 + 252) & 0x40) != 0 && (*(_BYTE *)(v9 + 249) & 4) != 0 )
        {
          CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1438, "!Connection->State.Freed");
          __int2c();
        }
        CurrentThreadId = PsGetCurrentThreadId();
        v11 = *(_BYTE *)(v9 + 251);
        v32 = CurrentThreadId;
        v31 = *(HANDLE *)(v9 + 256);
        if ( (*(_BYTE *)(a1 + 91) & 0x10) == 0 )
        {
          if ( (*(_BYTE *)(a1 + 88) & 0x10) == 0 )
          {
            v6 = -1073741436;
            goto LABEL_34;
          }
          *(_BYTE *)(v9 + 251) = v11 | 0x20;
          QuicStreamSwitchToAppOwnedBuffers(a1);
          *(_BYTE *)(v9 + 251) ^= (v11 ^ *(_BYTE *)(v9 + 251)) & 0x20;
        }
        v12 = 0;
        while ( 1 )
        {
          v13 = CxPlatPoolAlloc(*(_QWORD *)(v9 + 72) + 2112LL);
          if ( !v13 )
            break;
          v15 = *a3;
          ++v12;
          v16 = *((_QWORD *)a3 + 1);
          a3 += 4;
          LODWORD(v13[1].Next) = v15;
          LOBYTE(v15) = BYTE4(v13[1].Next);
          *((_QWORD *)&v13[1].Next + 1) = v16;
          BYTE4(v13[1].Next) = v15 & 0xFC | 2;
          v17 = p_P;
          v13->Next = (struct _SLIST_ENTRY *)&P;
          *((_QWORD *)&v13->Next + 1) = v17;
          *v17 = v13;
          p_P = (PVOID *)&v13->Next;
          if ( v12 >= v4 )
          {
            if ( v31 == v32 )
            {
              *(_BYTE *)(v9 + 251) |= 0x20u;
              v6 = QuicStreamProvideRecvBuffers(a1, &P);
              *(_BYTE *)(v9 + 251) ^= (v11 ^ *(_BYTE *)(v9 + 251)) & 0x20;
            }
            else
            {
              v18 = QuicOperationAlloc(*(_QWORD *)(v9 + 72), 0);
              v21 = v18;
              if ( v18 )
              {
                **(_DWORD **)(v18 + 24) = 16;
                *(_QWORD *)(*(_QWORD *)(v18 + 24) + 24LL) = a1;
                v22 = (_QWORD *)(*(_QWORD *)(v18 + 24) + 32LL);
                v22[1] = v22;
                *v22 = v22;
                CxPlatListMoveItems(&P, *(_QWORD *)(v21 + 24) + 32LL);
                CxPlatRefIncrement(a1 + 16);
                QuicConnQueueOper(v9, v23);
              }
              else
              {
                v6 = -1073741801;
                if ( (Microsoft_QuicEnableBits & 2) != 0 )
                  McTemplateU0sx_EtwWriteTransfer(v20, v19, "STRM_PROVIDE_RECV_BUFFERS, operation", 0);
              }
            }
            goto LABEL_34;
          }
        }
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(v14, 0, "provided_chunk", 0);
        v6 = -1073741801;
        goto LABEL_34;
      }
    }
  }
  v6 = -1073741811;
LABEL_34:
  while ( 1 )
  {
    v24 = P;
    if ( P == &P )
      break;
    v25 = (struct _SLIST_ENTRY *)((char *)P - 16);
    P = *(PVOID *)P;
    *((_QWORD *)P + 1) = &P;
    v26 = *(v24 - 2);
    ++*(_DWORD *)(v26 + 28);
    if ( ExQueryDepthSList((PSLIST_HEADER)v26) < *(_WORD *)(v26 + 16) )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v26, v25);
    }
    else
    {
      ++*(_DWORD *)(v26 + 32);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *, __int64))(v26 + 56))(v25, v26);
    }
    v27 = P;
    P = *(PVOID *)P;
    *((_QWORD *)P + 1) = &P;
    ExFreePoolWithTag(v27, 0x33316351u);
  }
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(P, QuicApiExitStatus, v6);
  return v6;
}

```

## disassembly

```asm
0x140029bb0  mov     [rsp-38h+arg_8], rbx
0x140029bb5  push    rbp
0x140029bb6  push    rsi
0x140029bb7  push    rdi
0x140029bb8  push    r12
0x140029bba  push    r13
0x140029bbc  push    r14
0x140029bbe  push    r15
0x140029bc0  mov     rbp, rsp
0x140029bc3  sub     rsp, 30h
0x140029bc7  test    cs:Microsoft_QuicEnableBits, 8
0x140029bce  lea     rax, [rbp+P]
0x140029bd2  mov     [rbp+var_8], rax
0x140029bd6  mov     r15, r8
0x140029bd9  lea     rax, [rbp+P]
0x140029bdd  mov     r14d, edx
0x140029be0  mov     [rbp+P], rax
0x140029be4  mov     rsi, rcx
0x140029be7  jz      short loc_140029BF7
0x140029be9  mov     r9, rcx
0x140029bec  mov     r8d, 1Ch
0x140029bf2  call    McTemplateU0qp_EtwWriteTransfer
0x140029bf7  xor     ebx, ebx
0x140029bf9  test    rsi, rsi
0x140029bfc  jz      loc_140029E2B
0x140029c02  cmp     dword ptr [rsi], 5
0x140029c05  jnz     loc_140029E2B
0x140029c0b  test    r15, r15
0x140029c0e  jz      loc_140029E2B
0x140029c14  test    r14d, r14d
0x140029c17  jz      loc_140029E2B
0x140029c1d  mov     ecx, ebx
0x140029c1f  mov     rax, r15
0x140029c22  cmp     [rax], ebx
0x140029c24  jz      loc_140029E2B
0x140029c2a  inc     ecx
0x140029c2c  add     rax, 10h
0x140029c30  cmp     ecx, r14d
0x140029c33  jb      short loc_140029C22
0x140029c35  test    byte ptr [rsi+5Ch], 8
0x140029c39  lea     r12, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140029c40  jz      short loc_140029C56
0x140029c42  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x140029c49  mov     edx, 59Ah
0x140029c4e  mov     rcx, r12
0x140029c51  call    CxPlatLogAssert
0x140029c56  test    byte ptr [rsi+5Ch], 40h
0x140029c5a  jz      short loc_140029C70
0x140029c5c  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x140029c63  mov     edx, 59Bh
0x140029c68  mov     rcx, r12
0x140029c6b  call    CxPlatLogAssert
0x140029c70  mov     rdi, [rsi+48h]
0x140029c74  test    byte ptr [rdi+0FCh], 40h
0x140029c7b  jz      short loc_140029C9C
0x140029c7d  test    byte ptr [rdi+0F9h], 4
0x140029c84  jz      short loc_140029C9C
0x140029c86  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x140029c8d  mov     edx, 59Eh
0x140029c92  mov     rcx, r12
0x140029c95  call    CxPlatLogAssert
0x140029c9a  int     2Ch; Windows NT - assertion failure
0x140029c9c  call    cs:__imp_PsGetCurrentThreadId
0x140029ca3  nop     dword ptr [rax+rax+00h]
0x140029ca8  test    byte ptr [rsi+5Bh], 10h
0x140029cac  mov     r12b, [rdi+0FBh]
0x140029cb3  mov     [rbp+arg_18], rax
0x140029cb7  mov     rax, [rdi+100h]
0x140029cbe  mov     [rbp+arg_0], rax
0x140029cc2  jnz     short loc_140029CF7
0x140029cc4  test    byte ptr [rsi+58h], 10h
0x140029cc8  jz      loc_140029D8B
0x140029cce  mov     al, r12b
0x140029cd1  mov     rcx, rsi
0x140029cd4  or      al, 20h
0x140029cd6  mov     [rdi+0FBh], al
0x140029cdc  call    QuicStreamSwitchToAppOwnedBuffers
0x140029ce1  mov     al, [rdi+0FBh]
0x140029ce7  mov     cl, al
0x140029ce9  xor     cl, r12b
0x140029cec  and     cl, 20h
0x140029cef  xor     cl, al
0x140029cf1  mov     [rdi+0FBh], cl
0x140029cf7  mov     r13d, ebx
0x140029cfa  test    r14d, r14d
0x140029cfd  jz      short loc_140029D51
0x140029cff  mov     rcx, [rdi+48h]
0x140029d03  add     rcx, 840h
0x140029d0a  call    CxPlatPoolAlloc
0x140029d0f  mov     rdx, rax
0x140029d12  test    rax, rax
0x140029d15  jz      short loc_140029D95
0x140029d17  mov     eax, [r15]
0x140029d1a  inc     r13d
0x140029d1d  mov     rcx, [r15+8]
0x140029d21  add     r15, 10h
0x140029d25  mov     [rdx+10h], eax
0x140029d28  mov     al, [rdx+14h]
0x140029d2b  mov     [rdx+18h], rcx
0x140029d2f  and     al, 0FEh
0x140029d31  or      al, 2
0x140029d33  lea     rcx, [rbp+P]
0x140029d37  mov     [rdx+14h], al
0x140029d3a  mov     rax, [rbp+var_8]
0x140029d3e  mov     [rdx], rcx
0x140029d41  mov     [rdx+8], rax
0x140029d45  mov     [rax], rdx
0x140029d48  mov     [rbp+var_8], rdx
0x140029d4c  cmp     r13d, r14d
0x140029d4f  jb      short loc_140029CFF
0x140029d51  mov     rax, [rbp+arg_0]
0x140029d55  cmp     rax, [rbp+arg_18]
0x140029d59  jnz     short loc_140029DB4
0x140029d5b  or      byte ptr [rdi+0FBh], 20h
0x140029d62  lea     rdx, [rbp+P]
0x140029d66  mov     rcx, rsi
0x140029d69  call    QuicStreamProvideRecvBuffers
0x140029d6e  mov     cl, [rdi+0FBh]
0x140029d74  mov     ebx, eax
0x140029d76  mov     dl, cl
0x140029d78  xor     dl, r12b
0x140029d7b  and     dl, 20h
0x140029d7e  xor     dl, cl
0x140029d80  mov     [rdi+0FBh], dl
0x140029d86  jmp     loc_140029E30
0x140029d8b  mov     ebx, 0C0000184h
0x140029d90  jmp     loc_140029E30
0x140029d95  test    cs:Microsoft_QuicEnableBits, 2
0x140029d9c  jz      short loc_140029DAD
0x140029d9e  xor     r9d, r9d
0x140029da1  lea     r8, aProvidedChunk; "provided_chunk"
0x140029da8  call    McTemplateU0sx_EtwWriteTransfer
0x140029dad  mov     ebx, 0C0000017h
0x140029db2  jmp     short loc_140029E30
0x140029db4  mov     rcx, [rdi+48h]
0x140029db8  xor     edx, edx
0x140029dba  call    QuicOperationAlloc
0x140029dbf  mov     r9, rax
0x140029dc2  test    rax, rax
0x140029dc5  jnz     short loc_140029DE3
0x140029dc7  test    cs:Microsoft_QuicEnableBits, 2
0x140029dce  mov     ebx, 0C0000017h
0x140029dd3  jz      short loc_140029E30
0x140029dd5  lea     r8, aStrmProvideRec; "STRM_PROVIDE_RECV_BUFFERS, operation"
0x140029ddc  call    McTemplateU0sx_EtwWriteTransfer
0x140029de1  jmp     short loc_140029E30
0x140029de3  mov     rax, [rax+18h]
0x140029de7  lea     rcx, [rbp+P]
0x140029deb  mov     dword ptr [rax], 10h
0x140029df1  mov     rax, [r9+18h]
0x140029df5  mov     [rax+18h], rsi
0x140029df9  mov     rax, [r9+18h]
0x140029dfd  add     rax, 20h ; ' '
0x140029e01  mov     [rax+8], rax
0x140029e05  mov     [rax], rax
0x140029e08  mov     rdx, [r9+18h]
0x140029e0c  add     rdx, 20h ; ' '
0x140029e10  call    CxPlatListMoveItems
0x140029e15  lea     rcx, [rsi+10h]
0x140029e19  call    CxPlatRefIncrement
0x140029e1e  mov     rcx, rdi
0x140029e21  mov     rdx, r9
0x140029e24  call    QuicConnQueueOper
0x140029e29  jmp     short loc_140029E30
0x140029e2b  mov     ebx, 0C000000Dh
0x140029e30  mov     rcx, [rbp+P]
0x140029e34  lea     rax, [rbp+P]
0x140029e38  cmp     rcx, rax
0x140029e3b  jz      short loc_140029EBA
0x140029e3d  mov     rax, [rcx]
0x140029e40  lea     rsi, [rcx-10h]
0x140029e44  mov     [rbp+P], rax
0x140029e48  lea     rdx, [rbp+P]
0x140029e4c  mov     [rax+8], rdx
0x140029e50  mov     rdi, [rsi]
0x140029e53  mov     rcx, rdi; SListHead
0x140029e56  inc     dword ptr [rdi+1Ch]
0x140029e59  call    cs:__imp_ExQueryDepthSList
0x140029e60  nop     dword ptr [rax+rax+00h]
0x140029e65  cmp     ax, [rdi+10h]
0x140029e69  jb      short loc_140029E7F
0x140029e6b  inc     dword ptr [rdi+20h]
0x140029e6e  mov     rdx, rdi
0x140029e71  mov     rax, [rdi+38h]
0x140029e75  mov     rcx, rsi
0x140029e78  call    _guard_dispatch_icall
0x140029e7d  jmp     short loc_140029E91
0x140029e7f  mov     rdx, rsi; ListEntry
0x140029e82  mov     rcx, rdi; ListHead
0x140029e85  call    cs:__imp_ExpInterlockedPushEntrySList
0x140029e8c  nop     dword ptr [rax+rax+00h]
0x140029e91  mov     rcx, [rbp+P]; P
0x140029e95  lea     rdx, [rbp+P]
0x140029e99  mov     rax, [rcx]
0x140029e9c  mov     [rbp+P], rax
0x140029ea0  mov     [rax+8], rdx
0x140029ea4  mov     edx, 33316351h; Tag
0x140029ea9  call    cs:__imp_ExFreePoolWithTag
0x140029eb0  nop     dword ptr [rax+rax+00h]
0x140029eb5  jmp     loc_140029E30
0x140029eba  test    cs:Microsoft_QuicEnableBits, 8
0x140029ec1  jz      short loc_140029ED2
0x140029ec3  mov     r8d, ebx
0x140029ec6  lea     rdx, QuicApiExitStatus
0x140029ecd  call    McTemplateU0q_EtwWriteTransfer
0x140029ed2  mov     eax, ebx
0x140029ed4  mov     rbx, [rsp+30h+arg_8]
0x140029ed9  add     rsp, 30h
0x140029edd  pop     r15
0x140029edf  pop     r14
0x140029ee1  pop     r13
0x140029ee3  pop     r12
0x140029ee5  pop     rdi
0x140029ee6  pop     rsi
0x140029ee7  pop     rbp
0x140029ee8  retn
```
