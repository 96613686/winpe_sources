# DownloadFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *,char * *,uint *,ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadResponseImpl *,long (*)(OneSettingsDownloadResponseImpl *),&OneSettingsFreeDownloadResponse(OneSettingsDownloadResponseImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadResponseImpl *,OneSettingsDownloadResponseImpl *,0,std::nullptr_t>>> &)

- ea: `0x1400126c4`
- end: `0x140012921`
- name: `?DownloadFromOneSettings@@YAJPEBG00PEAKPEAPEADPEAIPEAPEAGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUOneSettingsDownloadResponseImpl@@P6AJPEAU1@@Z$1?OneSettingsFreeDownloadResponse@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012928`
- `0x1400143cc`

## callees

- `0x1400126c4`
- `0x1400193cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001273e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400127d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001273e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400127d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001275d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400127f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001275d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400127f6`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x1400127e8`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x1400127e8`
- `OneSettingsClient!OneSettingsEndDownloadSession` at `0x140012903`
- `OneSettingsClient!OneSettingsEndDownloadSession` at `0x140012903`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x14001279a`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x1400127b7`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x14001279a`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x1400127b7`
- `OneSettingsClient!OneSettingsGetResponseDwordProperty` at `0x140012845`
- `OneSettingsClient!OneSettingsGetResponseDwordProperty` at `0x140012845`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x140012775`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x140012775`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x140012721`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x140012721`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x140012829`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x140012829`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x14001287a`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x14001287a`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x14001274f`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x1400128ed`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x14001274f`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x1400128ed`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x140012861`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x140012861`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1400126c4  mov     [rsp-38h+arg_10], r8
0x1400126c9  mov     [rsp-38h+arg_0], rcx
0x1400126ce  push    rbp
0x1400126cf  push    rbx
0x1400126d0  push    rsi
0x1400126d1  push    rdi
0x1400126d2  push    r12
0x1400126d4  push    r14
0x1400126d6  push    r15
0x1400126d8  mov     rbp, rsp
0x1400126db  sub     rsp, 40h
0x1400126df  mov     r12, r9
0x1400126e2  mov     r15, rdx
0x1400126e5  mov     rbx, rcx
0x1400126e8  xor     ecx, ecx
0x1400126ea  mov     [rbp+var_10], rcx
0x1400126ee  mov     [rbp+arg_18], rcx
0x1400126f2  test    r9, r9
0x1400126f5  jnz     short loc_140012701
0x1400126f7  mov     edi, 80004003h
0x1400126fc  jmp     loc_1400128E4
0x140012701  mov     r14, [rbp+arg_20]
0x140012705  test    r14, r14
0x140012708  jz      short loc_1400126F7
0x14001270a  cmp     [rbp+arg_30], rcx
0x14001270e  jz      short loc_1400126F7
0x140012710  mov     edi, ecx
0x140012712  mov     [rbp+var_10], rcx
0x140012716  lea     rdx, [rbp+var_10]
0x14001271a  lea     rcx, aSiuf; "siuf"
0x140012721  call    cs:__imp_OneSettingsStartDownloadSession
0x140012728  nop     dword ptr [rax+rax+00h]
0x14001272d  test    eax, eax
0x14001272f  js      loc_1400128E4
0x140012735  mov     rsi, [rbp+arg_18]
0x140012739  test    rsi, rsi
0x14001273c  jz      short loc_14001276D
0x14001273e  call    cs:__imp_GetLastError
0x140012745  nop     dword ptr [rax+rax+00h]
0x14001274a  mov     ebx, eax
0x14001274c  mov     rcx, rsi
0x14001274f  call    cs:__imp_OneSettingsFreeDownloadConfig
0x140012756  nop     dword ptr [rax+rax+00h]
0x14001275b  mov     ecx, ebx; dwErrCode
0x14001275d  call    cs:__imp_SetLastError
0x140012764  nop     dword ptr [rax+rax+00h]
0x140012769  mov     rbx, [rbp+arg_0]
0x14001276d  mov     [rbp+arg_18], rdi
0x140012771  lea     rcx, [rbp+arg_18]
0x140012775  call    cs:__imp_OneSettingsCreateDownloadConfig
0x14001277c  nop     dword ptr [rax+rax+00h]
0x140012781  test    eax, eax
0x140012783  js      loc_1400128E4
0x140012789  test    r15, r15
0x14001278c  jz      short loc_1400127AE
0x14001278e  mov     r8, r15
0x140012791  mov     edx, 1
0x140012796  mov     rcx, [rbp+arg_18]
0x14001279a  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x1400127a1  nop     dword ptr [rax+rax+00h]
0x1400127a6  test    eax, eax
0x1400127a8  js      loc_1400128E4
0x1400127ae  mov     r8, rbx
0x1400127b1  xor     edx, edx
0x1400127b3  mov     rcx, [rbp+arg_18]
0x1400127b7  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x1400127be  nop     dword ptr [rax+rax+00h]
0x1400127c3  test    eax, eax
0x1400127c5  js      loc_1400128E4
0x1400127cb  mov     rsi, [rbp+arg_38]
0x1400127cf  mov     r15, [rsi]
0x1400127d2  test    r15, r15
0x1400127d5  jz      short loc_140012802
0x1400127d7  call    cs:__imp_GetLastError
0x1400127de  nop     dword ptr [rax+rax+00h]
0x1400127e3  mov     ebx, eax
0x1400127e5  mov     rcx, r15
0x1400127e8  call    cs:__imp_OneSettingsFreeDownloadResponse
0x1400127ef  nop     dword ptr [rax+rax+00h]
0x1400127f4  mov     ecx, ebx; dwErrCode
0x1400127f6  call    cs:__imp_SetLastError
0x1400127fd  nop     dword ptr [rax+rax+00h]
0x140012802  mov     [rsi], rdi
0x140012805  mov     rax, [rbp+arg_18]
0x140012809  mov     [rsp+40h+var_18], rsi
0x14001280e  mov     [rsp+40h+var_20], rax
0x140012813  lea     r9, aV20; "v2.0"
0x14001281a  mov     r8, [rbp+arg_10]
0x14001281e  lea     rdx, aSiuf; "siuf"
0x140012825  mov     rcx, [rbp+var_10]
0x140012829  call    cs:__imp_OneSettingsDownloadEndpoint
0x140012830  nop     dword ptr [rax+rax+00h]
0x140012835  test    eax, eax
0x140012837  js      loc_1400128E4
0x14001283d  mov     r8, r12
0x140012840  xor     edx, edx
0x140012842  mov     rcx, [rsi]
0x140012845  call    cs:__imp_OneSettingsGetResponseDwordProperty
0x14001284c  nop     dword ptr [rax+rax+00h]
0x140012851  test    eax, eax
0x140012853  js      loc_1400128E4
0x140012859  mov     r8, r14
0x14001285c  xor     edx, edx
0x14001285e  mov     rcx, [rsi]
0x140012861  call    cs:__imp_OneSettingsGetResponseStringProperty
0x140012868  nop     dword ptr [rax+rax+00h]
0x14001286d  test    eax, eax
0x14001286f  js      short loc_1400128E4
0x140012871  mov     r8, [rbp+arg_30]
0x140012875  xor     edx, edx
0x140012877  mov     rcx, [rsi]
0x14001287a  call    cs:__imp_OneSettingsGetResponseWideStringProperty
0x140012881  nop     dword ptr [rax+rax+00h]
0x140012886  test    eax, eax
0x140012888  js      short loc_1400128E4
0x14001288a  cmp     dword ptr [r12], 0C8h
0x140012892  jz      short loc_1400128BC
0x140012894  cmp     dword ptr [r12], 194h
0x14001289c  jnz     short loc_1400128A5
0x14001289e  mov     edi, 5DD194h
0x1400128a3  jmp     short loc_1400128E4
0x1400128a5  mov     edi, 805DD400h
0x1400128aa  mov     eax, 5DD130h
0x1400128af  cmp     dword ptr [r12], 130h
0x1400128b7  cmovz   edi, eax
0x1400128ba  jmp     short loc_1400128E4
0x1400128bc  mov     rax, [r14]
0x1400128bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400128c3  inc     rbx
0x1400128c6  cmp     [rax+rbx], dil
0x1400128ca  jnz     short loc_1400128C3
0x1400128cc  mov     eax, 0FFFFFFFFh
0x1400128d1  cmp     rbx, rax
0x1400128d4  jb      short loc_1400128DB
0x1400128d6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400128db  lea     ecx, [rbx+1]
0x1400128de  mov     rax, [rbp+arg_28]
0x1400128e2  mov     [rax], ecx
0x1400128e4  mov     rcx, [rbp+arg_18]
0x1400128e8  test    rcx, rcx
0x1400128eb  jz      short loc_1400128FA
0x1400128ed  call    cs:__imp_OneSettingsFreeDownloadConfig
0x1400128f4  nop     dword ptr [rax+rax+00h]
0x1400128f9  nop
0x1400128fa  mov     rcx, [rbp+var_10]
0x1400128fe  test    rcx, rcx
0x140012901  jz      short loc_14001290F
0x140012903  call    cs:__imp_OneSettingsEndDownloadSession
0x14001290a  nop     dword ptr [rax+rax+00h]
0x14001290f  mov     eax, edi
0x140012911  add     rsp, 40h
0x140012915  pop     r15
0x140012917  pop     r14
0x140012919  pop     r12
0x14001291b  pop     rdi
0x14001291c  pop     rsi
0x14001291d  pop     rbx
0x14001291e  pop     rbp
0x14001291f  retn
```
