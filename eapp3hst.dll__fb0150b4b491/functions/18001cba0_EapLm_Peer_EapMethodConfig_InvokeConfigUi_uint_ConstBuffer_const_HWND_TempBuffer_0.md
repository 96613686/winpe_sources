# EapLm::Peer::EapMethodConfig::InvokeConfigUi(uint,ConstBuffer const &,HWND__ *,TempBuffer<0> &)

- ea: `0x18001cba0`
- end: `0x18001cdf5`
- name: `?InvokeConfigUi@EapMethodConfig@Peer@EapLm@@UEAAXIAEBUConstBuffer@@PEAUHWND__@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `597`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001cba0`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001cbf4`
- `ntdll!EtwEventEnabled` at `0x18001cd61`
- `ntdll!EtwEventEnabled` at `0x18001cbf4`
- `ntdll!EtwEventEnabled` at `0x18001cd61`

## string_xrefs

- `0x18001cd28`: `EapPeerInvokeConfigUI`
- `0x18001cc03`: `EapPeerInvokeConfigUI Entry:\n flags(%d)`
- `0x18001cd6b`: `EapPeerInvokeConfigUI Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::InvokeConfigUi(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *v8; // rax
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD, _QWORD, __int64, unsigned int *, const void **, struct _EAP_ERROR **); // rdi
  void (__fastcall *v10)(const void *); // r12
  void (__fastcall *v11)(struct _EAP_ERROR *); // r15
  __int64 v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  const wchar_t *v15; // rdx
  _UNKNOWN **result; // rax
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  struct _EAP_ERROR *v18; // [rsp+58h] [rbp-A8h] BYREF
  const void *v19; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  char v22[96]; // [rsp+80h] [rbp-80h] BYREF
  char v23[2048]; // [rsp+E0h] [rbp-20h] BYREF

  v21 = a4;
  v20 = a3;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "EapPeerInvokeConfigUI Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a2);
  HeapAllocator::Free(*(void **)a5);
  *(_QWORD *)a5 = 0;
  *(_QWORD *)(a5 + 8) = 0;
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 128), 0);
  v8 = *(_QWORD **)(a1 + 128);
  v9 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64, unsigned int *, const void **, struct _EAP_ERROR **))v8[27];
  v10 = (void (__fastcall *)(const void *))v8[29];
  v11 = (void (__fastcall *)(struct _EAP_ERROR *))v8[28];
  v17 = 0;
  v19 = 0;
  v18 = 0;
  v12 = *a3;
  v13 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v20[1]);
  v14 = v9(a1 + 16, v21, a2, v13, v12, &v17, &v19, &v18);
  if ( v14 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v22, v18, v14);
    v11(v18);
    EapHost::EapException::Throw(L"EapPeerInvokeConfigUI", v15, (const struct EapHost::EapError *)v22);
  }
  TempBuffer<0>::Assign(a5, v17, v19);
  v10(v19);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "EapPeerInvokeConfigUI Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v23);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          12,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001cba0  push    rbp
