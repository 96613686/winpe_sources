# node_remove

- ea: `0x14001bb24`
- end: `0x14001bdd8`
- name: `node_remove`
- size: `692`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bb24`
- `0x14001bde0`

## callees

- `0x14000218c`
- `0x14001b260`
- `0x14001bb24`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001bc8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bc8a`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall node_remove(_DWORD *a1, char *a2, char **a3)
{
  char *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r15
  char v9; // r12
  __int64 v10; // r13
  char *v11; // rbx
  __int64 v12; // r8
  int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // r10
  __int64 v16; // r11
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r9
  int v20; // ebx
  __int64 i; // r10
  __int64 v22; // r8
  __int64 v23; // rcx
  _QWORD *v24; // r14
  int v25; // ebx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  PDEVICE_OBJECT *result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
  }
  v6 = *a3;
  v7 = *(int *)*a3;
  if ( (int)v7 < -1 || (int)v7 >= *a1 )
  {
    if ( v6 == a2 )
    {
      *a3 = (char *)*((_QWORD *)a2 + 2);
    }
    else
    {
      v24 = v6 + 16;
      v25 = 0;
      if ( *((_QWORD *)v6 + 2) )
        node_remove(a1, a2, v6 + 16);
      v26 = a1[1];
      if ( *v24 )
      {
        if ( v26 > 0 )
        {
          do
          {
            v28 = v25++;
            v6[2 * v26 + 24 + v28] = *(_BYTE *)(2 * v26 + v28 + *v24 + 24);
            v26 = a1[1];
          }
          while ( v25 < v26 );
        }
      }
      else if ( v26 > 0 )
      {
        do
        {
          v27 = v25++;
          v6[2 * v26 + 24 + v27] = v6[v27 + 24 + v26];
          v26 = a1[1];
        }
        while ( v25 < v26 );
      }
    }
  }
  else
  {
    v8 = v7 >> 3;
    v9 = 7 - (v7 & 7);
    if ( ((a2[(v7 >> 3) + 24 + (int)a1[1]] >> v9) & 1) != 0 )
    {
      v10 = (a2[v8 + 24] >> (7 - (v7 & 7))) & 1;
      v11 = &v6[8 * v10];
      node_remove(a1, a2, v11 + 8);
      v12 = *((_QWORD *)v11 + 1);
      v13 = 0;
      if ( v12 && (v14 = (int)a1[1], ((*(char *)(v12 + v14 + v8 + 24) >> v9) & 1) != 0) )
      {
        v15 = *((_QWORD *)v6 + 1);
        v16 = *((_QWORD *)v6 + 2);
        if ( (int)v14 > 0 )
        {
          do
          {
            v17 = v13++;
            v6[v17 + 24] = *(_BYTE *)(v17 + v16 + 24) | *(_BYTE *)(v17 + v15 + 24);
            v6[v17 + 24 + (int)a1[1]] = *(_BYTE *)(v16 + v17 + (int)a1[1] + 24)
                                      | *(_BYTE *)(v15 + v17 + (int)a1[1] + 24);
            v18 = v17 + 2 * a1[1];
            v6[v18 + 24] = *(_BYTE *)(v16 + v18 + 24) & *(_BYTE *)(v15 + v18 + 24);
          }
          while ( v13 < a1[1] );
        }
      }
      else
      {
        *a3 = *(char **)&v6[8 * (2 - v10)];
        if ( v12 )
          eliminate(a1, v12);
        ExFreePoolWithTag(v6, 0);
      }
    }
    else
    {
      node_remove(a1, a2, v6 + 8);
      node_remove(a1, a2, v6 + 16);
      v19 = *((_QWORD *)v6 + 1);
      v20 = 0;
      for ( i = *((_QWORD *)v6 + 2); v20 < a1[1]; v6[v23 + 24] = *(_BYTE *)(i + v23 + 24) & *(_BYTE *)(v19 + v23 + 24) )
      {
        v22 = v20++;
        v6[v22 + 24] = *(_BYTE *)(v22 + i + 24) | *(_BYTE *)(v22 + v19 + 24);
        v6[v22 + 24 + (int)a1[1]] = *(_BYTE *)(v19 + v22 + (int)a1[1] + 24) | *(_BYTE *)(i + v22 + (int)a1[1] + 24);
        v23 = v22 + 2 * a1[1];
      }
    }
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return (PDEVICE_OBJECT *)WPP_SF_(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 40,
                                 WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14001bb24  push    rbx
0x14001bb26  push    rbp
0x14001bb27  push    rsi
0x14001bb28  push    rdi
0x14001bb29  push    r12
0x14001bb2b  push    r13
0x14001bb2d  push    r14
0x14001bb2f  push    r15
0x14001bb31  sub     rsp, 28h
0x14001bb35  mov     r14, r8
0x14001bb38  mov     rbp, rdx
0x14001bb3b  mov     rsi, rcx
0x14001bb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb45  lea     rax, WPP_GLOBAL_Control
0x14001bb4c  cmp     rcx, rax
0x14001bb4f  jz      short loc_14001BB73
0x14001bb51  mov     eax, [rcx+2Ch]
0x14001bb54  test    al, 1
0x14001bb56  jz      short loc_14001BB73
0x14001bb58  cmp     byte ptr [rcx+29h], 6
0x14001bb5c  jb      short loc_14001BB73
0x14001bb5e  mov     rcx, [rcx+18h]
0x14001bb62  lea     r8, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids
0x14001bb69  mov     edx, 27h ; '''
0x14001bb6e  call    WPP_SF_
0x14001bb73  mov     rdi, [r14]
0x14001bb76  movsxd  rax, dword ptr [rdi]
0x14001bb79  cmp     eax, 0FFFFFFFFh
0x14001bb7c  jl      loc_14001BD12
0x14001bb82  cmp     eax, [rsi]
0x14001bb84  jge     loc_14001BD12
0x14001bb8a  mov     r15, rax
0x14001bb8d  mov     r8b, al
0x14001bb90  movsxd  rax, dword ptr [rsi+4]
0x14001bb94  mov     r9d, 7
0x14001bb9a  sar     r15, 3
0x14001bb9e  and     r8b, r9b
0x14001bba1  add     rax, r15
0x14001bba4  mov     r12d, r9d
0x14001bba7  sub     r12b, r8b
0x14001bbaa  mov     cl, r12b
0x14001bbad  mov     dl, [rax+rbp+18h]
0x14001bbb1  sar     dl, cl
0x14001bbb3  test    dl, 1
0x14001bbb6  mov     rdx, rbp
0x14001bbb9  jz      loc_14001BC9B
0x14001bbbf  movzx   eax, r8b
0x14001bbc3  sub     r9d, eax
0x14001bbc6  movsx   eax, byte ptr [r15+rbp+18h]
0x14001bbcc  mov     cl, r9b
0x14001bbcf  sar     eax, cl
0x14001bbd1  mov     rcx, rsi
0x14001bbd4  and     eax, 1
0x14001bbd7  mov     r13d, eax
0x14001bbda  lea     rbx, [rdi+rax*8]
0x14001bbde  lea     r8, [rbx+8]
0x14001bbe2  call    node_remove
0x14001bbe7  mov     r8, [rbx+8]
0x14001bbeb  xor     ebx, ebx
0x14001bbed  test    r8, r8
0x14001bbf0  jz      short loc_14001BC66
0x14001bbf2  movsxd  r9, dword ptr [rsi+4]
0x14001bbf6  mov     cl, r12b
0x14001bbf9  lea     rax, [r8+r9]
0x14001bbfd  mov     dl, [rax+r15+18h]
0x14001bc02  sar     dl, cl
0x14001bc04  test    dl, 1
0x14001bc07  jz      short loc_14001BC66
0x14001bc09  mov     r10, [rdi+8]
0x14001bc0d  mov     r11, [rdi+10h]
0x14001bc11  test    r9d, r9d
0x14001bc14  jle     loc_14001BD91
0x14001bc1a  movsxd  r8, ebx
0x14001bc1d  inc     ebx
0x14001bc1f  mov     cl, [r8+r10+18h]
0x14001bc24  or      cl, [r8+r11+18h]
0x14001bc29  mov     [r8+rdi+18h], cl
0x14001bc2e  movsxd  rdx, dword ptr [rsi+4]
0x14001bc32  add     rdx, r8
0x14001bc35  mov     cl, [r10+rdx+18h]
0x14001bc3a  or      cl, [r11+rdx+18h]
0x14001bc3f  mov     [rdi+rdx+18h], cl
0x14001bc43  mov     eax, [rsi+4]
0x14001bc46  add     eax, eax
0x14001bc48  movsxd  rcx, eax
0x14001bc4b  add     rcx, r8
0x14001bc4e  mov     al, [r10+rcx+18h]
0x14001bc53  and     al, [r11+rcx+18h]
0x14001bc58  mov     [rdi+rcx+18h], al
0x14001bc5c  cmp     ebx, [rsi+4]
0x14001bc5f  jl      short loc_14001BC1A
0x14001bc61  jmp     loc_14001BD91
0x14001bc66  mov     eax, 2
0x14001bc6b  sub     rax, r13
0x14001bc6e  mov     rax, [rdi+rax*8]
0x14001bc72  mov     [r14], rax
0x14001bc75  test    r8, r8
0x14001bc78  jz      short loc_14001BC85
0x14001bc7a  mov     rdx, r8
0x14001bc7d  mov     rcx, rsi
0x14001bc80  call    eliminate
0x14001bc85  xor     edx, edx; Tag
0x14001bc87  mov     rcx, rdi; P
0x14001bc8a  call    cs:__imp_ExFreePoolWithTag
0x14001bc91  nop     dword ptr [rax+rax+00h]
0x14001bc96  jmp     loc_14001BD91
0x14001bc9b  lea     r8, [rdi+8]
0x14001bc9f  mov     rcx, rsi
0x14001bca2  call    node_remove
0x14001bca7  lea     r8, [rdi+10h]
0x14001bcab  mov     rdx, rbp
0x14001bcae  mov     rcx, rsi
0x14001bcb1  call    node_remove
0x14001bcb6  mov     r9, [rdi+8]
0x14001bcba  xor     ebx, ebx
0x14001bcbc  mov     r10, [rdi+10h]
0x14001bcc0  cmp     [rsi+4], ebx
0x14001bcc3  jle     loc_14001BD91
0x14001bcc9  movsxd  r8, ebx
0x14001bccc  inc     ebx
0x14001bcce  mov     cl, [r8+r9+18h]
0x14001bcd3  or      cl, [r8+r10+18h]
0x14001bcd8  mov     [r8+rdi+18h], cl
0x14001bcdd  movsxd  rdx, dword ptr [rsi+4]
0x14001bce1  add     rdx, r8
0x14001bce4  mov     cl, [r10+rdx+18h]
0x14001bce9  or      cl, [r9+rdx+18h]
0x14001bcee  mov     [rdi+rdx+18h], cl
0x14001bcf2  mov     eax, [rsi+4]
0x14001bcf5  add     eax, eax
0x14001bcf7  movsxd  rcx, eax
0x14001bcfa  add     rcx, r8
0x14001bcfd  mov     al, [r9+rcx+18h]
0x14001bd02  and     al, [r10+rcx+18h]
0x14001bd07  mov     [rdi+rcx+18h], al
0x14001bd0b  cmp     ebx, [rsi+4]
0x14001bd0e  jl      short loc_14001BCC9
0x14001bd10  jmp     short loc_14001BD91
0x14001bd12  cmp     rdi, rbp
0x14001bd15  jnz     short loc_14001BD20
0x14001bd17  mov     rax, [rbp+10h]
0x14001bd1b  mov     [r14], rax
0x14001bd1e  jmp     short loc_14001BD91
0x14001bd20  lea     r14, [rdi+10h]
0x14001bd24  xor     ebx, ebx
0x14001bd26  cmp     [r14], rbx
0x14001bd29  jz      short loc_14001BD39
0x14001bd2b  mov     r8, r14
0x14001bd2e  mov     rdx, rbp
0x14001bd31  mov     rcx, rsi
0x14001bd34  call    node_remove
0x14001bd39  mov     eax, [rsi+4]
0x14001bd3c  cmp     [r14], rbx
0x14001bd3f  jnz     short loc_14001BD6A
0x14001bd41  test    eax, eax
0x14001bd43  jle     short loc_14001BD91
0x14001bd45  movsxd  r8, eax
0x14001bd48  add     eax, eax
0x14001bd4a  movsxd  rdx, ebx
0x14001bd4d  inc     ebx
0x14001bd4f  movsxd  rcx, eax
0x14001bd52  add     r8, rdx
0x14001bd55  add     rcx, rdx
0x14001bd58  mov     al, [r8+rdi+18h]
0x14001bd5d  mov     [rcx+rdi+18h], al
0x14001bd61  mov     eax, [rsi+4]
0x14001bd64  cmp     ebx, eax
0x14001bd66  jl      short loc_14001BD45
0x14001bd68  jmp     short loc_14001BD91
0x14001bd6a  test    eax, eax
0x14001bd6c  jle     short loc_14001BD91
0x14001bd6e  add     eax, eax
0x14001bd70  movsxd  rcx, ebx
0x14001bd73  movsxd  r8, eax
0x14001bd76  inc     ebx
0x14001bd78  mov     rax, [r14]
0x14001bd7b  lea     rdx, [r8+rcx]
0x14001bd7f  add     rcx, r8
0x14001bd82  mov     al, [rdx+rax+18h]
0x14001bd86  mov     [rcx+rdi+18h], al
0x14001bd8a  mov     eax, [rsi+4]
0x14001bd8d  cmp     ebx, eax
0x14001bd8f  jl      short loc_14001BD6E
0x14001bd91  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd98  lea     rax, WPP_GLOBAL_Control
0x14001bd9f  cmp     rcx, rax
0x14001bda2  jz      short loc_14001BDC6
0x14001bda4  mov     eax, [rcx+2Ch]
0x14001bda7  test    al, 1
0x14001bda9  jz      short loc_14001BDC6
0x14001bdab  cmp     byte ptr [rcx+29h], 6
0x14001bdaf  jb      short loc_14001BDC6
0x14001bdb1  mov     rcx, [rcx+18h]
0x14001bdb5  lea     r8, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids
0x14001bdbc  mov     edx, 28h ; '('
0x14001bdc1  call    WPP_SF_
0x14001bdc6  add     rsp, 28h
0x14001bdca  pop     r15
0x14001bdcc  pop     r14
0x14001bdce  pop     r13
0x14001bdd0  pop     r12
0x14001bdd2  pop     rdi
0x14001bdd3  pop     rsi
0x14001bdd4  pop     rbp
0x14001bdd5  pop     rbx
0x14001bdd6  retn
```
