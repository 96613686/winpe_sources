# SepSddlGetAclForString

- ea: `0x140017ce8`
- end: `0x140018135`
- name: `SepSddlGetAclForString`
- size: `1101`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140017c04`

## callees

- `0x14000101d`
- `0x1400084c0`
- `0x140017b10`
- `0x140017ce8`
- `0x14001813c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400180f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400180f2`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140018030`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140018030`
- `ntoskrnl!wcschr` at `0x140017d0a`
- `ntoskrnl!wcschr` at `0x140017d0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017db9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017df2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017db9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017df2`
- `ntoskrnl!SeExports` at `0x140018044`

## pseudocode

```c
__int64 __fastcall SepSddlGetAclForString(wchar_t *Str1, const void **a2, wchar_t **a3)
{
  wchar_t *v5; // rsi
  wchar_t *v6; // rax
  unsigned int v8; // r8d
  __int64 v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rcx
  int i; // r9d
  unsigned int v13; // r12d
  unsigned int v14; // ebx
  _QWORD *v15; // rax
  unsigned int v16; // ebp
  PVOID PoolWithTag; // rax
  _WORD *v18; // rdi
  const wchar_t *v19; // rdi
  const wchar_t *j; // rdi
  wchar_t v21; // ax
  unsigned int k; // esi
  __int64 v23; // r15
  const wchar_t *v24; // rdi
  int v25; // ecx
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // r9
  const wchar_t *v29; // rsi
  void *Sid; // rcx
  int v31; // edi
  ACCESS_MASK AccessMask; // [rsp+90h] [rbp+8h] BYREF
  int v33; // [rsp+98h] [rbp+10h]
  int v34; // [rsp+A0h] [rbp+18h] BYREF
  const wchar_t *v35; // [rsp+A8h] [rbp+20h] BYREF

  *a2 = 0;
  v5 = Str1;
  v6 = wcschr(Str1, 0x3Au);
  *a3 = v6;
  if ( v6 == v5 )
    return 3221225485LL;
  v8 = 0;
  if ( v6 )
  {
    v10 = v6 - 1;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    v10 = &v5[v9];
  }
  *a3 = v10;
  v11 = v5;
  for ( i = 0; v11 < v10; ++v11 )
  {
    if ( *v11 == 59 )
    {
      ++v8;
    }
    else if ( *v11 != 32 )
    {
      i = 1;
    }
  }
  v13 = v8 / 5;
  if ( v8 != 5 * (v8 / 5) || !v8 && i )
    return (unsigned int)-1073741811;
  v14 = 0;
  if ( v13 )
  {
    v16 = 48 * v13 + 8;
    if ( v16 > 0xFFFF )
      v16 = 0xFFFF;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
    *a2 = PoolWithTag;
    v18 = PoolWithTag;
    if ( PoolWithTag )
    {
      v34 = 8;
      memset(PoolWithTag, 0, v16);
      *v18 = 2;
      v18[1] = v16;
      *((_DWORD *)v18 + 1) = 0;
      v33 = 0;
      while ( 1 )
      {
        AccessMask = 0;
        while ( *v5 == 32 )
          ++v5;
        v19 = v5 + 1;
        if ( *v5 != 40 )
          v19 = v5;
        while ( *v19 == 32 )
          ++v19;
        if ( wcsnicmp_0(v19, L"A", 1u) )
          break;
        for ( j = v19 + 2; *j == 32; ++j )
          ;
        if ( *j != 59 )
          break;
        do
          v21 = *++j;
        while ( *j == 32 );
        if ( v21 != 59 )
        {
          do
          {
            if ( v21 == 32 )
            {
              do
                ++j;
              while ( *j == 32 );
            }
            for ( k = 0; k < 8; ++k )
            {
              v23 = 2LL * k;
              if ( !wcsnicmp_0(j, (&off_14000C250)[v23], LODWORD(qword_14000C258[v23])) )
              {
                AccessMask |= HIDWORD(qword_14000C258[v23]);
                j += LODWORD(qword_14000C258[v23]);
                goto LABEL_48;
              }
            }
            v35 = j;
            SepSddlParseWideStringUlong(j, &v35, &AccessMask);
            if ( v35 == j )
              goto LABEL_79;
            j = v35;
LABEL_48:
            v21 = *j;
          }
          while ( *j != 59 );
        }
        v24 = j + 1;
        v25 = 2;
        do
        {
          while ( *v24 == 32 )
            ++v24;
          if ( *v24 != 59 )
            v14 = -1073741811;
          ++v24;
          --v25;
        }
        while ( v25 );
        if ( v14 )
          goto LABEL_80;
        while ( *v24 == 32 )
          ++v24;
        v26 = 0;
        while ( wcsnicmp_0(v24, &aWd_0[12 * v26], (unsigned int)dword_14000C3A4[6 * v26]) )
        {
          v26 = (unsigned int)(v26 + 1);
          if ( (unsigned int)v26 >= 0xE )
          {
            v14 = -1073741709;
            goto LABEL_80;
          }
        }
        v29 = &v24[dword_14000C3A4[6 * v26]];
        if ( dword_14000C398[6 * v26] != 1 || IoIsWdmVersionAvailable(1u, 0x20u) )
          Sid = *(void **)((char *)&SeExports->SeCreateTokenPrivilege + qword_14000C390[3 * v26]);
        else
          Sid = 0;
        if ( !v29 )
          goto LABEL_78;
        while ( *v29 == 32 )
          ++v29;
        if ( *v29 != 41 )
        {
LABEL_78:
          v14 = -1073741705;
          goto LABEL_80;
        }
        v31 = v33;
        v14 = 0;
        if ( Sid )
        {
          v14 = SepSddlAddAceToAcl(a2, &v34, v27, v28, AccessMask, v13 - v33, Sid);
          if ( v14 )
            goto LABEL_80;
        }
        v5 = (wchar_t *)(v29 + 1);
        if ( *v5 == 40 )
          ++v5;
        v33 = v31 + 1;
        if ( v31 + 1 >= v13 )
        {
          *((_WORD *)*a2 + 1) = v34;
          return v14;
        }
      }
LABEL_79:
      v14 = -1073741811;
LABEL_80:
      ExFreePoolWithTag((PVOID)*a2, 0);
      *a2 = 0;
      return v14;
    }
    return (unsigned int)-1073741670;
  }
  v15 = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
  *a2 = v15;
  if ( !v15 )
    return (unsigned int)-1073741670;
  *v15 = 524290;
  return v14;
}

