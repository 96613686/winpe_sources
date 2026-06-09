# EapLm::Peer::LegacyEapMethodConfig::InvokeConfigUi(uint,ConstBuffer const &,HWND__ *,TempBuffer<0> &)

- ea: `0x1800197a0`
- end: `0x180019a69`
- name: `?InvokeConfigUi@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIAEBUConstBuffer@@PEAUHWND__@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `713`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x18001549c`
- `0x180016400`
- `0x1800197a0`
- `0x18001b154`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800197ed`
- `ntdll!EtwEventEnabled` at `0x1800198ec`
- `ntdll!EtwEventEnabled` at `0x1800199d3`
- `ntdll!EtwEventEnabled` at `0x1800197ed`
- `ntdll!EtwEventEnabled` at `0x1800198ec`
- `ntdll!EtwEventEnabled` at `0x1800199d3`

## string_xrefs

- `0x1800197fa`: `RasEapInvokeConfigUI Entry:\n flags(%d)`
- `0x1800198f9`: `RasEapInvokeConfigUI failed %d`
- `0x1800199dd`: `RasEapInvokeConfigUI Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::LegacyEapMethodConfig::InvokeConfigUi(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v9; // rax
  __int64 (__fastcall *v10)(_QWORD, __int64, _QWORD, _QWORD, int, const void **, unsigned int *); // rbx
  void (__fastcall *v11)(const void *); // r14
  int v12; // eax
  unsigned int v13; // ebx
  _UNKNOWN **result; // rax
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  const void *v16; // [rsp+48h] [rbp-B8h] BYREF
  void **v17; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+5Ch] [rbp-A4h]
  int v20; // [rsp+68h] [rbp-98h]
  char v21[2048]; // [rsp+70h] [rbp-90h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "RasEapInvokeConfigUI Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v21);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 128), 0);
  v9 = *(_QWORD *)(a1 + 128);
  v10 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, const void **, unsigned int *))(v9 + 216);
  v11 = *(void (__fastcall **)(const void *))(v9 + 232);
  v15 = 0;
  v16 = 0;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a3[1]);
  v13 = v10(*(unsigned __int8 *)(a1 + 16), a4, a2, *a3, v12, &v16, &v15);
  if ( v13 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v21, 0x800u, "RasEapInvokeConfigUI failed %d", v13) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v21);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v13);
    v18 = *(_BYTE *)(a1 + 16);
    v19 = *(_QWORD *)(a1 + 20);
    if ( v18 != -2 )
      v19 = 0;
    v17 = &EapHost::EapMethodType::`vftable';
    v20 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v13, (const struct EapHost::EapMethodType *)&v17, v13);
  }
  TempBuffer<0>::Assign(a5, v15, v16);
  v11(v16);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "RasEapInvokeConfigUI Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v21);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          12,
                          WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800197a0  push    rbp
0x1800197a2  push    rbx
0x1800197a3  push    rsi
0x1800197a4  push    rdi
0x1800197a5  push    r12
0x1800197a7  push    r13
0x1800197a9  push    r14
0x1800197ab  push    r15
0x1800197ad  lea     rbp, [rsp-788h]
0x1800197b5  sub     rsp, 888h
0x1800197bc  mov     rax, cs:__security_cookie
0x1800197c3  xor     rax, rsp
0x1800197c6  mov     [rbp+7C0h+var_50], rax
0x1800197cd  mov     r13, r9
0x1800197d0  mov     r12, r8
0x1800197d3  mov     esi, edx
0x1800197d5  mov     rdi, rcx
0x1800197d8  mov     r15, [rbp+7C0h+arg_20]
0x1800197df  lea     rdx, DebugInfoEvent
0x1800197e6  mov     rcx, cs:eaphost_Context
0x1800197ed  call    cs:__imp_EtwEventEnabled
0x1800197f3  test    al, al
0x1800197f5  jz      short loc_180019835
0x1800197f7  mov     r9d, esi
0x1800197fa  lea     r8, aRaseapinvokeco_2; "RasEapInvokeConfigUI Entry:\n flags(%d)"
0x180019801  mov     edx, 800h; unsigned __int64
0x180019806  lea     rcx, [rsp+8C0h+var_850]; char *
0x18001980b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180019810  test    eax, eax
0x180019812  js      short loc_180019835
0x180019814  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001981b  jge     short loc_180019835
0x18001981d  lea     r8, [rsp+8C0h+var_850]
0x180019822  lea     rdx, DebugInfoEvent
0x180019829  lea     rcx, eaphost_Context
0x180019830  call    McTemplateU0s_EtwEventWriteTransfer
0x180019835  lea     rax, WPP_GLOBAL_Control
0x18001983c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019843  cmp     rcx, rax
0x180019846  jz      short loc_180019866
0x180019848  test    byte ptr [rcx+1Ch], 4
0x18001984c  jz      short loc_180019866
0x18001984e  mov     edx, 0Ah
0x180019853  mov     r9d, esi
0x180019856  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001985d  mov     rcx, [rcx+10h]
0x180019861  call    WPP_SF_d
0x180019866  xor     edx, edx; bool
0x180019868  mov     rcx, [rdi+80h]; this
0x18001986f  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x180019874  mov     rax, [rdi+80h]
0x18001987b  mov     rbx, [rax+0D8h]
0x180019882  mov     r14, [rax+0E8h]
0x180019889  mov     [rsp+8C0h+var_880], 0
0x180019891  mov     [rsp+8C0h+var_878], 0
0x18001989a  mov     rcx, [r12+8]
0x18001989f  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800198a4  movzx   ecx, byte ptr [rdi+10h]
0x1800198a8  lea     rdx, [rsp+8C0h+var_880]
0x1800198ad  mov     [rsp+8C0h+var_890], rdx
0x1800198b2  lea     rdx, [rsp+8C0h+var_878]
0x1800198b7  mov     [rsp+8C0h+var_898], rdx
0x1800198bc  mov     [rsp+8C0h+var_8A0], eax
0x1800198c0  mov     r9, [r12]
0x1800198c4  mov     r8d, esi
0x1800198c7  mov     rdx, r13
0x1800198ca  mov     rax, rbx
0x1800198cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198d2  mov     ebx, eax
0x1800198d4  xor     esi, esi
0x1800198d6  test    eax, eax
0x1800198d8  jz      loc_1800199A7
0x1800198de  lea     rdx, DebugErrorEvent
0x1800198e5  mov     rcx, cs:eaphost_Context
0x1800198ec  call    cs:__imp_EtwEventEnabled
0x1800198f2  test    al, al
0x1800198f4  jz      short loc_180019934
0x1800198f6  mov     r9d, ebx
0x1800198f9  lea     r8, aRaseapinvokeco_1; "RasEapInvokeConfigUI failed %d"
0x180019900  mov     edx, 800h; unsigned __int64
0x180019905  lea     rcx, [rsp+8C0h+var_850]; char *
0x18001990a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001990f  test    eax, eax
0x180019911  js      short loc_180019934
0x180019913  test    cs:byte_18004AF81, 8
0x18001991a  jz      short loc_180019934
0x18001991c  lea     r8, [rsp+8C0h+var_850]
0x180019921  lea     rdx, DebugErrorEvent
0x180019928  lea     rcx, eaphost_Context
0x18001992f  call    McTemplateU0s_EtwEventWriteTransfer
0x180019934  mov     rcx, cs:WPP_GLOBAL_Control
0x18001993b  lea     rax, WPP_GLOBAL_Control
0x180019942  cmp     rcx, rax
0x180019945  jz      short loc_180019965
0x180019947  test    byte ptr [rcx+1Ch], 1
0x18001994b  jz      short loc_180019965
0x18001994d  mov     edx, 0Bh
0x180019952  mov     r9d, ebx
0x180019955  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001995c  mov     rcx, [rcx+10h]
0x180019960  call    WPP_SF_d
0x180019965  mov     cl, [rdi+10h]
0x180019968  mov     [rsp+8C0h+var_868], cl
0x18001996c  mov     eax, [rdi+14h]
0x18001996f  mov     dword ptr [rsp+8C0h+var_864], eax
0x180019973  mov     eax, [rdi+18h]
0x180019976  mov     dword ptr [rsp+8C0h+var_864+4], eax
0x18001997a  cmp     cl, 0FEh
0x18001997d  jz      short loc_180019984
0x18001997f  mov     [rsp+8C0h+var_864], rsi
0x180019984  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001998b  mov     [rsp+8C0h+var_870], rax
0x180019990  mov     eax, [rdi+1Ch]
0x180019993  mov     [rsp+8C0h+var_858], eax
0x180019997  mov     r8d, ebx; unsigned int
0x18001999a  lea     rdx, [rsp+8C0h+var_870]; struct EapHost::EapMethodType *
0x18001999f  mov     ecx, ebx; unsigned int
0x1800199a1  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x1800199a7  mov     edx, [rsp+8C0h+var_880]
0x1800199ab  mov     r8, [rsp+8C0h+var_878]
0x1800199b0  mov     rcx, r15
0x1800199b3  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800199b8  mov     rcx, [rsp+8C0h+var_878]
0x1800199bd  mov     rax, r14
0x1800199c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c5  lea     rdx, DebugInfoEvent
0x1800199cc  mov     rcx, cs:eaphost_Context
0x1800199d3  call    cs:__imp_EtwEventEnabled
0x1800199d9  test    al, al
0x1800199db  jz      short loc_180019A18
0x1800199dd  lea     r8, aRaseapinvokeco; "RasEapInvokeConfigUI Exit"
0x1800199e4  mov     edx, 800h; unsigned __int64
0x1800199e9  lea     rcx, [rsp+8C0h+var_850]; char *
0x1800199ee  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800199f3  test    eax, eax
0x1800199f5  js      short loc_180019A18
0x1800199f7  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x1800199fe  jge     short loc_180019A18
0x180019a00  lea     r8, [rsp+8C0h+var_850]
0x180019a05  lea     rdx, DebugInfoEvent
0x180019a0c  lea     rcx, eaphost_Context
0x180019a13  call    McTemplateU0s_EtwEventWriteTransfer
0x180019a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a1f  lea     rax, WPP_GLOBAL_Control
0x180019a26  cmp     rcx, rax
0x180019a29  jz      short loc_180019A46
0x180019a2b  test    byte ptr [rcx+1Ch], 4
0x180019a2f  jz      short loc_180019A46
0x180019a31  mov     edx, 0Ch
0x180019a36  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180019a3d  mov     rcx, [rcx+10h]
0x180019a41  call    WPP_SF_
0x180019a46  mov     rcx, [rbp+7C0h+var_50]
0x180019a4d  xor     rcx, rsp; StackCookie
0x180019a50  call    __security_check_cookie
0x180019a55  add     rsp, 888h
0x180019a5c  pop     r15
0x180019a5e  pop     r14
0x180019a60  pop     r13
0x180019a62  pop     r12
0x180019a64  pop     rdi
0x180019a65  pop     rsi
0x180019a66  pop     rbx
0x180019a67  pop     rbp
0x180019a68  retn
```
