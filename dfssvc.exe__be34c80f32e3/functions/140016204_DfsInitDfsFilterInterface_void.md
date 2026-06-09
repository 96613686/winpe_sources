# DfsInitDfsFilterInterface(void)

- ea: `0x140016204`
- end: `0x1400162c0`
- name: `?DfsInitDfsFilterInterface@@YAKXZ`
- size: `188`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140018e88`

## callees

- `0x140016204`
- `0x1400169bc`
- `0x140016a84`
- `0x140016ba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001628b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001628b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400162a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400162a6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001626a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001626a`

## pseudocode

```c
__int64 __fastcall DfsInitDfsFilterInterface(void **a1)
{
  unsigned int started; // ebx
  __int64 i; // rdi
  void **v3; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp+10h] BYREF

  hObject = (HANDLE)-1LL;
  started = DfspOpenFilterTerminationHandle(a1);
  if ( !started )
  {
    started = DfspOpenDfsFilter(&hObject);
    if ( !started )
    {
      started = DfspStartKernelModeUpcallEngine(hObject);
      if ( !started )
      {
        ThreadId = 0;
        for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
        {
          v3 = (void **)CreateThread(0, 0, DfspUpcallSupportThreadRoutine, 0, 0, &ThreadId);
          (&DfsUpcallSupportThreadArray)[i] = v3;
          if ( v3 == (void **)-1LL )
          {
            started = GetLastError();
            break;
          }
        }
      }
    }
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
  }
  return started;
}

```

## disassembly

```asm
0x140016204  mov     [rsp+arg_10], rbx
0x140016209  push    rdi
0x14001620a  sub     rsp, 30h
0x14001620e  or      [rsp+38h+hObject], 0FFFFFFFFFFFFFFFFh
0x140016214  call    ?DfspOpenFilterTerminationHandle@@YAKPEAPEAX@Z; DfspOpenFilterTerminationHandle(void * *)
0x140016219  mov     ebx, eax
0x14001621b  test    eax, eax
0x14001621d  jnz     loc_1400162B2
0x140016223  lea     rcx, [rsp+38h+hObject]; void **
0x140016228  call    ?DfspOpenDfsFilter@@YAKPEAPEAX@Z; DfspOpenDfsFilter(void * *)
0x14001622d  mov     ebx, eax
0x14001622f  test    eax, eax
0x140016231  jnz     short loc_140016299
0x140016233  mov     rcx, [rsp+38h+hObject]; FileHandle
0x140016238  call    ?DfspStartKernelModeUpcallEngine@@YAKPEAX@Z; DfspStartKernelModeUpcallEngine(void *)
0x14001623d  mov     ebx, eax
0x14001623f  test    eax, eax
0x140016241  jnz     short loc_140016299
0x140016243  and     [rsp+38h+ThreadId], eax
0x140016247  xor     edi, edi
0x140016249  cmp     edi, 4
0x14001624c  jnb     short loc_140016299
0x14001624e  lea     rax, [rsp+38h+ThreadId]
0x140016253  xor     r9d, r9d; lpParameter
0x140016256  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14001625b  lea     r8, ?DfspUpcallSupportThreadRoutine@@YAKPEAX@Z; lpStartAddress
0x140016262  and     [rsp+38h+var_18], ebx
0x140016266  xor     edx, edx; dwStackSize
0x140016268  xor     ecx, ecx; lpThreadAttributes
0x14001626a  call    cs:__imp_CreateThread
0x140016271  nop     dword ptr [rax+rax+00h]
0x140016276  lea     rdx, ?DfsUpcallSupportThreadArray@@3PAPEAXA; void * near * DfsUpcallSupportThreadArray
0x14001627d  mov     [rdx+rdi*8], rax
0x140016281  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016285  jz      short loc_14001628B
0x140016287  inc     edi
0x140016289  jmp     short loc_140016249
0x14001628b  call    cs:__imp_GetLastError
0x140016292  nop     dword ptr [rax+rax+00h]
0x140016297  mov     ebx, eax
0x140016299  cmp     [rsp+38h+hObject], 0FFFFFFFFFFFFFFFFh
0x14001629f  jz      short loc_1400162B2
0x1400162a1  mov     rcx, [rsp+38h+hObject]; hObject
0x1400162a6  call    cs:__imp_CloseHandle
0x1400162ad  nop     dword ptr [rax+rax+00h]
0x1400162b2  mov     eax, ebx
0x1400162b4  mov     rbx, [rsp+38h+arg_10]
0x1400162b9  add     rsp, 30h
0x1400162bd  pop     rdi
0x1400162be  retn
```
