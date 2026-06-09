# HsmFltProcessRetrieveProperties

- ea: `0x14005062c`
- end: `0x140050c9a`
- name: `HsmFltProcessRetrieveProperties`
- size: `1646`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, PFLT_CALLBACK_DATA CallbackData, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14004ded0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000caf0`
- `0x14000db8c`
- `0x140037010`
- `0x14004a1e8`
- `0x14004c69c`
- `0x14005062c`
- `0x140058cbc`
- `0x14005cf90`
- `0x14005f078`

## import_xrefs

- `ntoskrnl!RtlCrc32` at `0x140050bcd`
- `ntoskrnl!RtlCrc32` at `0x140050bcd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050ab8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050ab8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050aac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050aac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050aea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050aea`
- `ntoskrnl!ExAllocatePool2` at `0x1400508d9`
- `ntoskrnl!ExAllocatePool2` at `0x14005091c`
- `ntoskrnl!ExAllocatePool2` at `0x1400508d9`
- `ntoskrnl!ExAllocatePool2` at `0x14005091c`
- `FLTMGR!FltIs32bitProcess` at `0x140050bb2`
- `FLTMGR!FltIs32bitProcess` at `0x140050bb2`
- `FLTMGR!FltReadFile` at `0x140050a26`
- `FLTMGR!FltReadFile` at `0x140050a26`

## pseudocode

```c
__int64 __fastcall HsmFltProcessRetrieveProperties(
        _DWORD *a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a9,
        unsigned int a10,
        unsigned int a11,
        struct _FILE_OBJECT *a12)
{
  void *v14; // r15
  __int64 Pool2; // r14
  PDEVICE_OBJECT v16; // r8
  int v17; // ebx
  __int64 v18; // rcx
  __int64 StreamSize; // r11
  int v20; // r10d
  unsigned int v21; // ecx
  unsigned int v22; // r8d
  __int64 v23; // r12
  int PropertyStream; // ebx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  unsigned int v27; // r13d
  __int64 v28; // r15
  unsigned int v29; // eax
  unsigned int v30; // esi
  __int64 *v31; // r8
  __int64 *i; // rax
  unsigned int v33; // edx
  unsigned int v34; // eax
  void *Buffer; // rbx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rsi
  int v39; // edx
  __int64 *v40; // r13
  __int64 v41; // r10
  __int64 *v42; // rcx
  __int64 *j; // rax
  size_t v44; // r14
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v48; // rbx
  _DWORD *v49; // r13
  void *v50; // r12
  unsigned __int64 v51; // rbx
  int v52; // eax
  ULONG BytesRead; // [rsp+60h] [rbp-68h] BYREF
  __int64 v54; // [rsp+68h] [rbp-60h]
  void *v55; // [rsp+70h] [rbp-58h]
  _DWORD *v56; // [rsp+78h] [rbp-50h]
  union _LARGE_INTEGER ByteOffset; // [rsp+80h] [rbp-48h] BYREF
  __int64 v58; // [rsp+88h] [rbp-40h]
  PFLT_INSTANCE InitiatingInstance; // [rsp+90h] [rbp-38h]
  __int64 v60; // [rsp+98h] [rbp-30h]
  _DWORD *v61; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v62; // [rsp+D8h] [rbp+10h]

