# ValidateStateForJetCompact(CDBInitProperties *,ulong &)

- ea: `0x100202a0`
- end: `0x100203f8`
- name: `?ValidateStateForJetCompact@@YGJPAVCDBInitProperties@@AAK@Z`
- size: `344`
- prototype: `int __cdecl(struct CDBInitProperties *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1001ebc0`

## callees

- `0x1001f2d0`
- `0x100202a0`

## pseudocode

```c
int __fastcall ValidateStateForJetCompact(int a1, int *a2)
{
  JoltProperties *v3; // esi
  unsigned int v5; // eax
  int v6; // esi
  JoltProperties *v7; // ebx
  unsigned int v8; // eax
  JoltProperties *v9; // ebx
  unsigned int v10; // eax
  JoltProperties *v11; // ebx
  unsigned int v12; // eax
  unsigned int v14; // [esp+Ch] [ebp-8h] BYREF
  int v15; // [esp+10h] [ebp-4h]

  v3 = *(JoltProperties **)(a1 + 12);
  v15 = a1;
  if ( JoltProperties::BinarySearch(v3, 0x103u, &v14) < 0 )
    v5 = 0;
  else
    v5 = *((_DWORD *)v3 + 4) + 48 * v14;
  *a2 = 0;
  if ( (*(_DWORD *)(v5 + 40) & 1) != 0 )
  {
    v6 = 0;
    switch ( *(_DWORD *)(v5 + 24) )
    {
      case 1:
        *a2 = 24;
        v6 = 24;
        break;
      case 2:
        *a2 = 16;
        v6 = 16;
        break;
      case 3:
        *a2 = 32;
        v6 = 32;
        break;
      case 4:
        *a2 = 64;
        v6 = 64;
        break;
      default:
        break;
    }
  }
  else
  {
    *a2 = 4096;
    v6 = 4096;
  }
  v7 = *(JoltProperties **)(a1 + 12);
  if ( JoltProperties::BinarySearch(v7, 0x10Fu, &v14) < 0 )
    v8 = 0;
  else
    v8 = *((_DWORD *)v7 + 4) + 48 * v14;
  if ( (*(_DWORD *)(v8 + 40) & 1) != 0 )
  {
    if ( *(_WORD *)(v8 + 24) == 0xFFFF )
      v6 |= 1u;
    else
      v6 |= 2u;
    *a2 = v6;
  }
  v9 = *(JoltProperties **)(v15 + 12);
  if ( JoltProperties::BinarySearch(v9, 0x110u, &v14) < 0 )
    v10 = 0;
  else
    v10 = *((_DWORD *)v9 + 4) + 48 * v14;
  if ( *(_WORD *)(v10 + 24) == 0xFFFF )
  {
    v6 |= 4u;
    *a2 = v6;
  }
  v11 = *(JoltProperties **)(v15 + 12);
  if ( JoltProperties::BinarySearch(v11, 0x112u, &v14) < 0 )
    v12 = 0;
  else
    v12 = *((_DWORD *)v11 + 4) + 48 * v14;
  if ( *(_WORD *)(v12 + 24) == 0xFFFF )
    *a2 = v6 | 0x200;
  return 0;
}

```

## disassembly

