# CKSThunkPin::GetExtendedHeaderSize(ulong,ulong)

- ea: `0x140002430`
- end: `0x14000246d`
- name: `?GetExtendedHeaderSize@CKSThunkPin@@AEAAKKK@Z`
- size: `61`
- prototype: `__int64 __fastcall(CKSThunkPin *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b064`

## callees

- `0x140002430`
- `0x140003770`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::GetExtendedHeaderSize(CKSThunkPin *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 13);
  if ( v3 )
  {
    LOBYTE(a3) = 1;
    return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2, a3);
  }
  else
  {
    if ( (a2 & 0x1000) == 0 )
      return (unsigned int)a3;
    if ( (int)a3 + 16 >= (unsigned int)a3 )
    {
      LODWORD(a3) = a3 + 16;
      return (unsigned int)a3;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140002430  sub     rsp, 28h
0x140002434  mov     rcx, [rcx+68h]
0x140002438  test    rcx, rcx
0x14000243b  jnz     short loc_140002458
0x14000243d  bt      edx, 0Ch
0x140002441  jnb     short loc_14000244F
0x140002443  lea     eax, [r8+10h]
0x140002447  cmp     eax, r8d
0x14000244a  jb      short loc_140002454
0x14000244c  mov     r8d, eax
0x14000244f  mov     eax, r8d
0x140002452  jmp     short loc_140002467
0x140002454  xor     eax, eax
0x140002456  jmp     short loc_140002467
0x140002458  mov     rax, [rcx]
0x14000245b  mov     r8b, 1
0x14000245e  mov     rax, [rax+20h]
0x140002462  call    _guard_dispatch_icall
0x140002467  add     rsp, 28h
0x14000246b  retn
```
