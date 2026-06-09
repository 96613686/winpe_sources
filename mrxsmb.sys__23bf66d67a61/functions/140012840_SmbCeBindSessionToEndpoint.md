# SmbCeBindSessionToEndpoint

- ea: `0x140012840`
- end: `0x140012cfc`
- name: `SmbCeBindSessionToEndpoint`
- size: `1212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14000a260`

## callees

- `0x140001470`
- `0x140004360`
- `0x1400045c0`
- `0x140012840`
- `0x140013470`
- `0x140013540`
- `0x1400135e0`
- `0x140013750`
- `0x140014400`
- `0x1400267cc`
- `0x140026d60`
- `0x14002d320`
- `0x140048954`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400129d7`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400129d7`
- `ntoskrnl!KeInitializeSpinLock` at `0x140012aa4`
- `ntoskrnl!KeInitializeSpinLock` at `0x140012aa4`
- `ntoskrnl!ExAllocatePool2` at `0x1400129ad`
- `ntoskrnl!ExAllocatePool2` at `0x1400129ad`
- `ntoskrnl!KeBugCheckEx` at `0x140012be7`
- `ntoskrnl!KeBugCheckEx` at `0x140012be7`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012ba7`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012ba7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001287f`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001287f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012892`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012892`

## pseudocode

