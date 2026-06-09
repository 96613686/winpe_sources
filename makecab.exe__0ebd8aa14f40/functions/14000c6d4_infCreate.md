# infCreate

- ea: `0x14000c6d4`
- end: `0x14000caa5`
- name: `infCreate`
- size: `977`
- prototype: `__int64 __fastcall(void *Src, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140007934`

## callees

- `0x140008620`
- `0x140009b38`
- `0x14000ae78`
- `0x14000c6d4`
- `0x14000caac`
- `0x14000d70c`
- `0x14000dfd8`
- `0x14000e406`
- `0x14000e412`
- `0x14000e450`

## import_xrefs

- `msvcrt!fprintf` at `0x14000c9e9`
- `msvcrt!fprintf` at `0x14000c9e9`
- `msvcrt!fclose` at `0x14000c969`
- `msvcrt!fclose` at `0x14000c969`
- `msvcrt!fopen` at `0x14000c897`
- `msvcrt!fopen` at `0x14000c897`
- `msvcrt!toupper` at `0x14000c7d2`
- `msvcrt!toupper` at `0x14000c7d2`
- `msvcrt!malloc` at `0x14000c720`
- `msvcrt!malloc` at `0x14000c8c7`
- `msvcrt!malloc` at `0x14000c720`
- `msvcrt!malloc` at `0x14000c8c7`
- `msvcrt!free` at `0x14000c8ba`
- `msvcrt!free` at `0x14000c914`
- `msvcrt!free` at `0x14000c946`
- `msvcrt!free` at `0x14000c955`
- `msvcrt!free` at `0x14000c95e`
- `msvcrt!free` at `0x14000c9ac`
- `msvcrt!free` at `0x14000c8ba`
- `msvcrt!free` at `0x14000c914`
- `msvcrt!free` at `0x14000c946`
- `msvcrt!free` at `0x14000c955`
- `msvcrt!free` at `0x14000c95e`
- `msvcrt!free` at `0x14000c9ac`
- `msvcrt!_strdup` at `0x14000c8e8`
- `msvcrt!_strdup` at `0x14000c8fa`
- `msvcrt!_strdup` at `0x14000c8e8`
- `msvcrt!_strdup` at `0x14000c8fa`

## string_xrefs

- `0x14000c983`: `Cannot create %1`
- `0x14000c99d`: `Cannot create %1: %2`
- `0x14000c9fb`: `INF header variable template`

## pseudocode

