# CXSendHelper::WriteSendMsgRead<TOOLINFO_64>(TOOLINFO_64 *,HWND__ *,uint,unsigned __int64,int)

- ea: `0x180025f2c`
- end: `0x180025fc8`
- name: `??$WriteSendMsgRead@UTOOLINFO_64@@@CXSendHelper@@QEAAHPEAUTOOLINFO_64@@PEAUHWND__@@I_KH@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025d84`

## callees

- `0x180025f2c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025fa5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025fa5`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025f5e`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025f5e`
- `USER32!SendMessageW` at `0x180025f7a`
- `USER32!SendMessageW` at `0x180025f7a`

## pseudocode

```c
_BOOL8 __fastcall CXSendHelper::WriteSendMsgRead<TOOLINFO_64>(
        __int64 a1,
        void *a2,
        HWND a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  return WriteProcessMemory(*(HANDLE *)(a1 + 16), *(LPVOID *)(a1 + 8), a2, 0x38u, 0)
      && (SendMessageW(a3, 0x438u, 0xFFu, *(_QWORD *)(a1 + 8)) || !a6)
      && ReadProcessMemory(*(HANDLE *)(a1 + 16), *(LPCVOID *)(a1 + 8), a2, 0x38u, 0);
}

```

## disassembly

```asm
0x180025f2c  mov     [rsp+arg_0], rbx
0x180025f31  mov     [rsp+arg_8], rsi
0x180025f36  push    rdi
0x180025f37  sub     rsp, 30h
0x180025f3b  mov     rsi, r8
0x180025f3e  mov     [rsp+38h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180025f47  mov     r8, rdx; lpBuffer
0x180025f4a  mov     rdi, rdx
0x180025f4d  mov     rdx, [rcx+8]; lpBaseAddress
0x180025f51  mov     rbx, rcx
0x180025f54  mov     rcx, [rcx+10h]; hProcess
0x180025f58  mov     r9d, 38h ; '8'; nSize
0x180025f5e  call    cs:__imp_WriteProcessMemory
0x180025f64  test    eax, eax
0x180025f66  jz      short loc_180025FB6
0x180025f68  mov     r9, [rbx+8]; lParam
0x180025f6c  mov     edx, 438h; Msg
0x180025f71  mov     r8d, 0FFh; wParam
0x180025f77  mov     rcx, rsi; hWnd
0x180025f7a  call    cs:__imp_SendMessageW
0x180025f80  test    rax, rax
0x180025f83  jnz     short loc_180025F8B
0x180025f85  cmp     [rsp+38h+arg_28], eax
0x180025f89  jnz     short loc_180025FB6
0x180025f8b  mov     rdx, [rbx+8]; lpBaseAddress
0x180025f8f  mov     r9d, 38h ; '8'; nSize
0x180025f95  mov     rcx, [rbx+10h]; hProcess
0x180025f99  mov     r8, rdi; lpBuffer
0x180025f9c  mov     [rsp+38h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180025fa5  call    cs:__imp_ReadProcessMemory
0x180025fab  xor     ecx, ecx
0x180025fad  test    eax, eax
0x180025faf  setnz   cl
0x180025fb2  mov     eax, ecx
0x180025fb4  jmp     short loc_180025FB8
0x180025fb6  xor     eax, eax
0x180025fb8  mov     rbx, [rsp+38h+arg_0]
0x180025fbd  mov     rsi, [rsp+38h+arg_8]
0x180025fc2  add     rsp, 30h
0x180025fc6  pop     rdi
0x180025fc7  retn
```
