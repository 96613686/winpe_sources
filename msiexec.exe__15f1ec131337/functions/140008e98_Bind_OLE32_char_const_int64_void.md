# Bind_OLE32(char const *,__int64 (**)(void))

- ea: `0x140008e98`
- end: `0x140008f2c`
- name: `?Bind_OLE32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z`
- size: `148`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName, __int64 (**)(void)))(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140009040`
- `0x1400090b0`
- `0x140009100`
- `0x1400091a0`

## callees

- `0x140008e98`
- `0x1400094c4`

## import_xrefs

- `KERNEL32!Sleep` at `0x140008ebb`
- `KERNEL32!Sleep` at `0x140008ebb`
- `KERNEL32!GetProcAddress` at `0x140008f03`
- `KERNEL32!GetProcAddress` at `0x140008f03`

## pseudocode

```c
__int64 (*__fastcall Bind_OLE32(LPCSTR lpProcName, __int64 (**a2)(void)))(void)
{
  HMODULE SystemLibrary; // rax
  __int64 (*v5)(void); // rcx
  __int64 (*ProcAddress)(void); // rax
  __int64 (*result)(void); // rax

  while ( _InterlockedExchange(&dword_1400111C0, 1) == 1 )
    Sleep(0xAu);
  SystemLibrary = qword_1400111B8;
  if ( byte_1400101A2 )
  {
    if ( !qword_1400111B8 )
    {
      SystemLibrary = LoadSystemLibrary(L"OLE32");
      qword_1400111B8 = SystemLibrary;
      if ( !SystemLibrary )
        byte_1400101A2 = 0;
    }
  }
  v5 = 0;
  if ( SystemLibrary )
  {
    ProcAddress = GetProcAddress(SystemLibrary, lpProcName);
    v5 = ProcAddress;
    if ( ProcAddress )
      *a2 = ProcAddress;
  }
  result = v5;
  dword_1400111C0 = 0;
  return result;
}

```

## disassembly

```asm
0x140008e98  mov     [rsp+arg_0], rbx
0x140008e9d  push    rdi
0x140008e9e  sub     rsp, 20h
0x140008ea2  mov     rbx, rdx
0x140008ea5  mov     rdi, rcx
0x140008ea8  mov     eax, 1
0x140008ead  xchg    eax, cs:dword_1400111C0
0x140008eb3  cmp     eax, 1
0x140008eb6  jnz     short loc_140008EC3
0x140008eb8  lea     ecx, [rax+9]; dwMilliseconds
0x140008ebb  call    cs:__imp_Sleep
0x140008ec1  jmp     short loc_140008EA8
0x140008ec3  cmp     cs:byte_1400101A2, 0
0x140008eca  mov     rax, cs:qword_1400111B8
0x140008ed1  jz      short loc_140008EF6
0x140008ed3  test    rax, rax
0x140008ed6  jnz     short loc_140008EF6
0x140008ed8  lea     rcx, aOle32; "OLE32"
0x140008edf  call    ?LoadSystemLibrary@@YAPEAUHINSTANCE__@@PEBG@Z; LoadSystemLibrary(ushort const *)
0x140008ee4  mov     cs:qword_1400111B8, rax
0x140008eeb  test    rax, rax
0x140008eee  jnz     short loc_140008EF6
0x140008ef0  mov     cs:byte_1400101A2, al
0x140008ef6  xor     ecx, ecx
0x140008ef8  test    rax, rax
0x140008efb  jz      short loc_140008F14
0x140008efd  mov     rdx, rdi; lpProcName
0x140008f00  mov     rcx, rax; hModule
0x140008f03  call    cs:__imp_GetProcAddress
0x140008f09  mov     rcx, rax
0x140008f0c  test    rax, rax
0x140008f0f  jz      short loc_140008F14
0x140008f11  mov     [rbx], rax
0x140008f14  mov     rbx, [rsp+28h+arg_0]
0x140008f19  mov     rax, rcx
0x140008f1c  mov     cs:dword_1400111C0, 0
0x140008f26  add     rsp, 20h
0x140008f2a  pop     rdi
0x140008f2b  retn
```
