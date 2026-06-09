# EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(IThirdPartyEapDispatcherPeerRuntime *,ObjectHandle const &,void * &)

- ea: `0x18002848c`
- end: `0x18002866b`
- name: `?DupImpersonationHanle@ThirdPartyEapMethodRuntime@Peer@EapLm@@AEAAXPEAUIThirdPartyEapDispatcherPeerRuntime@@AEBVObjectHandle@@AEAPEAX@Z`
- size: `479`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, struct IThirdPartyEapDispatcherPeerRuntime *, const struct ObjectHandle *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800280d0`
- `0x1800287c0`

## callees

- `0x1800122d8`
- `0x1800154c8`
- `0x18002848c`
- `0x1800294d4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002857e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002857e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002864d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002864d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800285a8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800285a8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002855b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002855b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        struct IThirdPartyEapDispatcherPeerRuntime *a2,
        const struct ObjectHandle *a3,
        void **a4)
{
  signed int LastError; // eax
  HANDLE v9; // rsi
  void *v10; // rbx
  HANDLE CurrentProcess; // rax
  signed int v12; // eax
  signed int v13; // eax
  void **v14; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-11h]
  int v16; // [rsp+58h] [rbp-1h]
  void **v17; // [rsp+60h] [rbp+7h] BYREF
  char v18; // [rsp+68h] [rbp+Fh]
  __int64 v19; // [rsp+6Ch] [rbp+13h]
  int v20; // [rsp+78h] [rbp+1Fh]
  DWORD dwProcessId; // [rsp+C8h] [rbp+6Fh] BYREF

  dwProcessId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)a3 + 1));
  if ( (*(int (__fastcall **)(struct IThirdPartyEapDispatcherPeerRuntime *, DWORD *))(*(_QWORD *)a2 + 24LL))(
         a2,
         &dwProcessId) < 0 )
  {
    LOBYTE(v15[0]) = *((_BYTE *)this + 16);
    HIDWORD(v15[0]) = *((_DWORD *)this + 5);
    LODWORD(v15[1]) = *((_DWORD *)this + 6);
    if ( LOBYTE(v15[0]) != 0xFE )
      *(_QWORD *)((char *)v15 + 4) = 0;
    v14 = &EapHost::EapMethodType::`vftable';
    v16 = *((_DWORD *)this + 7);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    EapHost::EapException::Throw(LastError, (const struct EapHost::EapMethodType *)&v14);
  }
  v14 = &ObjectHandle::`vftable';
  v15[0] = 0;
  v9 = OpenProcess(0x40u, 0, dwProcessId);
  ObjectHandle::Clear((ObjectHandle *)&v14);
  v15[0] = v9;
  if ( !v9 )
  {
    v18 = *((_BYTE *)this + 16);
    v19 = *(_QWORD *)((char *)this + 20);
    if ( v18 != -2 )
      v19 = 0;
    v17 = &EapHost::EapMethodType::`vftable';
    v20 = *((_DWORD *)this + 7);
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    EapHost::EapException::Throw(v13, (const struct EapHost::EapMethodType *)&v17);
  }
  v10 = (void *)*((_QWORD *)a3 + 1);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v10, v9, a4, 0, 1, 2u) )
  {
    v18 = *((_BYTE *)this + 16);
    v19 = *(_QWORD *)((char *)this + 20);
    if ( v18 != -2 )
      v19 = 0;
    v17 = &EapHost::EapMethodType::`vftable';
    v20 = *((_DWORD *)this + 7);
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    EapHost::EapException::Throw(v12, (const struct EapHost::EapMethodType *)&v17);
  }
  v14 = &ObjectHandle::`vftable';
  ObjectHandle::Clear((ObjectHandle *)&v14);
}

```

## disassembly

```asm
0x18002848c  push    rbp
0x18002848e  push    rbx
0x18002848f  push    rsi
0x180028490  push    rdi
0x180028491  push    r12
0x180028493  push    r14
0x180028495  lea     rbp, [rsp-2Fh]
0x18002849a  sub     rsp, 88h
0x1800284a1  mov     r14, r9
0x1800284a4  mov     rbx, r8
0x1800284a7  mov     rsi, rdx
0x1800284aa  mov     rdi, rcx
0x1800284ad  mov     [rbp+57h+dwProcessId], 0
0x1800284b4  lea     rax, WPP_GLOBAL_Control
0x1800284bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284c2  cmp     rcx, rax
0x1800284c5  jz      short loc_1800284DA
0x1800284c7  test    byte ptr [rcx+1Ch], 4
0x1800284cb  jz      short loc_1800284DA
0x1800284cd  mov     r9, [r8+8]
0x1800284d1  mov     rcx, [rcx+10h]
0x1800284d5  call    WPP_SF_q
0x1800284da  mov     rax, [rsi]
0x1800284dd  lea     rdx, [rbp+57h+dwProcessId]
0x1800284e1  mov     rcx, rsi
0x1800284e4  mov     rax, [rax+18h]
0x1800284e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284ed  test    eax, eax
0x1800284ef  jns     short loc_18002853F
0x1800284f1  mov     cl, [rdi+10h]
0x1800284f4  mov     [rbp+57h+var_68], cl
0x1800284f7  mov     eax, [rdi+14h]
0x1800284fa  mov     dword ptr [rbp+57h+var_68+4], eax
0x1800284fd  mov     eax, [rdi+18h]
0x180028500  mov     dword ptr [rbp+57h+var_68+8], eax
0x180028503  cmp     cl, 0FEh
0x180028506  jz      short loc_180028510
0x180028508  mov     qword ptr [rbp+57h+var_68+4], 0
0x180028510  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180028517  mov     [rbp+57h+var_70], rax
0x18002851b  mov     eax, [rdi+1Ch]
0x18002851e  mov     [rbp+57h+var_58], eax
0x180028521  call    cs:__imp_GetLastError
0x180028527  test    eax, eax
0x180028529  jle     short loc_180028533
0x18002852b  movzx   eax, ax
0x18002852e  or      eax, 80070000h
0x180028533  lea     rdx, [rbp+57h+var_70]; struct EapHost::EapMethodType *
0x180028537  mov     ecx, eax; unsigned int
0x180028539  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
0x18002853f  lea     r12, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180028546  mov     [rbp+57h+var_70], r12
0x18002854a  mov     qword ptr [rbp+57h+var_68], 0
0x180028552  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x180028556  xor     edx, edx; bInheritHandle
0x180028558  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18002855b  call    cs:__imp_OpenProcess
0x180028561  mov     rsi, rax
0x180028564  lea     rcx, [rbp+57h+var_70]; this
0x180028568  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18002856d  mov     qword ptr [rbp+57h+var_68], rsi
0x180028571  test    rsi, rsi
0x180028574  jz      loc_18002861D
0x18002857a  mov     rbx, [rbx+8]
0x18002857e  call    cs:__imp_GetCurrentProcess
0x180028584  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x18002858c  mov     [rsp+0B0h+bInheritHandle], 1; bInheritHandle
0x180028594  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x18002859c  mov     r9, r14; lpTargetHandle
0x18002859f  mov     r8, rsi; hTargetProcessHandle
0x1800285a2  mov     rdx, rbx; hSourceHandle
0x1800285a5  mov     rcx, rax; hSourceProcessHandle
0x1800285a8  call    cs:__imp_DuplicateHandle
0x1800285ae  test    eax, eax
0x1800285b0  jnz     short loc_180028600
0x1800285b2  mov     cl, [rdi+10h]
0x1800285b5  mov     [rbp+57h+var_48], cl
0x1800285b8  mov     eax, [rdi+14h]
0x1800285bb  mov     dword ptr [rbp+57h+var_44], eax
0x1800285be  mov     eax, [rdi+18h]
0x1800285c1  mov     dword ptr [rbp+57h+var_44+4], eax
0x1800285c4  cmp     cl, 0FEh
0x1800285c7  jz      short loc_1800285D1
0x1800285c9  mov     [rbp+57h+var_44], 0
0x1800285d1  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800285d8  mov     [rbp+57h+var_50], rax
0x1800285dc  mov     eax, [rdi+1Ch]
0x1800285df  mov     [rbp+57h+var_38], eax
0x1800285e2  call    cs:__imp_GetLastError
0x1800285e8  test    eax, eax
0x1800285ea  jle     short loc_1800285F4
0x1800285ec  movzx   eax, ax
0x1800285ef  or      eax, 80070000h
0x1800285f4  lea     rdx, [rbp+57h+var_50]; struct EapHost::EapMethodType *
0x1800285f8  mov     ecx, eax; unsigned int
0x1800285fa  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
0x180028600  mov     [rbp+57h+var_70], r12
0x180028604  lea     rcx, [rbp+57h+var_70]; this
0x180028608  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18002860d  add     rsp, 88h
0x180028614  pop     r14
0x180028616  pop     r12
0x180028618  pop     rdi
0x180028619  pop     rsi
0x18002861a  pop     rbx
0x18002861b  pop     rbp
0x18002861c  retn
0x18002861d  mov     cl, [rdi+10h]
0x180028620  mov     [rbp+57h+var_48], cl
0x180028623  mov     eax, [rdi+14h]
0x180028626  mov     dword ptr [rbp+57h+var_44], eax
0x180028629  mov     eax, [rdi+18h]
0x18002862c  mov     dword ptr [rbp+57h+var_44+4], eax
0x18002862f  cmp     cl, 0FEh
0x180028632  jz      short loc_18002863C
0x180028634  mov     [rbp+57h+var_44], 0
0x18002863c  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180028643  mov     [rbp+57h+var_50], rax
0x180028647  mov     eax, [rdi+1Ch]
0x18002864a  mov     [rbp+57h+var_38], eax
0x18002864d  call    cs:__imp_GetLastError
0x180028653  test    eax, eax
0x180028655  jle     short loc_18002865F
0x180028657  movzx   eax, ax
0x18002865a  or      eax, 80070000h
0x18002865f  lea     rdx, [rbp+57h+var_50]; struct EapHost::EapMethodType *
0x180028663  mov     ecx, eax; unsigned int
0x180028665  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
```
