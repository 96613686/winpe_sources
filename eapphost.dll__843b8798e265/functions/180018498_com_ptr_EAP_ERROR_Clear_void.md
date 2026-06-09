# com_ptr<_EAP_ERROR>::Clear(void)

- ea: `0x180018498`
- end: `0x1800184cb`
- name: `?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ`
- size: `51`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017ff0`
- `0x180018250`
- `0x180018850`
- `0x180018990`
- `0x180018c40`
- `0x180018d40`
- `0x180018e80`
- `0x1800190d0`
- `0x180019260`
- `0x180019390`
- `0x1800194c0`
- `0x18001f9c4`
- `0x18001fca4`
- `0x18001fd34`

## callees

- `0x180004160`
- `0x180018498`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800184b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800184b1`

## pseudocode

```c
void __fastcall com_ptr<_EAP_ERROR>::Clear(LPVOID *a1)
{
  LPVOID *v2; // rcx

  v2 = (LPVOID *)*a1;
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180018498  push    rbx
0x18001849a  sub     rsp, 20h
0x18001849e  mov     rbx, rcx
0x1800184a1  mov     rcx, [rcx]; void *
0x1800184a4  test    rcx, rcx
0x1800184a7  jz      short loc_1800184C4
0x1800184a9  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x1800184ae  mov     rcx, [rbx]; pv
0x1800184b1  call    cs:__imp_CoTaskMemFree
0x1800184b8  nop     dword ptr [rax+rax+00h]
0x1800184bd  mov     qword ptr [rbx], 0
0x1800184c4  add     rsp, 20h
0x1800184c8  pop     rbx
0x1800184c9  retn
```
