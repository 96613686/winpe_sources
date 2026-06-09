# FreeEAPAttributes(_EAP_ATTRIBUTES &)

- ea: `0x180018aac`
- end: `0x180018b08`
- name: `?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z`
- size: `92`
- prototype: `void __fastcall(struct _EAP_ATTRIBUTES *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018620`
- `0x180018fb0`
- `0x1800194b8`
- `0x18001ae80`

## callees

- `0x180018aac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ae9`

## pseudocode

```c
void __fastcall FreeEAPAttributes(struct _EAP_ATTRIBUTES *a1)
{
  DWORD i; // edi
  BYTE *pValue; // rcx

  if ( a1->pAttribs )
  {
    for ( i = 0; i < a1->dwNumberOfAttributes; ++i )
    {
      pValue = a1->pAttribs[i].pValue;
      if ( pValue )
        CoTaskMemFree(pValue);
    }
    CoTaskMemFree(a1->pAttribs);
  }
  a1->dwNumberOfAttributes = 0;
  a1->pAttribs = 0;
}

```

## disassembly

```asm
0x180018aac  mov     [rsp+arg_0], rbx
0x180018ab1  push    rdi
0x180018ab2  sub     rsp, 20h
0x180018ab6  cmp     qword ptr [rcx+8], 0
0x180018abb  mov     rbx, rcx
0x180018abe  jz      short loc_180018AEF
0x180018ac0  xor     edi, edi
0x180018ac2  cmp     [rcx], edi
0x180018ac4  jbe     short loc_180018AE5
0x180018ac6  mov     rax, [rbx+8]
0x180018aca  mov     ecx, edi
0x180018acc  add     rcx, rcx
0x180018acf  mov     rcx, [rax+rcx*8+8]; pv
0x180018ad4  test    rcx, rcx
0x180018ad7  jz      short loc_180018ADF
0x180018ad9  call    cs:__imp_CoTaskMemFree
0x180018adf  inc     edi
0x180018ae1  cmp     edi, [rbx]
0x180018ae3  jb      short loc_180018AC6
0x180018ae5  mov     rcx, [rbx+8]; pv
0x180018ae9  call    cs:__imp_CoTaskMemFree
0x180018aef  mov     dword ptr [rbx], 0
0x180018af5  mov     qword ptr [rbx+8], 0
0x180018afd  mov     rbx, [rsp+28h+arg_0]
0x180018b02  add     rsp, 20h
0x180018b06  pop     rdi
0x180018b07  retn
```
