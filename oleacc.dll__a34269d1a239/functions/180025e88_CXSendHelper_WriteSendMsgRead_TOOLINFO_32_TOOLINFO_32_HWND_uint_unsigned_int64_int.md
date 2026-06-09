# CXSendHelper::WriteSendMsgRead<TOOLINFO_32>(TOOLINFO_32 *,HWND__ *,uint,unsigned __int64,int)

- ea: `0x180025e88`
- end: `0x180025f24`
- name: `??$WriteSendMsgRead@UTOOLINFO_32@@@CXSendHelper@@QEAAHPEAUTOOLINFO_32@@PEAUHWND__@@I_KH@Z`
- size: `156`
- prototype: `_BOOL8 __fastcall(__int64, void *, HWND, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025c84`

## callees

- `0x180025e88`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025f01`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025f01`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025eba`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025eba`
- `USER32!SendMessageW` at `0x180025ed6`
- `USER32!SendMessageW` at `0x180025ed6`

## pseudocode

```c
_BOOL8 __fastcall CXSendHelper::WriteSendMsgRead<TOOLINFO_32>(
        __int64 a1,
        void *a2,
        HWND a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  return WriteProcessMemory(*(HANDLE *)(a1 + 16), *(LPVOID *)(a1 + 8), a2, 0x30u, 0)
      && (SendMessageW(a3, 0x438u, 0xFFu, *(_QWORD *)(a1 + 8)) || !a6)
      && ReadProcessMemory(*(HANDLE *)(a1 + 16), *(LPCVOID *)(a1 + 8), a2, 0x30u, 0);
}

```

## disassembly

```asm
0x180025e88  mov     [rsp+arg_0], rbx
0x180025e8d  mov     [rsp+arg_8], rsi
0x180025e92  push    rdi
0x180025e93  sub     rsp, 30h
0x180025e97  mov     rsi, r8
0x180025e9a  mov     [rsp+38h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180025ea3  mov     r8, rdx; lpBuffer
0x180025ea6  mov     rdi, rdx
0x180025ea9  mov     rdx, [rcx+8]; lpBaseAddress
0x180025ead  mov     rbx, rcx
0x180025eb0  mov     rcx, [rcx+10h]; hProcess
0x180025eb4  mov     r9d, 30h ; '0'; nSize
0x180025eba  call    cs:__imp_WriteProcessMemory
0x180025ec0  test    eax, eax
0x180025ec2  jz      short loc_180025F12
0x180025ec4  mov     r9, [rbx+8]; lParam
0x180025ec8  mov     edx, 438h; Msg
0x180025ecd  mov     r8d, 0FFh; wParam
0x180025ed3  mov     rcx, rsi; hWnd
0x180025ed6  call    cs:__imp_SendMessageW
0x180025edc  test    rax, rax
0x180025edf  jnz     short loc_180025EE7
0x180025ee1  cmp     [rsp+38h+arg_28], eax
0x180025ee5  jnz     short loc_180025F12
0x180025ee7  mov     rdx, [rbx+8]; lpBaseAddress
0x180025eeb  mov     r9d, 30h ; '0'; nSize
0x180025ef1  mov     rcx, [rbx+10h]; hProcess
0x180025ef5  mov     r8, rdi; lpBuffer
0x180025ef8  mov     [rsp+38h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180025f01  call    cs:__imp_ReadProcessMemory
0x180025f07  xor     ecx, ecx
0x180025f09  test    eax, eax
0x180025f0b  setnz   cl
0x180025f0e  mov     eax, ecx
0x180025f10  jmp     short loc_180025F14
0x180025f12  xor     eax, eax
0x180025f14  mov     rbx, [rsp+38h+arg_0]
0x180025f19  mov     rsi, [rsp+38h+arg_8]
0x180025f1e  add     rsp, 30h
0x180025f22  pop     rdi
0x180025f23  retn
```