  v62 = a2;
  v61 = a1;
  InitiatingInstance = *(PFLT_INSTANCE *)(a2 + 32);
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  v14 = 0;
  v55 = 0;
  Pool2 = 0;
  v56 = 0;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    if ( a4 )
      v17 = *(_DWORD *)(a4 + 40);
    else
      v17 = 0;
    v18 = a5;
    if ( a5 )
      StreamSize = HsmpGetStreamSize(a5);
    else
      StreamSize = 0;
    if ( v18 )
      v20 = *(_DWORD *)(v18 + 28);
    else
      v20 = 0;
    WPP_SF_qqLiqLiqq(v16->AttachedDevice, 32, v16, a2, v18, v20, StreamSize, a4, v17, a7, a3, CallbackData);
  }
  v21 = *(_DWORD *)(a9 + 16);
  if ( v21 < 0x20 || v21 > a10 || (v22 = *(_DWORD *)(a9 + 20)) == 0 || (a10 - v21) / v22 < 0x18 || a11 < a10 )
  {
    PropertyStream = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    v23 = a6;
    goto LABEL_90;
  }
  v23 = a6;
  PropertyStream = HsmpLoadPropertyStream(a2, a5, a3, a6, 0);
  HsmDbgBreakOnStatus((unsigned int)PropertyStream);
  if ( PropertyStream < 0 )
  {
LABEL_90:
    v46 = 0;
    goto LABEL_66;
  }
  v25 = *(_QWORD *)(v23 + 224);
  v54 = v25;
  v60 = v25;
  a12 = a3;
  v26 = 0;
  v27 = 0;
  v28 = a9 + *(unsigned int *)(a9 + 16);
  v29 = *(_DWORD *)(a9 + 20);
  LODWORD(v61) = v29;
  while ( (unsigned int)Pool2 < v29 )
  {
    v58 = 3 * Pool2;
    v30 = *(_DWORD *)(v28 + 24 * Pool2);
    if ( v30 )
    {
      if ( (unsigned __int8)HsmiDoesBlobOperationConflictWithExistingLocks(v25, &a12, v30, 0) )
      {
        PropertyStream = -1073688806;
        HsmDbgBreakOnStatus(3221278490LL);
        Pool2 = 0;
        v14 = 0;
        goto LABEL_65;
      }
      v31 = 0;
      for ( i = *(__int64 **)(v54 + 64); i != (__int64 *)(v54 + 64); i = (__int64 *)*i )
      {
        v31 = i;
        if ( *((_DWORD *)i + 4) == v30 )
          break;
      }
      if ( !v31 )
        goto LABEL_35;
      v33 = *(_DWORD *)((_BYTE *)v31 + (*((_BYTE *)v31 + 27) != 0 ? 4 : 0) + 24) & 0xFFFFFF;
      if ( v33 > *(_DWORD *)(v28 + 8 * v58 + 4) )
        goto LABEL_35;
      v34 = v31[3] & 0xFFFFFF;
      if ( v34 <= v26 )
        v34 = v26;
      v26 = v34;
      if ( *((_BYTE *)v31 + 27) )
      {
        v25 = v54;
        if ( (unsigned __int64)v33 + 4 > v27 )
          v27 = v33 + 4;
      }
      else
      {
LABEL_35:
        v25 = v54;
      }
    }
    Pool2 = (unsigned int)(Pool2 + 1);
    v29 = (unsigned int)v61;
  }
  if ( v26 )
  {
    Buffer = (void *)ExAllocatePool2(256, v26, 1917875016);
    v55 = Buffer;
    if ( !Buffer )
    {
      PropertyStream = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      Pool2 = 0;
      goto LABEL_64;
    }
  }
  else
  {
    Buffer = 0;
  }
  if ( v27 )
  {
    Pool2 = ExAllocatePool2(256, v27, 1917875016);
    v56 = (_DWORD *)Pool2;
    if ( !Pool2 )
    {
      PropertyStream = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      goto LABEL_64;
    }
  }
  v36 = 0;
  v37 = a9;
  while ( 1 )
  {
    LODWORD(a12) = v36;
    if ( (unsigned int)v36 >= *(_DWORD *)(v37 + 20) )
    {
      CallbackData->IoStatus.Information = a10;
      PropertyStream = 0;
      goto LABEL_63;
    }
    v38 = 3 * v36;
    v39 = *(_DWORD *)(v28 + 24 * v36);
    if ( v39 )
      break;
LABEL_87:
    v36 = (unsigned int)((_DWORD)a12 + 1);
    Buffer = v55;
  }
  v40 = 0;
  v41 = v54;
  v42 = (__int64 *)(v54 + 64);
  for ( j = *(__int64 **)(v54 + 64); j != v42; j = (__int64 *)*j )
  {
    v40 = j;
    if ( *((_DWORD *)j + 4) == v39 )
      break;
  }
  if ( j == v42 )
    goto LABEL_85;
  v44 = v40[3] & 0xFFFFFF;
  if ( (v40[3] & 0xFFFFFF) == 0 )
    goto LABEL_85;
  v61 = (_DWORD *)v40 + 7;
  if ( *((_BYTE *)v40 + 27) )
    v44 = *((_DWORD *)v40 + 7) & 0xFFFFFF;
  *(_DWORD *)(v28 + 8 * v38 + 16) = v44;
  if ( (unsigned int)v44 > *(_DWORD *)(v28 + 8 * v38 + 4) )
  {
    *(_DWORD *)(v28 + 8 * v38 + 20) = -2147483643;
LABEL_86:
    v37 = a9;
    goto LABEL_87;
  }
  ByteOffset.QuadPart = *((unsigned int *)v40 + 5) + 8LL;
  PropertyStream = FltReadFile(
                     InitiatingInstance,
                     *(PFILE_OBJECT *)(v41 + 24),
                     &ByteOffset,
                     v40[3] & 0xFFFFFF,
                     Buffer,
                     0,
                     &BytesRead,
                     0,
                     0);
  HsmDbgBreakOnStatus((unsigned int)PropertyStream);
  if ( PropertyStream >= 0 )
  {
    if ( !*((_BYTE *)v40 + 27) )
    {
      v50 = v55;
      v49 = v61;
      goto LABEL_79;
    }
    LODWORD(v61) = 0;
    LOBYTE(v45) = *((_BYTE *)v40 + 31);
    v48 = (unsigned int)HsmiDecompressBuffer(
                          HIBYTE(*((_DWORD *)v40 + 6)),
                          v45,
                          (__int64)v56,
                          (int)v44 + 4,
                          (__int64)v55,
                          v40[3] & 0xFFFFFF,
                          (__int64)&v61);
    HsmDbgBreakOnStatus(v48);
    if ( (int)v48 >= 0 && (_DWORD)v61 == (_DWORD)v44 + 4 )
    {
      v49 = v56;
      v50 = v56 + 1;
LABEL_79:
      v51 = *(_QWORD *)(v28 + 8 * v38 + 8);
      if ( FltIs32bitProcess(CallbackData) )
        v51 = (unsigned int)v51;
      LODWORD(v61) = RtlCrc32(v50, v44, 0);
      RtlCopyToUser((void *)v51, v50, v44);
      if ( (_DWORD)v61 == *v49 )
      {
        v52 = 0;
      }
      else
      {
        HsmDbgBreakOnCorruption();
        v52 = -2147430656;
      }
      *(_DWORD *)(v28 + 8 * v38 + 20) = v52;
      v23 = a6;
      goto LABEL_86;
    }
    HsmDbgBreakOnCorruption();
LABEL_85:
    *(_QWORD *)(v28 + 8 * v38 + 16) = 0;
    goto LABEL_86;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
      v62,
      v23,
      *(_QWORD *)(v23 + 32),
      PropertyStream);
  }
