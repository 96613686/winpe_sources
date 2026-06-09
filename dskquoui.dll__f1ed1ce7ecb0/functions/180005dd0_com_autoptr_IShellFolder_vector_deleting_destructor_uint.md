# com_autoptr<IShellFolder>::`vector deleting destructor'(uint)

- ea: `0x180005dd0`
- end: `0x180005e2f`
- name: `??_E?$com_autoptr@UIShellFolder@@@@UEAAPEAXI@Z`
- size: `95`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001534`
- `0x180005dd0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall com_autoptr<IShellFolder>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  __int64 v4; // rcx

  *a1 = &com_autoptr<IDiskQuotaControl>::`vftable';
  if ( *((_DWORD *)a1 + 2) )
  {
    v4 = a1[2];
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a1 = &a_ptr<IDiskQuotaUser>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180005dd0  mov     [rsp+arg_0], rbx
0x180005dd5  push    rdi
0x180005dd6  sub     rsp, 20h
0x180005dda  mov     edi, edx
0x180005ddc  mov     rbx, rcx
0x180005ddf  lea     rax, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x180005de6  mov     [rcx], rax
0x180005de9  cmp     dword ptr [rcx+8], 0
0x180005ded  jz      short loc_180005E04
0x180005def  mov     rcx, [rcx+10h]
0x180005df3  test    rcx, rcx
0x180005df6  jz      short loc_180005E04
0x180005df8  mov     rax, [rcx]
0x180005dfb  mov     rax, [rax+10h]
0x180005dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e04  lea     rax, ??_7?$a_ptr@UIDiskQuotaUser@@@@6B@; const a_ptr<IDiskQuotaUser>::`vftable'
0x180005e0b  mov     [rbx], rax
0x180005e0e  test    dil, 1
0x180005e12  jz      short loc_180005E21
0x180005e14  mov     edx, 18h; unsigned __int64
0x180005e19  mov     rcx, rbx; void *
0x180005e1c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005e21  mov     rax, rbx
0x180005e24  mov     rbx, [rsp+28h+arg_0]
0x180005e29  add     rsp, 20h
0x180005e2d  pop     rdi
0x180005e2e  retn
```
