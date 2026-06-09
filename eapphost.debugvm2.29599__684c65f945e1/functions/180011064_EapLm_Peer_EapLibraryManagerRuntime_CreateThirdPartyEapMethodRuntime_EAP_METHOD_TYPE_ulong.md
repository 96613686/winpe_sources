# EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE,ulong)

- ea: `0x180011064`
- end: `0x1800112cc`
- name: `?CreateThirdPartyEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAAPEAUIEapMethodRuntime@23@U_EAP_METHOD_TYPE@@K@Z`
- size: `616`
- prototype: `struct EapLm::Peer::IEapMethodRuntime *__fastcall(EapLm::Peer::EapLibraryManagerRuntime *__hidden this, struct _EAP_METHOD_TYPE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010d10`

## callees

- `0x180002a90`
- `0x180004988`
- `0x180009b98`
- `0x18000ada8`
- `0x180010eb4`
- `0x180011064`
- `0x180011578`
- `0x180011958`
- `0x180017590`
- `0x18001dcbc`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800110e5`
- `ntdll!EtwEventEnabled` at `0x180011226`
- `ntdll!EtwEventEnabled` at `0x1800110e5`
- `ntdll!EtwEventEnabled` at `0x180011226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001118e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001118e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001129d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001129d`

## string_xrefs

- `0x180011197`: `COM Error`
- `0x18001119e`: `Create Third Party Proxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct EapLm::Peer::IEapMethodRuntime *__fastcall EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(
        struct IThirdPartyEapDispatcherPeerRuntime **this,
        struct _EAP_METHOD_TYPE *a2,
        __int16 a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  bool v8; // zf
  EapLm::Peer::ThirdPartyEapMethodRuntime *v9; // rax
  __int64 v10; // rbx
  DWORD LastError; // eax
  EapLm::Peer::ThirdPartyEapMethodRuntime *v12; // rax
  EapLm::Peer::ThirdPartyEapMethodRuntime *v13; // rax
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  struct _EAP_METHOD_TYPE v16; // [rsp+40h] [rbp-C0h] BYREF
  char v17[2048]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = 0;
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v15, this + 120);
  while ( (unsigned int)v6 < *((_DWORD *)this + 238) )
  {
    v8 = (_DWORD)v6 == 32;
    if ( (unsigned int)v6 >= 0x20 )
      goto LABEL_21;
    if ( a2->dwAuthorId == LODWORD(this[3 * v6 + 20]) )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v17, 0x800u, " Hosting the third party Eap Method in existing Eap3Host process.") >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v17);
      }
      v9 = (EapLm::Peer::ThirdPartyEapMethodRuntime *)HeapAllocator::Alloc(0x170u);
      *(_QWORD *)&v16.eapType.type = v9;
      if ( v9 )
        v10 = EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(v9, a2, this[3 * v6 + 22]);
      else
        v10 = 0;
      goto LABEL_31;
    }
    v6 = (unsigned int)(v6 + 1);
  }
  v8 = (_DWORD)v6 == 32;
  if ( (unsigned int)v6 >= 0x20 )
  {
LABEL_21:
    if ( v8 )
    {
      if ( (Microsoft_Windows_EapHostEnableBits & 4) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          &eaphost_Context,
          (__int64)ExceededEap3HostProcessCntEvent,
          v7,
          1,
          (__int64)&v16);
LABEL_28:
      v13 = (EapLm::Peer::ThirdPartyEapMethodRuntime *)HeapAllocator::Alloc(0x170u);
      *(_QWORD *)&v16.eapType.type = v13;
      if ( v13 )
        v10 = EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(v13, a2, 0);
      else
        v10 = 0;
      goto LABEL_31;
    }
LABEL_24:
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(
                v17,
                0x800u,
                " Hosting the third party Eap Method in short lived Eap3Host process as method is not fast reconnect capable.") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v17);
    }
    goto LABEL_28;
  }
  if ( (a3 & 0x1000) == 0 )
    goto LABEL_24;
  v16 = *a2;
  if ( (int)EapLm::Peer::EapLibraryManagerRuntime::CreateProxy((EapLm::Peer::EapLibraryManagerRuntime *)this, &v16, v6) < 0 )
  {
    LastError = GetLastError();
    EapHost::EapException::Throw(L"Create Third Party Proxy", L"COM Error", LastError);
  }
  v12 = (EapLm::Peer::ThirdPartyEapMethodRuntime *)HeapAllocator::Alloc(0x170u);
  *(_QWORD *)&v16.eapType.type = v12;
  if ( v12 )
    v10 = EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(v12, a2, this[3 * v6 + 22]);
  else
    v10 = 0;
  ++*((_DWORD *)this + 238);
