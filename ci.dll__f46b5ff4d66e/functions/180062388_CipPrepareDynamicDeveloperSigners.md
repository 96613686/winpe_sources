# CipPrepareDynamicDeveloperSigners

- ea: `0x180062388`
- end: `0x18006287a`
- name: `CipPrepareDynamicDeveloperSigners`
- size: `1266`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006f584`

## callees

- `0x18000cf38`
- `0x18002bef0`
- `0x18002c040`
- `0x18002c340`
- `0x180062388`
- `0x180078190`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062574`
- `ntoskrnl!ExAllocatePool2` at `0x180062623`
- `ntoskrnl!ExAllocatePool2` at `0x1800626ca`
- `ntoskrnl!ExAllocatePool2` at `0x180062756`
- `ntoskrnl!ExAllocatePool2` at `0x180062574`
- `ntoskrnl!ExAllocatePool2` at `0x180062623`
- `ntoskrnl!ExAllocatePool2` at `0x1800626ca`
- `ntoskrnl!ExAllocatePool2` at `0x180062756`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062559`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800626af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800627f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062812`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062841`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062559`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800626af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800627f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062812`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062841`
- `ntoskrnl!ZwClose` at `0x180062828`
- `ntoskrnl!ZwClose` at `0x180062828`
- `ntoskrnl!ZwOpenKey` at `0x1800624d9`
- `ntoskrnl!ZwOpenKey` at `0x1800624d9`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062519`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800625aa`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006266f`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062705`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062519`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800625aa`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006266f`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062705`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180062434`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180062434`

## string_xrefs

- `0x1800623d8`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\CI\Developer\DeveloperUnlockCertificates`

## pseudocode

```c
__int64 __fastcall CipPrepareDynamicDeveloperSigners(unsigned int *a1, _QWORD *a2)
{
  _DWORD *v2; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  _WORD *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // r12d
  ULONG i; // esi
  NTSTATUS v8; // eax
  _DWORD *Pool2; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  ULONG v12; // r15d
  ULONG v13; // r14d
  NTSTATUS v14; // eax
  _DWORD *v15; // rax
  unsigned int v16; // ebx
  void *v17; // rax
  __int64 v18; // r15
  unsigned int j; // r14d
  void *v20; // rcx
  ULONG Length; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pulResult; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v27; // [rsp+5Ch] [rbp-A4h]
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v29; // [rsp+70h] [rbp-90h]
  _QWORD *v30; // [rsp+78h] [rbp-88h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[528]; // [rsp+B0h] [rbp-50h] BYREF

  v30 = a2;
  v29 = a1;
  memset(v32, 0, 0x20Au);
  v26 = 0;
  KeyHandle = 0;
  v24 = 0;
  pulResult = 0;
  v28 = 0;
  v2 = 0;
  Length = 0;
  memset(&ObjectAttributes, 0, 44);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIDeveloperCerts",
                             0,
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\Developer\\DeveloperUnlockCertificates",
                             0,
                             v32,
                             522,
                             &v26);
  if ( PersistedStateLocation < 0 )
    goto LABEL_51;
  v4 = v32;
  v28 = 0;
  v5 = 0x7FFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  PersistedStateLocation = v5 == 0 ? 0xC000000D : 0;
  if ( !v5 )
    goto LABEL_51;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  LOWORD(v28) = -2 - 2 * v5;
  WORD1(v28) = -2 * v5;
  *((_QWORD *)&v28 + 1) = v32;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v28;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
  {
    PersistedStateLocation = 0;
    goto LABEL_51;
  }
  v6 = 0;
  for ( i = 0; ; ++i )
  {
    v8 = ZwEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, v2, Length, &Length);
    PersistedStateLocation = v8;
    if ( v8 >= 0 )
      goto LABEL_17;
    if ( v8 == -2147483622 )
      break;
    if ( v8 != -1073741789 && v8 != -2147483643 )
      goto LABEL_51;
    if ( v2 )
      ExFreePoolWithTag(v2, 0x63734943u);
    Pool2 = (_DWORD *)ExAllocatePool2(258, Length, 1668499779);
    v2 = Pool2;
    if ( !Pool2 )
    {
      PersistedStateLocation = -1073741670;
      goto LABEL_51;
    }
    PersistedStateLocation = ZwEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, Pool2, Length, &Length);
    if ( PersistedStateLocation < 0 )
      goto LABEL_51;
