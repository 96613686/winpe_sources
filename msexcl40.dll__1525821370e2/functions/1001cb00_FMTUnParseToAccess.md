# FMTUnParseToAccess

- ea: `0x1001cb00`
- end: `0x1001ce00`
- name: `FMTUnParseToAccess`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1001cf30`

## callees

- `0x10006400`
- `0x1001c340`
- `0x1001cb00`
- `0x10035510`

## pseudocode

```c
int __thiscall FMTUnParseToAccess(_WORD *this, int a2, int a3)
{
  int v3; // eax
  int v4; // edx
  int v6; // ecx
  int v7; // edi
  int v8; // ebx
  _BYTE *v9; // esi
  int v10; // eax
  int result; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // edx
  _WORD *v15; // ecx
  int v16; // ebx
  _WORD *v17; // edi
  int v18; // esi
  _WORD *v19; // edx
  int v20; // ecx
  _WORD *v21; // eax
  int v22; // ecx
  _WORD *v23; // eax
  int v24; // edx
  _WORD *v25; // edi
  int v26; // esi
  bool v27; // zf
  int v28; // ecx
  _WORD *v29; // edx
  _WORD *v30; // eax
  int v31; // [esp+Ch] [ebp-21Ch]
  int v32; // [esp+10h] [ebp-218h]
  int v33; // [esp+14h] [ebp-214h]
  int v34; // [esp+1Ch] [ebp-20Ch]
  _WORD *v35; // [esp+20h] [ebp-208h]
  _DWORD v36[128]; // [esp+24h] [ebp-204h] BYREF

  v3 = a2;
  v4 = 0;
  v6 = 0;
  v35 = this;
  v32 = 0;
  *this = 0;
  v7 = *(_DWORD *)(a2 + 4);
  if ( v7 >= 3 )
  {
    v8 = 3;
    v34 = 3;
    v7 = 3;
  }
  else
  {
    v8 = *(_DWORD *)(a2 + 4);
    v34 = v8;
    if ( v7 <= 0 )
      goto LABEL_19;
  }
  do
  {
    v9 = *(_BYTE **)(v3 + 4 * v6 + 8);
    if ( v9 )
    {
      v10 = v4 + 1;
      if ( *v9 )
        v10 = v4;
      v4 = v10;
      v3 = a2;
    }
    ++v6;
  }
  while ( v6 < v8 );
  if ( v4 > 0 )
  {
    switch ( a3 )
    {
      case 1:
        WCSCPY2(v35, L"True/False", 0x100u);
        result = 0;
        break;
      case 5:
        WCSCPY2(v35, L"Currency", 0x100u);
        result = 0;
        break;
      case 7:
        WCSCPY2(v35, L"General Number", 0x100u);
        result = 0;
        break;
      case 8:
        WCSCPY2(v35, L"General Date", 0x100u);
        result = 0;
        break;
      case 10:
      case 12:
        WCSCPY2(v35, L"@", 0x100u);
        goto LABEL_17;
      default:
LABEL_17:
        result = 0;
        break;
    }
    return result;
  }
  this = v35;
LABEL_19:
  v12 = 0;
  v33 = 0;
  if ( v34 > 0 )
  {
    v31 = v7 - 1;
    do
    {
      v13 = *(_DWORD *)(v3 + 4 * v12 + 8);
      LOWORD(v36[0]) = 0;
      if ( v13 )
        v32 = UnParseSubFormat(a2, v13);
      v14 = 256;
      v15 = this;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v14;
      }
      while ( v14 );
      v16 = v14 != 0 ? 256 - v14 : 0;
      if ( v14 )
      {
        v17 = v36;
        v18 = 2147483646;
        v19 = &v35[v16];
        v20 = 256 - v16;
        if ( v16 != 256 )
        {
          do
          {
            if ( !v18 )
              break;
            if ( !*v17 )
              break;
            *v19++ = *v17++;
            --v18;
            --v20;
          }
          while ( v20 );
        }
        this = v35;
        v21 = v19 - 1;
        if ( v20 )
          v21 = v19;
        *v21 = 0;
      }
      if ( v33 < v31 )
      {
        v36[0] = 59;
        v22 = 256;
        v23 = this;
        do
        {
          if ( !*v23 )
            break;
          ++v23;
          --v22;
        }
        while ( v22 );
        v24 = v22 != 0 ? 256 - v22 : 0;
        if ( v22 )
        {
          v25 = v36;
          v26 = 2147483646;
          v28 = 256 - v24;
          v27 = v24 == 256;
          v29 = &v35[v24];
          if ( !v27 )
          {
            do
            {
              if ( !v26 )
                break;
              if ( !*v25 )
                break;
              *v29++ = *v25++;
              --v26;
              --v28;
            }
            while ( v28 );
          }
          v30 = v29 - 1;
          if ( v28 )
            v30 = v29;
          *v30 = 0;
        }
      }
      this = v35;
      v12 = v33 + 1;
      v3 = a2;
      v33 = v12;
    }
    while ( v12 < v34 );
  }
  return v32;
}

