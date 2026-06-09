# MountMgrVolumeMountPointDeleted

- ea: `0x14000ecbc`
- end: `0x14000f437`
- name: `MountMgrVolumeMountPointDeleted`
- size: `1915`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000f440`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x14000b5e8`
- `0x14000cd50`
- `0x14000db54`
- `0x14000ecbc`
- `0x140010600`
- `0x140010970`
- `0x140010d00`
- `0x140011500`
- `0x140012df0`
- `0x140012e60`
- `0x1400135a0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000effe`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000f344`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000effe`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000f344`
- `ntoskrnl!ExAllocatePool2` at `0x14000ed34`
- `ntoskrnl!ExAllocatePool2` at `0x14000ed34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f019`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f080`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f21e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f22f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f395`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f3a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f019`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f080`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f21e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f22f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f395`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f3a6`
- `ntoskrnl!RtlCompareMemory` at `0x14000f1a4`
- `ntoskrnl!RtlCompareMemory` at `0x14000f1a4`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeMountPointDeleted(__int64 a1, int a2, int a3)
{
  int SymbolicLink; // edi
  __int64 v7; // r8
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r14
  __int64 v13; // r13
  __int64 v14; // r12
  void *v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // r8
  _DWORD *v18; // rsi
  __int64 v21; // r8
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  void *v24; // r12
  void *i; // r14
  _WORD *v26; // rcx
  SIZE_T v27; // rbx
  _QWORD *v28; // rax
  void **v29; // rcx
  __int64 v30; // r14
  char *v31; // r12
  char *j; // rbx
  char *v33; // rcx
  void **v34; // rax
  void *v35; // [rsp+40h] [rbp-89h] BYREF
  __int64 v36; // [rsp+48h] [rbp-81h] BYREF
  PVOID v37[2]; // [rsp+50h] [rbp-79h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v39[2]; // [rsp+70h] [rbp-59h] BYREF
  PVOID v40[2]; // [rsp+80h] [rbp-49h] BYREF
  UNICODE_STRING String2; // [rsp+90h] [rbp-39h] BYREF
  UNICODE_STRING String1; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-19h]
  __int64 v44; // [rsp+B8h] [rbp-11h]
  PVOID v45[2]; // [rsp+C0h] [rbp-9h] BYREF
  PVOID v46[2]; // [rsp+D0h] [rbp+7h] BYREF
  char v47; // [rsp+148h] [rbp+7Fh] BYREF

  v47 = 0;
  v39[0] = 0;
  v36 = 0;
  v35 = 0;
  v37[0] = 0;
  v40[0] = (PVOID)13107200;
  *(_OWORD *)P = 0;
  *(_OWORD *)v45 = 0;
  String1 = 0;
  *(_OWORD *)v46 = 0;
  String2 = 0;
  v40[1] = (PVOID)ExAllocatePool2(258, 200, 1098149453);
  if ( !v40[1] )
  {
    SymbolicLink = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 274);
    goto LABEL_46;
  }
  SymbolicLink = MountMgrVolumeMountPointChanged(a1, a2, a3, (int)P, (__int64)v45, &String1);
  if ( SymbolicLink == 259 )
  {
    SymbolicLink = 0;
    goto LABEL_46;
  }
  if ( SymbolicLink < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_46;
    v9 = 275;
    goto LABEL_11;
  }
  if ( (int)FindDeviceInfo(a1, P, v7, v39) < 0 )
  {
    if ( (int)QueryVolumeName(a1, 0, 0, 0, (__int64)P, (__int64)v40, (__int64)v46) < 0 )
    {
      SymbolicLink = MountMgrQuerySymbolicLink(P, v40);
      if ( SymbolicLink < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_46;
        v9 = 276;
        goto LABEL_11;
      }
    }
    ExFreePoolWithTag(P[1], 0);
    *(_OWORD *)P = *(_OWORD *)v40;
    v40[1] = 0;
    SymbolicLink = FindDeviceInfo(a1, P, v11, v39);
    if ( SymbolicLink < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_46;
      v9 = 277;
      goto LABEL_11;
    }
  }
  SymbolicLink = FindDeviceInfo(a1, &String1, v7, &v36);
  if ( SymbolicLink < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_46;
    v9 = 278;
    goto LABEL_11;
  }
  v12 = *(_QWORD *)(a1 + 336);
  v13 = v39[0];
  v43 = v12;
  v14 = *(_QWORD *)(v36 + 176);
  v44 = v14;
  SymbolicLink = OpenRemoteDatabase(v39[0], 1, &v47, &v35);
  if ( v47 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_46;
    v9 = 279;
LABEL_11:
    v10 = (unsigned int)SymbolicLink;
    goto LABEL_12;
  }
  v15 = v35;
  if ( !v35 )
  {
    SymbolicLink = -1073741670;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_48;
    v9 = 280;
    v10 = 3221225626LL;
LABEL_12:
    WPP_SF_L(v8->AttachedDevice, v9, v7, v10);
    goto LABEL_46;
  }
  v16 = 0;
  v17 = 0;
  while ( 1 )
  {
    SymbolicLink = GetRemoteDatabaseEntry(v13, v15, v17, v37);
    if ( SymbolicLink < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 281, v7, (unsigned int)SymbolicLink);
      v18 = v37[0];
      goto LABEL_44;
    }
    v18 = v37[0];
    if ( !v37[0] )
    {
      SymbolicLink = -1073741811;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_46;
      v9 = 282;
      v10 = 3221225485LL;
      goto LABEL_12;
    }
    String2.MaximumLength = *((_WORD *)v37[0] + 5);
    String2.Length = String2.MaximumLength;
    String2.Buffer = (PWSTR)((char *)v37[0] + *((unsigned __int16 *)v37[0] + 4));
    if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
      break;
    v16 += *v18;
    ExFreePoolWithTag(v18, 0);
    v15 = v35;
    v17 = v16;
    v37[0] = 0;
  }
  if ( v18[1]-- != 1 )
  {
    SymbolicLink = WriteRemoteDatabaseEntry(v13, v35, v16, v18);
    goto LABEL_78;
  }
  SymbolicLink = DeleteRemoteDatabaseEntry(v13, v35, v16);
  if ( SymbolicLink < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v23 = 283;
      goto LABEL_63;
    }
    goto LABEL_44;
  }
  v24 = (void *)(v13 + 32);
  for ( i = *(void **)(v13 + 32); ; i = *(void **)i )
  {
    if ( i == v24 )
      goto LABEL_70;
    if ( !i )
    {
LABEL_108:
      SymbolicLink = -1073741275;
      goto LABEL_44;
    }
    v26 = (_WORD *)*((_QWORD *)i + 2);
    if ( *v26 == *((_WORD *)v18 + 7) )
    {
      v27 = *((unsigned __int16 *)v18 + 7);
      if ( RtlCompareMemory(v26 + 1, (char *)v18 + *((unsigned __int16 *)v18 + 6), v27) == v27 )
        break;
    }
  }
  if ( i == v24 )
  {
LABEL_70:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 284, v21, (unsigned int)SymbolicLink);
    SymbolicLink = -1073741823;
    goto LABEL_44;
  }
  v28 = *(_QWORD **)i;
  if ( *(void **)(*(_QWORD *)i + 8LL) != i || (v29 = (void **)*((_QWORD *)i + 1), *v29 != i) )
LABEL_107:
    __fastfail(3u);
  *v29 = v28;
  v28[1] = v29;
  ExFreePoolWithTag(*((PVOID *)i + 2), 0);
  ExFreePoolWithTag(i, 0);
  v12 = v43;
  v14 = v44;
LABEL_78:
  CloseFileHandleOutsideExtensionMutexLock(a1);
  v35 = 0;
  if ( SymbolicLink >= 0 )
  {
    SymbolicLink = VerifyEpoch(a1, v12, v14);
    if ( SymbolicLink < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_44;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 286);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_44;
      v23 = 287;
LABEL_63:
      WPP_SF_L(v22->AttachedDevice, v23, v21, (unsigned int)SymbolicLink);
      goto LABEL_44;
    }
    v36 = 0;
    SymbolicLink = FindDeviceInfo(a1, &String1, v21, &v36);
    if ( SymbolicLink < 0 )
    {
      if ( v36 )
        goto LABEL_104;
    }
    else
    {
      v30 = v36;
      if ( v36 )
      {
        v31 = (char *)(v36 + 48);
        for ( j = *(char **)(v36 + 48); ; j = *(char **)j )
        {
          if ( j == v31 )
            goto LABEL_44;
          if ( !j )
            goto LABEL_108;
          if ( *((_QWORD *)j + 2) == v13 && RtlEqualUnicodeString((PCUNICODE_STRING)(j + 24), (PCUNICODE_STRING)v45, 1u) )
            break;
        }
        *(_QWORD *)(v30 + 176) = ++*(_QWORD *)(a1 + 336);
        v33 = *(char **)j;
        if ( *(char **)(*(_QWORD *)j + 8LL) == j )
        {
          v34 = (void **)*((_QWORD *)j + 1);
          if ( *v34 == j )
          {
            *v34 = v33;
            *((_QWORD *)v33 + 1) = v34;
            ExFreePoolWithTag(*((PVOID *)j + 4), 0);
            ExFreePoolWithTag(j, 0);
            goto LABEL_44;
          }
        }
        goto LABEL_107;
      }
    }
    SymbolicLink = -1073741198;
LABEL_104:
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_44;
    v23 = 288;
    goto LABEL_63;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v23 = 285;
    goto LABEL_63;
  }
LABEL_44:
  if ( v18 )
    ExFreePoolWithTag(v18, 0);
LABEL_46:
  if ( v35 )
    CloseFileHandleOutsideExtensionMutexLock(a1);
LABEL_48:
  if ( v46[1] )
    ExFreePoolWithTag(v46[1], 0);
  if ( v45[1] )
    ExFreePoolWithTag(v45[1], 0);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( v40[1] )
    ExFreePoolWithTag(v40[1], 0);
  return (unsigned int)SymbolicLink;
}

```

