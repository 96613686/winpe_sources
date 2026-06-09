# CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)

- ea: `0x18003f848`
- end: `0x18003f891`
- name: `?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `73`
- prototype: `int(CCompRC *__hidden this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f4dc`

## callees

- `0x18002a7c8`
- `0x18003f848`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003f871`
- `KERNEL32!LoadLibraryExW` at `0x18003f871`

## string_xrefs

- `0x18003f856`: `mscorrc.dll`

## pseudocode

```c
__int64 __fastcall CCompRC::LoadResourceFile(CCompRC *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  bool v4; // zf
  DWORD v6; // r8d
  HMODULE Library; // rax

  v4 = *((_QWORD *)this + 26) == (_QWORD)L"mscorrc.dll";
  v6 = 2;
  if ( !v4 )
    v6 = 0;
  Library = LoadLibraryExW(a3, 0, v6);
  *a2 = Library;
  if ( Library )
    return 0;
  else
    return HRESULT_FROM_GetLastError();
}

```

## disassembly

```asm
0x18003f848  push    rbx
0x18003f84a  sub     rsp, 20h
0x18003f84e  xor     eax, eax
0x18003f850  mov     r9, r8
0x18003f853  mov     rbx, rdx
0x18003f856  lea     rdx, aMscorrcDll; "mscorrc.dll"
0x18003f85d  cmp     [rcx+0D0h], rdx
0x18003f864  mov     rcx, r9; lpLibFileName
0x18003f867  lea     r8d, [rax+2]
0x18003f86b  cmovnz  r8d, eax; dwFlags
0x18003f86f  xor     edx, edx; hFile
0x18003f871  call    cs:__imp_LoadLibraryExW
0x18003f877  mov     [rbx], rax
0x18003f87a  test    rax, rax
0x18003f87d  jnz     short loc_18003F889
0x18003f87f  add     rsp, 20h
0x18003f883  pop     rbx
0x18003f884  jmp     ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18003f889  xor     eax, eax
0x18003f88b  add     rsp, 20h
0x18003f88f  pop     rbx
0x18003f890  retn
```
