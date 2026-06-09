# ReadAhead(void *)

- ea: `0x180020a20`
- end: `0x180020a9d`
- name: `?ReadAhead@@YAKPEAX@Z`
- size: `125`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180020a20`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180020a75`
- `KERNEL32!ReleaseSemaphore` at `0x180020a75`
- `KERNEL32!WaitForSingleObject` at `0x180020a30`
- `KERNEL32!WaitForSingleObject` at `0x180020a85`
- `KERNEL32!WaitForSingleObject` at `0x180020a30`
- `KERNEL32!WaitForSingleObject` at `0x180020a85`
- `KERNEL32!_lread` at `0x180020a57`
- `KERNEL32!_lread` at `0x180020a57`
- `KERNEL32!ExitThread` at `0x180020a96`
- `KERNEL32!ExitThread` at `0x180020a96`

## pseudocode

```c
void __fastcall __noreturn ReadAhead(PVOID Parameter)
{
  void *v1; // rdx

  while ( 1 )
  {
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
    if ( dword_18008C298 )
      break;
    WaitForSingleObject(hSemaphore, 0xFFFFFFFF);
    v1 = Block;
    if ( *(void **)(qword_18008C320 + 40) == Block )
      v1 = lpBuffer;
    *(_DWORD *)(qword_18008C320 + 60) = _lread(*(_DWORD *)(qword_18008C320 + 28), v1, *(_DWORD *)(qword_18008C320 + 56));
    ReleaseSemaphore(hSemaphore, 1, 0);
  }
  ExitThread(0);
}

```

## disassembly

```asm
0x180020a20  sub     rsp, 28h
0x180020a24  jmp     short loc_180020A7B
0x180020a26  mov     rcx, cs:hSemaphore; hHandle
0x180020a2d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020a30  call    cs:__imp_WaitForSingleObject
0x180020a36  mov     rcx, cs:qword_18008C320
0x180020a3d  mov     rdx, cs:Block
0x180020a44  cmp     [rcx+28h], rdx
0x180020a48  mov     r8d, [rcx+38h]; uBytes
0x180020a4c  cmovz   rdx, cs:lpBuffer; lpBuffer
0x180020a54  mov     ecx, [rcx+1Ch]; hFile
0x180020a57  call    cs:__imp__lread
0x180020a5d  mov     rcx, cs:qword_18008C320
0x180020a64  xor     r8d, r8d; lpPreviousCount
0x180020a67  mov     [rcx+3Ch], eax
0x180020a6a  lea     edx, [r8+1]; lReleaseCount
0x180020a6e  mov     rcx, cs:hSemaphore; hSemaphore
0x180020a75  call    cs:__imp_ReleaseSemaphore
0x180020a7b  mov     rcx, cs:hHandle; hHandle
0x180020a82  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020a85  call    cs:__imp_WaitForSingleObject
0x180020a8b  cmp     cs:dword_18008C298, 0
0x180020a92  jz      short loc_180020A26
0x180020a94  xor     ecx, ecx; dwExitCode
0x180020a96  call    cs:__imp_ExitThread
```
