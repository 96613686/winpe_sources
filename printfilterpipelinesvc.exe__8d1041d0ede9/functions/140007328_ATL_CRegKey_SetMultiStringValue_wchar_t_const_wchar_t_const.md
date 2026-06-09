# ATL::CRegKey::SetMultiStringValue(wchar_t const *,wchar_t const *)

- ea: `0x140007328`
- end: `0x1400073c5`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEB_W0@Z`
- size: `157`
- prototype: `int(ATL::CRegKey *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004b9c`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140007328`
- `0x140045c74`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1400073a6`
- `ADVAPI32!RegSetValueExW` at `0x1400073a6`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetMultiStringValue(HKEY *this, const wchar_t *a2, const BYTE *a3)
{
  const BYTE *lpData; // r9
  DWORD cbData; // r10d
  __int64 v6; // rcx
  __int64 v7; // rcx
  _BYTE pExceptionObject[160]; // [rsp+30h] [rbp-B8h] BYREF

  lpData = a3;
  if ( !a3 )
  {
    SplException::TAtlException::TAtlException(
      (SplException::TAtlException *)pExceptionObject,
      (const char *)a2,
      0,
      0x80004005);
    throw (SplException::TAtlException *)pExceptionObject;
  }
  cbData = 0;
  do
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
    v7 = (unsigned int)(v6 + 1);
    a3 += 2 * v7;
    cbData += 2 * v7;
  }
  while ( (_DWORD)v7 != 1 );
  return RegSetValueExW(*this, a2, 0, 7u, lpData, cbData);
}

```

## disassembly

```asm
0x140007328  push    rbx
0x14000732a  sub     rsp, 0E0h
0x140007331  mov     rax, cs:__security_cookie
0x140007338  xor     rax, rsp
0x14000733b  mov     [rsp+0E8h+var_18], rax
0x140007343  xor     ebx, ebx
0x140007345  mov     r9, r8
0x140007348  mov     r11, rcx
0x14000734b  test    r8, r8
0x14000734e  jnz     short loc_140007372
0x140007350  mov     r9d, 80004005h; unsigned int
0x140007356  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x14000735b  call    ??0TAtlException@SplException@@QEAA@PEBDKK@Z; SplException::TAtlException::TAtlException(char const *,ulong,ulong)
0x140007360  lea     rdx, _TI3?AVTAtlException@SplException@@; pThrowInfo
0x140007367  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x14000736c  call    _CxxThrowException_0
0x140007372  mov     r10d, ebx
0x140007375  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140007379  inc     rcx
0x14000737c  cmp     [r8+rcx*2], bx
0x140007381  jnz     short loc_140007379
0x140007383  inc     ecx
0x140007385  lea     r8, [r8+rcx*2]
0x140007389  lea     r10d, [r10+rcx*2]
0x14000738d  cmp     ecx, 1
0x140007390  jnz     short loc_140007375
0x140007392  mov     [rsp+0E8h+cbData], r10d; cbData
0x140007397  xor     r8d, r8d; Reserved
0x14000739a  mov     [rsp+0E8h+lpData], r9; lpData
0x14000739f  lea     r9d, [rcx+6]; dwType
0x1400073a3  mov     rcx, [r11]; hKey
0x1400073a6  call    cs:__imp_RegSetValueExW
0x1400073ac  mov     rcx, [rsp+0E8h+var_18]
0x1400073b4  xor     rcx, rsp; StackCookie
0x1400073b7  call    __security_check_cookie
0x1400073bc  add     rsp, 0E0h
0x1400073c3  pop     rbx
0x1400073c4  retn
```
