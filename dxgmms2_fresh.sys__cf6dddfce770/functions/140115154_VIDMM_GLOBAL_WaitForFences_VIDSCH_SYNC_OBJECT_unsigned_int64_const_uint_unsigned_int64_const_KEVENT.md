# VIDMM_GLOBAL::WaitForFences(_VIDSCH_SYNC_OBJECT * *,unsigned __int64 const *,uint,unsigned __int64 const *,_KEVENT *)

- ea: `0x140115154`
- end: `0x140115641`
- name: `?WaitForFences@VIDMM_GLOBAL@@QEAAXPEAPEAU_VIDSCH_SYNC_OBJECT@@PEB_KI1PEAU_KEVENT@@@Z`
- size: `1261`
- prototype: `void __fastcall(VIDMM_GLOBAL *this, struct _VIDSCH_SYNC_OBJECT **, const unsigned __int64 *, unsigned int, const unsigned __int64 *, struct _KEVENT *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x140030854`
- `0x14003c320`
- `0x140097b64`
- `0x1400bf268`

## callees

- `0x140004268`
- `0x14002b790`
- `0x14002fb54`
- `0x140030b2c`
- `0x1400394c0`
- `0x140058f50`
- `0x140115154`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1401154cc`
- `ntoskrnl!ObfReferenceObject` at `0x1401154cc`
- `ntoskrnl!ObfDereferenceObject` at `0x140115350`
- `ntoskrnl!ObfDereferenceObject` at `0x1401155dc`
- `ntoskrnl!ObfDereferenceObject` at `0x140115350`
- `ntoskrnl!ObfDereferenceObject` at `0x1401155dc`
- `ntoskrnl!KeDelayExecutionThread` at `0x140115388`
- `ntoskrnl!KeDelayExecutionThread` at `0x140115388`
- `ntoskrnl!ObCreateObject` at `0x1401152e7`
- `ntoskrnl!ObCreateObject` at `0x1401152e7`
- `ntoskrnl!ExEventObjectType` at `0x140115293`
- `ntoskrnl!KeSetEvent` at `0x140115630`
- `ntoskrnl!KeSetEvent` at `0x140115630`
- `ntoskrnl!KeInitializeEvent` at `0x140115564`
- `ntoskrnl!KeInitializeEvent` at `0x140115564`
- `ntoskrnl!KeWaitForSingleObject` at `0x140115545`
- `ntoskrnl!KeWaitForSingleObject` at `0x140115545`
- `ntoskrnl!ExFreePoolWithTag` at `0x140115212`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401153ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401153e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401154b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140115212`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401153ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401153e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401154b3`
- `watchdog!WdLogSingleEntry1` at `0x140115304`
- `watchdog!WdLogSingleEntry1` at `0x14011559f`
- `watchdog!WdLogSingleEntry1` at `0x1401155f0`
- `watchdog!WdLogSingleEntry1` at `0x140115304`
- `watchdog!WdLogSingleEntry1` at `0x14011559f`
- `watchdog!WdLogSingleEntry1` at `0x1401155f0`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::WaitForFences(
        VIDMM_GLOBAL *this,
        struct _VIDSCH_SYNC_OBJECT **a2,
        const unsigned __int64 *a3,
        unsigned int a4,
        const unsigned __int64 *a5,
        struct _KEVENT *a6)
{
  struct _KEVENT *v6; // rsi
  __int64 v7; // r11
  const unsigned __int64 *v8; // rbx
  char v9; // r15
  VIDMM_GLOBAL *v11; // rax
  unsigned int v12; // r14d
  struct _VIDSCH_SYNC_OBJECT **v13; // r13
  unsigned int i; // r9d
  struct _VIDSCH_SYNC_OBJECT *v15; // rcx
  int v16; // eax
  __int64 v17; // rdi
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r10
  unsigned int v23; // r8d
  const unsigned __int64 *v24; // rsi
  __int64 v25; // rdx
  struct _VIDSCH_SYNC_OBJECT **v26; // r15
  unsigned __int64 v27; // r9
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  PVOID v30; // rcx
  int v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // ecx
  int v35; // r8d
  char v36; // [rsp+50h] [rbp-B0h]
  char v37; // [rsp+51h] [rbp-AFh]
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int64 *v39; // [rsp+60h] [rbp-A0h]
  VIDMM_GLOBAL *v40; // [rsp+68h] [rbp-98h]
  PVOID P; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v42[16]; // [rsp+78h] [rbp-88h] BYREF
  int v43; // [rsp+88h] [rbp-78h]
  const unsigned __int64 *v44; // [rsp+90h] [rbp-70h]
  struct _VIDSCH_SYNC_OBJECT **v45; // [rsp+98h] [rbp-68h]
  struct _KEVENT *v46; // [rsp+A0h] [rbp-60h]
  union _LARGE_INTEGER Interval; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v48[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v49; // [rsp+D0h] [rbp-30h]
  PVOID v50; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[16]; // [rsp+E8h] [rbp-18h] BYREF
  int v52; // [rsp+F8h] [rbp-8h]

  v6 = a6;
  v7 = 0;
  v8 = a3;
  v46 = a6;
  v9 = 1;
  Object = 0;
  v39 = a3;
  v36 = 1;
  v11 = this;
  v44 = a3;
  v12 = a4;
  v45 = a2;
  v13 = a2;
  v40 = this;
  v37 = 1;
  while ( 1 )
  {
    v50 = 0;
    v52 = 0;
    P = 0;
    v43 = 0;
    if ( a5 && !*((_BYTE *)v11 + 736) )
    {
      v20 = NonPagedPoolZeroedArray<unsigned __int64,2,945908054>::AllocateElements(&v50, a4);
      v21 = NonPagedPoolZeroedArray<_VIDSCH_SYNC_OBJECT *,2,945908054>::AllocateElements(&P, a4);
      v7 = 0;
      v22 = v21;
      if ( !v20 || !v21 )
      {
        LODWORD(v17) = -1073741801;
        WdLogSingleEntry1(1, -1073741801);
        WdLogGlobalForLineNumber = 18305;
        DxgkLogInternalTriageEvent(
          v32,
          0x40000,
          v33,
          (unsigned int)L"Could not wait on fence array - filtered fence object storage allocation failed. Status = 0x%I64p",
          -1073741801,
          0,
          0,
          0);
LABEL_19:
        v8 = v39;
        goto LABEL_20;
      }
      v12 = 0;
      v23 = 0;
      if ( a4 )
      {
        v24 = v44;
        v25 = 0;
        v26 = v45;
        do
        {
          v27 = v24[v25];
          v28 = a5[v25];
          if ( v28 <= v27 || v28 - v27 < 0x7FFFFFFF )
          {
            v29 = v12++;
            *(_QWORD *)(v20 + 8 * v29) = v27;
            *(_QWORD *)(v22 + 8 * v29) = v26[v25];
          }
          ++v23;
          ++v25;
        }
        while ( v23 < a4 );
        v6 = v46;
        v9 = v36;
      }
      v8 = (const unsigned __int64 *)v50;
      v13 = (struct _VIDSCH_SYNC_OBJECT **)P;
      v39 = (const unsigned __int64 *)v50;
    }
    for ( i = 0; i < v12; ++i )
    {
      v15 = v13[i];
      if ( v15 && !(unsigned __int8)VidSchIsMonitoredFenceSignaled(v15, v8[i]) )
      {
        v9 = v7;
        v36 = v7;
        goto LABEL_16;
      }
    }
    v36 = v9;
    if ( v9 )
    {
      if ( v6 )
        KeSetEvent(v6, 0, 0);
      break;
    }
LABEL_16:
    if ( v6 )
    {
      v30 = v6;
      Object = v6;
    }
    else
    {
      v48[0] = 48;
      v48[3] = 512;
      v48[1] = v7;
      v48[2] = v7;
      v49 = 0;
      v16 = ObCreateObject(0, ExEventObjectType, v48, 0, v7, 24, v7, v7, &Object);
      v17 = v16;
      if ( v16 < 0 )
      {
        WdLogSingleEntry1(1, v16);
        WdLogGlobalForLineNumber = 18394;
        DxgkLogInternalTriageEvent(
          v18,
          0x40000,
          v19,
          (unsigned int)L"Could not wait on fence array - kernel event object creation failed. Status = 0x%I64p",
          v17,
          0,
          0,
          0);
        goto LABEL_19;
      }
      KeInitializeEvent((PRKEVENT)Object, SynchronizationEvent, 0);
      v30 = Object;
    }
    ObfReferenceObject(v30);
    v31 = VidSchSubmitWaitFromCpu(
            v12,
            v13,
            v8,
            (__int64)Object,
            0,
            1,
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v40 + 2) + 744LL) + 320LL),
            0);
    v17 = v31;
    if ( v31 < 0 )
    {
      ObfDereferenceObject(Object);
      WdLogSingleEntry1(1, v17);
      WdLogGlobalForLineNumber = 18428;
      DxgkLogInternalTriageEvent(
        v34,
        0x40000,
        v35,
        (unsigned int)L"Could not wait on fence array - scheduler submission of the CPU wait failed. Status = 0x%I64p",
        v17,
        0,
        0,
        0);
      goto LABEL_19;
    }
    if ( v6 )
      break;
    v37 = 0;
    LODWORD(v17) = KeWaitForSingleObject(Object, Executive, 0, 0, 0);
LABEL_20:
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    if ( (int)v17 >= 0 || !v37 )
      break;
    Interval.QuadPart = 50000;
    KeDelayExecutionThread(0, 0, &Interval);
    v7 = 0;
    if ( P != v42 && P )
    {
      ExFreePoolWithTag(P, 0);
      v7 = 0;
    }
    P = 0;
    v11 = v40;
    v43 = 0;
    if ( v50 != v51 && v50 )
    {
      ExFreePoolWithTag(v50, 0);
      v11 = v40;
      v7 = 0;
    }
  }
  if ( P != v42 && P )
    ExFreePoolWithTag(P, 0);
  P = 0;
  v43 = 0;
  if ( v50 != v51 )
  {
    if ( v50 )
      ExFreePoolWithTag(v50, 0);
  }
}

```

