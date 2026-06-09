# NcaScriptLogsOpenLogFile(ushort const *,void * *)

- ea: `0x180009c4c`
- end: `0x180009cda`
- name: `?NcaScriptLogsOpenLogFile@@YAKPEBGPEAPEAX@Z`
- size: `142`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ae34`

## callees

- `0x180004f34`
- `0x180009c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009c76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009c76`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsOpenLogFile(const unsigned __int16 *a1, void **a2)
{
  DWORD LastError; // ebx
  HANDLE FileW; // rax

  LastError = 0;
  FileW = CreateFileW(a1, 0x40000000u, 0, 0, 1u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, LastError);
  }
  else
  {
    *a2 = FileW;
  }
  return LastError;
}

```

## disassembly

```asm
0x180009c4c  mov     rax, rsp
0x180009c4f  mov     [rax+8], rbx
0x180009c53  push    rdi
0x180009c54  sub     rsp, 40h
0x180009c58  xor     ebx, ebx
0x180009c5a  mov     rdi, rdx
0x180009c5d  mov     [rax-18h], rbx
0x180009c61  xor     r9d, r9d; lpSecurityAttributes
0x180009c64  mov     [rax-20h], ebx
0x180009c67  xor     r8d, r8d; dwShareMode
0x180009c6a  mov     edx, 40000000h; dwDesiredAccess
0x180009c6f  mov     dword ptr [rax-28h], 1
0x180009c76  call    cs:__imp_CreateFileW
0x180009c7d  nop     dword ptr [rax+rax+00h]
0x180009c82  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009c86  jnz     short loc_180009CC9
0x180009c88  call    cs:__imp_GetLastError
0x180009c8f  nop     dword ptr [rax+rax+00h]
0x180009c94  mov     ebx, eax
0x180009c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c9d  lea     rax, WPP_GLOBAL_Control
0x180009ca4  cmp     rcx, rax
0x180009ca7  jz      short loc_180009CCC
0x180009ca9  test    byte ptr [rcx+1Ch], 1
0x180009cad  jz      short loc_180009CCC
0x180009caf  mov     rcx, [rcx+10h]
0x180009cb3  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x180009cba  mov     edx, 1Ah
0x180009cbf  mov     r9d, ebx
0x180009cc2  call    WPP_SF_d
0x180009cc7  jmp     short loc_180009CCC
0x180009cc9  mov     [rdi], rax
0x180009ccc  mov     eax, ebx
0x180009cce  mov     rbx, [rsp+48h+arg_0]
0x180009cd3  add     rsp, 40h
0x180009cd7  pop     rdi
0x180009cd8  retn
```
