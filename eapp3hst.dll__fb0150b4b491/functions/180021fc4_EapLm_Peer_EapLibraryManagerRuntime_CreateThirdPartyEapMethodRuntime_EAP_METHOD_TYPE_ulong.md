# EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE,ulong)

- ea: `0x180021fc4`
- end: `0x18002222c`
- name: `?CreateThirdPartyEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAAPEAUIEapMethodRuntime@23@U_EAP_METHOD_TYPE@@K@Z`
- size: `616`
- prototype: `struct EapLm::Peer::IEapMethodRuntime *__fastcall(struct IThirdPartyEapDispatcherPeerRuntime **this, struct _EAP_METHOD_TYPE *, __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021c20`

## callees

- `0x1800017a0`
- `0x180003e38`
- `0x180012d18`
- `0x180014ecc`
- `0x180015534`
- `0x180016400`
- `0x18001b154`
- `0x180021e14`
- `0x180021fc4`
- `0x180027d9c`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180022045`
- `ntdll!EtwEventEnabled` at `0x180022186`
- `ntdll!EtwEventEnabled` at `0x180022045`
- `ntdll!EtwEventEnabled` at `0x180022186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800221fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800221fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220ee`

## string_xrefs

- `0x1800220f7`: `COM Error`
- `0x1800220fe`: `Create Third Party Proxy`

## pseudocode

```c
struct EapLm::Peer::IEapMethodRuntime *__fastcall EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(
        struct IThirdPartyEapDispatcherPeerRuntime **this,
        struct _EAP_METHOD_TYPE *a2,
        __int16 a3)
{
  __int64 v6; // rbx
  int v7; // r8d
  bool v8; // zf
  EapLm::Peer::ThirdPartyEapMethodRuntime *v9; // rax
  EapLm::Peer::ThirdPartyEapMethodRuntime *v10; // rbx
  DWORD LastError; // eax
  EapLm::Peer::ThirdPartyEapMethodRuntime *v12; // rax
  EapLm::Peer::ThirdPartyEapMethodRuntime *v13; // rax
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  struct _EAP_METHOD_TYPE v16; // [rsp+40h] [rbp-C0h] BYREF
  char v17[2048]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = 0;
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v15, (__int64)(this + 120));
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
          (unsigned int)&eaphost_Context,
          (unsigned int)ExceededEap3HostProcessCntEvent,
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
  return v10;
}

