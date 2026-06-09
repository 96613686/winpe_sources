# CDataSource::ValidateStateForJetOpenDatabase(ulong &)

- ea: `0x1001a140`
- end: `0x1001a263`
- name: `?ValidateStateForJetOpenDatabase@CDataSource@@QAEJAAK@Z`
- size: `291`
- prototype: `int __thiscall(CDataSource *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10019070`
- `0x100198d0`
- `0x10028340`

## callees

- `0x1001a140`
- `0x1001f2d0`

## pseudocode

```c
int __thiscall CDataSource::ValidateStateForJetOpenDatabase(CDataSource *this, unsigned int *a2)
{
  const GUID *v2; // edx
  int v3; // ebx
  __int128 *v4; // edi
  unsigned int v5; // ecx
  bool v6; // cf
  unsigned int v7; // eax
  int v8; // ebx
  JoltProperties *v9; // edi
  int v10; // eax
  int v11; // ecx
  __int128 v13; // [esp+10h] [ebp-1Ch] BYREF
  unsigned int v14; // [esp+20h] [ebp-Ch] BYREF
  unsigned int v15; // [esp+24h] [ebp-8h] BYREF

  v2 = &DBPROPSET_DBINIT;
  v3 = *((_DWORD *)this + 40);
  v4 = &v13;
  v14 = (unsigned int)this;
  v5 = 12;
  v13 = *(_OWORD *)(v3 + 20);
  while ( v2->Data1 == *(_DWORD *)v4 )
  {
    v2 = (const GUID *)((char *)v2 + 4);
    v4 = (__int128 *)((char *)v4 + 4);
    v6 = v5 < 4;
    v5 -= 4;
    if ( v6 )
    {
      if ( JoltProperties::BinarySearch((JoltProperties *)v3, 0x3Fu, &v15) < 0 )
        v7 = v14;
      else
        v7 = 48 * v15 + 16 + *(_DWORD *)(v3 + 16);
      switch ( *(_DWORD *)(v7 + 8) )
      {
        case 1:
          *a2 = 1;
          v8 = 0;
          break;
        case 3:
        case 0x10:
        case 0x13:
          *a2 = 0;
          v8 = 0;
          break;
        case 8:
        case 0xD:
          *a2 = 3;
          v8 = 0;
          break;
        case 0xC:
          *a2 = 2;
          v8 = 0;
          break;
        default:
          v8 = 1;
          break;
      }
      v9 = *(JoltProperties **)(v14 + 164);
      if ( JoltProperties::BinarySearch(v9, 0x106u, &v14) >= 0
        && (v10 = *((_DWORD *)v9 + 4), *(_WORD *)(v10 + 48 * v14 + 16) == 3) )
      {
        v11 = 0;
        if ( *(_DWORD *)(v10 + 48 * v14 + 24) == 1 )
          *a2 |= 0x100u;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( v8 != 1 )
        return v11;
      break;
    }
  }
  *a2 = 0;
  return -2147467259;
}

```

## disassembly

