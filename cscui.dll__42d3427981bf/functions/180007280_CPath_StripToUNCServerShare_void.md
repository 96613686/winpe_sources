# CPath::StripToUNCServerShare(void)

- ea: `0x180007280`
- end: `0x18000732d`
- name: `?StripToUNCServerShare@CPath@@QEAAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(CPath *__hidden this)`
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001e430`
- `0x180022134`
- `0x180024e70`
- `0x1800251a0`
- `0x180025ba4`
- `0x18003e540`
- `0x18003fadc`
- `0x18003fc84`
- `0x18003ff70`
- `0x180041028`

## callees

- `0x1800065a0`
- `0x180007280`
- `0x18000735c`
- `0x180032b44`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x1800072a9`
- `SHLWAPI!PathIsUNCW` at `0x1800072a9`
- `SHLWAPI!PathIsUNCServerShareW` at `0x1800072e8`
- `SHLWAPI!PathIsUNCServerShareW` at `0x1800072e8`
- `SHLWAPI!PathIsUNCServerW` at `0x1800072c0`
- `SHLWAPI!PathIsUNCServerW` at `0x1800072c0`

## pseudocode

```c
__int64 __fastcall CPath::StripToUNCServerShare(CPath *this)
{
  const WCHAR *v2; // rcx
  const WCHAR *ConstBuffer; // rax
  __int64 result; // rax
  _WORD *v5; // rdi
  const WCHAR *v6; // rax
  bool v7; // zf

  v2 = (const WCHAR *)*((_QWORD *)this + 67);
  if ( v2 == *((const WCHAR **)this + 68) )
    v2 = (const WCHAR *)*((_QWORD *)this + 66);
  if ( !PathIsUNCW(v2) )
    return 2147500037LL;
  ConstBuffer = CPath::_GetConstBuffer(this);
  if ( PathIsUNCServerW(ConstBuffer) )
    return 2147500037LL;
  result = CPath::RemoveBackslash(this);
  if ( (int)result >= 0 )
  {
    v5 = (_WORD *)((char *)this + 520);
    while ( 1 )
    {
      v6 = CPath::_GetConstBuffer(this);
      if ( PathIsUNCServerShareW(v6) )
        break;
      v5 = (_WORD *)((char *)this + 520);
      result = 1;
      v7 = *((_WORD *)this + 260) == 0;
      if ( !*((_WORD *)this + 260) )
        goto LABEL_12;
      result = CPath::RemoveFileSpecAndBackslash(this);
      if ( (int)result < 0 )
        return result;
    }
    v7 = *v5 == 0;
    result = 0;
LABEL_12:
    if ( v7 )
      return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007280  mov     [rsp+arg_0], rbx
0x180007285  mov     [rsp+arg_8], rsi
0x18000728a  push    rdi
0x18000728b  sub     rsp, 20h
0x18000728f  mov     rbx, rcx
0x180007292  mov     rcx, [rcx+218h]
0x180007299  cmp     rcx, [rbx+220h]
0x1800072a0  jnz     short loc_1800072A9
0x1800072a2  mov     rcx, [rbx+210h]; pszPath
0x1800072a9  call    cs:__imp_PathIsUNCW
0x1800072af  xor     esi, esi
0x1800072b1  test    eax, eax
0x1800072b3  jz      short loc_180007318
0x1800072b5  mov     rcx, rbx; this
0x1800072b8  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800072bd  mov     rcx, rax; pszPath
0x1800072c0  call    cs:__imp_PathIsUNCServerW
0x1800072c6  test    eax, eax
0x1800072c8  jnz     short loc_180007318
0x1800072ca  mov     rcx, rbx; this
0x1800072cd  call    ?RemoveBackslash@CPath@@QEAAJXZ; CPath::RemoveBackslash(void)
0x1800072d2  test    eax, eax
0x1800072d4  js      short loc_18000731D
0x1800072d6  lea     rdi, [rbx+208h]
0x1800072dd  mov     rcx, rbx; this
0x1800072e0  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800072e5  mov     rcx, rax; pszPath
0x1800072e8  call    cs:__imp_PathIsUNCServerShareW
0x1800072ee  test    eax, eax
0x1800072f0  jnz     short loc_180007311
0x1800072f2  lea     rdi, [rbx+208h]
0x1800072f9  mov     eax, 1
0x1800072fe  cmp     [rdi], si
0x180007301  jbe     short loc_180007316
0x180007303  mov     rcx, rbx; this
0x180007306  call    ?RemoveFileSpecAndBackslash@CPath@@QEAAJXZ; CPath::RemoveFileSpecAndBackslash(void)
0x18000730b  test    eax, eax
0x18000730d  jns     short loc_1800072DD
0x18000730f  jmp     short loc_18000731D
0x180007311  cmp     [rdi], si
0x180007314  mov     eax, esi
0x180007316  jnz     short loc_18000731D
0x180007318  mov     eax, 80004005h
0x18000731d  mov     rbx, [rsp+28h+arg_0]
0x180007322  mov     rsi, [rsp+28h+arg_8]
0x180007327  add     rsp, 20h
0x18000732b  pop     rdi
0x18000732c  retn
```
