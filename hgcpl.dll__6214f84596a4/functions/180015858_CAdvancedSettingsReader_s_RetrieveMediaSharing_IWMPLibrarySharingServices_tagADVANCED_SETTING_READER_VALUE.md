# CAdvancedSettingsReader::_s_RetrieveMediaSharing(IWMPLibrarySharingServices *,tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x180015858`
- end: `0x1800159c5`
- name: `?_s_RetrieveMediaSharing@CAdvancedSettingsReader@@CAXPEAUIWMPLibrarySharingServices@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `365`
- prototype: `void __fastcall(struct IWMPLibrarySharingServices *, struct tagADVANCED_SETTING_READER_VALUE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013368`

## callees

- `0x180006dfc`
- `0x180008fd0`
- `0x180012d78`
- `0x180013aa4`
- `0x180015858`
- `0x180015db8`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001590f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001590f`

## pseudocode

```c
void __fastcall CAdvancedSettingsReader::_s_RetrieveMediaSharing(
        struct IWMPLibrarySharingServices *a1,
        struct tagADVANCED_SETTING_READER_VALUE *a2)
{
  char v4; // di
  signed int v5; // eax
  unsigned int v6; // ebx
  const wchar_t **v7; // rax
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  __int16 v10; // r8
  unsigned int v11; // r9d
  unsigned int i; // edx
  __int64 v13; // rax
  unsigned int v14; // r9d
  unsigned int v15; // edx
  int v16; // [rsp+20h] [rbp-178h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-170h] BYREF
  _QWORD v18[42]; // [rsp+30h] [rbp-168h] BYREF

  v4 = 0;
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "RetrieveMediaSharing");
  v18[0] = &AdvancedSettingsTelemetry::RetrieveMediaSharing::`vftable';
  AdvancedSettingsTelemetry::RetrieveMediaSharing::StartActivity((AdvancedSettingsTelemetry::RetrieveMediaSharing *)v18);
  v16 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWMPLibrarySharingServices *, int *))a1->lpVtbl->isLibraryShared)(a1, &v16);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v10 = v16;
  }
  else
  {
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v7 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v5);
      v9 = L"???";
      if ( *v7 )
        v9 = *v7;
      McTemplateU0z_EventWriteTransfer(v8, Operational_RetrieveMediaSharingFailed, v9);
      v4 = 1;
    }
    if ( (v4 & 1) != 0 )
      LocalFree(hMem);
    v10 = 0;
    LOWORD(v16) = 0;
  }
  v11 = 0;
  for ( i = 1; i < 2; ++i )
  {
    if ( *((_WORD *)qword_18001EC30 + 6 * i) == v10 )
    {
      v11 = i;
      break;
    }
  }
  v13 = v11;
  v14 = 0;
  v15 = 1;
  *(_DWORD *)a2 = *((_DWORD *)&qword_18001EC30[1] + 3 * v13);
  while ( v15 < 2 )
  {
    if ( *((_WORD *)qword_18001EC30 + 6 * v15) == v10 )
    {
      v14 = v15;
      break;
    }
    ++v15;
  }
  *((_DWORD *)a2 + 1) = *((_DWORD *)qword_18001EC30 + 3 * v14 + 1);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, v6);
  AdvancedSettingsTelemetry::RetrieveMediaSharing::~RetrieveMediaSharing((AdvancedSettingsTelemetry::RetrieveMediaSharing *)v18);
}

