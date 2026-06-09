# UninitializeMapper

- ea: `0x1800909d4`
- end: `0x180090ae2`
- name: `UninitializeMapper`
- size: `270`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180089a14`

## callees

- `0x1800909d4`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180090a07`
- `KERNEL32!DeleteCriticalSection` at `0x180090a44`
- `KERNEL32!DeleteCriticalSection` at `0x180090a07`
- `KERNEL32!DeleteCriticalSection` at `0x180090a44`
- `KERNEL32!GetProcessHeap` at `0x180090a63`
- `KERNEL32!GetProcessHeap` at `0x180090a63`
- `KERNEL32!CloseHandle` at `0x180090a17`
- `KERNEL32!CloseHandle` at `0x180090a57`
- `KERNEL32!CloseHandle` at `0x180090a17`
- `KERNEL32!CloseHandle` at `0x180090a57`
- `KERNEL32!HeapFree` at `0x180090a7b`
- `KERNEL32!HeapFree` at `0x180090a7b`
- `rtutils!TracePrintfA` at `0x180090aca`
- `rtutils!TracePrintfA` at `0x180090aca`

## pseudocode

```c
void UninitializeMapper()
{
  char *v0; // rdx
  __int64 v1; // rdi
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  HANDLE ProcessHeap; // rax

  v0 = (char *)qword_1800D0848;
  if ( qword_1800D0848 )
  {
    v1 = 0;
    if ( dword_1800D083C )
    {
      while ( 1 )
      {
        v2 = (struct _RTL_CRITICAL_SECTION *)&v0[72 * v1];
        v2[1].LockCount = 0;
        DeleteCriticalSection(v2);
        CloseHandle(v2[1].DebugInfo);
        v1 = (unsigned int)(v1 + 1);
        if ( (unsigned int)v1 >= dword_1800D083C )
          break;
        v0 = (char *)qword_1800D0848;
      }
    }
    dword_1800D0830 = 0;
    DeleteCriticalSection(&stru_1800D0800);
    CloseHandle(hObject);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, qword_1800D0848);
  }
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800D0BE0 + 1),
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
0x1800909d4  mov     [rsp+arg_0], rbx
0x1800909d9  push    rdi
0x1800909da  sub     rsp, 20h
0x1800909de  mov     rdx, cs:qword_1800D0848
0x1800909e5  test    rdx, rdx
0x1800909e8  jz      loc_180090A87
0x1800909ee  xor     edi, edi
0x1800909f0  cmp     cs:dword_1800D083C, edi
0x1800909f6  jbe     short loc_180090A36
0x1800909f8  lea     rcx, [rdi+rdi*8]
0x1800909fc  lea     rbx, [rdx+rcx*8]
0x180090a00  and     dword ptr [rbx+30h], 0
0x180090a04  mov     rcx, rbx; lpCriticalSection
0x180090a07  call    cs:__imp_DeleteCriticalSection
0x180090a0e  nop     dword ptr [rax+rax+00h]
0x180090a13  mov     rcx, [rbx+28h]; hObject
0x180090a17  call    cs:__imp_CloseHandle
0x180090a1e  nop     dword ptr [rax+rax+00h]
0x180090a23  inc     edi
0x180090a25  cmp     edi, cs:dword_1800D083C
0x180090a2b  jnb     short loc_180090A36
0x180090a2d  mov     rdx, cs:qword_1800D0848
0x180090a34  jmp     short loc_1800909F8
0x180090a36  and     cs:dword_1800D0830, 0
0x180090a3d  lea     rcx, stru_1800D0800; lpCriticalSection
0x180090a44  call    cs:__imp_DeleteCriticalSection
0x180090a4b  nop     dword ptr [rax+rax+00h]
0x180090a50  mov     rcx, cs:hObject; hObject
0x180090a57  call    cs:__imp_CloseHandle
0x180090a5e  nop     dword ptr [rax+rax+00h]
0x180090a63  call    cs:__imp_GetProcessHeap
0x180090a6a  nop     dword ptr [rax+rax+00h]
0x180090a6f  mov     r8, cs:qword_1800D0848; lpMem
0x180090a76  xor     edx, edx; dwFlags
0x180090a78  mov     rcx, rax; hHeap
0x180090a7b  call    cs:__imp_HeapFree
0x180090a82  nop     dword ptr [rax+rax+00h]
0x180090a87  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180090a8e  jz      short loc_180090AB8
0x180090a90  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180090a97  test    rdx, rdx
0x180090a9a  jz      short loc_180090AD6
0x180090a9c  mov     rcx, cs:gNdpspEtwContext
0x180090aa3  lea     r8, aUninitializema_0; "UninitializeMapper: exited"
0x180090aaa  mov     rax, cs:gNdpspTemplateFunc
0x180090ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090ab6  jmp     short loc_180090AD6
0x180090ab8  mov     ecx, cs:dwTraceId; dwTraceID
0x180090abe  cmp     ecx, 0FFFFFFFFh
0x180090ac1  jz      short loc_180090AD6
0x180090ac3  lea     rdx, aUninitializema; "UninitializeMapper: exited"
0x180090aca  call    cs:__imp_TracePrintfA
0x180090ad1  nop     dword ptr [rax+rax+00h]
0x180090ad6  mov     rbx, [rsp+28h+arg_0]
0x180090adb  add     rsp, 20h
0x180090adf  pop     rdi
0x180090ae0  retn
```
