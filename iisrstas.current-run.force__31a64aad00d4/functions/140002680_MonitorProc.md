# MonitorProc

- ea: `0x140002680`
- end: `0x1400026f0`
- name: `MonitorProc`
- size: `112`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140002693`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400026ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140002693`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400026ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400026cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400026cc`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x1400026e2`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x1400026e2`

## pseudocode

```c
__int64 __fastcall MonitorProc(PVOID Parameter)
{
  void *v2; // rcx

  do
  {
    WaitForSingleObject(*((HANDLE *)Parameter + 32), 0xFFFFFFFF);
    do
    {
      v2 = (void *)*((_QWORD *)Parameter + 32);
      *((_BYTE *)Parameter + 264) = 0;
    }
    while ( !WaitForSingleObject(v2, 0x1388u) );
  }
  while ( *((_BYTE *)Parameter + 264) || *((_DWORD *)Parameter + 10) );
  CloseHandle(*((HANDLE *)Parameter + 32));
  PostThreadMessageW(*((_DWORD *)Parameter + 62), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140002680  push    rbx
0x140002682  sub     rsp, 20h
0x140002686  mov     rbx, rcx
0x140002689  mov     rcx, [rbx+100h]; hHandle
0x140002690  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002693  call    cs:__imp_WaitForSingleObject
0x140002699  mov     rcx, [rbx+100h]; hHandle
0x1400026a0  mov     edx, 1388h; dwMilliseconds
0x1400026a5  mov     byte ptr [rbx+108h], 0
0x1400026ac  call    cs:__imp_WaitForSingleObject
0x1400026b2  test    eax, eax
0x1400026b4  jz      short loc_140002699
0x1400026b6  cmp     byte ptr [rbx+108h], 0
0x1400026bd  jnz     short loc_140002689
0x1400026bf  cmp     dword ptr [rbx+28h], 0
0x1400026c3  jnz     short loc_140002689
0x1400026c5  mov     rcx, [rbx+100h]; hObject
0x1400026cc  call    cs:__imp_CloseHandle
0x1400026d2  mov     ecx, [rbx+0F8h]; idThread
0x1400026d8  xor     r9d, r9d; lParam
0x1400026db  xor     r8d, r8d; wParam
0x1400026de  lea     edx, [r9+12h]; Msg
0x1400026e2  call    cs:__imp_PostThreadMessageW
0x1400026e8  xor     eax, eax
0x1400026ea  add     rsp, 20h
0x1400026ee  pop     rbx
0x1400026ef  retn
```
