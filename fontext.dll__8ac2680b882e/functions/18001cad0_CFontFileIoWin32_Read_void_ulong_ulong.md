# CFontFileIoWin32::Read(void *,ulong,ulong *)

- ea: `0x18001cad0`
- end: `0x18001cb0e`
- name: `?Read@CFontFileIoWin32@@UEAAKPEAXKPEAK@Z`
- size: `62`
- prototype: `unsigned int(CFontFileIoWin32 *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18001cad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cafe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001caf4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001caf4`

## pseudocode

```c
__int64 __fastcall CFontFileIoWin32::Read(CFontFileIoWin32 *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v4; // rcx
  unsigned int v6; // ebx
  DWORD *v7; // r9
  int v9; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  v6 = 0;
  v7 = (DWORD *)&v9;
  v9 = 0;
  if ( a4 )
    v7 = a4;
  if ( !ReadFile(v4, a2, a3, v7, 0) )
    return GetLastError();
  return v6;
}

```

## disassembly

```asm
0x18001cad0  push    rbx
0x18001cad2  sub     rsp, 30h
0x18001cad6  mov     rcx, [rcx+10h]; hFile
0x18001cada  mov     rax, r9
0x18001cadd  xor     ebx, ebx
0x18001cadf  lea     r9, [rsp+38h+arg_0]
0x18001cae4  test    rax, rax
0x18001cae7  mov     [rsp+38h+arg_0], ebx
0x18001caeb  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x18001caf0  cmovnz  r9, rax; lpNumberOfBytesRead
0x18001caf4  call    cs:__imp_ReadFile
0x18001cafa  test    eax, eax
0x18001cafc  jnz     short loc_18001CB06
0x18001cafe  call    cs:__imp_GetLastError
0x18001cb04  mov     ebx, eax
0x18001cb06  mov     eax, ebx
0x18001cb08  add     rsp, 30h
0x18001cb0c  pop     rbx
0x18001cb0d  retn
```
