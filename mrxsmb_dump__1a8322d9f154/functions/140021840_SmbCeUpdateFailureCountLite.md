# SmbCeUpdateFailureCountLite

- ea: `0x140021840`
- end: `0x1400219e3`
- name: `SmbCeUpdateFailureCountLite`
- size: `419`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140045c60`
- `0x140046af0`

## callees

- `0x140013540`
- `0x140014400`
- `0x140021840`
- `0x140026950`
- `0x1400383d0`
- `0x14004c324`

## import_xrefs

- `rdbss!RxDiagnosticTrace` at `0x14005ed2e`
- `rdbss!RxDiagnosticTrace` at `0x14005ed2e`
- `rdbss!RxDispatchToWorkerThread` at `0x14005ed5f`
- `rdbss!RxDispatchToWorkerThread` at `0x14005ed5f`

## string_xrefs

- `0x14005ed09`: `Update:Index %d TargetCount %d CurrentCount %d FailureCount %d`

## pseudocode

```c
char __fastcall SmbCeUpdateFailureCountLite(_QWORD *BugCheckParameter2, __int64 a2, char a3)
{
  _UNKNOWN **v3; // rax
  __int64 v4; // r9
  char v8; // r12
  unsigned int v9; // ebx
  __int64 v10; // rdi
  unsigned __int8 v11; // dl
  ADDRESS_FAMILY v12; // r9
  char v13; // cl
  _DWORD *v14; // r15
  _DWORD *v15; // r14
  __int16 v16; // dx
  int v17; // eax
  __int64 v18; // r11
  int v19; // r8d
  char v20; // r10
  __int128 v22; // [rsp+50h] [rbp-38h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h] BYREF
  struct _RDBSS_DEVICE_OBJECT *pMRxDeviceObject; // [rsp+90h] [rbp+8h]

  v3 = &retaddr;
  v4 = BugCheckParameter2[72];
  if ( !*(_DWORD *)(v4 + 8) )
    return (char)v3;
  v8 = 0;
  v9 = 0;
  pMRxDeviceObject = (struct _RDBSS_DEVICE_OBJECT *)BugCheckParameter2[3];
  do
  {
    v10 = v4 + 312LL * v9;
    v11 = *(_BYTE *)(v10 + 36);
    LOBYTE(v3) = v11 >> 4;
    if ( (((v11 >> 4) ^ (*(_BYTE *)a2 >> 1)) & 1) != 0 )
      goto LABEL_9;
    LOWORD(v3) = *(_WORD *)(v10 + 56);
    if ( (_WORD)v3 != *(_WORD *)(a2 + 8) )
      goto LABEL_9;
    v12 = *(_WORD *)(v10 + 200);
    if ( v12 != *(_WORD *)(a2 + 136) )
      goto LABEL_9;
    v13 = 0;
    if ( (_WORD)v3 == 23 )
    {
      v3 = *(_UNKNOWN ***)(a2 + 24);
      if ( *(_UNKNOWN ***)(v10 + 72) == v3 )
      {
        v3 = *(_UNKNOWN ***)(a2 + 16);
        if ( *(_UNKNOWN ***)(v10 + 64) == v3 )
        {
          v3 = *(_UNKNOWN ***)(a2 + 152);
          if ( *(_UNKNOWN ***)(v10 + 216) == v3 )
          {
            v3 = *(_UNKNOWN ***)(a2 + 144);
            if ( *(_UNKNOWN ***)(v10 + 208) == v3 )
              goto LABEL_14;
          }
        }
      }
    }
    else
    {
      LODWORD(v3) = *(_DWORD *)(a2 + 12);
      if ( *(_DWORD *)(v10 + 60) == (_DWORD)v3 )
      {
        LODWORD(v3) = *(_DWORD *)(a2 + 140);
        if ( *(_DWORD *)(v10 + 204) == (_DWORD)v3 )
LABEL_14:
          v13 = 1;
      }
    }
    if ( v13 )
    {
      v14 = (_DWORD *)(v10 + 20);
      if ( a3 )
      {
        if ( *v14 )
          --*v14;
        v15 = (_DWORD *)(v10 + 28);
      }
      else
      {
        ++*(_DWORD *)(v10 + 28);
        v15 = (_DWORD *)(v10 + 28);
        if ( *(_DWORD *)(v10 + 28) > *(_DWORD *)(v10 + 32) )
        {
          *v14 = 0;
          *(_BYTE *)(v10 + 36) = v11 | 2;
          v8 = 1;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v22 = (unsigned __int64)(v10 + 200);
        v16 = SOCKADDR_SIZE(v12);
        v17 = *(_DWORD *)(v10 + 24);
        WORD4(v22) = v16;
        WPP_SF_qd_SOCKADDR_dddd(
          *(_QWORD *)(v18 + 24),
          (*(unsigned __int8 *)(v10 + 36) >> 4) & 1,
          v19,
          (_DWORD)BugCheckParameter2,
          v9,
          (__int64)&v22,
          (*(_BYTE *)(v10 + 36) & 0x10) != 0,
          *v14,
          v17,
          v20);
      }
      LOBYTE(v3) = RxDiagnosticTrace(
                     BugCheckParameter2[2],
                     1,
                     "Update:Index %d TargetCount %d CurrentCount %d FailureCount %d",
                     v9,
                     *v14,
                     *(_DWORD *)(v10 + 24),
                     *v15);
    }
LABEL_9:
    v4 = BugCheckParameter2[72];
    ++v9;
  }
  while ( v9 < *(_DWORD *)(v4 + 8) );
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_94e1a31e0cd6309a61e483fe0815e01e_Traceguids,
        BugCheckParameter2);
    }
    SmbCeReferenceServerEntry((ULONG_PTR)BugCheckParameter2);
    LODWORD(v3) = RxDispatchToWorkerThread(
                    pMRxDeviceObject,
                    NormalWorkQueue,
                    (PRX_WORKERTHREAD_ROUTINE)SmbCeComputeConnectionInfo,
                    BugCheckParameter2);
    if ( (_DWORD)v3 )
      LOBYTE(v3) = SmbCeDereferenceServerEntryEx((ULONG_PTR)BugCheckParameter2);
  }
  return (char)v3;
}

