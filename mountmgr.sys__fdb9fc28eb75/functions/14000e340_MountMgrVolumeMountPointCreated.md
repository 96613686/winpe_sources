# MountMgrVolumeMountPointCreated

- ea: `0x14000e340`
- end: `0x14000ebde`
- name: `MountMgrVolumeMountPointCreated`
- size: `2206`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x14000ebe4`

## callees

- `0x140001730`
- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x14000a810`
- `0x14000cd50`
- `0x14000db54`
- `0x14000e340`
- `0x14000fdb8`
- `0x140010600`
- `0x140010970`
- `0x140010d00`
- `0x140011500`
- `0x140012df0`
- `0x140012e60`
- `0x1400135a0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000e6bf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000eb7f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000e6bf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000eb7f`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3b6`
- `ntoskrnl!ExAllocatePool2` at `0x14000e887`
- `ntoskrnl!ExAllocatePool2` at `0x14000e982`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea91`
- `ntoskrnl!ExAllocatePool2` at `0x14000eaf8`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3b6`
- `ntoskrnl!ExAllocatePool2` at `0x14000e887`
- `ntoskrnl!ExAllocatePool2` at `0x14000e982`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea91`
- `ntoskrnl!ExAllocatePool2` at `0x14000eaf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e54c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e74f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e760`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e776`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e78d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e815`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e939`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e54c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e74f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e760`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e776`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e78d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e815`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e939`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeMountPointCreated(__int64 a1, int a2, int a3)
{
  _WORD *v6; // r12
  char *v7; // rsi
  __int64 v8; // r8
  int SymbolicLink; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int DeviceInfo; // eax
  unsigned int VolumeName; // eax
  __int64 v15; // r8
  int v16; // ebx
  __int64 v17; // r8
  __int64 v18; // rbx
  __int64 v19; // r13
  void *v20; // rdx
  __int64 i; // r8
  _DWORD *v22; // r15
  unsigned int v23; // ebx
  void *v24; // rcx
  __int64 v26; // r8
  unsigned int v27; // ebx
  __int64 Pool2; // rax
  unsigned __int16 *v29; // r15
  _QWORD *v30; // rax
  _QWORD *v31; // rdx
  __int64 v32; // rax
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rdx
  unsigned __int16 v35; // ax
  void *v36; // rax
  __int64 v37; // r13
  __int64 *v38; // rdi
  __int64 *v39; // r15
  __int64 **v40; // rax
  void *v41; // [rsp+40h] [rbp-89h] BYREF
  __int64 v42; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 *v43; // [rsp+50h] [rbp-79h] BYREF
  __int64 v44; // [rsp+58h] [rbp-71h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-69h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-59h] BYREF
  PVOID v47; // [rsp+80h] [rbp-49h] BYREF
  PVOID Src[2]; // [rsp+88h] [rbp-41h] BYREF
  PVOID v49[2]; // [rsp+A0h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-9h]
  __int64 v52; // [rsp+C8h] [rbp-1h]
  PVOID v53[2]; // [rsp+D0h] [rbp+7h] BYREF
  char v54; // [rsp+148h] [rbp+7Fh] BYREF

  v54 = 0;
  v42 = 0;
  v44 = 0;
  v47 = 0;
  v43 = 0;
  v49[0] = (PVOID)13107200;
  v41 = 0;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)Src = 0;
  String1 = 0;
  *(_OWORD *)v53 = 0;
  String2 = 0;
  v49[1] = (PVOID)ExAllocatePool2(258, 200, 1098149453);
  if ( !v49[1] )
  {
    SymbolicLink = -1073741670;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_54;
    v11 = 255;
LABEL_5:
    v12 = 3221225626LL;
LABEL_53:
    WPP_SF_L(v10->AttachedDevice, v11, v8, v12);
    goto LABEL_54;
  }
  SymbolicLink = MountMgrVolumeMountPointChanged(a1, a2, a3, (int)P, (__int64)Src, &String1);
  if ( SymbolicLink == 259 )
  {
    SymbolicLink = 0;
    goto LABEL_54;
  }
  if ( SymbolicLink < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_54;
    v11 = 256;
LABEL_52:
    v12 = (unsigned int)SymbolicLink;
    goto LABEL_53;
  }
  DeviceInfo = FindDeviceInfo(a1, P, v8, &v42);
  if ( DeviceInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 257, v8, (unsigned int)DeviceInfo);
    }
    VolumeName = QueryVolumeName(a1, 0, 0, 0, (__int64)P, (__int64)v49, (__int64)v53);
    v16 = VolumeName;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 258, v15, VolumeName);
    }
    if ( v16 < 0 )
    {
      SymbolicLink = MountMgrQuerySymbolicLink(P, v49);
      if ( SymbolicLink < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_54;
        v11 = 259;
        goto LABEL_52;
      }
    }
    ExFreePoolWithTag(P[1], 0);
    *(_OWORD *)P = *(_OWORD *)v49;
    v49[1] = 0;
    SymbolicLink = FindDeviceInfo(a1, P, v17, &v42);
    if ( SymbolicLink < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_54;
      v11 = 260;
      goto LABEL_52;
    }
  }
  SymbolicLink = FindDeviceInfo(a1, &String1, v8, &v44);
  if ( SymbolicLink < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_54;
    v11 = 261;
    goto LABEL_52;
  }
  v18 = v44;
  if ( !*(_BYTE *)(v44 + 133) )
    PostOnlineNotification(a1, v44 + 64);
  v19 = v42;
  v52 = *(_QWORD *)(a1 + 336);
  v51 = *(_QWORD *)(v18 + 176);
  SymbolicLink = OpenRemoteDatabase(v42, 1, &v54, &v41);
  if ( v54 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_54;
    v11 = 262;
    goto LABEL_52;
  }
  v20 = v41;
  if ( !v41 )
  {
    SymbolicLink = -1073741670;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_62;
    v11 = 263;
    goto LABEL_5;
  }
  LODWORD(v42) = 0;
  for ( i = 0; ; i = v23 )
  {
    SymbolicLink = GetRemoteDatabaseEntry(v19, v20, i, &v47);
    if ( SymbolicLink < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_54;
      v11 = 264;
      goto LABEL_52;
    }
    v22 = v47;
    if ( !v47 )
      break;
    String2.MaximumLength = *((_WORD *)v47 + 5);
    String2.Length = String2.MaximumLength;
    String2.Buffer = (PWSTR)((char *)v47 + *((unsigned __int16 *)v47 + 4));
    if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
    {
      ++v22[1];
      SymbolicLink = WriteRemoteDatabaseEntry(v19, v41, (unsigned int)v42, v22);
      ExFreePoolWithTag(v22, 0);
      goto LABEL_91;
    }
    LODWORD(v42) = *v22 + v42;
    v23 = v42;
    ExFreePoolWithTag(v22, 0);
    v20 = v41;
  }
  SymbolicLink = QueryUniqueId(&String1, &v43);
  if ( SymbolicLink >= 0 )
  {
    v6 = v43;
    v27 = *v43 + String1.Length + 16;
    Pool2 = ExAllocatePool2(258, v27, 1098149453);
    v29 = (unsigned __int16 *)Pool2;
    if ( !Pool2 )
    {
      SymbolicLink = -1073741670;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_54;
      v11 = 266;
      goto LABEL_5;
    }
    *(_DWORD *)Pool2 = v27;
    *(_DWORD *)(Pool2 + 4) = 1;
    *(_WORD *)(Pool2 + 8) = 16;
    *(_WORD *)(Pool2 + 10) = String1.Length;
    *(_WORD *)(Pool2 + 12) = *(_WORD *)(Pool2 + 8) + String1.Length;
    *(_WORD *)(Pool2 + 14) = *v6;
    memmove((void *)(Pool2 + *(unsigned __int16 *)(Pool2 + 8)), String1.Buffer, *(unsigned __int16 *)(Pool2 + 10));
    memmove((char *)v29 + v29[6], v6 + 1, v29[7]);
    SymbolicLink = AddRemoteDatabaseEntry(v19, v41, v29);
    ExFreePoolWithTag(v29, 0);
    if ( SymbolicLink < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_54;
      v11 = 267;
      goto LABEL_52;
    }
    v30 = (_QWORD *)ExAllocatePool2(258, 24, 1098149453);
    if ( !v30 )
    {
      SymbolicLink = -1073741670;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_54;
      v11 = 268;
      goto LABEL_5;
    }
    v30[2] = v6;
    v31 = *(_QWORD **)(v19 + 40);
    v6 = 0;
    if ( *v31 == v19 + 32 )
    {
      *v30 = v19 + 32;
      v30[1] = v31;
      *v31 = v30;
      *(_QWORD *)(v19 + 40) = v30;
LABEL_91:
      CloseFileHandleOutsideExtensionMutexLock(a1);
      v41 = 0;
      if ( SymbolicLink < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_62;
        v11 = 269;
        goto LABEL_52;
      }
      SymbolicLink = VerifyEpoch(a1, v52, v51);
      if ( SymbolicLink < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_54;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 270);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_54;
        v11 = 271;
        goto LABEL_52;
      }
      v32 = ExAllocatePool2(258, 40, 1098149453);
      v7 = (char *)v32;
      if ( !v32 )
      {
        SymbolicLink = -1073741670;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_54;
        v34 = 272;
        goto LABEL_107;
      }
      *(_WORD *)(v32 + 24) = Src[0];
      v35 = LOWORD(Src[0]) + 2;
      *((_WORD *)v7 + 13) = LOWORD(Src[0]) + 2;
      v36 = (void *)ExAllocatePool2(258, v35, 1098149453);
      *((_QWORD *)v7 + 4) = v36;
      if ( !v36 )
      {
        SymbolicLink = -1073741670;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_54;
        v34 = 273;
LABEL_107:
        WPP_SF_(v33->AttachedDevice, v34);
        goto LABEL_54;
      }
      memmove(v36, Src[1], LOWORD(Src[0]));
      *(_WORD *)(*((_QWORD *)v7 + 4) + 2 * ((unsigned __int64)LOWORD(Src[0]) >> 1)) = 0;
      *((_QWORD *)v7 + 2) = v19;
      v37 = v44;
      v38 = (__int64 *)(v44 + 48);
      v39 = *(__int64 **)(v44 + 48);
      if ( v39 != (__int64 *)(v44 + 48) )
      {
        do
        {
          if ( v39[2] == *((_QWORD *)v7 + 2)
            && RtlEqualUnicodeString((PCUNICODE_STRING)(v39 + 3), (PCUNICODE_STRING)(v7 + 24), 1u) )
          {
            break;
          }
          v39 = (__int64 *)*v39;
        }
        while ( v39 != v38 );
        v37 = v44;
        if ( v39 != v38 )
          goto LABEL_54;
      }
      v40 = (__int64 **)v38[1];
      if ( *v40 == v38 )
      {
        *(_QWORD *)v7 = v38;
        *((_QWORD *)v7 + 1) = v40;
        *v40 = (__int64 *)v7;
        v38[1] = (__int64)v7;
        v7 = 0;
        *(_QWORD *)(v37 + 176) = ++*(_QWORD *)(a1 + 336);
        goto LABEL_54;
      }
    }
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 265, v26, (unsigned int)SymbolicLink);
  v6 = v43;
LABEL_54:
  if ( v41 )
    CloseFileHandleOutsideExtensionMutexLock(a1);
  if ( v7 )
  {
    v24 = (void *)*((_QWORD *)v7 + 4);
    if ( v24 )
      ExFreePoolWithTag(v24, 0);
    ExFreePoolWithTag(v7, 0);
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
LABEL_62:
  if ( v53[1] )
    ExFreePoolWithTag(v53[1], 0);
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( v49[1] )
    ExFreePoolWithTag(v49[1], 0);
  return (unsigned int)SymbolicLink;
}

```

