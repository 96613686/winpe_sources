# TelCacheProvider::ShouldForceFullSyncForCommercial(bool)

- ea: `0x180012d3c`
- end: `0x180012f90`
- name: `?ShouldForceFullSyncForCommercial@TelCacheProvider@@AEAAH_N@Z`
- size: `596`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012af4`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x180011428`
- `0x1800125fc`
- `0x180012d3c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012e2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012e2a`

## string_xrefs

- `0x180012e4c`: `commercialId`
- `0x180012f30`: `commercialId`
- `0x180012ea6`: `Full sync may be needed because of Commercial ID change`
- `0x180012f0a`: `Full sync may be needed because of Commercial 45 day sync policy`
- `0x180012f17`: `TelCacheProvider::ShouldForceFullSyncForCommercial`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForCommercial(TelCacheProvider *this, char a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  int PersistedLocation; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int16 *v10; // r9
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int16 *v16; // r9
  struct _FILETIME v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r9
  unsigned __int16 *v20; // rax
  int v21; // r8d
  int v22; // ecx
  __int64 v23; // rcx
  unsigned __int16 *v24; // r8
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v29[40]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v30[264]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 0;
  if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved )
  {
    memset_0(v30, 0, 0x208u);
    PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                          v30,
                          v5,
                          L"DataCollectionGroupPolicy",
                          L"Software\\Policies\\Microsoft\\Windows\\DataCollection",
                          1);
    v10 = v30;
    v11 = PersistedLocation;
    if ( PersistedLocation < 0 )
      v10 = L"Software\\Policies\\Microsoft\\Windows\\DataCollection";
    Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v8, v7, v9, v10);
    if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
    {
      Windows::Compat::Shared::Registry::GetPersistedLocation(
        v30,
        v12,
        L"Diagnostics_AllowTelemetry",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
        1);
      v16 = v30;
      if ( v11 < 0 )
        v16 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection";
      Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v14, v13, v15, v16);
    }
    `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved = 1;
  }
  memset_0(v29, 0, sizeof(v29));
  v26 = 40;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v17 = SystemTimeAsFileTime;
  if ( !a2 )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, int *))(**((_QWORD **)this + 11) + 56LL))(
            *((_QWORD *)this + 11),
            L"commercialId",
            v29,
            &v26);
    v19 = v18;
    if ( v18 == -2147024894 )
      v29[0] = 0;
    v20 = v29;
    do
    {
      v21 = *(unsigned __int16 *)((char *)v20
                                + (char *)&`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId
                                - (char *)v29);
      v22 = *v20 - v21;
      if ( v22 )
        break;
      ++v20;
    }
    while ( v21 );
    if ( v22 )
    {
      v4 = 1;
      if ( (int)v19 >= 0 )
        AslLogCallPrintf(
          3,
          "TelCacheProvider::ShouldForceFullSyncForCommercial",
          2004,
          "Full sync may be needed because of Commercial ID change");
    }
    else
    {
      if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
        return v4;
      v23 = *((_QWORD *)this + 11);
      v28 = 0;
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *, __int64))(*(_QWORD *)v23 + 64LL))(
             v23,
             L"lastFullSync",
             &v28,
             v19) < 0 )
      {
        v4 = 1;
        AslLogCallPrintf(
          3,
          "TelCacheProvider::ShouldForceFullSyncForCommercial",
          2018,
          "Full sync may be needed because of Commercial 45 day sync policy");
      }
      else
      {
        LOBYTE(v4) = (unsigned __int64)(*(_QWORD *)&v17 - v28) > 0x235C7496C000LL;
        if ( (unsigned __int64)(*(_QWORD *)&v17 - v28) <= 0x235C7496C000LL )
          return v4;
      }
    }
  }
  if ( `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
    v24 = &`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId;
  else
    v24 = 0;
  (*(void (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 *))(**((_QWORD **)this + 11) + 80LL))(
    *((_QWORD *)this + 11),
    L"commercialId",
    v24);
  (*(void (__fastcall **)(_QWORD, const wchar_t *, struct _FILETIME))(**((_QWORD **)this + 11) + 88LL))(
    *((_QWORD *)this + 11),
    L"lastFullSync",
    v17);
  return v4;
}

