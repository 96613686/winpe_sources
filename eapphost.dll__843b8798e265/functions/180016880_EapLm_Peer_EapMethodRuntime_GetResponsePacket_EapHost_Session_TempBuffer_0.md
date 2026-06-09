# EapLm::Peer::EapMethodRuntime::GetResponsePacket(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180016880`
- end: `0x180016ac5`
- name: `?GetResponsePacket@EapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002af0`
- `0x180007564`
- `0x18000a21c`
- `0x180011cb8`
- `0x1800120c4`
- `0x18001296c`
- `0x1800155c8`
- `0x180016880`
- `0x18001e768`
- `0x18001e7c0`
- `0x180030e7c`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800168da`
- `ntdll!EtwEventEnabled` at `0x1800169d4`
- `ntdll!EtwEventEnabled` at `0x1800168da`
- `ntdll!EtwEventEnabled` at `0x1800169d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::EapMethodRuntime::GetResponsePacket(__int64 a1, __int64 a2, __int128 *a3)
{
  unsigned int v6; // eax
  __int128 v7; // xmm6
  const wchar_t *v8; // rdx
  __int64 v9; // [rsp+38h] [rbp-D0h] BYREF
  const struct _EAP_ERROR *v10; // [rsp+40h] [rbp-C8h] BYREF
  struct _EAP_ERROR *v11[2]; // [rsp+48h] [rbp-C0h] BYREF
  char v12[96]; // [rsp+58h] [rbp-B0h] BYREF
  char v13[2048]; // [rsp+B8h] [rbp-50h] BYREF

  HeapAllocator::Free(*(void **)a3);
  *(_QWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "EapPeerGetResponsePacket Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v13);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  }
  v10 = 0;
  TempBuffer<0>::TempBuffer<0>(v11, *(unsigned int *)(a2 + 76), 0);
  LODWORD(v9) = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v11[1]);
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, struct _EAP_ERROR *, const struct _EAP_ERROR **))(a1 + 360))(
         *(_QWORD *)(a2 + 64),
         &v9,
         v11[0],
         &v10);
  if ( v6 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v12, v10, v6);
    (*(void (__fastcall **)(const struct _EAP_ERROR *))(a1 + 424))(v10);
    EapHost::EapException::Throw(L"EapPeerGetResponsePacket", v8, (const struct EapHost::EapError *)v12);
  }
  if ( v11[1] < (struct _EAP_ERROR *)(unsigned int)v9 )
    EapHost::EapException::Throw(L"EapPeerGetResponsePacket", L"ResponsePacketSize", -2143158249);
  v11[1] = (struct _EAP_ERROR *)(unsigned int)v9;
  v7 = *a3;
  *a3 = *(_OWORD *)v11;
  *(_OWORD *)v11 = v7;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "EapPeerGetResponsePacket Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v13);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  }
  HeapAllocator::Free((void *)v7);
}