## disassembly

```asm
0x14000ecbc  push    rbp
0x14000ecbe  push    rbx
0x14000ecbf  push    rsi
0x14000ecc0  push    rdi
0x14000ecc1  push    r12
0x14000ecc3  push    r13
0x14000ecc5  push    r14
0x14000ecc7  push    r15
0x14000ecc9  lea     rbp, [rsp-1Fh]
0x14000ecce  sub     rsp, 0E8h
0x14000ecd5  xorps   xmm1, xmm1
0x14000ecd8  mov     [rbp+57h+arg_18], 0
0x14000ecdc  xorps   xmm0, xmm0
0x14000ecdf  mov     [rbp+57h+var_B0], 0
0x14000ece7  mov     rdi, rdx
0x14000ecea  mov     [rsp+120h+var_D8], 0
0x14000ecf3  mov     edx, 0C8h
0x14000ecf8  mov     [rsp+120h+var_E0], 0
0x14000ed01  mov     ebx, r8d
0x14000ed04  mov     [rbp+57h+var_D0], 0
0x14000ed0c  mov     r15, rcx
0x14000ed0f  mov     r8d, 41746E4Dh
0x14000ed15  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x14000ed19  lea     ecx, [rdx+3Ah]
0x14000ed1c  mov     word ptr [rbp+57h+var_A0+2], dx
0x14000ed20  movups  xmmword ptr [rbp+57h+P], xmm0
0x14000ed24  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x14000ed28  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x14000ed2c  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x14000ed30  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x14000ed34  call    cs:__imp_ExAllocatePool2
0x14000ed3b  nop     dword ptr [rax+rax+00h]
0x14000ed40  mov     [rbp+57h+var_A0+8], rax
0x14000ed44  test    rax, rax
0x14000ed47  jnz     short loc_14000ED83
0x14000ed49  mov     edi, 0C000009Ah
0x14000ed4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed55  lea     rbx, WPP_GLOBAL_Control
0x14000ed5c  cmp     rcx, rbx
0x14000ed5f  jz      loc_14000F08C
0x14000ed65  mov     eax, [rcx+2Ch]
0x14000ed68  test    al, 4
0x14000ed6a  jz      loc_14000F08C
0x14000ed70  mov     rcx, [rcx+18h]
0x14000ed74  mov     edx, 112h
0x14000ed79  call    WPP_SF_
0x14000ed7e  jmp     loc_14000F08C
0x14000ed83  lea     rax, [rbp+57h+String1]
0x14000ed87  mov     r8d, ebx; int
0x14000ed8a  mov     [rsp+120h+ObjectName], rax; ObjectName
0x14000ed8f  lea     r9, [rbp+57h+P]; int
0x14000ed93  lea     rax, [rbp+57h+var_60]
0x14000ed97  mov     rdx, rdi; int
0x14000ed9a  mov     rcx, r15; int
0x14000ed9d  mov     [rsp+120h+var_100], rax; __int64
0x14000eda2  call    MountMgrVolumeMountPointChanged
0x14000eda7  mov     edi, eax
0x14000eda9  cmp     eax, 103h
0x14000edae  jnz     short loc_14000EDB7
0x14000edb0  xor     edi, edi
0x14000edb2  jmp     loc_14000F08C
0x14000edb7  test    edi, edi
0x14000edb9  jns     short loc_14000EDF3
0x14000edbb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edc2  lea     rbx, WPP_GLOBAL_Control
0x14000edc9  cmp     rcx, rbx
0x14000edcc  jz      loc_14000F08C
0x14000edd2  mov     eax, [rcx+2Ch]
0x14000edd5  test    al, 1
0x14000edd7  jz      loc_14000F08C
0x14000eddd  mov     edx, 113h
0x14000ede2  mov     r9d, edi
0x14000ede5  mov     rcx, [rcx+18h]
0x14000ede9  call    WPP_SF_L
0x14000edee  jmp     loc_14000F08C
0x14000edf3  lea     r9, [rbp+57h+var_B0]
0x14000edf7  mov     rcx, r15
0x14000edfa  lea     rdx, [rbp+57h+P]
0x14000edfe  call    FindDeviceInfo
0x14000ee03  test    eax, eax
0x14000ee05  jns     loc_14000EEDE
0x14000ee0b  lea     rax, [rbp+57h+var_50]
0x14000ee0f  xor     r9d, r9d
0x14000ee12  mov     [rsp+120h+var_F0], rax
0x14000ee17  xor     r8d, r8d
0x14000ee1a  lea     rax, [rbp+57h+var_A0]
0x14000ee1e  xor     edx, edx
0x14000ee20  mov     [rsp+120h+ObjectName], rax
0x14000ee25  mov     rcx, r15
0x14000ee28  lea     rax, [rbp+57h+P]
0x14000ee2c  mov     [rsp+120h+var_100], rax
0x14000ee31  call    QueryVolumeName
0x14000ee36  test    eax, eax
0x14000ee38  jns     short loc_14000EE79
0x14000ee3a  lea     rdx, [rbp+57h+var_A0]
0x14000ee3e  lea     rcx, [rbp+57h+P]
0x14000ee42  call    MountMgrQuerySymbolicLink
0x14000ee47  mov     edi, eax
0x14000ee49  test    eax, eax
0x14000ee4b  jns     short loc_14000EE79
0x14000ee4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee54  lea     rbx, WPP_GLOBAL_Control
0x14000ee5b  cmp     rcx, rbx
0x14000ee5e  jz      loc_14000F08C
0x14000ee64  mov     eax, [rcx+2Ch]
0x14000ee67  test    al, 1
0x14000ee69  jz      loc_14000F08C
0x14000ee6f  mov     edx, 114h
0x14000ee74  jmp     loc_14000EDE2
0x14000ee79  mov     rcx, [rbp+57h+P+8]; P
0x14000ee7d  xor     edx, edx; Tag
0x14000ee7f  call    cs:__imp_ExFreePoolWithTag
0x14000ee86  nop     dword ptr [rax+rax+00h]
0x14000ee8b  movaps  xmm0, xmmword ptr [rbp+57h+var_A0]
0x14000ee8f  lea     r9, [rbp+57h+var_B0]
0x14000ee93  lea     rdx, [rbp+57h+P]
0x14000ee97  movdqa  xmmword ptr [rbp+57h+P], xmm0
0x14000ee9c  mov     rcx, r15
0x14000ee9f  mov     [rbp+57h+var_A0+8], 0
0x14000eea7  call    FindDeviceInfo
0x14000eeac  mov     edi, eax
0x14000eeae  test    eax, eax
0x14000eeb0  jns     short loc_14000EEDE
0x14000eeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eeb9  lea     rbx, WPP_GLOBAL_Control
0x14000eec0  cmp     rcx, rbx
0x14000eec3  jz      loc_14000F08C
0x14000eec9  mov     eax, [rcx+2Ch]
0x14000eecc  test    al, 1
0x14000eece  jz      loc_14000F08C
0x14000eed4  mov     edx, 115h
0x14000eed9  jmp     loc_14000EDE2
0x14000eede  lea     r9, [rsp+120h+var_D8]
0x14000eee3  mov     rcx, r15
0x14000eee6  lea     rdx, [rbp+57h+String1]
0x14000eeea  call    FindDeviceInfo
0x14000eeef  mov     edi, eax
0x14000eef1  test    eax, eax
0x14000eef3  jns     short loc_14000EF21
0x14000eef5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eefc  lea     rbx, WPP_GLOBAL_Control
0x14000ef03  cmp     rcx, rbx
0x14000ef06  jz      loc_14000F08C
0x14000ef0c  mov     eax, [rcx+2Ch]
0x14000ef0f  test    al, 1
0x14000ef11  jz      loc_14000F08C
0x14000ef17  mov     edx, 116h
0x14000ef1c  jmp     loc_14000EDE2
0x14000ef21  mov     rax, [rsp+120h+var_D8]
0x14000ef26  lea     r9, [rsp+120h+var_E0]
0x14000ef2b  mov     r14, [r15+150h]
0x14000ef32  lea     r8, [rbp+57h+arg_18]
0x14000ef36  mov     r13, [rbp+57h+var_B0]
0x14000ef3a  mov     dl, 1
0x14000ef3c  mov     rcx, r13
0x14000ef3f  mov     [rbp+57h+var_70], r14
0x14000ef43  mov     r12, [rax+0B0h]
0x14000ef4a  mov     [rbp+57h+var_68], r12
0x14000ef4e  call    OpenRemoteDatabase
0x14000ef53  cmp     [rbp+57h+arg_18], 0
0x14000ef57  mov     edi, eax
0x14000ef59  jz      short loc_14000EF87
0x14000ef5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef62  lea     rbx, WPP_GLOBAL_Control
0x14000ef69  cmp     rcx, rbx
0x14000ef6c  jz      loc_14000F08C
0x14000ef72  mov     eax, [rcx+2Ch]
0x14000ef75  test    al, 1
0x14000ef77  jz      loc_14000F08C
0x14000ef7d  mov     edx, 117h
0x14000ef82  jmp     loc_14000EDE2
0x14000ef87  mov     rdx, [rsp+120h+var_E0]
0x14000ef8c  test    rdx, rdx
0x14000ef8f  jnz     short loc_14000EFC8
0x14000ef91  mov     edi, 0C000009Ah
0x14000ef96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef9d  lea     rbx, WPP_GLOBAL_Control
0x14000efa4  cmp     rcx, rbx
0x14000efa7  jz      loc_14000F09E
0x14000efad  mov     eax, [rcx+2Ch]
0x14000efb0  test    al, 1
0x14000efb2  jz      loc_14000F09E
0x14000efb8  mov     edx, 118h
0x14000efbd  mov     r9d, 0C000009Ah
0x14000efc3  jmp     loc_14000EDE5
0x14000efc8  xor     ebx, ebx
0x14000efca  xor     r8d, r8d
0x14000efcd  jmp     short loc_14000F035
0x14000efcf  mov     rsi, [rbp+57h+var_D0]
0x14000efd3  test    rsi, rsi
0x14000efd6  jz      loc_14000F400
0x14000efdc  movzx   eax, word ptr [rsi+0Ah]
0x14000efe0  lea     rdx, [rbp+57h+String2]; String2
0x14000efe4  mov     [rbp+57h+String2.MaximumLength], ax
0x14000efe8  lea     rcx, [rbp+57h+String1]; String1
0x14000efec  mov     [rbp+57h+String2.Length], ax
0x14000eff0  mov     r8b, 1; CaseInSensitive
0x14000eff3  movzx   eax, word ptr [rsi+8]
0x14000eff7  add     rax, rsi
0x14000effa  mov     [rbp+57h+String2.Buffer], rax
0x14000effe  call    cs:__imp_RtlEqualUnicodeString
0x14000f005  nop     dword ptr [rax+rax+00h]
0x14000f00a  test    al, al
0x14000f00c  jnz     loc_14000F111
0x14000f012  add     ebx, [rsi]
0x14000f014  xor     edx, edx; Tag
0x14000f016  mov     rcx, rsi; P
0x14000f019  call    cs:__imp_ExFreePoolWithTag
0x14000f020  nop     dword ptr [rax+rax+00h]
0x14000f025  mov     rdx, [rsp+120h+var_E0]
0x14000f02a  mov     r8d, ebx
0x14000f02d  mov     [rbp+57h+var_D0], 0
0x14000f035  lea     r9, [rbp+57h+var_D0]
0x14000f039  mov     rcx, r13
0x14000f03c  call    GetRemoteDatabaseEntry
0x14000f041  mov     edi, eax
0x14000f043  test    eax, eax
0x14000f045  jns     short loc_14000EFCF
0x14000f047  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f04e  lea     rbx, WPP_GLOBAL_Control
0x14000f055  cmp     rcx, rbx
0x14000f058  jz      short loc_14000F072
0x14000f05a  mov     eax, [rcx+2Ch]
0x14000f05d  test    al, 1
0x14000f05f  jz      short loc_14000F072
0x14000f061  mov     rcx, [rcx+18h]
0x14000f065  mov     edx, 119h
0x14000f06a  mov     r9d, edi
0x14000f06d  call    WPP_SF_L
0x14000f072  mov     rsi, [rbp+57h+var_D0]
0x14000f076  test    rsi, rsi
0x14000f079  jz      short loc_14000F08C
0x14000f07b  xor     edx, edx; Tag
0x14000f07d  mov     rcx, rsi; P
0x14000f080  call    cs:__imp_ExFreePoolWithTag
0x14000f087  nop     dword ptr [rax+rax+00h]
0x14000f08c  mov     rdx, [rsp+120h+var_E0]
0x14000f091  test    rdx, rdx
0x14000f094  jz      short loc_14000F09E
0x14000f096  mov     rcx, r15
0x14000f099  call    CloseFileHandleOutsideExtensionMutexLock
0x14000f09e  mov     rcx, [rbp+57h+var_50+8]; P
0x14000f0a2  test    rcx, rcx
0x14000f0a5  jz      short loc_14000F0B5
0x14000f0a7  xor     edx, edx; Tag
0x14000f0a9  call    cs:__imp_ExFreePoolWithTag
0x14000f0b0  nop     dword ptr [rax+rax+00h]
0x14000f0b5  mov     rcx, [rbp+57h+var_60+8]; P
0x14000f0b9  test    rcx, rcx
0x14000f0bc  jz      short loc_14000F0CC
0x14000f0be  xor     edx, edx; Tag
0x14000f0c0  call    cs:__imp_ExFreePoolWithTag
0x14000f0c7  nop     dword ptr [rax+rax+00h]
0x14000f0cc  mov     rcx, [rbp+57h+P+8]; P
0x14000f0d0  test    rcx, rcx
0x14000f0d3  jz      short loc_14000F0E3
0x14000f0d5  xor     edx, edx; Tag
0x14000f0d7  call    cs:__imp_ExFreePoolWithTag
0x14000f0de  nop     dword ptr [rax+rax+00h]
0x14000f0e3  mov     rcx, [rbp+57h+var_A0+8]; P
0x14000f0e7  test    rcx, rcx
0x14000f0ea  jz      short loc_14000F0FA
0x14000f0ec  xor     edx, edx; Tag
0x14000f0ee  call    cs:__imp_ExFreePoolWithTag
0x14000f0f5  nop     dword ptr [rax+rax+00h]
0x14000f0fa  mov     eax, edi
0x14000f0fc  add     rsp, 0E8h
0x14000f103  pop     r15
0x14000f105  pop     r14
0x14000f107  pop     r13
0x14000f109  pop     r12
0x14000f10b  pop     rdi
0x14000f10c  pop     rsi
0x14000f10d  pop     rbx
0x14000f10e  pop     rbp
0x14000f10f  retn
0x14000f111  add     dword ptr [rsi+4], 0FFFFFFFFh
0x14000f115  mov     r8d, ebx
0x14000f118  mov     rdx, [rsp+120h+var_E0]
0x14000f11d  mov     rcx, r13
0x14000f120  jz      short loc_14000F131
0x14000f122  mov     r9, rsi
0x14000f125  call    WriteRemoteDatabaseEntry
0x14000f12a  mov     edi, eax
0x14000f12c  jmp     loc_14000F243
0x14000f131  call    DeleteRemoteDatabaseEntry
0x14000f136  mov     edi, eax
0x14000f138  test    eax, eax
0x14000f13a  jns     short loc_14000F174
0x14000f13c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f143  lea     rbx, WPP_GLOBAL_Control
0x14000f14a  cmp     rcx, rbx
0x14000f14d  jz      loc_14000F076
0x14000f153  mov     eax, [rcx+2Ch]
0x14000f156  test    al, 1
0x14000f158  jz      loc_14000F076
0x14000f15e  mov     edx, 11Bh
0x14000f163  mov     rcx, [rcx+18h]
0x14000f167  mov     r9d, edi
0x14000f16a  call    WPP_SF_L
  ... truncated ...
```
