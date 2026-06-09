# AccInfo::ClearBlob(void)

- ea: `0x180010b6c`
- end: `0x180010bd1`
- name: `?ClearBlob@AccInfo@@AEAAXXZ`
- size: `101`
- prototype: `void __fastcall(AccInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010b18`

## callees

- `0x180010b6c`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x180010bb5`
- `ntdll!NtFreeVirtualMemory` at `0x180010bb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010b9c`
- `USER32!RemovePropW` at `0x180010b84`
- `USER32!RemovePropW` at `0x180010b84`

## pseudocode

```c
void __fastcall AccInfo::ClearBlob(AccInfo *this)
{
  HANDLE CurrentProcess; // rax
  ULONG_PTR RegionSize; // [rsp+30h] [rbp+8h] BYREF
  PVOID BaseAddress; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_QWORD *)this + 7) )
  {
    RemovePropW(*((HWND *)this + 5), *((LPCWSTR *)this + 6));
    RegionSize = *((_QWORD *)this + 8);
    BaseAddress = (PVOID)*((_QWORD *)this + 7);
    CurrentProcess = GetCurrentProcess();
    NtFreeVirtualMemory(CurrentProcess, &BaseAddress, &RegionSize, 0x8000u);
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x180010b6c  push    rbx
0x180010b6e  sub     rsp, 20h
0x180010b72  cmp     qword ptr [rcx+38h], 0
0x180010b77  mov     rbx, rcx
0x180010b7a  jz      short loc_180010BCB
0x180010b7c  mov     rdx, [rcx+30h]; lpString
0x180010b80  mov     rcx, [rcx+28h]; hWnd
0x180010b84  call    cs:__imp_RemovePropW
0x180010b8a  mov     rax, [rbx+40h]
0x180010b8e  mov     [rsp+28h+RegionSize], rax
0x180010b93  mov     rax, [rbx+38h]
0x180010b97  mov     [rsp+28h+BaseAddress], rax
0x180010b9c  call    cs:__imp_GetCurrentProcess
0x180010ba2  mov     r9d, 8000h; FreeType
0x180010ba8  lea     r8, [rsp+28h+RegionSize]; RegionSize
0x180010bad  mov     rcx, rax; ProcessHandle
0x180010bb0  lea     rdx, [rsp+28h+BaseAddress]; BaseAddress
0x180010bb5  call    cs:__imp_NtFreeVirtualMemory
0x180010bbb  mov     qword ptr [rbx+38h], 0
0x180010bc3  mov     qword ptr [rbx+40h], 0
0x180010bcb  add     rsp, 20h
0x180010bcf  pop     rbx
0x180010bd0  retn
```
