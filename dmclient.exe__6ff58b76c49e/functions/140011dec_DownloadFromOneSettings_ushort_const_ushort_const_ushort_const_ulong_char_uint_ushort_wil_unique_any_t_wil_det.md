# DownloadFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *,char * *,uint *,ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadResponseImpl *,long (*)(OneSettingsDownloadResponseImpl *),&OneSettingsFreeDownloadResponse(OneSettingsDownloadResponseImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadResponseImpl *,OneSettingsDownloadResponseImpl *,0,std::nullptr_t>>> &)

- ea: `0x140011dec`
- end: `0x140011fe4`
- name: `?DownloadFromOneSettings@@YAJPEBG00PEAKPEAPEADPEAIPEAPEAGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUOneSettingsDownloadResponseImpl@@P6AJPEAU1@@Z$1?OneSettingsFreeDownloadResponse@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, _QWORD *, _DWORD *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011fec`
- `0x140015aec`

## callees

- `0x140011dec`
- `0x1400185c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011ed5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011e73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011e73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011ee8`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x140011ee0`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x140011ee0`
- `OneSettingsClient!OneSettingsEndDownloadSession` at `0x140011fcd`
- `OneSettingsClient!OneSettingsEndDownloadSession` at `0x140011fcd`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x140011ea4`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x140011ebb`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x140011ea4`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x140011ebb`
- `OneSettingsClient!OneSettingsGetResponseDwordProperty` at `0x140011f2b`
- `OneSettingsClient!OneSettingsGetResponseDwordProperty` at `0x140011f2b`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x140011e85`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x140011e85`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x140011e49`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x140011e49`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x140011f15`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x140011f15`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x140011f50`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x140011f50`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140011e6b`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140011fbd`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140011e6b`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140011fbd`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x140011f3d`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x140011f3d`

## pseudocode

```c
__int64 __fastcall DownloadFromOneSettings(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        _QWORD *a5,
        _DWORD *a6,
        __int64 a7,
        _QWORD *a8)
{
  __int64 v10; // rbx
  unsigned int v11; // edi
  _QWORD *v12; // r14
  __int64 v13; // rsi
  DWORD LastError; // ebx
  _QWORD *v15; // rsi
  __int64 v16; // r15
  DWORD v17; // ebx
  unsigned __int64 v18; // rbx
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  __int64 v23; // [rsp+98h] [rbp+58h] BYREF

  v10 = a1;
  v20 = 0;
  v23 = 0;
  if ( a4 && (v12 = a5) != 0 && a7 )
  {
    v11 = 0;
    v20 = 0;
    if ( (int)OneSettingsStartDownloadSession(L"siuf", &v20) >= 0 )
    {
      v13 = v23;
      if ( v23 )
      {
        LastError = GetLastError();
        OneSettingsFreeDownloadConfig(v13);
        SetLastError(LastError);
        v10 = a1;
      }
      v23 = 0;
      if ( (int)OneSettingsCreateDownloadConfig(&v23) >= 0
        && (!a2 || (int)OneSettingsSetConfigWideStringProperty(v23, 1, a2) >= 0)
        && (int)OneSettingsSetConfigWideStringProperty(v23, 0, v10) >= 0 )
      {
        v15 = a8;
        v16 = *a8;
        if ( *a8 )
        {
          v17 = GetLastError();
          OneSettingsFreeDownloadResponse(v16);
          SetLastError(v17);
        }
        *v15 = 0;
        if ( (int)OneSettingsDownloadEndpoint(v20, L"siuf", a3, L"v2.0", v23, v15) >= 0
          && (int)OneSettingsGetResponseDwordProperty(*v15, 0, a4) >= 0
          && (int)OneSettingsGetResponseStringProperty(*v15, 0, v12) >= 0
          && (int)OneSettingsGetResponseWideStringProperty(*v15, 0, a7) >= 0 )
        {
          if ( *a4 == 200 )
          {
            v18 = -1;
            do
              ++v18;
            while ( *(_BYTE *)(*v12 + v18) );
            if ( v18 >= 0xFFFFFFFF )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            *a6 = v18 + 1;
          }
          else if ( *a4 == 404 )
          {
            v11 = 6148500;
          }
          else
          {
            v11 = -2141334528;
            if ( *a4 == 304 )
              v11 = 6148400;
          }
        }
      }
    }
  }
  else
  {
    v11 = -2147467261;
  }
  if ( v23 )
    OneSettingsFreeDownloadConfig(v23);
  if ( v20 )
    OneSettingsEndDownloadSession();
  return v11;
}

```