LABEL_17:
    if ( v2[1] == 3 )
    {
      if ( v2[4] )
      {
        v10 = (unsigned int)v2[3];
        if ( (_DWORD)v10 )
        {
          if ( (int)SIPolicyHashSizeToAlgorithm(v10, &v24) >= 0 )
            ++v6;
        }
      }
    }
  }
  PersistedStateLocation = RtlULongLongToULong(144LL * v6, &pulResult);
  if ( PersistedStateLocation < 0 )
    goto LABEL_51;
  v11 = (_QWORD *)ExAllocatePool2(256, pulResult, 1668499779);
  if ( !v11 )
  {
    PersistedStateLocation = -1073741801;
    goto LABEL_51;
  }
  v12 = 0;
  pulResult = 0;
  v13 = 0;
  while ( 2 )
  {
    v14 = ZwEnumerateValueKey(KeyHandle, v13, KeyValueFullInformation, v2, Length, &Length);
    PersistedStateLocation = v14;
    if ( v14 < 0 )
    {
      if ( v14 == -2147483622 )
      {
        PersistedStateLocation = 0;
        *v29 = v6;
        *v30 = v11;
        goto LABEL_51;
      }
      if ( v14 != -1073741789 && v14 != -2147483643 )
        goto LABEL_46;
      if ( v2 )
        ExFreePoolWithTag(v2, 0x63734943u);
      v15 = (_DWORD *)ExAllocatePool2(258, Length, 1668499779);
      v2 = v15;
      if ( !v15 )
      {
        PersistedStateLocation = -1073741670;
        goto LABEL_46;
      }
      PersistedStateLocation = ZwEnumerateValueKey(KeyHandle, v13, KeyValueFullInformation, v15, Length, &Length);
      if ( PersistedStateLocation < 0 )
        goto LABEL_46;
    }
    if ( v2[1] != 3 || !v2[4] || (v16 = v2[3]) == 0 || (int)SIPolicyHashSizeToAlgorithm(v16, &v24) < 0 )
    {
LABEL_42:
      ++v13;
      continue;
    }
    break;
  }
  v27 = v2[2];
  v17 = (void *)ExAllocatePool2(256, v16, 1668499779);
  v18 = 18LL * v12;
  v11[v18 + 2] = v17;
  if ( v17 )
  {
    memmove(v17, (char *)v2 + v27, v16);
    HIDWORD(v11[v18]) = v24;
    LODWORD(v11[v18 + 1]) = v16;
    v12 = ++pulResult;
    goto LABEL_42;
  }
  PersistedStateLocation = -1073741801;
LABEL_46:
  for ( j = 0; j < v6; ++j )
  {
    v20 = (void *)v11[18 * j + 2];
    if ( v20 )
      ExFreePoolWithTag(v20, 0x63734943u);
  }
  ExFreePoolWithTag(v11, 0x63734943u);
