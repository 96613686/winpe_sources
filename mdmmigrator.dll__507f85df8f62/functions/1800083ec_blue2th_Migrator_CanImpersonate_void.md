# blue2th::Migrator::CanImpersonate(void)

- ea: `0x1800083ec`
- end: `0x180008518`
- name: `?CanImpersonate@Migrator@blue2th@@QEAA_NXZ`
- size: `300`
- prototype: `bool __fastcall(blue2th::Migrator *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008940`

## callees

- `0x1800022e0`
- `0x180007720`
- `0x180007818`
- `0x180007b38`
- `0x180007f40`
- `0x1800082ac`
- `0x1800083ec`
- `0x1800097fc`

## import_xrefs

- `DMCmnUtils!DmRevertToSelf` at `0x1800084c3`
- `DMCmnUtils!DmRevertToSelf` at `0x1800084c3`
- `DMCmnUtils!DmImpersonate` at `0x180008474`
- `DMCmnUtils!DmImpersonate` at `0x180008474`

## pseudocode

```c
bool __fastcall blue2th::Migrator::CanImpersonate(blue2th::Migrator *this)
{
  unsigned __int64 v2; // r8
  __int64 v3; // rax
  const unsigned __int16 *v4; // rcx
  int v5; // eax
  __int64 v6; // r8
  int v7; // ebx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-29h]
  int v11; // [rsp+30h] [rbp-19h] BYREF
  _OWORD v12[2]; // [rsp+38h] [rbp-11h] BYREF
  char *v13[4]; // [rsp+58h] [rbp+Fh] BYREF
  int v14[4]; // [rsp+78h] [rbp+2Fh] BYREF
  int *v15; // [rsp+88h] [rbp+3Fh]
  __int64 v16; // [rsp+90h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  memset(v12, 0, sizeof(v12));
  v2 = -1;
  do
    ++v2;
  while ( userSidRtv[v2] );
  std::wstring::_Construct<1,unsigned short const *>(v12, userSidRtv, v2);
  v3 = std::map<std::wstring,std::wstring>::operator[](this, v12);
  std::wstring::wstring((__int64)v13, v3);
  std::wstring::~wstring((char **)v12);
  v4 = (const unsigned __int16 *)v13;
  if ( v13[3] > (char *)7 )
    v4 = (const unsigned __int16 *)v13[0];
  v5 = DmImpersonate(v4);
  v7 = v5;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
  {
    v11 = v5;
    v15 = &v11;
    v16 = 4;
    McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, Impersonation, v6, 2, v14);
  }
  if ( v7 >= 0 && v7 != 1 )
  {
    v8 = DmRevertToSelf();
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\migrator.cpp",
        (const char *)(unsigned int)v8,
        v10);
  }
  std::wstring::~wstring(v13);
  return v7 >= 0;
}

```

## disassembly

```asm
0x1800083ec  mov     [rsp-8+arg_8], rbx
0x1800083f1  mov     [rsp-8+arg_10], rdi
0x1800083f6  push    rbp
0x1800083f7  lea     rbp, [rsp-57h]
0x1800083fc  sub     rsp, 0A0h
0x180008403  mov     rax, cs:__security_cookie
0x18000840a  xor     rax, rsp
0x18000840d  mov     [rbp+57h+var_8], rax
0x180008411  mov     rbx, rcx
0x180008414  mov     rdx, cs:?userSidRtv@@3PEBGEB; ushort const * const userSidRtv
0x18000841b  xorps   xmm0, xmm0
0x18000841e  movups  [rbp+57h+var_68], xmm0
0x180008422  xorps   xmm1, xmm1
0x180008425  movdqu  [rbp+57h+var_58], xmm1
0x18000842a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000842e  xor     edi, edi
0x180008430  inc     r8
0x180008433  cmp     [rdx+r8*2], di
0x180008438  jnz     short loc_180008430
0x18000843a  lea     rcx, [rbp+57h+var_68]
0x18000843e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180008443  nop
0x180008444  lea     rdx, [rbp+57h+var_68]
0x180008448  mov     rcx, rbx
0x18000844b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180008450  mov     rdx, rax
0x180008453  lea     rcx, [rbp+57h+var_48]
0x180008457  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000845c  nop
0x18000845d  lea     rcx, [rbp+57h+var_68]; void *
0x180008461  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008466  lea     rcx, [rbp+57h+var_48]
0x18000846a  cmp     [rbp+57h+var_30], 7
0x18000846f  cmova   rcx, [rbp+57h+var_48]
0x180008474  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18000847a  mov     ebx, eax
0x18000847c  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x180008483  jz      short loc_1800084BA
0x180008485  mov     [rbp+57h+var_70], eax
0x180008488  lea     rax, [rbp+57h+var_70]
0x18000848c  mov     [rbp+57h+var_18], rax
0x180008490  mov     [rbp+57h+var_10], 4
0x180008498  lea     rax, [rbp+57h+var_28]
0x18000849c  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800084a1  mov     r9d, 2
0x1800084a7  lea     rdx, Impersonation
0x1800084ae  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x1800084b5  call    McGenEventWrite_EventWriteTransfer
0x1800084ba  test    ebx, ebx
0x1800084bc  js      short loc_1800084D1
0x1800084be  cmp     ebx, 1
0x1800084c1  jz      short loc_1800084D1
0x1800084c3  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800084c9  mov     rcx, [rbp+5Fh]; this
0x1800084cd  test    eax, eax
0x1800084cf  js      short loc_180008503
0x1800084d1  shr     ebx, 1Fh
0x1800084d4  xor     bl, 1
0x1800084d7  lea     rcx, [rbp+57h+var_48]; void *
0x1800084db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800084e0  mov     al, bl
0x1800084e2  mov     rcx, [rbp+57h+var_8]
0x1800084e6  xor     rcx, rsp; StackCookie
0x1800084e9  call    __security_check_cookie
0x1800084ee  lea     r11, [rsp+0A0h+var_s0]
0x1800084f6  mov     rbx, [r11+18h]
0x1800084fa  mov     rdi, [r11+20h]
0x1800084fe  mov     rsp, r11
0x180008501  pop     rbp
0x180008502  retn
0x180008503  mov     r9d, eax; char *
0x180008506  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000850d  mov     edx, 0BAh; void *
0x180008512  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
