# Dfdll::CCOMPointer<ushort>::`scalar deleting destructor'(uint)

- ea: `0x180009100`
- end: `0x180009160`
- name: `??_G?$CCOMPointer@G@Dfdll@@UEAAPEAXI@Z`
- size: `96`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009100`
- `0x180012b30`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009122`
- `ole32!CoTaskMemFree` at `0x180009122`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Dfdll::CCOMPointer<unsigned short>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  void *v4; // rcx

  *a1 = &Dfdll::CCOMPointerBase::`vftable';
  v4 = (void *)a1[1];
  if ( v4 )
    CoTaskMemFree(v4);
  a1[1] = 0;
  *((_BYTE *)a1 + 20) = 0;
  *((_DWORD *)a1 + 4) = 0;
  *a1 = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x18);
  return a1;
}

```

## disassembly

```asm
0x180009100  mov     [rsp+arg_0], rbx
0x180009105  push    rdi
0x180009106  sub     rsp, 20h
0x18000910a  mov     edi, edx
0x18000910c  mov     rbx, rcx
0x18000910f  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x180009116  mov     [rcx], rax
0x180009119  mov     rcx, [rcx+8]; pv
0x18000911d  test    rcx, rcx
0x180009120  jz      short loc_180009128
0x180009122  call    cs:__imp_CoTaskMemFree
0x180009128  and     qword ptr [rbx+8], 0
0x18000912d  mov     byte ptr [rbx+14h], 0
0x180009131  and     dword ptr [rbx+10h], 0
0x180009135  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000913c  mov     [rbx], rax
0x18000913f  test    dil, 1
0x180009143  jz      short loc_180009152
0x180009145  mov     edx, 18h; struct std::nothrow_t *
0x18000914a  mov     rcx, rbx; void *
0x18000914d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009152  mov     rax, rbx
0x180009155  mov     rbx, [rsp+28h+arg_0]
0x18000915a  add     rsp, 20h
0x18000915e  pop     rdi
0x18000915f  retn
```
