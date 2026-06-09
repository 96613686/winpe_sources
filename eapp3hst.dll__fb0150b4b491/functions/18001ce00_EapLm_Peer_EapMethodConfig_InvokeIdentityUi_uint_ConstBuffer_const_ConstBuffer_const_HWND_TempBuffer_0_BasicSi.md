# EapLm::Peer::EapMethodConfig::InvokeIdentityUi(uint,ConstBuffer const &,ConstBuffer const &,HWND__ *,TempBuffer<0> &,BasicSimpleString<wchar_t> &)

- ea: `0x18001ce00`
- end: `0x18001d113`
- name: `?InvokeIdentityUi@EapMethodConfig@Peer@EapLm@@UEAAXIAEBUConstBuffer@@0PEAUHWND__@@AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z`
- size: `787`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x180013d10`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001ce00`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001ce7c`
- `ntdll!EtwEventEnabled` at `0x18001d077`
- `ntdll!EtwEventEnabled` at `0x18001ce7c`
- `ntdll!EtwEventEnabled` at `0x18001d077`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::InvokeIdentityUi(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        void **a7)
{
  _QWORD *v10; // rax
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **); // r14
  void (__fastcall *v12)(const void *); // r12
  __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // rdi
  unsigned int v16; // eax
  unsigned int v17; // eax
  const wchar_t *v18; // rdx
  _UNKNOWN **result; // rax
  unsigned int v20; // [rsp+60h] [rbp-908h] BYREF
  const void *v21; // [rsp+68h] [rbp-900h] BYREF
  const void *v22; // [rsp+70h] [rbp-8F8h] BYREF
  struct _EAP_ERROR *v23; // [rsp+78h] [rbp-8F0h] BYREF
  void (__fastcall *v24)(const void *); // [rsp+80h] [rbp-8E8h]
  _QWORD *v25; // [rsp+88h] [rbp-8E0h]
  __int64 *v26; // [rsp+90h] [rbp-8D8h]
  __int64 v27; // [rsp+98h] [rbp-8D0h]
  __int64 v28; // [rsp+A0h] [rbp-8C8h]
  void (__fastcall *v29)(struct _EAP_ERROR *); // [rsp+A8h] [rbp-8C0h]
  void **v30; // [rsp+B0h] [rbp-8B8h]
  char v31[96]; // [rsp+C0h] [rbp-8A8h] BYREF
  char v32[2048]; // [rsp+120h] [rbp-848h] BYREF

  v25 = a4;
  v26 = a3;
  v27 = a1;
  v28 = a5;
  v30 = a7;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v32, 0x800u, "EapPeerInvokeIdentityUI Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v32);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a2);
  HeapAllocator::Free(*(void **)a6);
  *(_QWORD *)a6 = 0;
  *(_QWORD *)(a6 + 8) = 0;
  BasicSimpleString<wchar_t>::Assign(a7, 0);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 176), 0);
  v10 = *(_QWORD **)(a1 + 176);
  v11 = (__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **))v10[27];
  v12 = (void (__fastcall *)(const void *))v10[29];
  v24 = v12;
  v29 = (void (__fastcall *)(struct _EAP_ERROR *))v10[28];
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v13 = *a4;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v25[1]);
  v15 = *v26;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v26[1]);
  v17 = v11(v27 + 16, a2, v28, v16, v15, v14, v13, &v20, &v21, (__int64 *)&v22, &v23);
  if ( v17 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v31, v23, v17);
    v29(v23);
    EapHost::EapException::Throw(L"EapPeerInvokeInteractiveUI", v18, (const struct EapHost::EapError *)v31);
  }
  try
  {
    TempBuffer<0>::Assign(a6, v20, v21);
    BasicSimpleString<wchar_t>::Assign(v30, (__int64)v22);
  }
  catch ( std::bad_alloc )
  {
    v24(v21);
    v24(v22);
    throw;
  }
  v12(v21);
  v12(v22);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v32, 0x800u, "EapPeerInvokeIdentityUI Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v32);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          19,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001ce00  push    rbx
0x18001ce02  push    rsi
0x18001ce03  push    rdi
0x18001ce04  push    r12
0x18001ce06  push    r13
0x18001ce08  push    r14
0x18001ce0a  push    r15
0x18001ce0c  sub     rsp, 930h
0x18001ce13  mov     rax, cs:__security_cookie
0x18001ce1a  xor     rax, rsp
0x18001ce1d  mov     [rsp+968h+var_48], rax
0x18001ce25  mov     rsi, r9
0x18001ce28  mov     [rsp+968h+var_8E0], r9
0x18001ce30  mov     [rsp+968h+var_8D8], r8
0x18001ce38  mov     r15d, edx
0x18001ce3b  mov     rdi, rcx
0x18001ce3e  mov     [rsp+968h+var_8D0], rcx
0x18001ce46  mov     rax, [rsp+968h+arg_20]
0x18001ce4e  mov     [rsp+968h+var_8C8], rax
0x18001ce56  mov     r13, [rsp+968h+arg_28]
0x18001ce5e  mov     rbx, [rsp+968h+arg_30]
0x18001ce66  mov     [rsp+968h+var_8B8], rbx
0x18001ce6e  lea     rdx, DebugInfoEvent
0x18001ce75  mov     rcx, cs:eaphost_Context
0x18001ce7c  call    cs:__imp_EtwEventEnabled
0x18001ce82  xor     r14d, r14d
0x18001ce85  test    al, al
0x18001ce87  jz      short loc_18001CECD
0x18001ce89  mov     r9d, r15d
0x18001ce8c  lea     r8, aEappeerinvokei_5; "EapPeerInvokeIdentityUI Entry:\n flags("...
0x18001ce93  mov     edx, 800h; unsigned __int64
0x18001ce98  lea     rcx, [rsp+968h+var_848]; char *
0x18001cea0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001cea5  test    eax, eax
0x18001cea7  js      short loc_18001CECD
0x18001cea9  cmp     cs:Microsoft_Windows_EapHostEnableBits, r14b
0x18001ceb0  jge     short loc_18001CECD
0x18001ceb2  lea     r8, [rsp+968h+var_848]
0x18001ceba  lea     rdx, DebugInfoEvent
0x18001cec1  lea     rcx, eaphost_Context
0x18001cec8  call    McTemplateU0s_EtwEventWriteTransfer
0x18001cecd  lea     rax, WPP_GLOBAL_Control
0x18001ced4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cedb  cmp     rcx, rax
0x18001cede  jz      short loc_18001CEFE
0x18001cee0  test    byte ptr [rcx+1Ch], 4
0x18001cee4  jz      short loc_18001CEFE
0x18001cee6  mov     edx, 12h
0x18001ceeb  mov     r9d, r15d
0x18001ceee  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001cef5  mov     rcx, [rcx+10h]
0x18001cef9  call    WPP_SF_d
0x18001cefe  mov     rcx, [r13+0]; void *
0x18001cf02  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001cf07  mov     [r13+0], r14
0x18001cf0b  mov     [r13+8], r14
0x18001cf0f  xor     edx, edx
0x18001cf11  mov     rcx, rbx
0x18001cf14  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001cf19  xor     edx, edx; bool
0x18001cf1b  mov     rcx, [rdi+0B0h]; this
0x18001cf22  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001cf27  mov     rax, [rdi+0B0h]
0x18001cf2e  mov     r14, [rax+0D8h]
0x18001cf35  mov     r12, [rax+0E8h]
0x18001cf3c  mov     [rsp+968h+var_8E8], r12
0x18001cf44  mov     rax, [rax+0E0h]
0x18001cf4b  mov     [rsp+968h+var_8C0], rax
0x18001cf53  xor     eax, eax
0x18001cf55  mov     [rsp+968h+var_908], eax
0x18001cf59  mov     [rsp+968h+var_900], rax
0x18001cf5e  mov     [rsp+968h+var_8F8], rax
0x18001cf63  mov     [rsp+968h+var_8F0], rax
0x18001cf68  mov     rsi, [rsi]
0x18001cf6b  mov     rcx, [rsp+968h+var_8E0]
0x18001cf73  mov     rcx, [rcx+8]
0x18001cf77  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001cf7c  mov     ebx, eax
0x18001cf7e  mov     rax, [rsp+968h+var_8D8]
0x18001cf86  mov     rdi, [rax]
0x18001cf89  mov     rcx, [rax+8]
0x18001cf8d  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001cf92  mov     rcx, [rsp+968h+var_8D0]
0x18001cf9a  add     rcx, 10h
0x18001cf9e  lea     rdx, [rsp+968h+var_8F0]
0x18001cfa3  mov     [rsp+968h+var_918], rdx
0x18001cfa8  lea     rdx, [rsp+968h+var_8F8]
0x18001cfad  mov     [rsp+968h+var_920], rdx
0x18001cfb2  lea     rdx, [rsp+968h+var_900]
0x18001cfb7  mov     [rsp+968h+var_928], rdx
0x18001cfbc  lea     rdx, [rsp+968h+var_908]
0x18001cfc1  mov     [rsp+968h+var_930], rdx
0x18001cfc6  mov     [rsp+968h+var_938], rsi
0x18001cfcb  mov     [rsp+968h+var_940], ebx
0x18001cfcf  mov     [rsp+968h+var_948], rdi
0x18001cfd4  mov     r9d, eax
0x18001cfd7  mov     r8, [rsp+968h+var_8C8]
0x18001cfdf  mov     edx, r15d
0x18001cfe2  mov     rax, r14
0x18001cfe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfea  test    eax, eax
0x18001cfec  jz      short loc_18001D02B
0x18001cfee  mov     r8d, eax; unsigned int
0x18001cff1  mov     rdx, [rsp+968h+var_8F0]; struct _EAP_ERROR *
0x18001cff6  lea     rcx, [rsp+968h+var_8A8]; this
0x18001cffe  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001d003  nop
0x18001d004  mov     rcx, [rsp+968h+var_8F0]
0x18001d009  mov     rax, [rsp+968h+var_8C0]
0x18001d011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d016  lea     r8, [rsp+968h+var_8A8]; struct EapHost::EapError *
0x18001d01e  lea     rcx, aEappeerinvokei_2; "EapPeerInvokeInteractiveUI"
0x18001d025  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001d02b  mov     edx, [rsp+968h+var_908]
0x18001d02f  mov     r8, [rsp+968h+var_900]
0x18001d034  mov     rcx, r13
0x18001d037  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001d03c  mov     rdx, [rsp+968h+var_8F8]
0x18001d041  mov     rcx, [rsp+968h+var_8B8]
0x18001d049  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001d04e  nop
0x18001d04f  mov     rcx, [rsp+968h+var_900]
0x18001d054  mov     rax, r12
0x18001d057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d05c  mov     rcx, [rsp+968h+var_8F8]
0x18001d061  mov     rax, r12
0x18001d064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d069  lea     rdx, DebugInfoEvent
0x18001d070  mov     rcx, cs:eaphost_Context
0x18001d077  call    cs:__imp_EtwEventEnabled
0x18001d07d  test    al, al
0x18001d07f  jz      short loc_18001D0C2
0x18001d081  lea     r8, aEappeerinvokei_1; "EapPeerInvokeIdentityUI Exit"
0x18001d088  mov     edx, 800h; unsigned __int64
0x18001d08d  lea     rcx, [rsp+968h+var_848]; char *
0x18001d095  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d09a  test    eax, eax
0x18001d09c  js      short loc_18001D0C2
0x18001d09e  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001d0a5  jge     short loc_18001D0C2
0x18001d0a7  lea     r8, [rsp+968h+var_848]
0x18001d0af  lea     rdx, DebugInfoEvent
0x18001d0b6  lea     rcx, eaphost_Context
0x18001d0bd  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0c9  lea     rax, WPP_GLOBAL_Control
0x18001d0d0  cmp     rcx, rax
0x18001d0d3  jz      short loc_18001D0F0
0x18001d0d5  test    byte ptr [rcx+1Ch], 4
0x18001d0d9  jz      short loc_18001D0F0
0x18001d0db  mov     edx, 13h
0x18001d0e0  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d0e7  mov     rcx, [rcx+10h]
0x18001d0eb  call    WPP_SF_
0x18001d0f0  mov     rcx, [rsp+968h+var_48]
0x18001d0f8  xor     rcx, rsp; StackCookie
0x18001d0fb  call    __security_check_cookie
0x18001d100  add     rsp, 930h
0x18001d107  pop     r15
0x18001d109  pop     r14
0x18001d10b  pop     r13
0x18001d10d  pop     r12
0x18001d10f  pop     rdi
0x18001d110  pop     rsi
0x18001d111  pop     rbx
0x18001d112  retn
```