```c
_QWORD *__fastcall infCreate(void *Src, __int64 a2)
{
  _QWORD *v4; // rbp
  const char *v5; // r8
  _QWORD *result; // rax
  __int64 v7; // rax
  const char *v8; // r14
  int v9; // eax
  int v10; // eax
  const char *v11; // rdx
  char **v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  const char *v15; // r15
  const char *v16; // r12
  int v17; // ebx
  char *v18; // rax
  char *v19; // rsi
  FILE **v20; // rax
  FILE **v21; // rbx
  char *v22; // rax
  char *v23; // rax
  FILE *v24; // rcx
  FILE *v25; // rcx
  FILE *v26; // rsi
  int v27; // ebx
  __int64 v28; // rax
  __int64 v29; // [rsp+30h] [rbp-CD8h]
  FILE *Stream; // [rsp+40h] [rbp-CC8h]
  _BYTE v31[4]; // [rsp+50h] [rbp-CB8h] BYREF
  int v32; // [rsp+54h] [rbp-CB4h]
  _QWORD *v33; // [rsp+E0h] [rbp-C28h]
  char pszDest[32]; // [rsp+CA0h] [rbp-68h] BYREF

  v32 = 0;
  memset_0(v31, 0, 0xC4Cu);
  v4 = malloc(0x218u);
  if ( v4 )
  {
    *(_OWORD *)v4 = 0;
    v4[2] = 0;
    memcpy_0(v31, Src, 0xC50u);
    v33 = v4;
    if ( (unsigned int)checkInfLineFormats(v31, a2) )
    {
      v7 = VarFind(*((_QWORD *)Src + 2), "InfSectionOrder", a2);
      v8 = "DCF";
      if ( v7 )
        v8 = *(const char **)(v7 + 8);
      while ( 1 )
      {
        if ( !*v8 )
        {
          *((_DWORD *)Src + 40) = 1;
          result = v4;
          *((_QWORD *)Src + 18) = v4;
          return result;
        }
        v9 = toupper(*v8) - 67;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 != 2 )
              return 0;
            v11 = "InfFileHeader";
            v12 = off_140010AB0;
            v29 = 2;
          }
          else
          {
            v11 = "InfDiskHeader";
            v12 = atfi;
            v29 = 0;
          }
        }
        else
        {
          v11 = "InfCabinetHeader";
          v12 = off_140010A98;
          v29 = 1;
        }
        v13 = VarFind(*((_QWORD *)Src + 2), v11, a2);
        v15 = ";";
        if ( v13 )
          v15 = *(const char **)(v13 + 8);
        v16 = *v12;
        v17 = 0;
        while ( 1 )
        {
          v18 = my_tempnam(v14, "inf");
          v19 = v18;
          if ( v18 )
          {
            Stream = fopen(v18, "wt");
            if ( Stream )
            {
              v20 = (FILE **)malloc(0x18u);
              v21 = v20;
              if ( v20 )
              {
                v20[1] = 0;
                v20[2] = 0;
                v22 = _strdup(v19);
                v21[1] = (FILE *)v22;
                if ( v22 )
                {
                  v23 = _strdup(v16);
                  v21[2] = (FILE *)v23;
                  if ( v23 )
                  {
                    *v21 = Stream;
                    free(v19);
                    goto LABEL_37;
                  }
                }
              }
              ErrSet(a2, "Out of memorying creating %1", "%s", v16);
              if ( v21 )
              {
                v24 = v21[2];
                if ( v24 )
                  free(v24);
                v25 = v21[1];
                if ( v25 )
                  free(v25);
                free(v21);
              }
              fclose(Stream);
              goto LABEL_35;
            }
          }
          if ( ++v17 > 100 )
            break;
          if ( v19 )
            free(v19);
        }
        if ( !v19 )
        {
          ErrSet(a2, "Cannot create %1", "%s", v16);
          goto LABEL_36;
        }
        ErrSet(a2, "Cannot create %1: %2", "%s%s", v16, v19);
LABEL_35:
        free(v19);
LABEL_36:
        v21 = 0;
LABEL_37:
        v4[v29] = v21;
        if ( !v21 )
          break;
        v26 = *v21;
        v27 = 1;
        if ( v15 )
        {
          while ( fprintf(v26, "%s\n", v15) >= 0
               && (unsigned int)nameFromTemplate(pszDest, (__int64)"INF header variable template", a2) )
          {
            v28 = VarFind(*((_QWORD *)Src + 2), pszDest, a2);
            if ( !v28 )
            {
              *(_DWORD *)(a2 + 512) = 0;
              *(_BYTE *)a2 = 0;
              *(_DWORD *)(a2 + 544) = 0;
              *(_QWORD *)(a2 + 552) = 0;
              goto LABEL_45;
            }
            v15 = *(const char **)(v28 + 8);
            ++v27;
            if ( !v15 )
              goto LABEL_45;
          }
          break;
        }
LABEL_45:
        ++v8;
      }
      infDestroy(v4);
    }
  }
  else
  {
    ErrSet(a2, "Out of memory creating INF file", v5);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c6d4  mov     [rsp+arg_10], rbx
0x14000c6d9  push    rbp
0x14000c6da  push    rsi
0x14000c6db  push    rdi
0x14000c6dc  push    r12
0x14000c6de  push    r13
0x14000c6e0  push    r14
0x14000c6e2  push    r15
0x14000c6e4  sub     rsp, 0CD0h
0x14000c6eb  mov     rax, cs:__security_cookie
0x14000c6f2  xor     rax, rsp
0x14000c6f5  mov     [rsp+0D08h+var_48], rax
0x14000c6fd  mov     rdi, rdx
0x14000c700  mov     r13, rcx
0x14000c703  xor     eax, eax
0x14000c705  lea     rcx, [rsp+0D08h+var_CB8]; void *
0x14000c70a  xor     edx, edx; Val
0x14000c70c  mov     [rsp+0D08h+var_CB4], eax
0x14000c710  mov     r8d, 0C4Ch; Size
0x14000c716  call    memset_0
0x14000c71b  mov     ecx, 218h; Size
0x14000c720  call    cs:__imp_malloc
0x14000c726  mov     rbp, rax
0x14000c729  test    rax, rax
0x14000c72c  jnz     short loc_14000C76A
0x14000c72e  lea     rdx, aOutOfMemoryCre_0; "Out of memory creating INF file"
0x14000c735  mov     rcx, rdi
0x14000c738  call    ErrSet
0x14000c73d  xor     eax, eax
0x14000c73f  mov     rcx, [rsp+0D08h+var_48]
0x14000c747  xor     rcx, rsp; StackCookie
0x14000c74a  call    __security_check_cookie
0x14000c74f  mov     rbx, [rsp+0D08h+arg_10]
0x14000c757  add     rsp, 0CD0h
0x14000c75e  pop     r15
0x14000c760  pop     r14
0x14000c762  pop     r13
0x14000c764  pop     r12
0x14000c766  pop     rdi
0x14000c767  pop     rsi
0x14000c768  pop     rbp
0x14000c769  retn
0x14000c76a  xorps   xmm0, xmm0
0x14000c76d  lea     rcx, [rsp+0D08h+var_CB8]; void *
0x14000c772  xor     eax, eax
0x14000c774  mov     rdx, r13; Src
0x14000c777  movups  xmmword ptr [rbp+0], xmm0
0x14000c77b  mov     r8d, 0C50h; Size
0x14000c781  mov     [rbp+10h], rax
0x14000c785  call    memcpy_0
0x14000c78a  mov     rdx, rdi
0x14000c78d  mov     [rsp+0D08h+var_C28], rbp
0x14000c795  lea     rcx, [rsp+0D08h+var_CB8]
0x14000c79a  call    checkInfLineFormats
0x14000c79f  test    eax, eax
0x14000c7a1  jz      short loc_14000C73D
0x14000c7a3  mov     rcx, [r13+10h]
0x14000c7a7  lea     rdx, aInfsectionorde; "InfSectionOrder"
0x14000c7ae  mov     r8, rdi
0x14000c7b1  call    VarFind
0x14000c7b6  lea     r14, aDcf; "DCF"
0x14000c7bd  test    rax, rax
0x14000c7c0  jz      loc_14000CA70
0x14000c7c6  mov     r14, [rax+8]
0x14000c7ca  jmp     loc_14000CA70
0x14000c7cf  movsx   ecx, al; C
0x14000c7d2  call    cs:__imp_toupper
0x14000c7d8  sub     eax, 43h ; 'C'
0x14000c7db  jz      short loc_14000C835
0x14000c7dd  sub     eax, 1
0x14000c7e0  jz      short loc_14000C810
0x14000c7e2  cmp     eax, 2
0x14000c7e5  jnz     loc_14000C73D
0x14000c7eb  mov     rdx, cs:off_140010AB8; "InfFileHeader"
0x14000c7f2  lea     rsi, off_140010AC0; "InfFileHeader*"
0x14000c7f9  mov     [rsp+0D08h+var_CD0], rsi
0x14000c7fe  lea     rbx, off_140010AB0; "INF files temporary file"
0x14000c805  mov     [rsp+0D08h+var_CD8], 10h
0x14000c80e  jmp     short loc_14000C858
0x14000c810  mov     rdx, cs:off_140010A88; "InfDiskHeader"
0x14000c817  lea     rsi, off_140010A90; "InfDiskHeader*"
0x14000c81e  mov     [rsp+0D08h+var_CD0], rsi
0x14000c823  lea     rbx, atfi
0x14000c82a  mov     [rsp+0D08h+var_CD8], 0
0x14000c833  jmp     short loc_14000C858
0x14000c835  mov     rdx, cs:off_140010AA0; "InfCabinetHeader"
0x14000c83c  lea     rax, off_140010AA8; "InfCabinetHeader*"
0x14000c843  mov     [rsp+0D08h+var_CD0], rax
0x14000c848  lea     rbx, off_140010A98; "INF cabinets temporary file"
0x14000c84f  mov     [rsp+0D08h+var_CD8], 8
0x14000c858  mov     rcx, [r13+10h]
0x14000c85c  mov     r8, rdi
0x14000c85f  call    VarFind
0x14000c864  lea     r15, asc_140011714; ";"
0x14000c86b  test    rax, rax
0x14000c86e  jz      short loc_14000C874
0x14000c870  mov     r15, [rax+8]
0x14000c874  mov     r12, [rbx]
0x14000c877  xor     ebx, ebx
0x14000c879  lea     rdx, aInf_0; "inf"
0x14000c880  call    my_tempnam
0x14000c885  mov     rsi, rax
0x14000c888  test    rax, rax
0x14000c88b  jz      short loc_14000C8A7
0x14000c88d  lea     rdx, Mode; "wt"
0x14000c894  mov     rcx, rax; FileName
0x14000c897  call    cs:__imp_fopen
0x14000c89d  mov     [rsp+0D08h+Stream], rax
0x14000c8a2  test    rax, rax
0x14000c8a5  jnz     short loc_14000C8C2
0x14000c8a7  inc     ebx
0x14000c8a9  cmp     ebx, 64h ; 'd'
0x14000c8ac  jg      loc_14000C971
0x14000c8b2  test    rsi, rsi
0x14000c8b5  jz      short loc_14000C879
0x14000c8b7  mov     rcx, rsi; Block
0x14000c8ba  call    cs:__imp_free
0x14000c8c0  jmp     short loc_14000C879
0x14000c8c2  mov     ecx, 18h; Size
0x14000c8c7  call    cs:__imp_malloc
0x14000c8cd  mov     rbx, rax
0x14000c8d0  test    rax, rax
0x14000c8d3  jz      short loc_14000C91F
0x14000c8d5  mov     rcx, rsi; Source
0x14000c8d8  mov     qword ptr [rax+8], 0
0x14000c8e0  mov     qword ptr [rax+10h], 0
0x14000c8e8  call    cs:__imp__strdup
0x14000c8ee  mov     [rbx+8], rax
0x14000c8f2  test    rax, rax
0x14000c8f5  jz      short loc_14000C91F
0x14000c8f7  mov     rcx, r12; Source
0x14000c8fa  call    cs:__imp__strdup
0x14000c900  mov     [rbx+10h], rax
0x14000c904  test    rax, rax
0x14000c907  jz      short loc_14000C91F
0x14000c909  mov     rcx, [rsp+0D08h+Stream]
0x14000c90e  mov     [rbx], rcx
0x14000c911  mov     rcx, rsi; Block
0x14000c914  call    cs:__imp_free
0x14000c91a  jmp     loc_14000C9B4
0x14000c91f  mov     r9, r12
0x14000c922  lea     r8, aS_4; "%s"
0x14000c929  lea     rdx, aOutOfMemorying; "Out of memorying creating %1"
0x14000c930  mov     rcx, rdi
0x14000c933  call    ErrSet
0x14000c938  test    rbx, rbx
0x14000c93b  jz      short loc_14000C964
0x14000c93d  mov     rcx, [rbx+10h]; Block
0x14000c941  test    rcx, rcx
0x14000c944  jz      short loc_14000C94C
0x14000c946  call    cs:__imp_free
0x14000c94c  mov     rcx, [rbx+8]; Block
0x14000c950  test    rcx, rcx
0x14000c953  jz      short loc_14000C95B
0x14000c955  call    cs:__imp_free
0x14000c95b  mov     rcx, rbx; Block
0x14000c95e  call    cs:__imp_free
0x14000c964  mov     rcx, [rsp+0D08h+Stream]; Stream
0x14000c969  call    cs:__imp_fclose
0x14000c96f  jmp     short loc_14000C9A9
0x14000c971  mov     r9, r12
0x14000c974  mov     rcx, rdi
0x14000c977  test    rsi, rsi
0x14000c97a  jnz     short loc_14000C991
0x14000c97c  lea     r8, aS_4; "%s"
0x14000c983  lea     rdx, aCannotCreate1; "Cannot create %1"
0x14000c98a  call    ErrSet
0x14000c98f  jmp     short loc_14000C9B2
0x14000c991  lea     r8, aSS_1; "%s%s"
0x14000c998  mov     [rsp+0D08h+var_CE8], rsi
0x14000c99d  lea     rdx, aCannotCreate12; "Cannot create %1: %2"
0x14000c9a4  call    ErrSet
0x14000c9a9  mov     rcx, rsi; Block
0x14000c9ac  call    cs:__imp_free
0x14000c9b2  xor     ebx, ebx
0x14000c9b4  mov     rax, [rsp+0D08h+var_CD8]
0x14000c9b9  mov     [rax+rbp], rbx
0x14000c9bd  test    rbx, rbx
0x14000c9c0  jz      loc_14000CA95
0x14000c9c6  mov     rsi, [rbx]
0x14000c9c9  mov     ebx, 1
0x14000c9ce  test    r15, r15
0x14000c9d1  jz      loc_14000CA6D
0x14000c9d7  mov     r12, [rsp+0D08h+var_CD0]
0x14000c9dc  mov     r8, r15
0x14000c9df  lea     rdx, aS_2; "%s\n"
0x14000c9e6  mov     rcx, rsi; Stream
0x14000c9e9  call    cs:__imp_fprintf
0x14000c9ef  test    eax, eax
0x14000c9f1  js      loc_14000CA95
0x14000c9f7  mov     r8, [r12]
0x14000c9fb  lea     rax, aInfHeaderVaria; "INF header variable template"
0x14000ca02  mov     [rsp+0D08h+var_CE0], rdi; __int64
0x14000ca07  lea     rcx, [rsp+0D08h+pszDest]; pszDest
0x14000ca0f  mov     r9d, ebx
0x14000ca12  mov     [rsp+0D08h+var_CE8], rax; __int64
0x14000ca17  mov     edx, 20h ; ' '
0x14000ca1c  call    nameFromTemplate
0x14000ca21  test    eax, eax
0x14000ca23  jz      short loc_14000CA95
0x14000ca25  mov     rcx, [r13+10h]
0x14000ca29  lea     rdx, [rsp+0D08h+pszDest]
0x14000ca31  mov     r8, rdi
0x14000ca34  call    VarFind
0x14000ca39  test    rax, rax
0x14000ca3c  jz      short loc_14000CA4B
0x14000ca3e  mov     r15, [rax+8]
0x14000ca42  inc     ebx
0x14000ca44  test    r15, r15
0x14000ca47  jnz     short loc_14000C9DC
0x14000ca49  jmp     short loc_14000CA6D
0x14000ca4b  mov     dword ptr [rdi+200h], 0
0x14000ca55  mov     byte ptr [rdi], 0
0x14000ca58  mov     dword ptr [rdi+220h], 0
0x14000ca62  mov     qword ptr [rdi+228h], 0
0x14000ca6d  inc     r14
0x14000ca70  mov     al, [r14]
0x14000ca73  test    al, al
0x14000ca75  jnz     loc_14000C7CF
0x14000ca7b  mov     dword ptr [r13+0A0h], 1
0x14000ca86  mov     rax, rbp
0x14000ca89  mov     [r13+90h], rbp
0x14000ca90  jmp     loc_14000C73F
0x14000ca95  mov     rdx, rdi
0x14000ca98  mov     rcx, rbp; Block
0x14000ca9b  call    infDestroy
0x14000caa0  jmp     loc_14000C73D
```
