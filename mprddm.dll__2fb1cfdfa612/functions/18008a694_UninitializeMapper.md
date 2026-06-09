# UninitializeMapper

- ea: `0x18008a694`
- end: `0x18008a779`
- name: `UninitializeMapper`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180083c10`

## callees

- `0x18008a694`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18008a6c6`
- `KERNEL32!DeleteCriticalSection` at `0x18008a6fa`
- `KERNEL32!DeleteCriticalSection` at `0x18008a6c6`
- `KERNEL32!DeleteCriticalSection` at `0x18008a6fa`
- `KERNEL32!GetProcessHeap` at `0x18008a70d`
- `KERNEL32!GetProcessHeap` at `0x18008a70d`
- `KERNEL32!CloseHandle` at `0x18008a6d0`
- `KERNEL32!CloseHandle` at `0x18008a707`
- `KERNEL32!CloseHandle` at `0x18008a6d0`
- `KERNEL32!CloseHandle` at `0x18008a707`
- `KERNEL32!HeapFree` at `0x18008a71f`
- `KERNEL32!HeapFree` at `0x18008a71f`
- `rtutils!TracePrintfA` at `0x18008a768`
- `rtutils!TracePrintfA` at `0x18008a768`

## pseudocode

```c
void UninitializeMapper()
{
  char *v0; // rdx
  __int64 v1; // rdi
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  HANDLE ProcessHeap; // rax

  v0 = (char *)qword_1800C9848;
  if ( qword_1800C9848 )
  {
    v1 = 0;
    if ( dword_1800C983C )
    {
      while ( 1 )
      {
        v2 = (struct _RTL_CRITICAL_SECTION *)&v0[72 * v1];
        v2[1].LockCount = 0;
        DeleteCriticalSection(v2);
        CloseHandle(v2[1].DebugInfo);
        v1 = (unsigned int)(v1 + 1);
        if ( (unsigned int)v1 >= dword_1800C983C )
          break;
        v0 = (char *)qword_1800C9848;
      }
    }
    dword_1800C9830 = 0;
    DeleteCriticalSection(&stru_1800C9800);
    CloseHandle(hObject);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, qword_1800C9848);
  }
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800C9BE0 + 1),
        L"UninitializeMapper: exited");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "UninitializeMapper: exited");
  }
}

```

## disassembly

```asm
0x18008a694  mov     [rsp+arg_0], rbx
0x18008a699  push    rdi
0x18008a69a  sub     rsp, 20h
0x18008a69e  mov     rdx, cs:qword_1800C9848
0x18008a6a5  test    rdx, rdx
0x18008a6a8  jz      short loc_18008A725
0x18008a6aa  xor     edi, edi
0x18008a6ac  cmp     cs:dword_1800C983C, edi
0x18008a6b2  jbe     short loc_18008A6E9
0x18008a6b4  lea     rcx, [rdi+rdi*8]
0x18008a6b8  lea     rbx, [rdx+rcx*8]
0x18008a6bc  mov     rcx, rbx; lpCriticalSection
0x18008a6bf  mov     dword ptr [rbx+30h], 0
0x18008a6c6  call    cs:__imp_DeleteCriticalSection
0x18008a6cc  mov     rcx, [rbx+28h]; hObject
0x18008a6d0  call    cs:__imp_CloseHandle
0x18008a6d6  inc     edi
0x18008a6d8  cmp     edi, cs:dword_1800C983C
0x18008a6de  jnb     short loc_18008A6E9
0x18008a6e0  mov     rdx, cs:qword_1800C9848
0x18008a6e7  jmp     short loc_18008A6B4
0x18008a6e9  lea     rcx, stru_1800C9800; lpCriticalSection
0x18008a6f0  mov     cs:dword_1800C9830, 0
0x18008a6fa  call    cs:__imp_DeleteCriticalSection
0x18008a700  mov     rcx, cs:hObject; hObject
0x18008a707  call    cs:__imp_CloseHandle
0x18008a70d  call    cs:__imp_GetProcessHeap
0x18008a713  mov     r8, cs:qword_1800C9848; lpMem
0x18008a71a  xor     edx, edx; dwFlags
0x18008a71c  mov     rcx, rax; hHeap
0x18008a71f  call    cs:__imp_HeapFree
0x18008a725  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18008a72c  jz      short loc_18008A756
0x18008a72e  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x18008a735  test    rdx, rdx
0x18008a738  jz      short loc_18008A76E
0x18008a73a  mov     rcx, cs:gNdpspEtwContext
0x18008a741  lea     r8, aUninitializema_0; "UninitializeMapper: exited"
0x18008a748  mov     rax, cs:gNdpspTemplateFunc
0x18008a74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a754  jmp     short loc_18008A76E
0x18008a756  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a75c  cmp     ecx, 0FFFFFFFFh
0x18008a75f  jz      short loc_18008A76E
0x18008a761  lea     rdx, aUninitializema; "UninitializeMapper: exited"
0x18008a768  call    cs:__imp_TracePrintfA
0x18008a76e  mov     rbx, [rsp+28h+arg_0]
0x18008a773  add     rsp, 20h
0x18008a777  pop     rdi
0x18008a778  retn
```
