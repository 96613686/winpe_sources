# Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)

- ea: `0x140018068`
- end: `0x14001817e`
- name: `?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z`
- size: `278`
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
- `0x140018068`

## pseudocode

```c
char __fastcall Marshal::JsonParser::BeginAggregate(_QWORD *a1, char a2, char a3, int a4)
{
  unsigned __int64 v4; // r10
  int v5; // edi
  unsigned __int64 v6; // rbx
  int v8; // esi
  int v9; // ecx
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  unsigned __int64 v16; // rdx
  bool v17; // cf
  char result; // al
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  v4 = a1[1];
  v5 = -1;
  v6 = a1[2];
  v8 = a3;
  if ( v6 >= v4 )
    v9 = -1;
  else
    v9 = *(unsigned __int16 *)(*a1 + 2 * v6);
  if ( v9 != a2 )
  {
    pExceptionObject = a4;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v10 = v4;
  v11 = 1;
  if ( v4 >= v6 + 1 )
    v10 = v6 + 1;
  a1[3] = v10;
  while ( 1 )
  {
    v12 = v6 + v11;
    if ( v6 + v11 >= v4
      || *(_WORD *)(*a1 + 2 * v12) != 9
      && *(_WORD *)(*a1 + 2 * v12) != 10
      && *(_WORD *)(*a1 + 2 * v12) != 13
      && *(_WORD *)(*a1 + 2 * v12) != 32 )
    {
      break;
    }
    ++v11;
  }
  v13 = v4;
  if ( v4 >= v12 )
    v13 = v12;
  a1[2] = v13;
  if ( v13 < v4 )
    v5 = *(unsigned __int16 *)(*a1 + 2 * v13);
  if ( v5 != v8 )
    return 1;
  v14 = v4;
  v15 = 1;
  if ( v4 >= v13 + 1 )
    v14 = v13 + 1;
  a1[3] = v14;
  while ( 1 )
  {
    v16 = v13 + v15;
    v17 = v4 < v13 + v15;
    if ( v4 <= v13 + v15 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v16) != 9
      && *(_WORD *)(*a1 + 2 * v16) != 10
      && *(_WORD *)(*a1 + 2 * v16) != 13
      && *(_WORD *)(*a1 + 2 * v16) != 32 )
    {
      v17 = v4 < v16;
      break;
    }
    ++v15;
  }
  if ( !v17 )
    v4 = v13 + v15;
  result = 0;
  a1[2] = v4;
  return result;
}

```

## disassembly

```asm
0x140018068  mov     [rsp+arg_0], rbx
0x14001806d  mov     [rsp+arg_10], rsi
0x140018072  push    rdi
0x140018073  sub     rsp, 20h
0x140018077  mov     r10, [rcx+8]
0x14001807b  or      edi, 0FFFFFFFFh
0x14001807e  mov     rbx, [rcx+10h]
0x140018082  mov     r11, rcx
0x140018085  movsx   esi, r8b
0x140018089  cmp     rbx, r10
0x14001808c  jnb     short loc_140018097
0x14001808e  mov     rax, [rcx]
0x140018091  movzx   ecx, word ptr [rax+rbx*2]
0x140018095  jmp     short loc_140018099
0x140018097  mov     ecx, edi
0x140018099  movsx   eax, dl
0x14001809c  cmp     ecx, eax
0x14001809e  jnz     loc_140018167
0x1400180a4  lea     rcx, [rbx+1]
0x1400180a8  mov     rax, r10
0x1400180ab  cmp     r10, rcx
0x1400180ae  mov     r8d, 1
0x1400180b4  cmovnb  rax, rcx
0x1400180b8  mov     [r11+18h], rax
0x1400180bc  lea     rdx, [rbx+r8]
0x1400180c0  cmp     rdx, r10
0x1400180c3  jnb     short loc_1400180E5
0x1400180c5  mov     rax, [r11]
0x1400180c8  movzx   ecx, word ptr [rax+rdx*2]
0x1400180cc  sub     ecx, 9
0x1400180cf  jz      short loc_1400180E0
0x1400180d1  sub     ecx, 1
0x1400180d4  jz      short loc_1400180E0
0x1400180d6  sub     ecx, 3
0x1400180d9  jz      short loc_1400180E0
0x1400180db  cmp     ecx, 13h
0x1400180de  jnz     short loc_1400180E5
0x1400180e0  inc     r8
0x1400180e3  jmp     short loc_1400180BC
0x1400180e5  cmp     r10, rdx
0x1400180e8  mov     r8, r10
0x1400180eb  cmovnb  r8, rdx
0x1400180ef  mov     [r11+10h], r8
0x1400180f3  cmp     r8, r10
0x1400180f6  jnb     short loc_140018100
0x1400180f8  mov     rax, [r11]
0x1400180fb  movzx   edi, word ptr [rax+r8*2]
0x140018100  cmp     edi, esi
0x140018102  jnz     short loc_140018154
0x140018104  lea     rcx, [r8+1]
0x140018108  mov     rax, r10
0x14001810b  cmp     r10, rcx
0x14001810e  mov     r9d, 1
0x140018114  cmovnb  rax, rcx
0x140018118  mov     [r11+18h], rax
0x14001811c  lea     rdx, [r8+r9]
0x140018120  cmp     r10, rdx
0x140018123  jbe     short loc_140018148
0x140018125  mov     rax, [r11]
0x140018128  movzx   ecx, word ptr [rax+rdx*2]
0x14001812c  sub     ecx, 9
0x14001812f  jz      short loc_140018140
0x140018131  sub     ecx, 1
0x140018134  jz      short loc_140018140
0x140018136  sub     ecx, 3
0x140018139  jz      short loc_140018140
0x14001813b  cmp     ecx, 13h
0x14001813e  jnz     short loc_140018145
0x140018140  inc     r9
0x140018143  jmp     short loc_14001811C
0x140018145  cmp     r10, rdx
0x140018148  cmovnb  r10, rdx
0x14001814c  xor     al, al
0x14001814e  mov     [r11+10h], r10
0x140018152  jmp     short loc_140018156
0x140018154  mov     al, 1
0x140018156  mov     rbx, [rsp+28h+arg_0]
0x14001815b  mov     rsi, [rsp+28h+arg_10]
0x140018160  add     rsp, 20h
0x140018164  pop     rdi
0x140018165  retn
0x140018167  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001816e  mov     [rsp+28h+pExceptionObject], r9d
0x140018173  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140018178  call    _CxxThrowException_0
```
