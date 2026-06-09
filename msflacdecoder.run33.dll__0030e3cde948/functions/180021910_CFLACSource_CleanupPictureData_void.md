# CFLACSource::CleanupPictureData(void)

- ea: `0x180021910`
- end: `0x18002193c`
- name: `?CleanupPictureData@CFLACSource@@AEAAXXZ`
- size: `44`
- prototype: `void __fastcall(CFLACSource *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026d90`
- `0x180027590`

## callees

- `0x180021910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021925`

## pseudocode

```c
void __fastcall CFLACSource::CleanupPictureData(CFLACSource *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 80);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 80) = 0;
  }
}

```

## disassembly

```asm
0x180021910  push    rbx
0x180021912  sub     rsp, 20h
0x180021916  mov     rbx, rcx
0x180021919  mov     rcx, [rcx+280h]; pv
0x180021920  test    rcx, rcx
0x180021923  jz      short loc_180021936
0x180021925  call    cs:__imp_CoTaskMemFree
0x18002192b  mov     qword ptr [rbx+280h], 0
0x180021936  add     rsp, 20h
0x18002193a  pop     rbx
0x18002193b  retn
```
