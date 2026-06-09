# _attribute_t::SetName(ushort const *)

- ea: `0x18000efc0`
- end: `0x18000f004`
- name: `?SetName@_attribute_t@@QEAAJPEBG@Z`
- size: `68`
- prototype: `int __fastcall(LPVOID *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d188`
- `0x18000d274`
- `0x18000f450`
- `0x18000f4a8`

## callees

- `0x18000efc0`
- `0x18000f248`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000efd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000efd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall _attribute_t::SetName(LPVOID *this, const unsigned __int16 *a2)
{
  CoTaskMemFree(*this);
  *this = 0;
  if ( a2 )
    return StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFFu, a2);
  else
    return 0;
}

```

## disassembly

```asm
0x18000efc0  mov     [rsp+arg_0], rbx
0x18000efc5  push    rdi
0x18000efc6  sub     rsp, 20h
0x18000efca  mov     rbx, rcx
0x18000efcd  mov     rdi, rdx
0x18000efd0  mov     rcx, [rcx]; pv
0x18000efd3  call    cs:__imp_CoTaskMemFree
0x18000efd9  mov     qword ptr [rbx], 0
0x18000efe0  test    rdi, rdi
0x18000efe3  jz      short loc_18000EFF7
0x18000efe5  mov     r8, rdi; unsigned __int16 *
0x18000efe8  mov     edx, 0FFFFh; unsigned __int64
0x18000efed  mov     rcx, rbx; unsigned __int16 **
0x18000eff0  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000eff5  jmp     short loc_18000EFF9
0x18000eff7  xor     eax, eax
0x18000eff9  mov     rbx, [rsp+28h+arg_0]
0x18000effe  add     rsp, 20h
0x18000f002  pop     rdi
0x18000f003  retn
```
