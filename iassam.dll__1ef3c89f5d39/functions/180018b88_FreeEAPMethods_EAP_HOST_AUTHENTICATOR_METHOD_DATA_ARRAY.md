# FreeEAPMethods(_EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY &)

- ea: `0x180018b88`
- end: `0x180018be5`
- name: `?FreeEAPMethods@@YAXAEAU_EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY@@@Z`
- size: `93`
- prototype: `void __fastcall(struct _EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018620`
- `0x18001a0c4`

## callees

- `0x180018b88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018bc6`

## pseudocode

```c
void __fastcall FreeEAPMethods(struct _EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY *a1)
{
  unsigned int i; // edi
  void *v3; // rcx

  if ( *((_QWORD *)a1 + 1) )
  {
    for ( i = 0; i < *(_DWORD *)a1; ++i )
    {
      v3 = *(void **)(32LL * i + *((_QWORD *)a1 + 1) + 24);
      if ( v3 )
        CoTaskMemFree(v3);
    }
    CoTaskMemFree(*((LPVOID *)a1 + 1));
  }
  *(_DWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
}

```

## disassembly

```asm
0x180018b88  mov     [rsp+arg_0], rbx
0x180018b8d  push    rdi
0x180018b8e  sub     rsp, 20h
0x180018b92  cmp     qword ptr [rcx+8], 0
0x180018b97  mov     rbx, rcx
0x180018b9a  jz      short loc_180018BCC
0x180018b9c  xor     edi, edi
0x180018b9e  cmp     [rcx], edi
0x180018ba0  jbe     short loc_180018BC2
0x180018ba2  mov     rax, [rbx+8]
0x180018ba6  mov     ecx, edi
0x180018ba8  shl     rcx, 5
0x180018bac  mov     rcx, [rcx+rax+18h]; pv
0x180018bb1  test    rcx, rcx
0x180018bb4  jz      short loc_180018BBC
0x180018bb6  call    cs:__imp_CoTaskMemFree
0x180018bbc  inc     edi
0x180018bbe  cmp     edi, [rbx]
0x180018bc0  jb      short loc_180018BA2
0x180018bc2  mov     rcx, [rbx+8]; pv
0x180018bc6  call    cs:__imp_CoTaskMemFree
0x180018bcc  mov     dword ptr [rbx], 0
0x180018bd2  mov     qword ptr [rbx+8], 0
0x180018bda  mov     rbx, [rsp+28h+arg_0]
0x180018bdf  add     rsp, 20h
0x180018be3  pop     rdi
0x180018be4  retn
```
