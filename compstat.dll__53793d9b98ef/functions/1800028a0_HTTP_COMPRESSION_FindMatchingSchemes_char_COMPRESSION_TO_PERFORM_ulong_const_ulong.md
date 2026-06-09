# HTTP_COMPRESSION::FindMatchingSchemes(char *,COMPRESSION_TO_PERFORM,ulong * const,ulong *)

- ea: `0x1800028a0`
- end: `0x180002baa`
- name: `?FindMatchingSchemes@HTTP_COMPRESSION@@CAXPEADW4COMPRESSION_TO_PERFORM@@QEAKPEAK@Z`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001310`

## callees

- `0x1800028a0`
- `0x180005f52`
- `0x180005f90`

## import_xrefs

- `msvcrt!_stricmp` at `0x180002b00`
- `msvcrt!_stricmp` at `0x180002b00`
- `msvcrt!atof` at `0x180006d70`
- `msvcrt!atof` at `0x180006d70`
- `msvcrt!isalnum` at `0x180002935`
- `msvcrt!isalnum` at `0x180002963`
- `msvcrt!isalnum` at `0x180002977`
- `msvcrt!isalnum` at `0x180002935`
- `msvcrt!isalnum` at `0x180002963`
- `msvcrt!isalnum` at `0x180002977`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180002ae9`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180002ae9`

## pseudocode

```c
int __fastcall HTTP_COMPRESSION::FindMatchingSchemes(unsigned __int8 *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  struct COMPRESSION_SCHEME * near *v4; // rax
  int v5; // r14d
  _DWORD *v6; // r15
  unsigned __int8 *k; // rbx
  unsigned int v8; // edi
  int v9; // r12d
  unsigned int v10; // r13d
  int v11; // ebp
  _BYTE *v12; // rsi
  int v13; // ecx
  double v14; // xmm6_8
  __int64 v15; // rax
  int v16; // ecx
  unsigned int v17; // r8d
  unsigned int v18; // edx
  __int64 v19; // r9
  __int64 v20; // r11
  double v21; // xmm1_8
  unsigned int v22; // ecx
  double v23; // xmm0_8
  unsigned int v24; // ebx
  __int64 v25; // rdi
  __int64 v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r15d
  const char *Str; // rax
  unsigned __int8 *i; // rbx
  unsigned __int8 *j; // rbx
  double v32; // rcx
  double v33; // rax
  double v34; // xmm0_8
  __int64 m; // rcx
  int v37; // [rsp+20h] [rbp-9F8h]
  unsigned int v38; // [rsp+24h] [rbp-9F4h]
  int v39; // [rsp+28h] [rbp-9F0h]
  _DWORD v42[100]; // [rsp+40h] [rbp-9D8h] BYREF
  _DWORD v43[104]; // [rsp+1D0h] [rbp-848h]
  double v45[199]; // [rsp+378h] [rbp-6A0h]

  LODWORD(v4) = *a1;
  v5 = 0;
  v6 = a4;
  k = a1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v38 = 0;
  v39 = 0;
  v37 = 0;
  if ( (_BYTE)v4 )
  {
    v11 = 0;
    v12 = 0;
    do
    {
      if ( (_BYTE)v4 == 32 )
      {
        do
          ++k;
        while ( *k == 32 );
      }
      LODWORD(v4) = isalnum(*k);
      if ( (_DWORD)v4 )
      {
        v13 = *k;
        v14 = DOUBLE_1_0;
        v15 = 2LL * v8;
        *(char **)&v45[v15 - 1] = (char *)k;
        v45[v15] = 1.0;
        if ( isalnum(v13) )
        {
          do
            v16 = *++k;
          while ( isalnum(v16) );
        }
        v12 = k;
      }
      else
      {
        if ( *k != 42 )
          break;
        v14 = DOUBLE_1_0;
        v11 = 1;
        ++k;
        v45[2 * v8] = 1.0;
      }
      for ( LODWORD(v4) = *k; (_BYTE)v4 == 32; ++k )
        LODWORD(v4) = k[1];
      if ( (_BYTE)v4 == 59 )
      {
        LODWORD(v4) = k[1];
        for ( i = k + 1; (_BYTE)v4 == 32; ++i )
          LODWORD(v4) = i[1];
        if ( (_BYTE)v4 != 113 )
          break;
        LODWORD(v4) = i[1];
        for ( j = i + 1; (_BYTE)v4 == 32; ++j )
          LODWORD(v4) = j[1];
        if ( (_BYTE)v4 != 61 )
          break;
        for ( k = j + 1; *k == 32; ++k )
          ;
        v14 = atof((const char *)k);
        v45[2 * v8] = v14;
        for ( LODWORD(v4) = *k; (_BYTE)v4; LODWORD(v4) = *++k )
        {
          if ( (_BYTE)v4 == 44 )
            break;
        }
      }
      if ( *k == 44 )
        ++k;
      if ( v11 )
      {
        if ( v14 != 0.0 )
          v9 = 1;
      }
      else
      {
        ++v8;
        *v12 = 0;
        if ( v8 >= 0x64 )
          break;
      }
      LODWORD(v4) = *k;
    }
    while ( (_BYTE)v4 );
    v5 = 0;
    v39 = v9;
  }
  v17 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      v18 = v17 + 1;
      LODWORD(v4) = v17;
      v17 = v18;
      if ( v18 >= v8 )
        break;
      v19 = v18;
      v20 = 2LL * (unsigned int)v4;
      do
      {
        if ( v45[2 * v19] > v45[v20] )
        {
          v32 = v45[v20 - 1];
          v45[v20 - 1] = v45[2 * v19 - 1];
          v33 = v45[2 * v19];
          v45[2 * v19 - 1] = v32;
          v34 = v45[v20];
          v45[v20] = v33;
          v45[2 * v19] = v34;
        }
        ++v18;
        ++v19;
      }
      while ( v18 < v8 );
    }
    v21 = v45[0];
    v22 = 1;
    for ( v43[0] = 0; v22 < v8; ++v22 )
    {
      LODWORD(v4) = 2 * v22;
      v23 = v45[2 * v22];
      if ( v23 == 0.0 )
        break;
      if ( v21 > v23 )
      {
        ++v10;
        v21 = v45[2 * v22];
        v43[v10] = v22;
      }
    }
    v38 = ++v10;
    v43[v10] = v22;
  }
  v24 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
  if ( HTTP_COMPRESSION::sm_dwNumberOfSchemes )
    LODWORD(v4) = (unsigned int)memset_0(v42, 0, 4LL * HTTP_COMPRESSION::sm_dwNumberOfSchemes);
  v25 = 0;
  if ( v10 )
  {
    do
    {
      if ( v24 )
      {
        v26 = 0;
        do
        {
          v4 = (&HTTP_COMPRESSION::sm_pCompressionSchemes)[v26];
          if ( *((_DWORD *)v4 + 60) && !v42[v26] )
          {
            v27 = v43[v25];
            v4 = (struct COMPRESSION_SCHEME * near *)(unsigned int)(v25 + 1);
            v28 = v43[(_QWORD)v4];
            if ( v27 < v28 )
            {
              do
              {
                Str = STRA::QueryStr((STRA *)((&HTTP_COMPRESSION::sm_pCompressionSchemes)[v26] + 7));
                LODWORD(v4) = _stricmp(*(char **)&v45[2 * v27 - 1], Str);
                if ( !(_DWORD)v4 )
                {
                  v42[v26] = 1;
                  *(_DWORD *)(a3 + 4LL * v37) = v26;
                  v5 = v37 + 1;
                  v24 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
                  ++v37;
                  goto LABEL_40;
                }
                ++v27;
              }
              while ( v27 < v28 );
              v24 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
            }
            v5 = v37;
          }
LABEL_40:
          v26 = (unsigned int)(v26 + 1);
        }
        while ( (unsigned int)v26 < v24 );
        v10 = v38;
      }
      v25 = (unsigned int)(v25 + 1);
    }
    while ( (unsigned int)v25 < v10 );
    v6 = a4;
    v9 = v39;
  }
  if ( v9 )
  {
    for ( m = 0; (unsigned int)m < v24; m = (unsigned int)(m + 1) )
    {
      if ( !v42[m] )
      {
        v4 = (&HTTP_COMPRESSION::sm_pCompressionSchemes)[m];
        v42[m] = 1;
        if ( *((_DWORD *)v4 + 60) )
        {
          v4 = (struct COMPRESSION_SCHEME * near *)v5++;
          *(_DWORD *)(a3 + 4LL * (_QWORD)v4) = m;
          v24 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
        }
      }
    }
  }
  *v6 = v5;
  return (int)v4;
}

