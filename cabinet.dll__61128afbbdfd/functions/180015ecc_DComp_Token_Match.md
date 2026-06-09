# DComp_Token_Match

- ea: `0x180015ecc`
- end: `0x180015fa7`
- name: `DComp_Token_Match`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016288`

## callees

- `0x180015ecc`

## pseudocode

```c
__int64 __fastcall DComp_Token_Match(__int64 a1, __int64 a2)
{
  __int16 v3; // r10
  unsigned int v4; // ecx
  __int64 result; // rax
  char *v6; // r11
  char v7; // cl
  char *v8; // rcx

  v3 = a2;
  v4 = *(unsigned __int16 *)(a1 + 380);
  if ( v4 < (__int16)a2 )
  {
    *(_DWORD *)(a1 + 392) = 1;
    *(_WORD *)(a1 + 380) = 0;
  }
  else
  {
    result = (unsigned int)(*(_DWORD *)(a1 + 368) + (__int16)a2);
    v6 = (char *)(*(_QWORD *)(a1 + 344) + (*(_DWORD *)(a1 + 372) & (unsigned int)(*(_DWORD *)(a1 + 368) - HIDWORD(a2))));
    *(_DWORD *)(a1 + 368) = result;
    *(_WORD *)(a1 + 380) = v4 - a2;
    while ( v3 )
    {
      v7 = *v6;
      --v3;
      ++v6;
      **(_BYTE **)(a1 + 360) = v7;
      *(_BYTE *)(*(_QWORD *)(a1 + 384))++ = v7;
      v8 = *(char **)(a1 + 352);
      if ( v6 == v8 )
        v6 = *(char **)(a1 + 344);
      result = *(_QWORD *)(a1 + 360) + 1LL;
      *(_QWORD *)(a1 + 360) = result;
      if ( (char *)result == v8 )
      {
        result = *(_QWORD *)(a1 + 344);
        *(_QWORD *)(a1 + 360) = result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015ecc  mov     [rsp+arg_0], rbx
0x180015ed1  mov     [rsp+arg_8], rdx
0x180015ed6  mov     r9, rcx
0x180015ed9  movsx   r10d, word ptr [rsp+arg_8]
0x180015edf  movzx   ecx, word ptr [rcx+17Ch]
0x180015ee6  cmp     ecx, r10d
0x180015ee9  jb      loc_180015F8C
0x180015eef  mov     r8d, [r9+170h]
0x180015ef6  mov     r11d, r8d
0x180015ef9  mov     eax, [r9+174h]
0x180015f00  shr     rdx, 20h
0x180015f04  sub     r11d, edx
0x180015f07  and     r11, rax
0x180015f0a  lea     eax, [r8+r10]
0x180015f0e  add     r11, [r9+158h]
0x180015f15  sub     cx, r10w
0x180015f19  mov     [r9+170h], eax
0x180015f20  mov     [r9+17Ch], cx
0x180015f28  jmp     short loc_180015F84
0x180015f2a  mov     cl, [r11]
0x180015f2d  dec     r10w
0x180015f31  mov     rax, [r9+168h]
0x180015f38  inc     r11
0x180015f3b  mov     [rax], cl
0x180015f3d  mov     rax, [r9+180h]
0x180015f44  mov     [rax], cl
0x180015f46  inc     qword ptr [r9+180h]
0x180015f4d  mov     rcx, [r9+160h]
0x180015f54  cmp     r11, rcx
0x180015f57  jnz     short loc_180015F60
0x180015f59  mov     r11, [r9+158h]
0x180015f60  mov     rax, [r9+168h]
0x180015f67  inc     rax
0x180015f6a  mov     [r9+168h], rax
0x180015f71  cmp     rax, rcx
0x180015f74  jnz     short loc_180015F84
0x180015f76  mov     rax, [r9+158h]
0x180015f7d  mov     [r9+168h], rax
0x180015f84  test    r10w, r10w
0x180015f88  jnz     short loc_180015F2A
0x180015f8a  jmp     short loc_180015FA1
0x180015f8c  xor     edx, edx
0x180015f8e  mov     dword ptr [r9+188h], 1
0x180015f99  mov     [r9+17Ch], dx
0x180015fa1  mov     rbx, [rsp+arg_0]
0x180015fa6  retn
```