```c
__int64 __fastcall SmbCeBindSessionToEndpoint(__int64 a1, struct _LIST_ENTRY **a2)
{
  ULONG_PTR v2; // r15
  __int64 v4; // r14
  volatile LONG *v5; // r12
  ULONG_PTR v6; // rdi
  __int64 v7; // rbx
  __int64 FirstVcEndpoint; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  int *v11; // rax
  _QWORD *v12; // rdx
  unsigned int v13; // ebp
  int **v14; // r8
  int *v15; // rdi
  __int64 v16; // rdx
  struct _LIST_ENTRY *v17; // rdi
  struct _LIST_ENTRY *Pool2; // rax
  struct _LIST_ENTRY *v19; // r12
  struct _LIST_ENTRY *v20; // r14
  unsigned int v21; // eax
  char *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  struct _LIST_ENTRY *v26; // rdx
  struct _LIST_ENTRY *v27; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  ULONG_PTR Flink; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // [rsp+40h] [rbp-58h]
  PEX_SPIN_LOCK SpinLock; // [rsp+48h] [rbp-50h]
  char v36; // [rsp+A0h] [rbp+8h]
  KIRQL v38; // [rsp+B0h] [rbp+18h]

  v2 = *(_QWORD *)(a1 + 384);
  v36 = 0;
  v4 = *(_QWORD *)(v2 + 24);
  v34 = v4;
  v5 = (volatile LONG *)(v4 + 1920);
  SpinLock = (PEX_SPIN_LOCK)(v4 + 1920);
  v38 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920));
  v6 = v2 + 616;
  *(_DWORD *)(v4 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v7 = *(_QWORD *)(v2 + 616);
  if ( v7 != v2 + 616 )
  {
    FirstVcEndpoint = v7 - 536;
    if ( FirstVcEndpoint )
    {
      while ( 1 )
      {
        if ( !*(_DWORD *)(FirstVcEndpoint + 12)
          && (*(_DWORD *)(FirstVcEndpoint + 4) & 2) != 0
          && !(unsigned __int8)SmbCeIsObjectBoundToEndpointLite(a1, FirstVcEndpoint) )
        {
          v36 = VctReferenceEndpointSafe(FirstVcEndpoint, v30);
          if ( v36 )
            break;
        }
        v29 = *(_QWORD *)(FirstVcEndpoint + 536);
        FirstVcEndpoint = 0;
        if ( v29 != v6 )
          FirstVcEndpoint = v29 - 536;
        if ( !FirstVcEndpoint )
          goto LABEL_3;
      }
LABEL_5:
      v9 = *(unsigned __int16 *)(v2 + 2);
      if ( (_WORD)v9 )
      {
        v10 = v2 + v9 + 8;
        if ( !v10 )
          goto LABEL_41;
      }
      else
      {
        v10 = 8;
      }
      v11 = *(int **)v10;
      if ( *(_QWORD *)v10 )
      {
        v12 = *(_QWORD **)(v10 + 8);
        if ( v12 )
        {
          if ( *((_QWORD *)v11 + 1) == v10 && *v12 == v10 )
          {
            while ( 1 )
            {
              v13 = -1073741300;
              if ( v11 == (int *)v10 )
                break;
              if ( !v11 )
                goto LABEL_41;
              if ( !*(_QWORD *)v11 )
                goto LABEL_41;
              v14 = (int **)*((_QWORD *)v11 + 1);
              if ( !v14 || *(int **)(*(_QWORD *)v11 + 8LL) != v11 || *v14 != v11 )
                goto LABEL_41;
              v15 = v11 - 100;
              if ( *(v11 - 98) < 0 )
                KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v11 - 100), *(v11 - 98), 0);
              if ( *(_WORD *)v15 != 0xE2FF )
              {
                if ( v11 != (int *)400 )
                {
                  SmbCeUpperDisconnectBindingObjectLite(v11 - 100, 3221225996LL);
                  SmbCeDereferenceBindingObject((ULONG_PTR)v15);
                }
                break;
              }
              v11 = *(int **)v11;
            }
            v16 = 0;
            v17 = 0;
            if ( DWORD2(xmmword_140070ED0) )
              v16 = DWORD2(xmmword_140070ED0);
            Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(64, v16 + 16, 1834181955);
            if ( !Pool2 )
            {
              v13 = -1073741670;
              goto LABEL_37;
            }
            v17 = Pool2 + 1;
            ExInterlockedInsertTailList(&ListHead, Pool2, &SmbMmSpinLock);
            HIDWORD(v17->Flink) = 0;
            v17[1].Blink = (struct _LIST_ENTRY *)v4;
            v19 = v17 + 25;
            LODWORD(v17->Flink) = 4252166;
            v20 = v17 + 26;
            HIDWORD(v17->Blink) = 1;
            LODWORD(v17->Blink) = 1;
            v17[25].Blink = v17 + 25;
            v17[25].Flink = v17 + 25;
            v17[26].Blink = v17 + 26;
            v17[26].Flink = v17 + 26;
            v21 = WORD1(v17->Flink);
            v17[30].Blink = (struct _LIST_ENTRY *)-1LL;
            v17[30].Flink = (struct _LIST_ENTRY *)-1LL;
            v17[29].Blink = (struct _LIST_ENTRY *)-1LL;
            v17[29].Flink = (struct _LIST_ENTRY *)-1LL;
            v17[28].Blink = 0;
            if ( (_WORD)v21 )
            {
              v22 = (char *)v17 + v21;
              if ( v22 )
              {
                *((_DWORD *)v22 + 52) = -1073741300;
                *((_DWORD *)v22 + 53) = 0;
                *((_QWORD *)v22 + 2) = v22 + 8;
                *((_QWORD *)v22 + 1) = v22 + 8;
                *((_QWORD *)v22 + 32) = v22 + 248;
                *((_QWORD *)v22 + 31) = v22 + 248;
                *((_QWORD *)v22 + 28) = v22 + 216;
                *((_QWORD *)v22 + 27) = v22 + 216;
                *((_QWORD *)v22 + 30) = v22 + 232;
                *((_QWORD *)v22 + 29) = v22 + 232;
                KeInitializeSpinLock((PKSPIN_LOCK)v22 + 16);
              }
            }
            v17[4].Flink = (struct _LIST_ENTRY *)&off_140061178;
            SmbCeReferenceServerEntry(v2);
            v17[27].Flink = (struct _LIST_ENTRY *)v2;
            _InterlockedExchange((volatile __int32 *)&v17->Blink + 1, 3);
            if ( *(_DWORD *)(FirstVcEndpoint + 12) )
              goto LABEL_33;
            v24 = *(unsigned __int16 *)(a1 + 2);
            if ( (_WORD)v24 )
              v25 = a1 + v24;
            else
              v25 = 0;
            v17[24].Flink = (struct _LIST_ENTRY *)a1;
            v26 = *(struct _LIST_ENTRY **)(v25 + 16);
            if ( v26->Flink == (struct _LIST_ENTRY *)(v25 + 8) )
            {
              v19->Flink = (struct _LIST_ENTRY *)(v25 + 8);
              v17[25].Blink = v26;
              v26->Flink = v19;
              *(_QWORD *)(v25 + 16) = v19;
              ++*(_DWORD *)(v25 + 24);
              v17[24].Blink = (struct _LIST_ENTRY *)FirstVcEndpoint;
              VctReferenceEndpoint(FirstVcEndpoint);
              v27 = *(struct _LIST_ENTRY **)(FirstVcEndpoint + 528);
              if ( v27->Flink == (struct _LIST_ENTRY *)(FirstVcEndpoint + 520) )
              {
                v20->Flink = (struct _LIST_ENTRY *)(FirstVcEndpoint + 520);
                v13 = 0;
                v17[26].Blink = v27;
                v27->Flink = v20;
                *(_QWORD *)(FirstVcEndpoint + 528) = v20;
LABEL_33:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqqL(
                    WPP_GLOBAL_Control->AttachedDevice,
                    11,
                    WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids,
                    a1,
                    FirstVcEndpoint,
                    v17,
                    v13);
                }
                if ( !v13 )
                {
                  SmbCeReferenceBindingObject(v17);
                  v4 = v34;
                  v5 = SpinLock;
                  goto LABEL_37;
                }
                Flink = (ULONG_PTR)v17[27].Flink;
                if ( Flink )
                {
                  SmbCeDereferenceServerEntryEx(Flink, 0, v23);
                  v17[27].Flink = 0;
                }
                SmbMmFreeObjectPool(v17);
                v4 = v34;
                v5 = SpinLock;
                goto LABEL_67;
              }
            }
          }
        }
      }
LABEL_41:
      __fastfail(3u);
    }
  }
LABEL_3:
  FirstVcEndpoint = SmbCeGetFirstVcEndpoint(v2);
  while ( FirstVcEndpoint )
  {
    if ( !*(_DWORD *)(FirstVcEndpoint + 12) && !(unsigned __int8)SmbCeIsObjectBoundToEndpointLite(a1, FirstVcEndpoint) )
    {
      v36 = VctReferenceEndpointSafe(FirstVcEndpoint, v32);
      if ( v36 )
        goto LABEL_5;
    }
    v33 = *(_QWORD *)(FirstVcEndpoint + 536);
    FirstVcEndpoint = 0;
    if ( v33 != v6 )
      FirstVcEndpoint = v33 - 536;
  }
  v13 = -1073741300;
LABEL_67:
  v17 = 0;
LABEL_37:
  if ( v36 )
    VctDereferenceEndpoint((PVOID)FirstVcEndpoint);
  *(_DWORD *)(v4 + 2352) = -1;
  ExReleaseSpinLockExclusive(v5, v38);
  *a2 = v17;
  return v13;
}

```

