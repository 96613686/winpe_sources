# CAppImport::ClearImportAppInfo(tagImportAppInfo *)

- ea: `0x180042ef8`
- end: `0x180042f60`
- name: `?ClearImportAppInfo@CAppImport@@CAXPEAUtagImportAppInfo@@@Z`
- size: `104`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800434f0`
- `0x180043900`

## callees

- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f3f`

## pseudocode

```c
void __fastcall CAppImport::ClearImportAppInfo(LPVOID *a1)
{
  __int64 i; // rdi

  CoTaskMemFree(*a1);
  CoTaskMemFree(a1[1]);
  if ( a1[4] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 7); i = (unsigned int)(i + 1) )
      CoTaskMemFree(*((LPVOID *)a1[4] + i));
    CoTaskMemFree(a1[4]);
  }
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  a1[4] = 0;
}

```

## disassembly

```asm
0x180042ef8  mov     [rsp+arg_0], rbx
0x180042efd  push    rdi
0x180042efe  sub     rsp, 20h
0x180042f02  mov     rbx, rcx
0x180042f05  mov     rcx, [rcx]; pv
0x180042f08  call    cs:__imp_CoTaskMemFree
0x180042f0e  mov     rcx, [rbx+8]; pv
0x180042f12  call    cs:__imp_CoTaskMemFree
0x180042f18  cmp     qword ptr [rbx+20h], 0
0x180042f1d  jz      short loc_180042F45
0x180042f1f  xor     edi, edi
0x180042f21  cmp     [rbx+1Ch], edi
0x180042f24  jbe     short loc_180042F3B
0x180042f26  mov     rcx, [rbx+20h]
0x180042f2a  mov     rcx, [rcx+rdi*8]; pv
0x180042f2e  call    cs:__imp_CoTaskMemFree
0x180042f34  inc     edi
0x180042f36  cmp     edi, [rbx+1Ch]
0x180042f39  jb      short loc_180042F26
0x180042f3b  mov     rcx, [rbx+20h]; pv
0x180042f3f  call    cs:__imp_CoTaskMemFree
0x180042f45  xorps   xmm0, xmm0
0x180042f48  xor     eax, eax
0x180042f4a  movups  xmmword ptr [rbx], xmm0
0x180042f4d  movups  xmmword ptr [rbx+10h], xmm0
0x180042f51  mov     [rbx+20h], rax
0x180042f55  mov     rbx, [rsp+28h+arg_0]
0x180042f5a  add     rsp, 20h
0x180042f5e  pop     rdi
0x180042f5f  retn
```
