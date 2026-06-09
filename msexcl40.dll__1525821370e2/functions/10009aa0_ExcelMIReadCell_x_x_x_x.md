# ExcelMIReadCell(x,x,x,x)

- ea: `0x10009aa0`
- end: `0x10009f49`
- name: `_ExcelMIReadCell@16`
- size: `1193`
- prototype: `int __fastcall(int, int, int, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10013490`

## callees

- `0x10006400`
- `0x10007350`
- `0x100098e0`
- `0x10009aa0`
- `0x1000fa20`
- `0x1002580a`
- `0x10025ab7`
- `0x1002ec67`
- `0x10035f40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10009e0e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10009e0e`

## pseudocode

```c
int __fastcall ExcelMIReadCell(int a1, int a2, int a3, _WORD *a4)
{
  unsigned __int8 *v4; // edi
  _WORD *v5; // eax
  int *v6; // ecx
  unsigned __int16 v7; // dx
  _DWORD *v8; // ecx
  int v9; // eax
  int v10; // eax
  int result; // eax
  int v12; // eax
  int *v13; // eax
  int v14; // edi
  int v15; // eax
  int v16; // esi
  int v17; // eax
  const void *v18; // ecx
  int v19; // eax
  WCHAR *v20; // ebx
  char v21; // dl
  int v22; // eax
  _WORD *v23; // esi
  bool v24; // zf
  int v25; // esi
  WCHAR *v26; // edi
  int v27; // eax
  UINT v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // esi
  int *v31; // edi
  unsigned int v32; // eax
  int v33; // eax
  const void *v34; // [esp+10h] [ebp-18h] BYREF
  _WORD *v35; // [esp+14h] [ebp-14h] BYREF
  __int64 v36; // [esp+18h] [ebp-10h] BYREF
  int v37; // [esp+24h] [ebp-4h]

  HIDWORD(v36) = a2;
  v4 = 0;
  v37 = a1;
  v5 = (_WORD *)(a2 + 40);
  while ( 2 )
  {
    v35 = v5;
    memset(a4, 0, 0x30u);
    v6 = *(int **)(HIDWORD(v36) + 44);
    if ( !v6 || *v35 != (_WORD)a3 || (v7 = HIWORD(a3), *(_WORD *)(HIDWORD(v36) + 42) > HIWORD(a3)) )
    {
      v8 = *(_DWORD **)(HIDWORD(v36) + 28);
      if ( v8 )
      {
        v9 = *(_DWORD *)(*(_DWORD *)(HIDWORD(v36) + 32) + 4);
        if ( (unsigned __int16)a3 < v9 || (unsigned __int16)a3 >= v9 + 32 )
        {
          while ( 1 )
          {
            v10 = v8[1];
            if ( (unsigned __int16)a3 < v10 || (unsigned __int16)a3 < v10 + 32 )
              break;
            v8 = (_DWORD *)*v8;
            if ( !v8 )
              return 2;
          }
          *(_DWORD *)(HIDWORD(v36) + 32) = v8;
        }
        else
        {
          v8 = *(_DWORD **)(HIDWORD(v36) + 32);
        }
        if ( v8 )
        {
          v12 = v8[1];
          if ( (unsigned __int16)a3 >= v12 )
          {
            v4 = (unsigned __int8 *)v8[(unsigned __int16)a3 - v12 + 2];
            if ( v4 )
            {
              v7 = HIWORD(a3);
              if ( (unsigned int)HIWORD(a3) >= *v4 && (unsigned int)HIWORD(a3) <= v4[1] )
              {
                v6 = (int *)*((_DWORD *)v4 + 4);
                if ( v6 )
                  goto LABEL_20;
              }
            }
          }
        }
      }
      return 2;
    }
LABEL_20:
    while ( *((unsigned __int8 *)v6 + 6) != v7 )
    {
      v6 = (int *)*v6;
      if ( !v6 )
        return 2;
    }
    *(_DWORD *)v35 = a3;
    *(_DWORD *)(HIDWORD(v36) + 44) = v6;
    *((_DWORD *)a4 + 1) = *((__int16 *)v6 + 2);
    switch ( *((_BYTE *)v6 + 7) )
    {
      case 1:
        goto LABEL_48;
      case 2:
        if ( *((_BYTE *)v6 + 9) )
        {
          *a4 = 8;
          *((_DWORD *)a4 + 4) = ExcelConvertToOurErrorCode(*((unsigned __int8 *)v6 + 8));
        }
        else
        {
          *a4 = 4;
          *((_DWORD *)a4 + 4) = *((_BYTE *)v6 + 8) != 0;
        }
        return 0;
      case 3:
        if ( *((_WORD *)v6 + 7) != 0xFFFF )
        {
          *a4 = 258;
          result = 0;
          *((_QWORD *)a4 + 2) = *((_QWORD *)v6 + 1);
          return result;
        }
        switch ( *((_BYTE *)v6 + 8) )
        {
          case 0:
            v34 = (const void *)*((unsigned __int8 *)v6 + 8);
            *a4 = 272;
            if ( v4 )
            {
              v13 = (int *)*((_DWORD *)v4 + 2);
              if ( v13 )
              {
                while ( __PAIR32__(v7, a3) != v13[1] || *((_WORD *)v13 + 4) != 519 )
                {
                  v13 = (int *)*v13;
                  if ( !v13 )
                    goto LABEL_32;
                }
              }
              else
              {
LABEL_32:
                v13 = 0;
              }
              v14 = v37;
              v15 = ExcelExtractContinueString(*(_DWORD *)(v37 + 36), *(_DWORD *)(v37 + 44), (int **)v13, &v34);
              v16 = v15;
              if ( v15 < 0 )
              {
                MemFree(v34);
                return v16;
              }
              v17 = TextStoragePut(*(_DWORD *)(v14 + 40), v34, (unsigned int)v15 >> 1, 1);
              v18 = v34;
              *((_DWORD *)a4 + 4) = v17;
              MemFree(v18);
              if ( *((_DWORD *)a4 + 4) == -1 )
                return -2;
              return 0;
            }
            *(_DWORD *)(HIDWORD(v36) + 44) = 0;
            v5 = v35;
            continue;
          case 1:
            *a4 = 260;
            *((_DWORD *)a4 + 4) = *((unsigned __int8 *)v6 + 10);
            return 0;
          case 2:
            *a4 = 264;
            *((_DWORD *)a4 + 4) = ExcelConvertToOurErrorCode(*((unsigned __int8 *)v6 + 10));
            return 0;
          default:
            return 0;
        }
      case 4:
      case 7:
        v19 = v6[2];
        if ( !v19 || v19 == -1 )
        {
          v20 = &WideCharStr;
        }
        else
        {
          v20 = (WCHAR *)(v19 + 14);
          v21 = *(_BYTE *)(v19 + 12);
          if ( (v21 & 0xF3) == 1 )
          {
            v22 = TextStoragePut(*(_DWORD *)(v37 + 40), v20, wcslen(v20), v21);
            v23 = a4;
            v24 = v22 == -1;
            *((_DWORD *)a4 + 4) = v22;
            goto LABEL_74;
          }
          if ( (v21 & 0xF3) != 0 )
          {
            v25 = strlen((const char *)v20);
            if ( 2 * v25 <= 512 )
            {
              v26 = &ExcelRecordTextBuffer;
              v27 = 512;
            }
            else
            {
              v26 = (WCHAR *)MemAllocate(2 * v25 + 2);
              if ( !v26 )
                return -2;
              v27 = 2 * v25;
            }
            v28 = *(_DWORD *)(v37 + 44);
            if ( v28 == 1200 )
              v29 = MultiByteToWideChar(0, 0, (LPCCH)v20, v25, v26, v27);
            else
              v29 = MultiByteToWideChar(v28, 0, (LPCCH)v20, v25, v26, v27);
            v23 = a4;
            *((_DWORD *)a4 + 4) = TextStoragePut(*(_DWORD *)(v37 + 40), v26, v29, 1);
            if ( v26 != &ExcelRecordTextBuffer )
              MemFree(v26);
            if ( *((_DWORD *)a4 + 4) == -1 )
              return -2;
            goto LABEL_75;
          }
        }
        v30 = wcslen(v20);
        if ( (int)(2 * v30) <= 512 )
        {
          v31 = UnicodeExpansionBuffer;
          v32 = 512;
        }
        else
        {
          v31 = (int *)MemAllocate(2 * v30 + 2);
          if ( !v31 )
            return -2;
          v32 = v30 + 1;
        }
        WCSCPY2(v31, v20, v32);
        v33 = TextStoragePut(*(_DWORD *)(v37 + 40), v31, v30, 1);
        v23 = a4;
        *((_DWORD *)a4 + 4) = v33;
        if ( v31 != UnicodeExpansionBuffer )
          MemFree(v31);
        v24 = *((_DWORD *)a4 + 4) == -1;
LABEL_74:
        if ( v24 )
          return -2;
LABEL_75:
        *v23 = 16;
        return 0;
      case 5:
        *a4 = 2;
        result = 0;
        *((_QWORD *)a4 + 2) = *((_QWORD *)v6 + 1);
        return result;
      case 6:
        *a4 = 2;
        ExcelConvertRK(&v36, &v35);
        if ( v34 )
        {
          result = 0;
          *((double *)a4 + 2) = (double)(int)v35;
          return result;
        }
        *((_QWORD *)a4 + 2) = v36;
        return 0;
      case 8:
      case 9:
        if ( v6[2] )
        {
          *a4 = 16;
          *((_DWORD *)a4 + 4) = v6[2];
          return 0;
        }
        else
        {
LABEL_48:
          *a4 = 1;
          return 0;
        }
      default:
        return 0;
    }
  }
}

```

