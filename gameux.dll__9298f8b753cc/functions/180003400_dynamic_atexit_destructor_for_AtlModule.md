# _dynamic_atexit_destructor_for___AtlModule__

- ea: `0x180003400`
- end: `0x18000349f`
- name: `_dynamic_atexit_destructor_for___AtlModule__`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001250`
- `0x180002d44`
- `0x180003400`
- `0x180004010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003482`
- `KERNEL32!DeleteCriticalSection` at `0x180003482`

## pseudocode

```c
void dynamic_atexit_destructor_for___AtlModule__()
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v0; // rbx
  __int64 *i; // rax

  v0 = off_1800070B0;
  for ( i = off_1800070B8; v0 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v0 )
  {
    if ( *v0 )
    {
      (*((void (__fastcall **)(_QWORD))*v0 + 8))(0);
      i = off_1800070B8;
    }
  }
  if ( qword_180007748 )
  {
    if ( qword_180007750 )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)&qword_180007748);
      qword_180007750 = 0;
    }
    if ( qword_180007780 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180007780 + 16LL))(qword_180007780);
    DeleteCriticalSection(&CriticalSection);
    qword_180007748 = 0;
  }
}

```

## disassembly

```asm
0x180003400  push    rbx
0x180003402  sub     rsp, 20h
0x180003406  mov     rbx, cs:off_1800070B0
0x18000340d  mov     rax, cs:off_1800070B8
0x180003414  cmp     rbx, rax
0x180003417  jnb     short loc_18000343C
0x180003419  mov     rdx, [rbx]
0x18000341c  test    rdx, rdx
0x18000341f  jz      short loc_180003433
0x180003421  mov     rax, [rdx+40h]
0x180003425  xor     ecx, ecx
0x180003427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342c  mov     rax, cs:off_1800070B8
0x180003433  add     rbx, 8
0x180003437  cmp     rbx, rax
0x18000343a  jb      short loc_180003419
0x18000343c  cmp     dword ptr cs:qword_180007748, 0
0x180003443  jz      short loc_18000348E
0x180003445  xor     ebx, ebx
0x180003447  cmp     cs:qword_180007750, rbx
0x18000344e  jz      short loc_180003463
0x180003450  lea     rcx, qword_180007748; struct ATL::_ATL_MODULE70 *
0x180003457  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000345c  mov     cs:qword_180007750, rbx
0x180003463  mov     rcx, cs:qword_180007780
0x18000346a  test    rcx, rcx
0x18000346d  jz      short loc_18000347B
0x18000346f  mov     rax, [rcx]
0x180003472  mov     rax, [rax+10h]
0x180003476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347b  lea     rcx, CriticalSection; lpCriticalSection
0x180003482  call    cs:__imp_DeleteCriticalSection
0x180003488  mov     dword ptr cs:qword_180007748, ebx
0x18000348e  lea     rcx, qword_180007748
0x180003495  add     rsp, 20h
0x180003499  pop     rbx
0x18000349a  jmp     _guard_check_icall_nop
```
