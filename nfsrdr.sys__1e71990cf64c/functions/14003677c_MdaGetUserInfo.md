# MdaGetUserInfo

- ea: `0x14003677c`
- end: `0x140036f29`
- name: `MdaGetUserInfo`
- size: `1965`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140025be0`

## callees

- `0x14000b680`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140036354`
- `0x14003677c`
- `0x140037244`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036873`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036a2f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036873`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036a2f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036860`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003689e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036a1c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036a53`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036860`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003689e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036a1c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036a53`
- `ntoskrnl!ZwOpenKey` at `0x1400368eb`
- `ntoskrnl!ZwOpenKey` at `0x1400368eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e9f`
- `ntoskrnl!ZwClose` at `0x140036936`
- `ntoskrnl!ZwClose` at `0x140036936`
- `ntoskrnl!ExAllocatePool2` at `0x1400367f7`
- `ntoskrnl!ExAllocatePool2` at `0x1400367f7`

## string_xrefs

- `0x140036d8b`: `MountType`
- `0x140036b82`: `DeleteSymlinks`
- `0x140036c23`: `DisplayAllLinks`
- `0x14003684a`: `\Registry\User\`
- `0x140036aad`: `Access`
- `0x140036b22`: `NFSReaddir`
- `0x140036b52`: `SymLinks`
- `0x140036bac`: `EUCMount`
- `0x140036c61`: `Mount`
- `0x140036ca5`: `ReadBuffer`
- `0x140036cde`: `WriteBuffer`
- `0x140036dd1`: `FileAttributeCache`
- `0x140036dc7`: `Cache`
- `0x140036e14`: `RemoteWriteCache`

## pseudocode

```c
__int64 __fastcall MdaGetUserInfo(void *a1, __int64 a2, __int64 a3, const UNICODE_STRING *a4, _DWORD *a5, __int64 a6)
{
  __int64 v6; // r13
  int v8; // r14d
  WCHAR *Pool2; // rax
  WCHAR *v10; // r12
  NTSTATUS appended; // eax
  __int64 v13; // rdi
  NTSTATUS v14; // eax
  NTSTATUS v15; // ebx
  int v16; // edx
  int v17; // r8d
  NTSTATUS v18; // ebx
  _DWORD *v19; // rcx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ecx
  BOOL v26; // eax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+38h] BYREF

  v30 = a2;
  KeyHandle = a1;
  v6 = *(_QWORD *)(a3 + 80);
  Destination = 0;
  LODWORD(v30) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids);
  v8 = 1024;
  Pool2 = (WCHAR *)ExAllocatePool2(258, 1024, 844260942);
  v10 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids);
    return 3221225626LL;
  }
  memset(Pool2, 0, 0x400u);
  *(_DWORD *)&Destination.Length = 20971520;
  Destination.Buffer = v10;
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\User\\");
  appended = RtlAppendUnicodeStringToString(&Destination, a4);
  v13 = a6;
  if ( appended < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids,
        (unsigned int)appended);
  }
  else
  {
    v14 = RtlAppendUnicodeToString(&Destination, L"\\SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default");
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids,
          (unsigned int)v14);
    }
    else
    {
      KeyHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &Destination;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_DZ(WPP_GLOBAL_Control->AttachedDevice, v16, v17, v15, (__int64)&Destination);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids,
            &Destination);
        }
        ZwClose(KeyHandle);
      }
    }
    if ( v15 >= 0 )
      goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids);
  Destination.Length = 0;
  RtlAppendUnicodeToString(&Destination, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\");
  v18 = RtlAppendUnicodeStringToString(&Destination, a4);
  if ( v18 < 0 )
    goto LABEL_97;
  v18 = RtlAppendUnicodeToString(&Destination, L"\\Default");
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids,
        (unsigned int)v18);
    goto LABEL_97;
  }