## disassembly

```asm
0x10009aa0  mov     edi, edi
0x10009aa2  push    ebp
0x10009aa3  mov     ebp, esp
0x10009aa5  sub     esp, 1Ch
0x10009aa8  push    ebx
0x10009aa9  mov     ebx, [ebp+arg_4]
0x10009aac  mov     eax, edx
0x10009aae  push    esi
0x10009aaf  mov     esi, [ebp+arg_0]
0x10009ab2  push    edi
0x10009ab3  mov     dword ptr [ebp+var_10+4], eax
0x10009ab6  xor     edi, edi
0x10009ab8  mov     [ebp+var_4], ecx
0x10009abb  add     eax, 28h ; '('
0x10009abe  mov     edi, edi
0x10009ac0  push    30h ; '0'; Size
0x10009ac2  push    0; Val
0x10009ac4  push    ebx; void *
0x10009ac5  mov     [ebp+var_14], eax
0x10009ac8  call    _memset
0x10009acd  mov     eax, dword ptr [ebp+var_10+4]
0x10009ad0  add     esp, 0Ch
0x10009ad3  mov     ecx, [eax+2Ch]
0x10009ad6  test    ecx, ecx
0x10009ad8  jz      short loc_10009AF0
0x10009ada  mov     edx, [ebp+var_14]
0x10009add  cmp     [edx], si
0x10009ae0  jnz     short loc_10009AF0
0x10009ae2  mov     dx, word ptr [ebp+arg_0+2]
0x10009ae6  cmp     [eax+2Ah], dx
0x10009aea  jbe     loc_10009B70
0x10009af0  mov     ecx, [eax+1Ch]
0x10009af3  test    ecx, ecx
0x10009af5  jz      short loc_10009B24
0x10009af7  mov     edi, [eax+20h]
0x10009afa  movzx   edx, si
0x10009afd  mov     eax, [edi+4]
0x10009b00  cmp     edx, eax
0x10009b02  jl      short loc_10009B10
0x10009b04  add     eax, 20h ; ' '
0x10009b07  cmp     edx, eax
0x10009b09  jge     short loc_10009B10
0x10009b0b  mov     ecx, edi
0x10009b0d  jmp     short loc_10009B38
0x10009b10  mov     eax, [ecx+4]
0x10009b13  cmp     edx, eax
0x10009b15  jl      short loc_10009B32
0x10009b17  add     eax, 20h ; ' '
0x10009b1a  cmp     edx, eax
0x10009b1c  jl      short loc_10009B32
0x10009b1e  mov     ecx, [ecx]
0x10009b20  test    ecx, ecx
0x10009b22  jnz     short loc_10009B10
0x10009b24  mov     eax, 2
0x10009b29  pop     edi
0x10009b2a  pop     esi
0x10009b2b  pop     ebx
0x10009b2c  mov     esp, ebp
0x10009b2e  pop     ebp
0x10009b2f  retn    8
0x10009b32  mov     eax, dword ptr [ebp+var_10+4]
0x10009b35  mov     [eax+20h], ecx
0x10009b38  test    ecx, ecx
0x10009b3a  jz      short loc_10009B24
0x10009b3c  mov     eax, [ecx+4]
0x10009b3f  cmp     edx, eax
0x10009b41  jl      short loc_10009B24
0x10009b43  sub     edx, eax
0x10009b45  mov     edi, [ecx+edx*4+8]
0x10009b49  test    edi, edi
0x10009b4b  jz      short loc_10009B24
0x10009b4d  movzx   eax, byte ptr [edi]
0x10009b50  mov     dx, word ptr [ebp+arg_0+2]
0x10009b54  cmp     dx, ax
0x10009b57  jb      short loc_10009B24
0x10009b59  movzx   eax, byte ptr [edi+1]
0x10009b5d  cmp     dx, ax
0x10009b60  ja      short loc_10009B24
0x10009b62  mov     ecx, [edi+10h]
0x10009b65  test    ecx, ecx
0x10009b67  jz      short loc_10009B24
0x10009b69  nop     dword ptr [eax+00000000h]
0x10009b70  movzx   eax, byte ptr [ecx+6]
0x10009b74  cmp     ax, dx
0x10009b77  jz      short loc_10009B8B
0x10009b79  mov     ecx, [ecx]
0x10009b7b  test    ecx, ecx
0x10009b7d  jnz     short loc_10009B70
0x10009b7f  lea     eax, [ecx+2]
0x10009b82  pop     edi
0x10009b83  pop     esi
0x10009b84  pop     ebx
0x10009b85  mov     esp, ebp
0x10009b87  pop     ebp
0x10009b88  retn    8
0x10009b8b  mov     eax, [ebp+var_14]
0x10009b8e  mov     [eax], esi
0x10009b90  mov     eax, dword ptr [ebp+var_10+4]
0x10009b93  mov     [eax+2Ch], ecx
0x10009b96  movsx   eax, word ptr [ecx+4]
0x10009b9a  mov     [ebx+4], eax
0x10009b9d  movzx   eax, byte ptr [ecx+7]
0x10009ba1  dec     eax; switch 9 cases
0x10009ba2  cmp     eax, 8
0x10009ba5  ja      def_10009BAB; jumptable 10009BAB default case
0x10009bab  jmp     ds:jpt_10009BAB[eax*4]; switch jump
0x10009bb2  cmp     word ptr [ecx+0Eh], 0FFFFh; jumptable 10009BAB case 3
0x10009bb7  jnz     loc_10009CB3
0x10009bbd  movzx   eax, byte ptr [ecx+8]
0x10009bc1  sub     eax, 0
0x10009bc4  jnz     loc_10009C6C
0x10009bca  mov     [ebp+var_18], eax
0x10009bcd  mov     eax, 110h
0x10009bd2  mov     [ebx], ax
0x10009bd5  test    edi, edi
0x10009bd7  jnz     short loc_10009BE7
0x10009bd9  mov     eax, dword ptr [ebp+var_10+4]
0x10009bdc  mov     [eax+2Ch], edi
0x10009bdf  mov     eax, [ebp+var_14]
0x10009be2  jmp     loc_10009AC0
0x10009be7  mov     eax, [edi+8]
0x10009bea  test    eax, eax
0x10009bec  jz      short loc_10009C0B
0x10009bee  mov     ecx, 207h
0x10009bf3  cmp     dx, [eax+6]
0x10009bf7  jnz     short loc_10009C05
0x10009bf9  cmp     si, [eax+4]
0x10009bfd  jnz     short loc_10009C05
0x10009bff  cmp     [eax+8], cx
0x10009c03  jz      short loc_10009C0D
0x10009c05  mov     eax, [eax]
0x10009c07  test    eax, eax
0x10009c09  jnz     short loc_10009BF3
0x10009c0b  xor     eax, eax
0x10009c0d  mov     edi, [ebp+var_4]
0x10009c10  lea     ecx, [ebp+var_18]
0x10009c13  push    ecx
0x10009c14  push    eax
0x10009c15  mov     edx, [edi+2Ch]
0x10009c18  mov     ecx, [edi+24h]
0x10009c1b  call    _ExcelExtractContinueString@16; ExcelExtractContinueString(x,x,x,x)
0x10009c20  mov     esi, eax
0x10009c22  test    esi, esi
0x10009c24  jns     short loc_10009C39
0x10009c26  mov     ecx, [ebp+var_18]
0x10009c29  call    _MemFree@4; MemFree(x)
0x10009c2e  mov     eax, esi
0x10009c30  pop     edi
0x10009c31  pop     esi
0x10009c32  pop     ebx
0x10009c33  mov     esp, ebp
0x10009c35  pop     ebp
0x10009c36  retn    8
0x10009c39  mov     edx, [ebp+var_18]
0x10009c3c  mov     ecx, [edi+28h]
0x10009c3f  push    1
0x10009c41  shr     esi, 1
0x10009c43  push    esi
0x10009c44  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x10009c49  mov     ecx, [ebp+var_18]
0x10009c4c  mov     [ebx+10h], eax
0x10009c4f  call    _MemFree@4; MemFree(x)
0x10009c54  cmp     dword ptr [ebx+10h], 0FFFFFFFFh
0x10009c58  jnz     def_10009BAB; jumptable 10009BAB default case
0x10009c5e  mov     eax, 0FFFFFFFEh
0x10009c63  pop     edi
0x10009c64  pop     esi
0x10009c65  pop     ebx
0x10009c66  mov     esp, ebp
0x10009c68  pop     ebp
0x10009c69  retn    8
0x10009c6c  sub     eax, 1
0x10009c6f  jz      short loc_10009C99
0x10009c71  sub     eax, 1
0x10009c74  jnz     def_10009BAB; jumptable 10009BAB default case
0x10009c7a  mov     eax, 108h
0x10009c7f  mov     [ebx], ax
0x10009c82  movzx   ecx, byte ptr [ecx+0Ah]
0x10009c86  call    _ExcelConvertToOurErrorCode@4; ExcelConvertToOurErrorCode(x)
0x10009c8b  mov     [ebx+10h], eax
0x10009c8e  xor     eax, eax
0x10009c90  pop     edi
0x10009c91  pop     esi
0x10009c92  pop     ebx
0x10009c93  mov     esp, ebp
0x10009c95  pop     ebp
0x10009c96  retn    8
0x10009c99  mov     eax, 104h
0x10009c9e  mov     [ebx], ax
0x10009ca1  movzx   eax, byte ptr [ecx+0Ah]
0x10009ca5  mov     [ebx+10h], eax
0x10009ca8  xor     eax, eax
0x10009caa  pop     edi
0x10009cab  pop     esi
0x10009cac  pop     ebx
0x10009cad  mov     esp, ebp
0x10009caf  pop     ebp
0x10009cb0  retn    8
0x10009cb3  mov     eax, 102h
0x10009cb8  mov     [ebx], ax
0x10009cbb  xor     eax, eax
0x10009cbd  movsd   xmm0, qword ptr [ecx+8]
0x10009cc2  movsd   qword ptr [ebx+10h], xmm0
0x10009cc7  pop     edi
0x10009cc8  pop     esi
0x10009cc9  pop     ebx
0x10009cca  mov     esp, ebp
0x10009ccc  pop     ebp
0x10009ccd  retn    8
0x10009cd0  cmp     byte ptr [ecx+9], 0; jumptable 10009BAB case 2
0x10009cd4  jnz     short loc_10009CF9
0x10009cd6  mov     eax, 4
0x10009cdb  mov     [ebx], ax
0x10009cde  xor     eax, eax
0x10009ce0  cmp     [ecx+8], al
0x10009ce3  mov     ecx, 10h
0x10009ce8  setnz   al
0x10009ceb  mov     [ebx+ecx], eax
0x10009cee  xor     eax, eax
0x10009cf0  pop     edi
0x10009cf1  pop     esi
0x10009cf2  pop     ebx
0x10009cf3  mov     esp, ebp
0x10009cf5  pop     ebp
0x10009cf6  retn    8
0x10009cf9  mov     eax, 8
0x10009cfe  mov     [ebx], ax
0x10009d01  movzx   ecx, byte ptr [ecx+8]
0x10009d05  call    _ExcelConvertToOurErrorCode@4; ExcelConvertToOurErrorCode(x)
0x10009d0a  mov     ecx, 10h
0x10009d0f  mov     [ebx+ecx], eax
0x10009d12  xor     eax, eax
0x10009d14  pop     edi
0x10009d15  pop     esi
0x10009d16  pop     ebx
0x10009d17  mov     esp, ebp
0x10009d19  pop     ebp
0x10009d1a  retn    8
0x10009d1d  cmp     dword ptr [ecx+8], 0; jumptable 10009BAB cases 8,9
0x10009d21  jz      short loc_10009D3C; jumptable 10009BAB case 1
0x10009d23  mov     eax, 10h
0x10009d28  mov     [ebx], ax
0x10009d2b  mov     eax, [ecx+8]
0x10009d2e  mov     [ebx+10h], eax
0x10009d31  xor     eax, eax
0x10009d33  pop     edi
0x10009d34  pop     esi
0x10009d35  pop     ebx
0x10009d36  mov     esp, ebp
0x10009d38  pop     ebp
0x10009d39  retn    8
0x10009d3c  mov     eax, 1; jumptable 10009BAB case 1
0x10009d41  mov     [ebx], ax
0x10009d44  xor     eax, eax
0x10009d46  pop     edi
0x10009d47  pop     esi
0x10009d48  pop     ebx
0x10009d49  mov     esp, ebp
0x10009d4b  pop     ebp
0x10009d4c  retn    8
0x10009d4f  mov     eax, [ecx+8]; jumptable 10009BAB cases 4,7
0x10009d52  test    eax, eax
0x10009d54  jz      short loc_10009D60
0x10009d56  cmp     eax, 0FFFFFFFFh
0x10009d59  jz      short loc_10009D60
0x10009d5b  lea     ebx, [eax+0Eh]
0x10009d5e  jmp     short loc_10009D76
0x10009d60  mov     ebx, offset WideCharStr
0x10009d65  test    eax, eax
0x10009d67  jz      loc_10009E51
0x10009d6d  cmp     eax, 0FFFFFFFFh
0x10009d70  jz      loc_10009E51
0x10009d76  mov     dl, [eax+0Ch]
0x10009d79  mov     al, dl
0x10009d7b  and     al, 0F3h
0x10009d7d  cmp     al, 1
0x10009d7f  jnz     short loc_10009DB2
0x10009d81  mov     ecx, ebx
0x10009d83  lea     esi, [ecx+2]
0x10009d86  mov     ax, [ecx]
0x10009d89  add     ecx, 2
0x10009d8c  test    ax, ax
0x10009d8f  jnz     short loc_10009D86
0x10009d91  sub     ecx, esi
0x10009d93  sar     ecx, 1
0x10009d95  push    edx
0x10009d96  push    ecx
0x10009d97  mov     ecx, [ebp+var_4]
0x10009d9a  mov     edx, ebx
0x10009d9c  mov     ecx, [ecx+28h]
0x10009d9f  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x10009da4  mov     esi, [ebp+arg_4]
0x10009da7  cmp     eax, 0FFFFFFFFh
0x10009daa  mov     [esi+10h], eax
0x10009dad  jmp     loc_10009EC4
0x10009db2  test    al, al
0x10009db4  jz      loc_10009E51
0x10009dba  mov     esi, ebx
0x10009dbc  lea     ecx, [esi+1]
0x10009dbf  nop
  ... truncated ...
```
