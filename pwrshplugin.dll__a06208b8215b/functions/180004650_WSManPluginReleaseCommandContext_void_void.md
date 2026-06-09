# WSManPluginReleaseCommandContext(void *,void *)

- ea: `0x180004650`
- end: `0x180004696`
- name: `?WSManPluginReleaseCommandContext@@YAXPEAX0@Z`
- size: `70`
- prototype: `void __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002fac`
- `0x180004650`
- `0x18000b010`

## pseudocode

```c
void __fastcall WSManPluginReleaseCommandContext(void *a1, void *a2)
{
  struct PwrshPlugInMediator *PwrshPlugInMediator; // rax
  _QWORD *v5; // rbx
  __int64 v6[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a1 && a2 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
      if ( *((_QWORD *)PwrshPlugInMediator + 2) )
        (*((void (__fastcall **)(struct PwrshPlugInMediator *, void *, void *))PwrshPlugInMediator + 4))(
          PwrshPlugInMediator,
          a1,
          a2);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &PlugInException * `RTTI Type Descriptor', (PlugInException **)v6) )
      {
        v5 = (_QWORD *)v6[0];
        if ( v6[0] )
        {
          if ( *(_QWORD *)(v6[0] + 8) )
          {
            operator delete[](*(void **)(v6[0] + 8));
            v5[1] = 0;
          }
          operator delete(v5);
        }
        __eh34_try_continuation(0, &PlugInException * `RTTI Type Descriptor', &loc_18000468B);
      }
    }
  }
}

```

## disassembly

```asm
0x180004650  test    rcx, rcx
0x180004653  jz      short locret_180004695
0x180004655  mov     [rsp+arg_0], rbx
0x18000465a  push    rdi
0x18000465b  sub     rsp, 30h
0x18000465f  mov     rbx, rdx
0x180004662  mov     rdi, rcx
0x180004665  test    rdx, rdx
0x180004668  jz      short loc_18000468B
0x18000466a  xor     ecx, ecx; unsigned __int16 *
0x18000466c  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004671  cmp     qword ptr [rax+10h], 0
0x180004676  jz      short loc_18000468B
0x180004678  mov     r8, rbx
0x18000467b  mov     rdx, rdi
0x18000467e  mov     rcx, rax
0x180004681  mov     rax, [rax+20h]
0x180004685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468a  nop
0x18000468b  mov     rbx, [rsp+38h+arg_0]
0x180004690  add     rsp, 30h
0x180004694  pop     rdi
0x180004695  retn
```
