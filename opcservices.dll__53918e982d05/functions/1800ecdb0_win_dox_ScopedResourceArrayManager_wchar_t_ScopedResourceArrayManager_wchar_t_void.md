# win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(void)

- ea: `0x1800ecdb0`
- end: `0x1800ece00`
- name: `??1?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@XZ`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fb150`
- `0x18012747b`
- `0x18012748d`

## callees

- `0x1800ecdb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecdef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecdef`

## pseudocode

```c
void __fastcall win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(__int64 a1)
{
  unsigned __int64 i; // rdi
  void *v3; // rcx

  if ( !*(_BYTE *)(a1 + 16) && *(_QWORD *)a1 )
  {
    for ( i = 0; i < *(_QWORD *)(a1 + 8); ++i )
    {
      v3 = *(void **)(*(_QWORD *)a1 + 8 * i);
      if ( v3 )
        CoTaskMemFree(v3);
    }
    CoTaskMemFree(*(LPVOID *)a1);
  }
}

```

## disassembly

```asm
0x1800ecdb0  mov     [rsp+arg_0], rbx
0x1800ecdb5  push    rdi
0x1800ecdb6  sub     rsp, 20h
0x1800ecdba  cmp     byte ptr [rcx+10h], 0
0x1800ecdbe  mov     rbx, rcx
0x1800ecdc1  jnz     short loc_1800ECDF5
0x1800ecdc3  cmp     qword ptr [rcx], 0
0x1800ecdc7  jz      short loc_1800ECDF5
0x1800ecdc9  xor     edi, edi
0x1800ecdcb  cmp     [rcx+8], rdi
0x1800ecdcf  jbe     short loc_1800ECDEC
0x1800ecdd1  mov     rax, [rbx]
0x1800ecdd4  mov     rcx, [rax+rdi*8]; pv
0x1800ecdd8  test    rcx, rcx
0x1800ecddb  jz      short loc_1800ECDE3
0x1800ecddd  call    cs:__imp_CoTaskMemFree
0x1800ecde3  inc     rdi
0x1800ecde6  cmp     rdi, [rbx+8]
0x1800ecdea  jb      short loc_1800ECDD1
0x1800ecdec  mov     rcx, [rbx]; pv
0x1800ecdef  call    cs:__imp_CoTaskMemFree
0x1800ecdf5  mov     rbx, [rsp+28h+arg_0]
0x1800ecdfa  add     rsp, 20h
0x1800ecdfe  pop     rdi
0x1800ecdff  retn
```
