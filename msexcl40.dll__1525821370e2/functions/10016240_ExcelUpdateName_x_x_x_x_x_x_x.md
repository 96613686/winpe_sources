# ExcelUpdateName(x,x,x,x,x,x,x)

- ea: `0x10016240`
- end: `0x100163c6`
- name: `_ExcelUpdateName@28`
- size: `390`
- prototype: `int __fastcall(int, int, _WORD *, __int16, __int16, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1001d870`

## callees

- `0x1000bba0`
- `0x1000dcc0`
- `0x1000df70`
- `0x10012270`
- `0x10016240`
- `0x10025f86`
- `0x1002611f`

## pseudocode

```c
int __fastcall ExcelUpdateName(int a1, int a2, _WORD *a3, __int16 a4, __int16 a5, int a6, int a7)
{
  int v8; // ecx
  int result; // eax
  _WORD *v10; // esi
  int v11; // eax
  int v12; // edx
  int *v13; // ecx
  int *v14; // eax
  int v15; // eax
  int v16; // edi
  char *v17; // esi
  int v18; // ecx
  int v19; // eax
  int v20; // [esp+Ch] [ebp-8h] BYREF
  int v21; // [esp+10h] [ebp-4h] BYREF

  v8 = *(_DWORD *)(a1 + 40);
  v21 = a2;
  *(_DWORD *)(a1 + 44) = 1;
  if ( v8 )
  {
    result = ExcelMIUpdateName(a3, a4, a5, a6, a7);
    if ( result )
      return result;
    if ( *(_DWORD *)(a1 + 48) )
      return ExcelMIUpdateName(a3, a4, a5, a6, a7);
    return 0;
  }
  v10 = a3;
  v11 = 2147483646;
  v12 = 256;
  v13 = dword_1003A7A0;
  do
  {
    if ( !v11 )
      break;
    if ( !*v10 )
      break;
    *(_WORD *)v13 = *v10++;
    v13 = (int *)((char *)v13 + 2);
    --v11;
    --v12;
  }
  while ( v12 );
  v14 = (int *)((char *)v13 - 2);
  if ( v12 )
    v14 = v13;
  *(_WORD *)v14 = 0;
  dword_1003A788 = v21;
  result = ExcelScanFile((int *)a1, dword_10038180, 0);
  if ( result >= 0 )
  {
    if ( result != 1 )
      return -10;
    v15 = a1;
    if ( *(_DWORD *)a1 == 1 )
      v15 = *(_DWORD *)(a1 + 44);
    v16 = *(_DWORD *)(v15 + 88);
    BFSetFilePosition(*(int **)(a1 + 20), 0, v16);
    if ( ExcelReadRecordHeader(a1, (__int16 *)&v21) )
      return -10;
    result = ExcelReadTotalRecord(a1, &v21, &v20);
    if ( !result )
    {
      v17 = (char *)v20;
      v18 = v20 + *(unsigned __int8 *)(v20 + 3);
      *(_WORD *)v20 = a5 | a4 & *(_WORD *)v20;
      *(_WORD *)(v18 + 7) = a6;
      *(_WORD *)(v18 + 9) = a7;
      *(_BYTE *)(v18 + 11) = BYTE2(a6);
      *(_BYTE *)(v18 + 12) = BYTE2(a7);
      BFSetFilePosition(*(int **)(a1 + 20), 0, v16 + 4);
      v19 = BFWriteFile(*(_DWORD *)(a1 + 20), v17, SHIWORD(v21));
      if ( !v19 )
        return 0;
      result = dword_10001970[abs32(v19)];
      if ( result == -10 )
        return -10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10016240  mov     edi, edi
0x10016242  push    ebp
0x10016243  mov     ebp, esp
0x10016245  sub     esp, 8
0x10016248  push    ebx
0x10016249  mov     ebx, ecx
0x1001624b  push    esi
0x1001624c  mov     esi, edx
0x1001624e  push    edi
0x1001624f  mov     ecx, [ebx+28h]
0x10016252  mov     [ebp+var_4], esi
0x10016255  mov     dword ptr [ebx+2Ch], 1
0x1001625c  test    ecx, ecx
0x1001625e  jz      short loc_100162A6
0x10016260  mov     edi, [ebp+arg_10]
0x10016263  push    edi
0x10016264  push    [ebp+arg_C]
0x10016267  push    [ebp+arg_8]
0x1001626a  push    [ebp+arg_4]
0x1001626d  push    [ebp+arg_0]
0x10016270  call    _ExcelMIUpdateName@28; ExcelMIUpdateName(x,x,x,x,x,x,x)
0x10016275  test    eax, eax
0x10016277  jnz     loc_100163BD
0x1001627d  cmp     [ebx+30h], eax
0x10016280  jz      loc_100163BB
0x10016286  mov     ecx, [ebx+34h]
0x10016289  mov     edx, esi
0x1001628b  push    edi
0x1001628c  push    [ebp+arg_C]
0x1001628f  push    [ebp+arg_8]
0x10016292  push    [ebp+arg_4]
0x10016295  push    [ebp+arg_0]
0x10016298  call    _ExcelMIUpdateName@28; ExcelMIUpdateName(x,x,x,x,x,x,x)
0x1001629d  pop     edi
0x1001629e  pop     esi
0x1001629f  pop     ebx
0x100162a0  mov     esp, ebp
0x100162a2  pop     ebp
0x100162a3  retn    14h
0x100162a6  mov     esi, [ebp+arg_0]
0x100162a9  mov     eax, 7FFFFFFEh
0x100162ae  mov     edx, 100h
0x100162b3  mov     ecx, offset dword_1003A7A0
0x100162b8  test    eax, eax
0x100162ba  jz      short loc_100162D3
0x100162bc  movzx   edi, word ptr [esi]
0x100162bf  test    di, di
0x100162c2  jz      short loc_100162D3
0x100162c4  mov     [ecx], di
0x100162c7  add     esi, 2
0x100162ca  add     ecx, 2
0x100162cd  dec     eax
0x100162ce  sub     edx, 1
0x100162d1  jnz     short loc_100162B8
0x100162d3  lea     eax, [ecx-2]
0x100162d6  test    edx, edx
0x100162d8  mov     edx, offset dword_10038180
0x100162dd  cmovnz  eax, ecx
0x100162e0  xor     ecx, ecx
0x100162e2  push    ecx
0x100162e3  mov     [eax], cx
0x100162e6  mov     ecx, ebx
0x100162e8  mov     eax, [ebp+var_4]
0x100162eb  mov     dword_1003A788, eax
0x100162f0  call    _ExcelScanFile@12; ExcelScanFile(x,x,x)
0x100162f5  test    eax, eax
0x100162f7  js      loc_100163BD
0x100162fd  cmp     eax, 1
0x10016300  jz      short loc_10016310
0x10016302  mov     eax, 0FFFFFFF6h
0x10016307  pop     edi
0x10016308  pop     esi
0x10016309  pop     ebx
0x1001630a  mov     esp, ebp
0x1001630c  pop     ebp
0x1001630d  retn    14h
0x10016310  cmp     dword ptr [ebx], 1
0x10016313  mov     eax, ebx
0x10016315  jnz     short loc_1001631A
0x10016317  mov     eax, [ebx+2Ch]
0x1001631a  mov     edi, [eax+58h]
0x1001631d  xor     edx, edx
0x1001631f  mov     ecx, [ebx+14h]
0x10016322  push    edi
0x10016323  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10016328  lea     edx, [ebp+var_4]
0x1001632b  mov     ecx, ebx
0x1001632d  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10016332  test    eax, eax
0x10016334  jnz     short loc_10016302
0x10016336  lea     eax, [ebp+var_8]
0x10016339  mov     ecx, ebx
0x1001633b  push    eax
0x1001633c  lea     edx, [ebp+var_4]
0x1001633f  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x10016344  test    eax, eax
0x10016346  jnz     short loc_100163BD
0x10016348  mov     esi, [ebp+var_8]
0x1001634b  xor     edx, edx
0x1001634d  movzx   eax, word ptr [esi]
0x10016350  and     ax, word ptr [ebp+arg_4]
0x10016354  movzx   ecx, byte ptr [esi+3]
0x10016358  or      ax, word ptr [ebp+arg_8]
0x1001635c  add     ecx, esi
0x1001635e  mov     [esi], ax
0x10016361  mov     ax, word ptr [ebp+arg_C]
0x10016365  mov     [ecx+7], ax
0x10016369  mov     ax, word ptr [ebp+arg_10]
0x1001636d  mov     [ecx+9], ax
0x10016371  mov     al, byte ptr [ebp+arg_C+2]
0x10016374  mov     [ecx+0Bh], al
0x10016377  mov     al, byte ptr [ebp+arg_10+2]
0x1001637a  mov     [ecx+0Ch], al
0x1001637d  lea     eax, [edi+4]
0x10016380  mov     ecx, [ebx+14h]
0x10016383  push    eax
0x10016384  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10016389  movsx   eax, word ptr [ebp+var_4+2]
0x1001638d  mov     edx, esi
0x1001638f  mov     ecx, [ebx+14h]
0x10016392  push    eax
0x10016393  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016398  test    eax, eax
0x1001639a  jz      short loc_100163BB
0x1001639c  cdq
0x1001639d  mov     ecx, 0FFFFFFF6h
0x100163a2  xor     eax, edx
0x100163a4  sub     eax, edx
0x100163a6  mov     eax, ds:dword_10001970[eax*4]
0x100163ad  cmp     eax, ecx
0x100163af  cmovz   eax, ecx
0x100163b2  pop     edi
0x100163b3  pop     esi
0x100163b4  pop     ebx
0x100163b5  mov     esp, ebp
0x100163b7  pop     ebp
0x100163b8  retn    14h
0x100163bb  xor     eax, eax
0x100163bd  pop     edi
0x100163be  pop     esi
0x100163bf  pop     ebx
0x100163c0  mov     esp, ebp
0x100163c2  pop     ebp
0x100163c3  retn    14h
```
