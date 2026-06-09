# ExcelMISave(x,x)

- ea: `0x1000d760`
- end: `0x1000da21`
- name: `_ExcelMISave@8`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x10011730`

## callees

- `0x1000ca90`
- `0x1000d590`
- `0x1000d760`
- `0x10025b48`
- `0x10025df5`
- `0x10025f86`
- `0x1002611f`
- `0x10035b40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1000d9d3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1000d9d3`

## pseudocode

```c
int __fastcall ExcelMISave(int a1, _DWORD *a2)
{
  int v2; // edi
  _DWORD *v4; // ecx
  int v5; // eax
  int v6; // ecx
  int *v7; // eax
  int v8; // edi
  int *v9; // esi
  __int16 v10; // dx
  _DWORD *v11; // ecx
  int i; // eax
  bool v13; // zf
  bool v14; // cc
  int result; // eax
  size_t v16; // edx
  _WORD *v17; // esi
  __int16 v18; // cx
  bool v19; // sf
  __int16 v20; // cx
  __int16 v21; // ax
  char *v22; // esi
  int v23; // edi
  int v24; // eax
  int v25; // esi
  _DWORD *v26; // edi
  int v27; // eax
  int v28; // edi
  int v29; // ebx
  LONG v30; // edx
  void (__thiscall *v31)(_DWORD, _DWORD, LONG, LONG, _DWORD, _DWORD); // ecx
  const void *v32; // [esp-8h] [ebp-30h]
  __int16 v33; // [esp+Ch] [ebp-1Ch]
  int v34; // [esp+10h] [ebp-18h]
  int v35; // [esp+14h] [ebp-14h]
  __int16 v36; // [esp+18h] [ebp-10h] BYREF
  __int16 v37; // [esp+1Ah] [ebp-Eh]
  void *v38; // [esp+1Ch] [ebp-Ch]
  char *v39; // [esp+20h] [ebp-8h]
  int v40; // [esp+24h] [ebp-4h]

  v2 = a1;
  v40 = a1;
  BFSetFilePosition(*(int **)(a1 + 20), 0, 0);
  if ( *(_DWORD *)(v2 + 44) )
  {
    v4 = *(_DWORD **)(v2 + 20);
    v5 = v4[1];
    v4[22] = 0;
    v4[16] = 65000;
    v4[21] = 0;
    v4[20] = 0;
    *v4 = 0;
    v4[2] = v5;
    v6 = 0;
    v34 = 0;
    while ( 1 )
    {
      v7 = (int *)a2[1];
      v8 = 0;
      a2[6] = v6;
      a2[5] = 0;
      v39 = (char *)v7;
      v35 = 0;
      if ( v7 )
      {
        do
        {
          v9 = v7 + 1;
          v10 = *((_WORD *)v7 + 2);
          if ( v10 == 133 )
          {
            v11 = (_DWORD *)*a2;
            for ( i = 0; i < v8; ++i )
              v11 = (_DWORD *)*v11;
            v35 = ++v8;
            *((_DWORD *)v39 + 2) = v11[9];
          }
          v13 = a2[9] == 5;
          v14 = a2[9] <= 5;
          if ( (int)a2[9] > 5 )
          {
            if ( v10 == 10 )
            {
              result = WriteStringPool(v40, (int)a2);
              if ( result )
                return result;
            }
            v13 = a2[9] == 5;
            v14 = a2[9] <= 5;
          }
          if ( !v13 && (v14 || *(_WORD *)v9 == 23) )
          {
            v16 = g_cbCurrentSize;
            v38 = pExcelRecordBuffer;
            v36 = 23;
            v17 = *(_WORD **)(v40 + 80);
            v18 = 6 * *v17;
            v19 = (__int16)(v18 + 2) < 0;
            v20 = v18 + 2;
            v21 = v20;
            v33 = v20;
            v37 = v20;
            if ( v19 || (g_cbCurrentSize & 0x80000000) != 0 )
            {
              v22 = (char *)v38;
            }
            else
            {
              if ( v20 < (int)g_cbCurrentSize )
                v16 = v20;
              v32 = v17;
              v22 = (char *)v38;
              memcpy(v38, v32, v16);
              v21 = v33;
            }
            a2[5] += v21 + 4;
            if ( a2[6] == 1
              && ((v23 = v40, (v24 = BFWriteFile(*(_DWORD *)(v40 + 20), (char *)&v36, 4u)) != 0)
               || (v24 = BFWriteFile(*(_DWORD *)(v23 + 20), v22, v37)) != 0) )
            {
              v25 = dword_10001970[abs32(v24)];
              if ( v25 == -10 )
                v25 = -10;
              if ( v25 )
                return v25;
              v8 = v35;
            }
            else
            {
              v8 = v35;
            }
          }
          else
          {
            a2[5] += *((__int16 *)v9 + 1) + 4;
            if ( a2[6] == 1 )
            {
              v27 = BFWriteFile(*(_DWORD *)(v40 + 20), (char *)v9, 4u);
              if ( v27 || (v27 = BFWriteFile(*(_DWORD *)(v40 + 20), v39 + 8, *((__int16 *)v9 + 1))) != 0 )
              {
                v25 = dword_10001970[abs32(v27)];
                if ( v25 == -10 )
                  v25 = -10;
                if ( v25 )
                  return v25;
              }
            }
          }
          v7 = *(int **)v39;
          v39 = (char *)v7;
        }
        while ( v7 );
        v6 = v34;
      }
      v26 = (_DWORD *)*a2;
      if ( *a2 )
        break;
LABEL_36:
      v34 = ++v6;
      if ( v6 > 1 )
      {
        v2 = v40;
        goto LABEL_46;
      }
    }
    while ( 1 )
    {
      if ( !v6 )
        *(_QWORD *)(v26 + 3) = 0;
      v25 = WriteWorksheet(v26);
      if ( v25 )
        return v25;
      v26 = (_DWORD *)*v26;
      v6 = v34;
      if ( !v26 )
        goto LABEL_36;
    }
  }
  else
  {
LABEL_46:
    v28 = *(_DWORD *)(v2 + 20);
    v29 = 0;
    if ( (*(_DWORD *)(v28 + 92) != 1 || (v29 = WriteFileBlock(v28)) == 0) && *(_DWORD *)(v28 + 24) == 1 )
    {
      v30 = *(_DWORD *)(v28 + 88);
      if ( *(_DWORD *)(v28 + 12) )
      {
        v31 = *(void (__thiscall **)(_DWORD, _DWORD, LONG, LONG, _DWORD, _DWORD))(**(_DWORD **)(v28 + 32) + 20);
        v31(v31, *(_DWORD *)(v28 + 32), v30, v30 >> 31, 0, 0);
      }
      else
      {
        SetFilePointer(*(HANDLE *)(v28 + 20), v30, 0, 0);
      }
      OSWriteFile(0);
    }
    result = dword_10001970[abs32(v29)];
    if ( result == -10 )
      return -10;
  }
  return result;
}

