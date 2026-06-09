# _hypothesis_builder::SetName(ushort const *)

- ea: `0x180018730`
- end: `0x180018777`
- name: `?SetName@_hypothesis_builder@@QEAAJPEBG@Z`
- size: `71`
- prototype: `int __fastcall(LPVOID *this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`

## callees

- `0x18000f248`
- `0x180018730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001874f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001874f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall _hypothesis_builder::SetName(LPVOID *this, const unsigned __int16 *a2)
{
  if ( !a2 )
    return -2147024809;
  CoTaskMemFree(*this);
  *this = 0;
  return StringCchCopyWithAlloc((unsigned __int16 **)this, 0xFFFFu, a2);
}

```

## disassembly

```asm
0x180018730  mov     [rsp+arg_0], rbx
0x180018735  push    rdi
0x180018736  sub     rsp, 20h
0x18001873a  mov     rbx, rdx
0x18001873d  mov     rdi, rcx
0x180018740  test    rdx, rdx
0x180018743  jnz     short loc_18001874C
0x180018745  mov     eax, 80070057h
0x18001874a  jmp     short loc_18001876C
0x18001874c  mov     rcx, [rcx]; pv
0x18001874f  call    cs:__imp_CoTaskMemFree
0x180018755  mov     r8, rbx; unsigned __int16 *
0x180018758  mov     qword ptr [rdi], 0
0x18001875f  mov     edx, 0FFFFh; unsigned __int64
0x180018764  mov     rcx, rdi; unsigned __int16 **
0x180018767  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18001876c  mov     rbx, [rsp+28h+arg_0]
0x180018771  add     rsp, 20h
0x180018775  pop     rdi
0x180018776  retn
```
