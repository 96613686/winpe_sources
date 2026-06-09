# VIDMM_GLOBAL::WaitForFences(_VIDSCH_SYNC_OBJECT * *,unsigned __int64 const *,uint,unsigned __int64 const *,_KEVENT *)

- ea: `0x1401128c4`
- end: `0x140112db1`
- name: `?WaitForFences@VIDMM_GLOBAL@@QEAAXPEAPEAU_VIDSCH_SYNC_OBJECT@@PEB_KI1PEAU_KEVENT@@@Z`
- size: `1261`
- prototype: `void __fastcall(VIDMM_GLOBAL *this, struct _VIDSCH_SYNC_OBJECT **, const unsigned __int64 *, unsigned int, const unsigned __int64 *, struct _KEVENT *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x140032a04`
- `0x14003d610`
- `0x14009d4b4`
- `0x1400bb7c8`

## callees

- `0x1400045ec`
- `0x14002e8b0`
- `0x140031cb8`
- `0x140032cb8`
- `0x14003a540`
- `0x140058680`
- `0x1401128c4`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140112c3c`
- `ntoskrnl!ObfReferenceObject` at `0x140112c3c`
- `ntoskrnl!ObfDereferenceObject` at `0x140112ac0`
- `ntoskrnl!ObfDereferenceObject` at `0x140112d4c`
- `ntoskrnl!ObfDereferenceObject` at `0x140112ac0`
- `ntoskrnl!ObfDereferenceObject` at `0x140112d4c`
- `ntoskrnl!KeDelayExecutionThread` at `0x140112af8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140112af8`
- `ntoskrnl!ObCreateObject` at `0x140112a57`
- `ntoskrnl!ObCreateObject` at `0x140112a57`
- `ntoskrnl!ExEventObjectType` at `0x140112a03`
- `ntoskrnl!KeSetEvent` at `0x140112da0`
- `ntoskrnl!KeSetEvent` at `0x140112da0`
- `ntoskrnl!KeInitializeEvent` at `0x140112cd4`
- `ntoskrnl!KeInitializeEvent` at `0x140112cd4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140112cb5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140112cb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112982`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112c23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112982`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140112c23`
- `watchdog!WdLogSingleEntry1` at `0x140112a74`
- `watchdog!WdLogSingleEntry1` at `0x140112d0f`
- `watchdog!WdLogSingleEntry1` at `0x140112d60`
- `watchdog!WdLogSingleEntry1` at `0x140112a74`
- `watchdog!WdLogSingleEntry1` at `0x140112d0f`
- `watchdog!WdLogSingleEntry1` at `0x140112d60`

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
        WdLogGlobalForLineNumber = 18133;
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
        WdLogGlobalForLineNumber = 18222;
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
      WdLogGlobalForLineNumber = 18256;
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
0x1401128c4  push    rbp
0x1401128c6  push    rbx
0x1401128c7  push    rsi
0x1401128c8  push    rdi
0x1401128c9  push    r12
0x1401128cb  push    r13
0x1401128cd  push    r14
0x1401128cf  push    r15
0x1401128d1  lea     rbp, [rsp-18h]
0x1401128d6  sub     rsp, 118h
0x1401128dd  mov     rax, cs:__security_cookie
0x1401128e4  xor     rax, rsp
0x1401128e7  mov     [rbp+50h+var_50], rax
0x1401128eb  mov     rsi, [rbp+50h+arg_28]
0x1401128f2  xor     r11d, r11d
0x1401128f5  mov     rbx, r8
0x1401128f8  mov     [rbp+50h+var_B0], rsi
0x1401128fc  mov     r15b, 1
0x1401128ff  mov     [rsp+150h+Object], r11
0x140112904  mov     [rsp+150h+var_F0], rbx
0x140112909  mov     r12d, r9d
0x14011290c  mov     [rsp+150h+var_100], r15b
0x140112911  mov     rax, rcx
0x140112914  mov     [rbp+50h+var_C0], r8
0x140112918  mov     r14d, r9d
0x14011291b  mov     [rbp+50h+var_B8], rdx
0x14011291f  mov     r13, rdx
0x140112922  mov     [rsp+150h+var_E8], rcx
0x140112927  mov     [rsp+150h+var_FF], 1
0x14011292c  mov     rdi, [rbp+50h+arg_20]
0x140112933  mov     [rbp+50h+var_70], r11
0x140112937  mov     [rbp+50h+var_58], r11d
0x14011293b  mov     [rsp+150h+P], r11
0x140112940  mov     [rbp+50h+var_C8], r11d
0x140112944  test    rdi, rdi
0x140112947  jnz     loc_140112B6F
0x14011294d  mov     r9d, r11d
0x140112950  cmp     r9d, r14d
0x140112953  jb      short loc_1401129D0
0x140112955  mov     [rsp+150h+var_100], r15b
0x14011295a  test    r15b, r15b
0x14011295d  jz      loc_1401129FA
0x140112963  test    rsi, rsi
0x140112966  jnz     loc_140112D98
0x14011296c  mov     rcx, [rsp+150h+P]; P
0x140112971  lea     rax, [rsp+150h+var_D8]
0x140112976  cmp     rcx, rax
0x140112979  jz      short loc_14011298E
0x14011297b  test    rcx, rcx
0x14011297e  jz      short loc_14011298E
0x140112980  xor     edx, edx; Tag
0x140112982  call    cs:__imp_ExFreePoolWithTag
0x140112989  nop     dword ptr [rax+rax+00h]
0x14011298e  mov     rcx, [rbp+50h+var_70]; P
0x140112992  lea     rax, [rbp+50h+var_68]
0x140112996  mov     [rsp+150h+P], 0
0x14011299f  mov     [rbp+50h+var_C8], 0
0x1401129a6  cmp     rcx, rax
0x1401129a9  jnz     loc_140112C18
0x1401129af  mov     rcx, [rbp+50h+var_50]
0x1401129b3  xor     rcx, rsp; StackCookie
0x1401129b6  call    __security_check_cookie
0x1401129bb  add     rsp, 118h
0x1401129c2  pop     r15
0x1401129c4  pop     r14
0x1401129c6  pop     r13
0x1401129c8  pop     r12
0x1401129ca  pop     rdi
0x1401129cb  pop     rsi
0x1401129cc  pop     rbx
0x1401129cd  pop     rbp
0x1401129ce  retn
0x1401129d0  mov     edx, r9d
0x1401129d3  mov     rcx, [r13+rdx*8+0]
0x1401129d8  test    rcx, rcx
0x1401129db  jz      loc_140112C10
0x1401129e1  mov     rdx, [rbx+rdx*8]
0x1401129e5  call    VidSchIsMonitoredFenceSignaled
0x1401129ea  test    al, al
0x1401129ec  jnz     loc_140112C10
0x1401129f2  mov     r15b, r11b
0x1401129f5  mov     [rsp+150h+var_100], r11b
0x1401129fa  test    rsi, rsi
0x1401129fd  jnz     loc_140112C34
0x140112a03  mov     rdx, cs:ExEventObjectType
0x140112a0a  lea     rax, [rsp+150h+Object]
0x140112a0f  mov     [rsp+150h+var_110], rax
0x140112a14  lea     r8, [rbp+50h+var_A0]
0x140112a18  mov     dword ptr [rsp+150h+var_118], r11d
0x140112a1d  xorps   xmm0, xmm0
0x140112a20  mov     dword ptr [rsp+150h+var_120], r11d
0x140112a25  xor     r9d, r9d
0x140112a28  mov     rdx, [rdx]
0x140112a2b  xor     ecx, ecx
0x140112a2d  mov     dword ptr [rsp+150h+var_128], 18h
0x140112a35  mov     [rsp+150h+Timeout], r11
0x140112a3a  mov     [rbp+50h+var_A0], 30h ; '0'
0x140112a42  mov     [rbp+50h+var_88], 200h
0x140112a4a  mov     [rbp+50h+var_98], r11
0x140112a4e  mov     [rbp+50h+var_90], r11
0x140112a52  movdqu  [rbp+50h+var_80], xmm0
0x140112a57  call    cs:__imp_ObCreateObject
0x140112a5e  nop     dword ptr [rax+rax+00h]
0x140112a63  movsxd  rdi, eax
0x140112a66  test    eax, eax
0x140112a68  jns     loc_140112CC8
0x140112a6e  mov     rdx, rdi
0x140112a71  lea     ecx, [rsi+1]
0x140112a74  call    cs:__imp_WdLogSingleEntry1
0x140112a7b  nop     dword ptr [rax+rax+00h]
0x140112a80  xor     eax, eax
0x140112a82  mov     cs:WdLogGlobalForLineNumber, 472Eh
0x140112a8c  mov     [rsp+150h+var_118], rax
0x140112a91  lea     r9, aCouldNotWaitOn_1; "Could not wait on fence array - kernel "...
0x140112a98  mov     [rsp+150h+var_120], rax
0x140112a9d  mov     [rsp+150h+var_128], rax
0x140112aa2  mov     [rsp+150h+Timeout], rdi
0x140112aa7  mov     edx, 40000h
0x140112aac  call    DxgkLogInternalTriageEvent
0x140112ab1  mov     rbx, [rsp+150h+var_F0]
0x140112ab6  mov     rcx, [rsp+150h+Object]; Object
0x140112abb  test    rcx, rcx
0x140112abe  jz      short loc_140112AD5
0x140112ac0  call    cs:__imp_ObfDereferenceObject
0x140112ac7  nop     dword ptr [rax+rax+00h]
0x140112acc  mov     [rsp+150h+Object], 0
0x140112ad5  test    edi, edi
0x140112ad7  jns     loc_14011296C
0x140112add  cmp     [rsp+150h+var_FF], 0
0x140112ae2  jz      loc_14011296C
0x140112ae8  lea     r8, [rbp+50h+Interval]; Interval
0x140112aec  mov     qword ptr [rbp+50h+Interval], 0C350h
0x140112af4  xor     edx, edx; Alertable
0x140112af6  xor     ecx, ecx; WaitMode
0x140112af8  call    cs:__imp_KeDelayExecutionThread
0x140112aff  nop     dword ptr [rax+rax+00h]
0x140112b04  mov     rcx, [rsp+150h+P]; P
0x140112b09  lea     rax, [rsp+150h+var_D8]
0x140112b0e  xor     r11d, r11d
0x140112b11  cmp     rcx, rax
0x140112b14  jz      short loc_140112B2C
0x140112b16  test    rcx, rcx
0x140112b19  jz      short loc_140112B2C
0x140112b1b  xor     edx, edx; Tag
0x140112b1d  call    cs:__imp_ExFreePoolWithTag
0x140112b24  nop     dword ptr [rax+rax+00h]
0x140112b29  xor     r11d, r11d
0x140112b2c  mov     rcx, [rbp+50h+var_70]; P
0x140112b30  lea     rax, [rbp+50h+var_68]
0x140112b34  cmp     rcx, rax
0x140112b37  mov     [rsp+150h+P], r11
0x140112b3c  mov     rax, [rsp+150h+var_E8]
0x140112b41  mov     [rbp+50h+var_C8], r11d
0x140112b45  jz      loc_14011292C
0x140112b4b  test    rcx, rcx
0x140112b4e  jz      loc_14011292C
0x140112b54  xor     edx, edx; Tag
0x140112b56  call    cs:__imp_ExFreePoolWithTag
0x140112b5d  nop     dword ptr [rax+rax+00h]
0x140112b62  mov     rax, [rsp+150h+var_E8]
0x140112b67  xor     r11d, r11d
0x140112b6a  jmp     loc_14011292C
0x140112b6f  cmp     [rax+2E0h], r11b
0x140112b76  jnz     loc_14011294D
0x140112b7c  mov     edx, r12d
0x140112b7f  lea     rcx, [rbp+50h+var_70]
0x140112b83  call    ?AllocateElements@?$NonPagedPoolZeroedArray@_K$01$0DIGBGJFG@@@QEAAPEA_KI@Z; NonPagedPoolZeroedArray<unsigned __int64,2,945908054>::AllocateElements(uint)
0x140112b88  mov     edx, r12d
0x140112b8b  lea     rcx, [rsp+150h+P]
0x140112b90  mov     rbx, rax
0x140112b93  call    ?AllocateElements@?$NonPagedPoolZeroedArray@PEAU_VIDSCH_SYNC_OBJECT@@$01$0DIGBGJFG@@@QEAAPEAPEAU_VIDSCH_SYNC_OBJECT@@I@Z; NonPagedPoolZeroedArray<_VIDSCH_SYNC_OBJECT *,2,945908054>::AllocateElements(uint)
0x140112b98  xor     r11d, r11d
0x140112b9b  mov     r10, rax
0x140112b9e  test    rbx, rbx
0x140112ba1  jz      loc_140112CFE
0x140112ba7  test    rax, rax
0x140112baa  jz      loc_140112CFE
0x140112bb0  mov     r14d, r11d
0x140112bb3  mov     r8d, r11d
0x140112bb6  test    r12d, r12d
0x140112bb9  jz      short loc_140112BFD
0x140112bbb  mov     rsi, [rbp+50h+var_C0]
0x140112bbf  mov     edx, r11d
0x140112bc2  mov     r15, [rbp+50h+var_B8]
0x140112bc6  mov     r9, [rsi+rdx*8]
0x140112bca  mov     rax, [rdi+rdx*8]
0x140112bce  cmp     rax, r9
0x140112bd1  ja      loc_140112CEA
0x140112bd7  mov     ecx, r14d
0x140112bda  inc     r14d
0x140112bdd  mov     [rbx+rcx*8], r9
0x140112be1  mov     rax, [r15+rdx*8]
0x140112be5  mov     [r10+rcx*8], rax
0x140112be9  inc     r8d
0x140112bec  inc     rdx
0x140112bef  cmp     r8d, r12d
0x140112bf2  jb      short loc_140112BC6
0x140112bf4  mov     rsi, [rbp+50h+var_B0]
0x140112bf8  mov     r15b, [rsp+150h+var_100]
0x140112bfd  mov     rbx, [rbp+50h+var_70]
0x140112c01  mov     r13, [rsp+150h+P]
0x140112c06  mov     [rsp+150h+var_F0], rbx
0x140112c0b  jmp     loc_14011294D
0x140112c10  inc     r9d
0x140112c13  jmp     loc_140112950
0x140112c18  test    rcx, rcx
0x140112c1b  jz      loc_1401129AF
0x140112c21  xor     edx, edx; Tag
0x140112c23  call    cs:__imp_ExFreePoolWithTag
0x140112c2a  nop     dword ptr [rax+rax+00h]
0x140112c2f  jmp     loc_1401129AF
0x140112c34  mov     rcx, rsi; Object
0x140112c37  mov     [rsp+150h+Object], rcx
0x140112c3c  call    cs:__imp_ObfReferenceObject
0x140112c43  nop     dword ptr [rax+rax+00h]
0x140112c48  mov     rax, [rsp+150h+var_E8]
0x140112c4d  mov     r8, rbx
0x140112c50  mov     r9, [rsp+150h+Object]
0x140112c55  mov     rdx, r13
0x140112c58  mov     [rsp+150h+var_118], 0
0x140112c61  mov     ecx, r14d
0x140112c64  mov     rax, [rax+10h]
0x140112c68  mov     rax, [rax+2E8h]
0x140112c6f  mov     rax, [rax+140h]
0x140112c76  mov     [rsp+150h+var_120], rax
0x140112c7b  mov     byte ptr [rsp+150h+var_128], 1
0x140112c80  mov     byte ptr [rsp+150h+Timeout], 0
0x140112c85  call    VidSchSubmitWaitFromCpu
0x140112c8a  movsxd  rdi, eax
0x140112c8d  test    eax, eax
0x140112c8f  js      loc_140112D47
0x140112c95  test    rsi, rsi
0x140112c98  jnz     loc_14011296C
0x140112c9e  mov     rcx, [rsp+150h+Object]; Object
0x140112ca3  xor     r9d, r9d; Alertable
0x140112ca6  xor     r8d, r8d; WaitMode
0x140112ca9  mov     [rsp+150h+var_FF], sil
0x140112cae  xor     edx, edx; WaitReason
0x140112cb0  mov     [rsp+150h+Timeout], rsi; Timeout
0x140112cb5  call    cs:__imp_KeWaitForSingleObject
0x140112cbc  nop     dword ptr [rax+rax+00h]
0x140112cc1  mov     edi, eax
0x140112cc3  jmp     loc_140112AB6
0x140112cc8  mov     rcx, [rsp+150h+Object]; Event
0x140112ccd  xor     r8d, r8d; State
0x140112cd0  lea     edx, [r8+1]; Type
0x140112cd4  call    cs:__imp_KeInitializeEvent
0x140112cdb  nop     dword ptr [rax+rax+00h]
0x140112ce0  mov     rcx, [rsp+150h+Object]
0x140112ce5  jmp     loc_140112C3C
0x140112cea  sub     rax, r9
0x140112ced  cmp     rax, 7FFFFFFFh
0x140112cf3  jnb     loc_140112BE9
0x140112cf9  jmp     loc_140112BD7
0x140112cfe  mov     rbx, 0FFFFFFFFC0000017h
0x140112d05  mov     edi, ebx
0x140112d07  mov     rdx, rbx
0x140112d0a  mov     ecx, 1
0x140112d0f  call    cs:__imp_WdLogSingleEntry1
0x140112d16  nop     dword ptr [rax+rax+00h]
0x140112d1b  xor     eax, eax
0x140112d1d  mov     cs:WdLogGlobalForLineNumber, 46D5h
0x140112d27  mov     [rsp+150h+var_118], rax
0x140112d2c  lea     r9, aCouldNotWaitOn_0; "Could not wait on fence array - filtere"...
0x140112d33  mov     [rsp+150h+var_120], rax
0x140112d38  mov     [rsp+150h+var_128], rax
0x140112d3d  mov     [rsp+150h+Timeout], rbx
0x140112d42  jmp     loc_140112AA7
0x140112d47  mov     rcx, [rsp+150h+Object]; Object
0x140112d4c  call    cs:__imp_ObfDereferenceObject
0x140112d53  nop     dword ptr [rax+rax+00h]
0x140112d58  mov     rdx, rdi
0x140112d5b  mov     ecx, 1
0x140112d60  call    cs:__imp_WdLogSingleEntry1
0x140112d67  nop     dword ptr [rax+rax+00h]
0x140112d6c  xor     eax, eax
0x140112d6e  mov     cs:WdLogGlobalForLineNumber, 4750h
0x140112d78  mov     [rsp+150h+var_118], rax
0x140112d7d  lea     r9, aCouldNotWaitOn; "Could not wait on fence array - schedul"...
0x140112d84  mov     [rsp+150h+var_120], rax
0x140112d89  mov     [rsp+150h+var_128], rax
0x140112d8e  mov     [rsp+150h+Timeout], rdi
0x140112d93  jmp     loc_140112AA7
0x140112d98  xor     r8d, r8d; Wait
0x140112d9b  xor     edx, edx; Increment
0x140112d9d  mov     rcx, rsi; Event
0x140112da0  call    cs:__imp_KeSetEvent
0x140112da7  nop     dword ptr [rax+rax+00h]
0x140112dac  jmp     loc_14011296C
```