LABEL_35:
  v19 = a5;
  *a5 = *(_DWORD *)(v6 + 2332);
  v19[1] = *(_DWORD *)(v6 + 2336);
  v19[2] = 0;
  v18 = NfsReadUserRegistry(&Destination, 0, L"Access", &v30);
  if ( v18 < 0 )
    goto LABEL_97;
  *(_DWORD *)(v13 + 32) = v30;
  v18 = NfsReadUserRegistry(&Destination, 0, L"NFSLookup", &v30);
  if ( v18 < 0 )
    goto LABEL_97;
  if ( (_DWORD)v30 )
    *(_DWORD *)(v13 + 56) |= 0x80u;
  v18 = NfsReadUserRegistry(&Destination, 0, L"NFSReaddir", &v30);
  if ( v18 < 0 )
    goto LABEL_97;
  if ( (_DWORD)v30 )
    *(_DWORD *)(v13 + 56) |= 0x100u;
  v18 = NfsReadUserRegistry(&Destination, 0, L"SymLinks", &v30);
  if ( v18 < 0 )
    goto LABEL_97;
  if ( (_DWORD)v30 )
    *(_DWORD *)(v13 + 56) |= 0x200u;
  if ( (int)NfsReadUserRegistry(&Destination, 0, L"DeleteSymlinks", &v30) >= 0 && (_DWORD)v30 )
    *(_DWORD *)(v13 + 56) |= 0x1000u;
  if ( (int)NfsReadUserRegistry(&Destination, 0, L"EUCMount", &v30) >= 0
    && ((_DWORD)v30 == 64
     || (_DWORD)v30 == 0x2000
     || (_DWORD)v30 == 0x4000
     || (_DWORD)v30 == 0x8000
     || (_DWORD)v30 == 0x10000
     || (_DWORD)v30 == 0x20000
     || (_DWORD)v30 == 0x40000
     || (_DWORD)v30 == 0x80000) )
  {
    *(_DWORD *)(v13 + 56) |= v30;
  }
  LODWORD(v30) = 0;
  NfsReadUserRegistry(&Destination, 0, L"SecFlavors", &v30);
  v20 = v30 & 0xF;
  if ( (v30 & 0xF) == 0 )
    v20 = 15;
  LODWORD(v30) = v20;
  *(_DWORD *)(v13 + 60) = v20;
  if ( (int)NfsReadUserRegistry(&Destination, 0, L"DisplayAllLinks", &v30) >= 0 && (_DWORD)v30 )
    *(_DWORD *)(v13 + 56) |= 0x800u;
  v21 = NfsReadUserRegistry(&Destination, L"Mount", L"Locking", &v30);
  v18 = v21;
  if ( v21 >= 0 && !(_DWORD)v30 )
  {
    *(_DWORD *)(v13 + 56) &= ~1u;
    goto LABEL_67;
  }
  *(_DWORD *)(v13 + 56) |= 1u;
  if ( v21 >= 0 )
  {
LABEL_67:
    v18 = NfsReadUserRegistry(&Destination, L"Mount", L"ReadBuffer", &v30);
    if ( v18 >= 0 )
    {
      v22 = v30;
      if ( (unsigned int)v30 > 0x400 )
      {
        if ( (unsigned int)v30 >= 0x100000 )
          v22 = 0x100000;
      }
      else
      {
        v22 = 1024;
      }
      *(_DWORD *)(v13 + 12) = v22;
      v18 = NfsReadUserRegistry(&Destination, L"Mount", L"WriteBuffer", &v30);
      if ( v18 >= 0 )
      {
        v23 = v30;
        if ( (unsigned int)v30 > 0x400 )
        {
          if ( (unsigned int)v30 >= 0x100000 )
            v23 = 0x100000;
          v8 = v23;
        }
        *(_DWORD *)(v13 + 16) = v8;
        v18 = NfsReadUserRegistry(&Destination, L"Mount", L"Timeout", &v30);
        if ( v18 >= 0 )
        {
          v24 = v30;
          if ( (unsigned int)v30 > 1 )
          {
            if ( (unsigned int)v30 >= 0x270F )
              v24 = 9999;
          }
          else
          {
            v24 = 1;
          }
          *(_DWORD *)(v13 + 20) = v24;
          v18 = NfsReadUserRegistry(&Destination, L"Mount", L"Retransmissions", &v30);
          if ( v18 >= 0 )
          {
            v25 = 0;
            if ( (_DWORD)v30 )
              v25 = v30;
            if ( v25 >= 0x270F )
              v25 = 9999;
            *(_DWORD *)(v13 + 24) = v25;
            v18 = NfsReadUserRegistry(&Destination, L"Mount", L"MountType", &v30);
            if ( v18 >= 0 )
            {
              v26 = (unsigned int)v30 > 1;
              *(_DWORD *)(v13 + 56) |= 4u;
              *(_DWORD *)(v13 + 28) = v26 + 1;
              v18 = NfsReadUserRegistry(&Destination, L"Cache", L"FileAttributeCache", &v30);
              if ( v18 >= 0 )
              {
                if ( (_DWORD)v30 )
                  *(_DWORD *)(v13 + 56) |= 0x10u;
                v18 = NfsReadUserRegistry(&Destination, L"Cache", L"RemoteWriteCache", &v30);
                if ( v18 >= 0 )
                {
                  if ( (_DWORD)v30 )
                    *(_DWORD *)(v13 + 56) |= 8u;
                  v18 = NfsReadUserRegistry(&Destination, L"Cache", L"HashTableSize", &v30);
                  if ( v18 >= 0 )
                  {
                    *(_DWORD *)(v13 + 40) = v30;
                    v18 = NfsReadUserRegistry(&Destination, L"Cache", L"AttributeTimeDelta", &v30);
                    if ( v18 >= 0 )
                      *(_QWORD *)(v13 + 48) = (unsigned int)v30;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_97:
  ExFreePoolWithTag(v10, 0);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids,
        (unsigned int)v18);
    MdaGetDefaultMountInfo(v13);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14003677c  mov     rax, rsp
0x14003677f  mov     [rax+18h], rbx
0x140036783  mov     [rax+20h], rdi
0x140036787  mov     [rax+10h], rdx
0x14003678b  mov     [rax+8], rcx
0x14003678f  push    rbp
0x140036790  push    r12
0x140036792  push    r13
0x140036794  push    r14
0x140036796  push    r15
0x140036798  mov     rbp, rsp
0x14003679b  sub     rsp, 70h
0x14003679f  mov     r13, [r8+50h]
0x1400367a3  xorps   xmm0, xmm0
0x1400367a6  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1400367aa  mov     r15, r9
0x1400367ad  mov     dword ptr [rbp+arg_8], 0
0x1400367b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400367bb  lea     rbx, WPP_GLOBAL_Control
0x1400367c2  cmp     rcx, rbx
0x1400367c5  jz      short loc_1400367E3
0x1400367c7  mov     eax, [rcx+2Ch]
0x1400367ca  test    al, 8
0x1400367cc  jz      short loc_1400367E3
0x1400367ce  mov     rcx, [rcx+18h]
0x1400367d2  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x1400367d9  mov     edx, 0Ah
0x1400367de  call    WPP_SF_
0x1400367e3  mov     r14d, 400h
0x1400367e9  mov     r8d, 3252664Eh
0x1400367ef  mov     edx, r14d
0x1400367f2  mov     ecx, 102h
0x1400367f7  call    cs:__imp_ExAllocatePool2
0x1400367fe  nop     dword ptr [rax+rax+00h]
0x140036803  mov     r12, rax
0x140036806  test    rax, rax
0x140036809  jnz     short loc_14003683D
0x14003680b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036812  cmp     rcx, rbx
0x140036815  jz      short loc_140036833
0x140036817  mov     eax, [rcx+2Ch]
0x14003681a  test    al, 1
0x14003681c  jz      short loc_140036833
0x14003681e  mov     rcx, [rcx+18h]
0x140036822  lea     edx, [r12+0Bh]
0x140036827  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x14003682e  call    WPP_SF_
0x140036833  mov     eax, 0C000009Ah
0x140036838  jmp     loc_140036F0E
0x14003683d  mov     r8, r14; Size
0x140036840  xor     edx, edx; Val
0x140036842  mov     rcx, r12; void *
0x140036845  call    memset
0x14003684a  lea     rdx, aRegistryUser; "\\Registry\\User\\"
0x140036851  mov     dword ptr [rbp+Destination.Length], 1400000h
0x140036858  lea     rcx, [rbp+Destination]; Destination
0x14003685c  mov     [rbp+Destination.Buffer], r12
0x140036860  call    cs:__imp_RtlAppendUnicodeToString
0x140036867  nop     dword ptr [rax+rax+00h]
0x14003686c  mov     rdx, r15; Source
0x14003686f  lea     rcx, [rbp+Destination]; Destination
0x140036873  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003687a  nop     dword ptr [rax+rax+00h]
0x14003687f  mov     rdi, [rbp+arg_28]
0x140036883  mov     edx, 100000h
0x140036888  mov     r9d, eax
0x14003688b  test    eax, eax
0x14003688d  js      loc_1400369B8
0x140036893  lea     rdx, aSoftwareMicros; "\\SOFTWARE\\Microsoft\\ClientForNFS\\Cu"...
0x14003689a  lea     rcx, [rbp+Destination]; Destination
0x14003689e  call    cs:__imp_RtlAppendUnicodeToString
0x1400368a5  nop     dword ptr [rax+rax+00h]
0x1400368aa  xor     ecx, ecx
0x1400368ac  mov     ebx, eax
0x1400368ae  test    eax, eax
0x1400368b0  js      loc_140036975
0x1400368b6  mov     [rbp+KeyHandle], rcx
0x1400368ba  lea     rax, [rbp+Destination]
0x1400368be  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400368c2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400368c6  xorps   xmm0, xmm0
0x1400368c9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400368cd  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400368d1  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400368d9  mov     edx, 20019h; DesiredAccess
0x1400368de  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400368e6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400368eb  call    cs:__imp_ZwOpenKey
0x1400368f2  nop     dword ptr [rax+rax+00h]
0x1400368f7  mov     ebx, eax
0x1400368f9  test    eax, eax
0x1400368fb  js      short loc_140036944
0x1400368fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140036904  lea     rax, WPP_GLOBAL_Control
0x14003690b  cmp     rcx, rax
0x14003690e  jz      short loc_140036932
0x140036910  test    dword ptr [rcx+2Ch], 100000h
0x140036917  jz      short loc_140036932
0x140036919  mov     rcx, [rcx+18h]
0x14003691d  lea     r9, [rbp+Destination]
0x140036921  mov     edx, 0Ch
0x140036926  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x14003692d  call    WPP_SF_Z
0x140036932  mov     rcx, [rbp+KeyHandle]; Handle
0x140036936  call    cs:__imp_ZwClose
0x14003693d  nop     dword ptr [rax+rax+00h]
0x140036942  jmp     short loc_1400369A7
0x140036944  mov     rcx, cs:WPP_GLOBAL_Control
0x14003694b  lea     rax, WPP_GLOBAL_Control
0x140036952  cmp     rcx, rax
0x140036955  jz      short loc_1400369A7
0x140036957  mov     eax, [rcx+2Ch]
0x14003695a  test    al, 1
0x14003695c  jz      short loc_1400369A7
0x14003695e  mov     rcx, [rcx+18h]
0x140036962  lea     rax, [rbp+Destination]
0x140036966  mov     r9d, ebx
0x140036969  mov     [rsp+70h+var_50], rax
0x14003696e  call    WPP_SF_DZ
0x140036973  jmp     short loc_1400369A7
0x140036975  mov     rcx, cs:WPP_GLOBAL_Control
0x14003697c  lea     rax, WPP_GLOBAL_Control
0x140036983  cmp     rcx, rax
0x140036986  jz      short loc_1400369A7
0x140036988  mov     eax, [rcx+2Ch]
0x14003698b  test    al, 1
0x14003698d  jz      short loc_1400369A7
0x14003698f  mov     rcx, [rcx+18h]
0x140036993  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x14003699a  mov     edx, 0Eh
0x14003699f  mov     r9d, ebx
0x1400369a2  call    WPP_SF_d
0x1400369a7  test    ebx, ebx
0x1400369a9  jns     loc_140036AA3
0x1400369af  lea     rbx, WPP_GLOBAL_Control
0x1400369b6  jmp     short loc_1400369E0
0x1400369b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400369bf  cmp     rcx, rbx
0x1400369c2  jz      short loc_1400369E5
0x1400369c4  mov     eax, [rcx+2Ch]
0x1400369c7  test    al, 1
0x1400369c9  jz      short loc_1400369E5
0x1400369cb  mov     rcx, [rcx+18h]
0x1400369cf  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x1400369d6  mov     edx, 0Fh
0x1400369db  call    WPP_SF_d
0x1400369e0  mov     edx, 100000h
0x1400369e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400369ec  cmp     rcx, rbx
0x1400369ef  jz      short loc_140036A0B
0x1400369f1  test    [rcx+2Ch], edx
0x1400369f4  jz      short loc_140036A0B
0x1400369f6  mov     rcx, [rcx+18h]
0x1400369fa  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x140036a01  mov     edx, 10h
0x140036a06  call    WPP_SF_
0x140036a0b  xor     eax, eax
0x140036a0d  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x140036a14  lea     rcx, [rbp+Destination]; Destination
0x140036a18  mov     [rbp+Destination.Length], ax
0x140036a1c  call    cs:__imp_RtlAppendUnicodeToString
0x140036a23  nop     dword ptr [rax+rax+00h]
0x140036a28  mov     rdx, r15; Source
0x140036a2b  lea     rcx, [rbp+Destination]; Destination
0x140036a2f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140036a36  nop     dword ptr [rax+rax+00h]
0x140036a3b  xor     r15d, r15d
0x140036a3e  mov     ebx, eax
0x140036a40  test    eax, eax
0x140036a42  js      loc_140036E93
0x140036a48  lea     rdx, aDefault; "\\Default"
0x140036a4f  lea     rcx, [rbp+Destination]; Destination
0x140036a53  call    cs:__imp_RtlAppendUnicodeToString
0x140036a5a  nop     dword ptr [rax+rax+00h]
0x140036a5f  mov     ebx, eax
0x140036a61  test    eax, eax
0x140036a63  jns     short loc_140036AA6
0x140036a65  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a6c  lea     r14, WPP_GLOBAL_Control
0x140036a73  cmp     rcx, r14
0x140036a76  jz      loc_140036E9A
0x140036a7c  mov     eax, [rcx+2Ch]
0x140036a7f  test    al, 1
0x140036a81  jz      loc_140036E9A
0x140036a87  mov     rcx, [rcx+18h]
0x140036a8b  lea     edx, [r15+11h]
0x140036a8f  mov     r9d, ebx
0x140036a92  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x140036a99  call    WPP_SF_d
0x140036a9e  jmp     loc_140036E9A
0x140036aa3  xor     r15d, r15d
0x140036aa6  mov     eax, [r13+91Ch]
0x140036aad  lea     r8, aAccess; "Access"
0x140036ab4  mov     rcx, [rbp+arg_20]
0x140036ab8  xor     edx, edx; PCWSTR
0x140036aba  mov     [rcx], eax
0x140036abc  mov     eax, [r13+920h]
0x140036ac3  mov     [rcx+4], eax
0x140036ac6  lea     rax, [rbp+arg_8]
0x140036aca  mov     [rcx+8], r15d
0x140036ace  lea     rcx, [rbp+Destination]; SourceString
0x140036ad2  mov     [rsp+70h+var_50], rax; void *
0x140036ad7  call    NfsReadUserRegistry
0x140036adc  mov     ebx, eax
0x140036ade  test    eax, eax
0x140036ae0  js      loc_140036E93
0x140036ae6  mov     eax, dword ptr [rbp+arg_8]
0x140036ae9  lea     r8, aNfslookup; "NFSLookup"
0x140036af0  mov     [rdi+20h], eax
0x140036af3  lea     rcx, [rbp+Destination]; SourceString
0x140036af7  lea     rax, [rbp+arg_8]
0x140036afb  xor     edx, edx; PCWSTR
0x140036afd  mov     [rsp+70h+var_50], rax; void *
0x140036b02  call    NfsReadUserRegistry
0x140036b07  mov     ebx, eax
0x140036b09  test    eax, eax
0x140036b0b  js      loc_140036E93
0x140036b11  cmp     dword ptr [rbp+arg_8], r15d
0x140036b15  jz      short loc_140036B1C
0x140036b17  bts     dword ptr [rdi+38h], 7
0x140036b1c  lea     rax, [rbp+arg_8]
0x140036b20  xor     edx, edx; PCWSTR
0x140036b22  lea     r8, aNfsreaddir; "NFSReaddir"
0x140036b29  mov     [rsp+70h+var_50], rax; void *
0x140036b2e  lea     rcx, [rbp+Destination]; SourceString
0x140036b32  call    NfsReadUserRegistry
0x140036b37  mov     ebx, eax
0x140036b39  test    eax, eax
0x140036b3b  js      loc_140036E93
0x140036b41  cmp     dword ptr [rbp+arg_8], r15d
0x140036b45  jz      short loc_140036B4C
0x140036b47  bts     dword ptr [rdi+38h], 8
0x140036b4c  lea     rax, [rbp+arg_8]
0x140036b50  xor     edx, edx; PCWSTR
0x140036b52  lea     r8, aSymlinks; "SymLinks"
0x140036b59  mov     [rsp+70h+var_50], rax; void *
0x140036b5e  lea     rcx, [rbp+Destination]; SourceString
0x140036b62  call    NfsReadUserRegistry
0x140036b67  mov     ebx, eax
0x140036b69  test    eax, eax
0x140036b6b  js      loc_140036E93
0x140036b71  cmp     dword ptr [rbp+arg_8], r15d
0x140036b75  jz      short loc_140036B7C
0x140036b77  bts     dword ptr [rdi+38h], 9
0x140036b7c  lea     rax, [rbp+arg_8]
0x140036b80  xor     edx, edx; PCWSTR
0x140036b82  lea     r8, aDeletesymlinks; "DeleteSymlinks"
0x140036b89  mov     [rsp+70h+var_50], rax; void *
0x140036b8e  lea     rcx, [rbp+Destination]; SourceString
0x140036b92  call    NfsReadUserRegistry
0x140036b97  test    eax, eax
0x140036b99  js      short loc_140036BA6
0x140036b9b  cmp     dword ptr [rbp+arg_8], r15d
0x140036b9f  jz      short loc_140036BA6
0x140036ba1  bts     dword ptr [rdi+38h], 0Ch
0x140036ba6  lea     rax, [rbp+arg_8]
0x140036baa  xor     edx, edx; PCWSTR
0x140036bac  lea     r8, aEucmount; "EUCMount"
0x140036bb3  mov     [rsp+70h+var_50], rax; void *
0x140036bb8  lea     rcx, [rbp+Destination]; SourceString
0x140036bbc  call    NfsReadUserRegistry
0x140036bc1  test    eax, eax
0x140036bc3  js      short loc_140036C01
0x140036bc5  mov     eax, dword ptr [rbp+arg_8]
0x140036bc8  cmp     eax, 40h ; '@'
0x140036bcb  jz      short loc_140036BFE
0x140036bcd  cmp     eax, 2000h
0x140036bd2  jz      short loc_140036BFE
0x140036bd4  cmp     eax, 4000h
0x140036bd9  jz      short loc_140036BFE
0x140036bdb  cmp     eax, 8000h
0x140036be0  jz      short loc_140036BFE
0x140036be2  cmp     eax, 10000h
0x140036be7  jz      short loc_140036BFE
0x140036be9  cmp     eax, 20000h
0x140036bee  jz      short loc_140036BFE
0x140036bf0  cmp     eax, 40000h
0x140036bf5  jz      short loc_140036BFE
0x140036bf7  cmp     eax, 80000h
0x140036bfc  jnz     short loc_140036C01
0x140036bfe  or      [rdi+38h], eax
0x140036c01  lea     rax, [rbp+arg_8]
0x140036c05  mov     dword ptr [rbp+arg_8], r15d
0x140036c09  lea     r8, aSecflavors; "SecFlavors"
0x140036c10  mov     [rsp+70h+var_50], rax; void *
0x140036c15  xor     edx, edx; PCWSTR
0x140036c17  lea     rcx, [rbp+Destination]; SourceString
0x140036c1b  call    NfsReadUserRegistry
0x140036c20  mov     eax, dword ptr [rbp+arg_8]
0x140036c23  lea     r8, aDisplayalllink; "DisplayAllLinks"
0x140036c2a  mov     ecx, 0Fh
0x140036c2f  and     eax, ecx
0x140036c31  cmovz   eax, ecx
0x140036c34  xor     edx, edx; PCWSTR
0x140036c36  mov     dword ptr [rbp+arg_8], eax
0x140036c39  lea     rcx, [rbp+Destination]; SourceString
0x140036c3d  mov     [rdi+3Ch], eax
0x140036c40  lea     rax, [rbp+arg_8]
0x140036c44  mov     [rsp+70h+var_50], rax; void *
0x140036c49  call    NfsReadUserRegistry
  ... truncated ...
```
