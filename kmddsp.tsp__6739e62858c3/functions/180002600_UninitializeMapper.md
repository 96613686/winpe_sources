# UninitializeMapper

- ea: `0x180002600`
- end: `0x1800026b1`
- name: `UninitializeMapper`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077c0`
- `0x180007c20`

## callees

- `0x180002600`
- `0x180007df8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000262d`
- `KERNEL32!DeleteCriticalSection` at `0x180002664`
- `KERNEL32!DeleteCriticalSection` at `0x18000262d`
- `KERNEL32!DeleteCriticalSection` at `0x180002664`
- `KERNEL32!LocalFree` at `0x18000268a`
- `KERNEL32!LocalFree` at `0x18000268a`
- `KERNEL32!CloseHandle` at `0x18000263d`
- `KERNEL32!CloseHandle` at `0x180002677`
- `KERNEL32!CloseHandle` at `0x18000263d`
- `KERNEL32!CloseHandle` at `0x180002677`

## pseudocode

```c
__int64 UninitializeMapper()
{
  __int64 i; // rdi
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  for ( i = 0; (unsigned int)i < dword_18000E2FC; i = (unsigned int)(i + 1) )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)((char *)hMem + 80 * i);
    v1[1].LockCount = 0;
    DeleteCriticalSection(v1);
    CloseHandle(v1[1].DebugInfo);
  }
  dword_18000E2F0 = 0;
  DeleteCriticalSection(&CriticalSection);
  CloseHandle(hObject);
  LocalFree(hMem);
  return TspLog(8, "UninitializeMapper: exited");
}

```

## disassembly

```asm
0x180002600  mov     [rsp+arg_0], rbx
0x180002605  push    rdi
0x180002606  sub     rsp, 20h
0x18000260a  xor     edi, edi
0x18000260c  cmp     cs:dword_18000E2FC, edi
0x180002612  jbe     short loc_180002653
0x180002614  lea     rbx, [rdi+rdi*4]
0x180002618  shl     rbx, 4
0x18000261c  add     rbx, cs:hMem
0x180002623  mov     rcx, rbx; lpCriticalSection
0x180002626  mov     dword ptr [rbx+30h], 0
0x18000262d  call    cs:__imp_DeleteCriticalSection
0x180002634  nop     dword ptr [rax+rax+00h]
0x180002639  mov     rcx, [rbx+28h]; hObject
0x18000263d  call    cs:__imp_CloseHandle
0x180002644  nop     dword ptr [rax+rax+00h]
0x180002649  inc     edi
0x18000264b  cmp     edi, cs:dword_18000E2FC
0x180002651  jb      short loc_180002614
0x180002653  lea     rcx, CriticalSection; lpCriticalSection
0x18000265a  mov     cs:dword_18000E2F0, 0
0x180002664  call    cs:__imp_DeleteCriticalSection
0x18000266b  nop     dword ptr [rax+rax+00h]
0x180002670  mov     rcx, cs:hObject; hObject
0x180002677  call    cs:__imp_CloseHandle
0x18000267e  nop     dword ptr [rax+rax+00h]
0x180002683  mov     rcx, cs:hMem; hMem
0x18000268a  call    cs:__imp_LocalFree
0x180002691  nop     dword ptr [rax+rax+00h]
0x180002696  lea     rdx, aUninitializema; "UninitializeMapper: exited"
0x18000269d  mov     ecx, 8
0x1800026a2  mov     rbx, [rsp+28h+arg_0]
0x1800026a7  add     rsp, 20h
0x1800026ab  pop     rdi
0x1800026ac  jmp     TspLog
```
