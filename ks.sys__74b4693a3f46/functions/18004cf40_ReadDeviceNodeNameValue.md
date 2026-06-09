# ReadDeviceNodeNameValue

- ea: `0x18004cf40`
- end: `0x18004d3f3`
- name: `ReadDeviceNodeNameValue`
- size: `1203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004cca0`

## callees

- `0x18000b7bc`
- `0x180019b80`
- `0x180019cc0`
- `0x180019fc0`
- `0x18004cf40`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d180`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d3be`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d180`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d3be`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d19e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d200`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d19e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d200`
- `ntoskrnl!RtlStringFromGUID` at `0x18004d00f`
- `ntoskrnl!RtlStringFromGUID` at `0x18004d00f`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d232`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d33d`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d232`
- `ntoskrnl!ZwQueryValueKey` at `0x18004d33d`
- `ntoskrnl!ZwClose` at `0x18004d3a9`
- `ntoskrnl!ZwClose` at `0x18004d3a9`
- `ntoskrnl!ZwOpenKey` at `0x18004d1e0`
- `ntoskrnl!ZwOpenKey` at `0x18004d1e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004d391`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004d391`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d2ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d2ea`

## string_xrefs

- `0x18004d03e`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\`

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
        (__int64)WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids);
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
                (__int64)WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids);
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
0x18004cf40  push    rbp
0x18004cf42  push    rbx
0x18004cf43  push    rsi
0x18004cf44  push    r14
0x18004cf46  push    r15
0x18004cf48  lea     rbp, [rsp-130h]
0x18004cf50  sub     rsp, 230h
0x18004cf57  mov     rax, cs:__security_cookie
0x18004cf5e  xor     rax, rsp
0x18004cf61  mov     [rbp+150h+var_40], rax
0x18004cf68  xorps   xmm0, xmm0
0x18004cf6b  xor     eax, eax
0x18004cf6d  mov     rsi, r8
0x18004cf70  mov     [rsp+250h+KeyHandle], rax
0x18004cf75  mov     rbx, rdx
0x18004cf78  mov     [rbp+150h+SourceString], ax
0x18004cf7c  mov     r14, rcx
0x18004cf7f  xor     edx, edx; Val
0x18004cf81  movups  xmmword ptr [rsp+250h+ObjectAttributes.ObjectName], xmm0
0x18004cf86  mov     r8d, 160h; Size
0x18004cf8c  lea     rcx, [rbp+150h+var_1AE]; void *
0x18004cf90  movups  xmmword ptr [rsp+250h+ObjectAttributes+1Ch], xmm0
0x18004cf95  mov     r15, r9
0x18004cf98  movups  xmmword ptr [rsp+250h+ObjectAttributes.Length], xmm0
0x18004cf9d  movups  [rbp+150h+KeyValueInformation], xmm0
0x18004cfa1  call    memset
0x18004cfa6  mov     [rsp+250h+var_220], 0
0x18004cfae  xorps   xmm0, xmm0
0x18004cfb1  xorps   xmm1, xmm1
0x18004cfb4  movups  xmmword ptr [rsp+250h+GuidString.Length], xmm0
0x18004cfb9  movups  xmmword ptr [rsp+250h+DestinationString.Length], xmm1
0x18004cfbe  test    rbx, rbx
0x18004cfc1  jnz     short loc_18004D007
0x18004cfc3  lea     rax, WPP_RECORDER_INITIALIZED
0x18004cfca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004cfd1  jz      short loc_18004CFFD
0x18004cfd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cfda  lea     rax, WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids
0x18004cfe1  mov     r9d, 0Ah
0x18004cfe7  mov     qword ptr [rsp+250h+Length], rax
0x18004cfec  mov     r8d, 1
0x18004cff2  mov     dl, 2
0x18004cff4  mov     rcx, [rcx+40h]
0x18004cff8  call    WPP_RECORDER_SF_
0x18004cffd  mov     eax, 0C000000Dh
0x18004d002  jmp     loc_18004D3D4
0x18004d007  lea     rdx, [rsp+250h+GuidString]; GuidString
0x18004d00c  mov     rcx, rbx; Guid
0x18004d00f  call    cs:__imp_RtlStringFromGUID
0x18004d016  nop     dword ptr [rax+rax+00h]
0x18004d01b  test    eax, eax
0x18004d01d  js      loc_18004D3D4
0x18004d023  mov     [rsp+250h+var_28], rdi
0x18004d02b  mov     ebx, 0B1h
0x18004d030  mov     r10d, 7FFFFFFEh
0x18004d036  test    rsi, rsi
0x18004d039  jnz     short loc_18004D084
0x18004d03b  mov     ecx, r10d
0x18004d03e  lea     r8, aRegistryMachin_3; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18004d045  mov     edx, ebx
0x18004d047  lea     rax, [rbp+150h+SourceString]
0x18004d04b  nop     dword ptr [rax+rax+00h]
0x18004d050  test    rcx, rcx
0x18004d053  jz      short loc_18004D074
0x18004d055  movzx   r9d, word ptr [r8]
0x18004d059  test    r9w, r9w
0x18004d05d  jz      short loc_18004D074
0x18004d05f  mov     [rax], r9w
0x18004d063  add     r8, 2
0x18004d067  add     rax, 2
0x18004d06b  dec     rcx
0x18004d06e  sub     rdx, 1
0x18004d072  jnz     short loc_18004D050
0x18004d074  test    rdx, rdx
0x18004d077  lea     rcx, [rax-2]
0x18004d07b  cmovnz  rcx, rax
0x18004d07f  xor     eax, eax
0x18004d081  mov     [rcx], ax
0x18004d084  mov     rcx, rbx
0x18004d087  lea     rax, [rbp+150h+SourceString]
0x18004d08b  nop     dword ptr [rax+rax+00h]
0x18004d090  cmp     word ptr [rax], 0
0x18004d094  jz      short loc_18004D0A0
0x18004d096  add     rax, 2
0x18004d09a  sub     rcx, 1
0x18004d09e  jnz     short loc_18004D090
0x18004d0a0  xor     eax, eax
0x18004d0a2  mov     rdx, rbx
0x18004d0a5  sub     rdx, rcx
0x18004d0a8  test    rcx, rcx
0x18004d0ab  cmovz   rdx, rax
0x18004d0af  jz      short loc_18004D0FC
0x18004d0b1  mov     rax, rbx
0x18004d0b4  lea     r8, aMediacategorie; "MediaCategories\\"
0x18004d0bb  sub     rax, rdx
0x18004d0be  mov     rcx, r10
0x18004d0c1  lea     rdx, [rbp+rdx*2+150h+SourceString]
0x18004d0c6  jz      short loc_18004D0EC
0x18004d0c8  test    rcx, rcx
0x18004d0cb  jz      short loc_18004D0EC
0x18004d0cd  movzx   r9d, word ptr [r8]
0x18004d0d1  test    r9w, r9w
0x18004d0d5  jz      short loc_18004D0EC
0x18004d0d7  mov     [rdx], r9w
0x18004d0db  add     r8, 2
0x18004d0df  add     rdx, 2
0x18004d0e3  dec     rcx
0x18004d0e6  sub     rax, 1
0x18004d0ea  jnz     short loc_18004D0C8
0x18004d0ec  test    rax, rax
0x18004d0ef  lea     rcx, [rdx-2]
0x18004d0f3  cmovnz  rcx, rdx
0x18004d0f7  xor     eax, eax
0x18004d0f9  mov     [rcx], ax
0x18004d0fc  mov     rcx, rbx
0x18004d0ff  lea     rax, [rbp+150h+SourceString]
0x18004d103  cmp     word ptr [rax], 0
0x18004d107  jz      short loc_18004D113
0x18004d109  add     rax, 2
0x18004d10d  sub     rcx, 1
0x18004d111  jnz     short loc_18004D103
0x18004d113  xor     eax, eax
0x18004d115  mov     edi, 0C000000Dh
0x18004d11a  test    rcx, rcx
0x18004d11d  mov     rdx, rbx
0x18004d120  cmovnz  edi, eax
0x18004d123  sub     rdx, rcx
0x18004d126  test    rcx, rcx
0x18004d129  cmovz   rdx, rax
0x18004d12d  jz      loc_18004D3B9
0x18004d133  mov     rax, [rsp+250h+GuidString.Buffer]
0x18004d138  sub     rbx, rdx
0x18004d13b  lea     rdx, [rbp+rdx*2+150h+SourceString]
0x18004d140  jz      short loc_18004D163
0x18004d142  test    r10, r10
0x18004d145  jz      short loc_18004D163
0x18004d147  movzx   ecx, word ptr [rax]
0x18004d14a  test    cx, cx
0x18004d14d  jz      short loc_18004D163
0x18004d14f  mov     [rdx], cx
0x18004d152  add     rax, 2
0x18004d156  add     rdx, 2
0x18004d15a  dec     r10
0x18004d15d  sub     rbx, 1
0x18004d161  jnz     short loc_18004D142
0x18004d163  xor     eax, eax
0x18004d165  lea     rcx, [rdx-2]
0x18004d169  test    rbx, rbx
0x18004d16c  mov     edi, 80000005h
0x18004d171  cmovnz  rcx, rdx
0x18004d175  cmovnz  edi, eax
0x18004d178  mov     [rcx], ax
0x18004d17b  lea     rcx, [rsp+250h+GuidString]; UnicodeString
0x18004d180  call    cs:__imp_RtlFreeUnicodeString
0x18004d187  nop     dword ptr [rax+rax+00h]
0x18004d18c  test    rbx, rbx
0x18004d18f  jz      loc_18004D3CA
0x18004d195  lea     rdx, [rbp+150h+SourceString]; SourceString
0x18004d199  lea     rcx, [rsp+250h+GuidString]; DestinationString
0x18004d19e  call    cs:__imp_RtlInitUnicodeString
0x18004d1a5  nop     dword ptr [rax+rax+00h]
0x18004d1aa  lea     rax, [rsp+250h+GuidString]
0x18004d1af  mov     [rsp+250h+ObjectAttributes.Length], 30h ; '0'
0x18004d1b7  xorps   xmm0, xmm0
0x18004d1ba  mov     [rsp+250h+ObjectAttributes.ObjectName], rax
0x18004d1bf  lea     r8, [rsp+250h+ObjectAttributes]; ObjectAttributes
0x18004d1c4  mov     [rsp+250h+ObjectAttributes.RootDirectory], rsi
0x18004d1c9  mov     edx, 20019h; DesiredAccess
0x18004d1ce  mov     [rsp+250h+ObjectAttributes.Attributes], 240h
0x18004d1d6  lea     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x18004d1db  movdqu  xmmword ptr [rbp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d1e0  call    cs:__imp_ZwOpenKey
0x18004d1e7  nop     dword ptr [rax+rax+00h]
0x18004d1ec  test    eax, eax
0x18004d1ee  js      loc_18004D3CC
0x18004d1f4  lea     rdx, aName; "Name"
0x18004d1fb  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x18004d200  call    cs:__imp_RtlInitUnicodeString
0x18004d207  nop     dword ptr [rax+rax+00h]
0x18004d20c  mov     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x18004d211  lea     rax, [rsp+250h+var_220]
0x18004d216  mov     [rsp+250h+ResultLength], rax; ResultLength
0x18004d21b  lea     r9, [rbp+150h+KeyValueInformation]; KeyValueInformation
0x18004d21f  mov     r8d, 2; KeyValueInformationClass
0x18004d225  mov     [rsp+250h+Length], 10h; Length
0x18004d22d  lea     rdx, [rsp+250h+DestinationString]; ValueName
0x18004d232  call    cs:__imp_ZwQueryValueKey
0x18004d239  nop     dword ptr [rax+rax+00h]
0x18004d23e  mov     ebx, eax
0x18004d240  mov     eax, 80000000h
0x18004d245  lea     ecx, [rbx+rax]
0x18004d248  test    eax, ecx
0x18004d24a  jnz     short loc_18004D258
0x18004d24c  cmp     ebx, 80000005h
0x18004d252  jnz     loc_18004D3A4
0x18004d258  mov     rax, [r14+0B8h]
0x18004d25f  mov     esi, [rax+8]
0x18004d262  test    esi, esi
0x18004d264  jnz     short loc_18004D27B
0x18004d266  mov     ecx, [rsp+250h+var_220]
0x18004d26a  mov     ebx, 80000005h
0x18004d26f  add     ecx, 0FFFFFFF4h
0x18004d272  mov     [r14+38h], rcx
0x18004d276  jmp     loc_18004D3A4
0x18004d27b  mov     ecx, [rsp+250h+var_220]
0x18004d27f  lea     eax, [rcx-0Ch]
0x18004d282  cmp     esi, eax
0x18004d284  jnb     short loc_18004D290
0x18004d286  mov     ebx, 0C0000023h
0x18004d28b  jmp     loc_18004D3A4
0x18004d290  test    r15, r15
0x18004d293  jnz     short loc_18004D2D9
0x18004d295  lea     rax, WPP_RECORDER_INITIALIZED
0x18004d29c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004d2a3  jz      short loc_18004D2CF
0x18004d2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d2ac  lea     rax, WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids
0x18004d2b3  mov     r9d, 0Bh
0x18004d2b9  mov     qword ptr [rsp+250h+Length], rax
0x18004d2be  mov     r8d, 1
0x18004d2c4  mov     dl, 2
0x18004d2c6  mov     rcx, [rcx+40h]
0x18004d2ca  call    WPP_RECORDER_SF_
0x18004d2cf  mov     ebx, 0C000000Dh
0x18004d2d4  jmp     loc_18004D3A4
0x18004d2d9  mov     rbx, rcx
0x18004d2dc  mov     rdx, rcx; NumberOfBytes
0x18004d2df  mov     ecx, 401h; PoolType
0x18004d2e4  mov     r8d, 766E534Bh; Tag
0x18004d2ea  call    cs:__imp_ExAllocatePoolWithTag
0x18004d2f1  nop     dword ptr [rax+rax+00h]
0x18004d2f6  mov     rdi, rax
0x18004d2f9  test    rax, rax
0x18004d2fc  jz      loc_18004D39F
0x18004d302  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18004d309  jnz     short loc_18004D318
0x18004d30b  mov     r8, rbx; Size
0x18004d30e  xor     edx, edx; Val
0x18004d310  mov     rcx, rax; void *
0x18004d313  call    memset
0x18004d318  mov     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x18004d31d  lea     rax, [rsp+250h+var_220]
0x18004d322  mov     [rsp+250h+ResultLength], rax; ResultLength
0x18004d327  lea     rdx, [rsp+250h+DestinationString]; ValueName
0x18004d32c  mov     eax, [rsp+250h+var_220]
0x18004d330  mov     r9, rdi; KeyValueInformation
0x18004d333  mov     r8d, 2; KeyValueInformationClass
0x18004d339  mov     [rsp+250h+Length], eax; Length
0x18004d33d  call    cs:__imp_ZwQueryValueKey
0x18004d344  nop     dword ptr [rax+rax+00h]
0x18004d349  mov     ebx, eax
0x18004d34b  test    eax, eax
0x18004d34d  js      short loc_18004D38C
0x18004d34f  mov     eax, [rsp+250h+var_220]
0x18004d353  add     eax, 0FFFFFFF4h
0x18004d356  cmp     esi, eax
0x18004d358  jnb     short loc_18004D361
0x18004d35a  mov     ebx, 0C0000023h
0x18004d35f  jmp     short loc_18004D38C
0x18004d361  mov     eax, [rdi+8]
0x18004d364  cmp     eax, 2
0x18004d367  jb      short loc_18004D387
0x18004d369  cmp     dword ptr [rdi+4], 1
0x18004d36d  jnz     short loc_18004D387
0x18004d36f  mov     r8d, eax; Size
0x18004d372  lea     rdx, [rdi+0Ch]; Src
0x18004d376  mov     rcx, r15; void *
0x18004d379  call    memmove
0x18004d37e  mov     eax, [rdi+8]
0x18004d381  mov     [r14+38h], rax
0x18004d385  jmp     short loc_18004D38C
0x18004d387  mov     ebx, 0C0000001h
0x18004d38c  xor     edx, edx; Tag
0x18004d38e  mov     rcx, rdi; P
0x18004d391  call    cs:__imp_ExFreePoolWithTag
0x18004d398  nop     dword ptr [rax+rax+00h]
0x18004d39d  jmp     short loc_18004D3A4
0x18004d39f  mov     ebx, 0C000009Ah
0x18004d3a4  mov     rcx, [rsp+250h+KeyHandle]; Handle
0x18004d3a9  call    cs:__imp_ZwClose
0x18004d3b0  nop     dword ptr [rax+rax+00h]
0x18004d3b5  mov     eax, ebx
0x18004d3b7  jmp     short loc_18004D3CC
0x18004d3b9  lea     rcx, [rsp+250h+GuidString]; UnicodeString
0x18004d3be  call    cs:__imp_RtlFreeUnicodeString
0x18004d3c5  nop     dword ptr [rax+rax+00h]
0x18004d3ca  mov     eax, edi
0x18004d3cc  mov     rdi, [rsp+250h+var_28]
0x18004d3d4  mov     rcx, [rbp+150h+var_40]
0x18004d3db  xor     rcx, rsp; StackCookie
0x18004d3de  call    __security_check_cookie
0x18004d3e3  add     rsp, 230h
0x18004d3ea  pop     r15
0x18004d3ec  pop     r14
0x18004d3ee  pop     rsi
0x18004d3ef  pop     rbx
0x18004d3f0  pop     rbp
0x18004d3f1  retn
```
