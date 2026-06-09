# TableCacheAdd

- ea: `0x10028429`
- end: `0x10028532`
- name: `TableCacheAdd`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10029730`

## callees

- `0x10006400`
- `0x1002580a`
- `0x100283fc`
- `0x10028429`

## pseudocode

```c
int __fastcall TableCacheAdd(int a1, int a2)
{
  _WORD *v2; // edi
  int result; // eax
  _WORD *v4; // ecx
  _WORD *v5; // edx
  unsigned int v7; // esi
  unsigned int v8; // ecx
  int v9; // eax
  _DWORD *v10; // ebx
  int *v11; // edi
  char *v12; // ecx
  int *v13; // edx
  __int16 v14; // ax
  unsigned int v15; // eax
  unsigned int v16; // ecx
  int v17; // eax
  _DWORD *v18; // esi
  unsigned int v20; // [esp+8h] [ebp-Ch]
  _DWORD *v22; // [esp+10h] [ebp-4h]

  v2 = (_WORD *)(a2 + 104);
  v22 = 0;
  result = TableCacheFind(*(_DWORD *)(a1 + 56), a2 + 104);
  if ( !result )
  {
    v4 = v2;
    v5 = v2 + 1;
    while ( *v4++ )
      ;
    v7 = 2 * (v4 - v5) + 2;
    v8 = 2 * (v4 - v5) + 18;
    if ( v8 >= v7 && (v9 = MemAllocate(v8), (v10 = (_DWORD *)v9) != 0) )
    {
      WCSCPY2((_WORD *)(v9 + 12), v2, v7 >> 1);
      v10[2] = *(_DWORD *)(a2 + 44);
      *v10 = *(_DWORD *)(a1 + 56);
      *(_DWORD *)(a1 + 56) = v10;
      v11 = *(int **)(a2 + 40);
      while ( v11 )
      {
        v12 = (char *)v11 + 42;
        v13 = v11 + 11;
        do
        {
          v14 = *(_WORD *)v12;
          v12 += 2;
        }
        while ( v14 );
        v15 = 2 * ((v12 - (char *)v13) >> 1) + 2;
        v16 = 2 * ((v12 - (char *)v13) >> 1) + 22;
        v20 = v15;
        if ( v16 < v15 )
          return 0;
        v17 = MemAllocate(v16);
        v18 = (_DWORD *)v17;
        if ( !v17 )
          return 0;
        *(_DWORD *)(v17 + 4) = v11[4];
        *(_DWORD *)(v17 + 8) = v11[2];
        *(_DWORD *)(v17 + 12) = v11[8];
        *(_BYTE *)(v17 + 16) = *((_BYTE *)v11 + 40);
        *(_BYTE *)(v17 + 17) = *((_BYTE *)v11 + 41);
        WCSCPY2((_WORD *)(v17 + 18), (_WORD *)v11 + 21, v20);
        if ( v22 )
          *v22 = v18;
        else
          v10[1] = v18;
        v11 = (int *)*v11;
        v22 = v18;
      }
      return (int)v10;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10028429  mov     edi, edi
0x1002842b  push    ebp
0x1002842c  mov     ebp, esp
0x1002842e  sub     esp, 0Ch
0x10028431  mov     eax, edx
0x10028433  mov     [ebp+var_C], ecx
0x10028436  mov     ecx, [ecx+38h]
0x10028439  push    ebx
0x1002843a  push    edi
0x1002843b  lea     edi, [eax+68h]
0x1002843e  mov     [ebp+var_8], eax
0x10028441  xor     ebx, ebx
0x10028443  mov     edx, edi
0x10028445  mov     [ebp+var_4], ebx
0x10028448  call    _TableCacheFind@8; TableCacheFind(x,x)
0x1002844d  test    eax, eax
0x1002844f  jnz     loc_1002852E
0x10028455  mov     ecx, edi
0x10028457  lea     edx, [ecx+2]
0x1002845a  mov     ax, [ecx]
0x1002845d  add     ecx, 2
0x10028460  cmp     ax, bx
0x10028463  jnz     short loc_1002845A
0x10028465  sub     ecx, edx
0x10028467  sar     ecx, 1
0x10028469  push    esi
0x1002846a  lea     esi, ds:2[ecx*2]
0x10028471  lea     ecx, [esi+10h]
0x10028474  cmp     ecx, esi
0x10028476  jb      loc_1002852B
0x1002847c  call    _MemAllocate@4; MemAllocate(x)
0x10028481  mov     ebx, eax
0x10028483  test    ebx, ebx
0x10028485  jz      loc_1002852B
0x1002848b  shr     esi, 1
0x1002848d  lea     ecx, [ebx+0Ch]
0x10028490  push    esi
0x10028491  mov     edx, edi
0x10028493  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10028498  mov     edi, [ebp+var_8]
0x1002849b  mov     ecx, [ebp+var_C]
0x1002849e  mov     eax, [edi+2Ch]
0x100284a1  mov     [ebx+8], eax
0x100284a4  mov     eax, [ecx+38h]
0x100284a7  mov     [ebx], eax
0x100284a9  mov     [ecx+38h], ebx
0x100284ac  mov     edi, [edi+28h]
0x100284af  jmp     short loc_10028523
0x100284b1  lea     ecx, [edi+2Ah]
0x100284b4  xor     esi, esi
0x100284b6  lea     edx, [ecx+2]
0x100284b9  mov     ax, [ecx]
0x100284bc  add     ecx, 2
0x100284bf  cmp     ax, si
0x100284c2  jnz     short loc_100284B9
0x100284c4  sub     ecx, edx
0x100284c6  sar     ecx, 1
0x100284c8  lea     eax, ds:2[ecx*2]
0x100284cf  lea     ecx, [eax+14h]
0x100284d2  mov     [ebp+var_C], eax
0x100284d5  cmp     ecx, eax
0x100284d7  jb      short loc_1002852B
0x100284d9  call    _MemAllocate@4; MemAllocate(x)
0x100284de  mov     esi, eax
0x100284e0  test    esi, esi
0x100284e2  jz      short loc_1002852B
0x100284e4  mov     ecx, [edi+10h]
0x100284e7  lea     edx, [edi+2Ah]
0x100284ea  push    [ebp+var_C]
0x100284ed  mov     [esi+4], ecx
0x100284f0  mov     ecx, [edi+8]
0x100284f3  mov     [esi+8], ecx
0x100284f6  mov     ecx, [edi+20h]
0x100284f9  mov     [esi+0Ch], ecx
0x100284fc  lea     ecx, [esi+12h]
0x100284ff  mov     al, [edi+28h]
0x10028502  mov     [esi+10h], al
0x10028505  mov     al, [edi+29h]
0x10028508  mov     [esi+11h], al
0x1002850b  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10028510  mov     eax, [ebp+var_4]
0x10028513  test    eax, eax
0x10028515  jnz     short loc_1002851C
0x10028517  mov     [ebx+4], esi
0x1002851a  jmp     short loc_1002851E
0x1002851c  mov     [eax], esi
0x1002851e  mov     edi, [edi]
0x10028520  mov     [ebp+var_4], esi
0x10028523  test    edi, edi
0x10028525  jnz     short loc_100284B1
0x10028527  mov     eax, ebx
0x10028529  jmp     short loc_1002852D
0x1002852b  xor     eax, eax
0x1002852d  pop     esi
0x1002852e  pop     edi
0x1002852f  pop     ebx
0x10028530  leave
0x10028531  retn
```
