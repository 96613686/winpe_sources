# WSManPluginReleaseShellContext(void *)

- ea: `0x1800046a0`
- end: `0x1800046cf`
- name: `?WSManPluginReleaseShellContext@@YAXPEAX@Z`
- size: `47`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180002fac`
- `0x1800046a0`
- `0x18000b010`

## pseudocode

```c
void __fastcall WSManPluginReleaseShellContext(void *a1)
{
  struct PwrshPlugInMediator *PwrshPlugInMediator; // rcx
  void (__fastcall *v3)(struct PwrshPlugInMediator *, void *); // rax
  _QWORD *v4; // rbx
  __int64 v5[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a1 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
      v3 = (void (__fastcall *)(struct PwrshPlugInMediator *, void *))*((_QWORD *)PwrshPlugInMediator + 2);
      if ( v3 )
        v3(PwrshPlugInMediator, a1);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &PlugInException * `RTTI Type Descriptor', (PlugInException **)v5) )
      {
        v4 = (_QWORD *)v5[0];
        if ( v5[0] )
        {
          if ( *(_QWORD *)(v5[0] + 8) )
          {
            operator delete[](*(void **)(v5[0] + 8));
            v4[1] = 0;
          }
          operator delete(v4);
        }
        __eh34_try_continuation(0, &PlugInException * `RTTI Type Descriptor', &loc_1800046C9);
      }
    }
  }
}

```

## disassembly

```asm
0x1800046a0  test    rcx, rcx
0x1800046a3  jz      short locret_1800046CE
0x1800046a5  push    rbx
0x1800046a6  sub     rsp, 30h
0x1800046aa  mov     rbx, rcx
0x1800046ad  xor     ecx, ecx; unsigned __int16 *
0x1800046af  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x1800046b4  mov     rcx, rax
0x1800046b7  mov     rax, [rax+10h]
0x1800046bb  test    rax, rax
0x1800046be  jz      short loc_1800046C9
0x1800046c0  mov     rdx, rbx
0x1800046c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c8  nop
0x1800046c9  add     rsp, 30h
0x1800046cd  pop     rbx
0x1800046ce  retn
```
