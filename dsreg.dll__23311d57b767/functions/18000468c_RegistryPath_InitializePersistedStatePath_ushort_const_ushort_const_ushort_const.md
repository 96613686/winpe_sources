# RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)

- ea: `0x18000468c`
- end: `0x1800048c5`
- name: `?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z`
- size: `569`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800372c4`
- `0x180037444`
- `0x180039290`
- `0x18003c828`
- `0x18003f0e4`
- `0x18004244c`
- `0x180056ef0`
- `0x18005f2c4`
- `0x18005f7fc`
- `0x18009ea50`
- `0x18009eb34`
- `0x18009ecd4`

## callees

- `0x18000468c`
- `0x18000554c`
- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18000cbd8`
- `0x1800107f0`
- `0x1800366c4`
- `0x180044300`
- `0x180044d30`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1800047bb`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800047bb`

## string_xrefs

- `0x1800046ec`: `RegistryPath::InitializePersistedStatePath`
- `0x18000470b`: `RegistryPath::InitializePersistedStatePath`
- `0x1800047f2`: `RegistryPath::InitializePersistedStatePath`
- `0x18000485b`: `RegistryPath::InitializePersistedStatePath`
- `0x1800048b9`: `RegistryPath::InitializePersistedStatePath`
- `0x180004828`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180004821`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180004803`: `RegistryPath::InitializeLocalMachinePath`
- `0x18000486a`: `%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = "%s", DefaultPath = "%s"`

## pseudocode

```c
__int64 __fastcall RegistryPath::InitializePersistedStatePath(
        RegistryPath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // esi
  int v9; // edi
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // ebx
  int PersistedStateLocation; // eax
  int v15; // r9d
  int v16; // eax
  const wchar_t *v17; // r8
  const wchar_t *v18; // rcx
  _BYTE v19[16]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  const wchar_t *v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+68h] [rbp-98h]
  unsigned __int16 v24[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v24, 0, 0x208u);
  if ( a2 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(a2, 0, a3, 0, v24, 520, 0);
    v8 = PersistedStateLocation;
    if ( PersistedStateLocation < 0 )
    {
      v9 = 0;
      Logger::WriteGetPersistedStateLocationFailureEvent(PersistedStateLocation, a2, a3, v15);
      v18 = L"<NULL>";
      if ( a3 )
        v18 = a3;
      Logger::TraceError(
        L"%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = \"%s\", DefaultPath = \"%s\"",
        L"RegistryPath::InitializePersistedStatePath",
        (unsigned int)v8,
        a2,
        v18);
    }
    else
    {
      if ( (unsigned int)IsEmptyString(a4)
        || (v16 = StringCchCatW(v24, 0x104u, L"\\"), v9 = v16, v16 >= 0)
        && (v16 = StringCchCatW(v24, 0x104u, a4), v9 = v16, v16 >= 0) )
      {
        v16 = RegistryPath::Initialize(this, HKEY_LOCAL_MACHINE, (wchar_t *)L"HKEY_LOCAL_MACHINE", v24);
        v9 = v16;
        if ( v16 >= 0 )
          goto LABEL_5;
        v17 = L"RegistryPath::InitializeLocalMachinePath";
      }
      else
      {
        v17 = L"StringCchLengthW";
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistryPath::InitializePersistedStatePath",
        v17,
        (unsigned int)v16);
    }
  }
  else
  {
    v8 = 0;
    v9 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistryPath::InitializePersistedStatePath", L"sourceId");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v20 = L"RegistryPath::InitializePersistedStatePath";
      v21 = 86;
      v22 = L"sourceId";
      v23 = 18;
      v11 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v10,
              3,
              v19);
      if ( v11 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v11);
    }
  }
LABEL_5:
  v12 = v8 | 0x10000000;
  if ( v8 >= 0 )
    v12 = v9;
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistryPath::InitializePersistedStatePath", v12);
  return v12;
}

```

## disassembly

