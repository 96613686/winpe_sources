# NetDownload::NetDownload(NetParams *,NetConnection *,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_GUID const *)

- ea: `0x18020fb44`
- end: `0x18020fcf5`
- name: `??0NetDownload@@QEAA@PEAVNetParams@@PEAVNetConnection@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_GUID@@@Z`
- size: `433`
- prototype: `__int64 __usercall@<rax>(DWORD_PTR dwContext@<rcx>, LPCWSTR lpszObjectName, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x180253ca0`
- `0x180253e50`

## callees

- `0x18012a85c`
- `0x18012e628`
- `0x18020fb44`
- `0x18020fffc`
- `0x180254390`
- `0x180254400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18020fb78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18020fb78`
- `WININET!HttpOpenRequestW` at `0x18020fc83`
- `WININET!HttpOpenRequestW` at `0x18020fc83`
- `WININET!InternetSetOptionW` at `0x18020fcc4`
- `WININET!InternetSetOptionW` at `0x18020fcc4`
- `WININET!InternetSetStatusCallbackW` at `0x18020fcd8`
- `WININET!InternetSetStatusCallbackW` at `0x18020fcd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
DWORD_PTR __fastcall NetDownload::NetDownload(
        DWORD_PTR dwContext,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        LPCWSTR lpszObjectName,
        __int128 *a6)
{
  const WCHAR *v10; // r14
  HINTERNET *v11; // rsi
  LPCWSTR *lplpszAcceptTypes; // rcx
  const WCHAR *lpszReferrer; // rdi
  void *v14; // rcx
  int Buffer; // [rsp+40h] [rbp-58h] BYREF
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF
  DWORD_PTR v18; // [rsp+58h] [rbp-40h]

  v10 = lpszObjectName;
  v18 = dwContext;
  *(_QWORD *)dwContext = &NetDownload::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)(dwContext + 8));
  *(_DWORD *)(dwContext + 48) = 0;
  ManualResetEvent::ManualResetEvent((ManualResetEvent *)(dwContext + 56), 0);
  ManualResetEvent::ManualResetEvent((ManualResetEvent *)(dwContext + 64), 0);
  *(_DWORD *)(dwContext + 72) = 0;
  *(_DWORD *)(dwContext + 76) = -2147483638;
  *(_QWORD *)(dwContext + 80) = &RefCountedArrayImpl::empty_;
  _InterlockedIncrement((volatile signed __int32 *)&RefCountedArrayImpl::empty_);
  *(_QWORD *)(dwContext + 88) = 0;
  *(_QWORD *)(dwContext + 96) = 0;
  if ( a6 )
    v17 = *a6;
  else
    v17 = 0;
  *(_OWORD *)(dwContext + 104) = v17;
  *(_QWORD *)(dwContext + 120) = 0;
  *(_QWORD *)(dwContext + 128) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2);
  *(_QWORD *)(dwContext + 136) = a3;
  AddReference<NetConnection>(a3);
  v11 = (HINTERNET *)(dwContext + 144);
  *(_QWORD *)(dwContext + 144) = 0;
  lplpszAcceptTypes = (LPCWSTR *)&NetParams::defaultAcceptTypes_;
  if ( *(_QWORD *)(a2 + 56) )
    lplpszAcceptTypes = 0;
  if ( *(_QWORD *)(a2 + 24) )
  {
    lpszReferrer = (const WCHAR *)(a2 + 8);
    if ( *((_QWORD *)lpszReferrer + 3) > 7u )
      lpszReferrer = *(const WCHAR **)lpszReferrer;
  }
  else
  {
    lpszReferrer = 0;
  }
  if ( *((_QWORD *)lpszObjectName + 3) > 7u )
    v10 = *(const WCHAR **)lpszObjectName;
  *(_QWORD *)&v17 = HttpOpenRequestW(*(HINTERNET *)(a3 + 56), 0, v10, 0, lpszReferrer, lplpszAcceptTypes, a4, dwContext);
  ScopedHandle<NetHandlePolicy,void *>::operator=(dwContext + 144, &v17);
  ScopedHandle<NetHandlePolicy,void *>::~ScopedHandle<NetHandlePolicy,void *>(&v17);
  v14 = *v11;
  if ( !*v11 || (Buffer = 1, !InternetSetOptionW(v14, 0x41u, &Buffer, 4u)) )
    OSException::ThrowLastError();
  InternetSetStatusCallbackW(*v11, NetDownload::StatusCallback);
  return dwContext;
}

```

