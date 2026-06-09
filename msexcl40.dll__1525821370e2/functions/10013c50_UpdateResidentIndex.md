# UpdateResidentIndex

- ea: `0x10013c50`
- end: `0x10013d02`
- name: `UpdateResidentIndex`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10013d10`

## callees

- `0x10013c50`

## pseudocode

```c
void __fastcall UpdateResidentIndex(int a1, int a2, int a3, int a4, unsigned __int8 a5)
{
  int v5; // ebx
  int v6; // edi
  bool v7; // cc
  int v8; // ebx
  int v9; // eax
  int v10; // edi
  int i; // ecx
  int v12; // eax
  int v13; // edx
  bool v14; // sf
  bool v15; // of
  int v16; // eax
  int v17; // eax
  int v19; // [esp+8h] [ebp-8h]
  int v20; // [esp+Ch] [ebp-4h]

  v5 = *(_DWORD *)(a2 + 40);
  v20 = v5;
  if ( v5 )
  {
    v6 = 0;
    v7 = *(_WORD *)(v5 + 8) > 0;
    v8 = a3;
    v19 = 0;
    if ( v7 )
    {
      do
      {
        v9 = v20;
        v10 = *(_DWORD *)(v20 + 4 * v6 + 16);
        if ( v10 )
        {
          for ( i = 0; i != 640; i += 20 )
          {
            v12 = *(_DWORD *)(v10 + i + 24);
            if ( v12 >= v8 )
              *(_DWORD *)(v10 + i + 24) = a4 + v12;
            v13 = *(_DWORD *)(v10 + i + 20);
            v15 = __OFSUB__(v13, v8);
            v14 = v13 - v8 < 0;
            v8 = a3;
            if ( ((v14 == v15) & a5) != 0 )
              *(_DWORD *)(v10 + i + 20) = v13 + a4;
          }
          if ( *(int *)(a1 + 4) >= 5 )
          {
            v16 = *(_DWORD *)(v10 + 4);
            if ( v16 >= a3 )
              *(_DWORD *)(v10 + 4) = a4 + v16;
          }
          v9 = v20;
        }
        v6 = v19 + 1;
        v19 = v6;
      }
      while ( v6 < *(__int16 *)(v9 + 8) );
    }
    v17 = *(_DWORD *)(v20 + 12);
    if ( v17 >= v8 )
      *(_DWORD *)(v20 + 12) = a4 + v17;
  }
}

```

## disassembly

```asm
0x10013c50  mov     edi, edi
0x10013c52  push    ebp
0x10013c53  mov     ebp, esp
0x10013c55  sub     esp, 0Ch
0x10013c58  push    ebx
0x10013c59  mov     ebx, [edx+28h]
0x10013c5c  mov     [ebp+var_C], ecx
0x10013c5f  mov     [ebp+var_4], ebx
0x10013c62  test    ebx, ebx
0x10013c64  jz      loc_10013CFB
0x10013c6a  push    esi
0x10013c6b  mov     esi, [ebp+arg_4]
0x10013c6e  xor     eax, eax
0x10013c70  push    edi
0x10013c71  xor     edi, edi
0x10013c73  cmp     ax, [ebx+8]
0x10013c77  mov     ebx, [ebp+arg_0]
0x10013c7a  mov     [ebp+var_8], edi
0x10013c7d  jge     short loc_10013CEA
0x10013c7f  nop
0x10013c80  mov     eax, [ebp+var_4]
0x10013c83  mov     edi, [eax+edi*4+10h]
0x10013c87  test    edi, edi
0x10013c89  jz      short loc_10013CDB
0x10013c8b  xor     ecx, ecx
0x10013c8d  nop     dword ptr [eax]
0x10013c90  mov     eax, [edi+ecx+18h]
0x10013c94  cmp     eax, ebx
0x10013c96  jl      short loc_10013C9E
0x10013c98  add     eax, esi
0x10013c9a  mov     [edi+ecx+18h], eax
0x10013c9e  mov     edx, [edi+ecx+14h]
0x10013ca2  xor     eax, eax
0x10013ca4  cmp     edx, ebx
0x10013ca6  mov     ebx, [ebp+arg_0]
0x10013ca9  setnl   al
0x10013cac  test    [ebp+arg_8], eax
0x10013caf  jz      short loc_10013CB8
0x10013cb1  lea     eax, [edx+esi]
0x10013cb4  mov     [edi+ecx+14h], eax
0x10013cb8  add     ecx, 14h
0x10013cbb  cmp     ecx, 280h
0x10013cc1  jnz     short loc_10013C90
0x10013cc3  mov     eax, [ebp+var_C]
0x10013cc6  cmp     dword ptr [eax+4], 5
0x10013cca  jl      short loc_10013CD8
0x10013ccc  mov     eax, [edi+4]
0x10013ccf  cmp     eax, ebx
0x10013cd1  jl      short loc_10013CD8
0x10013cd3  add     eax, esi
0x10013cd5  mov     [edi+4], eax
0x10013cd8  mov     eax, [ebp+var_4]
0x10013cdb  mov     edi, [ebp+var_8]
0x10013cde  movsx   eax, word ptr [eax+8]
0x10013ce2  inc     edi
0x10013ce3  mov     [ebp+var_8], edi
0x10013ce6  cmp     edi, eax
0x10013ce8  jl      short loc_10013C80
0x10013cea  mov     edi, [ebp+var_4]
0x10013ced  mov     eax, [edi+0Ch]
0x10013cf0  cmp     eax, ebx
0x10013cf2  jl      short loc_10013CF9
0x10013cf4  add     eax, esi
0x10013cf6  mov     [edi+0Ch], eax
0x10013cf9  pop     edi
0x10013cfa  pop     esi
0x10013cfb  pop     ebx
0x10013cfc  mov     esp, ebp
0x10013cfe  pop     ebp
0x10013cff  retn    0Ch
```
