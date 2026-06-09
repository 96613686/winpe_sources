# CKSThunkPin::GetExtendedHeaderSize(ulong,ulong)

- ea: `0x140002d30`
- end: `0x140002d6d`
- name: `?GetExtendedHeaderSize@CKSThunkPin@@AEAAKKK@Z`
- size: `61`
- prototype: `__int64 __fastcall(CKSThunkPin *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bfc4`

## callees

- `0x140002d30`
- `0x1400041f0`

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
0x140002d30  sub     rsp, 28h
0x140002d34  mov     rcx, [rcx+68h]
0x140002d38  test    rcx, rcx
0x140002d3b  jnz     short loc_140002D58
0x140002d3d  bt      edx, 0Ch
0x140002d41  jnb     short loc_140002D4F
0x140002d43  lea     eax, [r8+10h]
0x140002d47  cmp     eax, r8d
0x140002d4a  jb      short loc_140002D54
0x140002d4c  mov     r8d, eax
0x140002d4f  mov     eax, r8d
0x140002d52  jmp     short loc_140002D67
0x140002d54  xor     eax, eax
0x140002d56  jmp     short loc_140002D67
0x140002d58  mov     rax, [rcx]
0x140002d5b  mov     r8b, 1
0x140002d5e  mov     rax, [rax+20h]
0x140002d62  call    _guard_dispatch_icall
0x140002d67  add     rsp, 28h
0x140002d6b  retn
```
