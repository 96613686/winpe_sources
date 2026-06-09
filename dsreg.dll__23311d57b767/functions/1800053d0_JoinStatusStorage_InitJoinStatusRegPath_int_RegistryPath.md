# JoinStatusStorage::InitJoinStatusRegPath(int,RegistryPath &)

- ea: `0x1800053d0`
- end: `0x180005545`
- name: `?InitJoinStatusRegPath@JoinStatusStorage@@CAJHAEAVRegistryPath@@@Z`
- size: `373`
- prototype: `static int(int, struct RegistryPath *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18003fbac`
- `0x18004068c`
- `0x180042c18`
- `0x180096a40`
- `0x180096d08`

## callees

- `0x1800053d0`
- `0x18000554c`
- `0x180005894`
- `0x1800084f4`
- `0x18000bac0`
- `0x1800366c4`
- `0x180044300`
- `0x180044d30`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180005468`
- `ntdll!RtlGetPersistedStateLocation` at `0x180005468`

## string_xrefs

- `0x180005497`: `RegistryPath::InitializePersistedStatePath`
- `0x1800054c1`: `RegistryPath::InitializePersistedStatePath`
- `0x1800054ec`: `RegistryPath::InitializePersistedStatePath`
- `0x18000550b`: `RegistryPath::InitializePersistedStatePath`
- `0x180005526`: `RegistryPath::InitializeCurrentUserPath`
- `0x180005504`: `RegistryPath::InitializeLocalMachinePath`
- `0x1800054f3`: `%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = "%s", DefaultPath = "%s"`
- `0x18000552d`: `JoinStatusStorage::InitJoinStatusRegPath`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::InitJoinStatusRegPath(
        int a1,
        struct RegistryPath *a2,
        const unsigned __int16 *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int PersistedStateLocation; // eax
  int v8; // r9d
  int v9; // esi
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r9
  const wchar_t *v13; // r8
  unsigned __int16 v14[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( !a1 )
  {
    v4 = RegistryPath::InitializeCurrentUserPath(a2, (__int64)a2, a3);
    v5 = v4;
    if ( v4 >= 0 )
      return v5;
    v12 = (unsigned int)v4;
    v13 = L"RegistryPath::InitializeCurrentUserPath";
LABEL_13:
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"JoinStatusStorage::InitJoinStatusRegPath", v13, v12);
    return v5;
  }
  memset_0(v14, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CloudDomainJoinRoot",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin",
                             0,
                             v14,
                             520,
                             0);
  v9 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    v11 = 0;
    Logger::WriteGetPersistedStateLocationFailureEvent(
      PersistedStateLocation,
      L"CloudDomainJoinRoot",
      L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin",
      v8);
    Logger::TraceError(
      L"%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = \"%s\", DefaultPath = \"%s\"",
      L"RegistryPath::InitializePersistedStatePath",
      (unsigned int)v9,
      L"CloudDomainJoinRoot",
      L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin");
  }
  else
  {
    v10 = RegistryPath::Initialize(a2, HKEY_LOCAL_MACHINE, (wchar_t *)L"HKEY_LOCAL_MACHINE", v14);
    v11 = v10;
    if ( v10 < 0 )
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistryPath::InitializePersistedStatePath",
        L"RegistryPath::InitializeLocalMachinePath",
        (unsigned int)v10);
  }
  v5 = v9 | 0x10000000;
  if ( v9 >= 0 )
    v5 = v11;
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistryPath::InitializePersistedStatePath", v5);
  if ( (v5 & 0x80000000) != 0 )
  {
    v12 = v5;
    v13 = L"RegistryPath::InitializePersistedStatePath";
    goto LABEL_13;
  }
  return v5;
}

```

## disassembly