## disassembly

```asm
0x140012840  mov     [rsp+arg_8], rdx
0x140012845  push    rbx
0x140012846  push    rbp
0x140012847  push    rsi
0x140012848  push    rdi
0x140012849  push    r12
0x14001284b  push    r13
0x14001284d  push    r14
0x14001284f  push    r15
0x140012851  sub     rsp, 58h
0x140012855  mov     r15, [rcx+180h]
0x14001285c  mov     r13, rcx
0x14001285f  mov     [rsp+98h+arg_0], 0
0x140012867  mov     r14, [r15+18h]
0x14001286b  mov     [rsp+98h+var_58], r14
0x140012870  lea     r12, [r14+780h]
0x140012877  mov     rcx, r12; SpinLock
0x14001287a  mov     [rsp+98h+SpinLock], r12
0x14001287f  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012886  nop     dword ptr [rax+rax+00h]
0x14001288b  mov     [rsp+98h+arg_10], al
0x140012892  call    cs:__imp_PsGetCurrentThreadId
0x140012899  nop     dword ptr [rax+rax+00h]
0x14001289e  lea     rdi, [r15+268h]
0x1400128a5  mov     [r14+930h], eax
0x1400128ac  mov     rbx, [rdi]
0x1400128af  cmp     rbx, rdi
0x1400128b2  jz      short loc_1400128C1
0x1400128b4  add     rbx, 0FFFFFFFFFFFFFDE8h
0x1400128bb  jnz     loc_140012C67
0x1400128c1  xor     esi, esi
0x1400128c3  mov     rcx, r15
0x1400128c6  call    SmbCeGetFirstVcEndpoint
0x1400128cb  mov     rbx, rax
0x1400128ce  test    rax, rax
0x1400128d1  jnz     loc_14005D04C
0x1400128d7  jmp     loc_14005D095
0x1400128dc  movzx   eax, word ptr [r15+2]
0x1400128e1  test    ax, ax
0x1400128e4  jz      loc_140012BFB
0x1400128ea  lea     rcx, [rax+8]
0x1400128ee  add     rcx, r15
0x1400128f1  jz      loc_140012BF4
0x1400128f7  mov     rax, [rcx]
0x1400128fa  test    rax, rax
0x1400128fd  jz      loc_140012BF4
0x140012903  mov     rdx, [rcx+8]
0x140012907  test    rdx, rdx
0x14001290a  jz      loc_140012BF4
0x140012910  cmp     [rax+8], rcx
0x140012914  jnz     loc_140012BF4
0x14001291a  cmp     [rdx], rcx
0x14001291d  jnz     loc_140012BF4
0x140012923  mov     r9d, 0E2FFh
0x140012929  mov     ebp, 0C000020Ch
0x14001292e  cmp     rax, rcx
0x140012931  jz      short loc_14001298E
0x140012933  test    rax, rax
0x140012936  jz      loc_140012BF4
0x14001293c  mov     rdx, [rax]
0x14001293f  test    rdx, rdx
0x140012942  jz      loc_140012BF4
0x140012948  mov     r8, [rax+8]
0x14001294c  test    r8, r8
0x14001294f  jz      loc_140012BF4
0x140012955  cmp     [rdx+8], rax
0x140012959  jnz     loc_140012BF4
0x14001295f  cmp     [r8], rax
0x140012962  jnz     loc_140012BF4
0x140012968  lea     rdi, [rax-190h]
0x14001296f  movsxd  rdx, dword ptr [rdi+8]
0x140012973  test    edx, edx
0x140012975  js      loc_140012BD2
0x14001297b  cmp     [rdi], r9w
0x14001297f  jz      loc_140012C38
0x140012985  test    rdi, rdi
0x140012988  jnz     loc_140012C0D
0x14001298e  mov     eax, dword ptr cs:xmmword_140070ED0+8
0x140012994  mov     edx, esi
0x140012996  test    eax, eax
0x140012998  mov     ecx, 40h ; '@'
0x14001299d  mov     r8d, 6D536543h
0x1400129a3  mov     rdi, rsi
0x1400129a6  cmovnz  edx, eax
0x1400129a9  add     rdx, 10h
0x1400129ad  call    cs:__imp_ExAllocatePool2
0x1400129b4  nop     dword ptr [rax+rax+00h]
0x1400129b9  test    rax, rax
0x1400129bc  jz      loc_140012C9A
0x1400129c2  lea     r8, SmbMmSpinLock; Lock
0x1400129c9  mov     rdx, rax; ListEntry
0x1400129cc  lea     rcx, ListHead; ListHead
0x1400129d3  lea     rdi, [rax+10h]
0x1400129d7  call    cs:__imp_ExInterlockedInsertTailList
0x1400129de  nop     dword ptr [rax+rax+00h]
0x1400129e3  mov     [rdi+4], esi
0x1400129e6  mov     [rdi+18h], r14
0x1400129ea  lea     r12, [rdi+190h]
0x1400129f1  mov     dword ptr [rdi], 40E206h
0x1400129f7  lea     r14, [rdi+1A0h]
0x1400129fe  mov     dword ptr [rdi+0Ch], 1
0x140012a05  mov     dword ptr [rdi+8], 1
0x140012a0c  mov     [r12+8], r12
0x140012a11  mov     [r12], r12
0x140012a15  mov     [r14+8], r14
0x140012a19  mov     [r14], r14
0x140012a1c  movzx   eax, word ptr [rdi+2]
0x140012a20  mov     qword ptr [rdi+1E8h], 0FFFFFFFFFFFFFFFFh
0x140012a2b  mov     qword ptr [rdi+1E0h], 0FFFFFFFFFFFFFFFFh
0x140012a36  mov     qword ptr [rdi+1D8h], 0FFFFFFFFFFFFFFFFh
0x140012a41  mov     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFFFh
0x140012a4c  mov     [rdi+1C8h], rsi
0x140012a53  test    ax, ax
0x140012a56  jz      short loc_140012AB0
0x140012a58  mov     ecx, eax
0x140012a5a  add     rcx, rdi
0x140012a5d  jz      short loc_140012AB0
0x140012a5f  mov     [rcx+0D0h], ebp
0x140012a65  lea     rax, [rcx+8]
0x140012a69  mov     [rcx+0D4h], esi
0x140012a6f  mov     [rax+8], rax
0x140012a73  mov     [rax], rax
0x140012a76  lea     rax, [rcx+0F8h]
0x140012a7d  mov     [rax+8], rax
0x140012a81  mov     [rax], rax
0x140012a84  lea     rax, [rcx+0D8h]
0x140012a8b  mov     [rax+8], rax
0x140012a8f  mov     [rax], rax
0x140012a92  lea     rax, [rcx+0E8h]
0x140012a99  sub     rcx, 0FFFFFFFFFFFFFF80h; SpinLock
0x140012a9d  mov     [rax+8], rax
0x140012aa1  mov     [rax], rax
0x140012aa4  call    cs:__imp_KeInitializeSpinLock
0x140012aab  nop     dword ptr [rax+rax+00h]
0x140012ab0  lea     rax, off_140061178
0x140012ab7  mov     rcx, r15; BugCheckParameter2
0x140012aba  mov     [rdi+40h], rax
0x140012abe  call    SmbCeReferenceServerEntry
0x140012ac3  mov     [rdi+1B0h], r15
0x140012aca  mov     eax, 3
0x140012acf  xchg    eax, [rdi+0Ch]
0x140012ad2  cmp     dword ptr [rbx+0Ch], 0
0x140012ad6  jnz     short loc_140012B47
0x140012ad8  movzx   eax, word ptr [r13+2]
0x140012add  test    ax, ax
0x140012ae0  jz      loc_140012C05
0x140012ae6  add     rax, r13
0x140012ae9  lea     rcx, [rax+8]
0x140012aed  mov     [rdi+180h], r13
0x140012af4  mov     rdx, [rcx+8]
0x140012af8  cmp     [rdx], rcx
0x140012afb  jnz     loc_140012BF4
0x140012b01  mov     [r12], rcx
0x140012b05  mov     [r12+8], rdx
0x140012b0a  mov     [rdx], r12
0x140012b0d  mov     [rcx+8], r12
0x140012b11  mov     rcx, rbx
0x140012b14  inc     dword ptr [rax+18h]
0x140012b17  mov     [rdi+188h], rbx
0x140012b1e  call    VctReferenceEndpoint
0x140012b23  lea     rax, [rbx+208h]
0x140012b2a  mov     rcx, [rax+8]
0x140012b2e  cmp     [rcx], rax
0x140012b31  jnz     loc_140012BF4
0x140012b37  mov     [r14], rax
0x140012b3a  mov     ebp, esi
0x140012b3c  mov     [r14+8], rcx
0x140012b40  mov     [rcx], r14
0x140012b43  mov     [rax+8], r14
0x140012b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b4e  lea     rax, WPP_GLOBAL_Control
0x140012b55  cmp     rcx, rax
0x140012b58  jz      short loc_140012B65
0x140012b5a  mov     eax, [rcx+2Ch]
0x140012b5d  test    al, 40h
0x140012b5f  jnz     loc_140012CA4
0x140012b65  test    ebp, ebp
0x140012b67  jnz     loc_140012CD9
0x140012b6d  mov     rcx, rdi
0x140012b70  call    SmbCeReferenceBindingObject
0x140012b75  mov     r14, [rsp+98h+var_58]
0x140012b7a  mov     r12, [rsp+98h+SpinLock]
0x140012b7f  cmp     [rsp+98h+arg_0], 0
0x140012b87  jz      short loc_140012B91
0x140012b89  mov     rcx, rbx; pContext
0x140012b8c  call    VctDereferenceEndpoint
0x140012b91  movzx   edx, [rsp+98h+arg_10]; OldIrql
0x140012b99  mov     rcx, r12; SpinLock
0x140012b9c  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x140012ba7  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012bae  nop     dword ptr [rax+rax+00h]
0x140012bb3  mov     rax, [rsp+98h+arg_8]
0x140012bbb  mov     [rax], rdi
0x140012bbe  mov     eax, ebp
0x140012bc0  add     rsp, 58h
0x140012bc4  pop     r15
0x140012bc6  pop     r14
0x140012bc8  pop     r13
0x140012bca  pop     r12
0x140012bcc  pop     rdi
0x140012bcd  pop     rsi
0x140012bce  pop     rbp
0x140012bcf  pop     rbx
0x140012bd0  retn
0x140012bd2  mov     r9, rdx; BugCheckParameter3
0x140012bd5  mov     [rsp+98h+BugCheckParameter4], rsi; BugCheckParameter4
0x140012bda  mov     edx, 0A0001h; BugCheckParameter1
0x140012bdf  mov     r8, rdi; BugCheckParameter2
0x140012be2  mov     ecx, 27h ; '''; BugCheckCode
0x140012be7  call    cs:__imp_KeBugCheckEx
0x140012bf4  mov     ecx, 3
0x140012bf9  int     29h; Win8: RtlFailFast(ecx)
0x140012bfb  mov     ecx, 8
0x140012c00  jmp     loc_1400128F7
0x140012c05  mov     rax, rsi
0x140012c08  jmp     loc_140012AE9
0x140012c0d  mov     dword ptr [rsp+98h+arg_18], ebp
0x140012c14  mov     rcx, rdi
0x140012c17  mov     dword ptr [rsp+98h+arg_18+4], esi
0x140012c1e  mov     rdx, [rsp+98h+arg_18]
0x140012c26  call    SmbCeUpperDisconnectBindingObjectLite
0x140012c2b  mov     rcx, rdi; BugCheckParameter2
0x140012c2e  call    SmbCeDereferenceBindingObject
0x140012c33  jmp     loc_14001298E
0x140012c38  mov     rax, [rax]
0x140012c3b  jmp     loc_140012929
0x140012c40  cmp     [rbx+0Ch], esi
0x140012c43  jz      short loc_140012C6B
0x140012c45  mov     rdx, [rbx+218h]
0x140012c4c  mov     rbx, rsi
0x140012c4f  cmp     rdx, rdi
0x140012c52  lea     rcx, [rdx-218h]
0x140012c59  cmovnz  rbx, rcx
0x140012c5d  test    rbx, rbx
0x140012c60  jnz     short loc_140012C40
0x140012c62  jmp     loc_1400128C3
0x140012c67  xor     esi, esi
0x140012c69  jmp     short loc_140012C40
0x140012c6b  mov     eax, [rbx+4]
0x140012c6e  test    al, 2
0x140012c70  jz      short loc_140012C45
0x140012c72  mov     rdx, rbx
0x140012c75  mov     rcx, r13
0x140012c78  call    SmbCeIsObjectBoundToEndpointLite
0x140012c7d  test    al, al
0x140012c7f  jnz     short loc_140012C45
0x140012c81  mov     rcx, rbx
0x140012c84  call    VctReferenceEndpointSafe
0x140012c89  mov     [rsp+98h+arg_0], al
0x140012c90  test    al, al
0x140012c92  jnz     loc_1400128DC
0x140012c98  jmp     short loc_140012C45
0x140012c9a  mov     ebp, 0C000009Ah
0x140012c9f  jmp     loc_140012B7F
0x140012ca4  cmp     byte ptr [rcx+29h], 2
0x140012ca8  jb      loc_140012B65
0x140012cae  mov     rcx, [rcx+18h]
0x140012cb2  lea     r8, WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids
0x140012cb9  mov     [rsp+98h+var_68], ebp
0x140012cbd  mov     edx, 0Bh
0x140012cc2  mov     [rsp+98h+var_70], rdi
0x140012cc7  mov     r9, r13
0x140012cca  mov     [rsp+98h+BugCheckParameter4], rbx
0x140012ccf  call    WPP_SF_qqqL
0x140012cd4  jmp     loc_140012B65
0x140012cd9  mov     rcx, [rdi+1B0h]; BugCheckParameter2
0x140012ce0  test    rcx, rcx
0x140012ce3  jz      loc_14005D0A2
0x140012ce9  xor     edx, edx
0x140012ceb  call    SmbCeDereferenceServerEntryEx
0x140012cf0  mov     [rdi+1B0h], rsi
0x140012cf7  jmp     loc_14005D0A2
0x14005d04c  cmp     dword ptr [rbx+0Ch], 0
0x14005d050  jnz     short loc_14005D078
0x14005d052  mov     rdx, rbx
0x14005d055  mov     rcx, r13
0x14005d058  call    SmbCeIsObjectBoundToEndpointLite
0x14005d05d  test    al, al
0x14005d05f  jnz     short loc_14005D078
0x14005d061  mov     rcx, rbx
0x14005d064  call    VctReferenceEndpointSafe
0x14005d069  mov     [rsp+98h+arg_0], al
0x14005d070  test    al, al
0x14005d072  jnz     loc_1400128DC
0x14005d078  mov     rcx, [rbx+218h]
0x14005d07f  mov     rbx, rsi
0x14005d082  cmp     rcx, rdi
0x14005d085  lea     rax, [rcx-218h]
0x14005d08c  cmovnz  rbx, rax
0x14005d090  test    rbx, rbx
0x14005d093  jnz     short loc_14005D04C
0x14005d095  mov     ebp, 0C000020Ch
0x14005d09a  mov     rdi, rsi
0x14005d09d  jmp     loc_140012B7F
0x14005d0a2  mov     rcx, rdi
0x14005d0a5  call    SmbMmFreeObjectPool
0x14005d0aa  mov     r14, [rsp+98h+var_58]
0x14005d0af  mov     r12, [rsp+98h+SpinLock]
0x14005d0b4  jmp     short loc_14005D09A
```
