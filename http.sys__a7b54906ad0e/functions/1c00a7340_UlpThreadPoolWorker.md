# UlpThreadPoolWorker

- ea: `0x1c00a7340`
- end: `0x1c00a7501`
- name: `UlpThreadPoolWorker`
- size: `449`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1c0002bc0`
- `0x1c001b610`
- `0x1c009bb90`
- `0x1c00a7340`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c0136680`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1c00a737b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00a74f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00a737b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00a74f3`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1c00a73b4`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1c00a74a9`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1c00a73b4`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1c00a74a9`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1c00a739a`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1c00a739a`

## pseudocode

```c
void __fastcall UlpThreadPoolWorker(__int64 **StartContext)
{
  __int64 *v1; // r15
  __int64 v3; // rbx
  __int64 v4; // rdx
  PSLIST_ENTRY v5; // rax
  bool v6; // zf
  _QWORD *v7; // rcx
  _QWORD *v8; // r14
  _QWORD *p_Next; // rax
  __int64 v10; // rbp
  _QWORD *v11; // r8
  char v12; // si
  _QWORD *v13; // rdx
  void (__fastcall *v14)(_QWORD *); // rbx
  _QWORD *v15; // rdi
  PSLIST_ENTRY v16; // rax
  PSLIST_ENTRY v17; // r14
  struct _SLIST_ENTRY *Next; // rcx
  __int64 v19; // rbp
  struct _SLIST_ENTRY *v20; // rdx
  char v21; // si
  struct _SLIST_ENTRY *v22; // r8
  struct _SLIST_ENTRY *v23; // rbx
  _QWORD *v24; // rdi
  __int128 v25; // [rsp+30h] [rbp-58h] BYREF
  __int128 v26; // [rsp+40h] [rbp-48h] BYREF
  PSLIST_ENTRY v27; // [rsp+90h] [rbp+8h] BYREF
  __int64 v28; // [rsp+98h] [rbp+10h]

  v1 = *StartContext;
  v3 = **StartContext;
  v28 = v3;
  KeWaitForSingleObject(StartContext + 4, Executive, 0, 0, 0);
  if ( !*((_BYTE *)StartContext + 56) )
  {
    IoSetThreadHardErrorMode(0);
    do
    {
      v5 = ExpInterlockedFlushSList((PSLIST_HEADER)v1 + 1);
      v6 = *((_BYTE *)StartContext + 56) == 0;
      v27 = v5;
      if ( v6 )
      {
        if ( v5 || *(_BYTE *)(v3 + 32) && (UlpStealThreadPoolWork(v3, *((unsigned int *)v1 + 2), &v27), v27) )
        {
LABEL_5:
          v7 = 0;
          v8 = 0;
          _InterlockedExchange((volatile __int32 *)v1 + 3, 0);
          p_Next = &v27->Next;
          v25 = 0;
          if ( v27 )
          {
            do
            {
              v7 = (_QWORD *)*p_Next;
              *p_Next = v8;
              v8 = p_Next;
              p_Next = v7;
            }
            while ( v7 );
          }
          if ( v8 )
          {
            do
            {
              v10 = v8[4];
              v11 = v8 + 2;
              v12 = *((_BYTE *)v8 + 24);
              v13 = v8 + 4;
              v14 = (void (__fastcall *)(_QWORD *))v8[2];
              v15 = v8;
              v8 = (_QWORD *)*v8;
              *v13 = v7;
              *v11 = v7;
              *v15 = v7;
              UxPodAttachThread(v10, (__int64)&v25);
              v14(v15);
              UxPodDetachThread((__int64)&v25);
              if ( v12 )
                UxPodDereferenceSilo(v10, 1230466133);
              ++*((_DWORD *)v1 + 22);
              v7 = 0;
            }
            while ( v8 );
            v3 = v28;
          }
          continue;
        }
        KeWaitForSingleObject(v1 + 4, Executive, 0, 0, 0);
      }
      else if ( v5 )
      {
        goto LABEL_5;
      }
    }
    while ( !*((_BYTE *)StartContext + 56) );
  }
  if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x800000) != 0 )
    WPP_SF_ddL(17, v4, *((unsigned int *)StartContext + 2), *((unsigned int *)v1 + 2), *(_DWORD *)v3);
  v16 = ExpInterlockedFlushSList((PSLIST_HEADER)v1 + 1);
  if ( v16 )
  {
    v17 = 0;
    v26 = 0;
    do
    {
      Next = v16->Next;
      v16->Next = v17;
      v17 = v16;
      v16 = Next;
    }
    while ( Next );
    for ( ; v17; ++*((_DWORD *)v1 + 22) )
    {
      v19 = (__int64)v17[2].Next;
      v20 = v17 + 2;
      v21 = *((_BYTE *)&v17[1].Next + 8);
      v22 = v17 + 1;
      v23 = v17[1].Next;
      v24 = &v17->Next;
      v17 = v17->Next;
      v20->Next = 0;
      v22->Next = 0;
      *v24 = 0;
      UxPodAttachThread(v19, (__int64)&v26);
      ((void (__fastcall *)(_QWORD *))v23)(v24);
      UxPodDetachThread((__int64)&v26);
      if ( v21 )
        UxPodDereferenceSilo(v19, 1230466133);
    }
  }
}

