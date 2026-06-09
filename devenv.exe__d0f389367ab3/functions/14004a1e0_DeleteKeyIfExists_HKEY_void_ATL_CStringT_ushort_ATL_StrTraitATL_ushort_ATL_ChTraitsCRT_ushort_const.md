# DeleteKeyIfExists(HKEY__ *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14004a1e0`
- end: `0x14004a251`
- name: `?DeleteKeyIfExists@@YAJPEAUHKEY__@@PEAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(HKEY hkey, HANDLE hToken)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004772c`
- `0x14004c3d0`
- `0x14004c560`
- `0x140051c20`
- `0x14005215c`
- `0x140052388`

## callees

- `0x14004a1e0`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004a1f8`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004a1f8`
- `ADVAPI32!RevertToSelf` at `0x14004a239`
- `ADVAPI32!RevertToSelf` at `0x14004a239`
- `SHLWAPI!SHDeleteKeyW` at `0x14004a206`
- `SHLWAPI!SHDeleteKeyW` at `0x14004a206`

## pseudocode

```c
__int64 __fastcall DeleteKeyIfExists(HKEY hkey, HANDLE hToken, LPCWSTR *a3)
{
  BOOL v5; // esi
  LSTATUS v6; // eax
  unsigned int v7; // ebx

  v5 = ImpersonateLoggedOnUser(hToken);
  v6 = SHDeleteKeyW(hkey, *a3);
  if ( v6 )
  {
    if ( (unsigned int)(v6 - 2) < 2 )
    {
      v7 = 1;
    }
    else
    {
      v7 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v7 = v6;
    }
  }
  else
  {
    v7 = 0;
  }
  if ( v5 )
    RevertToSelf();
  return v7;
}

```

## disassembly

```asm
0x14004a1e0  mov     [rsp+arg_0], rbx
0x14004a1e5  mov     [rsp+arg_8], rsi
0x14004a1ea  push    rdi
0x14004a1eb  sub     rsp, 20h
0x14004a1ef  mov     rbx, rcx
0x14004a1f2  mov     rdi, r8
0x14004a1f5  mov     rcx, rdx; hToken
0x14004a1f8  call    cs:__imp_ImpersonateLoggedOnUser
0x14004a1fe  mov     rdx, [rdi]; pszSubKey
0x14004a201  mov     rcx, rbx; hkey
0x14004a204  mov     esi, eax
0x14004a206  call    cs:__imp_SHDeleteKeyW
0x14004a20c  mov     edx, eax
0x14004a20e  test    eax, eax
0x14004a210  jz      short loc_14004A233
0x14004a212  sub     edx, 2
0x14004a215  jz      short loc_14004A22C
0x14004a217  cmp     edx, 1
0x14004a21a  jz      short loc_14004A22C
0x14004a21c  movzx   ebx, ax
0x14004a21f  or      ebx, 80070000h
0x14004a225  test    eax, eax
0x14004a227  cmovle  ebx, eax
0x14004a22a  jmp     short loc_14004A235
0x14004a22c  mov     ebx, 1
0x14004a231  jmp     short loc_14004A235
0x14004a233  xor     ebx, ebx
0x14004a235  test    esi, esi
0x14004a237  jz      short loc_14004A23F
0x14004a239  call    cs:__imp_RevertToSelf
0x14004a23f  mov     rsi, [rsp+28h+arg_8]
0x14004a244  mov     eax, ebx
0x14004a246  mov     rbx, [rsp+28h+arg_0]
0x14004a24b  add     rsp, 20h
0x14004a24f  pop     rdi
0x14004a250  retn
```
