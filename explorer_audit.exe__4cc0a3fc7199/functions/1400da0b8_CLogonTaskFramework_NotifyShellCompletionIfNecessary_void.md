# CLogonTaskFramework::NotifyShellCompletionIfNecessary(void)

- ea: `0x1400da0b8`
- end: `0x1400da27e`
- name: `?NotifyShellCompletionIfNecessary@CLogonTaskFramework@@QEAAXXZ`
- size: `454`
- prototype: `void __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000f5a8`
- `0x14014f184`
- `0x14019fbd8`

## callees

- `0x14000edcc`
- `0x140016b10`
- `0x14001eba8`
- `0x140030c1c`
- `0x14007d124`
- `0x14007fde8`
- `0x140082398`
- `0x1400da0b8`
- `0x1401db010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1400da21b`
- `ntdll!RtlPublishWnfStateData` at `0x1400da239`
- `ntdll!RtlPublishWnfStateData` at `0x1400da21b`
- `ntdll!RtlPublishWnfStateData` at `0x1400da239`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400da0ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400da0ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400da0d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400da0d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400da1f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400da1f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400da154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400da154`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400da149`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400da149`
- `SHELL32!__imp_SHCreateSessionKey` at `0x1400da10f`
- `SHELL32!__imp_SHCreateSessionKey` at `0x1400da10f`
- `api-ms-win-core-biplmapi-l1-1-4!BiNotifyNewSessionComplete` at `0x1400da23f`
- `api-ms-win-core-biplmapi-l1-1-4!BiNotifyNewSessionComplete` at `0x1400da23f`

## string_xrefs

- `0x1400da11a`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLogonTaskFramework::NotifyShellCompletionIfNecessary(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  char Ptr; // si
  int v4; // eax
  int v5; // eax
  PVOID v6; // rbx
  unsigned int Error; // eax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v11; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v2 = this + 4;
  AcquireSRWLockExclusive(this + 4);
  Ptr = (char)this[29].Ptr;
  LOBYTE(this[29].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  if ( !Ptr )
  {
    hKey = 0;
    v4 = SHCreateSessionKey(131078, &hKey);
    if ( v4 >= 0 )
    {
      RegDeleteKeyExW(hKey, L"FSIAInProgress", 0, 0);
      RegCloseKey(hKey);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x325D,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v4,
        v9);
    }
    v11 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
    if ( (int)CLogonTaskFramework::s_QueryServiceImmersiveShell(
                (const struct _GUID *)&SID_ImmersiveLauncher,
                &GUID_d8d60399_a0f1_f987_5551_321fd1b49864,
                &v11) >= 0
      && IsOnUserDesktop() )
    {
      v5 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v11 + 96LL))(v11);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x326A,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v5,
          v9);
    }
    CLogonTaskFramework::s_PostTrayMessage(0x5BDu, 0, 0);
    v6 = this[6].Ptr;
    Error = ResultFromKnownLastError();
    if ( v6 )
      SetEvent(this[6].Ptr);
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3273,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)Error,
        v9);
    if ( !BYTE4(this[29].Ptr) )
    {
      RtlPublishWnfStateData(WNF_SHEL_LOGON_COMPLETE, 0, 0, 0);
      v9 = 0;
      RtlPublishWnfStateData(WNF_SHEL_SESSION_LOGON_COMPLETE, 0, 0, 0);
    }
    v8 = BiNotifyNewSessionComplete();
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3289,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v8,
        v9);
    Windows::Shell::CImmersiveCursor::DisableCursorSuppression();
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  }
}

```

## disassembly