```

## disassembly

```asm
0x140021840  mov     rax, rsp
0x140021843  push    rbp
0x140021844  push    rsi
0x140021845  push    r13
0x140021847  sub     rsp, 70h
0x14002184b  mov     r9, [rcx+240h]
0x140021852  movzx   r13d, r8b
0x140021856  mov     rsi, rdx
0x140021859  mov     rbp, rcx
0x14002185c  cmp     dword ptr [r9+8], 0
0x140021861  jbe     loc_140021921
0x140021867  mov     [rax+10h], rbx
0x14002186b  mov     [rax+18h], rdi
0x14002186f  mov     [rax+20h], r12
0x140021873  xor     r12b, r12b
0x140021876  mov     [rax-20h], r14
0x14002187a  xor     ebx, ebx
0x14002187c  mov     r14, [rcx+18h]
0x140021880  mov     [rsp+88h+pMRxDeviceObject], r14
0x140021888  mov     [rax-28h], r15
0x14002188c  nop     dword ptr [rax+00h]
0x140021890  movzx   ecx, byte ptr [rsi]
0x140021893  mov     eax, ebx
0x140021895  imul    rdi, rax, 138h
0x14002189c  shr     cl, 1
0x14002189e  add     rdi, r9
0x1400218a1  movzx   edx, byte ptr [rdi+24h]
0x1400218a5  movzx   eax, dl
0x1400218a8  shr     al, 4
0x1400218ab  xor     cl, al
0x1400218ad  test    cl, 1
0x1400218b0  jnz     short loc_1400218EB
0x1400218b2  movzx   eax, word ptr [rdi+38h]
0x1400218b6  cmp     ax, [rsi+8]
0x1400218ba  jnz     short loc_1400218EB
0x1400218bc  lea     r8, [rdi+0C8h]
0x1400218c3  movzx   r9d, word ptr [r8]
0x1400218c7  cmp     r9w, [rsi+88h]
0x1400218cf  jnz     short loc_1400218EB
0x1400218d1  xor     cl, cl
0x1400218d3  cmp     ax, 17h
0x1400218d7  jnz     short loc_14002192B
0x1400218d9  mov     rax, [rsi+18h]
0x1400218dd  cmp     [rdi+48h], rax
0x1400218e1  jz      short loc_140021945
0x1400218e3  test    cl, cl
0x1400218e5  jnz     loc_140021975
0x1400218eb  mov     r9, [rbp+240h]
0x1400218f2  inc     ebx
0x1400218f4  cmp     ebx, [r9+8]
0x1400218f8  jb      short loc_140021890
0x1400218fa  mov     r15, [rsp+88h+var_28]
0x1400218ff  test    r12b, r12b
0x140021902  mov     r12, [rsp+88h+arg_18]
0x14002190a  mov     r14, [rsp+88h+var_20]
0x14002190f  mov     rdi, [rsp+88h+arg_10]
0x140021917  mov     rbx, [rsp+88h+arg_8]
0x14002191f  jnz     short loc_140021997
0x140021921  add     rsp, 70h
0x140021925  pop     r13
0x140021927  pop     rsi
0x140021928  pop     rbp
0x140021929  retn
0x14002192b  mov     eax, [rsi+0Ch]
0x14002192e  cmp     [rdi+3Ch], eax
0x140021931  jnz     short loc_1400218E3
0x140021933  mov     eax, [rsi+8Ch]
0x140021939  cmp     [rdi+0CCh], eax
0x14002193f  jnz     short loc_1400218E3
0x140021941  mov     cl, 1
0x140021943  jmp     short loc_1400218E3
0x140021945  mov     rax, [rsi+10h]
0x140021949  cmp     [rdi+40h], rax
0x14002194d  jnz     short loc_1400218E3
0x14002194f  mov     rax, [rsi+98h]
0x140021956  cmp     [rdi+0D8h], rax
0x14002195d  jnz     short loc_1400218E3
0x14002195f  mov     rax, [rsi+90h]
0x140021966  cmp     [rdi+0D0h], rax
0x14002196d  jnz     loc_1400218E3
0x140021973  jmp     short loc_140021941
0x140021975  lea     r15, [rdi+14h]
0x140021979  test    r13b, r13b
0x14002197c  jz      loc_14005EC5E
0x140021982  mov     eax, [r15]
0x140021985  test    eax, eax
0x140021987  jz      loc_14005EC54
0x14002198d  dec     eax
0x14002198f  mov     [r15], eax
0x140021992  jmp     loc_14005EC54
0x140021997  mov     rcx, cs:WPP_GLOBAL_Control
0x14002199e  lea     rax, WPP_GLOBAL_Control
0x1400219a5  cmp     rcx, rax
0x1400219a8  jz      loc_14005ED40
0x1400219ae  test    dword ptr [rcx+2Ch], 100h
0x1400219b5  jz      loc_14005ED40
0x1400219bb  cmp     byte ptr [rcx+29h], 2
0x1400219bf  jb      loc_14005ED40
0x1400219c5  mov     rcx, [rcx+18h]
0x1400219c9  lea     r8, WPP_94e1a31e0cd6309a61e483fe0815e01e_Traceguids
0x1400219d0  mov     edx, 0Ch
0x1400219d5  mov     r9, rbp
0x1400219d8  call    WPP_SF_q
0x1400219dd  nop
0x1400219de  jmp     loc_14005ED40
0x14005ec54  mov     r10d, [rdi+1Ch]
0x14005ec58  lea     r14, [rdi+1Ch]
0x14005ec5c  jmp     short loc_14005EC7E
0x14005ec5e  inc     dword ptr [rdi+1Ch]
0x14005ec61  lea     r14, [rdi+1Ch]
0x14005ec65  mov     r10d, [r14]
0x14005ec68  cmp     r10d, [rdi+20h]
0x14005ec6c  jbe     short loc_14005EC7E
0x14005ec6e  or      dl, 2
0x14005ec71  mov     dword ptr [r15], 0
0x14005ec78  mov     [rdi+24h], dl
0x14005ec7b  mov     r12b, 1
0x14005ec7e  mov     r11, cs:WPP_GLOBAL_Control
0x14005ec85  lea     rax, WPP_GLOBAL_Control
0x14005ec8c  cmp     r11, rax
0x14005ec8f  jz      short loc_14005ED06
0x14005ec91  test    dword ptr [r11+2Ch], 100h
0x14005ec99  jz      short loc_14005ED06
0x14005ec9b  cmp     byte ptr [r11+29h], 2
0x14005eca0  jb      short loc_14005ED06
0x14005eca2  xorps   xmm0, xmm0
0x14005eca5  movzx   ecx, r9w; af
0x14005eca9  movups  [rsp+88h+var_38], xmm0
0x14005ecae  mov     qword ptr [rsp+88h+var_38], r8
0x14005ecb3  call    SOCKADDR_SIZE
0x14005ecb8  movzx   edx, al
0x14005ecbb  mov     r9, rbp
0x14005ecbe  mov     eax, [rdi+18h]
0x14005ecc1  mov     word ptr [rsp+88h+var_38+8], dx
0x14005ecc6  movzx   edx, byte ptr [rdi+24h]
0x14005ecca  movaps  xmm0, [rsp+88h+var_38]
0x14005eccf  mov     [rsp+88h+var_40], r10d
0x14005ecd4  mov     [rsp+88h+var_48], eax
0x14005ecd8  mov     eax, [r15]
0x14005ecdb  mov     [rsp+88h+var_50], eax
0x14005ecdf  lea     rax, [rsp+88h+var_38]
0x14005ece4  shr     edx, 4
0x14005ece7  and     edx, 1
0x14005ecea  movdqa  [rsp+88h+var_38], xmm0
0x14005ecf0  mov     rcx, [r11+18h]
0x14005ecf4  mov     [rsp+88h+var_58], edx
0x14005ecf8  mov     [rsp+88h+var_60], rax
0x14005ecfd  mov     [rsp+88h+var_68], ebx
0x14005ed01  call    WPP_SF_qd_SOCKADDR_dddd
0x14005ed06  mov     eax, [r14]
0x14005ed09  lea     r8, aUpdateIndexDTa; "Update:Index %d TargetCount %d CurrentC"...
0x14005ed10  mov     rcx, [rbp+10h]
0x14005ed14  mov     r9d, ebx
0x14005ed17  mov     [rsp+88h+var_58], eax
0x14005ed1b  mov     edx, 1
0x14005ed20  mov     eax, [rdi+18h]
0x14005ed23  mov     dword ptr [rsp+88h+var_60], eax
0x14005ed27  mov     eax, [r15]
0x14005ed2a  mov     [rsp+88h+var_68], eax
0x14005ed2e  call    cs:__imp_RxDiagnosticTrace
0x14005ed35  nop     dword ptr [rax+rax+00h]
0x14005ed3a  nop
0x14005ed3b  jmp     loc_1400218EB
0x14005ed40  mov     rcx, rbp; BugCheckParameter2
0x14005ed43  call    SmbCeReferenceServerEntry
0x14005ed48  mov     rcx, [rsp+88h+pMRxDeviceObject]; pMRxDeviceObject
0x14005ed50  lea     r8, SmbCeComputeConnectionInfo; Routine
0x14005ed57  mov     r9, rbp; pContext
0x14005ed5a  mov     edx, 3; WorkQueueType
0x14005ed5f  call    cs:__imp_RxDispatchToWorkerThread
0x14005ed66  nop     dword ptr [rax+rax+00h]
0x14005ed6b  test    eax, eax
0x14005ed6d  jz      loc_140021921
0x14005ed73  xor     edx, edx
0x14005ed75  mov     rcx, rbp; BugCheckParameter2
0x14005ed78  call    SmbCeDereferenceServerEntryEx
0x14005ed7d  nop
0x14005ed7e  jmp     loc_140021921
```
