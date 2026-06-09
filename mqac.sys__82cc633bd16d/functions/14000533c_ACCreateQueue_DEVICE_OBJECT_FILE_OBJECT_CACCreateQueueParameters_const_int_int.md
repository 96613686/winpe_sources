# ACCreateQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,CACCreateQueueParameters const *,int,int)

- ea: `0x14000533c`
- end: `0x1400057ec`
- name: `?ACCreateQueue@@YAJPEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@PEBVCACCreateQueueParameters@@HH@Z`
- size: `1200`
- prototype: `int(struct _DEVICE_OBJECT *, struct _FILE_OBJECT *, const struct CACCreateQueueParameters *, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14000a3b0`
- `0x14001cf7c`

## callees

- `0x140001010`
- `0x140001128`
- `0x140001c04`
- `0x14000533c`
- `0x140007684`
- `0x14000a104`
- `0x14000b9b4`
- `0x14001c530`
- `0x14002186c`
- `0x14002479c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140005384`
- `ntoskrnl!ProbeForRead` at `0x1400053c1`
- `ntoskrnl!ProbeForRead` at `0x1400053da`
- `ntoskrnl!ProbeForRead` at `0x1400053fc`
- `ntoskrnl!ProbeForRead` at `0x140005384`
- `ntoskrnl!ProbeForRead` at `0x1400053c1`
- `ntoskrnl!ProbeForRead` at `0x1400053da`
- `ntoskrnl!ProbeForRead` at `0x1400053fc`

## pseudocode

