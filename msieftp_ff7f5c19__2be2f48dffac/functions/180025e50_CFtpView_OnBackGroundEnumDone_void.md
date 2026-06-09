# CFtpView::_OnBackGroundEnumDone(void)

- ea: `0x180025e50`
- end: `0x180025f0a`
- name: `?_OnBackGroundEnumDone@CFtpView@@MEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(CFtpView *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180025e50`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180025ef2`
- `SHELL32!__imp_ILFree` at `0x180025ef2`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180025eb9`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180025eb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e92`

## pseudocode

```c
__int64 __fastcall CFtpView::_OnBackGroundEnumDone(CFtpView *this)
{
  HRESULT v1; // esi
  ITEMIDLIST *v3; // rdi
  IUnknown *v4; // rcx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( *((_QWORD *)this + 15) )
  {
    v3 = 0;
    EnterCriticalSection(&g_csDll);
    if ( *((_QWORD *)this + 15) )
    {
      v3 = (ITEMIDLIST *)*((_QWORD *)this + 15);
      *((_QWORD *)this + 15) = 0;
    }
    LeaveCriticalSection(&g_csDll);
    if ( v3 )
    {
      v4 = (IUnknown *)*((_QWORD *)this + 2);
      ppvOut = 0;
      v1 = IUnknown_QueryService(
             v4,
             (const GUID *const)&SID_SCommDlgBrowser,
             &GUID_000214e2_0000_0000_c000_000000000046,
             &ppvOut);
      if ( v1 >= 0 )
      {
        v1 = (*(__int64 (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(ppvOut, v3, 0);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
      ILFree(v3);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180025e50  mov     [rsp+arg_8], rbx
0x180025e55  mov     [rsp+arg_10], rsi
0x180025e5a  push    rdi
0x180025e5b  sub     rsp, 20h
0x180025e5f  xor     esi, esi
0x180025e61  mov     rbx, rcx
0x180025e64  cmp     [rcx+78h], rsi
0x180025e68  jz      loc_180025EF8
0x180025e6e  lea     rcx, g_csDll; lpCriticalSection
0x180025e75  xor     edi, edi
0x180025e77  call    cs:__imp_EnterCriticalSection
0x180025e7d  cmp     [rbx+78h], rsi
0x180025e81  jz      short loc_180025E8B
0x180025e83  mov     rdi, [rbx+78h]
0x180025e87  mov     [rbx+78h], rsi
0x180025e8b  lea     rcx, g_csDll; lpCriticalSection
0x180025e92  call    cs:__imp_LeaveCriticalSection
0x180025e98  test    rdi, rdi
0x180025e9b  jz      short loc_180025EF8
0x180025e9d  mov     rcx, [rbx+10h]; punk
0x180025ea1  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180025ea6  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180025ead  mov     [rsp+28h+ppvOut], rsi
0x180025eb2  lea     rdx, SID_SCommDlgBrowser; guidService
0x180025eb9  call    cs:__imp_IUnknown_QueryService
0x180025ebf  mov     esi, eax
0x180025ec1  test    eax, eax
0x180025ec3  js      short loc_180025EEF
0x180025ec5  mov     rcx, [rsp+28h+ppvOut]
0x180025eca  xor     r8d, r8d
0x180025ecd  mov     rdx, rdi
0x180025ed0  mov     rax, [rcx]
0x180025ed3  mov     rax, [rax+58h]
0x180025ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025edc  mov     rcx, [rsp+28h+ppvOut]
0x180025ee1  mov     esi, eax
0x180025ee3  mov     rax, [rcx]
0x180025ee6  mov     rax, [rax+10h]
0x180025eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eef  mov     rcx, rdi; pidl
0x180025ef2  call    cs:__imp_ILFree
0x180025ef8  mov     rbx, [rsp+28h+arg_8]
0x180025efd  mov     eax, esi
0x180025eff  mov     rsi, [rsp+28h+arg_10]
0x180025f04  add     rsp, 20h
0x180025f08  pop     rdi
0x180025f09  retn
```
