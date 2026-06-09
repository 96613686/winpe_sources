# IASTL::IASAttribute::clearValue(void)

- ea: `0x18000b680`
- end: `0x18000b6c2`
- name: `?clearValue@IASAttribute@IASTL@@IEAAXXZ`
- size: `66`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bea8`
- `0x18000c178`
- `0x18000c1fc`
- `0x18002752c`

## callees

- `0x18000b680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b69f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b6ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b69f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b6ac`

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
0x18000b680  push    rbx
0x18000b682  sub     rsp, 20h
0x18000b686  mov     rbx, rcx
0x18000b689  mov     rcx, [rcx]
0x18000b68c  mov     edx, [rcx+10h]
0x18000b68f  sub     edx, 5
0x18000b692  jz      short loc_18000B69B
0x18000b694  cmp     edx, 1
0x18000b697  jnz     short loc_18000B6B2
0x18000b699  jmp     short loc_18000B6A8
0x18000b69b  mov     rcx, [rcx+18h]; pv
0x18000b69f  call    cs:__imp_CoTaskMemFree
0x18000b6a5  mov     rcx, [rbx]
0x18000b6a8  mov     rcx, [rcx+20h]; pv
0x18000b6ac  call    cs:__imp_CoTaskMemFree
0x18000b6b2  mov     rax, [rbx]
0x18000b6b5  mov     dword ptr [rax+10h], 0
0x18000b6bc  add     rsp, 20h
0x18000b6c0  pop     rbx
0x18000b6c1  retn
```
