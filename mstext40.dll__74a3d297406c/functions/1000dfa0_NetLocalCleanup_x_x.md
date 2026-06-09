# NetLocalCleanup(x,x)

- ea: `0x1000dfa0`
- end: `0x1000e34b`
- name: `_NetLocalCleanup@8`
- size: `939`
- prototype: `int __stdcall(wchar_t *FullPath, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1000fc70`
- `0x1000ff30`
- `0x10010450`

## callees

- `0x1000b5f0`
- `0x1000b6d0`
- `0x1000b7a0`
- `0x1000c2f0`
- `0x1000dfa0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall NetLocalCleanup(wchar_t *FullPath, int *a2)
{
  int v2; // ebx
  int v3; // ebp
  int v4; // edx
  WCHAR *v5; // ecx
  WCHAR v6; // ax
  int v7; // ecx
  WCHAR *v8; // eax
  WCHAR *v9; // eax
  int v10; // edx
  char *v11; // edi
  WCHAR v12; // si
  int v13; // ecx
  WCHAR *v14; // eax
  WCHAR *v15; // eax
  int v16; // edx
  char *v17; // edi
  WCHAR v18; // si
  int v19; // ecx
  WCHAR *v20; // eax
  WCHAR *v21; // eax
  int v22; // edx
  int v23; // ebx
  WCHAR v24; // si
  int v25; // edx
  WCHAR *v26; // eax
  WCHAR v27; // cx
  int v28; // ecx
  WCHAR *v29; // eax
  WCHAR *v30; // eax
  int v31; // edx
  char *v32; // edi
  WCHAR v33; // si
  int v34; // ecx
  WCHAR *v35; // eax
  WCHAR *v36; // eax
  int v37; // edx
  char *v38; // edi
  WCHAR v39; // si
  int v41; // [esp+8h] [ebp-86Ch]
  int v42; // [esp+Ch] [ebp-868h] BYREF
  wchar_t Drive[10]; // [esp+10h] [ebp-864h] BYREF
  int v44[16]; // [esp+24h] [ebp-850h] BYREF
  WCHAR FileName[262]; // [esp+64h] [ebp-810h] BYREF
  wchar_t pszDest[256]; // [esp+270h] [ebp-604h] BYREF
  wchar_t Dir[256]; // [esp+470h] [ebp-404h] BYREF
  wchar_t Filename[256]; // [esp+670h] [ebp-204h] BYREF

  v42 = 0;
  DOSFileDelete(FullPath);
  if ( a2 )
  {
    SplitPath(FullPath, Drive, 9u, Dir, 0x100u, Filename, 0x100u, 0, 0);
    v2 = *a2;
    v41 = 0;
    if ( *a2 )
    {
      v3 = (char *)Drive - (char *)FileName;
      do
      {
        v4 = 261;
        v5 = FileName;
        while ( v4 != -2147483385 )
        {
          v6 = *(WCHAR *)((char *)v5 + v3);
          if ( !v6 )
            break;
          *v5++ = v6;
          if ( !--v4 )
          {
            --v5;
            break;
          }
        }
        *v5 = 0;
        v7 = 261;
        v8 = FileName;
        while ( *v8 )
        {
          ++v8;
          if ( !--v7 )
            goto LABEL_19;
        }
        v9 = &FileName[261 - v7];
        v10 = 2147483646;
        v11 = (char *)((char *)Dir - (char *)v9);
        while ( v10 )
        {
          v12 = *(WCHAR *)((char *)v9 + (_DWORD)v11);
          if ( !v12 )
            break;
          *v9 = v12;
          --v10;
          ++v9;
          if ( !--v7 )
          {
            --v9;
            break;
          }
        }
        *v9 = 0;
LABEL_19:
        v13 = 261;
        v14 = FileName;
        while ( *v14 )
        {
          ++v14;
          if ( !--v13 )
            goto LABEL_29;
        }
        v15 = &FileName[261 - v13];
        v16 = 2147483646;
        v17 = (char *)((char *)Filename - (char *)v15);
        while ( v16 )
        {
          v18 = *(_WORD *)&v17[(_DWORD)v15];
          if ( !v18 )
            break;
          *v15 = v18;
          --v16;
          ++v15;
          if ( !--v13 )
          {
            --v15;
            break;
          }
        }
        *v15 = 0;
LABEL_29:
        v19 = 261;
        v20 = FileName;
        while ( *v20 )
        {
          ++v20;
          if ( !--v19 )
            goto LABEL_39;
        }
        v21 = &FileName[261 - v19];
        v22 = 2147483646;
        v23 = v2 - (_DWORD)v21;
        while ( v22 )
        {
          v24 = *(WCHAR *)((char *)v21 + v23);
          if ( !v24 )
            break;
          *v21 = v24;
          --v22;
          ++v21;
          if ( !--v19 )
          {
            --v21;
            break;
          }
        }
        *v21 = 0;
LABEL_39:
        if ( DOSFindFirstMatchingFile(FileName, pszDest, 0x100u, (int)v44, (int)&v42) )
        {
          do
          {
            v25 = 261;
            v26 = FileName;
            while ( v25 != -2147483385 )
            {
              v27 = *(WCHAR *)((char *)v26 + v3);
              if ( !v27 )
                break;
              *v26++ = v27;
              if ( !--v25 )
              {
                --v26;
                break;
              }
            }
            *v26 = 0;
            v28 = 261;
            v29 = FileName;
            while ( *v29 )
            {
              ++v29;
              if ( !--v28 )
                goto LABEL_55;
            }
            v30 = &FileName[261 - v28];
            v31 = 2147483646;
            v32 = (char *)((char *)Dir - (char *)v30);
            while ( v31 )
            {
              v33 = *(WCHAR *)((char *)v30 + (_DWORD)v32);
              if ( !v33 )
                break;
              *v30 = v33;
              --v31;
              ++v30;
              if ( !--v28 )
              {
                --v30;
                break;
              }
            }
            *v30 = 0;
LABEL_55:
            v34 = 261;
            v35 = FileName;
            while ( *v35 )
            {
              ++v35;
              if ( !--v34 )
                goto LABEL_65;
            }
            v36 = &FileName[261 - v34];
            v37 = 2147483646;
            v38 = (char *)((char *)pszDest - (char *)v36);
            while ( v37 )
            {
              v39 = *(WCHAR *)((char *)v36 + (_DWORD)v38);
              if ( !v39 )
                break;
              *v36 = v39;
              --v37;
              ++v36;
              if ( !--v34 )
              {
                --v36;
                break;
              }
            }
            *v36 = 0;
LABEL_65:
            DOSFileDelete(FileName);
          }
          while ( DOSFindNextMatchingFile(pszDest, 0x100u, (int)v44, (int)&v42) );
        }
        v2 = a2[++v41];
      }
      while ( v2 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1000dfa0  sub     esp, 86Ch
0x1000dfa6  mov     eax, ___security_cookie
0x1000dfab  xor     eax, esp
0x1000dfad  mov     [esp+86Ch+var_4], eax
0x1000dfb4  push    ebx
0x1000dfb5  push    esi
0x1000dfb6  mov     esi, [esp+874h+FullPath]
0x1000dfbd  push    esi
0x1000dfbe  mov     [esp+878h+var_868], 0
0x1000dfc6  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1000dfcb  mov     ebx, [esp+874h+arg_4]
0x1000dfd2  test    ebx, ebx
0x1000dfd4  jz      loc_1000E330
0x1000dfda  push    0; ExtCount
0x1000dfdc  push    0; Ext
0x1000dfde  push    100h; FilenameCount
0x1000dfe3  lea     eax, [esp+880h+Filename]
0x1000dfea  push    eax; Filename
0x1000dfeb  push    100h; DirCount
0x1000dff0  lea     eax, [esp+888h+Dir]
0x1000dff7  push    eax; Dir
0x1000dff8  push    9; DriveCount
0x1000dffa  lea     eax, [esp+890h+Drive]
0x1000dffe  push    eax; Drive
0x1000dfff  push    esi; FullPath
0x1000e000  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1000e005  mov     ebx, [ebx]
0x1000e007  mov     [esp+874h+var_86C], 0
0x1000e00f  test    ebx, ebx
0x1000e011  jz      loc_1000E330
0x1000e017  push    ebp
0x1000e018  lea     ebp, [esp+878h+Drive]
0x1000e01c  lea     eax, [esp+878h+FileName]
0x1000e020  push    edi
0x1000e021  sub     ebp, eax
0x1000e023  jmp     short loc_1000E030
0x1000e030  mov     edx, 105h
0x1000e035  lea     ecx, [esp+87Ch+FileName]
0x1000e039  lea     esp, [esp+0]
0x1000e040  lea     eax, [edx+7FFFFEF9h]
0x1000e046  test    eax, eax
0x1000e048  jz      short loc_1000E05E
0x1000e04a  movzx   eax, word ptr [ecx+ebp]
0x1000e04e  test    ax, ax
0x1000e051  jz      short loc_1000E05E
0x1000e053  mov     [ecx], ax
0x1000e056  add     ecx, 2
0x1000e059  dec     edx
0x1000e05a  jnz     short loc_1000E040
0x1000e05c  jmp     short loc_1000E062
0x1000e05e  test    edx, edx
0x1000e060  jnz     short loc_1000E065
0x1000e062  sub     ecx, 2
0x1000e065  xor     eax, eax
0x1000e067  mov     [ecx], ax
0x1000e06a  mov     ecx, 105h
0x1000e06f  lea     eax, [esp+87Ch+FileName]
0x1000e073  cmp     word ptr [eax], 0
0x1000e077  jz      short loc_1000E081
0x1000e079  add     eax, 2
0x1000e07c  dec     ecx
0x1000e07d  jnz     short loc_1000E073
0x1000e07f  jmp     short loc_1000E0D5
0x1000e081  test    ecx, ecx
0x1000e083  jz      short loc_1000E0D5
0x1000e085  mov     edx, 105h
0x1000e08a  lea     eax, [esp+87Ch+FileName]
0x1000e08e  sub     edx, ecx
0x1000e090  mov     ecx, 105h
0x1000e095  lea     eax, [eax+edx*2]
0x1000e098  sub     ecx, edx
0x1000e09a  jz      short loc_1000E0CD
0x1000e09c  add     edx, 7FFFFEF9h
0x1000e0a2  lea     edi, [esp+87Ch+Dir]
0x1000e0a9  add     edx, ecx
0x1000e0ab  sub     edi, eax
0x1000e0ad  lea     ecx, [ecx+0]
0x1000e0b0  test    edx, edx
0x1000e0b2  jz      short loc_1000E0C9
0x1000e0b4  movzx   esi, word ptr [edi+eax]
0x1000e0b8  test    si, si
0x1000e0bb  jz      short loc_1000E0C9
0x1000e0bd  mov     [eax], si
0x1000e0c0  dec     edx
0x1000e0c1  add     eax, 2
0x1000e0c4  dec     ecx
0x1000e0c5  jnz     short loc_1000E0B0
0x1000e0c7  jmp     short loc_1000E0CD
0x1000e0c9  test    ecx, ecx
0x1000e0cb  jnz     short loc_1000E0D0
0x1000e0cd  sub     eax, 2
0x1000e0d0  xor     ecx, ecx
0x1000e0d2  mov     [eax], cx
0x1000e0d5  mov     ecx, 105h
0x1000e0da  lea     eax, [esp+87Ch+FileName]
0x1000e0de  mov     edi, edi
0x1000e0e0  cmp     word ptr [eax], 0
0x1000e0e4  jz      short loc_1000E0EE
0x1000e0e6  add     eax, 2
0x1000e0e9  dec     ecx
0x1000e0ea  jnz     short loc_1000E0E0
0x1000e0ec  jmp     short loc_1000E145
0x1000e0ee  test    ecx, ecx
0x1000e0f0  jz      short loc_1000E145
0x1000e0f2  mov     edx, 105h
0x1000e0f7  lea     eax, [esp+87Ch+FileName]
0x1000e0fb  sub     edx, ecx
0x1000e0fd  mov     ecx, 105h
0x1000e102  lea     eax, [eax+edx*2]
0x1000e105  sub     ecx, edx
0x1000e107  jz      short loc_1000E13D
0x1000e109  add     edx, 7FFFFEF9h
0x1000e10f  lea     edi, [esp+87Ch+Filename]
0x1000e116  add     edx, ecx
0x1000e118  sub     edi, eax
0x1000e11a  lea     ebx, [ebx+0]
0x1000e120  test    edx, edx
0x1000e122  jz      short loc_1000E139
0x1000e124  movzx   esi, word ptr [eax+edi]
0x1000e128  test    si, si
0x1000e12b  jz      short loc_1000E139
0x1000e12d  mov     [eax], si
0x1000e130  dec     edx
0x1000e131  add     eax, 2
0x1000e134  dec     ecx
0x1000e135  jnz     short loc_1000E120
0x1000e137  jmp     short loc_1000E13D
0x1000e139  test    ecx, ecx
0x1000e13b  jnz     short loc_1000E140
0x1000e13d  sub     eax, 2
0x1000e140  xor     ecx, ecx
0x1000e142  mov     [eax], cx
0x1000e145  mov     ecx, 105h
0x1000e14a  lea     eax, [esp+87Ch+FileName]
0x1000e14e  mov     edi, edi
0x1000e150  cmp     word ptr [eax], 0
0x1000e154  jz      short loc_1000E15E
0x1000e156  add     eax, 2
0x1000e159  dec     ecx
0x1000e15a  jnz     short loc_1000E150
0x1000e15c  jmp     short loc_1000E1A8
0x1000e15e  test    ecx, ecx
0x1000e160  jz      short loc_1000E1A8
0x1000e162  mov     edx, 105h
0x1000e167  lea     eax, [esp+87Ch+FileName]
0x1000e16b  sub     edx, ecx
0x1000e16d  mov     ecx, 105h
0x1000e172  lea     eax, [eax+edx*2]
0x1000e175  sub     ecx, edx
0x1000e177  jz      short loc_1000E1A0
0x1000e179  add     edx, 7FFFFEF9h
0x1000e17f  add     edx, ecx
0x1000e181  sub     ebx, eax
0x1000e183  test    edx, edx
0x1000e185  jz      short loc_1000E19C
0x1000e187  movzx   esi, word ptr [eax+ebx]
0x1000e18b  test    si, si
0x1000e18e  jz      short loc_1000E19C
0x1000e190  mov     [eax], si
0x1000e193  dec     edx
0x1000e194  add     eax, 2
0x1000e197  dec     ecx
0x1000e198  jnz     short loc_1000E183
0x1000e19a  jmp     short loc_1000E1A0
0x1000e19c  test    ecx, ecx
0x1000e19e  jnz     short loc_1000E1A3
0x1000e1a0  sub     eax, 2
0x1000e1a3  xor     ecx, ecx
0x1000e1a5  mov     [eax], cx
0x1000e1a8  lea     eax, [esp+87Ch+var_868]
0x1000e1ac  push    eax; int
0x1000e1ad  lea     eax, [esp+880h+var_850]
0x1000e1b1  push    eax; int
0x1000e1b2  push    100h; cchDest
0x1000e1b7  lea     eax, [esp+888h+pszDest]
0x1000e1be  push    eax; pszDest
0x1000e1bf  lea     eax, [esp+88Ch+FileName]
0x1000e1c3  push    eax; lpFileName
0x1000e1c4  call    _DOSFindFirstMatchingFile@20; DOSFindFirstMatchingFile(x,x,x,x,x)
0x1000e1c9  test    eax, eax
0x1000e1cb  jz      loc_1000E313
0x1000e1d1  mov     edx, 105h
0x1000e1d6  lea     eax, [esp+87Ch+FileName]
0x1000e1da  lea     ebx, [ebx+0]
0x1000e1e0  lea     ecx, [edx+7FFFFEF9h]
0x1000e1e6  test    ecx, ecx
0x1000e1e8  jz      short loc_1000E1FE
0x1000e1ea  movzx   ecx, word ptr [eax+ebp]
0x1000e1ee  test    cx, cx
0x1000e1f1  jz      short loc_1000E1FE
0x1000e1f3  mov     [eax], cx
0x1000e1f6  add     eax, 2
0x1000e1f9  dec     edx
0x1000e1fa  jnz     short loc_1000E1E0
0x1000e1fc  jmp     short loc_1000E202
0x1000e1fe  test    edx, edx
0x1000e200  jnz     short loc_1000E205
0x1000e202  sub     eax, 2
0x1000e205  xor     ecx, ecx
0x1000e207  mov     [eax], cx
0x1000e20a  mov     ecx, 105h
0x1000e20f  lea     eax, [esp+87Ch+FileName]
0x1000e213  cmp     word ptr [eax], 0
0x1000e217  jz      short loc_1000E221
0x1000e219  add     eax, 2
0x1000e21c  dec     ecx
0x1000e21d  jnz     short loc_1000E213
0x1000e21f  jmp     short loc_1000E275
0x1000e221  test    ecx, ecx
0x1000e223  jz      short loc_1000E275
0x1000e225  mov     edx, 105h
0x1000e22a  lea     eax, [esp+87Ch+FileName]
0x1000e22e  sub     edx, ecx
0x1000e230  mov     ecx, 105h
0x1000e235  lea     eax, [eax+edx*2]
0x1000e238  sub     ecx, edx
0x1000e23a  jz      short loc_1000E26D
0x1000e23c  add     edx, 7FFFFEF9h
0x1000e242  lea     edi, [esp+87Ch+Dir]
0x1000e249  add     edx, ecx
0x1000e24b  sub     edi, eax
0x1000e24d  lea     ecx, [ecx+0]
0x1000e250  test    edx, edx
0x1000e252  jz      short loc_1000E269
0x1000e254  movzx   esi, word ptr [edi+eax]
0x1000e258  test    si, si
0x1000e25b  jz      short loc_1000E269
0x1000e25d  mov     [eax], si
0x1000e260  dec     edx
0x1000e261  add     eax, 2
0x1000e264  dec     ecx
0x1000e265  jnz     short loc_1000E250
0x1000e267  jmp     short loc_1000E26D
0x1000e269  test    ecx, ecx
0x1000e26b  jnz     short loc_1000E270
0x1000e26d  sub     eax, 2
0x1000e270  xor     ecx, ecx
0x1000e272  mov     [eax], cx
0x1000e275  mov     ecx, 105h
0x1000e27a  lea     eax, [esp+87Ch+FileName]
0x1000e27e  mov     edi, edi
0x1000e280  cmp     word ptr [eax], 0
0x1000e284  jz      short loc_1000E28E
0x1000e286  add     eax, 2
0x1000e289  dec     ecx
0x1000e28a  jnz     short loc_1000E280
0x1000e28c  jmp     short loc_1000E2E5
0x1000e28e  test    ecx, ecx
0x1000e290  jz      short loc_1000E2E5
0x1000e292  mov     edx, 105h
0x1000e297  lea     eax, [esp+87Ch+FileName]
0x1000e29b  sub     edx, ecx
0x1000e29d  mov     ecx, 105h
0x1000e2a2  lea     eax, [eax+edx*2]
0x1000e2a5  sub     ecx, edx
0x1000e2a7  jz      short loc_1000E2DD
0x1000e2a9  add     edx, 7FFFFEF9h
0x1000e2af  lea     edi, [esp+87Ch+pszDest]
0x1000e2b6  add     edx, ecx
0x1000e2b8  sub     edi, eax
0x1000e2ba  lea     ebx, [ebx+0]
0x1000e2c0  test    edx, edx
0x1000e2c2  jz      short loc_1000E2D9
0x1000e2c4  movzx   esi, word ptr [edi+eax]
0x1000e2c8  test    si, si
0x1000e2cb  jz      short loc_1000E2D9
0x1000e2cd  mov     [eax], si
0x1000e2d0  dec     edx
0x1000e2d1  add     eax, 2
0x1000e2d4  dec     ecx
0x1000e2d5  jnz     short loc_1000E2C0
0x1000e2d7  jmp     short loc_1000E2DD
0x1000e2d9  test    ecx, ecx
0x1000e2db  jnz     short loc_1000E2E0
0x1000e2dd  sub     eax, 2
0x1000e2e0  xor     ecx, ecx
0x1000e2e2  mov     [eax], cx
0x1000e2e5  lea     eax, [esp+87Ch+FileName]
0x1000e2e9  push    eax
0x1000e2ea  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1000e2ef  lea     eax, [esp+87Ch+var_868]
0x1000e2f3  push    eax; int
0x1000e2f4  lea     eax, [esp+880h+var_850]
0x1000e2f8  push    eax; int
0x1000e2f9  push    100h; cchDest
0x1000e2fe  lea     eax, [esp+888h+pszDest]
0x1000e305  push    eax; pszDest
0x1000e306  call    _DOSFindNextMatchingFile@16; DOSFindNextMatchingFile(x,x,x,x)
0x1000e30b  test    eax, eax
0x1000e30d  jnz     loc_1000E1D1
0x1000e313  mov     eax, [esp+87Ch+var_86C]
0x1000e317  mov     ecx, [esp+87Ch+arg_4]
0x1000e31e  inc     eax
0x1000e31f  mov     [esp+87Ch+var_86C], eax
0x1000e323  mov     ebx, [ecx+eax*4]
0x1000e326  test    ebx, ebx
0x1000e328  jnz     loc_1000E030
0x1000e32e  pop     edi
0x1000e32f  pop     ebp
0x1000e330  mov     ecx, [esp+874h+var_4]
  ... truncated ...
```
