# IsFullPath(ushort const *)

- ea: `0x180015138`
- end: `0x1800151de`
- name: `?IsFullPath@@YAHPEBG@Z`
- size: `166`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086c4`

## callees

- `0x180014f48`
- `0x180015138`

## pseudocode

```c
__int64 __fastcall IsFullPath(const unsigned __int16 *a1, unsigned __int64 a2)
{
  unsigned int v3; // ebx
  const unsigned __int16 *v4; // rax
  __int64 v5; // rcx
  _WORD *v6; // r11
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v3 = 1;
  if ( !a1 )
    goto LABEL_10;
  v4 = a1;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  a2 = 0x7FFFFFFF - v5;
  if ( !v5
    || ((0x7FFFFFFF - v5) & (unsigned __int64)-(__int64)(v5 != 0)) < 2
    || a1[1] != 58
    || (unsigned __int16)(*a1 - 97) > 0x19u && (unsigned __int16)(*a1 - 65) > 0x19u )
  {
LABEL_10:
    v8 = 0;
    if ( (int)StringCchLengthW(a1, a2, &v8) < 0 || v8 < 2 || *v6 != 92 || v6[1] != 92 )
      return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180015138  mov     [rsp+arg_8], rbx
0x18001513d  push    rdi
0x18001513e  sub     rsp, 20h
0x180015142  xor     edi, edi
0x180015144  mov     r11, rcx
0x180015147  mov     ebx, 1
0x18001514c  test    rcx, rcx
0x18001514f  jz      short loc_1800151A2
0x180015151  mov     edx, 7FFFFFFFh
0x180015156  mov     rax, r11
0x180015159  mov     ecx, edx
0x18001515b  cmp     [rax], di
0x18001515e  jz      short loc_180015169
0x180015160  add     rax, 2
0x180015164  sub     rcx, rbx
0x180015167  jnz     short loc_18001515B
0x180015169  sub     rdx, rcx; unsigned __int64
0x18001516c  mov     rax, rcx
0x18001516f  neg     rax
0x180015172  sbb     r8, r8
0x180015175  and     r8, rdx
0x180015178  test    rcx, rcx
0x18001517b  jz      short loc_1800151A2
0x18001517d  cmp     r8, 2
0x180015181  jb      short loc_1800151A2
0x180015183  cmp     word ptr [r11+2], 3Ah ; ':'
0x180015189  jnz     short loc_1800151A2
0x18001518b  movzx   ecx, word ptr [r11]
0x18001518f  lea     eax, [rcx-61h]
0x180015192  cmp     ax, 19h
0x180015196  jbe     short loc_1800151D1
0x180015198  sub     cx, 41h ; 'A'
0x18001519c  cmp     cx, 19h
0x1800151a0  jbe     short loc_1800151D1
0x1800151a2  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x1800151a7  mov     [rsp+28h+arg_0], rdi
0x1800151ac  mov     rcx, r11; unsigned __int16 *
0x1800151af  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800151b4  test    eax, eax
0x1800151b6  js      short loc_1800151CF
0x1800151b8  cmp     [rsp+28h+arg_0], 2
0x1800151be  jb      short loc_1800151CF
0x1800151c0  cmp     word ptr [r11], 5Ch ; '\'
0x1800151c5  jnz     short loc_1800151CF
0x1800151c7  cmp     word ptr [r11+2], 5Ch ; '\'
0x1800151cd  jz      short loc_1800151D1
0x1800151cf  mov     ebx, edi
0x1800151d1  mov     eax, ebx
0x1800151d3  mov     rbx, [rsp+28h+arg_8]
0x1800151d8  add     rsp, 20h
0x1800151dc  pop     rdi
0x1800151dd  retn
```
