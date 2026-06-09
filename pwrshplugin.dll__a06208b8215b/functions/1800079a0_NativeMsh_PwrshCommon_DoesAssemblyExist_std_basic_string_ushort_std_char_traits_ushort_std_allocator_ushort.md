# NativeMsh::PwrshCommon::DoesAssemblyExist(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800079a0`
- end: `0x1800079ed`
- name: `?DoesAssemblyExist@PwrshCommon@NativeMsh@@MEAA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `77`
- prototype: `char __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800079a0`
- `0x18000b010`

## pseudocode

```c
char __fastcall NativeMsh::PwrshCommon::DoesAssemblyExist(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(_QWORD *)(a1 + 16);
  if ( a2[3] >= 8u )
    a2 = (_QWORD *)*a2;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *, const wchar_t *))(*(_QWORD *)v3 + 56LL))(v3, a2, L"r");
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 64LL))(*(_QWORD *)(a1 + 16), v4);
    LOBYTE(v4) = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x1800079a0  push    rbx
0x1800079a2  sub     rsp, 20h
0x1800079a6  cmp     qword ptr [rdx+18h], 8
0x1800079ab  mov     rbx, rcx
0x1800079ae  mov     rcx, [rcx+10h]
0x1800079b2  mov     rax, [rcx]
0x1800079b5  jb      short loc_1800079BA
0x1800079b7  mov     rdx, [rdx]
0x1800079ba  mov     rax, [rax+38h]
0x1800079be  lea     r8, aR; "r"
0x1800079c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ca  mov     r8, rax
0x1800079cd  test    rax, rax
0x1800079d0  jz      short loc_1800079E7
0x1800079d2  mov     rcx, [rbx+10h]
0x1800079d6  mov     rdx, [rcx]
0x1800079d9  mov     rax, [rdx+40h]
0x1800079dd  mov     rdx, r8
0x1800079e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e5  mov     al, 1
0x1800079e7  add     rsp, 20h
0x1800079eb  pop     rbx
0x1800079ec  retn
```
