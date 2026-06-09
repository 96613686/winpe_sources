# SSI_VECTOR_BUFFER::AddToVector(char *,ulong)

- ea: `0x180005548`
- end: `0x180005594`
- name: `?AddToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z`
- size: `76`
- prototype: `__int64 __fastcall(SSI_VECTOR_BUFFER *this, char *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a34`
- `0x1800040ec`
- `0x1800042fc`
- `0x180004afc`
- `0x180005620`

## callees

- `0x180005548`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SSI_VECTOR_BUFFER::AddToVector(SSI_VECTOR_BUFFER *this, char *a2, int a3)
{
  __int64 result; // rax
  __int64 v4; // rcx
  _QWORD v5[2]; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+30h] [rbp-18h]
  __int64 v7; // [rsp+34h] [rbp-14h]
  int v8; // [rsp+3Ch] [rbp-Ch]

  result = 0;
  if ( a3 )
  {
    *((_DWORD *)this + 70) += a3;
    v4 = *((_QWORD *)this + 37);
    v5[0] = 0;
    v7 = 0;
    v8 = 0;
    v5[1] = a2;
    v6 = a3;
    return (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v4 + 160LL))(v4, v5, 0xFFFFFFFFLL);
  }
  return result;
}

```

## disassembly

```asm
0x180005548  mov     r11, rsp
0x18000554b  sub     rsp, 48h
0x18000554f  xor     eax, eax
0x180005551  test    r8d, r8d
0x180005554  jz      short loc_18000558F
0x180005556  add     [rcx+118h], r8d
0x18000555d  mov     rcx, [rcx+128h]
0x180005564  mov     [r11-28h], rax
0x180005568  mov     [r11-14h], rax
0x18000556c  mov     [rsp+48h+var_C], eax
0x180005570  mov     [r11-20h], rdx
0x180005574  lea     rdx, [r11-28h]
0x180005578  mov     [r11-18h], r8d
0x18000557c  or      r8d, 0FFFFFFFFh
0x180005580  mov     rax, [rcx]
0x180005583  mov     rax, [rax+0A0h]
0x18000558a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558f  add     rsp, 48h
0x180005593  retn
```
