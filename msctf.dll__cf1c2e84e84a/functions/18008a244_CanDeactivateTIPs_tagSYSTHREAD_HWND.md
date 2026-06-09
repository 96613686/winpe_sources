# CanDeactivateTIPs(tagSYSTHREAD *,HWND__ *)

- ea: `0x18008a244`
- end: `0x18008a30c`
- name: `?CanDeactivateTIPs@@YAHPEAUtagSYSTHREAD@@PEAUHWND__@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct tagSYSTHREAD *, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180080540`

## callees

- `0x18008a244`
- `0x18008a314`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008a2a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008a2a2`
- `USER32!EnumThreadWindows` at `0x18008a2fb`
- `USER32!EnumThreadWindows` at `0x18008a2fb`
- `USER32!GetFocus` at `0x18008a287`
- `USER32!GetFocus` at `0x18008a287`
- `USER32!GetParent` at `0x18008a2b9`
- `USER32!GetParent` at `0x18008a2b9`
- `USER32!GetWindowThreadProcessId` at `0x18008a29a`
- `USER32!GetWindowThreadProcessId` at `0x18008a29a`

## pseudocode

```c
_BOOL8 __fastcall CanDeactivateTIPs(struct tagSYSTHREAD *a1, HWND a2)
{
  __int64 v4; // rcx
  HWND Focus; // rax
  HWND Parent; // rdi
  DWORD WindowThreadProcessId; // ebx
  DWORD v9; // ecx
  LPARAM lParam[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]

  if ( (*((_BYTE *)a1 + 192) & 1) != 0 )
    return 0;
  v4 = *(_QWORD *)a1;
  if ( !v4 || (*(_DWORD *)(v4 + 3668) & 0x200) != 0 )
    return 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58999946>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_58999946>::GetImpl'::`2'::impl) )
    return 1;
  Focus = GetFocus();
  Parent = Focus;
  if ( !Focus )
    goto LABEL_12;
  WindowThreadProcessId = GetWindowThreadProcessId(Focus, 0);
  if ( GetCurrentThreadId() != WindowThreadProcessId )
    goto LABEL_12;
  if ( !a2 )
    return 0;
  while ( Parent != a2 )
  {
    Parent = GetParent(Parent);
    if ( !Parent )
      return 0;
  }
LABEL_12:
  v9 = *((_DWORD *)a1 + 26);
  lParam[1] = *((_QWORD *)a1 + 17);
  v11 = 0;
  lParam[0] = (LPARAM)a2;
  EnumThreadWindows(v9, CheckVisibleWindowEnumProc, (LPARAM)lParam);
  return (_DWORD)v11 == 0;
}

```

## disassembly

```asm
0x18008a244  push    rbx
0x18008a246  push    rbp
0x18008a247  push    rsi
0x18008a248  push    rdi
0x18008a249  sub     rsp, 48h
0x18008a24d  test    byte ptr [rcx+0C0h], 1
0x18008a254  mov     rbp, rdx
0x18008a257  mov     rsi, rcx
0x18008a25a  jnz     short loc_18008A2C7
0x18008a25c  mov     rcx, [rcx]
0x18008a25f  test    rcx, rcx
0x18008a262  jz      short loc_18008A2C7
0x18008a264  test    dword ptr [rcx+0E54h], 200h
0x18008a26e  jnz     short loc_18008A2C7
0x18008a270  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_58999946@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58999946@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58999946> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_58999946>::GetImpl(void)'::`2'::impl
0x18008a277  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58999946@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58999946>::__private_IsEnabled(void)
0x18008a27c  test    al, al
0x18008a27e  jz      short loc_18008A287
0x18008a280  mov     eax, 1
0x18008a285  jmp     short loc_18008A2C9
0x18008a287  call    cs:__imp_GetFocus
0x18008a28d  mov     rdi, rax
0x18008a290  test    rax, rax
0x18008a293  jz      short loc_18008A2D2
0x18008a295  xor     edx, edx; lpdwProcessId
0x18008a297  mov     rcx, rax; hWnd
0x18008a29a  call    cs:__imp_GetWindowThreadProcessId
0x18008a2a0  mov     ebx, eax
0x18008a2a2  call    cs:__imp_GetCurrentThreadId
0x18008a2a8  cmp     eax, ebx
0x18008a2aa  jnz     short loc_18008A2D2
0x18008a2ac  test    rbp, rbp
0x18008a2af  jz      short loc_18008A2C7
0x18008a2b1  cmp     rdi, rbp
0x18008a2b4  jz      short loc_18008A2D2
0x18008a2b6  mov     rcx, rdi; hWnd
0x18008a2b9  call    cs:__imp_GetParent
0x18008a2bf  mov     rdi, rax
0x18008a2c2  test    rax, rax
0x18008a2c5  jnz     short loc_18008A2B1
0x18008a2c7  xor     eax, eax
0x18008a2c9  add     rsp, 48h
0x18008a2cd  pop     rdi
0x18008a2ce  pop     rsi
0x18008a2cf  pop     rbp
0x18008a2d0  pop     rbx
0x18008a2d1  retn
0x18008a2d2  mov     rax, [rsi+88h]
0x18008a2d9  lea     r8, [rsp+68h+lParam]; lParam
0x18008a2de  mov     ecx, [rsi+68h]; dwThreadId
0x18008a2e1  lea     rdx, ?CheckVisibleWindowEnumProc@@YAHPEAUHWND__@@_J@Z; lpfn
0x18008a2e8  mov     [rsp+68h+var_40], rax
0x18008a2ed  mov     [rsp+68h+var_38], 0
0x18008a2f6  mov     [rsp+68h+lParam], rbp
0x18008a2fb  call    cs:__imp_EnumThreadWindows
0x18008a301  xor     eax, eax
0x18008a303  cmp     dword ptr [rsp+68h+var_38], eax
0x18008a307  setz    al
0x18008a30a  jmp     short loc_18008A2C9
```
