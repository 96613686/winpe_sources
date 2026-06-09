# MyNextChar

- ea: `0x1800b7550`
- end: `0x1800b76c0`
- name: `MyNextChar`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b6400`
- `0x1800b7744`

## callees

- `0x180063c48`
- `0x1800b7550`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800b7634`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800b7634`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b756a`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b756a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800b7666`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800b7666`

## pseudocode

```c
BYTE *__fastcall MyNextChar(BYTE *a1, _BYTE *a2, unsigned int *a3)
{
  BYTE *v3; // rbx
  BOOL v6; // eax
  unsigned int v7; // ecx
  _BYTE *v8; // rdx
  unsigned int v9; // eax
  CHAR *v10; // rdx
  signed int v11; // r8d
  CHAR *v12; // rdi
  CHAR v13; // al
  __int64 v14; // rcx
  bool v15; // zf
  __int64 v16; // r8
  CHAR String1; // [rsp+50h] [rbp+18h] BYREF

  v3 = a1;
  v6 = IsDBCSLeadByte(*a1);
  v7 = *a3;
  if ( v6 )
  {
    v7 = v7 & 0xFFFFFFFC | 1;
  }
  else
  {
    if ( (v7 & 1) == 0 )
    {
      *a3 = 0;
      goto LABEL_8;
    }
    v7 = v7 & 0xFFFFFFFC | 2;
  }
  *a3 = v7;
  if ( (v7 & 2) != 0 )
  {
LABEL_6:
    LOBYTE(v7) = *v3;
    goto LABEL_28;
  }
LABEL_8:
  LOBYTE(v7) = 94;
  if ( *v3 == 94 )
  {
    v8 = v3 + 1;
    if ( v3[1] )
    {
      v7 = (char)*v8;
      if ( v7 - 64 > 0x1F )
      {
        v9 = v7 - 97;
        LOBYTE(v7) = *v8;
        if ( v9 <= 0x19 )
        {
          ++v3;
          LOBYTE(v7) = v7 - 96;
        }
      }
      else
      {
        ++v3;
        LOBYTE(v7) = *v8 - 64;
      }
    }
  }
  else
  {
    if ( *v3 == 60 )
    {
      v10 = (CHAR *)(v3 + 1);
      v11 = 0;
      v12 = (CHAR *)v3;
      if ( v3[1] )
      {
        do
        {
          if ( (unsigned int)v11 >= 3 )
            break;
          v13 = *v10;
          v12 = v10;
          v14 = v11;
          ++v10;
          ++v11;
          v15 = *v10 == 0;
          *(&String1 + v14) = v13;
        }
        while ( !v15 );
      }
      if ( (unsigned __int64)v11 >= 4 )
        _report_rangecheckfailure();
      *(&String1 + v11) = 0;
      if ( !lstrcmpA(&String1, "cr>") )
      {
        v3 = (BYTE *)v12;
        LOBYTE(v7) = 13;
        goto LABEL_28;
      }
      if ( CompareStringA(0x7Fu, 1u, &String1, -1, "lf>", -1) == 2 )
      {
        v3 = (BYTE *)v12;
        LOBYTE(v7) = 10;
        goto LABEL_28;
      }
      goto LABEL_6;
    }
    LOBYTE(v7) = *v3;
    if ( *v3 == 92 )
    {
      LOBYTE(v7) = v3[1];
      if ( (unsigned __int8)(v7 - 34) <= 0x3Cu && (v16 = 0x1400000004000001LL, _bittest64(&v16, v7 - 34)) )
        ++v3;
      else
        LOBYTE(v7) = 92;
    }
  }
LABEL_28:
  *a2 = v7;
  return v3 + 1;
}

```

## disassembly