```

## disassembly

```asm
0x180016880  mov     rax, rsp
0x180016883  push    rbp
0x180016884  push    rbx
0x180016885  push    rsi
0x180016886  push    rdi
0x180016887  push    r12
0x180016889  lea     rbp, [rax-7F8h]
0x180016890  sub     rsp, 8D0h
0x180016897  movaps  xmmword ptr [rax-38h], xmm6
0x18001689b  mov     rax, cs:__security_cookie
0x1800168a2  xor     rax, rsp
0x1800168a5  mov     [rbp+7F0h+var_40], rax
0x1800168ac  mov     rbx, r8
0x1800168af  mov     rsi, rdx
0x1800168b2  mov     rdi, rcx
0x1800168b5  mov     rcx, [r8]; void *
0x1800168b8  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800168bd  mov     qword ptr [rbx], 0
0x1800168c4  mov     qword ptr [rbx+8], 0
0x1800168cc  lea     rdx, DebugInfoEvent
0x1800168d3  mov     rcx, cs:eaphost_Context
0x1800168da  call    cs:__imp_EtwEventEnabled
0x1800168e1  nop     dword ptr [rax+rax+00h]
0x1800168e6  test    al, al
0x1800168e8  jz      short loc_180016923
0x1800168ea  lea     r8, aEappeergetresp; "EapPeerGetResponsePacket Entry"
0x1800168f1  mov     edx, 800h; unsigned __int64
0x1800168f6  lea     rcx, [rbp+7F0h+var_840]; char *
0x1800168fa  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800168ff  test    eax, eax
0x180016901  js      short loc_180016923
0x180016903  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001690a  jge     short loc_180016923
0x18001690c  lea     r8, [rbp+7F0h+var_840]
0x180016910  lea     rdx, DebugInfoEvent
0x180016917  lea     rcx, eaphost_Context
0x18001691e  call    McTemplateU0s_EtwEventWriteTransfer
0x180016923  lea     r12, WPP_GLOBAL_Control
0x18001692a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016931  cmp     rcx, r12
0x180016934  jz      short loc_180016951
0x180016936  test    byte ptr [rcx+1Ch], 4
0x18001693a  jz      short loc_180016951
0x18001693c  mov     edx, 19h
0x180016941  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180016948  mov     rcx, [rcx+10h]
0x18001694c  call    WPP_SF_
0x180016951  mov     [rsp+8F0h+var_8B8], 0
0x18001695a  mov     edx, [rsi+4Ch]
0x18001695d  xor     r8d, r8d
0x180016960  lea     rcx, [rsp+8F0h+var_8B8+8]
0x180016965  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x18001696a  nop
0x18001696b  mov     rcx, qword ptr [rsp+8F0h+var_8A8]
0x180016970  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180016975  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x180016979  lea     r9, [rsp+8F0h+var_8B8]
0x18001697e  mov     r8, [rsp+8F0h+var_8B8+8]
0x180016983  lea     rdx, [rsp+8F0h+var_8C0]
0x180016988  mov     rcx, [rsi+40h]
0x18001698c  mov     rax, [rdi+168h]
0x180016993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016998  test    eax, eax
0x18001699a  jnz     loc_180016A8F
0x1800169a0  mov     eax, dword ptr [rsp+8F0h+var_8C0]
0x1800169a4  cmp     qword ptr [rsp+8F0h+var_8A8], rax
0x1800169a9  jb      loc_180016A75
0x1800169af  mov     qword ptr [rsp+8F0h+var_8A8], rax
0x1800169b4  movups  xmm6, xmmword ptr [rbx]
0x1800169b7  movaps  xmm0, xmmword ptr [rsp+8F0h+var_8B8+8]
0x1800169bc  movdqu  xmmword ptr [rbx], xmm0
0x1800169c0  movdqa  xmmword ptr [rsp+8F0h+var_8B8+8], xmm6
0x1800169c6  lea     rdx, DebugInfoEvent
0x1800169cd  mov     rcx, cs:eaphost_Context
0x1800169d4  call    cs:__imp_EtwEventEnabled
0x1800169db  nop     dword ptr [rax+rax+00h]
0x1800169e0  test    al, al
0x1800169e2  jz      short loc_180016A1D
0x1800169e4  lea     r8, aEappeergetresp_3; "EapPeerGetResponsePacket Exit"
0x1800169eb  mov     edx, 800h; unsigned __int64
0x1800169f0  lea     rcx, [rbp+7F0h+var_840]; char *
0x1800169f4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800169f9  test    eax, eax
0x1800169fb  js      short loc_180016A1D
0x1800169fd  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180016a04  jge     short loc_180016A1D
0x180016a06  lea     r8, [rbp+7F0h+var_840]
0x180016a0a  lea     rdx, DebugInfoEvent
0x180016a11  lea     rcx, eaphost_Context
0x180016a18  call    McTemplateU0s_EtwEventWriteTransfer
0x180016a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a24  cmp     rcx, r12
0x180016a27  jz      short loc_180016A45
0x180016a29  test    byte ptr [rcx+1Ch], 4
0x180016a2d  jz      short loc_180016A45
0x180016a2f  mov     edx, 1Ah
0x180016a34  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180016a3b  mov     rcx, [rcx+10h]
0x180016a3f  call    WPP_SF_
0x180016a44  nop
0x180016a45  movq    rcx, xmm6; void *
0x180016a4a  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180016a4f  mov     rcx, [rbp+7F0h+var_40]
0x180016a56  xor     rcx, rsp; StackCookie
0x180016a59  call    __security_check_cookie
0x180016a5e  movaps  xmm6, [rsp+8F0h+var_38+8]
0x180016a66  add     rsp, 8D0h
0x180016a6d  pop     r12
0x180016a6f  pop     rdi
0x180016a70  pop     rsi
0x180016a71  pop     rbx
0x180016a72  pop     rbp
0x180016a73  retn
0x180016a75  mov     r8d, 80420017h; int
0x180016a7b  lea     rdx, aResponsepacket; "ResponsePacketSize"
0x180016a82  lea     rcx, aEappeergetresp_2; "EapPeerGetResponsePacket"
0x180016a89  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180016a8f  mov     r8d, eax; unsigned int
0x180016a92  mov     rdx, [rsp+8F0h+var_8B8]; struct _EAP_ERROR *
0x180016a97  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180016a9c  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180016aa1  nop
0x180016aa2  mov     rcx, [rsp+8F0h+var_8B8]
0x180016aa7  mov     rax, [rdi+1A8h]
0x180016aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab3  lea     r8, [rsp+8F0h+var_8A0]; struct EapHost::EapError *
0x180016ab8  lea     rcx, aEappeergetresp_2; "EapPeerGetResponsePacket"
0x180016abf  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
