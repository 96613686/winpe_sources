# EapLm::Peer::EapMethodRuntime::GetUIContext(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180026ea0`
- end: `0x1800270d0`
- name: `?GetUIContext@EapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x1800126f8`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x180026ea0`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180026f0f`
- `ntdll!EtwEventEnabled` at `0x18002700b`
- `ntdll!EtwEventEnabled` at `0x180026f0f`
- `ntdll!EtwEventEnabled` at `0x18002700b`

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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180026ea0  push    rbp
0x180026ea2  push    rbx
0x180026ea3  push    rsi
0x180026ea4  push    rdi
0x180026ea5  push    r12
0x180026ea7  lea     rbp, [rsp-7C0h]
0x180026eaf  sub     rsp, 8C0h
0x180026eb6  mov     rax, cs:__security_cookie
0x180026ebd  xor     rax, rsp
0x180026ec0  mov     [rbp+7E0h+var_30], rax
0x180026ec7  mov     rdi, r8
0x180026eca  mov     rsi, rdx
0x180026ecd  mov     rbx, rcx
0x180026ed0  mov     rcx, [r8]; void *
0x180026ed3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180026ed8  mov     qword ptr [rdi], 0
0x180026edf  mov     qword ptr [rdi+8], 0
0x180026ee7  mov     [rsp+8E0h+var_8A0], 0
0x180026ef0  mov     [rsp+8E0h+var_8B0], 0
0x180026ef8  mov     [rsp+8E0h+var_8A8], 0
0x180026f01  lea     rdx, DebugInfoEvent
0x180026f08  mov     rcx, cs:eaphost_Context
0x180026f0f  call    cs:__imp_EtwEventEnabled
0x180026f15  test    al, al
0x180026f17  jz      short loc_180026F52
0x180026f19  lea     r8, aEappeergetuico_0; "EapPeerGetUIContext Entry"
0x180026f20  mov     edx, 800h; unsigned __int64
0x180026f25  lea     rcx, [rbp+7E0h+var_830]; char *
0x180026f29  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180026f2e  test    eax, eax
0x180026f30  js      short loc_180026F52
0x180026f32  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180026f39  jge     short loc_180026F52
0x180026f3b  lea     r8, [rbp+7E0h+var_830]
0x180026f3f  lea     rdx, DebugInfoEvent
0x180026f46  lea     rcx, eaphost_Context
0x180026f4d  call    McTemplateU0s_EtwEventWriteTransfer
0x180026f52  lea     r12, WPP_GLOBAL_Control
0x180026f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f60  cmp     rcx, r12
0x180026f63  jz      short loc_180026F80
0x180026f65  test    byte ptr [rcx+1Ch], 4
0x180026f69  jz      short loc_180026F80
0x180026f6b  mov     edx, 1Eh
0x180026f70  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180026f77  mov     rcx, [rcx+10h]
0x180026f7b  call    WPP_SF_
0x180026f80  lea     r9, [rsp+8E0h+var_8A8]
0x180026f85  lea     r8, [rsp+8E0h+var_8A0]
0x180026f8a  lea     rdx, [rsp+8E0h+var_8B0]
0x180026f8f  mov     rcx, [rsi+40h]
0x180026f93  mov     rax, [rbx+178h]
0x180026f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f9f  test    eax, eax
0x180026fa1  jz      short loc_180026FD9
0x180026fa3  mov     r8d, eax; unsigned int
0x180026fa6  mov     rdx, [rsp+8E0h+var_8A8]; struct _EAP_ERROR *
0x180026fab  lea     rcx, [rsp+8E0h+var_890]; this
0x180026fb0  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180026fb5  nop
0x180026fb6  mov     rcx, [rsp+8E0h+var_8A8]
0x180026fbb  mov     rax, [rbx+1A8h]
0x180026fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fc7  lea     r8, [rsp+8E0h+var_890]; struct EapHost::EapError *
0x180026fcc  lea     rcx, aEappeergetuico_1; "EapPeerGetUIContext"
0x180026fd3  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x180026fd9  mov     eax, [rsp+8E0h+var_8B0]
0x180026fdd  test    eax, eax
0x180026fdf  jz      loc_180027092
0x180026fe5  mov     r8, [rsp+8E0h+var_8A0]
0x180026fea  test    r8, r8
0x180026fed  jz      loc_180027092
0x180026ff3  mov     edx, eax
0x180026ff5  mov     rcx, rdi
0x180026ff8  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180026ffd  lea     rdx, DebugInfoEvent
0x180027004  mov     rcx, cs:eaphost_Context
0x18002700b  call    cs:__imp_EtwEventEnabled
0x180027011  test    al, al
0x180027013  jz      short loc_18002704E
0x180027015  lea     r8, aEappeergetuico; "EapPeerGetUIContext Exit"
0x18002701c  mov     edx, 800h; unsigned __int64
0x180027021  lea     rcx, [rbp+7E0h+var_830]; char *
0x180027025  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002702a  test    eax, eax
0x18002702c  js      short loc_18002704E
0x18002702e  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180027035  jge     short loc_18002704E
0x180027037  lea     r8, [rbp+7E0h+var_830]
0x18002703b  lea     rdx, DebugInfoEvent
0x180027042  lea     rcx, eaphost_Context
0x180027049  call    McTemplateU0s_EtwEventWriteTransfer
0x18002704e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027055  cmp     rcx, r12
0x180027058  jz      short loc_180027075
0x18002705a  test    byte ptr [rcx+1Ch], 4
0x18002705e  jz      short loc_180027075
0x180027060  mov     edx, 1Fh
0x180027065  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x18002706c  mov     rcx, [rcx+10h]
0x180027070  call    WPP_SF_
0x180027075  mov     rcx, [rbp+7E0h+var_30]
0x18002707c  xor     rcx, rsp; StackCookie
0x18002707f  call    __security_check_cookie
0x180027084  add     rsp, 8C0h
0x18002708b  pop     r12
0x18002708d  pop     rdi
0x18002708e  pop     rsi
0x18002708f  pop     rbx
0x180027090  pop     rbp
0x180027091  retn
0x180027092  mov     r8d, 0Dh; unsigned int
0x180027098  mov     rdx, [rsp+8E0h+var_8A8]; struct _EAP_ERROR *
0x18002709d  lea     rcx, [rsp+8E0h+var_890]; this
0x1800270a2  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x1800270a7  nop
0x1800270a8  mov     rcx, [rsp+8E0h+var_8A8]
0x1800270ad  test    rcx, rcx
0x1800270b0  jz      short loc_1800270BE
0x1800270b2  mov     rax, [rbx+1A8h]
0x1800270b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270be  lea     r8, [rsp+8E0h+var_890]; struct EapHost::EapError *
0x1800270c3  lea     rcx, aEappeergetuico_1; "EapPeerGetUIContext"
0x1800270ca  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
