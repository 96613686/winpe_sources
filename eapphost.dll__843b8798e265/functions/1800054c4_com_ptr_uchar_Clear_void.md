# com_ptr<uchar>::Clear(void)

- ea: `0x1800054c4`
- end: `0x1800054ef`
- name: `?Clear@?$com_ptr@E@@QEAAXXZ`
- size: `43`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004f24`
- `0x180005448`
- `0x180005f60`
- `0x180018990`
- `0x180018d40`
- `0x1800190d0`

## callees

- `0x1800054c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054d5`

## pseudocode

```c
void __fastcall com_ptr<unsigned char>::Clear(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x1800054c4  push    rbx
0x1800054c6  sub     rsp, 20h
0x1800054ca  mov     rbx, rcx
0x1800054cd  mov     rcx, [rcx]; pv
0x1800054d0  test    rcx, rcx
0x1800054d3  jz      short loc_1800054E8
0x1800054d5  call    cs:__imp_CoTaskMemFree
0x1800054dc  nop     dword ptr [rax+rax+00h]
0x1800054e1  mov     qword ptr [rbx], 0
0x1800054e8  add     rsp, 20h
0x1800054ec  pop     rbx
0x1800054ed  retn
```
