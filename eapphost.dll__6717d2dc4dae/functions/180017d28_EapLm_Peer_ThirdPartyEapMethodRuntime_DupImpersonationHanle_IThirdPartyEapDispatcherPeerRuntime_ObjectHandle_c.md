# EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(IThirdPartyEapDispatcherPeerRuntime *,ObjectHandle const &,void * &)

- ea: `0x180017d28`
- end: `0x180017eda`
- name: `?DupImpersonationHanle@ThirdPartyEapMethodRuntime@Peer@EapLm@@AEAAXPEAUIThirdPartyEapDispatcherPeerRuntime@@AEBVObjectHandle@@AEAPEAX@Z`
- size: `434`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, struct IThirdPartyEapDispatcherPeerRuntime *, const struct ObjectHandle *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180017930`
- `0x180018020`

## callees

- `0x1800049d8`
- `0x180017d28`
- `0x180018d90`
- `0x18001dc24`
- `0x18002f1f4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017e0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017eb9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017e35`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017e35`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017de8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017de8`

## pseudocode

```c
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        struct IThirdPartyEapDispatcherPeerRuntime *a2,
        const struct ObjectHandle *a3,
        void **a4)
{
  __int64 v8; // rdx
  signed int LastError; // eax
  HANDLE v10; // rsi
  void *v11; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v13; // rdx
  signed int v14; // eax
  __int64 v15; // rdx
  signed int v16; // eax
  void **v17; // [rsp+40h] [rbp-19h] BYREF
  HANDLE v18; // [rsp+48h] [rbp-11h]
  int v19; // [rsp+58h] [rbp-1h]
  _QWORD v20[3]; // [rsp+60h] [rbp+7h] BYREF
  int v21; // [rsp+78h] [rbp+1Fh]
  DWORD dwProcessId; // [rsp+C8h] [rbp+6Fh] BYREF

  dwProcessId = 0;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)a3 + 1));
  }
  if ( (*(int (__fastcall **)(struct IThirdPartyEapDispatcherPeerRuntime *, DWORD *))(*(_QWORD *)a2 + 24LL))(
         a2,
         &dwProcessId) < 0 )
  {
    EapHost::EapType::EapType((EapHost::EapType *)&v17, (const struct _EAP_TYPE *)((char *)this + 16));
    v17 = &EapHost::EapMethodType::`vftable';
    v19 = *(_DWORD *)(v8 + 12);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    EapHost::EapException::Throw(LastError, (const struct EapHost::EapMethodType *)&v17, LastError);
  }
  v17 = &ObjectHandle::`vftable';
  v18 = 0;
  v10 = OpenProcess(0x40u, 0, dwProcessId);
  ObjectHandle::Clear((ObjectHandle *)&v17);
  v18 = v10;
  if ( !v10 )
  {
    EapHost::EapType::EapType((EapHost::EapType *)v20, (const struct _EAP_TYPE *)((char *)this + 16));
    v20[0] = &EapHost::EapMethodType::`vftable';
    v21 = *(_DWORD *)(v15 + 12);
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    EapHost::EapException::Throw(v16, (const struct EapHost::EapMethodType *)v20, v16);
  }
  v11 = (void *)*((_QWORD *)a3 + 1);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v11, v10, a4, 0, 1, 2u) )
  {
    EapHost::EapType::EapType((EapHost::EapType *)v20, (const struct _EAP_TYPE *)((char *)this + 16));
    v20[0] = &EapHost::EapMethodType::`vftable';
    v21 = *(_DWORD *)(v13 + 12);
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    EapHost::EapException::Throw(v14, (const struct EapHost::EapMethodType *)v20, v14);
  }
  v17 = &ObjectHandle::`vftable';
  ObjectHandle::Clear((ObjectHandle *)&v17);
}

```

## disassembly

```asm
0x180017d28  push    rbp
0x180017d2a  push    rbx
0x180017d2b  push    rsi
0x180017d2c  push    rdi
0x180017d2d  push    r12
0x180017d2f  push    r14
0x180017d31  lea     rbp, [rsp-2Fh]
0x180017d36  sub     rsp, 88h
0x180017d3d  mov     r14, r9
0x180017d40  mov     rbx, r8
0x180017d43  mov     rsi, rdx
0x180017d46  mov     rdi, rcx
0x180017d49  mov     [rbp+57h+dwProcessId], 0
0x180017d50  lea     rax, WPP_GLOBAL_Control
0x180017d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d5e  cmp     rcx, rax
0x180017d61  jz      short loc_180017D76
0x180017d63  test    byte ptr [rcx+1Ch], 4
0x180017d67  jz      short loc_180017D76
0x180017d69  mov     r9, [r8+8]
0x180017d6d  mov     rcx, [rcx+10h]
0x180017d71  call    WPP_SF_q
0x180017d76  mov     rax, [rsi]
0x180017d79  lea     rdx, [rbp+57h+dwProcessId]
0x180017d7d  mov     rcx, rsi
0x180017d80  mov     rax, [rax+18h]
0x180017d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d89  test    eax, eax
0x180017d8b  jns     short loc_180017DCC
0x180017d8d  lea     rdx, [rdi+10h]; struct _EAP_TYPE *
0x180017d91  lea     rcx, [rbp+57h+var_70]; this
0x180017d95  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180017d9a  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180017da1  mov     [rbp+57h+var_70], rcx
0x180017da5  mov     eax, [rdx+0Ch]
0x180017da8  mov     [rbp+57h+var_58], eax
0x180017dab  call    cs:__imp_GetLastError
0x180017db1  test    eax, eax
0x180017db3  jle     short loc_180017DBD
0x180017db5  movzx   eax, ax
0x180017db8  or      eax, 80070000h
0x180017dbd  mov     r8d, eax; unsigned int
0x180017dc0  lea     rdx, [rbp+57h+var_70]; struct EapHost::EapMethodType *
0x180017dc4  mov     ecx, eax; unsigned int
0x180017dc6  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180017dcc  lea     r12, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180017dd3  mov     [rbp+57h+var_70], r12
0x180017dd7  mov     [rbp+57h+var_68], 0
0x180017ddf  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x180017de3  xor     edx, edx; bInheritHandle
0x180017de5  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180017de8  call    cs:__imp_OpenProcess
0x180017dee  mov     rsi, rax
0x180017df1  lea     rcx, [rbp+57h+var_70]; this
0x180017df5  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180017dfa  mov     [rbp+57h+var_68], rsi
0x180017dfe  test    rsi, rsi
0x180017e01  jz      loc_180017E9B
0x180017e07  mov     rbx, [rbx+8]
0x180017e0b  call    cs:__imp_GetCurrentProcess
0x180017e11  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x180017e19  mov     [rsp+0B0h+bInheritHandle], 1; bInheritHandle
0x180017e21  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x180017e29  mov     r9, r14; lpTargetHandle
0x180017e2c  mov     r8, rsi; hTargetProcessHandle
0x180017e2f  mov     rdx, rbx; hSourceHandle
0x180017e32  mov     rcx, rax; hSourceProcessHandle
0x180017e35  call    cs:__imp_DuplicateHandle
0x180017e3b  test    eax, eax
0x180017e3d  jnz     short loc_180017E7E
0x180017e3f  lea     rdx, [rdi+10h]; struct _EAP_TYPE *
0x180017e43  lea     rcx, [rbp+57h+var_50]; this
0x180017e47  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180017e4c  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180017e53  mov     [rbp+57h+var_50], rcx
0x180017e57  mov     eax, [rdx+0Ch]
0x180017e5a  mov     [rbp+57h+var_38], eax
0x180017e5d  call    cs:__imp_GetLastError
0x180017e63  test    eax, eax
0x180017e65  jle     short loc_180017E6F
0x180017e67  movzx   eax, ax
0x180017e6a  or      eax, 80070000h
0x180017e6f  mov     r8d, eax; unsigned int
0x180017e72  lea     rdx, [rbp+57h+var_50]; struct EapHost::EapMethodType *
0x180017e76  mov     ecx, eax; unsigned int
0x180017e78  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180017e7e  mov     [rbp+57h+var_70], r12
0x180017e82  lea     rcx, [rbp+57h+var_70]; this
0x180017e86  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180017e8b  add     rsp, 88h
0x180017e92  pop     r14
0x180017e94  pop     r12
0x180017e96  pop     rdi
0x180017e97  pop     rsi
0x180017e98  pop     rbx
0x180017e99  pop     rbp
0x180017e9a  retn
0x180017e9b  lea     rdx, [rdi+10h]; struct _EAP_TYPE *
0x180017e9f  lea     rcx, [rbp+57h+var_50]; this
0x180017ea3  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180017ea8  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180017eaf  mov     [rbp+57h+var_50], rcx
0x180017eb3  mov     eax, [rdx+0Ch]
0x180017eb6  mov     [rbp+57h+var_38], eax
0x180017eb9  call    cs:__imp_GetLastError
0x180017ebf  test    eax, eax
0x180017ec1  jle     short loc_180017ECB
0x180017ec3  movzx   eax, ax
0x180017ec6  or      eax, 80070000h
0x180017ecb  mov     r8d, eax; unsigned int
0x180017ece  lea     rdx, [rbp+57h+var_50]; struct EapHost::EapMethodType *
0x180017ed2  mov     ecx, eax; unsigned int
0x180017ed4  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