```

## disassembly

```asm
0x140017ce8  push    rbx
0x140017cea  push    rbp
0x140017ceb  push    rsi
0x140017cec  push    rdi
0x140017ced  push    r12
0x140017cef  push    r13
0x140017cf1  push    r14
0x140017cf3  push    r15
0x140017cf5  sub     rsp, 48h
0x140017cf9  xor     edi, edi
0x140017cfb  mov     r14, rdx
0x140017cfe  mov     [rdx], rdi
0x140017d01  mov     rbx, r8
0x140017d04  mov     rsi, rcx
0x140017d07  lea     edx, [rdi+3Ah]; Ch
0x140017d0a  call    cs:__imp_wcschr
0x140017d11  nop     dword ptr [rax+rax+00h]
0x140017d16  mov     [rbx], rax
0x140017d19  cmp     rax, rsi
0x140017d1c  jnz     short loc_140017D28
0x140017d1e  mov     eax, 0C000000Dh
0x140017d23  jmp     loc_140018123
0x140017d28  mov     r8d, edi
0x140017d2b  test    rax, rax
0x140017d2e  jnz     short loc_140017D43
0x140017d30  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017d34  inc     rax
0x140017d37  cmp     [rsi+rax*2], di
0x140017d3b  jnz     short loc_140017D34
0x140017d3d  lea     rax, [rsi+rax*2]
0x140017d41  jmp     short loc_140017D47
0x140017d43  add     rax, 0FFFFFFFFFFFFFFFEh
0x140017d47  mov     [rbx], rax
0x140017d4a  mov     rcx, rsi
0x140017d4d  mov     r9d, edi
0x140017d50  mov     r10d, 1
0x140017d56  cmp     rsi, rax
0x140017d59  jnb     short loc_140017D7A
0x140017d5b  movzx   edx, word ptr [rcx]
0x140017d5e  cmp     dx, 3Bh ; ';'
0x140017d62  jnz     short loc_140017D69
0x140017d64  add     r8d, r10d
0x140017d67  jmp     short loc_140017D71
0x140017d69  cmp     dx, 20h ; ' '
0x140017d6d  cmovnz  r9d, r10d
0x140017d71  add     rcx, 2
0x140017d75  cmp     rcx, rax
0x140017d78  jb      short loc_140017D5B
0x140017d7a  mov     eax, 0CCCCCCCDh
0x140017d7f  mul     r8d
0x140017d82  mov     r12d, edx
0x140017d85  shr     r12d, 2
0x140017d89  lea     ecx, [r12+r12*4]
0x140017d8d  cmp     r8d, ecx
0x140017d90  jnz     loc_14001811C
0x140017d96  test    r8d, r8d
0x140017d99  jnz     short loc_140017DA4
0x140017d9b  test    r9d, r9d
0x140017d9e  jnz     loc_14001811C
0x140017da4  mov     ebx, edi
0x140017da6  mov     r8d, 6C416553h; Tag
0x140017dac  mov     ecx, r10d; PoolType
0x140017daf  test    r12d, r12d
0x140017db2  jnz     short loc_140017DD9
0x140017db4  lea     edx, [r12+8]; NumberOfBytes
0x140017db9  call    cs:__imp_ExAllocatePoolWithTag
0x140017dc0  nop     dword ptr [rax+rax+00h]
0x140017dc5  mov     [r14], rax
0x140017dc8  test    rax, rax
0x140017dcb  jz      short loc_140017E09
0x140017dcd  mov     qword ptr [rax], 80002h
0x140017dd4  jmp     loc_140018121
0x140017dd9  mov     eax, 0FFFFh
0x140017dde  lea     ebp, [r12+r12*2]
0x140017de2  shl     ebp, 4
0x140017de5  add     ebp, 8
0x140017de8  cmp     ebp, eax
0x140017dea  cmova   ebp, eax
0x140017ded  mov     edx, ebp; NumberOfBytes
0x140017def  mov     r15d, ebp
0x140017df2  call    cs:__imp_ExAllocatePoolWithTag
0x140017df9  nop     dword ptr [rax+rax+00h]
0x140017dfe  mov     [r14], rax
0x140017e01  mov     rdi, rax
0x140017e04  test    rax, rax
0x140017e07  jnz     short loc_140017E13
0x140017e09  mov     ebx, 0C000009Ah
0x140017e0e  jmp     loc_140018121
0x140017e13  mov     r13d, 8
0x140017e19  mov     r8, r15; Size
0x140017e1c  xor     edx, edx; Val
0x140017e1e  mov     [rsp+88h+arg_10], r13d
0x140017e26  mov     rcx, rdi; void *
0x140017e29  call    memset
0x140017e2e  xor     eax, eax
0x140017e30  mov     word ptr [rdi], 2
0x140017e35  mov     [rdi+2], bp
0x140017e39  mov     [rdi+4], eax
0x140017e3c  mov     [rsp+88h+arg_8], eax
0x140017e43  test    r12d, r12d
0x140017e46  jz      loc_1400180E6
0x140017e4c  mov     ebp, 0C000000Dh
0x140017e51  mov     r15w, 20h ; ' '
0x140017e56  mov     [rsp+88h+arg_0], 0
0x140017e61  jmp     short loc_140017E67
0x140017e63  add     rsi, 2
0x140017e67  movzx   eax, word ptr [rsi]
0x140017e6a  cmp     ax, r15w
0x140017e6e  jz      short loc_140017E63
0x140017e70  cmp     ax, 28h ; '('
0x140017e74  lea     rdi, [rsi+2]
0x140017e78  cmovnz  rdi, rsi
0x140017e7c  jmp     short loc_140017E82
0x140017e7e  add     rdi, 2
0x140017e82  cmp     [rdi], r15w
0x140017e86  jz      short loc_140017E7E
0x140017e88  mov     r8d, 1; MaxCount
0x140017e8e  lea     rdx, aA; "A"
0x140017e95  mov     rcx, rdi; Str1
0x140017e98  call    _wcsnicmp_0
0x140017e9d  test    eax, eax
0x140017e9f  jnz     loc_14001810E
0x140017ea5  add     rdi, 4
0x140017ea9  jmp     short loc_140017EAF
0x140017eab  add     rdi, 2
0x140017eaf  movzx   eax, word ptr [rdi]
0x140017eb2  cmp     ax, r15w
0x140017eb6  jz      short loc_140017EAB
0x140017eb8  cmp     ax, 3Bh ; ';'
0x140017ebc  jnz     loc_14001810E
0x140017ec2  add     rdi, 2
0x140017ec6  movzx   eax, word ptr [rdi]
0x140017ec9  cmp     ax, r15w
0x140017ecd  jz      short loc_140017EC2
0x140017ecf  cmp     ax, 3Bh ; ';'
0x140017ed3  jz      loc_140017F8F
0x140017ed9  cmp     ax, r15w
0x140017edd  jnz     short loc_140017EE9
0x140017edf  add     rdi, 2
0x140017ee3  cmp     [rdi], r15w
0x140017ee7  jz      short loc_140017EDF
0x140017ee9  xor     esi, esi
0x140017eeb  lea     rax, cs:140000000h
0x140017ef2  mov     r15d, esi
0x140017ef5  shl     r15, 4
0x140017ef9  mov     rcx, rdi; Str1
0x140017efc  mov     r8d, [r15+rax+0C258h]; MaxCount
0x140017f04  mov     rdx, [r15+rax+0C250h]; Str2
0x140017f0c  call    _wcsnicmp_0
0x140017f11  test    eax, eax
0x140017f13  jz      short loc_140017F54
0x140017f15  inc     esi
0x140017f17  cmp     esi, r13d
0x140017f1a  jb      short loc_140017EEB
0x140017f1c  lea     r8, [rsp+88h+arg_0]
0x140017f24  mov     [rsp+88h+arg_18], rdi
0x140017f2c  lea     rdx, [rsp+88h+arg_18]
0x140017f34  mov     rcx, rdi
0x140017f37  call    SepSddlParseWideStringUlong
0x140017f3c  cmp     [rsp+88h+arg_18], rdi
0x140017f44  jz      loc_14001810E
0x140017f4a  mov     rdi, [rsp+88h+arg_18]
0x140017f52  jmp     short loc_140017F7D
0x140017f54  mov     eax, [rsp+88h+arg_0]
0x140017f5b  lea     rcx, cs:140000000h
0x140017f62  or      eax, [r15+rcx+0C25Ch]
0x140017f6a  mov     [rsp+88h+arg_0], eax
0x140017f71  mov     eax, [r15+rcx+0C258h]
0x140017f79  lea     rdi, [rdi+rax*2]
0x140017f7d  movzx   eax, word ptr [rdi]
0x140017f80  mov     r15w, 20h ; ' '
0x140017f85  cmp     ax, 3Bh ; ';'
0x140017f89  jnz     loc_140017ED9
0x140017f8f  add     rdi, 2
0x140017f93  test    ebx, ebx
0x140017f95  jnz     loc_140018110
0x140017f9b  lea     ecx, [rbx+2]
0x140017f9e  jmp     short loc_140017FA4
0x140017fa0  add     rdi, 2
0x140017fa4  movzx   eax, word ptr [rdi]
0x140017fa7  cmp     ax, r15w
0x140017fab  jz      short loc_140017FA0
0x140017fad  cmp     ax, 3Bh ; ';'
0x140017fb1  cmovnz  ebx, ebp
0x140017fb4  add     rdi, 2
0x140017fb8  sub     ecx, 1
0x140017fbb  jnz     short loc_140017FA4
0x140017fbd  test    ebx, ebx
0x140017fbf  jnz     loc_140018110
0x140017fc5  jmp     short loc_140017FCB
0x140017fc7  add     rdi, 2
0x140017fcb  cmp     [rdi], r15w
0x140017fcf  jz      short loc_140017FC7
0x140017fd1  xor     ebx, ebx
0x140017fd3  lea     rax, cs:140000000h
0x140017fda  mov     rcx, rdi; Str1
0x140017fdd  lea     rdx, rva aWd_0[rax]; "WD" ...
0x140017fe4  lea     r15, [rbx+rbx*2]
0x140017fe8  mov     r8d, rva dword_14000C3A4[rax+r15*8]; MaxCount
0x140017ff0  lea     rdx, [rdx+r15*8]; Str2
0x140017ff4  call    _wcsnicmp_0
0x140017ff9  test    eax, eax
0x140017ffb  jz      short loc_14001800E
0x140017ffd  inc     ebx
0x140017fff  cmp     ebx, 0Eh
0x140018002  jb      short loc_140017FD3
0x140018004  mov     ebx, 0C0000073h
0x140018009  jmp     loc_140018110
0x14001800e  lea     rbx, cs:140000000h
0x140018015  cmp     rva dword_14000C398[rbx+r15*8], 1
0x14001801e  mov     eax, rva dword_14000C3A4[rbx+r15*8]
0x140018026  lea     rsi, [rdi+rax*2]
0x14001802a  jnz     short loc_140018044
0x14001802c  mov     dl, 20h ; ' '; MinorVersion
0x14001802e  mov     cl, 1; MajorVersion
0x140018030  call    cs:__imp_IoIsWdmVersionAvailable
0x140018037  nop     dword ptr [rax+rax+00h]
0x14001803c  test    al, al
0x14001803e  jnz     short loc_140018044
0x140018040  xor     ecx, ecx
0x140018042  jmp     short loc_14001805A
0x140018044  mov     rax, cs:__imp_SeExports
0x14001804b  mov     rdx, rva qword_14000C390[rbx+r15*8]
0x140018053  mov     rcx, [rax]
0x140018056  mov     rcx, [rdx+rcx]
0x14001805a  test    rsi, rsi
0x14001805d  jz      loc_140018107
0x140018063  mov     r15w, 20h ; ' '
0x140018068  jmp     short loc_14001806E
0x14001806a  add     rsi, 2
0x14001806e  movzx   eax, word ptr [rsi]
0x140018071  cmp     ax, r15w
0x140018075  jz      short loc_14001806A
0x140018077  cmp     ax, 29h ; ')'
0x14001807b  jnz     loc_140018107
0x140018081  mov     edi, [rsp+88h+arg_8]
0x140018088  xor     ebx, ebx
0x14001808a  test    rcx, rcx
0x14001808d  jz      short loc_1400180BE
0x14001808f  mov     [rsp+88h+Sid], rcx; Sid
0x140018094  lea     rdx, [rsp+88h+arg_10]; int
0x14001809c  mov     eax, r12d
0x14001809f  mov     rcx, r14; int
0x1400180a2  sub     eax, edi
0x1400180a4  mov     [rsp+88h+var_60], eax; int
0x1400180a8  mov     eax, [rsp+88h+arg_0]
0x1400180af  mov     [rsp+88h+AccessMask], eax; AccessMask
0x1400180b3  call    SepSddlAddAceToAcl
0x1400180b8  mov     ebx, eax
0x1400180ba  test    eax, eax
0x1400180bc  jnz     short loc_140018110
0x1400180be  add     rsi, 2
0x1400180c2  cmp     word ptr [rsi], 28h ; '('
0x1400180c6  jnz     short loc_1400180CC
0x1400180c8  add     rsi, 2
0x1400180cc  inc     edi
0x1400180ce  mov     [rsp+88h+arg_8], edi
0x1400180d5  cmp     edi, r12d
0x1400180d8  jb      loc_140017E56
0x1400180de  mov     r13d, [rsp+88h+arg_10]
0x1400180e6  mov     rax, [r14]
0x1400180e9  test    ebx, ebx
0x1400180eb  jz      short loc_140018115
0x1400180ed  xor     edx, edx; Tag
0x1400180ef  mov     rcx, rax; P
0x1400180f2  call    cs:__imp_ExFreePoolWithTag
0x1400180f9  nop     dword ptr [rax+rax+00h]
0x1400180fe  mov     qword ptr [r14], 0
0x140018105  jmp     short loc_140018121
0x140018107  mov     ebx, 0C0000077h
0x14001810c  jmp     short loc_140018110
0x14001810e  mov     ebx, ebp
0x140018110  mov     rax, [r14]
0x140018113  jmp     short loc_1400180ED
0x140018115  mov     [rax+2], r13w
0x14001811a  jmp     short loc_140018121
0x14001811c  mov     ebx, 0C000000Dh
0x140018121  mov     eax, ebx
0x140018123  add     rsp, 48h
0x140018127  pop     r15
0x140018129  pop     r14
0x14001812b  pop     r13
0x14001812d  pop     r12
0x14001812f  pop     rdi
0x140018130  pop     rsi
0x140018131  pop     rbp
0x140018132  pop     rbx
0x140018133  retn
```
