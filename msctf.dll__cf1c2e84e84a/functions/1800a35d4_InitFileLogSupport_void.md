# InitFileLogSupport(void)

- ea: `0x1800a35d4`
- end: `0x1800a3955`
- name: `?InitFileLogSupport@@YAHXZ`
- size: `897`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024b2c`

## callees

- `0x1800139a4`
- `0x18001e2c0`
- `0x1800226c0`
- `0x180022740`
- `0x18005c40c`
- `0x1800a35d4`
- `0x180106a60`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800a38a7`
- `msvcrt!wcsnlen` at `0x1800a38a7`
- `ntdll!NtQueryValueKey` at `0x1800a374d`
- `ntdll!NtQueryValueKey` at `0x1800a379b`
- `ntdll!NtQueryValueKey` at `0x1800a374d`
- `ntdll!NtQueryValueKey` at `0x1800a379b`
- `ntdll!RtlInitUnicodeString` at `0x1800a36ae`
- `ntdll!RtlInitUnicodeString` at `0x1800a3726`
- `ntdll!RtlInitUnicodeString` at `0x1800a36ae`
- `ntdll!RtlInitUnicodeString` at `0x1800a3726`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800a3642`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800a3642`
- `ntdll!NtClose` at `0x1800a3879`
- `ntdll!NtClose` at `0x1800a3879`
- `ntdll!NtOpenKey` at `0x1800a36ff`
- `ntdll!NtOpenKey` at `0x1800a36ff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800a3901`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800a3901`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a37d7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a3801`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a37d7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a3801`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800a361a`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800a361a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3765`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a37ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3765`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a37ea`

## pseudocode

```c
__int64 InitFileLogSupport(void)
{
  unsigned int v0; // ebx
  _DWORD *v1; // rsi
  DWORD v2; // eax
  DWORD v3; // r15d
  WCHAR *v4; // rax
  const unsigned __int16 *v5; // r14
  int v6; // ecx
  int i; // edx
  wchar_t v8; // r8
  ULONG ResultLength; // [rsp+30h] [rbp-4E8h] BYREF
  int v11; // [rsp+34h] [rbp-4E4h]
  int v12; // [rsp+38h] [rbp-4E0h]
  void *KeyHandle; // [rsp+40h] [rbp-4D8h] BYREF
  int v14; // [rsp+48h] [rbp-4D0h]
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-4C8h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+60h] [rbp-4B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-4A8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-498h] BYREF
  WCHAR SourceString[264]; // [rsp+B0h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+2C0h] [rbp-258h] BYREF

  v0 = 0;
  v12 = 0;
  if ( GetEnvironmentVariableW(L"SHIM_FILE_LOG", Buffer, 0x104u) && (int)TF_GetAppCompatFlags() < 0 )
  {
    KeyPath = 0;
    if ( RtlFormatCurrentUserKeyPath(&KeyPath) >= 0 )
    {
      KeyHandle = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      DestinationString = 0;
      StringCchCopyW(SourceString, 0x104u, KeyPath.Buffer);
      StringCchCatW(
        SourceString,
        0x104u,
        L"\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders");
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( !NtOpenKey(&KeyHandle, 1u, &ObjectAttributes) )
      {
        ResultLength = 0;
        ValueName = 0;
        RtlInitUnicodeString(&ValueName, L"AppData");
        if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength) == -1073741789 )
        {
          v1 = LocalAlloc(0x40u, ResultLength);
          if ( v1 )
          {
            if ( !NtQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, v1, ResultLength, &ResultLength) )
            {
              if ( v1[1] == 2 )
              {
                StringCchCopyNW(
                  &g_szFileLog,
                  0x104u,
                  (const unsigned __int16 *)((char *)v1 + (unsigned int)v1[2]),
                  (unsigned __int64)(unsigned int)v1[3] >> 1);
                v2 = ExpandEnvironmentStringsW(&g_szFileLog, 0, 0);
                v3 = v2;
                if ( v2 )
                {
                  v4 = (WCHAR *)LocalAlloc(0x40u, 2 * v2);
                  v5 = v4;
                  if ( v4 )
                  {
                    ExpandEnvironmentStringsW(&g_szFileLog, v4, v3);
                    StringCchCopyW(&g_szFileLog, 0x104u, v5);
                    cicMemFree(v5);
                  }
                }
              }
              else if ( v1[1] == 1 )
              {
                StringCchCopyNW(
                  &g_szFileLog,
                  0x104u,
                  (const unsigned __int16 *)((char *)v1 + (unsigned int)v1[2]),
                  (unsigned __int64)(unsigned int)v1[3] >> 1);
              }
              StringCchCatW(&g_szFileLog, 0x104u, L"\\");
              StringCchCatW(&g_szFileLog, 0x104u, Buffer);
            }
            cicMemFree(v1);
          }
        }
        NtClose(KeyHandle);
      }
    }
    StringCchCopyW(&g_szMutex, 0x104u, L"Local\\");
    v6 = wcsnlen(&g_szMutex, 0x104u);
    v14 = v6;
    v11 = 0;
    for ( i = 0; ; ++i )
    {
      v11 = i;
      if ( (unsigned __int64)i >= 0x104 )
        break;
      v8 = *(&g_szFileLog + i);
      if ( !v8 || (unsigned __int64)v6 >= 0x104 )
        break;
      if ( v8 == 92 )
        v8 = 95;
      *(&g_szMutex + v6++) = v8;
      v14 = v6;
    }
    g_LogMutex = CreateMutexW(0, 0, &g_szMutex);
    g_bFileLogEnabled = 1;
    v0 = 1;
    v12 = 1;
  }
  g_bInitFileLogSupport = 1;
  return v0;
}

