# LoadFontInfFile

- ea: `0x180007adc`
- end: `0x180007b6a`
- name: `LoadFontInfFile`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000739c`

## callees

- `0x1800077dc`
- `0x180007adc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b30`
- `SETUPAPI!SetupOpenInfFileW` at `0x180007b21`
- `SETUPAPI!SetupOpenInfFileW` at `0x180007b21`

## pseudocode

```c
__int64 __fastcall LoadFontInfFile(const wchar_t *a1, _QWORD *a2)
{
  DWORD FontInfFilename; // ebx
  HINF v4; // rsi
  HANDLE ProcessHeap; // rax
  PCWSTR FileName; // [rsp+30h] [rbp+8h] BYREF

  FileName = 0;
  if ( !a1 || !a2 )
    return 87;
  FontInfFilename = GetFontInfFilename((unsigned __int16 **)&FileName, a1);
  if ( !FontInfFilename )
  {
    v4 = SetupOpenInfFileW(FileName, 0, 2u, 0);
    if ( v4 == (HINF)-1LL )
      FontInfFilename = GetLastError();
    *a2 = v4;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)FileName);
  }
  return FontInfFilename;
}

```

## disassembly

```asm
0x180007adc  mov     rax, rsp
0x180007adf  mov     [rax+10h], rbx
0x180007ae3  mov     [rax+18h], rsi
0x180007ae7  push    rdi
0x180007ae8  sub     rsp, 20h
0x180007aec  mov     rdi, rdx
0x180007aef  mov     qword ptr [rax+8], 0
0x180007af7  test    rcx, rcx
0x180007afa  jz      short loc_180007B55
0x180007afc  test    rdx, rdx
0x180007aff  jz      short loc_180007B55
0x180007b01  mov     rdx, rcx
0x180007b04  lea     rcx, [rax+8]
0x180007b08  call    GetFontInfFilename
0x180007b0d  mov     ebx, eax
0x180007b0f  test    eax, eax
0x180007b11  jnz     short loc_180007B51
0x180007b13  xor     r9d, r9d; ErrorLine
0x180007b16  xor     edx, edx; InfClass
0x180007b18  lea     r8d, [rax+2]; InfStyle
0x180007b1c  mov     rcx, [rsp+28h+FileName]; FileName
0x180007b21  call    cs:__imp_SetupOpenInfFileW
0x180007b27  mov     rsi, rax
0x180007b2a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007b2e  jnz     short loc_180007B38
0x180007b30  call    cs:__imp_GetLastError
0x180007b36  mov     ebx, eax
0x180007b38  mov     [rdi], rsi
0x180007b3b  call    cs:__imp_GetProcessHeap
0x180007b41  mov     rcx, rax; hHeap
0x180007b44  mov     r8, [rsp+28h+FileName]; lpMem
0x180007b49  xor     edx, edx; dwFlags
0x180007b4b  call    cs:__imp_HeapFree
0x180007b51  mov     eax, ebx
0x180007b53  jmp     short loc_180007B5A
0x180007b55  mov     eax, 57h ; 'W'
0x180007b5a  mov     rbx, [rsp+28h+arg_8]
0x180007b5f  mov     rsi, [rsp+28h+arg_10]
0x180007b64  add     rsp, 20h
0x180007b68  pop     rdi
0x180007b69  retn
0x18002a5e3  push    rbp
0x18002a5e5  sub     rsp, 20h
0x18002a5e9  mov     rbp, rdx
0x18002a5ec  call    cs:__imp_GetProcessHeap
0x18002a5f2  mov     rcx, rax; hHeap
0x18002a5f5  mov     r8, [rbp+30h]; lpMem
0x18002a5f9  xor     edx, edx; dwFlags
0x18002a5fb  call    cs:__imp_HeapFree
0x18002a601  nop
0x18002a602  add     rsp, 20h
0x18002a606  pop     rbp
0x18002a607  retn
```
