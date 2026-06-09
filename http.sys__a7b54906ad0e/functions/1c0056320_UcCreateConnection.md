# UcCreateConnection

- ea: `0x1c0056320`
- end: `0x1c00567bc`
- name: `UcCreateConnection`
- size: `1180`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0058c64`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c00020e8`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c0040d50`
- `0x1c0051840`
- `0x1c0056320`
- `0x1c0056850`
- `0x1c0056d30`
- `0x1c00d6070`
- `0x1c00d60c4`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x1c005648f`
- `ntoskrnl!InitializeSListHead` at `0x1c005648f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00563e5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00563e5`
- `ntoskrnl!KeBugCheckEx` at `0x1c0056628`
- `ntoskrnl!KeBugCheckEx` at `0x1c0056691`
- `ntoskrnl!KeBugCheckEx` at `0x1c0056741`
- `ntoskrnl!KeBugCheckEx` at `0x1c00567af`
- `ntoskrnl!KeBugCheckEx` at `0x1c0056628`
- `ntoskrnl!KeBugCheckEx` at `0x1c0056691`
- `ntoskrnl!KeBugCheckEx` at `0x1c0056741`
- `ntoskrnl!KeBugCheckEx` at `0x1c00567af`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c005636f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c005636f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00564a9`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00564a9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00565b5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00566b4`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00565b5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00566b4`

## pseudocode

```c
__int64 __fastcall UcCreateConnection(__int64 a1, __int64 a2, struct _SLIST_ENTRY *a3, __int64 a4, PSLIST_ENTRY *a5)
{
  bool v5; // zf
  PSLIST_ENTRY v8; // r15
  __int64 v9; // rbx
  unsigned int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // rsi
  __int64 v13; // rcx
  unsigned int v14; // r8d
  unsigned int v15; // eax
  PSLIST_ENTRY v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 (__fastcall *v20)(__int64, __int64, __int64, __int64); // rax
  unsigned int v21; // r14d
  int v22; // edx
  int v23; // r8d
  int Stream; // eax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v26; // r9
  __int64 v27; // rcx
  struct _SLIST_ENTRY *v28; // rsi
  struct _KPROCESS *v29; // rax
  __int64 v30; // r9
  struct _SLIST_ENTRY *v31; // rbx
  ULONG_PTR BugCheckParameter4; // [rsp+20h] [rbp-60h]
  __int64 v34; // [rsp+28h] [rbp-58h]
  struct _SLIST_ENTRY *v35; // [rsp+40h] [rbp-40h] BYREF
  PSLIST_ENTRY v36; // [rsp+48h] [rbp-38h] BYREF
  struct _SLIST_ENTRY *v37; // [rsp+50h] [rbp-30h] BYREF
  __int128 v38; // [rsp+58h] [rbp-28h] BYREF
  __int128 v39; // [rsp+68h] [rbp-18h] BYREF

  v5 = UxCompactMode == 0;
  v36 = 0;
  v8 = 0;
  v37 = 0;
  *a5 = 0;
  if ( v5 )
  {
    v13 = qword_1C00745A0;
    v14 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v15 = *(_DWORD *)qword_1C00745A0 - 1;
    if ( v14 < *(_DWORD *)qword_1C00745A0 )
      v15 = v14;
    v12 = *(_QWORD *)(*(_QWORD *)(qword_1C00745A0 + 32) + 8LL * v15);
    if ( !*(_BYTE *)(v12 + 112) )
      goto LABEL_9;
  }
  else
  {
    v9 = qword_1C00745A0;
    v10 = KeGetCurrentNodeNumber() + 1;
    v11 = *(_DWORD *)v9 - 1;
    if ( v10 < *(_DWORD *)v9 )
      v11 = v10;
    v12 = *(_QWORD *)(*(_QWORD *)(v9 + 32) + 8LL * v11);
    if ( !*(_BYTE *)(v12 + 112) )
    {
      v13 = v9;
LABEL_9:
      PplpLazyInitializeLookasideList(v13, v12);
    }
  }
  ++*(_DWORD *)(v12 + 20);
  v16 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v12);
  if ( !v16 )
  {
    v17 = *(unsigned int *)(v12 + 40);
    v18 = *(unsigned int *)(v12 + 44);
    v19 = *(unsigned int *)(v12 + 36);
    v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v12 + 48);
    ++*(_DWORD *)(v12 + 24);
    v16 = (PSLIST_ENTRY)v20(v19, v18, v17, v12);
  }
  v35 = v16;
  if ( v16 )
  {
    memset(v16, 0, 0x1E0u);
    HIDWORD(v16[1].Next) = 1;
    LODWORD(v16[1].Next) = 1128817493;
    v16[2].Next = 0;
    v16[3].Next = 0;
    v16[4].Next = 0;
    v16[5].Next = 0;
    v16[6].Next = 0;
    v16[7].Next = 0;
    v16[8].Next = 0;
    v16[9].Next = 0;
    v16[10].Next = 0;
    v16[11].Next = 0;
    v16[12].Next = 0;
    v16[13].Next = 0;
    InitializeSListHead((PSLIST_HEADER)&v16[14]);
    *((_QWORD *)&v16[26].Next + 1) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)&v16[27].Next + 1);
    UxPodReferenceSilo(a4, 1129606229);
    *((_QWORD *)&v16[28].Next + 1) = a4;
    v16[29].Next = a3;
    *((_DWORD *)&v16[1].Next + 2) = 0;
    *((_QWORD *)&v16[16].Next + 1) = a2;
    _InterlockedAdd((volatile signed __int32 *)(a2 + 4), 1u);
    *((_QWORD *)&v16[25].Next + 1) = 0;
    *((_DWORD *)&v16[25].Next + 2) = 1;
    *((_QWORD *)&v16[24].Next + 1) = 0;
    v16[25].Next = 0;
    _InterlockedAdd((volatile signed __int32 *)&v16[1].Next + 1, 1u);
    if ( a1 )
    {
      UcTransformConnectionState(v16, 2);
      Stream = UxQuicCreateStream(a1, v22, v23, (unsigned int)&v36, (__int64)&v37, (__int64)&v35);
    }
    else
    {
      Stream = UxWskCreate(a2, &v36, &v37, &v35);
    }
    v8 = v16;
    v21 = Stream;
    if ( Stream >= 0 )
    {
      v16[25].Next = 0;
      v8 = 0;
      *((_QWORD *)&v16[24].Next + 1) = v36;
      v16[25].Next = v37;
      *((_QWORD *)&v16[25].Next + 1) = 1;
      *((_DWORD *)&v16[25].Next + 2) = 3;
      *a5 = v16;
    }
    v16 = v35;
  }
  else
  {
    v21 = -1073741670;
  }
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v16[1].Next + 1, 0xFFFFFFFF) == 1 )
    {
      CurrentProcess = IoGetCurrentProcess();
      v16 = v35;
      v27 = *((_QWORD *)&v35[28].Next + 1);
      v28 = v35 + 2;
      if ( UxSystemProcess == CurrentProcess )
      {
        v5 = v28->Next == 0;
        v38 = 0;
        if ( !v5 || v35[3].Next || v35[4].Next )
          KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v35[2], (ULONG_PTR)"minio\\http\\client\\inc\\http\\httpconn.h", 0x120u);
        if ( !KeGetCurrentIrql() )
        {
          UxPodAttachThread(v27, (__int64)&v38);
          UcFreeHttpConnection(v28);
          UxPodDetachThread((__int64)&v38);
          goto LABEL_36;
        }
      }
      else if ( v28->Next || v35[3].Next || v35[4].Next )
      {
        KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v35[2], (ULONG_PTR)"minio\\http\\client\\inc\\http\\httpconn.h", 0x11Au);
      }
      LODWORD(v34) = -1;
      LOBYTE(v26) = 1;
      UlThreadPoolEnqueueWorkItem(0, &v35[2], UcFreeHttpConnection, v26, v27, v34);
    }
    else
    {
      v16 = v35;
    }
  }
