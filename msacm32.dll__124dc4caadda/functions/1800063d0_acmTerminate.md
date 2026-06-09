# acmTerminate

- ea: `0x1800063d0`
- end: `0x180006491`
- name: `acmTerminate`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007400`

## callees

- `0x180005760`
- `0x1800063d0`
- `0x180006690`
- `0x1800087b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006461`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006473`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006461`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006473`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006454`

## pseudocode

```c
__int64 acmTerminate()
{
  __int64 v0; // rbx
  __int64 v3; // rax
  int v4; // edi

  v0 = gplag;
  if ( !gplag )
    return 0;
  if ( (*(_DWORD *)(gplag + 12))-- == 1 )
  {
    if ( *(_DWORD *)(v0 + 16) )
    {
      v3 = *(_QWORD *)(v0 + 96);
      if ( v3 )
      {
        v4 = 666;
        do
        {
          *(_QWORD *)(v3 + 36) = 0;
          *(_QWORD *)(v0 + 104) = v3;
          IDriverRemove(v3, 0);
          if ( !--v4 )
            *(_QWORD *)(v0 + 96) = 0;
          v3 = *(_QWORD *)(v0 + 96);
        }
        while ( v3 );
      }
      *(_DWORD *)(v0 + 16) = 0;
    }
    CloseHandle(*(HANDLE *)(v0 + 168));
    CloseHandle(*(HANDLE *)(v0 + 184));
    DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 128));
    threadTerminateProcess(v0);
    DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 24));
    pagDelete(v0);
  }
  return 1;
}

```

## disassembly

```asm
0x1800063d0  push    rbx
0x1800063d2  sub     rsp, 20h
0x1800063d6  mov     rbx, cs:gplag
0x1800063dd  test    rbx, rbx
0x1800063e0  jnz     short loc_1800063EA
0x1800063e2  xor     eax, eax
0x1800063e4  add     rsp, 20h
0x1800063e8  pop     rbx
0x1800063e9  retn
0x1800063ea  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1800063ee  jnz     loc_180006486
0x1800063f4  cmp     dword ptr [rbx+10h], 0
0x1800063f8  mov     [rsp+28h+arg_10], rdi
0x1800063fd  jz      short loc_180006440
0x1800063ff  mov     rax, [rbx+60h]
0x180006403  mov     [rsp+28h+arg_0], rsi
0x180006408  xor     esi, esi
0x18000640a  test    rax, rax
0x18000640d  jz      short loc_180006438
0x18000640f  mov     edi, 29Ah
0x180006414  mov     [rax+24h], rsi
0x180006418  xor     edx, edx
0x18000641a  mov     rcx, rax
0x18000641d  mov     [rbx+68h], rax
0x180006421  call    IDriverRemove
0x180006426  add     edi, 0FFFFFFFFh
0x180006429  jnz     short loc_18000642F
0x18000642b  mov     [rbx+60h], rsi
0x18000642f  mov     rax, [rbx+60h]
0x180006433  test    rax, rax
0x180006436  jnz     short loc_180006414
0x180006438  mov     [rbx+10h], esi
0x18000643b  mov     rsi, [rsp+28h+arg_0]
0x180006440  mov     rcx, [rbx+0A8h]; hObject
0x180006447  call    cs:__imp_CloseHandle
0x18000644d  mov     rcx, [rbx+0B8h]; hObject
0x180006454  call    cs:__imp_CloseHandle
0x18000645a  lea     rcx, [rbx+80h]; lpCriticalSection
0x180006461  call    cs:__imp_DeleteCriticalSection
0x180006467  mov     rcx, rbx
0x18000646a  call    threadTerminateProcess
0x18000646f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180006473  call    cs:__imp_DeleteCriticalSection
0x180006479  mov     rcx, rbx
0x18000647c  call    pagDelete
0x180006481  mov     rdi, [rsp+28h+arg_10]
0x180006486  mov     eax, 1
0x18000648b  add     rsp, 20h
0x18000648f  pop     rbx
0x180006490  retn
```
