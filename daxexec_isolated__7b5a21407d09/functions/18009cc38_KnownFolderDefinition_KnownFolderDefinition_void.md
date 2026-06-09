# KnownFolderDefinition::~KnownFolderDefinition(void)

- ea: `0x18009cc38`
- end: `0x18009cce9`
- name: `??1KnownFolderDefinition@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(KnownFolderDefinition *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f704`
- `0x18009ccf0`
- `0x18009cd78`
- `0x18009d0b0`
- `0x1800c7df1`

## callees

- `0x18009cc38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cc96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ccd6`

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
0x18009cc38  push    rbx
0x18009cc3a  sub     rsp, 20h
0x18009cc3e  xorps   xmm0, xmm0
0x18009cc41  mov     rbx, rcx
0x18009cc44  movq    rax, xmm0
0x18009cc49  cmp     [rcx], rax
0x18009cc4c  jnz     short loc_18009CC62
0x18009cc4e  psrldq  xmm0, 8
0x18009cc53  movq    rax, xmm0
0x18009cc58  cmp     [rcx+8], rax
0x18009cc5c  jz      loc_18009CCE2
0x18009cc62  mov     rcx, [rcx+18h]; pv
0x18009cc66  call    cs:__imp_CoTaskMemFree
0x18009cc6d  nop     dword ptr [rax+rax+00h]
0x18009cc72  mov     rcx, [rbx+20h]; pv
0x18009cc76  call    cs:__imp_CoTaskMemFree
0x18009cc7d  nop     dword ptr [rax+rax+00h]
0x18009cc82  mov     rcx, [rbx+38h]; pv
0x18009cc86  call    cs:__imp_CoTaskMemFree
0x18009cc8d  nop     dword ptr [rax+rax+00h]
0x18009cc92  mov     rcx, [rbx+40h]; pv
0x18009cc96  call    cs:__imp_CoTaskMemFree
0x18009cc9d  nop     dword ptr [rax+rax+00h]
0x18009cca2  mov     rcx, [rbx+48h]; pv
0x18009cca6  call    cs:__imp_CoTaskMemFree
0x18009ccad  nop     dword ptr [rax+rax+00h]
0x18009ccb2  mov     rcx, [rbx+50h]; pv
0x18009ccb6  call    cs:__imp_CoTaskMemFree
0x18009ccbd  nop     dword ptr [rax+rax+00h]
0x18009ccc2  mov     rcx, [rbx+58h]; pv
0x18009ccc6  call    cs:__imp_CoTaskMemFree
0x18009cccd  nop     dword ptr [rax+rax+00h]
0x18009ccd2  mov     rcx, [rbx+60h]; pv
0x18009ccd6  call    cs:__imp_CoTaskMemFree
0x18009ccdd  nop     dword ptr [rax+rax+00h]
0x18009cce2  add     rsp, 20h
0x18009cce6  pop     rbx
0x18009cce7  retn
```