```

## disassembly

```asm
0x180015858  mov     [rsp+arg_10], rbx
0x18001585d  mov     [rsp+arg_18], rsi
0x180015862  push    rdi
0x180015863  sub     rsp, 190h
0x18001586a  mov     rax, cs:__security_cookie
0x180015871  xor     rax, rsp
0x180015874  mov     [rsp+198h+var_18], rax
0x18001587c  mov     rsi, rdx
0x18001587f  mov     rbx, rcx
0x180015882  xor     edi, edi
0x180015884  lea     rdx, aRetrievemedias; "RetrieveMediaSharing"
0x18001588b  lea     rcx, [rsp+198h+var_168]
0x180015890  mov     [rsp+198h+var_178], edi
0x180015894  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015899  lea     rax, ??_7RetrieveMediaSharing@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::RetrieveMediaSharing::`vftable'
0x1800158a0  lea     rcx, [rsp+198h+var_168]; this
0x1800158a5  mov     [rsp+198h+var_168], rax
0x1800158aa  call    ?StartActivity@RetrieveMediaSharing@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::RetrieveMediaSharing::StartActivity(void)
0x1800158af  xor     eax, eax
0x1800158b1  lea     rdx, [rsp+198h+var_178]
0x1800158b6  mov     word ptr [rsp+198h+var_178], ax
0x1800158bb  mov     rcx, rbx
0x1800158be  mov     rax, [rbx]
0x1800158c1  mov     rax, [rax+18h]
0x1800158c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ca  mov     ebx, eax
0x1800158cc  test    eax, eax
0x1800158ce  jns     short loc_180015920
0x1800158d0  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x1800158d7  jz      short loc_180015904
0x1800158d9  mov     edx, eax; dwMessageId
0x1800158db  lea     rcx, [rsp+198h+hMem]; lpBuffer
0x1800158e0  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800158e5  lea     r8, asc_18001ECC8; "???"
0x1800158ec  lea     rdx, Operational_RetrieveMediaSharingFailed
0x1800158f3  cmp     [rax], rdi
0x1800158f6  cmovnz  r8, [rax]
0x1800158fa  call    McTemplateU0z_EventWriteTransfer
0x1800158ff  mov     edi, 1
0x180015904  test    dil, 1
0x180015908  jz      short loc_180015915
0x18001590a  mov     rcx, [rsp+198h+hMem]; hMem
0x18001590f  call    cs:__imp_LocalFree
0x180015915  xor     r8d, r8d
0x180015918  mov     word ptr [rsp+198h+var_178], r8w
0x18001591e  jmp     short loc_180015926
0x180015920  movzx   r8d, word ptr [rsp+198h+var_178]
0x180015926  xor     r9d, r9d
0x180015929  lea     r10, qword_18001EC30
0x180015930  lea     edx, [r9+1]
0x180015934  cmp     edx, 2
0x180015937  jnb     short loc_18001594D
0x180015939  mov     eax, edx
0x18001593b  lea     rcx, [rax+rax*2]
0x18001593f  cmp     [r10+rcx*4], r8w
0x180015944  jz      short loc_18001594A
0x180015946  inc     edx
0x180015948  jmp     short loc_180015934
0x18001594a  mov     r9d, edx
0x18001594d  mov     eax, r9d
0x180015950  xor     r9d, r9d
0x180015953  lea     rax, [rax+rax*2]
0x180015957  mov     eax, [r10+rax*4+8]
0x18001595c  lea     edx, [r9+1]
0x180015960  mov     [rsi], eax
0x180015962  cmp     edx, 2
0x180015965  jnb     short loc_18001597B
0x180015967  mov     eax, edx
0x180015969  lea     rcx, [rax+rax*2]
0x18001596d  cmp     [r10+rcx*4], r8w
0x180015972  jz      short loc_180015978
0x180015974  inc     edx
0x180015976  jmp     short loc_180015962
0x180015978  mov     r9d, edx
0x18001597b  mov     eax, r9d
0x18001597e  lea     rcx, [rsp+198h+var_168]
0x180015983  mov     edx, ebx
0x180015985  lea     rax, [rax+rax*2]
0x180015989  mov     eax, [r10+rax*4+4]
0x18001598e  mov     [rsi+4], eax
0x180015991  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015996  lea     rcx, [rsp+198h+var_168]; this
0x18001599b  call    ??1RetrieveMediaSharing@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::RetrieveMediaSharing::~RetrieveMediaSharing(void)
0x1800159a0  mov     rcx, [rsp+198h+var_18]
0x1800159a8  xor     rcx, rsp; StackCookie
0x1800159ab  call    __security_check_cookie
0x1800159b0  lea     r11, [rsp+198h+var_8]
0x1800159b8  mov     rbx, [r11+20h]
0x1800159bc  mov     rsi, [r11+28h]
0x1800159c0  mov     rsp, r11
0x1800159c3  pop     rdi
0x1800159c4  retn
```
