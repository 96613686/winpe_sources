# EapLm::Peer::LegacyEapMethodConfig::InvokeInteractiveUi(ConstBuffer const &,HWND__ *,TempBuffer<0> &)

- ea: `0x18001a090`
- end: `0x18001a37d`
- name: `?InvokeInteractiveUi@LegacyEapMethodConfig@Peer@EapLm@@UEAAXAEBUConstBuffer@@PEAUHWND__@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `749`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x18001549c`
- `0x180016400`
- `0x18001a090`
- `0x18001b154`
- `0x18001b1dc`
- `0x18001b2d4`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001a0cd`
- `ntdll!EtwEventEnabled` at `0x18001a1e4`
- `ntdll!EtwEventEnabled` at `0x18001a2d2`
- `ntdll!EtwEventEnabled` at `0x18001a0cd`
- `ntdll!EtwEventEnabled` at `0x18001a1e4`
- `ntdll!EtwEventEnabled` at `0x18001a2d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::LegacyEapMethodConfig::InvokeInteractiveUi(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int64 (__fastcall *v9)(_QWORD, __int64, _QWORD, _QWORD, const void **, unsigned int *); // rbx
  void (__fastcall *v10)(const void *); // r12
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r8
  _UNKNOWN **result; // rax
  unsigned int v15; // [rsp+40h] [rbp-888h] BYREF
  const void *v16; // [rsp+48h] [rbp-880h] BYREF
  void (__fastcall *v17)(const void *); // [rsp+50h] [rbp-878h]
  void **v18; // [rsp+58h] [rbp-870h] BYREF
  char v19; // [rsp+60h] [rbp-868h]
  __int64 v20; // [rsp+64h] [rbp-864h]
  int v21; // [rsp+70h] [rbp-858h]
  char v22[2048]; // [rsp+80h] [rbp-848h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v22, 0x800u, "RasEapInvokeInteractiveUI Entry:\n Context data(%Id) bytes", a2[1]) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v22);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2[1]);
  HeapAllocator::Free(*(void **)a4);
  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 152), 0);
  v8 = *(_QWORD *)(a1 + 152);
  v9 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, const void **, unsigned int *))(v8 + 216);
  v10 = *(void (__fastcall **)(const void *))(v8 + 232);
  v17 = v10;
  v15 = 0;
  v16 = 0;
  v11 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a2[1]);
  v12 = v9(*(unsigned __int8 *)(a1 + 16), a3, *a2, v11, &v16, &v15);
  if ( v12 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v22, 0x800u, "RasEapInvokeInteractiveUI failed %d", v12) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugErrorEvent, v22);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v12);
    v19 = *(_BYTE *)(a1 + 16);
    v20 = *(_QWORD *)(a1 + 20);
    if ( v19 != -2 )
      v20 = 0;
    v18 = &EapHost::EapMethodType::`vftable';
    v21 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v12, (const struct EapHost::EapMethodType *)&v18, v12);
  }
  try
  {
    TempBuffer<0>::Assign(a4, v15, v16);
  }
  catch ( std::bad_alloc )
  {
    v17(v16);
    throw;
  }
  v10(v16);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v22,
              0x800u,
              "RasEapInvokeInteractiveUI Exit:\n context data(%Id) bytes, returned(%d) bytes of data",
              a2[1],
              v15) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v22);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_Pd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v13, a2[1], v15);
  return result;
}

```

## disassembly