LABEL_51:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x63734943u);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x180062388  mov     [rsp-8+arg_10], rbx
0x18006238d  push    rbp
0x18006238e  push    rsi
0x18006238f  push    rdi
0x180062390  push    r12
0x180062392  push    r13
0x180062394  push    r14
0x180062396  push    r15
0x180062398  lea     rbp, [rsp-1D0h]
0x1800623a0  sub     rsp, 2D0h
0x1800623a7  mov     rax, cs:__security_cookie
0x1800623ae  xor     rax, rsp
0x1800623b1  mov     [rbp+200h+var_40], rax
0x1800623b8  mov     [rsp+300h+var_288], rdx
0x1800623bd  mov     ebx, 20Ah
0x1800623c2  mov     [rsp+300h+var_290], rcx
0x1800623c7  mov     r8d, ebx; Size
0x1800623ca  xor     edx, edx; Val
0x1800623cc  lea     rcx, [rbp+200h+var_250]; void *
0x1800623d0  call    memset
0x1800623d5  xor     r13d, r13d
0x1800623d8  lea     r8, aRegistryMachin_5; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1800623df  xorps   xmm0, xmm0
0x1800623e2  mov     [rsp+300h+var_2A8], r13d
0x1800623e7  xor     eax, eax
0x1800623e9  mov     [rsp+300h+KeyHandle], r13
0x1800623ee  lea     rax, [rsp+300h+var_2A8]
0x1800623f3  mov     [rsp+300h+var_2B8], r13d
0x1800623f8  mov     [rsp+300h+var_2D0], rax
0x1800623fd  lea     rcx, aCidevelopercer; "CIDeveloperCerts"
0x180062404  lea     rax, [rbp+200h+var_250]
0x180062408  mov     dword ptr [rsp+300h+ResultLength], ebx
0x18006240c  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x180062410  xor     r9d, r9d
0x180062413  mov     qword ptr [rsp+300h+Length], rax
0x180062418  xor     edx, edx
0x18006241a  mov     [rsp+300h+pulResult], r13d
0x18006241f  movups  [rsp+300h+var_2A0], xmm0
0x180062424  mov     edi, r13d
0x180062427  mov     [rsp+300h+var_2C0], r13d
0x18006242c  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x180062430  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x180062434  call    cs:__imp_RtlGetPersistedStateLocation
0x18006243b  nop     dword ptr [rax+rax+00h]
0x180062440  mov     ebx, eax
0x180062442  test    eax, eax
0x180062444  js      loc_18006281E
0x18006244a  xorps   xmm0, xmm0
0x18006244d  lea     rax, [rbp+200h+var_250]
0x180062451  movups  [rsp+300h+var_2A0], xmm0
0x180062456  mov     ecx, 7FFFh
0x18006245b  lea     edx, [r13+2]
0x18006245f  cmp     [rax], r13w
0x180062463  jz      short loc_18006246E
0x180062465  add     rax, rdx
0x180062468  sub     rcx, 1
0x18006246c  jnz     short loc_18006245F
0x18006246e  mov     rax, rcx
0x180062471  neg     rax
0x180062474  sbb     ebx, ebx
0x180062476  not     ebx
0x180062478  and     ebx, 0C000000Dh
0x18006247e  test    rcx, rcx
0x180062481  jz      loc_18006281E
0x180062487  add     cx, cx
0x18006248a  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x180062491  mov     eax, 0FFFEh
0x180062496  mov     [rbp+200h+ObjectAttributes.RootDirectory], r13
0x18006249a  sub     ax, cx
0x18006249d  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1800624a4  mov     word ptr [rsp+300h+var_2A0], ax
0x1800624a9  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1800624ad  add     ax, dx
0x1800624b0  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1800624b5  mov     word ptr [rsp+300h+var_2A0+2], ax
0x1800624ba  xorps   xmm0, xmm0
0x1800624bd  lea     rax, [rbp+200h+var_250]
0x1800624c1  mov     edx, 20019h; DesiredAccess
0x1800624c6  mov     qword ptr [rsp+300h+var_2A0+8], rax
0x1800624cb  lea     rax, [rsp+300h+var_2A0]
0x1800624d0  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1800624d4  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800624d9  call    cs:__imp_ZwOpenKey
0x1800624e0  nop     dword ptr [rax+rax+00h]
0x1800624e5  test    eax, eax
0x1800624e7  jns     short loc_1800624F1
0x1800624e9  mov     ebx, r13d
0x1800624ec  jmp     loc_18006281E
0x1800624f1  mov     r12d, r13d
0x1800624f4  mov     esi, r13d
0x1800624f7  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1800624fc  lea     rax, [rsp+300h+var_2C0]
0x180062501  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062506  mov     r9, rdi; KeyValueInformation
0x180062509  mov     eax, [rsp+300h+var_2C0]
0x18006250d  mov     r8d, 1; KeyValueInformationClass
0x180062513  mov     edx, esi; Index
0x180062515  mov     [rsp+300h+Length], eax; Length
0x180062519  call    cs:__imp_ZwEnumerateValueKey
0x180062520  nop     dword ptr [rax+rax+00h]
0x180062525  mov     ebx, eax
0x180062527  test    eax, eax
0x180062529  jns     loc_1800625C0
0x18006252f  cmp     eax, 8000001Ah
0x180062534  jz      loc_1800625F5
0x18006253a  cmp     eax, 0C0000023h
0x18006253f  jz      short loc_18006254C
0x180062541  cmp     eax, 80000005h
0x180062546  jnz     loc_18006281E
0x18006254c  test    rdi, rdi
0x18006254f  jz      short loc_180062565
0x180062551  mov     edx, 63734943h; Tag
0x180062556  mov     rcx, rdi; P
0x180062559  call    cs:__imp_ExFreePoolWithTag
0x180062560  nop     dword ptr [rax+rax+00h]
0x180062565  mov     edx, [rsp+300h+var_2C0]
0x180062569  mov     ecx, 102h
0x18006256e  mov     r8d, 63734943h
0x180062574  call    cs:__imp_ExAllocatePool2
0x18006257b  nop     dword ptr [rax+rax+00h]
0x180062580  mov     rdi, rax
0x180062583  test    rax, rax
0x180062586  jz      short loc_1800625EB
0x180062588  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x18006258d  lea     rax, [rsp+300h+var_2C0]
0x180062592  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062597  mov     r9, rdi; KeyValueInformation
0x18006259a  mov     eax, [rsp+300h+var_2C0]
0x18006259e  mov     r8d, 1; KeyValueInformationClass
0x1800625a4  mov     edx, esi; Index
0x1800625a6  mov     [rsp+300h+Length], eax; Length
0x1800625aa  call    cs:__imp_ZwEnumerateValueKey
0x1800625b1  nop     dword ptr [rax+rax+00h]
0x1800625b6  mov     ebx, eax
0x1800625b8  test    eax, eax
0x1800625ba  js      loc_18006281E
0x1800625c0  cmp     dword ptr [rdi+4], 3
0x1800625c4  jnz     short loc_1800625E4
0x1800625c6  cmp     [rdi+10h], r13d
0x1800625ca  jbe     short loc_1800625E4
0x1800625cc  mov     ecx, [rdi+0Ch]
0x1800625cf  test    ecx, ecx
0x1800625d1  jz      short loc_1800625E4
0x1800625d3  lea     rdx, [rsp+300h+var_2B8]
0x1800625d8  call    SIPolicyHashSizeToAlgorithm
0x1800625dd  test    eax, eax
0x1800625df  js      short loc_1800625E4
0x1800625e1  inc     r12d
0x1800625e4  inc     esi
0x1800625e6  jmp     loc_1800624F7
0x1800625eb  mov     ebx, 0C000009Ah
0x1800625f0  jmp     loc_18006281E
0x1800625f5  mov     eax, r12d
0x1800625f8  lea     rdx, [rsp+300h+pulResult]; pulResult
0x1800625fd  lea     rcx, [rax+rax*8]
0x180062601  shl     rcx, 4; ullOperand
0x180062605  call    RtlULongLongToULong
0x18006260a  mov     ebx, eax
0x18006260c  test    eax, eax
0x18006260e  js      loc_18006281E
0x180062614  mov     edx, [rsp+300h+pulResult]
0x180062618  mov     ecx, 100h
0x18006261d  mov     r8d, 63734943h
0x180062623  call    cs:__imp_ExAllocatePool2
0x18006262a  nop     dword ptr [rax+rax+00h]
0x18006262f  mov     rsi, rax
0x180062632  test    rax, rax
0x180062635  jnz     short loc_180062641
0x180062637  mov     ebx, 0C0000017h
0x18006263c  jmp     loc_18006281E
0x180062641  mov     r15d, r13d
0x180062644  mov     [rsp+300h+pulResult], r13d
0x180062649  mov     r14d, r13d
0x18006264c  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062651  lea     rax, [rsp+300h+var_2C0]
0x180062656  mov     [rsp+300h+ResultLength], rax; ResultLength
0x18006265b  mov     r9, rdi; KeyValueInformation
0x18006265e  mov     eax, [rsp+300h+var_2C0]
0x180062662  mov     r8d, 1; KeyValueInformationClass
0x180062668  mov     edx, r14d; Index
0x18006266b  mov     [rsp+300h+Length], eax; Length
0x18006266f  call    cs:__imp_ZwEnumerateValueKey
0x180062676  nop     dword ptr [rax+rax+00h]
0x18006267b  mov     ebx, eax
0x18006267d  test    eax, eax
0x18006267f  jns     loc_18006271B
0x180062685  cmp     eax, 8000001Ah
0x18006268a  jz      loc_1800627B5
0x180062690  cmp     eax, 0C0000023h
0x180062695  jz      short loc_1800626A2
0x180062697  cmp     eax, 80000005h
0x18006269c  jnz     loc_1800627D2
0x1800626a2  test    rdi, rdi
0x1800626a5  jz      short loc_1800626BB
0x1800626a7  mov     edx, 63734943h; Tag
0x1800626ac  mov     rcx, rdi; P
0x1800626af  call    cs:__imp_ExFreePoolWithTag
0x1800626b6  nop     dword ptr [rax+rax+00h]
0x1800626bb  mov     edx, [rsp+300h+var_2C0]
0x1800626bf  mov     ecx, 102h
0x1800626c4  mov     r8d, 63734943h
0x1800626ca  call    cs:__imp_ExAllocatePool2
0x1800626d1  nop     dword ptr [rax+rax+00h]
0x1800626d6  mov     rdi, rax
0x1800626d9  test    rax, rax
0x1800626dc  jz      loc_1800627AE
0x1800626e2  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1800626e7  lea     rax, [rsp+300h+var_2C0]
0x1800626ec  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1800626f1  mov     r9, rdi; KeyValueInformation
0x1800626f4  mov     eax, [rsp+300h+var_2C0]
0x1800626f8  mov     r8d, 1; KeyValueInformationClass
0x1800626fe  mov     edx, r14d; Index
0x180062701  mov     [rsp+300h+Length], eax; Length
0x180062705  call    cs:__imp_ZwEnumerateValueKey
0x18006270c  nop     dword ptr [rax+rax+00h]
0x180062711  mov     ebx, eax
0x180062713  test    eax, eax
0x180062715  js      loc_1800627D2
0x18006271b  cmp     dword ptr [rdi+4], 3
0x18006271f  jnz     loc_1800627A6
0x180062725  cmp     [rdi+10h], r13d
0x180062729  jbe     short loc_1800627A6
0x18006272b  mov     ebx, [rdi+0Ch]
0x18006272e  test    ebx, ebx
0x180062730  jz      short loc_1800627A6
0x180062732  lea     rdx, [rsp+300h+var_2B8]
0x180062737  mov     ecx, ebx
0x180062739  call    SIPolicyHashSizeToAlgorithm
0x18006273e  test    eax, eax
0x180062740  js      short loc_1800627A6
0x180062742  mov     eax, [rdi+8]
0x180062745  mov     r8d, 63734943h
0x18006274b  mov     edx, ebx
0x18006274d  mov     [rsp+300h+var_2A4], eax
0x180062751  mov     ecx, 100h
0x180062756  call    cs:__imp_ExAllocatePool2
0x18006275d  nop     dword ptr [rax+rax+00h]
0x180062762  mov     ecx, r15d
0x180062765  lea     r15, [rcx+rcx*8]
0x180062769  add     r15, r15
0x18006276c  mov     [rsi+r15*8+10h], rax
0x180062771  test    rax, rax
0x180062774  jz      short loc_1800627CA
0x180062776  mov     edx, [rsp+300h+var_2A4]
0x18006277a  mov     r8d, ebx; Size
0x18006277d  add     rdx, rdi; Src
0x180062780  mov     rcx, rax; void *
0x180062783  call    memmove
0x180062788  mov     eax, [rsp+300h+var_2B8]
0x18006278c  mov     [rsi+r15*8+4], eax
0x180062791  mov     [rsi+r15*8+8], ebx
0x180062796  mov     r15d, [rsp+300h+pulResult]
0x18006279b  inc     r15d
0x18006279e  mov     [rsp+300h+pulResult], r15d
0x1800627a3  xor     r13d, r13d
0x1800627a6  inc     r14d
0x1800627a9  jmp     loc_18006264C
0x1800627ae  mov     ebx, 0C000009Ah
0x1800627b3  jmp     short loc_1800627D2
0x1800627b5  mov     rax, [rsp+300h+var_290]
0x1800627ba  mov     ebx, r13d
0x1800627bd  mov     [rax], r12d
0x1800627c0  mov     rax, [rsp+300h+var_288]
0x1800627c5  mov     [rax], rsi
0x1800627c8  jmp     short loc_18006281E
0x1800627ca  mov     ebx, 0C0000017h
0x1800627cf  xor     r13d, r13d
0x1800627d2  mov     r15, rsi
0x1800627d5  mov     r14d, r13d
0x1800627d8  test    r12d, r12d
0x1800627db  jz      short loc_18006280A
0x1800627dd  mov     eax, r14d
0x1800627e0  lea     rcx, [rax+rax*8]
0x1800627e4  add     rcx, rcx
0x1800627e7  mov     rcx, [r15+rcx*8+10h]; P
0x1800627ec  test    rcx, rcx
0x1800627ef  jz      short loc_180062802
0x1800627f1  mov     edx, 63734943h; Tag
0x1800627f6  call    cs:__imp_ExFreePoolWithTag
0x1800627fd  nop     dword ptr [rax+rax+00h]
0x180062802  inc     r14d
0x180062805  cmp     r14d, r12d
0x180062808  jb      short loc_1800627DD
0x18006280a  mov     edx, 63734943h; Tag
0x18006280f  mov     rcx, rsi; P
0x180062812  call    cs:__imp_ExFreePoolWithTag
0x180062819  nop     dword ptr [rax+rax+00h]
0x18006281e  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x180062823  test    rcx, rcx
0x180062826  jz      short loc_180062834
0x180062828  call    cs:__imp_ZwClose
0x18006282f  nop     dword ptr [rax+rax+00h]
0x180062834  test    rdi, rdi
0x180062837  jz      short loc_18006284D
0x180062839  mov     edx, 63734943h; Tag
0x18006283e  mov     rcx, rdi; P
0x180062841  call    cs:__imp_ExFreePoolWithTag
0x180062848  nop     dword ptr [rax+rax+00h]
0x18006284d  mov     eax, ebx
  ... truncated ...
```
