# CTaskModule::`scalar deleting destructor'(uint)

- ea: `0x1800053f0`
- end: `0x180005462`
- name: `??_GCTaskModule@@UEAAPEAXI@Z`
- size: `114`
- prototype: `CTaskModule *__fastcall(CTaskModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180005340`
- `0x1800053f0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005449`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005449`

## pseudocode

```c
CTaskModule *__fastcall CTaskModule::`scalar deleting destructor'(CTaskModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rbx
  __int64 *v5; // rax

  v4 = off_180010160;
  v5 = (__int64 *)off_180010168;
  while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v5 )
  {
    if ( *(_QWORD *)v4 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 64LL))(0);
      v5 = (__int64 *)off_180010168;
    }
    v4 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v4 + 8);
  }
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800053f0  mov     [rsp+arg_0], rbx
0x1800053f5  mov     [rsp+arg_8], rsi
0x1800053fa  push    rdi
0x1800053fb  sub     rsp, 20h
0x1800053ff  mov     esi, edx
0x180005401  mov     rdi, rcx
0x180005404  mov     rbx, cs:off_180010160
0x18000540b  mov     rax, cs:off_180010168
0x180005412  jmp     short loc_180005432
0x180005414  mov     r8, [rbx]
0x180005417  test    r8, r8
0x18000541a  jz      short loc_18000542E
0x18000541c  xor     ecx, ecx
0x18000541e  mov     rax, [r8+40h]
0x180005422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005427  mov     rax, cs:off_180010168
0x18000542e  add     rbx, 8
0x180005432  cmp     rbx, rax
0x180005435  jb      short loc_180005414
0x180005437  mov     rcx, rdi; this
0x18000543a  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000543f  nop
0x180005440  test    sil, 1
0x180005444  jz      short loc_18000544F
0x180005446  mov     rcx, rdi
0x180005449  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000544f  mov     rax, rdi
0x180005452  mov     rbx, [rsp+28h+arg_0]
0x180005457  mov     rsi, [rsp+28h+arg_8]
0x18000545c  add     rsp, 20h
0x180005460  pop     rdi
0x180005461  retn
```
