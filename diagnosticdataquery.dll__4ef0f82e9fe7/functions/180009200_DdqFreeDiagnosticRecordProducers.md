# DdqFreeDiagnosticRecordProducers

- ea: `0x180009200`
- end: `0x18000924b`
- name: `DdqFreeDiagnosticRecordProducers`
- size: `75`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800018d0`
- `0x180009200`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000921d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000922d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000921d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000922d`

## pseudocode

```c
__int64 __fastcall DdqFreeDiagnosticRecordProducers(void *a1)
{
  unsigned int v1; // ebp
  __int64 i; // rsi

  v1 = *((_DWORD *)a1 + 4);
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 1) + 8 * i));
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x180009200  push    rbx
0x180009202  push    rbp
0x180009203  push    rsi
0x180009204  push    rdi
0x180009205  sub     rsp, 28h
0x180009209  mov     ebp, [rcx+10h]
0x18000920c  xor     esi, esi
0x18000920e  mov     rdi, rcx
0x180009211  test    ebp, ebp
0x180009213  jz      short loc_180009229
0x180009215  mov     rcx, [rdi+8]
0x180009219  mov     rcx, [rcx+rsi*8]; pv
0x18000921d  call    cs:__imp_CoTaskMemFree
0x180009223  inc     esi
0x180009225  cmp     esi, ebp
0x180009227  jb      short loc_180009215
0x180009229  mov     rcx, [rdi+8]; pv
0x18000922d  call    cs:__imp_CoTaskMemFree
0x180009233  mov     edx, 4; unsigned __int64
0x180009238  mov     rcx, rdi; void *
0x18000923b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009240  xor     eax, eax
0x180009242  add     rsp, 28h
0x180009246  pop     rdi
0x180009247  pop     rsi
0x180009248  pop     rbp
0x180009249  pop     rbx
0x18000924a  retn
```
