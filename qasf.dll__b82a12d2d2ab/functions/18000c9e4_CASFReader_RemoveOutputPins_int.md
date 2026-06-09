# CASFReader::RemoveOutputPins(int)

- ea: `0x18000c9e4`
- end: `0x18000cb35`
- name: `?RemoveOutputPins@CASFReader@@QEAAXH@Z`
- size: `337`
- prototype: `void __fastcall(CASFReader *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007f08`
- `0x18000ab04`

## callees

- `0x180007004`
- `0x18000c9e4`
- `0x18001f010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000ca1c`
- `KERNEL32!WaitForSingleObject` at `0x18000ca1c`

## pseudocode

```c
void __fastcall CASFReader::RemoveOutputPins(CASFReader *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  v2 = *((_QWORD *)this + 43);
  if ( v2 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2) )
    WaitForSingleObject(*((HANDLE *)this + 51), 0xFFFFFFFF);
  while ( 1 )
  {
    v5 = CBaseList::RemoveI((CASFReader *)((char *)this + 280), *((struct __POSITION **)this + 35));
    if ( !v5 )
      break;
    v3 = *(_QWORD *)(v5 + 48);
    v4 = v5 + 24;
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 28);
  v6 = *((_QWORD *)this + 46);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 46) = 0;
  }
  v7 = *((_QWORD *)this + 44);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 44) = 0;
  }
  v8 = *((_QWORD *)this + 45);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 45) = 0;
  }
  v9 = *((_QWORD *)this + 43);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 43) = 0;
  }
  v10 = *((_QWORD *)this + 47);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 47) = 0;
  }
}

```

## disassembly

```asm
0x18000c9e4  mov     [rsp+arg_0], rbx
0x18000c9e9  mov     [rsp+arg_8], rsi
0x18000c9ee  push    rdi
0x18000c9ef  sub     rsp, 20h
0x18000c9f3  mov     rbx, rcx
0x18000c9f6  mov     rcx, [rcx+158h]
0x18000c9fd  test    rcx, rcx
0x18000ca00  jz      short loc_18000CA22
0x18000ca02  mov     rax, [rcx]
0x18000ca05  mov     rax, [rax+20h]
0x18000ca09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca0e  test    eax, eax
0x18000ca10  jnz     short loc_18000CA22
0x18000ca12  mov     rcx, [rbx+198h]; hHandle
0x18000ca19  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ca1c  call    cs:__imp_WaitForSingleObject
0x18000ca22  lea     rsi, [rbx+118h]
0x18000ca29  jmp     short loc_18000CA62
0x18000ca2b  mov     rcx, [rax+30h]
0x18000ca2f  lea     rdi, [rax+18h]
0x18000ca33  test    rcx, rcx
0x18000ca36  jz      short loc_18000CA53
0x18000ca38  mov     rax, [rcx]
0x18000ca3b  mov     rax, [rax+28h]
0x18000ca3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca44  mov     rax, [rdi]
0x18000ca47  mov     rcx, rdi
0x18000ca4a  mov     rax, [rax+28h]
0x18000ca4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca53  mov     rax, [rdi]
0x18000ca56  mov     rcx, rdi
0x18000ca59  mov     rax, [rax+10h]
0x18000ca5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca62  mov     rdx, [rsi]; struct __POSITION *
0x18000ca65  mov     rcx, rsi; this
0x18000ca68  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000ca6d  test    rax, rax
0x18000ca70  jnz     short loc_18000CA2B
0x18000ca72  lock inc dword ptr [rbx+70h]
0x18000ca76  mov     rcx, [rbx+170h]
0x18000ca7d  test    rcx, rcx
0x18000ca80  jz      short loc_18000CA99
0x18000ca82  mov     rax, [rcx]
0x18000ca85  mov     rax, [rax+10h]
0x18000ca89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca8e  mov     qword ptr [rbx+170h], 0
0x18000ca99  mov     rcx, [rbx+160h]
0x18000caa0  test    rcx, rcx
0x18000caa3  jz      short loc_18000CABC
0x18000caa5  mov     rax, [rcx]
0x18000caa8  mov     rax, [rax+10h]
0x18000caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab1  mov     qword ptr [rbx+160h], 0
0x18000cabc  mov     rcx, [rbx+168h]
0x18000cac3  test    rcx, rcx
0x18000cac6  jz      short loc_18000CADF
0x18000cac8  mov     rax, [rcx]
0x18000cacb  mov     rax, [rax+10h]
0x18000cacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad4  mov     qword ptr [rbx+168h], 0
0x18000cadf  mov     rcx, [rbx+158h]
0x18000cae6  test    rcx, rcx
0x18000cae9  jz      short loc_18000CB02
0x18000caeb  mov     rax, [rcx]
0x18000caee  mov     rax, [rax+10h]
0x18000caf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caf7  mov     qword ptr [rbx+158h], 0
0x18000cb02  mov     rcx, [rbx+178h]
0x18000cb09  test    rcx, rcx
0x18000cb0c  jz      short loc_18000CB25
0x18000cb0e  mov     rax, [rcx]
0x18000cb11  mov     rax, [rax+10h]
0x18000cb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb1a  mov     qword ptr [rbx+178h], 0
0x18000cb25  mov     rbx, [rsp+28h+arg_0]
0x18000cb2a  mov     rsi, [rsp+28h+arg_8]
0x18000cb2f  add     rsp, 20h
0x18000cb33  pop     rdi
0x18000cb34  retn
```
