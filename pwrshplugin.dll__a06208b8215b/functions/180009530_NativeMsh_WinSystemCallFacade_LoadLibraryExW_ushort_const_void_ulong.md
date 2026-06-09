# NativeMsh::WinSystemCallFacade::LoadLibraryExW(ushort const *,void *,ulong)

- ea: `0x180009530`
- end: `0x180009543`
- name: `?LoadLibraryExW@WinSystemCallFacade@NativeMsh@@UEAAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `19`
- prototype: `HINSTANCE __fastcall(NativeMsh::WinSystemCallFacade *this, const unsigned __int16 *, void *, DWORD)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000953c`

## pseudocode

```c
HINSTANCE __fastcall NativeMsh::WinSystemCallFacade::LoadLibraryExW(
        NativeMsh::WinSystemCallFacade *this,
        const unsigned __int16 *a2,
        void *a3,
        DWORD a4)
{
  return LoadLibraryExW(a2, a3, a4);
}

```

## disassembly

```asm
0x180009530  mov     rax, r8
0x180009533  mov     rcx, rdx
0x180009536  mov     rdx, rax
0x180009539  mov     r8d, r9d
0x18000953c  jmp     cs:__imp_LoadLibraryExW
```
