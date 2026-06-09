# EapLm::Peer::EapMethodRuntime::GetResponsePacket(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180016010`
- end: `0x180016248`
- name: `?GetResponsePacket@EapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `568`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a90`
- `0x1800072cc`
- `0x180009dc4`
- `0x180011578`
- `0x180011958`
- `0x1800121ec`
- `0x180014d8c`
- `0x180016010`
- `0x18001dc64`
- `0x18001dcbc`
- `0x18002fc6c`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001606a`
- `ntdll!EtwEventEnabled` at `0x18001615e`
- `ntdll!EtwEventEnabled` at `0x18001606a`
- `ntdll!EtwEventEnabled` at `0x18001615e`

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
0x180016010  mov     rax, rsp
0x180016013  push    rbp
0x180016014  push    rbx
0x180016015  push    rsi
0x180016016  push    rdi
0x180016017  push    r12
0x180016019  lea     rbp, [rax-7F8h]
0x180016020  sub     rsp, 8D0h
0x180016027  movaps  xmmword ptr [rax-38h], xmm6
0x18001602b  mov     rax, cs:__security_cookie
0x180016032  xor     rax, rsp
0x180016035  mov     [rbp+7F0h+var_40], rax
0x18001603c  mov     rbx, r8
0x18001603f  mov     rsi, rdx
0x180016042  mov     rdi, rcx
0x180016045  mov     rcx, [r8]; void *
0x180016048  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001604d  mov     qword ptr [rbx], 0
0x180016054  mov     qword ptr [rbx+8], 0
0x18001605c  lea     rdx, DebugInfoEvent
0x180016063  mov     rcx, cs:eaphost_Context
0x18001606a  call    cs:__imp_EtwEventEnabled
0x180016070  test    al, al
0x180016072  jz      short loc_1800160AD
0x180016074  lea     r8, aEappeergetresp; "EapPeerGetResponsePacket Entry"
0x18001607b  mov     edx, 800h; unsigned __int64
0x180016080  lea     rcx, [rbp+7F0h+var_840]; char *
0x180016084  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180016089  test    eax, eax
0x18001608b  js      short loc_1800160AD
0x18001608d  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180016094  jge     short loc_1800160AD
0x180016096  lea     r8, [rbp+7F0h+var_840]
0x18001609a  lea     rdx, DebugInfoEvent
0x1800160a1  lea     rcx, eaphost_Context
0x1800160a8  call    McTemplateU0s_EtwEventWriteTransfer
0x1800160ad  lea     r12, WPP_GLOBAL_Control
0x1800160b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160bb  cmp     rcx, r12
0x1800160be  jz      short loc_1800160DB
0x1800160c0  test    byte ptr [rcx+1Ch], 4
0x1800160c4  jz      short loc_1800160DB
0x1800160c6  mov     edx, 19h
0x1800160cb  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x1800160d2  mov     rcx, [rcx+10h]
0x1800160d6  call    WPP_SF_
0x1800160db  mov     [rsp+8F0h+var_8B8], 0
0x1800160e4  mov     edx, [rsi+4Ch]
0x1800160e7  xor     r8d, r8d
0x1800160ea  lea     rcx, [rsp+8F0h+var_8B8+8]
0x1800160ef  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x1800160f4  nop
0x1800160f5  mov     rcx, qword ptr [rsp+8F0h+var_8A8]
0x1800160fa  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800160ff  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x180016103  lea     r9, [rsp+8F0h+var_8B8]
0x180016108  mov     r8, [rsp+8F0h+var_8B8+8]
0x18001610d  lea     rdx, [rsp+8F0h+var_8C0]
0x180016112  mov     rcx, [rsi+40h]
0x180016116  mov     rax, [rdi+168h]
0x18001611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016122  test    eax, eax
0x180016124  jnz     loc_180016212
0x18001612a  mov     eax, dword ptr [rsp+8F0h+var_8C0]
0x18001612e  cmp     qword ptr [rsp+8F0h+var_8A8], rax
0x180016133  jb      loc_1800161F8
0x180016139  mov     qword ptr [rsp+8F0h+var_8A8], rax
0x18001613e  movups  xmm6, xmmword ptr [rbx]
0x180016141  movaps  xmm0, xmmword ptr [rsp+8F0h+var_8B8+8]
0x180016146  movdqu  xmmword ptr [rbx], xmm0
0x18001614a  movdqa  xmmword ptr [rsp+8F0h+var_8B8+8], xmm6
0x180016150  lea     rdx, DebugInfoEvent
0x180016157  mov     rcx, cs:eaphost_Context
0x18001615e  call    cs:__imp_EtwEventEnabled
0x180016164  test    al, al
0x180016166  jz      short loc_1800161A1
0x180016168  lea     r8, aEappeergetresp_3; "EapPeerGetResponsePacket Exit"
0x18001616f  mov     edx, 800h; unsigned __int64
0x180016174  lea     rcx, [rbp+7F0h+var_840]; char *
0x180016178  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001617d  test    eax, eax
0x18001617f  js      short loc_1800161A1
0x180016181  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180016188  jge     short loc_1800161A1
0x18001618a  lea     r8, [rbp+7F0h+var_840]
0x18001618e  lea     rdx, DebugInfoEvent
0x180016195  lea     rcx, eaphost_Context
0x18001619c  call    McTemplateU0s_EtwEventWriteTransfer
0x1800161a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161a8  cmp     rcx, r12
0x1800161ab  jz      short loc_1800161C9
0x1800161ad  test    byte ptr [rcx+1Ch], 4
0x1800161b1  jz      short loc_1800161C9
0x1800161b3  mov     edx, 1Ah
0x1800161b8  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x1800161bf  mov     rcx, [rcx+10h]
0x1800161c3  call    WPP_SF_
0x1800161c8  nop
0x1800161c9  movq    rcx, xmm6; void *
0x1800161ce  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800161d3  mov     rcx, [rbp+7F0h+var_40]
0x1800161da  xor     rcx, rsp; StackCookie
0x1800161dd  call    __security_check_cookie
0x1800161e2  movaps  xmm6, [rsp+8F0h+var_38+8]
0x1800161ea  add     rsp, 8D0h
0x1800161f1  pop     r12
0x1800161f3  pop     rdi
0x1800161f4  pop     rsi
0x1800161f5  pop     rbx
0x1800161f6  pop     rbp
0x1800161f7  retn
0x1800161f8  mov     r8d, 80420017h; int
0x1800161fe  lea     rdx, aResponsepacket; "ResponsePacketSize"
0x180016205  lea     rcx, aEappeergetresp_2; "EapPeerGetResponsePacket"
0x18001620c  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180016212  mov     r8d, eax; unsigned int
0x180016215  mov     rdx, [rsp+8F0h+var_8B8]; struct _EAP_ERROR *
0x18001621a  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18001621f  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180016224  nop
0x180016225  mov     rcx, [rsp+8F0h+var_8B8]
0x18001622a  mov     rax, [rdi+1A8h]
0x180016231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016236  lea     r8, [rsp+8F0h+var_8A0]; struct EapHost::EapError *
0x18001623b  lea     rcx, aEappeergetresp_2; "EapPeerGetResponsePacket"
0x180016242  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
