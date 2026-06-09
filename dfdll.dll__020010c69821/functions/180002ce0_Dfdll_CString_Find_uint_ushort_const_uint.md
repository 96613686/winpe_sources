# Dfdll::CString::Find(uint,ushort const *,uint &)

- ea: `0x180002ce0`
- end: `0x180002dad`
- name: `?Find@CString@Dfdll@@QEAAJIPEBGAEAI@Z`
- size: `205`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this, unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003e88`

## callees

- `0x180002ce0`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::Find(
        Dfdll::CString *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v4; // r10d
  const unsigned __int16 *v8; // rax
  __int64 v9; // r11
  unsigned int v10; // ecx
  __int64 v11; // r9
  unsigned int v12; // r11d
  _WORD *i; // r8
  int v14; // ecx

  v4 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v8 = a3;
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = v9 == 0 ? 0x80070057 : 0;
  v11 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
    return v10;
  v12 = *((_DWORD *)this + 8);
  if ( a2 >= v12 )
  {
    return (unsigned int)-2147023728;
  }
  else
  {
    for ( i = (_WORD *)(*((_QWORD *)this + 2) + 2LL * a2); ; ++i )
    {
      v14 = 0;
      if ( (_DWORD)v11 )
        break;
LABEL_11:
      if ( ++a2 >= v12 )
        return (unsigned int)-2147023728;
    }
    while ( *i != a3[v14] )
    {
      if ( ++v14 >= (unsigned int)v11 )
        goto LABEL_11;
    }
    *a4 = a2;
  }
  return v4;
}

```

## disassembly

```asm
0x180002ce0  mov     rax, rsp
0x180002ce3  mov     [rax+8], rbx
0x180002ce7  mov     [rax+10h], rsi
0x180002ceb  mov     [rax+18h], rdi
0x180002cef  mov     [rax+20h], r14
0x180002cf3  xor     r10d, r10d
0x180002cf6  mov     r14, r9
0x180002cf9  mov     rsi, r8
0x180002cfc  mov     rdi, rcx
0x180002cff  test    r8, r8
0x180002d02  jz      loc_180002D8D
0x180002d08  mov     ebx, 7FFFFFFFh
0x180002d0d  mov     rax, r8
0x180002d10  mov     r11d, ebx
0x180002d13  cmp     [rax], r10w
0x180002d17  jz      short loc_180002D23
0x180002d19  add     rax, 2
0x180002d1d  sub     r11, 1
0x180002d21  jnz     short loc_180002D13
0x180002d23  mov     rax, r11
0x180002d26  neg     rax
0x180002d29  mov     rax, r11
0x180002d2c  sbb     ecx, ecx
0x180002d2e  sub     rbx, r11
0x180002d31  not     ecx
0x180002d33  and     ecx, 80070057h
0x180002d39  neg     rax
0x180002d3c  sbb     r9, r9
0x180002d3f  and     r9, rbx
0x180002d42  test    r11, r11
0x180002d45  jz      short loc_180002D92
0x180002d47  mov     r11d, [rdi+20h]
0x180002d4b  mov     rcx, [rdi+10h]
0x180002d4f  cmp     edx, r11d
0x180002d52  jnb     short loc_180002D80
0x180002d54  mov     eax, edx
0x180002d56  lea     r8, [rcx+rax*2]
0x180002d5a  mov     ecx, r10d
0x180002d5d  test    r9d, r9d
0x180002d60  jz      short loc_180002D75
0x180002d62  movzx   ebx, word ptr [r8]
0x180002d66  mov     eax, ecx
0x180002d68  cmp     bx, [rsi+rax*2]
0x180002d6c  jz      short loc_180002D88
0x180002d6e  inc     ecx
0x180002d70  cmp     ecx, r9d
0x180002d73  jb      short loc_180002D66
0x180002d75  inc     edx
0x180002d77  add     r8, 2
0x180002d7b  cmp     edx, r11d
0x180002d7e  jb      short loc_180002D5A
0x180002d80  mov     r10d, 80070490h
0x180002d86  jmp     short loc_180002D95
0x180002d88  mov     [r14], edx
0x180002d8b  jmp     short loc_180002D95
0x180002d8d  mov     ecx, 80070057h
0x180002d92  mov     r10d, ecx
0x180002d95  mov     rbx, [rsp+arg_0]
0x180002d9a  mov     eax, r10d
0x180002d9d  mov     rsi, [rsp+arg_8]
0x180002da2  mov     rdi, [rsp+arg_10]
0x180002da7  mov     r14, [rsp+arg_18]
0x180002dac  retn
```
