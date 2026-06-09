# UninitializeMapper

- ea: `0x180028de8`
- end: `0x180028ecd`
- name: `UninitializeMapper`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021820`

## callees

- `0x180028de8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028e61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028e61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028e73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028e73`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028e1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028e4e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028e1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e5b`
- `rtutils!TracePrintfA` at `0x180028ebc`
- `rtutils!TracePrintfA` at `0x180028ebc`

## pseudocode

```c
void UninitializeMapper()
{
  char *v0; // rdx
  __int64 v1; // rdi
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  HANDLE ProcessHeap; // rax

  v0 = (char *)lpMem;
  if ( lpMem )
  {
    v1 = 0;
    if ( dword_18003EBBC )
    {
      while ( 1 )
      {
        v2 = (struct _RTL_CRITICAL_SECTION *)&v0[72 * v1];
        v2[1].LockCount = 0;
        DeleteCriticalSection(v2);
        CloseHandle(v2[1].DebugInfo);
        v1 = (unsigned int)(v1 + 1);
        if ( (unsigned int)v1 >= dword_18003EBBC )
          break;
        v0 = (char *)lpMem;
      }
    }
    dword_18003EBB0 = 0;
    DeleteCriticalSection(&CriticalSection);
    CloseHandle(hObject);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC48 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        qword_18003EC48,
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
0x180028de8  mov     [rsp+arg_0], rbx
0x180028ded  push    rdi
0x180028dee  sub     rsp, 20h
0x180028df2  mov     rdx, cs:lpMem
0x180028df9  test    rdx, rdx
0x180028dfc  jz      short loc_180028E79
0x180028dfe  xor     edi, edi
0x180028e00  cmp     cs:dword_18003EBBC, edi
0x180028e06  jbe     short loc_180028E3D
0x180028e08  lea     rcx, [rdi+rdi*8]
0x180028e0c  lea     rbx, [rdx+rcx*8]
0x180028e10  mov     rcx, rbx; lpCriticalSection
0x180028e13  mov     dword ptr [rbx+30h], 0
0x180028e1a  call    cs:__imp_DeleteCriticalSection
0x180028e20  mov     rcx, [rbx+28h]; hObject
0x180028e24  call    cs:__imp_CloseHandle
0x180028e2a  inc     edi
0x180028e2c  cmp     edi, cs:dword_18003EBBC
0x180028e32  jnb     short loc_180028E3D
0x180028e34  mov     rdx, cs:lpMem
0x180028e3b  jmp     short loc_180028E08
0x180028e3d  lea     rcx, CriticalSection; lpCriticalSection
0x180028e44  mov     cs:dword_18003EBB0, 0
0x180028e4e  call    cs:__imp_DeleteCriticalSection
0x180028e54  mov     rcx, cs:hObject; hObject
0x180028e5b  call    cs:__imp_CloseHandle
0x180028e61  call    cs:__imp_GetProcessHeap
0x180028e67  mov     r8, cs:lpMem; lpMem
0x180028e6e  xor     edx, edx; dwFlags
0x180028e70  mov     rcx, rax; hHeap
0x180028e73  call    cs:__imp_HeapFree
0x180028e79  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180028e80  jz      short loc_180028EAA
0x180028e82  mov     rdx, cs:qword_18003EC48
0x180028e89  test    rdx, rdx
0x180028e8c  jz      short loc_180028EC2
0x180028e8e  mov     rcx, cs:gNdpspEtwContext
0x180028e95  lea     r8, aUninitializema_0; "UninitializeMapper: exited"
0x180028e9c  mov     rax, cs:gNdpspTemplateFunc
0x180028ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ea8  jmp     short loc_180028EC2
0x180028eaa  mov     ecx, cs:dwTraceId; dwTraceID
0x180028eb0  cmp     ecx, 0FFFFFFFFh
0x180028eb3  jz      short loc_180028EC2
0x180028eb5  lea     rdx, aUninitializema; "UninitializeMapper: exited"
0x180028ebc  call    cs:__imp_TracePrintfA
0x180028ec2  mov     rbx, [rsp+28h+arg_0]
0x180028ec7  add     rsp, 20h
0x180028ecb  pop     rdi
0x180028ecc  retn
```
