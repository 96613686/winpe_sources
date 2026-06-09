# CompareStorageDuids(_STORAGE_DEVICE_UNIQUE_IDENTIFIER *,_STORAGE_DEVICE_UNIQUE_IDENTIFIER *)

- ea: `0x18000536c`
- end: `0x18000569f`
- name: `?CompareStorageDuids@@YA?AW4_DUID_MATCH_STATUS@@PEAU_STORAGE_DEVICE_UNIQUE_IDENTIFIER@@0@Z`
- size: `819`
- prototype: `int __fastcall(unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800056a8`

## callees

- `0x18000536c`
- `0x18000832f`

## pseudocode

```c
int __fastcall CompareStorageDuids(unsigned int *a1, _DWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rsi
  __int64 v6; // r14
  int result; // eax
  char *v8; // rbp
  _DWORD *v9; // r14
  unsigned int v10; // eax
  char *v11; // rsi
  unsigned int v12; // r15d
  int v13; // r12d
  int v14; // r13d
  _DWORD *v15; // rbp
  _DWORD *v16; // rsi
  _DWORD *v17; // rbp
  unsigned int v18; // eax
  char *v19; // rax
  signed __int64 v20; // rcx
  int v21; // r8d
  int v22; // edx
  char *v23; // rax
  signed __int64 v24; // rcx
  int v25; // r8d
  int v26; // edx
  char *v27; // rcx
  signed __int64 v28; // rdx
  int v29; // r9d
  int v30; // r8d
  _DWORD *v31; // rcx
  _DWORD *v32; // rdx
  int v33; // [rsp+60h] [rbp+8h]
  unsigned int v34; // [rsp+70h] [rbp+18h]

  if ( !a1 || !a2 )
    return 101;
  if ( a1[1] < 0x14 )
    return 100;
  v4 = a2[1];
  if ( v4 < 0x14 )
    return 100;
  if ( *a1 != 1 || *a2 != 1 )
    return 102;
  v5 = a1[2];
  if ( !*((_QWORD *)a1 + 1) && !a1[4] )
    return 103;
  v6 = (unsigned int)a2[2];
  if ( !*((_QWORD *)a2 + 1) && !a2[4] )
    return 103;
  if ( a1[1] != v4 || (result = memcmp_0(a1, a2, a1[1])) != 0 )
  {
    if ( (_DWORD)v5 && (_DWORD)v6 )
    {
      v8 = (char *)a1 + v5;
      if ( *(unsigned int *)((char *)a1 + v5 + 4) < 0x10 )
        return 104;
      v9 = (_DWORD *)((char *)a2 + v6);
      v10 = v9[1];
      if ( v10 < 0x10 )
        return 104;
      if ( *((_DWORD *)v8 + 1) == v10 && !memcmp_0((char *)a1 + v5, v9, *((unsigned int *)v8 + 1)) )
        return 1;
      v11 = v8 + 12;
      v34 = *((_DWORD *)v8 + 2);
      v12 = 0;
      if ( v34 )
      {
        while ( 1 )
        {
          v13 = *((_DWORD *)v11 + 1);
          if ( (v13 == 8 || (unsigned int)(v13 - 1) <= 2) && *((_DWORD *)v11 + 3) == 1 )
          {
            v14 = *(_DWORD *)v11;
            if ( *(_DWORD *)v11 == 3 || (unsigned int)(v14 - 1) <= 1 )
            {
              if ( v9[2] )
                break;
            }
          }
LABEL_34:
          ++v12;
          v11 += *((unsigned __int16 *)v11 + 5);
          if ( v12 >= v34 )
            goto LABEL_35;
        }
        v33 = 0;
        v15 = v9 + 3;
        while ( v13 != v15[1]
             || v15[3] != 1
             || v14 != *v15
             || *((_WORD *)v11 + 4) != *((_WORD *)v15 + 4)
             || memcmp_0(v11 + 16, v15 + 4, *((unsigned __int16 *)v11 + 4)) )
        {
          v15 = (_DWORD *)((char *)v15 + *((unsigned __int16 *)v15 + 5));
          if ( (unsigned int)++v33 >= v9[2] )
            goto LABEL_34;
        }
        return 1;
      }
    }
LABEL_35:
    if ( a1[3] && a2[3] )
    {
      v16 = (unsigned int *)((char *)a1 + a1[3]);
      if ( v16[1] < 0x28u )
        return 105;
      v17 = (_DWORD *)((char *)a2 + (unsigned int)a2[3]);
      v18 = v17[1];
      if ( v18 < 0x28 )
        return 105;
      if ( v16[1] == v18 && !memcmp_0((char *)a1 + a1[3], (char *)a2 + (unsigned int)a2[3], (unsigned int)v16[1]) )
        return 1;
      if ( v16[6] && v17[6] )
      {
        v19 = (char *)v16 + (unsigned int)v16[6];
        v20 = (char *)v17 + (unsigned int)v17[6] - v19;
        do
        {
          v21 = (unsigned __int8)v19[v20];
          v22 = (unsigned __int8)*v19 - v21;
          if ( v22 )
            break;
          ++v19;
        }
        while ( v21 );
        if ( !v22 )
        {
          if ( v16[3] && v17[3] )
          {
            v23 = (char *)v16 + (unsigned int)v16[3];
            v24 = (char *)v17 + (unsigned int)v17[3] - v23;
            do
            {
              v25 = (unsigned __int8)v23[v24];
              v26 = (unsigned __int8)*v23 - v25;
              if ( v26 )
                break;
              ++v23;
            }
            while ( v25 );
            if ( v26 )
              return 2;
          }
          if ( v16[4] && v17[4] )
          {
            v27 = (char *)v16 + (unsigned int)v16[4];
            v28 = (char *)v17 + (unsigned int)v17[4] - v27;
            do
            {
              v29 = (unsigned __int8)v27[v28];
              v30 = (unsigned __int8)*v27 - v29;
              if ( v30 )
                break;
              ++v27;
            }
            while ( v29 );
            if ( v30 )
              return 2;
          }
          return 1;
        }
      }
    }
    if ( !a1[4] || !a2[4] )
      return 2;
    v31 = (unsigned int *)((char *)a1 + a1[4]);
    v32 = (_DWORD *)((char *)a2 + (unsigned int)a2[4]);
    if ( *v31 == 1 || *v32 == 1 )
    {
      if ( v31[1] < 0x1Cu || v32[1] < 0x1Cu )
        return 106;
      else
        return (memcmp_0(v31, v32, 0x1Cu) != 0) + 1;
    }
    else
    {
      return 107;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000536c  mov     [rsp+arg_8], rbx
0x180005371  push    rbp
0x180005372  push    rsi
0x180005373  push    rdi
0x180005374  push    r12
0x180005376  push    r13
0x180005378  push    r14
0x18000537a  push    r15
0x18000537c  sub     rsp, 20h
0x180005380  xor     r13d, r13d
0x180005383  mov     rdi, rdx
0x180005386  mov     rbx, rcx
0x180005389  test    rcx, rcx
0x18000538c  jz      loc_180005685
0x180005392  test    rdx, rdx
0x180005395  jz      loc_180005685
0x18000539b  cmp     dword ptr [rcx+4], 14h
0x18000539f  jb      loc_18000567E
0x1800053a5  mov     eax, [rdx+4]
0x1800053a8  cmp     eax, 14h
0x1800053ab  jb      loc_18000567E
0x1800053b1  cmp     dword ptr [rcx], 1
0x1800053b4  jnz     loc_180005677
0x1800053ba  cmp     dword ptr [rdx], 1
0x1800053bd  jnz     loc_180005677
0x1800053c3  mov     esi, [rcx+8]
0x1800053c6  test    esi, esi
0x1800053c8  jnz     short loc_1800053D6
0x1800053ca  cmp     [rcx+0Ch], r13d
0x1800053ce  jnz     short loc_1800053D6
0x1800053d0  cmp     [rcx+10h], r13d
0x1800053d4  jz      short loc_1800053EB
0x1800053d6  mov     r14d, [rdx+8]
0x1800053da  test    r14d, r14d
0x1800053dd  jnz     short loc_1800053F5
0x1800053df  cmp     [rdx+0Ch], r13d
0x1800053e3  jnz     short loc_1800053F5
0x1800053e5  cmp     [rdx+10h], r13d
0x1800053e9  jnz     short loc_1800053F5
0x1800053eb  mov     eax, 67h ; 'g'
0x1800053f0  jmp     loc_18000568A
0x1800053f5  cmp     [rcx+4], eax
0x1800053f8  jnz     short loc_18000540B
0x1800053fa  mov     r8d, [rcx+4]; Size
0x1800053fe  call    memcmp_0
0x180005403  test    eax, eax
0x180005405  jz      loc_18000568A
0x18000540b  test    esi, esi
0x18000540d  jz      loc_18000550E
0x180005413  test    r14d, r14d
0x180005416  jz      loc_18000550E
0x18000541c  lea     rbp, [rbx+rsi]
0x180005420  cmp     dword ptr [rbp+4], 10h
0x180005424  jb      loc_180005611
0x18000542a  add     r14, rdi
0x18000542d  mov     eax, [r14+4]
0x180005431  cmp     eax, 10h
0x180005434  jb      loc_180005611
0x18000543a  cmp     [rbp+4], eax
0x18000543d  jnz     short loc_180005456
0x18000543f  mov     r8d, [rbp+4]; Size
0x180005443  mov     rdx, r14; Buf2
0x180005446  mov     rcx, rbp; Buf1
0x180005449  call    memcmp_0
0x18000544e  test    eax, eax
0x180005450  jz      loc_180005618
0x180005456  mov     eax, [rbp+8]
0x180005459  lea     rsi, [rbp+0Ch]
0x18000545d  mov     [rsp+58h+arg_10], eax
0x180005461  mov     r15d, r13d
0x180005464  test    eax, eax
0x180005466  jz      loc_18000550E
0x18000546c  mov     r12d, [rsi+4]
0x180005470  cmp     r12d, 8
0x180005474  jz      short loc_180005480
0x180005476  lea     eax, [r12-1]
0x18000547b  cmp     eax, 2
0x18000547e  ja      short loc_1800054F6
0x180005480  cmp     dword ptr [rsi+0Ch], 1
0x180005484  jnz     short loc_1800054F6
0x180005486  mov     r13d, [rsi]
0x180005489  cmp     r13d, 3
0x18000548d  jz      short loc_180005498
0x18000548f  lea     eax, [r13-1]
0x180005493  cmp     eax, 1
0x180005496  ja      short loc_1800054F6
0x180005498  cmp     dword ptr [r14+8], 0
0x18000549d  jbe     short loc_1800054F6
0x18000549f  mov     [rsp+58h+arg_0], 0
0x1800054a7  lea     rbp, [r14+0Ch]
0x1800054ab  cmp     r12d, [rbp+4]
0x1800054af  jnz     short loc_1800054DF
0x1800054b1  cmp     dword ptr [rbp+0Ch], 1
0x1800054b5  jnz     short loc_1800054DF
0x1800054b7  cmp     r13d, [rbp+0]
0x1800054bb  jnz     short loc_1800054DF
0x1800054bd  movzx   eax, word ptr [rsi+8]
0x1800054c1  cmp     ax, [rbp+8]
0x1800054c5  jnz     short loc_1800054DF
0x1800054c7  mov     r8d, eax; Size
0x1800054ca  lea     rdx, [rbp+10h]; Buf2
0x1800054ce  lea     rcx, [rsi+10h]; Buf1
0x1800054d2  call    memcmp_0
0x1800054d7  test    eax, eax
0x1800054d9  jz      loc_180005618
0x1800054df  movzx   eax, word ptr [rbp+0Ah]
0x1800054e3  add     rbp, rax
0x1800054e6  mov     eax, [rsp+58h+arg_0]
0x1800054ea  inc     eax
0x1800054ec  mov     [rsp+58h+arg_0], eax
0x1800054f0  cmp     eax, [r14+8]
0x1800054f4  jb      short loc_1800054AB
0x1800054f6  movzx   eax, word ptr [rsi+0Ah]
0x1800054fa  inc     r15d
0x1800054fd  add     rsi, rax
0x180005500  cmp     r15d, [rsp+58h+arg_10]
0x180005505  jb      loc_18000546C
0x18000550b  xor     r13d, r13d
0x18000550e  cmp     [rbx+0Ch], r13d
0x180005512  jz      loc_180005626
0x180005518  cmp     [rdi+0Ch], r13d
0x18000551c  jz      loc_180005626
0x180005522  mov     esi, [rbx+0Ch]
0x180005525  add     rsi, rbx
0x180005528  cmp     dword ptr [rsi+4], 28h ; '('
0x18000552c  jb      loc_18000561F
0x180005532  mov     ebp, [rdi+0Ch]
0x180005535  add     rbp, rdi
0x180005538  mov     eax, [rbp+4]
0x18000553b  cmp     eax, 28h ; '('
0x18000553e  jb      loc_18000561F
0x180005544  cmp     [rsi+4], eax
0x180005547  jnz     short loc_180005560
0x180005549  mov     r8d, [rsi+4]; Size
0x18000554d  mov     rdx, rbp; Buf2
0x180005550  mov     rcx, rsi; Buf1
0x180005553  call    memcmp_0
0x180005558  test    eax, eax
0x18000555a  jz      loc_180005618
0x180005560  cmp     [rsi+18h], r13d
0x180005564  jz      loc_180005626
0x18000556a  cmp     [rbp+18h], r13d
0x18000556e  jz      loc_180005626
0x180005574  mov     ecx, [rbp+18h]
0x180005577  mov     eax, [rsi+18h]
0x18000557a  add     rcx, rbp
0x18000557d  add     rax, rsi
0x180005580  sub     rcx, rax
0x180005583  movzx   edx, byte ptr [rax]
0x180005586  movzx   r8d, byte ptr [rax+rcx]
0x18000558b  sub     edx, r8d
0x18000558e  jnz     short loc_180005598
0x180005590  inc     rax
0x180005593  test    r8d, r8d
0x180005596  jnz     short loc_180005583
0x180005598  test    edx, edx
0x18000559a  jnz     loc_180005626
0x1800055a0  cmp     [rsi+0Ch], r13d
0x1800055a4  jz      short loc_1800055D4
0x1800055a6  cmp     [rbp+0Ch], r13d
0x1800055aa  jz      short loc_1800055D4
0x1800055ac  mov     ecx, [rbp+0Ch]
0x1800055af  mov     eax, [rsi+0Ch]
0x1800055b2  add     rcx, rbp
0x1800055b5  add     rax, rsi
0x1800055b8  sub     rcx, rax
0x1800055bb  movzx   edx, byte ptr [rax]
0x1800055be  movzx   r8d, byte ptr [rax+rcx]
0x1800055c3  sub     edx, r8d
0x1800055c6  jnz     short loc_1800055D0
0x1800055c8  inc     rax
0x1800055cb  test    r8d, r8d
0x1800055ce  jnz     short loc_1800055BB
0x1800055d0  test    edx, edx
0x1800055d2  jnz     short loc_18000560A
0x1800055d4  cmp     [rsi+10h], r13d
0x1800055d8  jz      short loc_180005618
0x1800055da  cmp     [rbp+10h], r13d
0x1800055de  jz      short loc_180005618
0x1800055e0  mov     edx, [rbp+10h]
0x1800055e3  mov     ecx, [rsi+10h]
0x1800055e6  add     rdx, rbp
0x1800055e9  add     rcx, rsi
0x1800055ec  sub     rdx, rcx
0x1800055ef  movzx   r8d, byte ptr [rcx]
0x1800055f3  movzx   r9d, byte ptr [rcx+rdx]
0x1800055f8  sub     r8d, r9d
0x1800055fb  jnz     short loc_180005605
0x1800055fd  inc     rcx
0x180005600  test    r9d, r9d
0x180005603  jnz     short loc_1800055EF
0x180005605  test    r8d, r8d
0x180005608  jz      short loc_180005618
0x18000560a  mov     eax, 2
0x18000560f  jmp     short loc_18000568A
0x180005611  mov     eax, 68h ; 'h'
0x180005616  jmp     short loc_18000568A
0x180005618  mov     eax, 1
0x18000561d  jmp     short loc_18000568A
0x18000561f  mov     eax, 69h ; 'i'
0x180005624  jmp     short loc_18000568A
0x180005626  cmp     [rbx+10h], r13d
0x18000562a  jz      short loc_18000560A
0x18000562c  cmp     [rdi+10h], r13d
0x180005630  jz      short loc_18000560A
0x180005632  mov     ecx, [rbx+10h]
0x180005635  mov     edx, [rdi+10h]
0x180005638  add     rcx, rbx; Buf1
0x18000563b  add     rdx, rdi; Buf2
0x18000563e  cmp     dword ptr [rcx], 1
0x180005641  jz      short loc_18000564F
0x180005643  cmp     dword ptr [rdx], 1
0x180005646  jz      short loc_18000564F
0x180005648  mov     eax, 6Bh ; 'k'
0x18000564d  jmp     short loc_18000568A
0x18000564f  mov     r8d, 1Ch; Size
0x180005655  cmp     [rcx+4], r8d
0x180005659  jb      short loc_180005670
0x18000565b  cmp     [rdx+4], r8d
0x18000565f  jb      short loc_180005670
0x180005661  call    memcmp_0
0x180005666  neg     eax
0x180005668  sbb     eax, eax
0x18000566a  neg     eax
0x18000566c  inc     eax
0x18000566e  jmp     short loc_18000568A
0x180005670  mov     eax, 6Ah ; 'j'
0x180005675  jmp     short loc_18000568A
0x180005677  mov     eax, 66h ; 'f'
0x18000567c  jmp     short loc_18000568A
0x18000567e  mov     eax, 64h ; 'd'
0x180005683  jmp     short loc_18000568A
0x180005685  mov     eax, 65h ; 'e'
0x18000568a  mov     rbx, [rsp+58h+arg_8]
0x18000568f  add     rsp, 20h
0x180005693  pop     r15
0x180005695  pop     r14
0x180005697  pop     r13
0x180005699  pop     r12
0x18000569b  pop     rdi
0x18000569c  pop     rsi
0x18000569d  pop     rbp
0x18000569e  retn
```
