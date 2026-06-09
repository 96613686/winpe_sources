# operator delete(void *)

- ea: `0x18000a990`
- end: `0x18000a9c6`
- name: `??3@YAXPEAX@Z`
- size: `54`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `94`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001154`
- `0x180001460`
- `0x1800015bc`
- `0x180001808`
- `0x180001c80`
- `0x1800021e0`
- `0x180002460`
- `0x180002a90`
- `0x180003274`
- `0x180003ef0`
- `0x180004b40`
- `0x1800052d0`
- `0x1800059b8`
- `0x180005b30`
- `0x180005bd0`
- `0x180006710`
- `0x180006d40`
- `0x1800077b0`
- `0x180007cc0`
- `0x180008f80`
- `0x180009e30`
- `0x18000c300`
- `0x18000c470`
- `0x18000ca20`
- `0x18000d5d0`
- `0x18000dab0`
- `0x18000e610`
- `0x18000eb80`
- `0x18000ef60`
- `0x1800101e0`
- `0x1800105e0`
- `0x180010b38`
- `0x180010ed8`
- `0x180011280`
- `0x1800119b8`
- `0x180011c20`
- `0x180011cc4`
- `0x180011eb4`
- `0x180012298`
- `0x180012390`
- `0x18001254c`
- `0x1800127c8`
- `0x1800128d8`
- `0x180012b4c`
- `0x180012dd4`
- `0x180012e70`
- `0x180012ec0`
- `0x180012f0c`
- `0x180014df0`
- `0x180015380`

## callees

- `0x18000a990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9ad`

## pseudocode

```c
void __fastcall operator delete(HLOCAL hMem)
{
  DWORD LastError; // edi

  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(hMem);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x18000a990  test    rcx, rcx
0x18000a993  jz      short locret_18000A9C5
0x18000a995  push    rbx
0x18000a996  sub     rsp, 20h
0x18000a99a  mov     rbx, rcx
0x18000a99d  mov     [rsp+28h+arg_0], rdi
0x18000a9a2  call    cs:__imp_GetLastError
0x18000a9a8  mov     rcx, rbx; hMem
0x18000a9ab  mov     edi, eax
0x18000a9ad  call    cs:__imp_LocalFree
0x18000a9b3  mov     ecx, edi; dwErrCode
0x18000a9b5  call    cs:__imp_SetLastError
0x18000a9bb  mov     rdi, [rsp+28h+arg_0]
0x18000a9c0  add     rsp, 20h
0x18000a9c4  pop     rbx
0x18000a9c5  retn
```
