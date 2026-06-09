# ReadDeviceNodeNameValue

- ea: `0x18004d110`
- end: `0x18004d5c3`
- name: `ReadDeviceNodeNameValue`
- size: `1203`
- prototype: `NTSTATUS __fastcall(__int64, const GUID *, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ce70`

## callees

- `0x18000b7bc`
- `0x180019bd0`
- `0x180019d00`
- `0x18001a000`
- `0x18004d110`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d350`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d58e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d350`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d58e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d36e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d3d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d36e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d3d0`
- `ntoskrnl!RtlStringFromGUID` at `0x18004d1df`
- `ntoskrnl!RtlStringFromGUID` at `0x18004d1df`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d402`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d50d`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d402`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d50d`
- `ntoskrnl!ZwClose` at `0x18004d579`
- `ntoskrnl!ZwClose` at `0x18004d579`
- `ntoskrnl!ZwOpenKey` at `0x18004d3b0`
- `ntoskrnl!ZwOpenKey` at `0x18004d3b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004d561`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004d561`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d4ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d4ba`

## string_xrefs

- `0x18004d20e`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\`

## pseudocode

```c
NTSTATUS __fastcall ReadDeviceNodeNameValue(__int64 a1, const GUID *a2, void *a3, void *a4)
{
  NTSTATUS result; // eax
  __int64 v8; // r10
  __int64 v9; // rcx
  const wchar_t *v10; // r8
  __int64 v11; // rdx
  WCHAR *v12; // rax
  WCHAR *v13; // rcx
  __int64 v14; // rcx
  WCHAR *v15; // rax
  __int64 v16; // rdx
  const wchar_t *v17; // r8
  bool v18; // zf
  __int64 v19; // rax
  __int64 v20; // rcx
  WCHAR *v21; // rdx
  WCHAR *v22; // rcx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  int v25; // edi
  wchar_t *Buffer; // rax
  __int64 v27; // rbx
  WCHAR *v28; // rdx
  WCHAR *v29; // rcx
  int v30; // edx
  NTSTATUS v31; // ebx
  ULONG v32; // esi
  size_t v33; // rbx
  _DWORD *PoolWithTag; // rax
  _DWORD *v35; // rdi
  unsigned int v36; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING GuidString; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SourceString[184]; // [rsp+A0h] [rbp-60h] BYREF

  KeyHandle = 0;
  memset(SourceString, 0, 354);
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  ResultLength = 0;
  GuidString = 0;
  DestinationString = 0;
  if ( !a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        10,
        (__int64)WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids);
    }
    return -1073741811;
  }
  result = RtlStringFromGUID(a2, &GuidString);
  if ( result < 0 )
    return result;
  v8 = 2147483646;
  if ( !a3 )
  {
    v9 = 2147483646;
    v10 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\";
    v11 = 177;
    v12 = SourceString;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
  }
  v14 = 177;
  v15 = SourceString;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = 177 - v14;
  if ( v14 )
  {
    v17 = L"MediaCategories\\";
    v19 = v14;
    v18 = v16 == 177;
    v20 = 2147483646;
    v21 = &SourceString[v16];
    if ( !v18 )
    {
      do
      {
        if ( !v20 )
          break;
        if ( !*v17 )
          break;
        *v21++ = *v17++;
        --v20;
        --v19;
      }
      while ( v19 );
    }
    v22 = v21 - 1;
    if ( v19 )
      v22 = v21;
    *v22 = 0;
  }
  v23 = 177;
  v24 = SourceString;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = -1073741811;
  if ( !v23 )
  {
    RtlFreeUnicodeString(&GuidString);
    return v25;
  }
  Buffer = GuidString.Buffer;
  v27 = v23;
  v28 = &SourceString[177 - v23];
  do
  {
    if ( !v8 )
      break;
    if ( !*Buffer )
      break;
    *v28++ = *Buffer++;
    --v8;
    --v27;
  }
  while ( v27 );
  v29 = v28 - 1;
  v25 = -2147483643;
  if ( v27 )
  {
    v29 = v28;
    v25 = 0;
  }
  *v29 = 0;
  RtlFreeUnicodeString(&GuidString);
  if ( !v27 )
    return v25;
  RtlInitUnicodeString(&GuidString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &GuidString;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Name");
    v31 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            &KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( (int)(v31 + 0x80000000) < 0 || v31 == -2147483643 )
    {
      v32 = *(_DWORD *)(*(_QWORD *)(a1 + 184) + 8LL);
      if ( v32 )
      {
        if ( v32 >= ResultLength - 12 )
        {
          if ( a4 )
          {
            v33 = ResultLength;
            PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, ResultLength, 0x766E534Bu);
            v35 = PoolWithTag;
            if ( PoolWithTag )
            {
              if ( !ExPoolZeroingNativelySupported )
                memset(PoolWithTag, 0, v33);
              v31 = ZwQueryValueKey(
                      KeyHandle,
                      &DestinationString,
                      KeyValuePartialInformation,
                      v35,
                      ResultLength,
                      &ResultLength);
              if ( v31 >= 0 )
              {
                if ( v32 >= ResultLength - 12 )
                {
                  v36 = v35[2];
                  if ( v36 >= 2 && v35[1] == 1 )
                  {
                    memmove(a4, v35 + 3, v36);
                    *(_QWORD *)(a1 + 56) = (unsigned int)v35[2];
                  }
                  else
                  {
                    v31 = -1073741823;
                  }
                }
                else
                {
                  v31 = -1073741789;
                }
              }
              ExFreePoolWithTag(v35, 0);
            }
            else
            {
              v31 = -1073741670;
            }
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v30) = 2;
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v30,
                1,
                11,
                (__int64)WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids);
            }
            v31 = -1073741811;
          }
        }
        else
        {
          v31 = -1073741789;
        }
      }
      else
      {
        v31 = -2147483643;
        *(_QWORD *)(a1 + 56) = ResultLength - 12;
      }
    }
    ZwClose(KeyHandle);
    return v31;
  }
  return result;
}