LABEL_31:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 16));
  return (struct EapLm::Peer::IEapMethodRuntime *)v10;
}

```

## disassembly

```asm
0x180011064  mov     [rsp-8+arg_10], rbx
0x180011069  push    rbp
0x18001106a  push    rsi
0x18001106b  push    rdi
0x18001106c  push    r14
0x18001106e  push    r15
0x180011070  lea     rbp, [rsp-760h]
0x180011078  sub     rsp, 860h
0x18001107f  mov     rax, cs:__security_cookie
0x180011086  xor     rax, rsp
0x180011089  mov     [rbp+780h+var_30], rax
0x180011090  mov     r15d, r8d
0x180011093  mov     rsi, rdx
0x180011096  mov     rdi, rcx
0x180011099  xor     ebx, ebx
0x18001109b  lea     rdx, [rcx+3C0h]
0x1800110a2  lea     rcx, [rsp+880h+var_850]
0x1800110a7  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x1800110ac  nop
0x1800110ad  cmp     ebx, [rdi+3B8h]
0x1800110b3  jnb     loc_18001115D
0x1800110b9  cmp     ebx, 20h ; ' '
0x1800110bc  jnb     loc_1800111E8
0x1800110c2  lea     r14, [rbx+rbx*2]
0x1800110c6  mov     eax, [rdi+r14*8+0A0h]
0x1800110ce  cmp     [rsi+0Ch], eax
0x1800110d1  jz      short loc_1800110D7
0x1800110d3  inc     ebx
0x1800110d5  jmp     short loc_1800110AD
0x1800110d7  lea     rdx, DebugInfoEvent
0x1800110de  mov     rcx, cs:eaphost_Context
0x1800110e5  call    cs:__imp_EtwEventEnabled
0x1800110eb  test    al, al
0x1800110ed  jz      short loc_18001112A
0x1800110ef  lea     r8, aHostingTheThir_0; " Hosting the third party Eap Method in "...
0x1800110f6  mov     edx, 800h; unsigned __int64
0x1800110fb  lea     rcx, [rsp+880h+var_830]; char *
0x180011100  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011105  test    eax, eax
0x180011107  js      short loc_18001112A
0x180011109  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180011110  jge     short loc_18001112A
0x180011112  lea     r8, [rsp+880h+var_830]
0x180011117  lea     rdx, DebugInfoEvent
0x18001111e  lea     rcx, eaphost_Context
0x180011125  call    McTemplateU0s_EtwEventWriteTransfer
0x18001112a  mov     ecx, 170h; unsigned __int64
0x18001112f  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180011134  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x180011139  test    rax, rax
0x18001113c  jz      short loc_180011156
0x18001113e  mov     r8, [rdi+r14*8+0B0h]; struct IThirdPartyEapDispatcherPeerRuntime *
0x180011146  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x180011149  mov     rcx, rax; this
0x18001114c  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x180011151  mov     rbx, rax
0x180011154  jmp     short loc_180011158
0x180011156  xor     ebx, ebx
0x180011158  jmp     loc_180011294
0x18001115d  cmp     ebx, 20h ; ' '
0x180011160  jnb     loc_1800111E8
0x180011166  bt      r15d, 0Ch
0x18001116b  jnb     loc_180011218
0x180011171  movaps  xmm0, xmmword ptr [rsi]
0x180011174  movdqa  xmmword ptr [rsp+880h+var_840.eapType.type], xmm0
0x18001117a  mov     r8d, ebx; int
0x18001117d  lea     rdx, [rsp+880h+var_840]; struct _EAP_METHOD_TYPE
0x180011182  mov     rcx, rdi; this
0x180011185  call    ?CreateProxy@EapLibraryManagerRuntime@Peer@EapLm@@QEAAJU_EAP_METHOD_TYPE@@H@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(_EAP_METHOD_TYPE,int)
0x18001118a  test    eax, eax
0x18001118c  jns     short loc_1800111AB
0x18001118e  call    cs:__imp_GetLastError
0x180011194  mov     r8d, eax; int
0x180011197  lea     rdx, aComError; "COM Error"
0x18001119e  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x1800111a5  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800111ab  mov     ecx, 170h; unsigned __int64
0x1800111b0  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800111b5  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x1800111ba  test    rax, rax
0x1800111bd  jz      short loc_1800111DB
0x1800111bf  lea     r8, [rbx+rbx*2]
0x1800111c3  mov     r8, [rdi+r8*8+0B0h]; struct IThirdPartyEapDispatcherPeerRuntime *
0x1800111cb  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x1800111ce  mov     rcx, rax; this
0x1800111d1  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x1800111d6  mov     rbx, rax
0x1800111d9  jmp     short loc_1800111DD
0x1800111db  xor     ebx, ebx
0x1800111dd  inc     dword ptr [rdi+3B8h]
0x1800111e3  jmp     loc_180011294
0x1800111e8  jnz     short loc_180011218
0x1800111ea  test    cs:Microsoft_Windows_EapHostEnableBits, 4
0x1800111f1  jz      short loc_18001126B
0x1800111f3  lea     rax, [rsp+880h+var_840]
0x1800111f8  mov     [rsp+880h+var_860], rax
0x1800111fd  mov     r9d, 1
0x180011203  lea     rdx, ExceededEap3HostProcessCntEvent
0x18001120a  lea     rcx, eaphost_Context
0x180011211  call    McGenEventWrite_EtwEventWriteTransfer
0x180011216  jmp     short loc_18001126B
0x180011218  lea     rdx, DebugInfoEvent
0x18001121f  mov     rcx, cs:eaphost_Context
0x180011226  call    cs:__imp_EtwEventEnabled
0x18001122c  test    al, al
0x18001122e  jz      short loc_18001126B
0x180011230  lea     r8, aHostingTheThir; " Hosting the third party Eap Method in "...
0x180011237  mov     edx, 800h; unsigned __int64
0x18001123c  lea     rcx, [rsp+880h+var_830]; char *
0x180011241  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011246  test    eax, eax
0x180011248  js      short loc_18001126B
0x18001124a  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180011251  jge     short loc_18001126B
0x180011253  lea     r8, [rsp+880h+var_830]
0x180011258  lea     rdx, DebugInfoEvent
0x18001125f  lea     rcx, eaphost_Context
0x180011266  call    McTemplateU0s_EtwEventWriteTransfer
0x18001126b  mov     ecx, 170h; unsigned __int64
0x180011270  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180011275  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x18001127a  test    rax, rax
0x18001127d  jz      short loc_180011292
0x18001127f  xor     r8d, r8d; struct IThirdPartyEapDispatcherPeerRuntime *
0x180011282  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x180011285  mov     rcx, rax; this
0x180011288  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x18001128d  mov     rbx, rax
0x180011290  jmp     short loc_180011294
0x180011292  xor     ebx, ebx
0x180011294  mov     rcx, [rsp+880h+var_850]
0x180011299  add     rcx, 10h; lpCriticalSection
0x18001129d  call    cs:__imp_LeaveCriticalSection
0x1800112a3  mov     rax, rbx
0x1800112a6  mov     rcx, [rbp+780h+var_30]
0x1800112ad  xor     rcx, rsp; StackCookie
0x1800112b0  call    __security_check_cookie
0x1800112b5  mov     rbx, [rsp+880h+arg_10]
0x1800112bd  add     rsp, 860h
0x1800112c4  pop     r15
0x1800112c6  pop     r14
0x1800112c8  pop     rdi
0x1800112c9  pop     rsi
0x1800112ca  pop     rbp
0x1800112cb  retn
```
