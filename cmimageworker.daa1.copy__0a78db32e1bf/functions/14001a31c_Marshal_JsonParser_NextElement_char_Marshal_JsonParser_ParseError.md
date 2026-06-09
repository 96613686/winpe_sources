# Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)

- ea: `0x14001a31c`
- end: `0x14001a3bd`
- name: `?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z`
- size: `161`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010274`
- `0x140010724`
- `0x140010c74`
- `0x1400111d0`
- `0x14001a3c4`
- `0x14001e274`

## callees

- `0x140002d4e`
- `0x14001a31c`

## pseudocode

```c
char __fastcall Marshal::JsonParser::NextElement(_QWORD *a1, char a2, int a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v5; // r11
  int v6; // ecx
  char v7; // bl
  unsigned __int64 v8; // rax
  __int64 v9; // r8
  unsigned __int64 v10; // rdx
  bool v11; // cf
  char result; // al
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  v3 = a1[1];
  v5 = a1[2];
  if ( v5 >= v3 )
    v6 = -1;
  else
    v6 = *(unsigned __int16 *)(*a1 + 2 * v5);
  if ( v6 == a2 )
  {
    v7 = 0;
  }
  else
  {
    if ( v6 != 44 )
    {
      pExceptionObject = a3;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v7 = 1;
  }
  v8 = v3;
  v9 = 1;
  if ( v3 >= v5 + 1 )
    v8 = v5 + 1;
  a1[3] = v8;
  while ( 1 )
  {
    v10 = v5 + v9;
    v11 = v3 < v5 + v9;
    if ( v3 <= v5 + v9 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v10) != 9
      && *(_WORD *)(*a1 + 2 * v10) != 10
      && *(_WORD *)(*a1 + 2 * v10) != 13
      && *(_WORD *)(*a1 + 2 * v10) != 32 )
    {
      v11 = v3 < v10;
      break;
    }
    ++v9;
  }
  if ( !v11 )
    v3 = v5 + v9;
  result = v7;
  a1[2] = v3;
  return result;
}

```

## disassembly

```asm
0x14001a31c  push    rbx
0x14001a31e  sub     rsp, 20h
0x14001a322  mov     r9, [rcx+8]
0x14001a326  mov     r10, rcx
0x14001a329  mov     r11, [rcx+10h]
0x14001a32d  cmp     r11, r9
0x14001a330  jnb     short loc_14001A33C
0x14001a332  mov     rax, [rcx]
0x14001a335  movzx   ecx, word ptr [rax+r11*2]
0x14001a33a  jmp     short loc_14001A33F
0x14001a33c  or      ecx, 0FFFFFFFFh
0x14001a33f  movsx   eax, dl
0x14001a342  cmp     ecx, eax
0x14001a344  jnz     short loc_14001A34A
0x14001a346  xor     bl, bl
0x14001a348  jmp     short loc_14001A351
0x14001a34a  cmp     ecx, 2Ch ; ','
0x14001a34d  jnz     short loc_14001A3A6
0x14001a34f  mov     bl, 1
0x14001a351  lea     rcx, [r11+1]
0x14001a355  mov     rax, r9
0x14001a358  cmp     r9, rcx
0x14001a35b  mov     r8d, 1
0x14001a361  cmovnb  rax, rcx
0x14001a365  mov     [r10+18h], rax
0x14001a369  lea     rdx, [r11+r8]
0x14001a36d  cmp     r9, rdx
0x14001a370  jbe     short loc_14001A395
0x14001a372  mov     rax, [r10]
0x14001a375  movzx   ecx, word ptr [rax+rdx*2]
0x14001a379  sub     ecx, 9
0x14001a37c  jz      short loc_14001A38D
0x14001a37e  sub     ecx, 1
0x14001a381  jz      short loc_14001A38D
0x14001a383  sub     ecx, 3
0x14001a386  jz      short loc_14001A38D
0x14001a388  cmp     ecx, 13h
0x14001a38b  jnz     short loc_14001A392
0x14001a38d  inc     r8
0x14001a390  jmp     short loc_14001A369
0x14001a392  cmp     r9, rdx
0x14001a395  cmovnb  r9, rdx
0x14001a399  mov     al, bl
0x14001a39b  mov     [r10+10h], r9
0x14001a39f  add     rsp, 20h
0x14001a3a3  pop     rbx
0x14001a3a4  retn
0x14001a3a6  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001a3ad  mov     [rsp+28h+pExceptionObject], r8d
0x14001a3b2  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001a3b7  call    _CxxThrowException_0
```