```

## disassembly

```asm
0x18004d110  push    rbp
0x18004d112  push    rbx
0x18004d113  push    rsi
0x18004d114  push    r14
0x18004d116  push    r15
0x18004d118  lea     rbp, [rsp-130h]
0x18004d120  sub     rsp, 230h
0x18004d127  mov     rax, cs:__security_cookie
0x18004d12e  xor     rax, rsp
0x18004d131  mov     [rbp+150h+var_40], rax
0x18004d138  xorps   xmm0, xmm0
0x18004d13b  xor     eax, eax
0x18004d13d  mov     rsi, r8
0x18004d140  mov     [rsp+250h+KeyHandle], rax
0x18004d145  mov     rbx, rdx
0x18004d148  mov     [rbp+150h+SourceString], ax
0x18004d14c  mov     r14, rcx
0x18004d14f  xor     edx, edx; Val
0x18004d151  movups  xmmword ptr [rsp+250h+ObjectAttributes.ObjectName], xmm0
0x18004d156  mov     r8d, 160h; Size
0x18004d15c  lea     rcx, [rbp+150h+var_1AE]; void *
0x18004d160  movups  xmmword ptr [rsp+250h+ObjectAttributes+1Ch], xmm0
0x18004d165  mov     r15, r9
0x18004d168  movups  xmmword ptr [rsp+250h+ObjectAttributes.Length], xmm0
0x18004d16d  movups  [rbp+150h+KeyValueInformation], xmm0
0x18004d171  call    memset
0x18004d176  mov     [rsp+250h+var_220], 0
0x18004d17e  xorps   xmm0, xmm0
0x18004d181  xorps   xmm1, xmm1
0x18004d184  movups  xmmword ptr [rsp+250h+GuidString.Length], xmm0
0x18004d189  movups  xmmword ptr [rsp+250h+DestinationString.Length], xmm1
0x18004d18e  test    rbx, rbx
0x18004d191  jnz     short loc_18004D1D7
0x18004d193  lea     rax, WPP_RECORDER_INITIALIZED
0x18004d19a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004d1a1  jz      short loc_18004D1CD
0x18004d1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1aa  lea     rax, WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids
0x18004d1b1  mov     r9d, 0Ah
0x18004d1b7  mov     qword ptr [rsp+250h+Length], rax
0x18004d1bc  mov     r8d, 1
0x18004d1c2  mov     dl, 2
0x18004d1c4  mov     rcx, [rcx+40h]
0x18004d1c8  call    WPP_RECORDER_SF_
0x18004d1cd  mov     eax, 0C000000Dh
0x18004d1d2  jmp     loc_18004D5A4
0x18004d1d7  lea     rdx, [rsp+250h+GuidString]; GuidString
0x18004d1dc  mov     rcx, rbx; Guid
0x18004d1df  call    cs:__imp_RtlStringFromGUID
0x18004d1e6  nop     dword ptr [rax+rax+00h]
0x18004d1eb  test    eax, eax
0x18004d1ed  js      loc_18004D5A4
0x18004d1f3  mov     [rsp+250h+var_28], rdi
0x18004d1fb  mov     ebx, 0B1h
0x18004d200  mov     r10d, 7FFFFFFEh
0x18004d206  test    rsi, rsi
0x18004d209  jnz     short loc_18004D254
0x18004d20b  mov     ecx, r10d
0x18004d20e  lea     r8, aRegistryMachin_3; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18004d215  mov     edx, ebx
0x18004d217  lea     rax, [rbp+150h+SourceString]
0x18004d21b  nop     dword ptr [rax+rax+00h]
0x18004d220  test    rcx, rcx
0x18004d223  jz      short loc_18004D244
0x18004d225  movzx   r9d, word ptr [r8]
0x18004d229  test    r9w, r9w
0x18004d22d  jz      short loc_18004D244
0x18004d22f  mov     [rax], r9w
0x18004d233  add     r8, 2
0x18004d237  add     rax, 2
0x18004d23b  dec     rcx
0x18004d23e  sub     rdx, 1
0x18004d242  jnz     short loc_18004D220
0x18004d244  test    rdx, rdx
0x18004d247  lea     rcx, [rax-2]
0x18004d24b  cmovnz  rcx, rax
0x18004d24f  xor     eax, eax
0x18004d251  mov     [rcx], ax
0x18004d254  mov     rcx, rbx
0x18004d257  lea     rax, [rbp+150h+SourceString]
0x18004d25b  nop     dword ptr [rax+rax+00h]
0x18004d260  cmp     word ptr [rax], 0
0x18004d264  jz      short loc_18004D270
0x18004d266  add     rax, 2
0x18004d26a  sub     rcx, 1
0x18004d26e  jnz     short loc_18004D260
0x18004d270  xor     eax, eax
0x18004d272  mov     rdx, rbx
0x18004d275  sub     rdx, rcx
0x18004d278  test    rcx, rcx
0x18004d27b  cmovz   rdx, rax
0x18004d27f  jz      short loc_18004D2CC
0x18004d281  mov     rax, rbx
0x18004d284  lea     r8, aMediacategorie; "MediaCategories\\"
0x18004d28b  sub     rax, rdx
0x18004d28e  mov     rcx, r10
0x18004d291  lea     rdx, [rbp+rdx*2+150h+SourceString]
0x18004d296  jz      short loc_18004D2BC
0x18004d298  test    rcx, rcx
0x18004d29b  jz      short loc_18004D2BC
0x18004d29d  movzx   r9d, word ptr [r8]
0x18004d2a1  test    r9w, r9w
0x18004d2a5  jz      short loc_18004D2BC
0x18004d2a7  mov     [rdx], r9w
0x18004d2ab  add     r8, 2
0x18004d2af  add     rdx, 2
0x18004d2b3  dec     rcx
0x18004d2b6  sub     rax, 1
0x18004d2ba  jnz     short loc_18004D298
0x18004d2bc  test    rax, rax
0x18004d2bf  lea     rcx, [rdx-2]
0x18004d2c3  cmovnz  rcx, rdx
0x18004d2c7  xor     eax, eax
0x18004d2c9  mov     [rcx], ax
0x18004d2cc  mov     rcx, rbx
0x18004d2cf  lea     rax, [rbp+150h+SourceString]
0x18004d2d3  cmp     word ptr [rax], 0
0x18004d2d7  jz      short loc_18004D2E3
0x18004d2d9  add     rax, 2
0x18004d2dd  sub     rcx, 1
0x18004d2e1  jnz     short loc_18004D2D3
0x18004d2e3  xor     eax, eax
0x18004d2e5  mov     edi, 0C000000Dh
0x18004d2ea  test    rcx, rcx
0x18004d2ed  mov     rdx, rbx
0x18004d2f0  cmovnz  edi, eax
0x18004d2f3  sub     rdx, rcx
0x18004d2f6  test    rcx, rcx
0x18004d2f9  cmovz   rdx, rax
0x18004d2fd  jz      loc_18004D589
0x18004d303  mov     rax, [rsp+250h+GuidString.Buffer]
0x18004d308  sub     rbx, rdx
0x18004d30b  lea     rdx, [rbp+rdx*2+150h+SourceString]
0x18004d310  jz      short loc_18004D333
0x18004d312  test    r10, r10
0x18004d315  jz      short loc_18004D333
0x18004d317  movzx   ecx, word ptr [rax]
0x18004d31a  test    cx, cx
0x18004d31d  jz      short loc_18004D333
0x18004d31f  mov     [rdx], cx
0x18004d322  add     rax, 2
0x18004d326  add     rdx, 2
0x18004d32a  dec     r10
0x18004d32d  sub     rbx, 1
0x18004d331  jnz     short loc_18004D312
0x18004d333  xor     eax, eax
0x18004d335  lea     rcx, [rdx-2]
0x18004d339  test    rbx, rbx
0x18004d33c  mov     edi, 80000005h
0x18004d341  cmovnz  rcx, rdx
0x18004d345  cmovnz  edi, eax
0x18004d348  mov     [rcx], ax
0x18004d34b  lea     rcx, [rsp+250h+GuidString]; UnicodeString
0x18004d350  call    cs:__imp_RtlFreeUnicodeString
0x18004d357  nop     dword ptr [rax+rax+00h]
0x18004d35c  test    rbx, rbx
0x18004d35f  jz      loc_18004D59A
0x18004d365  lea     rdx, [rbp+150h+SourceString]; SourceString
0x18004d369  lea     rcx, [rsp+250h+GuidString]; DestinationString
0x18004d36e  call    cs:__imp_RtlInitUnicodeString
0x18004d375  nop     dword ptr [rax+rax+00h]
0x18004d37a  lea     rax, [rsp+250h+GuidString]
0x18004d37f  mov     [rsp+250h+ObjectAttributes.Length], 30h ; '0'
0x18004d387  xorps   xmm0, xmm0
0x18004d38a  mov     [rsp+250h+ObjectAttributes.ObjectName], rax
0x18004d38f  lea     r8, [rsp+250h+ObjectAttributes]; ObjectAttributes
0x18004d394  mov     [rsp+250h+ObjectAttributes.RootDirectory], rsi
0x18004d399  mov     edx, 20019h; DesiredAccess
0x18004d39e  mov     [rsp+250h+ObjectAttributes.Attributes], 240h
0x18004d3a6  lea     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x18004d3ab  movdqu  xmmword ptr [rbp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d3b0  call    cs:__imp_ZwOpenKey
0x18004d3b7  nop     dword ptr [rax+rax+00h]
0x18004d3bc  test    eax, eax
0x18004d3be  js      loc_18004D59C
0x18004d3c4  lea     rdx, aName; "Name"
0x18004d3cb  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x18004d3d0  call    cs:__imp_RtlInitUnicodeString
0x18004d3d7  nop     dword ptr [rax+rax+00h]
0x18004d3dc  mov     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x18004d3e1  lea     rax, [rsp+250h+var_220]
0x18004d3e6  mov     [rsp+250h+ResultLength], rax; ResultLength
0x18004d3eb  lea     r9, [rbp+150h+KeyValueInformation]; KeyValueInformation
0x18004d3ef  mov     r8d, 2; KeyValueInformationClass
0x18004d3f5  mov     [rsp+250h+Length], 10h; Length
0x18004d3fd  lea     rdx, [rsp+250h+DestinationString]; ValueName
0x18004d402  call    cs:__imp_ZwQueryValueKey
0x18004d409  nop     dword ptr [rax+rax+00h]
0x18004d40e  mov     ebx, eax
0x18004d410  mov     eax, 80000000h
0x18004d415  lea     ecx, [rbx+rax]
0x18004d418  test    eax, ecx
0x18004d41a  jnz     short loc_18004D428
0x18004d41c  cmp     ebx, 80000005h
0x18004d422  jnz     loc_18004D574
0x18004d428  mov     rax, [r14+0B8h]
0x18004d42f  mov     esi, [rax+8]
0x18004d432  test    esi, esi
0x18004d434  jnz     short loc_18004D44B
0x18004d436  mov     ecx, [rsp+250h+var_220]
0x18004d43a  mov     ebx, 80000005h
0x18004d43f  add     ecx, 0FFFFFFF4h
0x18004d442  mov     [r14+38h], rcx
0x18004d446  jmp     loc_18004D574
0x18004d44b  mov     ecx, [rsp+250h+var_220]
0x18004d44f  lea     eax, [rcx-0Ch]
0x18004d452  cmp     esi, eax
0x18004d454  jnb     short loc_18004D460
0x18004d456  mov     ebx, 0C0000023h
0x18004d45b  jmp     loc_18004D574
0x18004d460  test    r15, r15
0x18004d463  jnz     short loc_18004D4A9
0x18004d465  lea     rax, WPP_RECORDER_INITIALIZED
0x18004d46c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004d473  jz      short loc_18004D49F
0x18004d475  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d47c  lea     rax, WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids
0x18004d483  mov     r9d, 0Bh
0x18004d489  mov     qword ptr [rsp+250h+Length], rax
0x18004d48e  mov     r8d, 1
0x18004d494  mov     dl, 2
0x18004d496  mov     rcx, [rcx+40h]
0x18004d49a  call    WPP_RECORDER_SF_
0x18004d49f  mov     ebx, 0C000000Dh
0x18004d4a4  jmp     loc_18004D574
0x18004d4a9  mov     rbx, rcx
0x18004d4ac  mov     rdx, rcx; NumberOfBytes
0x18004d4af  mov     ecx, 401h; PoolType
0x18004d4b4  mov     r8d, 766E534Bh; Tag
0x18004d4ba  call    cs:__imp_ExAllocatePoolWithTag
0x18004d4c1  nop     dword ptr [rax+rax+00h]
0x18004d4c6  mov     rdi, rax
0x18004d4c9  test    rax, rax
0x18004d4cc  jz      loc_18004D56F
0x18004d4d2  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18004d4d9  jnz     short loc_18004D4E8
0x18004d4db  mov     r8, rbx; Size
0x18004d4de  xor     edx, edx; Val
0x18004d4e0  mov     rcx, rax; void *
0x18004d4e3  call    memset
0x18004d4e8  mov     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x18004d4ed  lea     rax, [rsp+250h+var_220]
0x18004d4f2  mov     [rsp+250h+ResultLength], rax; ResultLength
0x18004d4f7  lea     rdx, [rsp+250h+DestinationString]; ValueName
0x18004d4fc  mov     eax, [rsp+250h+var_220]
0x18004d500  mov     r9, rdi; KeyValueInformation
0x18004d503  mov     r8d, 2; KeyValueInformationClass
0x18004d509  mov     [rsp+250h+Length], eax; Length
0x18004d50d  call    cs:__imp_ZwQueryValueKey
0x18004d514  nop     dword ptr [rax+rax+00h]
0x18004d519  mov     ebx, eax
0x18004d51b  test    eax, eax
0x18004d51d  js      short loc_18004D55C
0x18004d51f  mov     eax, [rsp+250h+var_220]
0x18004d523  add     eax, 0FFFFFFF4h
0x18004d526  cmp     esi, eax
0x18004d528  jnb     short loc_18004D531
0x18004d52a  mov     ebx, 0C0000023h
0x18004d52f  jmp     short loc_18004D55C
0x18004d531  mov     eax, [rdi+8]
0x18004d534  cmp     eax, 2
0x18004d537  jb      short loc_18004D557
0x18004d539  cmp     dword ptr [rdi+4], 1
0x18004d53d  jnz     short loc_18004D557
0x18004d53f  mov     r8d, eax; Size
0x18004d542  lea     rdx, [rdi+0Ch]; Src
0x18004d546  mov     rcx, r15; void *
0x18004d549  call    memmove
0x18004d54e  mov     eax, [rdi+8]
0x18004d551  mov     [r14+38h], rax
0x18004d555  jmp     short loc_18004D55C
0x18004d557  mov     ebx, 0C0000001h
0x18004d55c  xor     edx, edx; Tag
0x18004d55e  mov     rcx, rdi; P
0x18004d561  call    cs:__imp_ExFreePoolWithTag
0x18004d568  nop     dword ptr [rax+rax+00h]
0x18004d56d  jmp     short loc_18004D574
0x18004d56f  mov     ebx, 0C000009Ah
0x18004d574  mov     rcx, [rsp+250h+KeyHandle]; Handle
0x18004d579  call    cs:__imp_ZwClose
0x18004d580  nop     dword ptr [rax+rax+00h]
0x18004d585  mov     eax, ebx
0x18004d587  jmp     short loc_18004D59C
0x18004d589  lea     rcx, [rsp+250h+GuidString]; UnicodeString
0x18004d58e  call    cs:__imp_RtlFreeUnicodeString
0x18004d595  nop     dword ptr [rax+rax+00h]
0x18004d59a  mov     eax, edi
0x18004d59c  mov     rdi, [rsp+250h+var_28]
0x18004d5a4  mov     rcx, [rbp+150h+var_40]
0x18004d5ab  xor     rcx, rsp; StackCookie
0x18004d5ae  call    __security_check_cookie
0x18004d5b3  add     rsp, 230h
0x18004d5ba  pop     r15
0x18004d5bc  pop     r14
0x18004d5be  pop     rsi
0x18004d5bf  pop     rbx
0x18004d5c0  pop     rbp
0x18004d5c1  retn
```
