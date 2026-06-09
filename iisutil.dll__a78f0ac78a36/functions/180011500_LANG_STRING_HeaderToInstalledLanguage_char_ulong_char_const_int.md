# LANG_STRING::HeaderToInstalledLanguage(char *,ulong,char const * *,int)

- ea: `0x180011500`
- end: `0x18001197d`
- name: `?HeaderToInstalledLanguage@LANG_STRING@@AEAAJPEADKPEAPEBDH@Z`
- size: `1149`
- prototype: `__int64 __fastcall(LANG_STRING *this, char *String, int, const char **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800113d0`

## callees

- `0x180002b60`
- `0x180011500`
- `0x180011a50`
- `0x180011ac0`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!strtok` at `0x18001156b`
- `msvcrt!strtok` at `0x18001159d`
- `msvcrt!strtok` at `0x1800115b5`
- `msvcrt!strtok` at `0x180011823`
- `msvcrt!strtok` at `0x18001156b`
- `msvcrt!strtok` at `0x18001159d`
- `msvcrt!strtok` at `0x1800115b5`
- `msvcrt!strtok` at `0x180011823`
- `msvcrt!isdigit` at `0x18001185b`
- `msvcrt!isdigit` at `0x18001185b`
- `msvcrt!atof` at `0x18001187c`
- `msvcrt!atof` at `0x18001187c`
- `msvcrt!_stricmp` at `0x18001170e`
- `msvcrt!_stricmp` at `0x18001170e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117d2`

## pseudocode

```c
__int64 __fastcall LANG_STRING::HeaderToInstalledLanguage(
        LANG_STRING *this,
        char *String,
        int a3,
        const char **a4,
        int a5)
{
  __int64 v7; // rdi
  char *i; // rcx
  char *v9; // rax
  __int64 j; // r14
  char *v11; // rbx
  char *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  const char **v17; // rsi
  int ParentLanguage; // ebx
  int v19; // r15d
  unsigned int m; // r12d
  double v21; // xmm1_8
  unsigned int v22; // r8d
  __int64 n; // rcx
  char *v24; // xmm0_8
  char *v25; // rdi
  __int64 v26; // rsi
  HANDLE ProcessHeap; // rax
  const char *v29; // r12
  int v30; // esi
  _BYTE *k; // rbx
  double v32; // xmm0_8
  __int64 ii; // rdi
  __int64 v34; // rdx
  char *v35; // rdx
  unsigned __int16 *v36; // rax
  int v37; // ecx
  int v38; // edx
  int v40; // [rsp+30h] [rbp-D8h]
  _BYTE v43[32]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-A0h]
  int v45; // [rsp+70h] [rbp-98h]
  __int16 v46; // [rsp+74h] [rbp-94h]
  _BYTE v47[32]; // [rsp+78h] [rbp-90h] BYREF
  char *v48; // [rsp+98h] [rbp-70h]
  int v49; // [rsp+A0h] [rbp-68h]
  __int16 v50; // [rsp+A4h] [rbp-64h]
  _OWORD v51[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v52[2]; // [rsp+C8h] [rbp-40h] BYREF
  char *Stringa[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v54[44]; // [rsp+F8h] [rbp-10h]

  v7 = 0;
  Stringa[0] = 0;
  memset_0(&Stringa[1], 0, 0x160u);
  for ( i = String; ; i = 0 )
  {
    v9 = strtok(i, ",");
    if ( !v9 || (unsigned int)v7 >= 0xF )
      break;
    v13 = 3 * v7;
    v7 = (unsigned int)(v7 + 1);
    Stringa[v13] = v9;
  }
  for ( j = 0; (unsigned int)j < (unsigned int)v7; j = (unsigned int)(j + 1) )
  {
    v11 = Stringa[3 * j];
    if ( *v11 )
    {
      if ( v11 != strtok(Stringa[3 * j], ";") )
        return (unsigned int)-2147024883;
      v12 = strtok(0, ";");
      if ( v12 )
      {
        if ( strtok(0, ";") )
          return (unsigned int)-2147024883;
        if ( *v12 != 113 )
          return (unsigned int)-2147024883;
        if ( v12[1] != 61 )
          return (unsigned int)-2147024883;
        v29 = v12 + 2;
        if ( (unsigned __int8)(v12[2] - 48) > 1u )
          return (unsigned int)-2147024883;
        if ( v12[3] == 46 )
        {
          v30 = 0;
          for ( k = v12 + 4; *k; ++k )
          {
            if ( !isdigit((unsigned __int8)*k) )
              return (unsigned int)-2147024883;
            if ( (unsigned int)++v30 > 3 )
              return (unsigned int)-2147024883;
          }
          if ( !v30 )
            return (unsigned int)-2147024883;
        }
        v32 = atof(v29);
        if ( v32 < 0.0 || v32 > 1.0 )
          return (unsigned int)-2147024883;
        *(double *)&Stringa[3 * j + 1] = v32;
      }
      else
      {
        Stringa[3 * j + 1] = (char *)0x3FF0000000000000LL;
      }
    }
    else
    {
      LODWORD(v54[3 * j]) = 1;
    }
  }
  v14 = 0;
  v15 = 0;
  if ( !(_DWORD)v7 )
    return (unsigned int)-2147024883;
  do
  {
    if ( !LODWORD(v54[3 * v15]) )
    {
      v16 = 3 * v14;
      v14 = (unsigned int)(v14 + 1);
      *(_OWORD *)&Stringa[v16] = *(_OWORD *)&Stringa[3 * v15];
      v54[v16] = v54[3 * v15];
    }
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < (unsigned int)v7 );
  v40 = v14;
  if ( !(_DWORD)v14 )
    return (unsigned int)-2147024883;
  v17 = a4;
  ParentLanguage = 0;
  v19 = 0;
  for ( m = 0; ; ++m )
  {
    if ( m >= (unsigned int)v14 )
    {
      if ( !v19 )
        *v17 = (const char *)**((_QWORD **)this + 4);
      return (unsigned int)ParentLanguage;
    }
    if ( v19 )
      return (unsigned int)ParentLanguage;
    v21 = DOUBLE_N1_0;
    v22 = 0;
    for ( n = 0; (unsigned int)n < (unsigned int)v14; n = (unsigned int)(n + 1) )
    {
      if ( !LODWORD(v54[3 * n]) && *(double *)&Stringa[3 * n + 1] > v21 )
      {
        v21 = *(double *)&Stringa[3 * n + 1];
        v22 = n;
      }
    }
    v24 = Stringa[3 * v22 + 1];
    LODWORD(v54[3 * v22]) = 1;
    if ( *(double *)&v24 > 0.0 )
      break;
LABEL_38:
    ;
  }
  v25 = Stringa[3 * v22];
  if ( v25 < String || v25 > &String[a3] || !(unsigned int)LANG_STRING::ValidLanguage(this, Stringa[3 * v22]) )
    return (unsigned int)-2147024883;
  if ( *v25 == 42 )
  {
    v19 = 1;
    *v17 = (const char *)**((_QWORD **)this + 4);
    goto LABEL_38;
  }
  v26 = 0;
  if ( *((_DWORD *)this + 10) )
  {
    do
    {
      if ( !_stricmp(v25, *(const char **)(*((_QWORD *)this + 4) + 8 * v26)) )
      {
        v19 = 1;
        *a4 = *(const char **)(*((_QWORD *)this + 4) + 8 * v26);
      }
      v26 = (unsigned int)(v26 + 1);
    }
    while ( (unsigned int)v26 < *((_DWORD *)this + 10) );
    LODWORD(v14) = v40;
  }
  if ( !a5 || v19 )
  {
    v17 = a4;
    goto LABEL_38;
  }
  v45 = 32;
  v46 = 256;
  lpMem = v51;
  memset(v51, 0, sizeof(v51));
  ParentLanguage = LANG_STRING::GetParentLanguage(this, v25, (struct BUFFER *)v43);
  if ( ParentLanguage >= 0 )
  {
    for ( ii = 0; ; ii = (unsigned int)(ii + 1) )
    {
      if ( (unsigned int)ii >= *((_DWORD *)this + 10) )
      {
        v17 = a4;
        goto LABEL_72;
      }
      v34 = *((_QWORD *)this + 4);
      v48 = (char *)v52;
      memset(v52, 0, sizeof(v52));
      v35 = *(char **)(v34 + 8 * ii);
      v49 = 32;
      v50 = 256;
      ParentLanguage = LANG_STRING::GetParentLanguage(this, v35, (struct BUFFER *)v47);
      if ( ParentLanguage < 0 )
        break;
      v36 = (unsigned __int16 *)lpMem;
      do
      {
        v37 = *(unsigned __int16 *)((char *)v36 + v48 - (_BYTE *)lpMem);
        v38 = *v36 - v37;
        if ( v38 )
          break;
        ++v36;
      }
      while ( v37 );
      if ( !v38 )
      {
        v19 = 1;
        v17 = a4;
        *a4 = *(const char **)(*((_QWORD *)this + 4) + 8 * ii);
        BUFFER::~BUFFER((BUFFER *)v47);
LABEL_72:
        BUFFER::~BUFFER((BUFFER *)v43);
        goto LABEL_38;
      }
      BUFFER::~BUFFER((BUFFER *)v47);
    }
    BUFFER::~BUFFER((BUFFER *)v47);
    BUFFER::~BUFFER((BUFFER *)v43);
  }
  else if ( (_BYTE)v46 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return (unsigned int)ParentLanguage;
}

```

## disassembly

```asm
0x180011500  mov     rax, rsp
0x180011503  mov     [rax+18h], rbx
0x180011507  push    rbp
0x180011508  push    rsi
0x180011509  push    rdi
0x18001150a  push    r12
0x18001150c  push    r13
0x18001150e  push    r14
0x180011510  push    r15
0x180011512  lea     rbp, [rax-1A8h]
0x180011519  sub     rsp, 270h
0x180011520  movaps  xmmword ptr [rax-48h], xmm6
0x180011524  mov     rax, cs:__security_cookie
0x18001152b  xor     rax, rsp
0x18001152e  mov     [rbp+1A0h+var_50], rax
0x180011535  mov     dword ptr [rsp+2A0h+var_270], r8d
0x18001153a  mov     rbx, rdx
0x18001153d  mov     qword ptr [rsp+2A0h+var_268], rdx
0x180011542  mov     r13, rcx
0x180011545  xor     edi, edi
0x180011547  mov     qword ptr [rsp+2A0h+var_280], r9
0x18001154c  xor     edx, edx; Val
0x18001154e  mov     [rbp+1A0h+String], rdi
0x180011552  mov     r8d, 160h; Size
0x180011558  lea     rcx, [rbp+1A0h+String+8]; void *
0x18001155c  call    memset_0
0x180011561  mov     rcx, rbx; String
0x180011564  lea     rdx, Delimiter; ","
0x18001156b  call    cs:__imp_strtok
0x180011571  test    rax, rax
0x180011574  jnz     short loc_1800115DB
0x180011576  xor     r14d, r14d
0x180011579  xorps   xmm6, xmm6
0x18001157c  cmp     r14d, edi
0x18001157f  jnb     short loc_1800115F2
0x180011581  lea     r15, [r14+r14*2]
0x180011585  mov     rbx, [rbp+r15*8+1A0h+String]
0x18001158a  cmp     byte ptr [rbx], 0
0x18001158d  jz      loc_18001180C
0x180011593  lea     rdx, a01020304050607+0C6h; ";"
0x18001159a  mov     rcx, rbx; String
0x18001159d  call    cs:__imp_strtok
0x1800115a3  cmp     rbx, rax
0x1800115a6  jnz     loc_1800117ED
0x1800115ac  lea     rdx, a01020304050607+0C6h; ";"
0x1800115b3  xor     ecx, ecx; String
0x1800115b5  call    cs:__imp_strtok
0x1800115bb  mov     rbx, rax
0x1800115be  test    rax, rax
0x1800115c1  jnz     loc_18001181A
0x1800115c7  mov     rax, 3FF0000000000000h
0x1800115d1  mov     [rbp+r15*8+1A0h+String+8], rax
0x1800115d6  inc     r14d
0x1800115d9  jmp     short loc_18001157C
0x1800115db  cmp     edi, 0Fh
0x1800115de  jnb     short loc_180011576
0x1800115e0  lea     rdx, [rdi+rdi*2]
0x1800115e4  inc     edi
0x1800115e6  xor     ecx, ecx
0x1800115e8  mov     [rbp+rdx*8+1A0h+String], rax
0x1800115ed  jmp     loc_180011564
0x1800115f2  xor     r14d, r14d
0x1800115f5  xor     edx, edx
0x1800115f7  test    edi, edi
0x1800115f9  jz      loc_1800117ED
0x1800115ff  lea     r8, [rdx+rdx*2]
0x180011603  cmp     dword ptr [rbp+r8*8+1A0h+var_1B0], 0
0x180011609  jnz     short loc_18001162A
0x18001160b  movups  xmm0, xmmword ptr [rbp+r8*8+1A0h+String]
0x180011611  lea     rcx, [r14+r14*2]
0x180011615  inc     r14d
0x180011618  movups  xmmword ptr [rbp+rcx*8+1A0h+String], xmm0
0x18001161d  movsd   xmm1, [rbp+r8*8+1A0h+var_1B0]
0x180011624  movsd   [rbp+rcx*8+1A0h+var_1B0], xmm1
0x18001162a  inc     edx
0x18001162c  cmp     edx, edi
0x18001162e  jb      short loc_1800115FF
0x180011630  mov     [rsp+2A0h+var_278], r14d
0x180011635  test    r14d, r14d
0x180011638  jz      loc_1800117ED
0x18001163e  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x180011643  xor     ebx, ebx
0x180011645  xor     r15d, r15d
0x180011648  xor     r12d, r12d
0x18001164b  mov     [rsp+2A0h+var_274], r12d
0x180011650  cmp     r12d, r14d
0x180011653  jnb     loc_180011754
0x180011659  test    r15d, r15d
0x18001165c  jnz     loc_18001175D
0x180011662  movsd   xmm1, cs:__real@bff0000000000000
0x18001166a  xor     r8d, r8d
0x18001166d  xor     ecx, ecx
0x18001166f  test    r14d, r14d
0x180011672  jz      short loc_180011698
0x180011674  lea     rdx, [rcx+rcx*2]
0x180011678  cmp     dword ptr [rbp+rdx*8+1A0h+var_1B0], 0
0x18001167d  jnz     short loc_180011691
0x18001167f  movsd   xmm0, [rbp+rdx*8+1A0h+String+8]
0x180011685  comisd  xmm0, xmm1
0x180011689  jbe     short loc_180011691
0x18001168b  movaps  xmm1, xmm0
0x18001168e  mov     r8d, ecx
0x180011691  inc     ecx
0x180011693  cmp     ecx, r14d
0x180011696  jb      short loc_180011674
0x180011698  mov     eax, r8d
0x18001169b  lea     rdi, [rax+rax*2]
0x18001169f  movsd   xmm0, [rbp+rdi*8+1A0h+String+8]
0x1800116a5  comisd  xmm0, xmm6
0x1800116a9  mov     dword ptr [rbp+rdi*8+1A0h+var_1B0], 1
0x1800116b1  jbe     loc_18001174C
0x1800116b7  mov     rdi, [rbp+rdi*8+1A0h+String]
0x1800116bc  mov     rcx, qword ptr [rsp+2A0h+var_268]
0x1800116c1  cmp     rdi, rcx
0x1800116c4  jb      loc_1800117ED
0x1800116ca  mov     eax, dword ptr [rsp+2A0h+var_270]
0x1800116ce  add     rax, rcx
0x1800116d1  cmp     rdi, rax
0x1800116d4  ja      loc_1800117ED
0x1800116da  mov     rdx, rdi; char *
0x1800116dd  mov     rcx, r13; this
0x1800116e0  call    ?ValidLanguage@LANG_STRING@@AEAAHPEBD@Z; LANG_STRING::ValidLanguage(char const *)
0x1800116e5  test    eax, eax
0x1800116e7  jz      loc_1800117ED
0x1800116ed  cmp     byte ptr [rdi], 2Ah ; '*'
0x1800116f0  jz      loc_1800117F7
0x1800116f6  xor     esi, esi
0x1800116f8  cmp     [r13+28h], esi
0x1800116fc  jbe     short loc_180011739
0x1800116fe  mov     r14, qword ptr [rsp+2A0h+var_280]
0x180011703  mov     rdx, [r13+20h]
0x180011707  mov     rcx, rdi; String1
0x18001170a  mov     rdx, [rdx+rsi*8]; String2
0x18001170e  call    cs:__imp__stricmp
0x180011714  test    eax, eax
0x180011716  jnz     short loc_180011727
0x180011718  lea     r15d, [rax+1]
0x18001171c  mov     rax, [r13+20h]
0x180011720  mov     rcx, [rax+rsi*8]
0x180011724  mov     [r14], rcx
0x180011727  inc     esi
0x180011729  cmp     esi, [r13+28h]
0x18001172d  jb      short loc_180011703
0x18001172f  mov     r14d, [rsp+2A0h+var_278]
0x180011734  mov     r12d, [rsp+2A0h+var_274]
0x180011739  cmp     [rbp+1A0h+arg_20], 0
0x180011740  jz      short loc_180011747
0x180011742  test    r15d, r15d
0x180011745  jz      short loc_18001178E
0x180011747  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x18001174c  inc     r12d
0x18001174f  jmp     loc_18001164B
0x180011754  test    r15d, r15d
0x180011757  jz      loc_18001196E
0x18001175d  mov     eax, ebx
0x18001175f  mov     rcx, [rbp+1A0h+var_50]
0x180011766  xor     rcx, rsp; StackCookie
0x180011769  call    __security_check_cookie
0x18001176e  lea     r11, [rsp+2A0h+var_30]
0x180011776  mov     rbx, [r11+50h]
0x18001177a  movaps  xmm6, xmmword ptr [r11-10h]
0x18001177f  mov     rsp, r11
0x180011782  pop     r15
0x180011784  pop     r14
0x180011786  pop     r13
0x180011788  pop     r12
0x18001178a  pop     rdi
0x18001178b  pop     rsi
0x18001178c  pop     rbp
0x18001178d  retn
0x18001178e  xorps   xmm0, xmm0
0x180011791  mov     [rsp+2A0h+var_238], 20h ; ' '
0x180011799  lea     rax, [rbp+1A0h+var_200]
0x18001179d  mov     [rsp+2A0h+var_234], 100h
0x1800117a4  lea     r8, [rsp+2A0h+var_260]; struct BUFFER *
0x1800117a9  mov     [rsp+2A0h+lpMem], rax
0x1800117ae  mov     rdx, rdi; char *
0x1800117b1  mov     rcx, r13; this
0x1800117b4  movups  [rbp+1A0h+var_200], xmm0
0x1800117b8  movups  [rbp+1A0h+var_1F0], xmm0
0x1800117bc  call    ?GetParentLanguage@LANG_STRING@@AEAAJPEADPEAVBUFFER@@@Z; LANG_STRING::GetParentLanguage(char *,BUFFER *)
0x1800117c1  mov     ebx, eax
0x1800117c3  test    eax, eax
0x1800117c5  jns     loc_1800118A6
0x1800117cb  cmp     byte ptr [rsp+2A0h+var_234], 0
0x1800117d0  jz      short loc_18001175D
0x1800117d2  call    cs:__imp_GetProcessHeap
0x1800117d8  mov     r8, [rsp+2A0h+lpMem]; lpMem
0x1800117dd  xor     edx, edx; dwFlags
0x1800117df  mov     rcx, rax; hHeap
0x1800117e2  call    cs:__imp_HeapFree
0x1800117e8  jmp     loc_18001175D
0x1800117ed  mov     ebx, 8007000Dh
0x1800117f2  jmp     loc_18001175D
0x1800117f7  mov     rax, [r13+20h]
0x1800117fb  mov     r15d, 1
0x180011801  mov     rcx, [rax]
0x180011804  mov     [rsi], rcx
0x180011807  jmp     loc_18001174C
0x18001180c  mov     dword ptr [rbp+r15*8+1A0h+var_1B0], 1
0x180011815  jmp     loc_1800115D6
0x18001181a  lea     rdx, a01020304050607+0C6h; ";"
0x180011821  xor     ecx, ecx; String
0x180011823  call    cs:__imp_strtok
0x180011829  test    rax, rax
0x18001182c  jnz     short loc_1800117ED
0x18001182e  cmp     byte ptr [rbx], 71h ; 'q'
0x180011831  jnz     short loc_1800117ED
0x180011833  cmp     byte ptr [rbx+1], 3Dh ; '='
0x180011837  jnz     short loc_1800117ED
0x180011839  lea     r12, [rbx+2]
0x18001183d  mov     al, [r12]
0x180011841  sub     al, 30h ; '0'
0x180011843  cmp     al, 1
0x180011845  ja      short loc_1800117ED
0x180011847  cmp     byte ptr [rbx+3], 2Eh ; '.'
0x18001184b  jnz     short loc_180011879
0x18001184d  xor     esi, esi
0x18001184f  add     rbx, 4
0x180011853  cmp     byte ptr [rbx], 0
0x180011856  jz      short loc_180011871
0x180011858  movzx   ecx, byte ptr [rbx]; C
0x18001185b  call    cs:__imp_isdigit
0x180011861  test    eax, eax
0x180011863  jz      short loc_1800117ED
0x180011865  inc     esi
0x180011867  cmp     esi, 3
0x18001186a  ja      short loc_1800117ED
0x18001186c  inc     rbx
0x18001186f  jmp     short loc_180011853
0x180011871  test    esi, esi
0x180011873  jz      loc_1800117ED
0x180011879  mov     rcx, r12; String
0x18001187c  call    cs:__imp_atof
0x180011882  comisd  xmm6, xmm0
0x180011886  ja      loc_1800117ED
0x18001188c  comisd  xmm0, cs:__real@3ff0000000000000
0x180011894  ja      loc_1800117ED
0x18001189a  movsd   [rbp+r15*8+1A0h+String+8], xmm0
0x1800118a1  jmp     loc_1800115D6
0x1800118a6  xor     edi, edi
0x1800118a8  cmp     edi, [r13+28h]
0x1800118ac  jnb     loc_180011941
0x1800118b2  mov     rdx, [r13+20h]
0x1800118b6  lea     rax, [rbp+1A0h+var_1E0]
0x1800118ba  xorps   xmm0, xmm0
0x1800118bd  mov     [rbp+1A0h+var_210], rax
0x1800118c1  movups  [rbp+1A0h+var_1E0], xmm0
0x1800118c5  lea     r8, [rsp+2A0h+var_230]; struct BUFFER *
0x1800118ca  mov     rcx, r13; this
0x1800118cd  movups  [rbp+1A0h+var_1D0], xmm0
0x1800118d1  mov     rdx, [rdx+rdi*8]; char *
0x1800118d5  mov     [rbp+1A0h+var_208], 20h ; ' '
0x1800118dc  mov     [rbp+1A0h+var_204], 100h
0x1800118e2  call    ?GetParentLanguage@LANG_STRING@@AEAAJPEADPEAVBUFFER@@@Z; LANG_STRING::GetParentLanguage(char *,BUFFER *)
0x1800118e7  mov     ebx, eax
0x1800118e9  test    eax, eax
0x1800118eb  js      short loc_180011955
0x1800118ed  mov     rax, [rsp+2A0h+lpMem]
0x1800118f2  mov     r8, [rbp+1A0h+var_210]
0x1800118f6  sub     r8, rax
0x1800118f9  movzx   edx, word ptr [rax]
0x1800118fc  movzx   ecx, word ptr [rax+r8]
0x180011901  sub     edx, ecx
0x180011903  jnz     short loc_18001190D
0x180011905  add     rax, 2
0x180011909  test    ecx, ecx
0x18001190b  jnz     short loc_1800118F9
0x18001190d  test    edx, edx
0x18001190f  jz      short loc_18001191F
0x180011911  lea     rcx, [rsp+2A0h+var_230]; this
0x180011916  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001191b  inc     edi
0x18001191d  jmp     short loc_1800118A8
0x18001191f  mov     rax, [r13+20h]
0x180011923  mov     r15d, 1
0x180011929  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x18001192e  mov     rcx, [rax+rdi*8]
0x180011932  mov     [rsi], rcx
0x180011935  lea     rcx, [rsp+2A0h+var_230]; this
0x18001193a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001193f  jmp     short loc_180011946
0x180011941  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x180011946  lea     rcx, [rsp+2A0h+var_260]; this
0x18001194b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011950  jmp     loc_18001174C
0x180011955  lea     rcx, [rsp+2A0h+var_230]; this
0x18001195a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001195f  lea     rcx, [rsp+2A0h+var_260]; this
0x180011964  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011969  jmp     loc_18001175D
0x18001196e  mov     rax, [r13+20h]
0x180011972  mov     rcx, [rax]
0x180011975  mov     [rsi], rcx
0x180011978  jmp     loc_18001175D
```
