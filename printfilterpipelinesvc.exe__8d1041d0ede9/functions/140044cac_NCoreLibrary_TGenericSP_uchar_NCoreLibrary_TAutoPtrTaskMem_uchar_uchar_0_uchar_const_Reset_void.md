# NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrTaskMem<uchar>,uchar *,0,uchar const *>::Reset(void)

- ea: `0x140044cac`
- end: `0x140044cd0`
- name: `?Reset@?$TGenericSP@EV?$TAutoPtrTaskMem@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ`
- size: `36`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004432c`
- `0x140044574`

## callees

- `0x140044cac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044cbd`

## pseudocode

```c
void __fastcall NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrTaskMem<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(
        void **a1)
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
0x140044cac  push    rbx
0x140044cae  sub     rsp, 20h
0x140044cb2  mov     rbx, rcx
0x140044cb5  mov     rcx, [rcx]; pv
0x140044cb8  test    rcx, rcx
0x140044cbb  jz      short loc_140044CCA
0x140044cbd  call    cs:__imp_CoTaskMemFree
0x140044cc3  mov     qword ptr [rbx], 0
0x140044cca  add     rsp, 20h
0x140044cce  pop     rbx
0x140044ccf  retn
```
