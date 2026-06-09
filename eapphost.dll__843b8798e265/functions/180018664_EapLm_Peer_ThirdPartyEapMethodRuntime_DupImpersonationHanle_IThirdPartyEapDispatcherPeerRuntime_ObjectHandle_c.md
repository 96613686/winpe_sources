# EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(IThirdPartyEapDispatcherPeerRuntime *,ObjectHandle const &,void * &)

- ea: `0x180018664`
- end: `0x18001883b`
- name: `?DupImpersonationHanle@ThirdPartyEapMethodRuntime@Peer@EapLm@@AEAAXPEAUIThirdPartyEapDispatcherPeerRuntime@@AEBVObjectHandle@@AEAPEAX@Z`
- size: `471`
- prototype: `void(EapLm::Peer::ThirdPartyEapMethodRuntime *__hidden this, struct IThirdPartyEapDispatcherPeerRuntime *, const struct ObjectHandle *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180018250`
- `0x180018990`

## callees

- `0x180004b4c`
- `0x180018664`
- `0x180019740`
- `0x18001e728`
- `0x18003032c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018753`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018814`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018783`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018783`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001872a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001872a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180018664  push    rbp
0x180018666  push    rbx
0x180018667  push    rsi
0x180018668  push    rdi
0x180018669  push    r12
0x18001866b  push    r14
0x18001866d  lea     rbp, [rsp-2Fh]
0x180018672  sub     rsp, 88h
0x180018679  mov     r14, r9
0x18001867c  mov     rbx, r8
0x18001867f  mov     rsi, rdx
0x180018682  mov     rdi, rcx
0x180018685  mov     [rbp+57h+dwProcessId], 0
0x18001868c  lea     rax, WPP_GLOBAL_Control
0x180018693  mov     rcx, cs:WPP_GLOBAL_Control
0x18001869a  cmp     rcx, rax
0x18001869d  jz      short loc_1800186B2
0x18001869f  test    byte ptr [rcx+1Ch], 4
0x1800186a3  jz      short loc_1800186B2
0x1800186a5  mov     r9, [r8+8]
0x1800186a9  mov     rcx, [rcx+10h]
0x1800186ad  call    WPP_SF_q
0x1800186b2  mov     rax, [rsi]
0x1800186b5  lea     rdx, [rbp+57h+dwProcessId]
0x1800186b9  mov     rcx, rsi
0x1800186bc  mov     rax, [rax+18h]
0x1800186c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c5  test    eax, eax
0x1800186c7  jns     short loc_18001870E
0x1800186c9  lea     rdx, [rdi+10h]; struct _EAP_TYPE *
0x1800186cd  lea     rcx, [rbp+57h+var_70]; this
0x1800186d1  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x1800186d6  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800186dd  mov     [rbp+57h+var_70], rcx
0x1800186e1  mov     eax, [rdx+0Ch]
0x1800186e4  mov     [rbp+57h+var_58], eax
0x1800186e7  call    cs:__imp_GetLastError
0x1800186ee  nop     dword ptr [rax+rax+00h]
0x1800186f3  test    eax, eax
0x1800186f5  jle     short loc_1800186FF
0x1800186f7  movzx   eax, ax
0x1800186fa  or      eax, 80070000h
0x1800186ff  mov     r8d, eax; unsigned int
0x180018702  lea     rdx, [rbp+57h+var_70]; struct EapHost::EapMethodType *
0x180018706  mov     ecx, eax; unsigned int
0x180018708  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001870e  lea     r12, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180018715  mov     [rbp+57h+var_70], r12
0x180018719  mov     [rbp+57h+var_68], 0
0x180018721  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x180018725  xor     edx, edx; bInheritHandle
0x180018727  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18001872a  call    cs:__imp_OpenProcess
0x180018731  nop     dword ptr [rax+rax+00h]
0x180018736  mov     rsi, rax
0x180018739  lea     rcx, [rbp+57h+var_70]; this
0x18001873d  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180018742  mov     [rbp+57h+var_68], rsi
0x180018746  test    rsi, rsi
0x180018749  jz      loc_1800187F6
0x18001874f  mov     rbx, [rbx+8]
0x180018753  call    cs:__imp_GetCurrentProcess
0x18001875a  nop     dword ptr [rax+rax+00h]
0x18001875f  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x180018767  mov     [rsp+0B0h+bInheritHandle], 1; bInheritHandle
0x18001876f  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x180018777  mov     r9, r14; lpTargetHandle
0x18001877a  mov     r8, rsi; hTargetProcessHandle
0x18001877d  mov     rdx, rbx; hSourceHandle
0x180018780  mov     rcx, rax; hSourceProcessHandle
0x180018783  call    cs:__imp_DuplicateHandle
0x18001878a  nop     dword ptr [rax+rax+00h]
0x18001878f  test    eax, eax
0x180018791  jnz     short loc_1800187D8
0x180018793  lea     rdx, [rdi+10h]; struct _EAP_TYPE *
0x180018797  lea     rcx, [rbp+57h+var_50]; this
0x18001879b  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x1800187a0  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800187a7  mov     [rbp+57h+var_50], rcx
0x1800187ab  mov     eax, [rdx+0Ch]
0x1800187ae  mov     [rbp+57h+var_38], eax
0x1800187b1  call    cs:__imp_GetLastError
0x1800187b8  nop     dword ptr [rax+rax+00h]
0x1800187bd  test    eax, eax
0x1800187bf  jle     short loc_1800187C9
0x1800187c1  movzx   eax, ax
0x1800187c4  or      eax, 80070000h
0x1800187c9  mov     r8d, eax; unsigned int
0x1800187cc  lea     rdx, [rbp+57h+var_50]; struct EapHost::EapMethodType *
0x1800187d0  mov     ecx, eax; unsigned int
0x1800187d2  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x1800187d8  mov     [rbp+57h+var_70], r12
0x1800187dc  lea     rcx, [rbp+57h+var_70]; this
0x1800187e0  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x1800187e5  add     rsp, 88h
0x1800187ec  pop     r14
0x1800187ee  pop     r12
0x1800187f0  pop     rdi
0x1800187f1  pop     rsi
0x1800187f2  pop     rbx
0x1800187f3  pop     rbp
0x1800187f4  retn
0x1800187f6  lea     rdx, [rdi+10h]; struct _EAP_TYPE *
0x1800187fa  lea     rcx, [rbp+57h+var_50]; this
0x1800187fe  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180018803  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001880a  mov     [rbp+57h+var_50], rcx
0x18001880e  mov     eax, [rdx+0Ch]
0x180018811  mov     [rbp+57h+var_38], eax
0x180018814  call    cs:__imp_GetLastError
0x18001881b  nop     dword ptr [rax+rax+00h]
0x180018820  test    eax, eax
0x180018822  jle     short loc_18001882C
0x180018824  movzx   eax, ax
0x180018827  or      eax, 80070000h
0x18001882c  mov     r8d, eax; unsigned int
0x18001882f  lea     rdx, [rbp+57h+var_50]; struct EapHost::EapMethodType *
0x180018833  mov     ecx, eax; unsigned int
0x180018835  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
