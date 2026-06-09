# EapLm::Peer::EapMethodRuntime::GetUIContext(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180016e90`
- end: `0x1800170cd`
- name: `?GetUIContext@EapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002af0`
- `0x180007564`
- `0x18000a21c`
- `0x180011cb8`
- `0x1800120c4`
- `0x1800155c8`
- `0x180016e90`
- `0x18001e768`
- `0x180030f54`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180016eff`
- `ntdll!EtwEventEnabled` at `0x180017001`
- `ntdll!EtwEventEnabled` at `0x180016eff`
- `ntdll!EtwEventEnabled` at `0x180017001`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapLm::Peer::EapMethodRuntime::GetUIContext(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  const wchar_t *v7; // rdx
  __int64 result; // rax
  const wchar_t *v9; // rdx
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  struct _EAP_ERROR *v11; // [rsp+38h] [rbp-C8h] BYREF
  const void *v12; // [rsp+40h] [rbp-C0h] BYREF
  char v13[96]; // [rsp+50h] [rbp-B0h] BYREF
  char v14[2048]; // [rsp+B0h] [rbp-50h] BYREF

  HeapAllocator::Free(*(void **)a3);
  *(_QWORD *)a3 = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, "EapPeerGetUIContext Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v14);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, const void **, struct _EAP_ERROR **))(a1 + 376))(
         *(_QWORD *)(a2 + 64),
         &v10,
         &v12,
         &v11);
  if ( v6 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v13, v11, v6);
    (*(void (__fastcall **)(struct _EAP_ERROR *))(a1 + 424))(v11);
    EapHost::EapException::Throw(L"EapPeerGetUIContext", v7, (const struct EapHost::EapError *)v13);
  }
  if ( !v10 || !v12 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v13, v11, 0xDu);
    if ( v11 )
      (*(void (**)(void))(a1 + 424))();
    EapHost::EapException::Throw(L"EapPeerGetUIContext", v9, (const struct EapHost::EapError *)v13);
  }
  TempBuffer<0>::Assign(a3, v10, v12);
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  if ( (_BYTE)result )
  {
    result = StringCchPrintfA(v14, 0x800u, "EapPeerGetUIContext Exit");
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
      result = McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v14);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180016e90  push    rbp
0x180016e92  push    rbx
0x180016e93  push    rsi
0x180016e94  push    rdi
0x180016e95  push    r12
0x180016e97  lea     rbp, [rsp-7C0h]
0x180016e9f  sub     rsp, 8C0h
0x180016ea6  mov     rax, cs:__security_cookie
0x180016ead  xor     rax, rsp
0x180016eb0  mov     [rbp+7E0h+var_30], rax
0x180016eb7  mov     rdi, r8
0x180016eba  mov     rsi, rdx
0x180016ebd  mov     rbx, rcx
0x180016ec0  mov     rcx, [r8]; void *
0x180016ec3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180016ec8  mov     qword ptr [rdi], 0
0x180016ecf  mov     qword ptr [rdi+8], 0
0x180016ed7  mov     [rsp+8E0h+var_8A0], 0
0x180016ee0  mov     [rsp+8E0h+var_8B0], 0
0x180016ee8  mov     [rsp+8E0h+var_8A8], 0
0x180016ef1  lea     rdx, DebugInfoEvent
0x180016ef8  mov     rcx, cs:eaphost_Context
0x180016eff  call    cs:__imp_EtwEventEnabled
0x180016f06  nop     dword ptr [rax+rax+00h]
0x180016f0b  test    al, al
0x180016f0d  jz      short loc_180016F48
0x180016f0f  lea     r8, aEappeergetuico_0; "EapPeerGetUIContext Entry"
0x180016f16  mov     edx, 800h; unsigned __int64
0x180016f1b  lea     rcx, [rbp+7E0h+var_830]; char *
0x180016f1f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180016f24  test    eax, eax
0x180016f26  js      short loc_180016F48
0x180016f28  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180016f2f  jge     short loc_180016F48
0x180016f31  lea     r8, [rbp+7E0h+var_830]
0x180016f35  lea     rdx, DebugInfoEvent
0x180016f3c  lea     rcx, eaphost_Context
0x180016f43  call    McTemplateU0s_EtwEventWriteTransfer
0x180016f48  lea     r12, WPP_GLOBAL_Control
0x180016f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f56  cmp     rcx, r12
0x180016f59  jz      short loc_180016F76
0x180016f5b  test    byte ptr [rcx+1Ch], 4
0x180016f5f  jz      short loc_180016F76
0x180016f61  mov     edx, 1Eh
0x180016f66  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180016f6d  mov     rcx, [rcx+10h]
0x180016f71  call    WPP_SF_
0x180016f76  lea     r9, [rsp+8E0h+var_8A8]
0x180016f7b  lea     r8, [rsp+8E0h+var_8A0]
0x180016f80  lea     rdx, [rsp+8E0h+var_8B0]
0x180016f85  mov     rcx, [rsi+40h]
0x180016f89  mov     rax, [rbx+178h]
0x180016f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f95  test    eax, eax
0x180016f97  jz      short loc_180016FCF
0x180016f99  mov     r8d, eax; unsigned int
0x180016f9c  mov     rdx, [rsp+8E0h+var_8A8]; struct _EAP_ERROR *
0x180016fa1  lea     rcx, [rsp+8E0h+var_890]; this
0x180016fa6  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180016fab  nop
0x180016fac  mov     rcx, [rsp+8E0h+var_8A8]
0x180016fb1  mov     rax, [rbx+1A8h]
0x180016fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fbd  lea     r8, [rsp+8E0h+var_890]; struct EapHost::EapError *
0x180016fc2  lea     rcx, aEappeergetuico_1; "EapPeerGetUIContext"
0x180016fc9  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x180016fcf  mov     eax, [rsp+8E0h+var_8B0]
0x180016fd3  test    eax, eax
0x180016fd5  jz      loc_18001708F
0x180016fdb  mov     r8, [rsp+8E0h+var_8A0]
0x180016fe0  test    r8, r8
0x180016fe3  jz      loc_18001708F
0x180016fe9  mov     edx, eax
0x180016feb  mov     rcx, rdi
0x180016fee  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180016ff3  lea     rdx, DebugInfoEvent
0x180016ffa  mov     rcx, cs:eaphost_Context
0x180017001  call    cs:__imp_EtwEventEnabled
0x180017008  nop     dword ptr [rax+rax+00h]
0x18001700d  test    al, al
0x18001700f  jz      short loc_18001704A
0x180017011  lea     r8, aEappeergetuico; "EapPeerGetUIContext Exit"
0x180017018  mov     edx, 800h; unsigned __int64
0x18001701d  lea     rcx, [rbp+7E0h+var_830]; char *
0x180017021  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180017026  test    eax, eax
0x180017028  js      short loc_18001704A
0x18001702a  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180017031  jge     short loc_18001704A
0x180017033  lea     r8, [rbp+7E0h+var_830]
0x180017037  lea     rdx, DebugInfoEvent
0x18001703e  lea     rcx, eaphost_Context
0x180017045  call    McTemplateU0s_EtwEventWriteTransfer
0x18001704a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017051  cmp     rcx, r12
0x180017054  jz      short loc_180017071
0x180017056  test    byte ptr [rcx+1Ch], 4
0x18001705a  jz      short loc_180017071
0x18001705c  mov     edx, 1Fh
0x180017061  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180017068  mov     rcx, [rcx+10h]
0x18001706c  call    WPP_SF_
0x180017071  mov     rcx, [rbp+7E0h+var_30]
0x180017078  xor     rcx, rsp; StackCookie
0x18001707b  call    __security_check_cookie
0x180017080  add     rsp, 8C0h
0x180017087  pop     r12
0x180017089  pop     rdi
0x18001708a  pop     rsi
0x18001708b  pop     rbx
0x18001708c  pop     rbp
0x18001708d  retn
0x18001708f  mov     r8d, 0Dh; unsigned int
0x180017095  mov     rdx, [rsp+8E0h+var_8A8]; struct _EAP_ERROR *
0x18001709a  lea     rcx, [rsp+8E0h+var_890]; this
0x18001709f  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x1800170a4  nop
0x1800170a5  mov     rcx, [rsp+8E0h+var_8A8]
0x1800170aa  test    rcx, rcx
0x1800170ad  jz      short loc_1800170BB
0x1800170af  mov     rax, [rbx+1A8h]
0x1800170b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170bb  lea     r8, [rsp+8E0h+var_890]; struct EapHost::EapError *
0x1800170c0  lea     rcx, aEappeergetuico_1; "EapPeerGetUIContext"
0x1800170c7  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