```asm
0x18001a090  push    rbx
0x18001a092  push    rsi
0x18001a093  push    rdi
0x18001a094  push    r12
0x18001a096  push    r13
0x18001a098  push    r15
0x18001a09a  sub     rsp, 898h
0x18001a0a1  mov     rax, cs:__security_cookie
0x18001a0a8  xor     rax, rsp
0x18001a0ab  mov     [rsp+8C8h+var_48], rax
0x18001a0b3  mov     r15, r9
0x18001a0b6  mov     r13, r8
0x18001a0b9  mov     rsi, rdx
0x18001a0bc  mov     rdi, rcx
0x18001a0bf  lea     rdx, DebugInfoEvent
0x18001a0c6  mov     rcx, cs:eaphost_Context
0x18001a0cd  call    cs:__imp_EtwEventEnabled
0x18001a0d3  xor     ebx, ebx
0x18001a0d5  test    al, al
0x18001a0d7  jz      short loc_18001A11D
0x18001a0d9  mov     r9, [rsi+8]
0x18001a0dd  lea     r8, aRaseapinvokein_1; "RasEapInvokeInteractiveUI Entry:\n Cont"...
0x18001a0e4  mov     edx, 800h; unsigned __int64
0x18001a0e9  lea     rcx, [rsp+8C8h+var_848]; char *
0x18001a0f1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a0f6  test    eax, eax
0x18001a0f8  js      short loc_18001A11D
0x18001a0fa  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18001a100  jge     short loc_18001A11D
0x18001a102  lea     r8, [rsp+8C8h+var_848]
0x18001a10a  lea     rdx, DebugInfoEvent
0x18001a111  lea     rcx, eaphost_Context
0x18001a118  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a11d  lea     rax, WPP_GLOBAL_Control
0x18001a124  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a12b  cmp     rcx, rax
0x18001a12e  jz      short loc_18001A14F
0x18001a130  test    byte ptr [rcx+1Ch], 4
0x18001a134  jz      short loc_18001A14F
0x18001a136  mov     edx, 19h
0x18001a13b  mov     r9, [rsi+8]
0x18001a13f  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a146  mov     rcx, [rcx+10h]
0x18001a14a  call    WPP_SF_P
0x18001a14f  mov     rcx, [r15]; void *
0x18001a152  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001a157  mov     [r15], rbx
0x18001a15a  mov     [r15+8], rbx
0x18001a15e  xor     edx, edx; bool
0x18001a160  mov     rcx, [rdi+98h]; this
0x18001a167  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001a16c  mov     rax, [rdi+98h]
0x18001a173  mov     rbx, [rax+0D8h]
0x18001a17a  mov     r12, [rax+0E8h]
0x18001a181  mov     [rsp+8C8h+var_878], r12
0x18001a186  mov     [rsp+8C8h+var_888], 0
0x18001a18e  mov     [rsp+8C8h+var_880], 0
0x18001a197  mov     rcx, [rsi+8]
0x18001a19b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001a1a0  movzx   ecx, byte ptr [rdi+10h]
0x18001a1a4  lea     rdx, [rsp+8C8h+var_888]
0x18001a1a9  mov     [rsp+8C8h+var_8A0], rdx
0x18001a1ae  lea     rdx, [rsp+8C8h+var_880]
0x18001a1b3  mov     [rsp+8C8h+var_8A8], rdx
0x18001a1b8  mov     r9d, eax
0x18001a1bb  mov     r8, [rsi]
0x18001a1be  mov     rdx, r13
0x18001a1c1  mov     rax, rbx
0x18001a1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1c9  mov     ebx, eax
0x18001a1cb  xor     r13d, r13d
0x18001a1ce  test    eax, eax
0x18001a1d0  jz      loc_18001A2A5
0x18001a1d6  lea     rdx, DebugErrorEvent
0x18001a1dd  mov     rcx, cs:eaphost_Context
0x18001a1e4  call    cs:__imp_EtwEventEnabled
0x18001a1ea  test    al, al
0x18001a1ec  jz      short loc_18001A232
0x18001a1ee  mov     r9d, ebx
0x18001a1f1  lea     r8, aRaseapinvokein_0; "RasEapInvokeInteractiveUI failed %d"
0x18001a1f8  mov     edx, 800h; unsigned __int64
0x18001a1fd  lea     rcx, [rsp+8C8h+var_848]; char *
0x18001a205  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a20a  test    eax, eax
0x18001a20c  js      short loc_18001A232
0x18001a20e  test    cs:byte_18004AF81, 8
0x18001a215  jz      short loc_18001A232
0x18001a217  lea     r8, [rsp+8C8h+var_848]
0x18001a21f  lea     rdx, DebugErrorEvent
0x18001a226  lea     rcx, eaphost_Context
0x18001a22d  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a232  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a239  lea     rax, WPP_GLOBAL_Control
0x18001a240  cmp     rcx, rax
0x18001a243  jz      short loc_18001A263
0x18001a245  test    byte ptr [rcx+1Ch], 1
0x18001a249  jz      short loc_18001A263
0x18001a24b  mov     edx, 1Ah
0x18001a250  mov     r9d, ebx
0x18001a253  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a25a  mov     rcx, [rcx+10h]
0x18001a25e  call    WPP_SF_d
0x18001a263  mov     cl, [rdi+10h]
0x18001a266  mov     [rsp+8C8h+var_868], cl
0x18001a26a  mov     eax, [rdi+14h]
0x18001a26d  mov     dword ptr [rsp+8C8h+var_864], eax
0x18001a271  mov     eax, [rdi+18h]
0x18001a274  mov     dword ptr [rsp+8C8h+var_864+4], eax
0x18001a278  cmp     cl, 0FEh
0x18001a27b  jz      short loc_18001A282
0x18001a27d  mov     [rsp+8C8h+var_864], r13
0x18001a282  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001a289  mov     [rsp+8C8h+var_870], rax
0x18001a28e  mov     eax, [rdi+1Ch]
0x18001a291  mov     [rsp+8C8h+var_858], eax
0x18001a295  mov     r8d, ebx; unsigned int
0x18001a298  lea     rdx, [rsp+8C8h+var_870]; struct EapHost::EapMethodType *
0x18001a29d  mov     ecx, ebx; unsigned int
0x18001a29f  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001a2a5  mov     edx, [rsp+8C8h+var_888]
0x18001a2a9  mov     r8, [rsp+8C8h+var_880]
0x18001a2ae  mov     rcx, r15
0x18001a2b1  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001a2b6  nop
0x18001a2b7  mov     rcx, [rsp+8C8h+var_880]
0x18001a2bc  mov     rax, r12
0x18001a2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2c4  lea     rdx, DebugInfoEvent
0x18001a2cb  mov     rcx, cs:eaphost_Context
0x18001a2d2  call    cs:__imp_EtwEventEnabled
0x18001a2d8  test    al, al
0x18001a2da  jz      short loc_18001A329
0x18001a2dc  mov     eax, [rsp+8C8h+var_888]
0x18001a2e0  mov     dword ptr [rsp+8C8h+var_8A8], eax
0x18001a2e4  mov     r9, [rsi+8]
0x18001a2e8  lea     r8, aRaseapinvokein_2; "RasEapInvokeInteractiveUI Exit:\n conte"...
0x18001a2ef  mov     edx, 800h; unsigned __int64
0x18001a2f4  lea     rcx, [rsp+8C8h+var_848]; char *
0x18001a2fc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a301  test    eax, eax
0x18001a303  js      short loc_18001A329
0x18001a305  cmp     cs:Microsoft_Windows_EapHostEnableBits, r13b
0x18001a30c  jge     short loc_18001A329
0x18001a30e  lea     r8, [rsp+8C8h+var_848]
0x18001a316  lea     rdx, DebugInfoEvent
0x18001a31d  lea     rcx, eaphost_Context
0x18001a324  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a329  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a330  lea     rax, WPP_GLOBAL_Control
0x18001a337  cmp     rcx, rax
0x18001a33a  jz      short loc_18001A35C
0x18001a33c  test    byte ptr [rcx+1Ch], 4
0x18001a340  jz      short loc_18001A35C
0x18001a342  mov     edx, 1Bh
0x18001a347  mov     eax, [rsp+8C8h+var_888]
0x18001a34b  mov     dword ptr [rsp+8C8h+var_8A8], eax
0x18001a34f  mov     r9, [rsi+8]
0x18001a353  mov     rcx, [rcx+10h]
0x18001a357  call    WPP_SF_Pd
0x18001a35c  mov     rcx, [rsp+8C8h+var_48]
0x18001a364  xor     rcx, rsp; StackCookie
0x18001a367  call    __security_check_cookie
0x18001a36c  add     rsp, 898h
0x18001a373  pop     r15
0x18001a375  pop     r13
0x18001a377  pop     r12
0x18001a379  pop     rdi
0x18001a37a  pop     rsi
0x18001a37b  pop     rbx
0x18001a37c  retn
```