```asm
0x1800053d0  push    rbx
0x1800053d2  push    rsi
0x1800053d3  push    rdi
0x1800053d4  push    r15
0x1800053d6  sub     rsp, 268h
0x1800053dd  mov     rax, cs:__security_cookie
0x1800053e4  xor     rax, rsp
0x1800053e7  mov     [rsp+288h+var_38], rax
0x1800053ef  mov     rbx, rdx
0x1800053f2  test    ecx, ecx
0x1800053f4  jnz     short loc_180005427
0x1800053f6  mov     rcx, rdx; this
0x1800053f9  call    ?InitializeCurrentUserPath@RegistryPath@@QEAAJKPEBG@Z; RegistryPath::InitializeCurrentUserPath(ulong,ushort const *)
0x1800053fe  mov     ebx, eax
0x180005400  test    eax, eax
0x180005402  js      loc_180005523
0x180005408  mov     eax, ebx
0x18000540a  mov     rcx, [rsp+288h+var_38]
0x180005412  xor     rcx, rsp; StackCookie
0x180005415  call    __security_check_cookie
0x18000541a  add     rsp, 268h
0x180005421  pop     r15
0x180005423  pop     rdi
0x180005424  pop     rsi
0x180005425  pop     rbx
0x180005426  retn
0x180005427  mov     edi, 208h
0x18000542c  lea     rcx, [rsp+288h+var_248]; void *
0x180005431  mov     r8d, edi; Size
0x180005434  xor     edx, edx; Val
0x180005436  call    memset_0
0x18000543b  lea     rax, [rsp+288h+var_248]
0x180005440  mov     [rsp+288h+var_258], 0
0x180005449  lea     r15, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x180005450  mov     [rsp+288h+var_260], edi
0x180005454  mov     r8, r15
0x180005457  mov     [rsp+288h+var_268], rax
0x18000545c  xor     r9d, r9d
0x18000545f  lea     rcx, aClouddomainjoi_0; "CloudDomainJoinRoot"
0x180005466  xor     edx, edx
0x180005468  call    cs:__imp_RtlGetPersistedStateLocation
0x18000546e  mov     esi, eax
0x180005470  test    eax, eax
0x180005472  js      short loc_1800054CA
0x180005474  lea     r9, [rsp+288h+var_248]; unsigned __int16 *
0x180005479  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180005480  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180005487  mov     rcx, rbx; this
0x18000548a  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18000548f  mov     edi, eax
0x180005491  test    eax, eax
0x180005493  js      short loc_180005501
0x180005495  mov     ebx, esi
0x180005497  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x18000549e  bts     ebx, 1Ch
0x1800054a2  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800054a9  test    esi, esi
0x1800054ab  cmovns  ebx, edi
0x1800054ae  mov     r8d, ebx
0x1800054b1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800054b6  test    ebx, ebx
0x1800054b8  jns     loc_180005408
0x1800054be  mov     r9d, ebx
0x1800054c1  lea     r8, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x1800054c8  jmp     short loc_18000552D
0x1800054ca  mov     r8, r15; unsigned __int16 *
0x1800054cd  lea     rdx, aClouddomainjoi_0; "CloudDomainJoinRoot"
0x1800054d4  mov     ecx, esi; int
0x1800054d6  xor     edi, edi
0x1800054d8  call    ?WriteGetPersistedStateLocationFailureEvent@Logger@@SAJJPEBG0H@Z; Logger::WriteGetPersistedStateLocationFailureEvent(long,ushort const *,ushort const *,int)
0x1800054dd  lea     r9, aClouddomainjoi_0; "CloudDomainJoinRoot"
0x1800054e4  mov     [rsp+288h+var_268], r15
0x1800054e9  mov     r8d, esi
0x1800054ec  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x1800054f3  lea     rcx, aSRtlgetpersist; "%s: RtlGetPersistedStateLocation failed"...
0x1800054fa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800054ff  jmp     short loc_180005495
0x180005501  mov     r9d, eax
0x180005504  lea     r8, aRegistrypathIn; "RegistryPath::InitializeLocalMachinePat"...
0x18000550b  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180005512  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180005519  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000551e  jmp     loc_180005495
0x180005523  mov     r9d, eax
0x180005526  lea     r8, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x18000552d  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::InitJoinStatusRegPat"...
0x180005534  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18000553b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005540  jmp     loc_180005408
```