```asm
0x18000468c  push    rbp
0x18000468e  push    rbx
0x18000468f  push    rsi
0x180004690  push    rdi
0x180004691  push    r12
0x180004693  push    r14
0x180004695  push    r15
0x180004697  lea     rbp, [rsp-190h]
0x18000469f  sub     rsp, 290h
0x1800046a6  mov     rax, cs:__security_cookie
0x1800046ad  xor     rax, rsp
0x1800046b0  mov     [rbp+1C0h+var_40], rax
0x1800046b7  mov     rbx, r8
0x1800046ba  mov     r14, rdx
0x1800046bd  mov     r12, rcx
0x1800046c0  mov     edi, 208h
0x1800046c5  mov     r8d, edi; Size
0x1800046c8  lea     rcx, [rsp+2C0h+var_250]; void *
0x1800046cd  xor     edx, edx; Val
0x1800046cf  mov     r15, r9
0x1800046d2  call    memset_0
0x1800046d7  test    r14, r14
0x1800046da  jnz     loc_180004799
0x1800046e0  lea     rbx, aSourceid; "sourceId"
0x1800046e7  xor     esi, esi
0x1800046e9  mov     r8, rbx
0x1800046ec  lea     rdx, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x1800046f3  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800046fa  mov     edi, 80070057h
0x1800046ff  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180004704  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000470b  lea     r14, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180004712  jz      short loc_180004759
0x180004714  lea     rax, [rsp+2C0h+var_280]
0x180004719  mov     [rsp+2C0h+var_270], r14
0x18000471e  lea     r9d, [rsi+3]
0x180004722  mov     [rsp+2C0h+var_2A0], rax
0x180004727  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000472e  mov     [rsp+2C0h+var_268], 56h ; 'V'
0x180004737  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000473e  mov     [rsp+2C0h+var_260], rbx
0x180004743  mov     [rsp+2C0h+var_258], 12h
0x18000474c  call    McGenEventWrite_EventWriteTransfer
0x180004751  test    eax, eax
0x180004753  jnz     loc_180004821
0x180004759  mov     ebx, esi
0x18000475b  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180004762  bts     ebx, 1Ch
0x180004766  mov     rdx, r14
0x180004769  test    esi, esi
0x18000476b  cmovns  ebx, edi
0x18000476e  mov     r8d, ebx
0x180004771  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180004776  mov     eax, ebx
0x180004778  mov     rcx, [rbp+1C0h+var_40]
0x18000477f  xor     rcx, rsp; StackCookie
0x180004782  call    __security_check_cookie
0x180004787  add     rsp, 290h
0x18000478e  pop     r15
0x180004790  pop     r14
0x180004792  pop     r12
0x180004794  pop     rdi
0x180004795  pop     rsi
0x180004796  pop     rbx
0x180004797  pop     rbp
0x180004798  retn
0x180004799  mov     [rsp+2C0h+var_290], 0
0x1800047a2  lea     rax, [rsp+2C0h+var_250]
0x1800047a7  mov     [rsp+2C0h+var_298], edi
0x1800047ab  xor     r9d, r9d
0x1800047ae  mov     r8, rbx
0x1800047b1  mov     [rsp+2C0h+var_2A0], rax
0x1800047b6  xor     edx, edx
0x1800047b8  mov     rcx, r14
0x1800047bb  call    cs:__imp_RtlGetPersistedStateLocation
0x1800047c1  mov     esi, eax
0x1800047c3  test    eax, eax
0x1800047c5  js      short loc_180004838
0x1800047c7  mov     rcx, r15; unsigned __int16 *
0x1800047ca  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800047cf  test    eax, eax
0x1800047d1  jz      loc_18000487B
0x1800047d7  lea     r9, [rsp+2C0h+var_250]; unsigned __int16 *
0x1800047dc  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800047e3  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x1800047ea  mov     rcx, r12; this
0x1800047ed  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800047f2  lea     r14, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x1800047f9  mov     edi, eax
0x1800047fb  test    eax, eax
0x1800047fd  jns     loc_180004759
0x180004803  lea     r8, aRegistrypathIn; "RegistryPath::InitializeLocalMachinePat"...
0x18000480a  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180004811  mov     rdx, r14
0x180004814  mov     r9d, eax
0x180004817  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000481c  jmp     loc_180004759
0x180004821  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180004828  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000482f  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180004836  jmp     short loc_180004814
0x180004838  mov     r8, rbx; unsigned __int16 *
0x18000483b  mov     rdx, r14; unsigned __int16 *
0x18000483e  mov     ecx, esi; int
0x180004840  xor     edi, edi
0x180004842  call    ?WriteGetPersistedStateLocationFailureEvent@Logger@@SAJJPEBG0H@Z; Logger::WriteGetPersistedStateLocationFailureEvent(long,ushort const *,ushort const *,int)
0x180004847  test    rbx, rbx
0x18000484a  lea     rcx, aNull_2; "<NULL>"
0x180004851  mov     r9, r14
0x180004854  mov     r8d, esi
0x180004857  cmovnz  rcx, rbx
0x18000485b  lea     r14, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180004862  mov     [rsp+2C0h+var_2A0], rcx
0x180004867  mov     rdx, r14
0x18000486a  lea     rcx, aSRtlgetpersist; "%s: RtlGetPersistedStateLocation failed"...
0x180004871  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180004876  jmp     loc_180004759
0x18000487b  mov     ebx, 104h
0x180004880  lea     r8, asc_1800D720C; "\\"
0x180004887  mov     edx, ebx; unsigned __int64
0x180004889  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18000488e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004893  mov     edi, eax
0x180004895  test    eax, eax
0x180004897  js      short loc_1800048B2
0x180004899  mov     r8, r15; unsigned __int16 *
0x18000489c  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x1800048a1  mov     edx, ebx; unsigned __int64
0x1800048a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800048a8  mov     edi, eax
0x1800048aa  test    eax, eax
0x1800048ac  jns     loc_1800047D7
0x1800048b2  lea     r8, aStringcchlengt; "StringCchLengthW"
0x1800048b9  lea     r14, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x1800048c0  jmp     loc_18000480A
```