```asm
0x100202a0  mov     edi, edi
0x100202a2  push    ebp
0x100202a3  mov     ebp, esp
0x100202a5  sub     esp, 8
0x100202a8  push    ebx
0x100202a9  push    esi
0x100202aa  mov     ebx, ecx
0x100202ac  lea     eax, [ebp+var_8]
0x100202af  push    edi
0x100202b0  push    eax; unsigned int *
0x100202b1  push    103h; unsigned int
0x100202b6  mov     esi, [ebx+0Ch]
0x100202b9  mov     edi, edx
0x100202bb  mov     ecx, esi; this
0x100202bd  mov     [ebp+var_4], ebx
0x100202c0  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100202c5  test    eax, eax
0x100202c7  js      short loc_100202D7
0x100202c9  mov     eax, [ebp+var_8]
0x100202cc  lea     eax, [eax+eax*2]
0x100202cf  shl     eax, 4
0x100202d2  add     eax, [esi+10h]
0x100202d5  jmp     short loc_100202D9
0x100202d7  xor     eax, eax
0x100202d9  mov     dword ptr [edi], 0
0x100202df  test    dword ptr [eax+28h], 1
0x100202e6  jz      short loc_1002032E
0x100202e8  mov     eax, [eax+18h]
0x100202eb  xor     esi, esi
0x100202ed  dec     eax; switch 4 cases
0x100202ee  cmp     eax, 3
0x100202f1  ja      short def_100202F3; jumptable 100202F3 default case
0x100202f3  jmp     ds:jpt_100202F3[eax*4]; switch jump
0x100202fa  mov     dword ptr [edi], 18h; jumptable 100202F3 case 1
0x10020300  mov     esi, 18h
0x10020305  jmp     short def_100202F3; jumptable 100202F3 default case
0x10020307  mov     dword ptr [edi], 10h; jumptable 100202F3 case 2
0x1002030d  mov     esi, 10h
0x10020312  jmp     short def_100202F3; jumptable 100202F3 default case
0x10020314  mov     dword ptr [edi], 20h ; ' '; jumptable 100202F3 case 3
0x1002031a  mov     esi, 20h ; ' '
0x1002031f  jmp     short def_100202F3; jumptable 100202F3 default case
0x10020321  mov     dword ptr [edi], 40h ; '@'; jumptable 100202F3 case 4
0x10020327  mov     esi, 40h ; '@'
0x1002032c  jmp     short def_100202F3; jumptable 100202F3 default case
0x1002032e  mov     dword ptr [edi], 1000h
0x10020334  mov     esi, 1000h
0x10020339  mov     ebx, [ebx+0Ch]; jumptable 100202F3 default case
0x1002033c  lea     eax, [ebp+var_8]
0x1002033f  push    eax; unsigned int *
0x10020340  push    10Fh; unsigned int
0x10020345  mov     ecx, ebx; this
0x10020347  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1002034c  test    eax, eax
0x1002034e  js      short loc_1002035E
0x10020350  mov     eax, [ebp+var_8]
0x10020353  lea     eax, [eax+eax*2]
0x10020356  shl     eax, 4
0x10020359  add     eax, [ebx+10h]
0x1002035c  jmp     short loc_10020360
0x1002035e  xor     eax, eax
0x10020360  or      ecx, 0FFFFFFFFh
0x10020363  test    dword ptr [eax+28h], 1
0x1002036a  jz      short loc_1002037C
0x1002036c  cmp     cx, [eax+18h]
0x10020370  jnz     short loc_10020377
0x10020372  or      esi, 1
0x10020375  jmp     short loc_1002037A
0x10020377  or      esi, 2
0x1002037a  mov     [edi], esi
0x1002037c  mov     ebx, [ebp+var_4]
0x1002037f  lea     eax, [ebp+var_8]
0x10020382  push    eax; unsigned int *
0x10020383  push    110h; unsigned int
0x10020388  mov     ebx, [ebx+0Ch]
0x1002038b  mov     ecx, ebx; this
0x1002038d  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10020392  test    eax, eax
0x10020394  js      short loc_100203A4
0x10020396  mov     eax, [ebp+var_8]
0x10020399  lea     eax, [eax+eax*2]
0x1002039c  shl     eax, 4
0x1002039f  add     eax, [ebx+10h]
0x100203a2  jmp     short loc_100203A6
0x100203a4  xor     eax, eax
0x100203a6  or      ecx, 0FFFFFFFFh
0x100203a9  cmp     cx, [eax+18h]
0x100203ad  jnz     short loc_100203B4
0x100203af  or      esi, 4
0x100203b2  mov     [edi], esi
0x100203b4  mov     eax, [ebp+var_4]
0x100203b7  mov     ebx, [eax+0Ch]
0x100203ba  lea     eax, [ebp+var_8]
0x100203bd  push    eax; unsigned int *
0x100203be  push    112h; unsigned int
0x100203c3  mov     ecx, ebx; this
0x100203c5  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100203ca  test    eax, eax
0x100203cc  js      short loc_100203DC
0x100203ce  mov     eax, [ebp+var_8]
0x100203d1  lea     eax, [eax+eax*2]
0x100203d4  shl     eax, 4
0x100203d7  add     eax, [ebx+10h]
0x100203da  jmp     short loc_100203DE
0x100203dc  xor     eax, eax
0x100203de  or      ecx, 0FFFFFFFFh
0x100203e1  cmp     cx, [eax+18h]
0x100203e5  jnz     short loc_100203EF
0x100203e7  or      esi, 200h
0x100203ed  mov     [edi], esi
0x100203ef  pop     edi
0x100203f0  pop     esi
0x100203f1  xor     eax, eax
0x100203f3  pop     ebx
0x100203f4  mov     esp, ebp
0x100203f6  pop     ebp
0x100203f7  retn
```