```

## disassembly

```asm
0x180021fc4  mov     [rsp-8+arg_10], rbx
0x180021fc9  push    rbp
0x180021fca  push    rsi
0x180021fcb  push    rdi
0x180021fcc  push    r14
0x180021fce  push    r15
0x180021fd0  lea     rbp, [rsp-760h]
0x180021fd8  sub     rsp, 860h
0x180021fdf  mov     rax, cs:__security_cookie
0x180021fe6  xor     rax, rsp
0x180021fe9  mov     [rbp+780h+var_30], rax
0x180021ff0  mov     r15d, r8d
0x180021ff3  mov     rsi, rdx
0x180021ff6  mov     rdi, rcx
0x180021ff9  xor     ebx, ebx
0x180021ffb  lea     rdx, [rcx+3C0h]
0x180022002  lea     rcx, [rsp+880h+var_850]
0x180022007  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18002200c  nop
0x18002200d  cmp     ebx, [rdi+3B8h]
0x180022013  jnb     loc_1800220BD
0x180022019  cmp     ebx, 20h ; ' '
0x18002201c  jnb     loc_180022148
0x180022022  lea     r14, [rbx+rbx*2]
0x180022026  mov     eax, [rdi+r14*8+0A0h]
0x18002202e  cmp     [rsi+0Ch], eax
0x180022031  jz      short loc_180022037
0x180022033  inc     ebx
0x180022035  jmp     short loc_18002200D
0x180022037  lea     rdx, DebugInfoEvent
0x18002203e  mov     rcx, cs:eaphost_Context
0x180022045  call    cs:__imp_EtwEventEnabled
0x18002204b  test    al, al
0x18002204d  jz      short loc_18002208A
0x18002204f  lea     r8, aHostingTheThir_0; " Hosting the third party Eap Method in "...
0x180022056  mov     edx, 800h; unsigned __int64
0x18002205b  lea     rcx, [rsp+880h+var_830]; char *
0x180022060  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180022065  test    eax, eax
0x180022067  js      short loc_18002208A
0x180022069  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180022070  jge     short loc_18002208A
0x180022072  lea     r8, [rsp+880h+var_830]
0x180022077  lea     rdx, DebugInfoEvent
0x18002207e  lea     rcx, eaphost_Context
0x180022085  call    McTemplateU0s_EtwEventWriteTransfer
0x18002208a  mov     ecx, 170h; unsigned __int64
0x18002208f  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180022094  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x180022099  test    rax, rax
0x18002209c  jz      short loc_1800220B6
0x18002209e  mov     r8, [rdi+r14*8+0B0h]; struct IThirdPartyEapDispatcherPeerRuntime *
0x1800220a6  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x1800220a9  mov     rcx, rax; this
0x1800220ac  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x1800220b1  mov     rbx, rax
0x1800220b4  jmp     short loc_1800220B8
0x1800220b6  xor     ebx, ebx
0x1800220b8  jmp     loc_1800221F4
0x1800220bd  cmp     ebx, 20h ; ' '
0x1800220c0  jnb     loc_180022148
0x1800220c6  bt      r15d, 0Ch
0x1800220cb  jnb     loc_180022178
0x1800220d1  movaps  xmm0, xmmword ptr [rsi]
0x1800220d4  movdqa  xmmword ptr [rsp+880h+var_840.eapType.type], xmm0
0x1800220da  mov     r8d, ebx; int
0x1800220dd  lea     rdx, [rsp+880h+var_840]; struct _EAP_METHOD_TYPE
0x1800220e2  mov     rcx, rdi; this
0x1800220e5  call    ?CreateProxy@EapLibraryManagerRuntime@Peer@EapLm@@QEAAJU_EAP_METHOD_TYPE@@H@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(_EAP_METHOD_TYPE,int)
0x1800220ea  test    eax, eax
0x1800220ec  jns     short loc_18002210B
0x1800220ee  call    cs:__imp_GetLastError
0x1800220f4  mov     r8d, eax; int
0x1800220f7  lea     rdx, aComError; "COM Error"
0x1800220fe  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180022105  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18002210b  mov     ecx, 170h; unsigned __int64
0x180022110  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180022115  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x18002211a  test    rax, rax
0x18002211d  jz      short loc_18002213B
0x18002211f  lea     r8, [rbx+rbx*2]
0x180022123  mov     r8, [rdi+r8*8+0B0h]; struct IThirdPartyEapDispatcherPeerRuntime *
0x18002212b  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x18002212e  mov     rcx, rax; this
0x180022131  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x180022136  mov     rbx, rax
0x180022139  jmp     short loc_18002213D
0x18002213b  xor     ebx, ebx
0x18002213d  inc     dword ptr [rdi+3B8h]
0x180022143  jmp     loc_1800221F4
0x180022148  jnz     short loc_180022178
0x18002214a  test    cs:Microsoft_Windows_EapHostEnableBits, 4
0x180022151  jz      short loc_1800221CB
0x180022153  lea     rax, [rsp+880h+var_840]
0x180022158  mov     [rsp+880h+var_860], rax
0x18002215d  mov     r9d, 1
0x180022163  lea     rdx, ExceededEap3HostProcessCntEvent
0x18002216a  lea     rcx, eaphost_Context
0x180022171  call    McGenEventWrite_EtwEventWriteTransfer
0x180022176  jmp     short loc_1800221CB
0x180022178  lea     rdx, DebugInfoEvent
0x18002217f  mov     rcx, cs:eaphost_Context
0x180022186  call    cs:__imp_EtwEventEnabled
0x18002218c  test    al, al
0x18002218e  jz      short loc_1800221CB
0x180022190  lea     r8, aHostingTheThir; " Hosting the third party Eap Method in "...
0x180022197  mov     edx, 800h; unsigned __int64
0x18002219c  lea     rcx, [rsp+880h+var_830]; char *
0x1800221a1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800221a6  test    eax, eax
0x1800221a8  js      short loc_1800221CB
0x1800221aa  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800221b1  jge     short loc_1800221CB
0x1800221b3  lea     r8, [rsp+880h+var_830]
0x1800221b8  lea     rdx, DebugInfoEvent
0x1800221bf  lea     rcx, eaphost_Context
0x1800221c6  call    McTemplateU0s_EtwEventWriteTransfer
0x1800221cb  mov     ecx, 170h; unsigned __int64
0x1800221d0  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800221d5  mov     qword ptr [rsp+880h+var_840.eapType.type], rax
0x1800221da  test    rax, rax
0x1800221dd  jz      short loc_1800221F2
0x1800221df  xor     r8d, r8d; struct IThirdPartyEapDispatcherPeerRuntime *
0x1800221e2  mov     rdx, rsi; struct _EAP_METHOD_TYPE *
0x1800221e5  mov     rcx, rax; this
0x1800221e8  call    ??0ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@PEAUIThirdPartyEapDispatcherPeerRuntime@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::ThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE const &,IThirdPartyEapDispatcherPeerRuntime *)
0x1800221ed  mov     rbx, rax
0x1800221f0  jmp     short loc_1800221F4
0x1800221f2  xor     ebx, ebx
0x1800221f4  mov     rcx, [rsp+880h+var_850]
0x1800221f9  add     rcx, 10h; lpCriticalSection
0x1800221fd  call    cs:__imp_LeaveCriticalSection
0x180022203  mov     rax, rbx
0x180022206  mov     rcx, [rbp+780h+var_30]
0x18002220d  xor     rcx, rsp; StackCookie
0x180022210  call    __security_check_cookie
0x180022215  mov     rbx, [rsp+880h+arg_10]
0x18002221d  add     rsp, 860h
0x180022224  pop     r15
0x180022226  pop     r14
0x180022228  pop     rdi
0x180022229  pop     rsi
0x18002222a  pop     rbp
0x18002222b  retn
```
