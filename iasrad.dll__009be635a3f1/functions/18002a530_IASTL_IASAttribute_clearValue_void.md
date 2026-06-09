# IASTL::IASAttribute::clearValue(void)

- ea: `0x18002a530`
- end: `0x18002a572`
- name: `?clearValue@IASAttribute@IASTL@@IEAAXXZ`
- size: `66`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002aaf4`
- `0x18002ac78`

## callees

- `0x18002a530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a55c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a55c`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::clearValue(IASTL::IASAttribute *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( *(_DWORD *)(v2 + 16) == 5 )
  {
    CoTaskMemFree(*(LPVOID *)(v2 + 24));
    v2 = *(_QWORD *)this;
LABEL_5:
    CoTaskMemFree(*(LPVOID *)(v2 + 32));
    goto LABEL_6;
  }
  if ( *(_DWORD *)(v2 + 16) == 6 )
    goto LABEL_5;
LABEL_6:
  *(_DWORD *)(*(_QWORD *)this + 16LL) = 0;
}

```

## disassembly

```asm
0x18002a530  push    rbx
0x18002a532  sub     rsp, 20h
0x18002a536  mov     rbx, rcx
0x18002a539  mov     rcx, [rcx]
0x18002a53c  mov     edx, [rcx+10h]
0x18002a53f  sub     edx, 5
0x18002a542  jz      short loc_18002A54B
0x18002a544  cmp     edx, 1
0x18002a547  jnz     short loc_18002A562
0x18002a549  jmp     short loc_18002A558
0x18002a54b  mov     rcx, [rcx+18h]; pv
0x18002a54f  call    cs:__imp_CoTaskMemFree
0x18002a555  mov     rcx, [rbx]
0x18002a558  mov     rcx, [rcx+20h]; pv
0x18002a55c  call    cs:__imp_CoTaskMemFree
0x18002a562  mov     rax, [rbx]
0x18002a565  mov     dword ptr [rax+10h], 0
0x18002a56c  add     rsp, 20h
0x18002a570  pop     rbx
0x18002a571  retn
```