## disassembly

```asm
0x14000e340  push    rbp
0x14000e342  push    rbx
0x14000e343  push    rsi
0x14000e344  push    rdi
0x14000e345  push    r12
0x14000e347  push    r13
0x14000e349  push    r14
0x14000e34b  push    r15
0x14000e34d  lea     rbp, [rsp-1Fh]
0x14000e352  sub     rsp, 0E8h
0x14000e359  xor     eax, eax
0x14000e35b  xorps   xmm1, xmm1
0x14000e35e  xorps   xmm0, xmm0
0x14000e361  mov     [rbp+57h+arg_18], al
0x14000e364  mov     rdi, rdx
0x14000e367  mov     [rsp+120h+var_D8], rax
0x14000e36c  mov     edx, 0C8h
0x14000e371  mov     [rbp+57h+var_C8], rax
0x14000e375  mov     ebx, r8d
0x14000e378  mov     [rbp+57h+var_A0], rax
0x14000e37c  mov     r14, rcx
0x14000e37f  mov     [rbp+57h+var_D0], rax
0x14000e383  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x14000e387  lea     r13d, [rdx+3Ah]
0x14000e38b  mov     [rsp+120h+var_E0], rax
0x14000e390  mov     ecx, r13d
0x14000e393  mov     word ptr [rbp+57h+var_80+2], dx
0x14000e397  mov     r8d, 41746E4Dh
0x14000e39d  mov     r12d, eax
0x14000e3a0  mov     esi, eax
0x14000e3a2  movups  xmmword ptr [rbp+57h+P], xmm0
0x14000e3a6  movups  xmmword ptr [rbp+57h+Src], xmm1
0x14000e3aa  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x14000e3ae  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x14000e3b2  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x14000e3b6  call    cs:__imp_ExAllocatePool2
0x14000e3bd  nop     dword ptr [rax+rax+00h]
0x14000e3c2  xor     r15d, r15d
0x14000e3c5  mov     [rbp+57h+var_80+8], rax
0x14000e3c9  test    rax, rax
0x14000e3cc  jnz     short loc_14000E404
0x14000e3ce  mov     ebx, 0C000009Ah
0x14000e3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3da  lea     rdi, WPP_GLOBAL_Control
0x14000e3e1  cmp     rcx, rdi
0x14000e3e4  jz      loc_14000E72D
0x14000e3ea  mov     eax, [rcx+2Ch]
0x14000e3ed  test    al, 1
0x14000e3ef  jz      loc_14000E72D
0x14000e3f5  lea     edx, [r13-3]
0x14000e3f9  mov     r9d, 0C000009Ah
0x14000e3ff  jmp     loc_14000E724
0x14000e404  lea     rax, [rbp+57h+String1]
0x14000e408  mov     r8d, ebx; int
0x14000e40b  mov     [rsp+120h+ObjectName], rax; ObjectName
0x14000e410  lea     r9, [rbp+57h+P]; int
0x14000e414  lea     rax, [rbp+57h+Src]
0x14000e418  mov     rdx, rdi; int
0x14000e41b  mov     rcx, r14; int
0x14000e41e  mov     [rsp+120h+var_100], rax; __int64
0x14000e423  call    MountMgrVolumeMountPointChanged
0x14000e428  mov     ebx, eax
0x14000e42a  cmp     eax, 103h
0x14000e42f  jnz     short loc_14000E439
0x14000e431  mov     ebx, r15d
0x14000e434  jmp     loc_14000E72D
0x14000e439  test    ebx, ebx
0x14000e43b  jns     short loc_14000E469
0x14000e43d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e444  lea     rdi, WPP_GLOBAL_Control
0x14000e44b  cmp     rcx, rdi
0x14000e44e  jz      loc_14000E72D
0x14000e454  mov     eax, [rcx+2Ch]
0x14000e457  test    al, 1
0x14000e459  jz      loc_14000E72D
0x14000e45f  mov     edx, 100h
0x14000e464  jmp     loc_14000E721
0x14000e469  lea     r9, [rsp+120h+var_D8]
0x14000e46e  mov     rcx, r14
0x14000e471  lea     rdx, [rbp+57h+P]
0x14000e475  call    FindDeviceInfo
0x14000e47a  lea     rdi, WPP_GLOBAL_Control
0x14000e481  test    eax, eax
0x14000e483  jns     loc_14000E5A1
0x14000e489  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e490  cmp     rcx, rdi
0x14000e493  jz      short loc_14000E4B4
0x14000e495  mov     edx, [rcx+2Ch]
0x14000e498  test    dl, 1
0x14000e49b  jz      short loc_14000E4B4
0x14000e49d  cmp     byte ptr [rcx+29h], 2
0x14000e4a1  jb      short loc_14000E4B4
0x14000e4a3  mov     rcx, [rcx+18h]
0x14000e4a7  mov     edx, 101h
0x14000e4ac  mov     r9d, eax
0x14000e4af  call    WPP_SF_L
0x14000e4b4  lea     rax, [rbp+57h+var_50]
0x14000e4b8  xor     r9d, r9d
0x14000e4bb  mov     [rsp+120h+var_F0], rax
0x14000e4c0  xor     r8d, r8d
0x14000e4c3  lea     rax, [rbp+57h+var_80]
0x14000e4c7  xor     edx, edx
0x14000e4c9  mov     [rsp+120h+ObjectName], rax
0x14000e4ce  mov     rcx, r14
0x14000e4d1  lea     rax, [rbp+57h+P]
0x14000e4d5  mov     [rsp+120h+var_100], rax
0x14000e4da  call    QueryVolumeName
0x14000e4df  mov     ebx, eax
0x14000e4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4e8  cmp     rcx, rdi
0x14000e4eb  jz      short loc_14000E50A
0x14000e4ed  mov     edx, [rcx+2Ch]
0x14000e4f0  test    dl, 1
0x14000e4f3  jz      short loc_14000E50A
0x14000e4f5  cmp     byte ptr [rcx+29h], 2
0x14000e4f9  jb      short loc_14000E50A
0x14000e4fb  mov     rcx, [rcx+18h]
0x14000e4ff  mov     edx, r13d
0x14000e502  mov     r9d, eax
0x14000e505  call    WPP_SF_L
0x14000e50a  test    ebx, ebx
0x14000e50c  jns     short loc_14000E546
0x14000e50e  lea     rdx, [rbp+57h+var_80]
0x14000e512  lea     rcx, [rbp+57h+P]
0x14000e516  call    MountMgrQuerySymbolicLink
0x14000e51b  mov     ebx, eax
0x14000e51d  test    eax, eax
0x14000e51f  jns     short loc_14000E546
0x14000e521  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e528  cmp     rcx, rdi
0x14000e52b  jz      loc_14000E72D
0x14000e531  mov     eax, [rcx+2Ch]
0x14000e534  test    al, 1
0x14000e536  jz      loc_14000E72D
0x14000e53c  mov     edx, 103h
0x14000e541  jmp     loc_14000E721
0x14000e546  mov     rcx, [rbp+57h+P+8]; P
0x14000e54a  xor     edx, edx; Tag
0x14000e54c  call    cs:__imp_ExFreePoolWithTag
0x14000e553  nop     dword ptr [rax+rax+00h]
0x14000e558  movaps  xmm0, xmmword ptr [rbp+57h+var_80]
0x14000e55c  lea     r9, [rsp+120h+var_D8]
0x14000e561  lea     rdx, [rbp+57h+P]
0x14000e565  movdqa  xmmword ptr [rbp+57h+P], xmm0
0x14000e56a  mov     rcx, r14
0x14000e56d  mov     [rbp+57h+var_80+8], r15
0x14000e571  call    FindDeviceInfo
0x14000e576  mov     ebx, eax
0x14000e578  test    eax, eax
0x14000e57a  jns     short loc_14000E5A1
0x14000e57c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e583  cmp     rcx, rdi
0x14000e586  jz      loc_14000E72D
0x14000e58c  mov     eax, [rcx+2Ch]
0x14000e58f  test    al, 1
0x14000e591  jz      loc_14000E72D
0x14000e597  mov     edx, 104h
0x14000e59c  jmp     loc_14000E721
0x14000e5a1  lea     r9, [rbp+57h+var_C8]
0x14000e5a5  mov     rcx, r14
0x14000e5a8  lea     rdx, [rbp+57h+String1]
0x14000e5ac  call    FindDeviceInfo
0x14000e5b1  mov     ebx, eax
0x14000e5b3  test    eax, eax
0x14000e5b5  jns     short loc_14000E5DC
0x14000e5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5be  cmp     rcx, rdi
0x14000e5c1  jz      loc_14000E72D
0x14000e5c7  mov     eax, [rcx+2Ch]
0x14000e5ca  test    al, 1
0x14000e5cc  jz      loc_14000E72D
0x14000e5d2  mov     edx, 105h
0x14000e5d7  jmp     loc_14000E721
0x14000e5dc  mov     rbx, [rbp+57h+var_C8]
0x14000e5e0  cmp     [rbx+85h], r15b
0x14000e5e7  jnz     short loc_14000E5F5
0x14000e5e9  lea     rdx, [rbx+40h]
0x14000e5ed  mov     rcx, r14
0x14000e5f0  call    PostOnlineNotification
0x14000e5f5  mov     rax, [r14+150h]
0x14000e5fc  lea     r9, [rsp+120h+var_E0]
0x14000e601  mov     r13, [rsp+120h+var_D8]
0x14000e606  lea     r8, [rbp+57h+arg_18]
0x14000e60a  mov     [rbp+57h+var_58], rax
0x14000e60e  mov     dl, 1
0x14000e610  mov     rax, [rbx+0B0h]
0x14000e617  mov     rcx, r13
0x14000e61a  mov     [rbp+57h+var_60], rax
0x14000e61e  call    OpenRemoteDatabase
0x14000e623  mov     ebx, eax
0x14000e625  cmp     [rbp+57h+arg_18], r15b
0x14000e629  jz      short loc_14000E650
0x14000e62b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e632  cmp     rcx, rdi
0x14000e635  jz      loc_14000E72D
0x14000e63b  mov     eax, [rcx+2Ch]
0x14000e63e  test    al, 1
0x14000e640  jz      loc_14000E72D
0x14000e646  mov     edx, 106h
0x14000e64b  jmp     loc_14000E721
0x14000e650  mov     rdx, [rsp+120h+var_E0]
0x14000e655  test    rdx, rdx
0x14000e658  jnz     short loc_14000E684
0x14000e65a  mov     ebx, 0C000009Ah
0x14000e65f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e666  cmp     rcx, rdi
0x14000e669  jz      loc_14000E782
0x14000e66f  mov     eax, [rcx+2Ch]
0x14000e672  test    al, 1
0x14000e674  jz      loc_14000E782
0x14000e67a  mov     edx, 107h
0x14000e67f  jmp     loc_14000E3F9
0x14000e684  mov     dword ptr [rsp+120h+var_D8], r15d
0x14000e689  xor     r8d, r8d
0x14000e68c  jmp     short loc_14000E6F7
0x14000e68e  mov     r15, [rbp+57h+var_A0]
0x14000e692  lea     rcx, [rbp+57h+String1]; String1
0x14000e696  test    r15, r15
0x14000e699  jz      loc_14000E82C
0x14000e69f  movzx   eax, word ptr [r15+0Ah]
0x14000e6a4  lea     rdx, [rbp+57h+String2]; String2
0x14000e6a8  mov     [rbp+57h+String2.MaximumLength], ax
0x14000e6ac  mov     r8b, 1; CaseInSensitive
0x14000e6af  mov     [rbp+57h+String2.Length], ax
0x14000e6b3  movzx   eax, word ptr [r15+8]
0x14000e6b8  add     rax, r15
0x14000e6bb  mov     [rbp+57h+String2.Buffer], rax
0x14000e6bf  call    cs:__imp_RtlEqualUnicodeString
0x14000e6c6  nop     dword ptr [rax+rax+00h]
0x14000e6cb  test    al, al
0x14000e6cd  jnz     loc_14000E7F5
0x14000e6d3  mov     ebx, dword ptr [rsp+120h+var_D8]
0x14000e6d7  xor     edx, edx; Tag
0x14000e6d9  add     ebx, [r15]
0x14000e6dc  mov     rcx, r15; P
0x14000e6df  mov     dword ptr [rsp+120h+var_D8], ebx
0x14000e6e3  call    cs:__imp_ExFreePoolWithTag
0x14000e6ea  nop     dword ptr [rax+rax+00h]
0x14000e6ef  mov     rdx, [rsp+120h+var_E0]
0x14000e6f4  mov     r8d, ebx
0x14000e6f7  lea     r9, [rbp+57h+var_A0]
0x14000e6fb  mov     rcx, r13
0x14000e6fe  call    GetRemoteDatabaseEntry
0x14000e703  mov     ebx, eax
0x14000e705  test    eax, eax
0x14000e707  jns     short loc_14000E68E
0x14000e709  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e710  cmp     rcx, rdi
0x14000e713  jz      short loc_14000E72D
0x14000e715  mov     eax, [rcx+2Ch]
0x14000e718  test    al, 1
0x14000e71a  jz      short loc_14000E72D
0x14000e71c  mov     edx, 108h
0x14000e721  mov     r9d, ebx
0x14000e724  mov     rcx, [rcx+18h]
0x14000e728  call    WPP_SF_L
0x14000e72d  mov     rdx, [rsp+120h+var_E0]
0x14000e732  test    rdx, rdx
0x14000e735  jz      short loc_14000E73F
0x14000e737  mov     rcx, r14
0x14000e73a  call    CloseFileHandleOutsideExtensionMutexLock
0x14000e73f  test    rsi, rsi
0x14000e742  jz      short loc_14000E76C
0x14000e744  mov     rcx, [rsi+20h]; P
0x14000e748  test    rcx, rcx
0x14000e74b  jz      short loc_14000E75B
0x14000e74d  xor     edx, edx; Tag
0x14000e74f  call    cs:__imp_ExFreePoolWithTag
0x14000e756  nop     dword ptr [rax+rax+00h]
0x14000e75b  xor     edx, edx; Tag
0x14000e75d  mov     rcx, rsi; P
0x14000e760  call    cs:__imp_ExFreePoolWithTag
0x14000e767  nop     dword ptr [rax+rax+00h]
0x14000e76c  test    r12, r12
0x14000e76f  jz      short loc_14000E782
0x14000e771  xor     edx, edx; Tag
0x14000e773  mov     rcx, r12; P
0x14000e776  call    cs:__imp_ExFreePoolWithTag
0x14000e77d  nop     dword ptr [rax+rax+00h]
0x14000e782  mov     rcx, [rbp+57h+var_50+8]; P
0x14000e786  test    rcx, rcx
0x14000e789  jz      short loc_14000E799
0x14000e78b  xor     edx, edx; Tag
0x14000e78d  call    cs:__imp_ExFreePoolWithTag
0x14000e794  nop     dword ptr [rax+rax+00h]
0x14000e799  mov     rcx, [rbp+57h+Src+8]; P
0x14000e79d  test    rcx, rcx
0x14000e7a0  jz      short loc_14000E7B0
0x14000e7a2  xor     edx, edx; Tag
0x14000e7a4  call    cs:__imp_ExFreePoolWithTag
0x14000e7ab  nop     dword ptr [rax+rax+00h]
0x14000e7b0  mov     rcx, [rbp+57h+P+8]; P
0x14000e7b4  test    rcx, rcx
0x14000e7b7  jz      short loc_14000E7C7
0x14000e7b9  xor     edx, edx; Tag
0x14000e7bb  call    cs:__imp_ExFreePoolWithTag
0x14000e7c2  nop     dword ptr [rax+rax+00h]
0x14000e7c7  mov     rcx, [rbp+57h+var_80+8]; P
0x14000e7cb  test    rcx, rcx
0x14000e7ce  jz      short loc_14000E7DE
  ... truncated ...
```