LABEL_36:
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)&v16[1].Next + 1, 0xFFFFFFFF) == 1 )
  {
    v29 = IoGetCurrentProcess();
    v30 = *((_QWORD *)&v35[28].Next + 1);
    v31 = v35 + 2;
    if ( UxSystemProcess == v29 )
    {
      v39 = 0;
      if ( v31->Next || v35[3].Next || v35[4].Next )
        KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v35[2], (ULONG_PTR)"minio\\http\\client\\inc\\http\\httpconn.h", 0x120u);
      if ( !KeGetCurrentIrql() )
      {
        UxPodAttachThread(v30, (__int64)&v39);
        UcFreeHttpConnection(v31);
        UxPodDetachThread((__int64)&v39);
        return v21;
      }
    }
    else if ( v31->Next || v35[3].Next || v35[4].Next )
    {
      KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v35[2], (ULONG_PTR)"minio\\http\\client\\inc\\http\\httpconn.h", 0x11Au);
    }
    LODWORD(v34) = -1;
    BugCheckParameter4 = v30;
    LOBYTE(v30) = 1;
    UlThreadPoolEnqueueWorkItem(0, &v35[2], UcFreeHttpConnection, v30, BugCheckParameter4, v34);
  }
  return v21;
}

```

## disassembly

```asm
0x1c0056320  mov     [rsp-38h+arg_0], rbx
0x1c0056325  mov     [rsp-38h+arg_18], r9
0x1c005632a  mov     [rsp-38h+arg_10], r8
0x1c005632f  push    rbp
0x1c0056330  push    rsi
0x1c0056331  push    rdi
0x1c0056332  push    r12
0x1c0056334  push    r13
0x1c0056336  push    r14
0x1c0056338  push    r15
0x1c005633a  mov     rbp, rsp
0x1c005633d  sub     rsp, 80h
0x1c0056344  mov     r12, [rbp+arg_20]
0x1c0056348  xor     edi, edi
0x1c005634a  cmp     cs:UxCompactMode, dil
0x1c0056351  mov     r14, rdx
0x1c0056354  mov     r13, rcx
0x1c0056357  mov     [rbp+var_38], rdi
0x1c005635b  mov     r15d, edi
0x1c005635e  mov     [rbp+var_30], rdi
0x1c0056362  mov     [r12], rdi
0x1c0056366  jz      short loc_1C00563A3
0x1c0056368  mov     rbx, cs:qword_1C00745A0
0x1c005636f  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0056376  nop     dword ptr [rax+rax+00h]
0x1c005637b  mov     edx, [rbx]
0x1c005637d  movzx   r8d, ax
0x1c0056381  inc     r8d
0x1c0056384  cmp     r8d, edx
0x1c0056387  lea     eax, [rdx-1]
0x1c005638a  cmovb   eax, r8d
0x1c005638e  mov     edx, eax
0x1c0056390  mov     rax, [rbx+20h]
0x1c0056394  mov     rsi, [rax+rdx*8]
0x1c0056398  cmp     [rsi+70h], dil
0x1c005639c  jnz     short loc_1C00563DA
0x1c005639e  mov     rcx, rbx
0x1c00563a1  jmp     short loc_1C00563D2
0x1c00563a3  mov     eax, gs:1A4h
0x1c00563ab  mov     rcx, cs:qword_1C00745A0
0x1c00563b2  lea     r8d, [rax+1]
0x1c00563b6  mov     edx, [rcx]
0x1c00563b8  cmp     r8d, edx
0x1c00563bb  lea     eax, [rdx-1]
0x1c00563be  cmovb   eax, r8d
0x1c00563c2  mov     edx, eax
0x1c00563c4  mov     rax, [rcx+20h]
0x1c00563c8  mov     rsi, [rax+rdx*8]
0x1c00563cc  cmp     [rsi+70h], dil
0x1c00563d0  jnz     short loc_1C00563DA
0x1c00563d2  mov     rdx, rsi
0x1c00563d5  call    PplpLazyInitializeLookasideList
0x1c00563da  mov     edi, 1
0x1c00563df  mov     rcx, rsi; ListHead
0x1c00563e2  add     [rsi+14h], edi
0x1c00563e5  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00563ec  nop     dword ptr [rax+rax+00h]
0x1c00563f1  mov     rbx, rax
0x1c00563f4  test    rax, rax
0x1c00563f7  jnz     short loc_1C0056416
0x1c00563f9  mov     r8d, [rsi+28h]
0x1c00563fd  mov     r9, rsi
0x1c0056400  mov     edx, [rsi+2Ch]
0x1c0056403  mov     ecx, [rsi+24h]
0x1c0056406  mov     rax, [rsi+30h]
0x1c005640a  add     [rsi+18h], edi
0x1c005640d  call    cs:__guard_dispatch_icall_fptr
0x1c0056413  mov     rbx, rax
0x1c0056416  xor     esi, esi
0x1c0056418  mov     [rbp+var_40], rbx
0x1c005641c  test    rbx, rbx
0x1c005641f  jnz     short loc_1C005642C
0x1c0056421  mov     r14d, 0C000009Ah
0x1c0056427  jmp     loc_1C0056593
0x1c005642c  xor     edx, edx; Val
0x1c005642e  mov     r8d, 1E0h; Size
0x1c0056434  mov     rcx, rbx; void *
0x1c0056437  call    memset
0x1c005643c  mov     [rbx+14h], edi
0x1c005643f  lea     rcx, [rbx+0E0h]; SListHead
0x1c0056446  mov     dword ptr [rbx+10h], 43486355h
0x1c005644d  mov     [rbx+20h], rsi
0x1c0056451  mov     [rbx+30h], rsi
0x1c0056455  mov     [rbx+40h], rsi
0x1c0056459  mov     [rbx+50h], rsi
0x1c005645d  mov     [rbx+60h], rsi
0x1c0056461  mov     [rbx+70h], rsi
0x1c0056465  mov     [rbx+80h], rsi
0x1c005646c  mov     [rbx+90h], rsi
0x1c0056473  mov     [rbx+0A0h], rsi
0x1c005647a  mov     [rbx+0B0h], rsi
0x1c0056481  mov     [rbx+0C0h], rsi
0x1c0056488  mov     [rbx+0D0h], rsi
0x1c005648f  call    cs:__imp_InitializeSListHead
0x1c0056496  nop     dword ptr [rax+rax+00h]
0x1c005649b  lea     rcx, [rbx+1B8h]; SpinLock
0x1c00564a2  mov     [rbx+1A8h], rsi
0x1c00564a9  call    cs:__imp_KeInitializeSpinLock
0x1c00564b0  nop     dword ptr [rax+rax+00h]
0x1c00564b5  mov     rsi, [rbp+arg_18]
0x1c00564b9  mov     edx, 43546C55h
0x1c00564be  mov     rcx, rsi
0x1c00564c1  call    UxPodReferenceSilo
0x1c00564c6  mov     rax, [rbp+arg_10]
0x1c00564ca  mov     [rbx+1C8h], rsi
0x1c00564d1  xor     esi, esi
0x1c00564d3  mov     [rbx+1D0h], rax
0x1c00564da  mov     [rbx+18h], esi
0x1c00564dd  mov     [rbx+108h], r14
0x1c00564e4  lock add [r14+4], edi
0x1c00564e9  mov     [rbx+198h], rsi
0x1c00564f0  mov     [rbx+198h], edi
0x1c00564f6  mov     [rbx+188h], rsi
0x1c00564fd  mov     [rbx+190h], rsi
0x1c0056504  lock add [rbx+14h], edi
0x1c0056508  test    r13, r13
0x1c005650b  jz      short loc_1C0056538
0x1c005650d  lea     edx, [rsi+2]
0x1c0056510  mov     rcx, rbx
0x1c0056513  call    UcTransformConnectionState
0x1c0056518  lea     rax, [rbp+var_40]
0x1c005651c  mov     rcx, r13
0x1c005651f  mov     [rsp+80h+var_58], rax
0x1c0056524  lea     r9, [rbp+var_38]
0x1c0056528  lea     rax, [rbp+var_30]
0x1c005652c  mov     [rsp+80h+BugCheckParameter4], rax
0x1c0056531  call    UxQuicCreateStream
0x1c0056536  jmp     short loc_1C005654C
0x1c0056538  lea     r9, [rbp+var_40]
0x1c005653c  mov     rcx, r14
0x1c005653f  lea     r8, [rbp+var_30]
0x1c0056543  lea     rdx, [rbp+var_38]
0x1c0056547  call    UxWskCreate
0x1c005654c  mov     r15, rbx
0x1c005654f  mov     r14d, eax
0x1c0056552  test    eax, eax
0x1c0056554  js      short loc_1C005658F
0x1c0056556  mov     [rbx+190h], rsi
0x1c005655d  mov     r15, rsi
0x1c0056560  mov     rax, [rbp+var_38]
0x1c0056564  mov     [rbx+188h], rax
0x1c005656b  mov     rax, [rbp+var_30]
0x1c005656f  mov     [rbx+190h], rax
0x1c0056576  mov     qword ptr [rbx+198h], 1
0x1c0056581  mov     dword ptr [rbx+198h], 3
0x1c005658b  mov     [r12], rbx
0x1c005658f  mov     rbx, [rbp+var_40]
0x1c0056593  or      r13d, 0FFFFFFFFh
0x1c0056597  or      r12d, 0FFFFFFFFh
0x1c005659b  test    rbx, rbx
0x1c005659e  jz      loc_1C00566A2
0x1c00565a4  mov     eax, r12d
0x1c00565a7  lock xadd [rbx+14h], eax
0x1c00565ac  add     eax, r12d
0x1c00565af  jnz     loc_1C005669E
0x1c00565b5  call    cs:__imp_IoGetCurrentProcess
0x1c00565bc  nop     dword ptr [rax+rax+00h]
0x1c00565c1  cmp     cs:UxSystemProcess, rax
0x1c00565c8  mov     rbx, [rbp+var_40]
0x1c00565cc  mov     rcx, [rbx+1C8h]
0x1c00565d3  lea     rsi, [rbx+20h]
0x1c00565d7  jz      short loc_1C0056635
0x1c00565d9  cmp     qword ptr [rsi], 0
0x1c00565dd  jnz     short loc_1C005660D
0x1c00565df  cmp     qword ptr [rsi+10h], 0
0x1c00565e4  jnz     short loc_1C005660D
0x1c00565e6  cmp     qword ptr [rsi+20h], 0
0x1c00565eb  jnz     short loc_1C005660D
0x1c00565ed  mov     dword ptr [rsp+80h+var_58], r13d
0x1c00565f2  lea     r8, UcFreeHttpConnection
0x1c00565f9  mov     [rsp+80h+BugCheckParameter4], rcx
0x1c00565fe  mov     r9b, dil
0x1c0056601  xor     ecx, ecx
0x1c0056603  mov     rdx, rsi
0x1c0056606  call    UlThreadPoolEnqueueWorkItem
0x1c005660b  jmp     short loc_1C0056672
0x1c005660d  lea     r9, aMinioHttpClien_0; "minio\\http\\client\\inc\\http\\httpcon"...
0x1c0056614  mov     [rsp+80h+BugCheckParameter4], 11Ah; BugCheckParameter4
0x1c005661d  mov     r8, rsi; BugCheckParameter2
0x1c0056620  mov     rdx, rdi; BugCheckParameter1
0x1c0056623  mov     ecx, 0FAh; BugCheckCode
0x1c0056628  call    cs:__imp_KeBugCheckEx
0x1c0056635  cmp     qword ptr [rsi], 0
0x1c0056639  xorps   xmm0, xmm0
0x1c005663c  movups  [rbp+var_28], xmm0
0x1c0056640  jnz     short loc_1C0056676
0x1c0056642  cmp     qword ptr [rsi+10h], 0
0x1c0056647  jnz     short loc_1C0056676
0x1c0056649  cmp     qword ptr [rsi+20h], 0
0x1c005664e  jnz     short loc_1C0056676
0x1c0056650  mov     rax, cr8
0x1c0056654  test    al, al
0x1c0056656  jnz     short loc_1C00565ED
0x1c0056658  lea     rdx, [rbp+var_28]
0x1c005665c  call    UxPodAttachThread
0x1c0056661  mov     rcx, rsi
0x1c0056664  call    UcFreeHttpConnection
0x1c0056669  lea     rcx, [rbp+var_28]
0x1c005666d  call    UxPodDetachThread
0x1c0056672  xor     esi, esi
0x1c0056674  jmp     short loc_1C00566A2
0x1c0056676  lea     r9, aMinioHttpClien_0; "minio\\http\\client\\inc\\http\\httpcon"...
0x1c005667d  mov     [rsp+80h+BugCheckParameter4], 120h; BugCheckParameter4
0x1c0056686  mov     r8, rsi; BugCheckParameter2
0x1c0056689  mov     rdx, rdi; BugCheckParameter1
0x1c005668c  mov     ecx, 0FAh; BugCheckCode
0x1c0056691  call    cs:__imp_KeBugCheckEx
0x1c005669e  mov     rbx, [rbp+var_40]
0x1c00566a2  test    r15, r15
0x1c00566a5  jz      short loc_1C0056707
0x1c00566a7  mov     eax, r12d
0x1c00566aa  lock xadd [rbx+14h], eax
0x1c00566af  add     eax, r12d
0x1c00566b2  jnz     short loc_1C0056707
0x1c00566b4  call    cs:__imp_IoGetCurrentProcess
0x1c00566bb  nop     dword ptr [rax+rax+00h]
0x1c00566c0  cmp     cs:UxSystemProcess, rax
0x1c00566c7  mov     rcx, [rbp+var_40]
0x1c00566cb  mov     r9, [rcx+1C8h]
0x1c00566d2  lea     rbx, [rcx+20h]
0x1c00566d6  jz      short loc_1C005674E
0x1c00566d8  cmp     [rbx], rsi
0x1c00566db  jnz     short loc_1C0056726
0x1c00566dd  cmp     [rbx+10h], rsi
0x1c00566e1  jnz     short loc_1C0056726
0x1c00566e3  cmp     [rbx+20h], rsi
0x1c00566e7  jnz     short loc_1C0056726
0x1c00566e9  mov     dword ptr [rsp+80h+var_58], r13d
0x1c00566ee  lea     r8, UcFreeHttpConnection
0x1c00566f5  mov     [rsp+80h+BugCheckParameter4], r9
0x1c00566fa  mov     rdx, rbx
0x1c00566fd  mov     r9b, dil
0x1c0056700  xor     ecx, ecx
0x1c0056702  call    UlThreadPoolEnqueueWorkItem
0x1c0056707  mov     rbx, [rsp+80h+arg_0]
0x1c005670f  mov     eax, r14d
0x1c0056712  add     rsp, 80h
0x1c0056719  pop     r15
0x1c005671b  pop     r14
0x1c005671d  pop     r13
0x1c005671f  pop     r12
0x1c0056721  pop     rdi
0x1c0056722  pop     rsi
0x1c0056723  pop     rbp
0x1c0056724  retn
0x1c0056726  lea     r9, aMinioHttpClien_0; "minio\\http\\client\\inc\\http\\httpcon"...
0x1c005672d  mov     [rsp+80h+BugCheckParameter4], 11Ah; BugCheckParameter4
0x1c0056736  mov     r8, rbx; BugCheckParameter2
0x1c0056739  mov     rdx, rdi; BugCheckParameter1
0x1c005673c  mov     ecx, 0FAh; BugCheckCode
0x1c0056741  call    cs:__imp_KeBugCheckEx
0x1c005674e  xorps   xmm0, xmm0
0x1c0056751  movups  [rbp+var_18], xmm0
0x1c0056755  cmp     [rbx], rsi
0x1c0056758  jnz     short loc_1C0056794
0x1c005675a  cmp     [rbx+10h], rsi
0x1c005675e  jnz     short loc_1C0056794
0x1c0056760  cmp     [rbx+20h], rsi
0x1c0056764  jnz     short loc_1C0056794
0x1c0056766  mov     rax, cr8
0x1c005676a  test    al, al
0x1c005676c  jnz     loc_1C00566E9
0x1c0056772  lea     rdx, [rbp+var_18]
0x1c0056776  mov     rcx, r9
0x1c0056779  call    UxPodAttachThread
0x1c005677e  mov     rcx, rbx
0x1c0056781  call    UcFreeHttpConnection
0x1c0056786  lea     rcx, [rbp+var_18]
0x1c005678a  call    UxPodDetachThread
0x1c005678f  jmp     loc_1C0056707
0x1c0056794  lea     r9, aMinioHttpClien_0; "minio\\http\\client\\inc\\http\\httpcon"...
0x1c005679b  mov     [rsp+80h+BugCheckParameter4], 120h; BugCheckParameter4
0x1c00567a4  mov     r8, rbx; BugCheckParameter2
0x1c00567a7  mov     rdx, rdi; BugCheckParameter1
0x1c00567aa  mov     ecx, 0FAh; BugCheckCode
0x1c00567af  call    cs:__imp_KeBugCheckEx
```
