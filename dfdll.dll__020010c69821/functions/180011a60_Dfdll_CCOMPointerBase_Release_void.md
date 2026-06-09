# Dfdll::CCOMPointerBase::Release(void)

- ea: `0x180011a60`
- end: `0x180011a8b`
- name: `?Release@CCOMPointerBase@Dfdll@@MEAAXXZ`
- size: `43`
- prototype: `void __fastcall(Dfdll::CCOMPointerBase *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180011a60`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180011a72`
- `ole32!CoTaskMemFree` at `0x180011a72`

## pseudocode

```c
void __fastcall Dfdll::CCOMPointerBase::Release(Dfdll::CCOMPointerBase *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CoTaskMemFree(v2);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_BYTE *)this + 20) = 0;
}

```

## disassembly

```asm
0x180011a60  push    rbx
0x180011a62  sub     rsp, 20h
0x180011a66  mov     rbx, rcx
0x180011a69  mov     rcx, [rcx+8]; pv
0x180011a6d  test    rcx, rcx
0x180011a70  jz      short loc_180011A78
0x180011a72  call    cs:__imp_CoTaskMemFree
0x180011a78  and     qword ptr [rbx+8], 0
0x180011a7d  and     dword ptr [rbx+10h], 0
0x180011a81  mov     byte ptr [rbx+14h], 0
0x180011a85  add     rsp, 20h
0x180011a89  pop     rbx
0x180011a8a  retn
```