```

## disassembly

```asm
0x180012d3c  push    rbp
0x180012d3e  push    rbx
0x180012d3f  push    rsi
0x180012d40  push    rdi
0x180012d41  push    r14
0x180012d43  push    r15
0x180012d45  lea     rbp, [rsp-1C8h]
0x180012d4d  sub     rsp, 2C8h
0x180012d54  mov     rax, cs:__security_cookie
0x180012d5b  xor     rax, rsp
0x180012d5e  mov     [rbp+1F0h+var_40], rax
0x180012d65  xor     r15d, r15d
0x180012d68  mov     sil, dl
0x180012d6b  cmp     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, r15b; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x180012d72  mov     r14, rcx
0x180012d75  mov     edi, r15d
0x180012d78  jnz     loc_180012E08
0x180012d7e  xor     edx, edx; Val
0x180012d80  lea     rcx, [rbp+1F0h+var_250]; void *
0x180012d84  mov     r8d, 208h; Size
0x180012d8a  call    memset_0
0x180012d8f  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180012d96  mov     [rsp+2F0h+var_2D0], 1; int
0x180012d9e  lea     r8, aDatacollection; "DataCollectionGroupPolicy"
0x180012da5  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x180012da9  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180012dae  lea     r9, [rbp+1F0h+var_250]
0x180012db2  mov     ebx, eax
0x180012db4  test    eax, eax
0x180012db6  jns     short loc_180012DBF
0x180012db8  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180012dbf  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x180012dc4  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180012dcc  jnz     short loc_180012E01
0x180012dce  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180012dd5  mov     [rsp+2F0h+var_2D0], 1; int
0x180012ddd  lea     r8, aDiagnosticsAll; "Diagnostics_AllowTelemetry"
0x180012de4  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x180012de8  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180012ded  lea     r9, [rbp+1F0h+var_250]
0x180012df1  test    ebx, ebx
0x180012df3  jns     short loc_180012DFC
0x180012df5  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180012dfc  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x180012e01  mov     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x180012e08  xor     edx, edx; Val
0x180012e0a  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x180012e0f  lea     r8d, [rdx+50h]; Size
0x180012e13  call    memset_0
0x180012e18  lea     rcx, [rsp+2F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012e1d  mov     [rsp+2F0h+var_2C0], 28h ; '('
0x180012e25  mov     qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180012e2a  call    cs:__imp_GetSystemTimeAsFileTime
0x180012e30  mov     rbx, qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime]
0x180012e35  test    sil, sil
0x180012e38  jnz     loc_180012F28
0x180012e3e  mov     rcx, [r14+58h]
0x180012e42  lea     r9, [rsp+2F0h+var_2C0]
0x180012e47  lea     r8, [rsp+2F0h+var_2A0]
0x180012e4c  lea     rdx, aCommercialid_0; "commercialId"
0x180012e53  mov     rax, [rcx]
0x180012e56  mov     rax, [rax+38h]
0x180012e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5f  mov     r9d, eax
0x180012e62  cmp     eax, 80070002h
0x180012e67  jnz     short loc_180012E6F
0x180012e69  mov     [rsp+2F0h+var_2A0], r15w
0x180012e6f  lea     rax, [rsp+2F0h+var_2A0]
0x180012e74  lea     rdx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180012e7b  sub     rdx, rax
0x180012e7e  movzx   ecx, word ptr [rax]
0x180012e81  movzx   r8d, word ptr [rax+rdx]
0x180012e86  sub     ecx, r8d
0x180012e89  jnz     short loc_180012E94
0x180012e8b  add     rax, 2
0x180012e8f  test    r8d, r8d
0x180012e92  jnz     short loc_180012E7E
0x180012e94  test    ecx, ecx
0x180012e96  jz      short loc_180012EB5
0x180012e98  mov     edi, 1
0x180012e9d  test    r9d, r9d
0x180012ea0  js      loc_180012F28
0x180012ea6  lea     r9, aFullSyncMayBeN_3; "Full sync may be needed because of Comm"...
0x180012ead  mov     r8d, 7D4h
0x180012eb3  jmp     short loc_180012F17
0x180012eb5  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180012ebd  jz      loc_180012F6F
0x180012ec3  mov     rcx, [r14+58h]
0x180012ec7  lea     r8, [rsp+2F0h+var_2B0]
0x180012ecc  mov     [rsp+2F0h+var_2B0], r15
0x180012ed1  lea     rdx, aLastfullsync; "lastFullSync"
0x180012ed8  mov     rax, [rcx]
0x180012edb  mov     rax, [rax+40h]
0x180012edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee4  test    eax, eax
0x180012ee6  js      short loc_180012F05
0x180012ee8  mov     rax, rbx
0x180012eeb  mov     rcx, 235C7496C000h
0x180012ef5  sub     rax, [rsp+2F0h+var_2B0]
0x180012efa  cmp     rax, rcx
0x180012efd  setnbe  dil
0x180012f01  jbe     short loc_180012F6F
0x180012f03  jmp     short loc_180012F28
0x180012f05  mov     edi, 1
0x180012f0a  lea     r9, aFullSyncMayBeN; "Full sync may be needed because of Comm"...
0x180012f11  mov     r8d, 7E2h
0x180012f17  lea     rdx, aTelcacheprovid_29; "TelCacheProvider::ShouldForceFullSyncFo"...
0x180012f1e  mov     ecx, 3
0x180012f23  call    AslLogCallPrintf
0x180012f28  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, r15w; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180012f30  lea     rdx, aCommercialid_0; "commercialId"
0x180012f37  mov     rcx, [r14+58h]
0x180012f3b  mov     rax, [rcx]
0x180012f3e  mov     rax, [rax+50h]
0x180012f42  jz      short loc_180012F4D
0x180012f44  lea     r8, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x180012f4b  jmp     short loc_180012F50
0x180012f4d  xor     r8d, r8d
0x180012f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f55  mov     rcx, [r14+58h]
0x180012f59  lea     rdx, aLastfullsync; "lastFullSync"
0x180012f60  mov     r8, rbx
0x180012f63  mov     r9, [rcx]
0x180012f66  mov     rax, [r9+58h]
0x180012f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f6f  mov     eax, edi
0x180012f71  mov     rcx, [rbp+1F0h+var_40]
0x180012f78  xor     rcx, rsp; StackCookie
0x180012f7b  call    __security_check_cookie
0x180012f80  add     rsp, 2C8h
0x180012f87  pop     r15
0x180012f89  pop     r14
0x180012f8b  pop     rdi
0x180012f8c  pop     rsi
0x180012f8d  pop     rbx
0x180012f8e  pop     rbp
0x180012f8f  retn
```
