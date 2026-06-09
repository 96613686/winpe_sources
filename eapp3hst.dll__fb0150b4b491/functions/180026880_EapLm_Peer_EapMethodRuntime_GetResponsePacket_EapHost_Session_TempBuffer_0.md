# EapLm::Peer::EapMethodRuntime::GetResponsePacket(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180026880`
- end: `0x180026ab0`
- name: `?GetResponsePacket@EapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x180005894`
- `0x180012620`
- `0x1800154dc`
- `0x180015534`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x180026880`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800268da`
- `ntdll!EtwEventEnabled` at `0x180026a16`
- `ntdll!EtwEventEnabled` at `0x1800268da`
- `ntdll!EtwEventEnabled` at `0x180026a16`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::EapMethodRuntime::GetResponsePacket(__int64 a1, __int64 a2, __int128 *a3)
{
  unsigned int v6; // eax
  const wchar_t *v7; // rdx
  __int128 v8; // xmm6
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  v10 = 0;
  TempBuffer<0>::TempBuffer<0>((__int64)v11, *(unsigned int *)(a2 + 76), 0);
  LODWORD(v9) = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>((unsigned __int64)v11[1]);
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, struct _EAP_ERROR *, const struct _EAP_ERROR **))(a1 + 360))(
         *(_QWORD *)(a2 + 64),
         &v9,
         v11[0],
         &v10);
  if ( v6 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v12, v10, v6);
    (*(void (__fastcall **)(const struct _EAP_ERROR *))(a1 + 424))(v10);
    EapHost::EapException::Throw(L"EapPeerGetResponsePacket", v7, (const struct EapHost::EapError *)v12);
  }
  if ( v11[1] < (struct _EAP_ERROR *)(unsigned int)v9 )
    EapHost::EapException::Throw(L"EapPeerGetResponsePacket", L"ResponsePacketSize", -2143158249);
  v11[1] = (struct _EAP_ERROR *)(unsigned int)v9;
  v8 = *a3;
  *a3 = *(_OWORD *)v11;
  *(_OWORD *)v11 = v8;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "EapPeerGetResponsePacket Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v13);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  HeapAllocator::Free((void *)v8);
}

