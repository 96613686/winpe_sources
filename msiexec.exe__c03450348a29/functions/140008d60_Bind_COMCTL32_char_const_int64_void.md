# Bind_COMCTL32(char const *,__int64 (**)(void))

- ea: `0x140008d60`
- end: `0x140008df5`
- name: `?Bind_COMCTL32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z`
- size: `149`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName, __int64 (**)(void)))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009300`
- `0x1400093e0`

## callees

- `0x140008d60`

## import_xrefs

- `KERNEL32!Sleep` at `0x140008d83`
- `KERNEL32!Sleep` at `0x140008d83`
- `KERNEL32!LoadLibraryW` at `0x140008da7`
- `KERNEL32!LoadLibraryW` at `0x140008da7`
- `KERNEL32!GetProcAddress` at `0x140008dcc`
- `KERNEL32!GetProcAddress` at `0x140008dcc`

## string_xrefs

- `0x140008da0`: `COMCTL32`

## pseudocode

```c
__int64 (*__fastcall Bind_COMCTL32(LPCSTR lpProcName, __int64 (**a2)(void)))(void)
{
  HMODULE LibraryW; // rax
  __int64 (*v5)(void); // rcx
  __int64 (*ProcAddress)(void); // rax
  __int64 (*result)(void); // rax

  while ( _InterlockedExchange(&dword_1400111D0, 1) == 1 )
    Sleep(0xAu);
  LibraryW = hModule;
  if ( byte_1400101A3 )
  {
    if ( !hModule )
    {
      LibraryW = LoadLibraryW(L"COMCTL32");
      hModule = LibraryW;
      if ( !LibraryW )
        byte_1400101A3 = 0;
    }
  }
  v5 = 0;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, lpProcName);
    v5 = ProcAddress;
    if ( ProcAddress )
      *a2 = ProcAddress;
  }
  result = v5;
  dword_1400111D0 = 0;
  return result;
}

```

## disassembly

```asm
0x140008d60  mov     [rsp+arg_0], rbx
0x140008d65  push    rdi
0x140008d66  sub     rsp, 20h
0x140008d6a  mov     rbx, rdx
0x140008d6d  mov     rdi, rcx
0x140008d70  mov     eax, 1
0x140008d75  xchg    eax, cs:dword_1400111D0
0x140008d7b  cmp     eax, 1
0x140008d7e  jnz     short loc_140008D8B
0x140008d80  lea     ecx, [rax+9]; dwMilliseconds
0x140008d83  call    cs:__imp_Sleep
0x140008d89  jmp     short loc_140008D70
0x140008d8b  cmp     cs:byte_1400101A3, 0
0x140008d92  mov     rax, cs:hModule
0x140008d99  jz      short loc_140008DBF
0x140008d9b  test    rax, rax
0x140008d9e  jnz     short loc_140008DBF
0x140008da0  lea     rcx, aComctl32; "COMCTL32"
0x140008da7  call    cs:__imp_LoadLibraryW
0x140008dad  mov     cs:hModule, rax
0x140008db4  test    rax, rax
0x140008db7  jnz     short loc_140008DBF
0x140008db9  mov     cs:byte_1400101A3, al
0x140008dbf  xor     ecx, ecx
0x140008dc1  test    rax, rax
0x140008dc4  jz      short loc_140008DDD
0x140008dc6  mov     rdx, rdi; lpProcName
0x140008dc9  mov     rcx, rax; hModule
0x140008dcc  call    cs:__imp_GetProcAddress
0x140008dd2  mov     rcx, rax
0x140008dd5  test    rax, rax
0x140008dd8  jz      short loc_140008DDD
0x140008dda  mov     [rbx], rax
0x140008ddd  mov     rbx, [rsp+28h+arg_0]
0x140008de2  mov     rax, rcx
0x140008de5  mov     cs:dword_1400111D0, 0
0x140008def  add     rsp, 20h
0x140008df3  pop     rdi
0x140008df4  retn
```