## disassembly

```asm
0x18020fb44  push    rbx
0x18020fb46  push    rbp
0x18020fb47  push    rsi
0x18020fb48  push    rdi
0x18020fb49  push    r14
0x18020fb4b  push    r15
0x18020fb4d  sub     rsp, 68h
0x18020fb51  mov     r15d, r9d
0x18020fb54  mov     rbp, r8
0x18020fb57  mov     rdi, rdx
0x18020fb5a  mov     rbx, rcx
0x18020fb5d  mov     r14, [rsp+98h+lpszObjectName]
0x18020fb65  mov     [rsp+98h+var_40], rcx
0x18020fb6a  lea     rax, ??_7NetDownload@@6B@; const NetDownload::`vftable'
0x18020fb71  mov     [rcx], rax
0x18020fb74  add     rcx, 8; lpCriticalSection
0x18020fb78  call    cs:__imp_InitializeCriticalSection
0x18020fb7e  nop
0x18020fb7f  mov     dword ptr [rbx+30h], 0
0x18020fb86  lea     rcx, [rbx+38h]; this
0x18020fb8a  xor     edx, edx; bool
0x18020fb8c  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x18020fb91  nop
0x18020fb92  lea     rcx, [rbx+40h]; this
0x18020fb96  xor     edx, edx; bool
0x18020fb98  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x18020fb9d  nop
0x18020fb9e  mov     dword ptr [rbx+48h], 0
0x18020fba5  mov     dword ptr [rbx+4Ch], 8000000Ah
0x18020fbac  lea     rax, ?empty_@RefCountedArrayImpl@@1UData@1@A; RefCountedArrayImpl::Data RefCountedArrayImpl::empty_
0x18020fbb3  mov     [rbx+50h], rax
0x18020fbb7  lock inc cs:?empty_@RefCountedArrayImpl@@1UData@1@A; RefCountedArrayImpl::Data RefCountedArrayImpl::empty_
0x18020fbbe  mov     qword ptr [rbx+58h], 0
0x18020fbc6  mov     qword ptr [rbx+60h], 0
0x18020fbce  mov     rax, [rsp+98h+arg_28]
0x18020fbd6  test    rax, rax
0x18020fbd9  jz      short loc_18020FBE6
0x18020fbdb  movups  xmm0, xmmword ptr [rax]
0x18020fbde  movdqu  [rsp+98h+var_50], xmm0
0x18020fbe4  jmp     short loc_18020FBEE
0x18020fbe6  xorps   xmm0, xmm0
0x18020fbe9  movups  [rsp+98h+var_50], xmm0
0x18020fbee  lea     rax, [rsp+98h+var_50]
0x18020fbf3  movups  xmm0, xmmword ptr [rax]
0x18020fbf6  movdqu  xmmword ptr [rbx+68h], xmm0
0x18020fbfb  mov     qword ptr [rbx+78h], 0
0x18020fc03  mov     [rbx+80h], rdi
0x18020fc0a  test    rdi, rdi
0x18020fc0d  jz      short loc_18020FC12
0x18020fc0f  lock inc dword ptr [rdi]
0x18020fc12  mov     [rbx+88h], rbp
0x18020fc19  mov     rcx, rbp
0x18020fc1c  call    ??$AddReference@VNetConnection@@@@YAXPEAVNetConnection@@@Z; AddReference<NetConnection>(NetConnection *)
0x18020fc21  nop
0x18020fc22  lea     rsi, [rbx+90h]
0x18020fc29  mov     qword ptr [rsi], 0
0x18020fc30  lea     rcx, ?defaultAcceptTypes_@NetParams@@0PAPEB_WA; wchar_t const * near * NetParams::defaultAcceptTypes_
0x18020fc37  xor     eax, eax
0x18020fc39  cmp     [rdi+38h], rax
0x18020fc3d  cmovnz  rcx, rax
0x18020fc41  cmp     [rdi+18h], rax
0x18020fc45  jnz     short loc_18020FC4B
0x18020fc47  xor     edi, edi
0x18020fc49  jmp     short loc_18020FC59
0x18020fc4b  add     rdi, 8
0x18020fc4f  cmp     qword ptr [rdi+18h], 7
0x18020fc54  jbe     short loc_18020FC59
0x18020fc56  mov     rdi, [rdi]
0x18020fc59  cmp     qword ptr [r14+18h], 7
0x18020fc5e  jbe     short loc_18020FC63
0x18020fc60  mov     r14, [r14]
0x18020fc63  mov     [rsp+98h+dwContext], rbx; dwContext
0x18020fc68  mov     [rsp+98h+dwFlags], r15d; dwFlags
0x18020fc6d  mov     [rsp+98h+lplpszAcceptTypes], rcx; lplpszAcceptTypes
0x18020fc72  mov     [rsp+98h+lpszReferrer], rdi; lpszReferrer
0x18020fc77  xor     r9d, r9d; lpszVersion
0x18020fc7a  mov     r8, r14; lpszObjectName
0x18020fc7d  xor     edx, edx; lpszVerb
0x18020fc7f  mov     rcx, [rbp+38h]; hConnect
0x18020fc83  call    cs:__imp_HttpOpenRequestW
0x18020fc89  mov     qword ptr [rsp+98h+var_50], rax
0x18020fc8e  lea     rdx, [rsp+98h+var_50]
0x18020fc93  mov     rcx, rsi
0x18020fc96  call    ??4?$ScopedHandle@UNetHandlePolicy@@PEAX@@QEAAAEAV0@$$QEAV0@@Z; ScopedHandle<NetHandlePolicy,void *>::operator=(ScopedHandle<NetHandlePolicy,void *> &&)
0x18020fc9b  lea     rcx, [rsp+98h+var_50]
0x18020fca0  call    ??1?$ScopedHandle@UNetHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<NetHandlePolicy,void *>::~ScopedHandle<NetHandlePolicy,void *>(void)
0x18020fca5  mov     rcx, [rsi]; hInternet
0x18020fca8  test    rcx, rcx
0x18020fcab  jz      short loc_18020FCEF
0x18020fcad  mov     [rsp+98h+Buffer], 1
0x18020fcb5  mov     r9d, 4; dwBufferLength
0x18020fcbb  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x18020fcc0  lea     edx, [r9+3Dh]; dwOption
0x18020fcc4  call    cs:__imp_InternetSetOptionW
0x18020fcca  test    eax, eax
0x18020fccc  jz      short loc_18020FCEF
0x18020fcce  lea     rdx, ?StatusCallback@NetDownload@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18020fcd5  mov     rcx, [rsi]; hInternet
0x18020fcd8  call    cs:__imp_InternetSetStatusCallbackW
0x18020fcde  nop
0x18020fcdf  mov     rax, rbx
0x18020fce2  add     rsp, 68h
0x18020fce6  pop     r15
0x18020fce8  pop     r14
0x18020fcea  pop     rdi
0x18020fceb  pop     rsi
0x18020fcec  pop     rbp
0x18020fced  pop     rbx
0x18020fcee  retn
0x18020fcef  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
