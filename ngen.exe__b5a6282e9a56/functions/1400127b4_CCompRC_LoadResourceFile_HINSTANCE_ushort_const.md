# CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)

- ea: `0x1400127b4`
- end: `0x14001281b`
- name: `?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(CCompRC *this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001281c`

## callees

- `0x1400127b4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1400127de`
- `KERNEL32!LoadLibraryExW` at `0x1400127de`
- `KERNEL32!GetLastError` at `0x1400127ec`
- `KERNEL32!GetLastError` at `0x1400127ec`

## string_xrefs

- `0x1400127c6`: `mscorrc.dll`

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
0x1400127b4  mov     [rsp+arg_0], rbx
0x1400127b9  push    rdi
0x1400127ba  sub     rsp, 20h
0x1400127be  mov     rax, r8
0x1400127c1  xor     edi, edi
0x1400127c3  mov     rbx, rdx
0x1400127c6  lea     rdx, aMscorrcDll; "mscorrc.dll"
0x1400127cd  cmp     [rcx+30h], rdx
0x1400127d1  mov     rcx, rax; lpLibFileName
0x1400127d4  lea     r8d, [rdi+2]
0x1400127d8  cmovnz  r8d, edi; dwFlags
0x1400127dc  xor     edx, edx; hFile
0x1400127de  call    cs:__imp_LoadLibraryExW
0x1400127e4  mov     [rbx], rax
0x1400127e7  test    rax, rax
0x1400127ea  jnz     short loc_14001280E
0x1400127ec  call    cs:__imp_GetLastError
0x1400127f2  mov     ecx, eax
0x1400127f4  test    eax, eax
0x1400127f6  jnz     short loc_1400127FF
0x1400127f8  mov     eax, 80004005h
0x1400127fd  jmp     short loc_140012810
0x1400127ff  movzx   eax, cx
0x140012802  or      eax, 80070000h
0x140012807  test    ecx, ecx
0x140012809  cmovle  eax, ecx
0x14001280c  jmp     short loc_140012810
0x14001280e  xor     eax, eax
0x140012810  mov     rbx, [rsp+28h+arg_0]
0x140012815  add     rsp, 20h
0x140012819  pop     rdi
0x14001281a  retn
```
