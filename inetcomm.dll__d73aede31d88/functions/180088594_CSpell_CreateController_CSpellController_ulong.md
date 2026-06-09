# CSpell::CreateController(CSpellController * *,ulong)

- ea: `0x180088594`
- end: `0x1800887bc`
- name: `?CreateController@CSpell@@AEAAJPEAPEAVCSpellController@@K@Z`
- size: `552`
- prototype: `int(CSpell *__hidden this, struct CSpellController **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180088d08`

## callees

- `0x1800299d0`
- `0x180088594`
- `0x18008bf28`
- `0x18008d950`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z` at `0x180088613`
- `MSOERT2!__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z` at `0x180088633`
- `MSOERT2!__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z` at `0x180088651`
- `MSOERT2!__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z` at `0x180088613`
- `MSOERT2!__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z` at `0x180088633`
- `MSOERT2!__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z` at `0x180088651`
- `SHLWAPI!PathAppendW` at `0x18008866f`
- `SHLWAPI!PathAppendW` at `0x18008868b`
- `SHLWAPI!PathAppendW` at `0x1800886a5`
- `SHLWAPI!PathAppendW` at `0x18008866f`
- `SHLWAPI!PathAppendW` at `0x18008868b`
- `SHLWAPI!PathAppendW` at `0x1800886a5`

## pseudocode

```c
__int64 __fastcall CSpell::CreateController(CSpell *this, struct CSpellController **a2, unsigned int a3)
{
  int StoreRootDirectoryFromRegistryKey; // ebx
  struct CSpellController *v7; // rax
  HINSTANCE v8; // r8
  struct ITextContext **v9; // rdi
  WCHAR v11[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v12[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR pszPath[264]; // [rsp+460h] [rbp+360h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(v12, 0, 0x208u);
  memset_0(v11, 0, 0x208u);
  StoreRootDirectoryFromRegistryKey = GetStoreRootDirectoryFromRegistryKey(HKEY_CURRENT_USER, pszPath, 0x104u);
  if ( StoreRootDirectoryFromRegistryKey < 0
    || (StoreRootDirectoryFromRegistryKey = GetStoreRootDirectoryFromRegistryKey(HKEY_CURRENT_USER, v12, 0x104u),
        StoreRootDirectoryFromRegistryKey < 0)
    || (StoreRootDirectoryFromRegistryKey = GetStoreRootDirectoryFromRegistryKey(HKEY_CURRENT_USER, v11, 0x104u),
        StoreRootDirectoryFromRegistryKey < 0) )
  {
LABEL_15:
    if ( *a2 )
    {
      (**(void (__fastcall ***)(_QWORD, __int64))*a2)(*a2, 1);
      *a2 = 0;
    }
    return (unsigned int)StoreRootDirectoryFromRegistryKey;
  }
  if ( !PathAppendW(pszPath, L"UserDictionary.lex")
    || !PathAppendW(v12, L"UserDictionary_IgnoreSession.lex")
    || !PathAppendW(v11, L"UserDictionary_ChangeSession.lex") )
  {
    return (unsigned int)StoreRootDirectoryFromRegistryKey;
  }
  v7 = (struct CSpellController *)operator new(0x30u);
  if ( !v7 )
  {
    *a2 = 0;
    StoreRootDirectoryFromRegistryKey = -2147467259;
    goto LABEL_15;
  }
  *(_QWORD *)v7 = &CSpellController::`vftable';
  _InterlockedIncrement(&g_cRef);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 3) = CSpell_SelectWordCallback;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 4) = this;
  *a2 = v7;
  StoreRootDirectoryFromRegistryKey = CSpellController::Setup(
                                        v7,
                                        *((HWND *)this + 12),
                                        v8,
                                        a3,
                                        *((_DWORD *)this + 27),
                                        pszPath,
                                        v12,
                                        v11);
  if ( StoreRootDirectoryFromRegistryKey < 0 )
    goto LABEL_15;
  StoreRootDirectoryFromRegistryKey = -2147467259;
  v9 = (struct ITextContext **)*((_QWORD *)*a2 + 1);
  if ( v9 )
  {
    StoreRootDirectoryFromRegistryKey = CUserDictionary::ClearDictionary(v9[4], v9[1]);
    if ( StoreRootDirectoryFromRegistryKey >= 0 )
      StoreRootDirectoryFromRegistryKey = CUserDictionary::ClearDictionary(v9[5], v9[1]);
  }
  if ( StoreRootDirectoryFromRegistryKey < 0 )
    goto LABEL_15;
  return (unsigned int)StoreRootDirectoryFromRegistryKey;
}

```

## disassembly

```asm
0x180088594  push    rbp
0x180088596  push    rbx
0x180088597  push    rsi
0x180088598  push    rdi
0x180088599  push    r13
0x18008859b  push    r14
0x18008859d  lea     rbp, [rsp-588h]
0x1800885a5  sub     rsp, 688h
0x1800885ac  mov     rax, cs:__security_cookie
0x1800885b3  xor     rax, rsp
0x1800885b6  mov     [rbp+5B0h+var_40], rax
0x1800885bd  mov     r14d, r8d
0x1800885c0  mov     rsi, rdx
0x1800885c3  mov     rdi, rcx
0x1800885c6  mov     ebx, 208h
0x1800885cb  mov     r8d, ebx; Size
0x1800885ce  lea     rcx, [rbp+5B0h+pszPath]; void *
0x1800885d5  xor     edx, edx; Val
0x1800885d7  call    memset_0
0x1800885dc  mov     r8d, ebx; Size
0x1800885df  lea     rcx, [rbp+5B0h+var_460]; void *
0x1800885e6  xor     edx, edx; Val
0x1800885e8  call    memset_0
0x1800885ed  mov     r8d, ebx; Size
0x1800885f0  lea     rcx, [rsp+6B0h+var_670]; void *
0x1800885f5  xor     edx, edx; Val
0x1800885f7  call    memset_0
0x1800885fc  mov     r13, 0FFFFFFFF80000001h
0x180088603  lea     rdx, [rbp+5B0h+pszPath]
0x18008860a  mov     rcx, r13
0x18008860d  mov     r8d, 104h
0x180088613  call    cs:__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z; GetStoreRootDirectoryFromRegistryKey(HKEY__ *,ushort *,ulong)
0x180088619  mov     ebx, eax
0x18008861b  test    eax, eax
0x18008861d  js      loc_18008877C
0x180088623  mov     r8d, 104h
0x180088629  lea     rdx, [rbp+5B0h+var_460]
0x180088630  mov     rcx, r13
0x180088633  call    cs:__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z; GetStoreRootDirectoryFromRegistryKey(HKEY__ *,ushort *,ulong)
0x180088639  mov     ebx, eax
0x18008863b  test    eax, eax
0x18008863d  js      loc_18008877C
0x180088643  mov     r8d, 104h
0x180088649  lea     rdx, [rsp+6B0h+var_670]
0x18008864e  mov     rcx, r13
0x180088651  call    cs:__imp_?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z; GetStoreRootDirectoryFromRegistryKey(HKEY__ *,ushort *,ulong)
0x180088657  mov     ebx, eax
0x180088659  test    eax, eax
0x18008865b  js      loc_18008877C
0x180088661  lea     rdx, aUserdictionary_0; "UserDictionary.lex"
0x180088668  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x18008866f  call    cs:__imp_PathAppendW
0x180088675  test    eax, eax
0x180088677  jz      loc_18008879B
0x18008867d  lea     rdx, aUserdictionary; "UserDictionary_IgnoreSession.lex"
0x180088684  lea     rcx, [rbp+5B0h+var_460]; pszPath
0x18008868b  call    cs:__imp_PathAppendW
0x180088691  test    eax, eax
0x180088693  jz      loc_18008879B
0x180088699  lea     rdx, aUserdictionary_1; "UserDictionary_ChangeSession.lex"
0x1800886a0  lea     rcx, [rsp+6B0h+var_670]; pszPath
0x1800886a5  call    cs:__imp_PathAppendW
0x1800886ab  test    eax, eax
0x1800886ad  jz      loc_18008879B
0x1800886b3  mov     ecx, 30h ; '0'; Size
0x1800886b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800886bd  mov     rcx, rax; this
0x1800886c0  test    rax, rax
0x1800886c3  jz      loc_180088770
0x1800886c9  lea     rax, ??_7CSpellController@@6B@; const CSpellController::`vftable'
0x1800886d0  mov     [rcx], rax
0x1800886d3  lock inc cs:?g_cRef@@3JA; long g_cRef
0x1800886da  mov     qword ptr [rcx+8], 0
0x1800886e2  lea     rax, ?CSpell_SelectWordCallback@@YAJPEAX@Z; CSpell_SelectWordCallback(void *)
0x1800886e9  mov     [rcx+18h], rax
0x1800886ed  mov     r9d, r14d; unsigned int
0x1800886f0  mov     qword ptr [rcx+10h], 0
0x1800886f8  lea     rax, [rsp+6B0h+var_670]
0x1800886fd  mov     [rsp+6B0h+var_678], rax; unsigned __int16 *
0x180088702  lea     rax, [rbp+5B0h+var_460]
0x180088709  mov     [rsp+6B0h+var_680], rax; unsigned __int16 *
0x18008870e  lea     rax, [rbp+5B0h+pszPath]
0x180088715  mov     [rcx+20h], rdi
0x180088719  mov     [rsp+6B0h+var_688], rax; unsigned __int16 *
0x18008871e  mov     [rsi], rcx
0x180088721  mov     eax, [rdi+6Ch]
0x180088724  mov     rdx, [rdi+60h]; HWND
0x180088728  mov     [rsp+6B0h+var_690], eax; unsigned int
0x18008872c  call    ?Setup@CSpellController@@QEAAJPEAUHWND__@@PEAUHINSTANCE__@@KKPEBG22@Z; CSpellController::Setup(HWND__ *,HINSTANCE__ *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180088731  mov     ebx, eax
0x180088733  test    eax, eax
0x180088735  js      short loc_18008877C
0x180088737  mov     rax, [rsi]
0x18008873a  mov     ebx, 80004005h
0x18008873f  mov     rdi, [rax+8]
0x180088743  test    rdi, rdi
0x180088746  jz      short loc_18008876A
0x180088748  mov     rdx, [rdi+8]; struct ITextContext *
0x18008874c  mov     rcx, [rdi+20h]; this
0x180088750  call    ?ClearDictionary@CUserDictionary@@QEAAJPEAUITextContext@@@Z; CUserDictionary::ClearDictionary(ITextContext *)
0x180088755  mov     ebx, eax
0x180088757  test    eax, eax
0x180088759  js      short loc_18008876A
0x18008875b  mov     rdx, [rdi+8]; struct ITextContext *
0x18008875f  mov     rcx, [rdi+28h]; this
0x180088763  call    ?ClearDictionary@CUserDictionary@@QEAAJPEAUITextContext@@@Z; CUserDictionary::ClearDictionary(ITextContext *)
0x180088768  mov     ebx, eax
0x18008876a  test    ebx, ebx
0x18008876c  jns     short loc_18008879B
0x18008876e  jmp     short loc_18008877C
0x180088770  mov     qword ptr [rsi], 0
0x180088777  mov     ebx, 80004005h
0x18008877c  mov     rcx, [rsi]
0x18008877f  test    rcx, rcx
0x180088782  jz      short loc_18008879B
0x180088784  mov     rax, [rcx]
0x180088787  mov     edx, 1
0x18008878c  mov     rax, [rax]
0x18008878f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088794  mov     qword ptr [rsi], 0
0x18008879b  mov     eax, ebx
0x18008879d  mov     rcx, [rbp+5B0h+var_40]
0x1800887a4  xor     rcx, rsp; StackCookie
0x1800887a7  call    __security_check_cookie
0x1800887ac  add     rsp, 688h
0x1800887b3  pop     r14
0x1800887b5  pop     r13
0x1800887b7  pop     rdi
0x1800887b8  pop     rsi
0x1800887b9  pop     rbx
0x1800887ba  pop     rbp
0x1800887bb  retn
```