```

## disassembly

```asm
0x1800a35d4  push    rbx
0x1800a35d6  push    rsi
0x1800a35d7  push    r12
0x1800a35d9  push    r13
0x1800a35db  push    r14
0x1800a35dd  push    r15
0x1800a35df  sub     rsp, 4E8h
0x1800a35e6  mov     rax, cs:__security_cookie
0x1800a35ed  xor     rax, rsp
0x1800a35f0  mov     [rsp+518h+var_48], rax
0x1800a35f8  xor     r12d, r12d
0x1800a35fb  mov     ebx, r12d
0x1800a35fe  mov     [rsp+518h+var_4E0], ebx
0x1800a3602  mov     r13d, 104h
0x1800a3608  mov     r8d, r13d; nSize
0x1800a360b  lea     rdx, [rsp+518h+Buffer]; lpBuffer
0x1800a3613  lea     rcx, Name; "SHIM_FILE_LOG"
0x1800a361a  call    cs:__imp_GetEnvironmentVariableW
0x1800a3620  test    eax, eax
0x1800a3622  jz      loc_1800A3927
0x1800a3628  call    TF_GetAppCompatFlags
0x1800a362d  test    eax, eax
0x1800a362f  jns     loc_1800A3927
0x1800a3635  xorps   xmm0, xmm0
0x1800a3638  movups  xmmword ptr [rsp+518h+KeyPath.Length], xmm0
0x1800a363d  lea     rcx, [rsp+518h+KeyPath]; KeyPath
0x1800a3642  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800a3648  test    eax, eax
0x1800a364a  js      loc_1800A3881
0x1800a3650  mov     [rsp+518h+KeyHandle], r12
0x1800a3655  xorps   xmm0, xmm0
0x1800a3658  movups  xmmword ptr [rsp+518h+ObjectAttributes.Length], xmm0
0x1800a3660  movups  xmmword ptr [rsp+518h+ObjectAttributes.ObjectName], xmm0
0x1800a3668  movups  xmmword ptr [rsp+518h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a3670  movups  xmmword ptr [rsp+518h+DestinationString.Length], xmm0
0x1800a3675  mov     r8, [rsp+518h+KeyPath.Buffer]; unsigned __int16 *
0x1800a367a  mov     edx, r13d; unsigned __int64
0x1800a367d  lea     rcx, [rsp+518h+SourceString]; unsigned __int16 *
0x1800a3685  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a368a  lea     r8, aSoftwareMicros_6; "\\Software\\Microsoft\\Windows\\Current"...
0x1800a3691  mov     edx, r13d; unsigned __int64
0x1800a3694  lea     rcx, [rsp+518h+SourceString]; unsigned __int16 *
0x1800a369c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a36a1  lea     rdx, [rsp+518h+SourceString]; SourceString
0x1800a36a9  lea     rcx, [rsp+518h+DestinationString]; DestinationString
0x1800a36ae  call    cs:__imp_RtlInitUnicodeString
0x1800a36b4  mov     [rsp+518h+ObjectAttributes.Length], 30h ; '0'
0x1800a36bf  mov     [rsp+518h+ObjectAttributes.RootDirectory], r12
0x1800a36c7  lea     r14d, [r12+40h]
0x1800a36cc  mov     [rsp+518h+ObjectAttributes.Attributes], r14d
0x1800a36d4  lea     rax, [rsp+518h+DestinationString]
0x1800a36d9  mov     [rsp+518h+ObjectAttributes.ObjectName], rax
0x1800a36e1  xorps   xmm0, xmm0
0x1800a36e4  movdqu  xmmword ptr [rsp+518h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a36ed  lea     r8, [rsp+518h+ObjectAttributes]; ObjectAttributes
0x1800a36f5  lea     edx, [r12+1]; DesiredAccess
0x1800a36fa  lea     rcx, [rsp+518h+KeyHandle]; KeyHandle
0x1800a36ff  call    cs:__imp_NtOpenKey
0x1800a3705  test    eax, eax
0x1800a3707  jnz     loc_1800A3881
0x1800a370d  mov     [rsp+518h+var_4E8], r12d
0x1800a3712  xorps   xmm0, xmm0
0x1800a3715  movups  xmmword ptr [rsp+518h+ValueName.Length], xmm0
0x1800a371a  lea     rdx, SourceString; "AppData"
0x1800a3721  lea     rcx, [rsp+518h+ValueName]; DestinationString
0x1800a3726  call    cs:__imp_RtlInitUnicodeString
0x1800a372c  lea     rax, [rsp+518h+var_4E8]
0x1800a3731  mov     [rsp+518h+ResultLength], rax; ResultLength
0x1800a3736  mov     [rsp+518h+Length], r12d; Length
0x1800a373b  xor     r9d, r9d; KeyValueInformation
0x1800a373e  lea     r8d, [r12+1]; KeyValueInformationClass
0x1800a3743  lea     rdx, [rsp+518h+ValueName]; ValueName
0x1800a3748  mov     rcx, [rsp+518h+KeyHandle]; KeyHandle
0x1800a374d  call    cs:__imp_NtQueryValueKey
0x1800a3753  cmp     eax, 0C0000023h
0x1800a3758  jnz     loc_1800A386D
0x1800a375e  mov     edx, [rsp+518h+var_4E8]; uBytes
0x1800a3762  mov     ecx, r14d; uFlags
0x1800a3765  call    cs:__imp_LocalAlloc
0x1800a376b  mov     rsi, rax
0x1800a376e  test    rax, rax
0x1800a3771  jz      loc_1800A386D
0x1800a3777  lea     rax, [rsp+518h+var_4E8]
0x1800a377c  mov     [rsp+518h+ResultLength], rax; ResultLength
0x1800a3781  mov     ecx, [rsp+518h+var_4E8]
0x1800a3785  mov     [rsp+518h+Length], ecx; Length
0x1800a3789  mov     r9, rsi; KeyValueInformation
0x1800a378c  lea     r8d, [r12+1]; KeyValueInformationClass
0x1800a3791  lea     rdx, [rsp+518h+ValueName]; ValueName
0x1800a3796  mov     rcx, [rsp+518h+KeyHandle]; KeyHandle
0x1800a379b  call    cs:__imp_NtQueryValueKey
0x1800a37a1  lea     rbx, ?g_szFileLog@@3PAGA; ushort near * g_szFileLog
0x1800a37a8  test    eax, eax
0x1800a37aa  jnz     loc_1800A3863
0x1800a37b0  cmp     dword ptr [rsi+4], 2
0x1800a37b4  jnz     short loc_1800A381F
0x1800a37b6  mov     r9d, [rsi+0Ch]
0x1800a37ba  shr     r9, 1; unsigned __int64
0x1800a37bd  mov     r8d, [rsi+8]
0x1800a37c1  add     r8, rsi; unsigned __int16 *
0x1800a37c4  mov     edx, r13d; unsigned __int64
0x1800a37c7  mov     rcx, rbx; unsigned __int16 *
0x1800a37ca  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800a37cf  xor     r8d, r8d; nSize
0x1800a37d2  xor     edx, edx; lpDst
0x1800a37d4  mov     rcx, rbx; lpSrc
0x1800a37d7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a37dd  mov     r15d, eax
0x1800a37e0  test    eax, eax
0x1800a37e2  jz      short loc_1800A383E
0x1800a37e4  lea     edx, [rax+rax]; uBytes
0x1800a37e7  mov     ecx, r14d; uFlags
0x1800a37ea  call    cs:__imp_LocalAlloc
0x1800a37f0  mov     r14, rax
0x1800a37f3  test    rax, rax
0x1800a37f6  jz      short loc_1800A383E
0x1800a37f8  mov     r8d, r15d; nSize
0x1800a37fb  mov     rdx, rax; lpDst
0x1800a37fe  mov     rcx, rbx; lpSrc
0x1800a3801  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a3807  mov     r8, r14; unsigned __int16 *
0x1800a380a  mov     edx, r13d; unsigned __int64
0x1800a380d  mov     rcx, rbx; unsigned __int16 *
0x1800a3810  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a3815  mov     rcx, r14
0x1800a3818  call    cicMemFree
0x1800a381d  jmp     short loc_1800A383E
0x1800a381f  cmp     dword ptr [rsi+4], 1
0x1800a3823  jnz     short loc_1800A383E
0x1800a3825  mov     r9d, [rsi+0Ch]
0x1800a3829  shr     r9, 1; unsigned __int64
0x1800a382c  mov     r8d, [rsi+8]
0x1800a3830  add     r8, rsi; unsigned __int16 *
0x1800a3833  mov     rdx, r13; unsigned __int64
0x1800a3836  mov     rcx, rbx; unsigned __int16 *
0x1800a3839  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800a383e  lea     r8, SubBlock; "\\"
0x1800a3845  mov     rdx, r13; unsigned __int64
0x1800a3848  mov     rcx, rbx; unsigned __int16 *
0x1800a384b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a3850  lea     r8, [rsp+518h+Buffer]; unsigned __int16 *
0x1800a3858  mov     rdx, r13; unsigned __int64
0x1800a385b  mov     rcx, rbx; unsigned __int16 *
0x1800a385e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a3863  mov     rcx, rsi
0x1800a3866  call    cicMemFree
0x1800a386b  jmp     short loc_1800A3874
0x1800a386d  lea     rbx, ?g_szFileLog@@3PAGA; ushort near * g_szFileLog
0x1800a3874  mov     rcx, [rsp+518h+KeyHandle]; Handle
0x1800a3879  call    cs:__imp_NtClose
0x1800a387f  jmp     short loc_1800A3888
0x1800a3881  lea     rbx, ?g_szFileLog@@3PAGA; ushort near * g_szFileLog
0x1800a3888  lea     r8, aLocal; "Local\\"
0x1800a388f  mov     rdx, r13; unsigned __int64
0x1800a3892  lea     rsi, ?g_szMutex@@3PAGA; ushort near * g_szMutex
0x1800a3899  mov     rcx, rsi; unsigned __int16 *
0x1800a389c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a38a1  mov     rdx, r13; MaxCount
0x1800a38a4  mov     rcx, rsi; Source
0x1800a38a7  call    cs:__imp_wcsnlen
0x1800a38ad  mov     rcx, rax
0x1800a38b0  mov     [rsp+518h+var_4D0], eax
0x1800a38b4  mov     [rsp+518h+var_4E4], r12d
0x1800a38b9  mov     edx, r12d
0x1800a38bc  mov     [rsp+518h+var_4E4], edx
0x1800a38c0  movsxd  r8, edx
0x1800a38c3  cmp     r8, r13
0x1800a38c6  jnb     short loc_1800A38FA
0x1800a38c8  movzx   r8d, word ptr [rbx+r8*2]
0x1800a38cd  test    r8w, r8w
0x1800a38d1  jz      short loc_1800A38FA
0x1800a38d3  movsxd  rax, ecx
0x1800a38d6  cmp     rax, r13
0x1800a38d9  jnb     short loc_1800A38FA
0x1800a38db  movsxd  rax, ecx
0x1800a38de  cmp     r8w, 5Ch ; '\'
0x1800a38e3  jnz     short loc_1800A38EB
0x1800a38e5  mov     r8d, 5Fh ; '_'
0x1800a38eb  mov     [rsi+rax*2], r8w
0x1800a38f0  inc     edx
0x1800a38f2  inc     ecx
0x1800a38f4  mov     [rsp+518h+var_4D0], ecx
0x1800a38f8  jmp     short loc_1800A38BC
0x1800a38fa  mov     r8, rsi; lpName
0x1800a38fd  xor     edx, edx; bInitialOwner
0x1800a38ff  xor     ecx, ecx; lpMutexAttributes
0x1800a3901  call    cs:__imp_CreateMutexW
0x1800a3907  mov     cs:?g_LogMutex@@3PEAXEA, rax; void * g_LogMutex
0x1800a390e  mov     cs:?g_bFileLogEnabled@@3HA, 1; int g_bFileLogEnabled
0x1800a3918  mov     ebx, 1
0x1800a391d  mov     [rsp+518h+var_4E0], ebx
0x1800a3921  jmp     short loc_1800A3927
0x1800a3923  mov     ebx, [rsp+518h+var_4E0]
0x1800a3927  mov     cs:?g_bInitFileLogSupport@@3HA, 1; int g_bInitFileLogSupport
0x1800a3931  mov     eax, ebx
0x1800a3933  mov     rcx, [rsp+518h+var_48]
0x1800a393b  xor     rcx, rsp; StackCookie
0x1800a393e  call    __security_check_cookie
0x1800a3943  add     rsp, 4E8h
0x1800a394a  pop     r15
0x1800a394c  pop     r14
0x1800a394e  pop     r13
0x1800a3950  pop     r12
0x1800a3952  pop     rsi
0x1800a3953  pop     rbx
0x1800a3954  retn
```
