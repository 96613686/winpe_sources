# UtilLoadLibraryExWrapper

- ea: `0x18002134c`
- end: `0x180021443`
- name: `UtilLoadLibraryExWrapper`
- size: `247`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004814`
- `0x18000c2f0`
- `0x18000c368`
- `0x18000c4a8`

## callees

- `0x180007014`
- `0x180021224`
- `0x18002134c`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800213b8`
- `msvcrt!_wcsnicmp` at `0x1800213b8`
- `msvcrt!wcschr` at `0x18002139a`
- `msvcrt!wcschr` at `0x18002139a`
- `KERNEL32!GetLastError` at `0x180021380`
- `KERNEL32!GetLastError` at `0x180021380`
- `KERNEL32!SetLastError` at `0x18002141e`
- `KERNEL32!SetLastError` at `0x18002141e`

## string_xrefs

- `0x1800213ae`: `\system32\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilLoadLibraryExWrapper(unsigned __int16 *a1)
{
  __int64 Library; // rsi
  const wchar_t *i; // rbx
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  unsigned __int64 v6; // rax
  signed __int64 v7; // rbx
  WCHAR LibFileName[8]; // [rsp+20h] [rbp-448h] BYREF
  _DWORD v10[256]; // [rsp+30h] [rbp-438h]

  Library = IsolationAwareLoadLibraryExW(a1);
  if ( !Library && GetLastError() == 2 )
  {
    for ( i = a1; ; i = v5 + 1 )
    {
      v4 = wcschr(i, 0x5Cu);
      v5 = v4;
      if ( !v4 )
        break;
      if ( !_wcsnicmp(v4, L"\\system32\\", 0xAu) )
      {
        v6 = -1;
        do
          ++v6;
        while ( a1[v6] );
        if ( v6 < 0x208 && !StringCchCopyW(LibFileName, 0x208u, a1) )
        {
          v7 = (char *)v5 - (char *)a1;
          *(_OWORD *)((char *)LibFileName + v7) = *(_OWORD *)L"\\syswow64\\";
          *(_DWORD *)((char *)v10 + v7) = *(_DWORD *)L"4\\";
          Library = IsolationAwareLoadLibraryExW(LibFileName);
          if ( !Library )
            SetLastError(2u);
        }
        return Library;
      }
    }
  }
  return Library;
}

```

## disassembly

```asm
0x18002134c  push    rbx
0x18002134e  push    rbp
0x18002134f  push    rsi
0x180021350  push    rdi
0x180021351  sub     rsp, 448h
0x180021358  mov     rax, cs:__security_cookie
0x18002135f  xor     rax, rsp
0x180021362  mov     [rsp+468h+var_38], rax
0x18002136a  mov     rdi, rcx
0x18002136d  call    IsolationAwareLoadLibraryExW
0x180021372  xor     ebp, ebp
0x180021374  mov     rsi, rax
0x180021377  test    rax, rax
0x18002137a  jnz     loc_180021424
0x180021380  call    cs:__imp_GetLastError
0x180021386  cmp     eax, 2
0x180021389  jnz     loc_180021424
0x18002138f  mov     rbx, rdi
0x180021392  mov     edx, 5Ch ; '\'; Ch
0x180021397  mov     rcx, rbx; Str
0x18002139a  call    cs:__imp_wcschr
0x1800213a0  mov     rbx, rax
0x1800213a3  test    rax, rax
0x1800213a6  jz      short loc_180021424
0x1800213a8  mov     r8d, 0Ah; MaxCount
0x1800213ae  lea     rdx, aSystem32; "\\system32\\"
0x1800213b5  mov     rcx, rax; String1
0x1800213b8  call    cs:__imp__wcsnicmp
0x1800213be  test    eax, eax
0x1800213c0  jz      short loc_1800213C8
0x1800213c2  add     rbx, 2
0x1800213c6  jmp     short loc_180021392
0x1800213c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800213cc  inc     rax
0x1800213cf  cmp     [rdi+rax*2], bp
0x1800213d3  jnz     short loc_1800213CC
0x1800213d5  mov     edx, 208h; unsigned __int64
0x1800213da  cmp     rax, rdx
0x1800213dd  jnb     short loc_180021424
0x1800213df  mov     r8, rdi; unsigned __int16 *
0x1800213e2  lea     rcx, [rsp+468h+LibFileName]; unsigned __int16 *
0x1800213e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800213ec  test    eax, eax
0x1800213ee  jnz     short loc_180021424
0x1800213f0  movups  xmm0, xmmword ptr cs:aSyswow64; "\\syswow64\\"
0x1800213f7  mov     eax, dword ptr cs:aSyswow64+10h; "4\\"
0x1800213fd  lea     rcx, [rsp+468h+LibFileName]; lpLibFileName
0x180021402  sub     rbx, rdi
0x180021405  movups  xmmword ptr [rsp+rbx+468h+LibFileName], xmm0
0x18002140a  mov     [rsp+rbx+468h+var_438], eax
0x18002140e  call    IsolationAwareLoadLibraryExW
0x180021413  mov     rsi, rax
0x180021416  test    rax, rax
0x180021419  jnz     short loc_180021424
0x18002141b  lea     ecx, [rax+2]; dwErrCode
0x18002141e  call    cs:__imp_SetLastError
0x180021424  mov     rax, rsi
0x180021427  mov     rcx, [rsp+468h+var_38]
0x18002142f  xor     rcx, rsp; StackCookie
0x180021432  call    __security_check_cookie
0x180021437  add     rsp, 448h
0x18002143e  pop     rdi
0x18002143f  pop     rsi
0x180021440  pop     rbp
0x180021441  pop     rbx
0x180021442  retn
```
