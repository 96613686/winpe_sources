# WSManPluginShutdown(void *,ulong,ulong)

- ea: `0x180004830`
- end: `0x1800048f6`
- name: `?WSManPluginShutdown@@YAKPEAXKK@Z`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180002fac`
- `0x180004830`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800048e3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800048e3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800048a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800048bc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800048da`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800048a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800048bc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800048da`

## pseudocode

```c
__int64 __fastcall WSManPluginShutdown(_QWORD *a1)
{
  _QWORD *v1; // rdi
  struct PwrshPlugInMediator *PwrshPlugInMediator; // rbx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF

  v1 = a1;
  if ( !a1 )
    return 1100;
  try
  {
    PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
    if ( *(_QWORD *)PwrshPlugInMediator )
      (*(void (__fastcall **)(struct PwrshPlugInMediator *))PwrshPlugInMediator)(PwrshPlugInMediator);
    if ( !*((_BYTE *)PwrshPlugInMediator + 96) )
    {
      *((_BYTE *)PwrshPlugInMediator + 96) = 1;
      v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)PwrshPlugInMediator + 19);
      if ( v4 )
      {
        (**v4)(v4, 1);
        *((_QWORD *)PwrshPlugInMediator + 19) = 0;
      }
      v5 = (void *)*((_QWORD *)PwrshPlugInMediator + 10);
      if ( v5 )
      {
        operator delete[](v5);
        *((_QWORD *)PwrshPlugInMediator + 10) = 0;
      }
      v6 = (void *)*((_QWORD *)PwrshPlugInMediator + 11);
      if ( v6 )
      {
        operator delete[](v6);
        *((_QWORD *)PwrshPlugInMediator + 11) = 0;
      }
    }
  }
  catch ( PlugInException *v9 )
  {
    v8 = (_QWORD *)v9;
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 8) )
      {
        operator delete[](*(void **)(v9 + 8));
        v8[1] = 0;
      }
      operator delete(v8);
    }
    v1 = a1;
  }
  PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
  if ( *(_QWORD *)PwrshPlugInMediator )
    (*(void (__fastcall **)(struct PwrshPlugInMediator *))PwrshPlugInMediator)(PwrshPlugInMediator);
  if ( !*((_BYTE *)PwrshPlugInMediator + 96) )
  {
    *((_BYTE *)PwrshPlugInMediator + 96) = 1;
    v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)PwrshPlugInMediator + 19);
    if ( v4 )
    {
      (**v4)(v4, 1);
      *((_QWORD *)PwrshPlugInMediator + 19) = 0;
    }
    v5 = (void *)*((_QWORD *)PwrshPlugInMediator + 10);
    if ( v5 )
    {
      operator delete[](v5);
      *((_QWORD *)PwrshPlugInMediator + 10) = 0;
    }
    v6 = (void *)*((_QWORD *)PwrshPlugInMediator + 11);
    if ( v6 )
    {
      operator delete[](v6);
      *((_QWORD *)PwrshPlugInMediator + 11) = 0;
    }
  }
  v8 = (_QWORD *)v9;
}

```

## disassembly

```asm
0x180004830  mov     [rsp+arg_8], rbx
0x180004835  mov     [rsp+arg_0], rcx
0x18000483a  push    rdi
0x18000483b  sub     rsp, 30h
0x18000483f  mov     rdi, rcx
0x180004842  test    rcx, rcx
0x180004845  jnz     short loc_180004851
0x180004847  mov     eax, 44Ch
0x18000484c  jmp     loc_1800048EB
0x180004851  xor     ecx, ecx; unsigned __int16 *
0x180004853  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004858  mov     rbx, rax
0x18000485b  mov     rax, [rax]
0x18000485e  test    rax, rax
0x180004861  jz      short loc_18000486B
0x180004863  mov     rcx, rbx
0x180004866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000486b  cmp     byte ptr [rbx+60h], 0
0x18000486f  jnz     short loc_1800048CA
0x180004871  mov     byte ptr [rbx+60h], 1
0x180004875  mov     rcx, [rbx+98h]
0x18000487c  test    rcx, rcx
0x18000487f  jz      short loc_18000489C
0x180004881  mov     rax, [rcx]
0x180004884  mov     edx, 1
0x180004889  mov     rax, [rax]
0x18000488c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004891  mov     qword ptr [rbx+98h], 0
0x18000489c  mov     rcx, [rbx+50h]
0x1800048a0  test    rcx, rcx
0x1800048a3  jz      short loc_1800048B3
0x1800048a5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800048ab  mov     qword ptr [rbx+50h], 0
0x1800048b3  mov     rcx, [rbx+58h]
0x1800048b7  test    rcx, rcx
0x1800048ba  jz      short loc_1800048CA
0x1800048bc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800048c2  mov     qword ptr [rbx+58h], 0
0x1800048ca  jmp     short loc_1800048D1
0x1800048cc  mov     rdi, [rsp+38h+arg_0]
0x1800048d1  mov     rcx, [rdi+8]
0x1800048d5  test    rcx, rcx
0x1800048d8  jz      short loc_1800048E0
0x1800048da  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800048e0  mov     rcx, rdi
0x1800048e3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800048e9  xor     eax, eax
0x1800048eb  mov     rbx, [rsp+38h+arg_8]
0x1800048f0  add     rsp, 30h
0x1800048f4  pop     rdi
0x1800048f5  retn
```
