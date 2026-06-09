# CheckOutOffset

- ea: `0x18001a234`
- end: `0x18001a2c5`
- name: `CheckOutOffset`
- size: `145`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180019804`
- `0x18001986c`
- `0x1800198f8`
- `0x18001a76c`
- `0x18001a7b8`
- `0x18001aa68`
- `0x18001aadc`

## callees

- `0x18001a234`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CheckOutOffset(__int64 a1, unsigned int a2, unsigned __int64 a3)
{
  unsigned int v4; // r8d
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  __int64 v7; // rax

  if ( *(_QWORD *)a1 )
  {
    if ( a3 <= 0xFFFFFFFF )
    {
      v4 = a2 + a3;
      if ( v4 >= a2 )
      {
        v5 = *(unsigned int *)(a1 + 8);
        if ( v4 <= v5 )
          return 0;
        if ( *(_QWORD *)(a1 + 16) )
        {
          v6 = 11 * (int)v5 / 0xAu;
          if ( v6 <= v4 )
          {
            *(_DWORD *)(a1 + 8) = v4;
            LODWORD(v6) = v4;
          }
          else
          {
            *(_DWORD *)(a1 + 8) = v6;
          }
          v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 16))(*(_QWORD *)a1, (unsigned int)v6);
          *(_QWORD *)a1 = v7;
          if ( !v7 )
          {
            *(_DWORD *)(a1 + 8) = 0;
            return 1005;
          }
          return 0;
        }
      }
    }
  }
  return 1002;
}

```

## disassembly

```asm
0x18001a234  push    rbx
0x18001a236  sub     rsp, 20h
0x18001a23a  cmp     qword ptr [rcx], 0
0x18001a23e  mov     rbx, rcx
0x18001a241  mov     [rsp+28h+arg_0], 0
0x18001a24a  jz      short loc_18001A2BA
0x18001a24c  mov     eax, 0FFFFFFFFh
0x18001a251  cmp     r8, rax
0x18001a254  ja      short loc_18001A2BA
0x18001a256  add     r8d, edx
0x18001a259  cmp     r8d, edx
0x18001a25c  jb      short loc_18001A2BA
0x18001a25e  mov     eax, [rcx+8]
0x18001a261  mov     dword ptr [rsp+28h+arg_0], r8d
0x18001a266  cmp     [rsp+28h+arg_0], rax
0x18001a26b  jbe     short loc_18001A2B6
0x18001a26d  cmp     qword ptr [rcx+10h], 0
0x18001a272  jz      short loc_18001A2BA
0x18001a274  imul    ecx, eax, 0Bh
0x18001a277  mov     eax, 0CCCCCCCDh
0x18001a27c  mul     ecx
0x18001a27e  shr     edx, 3
0x18001a281  mov     eax, edx
0x18001a283  cmp     rax, [rsp+28h+arg_0]
0x18001a288  jbe     short loc_18001A28F
0x18001a28a  mov     [rbx+8], eax
0x18001a28d  jmp     short loc_18001A296
0x18001a28f  mov     [rbx+8], r8d
0x18001a293  mov     eax, r8d
0x18001a296  mov     rcx, [rbx]
0x18001a299  mov     edx, eax
0x18001a29b  mov     rax, [rbx+10h]
0x18001a29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2a4  mov     [rbx], rax
0x18001a2a7  test    rax, rax
0x18001a2aa  jnz     short loc_18001A2B6
0x18001a2ac  mov     [rbx+8], eax
0x18001a2af  mov     eax, 3EDh
0x18001a2b4  jmp     short loc_18001A2BF
0x18001a2b6  xor     eax, eax
0x18001a2b8  jmp     short loc_18001A2BF
0x18001a2ba  mov     eax, 3EAh
0x18001a2bf  add     rsp, 20h
0x18001a2c3  pop     rbx
0x18001a2c4  retn
```