```asm
0x1001a140  mov     edi, edi
0x1001a142  push    ebp
0x1001a143  mov     ebp, esp
0x1001a145  sub     esp, 20h
0x1001a148  mov     eax, ecx
0x1001a14a  mov     edx, offset _DBPROPSET_DBINIT
0x1001a14f  push    ebx
0x1001a150  push    esi
0x1001a151  push    edi
0x1001a152  mov     ebx, [eax+0A0h]
0x1001a158  lea     edi, [ebp+var_1C]
0x1001a15b  mov     [ebp+var_C], eax
0x1001a15e  mov     ecx, 0Ch
0x1001a163  movups  xmm0, xmmword ptr [ebx+14h]
0x1001a167  movups  [ebp+var_1C], xmm0
0x1001a16b  nop     dword ptr [eax+eax+00h]
0x1001a170  mov     eax, [edx]
0x1001a172  mov     esi, [ebp+arg_0]
0x1001a175  cmp     eax, [edi]
0x1001a177  jnz     loc_1001A24F
0x1001a17d  add     edx, 4
0x1001a180  add     edi, 4
0x1001a183  sub     ecx, 4
0x1001a186  jnb     short loc_1001A170
0x1001a188  lea     eax, [ebp+var_8]
0x1001a18b  mov     ecx, ebx; this
0x1001a18d  push    eax; unsigned int *
0x1001a18e  push    3Fh ; '?'; unsigned int
0x1001a190  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001a195  test    eax, eax
0x1001a197  js      short loc_1001A1AC
0x1001a199  mov     eax, [ebp+var_8]
0x1001a19c  lea     ecx, [eax+eax*2]
0x1001a19f  mov     eax, [ebx+10h]
0x1001a1a2  shl     ecx, 4
0x1001a1a5  add     ecx, 10h
0x1001a1a8  add     eax, ecx
0x1001a1aa  jmp     short loc_1001A1AF
0x1001a1ac  mov     eax, [ebp+var_C]
0x1001a1af  mov     eax, [eax+8]
0x1001a1b2  dec     eax; switch 19 cases
0x1001a1b3  cmp     eax, 12h
0x1001a1b6  ja      short def_1001A1BF; jumptable 1001A1BF default case, cases 2,4-7,9-11,14,15,17,18
0x1001a1b8  movzx   eax, ds:byte_1001A278[eax]
0x1001a1bf  jmp     ds:jpt_1001A1BF[eax*4]; switch jump
0x1001a1c6  mov     dword ptr [esi], 0; jumptable 1001A1BF cases 3,16,19
0x1001a1cc  xor     ebx, ebx
0x1001a1ce  jmp     short loc_1001A1F3
0x1001a1d0  mov     dword ptr [esi], 2; jumptable 1001A1BF case 12
0x1001a1d6  xor     ebx, ebx
0x1001a1d8  jmp     short loc_1001A1F3
0x1001a1da  mov     dword ptr [esi], 1; jumptable 1001A1BF case 1
0x1001a1e0  xor     ebx, ebx
0x1001a1e2  jmp     short loc_1001A1F3
0x1001a1e4  mov     dword ptr [esi], 3; jumptable 1001A1BF cases 8,13
0x1001a1ea  xor     ebx, ebx
0x1001a1ec  jmp     short loc_1001A1F3
0x1001a1ee  mov     ebx, 1; jumptable 1001A1BF default case, cases 2,4-7,9-11,14,15,17,18
0x1001a1f3  mov     edi, [ebp+var_C]
0x1001a1f6  lea     eax, [ebp+var_C]
0x1001a1f9  push    eax; unsigned int *
0x1001a1fa  push    106h; unsigned int
0x1001a1ff  mov     edi, [edi+0A4h]
0x1001a205  mov     ecx, edi; this
0x1001a207  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001a20c  test    eax, eax
0x1001a20e  js      short loc_1001A23A
0x1001a210  mov     eax, [ebp+var_C]
0x1001a213  mov     edx, 3
0x1001a218  lea     ecx, [eax+eax*2]
0x1001a21b  mov     eax, [edi+10h]
0x1001a21e  add     ecx, ecx
0x1001a220  cmp     dx, [eax+ecx*8+10h]
0x1001a225  jnz     short loc_1001A23A
0x1001a227  mov     eax, [eax+ecx*8+18h]
0x1001a22b  xor     ecx, ecx
0x1001a22d  sub     eax, 1
0x1001a230  jnz     short loc_1001A23F
0x1001a232  or      dword ptr [esi], 100h
0x1001a238  jmp     short loc_1001A23F
0x1001a23a  mov     ecx, 80004005h
0x1001a23f  cmp     ebx, 1
0x1001a242  jz      short loc_1001A24F
0x1001a244  mov     eax, ecx
0x1001a246  pop     edi
0x1001a247  pop     esi
0x1001a248  pop     ebx
0x1001a249  mov     esp, ebp
0x1001a24b  pop     ebp
0x1001a24c  retn    4
0x1001a24f  pop     edi
0x1001a250  mov     dword ptr [esi], 0
0x1001a256  mov     eax, 80004005h
0x1001a25b  pop     esi
0x1001a25c  pop     ebx
0x1001a25d  mov     esp, ebp
0x1001a25f  pop     ebp
0x1001a260  retn    4
```