```

## disassembly

```asm
0x180026880  mov     rax, rsp
0x180026883  push    rbp
0x180026884  push    rbx
0x180026885  push    rsi
0x180026886  push    rdi
0x180026887  push    r12
0x180026889  lea     rbp, [rax-7F8h]
0x180026890  sub     rsp, 8D0h
0x180026897  movaps  xmmword ptr [rax-38h], xmm6
0x18002689b  mov     rax, cs:__security_cookie
0x1800268a2  xor     rax, rsp
0x1800268a5  mov     [rbp+7F0h+var_40], rax
0x1800268ac  mov     rbx, r8
0x1800268af  mov     rsi, rdx
0x1800268b2  mov     rdi, rcx
0x1800268b5  mov     rcx, [r8]; void *
0x1800268b8  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800268bd  mov     qword ptr [rbx], 0
0x1800268c4  mov     qword ptr [rbx+8], 0
0x1800268cc  lea     rdx, DebugInfoEvent
0x1800268d3  mov     rcx, cs:eaphost_Context
0x1800268da  call    cs:__imp_EtwEventEnabled
0x1800268e0  test    al, al
0x1800268e2  jz      short loc_18002691D
0x1800268e4  lea     r8, aEappeergetresp; "EapPeerGetResponsePacket Entry"
0x1800268eb  mov     edx, 800h; unsigned __int64
0x1800268f0  lea     rcx, [rbp+7F0h+var_840]; char *
0x1800268f4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800268f9  test    eax, eax
0x1800268fb  js      short loc_18002691D
0x1800268fd  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180026904  jge     short loc_18002691D
0x180026906  lea     r8, [rbp+7F0h+var_840]
0x18002690a  lea     rdx, DebugInfoEvent
0x180026911  lea     rcx, eaphost_Context
0x180026918  call    McTemplateU0s_EtwEventWriteTransfer
0x18002691d  lea     r12, WPP_GLOBAL_Control
0x180026924  mov     rcx, cs:WPP_GLOBAL_Control
0x18002692b  cmp     rcx, r12
0x18002692e  jz      short loc_18002694B
0x180026930  test    byte ptr [rcx+1Ch], 4
0x180026934  jz      short loc_18002694B
0x180026936  mov     edx, 19h
0x18002693b  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180026942  mov     rcx, [rcx+10h]
0x180026946  call    WPP_SF_
0x18002694b  mov     [rsp+8F0h+var_8B8], 0
0x180026954  mov     edx, [rsi+4Ch]
0x180026957  xor     r8d, r8d
0x18002695a  lea     rcx, [rsp+8F0h+var_8B8+8]
0x18002695f  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x180026964  nop
0x180026965  mov     rcx, qword ptr [rsp+8F0h+var_8A8]
0x18002696a  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002696f  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x180026973  lea     r9, [rsp+8F0h+var_8B8]
0x180026978  mov     r8, [rsp+8F0h+var_8B8+8]
0x18002697d  lea     rdx, [rsp+8F0h+var_8C0]
0x180026982  mov     rcx, [rsi+40h]
0x180026986  mov     rax, [rdi+168h]
0x18002698d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026992  test    eax, eax
0x180026994  jz      short loc_1800269CC
0x180026996  mov     r8d, eax; unsigned int
0x180026999  mov     rdx, [rsp+8F0h+var_8B8]; struct _EAP_ERROR *
0x18002699e  lea     rcx, [rsp+8F0h+var_8A0]; this
0x1800269a3  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x1800269a8  nop
0x1800269a9  mov     rcx, [rsp+8F0h+var_8B8]
0x1800269ae  mov     rax, [rdi+1A8h]
0x1800269b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269ba  lea     r8, [rsp+8F0h+var_8A0]; struct EapHost::EapError *
0x1800269bf  lea     rcx, aEappeergetresp_2; "EapPeerGetResponsePacket"
0x1800269c6  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x1800269cc  mov     eax, dword ptr [rsp+8F0h+var_8C0]
0x1800269d0  cmp     qword ptr [rsp+8F0h+var_8A8], rax
0x1800269d5  jnb     short loc_1800269F1
0x1800269d7  mov     r8d, 80420017h; int
0x1800269dd  lea     rdx, aResponsepacket; "ResponsePacketSize"
0x1800269e4  lea     rcx, aEappeergetresp_2; "EapPeerGetResponsePacket"
0x1800269eb  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800269f1  mov     qword ptr [rsp+8F0h+var_8A8], rax
0x1800269f6  movups  xmm6, xmmword ptr [rbx]
0x1800269f9  movaps  xmm0, xmmword ptr [rsp+8F0h+var_8B8+8]
0x1800269fe  movdqu  xmmword ptr [rbx], xmm0
0x180026a02  movdqa  xmmword ptr [rsp+8F0h+var_8B8+8], xmm6
0x180026a08  lea     rdx, DebugInfoEvent
0x180026a0f  mov     rcx, cs:eaphost_Context
0x180026a16  call    cs:__imp_EtwEventEnabled
0x180026a1c  test    al, al
0x180026a1e  jz      short loc_180026A59
0x180026a20  lea     r8, aEappeergetresp_3; "EapPeerGetResponsePacket Exit"
0x180026a27  mov     edx, 800h; unsigned __int64
0x180026a2c  lea     rcx, [rbp+7F0h+var_840]; char *
0x180026a30  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180026a35  test    eax, eax
0x180026a37  js      short loc_180026A59
0x180026a39  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180026a40  jge     short loc_180026A59
0x180026a42  lea     r8, [rbp+7F0h+var_840]
0x180026a46  lea     rdx, DebugInfoEvent
0x180026a4d  lea     rcx, eaphost_Context
0x180026a54  call    McTemplateU0s_EtwEventWriteTransfer
0x180026a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a60  cmp     rcx, r12
0x180026a63  jz      short loc_180026A81
0x180026a65  test    byte ptr [rcx+1Ch], 4
0x180026a69  jz      short loc_180026A81
0x180026a6b  mov     edx, 1Ah
0x180026a70  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180026a77  mov     rcx, [rcx+10h]
0x180026a7b  call    WPP_SF_
0x180026a80  nop
0x180026a81  movq    rcx, xmm6; void *
0x180026a86  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180026a8b  mov     rcx, [rbp+7F0h+var_40]
0x180026a92  xor     rcx, rsp; StackCookie
0x180026a95  call    __security_check_cookie
0x180026a9a  movaps  xmm6, [rsp+8F0h+var_38+8]
0x180026aa2  add     rsp, 8D0h
0x180026aa9  pop     r12
0x180026aab  pop     rdi
0x180026aac  pop     rsi
0x180026aad  pop     rbx
0x180026aae  pop     rbp
0x180026aaf  retn
```