```asm
0x1800b7550  mov     [rsp+arg_0], rbx
0x1800b7555  mov     [rsp+arg_8], rsi
0x1800b755a  push    rdi
0x1800b755b  sub     rsp, 30h
0x1800b755f  mov     rbx, rcx
0x1800b7562  mov     rdi, r8
0x1800b7565  mov     cl, [rcx]; TestChar
0x1800b7567  mov     rsi, rdx
0x1800b756a  call    cs:__imp_IsDBCSLeadByte
0x1800b7570  mov     ecx, [rdi]
0x1800b7572  test    eax, eax
0x1800b7574  jz      short loc_1800B757E
0x1800b7576  and     ecx, 0FFFFFFFDh
0x1800b7579  or      ecx, 1
0x1800b757c  jmp     short loc_1800B7589
0x1800b757e  test    cl, 1
0x1800b7581  jz      short loc_1800B7597
0x1800b7583  and     ecx, 0FFFFFFFEh
0x1800b7586  or      ecx, 2
0x1800b7589  mov     [rdi], ecx
0x1800b758b  test    cl, 2
0x1800b758e  jz      short loc_1800B759D
0x1800b7590  mov     cl, [rbx]
0x1800b7592  jmp     loc_1800B76A4
0x1800b7597  mov     dword ptr [rdi], 0
0x1800b759d  mov     cl, 5Eh ; '^'
0x1800b759f  cmp     [rbx], cl
0x1800b75a1  jnz     short loc_1800B75E1
0x1800b75a3  lea     rdx, [rbx+1]
0x1800b75a7  cmp     byte ptr [rdx], 0
0x1800b75aa  jz      loc_1800B76A4
0x1800b75b0  movsx   ecx, byte ptr [rdx]
0x1800b75b3  lea     eax, [rcx-40h]
0x1800b75b6  cmp     eax, 1Fh
0x1800b75b9  ja      short loc_1800B75C8
0x1800b75bb  mov     cl, [rdx]
0x1800b75bd  mov     rbx, rdx
0x1800b75c0  sub     cl, 40h ; '@'
0x1800b75c3  jmp     loc_1800B76A4
0x1800b75c8  lea     eax, [rcx-61h]
0x1800b75cb  mov     cl, [rdx]
0x1800b75cd  cmp     eax, 19h
0x1800b75d0  ja      loc_1800B76A4
0x1800b75d6  mov     rbx, rdx
0x1800b75d9  sub     cl, 60h ; '`'
0x1800b75dc  jmp     loc_1800B76A4
0x1800b75e1  cmp     byte ptr [rbx], 3Ch ; '<'
0x1800b75e4  jnz     loc_1800B767C
0x1800b75ea  lea     rdx, [rbx+1]
0x1800b75ee  xor     r8d, r8d
0x1800b75f1  mov     rdi, rbx
0x1800b75f4  cmp     [rdx], r8b
0x1800b75f7  jz      short loc_1800B7616
0x1800b75f9  cmp     r8d, 3
0x1800b75fd  jnb     short loc_1800B7616
0x1800b75ff  mov     al, [rdx]
0x1800b7601  mov     rdi, rdx
0x1800b7604  movsxd  rcx, r8d
0x1800b7607  inc     rdx
0x1800b760a  inc     r8d
0x1800b760d  cmp     byte ptr [rdx], 0
0x1800b7610  mov     [rsp+rcx+38h+String1], al
0x1800b7614  jnz     short loc_1800B75F9
0x1800b7616  movsxd  rax, r8d
0x1800b7619  cmp     rax, 4
0x1800b761d  jnb     loc_1800B76BA
0x1800b7623  lea     rdx, aCr; "cr>"
0x1800b762a  mov     [rsp+rax+38h+String1], 0
0x1800b762f  lea     rcx, [rsp+38h+String1]; lpString1
0x1800b7634  call    cs:__imp_lstrcmpA
0x1800b763a  test    eax, eax
0x1800b763c  jnz     short loc_1800B7645
0x1800b763e  mov     rbx, rdi
0x1800b7641  mov     cl, 0Dh
0x1800b7643  jmp     short loc_1800B76A4
0x1800b7645  or      r9d, 0FFFFFFFFh; cchCount1
0x1800b7649  lea     rax, aLf; "lf>"
0x1800b7650  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800b7655  lea     r8, [rsp+38h+String1]; lpString1
0x1800b765a  mov     [rsp+38h+lpString2], rax; lpString2
0x1800b765f  lea     edx, [r9+2]; dwCmpFlags
0x1800b7663  lea     ecx, [rdx+7Eh]; Locale
0x1800b7666  call    cs:__imp_CompareStringA
0x1800b766c  cmp     eax, 2
0x1800b766f  jnz     loc_1800B7590
0x1800b7675  mov     rbx, rdi
0x1800b7678  mov     cl, 0Ah
0x1800b767a  jmp     short loc_1800B76A4
0x1800b767c  mov     cl, [rbx]
0x1800b767e  cmp     cl, 5Ch ; '\'
0x1800b7681  jnz     short loc_1800B76A4
0x1800b7683  mov     cl, [rbx+1]
0x1800b7686  lea     eax, [rcx-22h]
0x1800b7689  cmp     al, 3Ch ; '<'
0x1800b768b  ja      short loc_1800B76A2
0x1800b768d  mov     r8, 1400000004000001h
0x1800b7697  bt      r8, rax
0x1800b769b  jnb     short loc_1800B76A2
0x1800b769d  inc     rbx
0x1800b76a0  jmp     short loc_1800B76A4
0x1800b76a2  mov     cl, 5Ch ; '\'
0x1800b76a4  mov     [rsi], cl
0x1800b76a6  lea     rax, [rbx+1]
0x1800b76aa  mov     rbx, [rsp+38h+arg_0]
0x1800b76af  mov     rsi, [rsp+38h+arg_8]
0x1800b76b4  add     rsp, 30h
0x1800b76b8  pop     rdi
0x1800b76b9  retn
0x1800b76ba  call    __report_rangecheckfailure
```
