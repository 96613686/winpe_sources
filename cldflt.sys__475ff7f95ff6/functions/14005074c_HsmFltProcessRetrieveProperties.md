# HsmFltProcessRetrieveProperties

- ea: `0x14005074c`
- end: `0x140050dba`
- name: `HsmFltProcessRetrieveProperties`
- size: `1646`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64, __int64, __int64, __int64, PFLT_CALLBACK_DATA CallbackData, __int64, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14004dff0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000caf0`
- `0x14000db8c`
- `0x140037030`
- `0x14004a2d8`
- `0x14004c78c`
- `0x14005074c`
- `0x140058ddc`
- `0x14005d0b0`
- `0x14005f198`

## import_xrefs

- `ntoskrnl!RtlCrc32` at `0x140050ced`
- `ntoskrnl!RtlCrc32` at `0x140050ced`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050bd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050bd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050bcc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050bcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050bf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050bf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050c0a`
- `ntoskrnl!ExAllocatePool2` at `0x1400509f9`
- `ntoskrnl!ExAllocatePool2` at `0x140050a3c`
- `ntoskrnl!ExAllocatePool2` at `0x1400509f9`
- `ntoskrnl!ExAllocatePool2` at `0x140050a3c`
- `FLTMGR!FltIs32bitProcess` at `0x140050cd2`
- `FLTMGR!FltIs32bitProcess` at `0x140050cd2`
- `FLTMGR!FltReadFile` at `0x140050b46`
- `FLTMGR!FltReadFile` at `0x140050b46`

## pseudocode

