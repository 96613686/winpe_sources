# IASFreeAttributesArray

- ea: `0x18000b08c`
- end: `0x18000b0d8`
- name: `IASFreeAttributesArray`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800133bc`

## callees

- `0x18000b02c`
- `0x18000b08c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b0c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b0c2`

## pseudocode

```c
void __fastcall IASFreeAttributesArray(unsigned int a1, _QWORD *a2)
{
  __int64 i; // rbx
  _DWORD *v5; // rcx

  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    {
      v5 = (_DWORD *)a2[i];
      if ( v5 )
        IASFreeAttribute(v5);
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x18000b08c  test    rdx, rdx
0x18000b08f  jz      short locret_18000B0D7
0x18000b091  mov     [rsp+arg_0], rbx
0x18000b096  mov     [rsp+arg_8], rsi
0x18000b09b  push    rdi
0x18000b09c  sub     rsp, 20h
0x18000b0a0  xor     ebx, ebx
0x18000b0a2  mov     rdi, rdx
0x18000b0a5  mov     esi, ecx
0x18000b0a7  test    ecx, ecx
0x18000b0a9  jz      short loc_18000B0BF
0x18000b0ab  mov     rcx, [rdi+rbx*8]; pv
0x18000b0af  test    rcx, rcx
0x18000b0b2  jz      short loc_18000B0B9
0x18000b0b4  call    IASFreeAttribute
0x18000b0b9  inc     ebx
0x18000b0bb  cmp     ebx, esi
0x18000b0bd  jb      short loc_18000B0AB
0x18000b0bf  mov     rcx, rdi; pv
0x18000b0c2  call    cs:__imp_CoTaskMemFree
0x18000b0c8  mov     rbx, [rsp+28h+arg_0]
0x18000b0cd  mov     rsi, [rsp+28h+arg_8]
0x18000b0d2  add     rsp, 20h
0x18000b0d6  pop     rdi
0x18000b0d7  retn
```