```c
__int64 __fastcall ACCreateQueue(
        struct _DEVICE_OBJECT *a1,
        struct _FILE_OBJECT *a2,
        const struct CACCreateQueueParameters *a3,
        int a4,
        int a5)
{
  struct QUEUE_FORMAT *v8; // rsi
  PVOID DeviceExtension; // r12
  void *v10; // rbx
  volatile void *v11; // rsi
  struct _GUID *v12; // rbx
  volatile void *v13; // rbx
  struct QueueCounters *v14; // rax
  CQueue *v15; // r10
  CQueue *v16; // rbx
  struct QueueCounters *v17; // rax
  CQueue *v18; // r10
  __int64 v19; // rax
  unsigned __int8 v21; // dl
  char v22; // r8
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  bool v28; // zf
  bool v29; // al
  struct _GUID v30; // [rsp+60h] [rbp-38h] BYREF
  struct QUEUE_FORMAT *v31; // [rsp+A0h] [rbp+8h] BYREF
  int v32; // [rsp+B8h] [rbp+20h]

  v32 = a4;
  v8 = 0;
  v31 = 0;
  DeviceExtension = a1->DeviceExtension;
  if ( !a5 )
  {
    if ( operator new(0x180u, 0x40u, 0x5141514Du, LowPoolPriority) )
    {
      v17 = (struct QueueCounters *)MapQM2ACQueueCounters(DeviceExtension, *((_QWORD *)a3 + 3));
      v16 = CQueue::CQueue(
              v18,
              a1,
              a2,
              0,
              0,
              *(_DWORD *)a3,
              *((const struct _GUID **)a3 + 1),
              *((const struct QUEUE_FORMAT **)a3 + 2),
              v17,
              *((_QWORD *)a3 + 4),
              *((_DWORD *)a3 + 10),
              *((const struct CSenderStream **)a3 + 6));
      goto LABEL_8;
    }
LABEL_7:
    v16 = 0;
    goto LABEL_8;
  }
  ProbeForRead(a3, 0x38u, 1u);
  v10 = (void *)*((_QWORD *)a3 + 2);
  ACProbeArrayElementsForRead(v10, 0x20u, 1u);
  ACDeepCopyQueueFormat((struct QUEUE_FORMAT *)v10, 1u, &v31);
  v11 = (volatile void *)*((_QWORD *)a3 + 3);
  ProbeForRead(v11, 0x10u, 1u);
  v12 = (struct _GUID *)*((_QWORD *)a3 + 1);
  ProbeForRead(v12, 0x10u, 1u);
  v30 = *v12;
  v13 = (volatile void *)*((_QWORD *)a3 + 6);
  ProbeForRead(v13, 0x38u, 1u);
  if ( !operator new(0x180u, 0x40u, 0x5141514Du, LowPoolPriority) )
  {
    v8 = v31;
    goto LABEL_7;
  }
  v14 = (struct QueueCounters *)MapQM2ACQueueCounters(DeviceExtension, v11);
  v8 = v31;
  v16 = CQueue::CQueue(
          v15,
          a1,
          a2,
          0,
          0,
          *(_DWORD *)a3,
          &v30,
          v31,
          v14,
          *((_QWORD *)a3 + 4),
          *((_DWORD *)a3 + 10),
          (const struct CSenderStream *)v13);
LABEL_8:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    if ( v16 )
      v19 = *((_QWORD *)v16 + 19);
    else
      v19 = 0;
    WPP_SF_qq(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 187, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v16, v19);
  }
  if ( !v16
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 188, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  a2->FsContext = v16;
  if ( !v32 )
  {
    *((_DWORD *)a2->FsContext2 + 5) |= 1u;
    *((_DWORD *)a2->FsContext2 + 5) |= 4u;
    *((_DWORD *)a2->FsContext2 + 5) &= ~2u;
  }
  if ( !v16 )
  {
    if ( v8 )
      ACFreeDeepCopyQueueFormat(v8, 1u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 189, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
    }
    return 3221225626LL;
  }
  v21 = *((_BYTE *)v16 + 88);
  if ( v21 > 8u )
    goto LABEL_63;
  v22 = *((_BYTE *)v16 + 89);
  v23 = v22 & 0xF;
  if ( v23 > 5 || !v21 || v21 == 3 && !*((_QWORD *)v16 + 12) )
    goto LABEL_63;
  if ( v21 == 8 && !*((_QWORD *)v16 + 12) )
    goto LABEL_63;
  if ( (*((_BYTE *)v16 + 89) & 0xF) != 0 )
  {
    v24 = v23 - 1;
    if ( !v24 )
    {
      v29 = (unsigned __int8)(v21 - 5) > 2u;
      goto LABEL_46;
    }
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( !v27 )
        {
          v28 = v21 == 5;
          goto LABEL_42;
        }
        if ( v27 == 1 )
        {
          v28 = v21 == 8;
LABEL_42:
          v29 = v28;
          goto LABEL_46;
        }
        goto LABEL_45;
      }
    }
    if ( v21 != 4 && v22 >= 0 )
    {
LABEL_45:
      v29 = 0;
      goto LABEL_46;
    }
  }
  else if ( v21 == 4 || v22 < 0 )
  {
    goto LABEL_45;
  }
  v29 = 1;
LABEL_46:
  if ( v29 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)a3 + 2) + 1LL) & 0xF) == 5 || !*(_DWORD *)a3 || *((_QWORD *)v16 + 19) )
    {
      if ( v8 )
        ACFreeDeepCopyQueueFormat(v8, 1u);
      return 0;
    }
    else
    {
      if ( v8 )
        ACFreeDeepCopyQueueFormat(v8, 1u);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 191, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
      }
      return 3221225626LL;
    }
  }
LABEL_63:
  if ( v8 )
    ACFreeDeepCopyQueueFormat(v8, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 190, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000533c  mov     rax, rsp
0x14000533f  mov     [rax+10h], rbx
0x140005343  mov     [rax+18h], rsi
0x140005347  mov     [rax+20h], r9d
0x14000534b  push    rdi
0x14000534c  push    r12
0x14000534e  push    r13
0x140005350  push    r14
0x140005352  push    r15
0x140005354  sub     rsp, 70h
0x140005358  mov     r14, r8
0x14000535b  mov     r15, rdx
0x14000535e  mov     r13, rcx
0x140005361  xor     esi, esi
0x140005363  mov     [rax+8], rsi
0x140005367  mov     r12, [rcx+40h]
0x14000536b  cmp     [rsp+98h+arg_20], esi
0x140005372  jz      loc_140005498
0x140005378  lea     edi, [rsi+1]
0x14000537b  mov     r8d, edi; Alignment
0x14000537e  lea     edx, [rsi+38h]; Length
0x140005381  mov     rcx, r14; Address
0x140005384  call    cs:__imp_ProbeForRead
0x14000538b  nop     dword ptr [rax+rax+00h]
0x140005390  mov     rbx, [r14+10h]
0x140005394  mov     r8d, edi; unsigned int
0x140005397  lea     edx, [rsi+20h]; unsigned int
0x14000539a  mov     rcx, rbx; void *
0x14000539d  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x1400053a2  lea     r8, [rsp+98h+arg_0]; struct QUEUE_FORMAT **
0x1400053aa  mov     edx, edi; unsigned int
0x1400053ac  mov     rcx, rbx; struct QUEUE_FORMAT *
0x1400053af  call    ?ACDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@KPEAPEAU1@@Z; ACDeepCopyQueueFormat(QUEUE_FORMAT *,ulong,QUEUE_FORMAT * *)
0x1400053b4  mov     rsi, [r14+18h]
0x1400053b8  mov     r8d, edi; Alignment
0x1400053bb  lea     edx, [rdi+0Fh]; Length
0x1400053be  mov     rcx, rsi; Address
0x1400053c1  call    cs:__imp_ProbeForRead
0x1400053c8  nop     dword ptr [rax+rax+00h]
0x1400053cd  mov     rbx, [r14+8]
0x1400053d1  mov     r8d, edi; Alignment
0x1400053d4  lea     edx, [rdi+0Fh]; Length
0x1400053d7  mov     rcx, rbx; Address
0x1400053da  call    cs:__imp_ProbeForRead
0x1400053e1  nop     dword ptr [rax+rax+00h]
0x1400053e6  movups  xmm0, xmmword ptr [rbx]
0x1400053e9  movdqu  xmmword ptr [rsp+98h+var_38.Data1], xmm0
0x1400053ef  mov     rbx, [r14+30h]
0x1400053f3  mov     r8d, edi; Alignment
0x1400053f6  lea     edx, [rdi+37h]; Length
0x1400053f9  mov     rcx, rbx; Address
0x1400053fc  call    cs:__imp_ProbeForRead
0x140005403  nop     dword ptr [rax+rax+00h]
0x140005408  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000540b  lea     edx, [rdi+3Fh]; unsigned __int64
0x14000540e  mov     ecx, 180h; unsigned __int64
0x140005413  mov     r8d, 5141514Dh; unsigned int
0x140005419  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000541e  mov     r10, rax
0x140005421  test    rax, rax
0x140005424  jz      short loc_14000548B
0x140005426  mov     rdx, rsi
0x140005429  mov     rcx, r12
0x14000542c  call    MapQM2ACQueueCounters
0x140005431  mov     [rsp+98h+var_40], rbx; struct CSenderStream *
0x140005436  mov     ecx, [r14+28h]
0x14000543a  mov     [rsp+98h+var_48], ecx; unsigned int
0x14000543e  mov     rcx, [r14+20h]
0x140005442  mov     [rsp+98h+var_50], rcx; __int64
0x140005447  mov     [rsp+98h+var_58], rax; struct QueueCounters *
0x14000544c  mov     rsi, [rsp+98h+arg_0]
0x140005454  mov     [rsp+98h+var_60], rsi; struct QUEUE_FORMAT *
0x140005459  lea     rax, [rsp+98h+var_38]
0x14000545e  mov     [rsp+98h+var_68], rax; struct _GUID *
0x140005463  mov     eax, [r14]
0x140005466  mov     [rsp+98h+var_70], eax; int
0x14000546a  mov     [rsp+98h+var_78], 0; unsigned int
0x140005472  xor     r9d, r9d; unsigned int
0x140005475  mov     r8, r15; struct _FILE_OBJECT *
0x140005478  mov     rdx, r13; struct _DEVICE_OBJECT *
0x14000547b  mov     rcx, r10; this
0x14000547e  call    ??0CQueue@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@KKHPEBU_GUID@@PEBUQUEUE_FORMAT@@PEAUQueueCounters@@_JKPEBVCSenderStream@@@Z; CQueue::CQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,ulong,ulong,int,_GUID const *,QUEUE_FORMAT const *,QueueCounters *,__int64,ulong,CSenderStream const *)
0x140005483  mov     rbx, rax
0x140005486  jmp     loc_140005525
0x14000548b  mov     rsi, [rsp+98h+arg_0]
0x140005493  jmp     loc_140005523
0x140005498  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000549b  lea     edx, [r9+40h]; unsigned __int64
0x14000549f  mov     ecx, 180h; unsigned __int64
0x1400054a4  mov     r8d, 5141514Dh; unsigned int
0x1400054aa  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x1400054af  mov     r10, rax
0x1400054b2  test    rax, rax
0x1400054b5  jz      short loc_14000551E
0x1400054b7  mov     rdx, [r14+18h]
0x1400054bb  mov     rcx, r12
0x1400054be  call    MapQM2ACQueueCounters
0x1400054c3  mov     rcx, [r14+30h]
0x1400054c7  mov     [rsp+98h+var_40], rcx; struct CSenderStream *
0x1400054cc  mov     ecx, [r14+28h]
0x1400054d0  mov     [rsp+98h+var_48], ecx; unsigned int
0x1400054d4  mov     rcx, [r14+20h]
0x1400054d8  mov     [rsp+98h+var_50], rcx; __int64
0x1400054dd  mov     [rsp+98h+var_58], rax; struct QueueCounters *
0x1400054e2  mov     rax, [r14+10h]
0x1400054e6  mov     [rsp+98h+var_60], rax; struct QUEUE_FORMAT *
0x1400054eb  mov     rax, [r14+8]
0x1400054ef  mov     [rsp+98h+var_68], rax; struct _GUID *
0x1400054f4  mov     eax, [r14]
0x1400054f7  mov     [rsp+98h+var_70], eax; int
0x1400054fb  mov     [rsp+98h+var_78], 0; unsigned int
0x140005503  xor     r9d, r9d; unsigned int
0x140005506  mov     r8, r15; struct _FILE_OBJECT *
0x140005509  mov     rdx, r13; struct _DEVICE_OBJECT *
0x14000550c  mov     rcx, r10; this
0x14000550f  call    ??0CQueue@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@KKHPEBU_GUID@@PEBUQUEUE_FORMAT@@PEAUQueueCounters@@_JKPEBVCSenderStream@@@Z; CQueue::CQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,ulong,ulong,int,_GUID const *,QUEUE_FORMAT const *,QueueCounters *,__int64,ulong,CSenderStream const *)
0x140005514  mov     rbx, rax
0x140005517  mov     edi, 1
0x14000551c  jmp     short loc_140005525
0x14000551e  mov     edi, 1
0x140005523  xor     ebx, ebx
0x140005525  lea     r12, WPP_GLOBAL_Control
0x14000552c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005533  cmp     rcx, r12
0x140005536  jz      short loc_14000556C
0x140005538  mov     eax, [rcx+6Ch]
0x14000553b  test    al, 4
0x14000553d  jz      short loc_14000556C
0x14000553f  test    rbx, rbx
0x140005542  jz      short loc_14000554D
0x140005544  mov     rax, [rbx+98h]
0x14000554b  jmp     short loc_14000554F
0x14000554d  xor     eax, eax
0x14000554f  mov     edx, 0BBh
0x140005554  mov     qword ptr [rsp+98h+var_78], rax
0x140005559  mov     r9, rbx
0x14000555c  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005563  mov     rcx, [rcx+58h]
0x140005567  call    WPP_SF_qq
0x14000556c  test    rbx, rbx
0x14000556f  jnz     short loc_14000559A
0x140005571  mov     rcx, cs:WPP_GLOBAL_Control
0x140005578  cmp     rcx, r12
0x14000557b  jz      short loc_14000559A
0x14000557d  mov     eax, [rcx+6Ch]
0x140005580  test    dil, al
0x140005583  jz      short loc_14000559A
0x140005585  mov     edx, 0BCh
0x14000558a  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005591  mov     rcx, [rcx+58h]
0x140005595  call    WPP_SF_
0x14000559a  mov     [r15+18h], rbx
0x14000559e  cmp     [rsp+98h+arg_18], 0
0x1400055a6  jnz     short loc_1400055BF
0x1400055a8  mov     rax, [r15+20h]
0x1400055ac  or      [rax+14h], edi
0x1400055af  mov     rax, [r15+20h]
0x1400055b3  or      dword ptr [rax+14h], 4
0x1400055b7  mov     rax, [r15+20h]
0x1400055bb  and     dword ptr [rax+14h], 0FFFFFFFDh
0x1400055bf  test    rbx, rbx
0x1400055c2  jnz     short loc_140005606
0x1400055c4  test    rsi, rsi
0x1400055c7  jz      short loc_1400055D3
0x1400055c9  mov     edx, edi; unsigned int
0x1400055cb  mov     rcx, rsi; struct QUEUE_FORMAT *
0x1400055ce  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x1400055d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055da  cmp     rcx, r12
0x1400055dd  jz      short loc_1400055FC
0x1400055df  mov     eax, [rcx+6Ch]
0x1400055e2  test    dil, al
0x1400055e5  jz      short loc_1400055FC
0x1400055e7  mov     edx, 0BDh
0x1400055ec  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400055f3  mov     rcx, [rcx+58h]
0x1400055f7  call    WPP_SF_
0x1400055fc  mov     eax, 0C000009Ah
0x140005601  jmp     loc_1400057D1
0x140005606  mov     dl, [rbx+58h]
0x140005609  mov     r9b, 8
0x14000560c  cmp     dl, r9b
0x14000560f  ja      loc_14000573E
0x140005615  movzx   r8d, byte ptr [rbx+59h]
0x14000561a  mov     ecx, r8d
0x14000561d  and     ecx, 0Fh
0x140005620  cmp     ecx, 5
0x140005623  ja      loc_14000573E
0x140005629  test    dl, dl
0x14000562b  jz      loc_14000573E
0x140005631  cmp     dl, 3
0x140005634  jnz     short loc_140005641
0x140005636  cmp     qword ptr [rbx+60h], 0
0x14000563b  jz      loc_14000573E
0x140005641  cmp     dl, r9b
0x140005644  jnz     short loc_140005651
0x140005646  cmp     qword ptr [rbx+60h], 0
0x14000564b  jz      loc_14000573E
0x140005651  test    ecx, ecx
0x140005653  jz      loc_140005724
0x140005659  sub     ecx, 1
0x14000565c  jz      loc_140005716
0x140005662  sub     ecx, 1
0x140005665  jz      short loc_140005683
0x140005667  sub     ecx, 1
0x14000566a  jz      short loc_140005683
0x14000566c  sub     ecx, 1
0x14000566f  jz      short loc_14000567B
0x140005671  cmp     ecx, 1
0x140005674  jnz     short loc_140005695
0x140005676  cmp     dl, r9b
0x140005679  jmp     short loc_14000567E
0x14000567b  cmp     dl, 5
0x14000567e  setz    al
0x140005681  jmp     short loc_140005697
0x140005683  cmp     dl, 4
0x140005686  jz      loc_140005736
0x14000568c  test    r8b, r8b
0x14000568f  js      loc_140005736
0x140005695  xor     al, al
0x140005697  test    al, al
0x140005699  jz      loc_14000573E
0x14000569f  mov     rax, [r14+10h]
0x1400056a3  mov     cl, [rax+1]
0x1400056a6  and     cl, 0Fh
0x1400056a9  cmp     cl, 5
0x1400056ac  jz      short loc_140005700
0x1400056ae  cmp     dword ptr [r14], 0
0x1400056b2  jz      short loc_140005700
0x1400056b4  cmp     qword ptr [rbx+98h], 0
0x1400056bc  jnz     short loc_140005700
0x1400056be  test    rsi, rsi
0x1400056c1  jz      short loc_1400056CD
0x1400056c3  mov     edx, edi; unsigned int
0x1400056c5  mov     rcx, rsi; struct QUEUE_FORMAT *
0x1400056c8  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x1400056cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400056d4  cmp     rcx, r12
0x1400056d7  jz      short loc_1400056F6
0x1400056d9  mov     eax, [rcx+6Ch]
0x1400056dc  test    dil, al
0x1400056df  jz      short loc_1400056F6
0x1400056e1  mov     edx, 0BFh
0x1400056e6  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400056ed  mov     rcx, [rcx+58h]
0x1400056f1  call    WPP_SF_
0x1400056f6  mov     eax, 0C000009Ah
0x1400056fb  jmp     loc_1400057D1
0x140005700  test    rsi, rsi
0x140005703  jz      short loc_14000570F
0x140005705  mov     edx, edi; unsigned int
0x140005707  mov     rcx, rsi; struct QUEUE_FORMAT *
0x14000570a  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x14000570f  xor     eax, eax
0x140005711  jmp     loc_1400057D1
0x140005716  sub     dl, 5
0x140005719  cmp     dl, 2
0x14000571c  setnbe  al
0x14000571f  jmp     loc_140005697
0x140005724  cmp     dl, 4
0x140005727  jz      loc_140005695
0x14000572d  test    r8b, r8b
0x140005730  js      loc_140005695
0x140005736  mov     al, dil
0x140005739  jmp     loc_140005697
0x14000573e  test    rsi, rsi
0x140005741  jz      short loc_14000574D
0x140005743  mov     edx, edi; unsigned int
0x140005745  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140005748  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x14000574d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005754  cmp     rcx, r12
0x140005757  jz      short loc_140005776
0x140005759  mov     eax, [rcx+6Ch]
0x14000575c  test    dil, al
0x14000575f  jz      short loc_140005776
0x140005761  mov     edx, 0BEh
0x140005766  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000576d  mov     rcx, [rcx+58h]
0x140005771  call    WPP_SF_
0x140005776  mov     eax, 0C000009Ah
0x14000577b  jmp     short loc_1400057D1
0x14000577d  mov     edi, eax
0x14000577f  mov     rbx, [rsp+98h+arg_0]
0x140005787  test    rbx, rbx
0x14000578a  jz      short loc_140005799
0x14000578c  mov     edx, 1; unsigned int
0x140005791  mov     rcx, rbx; struct QUEUE_FORMAT *
0x140005794  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005799  lea     rax, WPP_GLOBAL_Control
0x1400057a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057a7  cmp     rcx, rax
0x1400057aa  jz      short loc_1400057CF
0x1400057ac  mov     eax, [rcx+6Ch]
0x1400057af  test    al, 1
0x1400057b1  jz      short loc_1400057CF
0x1400057b3  mov     edx, 0C0h
0x1400057b8  mov     [rsp+98h+var_78], edi
0x1400057bc  mov     r9, rbx
0x1400057bf  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
  ... truncated ...
```
