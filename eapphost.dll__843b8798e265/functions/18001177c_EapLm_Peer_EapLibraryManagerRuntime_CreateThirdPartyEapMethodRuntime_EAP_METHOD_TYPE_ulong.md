# EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE,ulong)

- ea: `0x18001177c`
- end: `0x1800119fd`
- name: `?CreateThirdPartyEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAAPEAUIEapMethodRuntime@23@U_EAP_METHOD_TYPE@@K@Z`
- size: `641`
- prototype: `struct EapLm::Peer::IEapMethodRuntime *__fastcall(EapLm::Peer::EapLibraryManagerRuntime *__hidden this, struct _EAP_METHOD_TYPE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800113c0`

## callees

- `0x180002af0`
- `0x180004af8`
- `0x180009fe4`
- `0x18000b248`
- `0x1800115b4`
- `0x18001177c`
- `0x180011cb8`
- `0x1800120c4`
- `0x180017e7c`
- `0x18001e7c0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800117fd`
- `ntdll!EtwEventEnabled` at `0x18001194a`
- `ntdll!EtwEventEnabled` at `0x1800117fd`
- `ntdll!EtwEventEnabled` at `0x18001194a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119c7`

## string_xrefs

- `0x1800118bb`: `COM Error`
- `0x1800118c2`: `Create Third Party Proxy`

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
0x18001177c  mov     [rsp-8+arg_10], rbx
0x180011781  push    rbp
0x180011782  push    rsi
0x180011783  push    rdi
0x180011784  push    r14
0x180011786  push    r15
0x180011788  lea     rbp, [rsp-760h]
0x180011790  sub     rsp, 860h
0x180011797  mov     rax, cs:__security_cookie
0x18001179e  xor     rax, rsp
0x1800117a1  mov     [rbp+780h+var_30], rax
0x1800117a8  mov     r15d, r8d
0x1800117ab  mov     rsi, rdx
0x1800117ae  mov     rdi, rcx
0x1800117b1  xor     ebx, ebx
0x1800117b3  lea     rdx, [rcx+3C0h]
0x1800117ba  lea     rcx, [rsp+880h+var_850]
0x1800117bf  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x1800117c4  nop
0x1800117c5  cmp     ebx, [rdi+3B8h]
0x1800117cb  jnb     loc_18001187B
0x1800117d1  cmp     ebx, 20h ; ' '
0x1800117d4  jnb     loc_18001190C
0x1800117da  lea     r14, [rbx+rbx*2]
0x1800117de  mov     eax, [rdi+r14*8+0A0h]
0x1800117e6  cmp     [rsi+0Ch], eax
0x1800117e9  jz      short loc_1800117EF
0x1800117eb  inc     ebx
0x1800117ed  jmp     short loc_1800117C5
0x1800117ef  lea     rdx, DebugInfoEvent
0x1800117f6  mov     rcx, cs:eaphost_Context
0x1800117fd  call    cs:__imp_EtwEventEnabled
0x180011804  nop     dword ptr [rax+rax+00h]
0x180011809  test    al, al
0x18001180b  jz      short loc_180011848
0x18001180d  lea     r8, aHostingTheThir_0; " Hosting the third party Eap Method in "...
0x180011814  mov     edx, 800h; unsigned __int64
0x180011819  lea     rcx, [rsp+880h+var_830]; char *
0x18001181e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011823  test    eax, eax
0x180011825  js      short loc_180011848
0x180011827  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001182e  jge     short loc_180011848
0x180011830  lea     r8, [rsp+880h+var_830]
0x180011835  lea     rdx, DebugInfoEvent
0x18001183c  lea     rcx, eaphost_Context
0x180011843  call    McTemplateU0s_EtwEventWriteTransfer
0x180011848  mov     ecx, 170h; unsigned __int64
0x18001184d  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180011852  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x180011857  test    rax, rax
0x18001185a  jz      short loc_180011874
0x18001185c  mov     r8, [rdi+r14*8+0B0h]; struct IThirdPartyEapDispatcherPeerRuntime *
0x180011864  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x180011867  mov     rcx, rax; this
0x18001186a  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x18001186f  mov     rbx, rax
0x180011872  jmp     short loc_180011876
0x180011874  xor     ebx, ebx
0x180011876  jmp     loc_1800119BE
0x18001187b  cmp     ebx, 20h ; ' '
0x18001187e  jnb     loc_18001190C
0x180011884  bt      r15d, 0Ch
0x180011889  jnb     loc_18001193C
0x18001188f  movaps  xmm0, xmmword ptr [rsi]
0x180011892  movdqa  xmmword ptr [rsp+880h+var_840.eapType.type], xmm0
0x180011898  mov     r8d, ebx; int
0x18001189b  lea     rdx, [rsp+880h+var_840]; struct _EAP_METHOD_TYPE
0x1800118a0  mov     rcx, rdi; this
0x1800118a3  call    ?CreateProxy@EapLibraryManagerRuntime@Peer@EapLm@@QEAAJU_EAP_METHOD_TYPE@@H@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(_EAP_METHOD_TYPE,int)
0x1800118a8  test    eax, eax
0x1800118aa  jns     short loc_1800118CF
0x1800118ac  call    cs:__imp_GetLastError
0x1800118b3  nop     dword ptr [rax+rax+00h]
0x1800118b8  mov     r8d, eax; int
0x1800118bb  lea     rdx, aComError; "COM Error"
0x1800118c2  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x1800118c9  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800118cf  mov     ecx, 170h; unsigned __int64
0x1800118d4  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800118d9  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x1800118de  test    rax, rax
0x1800118e1  jz      short loc_1800118FF
0x1800118e3  lea     r8, [rbx+rbx*2]
0x1800118e7  mov     r8, [rdi+r8*8+0B0h]; struct IThirdPartyEapDispatcherPeerRuntime *
0x1800118ef  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x1800118f2  mov     rcx, rax; this
0x1800118f5  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x1800118fa  mov     rbx, rax
0x1800118fd  jmp     short loc_180011901
0x1800118ff  xor     ebx, ebx
0x180011901  inc     dword ptr [rdi+3B8h]
0x180011907  jmp     loc_1800119BE
0x18001190c  jnz     short loc_18001193C
0x18001190e  test    cs:Microsoft_Windows_EapHostEnableBits, 4
0x180011915  jz      short loc_180011995
0x180011917  lea     rax, [rsp+880h+var_840]
0x18001191c  mov     [rsp+880h+var_860], rax
0x180011921  mov     r9d, 1
0x180011927  lea     rdx, ExceededEap3HostProcessCntEvent
0x18001192e  lea     rcx, eaphost_Context
0x180011935  call    McGenEventWrite_EtwEventWriteTransfer
0x18001193a  jmp     short loc_180011995
0x18001193c  lea     rdx, DebugInfoEvent
0x180011943  mov     rcx, cs:eaphost_Context
0x18001194a  call    cs:__imp_EtwEventEnabled
0x180011951  nop     dword ptr [rax+rax+00h]
0x180011956  test    al, al
0x180011958  jz      short loc_180011995
0x18001195a  lea     r8, aHostingTheThir; " Hosting the third party Eap Method in "...
0x180011961  mov     edx, 800h; unsigned __int64
0x180011966  lea     rcx, [rsp+880h+var_830]; char *
0x18001196b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011970  test    eax, eax
0x180011972  js      short loc_180011995
0x180011974  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001197b  jge     short loc_180011995
0x18001197d  lea     r8, [rsp+880h+var_830]
0x180011982  lea     rdx, DebugInfoEvent
0x180011989  lea     rcx, eaphost_Context
0x180011990  call    McTemplateU0s_EtwEventWriteTransfer
0x180011995  mov     ecx, 170h; unsigned __int64
0x18001199a  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18001199f  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x1800119a4  test    rax, rax
0x1800119a7  jz      short loc_1800119BC
0x1800119a9  xor     r8d, r8d; struct IThirdPartyEapDispatcherPeerRuntime *
0x1800119ac  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x1800119af  mov     rcx, rax; this
0x1800119b2  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x1800119b7  mov     rbx, rax
0x1800119ba  jmp     short loc_1800119BE
0x1800119bc  xor     ebx, ebx
0x1800119be  mov     rcx, [rsp+880h+var_850]
0x1800119c3  add     rcx, 10h; lpCriticalSection
0x1800119c7  call    cs:__imp_LeaveCriticalSection
0x1800119ce  nop     dword ptr [rax+rax+00h]
0x1800119d3  mov     rax, rbx
0x1800119d6  mov     rcx, [rbp+780h+var_30]
0x1800119dd  xor     rcx, rsp; StackCookie
0x1800119e0  call    __security_check_cookie
0x1800119e5  mov     rbx, [rsp+880h+arg_10]
0x1800119ed  add     rsp, 860h
0x1800119f4  pop     r15
0x1800119f6  pop     r14
0x1800119f8  pop     rdi
0x1800119f9  pop     rsi
0x1800119fa  pop     rbp
0x1800119fb  retn
```
