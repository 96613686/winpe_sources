# ClrCreateManagedInstance

- ea: `0x18002c0d0`
- end: `0x18002c158`
- name: `ClrCreateManagedInstance`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180023440`

## callees

- `0x180029b70`
- `0x18002c0d0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002c126`
- `KERNEL32!GetProcAddress` at `0x18002c126`

## string_xrefs

- `0x18002c11f`: `ClrCreateManagedInstance`

## pseudocode

```c
__int64 ClrCreateManagedInstance()
{
  __int64 (*ProcAddress)(void); // rax
  __int64 result; // rax
  HMODULE hModule; // [rsp+48h] [rbp+20h] BYREF

  ProcAddress = (__int64 (*)(void))g_ClrCreateManagedInstance;
  if ( g_ClrCreateManagedInstance )
    return ProcAddress();
  hModule = 0;
  result = GetInstallation((CLRFullPath *)1, &hModule, 1);
  if ( (int)result >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "ClrCreateManagedInstance");
    g_ClrCreateManagedInstance = (int (*)(const unsigned __int16 *, const struct _GUID *, void **))ProcAddress;
    if ( ProcAddress )
      return ProcAddress();
    return 2148734721LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002c0d0  mov     [rsp+arg_0], rbx
0x18002c0d5  mov     [rsp+arg_8], rsi
0x18002c0da  push    rdi
0x18002c0db  sub     rsp, 20h
0x18002c0df  mov     rax, cs:?g_ClrCreateManagedInstance@@3P6AJPEBGAEBU_GUID@@PEAPEAX@ZEA; long (*g_ClrCreateManagedInstance)(ushort const *,_GUID const &,void * *)
0x18002c0e6  mov     rbx, r8
0x18002c0e9  mov     rdi, rdx
0x18002c0ec  mov     rsi, rcx
0x18002c0ef  test    rax, rax
0x18002c0f2  jz      short loc_18002C0FB
0x18002c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0f9  jmp     short loc_18002C148
0x18002c0fb  mov     ecx, 1; int
0x18002c100  mov     [rsp+28h+hModule], 0
0x18002c109  mov     r8d, ecx; int
0x18002c10c  lea     rdx, [rsp+28h+hModule]; HINSTANCE *
0x18002c111  call    ?GetInstallation@@YAJHPEAPEAUHINSTANCE__@@H@Z; GetInstallation(int,HINSTANCE__ * *,int)
0x18002c116  test    eax, eax
0x18002c118  js      short loc_18002C148
0x18002c11a  mov     rcx, [rsp+28h+hModule]; hModule
0x18002c11f  lea     rdx, aClrcreatemanag_1; "ClrCreateManagedInstance"
0x18002c126  call    cs:__imp_GetProcAddress
0x18002c12c  mov     cs:?g_ClrCreateManagedInstance@@3P6AJPEBGAEBU_GUID@@PEAPEAX@ZEA, rax; long (*g_ClrCreateManagedInstance)(ushort const *,_GUID const &,void * *)
0x18002c133  test    rax, rax
0x18002c136  jz      short loc_18002C143
0x18002c138  mov     r8, rbx
0x18002c13b  mov     rdx, rdi
0x18002c13e  mov     rcx, rsi
0x18002c141  jmp     short loc_18002C0F4
0x18002c143  mov     eax, 80131701h
0x18002c148  mov     rbx, [rsp+28h+arg_0]
0x18002c14d  mov     rsi, [rsp+28h+arg_8]
0x18002c152  add     rsp, 20h
0x18002c156  pop     rdi
0x18002c157  retn
```
