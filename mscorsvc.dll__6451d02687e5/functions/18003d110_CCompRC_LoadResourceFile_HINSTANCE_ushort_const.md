# CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)

- ea: `0x18003d110`
- end: `0x18003d177`
- name: `?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `103`
- prototype: `int(CCompRC *__hidden this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d178`

## callees

- `0x18003d110`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003d13a`
- `KERNEL32!LoadLibraryExW` at `0x18003d13a`
- `KERNEL32!GetLastError` at `0x18003d148`
- `KERNEL32!GetLastError` at `0x18003d148`

## string_xrefs

- `0x18003d122`: `mscorrc.dll`

## pseudocode

```c
__int64 __fastcall CCompRC::LoadResourceFile(CCompRC *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  bool v4; // zf
  DWORD v6; // r8d
  HMODULE Library; // rax
  signed int LastError; // ecx
  __int64 result; // rax

  v4 = *((_QWORD *)this + 6) == (_QWORD)L"mscorrc.dll";
  v6 = 2;
  if ( !v4 )
    v6 = 0;
  Library = LoadLibraryExW(a3, 0, v6);
  *a2 = Library;
  if ( Library )
    return 0;
  LastError = GetLastError();
  if ( !LastError )
    return 2147500037LL;
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x18003d110  mov     [rsp+arg_0], rbx
0x18003d115  push    rdi
0x18003d116  sub     rsp, 20h
0x18003d11a  mov     rax, r8
0x18003d11d  xor     edi, edi
0x18003d11f  mov     rbx, rdx
0x18003d122  lea     rdx, aMscorrcDll; "mscorrc.dll"
0x18003d129  cmp     [rcx+30h], rdx
0x18003d12d  mov     rcx, rax; lpLibFileName
0x18003d130  lea     r8d, [rdi+2]
0x18003d134  cmovnz  r8d, edi; dwFlags
0x18003d138  xor     edx, edx; hFile
0x18003d13a  call    cs:__imp_LoadLibraryExW
0x18003d140  mov     [rbx], rax
0x18003d143  test    rax, rax
0x18003d146  jnz     short loc_18003D16A
0x18003d148  call    cs:__imp_GetLastError
0x18003d14e  mov     ecx, eax
0x18003d150  test    eax, eax
0x18003d152  jnz     short loc_18003D15B
0x18003d154  mov     eax, 80004005h
0x18003d159  jmp     short loc_18003D16C
0x18003d15b  movzx   eax, cx
0x18003d15e  or      eax, 80070000h
0x18003d163  test    ecx, ecx
0x18003d165  cmovle  eax, ecx
0x18003d168  jmp     short loc_18003D16C
0x18003d16a  xor     eax, eax
0x18003d16c  mov     rbx, [rsp+28h+arg_0]
0x18003d171  add     rsp, 20h
0x18003d175  pop     rdi
0x18003d176  retn
```
