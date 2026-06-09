# CONFIG_FILE::FindOrCreateParent(IConfigDomNode *,ushort const *,IConfigDomNode * *)

- ea: `0x1800262cc`
- end: `0x1800265be`
- name: `?FindOrCreateParent@CONFIG_FILE@@QEAAJPEAVIConfigDomNode@@PEBGPEAPEAV2@@Z`
- size: `754`
- prototype: `int(CONFIG_FILE *__hidden this, struct IConfigDomNode *, const unsigned __int16 *, struct IConfigDomNode **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180024780`

## callees

- `0x1800262cc`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002638a`
- `msvcrt!wcschr` at `0x180026501`
- `msvcrt!wcschr` at `0x18002638a`
- `msvcrt!wcschr` at `0x180026501`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002658e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026599`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002658e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026599`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002642b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026439`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800264b0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002642b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026439`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800264b0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026330`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026351`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026330`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026351`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800263b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002652f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800263b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002652f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800263a9`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180026520`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800263a9`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180026520`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800263cc`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800263cc`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::FindOrCreateParent(
        CONFIG_FILE *this,
        struct IConfigDomNode *a2,
        const unsigned __int16 *a3,
        struct IConfigDomNode **a4)
{
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  int v9; // eax
  const wchar_t *v10; // rsi
  int v11; // ebx
  struct IConfigDomNode *v12; // rcx
  unsigned __int16 *Str; // rbx
  unsigned __int16 *v14; // rax
  signed __int64 v15; // rbx
  int v16; // edx
  int v17; // ecx
  __int64 (__fastcall *v18)(struct IConfigDomNode *, unsigned __int16 *, struct IConfigDomNode **, __int64, int); // rbx
  unsigned __int16 *v19; // rax
  struct IConfigDomNode *v20; // rcx
  wchar_t *v21; // rax
  wchar_t *v22; // rbx
  struct IConfigDomNode *v24; // [rsp+30h] [rbp-D0h] BYREF
  struct IConfigDomNode *v25; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v28[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v29[64]; // [rsp+130h] [rbp+30h] BYREF

  v24 = 0;
  v25 = 0;
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v26, v28, 0x40u);
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v27, v29, 0x40u);
  if ( a2 && a3 && a4 )
  {
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)a2 + 128LL))(a2);
    v7 = wcschr(a3, 0x2Fu);
    v8 = v7;
    if ( v7 )
    {
      v9 = STRU::Copy((STRU *)v26, a3, v7 - a3);
      v10 = v8 + 1;
    }
    else
    {
      v9 = STRU::Copy((STRU *)v26, a3);
      v10 = 0;
    }
    v11 = v9;
    if ( v9 < 0 )
    {
LABEL_27:
      v20 = v24;
      goto LABEL_30;
    }
    while ( !STRU::IsEmpty((STRU *)v26) )
    {
      v11 = (*(__int64 (__fastcall **)(struct IConfigDomNode *, struct IConfigDomNode **, _QWORD))(*(_QWORD *)a2 + 8LL))(
              a2,
              &v24,
              0);
      if ( v11 < 0 )
        goto LABEL_27;
      v12 = v24;
      while ( v12 )
      {
        v11 = (**(__int64 (__fastcall ***)(struct IConfigDomNode *, _BYTE *, _QWORD))v12)(v12, v27, 0);
        if ( v11 < 0 )
          goto LABEL_27;
        Str = STRU::QueryStr((STRU *)v26);
        v14 = STRU::QueryStr((STRU *)v27);
        v15 = (char *)Str - (char *)v14;
        do
        {
          v16 = *(unsigned __int16 *)((char *)v14 + v15);
          v17 = *v14 - v16;
          if ( v17 )
            break;
          ++v14;
        }
        while ( v16 );
        if ( !v17 )
        {
          if ( v24 )
            goto LABEL_21;
          break;
        }
        v11 = (*(__int64 (__fastcall **)(struct IConfigDomNode *, struct IConfigDomNode **, _QWORD))(*(_QWORD *)v24 + 16LL))(
                v24,
                &v25,
                0);
        if ( v11 < 0 )
          goto LABEL_27;
        (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v24 + 120LL))(v24);
        v12 = v25;
        v24 = v25;
      }
      v18 = *(__int64 (__fastcall **)(struct IConfigDomNode *, unsigned __int16 *, struct IConfigDomNode **, __int64, int))(*(_QWORD *)a2 + 72LL);
      v19 = STRU::QueryStr((STRU *)v26);
      v11 = v18(a2, v19, &v24, 0xFFFFFFFFLL, 1);
      if ( v11 < 0 )
        goto LABEL_27;
LABEL_21:
      (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)a2 + 120LL))(a2);
      a2 = v24;
      v20 = 0;
      v24 = 0;
      if ( !v10 )
        goto LABEL_26;
      v21 = wcschr(v10, 0x2Fu);
      v22 = v21;
      if ( v21 )
      {
        STRU::Copy((STRU *)v26, v10, v21 - v10);
        v10 = v22 + 1;
      }
      else
      {
        STRU::Copy((STRU *)v26, v10);
        v10 = 0;
      }
    }
    v20 = v24;
LABEL_26:
    v11 = 0;
    *a4 = a2;
  }
  else
  {
    v20 = v24;
    v11 = -2147024809;
  }
  a2 = 0;
LABEL_30:
  if ( v20 )
  {
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v20 + 120LL))(v20);
    v24 = 0;
  }
  if ( a2 )
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)a2 + 120LL))(a2);
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800262cc  push    rbp
0x1800262ce  push    rbx
0x1800262cf  push    rsi
0x1800262d0  push    rdi
0x1800262d1  push    r14
0x1800262d3  lea     rbp, [rsp-0C0h]
0x1800262db  sub     rsp, 1C0h
0x1800262e2  mov     rax, cs:__security_cookie
0x1800262e9  xor     rax, rsp
0x1800262ec  mov     [rbp+0E0h+var_30], rax
0x1800262f3  mov     rbx, r8
0x1800262f6  mov     [rsp+1E0h+var_1B0], 0
0x1800262ff  mov     rdi, rdx
0x180026302  mov     [rsp+1E0h+var_1A8], 0
0x18002630b  xor     edx, edx; Val
0x18002630d  lea     rcx, [rbp+0E0h+var_130]; void *
0x180026311  mov     r8d, 80h; Size
0x180026317  mov     r14, r9
0x18002631a  call    memset_0
0x18002631f  mov     esi, 40h ; '@'
0x180026324  lea     rdx, [rbp+0E0h+var_130]
0x180026328  mov     r8d, esi
0x18002632b  lea     rcx, [rsp+1E0h+var_1A0]
0x180026330  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180026336  xor     edx, edx; Val
0x180026338  lea     r8d, [rsi+40h]; Size
0x18002633c  lea     rcx, [rbp+0E0h+var_B0]; void *
0x180026340  call    memset_0
0x180026345  mov     r8d, esi
0x180026348  lea     rdx, [rbp+0E0h+var_B0]
0x18002634c  lea     rcx, [rsp+1E0h+var_168]
0x180026351  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180026357  test    rdi, rdi
0x18002635a  jz      loc_18002654F
0x180026360  test    rbx, rbx
0x180026363  jz      loc_18002654F
0x180026369  test    r14, r14
0x18002636c  jz      loc_18002654F
0x180026372  mov     rax, [rdi]
0x180026375  mov     rcx, rdi
0x180026378  mov     rax, [rax+80h]
0x18002637f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026384  lea     edx, [rsi-11h]; Ch
0x180026387  mov     rcx, rbx; Str
0x18002638a  call    cs:__imp_wcschr
0x180026390  mov     rdx, rbx
0x180026393  lea     rcx, [rsp+1E0h+var_1A0]
0x180026398  mov     rsi, rax
0x18002639b  test    rax, rax
0x18002639e  jz      short loc_1800263B5
0x1800263a0  mov     r8, rax
0x1800263a3  sub     r8, rbx
0x1800263a6  sar     r8, 1
0x1800263a9  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800263af  add     rsi, 2
0x1800263b3  jmp     short loc_1800263BD
0x1800263b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800263bb  xor     esi, esi
0x1800263bd  mov     ebx, eax
0x1800263bf  test    eax, eax
0x1800263c1  js      loc_180026548
0x1800263c7  lea     rcx, [rsp+1E0h+var_1A0]
0x1800263cc  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800263d2  test    al, al
0x1800263d4  jnz     loc_18002653C
0x1800263da  mov     rax, [rdi]
0x1800263dd  lea     rdx, [rsp+1E0h+var_1B0]
0x1800263e2  xor     r8d, r8d
0x1800263e5  mov     rcx, rdi
0x1800263e8  mov     rax, [rax+8]
0x1800263ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263f1  mov     ebx, eax
0x1800263f3  test    eax, eax
0x1800263f5  js      loc_180026548
0x1800263fb  mov     rcx, [rsp+1E0h+var_1B0]
0x180026400  test    rcx, rcx
0x180026403  jz      loc_1800264A4
0x180026409  mov     rax, [rcx]
0x18002640c  lea     rdx, [rsp+1E0h+var_168]
0x180026411  xor     r8d, r8d
0x180026414  mov     rax, [rax]
0x180026417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002641c  mov     ebx, eax
0x18002641e  test    eax, eax
0x180026420  js      loc_180026548
0x180026426  lea     rcx, [rsp+1E0h+var_1A0]
0x18002642b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026431  lea     rcx, [rsp+1E0h+var_168]
0x180026436  mov     rbx, rax
0x180026439  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002643f  sub     rbx, rax
0x180026442  movzx   ecx, word ptr [rax]
0x180026445  movzx   edx, word ptr [rax+rbx]
0x180026449  sub     ecx, edx
0x18002644b  jnz     short loc_180026455
0x18002644d  add     rax, 2
0x180026451  test    edx, edx
0x180026453  jnz     short loc_180026442
0x180026455  test    ecx, ecx
0x180026457  jz      short loc_18002649C
0x180026459  mov     rcx, [rsp+1E0h+var_1B0]
0x18002645e  lea     rdx, [rsp+1E0h+var_1A8]
0x180026463  xor     r8d, r8d
0x180026466  mov     rax, [rcx]
0x180026469  mov     rax, [rax+10h]
0x18002646d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026472  mov     ebx, eax
0x180026474  test    eax, eax
0x180026476  js      loc_180026548
0x18002647c  mov     rcx, [rsp+1E0h+var_1B0]
0x180026481  mov     rax, [rcx]
0x180026484  mov     rax, [rax+78h]
0x180026488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002648d  mov     rcx, [rsp+1E0h+var_1A8]
0x180026492  mov     [rsp+1E0h+var_1B0], rcx
0x180026497  jmp     loc_180026400
0x18002649c  cmp     [rsp+1E0h+var_1B0], 0
0x1800264a2  jnz     short loc_1800264DB
0x1800264a4  mov     rax, [rdi]
0x1800264a7  lea     rcx, [rsp+1E0h+var_1A0]
0x1800264ac  mov     rbx, [rax+48h]
0x1800264b0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800264b6  or      r9d, 0FFFFFFFFh
0x1800264ba  mov     [rsp+1E0h+var_1C0], 1
0x1800264c2  mov     rdx, rax
0x1800264c5  lea     r8, [rsp+1E0h+var_1B0]
0x1800264ca  mov     rax, rbx
0x1800264cd  mov     rcx, rdi
0x1800264d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264d5  mov     ebx, eax
0x1800264d7  test    eax, eax
0x1800264d9  js      short loc_180026548
0x1800264db  mov     rax, [rdi]
0x1800264de  mov     rcx, rdi
0x1800264e1  mov     rax, [rax+78h]
0x1800264e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ea  mov     rdi, [rsp+1E0h+var_1B0]
0x1800264ef  xor     ecx, ecx
0x1800264f1  mov     [rsp+1E0h+var_1B0], rcx
0x1800264f6  test    rsi, rsi
0x1800264f9  jz      short loc_180026541
0x1800264fb  lea     edx, [rcx+2Fh]; Ch
0x1800264fe  mov     rcx, rsi; Str
0x180026501  call    cs:__imp_wcschr
0x180026507  mov     rdx, rsi
0x18002650a  lea     rcx, [rsp+1E0h+var_1A0]
0x18002650f  mov     rbx, rax
0x180026512  test    rax, rax
0x180026515  jz      short loc_18002652F
0x180026517  mov     r8, rax
0x18002651a  sub     r8, rsi
0x18002651d  sar     r8, 1
0x180026520  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180026526  lea     rsi, [rbx+2]
0x18002652a  jmp     loc_1800263C7
0x18002652f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026535  xor     esi, esi
0x180026537  jmp     loc_1800263C7
0x18002653c  mov     rcx, [rsp+1E0h+var_1B0]
0x180026541  xor     ebx, ebx
0x180026543  mov     [r14], rdi
0x180026546  jmp     short loc_180026559
0x180026548  mov     rcx, [rsp+1E0h+var_1B0]
0x18002654d  jmp     short loc_18002655B
0x18002654f  mov     rcx, [rsp+1E0h+var_1B0]
0x180026554  mov     ebx, 80070057h
0x180026559  xor     edi, edi
0x18002655b  test    rcx, rcx
0x18002655e  jz      short loc_180026575
0x180026560  mov     rax, [rcx]
0x180026563  mov     rax, [rax+78h]
0x180026567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002656c  mov     [rsp+1E0h+var_1B0], 0
0x180026575  test    rdi, rdi
0x180026578  jz      short loc_180026589
0x18002657a  mov     rax, [rdi]
0x18002657d  mov     rcx, rdi
0x180026580  mov     rax, [rax+78h]
0x180026584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026589  lea     rcx, [rsp+1E0h+var_168]
0x18002658e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180026594  lea     rcx, [rsp+1E0h+var_1A0]
0x180026599  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002659f  mov     eax, ebx
0x1800265a1  mov     rcx, [rbp+0E0h+var_30]
0x1800265a8  xor     rcx, rsp; StackCookie
0x1800265ab  call    __security_check_cookie
0x1800265b0  add     rsp, 1C0h
0x1800265b7  pop     r14
0x1800265b9  pop     rdi
0x1800265ba  pop     rsi
0x1800265bb  pop     rbx
0x1800265bc  pop     rbp
0x1800265bd  retn
```
