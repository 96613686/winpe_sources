# _attribute_t::FreeAll(void)

- ea: `0x18000678c`
- end: `0x1800067f7`
- name: `?FreeAll@_attribute_t@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006030`
- `0x180006100`
- `0x180006274`
- `0x180006800`
- `0x180006ac0`
- `0x1800086b0`
- `0x180009e60`
- `0x18000ad60`
- `0x18000d100`
- `0x18000d560`
- `0x18000d720`
- `0x18000d9e0`
- `0x18000dc5c`

## callees

- `0x18000678c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000679f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000679f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067dd`

## pseudocode

```c
void __fastcall _attribute_t::FreeAll(LPVOID *this)
{
  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
  CoTaskMemFree(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18000678c  push    rbx
0x18000678e  sub     rsp, 20h
0x180006792  cmp     dword ptr [rcx+8], 0Ah
0x180006796  mov     rbx, rcx
0x180006799  jnz     short loc_1800067B5
0x18000679b  mov     rcx, [rcx+10h]; pv
0x18000679f  call    cs:__imp_CoTaskMemFree
0x1800067a6  nop     dword ptr [rax+rax+00h]
0x1800067ab  mov     qword ptr [rbx+10h], 0
0x1800067b3  jmp     short loc_1800067DA
0x1800067b5  cmp     dword ptr [rcx+8], 0Eh
0x1800067b9  jnz     short loc_1800067DA
0x1800067bb  mov     rcx, [rcx+18h]; pv
0x1800067bf  call    cs:__imp_CoTaskMemFree
0x1800067c6  nop     dword ptr [rax+rax+00h]
0x1800067cb  mov     qword ptr [rbx+18h], 0
0x1800067d3  mov     dword ptr [rbx+10h], 0
0x1800067da  mov     rcx, [rbx]; pv
0x1800067dd  call    cs:__imp_CoTaskMemFree
0x1800067e4  nop     dword ptr [rax+rax+00h]
0x1800067e9  mov     qword ptr [rbx], 0
0x1800067f0  add     rsp, 20h
0x1800067f4  pop     rbx
0x1800067f5  retn
```
