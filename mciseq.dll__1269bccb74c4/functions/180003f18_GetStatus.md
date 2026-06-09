# GetStatus

- ea: `0x180003f18`
- end: `0x180003f5f`
- name: `GetStatus`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dc0`
- `0x180004588`

## callees

- `0x180003f18`
- `0x1800058bc`

## pseudocode

```c
char __fastcall GetStatus(__int64 a1)
{
  char result; // al

  if ( LookByte(a1) >= 0 )
  {
    result = 0;
    if ( *(char *)(a1 + 12) < 0 )
      return *(_BYTE *)(a1 + 12);
  }
  else
  {
    result = LookByte(a1);
    if ( !*(_DWORD *)a1 )
      ++*(_QWORD *)(a1 + 24);
    if ( (unsigned __int8)result < 0xF0u )
    {
      *(_BYTE *)(a1 + 12) = result;
    }
    else if ( (unsigned __int8)result <= 0xF7u )
    {
      *(_BYTE *)(a1 + 12) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003f18  push    rbx
0x180003f1a  sub     rsp, 20h
0x180003f1e  mov     rbx, rcx
0x180003f21  call    LookByte
0x180003f26  test    al, al
0x180003f28  jns     short loc_180003F4E
0x180003f2a  mov     rcx, rbx
0x180003f2d  call    LookByte
0x180003f32  cmp     dword ptr [rbx], 0
0x180003f35  jnz     short loc_180003F3B
0x180003f37  inc     qword ptr [rbx+18h]
0x180003f3b  cmp     al, 0F0h
0x180003f3d  jb      short loc_180003F49
0x180003f3f  cmp     al, 0F7h
0x180003f41  ja      short loc_180003F59
0x180003f43  mov     byte ptr [rbx+0Ch], 0
0x180003f47  jmp     short loc_180003F59
0x180003f49  mov     [rbx+0Ch], al
0x180003f4c  jmp     short loc_180003F59
0x180003f4e  movzx   ecx, byte ptr [rbx+0Ch]
0x180003f52  xor     eax, eax
0x180003f54  test    cl, cl
0x180003f56  cmovs   eax, ecx
0x180003f59  add     rsp, 20h
0x180003f5d  pop     rbx
0x180003f5e  retn
```
