# RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)

- ea: `0x18002b1a0`
- end: `0x18002b315`
- name: `?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z`
- size: `373`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d770`

## callees

- `0x1800073c0`
- `0x18000c190`
- `0x18000e5d4`
- `0x18000e990`
- `0x1800270c8`
- `0x180027448`
- `0x18002b1a0`
- `0x18002e850`
- `0x180046ce0`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18002b20b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002b20b`

## string_xrefs

- `0x18002b211`: `RegistryPath::InitializePersistedStatePath`
- `0x18002b2b5`: `RegistryPath::InitializeLocalMachinePath`
- `0x18002b236`: `%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = "%s", DefaultPath = "%s"`

## pseudocode

```c
__int64 __fastcall RegistryPath::InitializePersistedStatePath(
        RegistryPath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int PersistedStateLocation; // eax
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r8
  int v8; // r9d
  int v9; // esi
  unsigned int v10; // edi
  int v11; // eax
  const wchar_t *v12; // r8
  unsigned int v13; // ebx
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-238h] BYREF

  memset_0(v15, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CloudDomainJoinRoot",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin",
                             0,
                             v15,
                             520,
                             0);
  v9 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    v10 = 0;
    Logger::WriteGetPersistedStateLocationFailureEvent(PersistedStateLocation, v6, v7, v8);
    Logger::TraceError(
      L"%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = \"%s\", DefaultPath = \"%s\"",
      L"RegistryPath::InitializePersistedStatePath",
      (unsigned int)v9,
      L"CloudDomainJoinRoot",
      L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin");
    goto LABEL_10;
  }
  if ( (unsigned int)IsEmptyString(0)
    || (v11 = StringCchCatW(v15, 0x104u, L"\\"), v10 = v11, v11 >= 0)
    && (v11 = StringCchCatW(v15, 0x104u, 0), v10 = v11, v11 >= 0) )
  {
    v11 = RegistryPath::Initialize(this, HKEY_LOCAL_MACHINE, L"HKEY_LOCAL_MACHINE", v15);
    v10 = v11;
    if ( v11 >= 0 )
      goto LABEL_10;
    v12 = L"RegistryPath::InitializeLocalMachinePath";
  }
  else
  {
    v12 = L"StringCchLengthW";
  }
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistryPath::InitializePersistedStatePath",
    v12,
    (unsigned int)v11);
LABEL_10:
  v13 = v9 | 0x10000000;
  if ( v9 >= 0 )
    v13 = v10;
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistryPath::InitializePersistedStatePath", v13);
  return v13;
}

```

## disassembly

```asm
0x18002b1a0  mov     [rsp+arg_8], rbx
0x18002b1a5  mov     [rsp+arg_10], rbp
0x18002b1aa  push    rsi
0x18002b1ab  push    rdi
0x18002b1ac  push    r14
0x18002b1ae  sub     rsp, 260h
0x18002b1b5  mov     rax, cs:__security_cookie
0x18002b1bc  xor     rax, rsp
0x18002b1bf  mov     [rsp+278h+var_28], rax
0x18002b1c7  mov     rbx, rcx
0x18002b1ca  mov     edi, 208h
0x18002b1cf  mov     r8d, edi; Size
0x18002b1d2  lea     rcx, [rsp+278h+var_238]; void *
0x18002b1d7  xor     edx, edx; Val
0x18002b1d9  call    memset_0
0x18002b1de  lea     rax, [rsp+278h+var_238]
0x18002b1e3  mov     [rsp+278h+var_248], 0
0x18002b1ec  lea     r14, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x18002b1f3  mov     [rsp+278h+var_250], edi
0x18002b1f7  mov     r8, r14
0x18002b1fa  mov     [rsp+278h+var_258], rax
0x18002b1ff  xor     r9d, r9d
0x18002b202  lea     rcx, aClouddomainjoi; "CloudDomainJoinRoot"
0x18002b209  xor     edx, edx
0x18002b20b  call    cs:__imp_RtlGetPersistedStateLocation
0x18002b211  lea     rbp, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x18002b218  mov     esi, eax
0x18002b21a  test    eax, eax
0x18002b21c  jns     short loc_18002B24A
0x18002b21e  mov     ecx, eax; int
0x18002b220  xor     edi, edi
0x18002b222  call    ?WriteGetPersistedStateLocationFailureEvent@Logger@@SAJJPEBG0H@Z; Logger::WriteGetPersistedStateLocationFailureEvent(long,ushort const *,ushort const *,int)
0x18002b227  lea     r9, aClouddomainjoi; "CloudDomainJoinRoot"
0x18002b22e  mov     [rsp+278h+var_258], r14
0x18002b233  mov     r8d, esi
0x18002b236  lea     rcx, aSRtlgetpersist; "%s: RtlGetPersistedStateLocation failed"...
0x18002b23d  mov     rdx, rbp
0x18002b240  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002b245  jmp     loc_18002B2CE
0x18002b24a  xor     ecx, ecx; unsigned __int16 *
0x18002b24c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18002b251  test    eax, eax
0x18002b253  jnz     short loc_18002B294
0x18002b255  mov     r14d, 104h
0x18002b25b  lea     r8, asc_180050E74; "\\"
0x18002b262  mov     edx, r14d; unsigned __int64
0x18002b265  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002b26a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b26f  mov     edi, eax
0x18002b271  test    eax, eax
0x18002b273  jns     short loc_18002B27E
0x18002b275  lea     r8, aStringcchlengt; "StringCchLengthW"
0x18002b27c  jmp     short loc_18002B2BC
0x18002b27e  xor     r8d, r8d; unsigned __int16 *
0x18002b281  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002b286  mov     rdx, r14; unsigned __int64
0x18002b289  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b28e  mov     edi, eax
0x18002b290  test    eax, eax
0x18002b292  js      short loc_18002B275
0x18002b294  lea     r9, [rsp+278h+var_238]; unsigned __int16 *
0x18002b299  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18002b2a0  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x18002b2a7  mov     rcx, rbx; this
0x18002b2aa  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18002b2af  mov     edi, eax
0x18002b2b1  test    eax, eax
0x18002b2b3  jns     short loc_18002B2CE
0x18002b2b5  lea     r8, aRegistrypathIn; "RegistryPath::InitializeLocalMachinePat"...
0x18002b2bc  mov     r9d, eax
0x18002b2bf  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18002b2c6  mov     rdx, rbp
0x18002b2c9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002b2ce  mov     ebx, esi
0x18002b2d0  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18002b2d7  bts     ebx, 1Ch
0x18002b2db  mov     rdx, rbp
0x18002b2de  test    esi, esi
0x18002b2e0  cmovns  ebx, edi
0x18002b2e3  mov     r8d, ebx
0x18002b2e6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002b2eb  mov     eax, ebx
0x18002b2ed  mov     rcx, [rsp+278h+var_28]
0x18002b2f5  xor     rcx, rsp; StackCookie
0x18002b2f8  call    __security_check_cookie
0x18002b2fd  lea     r11, [rsp+278h+var_18]
0x18002b305  mov     rbx, [r11+28h]
0x18002b309  mov     rbp, [r11+30h]
0x18002b30d  mov     rsp, r11
0x18002b310  pop     r14
0x18002b312  pop     rdi
0x18002b313  pop     rsi
0x18002b314  retn
```