```asm
0x1400da0b8  mov     [rsp+arg_10], rbx
0x1400da0bd  mov     [rsp+arg_18], rsi
0x1400da0c2  push    rdi
0x1400da0c3  sub     rsp, 30h
0x1400da0c7  mov     rdi, rcx
0x1400da0ca  lea     rbx, [rcx+20h]
0x1400da0ce  mov     rcx, rbx; SRWLock
0x1400da0d1  call    cs:__imp_AcquireSRWLockExclusive
0x1400da0d7  mov     sil, [rdi+0E8h]
0x1400da0de  mov     byte ptr [rdi+0E8h], 1
0x1400da0e5  test    rbx, rbx
0x1400da0e8  jz      short loc_1400DA0F3
0x1400da0ea  mov     rcx, rbx; SRWLock
0x1400da0ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1400da0f3  test    sil, sil
0x1400da0f6  jnz     loc_1400DA26E
0x1400da0fc  mov     [rsp+38h+hKey], 0
0x1400da105  lea     rdx, [rsp+38h+hKey]
0x1400da10a  mov     ecx, 20006h
0x1400da10f  call    cs:__imp_SHCreateSessionKey
0x1400da115  mov     rcx, [rsp+38h]; this
0x1400da11a  lea     rsi, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400da121  test    eax, eax
0x1400da123  jns     short loc_1400DA137
0x1400da125  mov     r9d, eax; char *
0x1400da128  mov     r8, rsi; unsigned int
0x1400da12b  mov     edx, 325Dh; void *
0x1400da130  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400da135  jmp     short loc_1400DA15A
0x1400da137  xor     r9d, r9d; Reserved
0x1400da13a  xor     r8d, r8d; samDesired
0x1400da13d  lea     rdx, aFsiainprogress; "FSIAInProgress"
0x1400da144  mov     rcx, [rsp+38h+hKey]; hKey
0x1400da149  call    cs:__imp_RegDeleteKeyExW
0x1400da14f  mov     rcx, [rsp+38h+hKey]; hKey
0x1400da154  call    cs:__imp_RegCloseKey
0x1400da15a  mov     [rsp+38h+arg_0], 0
0x1400da163  lea     rcx, [rsp+38h+arg_0]
0x1400da168  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400da16d  lea     r8, [rsp+38h+arg_0]; void **
0x1400da172  lea     rdx, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864; struct _GUID *
0x1400da179  lea     rcx, SID_ImmersiveLauncher; struct _GUID *
0x1400da180  call    ?s_QueryServiceImmersiveShell@CLogonTaskFramework@@CAJAEBU_GUID@@0PEAPEAX@Z; CLogonTaskFramework::s_QueryServiceImmersiveShell(_GUID const &,_GUID const &,void * *)
0x1400da185  test    eax, eax
0x1400da187  js      short loc_1400DA1BC
0x1400da189  call    ?IsOnUserDesktop@@YA_NXZ; IsOnUserDesktop(void)
0x1400da18e  test    al, al
0x1400da190  jz      short loc_1400DA1BC
0x1400da192  mov     rcx, [rsp+38h+arg_0]
0x1400da197  mov     rax, [rcx]
0x1400da19a  mov     rax, [rax+60h]
0x1400da19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400da1a3  mov     rcx, [rsp+38h]; this
0x1400da1a8  test    eax, eax
0x1400da1aa  jns     short loc_1400DA1BC
0x1400da1ac  mov     r9d, eax; char *
0x1400da1af  mov     r8, rsi; unsigned int
0x1400da1b2  mov     edx, 326Ah; void *
0x1400da1b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400da1bc  xor     r8d, r8d; lParam
0x1400da1bf  xor     edx, edx; wParam
0x1400da1c1  mov     ecx, 5BDh; Msg
0x1400da1c6  call    ?s_PostTrayMessage@CLogonTaskFramework@@CAXI_K_J@Z; CLogonTaskFramework::s_PostTrayMessage(uint,unsigned __int64,__int64)
0x1400da1cb  mov     rbx, [rdi+30h]
0x1400da1cf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400da1d4  mov     rcx, [rsp+38h]; this
0x1400da1d9  test    rbx, rbx
0x1400da1dc  jnz     short loc_1400DA1F0
0x1400da1de  mov     r9d, eax; char *
0x1400da1e1  mov     r8, rsi; unsigned int
0x1400da1e4  mov     edx, 3273h; void *
0x1400da1e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400da1ee  jmp     short loc_1400DA1FA
0x1400da1f0  mov     rcx, [rdi+30h]; hEvent
0x1400da1f4  call    cs:__imp_SetEvent
0x1400da1fa  cmp     byte ptr [rdi+0ECh], 0
0x1400da201  jnz     short loc_1400DA23F
0x1400da203  mov     qword ptr [rsp+38h+var_18], 0
0x1400da20c  xor     r9d, r9d
0x1400da20f  xor     r8d, r8d
0x1400da212  xor     edx, edx
0x1400da214  mov     rcx, cs:WNF_SHEL_LOGON_COMPLETE
0x1400da21b  call    cs:__imp_RtlPublishWnfStateData
0x1400da221  mov     qword ptr [rsp+38h+var_18], 0; int
0x1400da22a  xor     r9d, r9d
0x1400da22d  xor     r8d, r8d
0x1400da230  xor     edx, edx
0x1400da232  mov     rcx, cs:WNF_SHEL_SESSION_LOGON_COMPLETE
0x1400da239  call    cs:__imp_RtlPublishWnfStateData
0x1400da23f  call    cs:__imp_BiNotifyNewSessionComplete
0x1400da245  mov     rcx, [rsp+38h]; this
0x1400da24a  test    eax, eax
0x1400da24c  jns     short loc_1400DA25E
0x1400da24e  mov     r9d, eax; char *
0x1400da251  mov     r8, rsi; unsigned int
0x1400da254  mov     edx, 3289h; void *
0x1400da259  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400da25e  call    ?DisableCursorSuppression@CImmersiveCursor@Shell@Windows@@SAXXZ; Windows::Shell::CImmersiveCursor::DisableCursorSuppression(void)
0x1400da263  nop
0x1400da264  lea     rcx, [rsp+38h+arg_0]
0x1400da269  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400da26e  mov     rbx, [rsp+38h+arg_10]
0x1400da273  mov     rsi, [rsp+38h+arg_18]
0x1400da278  add     rsp, 30h
0x1400da27c  pop     rdi
0x1400da27d  retn
```