```

## disassembly

```asm
0x1000d760  mov     edi, edi
0x1000d762  push    ebp
0x1000d763  mov     ebp, esp
0x1000d765  sub     esp, 1Ch
0x1000d768  push    ebx
0x1000d769  push    esi
0x1000d76a  push    edi
0x1000d76b  mov     edi, ecx
0x1000d76d  mov     ebx, edx
0x1000d76f  xor     esi, esi
0x1000d771  mov     [ebp+var_4], edi
0x1000d774  push    esi
0x1000d775  xor     edx, edx
0x1000d777  mov     ecx, [edi+14h]
0x1000d77a  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x1000d77f  cmp     [edi+2Ch], esi
0x1000d782  jz      loc_1000D9A4
0x1000d788  mov     ecx, [edi+14h]
0x1000d78b  mov     eax, [ecx+4]
0x1000d78e  mov     [ecx+58h], esi
0x1000d791  mov     dword ptr [ecx+40h], 0FDE8h
0x1000d798  mov     [ecx+54h], esi
0x1000d79b  mov     [ecx+50h], esi
0x1000d79e  mov     [ecx], esi
0x1000d7a0  mov     [ecx+8], eax
0x1000d7a3  xor     ecx, ecx
0x1000d7a5  mov     [ebp+var_18], ecx
0x1000d7a8  mov     eax, [ebx+4]
0x1000d7ab  xor     edi, edi
0x1000d7ad  mov     [ebx+18h], ecx
0x1000d7b0  mov     dword ptr [ebx+14h], 0
0x1000d7b7  mov     [ebp+var_8], eax
0x1000d7ba  mov     [ebp+var_14], edi
0x1000d7bd  test    eax, eax
0x1000d7bf  jz      loc_1000D8F7
0x1000d7c5  lea     esi, [eax+4]
0x1000d7c8  mov     ecx, 85h
0x1000d7cd  movzx   eax, word ptr [esi]
0x1000d7d0  mov     edx, eax
0x1000d7d2  cmp     ax, cx
0x1000d7d5  jnz     short loc_1000D7F4
0x1000d7d7  mov     ecx, [ebx]
0x1000d7d9  xor     eax, eax
0x1000d7db  test    edi, edi
0x1000d7dd  jle     short loc_1000D7E7
0x1000d7df  nop
0x1000d7e0  mov     ecx, [ecx]
0x1000d7e2  inc     eax
0x1000d7e3  cmp     eax, edi
0x1000d7e5  jl      short loc_1000D7E0
0x1000d7e7  mov     eax, [ecx+24h]
0x1000d7ea  inc     edi
0x1000d7eb  mov     ecx, [ebp+var_8]
0x1000d7ee  mov     [ebp+var_14], edi
0x1000d7f1  mov     [ecx+8], eax
0x1000d7f4  cmp     dword ptr [ebx+24h], 5
0x1000d7f8  jle     short loc_1000D816
0x1000d7fa  cmp     dx, 0Ah
0x1000d7fe  jnz     short loc_1000D812
0x1000d800  mov     ecx, [ebp+var_4]
0x1000d803  mov     edx, ebx
0x1000d805  call    WriteStringPool
0x1000d80a  test    eax, eax
0x1000d80c  jnz     loc_1000DA1A
0x1000d812  cmp     dword ptr [ebx+24h], 5
0x1000d816  jz      loc_1000D940
0x1000d81c  jle     short loc_1000D828
0x1000d81e  cmp     word ptr [esi], 17h
0x1000d822  jnz     loc_1000D940
0x1000d828  mov     eax, _pExcelRecordBuffer
0x1000d82d  mov     edx, _g_cbCurrentSize
0x1000d833  mov     [ebp+var_C], eax
0x1000d836  mov     eax, 17h
0x1000d83b  mov     [ebp+var_10], ax
0x1000d83f  mov     eax, [ebp+var_4]
0x1000d842  mov     esi, [eax+50h]
0x1000d845  mov     ax, [esi]
0x1000d848  mov     cx, ax
0x1000d84b  add     ax, ax
0x1000d84e  add     cx, ax
0x1000d851  add     cx, cx
0x1000d854  add     cx, 2
0x1000d858  movzx   eax, cx
0x1000d85b  movzx   edi, cx
0x1000d85e  mov     [ebp+var_1C], eax
0x1000d861  mov     [ebp+var_E], cx
0x1000d865  js      short loc_1000D888
0x1000d867  test    edx, edx
0x1000d869  js      short loc_1000D888
0x1000d86b  movsx   eax, cx
0x1000d86e  cmp     eax, edx
0x1000d870  jge     short loc_1000D875
0x1000d872  movsx   edx, di
0x1000d875  push    edx; Size
0x1000d876  push    esi; Src
0x1000d877  mov     esi, [ebp+var_C]
0x1000d87a  push    esi; void *
0x1000d87b  call    _memcpy
0x1000d880  mov     eax, [ebp+var_1C]
0x1000d883  add     esp, 0Ch
0x1000d886  jmp     short loc_1000D88B
0x1000d888  mov     esi, [ebp+var_C]
0x1000d88b  cwde
0x1000d88c  add     eax, 4
0x1000d88f  add     [ebx+14h], eax
0x1000d892  cmp     dword ptr [ebx+18h], 1
0x1000d896  jnz     short loc_1000D8DF
0x1000d898  mov     edi, [ebp+var_4]
0x1000d89b  lea     edx, [ebp+var_10]
0x1000d89e  push    4
0x1000d8a0  mov     ecx, [edi+14h]
0x1000d8a3  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000d8a8  test    eax, eax
0x1000d8aa  jnz     short loc_1000D8BF
0x1000d8ac  movsx   eax, [ebp+var_E]
0x1000d8b0  mov     edx, esi
0x1000d8b2  mov     ecx, [edi+14h]
0x1000d8b5  push    eax
0x1000d8b6  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000d8bb  test    eax, eax
0x1000d8bd  jz      short loc_1000D8DF
0x1000d8bf  cdq
0x1000d8c0  xor     eax, edx
0x1000d8c2  sub     eax, edx
0x1000d8c4  mov     esi, ds:dword_10001970[eax*4]
0x1000d8cb  cmp     esi, 0FFFFFFF6h
0x1000d8ce  mov     eax, 0FFFFFFF6h
0x1000d8d3  cmovz   esi, eax
0x1000d8d6  test    esi, esi
0x1000d8d8  jnz     short loc_1000D937
0x1000d8da  mov     edi, [ebp+var_14]
0x1000d8dd  jmp     short loc_1000D8E4
0x1000d8df  mov     edi, [ebp+var_14]
0x1000d8e2  xor     esi, esi
0x1000d8e4  mov     eax, [ebp+var_8]
0x1000d8e7  mov     eax, [eax]
0x1000d8e9  mov     [ebp+var_8], eax
0x1000d8ec  test    eax, eax
0x1000d8ee  jnz     loc_1000D7C5
0x1000d8f4  mov     ecx, [ebp+var_18]
0x1000d8f7  mov     edi, [ebx]
0x1000d8f9  test    edi, edi
0x1000d8fb  jz      short loc_1000D926
0x1000d8fd  nop     dword ptr [eax]
0x1000d900  test    ecx, ecx
0x1000d902  jnz     short loc_1000D90C
0x1000d904  xorps   xmm0, xmm0
0x1000d907  movq    qword ptr [edi+0Ch], xmm0
0x1000d90c  mov     ecx, [ebp+var_4]
0x1000d90f  mov     edx, ebx
0x1000d911  push    edi
0x1000d912  call    WriteWorksheet
0x1000d917  mov     esi, eax
0x1000d919  test    esi, esi
0x1000d91b  jnz     short loc_1000D937
0x1000d91d  mov     edi, [edi]
0x1000d91f  mov     ecx, [ebp+var_18]
0x1000d922  test    edi, edi
0x1000d924  jnz     short loc_1000D900
0x1000d926  inc     ecx
0x1000d927  mov     [ebp+var_18], ecx
0x1000d92a  cmp     ecx, 1
0x1000d92d  jle     loc_1000D7A8
0x1000d933  test    esi, esi
0x1000d935  jz      short loc_1000D9A1
0x1000d937  mov     eax, esi
0x1000d939  pop     edi
0x1000d93a  pop     esi
0x1000d93b  pop     ebx
0x1000d93c  mov     esp, ebp
0x1000d93e  pop     ebp
0x1000d93f  retn
0x1000d940  movsx   eax, word ptr [esi+2]
0x1000d944  add     eax, 4
0x1000d947  add     [ebx+14h], eax
0x1000d94a  cmp     dword ptr [ebx+18h], 1
0x1000d94e  jnz     short loc_1000D8E2
0x1000d950  mov     eax, [ebp+var_4]
0x1000d953  mov     edx, esi
0x1000d955  push    4
0x1000d957  mov     ecx, [eax+14h]
0x1000d95a  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000d95f  test    eax, eax
0x1000d961  jnz     short loc_1000D981
0x1000d963  movsx   eax, word ptr [esi+2]
0x1000d967  mov     edx, [ebp+var_8]
0x1000d96a  push    eax
0x1000d96b  mov     eax, [ebp+var_4]
0x1000d96e  lea     edx, [edx+8]
0x1000d971  mov     ecx, [eax+14h]
0x1000d974  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000d979  test    eax, eax
0x1000d97b  jz      loc_1000D8E2
0x1000d981  cdq
0x1000d982  xor     eax, edx
0x1000d984  sub     eax, edx
0x1000d986  mov     esi, ds:dword_10001970[eax*4]
0x1000d98d  cmp     esi, 0FFFFFFF6h
0x1000d990  mov     eax, 0FFFFFFF6h
0x1000d995  cmovz   esi, eax
0x1000d998  test    esi, esi
0x1000d99a  jnz     short loc_1000D937
0x1000d99c  jmp     loc_1000D8E4
0x1000d9a1  mov     edi, [ebp+var_4]
0x1000d9a4  mov     edi, [edi+14h]
0x1000d9a7  xor     ebx, ebx
0x1000d9a9  cmp     dword ptr [edi+5Ch], 1
0x1000d9ad  jnz     short loc_1000D9BC
0x1000d9af  mov     ecx, edi
0x1000d9b1  call    WriteFileBlock
0x1000d9b6  mov     ebx, eax
0x1000d9b8  test    ebx, ebx
0x1000d9ba  jnz     short loc_1000DA01
0x1000d9bc  cmp     dword ptr [edi+18h], 1
0x1000d9c0  jnz     short loc_1000DA01
0x1000d9c2  cmp     dword ptr [edi+0Ch], 0
0x1000d9c6  mov     edx, [edi+58h]
0x1000d9c9  push    0; dwMoveMethod
0x1000d9cb  push    0; lpDistanceToMoveHigh
0x1000d9cd  jnz     short loc_1000D9DB
0x1000d9cf  push    edx; lDistanceToMove
0x1000d9d0  push    dword ptr [edi+14h]; hFile
0x1000d9d3  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1000d9d9  jmp     short loc_1000D9F5
0x1000d9db  mov     eax, [edi+20h]
0x1000d9de  mov     ecx, edx
0x1000d9e0  sar     ecx, 1Fh
0x1000d9e3  push    ecx
0x1000d9e4  push    edx
0x1000d9e5  mov     esi, [eax]
0x1000d9e7  push    eax
0x1000d9e8  mov     esi, [esi+14h]
0x1000d9eb  mov     ecx, esi
0x1000d9ed  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000d9f3  call    esi
0x1000d9f5  mov     edx, [edi+4]
0x1000d9f8  mov     ecx, edi
0x1000d9fa  push    0; nNumberOfBytesToWrite
0x1000d9fc  call    OSWriteFile
0x1000da01  mov     eax, ebx
0x1000da03  mov     ecx, 0FFFFFFF6h
0x1000da08  cdq
0x1000da09  xor     eax, edx
0x1000da0b  sub     eax, edx
0x1000da0d  mov     eax, ds:dword_10001970[eax*4]
0x1000da14  cmp     eax, 0FFFFFFF6h
0x1000da17  cmovz   eax, ecx
0x1000da1a  pop     edi
0x1000da1b  pop     esi
0x1000da1c  pop     ebx
0x1000da1d  mov     esp, ebp
0x1000da1f  pop     ebp
0x1000da20  retn
```