```

## disassembly

```asm
0x1001cb00  mov     edi, edi
0x1001cb02  push    ebp
0x1001cb03  mov     ebp, esp
0x1001cb05  sub     esp, 21Ch
0x1001cb0b  mov     eax, ___security_cookie
0x1001cb10  xor     eax, ebp
0x1001cb12  mov     [ebp+var_4], eax
0x1001cb15  mov     eax, [ebp+arg_0]
0x1001cb18  xor     edx, edx
0x1001cb1a  push    ebx
0x1001cb1b  push    esi
0x1001cb1c  mov     esi, ecx
0x1001cb1e  mov     [ebp+var_210], eax
0x1001cb24  xor     ecx, ecx
0x1001cb26  mov     [ebp+var_208], esi
0x1001cb2c  push    edi
0x1001cb2d  mov     [ebp+var_218], 0
0x1001cb37  mov     [esi], cx
0x1001cb3a  mov     edi, [eax+4]
0x1001cb3d  cmp     edi, 3
0x1001cb40  jge     short loc_1001CB54
0x1001cb42  mov     ebx, edi
0x1001cb44  mov     [ebp+var_20C], ebx
0x1001cb4a  test    edi, edi
0x1001cb4c  jle     loc_1001CC7A
0x1001cb52  jmp     short loc_1001CB61
0x1001cb54  mov     ebx, 3
0x1001cb59  mov     [ebp+var_20C], ebx
0x1001cb5f  mov     edi, ebx
0x1001cb61  mov     esi, [eax+ecx*4+8]
0x1001cb65  test    esi, esi
0x1001cb67  jz      short loc_1001CB7A
0x1001cb69  cmp     byte ptr [esi], 0
0x1001cb6c  lea     eax, [edx+1]
0x1001cb6f  cmovnz  eax, edx
0x1001cb72  mov     edx, eax
0x1001cb74  mov     eax, [ebp+var_210]
0x1001cb7a  inc     ecx
0x1001cb7b  cmp     ecx, ebx
0x1001cb7d  jl      short loc_1001CB61
0x1001cb7f  test    edx, edx
0x1001cb81  jle     loc_1001CC74
0x1001cb87  mov     eax, [ebp+arg_4]
0x1001cb8a  dec     eax; switch 12 cases
0x1001cb8b  cmp     eax, 0Bh
0x1001cb8e  ja      def_1001CB9B; jumptable 1001CB9B default case, cases 2-4,6,9,11
0x1001cb94  movzx   eax, ds:byte_1001CE18[eax]
0x1001cb9b  jmp     ds:jpt_1001CB9B[eax*4]; switch jump
0x1001cba2  mov     ecx, [ebp+var_208]; jumptable 1001CB9B case 1
0x1001cba8  mov     edx, offset aTrueFalse; "True/False"
0x1001cbad  push    100h
0x1001cbb2  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001cbb7  pop     edi
0x1001cbb8  pop     esi
0x1001cbb9  xor     eax, eax
0x1001cbbb  pop     ebx
0x1001cbbc  mov     ecx, [ebp+var_4]
0x1001cbbf  xor     ecx, ebp; StackCookie
0x1001cbc1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cbc6  mov     esp, ebp
0x1001cbc8  pop     ebp
0x1001cbc9  retn    8
0x1001cbcc  mov     ecx, [ebp+var_208]; jumptable 1001CB9B case 5
0x1001cbd2  mov     edx, offset aCurrency; "Currency"
0x1001cbd7  push    100h
0x1001cbdc  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001cbe1  pop     edi
0x1001cbe2  pop     esi
0x1001cbe3  xor     eax, eax
0x1001cbe5  pop     ebx
0x1001cbe6  mov     ecx, [ebp+var_4]
0x1001cbe9  xor     ecx, ebp; StackCookie
0x1001cbeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cbf0  mov     esp, ebp
0x1001cbf2  pop     ebp
0x1001cbf3  retn    8
0x1001cbf6  mov     ecx, [ebp+var_208]; jumptable 1001CB9B case 7
0x1001cbfc  mov     edx, offset aGeneralNumber; "General Number"
0x1001cc01  push    100h
0x1001cc06  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001cc0b  pop     edi
0x1001cc0c  pop     esi
0x1001cc0d  xor     eax, eax
0x1001cc0f  pop     ebx
0x1001cc10  mov     ecx, [ebp+var_4]
0x1001cc13  xor     ecx, ebp; StackCookie
0x1001cc15  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cc1a  mov     esp, ebp
0x1001cc1c  pop     ebp
0x1001cc1d  retn    8
0x1001cc20  mov     ecx, [ebp+var_208]; jumptable 1001CB9B case 8
0x1001cc26  mov     edx, offset aGeneralDate; "General Date"
0x1001cc2b  push    100h
0x1001cc30  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001cc35  pop     edi
0x1001cc36  pop     esi
0x1001cc37  xor     eax, eax
0x1001cc39  pop     ebx
0x1001cc3a  mov     ecx, [ebp+var_4]
0x1001cc3d  xor     ecx, ebp; StackCookie
0x1001cc3f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cc44  mov     esp, ebp
0x1001cc46  pop     ebp
0x1001cc47  retn    8
0x1001cc4a  mov     ecx, [ebp+var_208]; jumptable 1001CB9B cases 10,12
0x1001cc50  mov     edx, offset asc_10004A1C; "@"
0x1001cc55  push    100h
0x1001cc5a  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001cc5f  pop     edi; jumptable 1001CB9B default case, cases 2-4,6,9,11
0x1001cc60  pop     esi
0x1001cc61  xor     eax, eax
0x1001cc63  pop     ebx
0x1001cc64  mov     ecx, [ebp+var_4]
0x1001cc67  xor     ecx, ebp; StackCookie
0x1001cc69  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cc6e  mov     esp, ebp
0x1001cc70  pop     ebp
0x1001cc71  retn    8
0x1001cc74  mov     esi, [ebp+var_208]
0x1001cc7a  xor     ebx, ebx
0x1001cc7c  mov     [ebp+var_214], ebx
0x1001cc82  cmp     [ebp+var_20C], ebx
0x1001cc88  jle     loc_1001CDE7
0x1001cc8e  dec     edi
0x1001cc8f  mov     [ebp+var_21C], edi
0x1001cc95  nop     word ptr [eax+eax+00000000h]
0x1001cca0  mov     eax, [eax+ebx*4+8]
0x1001cca4  xor     ecx, ecx
0x1001cca6  mov     word ptr [ebp+var_204], cx
0x1001ccad  test    eax, eax
0x1001ccaf  jz      short loc_1001CCCE
0x1001ccb1  push    eax
0x1001ccb2  push    [ebp+var_210]
0x1001ccb8  mov     edx, 100h
0x1001ccbd  lea     ecx, [ebp+var_204]
0x1001ccc3  call    UnParseSubFormat
0x1001ccc8  mov     [ebp+var_218], eax
0x1001ccce  mov     edx, 100h
0x1001ccd3  mov     ecx, esi
0x1001ccd5  cmp     word ptr [ecx], 0
0x1001ccd9  jz      short loc_1001CCE3
0x1001ccdb  add     ecx, 2
0x1001ccde  sub     edx, 1
0x1001cce1  jnz     short loc_1001CCD5
0x1001cce3  mov     eax, 100h
0x1001cce8  mov     ebx, edx
0x1001ccea  sub     eax, edx
0x1001ccec  neg     ebx
0x1001ccee  sbb     ebx, ebx
0x1001ccf0  and     ebx, eax
0x1001ccf2  test    edx, edx
0x1001ccf4  jz      short loc_1001CD41
0x1001ccf6  mov     eax, [ebp+var_208]
0x1001ccfc  lea     edi, [ebp+var_204]
0x1001cd02  mov     ecx, 100h
0x1001cd07  mov     esi, 7FFFFFFEh
0x1001cd0c  lea     edx, [eax+ebx*2]
0x1001cd0f  sub     ecx, ebx
0x1001cd11  jz      short loc_1001CD2E
0x1001cd13  test    esi, esi
0x1001cd15  jz      short loc_1001CD2E
0x1001cd17  movzx   eax, word ptr [edi]
0x1001cd1a  test    ax, ax
0x1001cd1d  jz      short loc_1001CD2E
0x1001cd1f  mov     [edx], ax
0x1001cd22  add     edi, 2
0x1001cd25  add     edx, 2
0x1001cd28  dec     esi
0x1001cd29  sub     ecx, 1
0x1001cd2c  jnz     short loc_1001CD13
0x1001cd2e  mov     esi, [ebp+var_208]
0x1001cd34  lea     eax, [edx-2]
0x1001cd37  test    ecx, ecx
0x1001cd39  cmovnz  eax, edx
0x1001cd3c  xor     ecx, ecx
0x1001cd3e  mov     [eax], cx
0x1001cd41  mov     ebx, [ebp+var_214]
0x1001cd47  cmp     ebx, [ebp+var_21C]
0x1001cd4d  jge     short loc_1001CDC8
0x1001cd4f  mov     [ebp+var_204], 3Bh ; ';'
0x1001cd59  mov     ecx, 100h
0x1001cd5e  mov     eax, esi
0x1001cd60  cmp     word ptr [eax], 0
0x1001cd64  jz      short loc_1001CD6E
0x1001cd66  add     eax, 2
0x1001cd69  sub     ecx, 1
0x1001cd6c  jnz     short loc_1001CD60
0x1001cd6e  mov     eax, 100h
0x1001cd73  mov     edx, ecx
0x1001cd75  sub     eax, ecx
0x1001cd77  neg     edx
0x1001cd79  sbb     edx, edx
0x1001cd7b  and     edx, eax
0x1001cd7d  test    ecx, ecx
0x1001cd7f  jz      short loc_1001CDC8
0x1001cd81  mov     eax, [ebp+var_208]
0x1001cd87  lea     edi, [ebp+var_204]
0x1001cd8d  mov     ecx, 100h
0x1001cd92  mov     esi, 7FFFFFFEh
0x1001cd97  sub     ecx, edx
0x1001cd99  lea     edx, [eax+edx*2]
0x1001cd9c  jz      short loc_1001CDBB
0x1001cd9e  mov     edi, edi
0x1001cda0  test    esi, esi
0x1001cda2  jz      short loc_1001CDBB
0x1001cda4  movzx   eax, word ptr [edi]
0x1001cda7  test    ax, ax
0x1001cdaa  jz      short loc_1001CDBB
0x1001cdac  mov     [edx], ax
0x1001cdaf  add     edi, 2
0x1001cdb2  add     edx, 2
0x1001cdb5  dec     esi
0x1001cdb6  sub     ecx, 1
0x1001cdb9  jnz     short loc_1001CDA0
0x1001cdbb  test    ecx, ecx
0x1001cdbd  lea     eax, [edx-2]
0x1001cdc0  cmovnz  eax, edx
0x1001cdc3  xor     ecx, ecx
0x1001cdc5  mov     [eax], cx
0x1001cdc8  mov     esi, [ebp+var_208]
0x1001cdce  inc     ebx
0x1001cdcf  mov     eax, [ebp+var_210]
0x1001cdd5  mov     [ebp+var_214], ebx
0x1001cddb  cmp     ebx, [ebp+var_20C]
0x1001cde1  jl      loc_1001CCA0
0x1001cde7  mov     ecx, [ebp+var_4]
0x1001cdea  mov     eax, [ebp+var_218]
0x1001cdf0  xor     ecx, ebp; StackCookie
0x1001cdf2  pop     edi
0x1001cdf3  pop     esi
0x1001cdf4  pop     ebx
0x1001cdf5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cdfa  mov     esp, ebp
0x1001cdfc  pop     ebp
0x1001cdfd  retn    8
```
