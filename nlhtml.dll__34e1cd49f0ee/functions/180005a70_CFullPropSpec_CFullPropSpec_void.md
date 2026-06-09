# CFullPropSpec::~CFullPropSpec(void)

- ea: `0x180005a70`
- end: `0x180005a9e`
- name: `??1CFullPropSpec@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CFullPropSpec *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057b8`
- `0x18000e318`
- `0x18000f90c`
- `0x18002172c`

## callees

- `0x180005a70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a8e`

## pseudocode

```c
void __fastcall CFullPropSpec::~CFullPropSpec(CFullPropSpec *this)
{
  void *v2; // rcx

  if ( !*((_DWORD *)this + 4) )
  {
    v2 = (void *)*((_QWORD *)this + 3);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)this + 3) = 0;
    }
  }
}

```

## disassembly

```asm
0x180005a70  push    rbx
0x180005a72  sub     rsp, 20h
0x180005a76  cmp     dword ptr [rcx+10h], 0
0x180005a7a  mov     rbx, rcx
0x180005a7d  jz      short loc_180005A85
0x180005a7f  add     rsp, 20h
0x180005a83  pop     rbx
0x180005a84  retn
0x180005a85  mov     rcx, [rcx+18h]; pv
0x180005a89  test    rcx, rcx
0x180005a8c  jz      short loc_180005A7F
0x180005a8e  call    cs:__imp_CoTaskMemFree
0x180005a94  mov     qword ptr [rbx+18h], 0
0x180005a9c  jmp     short loc_180005A7F
```
