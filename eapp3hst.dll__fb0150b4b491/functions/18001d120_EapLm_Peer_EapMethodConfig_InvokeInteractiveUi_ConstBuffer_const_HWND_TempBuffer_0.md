# EapLm::Peer::EapMethodConfig::InvokeInteractiveUi(ConstBuffer const &,HWND__ *,TempBuffer<0> &)

- ea: `0x18001d120`
- end: `0x18001d361`
- name: `?InvokeInteractiveUi@EapMethodConfig@Peer@EapLm@@UEAAXAEBUConstBuffer@@PEAUHWND__@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x180005894`
- `0x1800126f8`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001b1dc`
- `0x18001d120`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001d169`
- `ntdll!EtwEventEnabled` at `0x18001d2cd`
- `ntdll!EtwEventEnabled` at `0x18001d169`
- `ntdll!EtwEventEnabled` at `0x18001d2cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::InvokeInteractiveUi(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v7; // rax
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD, __int64, unsigned int *, const void **, struct _EAP_ERROR **); // rdi
  void (__fastcall *v9)(const void *); // r12
  void (__fastcall *v10)(struct _EAP_ERROR *); // r15
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  const wchar_t *v14; // rdx
  _UNKNOWN **result; // rax
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _EAP_ERROR *v17; // [rsp+48h] [rbp-B8h] BYREF
  const void *v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h]
  char v20[96]; // [rsp+60h] [rbp-A0h] BYREF
  char v21[2048]; // [rsp+C0h] [rbp-40h] BYREF

  v19 = a3;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "EapPeerInvokeInteractiveUI Entry:\n context data(%Id) bytes", a2[1]) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v21);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a2[1]);
  HeapAllocator::Free(*(void **)a4);
  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 152), 0);
  v7 = *(_QWORD **)(a1 + 152);
  v8 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64, unsigned int *, const void **, struct _EAP_ERROR **))v7[27];
  v9 = (void (__fastcall *)(const void *))v7[29];
  v10 = (void (__fastcall *)(struct _EAP_ERROR *))v7[28];
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v11 = *a2;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a2[1]);
  v13 = v8(a1 + 16, v19, v12, v11, &v16, &v18, &v17);
  if ( v13 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v20, v17, v13);
    v10(v17);
    EapHost::EapException::Throw(L"EapPeerInvokeInteractiveUI", v14, (const struct EapHost::EapError *)v20);
  }
  TempBuffer<0>::Assign(a4, v16, v18);
  v9(v18);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "EapPeerInvokeInteractiveUI Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v21);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          21,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001d120  push    rbp
0x18001d122  push    rbx
0x18001d123  push    rsi
0x18001d124  push    rdi
0x18001d125  push    r12
0x18001d127  push    r13
0x18001d129  push    r14
0x18001d12b  push    r15
0x18001d12d  lea     rbp, [rsp-7D8h]
0x18001d135  sub     rsp, 8D8h
0x18001d13c  mov     rax, cs:__security_cookie
0x18001d143  xor     rax, rsp
0x18001d146  mov     [rbp+810h+var_50], rax
0x18001d14d  mov     r14, r9
0x18001d150  mov     [rsp+910h+var_8B8], r8
0x18001d155  mov     rsi, rdx
0x18001d158  mov     r13, rcx
0x18001d15b  lea     rdx, DebugInfoEvent
0x18001d162  mov     rcx, cs:eaphost_Context
0x18001d169  call    cs:__imp_EtwEventEnabled
0x18001d16f  xor     ebx, ebx
0x18001d171  test    al, al
0x18001d173  jz      short loc_18001D1B1
0x18001d175  mov     r9, [rsi+8]
0x18001d179  lea     r8, aEappeerinvokei_0; "EapPeerInvokeInteractiveUI Entry:\n con"...
0x18001d180  mov     edx, 800h; unsigned __int64
0x18001d185  lea     rcx, [rbp+810h+var_850]; char *
0x18001d189  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d18e  test    eax, eax
0x18001d190  js      short loc_18001D1B1
0x18001d192  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18001d198  jge     short loc_18001D1B1
0x18001d19a  lea     r8, [rbp+810h+var_850]
0x18001d19e  lea     rdx, DebugInfoEvent
0x18001d1a5  lea     rcx, eaphost_Context
0x18001d1ac  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d1b1  lea     rax, WPP_GLOBAL_Control
0x18001d1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1bf  cmp     rcx, rax
0x18001d1c2  jz      short loc_18001D1E3
0x18001d1c4  test    byte ptr [rcx+1Ch], 4
0x18001d1c8  jz      short loc_18001D1E3
0x18001d1ca  mov     edx, 14h
0x18001d1cf  mov     r9, [rsi+8]
0x18001d1d3  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d1da  mov     rcx, [rcx+10h]
0x18001d1de  call    WPP_SF_P
0x18001d1e3  mov     rcx, [r14]; void *
0x18001d1e6  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001d1eb  mov     [r14], rbx
0x18001d1ee  mov     [r14+8], rbx
0x18001d1f2  xor     edx, edx; bool
0x18001d1f4  mov     rcx, [r13+98h]; this
0x18001d1fb  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001d200  mov     rax, [r13+98h]
0x18001d207  mov     rdi, [rax+0D8h]
0x18001d20e  mov     r12, [rax+0E8h]
0x18001d215  mov     r15, [rax+0E0h]
0x18001d21c  mov     [rsp+910h+var_8D0], ebx
0x18001d220  mov     [rsp+910h+var_8C0], rbx
0x18001d225  mov     [rsp+910h+var_8C8], rbx
0x18001d22a  mov     rbx, [rsi]
0x18001d22d  mov     rcx, [rsi+8]
0x18001d231  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001d236  lea     rcx, [r13+10h]
0x18001d23a  lea     rdx, [rsp+910h+var_8C8]
0x18001d23f  mov     [rsp+910h+var_8E0], rdx
0x18001d244  lea     rdx, [rsp+910h+var_8C0]
0x18001d249  mov     [rsp+910h+var_8E8], rdx
0x18001d24e  lea     rdx, [rsp+910h+var_8D0]
0x18001d253  mov     [rsp+910h+var_8F0], rdx
0x18001d258  mov     r9, rbx
0x18001d25b  mov     r8d, eax
0x18001d25e  mov     rdx, [rsp+910h+var_8B8]
0x18001d263  mov     rax, rdi
0x18001d266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d26b  test    eax, eax
0x18001d26d  jz      short loc_18001D2A1
0x18001d26f  mov     r8d, eax; unsigned int
0x18001d272  mov     rdx, [rsp+910h+var_8C8]; struct _EAP_ERROR *
0x18001d277  lea     rcx, [rsp+910h+var_8B0]; this
0x18001d27c  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001d281  nop
0x18001d282  mov     rcx, [rsp+910h+var_8C8]
0x18001d287  mov     rax, r15
0x18001d28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d28f  lea     r8, [rsp+910h+var_8B0]; struct EapHost::EapError *
0x18001d294  lea     rcx, aEappeerinvokei_2; "EapPeerInvokeInteractiveUI"
0x18001d29b  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001d2a1  mov     edx, [rsp+910h+var_8D0]
0x18001d2a5  mov     r8, [rsp+910h+var_8C0]
0x18001d2aa  mov     rcx, r14
0x18001d2ad  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001d2b2  mov     rcx, [rsp+910h+var_8C0]
0x18001d2b7  mov     rax, r12
0x18001d2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2bf  lea     rdx, DebugInfoEvent
0x18001d2c6  mov     rcx, cs:eaphost_Context
0x18001d2cd  call    cs:__imp_EtwEventEnabled
0x18001d2d3  test    al, al
0x18001d2d5  jz      short loc_18001D310
0x18001d2d7  lea     r8, aEappeerinvokei; "EapPeerInvokeInteractiveUI Exit"
0x18001d2de  mov     edx, 800h; unsigned __int64
0x18001d2e3  lea     rcx, [rbp+810h+var_850]; char *
0x18001d2e7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d2ec  test    eax, eax
0x18001d2ee  js      short loc_18001D310
0x18001d2f0  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001d2f7  jge     short loc_18001D310
0x18001d2f9  lea     r8, [rbp+810h+var_850]
0x18001d2fd  lea     rdx, DebugInfoEvent
0x18001d304  lea     rcx, eaphost_Context
0x18001d30b  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d310  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d317  lea     rax, WPP_GLOBAL_Control
0x18001d31e  cmp     rcx, rax
0x18001d321  jz      short loc_18001D33E
0x18001d323  test    byte ptr [rcx+1Ch], 4
0x18001d327  jz      short loc_18001D33E
0x18001d329  mov     edx, 15h
0x18001d32e  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d335  mov     rcx, [rcx+10h]
0x18001d339  call    WPP_SF_
0x18001d33e  mov     rcx, [rbp+810h+var_50]
0x18001d345  xor     rcx, rsp; StackCookie
0x18001d348  call    __security_check_cookie
0x18001d34d  add     rsp, 8D8h
0x18001d354  pop     r15
0x18001d356  pop     r14
0x18001d358  pop     r13
0x18001d35a  pop     r12
0x18001d35c  pop     rdi
0x18001d35d  pop     rsi
0x18001d35e  pop     rbx
0x18001d35f  pop     rbp
0x18001d360  retn
```
