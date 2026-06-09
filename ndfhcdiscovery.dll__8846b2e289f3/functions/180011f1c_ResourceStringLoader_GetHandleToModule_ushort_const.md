# ResourceStringLoader::GetHandleToModule(ushort const *)

- ea: `0x180011f1c`
- end: `0x180011fc4`
- name: `?GetHandleToModule@ResourceStringLoader@@AEAAPEAUHINSTANCE__@@PEBG@Z`
- size: `168`
- prototype: `HINSTANCE(ResourceStringLoader *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011fcc`

## callees

- `0x180011f1c`
- `0x180013686`
- `0x1800136b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011f9b`
- `KERNEL32!SetLastError` at `0x180011f9b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180011f5a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180011f5a`
- `KERNEL32!GetLastError` at `0x180011f8d`
- `KERNEL32!GetLastError` at `0x180011f8d`
- `KERNEL32!LoadLibraryExW` at `0x180011f79`
- `KERNEL32!LoadLibraryExW` at `0x180011f79`

## pseudocode

```c
HINSTANCE __fastcall ResourceStringLoader::GetHandleToModule(ResourceStringLoader *this, const unsigned __int16 *a2)
{
  HMODULE Library; // rbx
  DWORD LastError; // eax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(a2, Dst, 0x104u) )
  {
    Library = 0;
LABEL_4:
    LastError = GetLastError();
    SetLastError(LastError);
    return Library;
  }
  Library = LoadLibraryExW(Dst, 0, 0x22u);
  if ( !Library )
    goto LABEL_4;
  return Library;
}

```

## disassembly

```asm
0x180011f1c  push    rbx
0x180011f1e  sub     rsp, 240h
0x180011f25  mov     rax, cs:__security_cookie
0x180011f2c  xor     rax, rsp
0x180011f2f  mov     [rsp+248h+var_18], rax
0x180011f37  mov     rbx, rdx
0x180011f3a  lea     rcx, [rsp+248h+Dst]; void *
0x180011f3f  xor     edx, edx; Val
0x180011f41  mov     r8d, 208h; Size
0x180011f47  call    memset_0
0x180011f4c  mov     r8d, 104h; nSize
0x180011f52  lea     rdx, [rsp+248h+Dst]; lpDst
0x180011f57  mov     rcx, rbx; lpSrc
0x180011f5a  call    cs:__imp_ExpandEnvironmentStringsW
0x180011f61  nop     dword ptr [rax+rax+00h]
0x180011f66  test    eax, eax
0x180011f68  jnz     short loc_180011F6E
0x180011f6a  xor     ebx, ebx
0x180011f6c  jmp     short loc_180011F8D
0x180011f6e  xor     edx, edx; hFile
0x180011f70  lea     rcx, [rsp+248h+Dst]; lpLibFileName
0x180011f75  lea     r8d, [rdx+22h]; dwFlags
0x180011f79  call    cs:__imp_LoadLibraryExW
0x180011f80  nop     dword ptr [rax+rax+00h]
0x180011f85  mov     rbx, rax
0x180011f88  test    rax, rax
0x180011f8b  jnz     short loc_180011FA7
0x180011f8d  call    cs:__imp_GetLastError
0x180011f94  nop     dword ptr [rax+rax+00h]
0x180011f99  mov     ecx, eax; dwErrCode
0x180011f9b  call    cs:__imp_SetLastError
0x180011fa2  nop     dword ptr [rax+rax+00h]
0x180011fa7  mov     rax, rbx
0x180011faa  mov     rcx, [rsp+248h+var_18]
0x180011fb2  xor     rcx, rsp; StackCookie
0x180011fb5  call    __security_check_cookie
0x180011fba  add     rsp, 240h
0x180011fc1  pop     rbx
0x180011fc2  retn
```