## disassembly

```asm
0x140011dec  mov     [rsp-38h+arg_10], r8
0x140011df1  mov     [rsp-38h+arg_0], rcx
0x140011df6  push    rbp
0x140011df7  push    rbx
0x140011df8  push    rsi
0x140011df9  push    rdi
0x140011dfa  push    r12
0x140011dfc  push    r14
0x140011dfe  push    r15
0x140011e00  mov     rbp, rsp
0x140011e03  sub     rsp, 40h
0x140011e07  mov     r12, r9
0x140011e0a  mov     r15, rdx
0x140011e0d  mov     rbx, rcx
0x140011e10  xor     ecx, ecx
0x140011e12  mov     [rbp+var_10], rcx
0x140011e16  mov     [rbp+arg_18], rcx
0x140011e1a  test    r9, r9
0x140011e1d  jnz     short loc_140011E29
0x140011e1f  mov     edi, 80004003h
0x140011e24  jmp     loc_140011FB4
0x140011e29  mov     r14, [rbp+arg_20]
0x140011e2d  test    r14, r14
0x140011e30  jz      short loc_140011E1F
0x140011e32  cmp     [rbp+arg_30], rcx
0x140011e36  jz      short loc_140011E1F
0x140011e38  mov     edi, ecx
0x140011e3a  mov     [rbp+var_10], rcx
0x140011e3e  lea     rdx, [rbp+var_10]
0x140011e42  lea     rcx, aSiuf; "siuf"
0x140011e49  call    cs:__imp_OneSettingsStartDownloadSession
0x140011e4f  test    eax, eax
0x140011e51  js      loc_140011FB4
0x140011e57  mov     rsi, [rbp+arg_18]
0x140011e5b  test    rsi, rsi
0x140011e5e  jz      short loc_140011E7D
0x140011e60  call    cs:__imp_GetLastError
0x140011e66  mov     ebx, eax
0x140011e68  mov     rcx, rsi
0x140011e6b  call    cs:__imp_OneSettingsFreeDownloadConfig
0x140011e71  mov     ecx, ebx; dwErrCode
0x140011e73  call    cs:__imp_SetLastError
0x140011e79  mov     rbx, [rbp+arg_0]
0x140011e7d  mov     [rbp+arg_18], rdi
0x140011e81  lea     rcx, [rbp+arg_18]
0x140011e85  call    cs:__imp_OneSettingsCreateDownloadConfig
0x140011e8b  test    eax, eax
0x140011e8d  js      loc_140011FB4
0x140011e93  test    r15, r15
0x140011e96  jz      short loc_140011EB2
0x140011e98  mov     r8, r15
0x140011e9b  mov     edx, 1
0x140011ea0  mov     rcx, [rbp+arg_18]
0x140011ea4  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x140011eaa  test    eax, eax
0x140011eac  js      loc_140011FB4
0x140011eb2  mov     r8, rbx
0x140011eb5  xor     edx, edx
0x140011eb7  mov     rcx, [rbp+arg_18]
0x140011ebb  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x140011ec1  test    eax, eax
0x140011ec3  js      loc_140011FB4
0x140011ec9  mov     rsi, [rbp+arg_38]
0x140011ecd  mov     r15, [rsi]
0x140011ed0  test    r15, r15
0x140011ed3  jz      short loc_140011EEE
0x140011ed5  call    cs:__imp_GetLastError
0x140011edb  mov     ebx, eax
0x140011edd  mov     rcx, r15
0x140011ee0  call    cs:__imp_OneSettingsFreeDownloadResponse
0x140011ee6  mov     ecx, ebx; dwErrCode
0x140011ee8  call    cs:__imp_SetLastError
0x140011eee  mov     [rsi], rdi
0x140011ef1  mov     rax, [rbp+arg_18]
0x140011ef5  mov     [rsp+40h+var_18], rsi
0x140011efa  mov     [rsp+40h+var_20], rax
0x140011eff  lea     r9, aV20; "v2.0"
0x140011f06  mov     r8, [rbp+arg_10]
0x140011f0a  lea     rdx, aSiuf; "siuf"
0x140011f11  mov     rcx, [rbp+var_10]
0x140011f15  call    cs:__imp_OneSettingsDownloadEndpoint
0x140011f1b  test    eax, eax
0x140011f1d  js      loc_140011FB4
0x140011f23  mov     r8, r12
0x140011f26  xor     edx, edx
0x140011f28  mov     rcx, [rsi]
0x140011f2b  call    cs:__imp_OneSettingsGetResponseDwordProperty
0x140011f31  test    eax, eax
0x140011f33  js      short loc_140011FB4
0x140011f35  mov     r8, r14
0x140011f38  xor     edx, edx
0x140011f3a  mov     rcx, [rsi]
0x140011f3d  call    cs:__imp_OneSettingsGetResponseStringProperty
0x140011f43  test    eax, eax
0x140011f45  js      short loc_140011FB4
0x140011f47  mov     r8, [rbp+arg_30]
0x140011f4b  xor     edx, edx
0x140011f4d  mov     rcx, [rsi]
0x140011f50  call    cs:__imp_OneSettingsGetResponseWideStringProperty
0x140011f56  test    eax, eax
0x140011f58  js      short loc_140011FB4
0x140011f5a  cmp     dword ptr [r12], 0C8h
0x140011f62  jz      short loc_140011F8C
0x140011f64  cmp     dword ptr [r12], 194h
0x140011f6c  jnz     short loc_140011F75
0x140011f6e  mov     edi, 5DD194h
0x140011f73  jmp     short loc_140011FB4
0x140011f75  mov     edi, 805DD400h
0x140011f7a  mov     eax, 5DD130h
0x140011f7f  cmp     dword ptr [r12], 130h
0x140011f87  cmovz   edi, eax
0x140011f8a  jmp     short loc_140011FB4
0x140011f8c  mov     rax, [r14]
0x140011f8f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140011f93  inc     rbx
0x140011f96  cmp     [rax+rbx], dil
0x140011f9a  jnz     short loc_140011F93
0x140011f9c  mov     eax, 0FFFFFFFFh
0x140011fa1  cmp     rbx, rax
0x140011fa4  jb      short loc_140011FAB
0x140011fa6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140011fab  lea     ecx, [rbx+1]
0x140011fae  mov     rax, [rbp+arg_28]
0x140011fb2  mov     [rax], ecx
0x140011fb4  mov     rcx, [rbp+arg_18]
0x140011fb8  test    rcx, rcx
0x140011fbb  jz      short loc_140011FC4
0x140011fbd  call    cs:__imp_OneSettingsFreeDownloadConfig
0x140011fc3  nop
0x140011fc4  mov     rcx, [rbp+var_10]
0x140011fc8  test    rcx, rcx
0x140011fcb  jz      short loc_140011FD3
0x140011fcd  call    cs:__imp_OneSettingsEndDownloadSession
0x140011fd3  mov     eax, edi
0x140011fd5  add     rsp, 40h
0x140011fd9  pop     r15
0x140011fdb  pop     r14
0x140011fdd  pop     r12
0x140011fdf  pop     rdi
0x140011fe0  pop     rsi
0x140011fe1  pop     rbx
0x140011fe2  pop     rbp
0x140011fe3  retn
```
