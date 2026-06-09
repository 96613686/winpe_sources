# com_ptr<_EAP_ERROR>::Clear(void)

- ea: `0x180017b78`
- end: `0x180017ba4`
- name: `?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800176f8`
- `0x180017930`
- `0x180017ee0`
- `0x180018020`
- `0x1800182d0`
- `0x1800183d0`
- `0x180018500`
- `0x180018740`
- `0x1800188c0`
- `0x1800189f0`
- `0x180018b20`
- `0x18001ee94`
- `0x18001f168`
- `0x18001f1f8`

## callees

- `0x18000404c`
- `0x180017b78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017b91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017b91`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180017b78  push    rbx
0x180017b7a  sub     rsp, 20h
0x180017b7e  mov     rbx, rcx
0x180017b81  mov     rcx, [rcx]; void *
0x180017b84  test    rcx, rcx
0x180017b87  jz      short loc_180017B9E
0x180017b89  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180017b8e  mov     rcx, [rbx]; pv
0x180017b91  call    cs:__imp_CoTaskMemFree
0x180017b97  mov     qword ptr [rbx], 0
0x180017b9e  add     rsp, 20h
0x180017ba2  pop     rbx
0x180017ba3  retn
```