```c
__int64 __fastcall HsmFltProcessRetrieveProperties(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a9,
        unsigned int a10,
        unsigned int a11,
        __int64 a12)
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
  NTSTATUS PropertyStream; // ebx
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
  int v45; // edx
  __int64 v46; // rax
  int v48; // ebx
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
    WPP_SF_qqLiqLiqq(v16->AttachedDevice, 32, v16, a2, v18, v20, StreamSize, a4, v17, a7, a3, CallbackData, BytesRead);
  }
  v21 = *(_DWORD *)(a9 + 16);
  if ( v21 < 0x20 || v21 > a10 || (v22 = *(_DWORD *)(a9 + 20)) == 0 || (a10 - v21) / v22 < 0x18 || a11 < a10 )
  {
    PropertyStream = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    v23 = a6;
    goto LABEL_90;
  }
  v23 = a6;
  PropertyStream = HsmpLoadPropertyStream(a2, 0);
  HsmDbgBreakOnStatus(PropertyStream);
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
        HsmDbgBreakOnStatus(-1073688806);
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
      HsmDbgBreakOnStatus(-1073741670);
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
      HsmDbgBreakOnStatus(-1073741670);
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
    v36 = (unsigned int)(a12 + 1);
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
  HsmDbgBreakOnStatus(PropertyStream);
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
    v48 = HsmiDecompressBuffer(
            HIBYTE(*((_DWORD *)v40 + 6)),
            v45,
            (_DWORD)v56,
            (int)v44 + 4,
            (__int64)v55,
            v40[3] & 0xFFFFFF,
            (__int64)&v61);
    HsmDbgBreakOnStatus(v48);
    if ( v48 >= 0 && (_DWORD)v61 == (_DWORD)v44 + 4 )
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
0x14005074c  mov     r11, rsp
0x14005074f  mov     [r11+18h], rbx
0x140050753  mov     [r11+20h], rsi
0x140050757  mov     [r11+10h], rdx
0x14005075b  mov     [r11+8], rcx
0x14005075f  push    rdi
0x140050760  push    r12
0x140050762  push    r13
0x140050764  push    r14
0x140050766  push    r15
0x140050768  sub     rsp, 0A0h
0x14005076f  mov     rsi, r8
0x140050772  mov     r13, rdx
0x140050775  mov     rax, [rdx+20h]
0x140050779  mov     [rsp+0C8h+InitiatingInstance], rax
0x140050781  xor     edi, edi
0x140050783  mov     [r11-48h], rdi
0x140050787  mov     [rsp+0C8h+var_68], edi
0x14005078b  mov     r15d, edi
0x14005078e  mov     [rsp+0C8h+var_58], rdi
0x140050793  mov     r14d, edi
0x140050796  mov     [rsp+0C8h+var_50], rdi
0x14005079b  lea     rax, WPP_GLOBAL_Control
0x1400507a2  mov     r8, cs:WPP_GLOBAL_Control
0x1400507a9  cmp     r8, rax
0x1400507ac  jz      loc_140050842
0x1400507b2  mov     eax, [r8+2Ch]
0x1400507b6  test    al, 1
0x1400507b8  jz      loc_140050842
0x1400507be  cmp     byte ptr [r8+29h], 5
0x1400507c3  jb      short loc_140050842
0x1400507c5  test    r9, r9
0x1400507c8  jz      short loc_1400507D0
0x1400507ca  mov     ebx, [r9+28h]
0x1400507ce  jmp     short loc_1400507D2
0x1400507d0  mov     ebx, edi
0x1400507d2  mov     rcx, [rsp+0C8h+arg_20]
0x1400507da  test    rcx, rcx
0x1400507dd  jz      short loc_1400507E9
0x1400507df  call    HsmpGetStreamSize
0x1400507e4  mov     r11, rax
0x1400507e7  jmp     short loc_1400507EC
0x1400507e9  mov     r11, rdi
0x1400507ec  test    rcx, rcx
0x1400507ef  jz      short loc_1400507F7
0x1400507f1  mov     r10d, [rcx+1Ch]
0x1400507f5  jmp     short loc_1400507FA
0x1400507f7  mov     r10d, edi
0x1400507fa  mov     edx, 20h ; ' '
0x1400507ff  mov     rax, [rsp+0C8h+CallbackData]
0x140050807  mov     [rsp+0C8h+var_70], rax
0x14005080c  mov     [rsp+0C8h+var_78], rsi
0x140050811  mov     rax, [rsp+0C8h+arg_30]
0x140050819  mov     [rsp+0C8h+var_80], rax
0x14005081e  mov     dword ptr [rsp+0C8h+CallbackContext], ebx
0x140050822  mov     [rsp+0C8h+CallbackRoutine], r9
0x140050827  mov     [rsp+0C8h+BytesRead], r11
0x14005082c  mov     [rsp+0C8h+Flags], r10d
0x140050831  mov     [rsp+0C8h+Buffer], rcx
0x140050836  mov     r9, r13
0x140050839  mov     rcx, [r8+18h]
0x14005083d  call    WPP_SF_qqLiqLiqq
0x140050842  mov     rax, [rsp+0C8h+arg_40]
0x14005084a  mov     ecx, [rax+10h]
0x14005084d  cmp     ecx, 20h ; ' '
0x140050850  jb      loc_140050D9E
0x140050856  mov     r9d, [rsp+0C8h+arg_48]
0x14005085e  cmp     ecx, r9d
0x140050861  ja      loc_140050D9E
0x140050867  mov     r8d, [rax+14h]
0x14005086b  test    r8d, r8d
0x14005086e  jz      loc_140050D9E
0x140050874  mov     eax, r9d
0x140050877  sub     eax, ecx
0x140050879  xor     edx, edx
0x14005087b  div     r8d
0x14005087e  cmp     eax, 18h
0x140050881  jb      loc_140050D9E
0x140050887  cmp     [rsp+0C8h+arg_50], r9d
0x14005088f  jb      loc_140050D9E
0x140050895  mov     byte ptr [rsp+0C8h+Buffer], dil; char
0x14005089a  mov     r12, [rsp+0C8h+arg_28]
0x1400508a2  mov     r9, r12
0x1400508a5  mov     r8, rsi
0x1400508a8  mov     rdx, [rsp+0C8h+arg_20]
0x1400508b0  mov     rcx, r13; int
0x1400508b3  call    HsmpLoadPropertyStream
0x1400508b8  mov     ebx, eax
0x1400508ba  mov     ecx, eax
0x1400508bc  call    HsmDbgBreakOnStatus
0x1400508c1  test    ebx, ebx
0x1400508c3  js      loc_140050DB2
0x1400508c9  mov     rcx, [r12+0E0h]
0x1400508d1  mov     [rsp+0C8h+var_60], rcx
0x1400508d6  mov     [rsp+0C8h+var_30], rcx
0x1400508de  mov     [rsp+0C8h+arg_58], rsi
0x1400508e6  mov     ebx, edi
0x1400508e8  mov     r13d, edi
0x1400508eb  mov     rsi, [rsp+0C8h+arg_40]
0x1400508f3  mov     r15d, [rsi+10h]
0x1400508f7  add     r15, rsi
0x1400508fa  mov     eax, [rsi+14h]
0x1400508fd  mov     dword ptr [rsp+0C8h+arg_0], eax
0x140050904  cmp     r14d, eax
0x140050907  jnb     loc_1400509E8
0x14005090d  lea     rax, [r14+r14*2]
0x140050911  mov     [rsp+0C8h+var_40], rax
0x140050919  mov     esi, [r15+rax*8]
0x14005091d  test    esi, esi
0x14005091f  jz      loc_1400509C2
0x140050925  xor     r9d, r9d
0x140050928  mov     r8d, esi
0x14005092b  lea     rdx, [rsp+0C8h+arg_58]
0x140050933  call    HsmiDoesBlobOperationConflictWithExistingLocks
0x140050938  test    al, al
0x14005093a  jnz     loc_1400509D1
0x140050940  mov     r8, rdi
0x140050943  mov     rcx, [rsp+0C8h+var_60]
0x140050948  add     rcx, 40h ; '@'
0x14005094c  mov     rax, [rcx]
0x14005094f  jmp     short loc_14005095C
0x140050951  mov     r8, rax
0x140050954  cmp     [rax+10h], esi
0x140050957  jz      short loc_140050961
0x140050959  mov     rax, [rax]
0x14005095c  cmp     rax, rcx
0x14005095f  jnz     short loc_140050951
0x140050961  test    r8, r8
0x140050964  jz      short loc_1400509BD
0x140050966  mov     r9b, [r8+1Bh]
0x14005096a  mov     al, r9b
0x14005096d  neg     al
0x14005096f  sbb     rcx, rcx
0x140050972  and     ecx, 4
0x140050975  mov     edx, [rcx+r8+18h]
0x14005097a  and     edx, 0FFFFFFh
0x140050980  mov     rax, [rsp+0C8h+var_40]
0x140050988  cmp     edx, [r15+rax*8+4]
0x14005098d  ja      short loc_1400509BD
0x14005098f  mov     eax, [r8+18h]
0x140050993  and     eax, 0FFFFFFh
0x140050998  cmp     eax, ebx
0x14005099a  cmovbe  eax, ebx
0x14005099d  mov     ebx, eax
0x14005099f  test    r9b, r9b
0x1400509a2  jz      short loc_1400509BD
0x1400509a4  mov     ecx, edx
0x1400509a6  add     rcx, 4
0x1400509aa  mov     eax, r13d
0x1400509ad  cmp     rcx, rax
0x1400509b0  mov     rcx, [rsp+0C8h+var_60]
0x1400509b5  jbe     short loc_1400509C2
0x1400509b7  lea     r13d, [rdx+4]
0x1400509bb  jmp     short loc_1400509C2
0x1400509bd  mov     rcx, [rsp+0C8h+var_60]
0x1400509c2  inc     r14d
0x1400509c5  mov     eax, dword ptr [rsp+0C8h+arg_0]
0x1400509cc  jmp     loc_140050904
0x1400509d1  mov     ebx, 0C000CF1Ah
0x1400509d6  mov     ecx, ebx
0x1400509d8  call    HsmDbgBreakOnStatus
0x1400509dd  mov     r14, rdi
0x1400509e0  mov     r15, rdi
0x1400509e3  jmp     loc_140050BBD
0x1400509e8  test    ebx, ebx
0x1400509ea  jz      short loc_140050A26
0x1400509ec  mov     edx, ebx
0x1400509ee  mov     ecx, 100h
0x1400509f3  mov     r8d, 72507348h
0x1400509f9  call    cs:__imp_ExAllocatePool2
0x140050a00  nop     dword ptr [rax+rax+00h]
0x140050a05  mov     rbx, rax
0x140050a08  mov     [rsp+0C8h+var_58], rax
0x140050a0d  test    rax, rax
0x140050a10  jnz     short loc_140050A29
0x140050a12  mov     ecx, 0C000009Ah
0x140050a17  mov     ebx, ecx
0x140050a19  call    HsmDbgBreakOnStatus
0x140050a1e  mov     r14, rdi
0x140050a21  jmp     loc_140050BB8
0x140050a26  mov     rbx, rdi
0x140050a29  test    r13d, r13d
0x140050a2c  jz      short loc_140050A66
0x140050a2e  mov     edx, r13d
0x140050a31  mov     ecx, 100h
0x140050a36  mov     r8d, 72507348h
0x140050a3c  call    cs:__imp_ExAllocatePool2
0x140050a43  nop     dword ptr [rax+rax+00h]
0x140050a48  mov     r14, rax
0x140050a4b  mov     [rsp+0C8h+var_50], rax
0x140050a50  test    rax, rax
0x140050a53  jnz     short loc_140050A66
0x140050a55  mov     ecx, 0C000009Ah
0x140050a5a  mov     ebx, ecx
0x140050a5c  call    HsmDbgBreakOnStatus
0x140050a61  jmp     loc_140050BB8
0x140050a66  mov     eax, edi
0x140050a68  mov     rcx, [rsp+0C8h+arg_40]
0x140050a70  mov     dword ptr [rsp+0C8h+arg_58], eax
0x140050a77  cmp     eax, [rcx+14h]
0x140050a7a  jnb     loc_140050D84
0x140050a80  lea     rsi, [rax+rax*2]
0x140050a84  mov     edx, [r15+rsi*8]
0x140050a88  test    edx, edx
0x140050a8a  jz      loc_140050D71
0x140050a90  mov     r13, rdi
0x140050a93  mov     r10, [rsp+0C8h+var_60]
0x140050a98  lea     rcx, [r10+40h]
0x140050a9c  mov     rax, [rcx]
0x140050a9f  jmp     short loc_140050AAC
0x140050aa1  mov     r13, rax
0x140050aa4  cmp     [rax+10h], edx
0x140050aa7  jz      short loc_140050AB1
0x140050aa9  mov     rax, [rax]
0x140050aac  cmp     rax, rcx
0x140050aaf  jnz     short loc_140050AA1
0x140050ab1  cmp     rax, rcx
0x140050ab4  jz      loc_140050D64
0x140050aba  mov     r14d, [r13+18h]
0x140050abe  mov     ecx, 0FFFFFFh
0x140050ac3  and     r14d, ecx
0x140050ac6  jz      loc_140050D64
0x140050acc  lea     rax, [r13+1Ch]
0x140050ad0  mov     [rsp+0C8h+arg_0], rax
0x140050ad8  cmp     [r13+1Bh], dil
0x140050adc  jz      short loc_140050AE4
0x140050ade  mov     r14d, [rax]
0x140050ae1  and     r14d, ecx
0x140050ae4  mov     [r15+rsi*8+10h], r14d
0x140050ae9  cmp     r14d, [r15+rsi*8+4]
0x140050aee  jbe     short loc_140050AFE
0x140050af0  mov     dword ptr [r15+rsi*8+14h], 80000005h
0x140050af9  jmp     loc_140050D69
0x140050afe  mov     eax, [r13+14h]
0x140050b02  add     rax, 8
0x140050b06  mov     qword ptr [rsp+0C8h+ByteOffset], rax
0x140050b0e  mov     r9d, [r13+18h]
0x140050b12  and     r9d, ecx; Length
0x140050b15  mov     [rsp+0C8h+CallbackContext], rdi; CallbackContext
0x140050b1a  mov     [rsp+0C8h+CallbackRoutine], rdi; CallbackRoutine
0x140050b1f  lea     rax, [rsp+0C8h+var_68]
0x140050b24  mov     [rsp+0C8h+BytesRead], rax; BytesRead
0x140050b29  mov     [rsp+0C8h+Flags], edi; Flags
0x140050b2d  mov     [rsp+0C8h+Buffer], rbx; Buffer
0x140050b32  lea     r8, [rsp+0C8h+ByteOffset]; ByteOffset
0x140050b3a  mov     rdx, [r10+18h]; FileObject
0x140050b3e  mov     rcx, [rsp+0C8h+InitiatingInstance]; InitiatingInstance
0x140050b46  call    cs:__imp_FltReadFile
0x140050b4d  nop     dword ptr [rax+rax+00h]
0x140050b52  mov     ebx, eax
0x140050b54  mov     ecx, eax
0x140050b56  call    HsmDbgBreakOnStatus
0x140050b5b  test    ebx, ebx
0x140050b5d  jns     loc_140050C3E
0x140050b63  mov     rcx, cs:WPP_GLOBAL_Control
0x140050b6a  lea     rax, WPP_GLOBAL_Control
0x140050b71  cmp     rcx, rax
0x140050b74  jz      short loc_140050BB3
0x140050b76  mov     eax, [rcx+2Ch]
0x140050b79  test    al, 1
0x140050b7b  jz      short loc_140050BB3
0x140050b7d  cmp     byte ptr [rcx+29h], 2
0x140050b81  jb      short loc_140050BB3
0x140050b83  mov     edx, 21h ; '!'
0x140050b88  mov     dword ptr [rsp+0C8h+BytesRead], ebx
0x140050b8c  mov     rax, [r12+20h]
0x140050b91  mov     qword ptr [rsp+0C8h+Flags], rax
0x140050b96  mov     [rsp+0C8h+Buffer], r12
0x140050b9b  mov     r9, [rsp+0C8h+arg_8]
0x140050ba3  lea     r8, WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids
0x140050baa  mov     rcx, [rcx+18h]
0x140050bae  call    WPP_SF_qqqd
0x140050bb3  mov     r14, [rsp+0C8h+var_50]
0x140050bb8  mov     r15, [rsp+0C8h+var_58]
0x140050bbd  mov     rax, [rsp+0C8h+var_60]
0x140050bc2  test    rax, rax
0x140050bc5  jz      short loc_140050BE4
0x140050bc7  lea     rcx, [r12+78h]; Resource
0x140050bcc  call    cs:__imp_ExReleaseResourceLite
0x140050bd3  nop     dword ptr [rax+rax+00h]
0x140050bd8  call    cs:__imp_KeLeaveCriticalRegion
0x140050bdf  nop     dword ptr [rax+rax+00h]
0x140050be4  test    r15, r15
0x140050be7  jz      short loc_140050BFD
0x140050be9  mov     edx, 72507348h; Tag
0x140050bee  mov     rcx, r15; P
0x140050bf1  call    cs:__imp_ExFreePoolWithTag
0x140050bf8  nop     dword ptr [rax+rax+00h]
0x140050bfd  test    r14, r14
0x140050c00  jz      short loc_140050C16
0x140050c02  mov     edx, 72507348h; Tag
0x140050c07  mov     rcx, r14; P
0x140050c0a  call    cs:__imp_ExFreePoolWithTag
0x140050c11  nop     dword ptr [rax+rax+00h]
0x140050c16  mov     rcx, r12
0x140050c19  call    HsmpUnloadPropertyStream
0x140050c1e  mov     eax, ebx
0x140050c20  lea     r11, [rsp+0C8h+var_28]
0x140050c28  mov     rbx, [r11+40h]
0x140050c2c  mov     rsi, [r11+48h]
  ... truncated ...
```
