# KnownFolderDefinition::~KnownFolderDefinition(void)

- ea: `0x18009b2e0`
- end: `0x18009b391`
- name: `??1KnownFolderDefinition@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(KnownFolderDefinition *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d348`
- `0x18004d994`
- `0x18009b398`
- `0x18009b654`
- `0x1800c6a7a`

## callees

- `0x18009b2e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b30e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b31e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b34e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b35e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b37e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b30e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b31e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b34e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b35e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b37e`

## pseudocode

```c
void __fastcall KnownFolderDefinition::~KnownFolderDefinition(LPVOID *this)
{
  if ( *this || this[1] != (LPVOID)_mm_srli_si128((__m128i)0LL, 8).m128i_i64[0] )
  {
    CoTaskMemFree(this[3]);
    CoTaskMemFree(this[4]);
    CoTaskMemFree(this[7]);
    CoTaskMemFree(this[8]);
    CoTaskMemFree(this[9]);
    CoTaskMemFree(this[10]);
    CoTaskMemFree(this[11]);
    CoTaskMemFree(this[12]);
  }
}

```

## disassembly

```asm
0x18009b2e0  push    rbx
0x18009b2e2  sub     rsp, 20h
0x18009b2e6  xorps   xmm0, xmm0
0x18009b2e9  mov     rbx, rcx
0x18009b2ec  movq    rax, xmm0
0x18009b2f1  cmp     [rcx], rax
0x18009b2f4  jnz     short loc_18009B30A
0x18009b2f6  psrldq  xmm0, 8
0x18009b2fb  movq    rax, xmm0
0x18009b300  cmp     [rcx+8], rax
0x18009b304  jz      loc_18009B38A
0x18009b30a  mov     rcx, [rcx+18h]; pv
0x18009b30e  call    cs:__imp_CoTaskMemFree
0x18009b315  nop     dword ptr [rax+rax+00h]
0x18009b31a  mov     rcx, [rbx+20h]; pv
0x18009b31e  call    cs:__imp_CoTaskMemFree
0x18009b325  nop     dword ptr [rax+rax+00h]
0x18009b32a  mov     rcx, [rbx+38h]; pv
0x18009b32e  call    cs:__imp_CoTaskMemFree
0x18009b335  nop     dword ptr [rax+rax+00h]
0x18009b33a  mov     rcx, [rbx+40h]; pv
0x18009b33e  call    cs:__imp_CoTaskMemFree
0x18009b345  nop     dword ptr [rax+rax+00h]
0x18009b34a  mov     rcx, [rbx+48h]; pv
0x18009b34e  call    cs:__imp_CoTaskMemFree
0x18009b355  nop     dword ptr [rax+rax+00h]
0x18009b35a  mov     rcx, [rbx+50h]; pv
0x18009b35e  call    cs:__imp_CoTaskMemFree
0x18009b365  nop     dword ptr [rax+rax+00h]
0x18009b36a  mov     rcx, [rbx+58h]; pv
0x18009b36e  call    cs:__imp_CoTaskMemFree
0x18009b375  nop     dword ptr [rax+rax+00h]
0x18009b37a  mov     rcx, [rbx+60h]; pv
0x18009b37e  call    cs:__imp_CoTaskMemFree
0x18009b385  nop     dword ptr [rax+rax+00h]
0x18009b38a  add     rsp, 20h
0x18009b38e  pop     rbx
0x18009b38f  retn
```
