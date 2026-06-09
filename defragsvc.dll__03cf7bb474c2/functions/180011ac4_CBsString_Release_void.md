# CBsString::_Release(void)

- ea: `0x180011ac4`
- end: `0x180011afe`
- name: `?_Release@CBsString@@AEAAXXZ`
- size: `58`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `26`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e4e0`
- `0x180011540`
- `0x1800117f4`
- `0x1800119a0`
- `0x180011a08`
- `0x180011ab8`
- `0x180015290`
- `0x180036638`
- `0x180038df0`
- `0x180039ee0`
- `0x18003c9e0`
- `0x18003d0b0`
- `0x18003ec00`
- `0x18003f2cc`
- `0x18003f608`
- `0x1800402b0`
- `0x180041fa4`
- `0x180042c1c`
- `0x1800431e0`
- `0x180053410`
- `0x180058f00`
- `0x180059e64`
- `0x180066fc8`
- `0x1800672b0`
- `0x180067544`
- `0x1800677b4`

## callees

- `0x180011ac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011af6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011af6`

## pseudocode

```c
void __fastcall CBsString::_Release(LPVOID *this)
{
  if ( *this != &qword_18006F470 )
    CoTaskMemFree(*this);
  *this = (LPVOID)&qword_18006F470;
  this[1] = 0;
}

```

## disassembly

```asm
0x180011ac4  mov     [rsp+arg_0], rbx
0x180011ac9  push    rdi
0x180011aca  sub     rsp, 20h
0x180011ace  lea     rdi, qword_18006F470
0x180011ad5  mov     rbx, rcx
0x180011ad8  cmp     [rcx], rdi
0x180011adb  jnz     short loc_180011AF3
0x180011add  mov     [rbx], rdi
0x180011ae0  mov     qword ptr [rbx+8], 0
0x180011ae8  mov     rbx, [rsp+28h+arg_0]
0x180011aed  add     rsp, 20h
0x180011af1  pop     rdi
0x180011af2  retn
0x180011af3  mov     rcx, [rcx]; pv
0x180011af6  call    cs:__imp_CoTaskMemFree
0x180011afc  jmp     short loc_180011ADD
```
