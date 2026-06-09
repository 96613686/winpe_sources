# CILogRead::SetPosition(_ULARGE_INTEGER)

- ea: `0x180003290`
- end: `0x1800032d1`
- name: `?SetPosition@CILogRead@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(CILogRead *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003290`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogRead::SetPosition(CILogRead *this, union _ULARGE_INTEGER a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  unsigned int v4; // ebx
  ulong v5; // ebx
  unsigned int v6; // [rsp+30h] [rbp-18h] BYREF
  ulong v7; // [rsp+34h] [rbp-14h] BYREF

  v2 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v2 + 392) || a2.QuadPart )
    return 2147942487LL;
  try
  {
    result = (*(__int64 (__fastcall **)(CILogRead *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 32LL))(this, 0, 0, 0);
  }
  catch ( long v6 )
  {
    v4 = v6;
    if ( v6 == -2147479510 )
      CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
    return v4;
  }
  catch ( ulong v7 )
  {
    v5 = v7;
    if ( v7 == -2147479510 )
      CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
    return v5;
  }
  result = (*(__int64 (__fastcall **)(CILogRead *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 32LL))(this, 0, 0, 0);
}

```

## disassembly

```asm
0x180003290  mov     [rsp+arg_0], rcx
0x180003295  sub     rsp, 48h
0x180003299  mov     rax, [rcx+10h]
0x18000329d  cmp     qword ptr [rax+188h], 0
0x1800032a5  jz      short loc_1800032C7
0x1800032a7  test    rdx, rdx
0x1800032aa  jnz     short loc_1800032C7
0x1800032ac  mov     rax, [rcx]
0x1800032af  xor     r9d, r9d
0x1800032b2  xor     r8d, r8d
0x1800032b5  mov     rax, [rax+20h]
0x1800032b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032be  nop
0x1800032bf  jmp     short loc_1800032CC
0x1800032c1  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800032c5  jmp     short loc_1800032CC
0x1800032c7  mov     eax, 80070057h
0x1800032cc  add     rsp, 48h
0x1800032d0  retn
```