```

## disassembly

```asm
0x1800028a0  mov     r11, rsp
0x1800028a3  push    rbx
0x1800028a4  push    r14
0x1800028a6  push    r15
0x1800028a8  sub     rsp, 0A00h
0x1800028af  mov     rax, cs:__security_cookie
0x1800028b6  xor     rax, rsp
0x1800028b9  mov     [rsp+0A18h+var_68], rax
0x1800028c1  movzx   eax, byte ptr [rcx]
0x1800028c4  xor     r14d, r14d
0x1800028c7  mov     [r11+10h], rbp
0x1800028cb  mov     r15, r9
0x1800028ce  mov     [r11-20h], rsi
0x1800028d2  mov     rbx, rcx
0x1800028d5  mov     [r11-28h], rdi
0x1800028d9  xor     edi, edi
0x1800028db  mov     [r11-30h], r12
0x1800028df  xor     r12d, r12d
0x1800028e2  mov     [r11-38h], r13
0x1800028e6  xor     r13d, r13d
0x1800028e9  movaps  xmmword ptr [r11-58h], xmm8
0x1800028ee  xorps   xmm8, xmm8
0x1800028f2  mov     [rsp+0A18h+var_9E0], r9
0x1800028f7  mov     [rsp+0A18h+var_9E8], r8
0x1800028fc  mov     [rsp+0A18h+var_9F4], r13d
0x180002901  mov     [rsp+0A18h+var_9F0], r12d
0x180002906  mov     [rsp+0A18h+var_9F8], r14d
0x18000290b  test    al, al
0x18000290d  jz      loc_1800029CC
0x180002913  xor     ebp, ebp
0x180002915  movaps  xmmword ptr [r11-48h], xmm6
0x18000291a  xor     esi, esi
0x18000291c  mov     r14, 3FF0000000000000h
0x180002926  cmp     al, 20h ; ' '
0x180002928  jnz     short loc_180002932
0x18000292a  inc     rbx
0x18000292d  cmp     byte ptr [rbx], 20h ; ' '
0x180002930  jz      short loc_18000292A
0x180002932  movzx   ecx, byte ptr [rbx]; C
0x180002935  call    cs:__imp_isalnum
0x18000293b  test    eax, eax
0x18000293d  jz      loc_180006CE6
0x180002943  movzx   ecx, byte ptr [rbx]; C
0x180002946  movsd   xmm6, cs:__real@3ff0000000000000
0x18000294e  mov     eax, edi
0x180002950  add     rax, rax
0x180002953  mov     [rsp+rax*8+0A18h+String1], rbx
0x18000295b  mov     [rsp+rax*8+0A18h+var_6A0], r14
0x180002963  call    cs:__imp_isalnum
0x180002969  test    eax, eax
0x18000296b  jz      short loc_180002981
0x18000296d  nop     dword ptr [rax]
0x180002970  movzx   ecx, byte ptr [rbx+1]; C
0x180002974  inc     rbx
0x180002977  call    cs:__imp_isalnum
0x18000297d  test    eax, eax
0x18000297f  jnz     short loc_180002970
0x180002981  mov     rsi, rbx
0x180002984  movzx   eax, byte ptr [rbx]
0x180002987  cmp     al, 20h ; ' '
0x180002989  jz      loc_180006D11
0x18000298f  cmp     al, 3Bh ; ';'
0x180002991  jz      loc_180006D21
0x180002997  cmp     byte ptr [rbx], 2Ch ; ','
0x18000299a  jnz     short loc_18000299F
0x18000299c  inc     rbx
0x18000299f  test    ebp, ebp
0x1800029a1  jnz     loc_180006DAA
0x1800029a7  inc     edi
0x1800029a9  mov     [rsi], r13b
0x1800029ac  cmp     edi, 64h ; 'd'
0x1800029af  jnb     short loc_1800029BC
0x1800029b1  movzx   eax, byte ptr [rbx]
0x1800029b4  test    al, al
0x1800029b6  jnz     loc_180002926
0x1800029bc  movaps  xmm6, [rsp+0A18h+var_48]
0x1800029c4  xor     r14d, r14d
0x1800029c7  mov     [rsp+0A18h+var_9F0], r12d
0x1800029cc  xor     r8d, r8d
0x1800029cf  test    edi, edi
0x1800029d1  jz      loc_180002A6A
0x1800029d7  lea     edx, [r8+1]
0x1800029db  mov     eax, r8d
0x1800029de  mov     r8d, edx
0x1800029e1  cmp     edx, edi
0x1800029e3  jnb     short loc_180002A19
0x1800029e5  mov     r11d, eax
0x1800029e8  mov     r9d, edx
0x1800029eb  add     r11, r11
0x1800029ee  mov     r10, r9
0x1800029f1  add     r10, r10
0x1800029f4  movsd   xmm0, [rsp+r10*8+0A18h+var_6A0]
0x1800029fe  comisd  xmm0, [rsp+r11*8+0A18h+var_6A0]
0x180002a08  ja      loc_180006DC2
0x180002a0e  inc     edx
0x180002a10  inc     r9
0x180002a13  cmp     edx, edi
0x180002a15  jnb     short loc_1800029D7
0x180002a17  jmp     short loc_1800029EE
0x180002a19  movsd   xmm1, [rsp+0A18h+var_6A0]
0x180002a22  mov     ecx, 1
0x180002a27  mov     [rsp+0A18h+var_848], r13d
0x180002a2f  cmp     edi, ecx
0x180002a31  jbe     short loc_180002A5A
0x180002a33  mov     eax, ecx
0x180002a35  add     rax, rax
0x180002a38  movsd   xmm0, [rsp+rax*8+0A18h+var_6A0]
0x180002a41  ucomisd xmm0, xmm8
0x180002a46  jp      short loc_180002A4A
0x180002a48  jz      short loc_180002A5A
0x180002a4a  comisd  xmm1, xmm0
0x180002a4e  ja      loc_180006E0B
0x180002a54  inc     ecx
0x180002a56  cmp     ecx, edi
0x180002a58  jb      short loc_180002A33
0x180002a5a  inc     r13d
0x180002a5d  mov     [rsp+0A18h+var_9F4], r13d
0x180002a62  mov     [rsp+r13*4+0A18h+var_848], ecx
0x180002a6a  mov     ebx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180002a70  movaps  xmm8, [rsp+0A18h+var_58]
0x180002a79  test    ebx, ebx
0x180002a7b  jz      short loc_180002A90
0x180002a7d  mov     r8d, ebx
0x180002a80  lea     rcx, [rsp+0A18h+var_9D8]; void *
0x180002a85  shl     r8, 2; Size
0x180002a89  xor     edx, edx; Val
0x180002a8b  call    memset_0
0x180002a90  xor     edi, edi
0x180002a92  lea     r8, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x180002a99  test    r13d, r13d
0x180002a9c  jz      loc_180002B59
0x180002aa2  test    ebx, ebx
0x180002aa4  jz      loc_180002B44
0x180002aaa  mov     r13, [rsp+0A18h+var_9E8]
0x180002aaf  xor     esi, esi
0x180002ab1  mov     rax, [r8+rsi*8]
0x180002ab5  cmp     dword ptr [rax+0F0h], 0
0x180002abc  jz      short loc_180002B35
0x180002abe  cmp     [rsp+rsi*4+0A18h+var_9D8], 0
0x180002ac3  jnz     short loc_180002B35
0x180002ac5  mov     r14d, [rsp+rdi*4+0A18h+var_848]
0x180002acd  lea     eax, [rdi+1]
0x180002ad0  mov     r15d, [rsp+rax*4+0A18h+var_848]
0x180002ad8  cmp     r14d, r15d
0x180002adb  jnb     loc_180006E37
0x180002ae1  mov     rcx, [r8+rsi*8]
0x180002ae5  add     rcx, 38h ; '8'
0x180002ae9  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180002aef  mov     ecx, r14d
0x180002af2  mov     rdx, rax; String2
0x180002af5  add     rcx, rcx
0x180002af8  mov     rcx, [rsp+rcx*8+0A18h+String1]; String1
0x180002b00  call    cs:__imp__stricmp
0x180002b06  lea     r8, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x180002b0d  test    eax, eax
0x180002b0f  jnz     loc_180006E1E
0x180002b15  movsxd  r14, [rsp+0A18h+var_9F8]
0x180002b1a  mov     [rsp+rsi*4+0A18h+var_9D8], 1
0x180002b22  mov     [r13+r14*4+0], esi
0x180002b27  inc     r14d
0x180002b2a  mov     ebx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180002b30  mov     [rsp+0A18h+var_9F8], r14d
0x180002b35  inc     esi
0x180002b37  cmp     esi, ebx
0x180002b39  jb      loc_180002AB1
0x180002b3f  mov     r13d, [rsp+0A18h+var_9F4]
0x180002b44  inc     edi
0x180002b46  cmp     edi, r13d
0x180002b49  jb      loc_180002AA2
0x180002b4f  mov     r15, [rsp+0A18h+var_9E0]
0x180002b54  mov     r12d, [rsp+0A18h+var_9F0]
0x180002b59  mov     r13, [rsp+0A18h+var_38]
0x180002b61  test    r12d, r12d
0x180002b64  mov     r12, [rsp+0A18h+var_30]
0x180002b6c  mov     rdi, [rsp+0A18h+var_28]
0x180002b74  mov     rsi, [rsp+0A18h+var_20]
0x180002b7c  mov     rbp, [rsp+0A18h+arg_8]
0x180002b84  jnz     loc_180006E41
0x180002b8a  mov     [r15], r14d
0x180002b8d  mov     rcx, [rsp+0A18h+var_68]
0x180002b95  xor     rcx, rsp; StackCookie
0x180002b98  call    __security_check_cookie
0x180002b9d  add     rsp, 0A00h
0x180002ba4  pop     r15
0x180002ba6  pop     r14
0x180002ba8  pop     rbx
0x180002ba9  retn
0x180006ce6  cmp     byte ptr [rbx], 2Ah ; '*'
0x180006ce9  jnz     loc_1800029BC
0x180006cef  movsd   xmm6, cs:__real@3ff0000000000000
0x180006cf7  mov     ebp, 1
0x180006cfc  mov     eax, edi
0x180006cfe  add     rax, rax
0x180006d01  inc     rbx
0x180006d04  mov     [rsp+rax*8+0A18h+var_6A0], r14
0x180006d0c  jmp     loc_180002984
0x180006d11  movzx   eax, byte ptr [rbx+1]
0x180006d15  inc     rbx
0x180006d18  cmp     al, 20h ; ' '
0x180006d1a  jz      short loc_180006D11
0x180006d1c  jmp     loc_18000298F
0x180006d21  movzx   eax, byte ptr [rbx+1]
0x180006d25  inc     rbx
0x180006d28  cmp     al, 20h ; ' '
0x180006d2a  jnz     short loc_180006D37
0x180006d2c  movzx   eax, byte ptr [rbx+1]
0x180006d30  inc     rbx
0x180006d33  cmp     al, 20h ; ' '
0x180006d35  jz      short loc_180006D2C
0x180006d37  cmp     al, 71h ; 'q'
0x180006d39  jnz     loc_1800029BC
0x180006d3f  movzx   eax, byte ptr [rbx+1]
0x180006d43  inc     rbx
0x180006d46  cmp     al, 20h ; ' '
0x180006d48  jnz     short loc_180006D55
0x180006d4a  movzx   eax, byte ptr [rbx+1]
0x180006d4e  inc     rbx
0x180006d51  cmp     al, 20h ; ' '
0x180006d53  jz      short loc_180006D4A
0x180006d55  cmp     al, 3Dh ; '='
0x180006d57  jnz     loc_1800029BC
0x180006d5d  inc     rbx
0x180006d60  cmp     byte ptr [rbx], 20h ; ' '
0x180006d63  jnz     short loc_180006D6D
0x180006d65  inc     rbx
0x180006d68  cmp     byte ptr [rbx], 20h ; ' '
0x180006d6b  jz      short loc_180006D65
0x180006d6d  mov     rcx, rbx; String
0x180006d70  call    cs:__imp_atof
0x180006d76  mov     eax, edi
0x180006d78  movaps  xmm6, xmm0
0x180006d7b  add     rax, rax
0x180006d7e  movsd   [rsp+rax*8+0A18h+var_6A0], xmm0
0x180006d87  movzx   eax, byte ptr [rbx]
0x180006d8a  test    al, al
0x180006d8c  jz      loc_180002997
0x180006d92  cmp     al, 2Ch ; ','
0x180006d94  jz      loc_180002997
0x180006d9a  movzx   eax, byte ptr [rbx+1]
0x180006d9e  inc     rbx
0x180006da1  test    al, al
0x180006da3  jnz     short loc_180006D92
0x180006da5  jmp     loc_180002997
0x180006daa  ucomisd xmm6, xmm8
0x180006daf  jp      short loc_180006DB7
0x180006db1  jz      loc_1800029B1
0x180006db7  mov     r12d, 1
0x180006dbd  jmp     loc_1800029B1
0x180006dc2  mov     rax, [rsp+r10*8+0A18h+String1]
0x180006dca  mov     rcx, [rsp+r11*8+0A18h+String1]
0x180006dd2  mov     [rsp+r11*8+0A18h+String1], rax
0x180006dda  mov     rax, [rsp+r10*8+0A18h+var_6A0]
0x180006de2  mov     [rsp+r10*8+0A18h+String1], rcx
0x180006dea  movsd   xmm0, [rsp+r11*8+0A18h+var_6A0]
0x180006df4  mov     [rsp+r11*8+0A18h+var_6A0], rax
0x180006dfc  movsd   [rsp+r10*8+0A18h+var_6A0], xmm0
0x180006e06  jmp     loc_180002A0E
0x180006e0b  inc     r13d
0x180006e0e  movaps  xmm1, xmm0
0x180006e11  mov     [rsp+r13*4+0A18h+var_848], ecx
0x180006e19  jmp     loc_180002A54
0x180006e1e  inc     r14d
0x180006e21  cmp     r14d, r15d
0x180006e24  jb      loc_180002AE1
0x180006e2a  mov     ebx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180006e30  lea     r8, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x180006e37  mov     r14d, [rsp+0A18h+var_9F8]
0x180006e3c  jmp     loc_180002B35
0x180006e41  xor     ecx, ecx
0x180006e43  test    ebx, ebx
0x180006e45  jz      loc_180002B8A
0x180006e4b  mov     rdx, [rsp+0A18h+var_9E8]
0x180006e50  cmp     [rsp+rcx*4+0A18h+var_9D8], 0
0x180006e55  jnz     short loc_180006E7B
0x180006e57  mov     rax, [r8+rcx*8]
0x180006e5b  mov     [rsp+rcx*4+0A18h+var_9D8], 1
0x180006e63  cmp     dword ptr [rax+0F0h], 0
0x180006e6a  jz      short loc_180006E7B
0x180006e6c  movsxd  rax, r14d
0x180006e6f  inc     r14d
0x180006e72  mov     [rdx+rax*4], ecx
0x180006e75  mov     ebx, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180006e7b  inc     ecx
0x180006e7d  cmp     ecx, ebx
0x180006e7f  jb      short loc_180006E50
0x180006e81  jmp     loc_180002B8A
```