0x18001cba2  push    rbx
0x18001cba3  push    rsi
0x18001cba4  push    rdi
0x18001cba5  push    r12
0x18001cba7  push    r13
0x18001cba9  push    r14
0x18001cbab  push    r15
0x18001cbad  lea     rbp, [rsp-7F8h]
0x18001cbb5  sub     rsp, 8F8h
0x18001cbbc  mov     rax, cs:__security_cookie
0x18001cbc3  xor     rax, rsp
0x18001cbc6  mov     [rbp+830h+var_50], rax
0x18001cbcd  mov     [rsp+930h+var_8C0], r9
0x18001cbd2  mov     rbx, r8
0x18001cbd5  mov     [rsp+930h+var_8C8], rbx
0x18001cbda  mov     esi, edx
0x18001cbdc  mov     r13, rcx
0x18001cbdf  mov     r14, [rbp+830h+arg_20]
0x18001cbe6  lea     rdx, DebugInfoEvent
0x18001cbed  mov     rcx, cs:eaphost_Context
0x18001cbf4  call    cs:__imp_EtwEventEnabled
0x18001cbfa  xor     edi, edi
0x18001cbfc  test    al, al
0x18001cbfe  jz      short loc_18001CC3C
0x18001cc00  mov     r9d, esi
0x18001cc03  lea     r8, aEappeerinvokec_1; "EapPeerInvokeConfigUI Entry:\n flags(%d"...
0x18001cc0a  mov     edx, 800h; unsigned __int64
0x18001cc0f  lea     rcx, [rbp+830h+var_850]; char *
0x18001cc13  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001cc18  test    eax, eax
0x18001cc1a  js      short loc_18001CC3C
0x18001cc1c  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x18001cc23  jge     short loc_18001CC3C
0x18001cc25  lea     r8, [rbp+830h+var_850]
0x18001cc29  lea     rdx, DebugInfoEvent
0x18001cc30  lea     rcx, eaphost_Context
0x18001cc37  call    McTemplateU0s_EtwEventWriteTransfer
0x18001cc3c  lea     rax, WPP_GLOBAL_Control
0x18001cc43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc4a  cmp     rcx, rax
0x18001cc4d  jz      short loc_18001CC6D
0x18001cc4f  test    byte ptr [rcx+1Ch], 4
0x18001cc53  jz      short loc_18001CC6D
0x18001cc55  mov     edx, 0Bh
0x18001cc5a  mov     r9d, esi
0x18001cc5d  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001cc64  mov     rcx, [rcx+10h]
0x18001cc68  call    WPP_SF_d
0x18001cc6d  mov     rcx, [r14]; void *
0x18001cc70  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001cc75  mov     [r14], rdi
0x18001cc78  mov     [r14+8], rdi
0x18001cc7c  xor     edx, edx; bool
0x18001cc7e  mov     rcx, [r13+80h]; this
0x18001cc85  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001cc8a  mov     rax, [r13+80h]
0x18001cc91  mov     rdi, [rax+0D8h]
0x18001cc98  mov     r12, [rax+0E8h]
0x18001cc9f  mov     r15, [rax+0E0h]
0x18001cca6  xor     eax, eax
0x18001cca8  mov     [rsp+930h+var_8E0], eax
0x18001ccac  mov     [rsp+930h+var_8D0], rax
0x18001ccb1  mov     [rsp+930h+var_8D8], rax
0x18001ccb6  mov     rbx, [rbx]
0x18001ccb9  mov     rcx, [rsp+930h+var_8C8]
0x18001ccbe  mov     rcx, [rcx+8]
0x18001ccc2  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001ccc7  lea     rcx, [r13+10h]
0x18001cccb  lea     rdx, [rsp+930h+var_8D8]
0x18001ccd0  mov     [rsp+930h+var_8F8], rdx
0x18001ccd5  lea     rdx, [rsp+930h+var_8D0]
0x18001ccda  mov     [rsp+930h+var_900], rdx
0x18001ccdf  lea     rdx, [rsp+930h+var_8E0]
0x18001cce4  mov     [rsp+930h+var_908], rdx
0x18001cce9  mov     [rsp+930h+var_910], rbx
0x18001ccee  mov     r9d, eax
0x18001ccf1  mov     r8d, esi
0x18001ccf4  mov     rdx, [rsp+930h+var_8C0]
0x18001ccf9  mov     rax, rdi
0x18001ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd01  test    eax, eax
0x18001cd03  jz      short loc_18001CD35
0x18001cd05  mov     r8d, eax; unsigned int
0x18001cd08  mov     rdx, [rsp+930h+var_8D8]; struct _EAP_ERROR *
0x18001cd0d  lea     rcx, [rbp+830h+var_8B0]; this
0x18001cd11  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001cd16  nop
0x18001cd17  mov     rcx, [rsp+930h+var_8D8]
0x18001cd1c  mov     rax, r15
0x18001cd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd24  lea     r8, [rbp+830h+var_8B0]; struct EapHost::EapError *
0x18001cd28  lea     rcx, aEappeerinvokec; "EapPeerInvokeConfigUI"
0x18001cd2f  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001cd35  mov     edx, [rsp+930h+var_8E0]
0x18001cd39  mov     r8, [rsp+930h+var_8D0]
0x18001cd3e  mov     rcx, r14
0x18001cd41  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001cd46  mov     rcx, [rsp+930h+var_8D0]
0x18001cd4b  mov     rax, r12
0x18001cd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd53  lea     rdx, DebugInfoEvent
0x18001cd5a  mov     rcx, cs:eaphost_Context
0x18001cd61  call    cs:__imp_EtwEventEnabled
0x18001cd67  test    al, al
0x18001cd69  jz      short loc_18001CDA4
0x18001cd6b  lea     r8, aEappeerinvokec_0; "EapPeerInvokeConfigUI Exit"
0x18001cd72  mov     edx, 800h; unsigned __int64
0x18001cd77  lea     rcx, [rbp+830h+var_850]; char *
0x18001cd7b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001cd80  test    eax, eax
0x18001cd82  js      short loc_18001CDA4
0x18001cd84  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001cd8b  jge     short loc_18001CDA4
0x18001cd8d  lea     r8, [rbp+830h+var_850]
0x18001cd91  lea     rdx, DebugInfoEvent
0x18001cd98  lea     rcx, eaphost_Context
0x18001cd9f  call    McTemplateU0s_EtwEventWriteTransfer
0x18001cda4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdab  lea     rax, WPP_GLOBAL_Control
0x18001cdb2  cmp     rcx, rax
0x18001cdb5  jz      short loc_18001CDD2
0x18001cdb7  test    byte ptr [rcx+1Ch], 4
0x18001cdbb  jz      short loc_18001CDD2
0x18001cdbd  mov     edx, 0Ch
0x18001cdc2  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001cdc9  mov     rcx, [rcx+10h]
0x18001cdcd  call    WPP_SF_
0x18001cdd2  mov     rcx, [rbp+830h+var_50]
0x18001cdd9  xor     rcx, rsp; StackCookie
0x18001cddc  call    __security_check_cookie
0x18001cde1  add     rsp, 8F8h
0x18001cde8  pop     r15
0x18001cdea  pop     r14
0x18001cdec  pop     r13
0x18001cdee  pop     r12
0x18001cdf0  pop     rdi
0x18001cdf1  pop     rsi
0x18001cdf2  pop     rbx
0x18001cdf3  pop     rbp
0x18001cdf4  retn
```
