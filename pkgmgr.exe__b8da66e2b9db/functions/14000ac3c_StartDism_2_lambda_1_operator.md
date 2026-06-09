# _StartDism_::_2_::_lambda_1_::operator()

- ea: `0x14000ac3c`
- end: `0x14000aca0`
- name: `_StartDism_::_2_::_lambda_1_::operator()`
- size: `100`
- prototype: `HLOCAL *__fastcall(char ***)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ac1c`
- `0x14000ccac`

## callees

- `0x14000ac3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14000ac82`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14000ac82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac6c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14000ac94`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14000ac94`

## pseudocode

```c
HLOCAL *__fastcall StartDism_::_2_::_lambda_1_::operator()(char ***a1)
{
  char *v2; // rcx
  char *v3; // rcx
  HLOCAL *result; // rax

  v2 = **a1;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = (*a1)[1];
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  if ( *(_DWORD *)a1[1] )
    DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)*a1[2]);
  result = (HLOCAL *)a1[2];
  if ( *result )
    return (HLOCAL *)LocalFree(*result);
  return result;
}

```

## disassembly

```asm
0x14000ac3c  push    rbx
0x14000ac3e  sub     rsp, 20h
0x14000ac42  mov     rax, [rcx]
0x14000ac45  mov     rbx, rcx
0x14000ac48  mov     rcx, [rax]; hObject
0x14000ac4b  lea     rax, [rcx-1]
0x14000ac4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000ac53  ja      short loc_14000AC5B
0x14000ac55  call    cs:__imp_CloseHandle
0x14000ac5b  mov     rax, [rbx]
0x14000ac5e  mov     rcx, [rax+8]; hObject
0x14000ac62  lea     rax, [rcx-1]
0x14000ac66  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000ac6a  ja      short loc_14000AC72
0x14000ac6c  call    cs:__imp_CloseHandle
0x14000ac72  mov     rax, [rbx+8]
0x14000ac76  cmp     dword ptr [rax], 0
0x14000ac79  jz      short loc_14000AC88
0x14000ac7b  mov     rcx, [rbx+10h]
0x14000ac7f  mov     rcx, [rcx]; lpAttributeList
0x14000ac82  call    cs:__imp_DeleteProcThreadAttributeList
0x14000ac88  mov     rax, [rbx+10h]
0x14000ac8c  mov     rcx, [rax]; hMem
0x14000ac8f  test    rcx, rcx
0x14000ac92  jz      short loc_14000AC9A
0x14000ac94  call    cs:__imp_LocalFree
0x14000ac9a  add     rsp, 20h
0x14000ac9e  pop     rbx
0x14000ac9f  retn
```