```

## disassembly

```asm
0x1c00a7340  push    rbx
0x1c00a7342  push    rbp
0x1c00a7343  push    rsi
0x1c00a7344  push    rdi
0x1c00a7345  push    r14
0x1c00a7347  push    r15
0x1c00a7349  sub     rsp, 58h
0x1c00a734d  mov     r15, [rcx]
0x1c00a7350  xor     r9d, r9d; Alertable
0x1c00a7353  mov     [rsp+88h+arg_10], r12
0x1c00a735b  xor     r8d, r8d; WaitMode
0x1c00a735e  mov     r12, rcx
0x1c00a7361  mov     [rsp+88h+Timeout], 0; Timeout
0x1c00a736a  add     rcx, 20h ; ' '; Object
0x1c00a736e  xor     edx, edx; WaitReason
0x1c00a7370  mov     rbx, [r15]
0x1c00a7373  mov     [rsp+88h+arg_8], rbx
0x1c00a737b  call    cs:__imp_KeWaitForSingleObject
0x1c00a7382  nop     dword ptr [rax+rax+00h]
0x1c00a7387  cmp     byte ptr [r12+38h], 0
0x1c00a738d  jnz     loc_1C00A7495
0x1c00a7393  xor     ecx, ecx; EnableHardErrors
0x1c00a7395  mov     [rsp+88h+var_38], r13
0x1c00a739a  call    cs:__imp_IoSetThreadHardErrorMode
0x1c00a73a1  nop     dword ptr [rax+rax+00h]
0x1c00a73a6  nop     word ptr [rax+rax+00000000h]
0x1c00a73b0  lea     rcx, [r15+10h]; ListHead
0x1c00a73b4  call    cs:__imp_ExpInterlockedFlushSList
0x1c00a73bb  nop     dword ptr [rax+rax+00h]
0x1c00a73c0  cmp     byte ptr [r12+38h], 0
0x1c00a73c6  mov     [rsp+88h+arg_0], rax
0x1c00a73ce  jnz     loc_1C00E65E6
0x1c00a73d4  test    rax, rax
0x1c00a73d7  jz      loc_1C00A74D4
0x1c00a73dd  xor     ecx, ecx
0x1c00a73df  xorps   xmm0, xmm0
0x1c00a73e2  mov     eax, ecx
0x1c00a73e4  mov     r14d, ecx
0x1c00a73e7  xchg    eax, [r15+0Ch]
0x1c00a73eb  mov     rax, [rsp+88h+arg_0]
0x1c00a73f3  movups  [rsp+88h+var_58], xmm0
0x1c00a73f8  test    rax, rax
0x1c00a73fb  jz      short loc_1C00A7411
0x1c00a73fd  nop     dword ptr [rax]
0x1c00a7400  mov     rcx, [rax]
0x1c00a7403  mov     [rax], r14
0x1c00a7406  mov     r14, rax
0x1c00a7409  mov     rax, rcx
0x1c00a740c  test    rcx, rcx
0x1c00a740f  jnz     short loc_1C00A7400
0x1c00a7411  test    r14, r14
0x1c00a7414  jz      short loc_1C00A7484
0x1c00a7416  mov     rbp, [r14+20h]
0x1c00a741a  lea     r8, [r14+10h]
0x1c00a741e  movzx   esi, byte ptr [r14+18h]
0x1c00a7423  lea     rdx, [r14+20h]
0x1c00a7427  mov     rbx, [r8]
0x1c00a742a  mov     rdi, r14
0x1c00a742d  mov     r14, [r14]
0x1c00a7430  mov     [rdx], rcx
0x1c00a7433  lea     rdx, [rsp+88h+var_58]
0x1c00a7438  mov     [r8], rcx
0x1c00a743b  mov     [rdi], rcx
0x1c00a743e  mov     rcx, rbp
0x1c00a7441  call    UxPodAttachThread
0x1c00a7446  mov     rcx, rdi
0x1c00a7449  mov     rax, rbx
0x1c00a744c  call    cs:__guard_dispatch_icall_fptr
0x1c00a7452  lea     rcx, [rsp+88h+var_58]
0x1c00a7457  call    UxPodDetachThread
0x1c00a745c  test    sil, sil
0x1c00a745f  jz      short loc_1C00A746E
0x1c00a7461  mov     edx, 49576C55h
0x1c00a7466  mov     rcx, rbp
0x1c00a7469  call    UxPodDereferenceSilo
0x1c00a746e  inc     dword ptr [r15+58h]
0x1c00a7472  mov     ecx, 0
0x1c00a7477  test    r14, r14
0x1c00a747a  jnz     short loc_1C00A7416
0x1c00a747c  mov     rbx, [rsp+88h+arg_8]
0x1c00a7484  cmp     byte ptr [r12+38h], 0
0x1c00a748a  jz      loc_1C00A73B0
0x1c00a7490  mov     r13, [rsp+88h+var_38]
0x1c00a7495  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 800000h
0x1c00a749f  jnz     loc_1C00E65F4
0x1c00a74a5  lea     rcx, [r15+10h]; ListHead
0x1c00a74a9  call    cs:__imp_ExpInterlockedFlushSList
0x1c00a74b0  nop     dword ptr [rax+rax+00h]
0x1c00a74b5  mov     r12, [rsp+88h+arg_10]
0x1c00a74bd  test    rax, rax
0x1c00a74c0  jnz     loc_1C00E6613
0x1c00a74c6  add     rsp, 58h
0x1c00a74ca  pop     r15
0x1c00a74cc  pop     r14
0x1c00a74ce  pop     rdi
0x1c00a74cf  pop     rsi
0x1c00a74d0  pop     rbp
0x1c00a74d1  pop     rbx
0x1c00a74d2  retn
0x1c00a74d4  cmp     byte ptr [rbx+20h], 0
0x1c00a74d8  jnz     loc_1C00E65BE
0x1c00a74de  lea     rcx, [r15+20h]; Object
0x1c00a74e2  mov     [rsp+88h+Timeout], 0; Timeout
0x1c00a74eb  xor     r9d, r9d; Alertable
0x1c00a74ee  xor     r8d, r8d; WaitMode
0x1c00a74f1  xor     edx, edx; WaitReason
0x1c00a74f3  call    cs:__imp_KeWaitForSingleObject
0x1c00a74fa  nop     dword ptr [rax+rax+00h]
0x1c00a74ff  jmp     short loc_1C00A7484
0x1c00e65be  mov     edx, [r15+8]
0x1c00e65c2  lea     r8, [rsp+88h+arg_0]
0x1c00e65ca  mov     rcx, rbx
0x1c00e65cd  call    UlpStealThreadPoolWork
0x1c00e65d2  cmp     [rsp+88h+arg_0], 0
0x1c00e65db  jnz     loc_1C00A73DD
0x1c00e65e1  jmp     loc_1C00A74DE
0x1c00e65e6  test    rax, rax
0x1c00e65e9  jz      loc_1C00A7484
0x1c00e65ef  jmp     loc_1C00A73DD
0x1c00e65f4  mov     eax, [rbx]
0x1c00e65f6  mov     ecx, 11h
0x1c00e65fb  mov     r9d, [r15+8]
0x1c00e65ff  mov     r8d, [r12+8]
0x1c00e6604  mov     dword ptr [rsp+88h+Timeout], eax
0x1c00e6608  call    WPP_SF_ddL
0x1c00e660d  nop
0x1c00e660e  jmp     loc_1C00A74A5
0x1c00e6613  xorps   xmm0, xmm0
0x1c00e6616  xor     r14d, r14d
0x1c00e6619  movups  [rsp+88h+var_48], xmm0
0x1c00e661e  mov     rcx, [rax]
0x1c00e6621  mov     [rax], r14
0x1c00e6624  mov     r14, rax
0x1c00e6627  mov     rax, rcx
0x1c00e662a  test    rcx, rcx
0x1c00e662d  jnz     short loc_1C00E661E
0x1c00e662f  test    r14, r14
0x1c00e6632  jz      loc_1C00A74C6
0x1c00e6638  mov     rbp, [r14+20h]
0x1c00e663c  lea     rdx, [r14+20h]
0x1c00e6640  movzx   esi, byte ptr [r14+18h]
0x1c00e6645  lea     r8, [r14+10h]
0x1c00e6649  mov     rbx, [r8]
0x1c00e664c  mov     rdi, r14
0x1c00e664f  mov     r14, [r14]
0x1c00e6652  mov     rcx, rbp
0x1c00e6655  mov     qword ptr [rdx], 0
0x1c00e665c  lea     rdx, [rsp+88h+var_48]
0x1c00e6661  mov     qword ptr [r8], 0
0x1c00e6668  mov     qword ptr [rdi], 0
0x1c00e666f  call    UxPodAttachThread
0x1c00e6674  mov     rcx, rdi
0x1c00e6677  mov     rax, rbx
0x1c00e667a  call    cs:__guard_dispatch_icall_fptr
0x1c00e6680  lea     rcx, [rsp+88h+var_48]
0x1c00e6685  call    UxPodDetachThread
0x1c00e668a  test    sil, sil
0x1c00e668d  jz      short loc_1C00E669C
0x1c00e668f  mov     edx, 49576C55h
0x1c00e6694  mov     rcx, rbp
0x1c00e6697  call    UxPodDereferenceSilo
0x1c00e669c  inc     dword ptr [r15+58h]
0x1c00e66a0  test    r14, r14
0x1c00e66a3  jnz     short loc_1C00E6638
0x1c00e66a5  jmp     loc_1C00A74C6
```