## disassembly

```asm
0x140115154  push    rbp
0x140115156  push    rbx
0x140115157  push    rsi
0x140115158  push    rdi
0x140115159  push    r12
0x14011515b  push    r13
0x14011515d  push    r14
0x14011515f  push    r15
0x140115161  lea     rbp, [rsp-18h]
0x140115166  sub     rsp, 118h
0x14011516d  mov     rax, cs:__security_cookie
0x140115174  xor     rax, rsp
0x140115177  mov     [rbp+50h+var_50], rax
0x14011517b  mov     rsi, [rbp+50h+arg_28]
0x140115182  xor     r11d, r11d
0x140115185  mov     rbx, r8
0x140115188  mov     [rbp+50h+var_B0], rsi
0x14011518c  mov     r15b, 1
0x14011518f  mov     [rsp+150h+Object], r11
0x140115194  mov     [rsp+150h+var_F0], rbx
0x140115199  mov     r12d, r9d
0x14011519c  mov     [rsp+150h+var_100], r15b
0x1401151a1  mov     rax, rcx
0x1401151a4  mov     [rbp+50h+var_C0], r8
0x1401151a8  mov     r14d, r9d
0x1401151ab  mov     [rbp+50h+var_B8], rdx
0x1401151af  mov     r13, rdx
0x1401151b2  mov     [rsp+150h+var_E8], rcx
0x1401151b7  mov     [rsp+150h+var_FF], 1
0x1401151bc  mov     rdi, [rbp+50h+arg_20]
0x1401151c3  mov     [rbp+50h+var_70], r11
0x1401151c7  mov     [rbp+50h+var_58], r11d
0x1401151cb  mov     [rsp+150h+P], r11
0x1401151d0  mov     [rbp+50h+var_C8], r11d
0x1401151d4  test    rdi, rdi
0x1401151d7  jnz     loc_1401153FF
0x1401151dd  mov     r9d, r11d
0x1401151e0  cmp     r9d, r14d
0x1401151e3  jb      short loc_140115260
0x1401151e5  mov     [rsp+150h+var_100], r15b
0x1401151ea  test    r15b, r15b
0x1401151ed  jz      loc_14011528A
0x1401151f3  test    rsi, rsi
0x1401151f6  jnz     loc_140115628
0x1401151fc  mov     rcx, [rsp+150h+P]; P
0x140115201  lea     rax, [rsp+150h+var_D8]
0x140115206  cmp     rcx, rax
0x140115209  jz      short loc_14011521E
0x14011520b  test    rcx, rcx
0x14011520e  jz      short loc_14011521E
0x140115210  xor     edx, edx; Tag
0x140115212  call    cs:__imp_ExFreePoolWithTag
0x140115219  nop     dword ptr [rax+rax+00h]
0x14011521e  mov     rcx, [rbp+50h+var_70]; P
0x140115222  lea     rax, [rbp+50h+var_68]
0x140115226  mov     [rsp+150h+P], 0
0x14011522f  mov     [rbp+50h+var_C8], 0
0x140115236  cmp     rcx, rax
0x140115239  jnz     loc_1401154A8
0x14011523f  mov     rcx, [rbp+50h+var_50]
0x140115243  xor     rcx, rsp; StackCookie
0x140115246  call    __security_check_cookie
0x14011524b  add     rsp, 118h
0x140115252  pop     r15
0x140115254  pop     r14
0x140115256  pop     r13
0x140115258  pop     r12
0x14011525a  pop     rdi
0x14011525b  pop     rsi
0x14011525c  pop     rbx
0x14011525d  pop     rbp
0x14011525e  retn
0x140115260  mov     edx, r9d
0x140115263  mov     rcx, [r13+rdx*8+0]
0x140115268  test    rcx, rcx
0x14011526b  jz      loc_1401154A0
0x140115271  mov     rdx, [rbx+rdx*8]
0x140115275  call    VidSchIsMonitoredFenceSignaled
0x14011527a  test    al, al
0x14011527c  jnz     loc_1401154A0
0x140115282  mov     r15b, r11b
0x140115285  mov     [rsp+150h+var_100], r11b
0x14011528a  test    rsi, rsi
0x14011528d  jnz     loc_1401154C4
0x140115293  mov     rdx, cs:ExEventObjectType
0x14011529a  lea     rax, [rsp+150h+Object]
0x14011529f  mov     [rsp+150h+var_110], rax
0x1401152a4  lea     r8, [rbp+50h+var_A0]
0x1401152a8  mov     dword ptr [rsp+150h+var_118], r11d
0x1401152ad  xorps   xmm0, xmm0
0x1401152b0  mov     dword ptr [rsp+150h+var_120], r11d
0x1401152b5  xor     r9d, r9d
0x1401152b8  mov     rdx, [rdx]
0x1401152bb  xor     ecx, ecx
0x1401152bd  mov     dword ptr [rsp+150h+var_128], 18h
0x1401152c5  mov     [rsp+150h+Timeout], r11
0x1401152ca  mov     [rbp+50h+var_A0], 30h ; '0'
0x1401152d2  mov     [rbp+50h+var_88], 200h
0x1401152da  mov     [rbp+50h+var_98], r11
0x1401152de  mov     [rbp+50h+var_90], r11
0x1401152e2  movdqu  [rbp+50h+var_80], xmm0
0x1401152e7  call    cs:__imp_ObCreateObject
0x1401152ee  nop     dword ptr [rax+rax+00h]
0x1401152f3  movsxd  rdi, eax
0x1401152f6  test    eax, eax
0x1401152f8  jns     loc_140115558
0x1401152fe  mov     rdx, rdi
0x140115301  lea     ecx, [rsi+1]
0x140115304  call    cs:__imp_WdLogSingleEntry1
0x14011530b  nop     dword ptr [rax+rax+00h]
0x140115310  xor     eax, eax
0x140115312  mov     cs:WdLogGlobalForLineNumber, 47DAh
0x14011531c  mov     [rsp+150h+var_118], rax
0x140115321  lea     r9, aCouldNotWaitOn_1; "Could not wait on fence array - kernel "...
0x140115328  mov     [rsp+150h+var_120], rax
0x14011532d  mov     [rsp+150h+var_128], rax
0x140115332  mov     [rsp+150h+Timeout], rdi
0x140115337  mov     edx, 40000h
0x14011533c  call    DxgkLogInternalTriageEvent
0x140115341  mov     rbx, [rsp+150h+var_F0]
0x140115346  mov     rcx, [rsp+150h+Object]; Object
0x14011534b  test    rcx, rcx
0x14011534e  jz      short loc_140115365
0x140115350  call    cs:__imp_ObfDereferenceObject
0x140115357  nop     dword ptr [rax+rax+00h]
0x14011535c  mov     [rsp+150h+Object], 0
0x140115365  test    edi, edi
0x140115367  jns     loc_1401151FC
0x14011536d  cmp     [rsp+150h+var_FF], 0
0x140115372  jz      loc_1401151FC
0x140115378  lea     r8, [rbp+50h+Interval]; Interval
0x14011537c  mov     qword ptr [rbp+50h+Interval], 0C350h
0x140115384  xor     edx, edx; Alertable
0x140115386  xor     ecx, ecx; WaitMode
0x140115388  call    cs:__imp_KeDelayExecutionThread
0x14011538f  nop     dword ptr [rax+rax+00h]
0x140115394  mov     rcx, [rsp+150h+P]; P
0x140115399  lea     rax, [rsp+150h+var_D8]
0x14011539e  xor     r11d, r11d
0x1401153a1  cmp     rcx, rax
0x1401153a4  jz      short loc_1401153BC
0x1401153a6  test    rcx, rcx
0x1401153a9  jz      short loc_1401153BC
0x1401153ab  xor     edx, edx; Tag
0x1401153ad  call    cs:__imp_ExFreePoolWithTag
0x1401153b4  nop     dword ptr [rax+rax+00h]
0x1401153b9  xor     r11d, r11d
0x1401153bc  mov     rcx, [rbp+50h+var_70]; P
0x1401153c0  lea     rax, [rbp+50h+var_68]
0x1401153c4  cmp     rcx, rax
0x1401153c7  mov     [rsp+150h+P], r11
0x1401153cc  mov     rax, [rsp+150h+var_E8]
0x1401153d1  mov     [rbp+50h+var_C8], r11d
0x1401153d5  jz      loc_1401151BC
0x1401153db  test    rcx, rcx
0x1401153de  jz      loc_1401151BC
0x1401153e4  xor     edx, edx; Tag
0x1401153e6  call    cs:__imp_ExFreePoolWithTag
0x1401153ed  nop     dword ptr [rax+rax+00h]
0x1401153f2  mov     rax, [rsp+150h+var_E8]
0x1401153f7  xor     r11d, r11d
0x1401153fa  jmp     loc_1401151BC
0x1401153ff  cmp     [rax+2E0h], r11b
0x140115406  jnz     loc_1401151DD
0x14011540c  mov     edx, r12d
0x14011540f  lea     rcx, [rbp+50h+var_70]
0x140115413  call    ?AllocateElements@?$NonPagedPoolZeroedArray@_K$01$0DIGBGJFG@@@QEAAPEA_KI@Z; NonPagedPoolZeroedArray<unsigned __int64,2,945908054>::AllocateElements(uint)
0x140115418  mov     edx, r12d
0x14011541b  lea     rcx, [rsp+150h+P]
0x140115420  mov     rbx, rax
0x140115423  call    ?AllocateElements@?$NonPagedPoolZeroedArray@PEAU_VIDSCH_SYNC_OBJECT@@$01$0DIGBGJFG@@@QEAAPEAPEAU_VIDSCH_SYNC_OBJECT@@I@Z; NonPagedPoolZeroedArray<_VIDSCH_SYNC_OBJECT *,2,945908054>::AllocateElements(uint)
0x140115428  xor     r11d, r11d
0x14011542b  mov     r10, rax
0x14011542e  test    rbx, rbx
0x140115431  jz      loc_14011558E
0x140115437  test    rax, rax
0x14011543a  jz      loc_14011558E
0x140115440  mov     r14d, r11d
0x140115443  mov     r8d, r11d
0x140115446  test    r12d, r12d
0x140115449  jz      short loc_14011548D
0x14011544b  mov     rsi, [rbp+50h+var_C0]
0x14011544f  mov     edx, r11d
0x140115452  mov     r15, [rbp+50h+var_B8]
0x140115456  mov     r9, [rsi+rdx*8]
0x14011545a  mov     rax, [rdi+rdx*8]
0x14011545e  cmp     rax, r9
0x140115461  ja      loc_14011557A
0x140115467  mov     ecx, r14d
0x14011546a  inc     r14d
0x14011546d  mov     [rbx+rcx*8], r9
0x140115471  mov     rax, [r15+rdx*8]
0x140115475  mov     [r10+rcx*8], rax
0x140115479  inc     r8d
0x14011547c  inc     rdx
0x14011547f  cmp     r8d, r12d
0x140115482  jb      short loc_140115456
0x140115484  mov     rsi, [rbp+50h+var_B0]
0x140115488  mov     r15b, [rsp+150h+var_100]
0x14011548d  mov     rbx, [rbp+50h+var_70]
0x140115491  mov     r13, [rsp+150h+P]
0x140115496  mov     [rsp+150h+var_F0], rbx
0x14011549b  jmp     loc_1401151DD
0x1401154a0  inc     r9d
0x1401154a3  jmp     loc_1401151E0
0x1401154a8  test    rcx, rcx
0x1401154ab  jz      loc_14011523F
0x1401154b1  xor     edx, edx; Tag
0x1401154b3  call    cs:__imp_ExFreePoolWithTag
0x1401154ba  nop     dword ptr [rax+rax+00h]
0x1401154bf  jmp     loc_14011523F
0x1401154c4  mov     rcx, rsi; Object
0x1401154c7  mov     [rsp+150h+Object], rcx
0x1401154cc  call    cs:__imp_ObfReferenceObject
0x1401154d3  nop     dword ptr [rax+rax+00h]
0x1401154d8  mov     rax, [rsp+150h+var_E8]
0x1401154dd  mov     r8, rbx
0x1401154e0  mov     r9, [rsp+150h+Object]
0x1401154e5  mov     rdx, r13
0x1401154e8  mov     [rsp+150h+var_118], 0
0x1401154f1  mov     ecx, r14d
0x1401154f4  mov     rax, [rax+10h]
0x1401154f8  mov     rax, [rax+2E8h]
0x1401154ff  mov     rax, [rax+140h]
0x140115506  mov     [rsp+150h+var_120], rax
0x14011550b  mov     byte ptr [rsp+150h+var_128], 1
0x140115510  mov     byte ptr [rsp+150h+Timeout], 0
0x140115515  call    VidSchSubmitWaitFromCpu
0x14011551a  movsxd  rdi, eax
0x14011551d  test    eax, eax
0x14011551f  js      loc_1401155D7
0x140115525  test    rsi, rsi
0x140115528  jnz     loc_1401151FC
0x14011552e  mov     rcx, [rsp+150h+Object]; Object
0x140115533  xor     r9d, r9d; Alertable
0x140115536  xor     r8d, r8d; WaitMode
0x140115539  mov     [rsp+150h+var_FF], sil
0x14011553e  xor     edx, edx; WaitReason
0x140115540  mov     [rsp+150h+Timeout], rsi; Timeout
0x140115545  call    cs:__imp_KeWaitForSingleObject
0x14011554c  nop     dword ptr [rax+rax+00h]
0x140115551  mov     edi, eax
0x140115553  jmp     loc_140115346
0x140115558  mov     rcx, [rsp+150h+Object]; Event
0x14011555d  xor     r8d, r8d; State
0x140115560  lea     edx, [r8+1]; Type
0x140115564  call    cs:__imp_KeInitializeEvent
0x14011556b  nop     dword ptr [rax+rax+00h]
0x140115570  mov     rcx, [rsp+150h+Object]
0x140115575  jmp     loc_1401154CC
0x14011557a  sub     rax, r9
0x14011557d  cmp     rax, 7FFFFFFFh
0x140115583  jnb     loc_140115479
0x140115589  jmp     loc_140115467
0x14011558e  mov     rbx, 0FFFFFFFFC0000017h
0x140115595  mov     edi, ebx
0x140115597  mov     rdx, rbx
0x14011559a  mov     ecx, 1
0x14011559f  call    cs:__imp_WdLogSingleEntry1
0x1401155a6  nop     dword ptr [rax+rax+00h]
0x1401155ab  xor     eax, eax
0x1401155ad  mov     cs:WdLogGlobalForLineNumber, 4781h
0x1401155b7  mov     [rsp+150h+var_118], rax
0x1401155bc  lea     r9, aCouldNotWaitOn_0; "Could not wait on fence array - filtere"...
0x1401155c3  mov     [rsp+150h+var_120], rax
0x1401155c8  mov     [rsp+150h+var_128], rax
0x1401155cd  mov     [rsp+150h+Timeout], rbx
0x1401155d2  jmp     loc_140115337
0x1401155d7  mov     rcx, [rsp+150h+Object]; Object
0x1401155dc  call    cs:__imp_ObfDereferenceObject
0x1401155e3  nop     dword ptr [rax+rax+00h]
0x1401155e8  mov     rdx, rdi
0x1401155eb  mov     ecx, 1
0x1401155f0  call    cs:__imp_WdLogSingleEntry1
0x1401155f7  nop     dword ptr [rax+rax+00h]
0x1401155fc  xor     eax, eax
0x1401155fe  mov     cs:WdLogGlobalForLineNumber, 47FCh
0x140115608  mov     [rsp+150h+var_118], rax
0x14011560d  lea     r9, aCouldNotWaitOn; "Could not wait on fence array - schedul"...
0x140115614  mov     [rsp+150h+var_120], rax
0x140115619  mov     [rsp+150h+var_128], rax
0x14011561e  mov     [rsp+150h+Timeout], rdi
0x140115623  jmp     loc_140115337
0x140115628  xor     r8d, r8d; Wait
0x14011562b  xor     edx, edx; Increment
0x14011562d  mov     rcx, rsi; Event
0x140115630  call    cs:__imp_KeSetEvent
0x140115637  nop     dword ptr [rax+rax+00h]
0x14011563c  jmp     loc_1401151FC
```