LABEL_63:
  Pool2 = (__int64)v56;
LABEL_64:
  v14 = v55;
LABEL_65:
  v46 = v54;
LABEL_66:
  if ( v46 )
  {
    ExReleaseResourceLite((PERESOURCE)(v23 + 120));
    KeLeaveCriticalRegion();
  }
  if ( v14 )
    ExFreePoolWithTag(v14, 0x72507348u);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x72507348u);
  HsmpUnloadPropertyStream(v23);
  return (unsigned int)PropertyStream;
}

```

## disassembly

```asm
0x14005062c  mov     r11, rsp
0x14005062f  mov     [r11+18h], rbx
0x140050633  mov     [r11+20h], rsi
0x140050637  mov     [r11+10h], rdx
0x14005063b  mov     [r11+8], rcx
0x14005063f  push    rdi
0x140050640  push    r12
0x140050642  push    r13
0x140050644  push    r14
0x140050646  push    r15
0x140050648  sub     rsp, 0A0h
0x14005064f  mov     rsi, r8
0x140050652  mov     r13, rdx
0x140050655  mov     rax, [rdx+20h]
0x140050659  mov     [rsp+0C8h+InitiatingInstance], rax
0x140050661  xor     edi, edi
0x140050663  mov     [r11-48h], rdi
0x140050667  mov     [rsp+0C8h+var_68], edi
0x14005066b  mov     r15d, edi
0x14005066e  mov     [rsp+0C8h+var_58], rdi
0x140050673  mov     r14d, edi
0x140050676  mov     [rsp+0C8h+var_50], rdi
0x14005067b  lea     rax, WPP_GLOBAL_Control
0x140050682  mov     r8, cs:WPP_GLOBAL_Control
0x140050689  cmp     r8, rax
0x14005068c  jz      loc_140050722
0x140050692  mov     eax, [r8+2Ch]
0x140050696  test    al, 1
0x140050698  jz      loc_140050722
0x14005069e  cmp     byte ptr [r8+29h], 5
0x1400506a3  jb      short loc_140050722
0x1400506a5  test    r9, r9
0x1400506a8  jz      short loc_1400506B0
0x1400506aa  mov     ebx, [r9+28h]
0x1400506ae  jmp     short loc_1400506B2
0x1400506b0  mov     ebx, edi
0x1400506b2  mov     rcx, [rsp+0C8h+arg_20]
0x1400506ba  test    rcx, rcx
0x1400506bd  jz      short loc_1400506C9
0x1400506bf  call    HsmpGetStreamSize
0x1400506c4  mov     r11, rax
0x1400506c7  jmp     short loc_1400506CC
0x1400506c9  mov     r11, rdi
0x1400506cc  test    rcx, rcx
0x1400506cf  jz      short loc_1400506D7
0x1400506d1  mov     r10d, [rcx+1Ch]
0x1400506d5  jmp     short loc_1400506DA
0x1400506d7  mov     r10d, edi
0x1400506da  mov     edx, 20h ; ' '
0x1400506df  mov     rax, [rsp+0C8h+CallbackData]
0x1400506e7  mov     [rsp+0C8h+var_70], rax
0x1400506ec  mov     [rsp+0C8h+var_78], rsi
0x1400506f1  mov     rax, [rsp+0C8h+arg_30]
0x1400506f9  mov     [rsp+0C8h+var_80], rax
0x1400506fe  mov     dword ptr [rsp+0C8h+CallbackContext], ebx
0x140050702  mov     [rsp+0C8h+CallbackRoutine], r9
0x140050707  mov     [rsp+0C8h+BytesRead], r11
0x14005070c  mov     [rsp+0C8h+Flags], r10d
0x140050711  mov     [rsp+0C8h+Buffer], rcx
0x140050716  mov     r9, r13
0x140050719  mov     rcx, [r8+18h]
0x14005071d  call    WPP_SF_qqLiqLiqq
0x140050722  mov     rax, [rsp+0C8h+arg_40]
0x14005072a  mov     ecx, [rax+10h]
0x14005072d  cmp     ecx, 20h ; ' '
0x140050730  jb      loc_140050C7E
0x140050736  mov     r9d, [rsp+0C8h+arg_48]
0x14005073e  cmp     ecx, r9d
0x140050741  ja      loc_140050C7E
0x140050747  mov     r8d, [rax+14h]
0x14005074b  test    r8d, r8d
0x14005074e  jz      loc_140050C7E
0x140050754  mov     eax, r9d
0x140050757  sub     eax, ecx
0x140050759  xor     edx, edx
0x14005075b  div     r8d
0x14005075e  cmp     eax, 18h
0x140050761  jb      loc_140050C7E
0x140050767  cmp     [rsp+0C8h+arg_50], r9d
0x14005076f  jb      loc_140050C7E
0x140050775  mov     byte ptr [rsp+0C8h+Buffer], dil; char
0x14005077a  mov     r12, [rsp+0C8h+arg_28]
0x140050782  mov     r9, r12
0x140050785  mov     r8, rsi
0x140050788  mov     rdx, [rsp+0C8h+arg_20]
0x140050790  mov     rcx, r13; int
0x140050793  call    HsmpLoadPropertyStream
0x140050798  mov     ebx, eax
0x14005079a  mov     ecx, eax
0x14005079c  call    HsmDbgBreakOnStatus
0x1400507a1  test    ebx, ebx
0x1400507a3  js      loc_140050C92
0x1400507a9  mov     rcx, [r12+0E0h]
0x1400507b1  mov     [rsp+0C8h+var_60], rcx
0x1400507b6  mov     [rsp+0C8h+var_30], rcx
0x1400507be  mov     [rsp+0C8h+arg_58], rsi
0x1400507c6  mov     ebx, edi
0x1400507c8  mov     r13d, edi
0x1400507cb  mov     rsi, [rsp+0C8h+arg_40]
0x1400507d3  mov     r15d, [rsi+10h]
0x1400507d7  add     r15, rsi
0x1400507da  mov     eax, [rsi+14h]
0x1400507dd  mov     dword ptr [rsp+0C8h+arg_0], eax
0x1400507e4  cmp     r14d, eax
0x1400507e7  jnb     loc_1400508C8
0x1400507ed  lea     rax, [r14+r14*2]
0x1400507f1  mov     [rsp+0C8h+var_40], rax
0x1400507f9  mov     esi, [r15+rax*8]
0x1400507fd  test    esi, esi
0x1400507ff  jz      loc_1400508A2
0x140050805  xor     r9d, r9d
0x140050808  mov     r8d, esi
0x14005080b  lea     rdx, [rsp+0C8h+arg_58]
0x140050813  call    HsmiDoesBlobOperationConflictWithExistingLocks
0x140050818  test    al, al
0x14005081a  jnz     loc_1400508B1
0x140050820  mov     r8, rdi
0x140050823  mov     rcx, [rsp+0C8h+var_60]
0x140050828  add     rcx, 40h ; '@'
0x14005082c  mov     rax, [rcx]
0x14005082f  jmp     short loc_14005083C
0x140050831  mov     r8, rax
0x140050834  cmp     [rax+10h], esi
0x140050837  jz      short loc_140050841
0x140050839  mov     rax, [rax]
0x14005083c  cmp     rax, rcx
0x14005083f  jnz     short loc_140050831
0x140050841  test    r8, r8
0x140050844  jz      short loc_14005089D
0x140050846  mov     r9b, [r8+1Bh]
0x14005084a  mov     al, r9b
0x14005084d  neg     al
0x14005084f  sbb     rcx, rcx
0x140050852  and     ecx, 4
0x140050855  mov     edx, [rcx+r8+18h]
0x14005085a  and     edx, 0FFFFFFh
0x140050860  mov     rax, [rsp+0C8h+var_40]
0x140050868  cmp     edx, [r15+rax*8+4]
0x14005086d  ja      short loc_14005089D
0x14005086f  mov     eax, [r8+18h]
0x140050873  and     eax, 0FFFFFFh
0x140050878  cmp     eax, ebx
0x14005087a  cmovbe  eax, ebx
0x14005087d  mov     ebx, eax
0x14005087f  test    r9b, r9b
0x140050882  jz      short loc_14005089D
0x140050884  mov     ecx, edx
0x140050886  add     rcx, 4
0x14005088a  mov     eax, r13d
0x14005088d  cmp     rcx, rax
0x140050890  mov     rcx, [rsp+0C8h+var_60]
0x140050895  jbe     short loc_1400508A2
0x140050897  lea     r13d, [rdx+4]
0x14005089b  jmp     short loc_1400508A2
0x14005089d  mov     rcx, [rsp+0C8h+var_60]
0x1400508a2  inc     r14d
0x1400508a5  mov     eax, dword ptr [rsp+0C8h+arg_0]
0x1400508ac  jmp     loc_1400507E4
0x1400508b1  mov     ebx, 0C000CF1Ah
0x1400508b6  mov     ecx, ebx
0x1400508b8  call    HsmDbgBreakOnStatus
0x1400508bd  mov     r14, rdi
0x1400508c0  mov     r15, rdi
0x1400508c3  jmp     loc_140050A9D
0x1400508c8  test    ebx, ebx
0x1400508ca  jz      short loc_140050906
0x1400508cc  mov     edx, ebx
0x1400508ce  mov     ecx, 100h
0x1400508d3  mov     r8d, 72507348h
0x1400508d9  call    cs:__imp_ExAllocatePool2
0x1400508e0  nop     dword ptr [rax+rax+00h]
0x1400508e5  mov     rbx, rax
0x1400508e8  mov     [rsp+0C8h+var_58], rax
0x1400508ed  test    rax, rax
0x1400508f0  jnz     short loc_140050909
0x1400508f2  mov     ecx, 0C000009Ah
0x1400508f7  mov     ebx, ecx
0x1400508f9  call    HsmDbgBreakOnStatus
0x1400508fe  mov     r14, rdi
0x140050901  jmp     loc_140050A98
0x140050906  mov     rbx, rdi
0x140050909  test    r13d, r13d
0x14005090c  jz      short loc_140050946
0x14005090e  mov     edx, r13d
0x140050911  mov     ecx, 100h
0x140050916  mov     r8d, 72507348h
0x14005091c  call    cs:__imp_ExAllocatePool2
0x140050923  nop     dword ptr [rax+rax+00h]
0x140050928  mov     r14, rax
0x14005092b  mov     [rsp+0C8h+var_50], rax
0x140050930  test    rax, rax
0x140050933  jnz     short loc_140050946
0x140050935  mov     ecx, 0C000009Ah
0x14005093a  mov     ebx, ecx
0x14005093c  call    HsmDbgBreakOnStatus
0x140050941  jmp     loc_140050A98
0x140050946  mov     eax, edi
0x140050948  mov     rcx, [rsp+0C8h+arg_40]
0x140050950  mov     dword ptr [rsp+0C8h+arg_58], eax
0x140050957  cmp     eax, [rcx+14h]
0x14005095a  jnb     loc_140050C64
0x140050960  lea     rsi, [rax+rax*2]
0x140050964  mov     edx, [r15+rsi*8]
0x140050968  test    edx, edx
0x14005096a  jz      loc_140050C51
0x140050970  mov     r13, rdi
0x140050973  mov     r10, [rsp+0C8h+var_60]
0x140050978  lea     rcx, [r10+40h]
0x14005097c  mov     rax, [rcx]
0x14005097f  jmp     short loc_14005098C
0x140050981  mov     r13, rax
0x140050984  cmp     [rax+10h], edx
0x140050987  jz      short loc_140050991
0x140050989  mov     rax, [rax]
0x14005098c  cmp     rax, rcx
0x14005098f  jnz     short loc_140050981
0x140050991  cmp     rax, rcx
0x140050994  jz      loc_140050C44
0x14005099a  mov     r14d, [r13+18h]
0x14005099e  mov     ecx, 0FFFFFFh
0x1400509a3  and     r14d, ecx
0x1400509a6  jz      loc_140050C44
0x1400509ac  lea     rax, [r13+1Ch]
0x1400509b0  mov     [rsp+0C8h+arg_0], rax
0x1400509b8  cmp     [r13+1Bh], dil
0x1400509bc  jz      short loc_1400509C4
0x1400509be  mov     r14d, [rax]
0x1400509c1  and     r14d, ecx
0x1400509c4  mov     [r15+rsi*8+10h], r14d
0x1400509c9  cmp     r14d, [r15+rsi*8+4]
0x1400509ce  jbe     short loc_1400509DE
0x1400509d0  mov     dword ptr [r15+rsi*8+14h], 80000005h
0x1400509d9  jmp     loc_140050C49
0x1400509de  mov     eax, [r13+14h]
0x1400509e2  add     rax, 8
0x1400509e6  mov     qword ptr [rsp+0C8h+ByteOffset], rax
0x1400509ee  mov     r9d, [r13+18h]
0x1400509f2  and     r9d, ecx; Length
0x1400509f5  mov     [rsp+0C8h+CallbackContext], rdi; CallbackContext
0x1400509fa  mov     [rsp+0C8h+CallbackRoutine], rdi; CallbackRoutine
0x1400509ff  lea     rax, [rsp+0C8h+var_68]
0x140050a04  mov     [rsp+0C8h+BytesRead], rax; BytesRead
0x140050a09  mov     [rsp+0C8h+Flags], edi; Flags
0x140050a0d  mov     [rsp+0C8h+Buffer], rbx; Buffer
0x140050a12  lea     r8, [rsp+0C8h+ByteOffset]; ByteOffset
0x140050a1a  mov     rdx, [r10+18h]; FileObject
0x140050a1e  mov     rcx, [rsp+0C8h+InitiatingInstance]; InitiatingInstance
0x140050a26  call    cs:__imp_FltReadFile
0x140050a2d  nop     dword ptr [rax+rax+00h]
0x140050a32  mov     ebx, eax
0x140050a34  mov     ecx, eax
0x140050a36  call    HsmDbgBreakOnStatus
0x140050a3b  test    ebx, ebx
0x140050a3d  jns     loc_140050B1E
0x140050a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140050a4a  lea     rax, WPP_GLOBAL_Control
0x140050a51  cmp     rcx, rax
0x140050a54  jz      short loc_140050A93
0x140050a56  mov     eax, [rcx+2Ch]
0x140050a59  test    al, 1
0x140050a5b  jz      short loc_140050A93
0x140050a5d  cmp     byte ptr [rcx+29h], 2
0x140050a61  jb      short loc_140050A93
0x140050a63  mov     edx, 21h ; '!'
0x140050a68  mov     dword ptr [rsp+0C8h+BytesRead], ebx
0x140050a6c  mov     rax, [r12+20h]
0x140050a71  mov     qword ptr [rsp+0C8h+Flags], rax
0x140050a76  mov     [rsp+0C8h+Buffer], r12
0x140050a7b  mov     r9, [rsp+0C8h+arg_8]
0x140050a83  lea     r8, WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids
0x140050a8a  mov     rcx, [rcx+18h]
0x140050a8e  call    WPP_SF_qqqd
0x140050a93  mov     r14, [rsp+0C8h+var_50]
0x140050a98  mov     r15, [rsp+0C8h+var_58]
0x140050a9d  mov     rax, [rsp+0C8h+var_60]
0x140050aa2  test    rax, rax
0x140050aa5  jz      short loc_140050AC4
0x140050aa7  lea     rcx, [r12+78h]; Resource
0x140050aac  call    cs:__imp_ExReleaseResourceLite
0x140050ab3  nop     dword ptr [rax+rax+00h]
0x140050ab8  call    cs:__imp_KeLeaveCriticalRegion
0x140050abf  nop     dword ptr [rax+rax+00h]
0x140050ac4  test    r15, r15
0x140050ac7  jz      short loc_140050ADD
0x140050ac9  mov     edx, 72507348h; Tag
0x140050ace  mov     rcx, r15; P
0x140050ad1  call    cs:__imp_ExFreePoolWithTag
0x140050ad8  nop     dword ptr [rax+rax+00h]
0x140050add  test    r14, r14
0x140050ae0  jz      short loc_140050AF6
0x140050ae2  mov     edx, 72507348h; Tag
0x140050ae7  mov     rcx, r14; P
0x140050aea  call    cs:__imp_ExFreePoolWithTag
0x140050af1  nop     dword ptr [rax+rax+00h]
0x140050af6  mov     rcx, r12
0x140050af9  call    HsmpUnloadPropertyStream
0x140050afe  mov     eax, ebx
0x140050b00  lea     r11, [rsp+0C8h+var_28]
0x140050b08  mov     rbx, [r11+40h]
0x140050b0c  mov     rsi, [r11+48h]
  ... truncated ...
```
