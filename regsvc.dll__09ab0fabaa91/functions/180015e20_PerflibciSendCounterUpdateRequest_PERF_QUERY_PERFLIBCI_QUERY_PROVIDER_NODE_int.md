# PerflibciSendCounterUpdateRequest(_PERF_QUERY *,PERFLIBCI_QUERY_PROVIDER_NODE *,int)

- ea: `0x180015e20`
- end: `0x18001619c`
- name: `?PerflibciSendCounterUpdateRequest@@YAKPEAU_PERF_QUERY@@PEAUPERFLIBCI_QUERY_PROVIDER_NODE@@H@Z`
- size: `892`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *, struct PERFLIBCI_QUERY_PROVIDER_NODE *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180005f20`
- `0x1800163f4`

## callees

- `0x1800014c0`
- `0x180005da0`
- `0x1800070d0`
- `0x180008050`
- `0x180015e20`
- `0x1800161a4`
- `0x18001e431`

## pseudocode

```c
__int64 __fastcall PerflibciSendCounterUpdateRequest(
        struct _PERF_QUERY *a1,
        struct PERFLIBCI_QUERY_PROVIDER_NODE *a2,
        int a3)
{
  __int64 v3; // r9
  unsigned int v7; // ebx
  unsigned int *v8; // r12
  unsigned int v9; // r8d
  unsigned int i; // edx
  bool v11; // zf
  __int64 *v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // ebx
  unsigned int v15; // r15d
  unsigned __int16 *v16; // rsi
  __int64 v17; // r11
  unsigned int v18; // edx
  char *v19; // rdi
  unsigned int v20; // eax
  _DWORD *v21; // rbx
  bool v22; // zf
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // r13d
  unsigned int *v29; // rdx
  unsigned int v30; // eax
  int v31; // ecx
  _DWORD *v32; // rdi
  unsigned int v33; // esi
  unsigned int v34; // ecx
  char *v35; // r15
  int v36; // eax
  unsigned int j; // [rsp+30h] [rbp-10h]
  unsigned int *v39; // [rsp+38h] [rbp-8h]
  void *Block; // [rsp+88h] [rbp+48h] BYREF
  int v41; // [rsp+90h] [rbp+50h]
  unsigned int v42; // [rsp+98h] [rbp+58h] BYREF

  v41 = a3;
  v3 = *((_QWORD *)a2 + 2);
  Block = 0;
  v42 = 0;
  v7 = 0;
  v8 = 0;
  if ( v3 )
  {
    v9 = 0;
    for ( i = 0; i < *((_DWORD *)a2 + 7); i += *(_DWORD *)(i + v3 + 20) )
    {
      if ( *(_DWORD *)(i + v3 + 16) != 1223 )
        continue;
      if ( a3 == 1 )
      {
        v11 = *(_DWORD *)(i + v3 + 36) == -3;
      }
      else
      {
        if ( a3 )
          continue;
        v11 = *(_DWORD *)(i + v3 + 36) == -2;
      }
      if ( v11 )
      {
        v9 += *(_DWORD *)(i + v3 + 20);
        if ( v9 < *(_DWORD *)(i + v3 + 20) )
          return 534;
      }
    }
    if ( !v9 )
      return v7;
    v12 = &qword_180023510;
    if ( *((_QWORD *)a1 + 1) )
      v12 = (__int64 *)*((_QWORD *)a1 + 1);
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = (2 * v13 + 9) & 0xFFFFFFF8;
    v15 = v9 + v14 + 16;
    if ( v15 < v14 || v9 + 16 < v9 )
    {
      v7 = 534;
      goto LABEL_83;
    }
    v16 = (unsigned __int16 *)operator new(v15);
    if ( !v16 )
    {
      v7 = 14;
      goto LABEL_83;
    }
    *((_DWORD *)v16 + 2) = 16;
    *(_DWORD *)v16 = v14 + 16;
    *((_DWORD *)v16 + 3) = v14;
    StringCbCopyW(v16 + 8, v14, *((const unsigned __int16 **)a1 + 1));
    v17 = *(unsigned int *)v16;
    v18 = 0;
    v42 = 0;
    if ( *((_DWORD *)a2 + 7) )
    {
      v19 = (char *)v16 + v17;
      v20 = 0;
      do
      {
        v21 = (_DWORD *)(*((_QWORD *)a2 + 2) + v20);
        if ( v21[4] == 1223 )
        {
          if ( a3 == 1 )
          {
            v22 = v21[9] == -3;
            goto LABEL_28;
          }
          if ( !a3 )
          {
            v22 = v21[9] == -2;
LABEL_28:
            if ( v22 )
            {
              memcpy_0(v19, (const void *)(*((_QWORD *)a2 + 2) + v20), (unsigned int)v21[5]);
              v18 = v42;
              v19 += (unsigned int)v21[5];
            }
          }
        }
        v18 += v21[5];
        v20 = v18;
        v42 = v18;
      }
      while ( v18 < *((_DWORD *)a2 + 7) );
    }
    v23 = *((_QWORD *)a2 + 6);
    v42 = 0x2000;
    v7 = PerfpSendNotification(v23, 2 - (unsigned int)(a3 != 0), (_DWORD)v16, v15, (__int64)&Block, (__int64)&v42);
    operator delete(v16);
    v8 = (unsigned int *)Block;
    if ( !v7 )
    {
      if ( !*(_DWORD *)Block )
      {
        v24 = *((_DWORD *)a2 + 7);
        v25 = 0;
        if ( a3 )
        {
          if ( v24 )
          {
            do
            {
              v26 = *((_QWORD *)a2 + 2);
              if ( *(_DWORD *)(v25 + v26 + 16) == 1223 && a3 == 1 && *(_DWORD *)(v25 + v26 + 36) == -3 )
                *(_DWORD *)(v25 + v26 + 16) = 4200;
              v25 += *(_DWORD *)(v25 + v26 + 20);
            }
            while ( v25 < *((_DWORD *)a2 + 7) );
          }
        }
        else if ( v24 )
        {
          do
          {
            v27 = *((_QWORD *)a2 + 2);
            if ( *(_DWORD *)(v25 + v27 + 16) == 1223 && *(_DWORD *)(v25 + v27 + 36) == -2 )
              *(_DWORD *)(v25 + v27 + 16) = 0;
            v25 += *(_DWORD *)(v25 + v27 + 20);
          }
          while ( v25 < *((_DWORD *)a2 + 7) );
        }
      }
      v28 = 8;
      for ( j = 0; j < *v8; ++j )
      {
        if ( v28 >= v42 )
          break;
        v29 = (unsigned int *)((char *)v8 + v28);
        v39 = v29;
        v28 += *v29;
        if ( v29[3] )
        {
          v7 = v29[3];
          continue;
        }
        v30 = 0;
        LODWORD(Block) = 0;
        if ( !*((_DWORD *)a2 + 7) )
          continue;
        v31 = v41;
        do
        {
          v32 = (_DWORD *)(*((_QWORD *)a2 + 2) + v30);
          if ( v31 == 1 )
          {
            if ( v32[9] != -3 )
              goto LABEL_69;
          }
          else if ( v31 || v32[9] != -2 )
          {
            goto LABEL_69;
          }
          if ( v7 )
          {
            v32[4] = v7;
            goto LABEL_69;
          }
          v33 = 16;
          while ( 1 )
          {
            if ( v33 >= *v29 )
              goto LABEL_67;
            v34 = *v29 - v33;
            if ( v34 < 0x28 || (v35 = (char *)v29 + v33, v34 < *((_DWORD *)v35 + 5)) || *((_DWORD *)v35 + 5) < 0x28u )
            {
              v32[4] = 87;
              goto LABEL_67;
            }
            if ( (unsigned __int8)PerflibiIsEqualCounter(v35, v32, 0) )
              break;
            v33 += *((_DWORD *)v35 + 5);
            v29 = v39;
          }
          v36 = *((_DWORD *)v35 + 4);
          if ( !v36 )
          {
            v32[4] = 0;
            goto LABEL_66;
          }
          if ( !v32[4] )
          {
LABEL_66:
            v29 = v39;
LABEL_67:
            v31 = v41;
            goto LABEL_68;
          }
          if ( v36 == 5 )
          {
            v32[4] = 5;
            goto LABEL_66;
          }
          v29 = v39;
          v31 = v41;
          if ( v32[4] == 1223 )
            v32[4] = v36;
LABEL_68:
          v30 = (unsigned int)Block;
LABEL_69:
          v30 += v32[5];
          LODWORD(Block) = v30;
        }
        while ( v30 < *((_DWORD *)a2 + 7) );
      }
    }
LABEL_83:
    operator delete(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180015e20  mov     [rsp-38h+arg_0], rbx
0x180015e25  mov     [rsp-38h+arg_10], r8d
0x180015e2a  push    rbp
0x180015e2b  push    rsi
0x180015e2c  push    rdi
0x180015e2d  push    r12
0x180015e2f  push    r13
0x180015e31  push    r14
0x180015e33  push    r15
0x180015e35  mov     rbp, rsp
0x180015e38  sub     rsp, 40h
0x180015e3c  mov     r9, [rdx+10h]
0x180015e40  xor     r10d, r10d
0x180015e43  mov     [rbp+Block], r10
0x180015e47  mov     r13d, r8d
0x180015e4a  mov     [rbp+arg_18], r10d
0x180015e4e  mov     r14, rdx
0x180015e51  mov     rdi, rcx
0x180015e54  mov     ebx, r10d
0x180015e57  mov     r12d, r10d
0x180015e5a  test    r9, r9
0x180015e5d  jz      loc_180016182
0x180015e63  mov     r8d, r10d
0x180015e66  mov     edx, r10d
0x180015e69  cmp     edx, [r14+1Ch]
0x180015e6d  jnb     short loc_180015EB4
0x180015e6f  mov     ecx, edx
0x180015e71  cmp     dword ptr [rcx+r9+10h], 4C7h
0x180015e7a  jnz     short loc_180015EA3
0x180015e7c  cmp     r13d, 1
0x180015e80  jnz     short loc_180015E8A
0x180015e82  cmp     dword ptr [rcx+r9+24h], 0FFFFFFFDh
0x180015e88  jmp     short loc_180015E95
0x180015e8a  test    r13d, r13d
0x180015e8d  jnz     short loc_180015EA3
0x180015e8f  cmp     dword ptr [rcx+r9+24h], 0FFFFFFFEh
0x180015e95  jnz     short loc_180015EA3
0x180015e97  add     r8d, [rcx+r9+14h]
0x180015e9c  cmp     r8d, [rcx+r9+14h]
0x180015ea1  jb      short loc_180015EAA
0x180015ea3  add     edx, [rcx+r9+14h]
0x180015ea8  jmp     short loc_180015E69
0x180015eaa  mov     ebx, 216h
0x180015eaf  jmp     loc_180016182
0x180015eb4  test    r8d, r8d
0x180015eb7  jz      loc_180016182
0x180015ebd  cmp     [rdi+8], r10
0x180015ec1  lea     rax, qword_180023510
0x180015ec8  cmovnz  rax, [rdi+8]
0x180015ecd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015ed1  inc     rbx
0x180015ed4  cmp     [rax+rbx*2], r10w
0x180015ed9  jnz     short loc_180015ED1
0x180015edb  lea     ebx, ds:9[rbx*2]
0x180015ee2  and     ebx, 0FFFFFFF8h
0x180015ee5  lea     r15d, [rbx+10h]
0x180015ee9  add     r15d, r8d
0x180015eec  cmp     r15d, ebx
0x180015eef  jb      loc_180016175
0x180015ef5  lea     eax, [r8+10h]
0x180015ef9  cmp     eax, r8d
0x180015efc  jb      loc_180016175
0x180015f02  mov     ecx, r15d
0x180015f05  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180015f0a  mov     rsi, rax
0x180015f0d  test    rax, rax
0x180015f10  jz      loc_18001616E
0x180015f16  lea     eax, [rbx+10h]
0x180015f19  mov     dword ptr [rsi+8], 10h
0x180015f20  mov     [rsi], eax
0x180015f22  lea     rcx, [rsi+10h]; unsigned __int16 *
0x180015f26  mov     [rsi+0Ch], ebx
0x180015f29  mov     r8, [rdi+8]; unsigned __int16 *
0x180015f2d  mov     edx, ebx; unsigned __int64
0x180015f2f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180015f34  mov     r11d, [rsi]
0x180015f37  xor     edx, edx
0x180015f39  mov     [rbp+arg_18], edx
0x180015f3c  cmp     [r14+1Ch], edx
0x180015f40  jbe     short loc_180015F94
0x180015f42  lea     rdi, [rsi+r11]
0x180015f46  xor     eax, eax
0x180015f48  mov     ebx, eax
0x180015f4a  add     rbx, [r14+10h]
0x180015f4e  cmp     dword ptr [rbx+10h], 4C7h
0x180015f55  jnz     short loc_180015F86
0x180015f57  cmp     r13d, 1
0x180015f5b  jnz     short loc_180015F63
0x180015f5d  cmp     dword ptr [rbx+24h], 0FFFFFFFDh
0x180015f61  jmp     short loc_180015F6C
0x180015f63  test    r13d, r13d
0x180015f66  jnz     short loc_180015F86
0x180015f68  cmp     dword ptr [rbx+24h], 0FFFFFFFEh
0x180015f6c  jnz     short loc_180015F86
0x180015f6e  mov     r8d, [rbx+14h]; Size
0x180015f72  mov     rdx, rbx; Src
0x180015f75  mov     rcx, rdi; void *
0x180015f78  call    memcpy_0
0x180015f7d  mov     eax, [rbx+14h]
0x180015f80  mov     edx, [rbp+arg_18]
0x180015f83  add     rdi, rax
0x180015f86  add     edx, [rbx+14h]
0x180015f89  mov     eax, edx
0x180015f8b  mov     [rbp+arg_18], edx
0x180015f8e  cmp     edx, [r14+1Ch]
0x180015f92  jb      short loc_180015F48
0x180015f94  mov     rcx, [r14+30h]
0x180015f98  mov     eax, r13d
0x180015f9b  neg     eax
0x180015f9d  mov     [rbp+arg_18], 2000h
0x180015fa4  lea     rax, [rbp+arg_18]
0x180015fa8  mov     r9d, r15d
0x180015fab  mov     [rsp+40h+var_18], rax
0x180015fb0  sbb     edx, edx
0x180015fb2  lea     rax, [rbp+Block]
0x180015fb6  add     edx, 2
0x180015fb9  mov     r8, rsi
0x180015fbc  mov     [rsp+40h+var_20], rax
0x180015fc1  call    PerfpSendNotification
0x180015fc6  mov     rcx, rsi; Block
0x180015fc9  mov     ebx, eax
0x180015fcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015fd0  mov     r12, [rbp+Block]
0x180015fd4  xor     r8d, r8d
0x180015fd7  test    ebx, ebx
0x180015fd9  jnz     loc_18001617A
0x180015fdf  cmp     [r12], r8d
0x180015fe3  jnz     short loc_180016050
0x180015fe5  mov     eax, [r14+1Ch]
0x180015fe9  mov     edx, r8d
0x180015fec  test    r13d, r13d
0x180015fef  jz      short loc_180016026
0x180015ff1  test    eax, eax
0x180015ff3  jz      short loc_180016050
0x180015ff5  mov     rcx, [r14+10h]
0x180015ff9  mov     eax, edx
0x180015ffb  cmp     dword ptr [rax+rcx+10h], 4C7h
0x180016003  jnz     short loc_18001601A
0x180016005  cmp     r13d, 1
0x180016009  jnz     short loc_18001601A
0x18001600b  cmp     dword ptr [rax+rcx+24h], 0FFFFFFFDh
0x180016010  jnz     short loc_18001601A
0x180016012  mov     dword ptr [rax+rcx+10h], 1068h
0x18001601a  add     edx, [rax+rcx+14h]
0x18001601e  cmp     edx, [r14+1Ch]
0x180016022  jb      short loc_180015FF5
0x180016024  jmp     short loc_180016050
0x180016026  test    eax, eax
0x180016028  jz      short loc_180016050
0x18001602a  mov     rcx, [r14+10h]
0x18001602e  mov     eax, edx
0x180016030  cmp     dword ptr [rax+rcx+10h], 4C7h
0x180016038  jnz     short loc_180016046
0x18001603a  cmp     dword ptr [rax+rcx+24h], 0FFFFFFFEh
0x18001603f  jnz     short loc_180016046
0x180016041  mov     [rax+rcx+10h], r8d
0x180016046  add     edx, [rax+rcx+14h]
0x18001604a  cmp     edx, [r14+1Ch]
0x18001604e  jb      short loc_18001602A
0x180016050  mov     r13d, 8
0x180016056  mov     [rbp+var_10], r8d
0x18001605a  cmp     [r12], r8d
0x18001605e  jbe     loc_18001617A
0x180016064  cmp     r13d, [rbp+arg_18]
0x180016068  jnb     loc_18001617A
0x18001606e  mov     edx, r13d
0x180016071  add     rdx, r12
0x180016074  mov     [rbp+var_8], rdx
0x180016078  add     r13d, [rdx]
0x18001607b  cmp     [rdx+0Ch], r8d
0x18001607f  jnz     loc_180016157
0x180016085  mov     eax, r8d
0x180016088  mov     dword ptr [rbp+Block], eax
0x18001608b  cmp     [r14+1Ch], r8d
0x18001608f  jbe     loc_18001615A
0x180016095  mov     ecx, [rbp+arg_10]
0x180016098  mov     edi, eax
0x18001609a  add     rdi, [r14+10h]
0x18001609e  cmp     ecx, 1
0x1800160a1  jnz     short loc_1800160AB
0x1800160a3  cmp     dword ptr [rdi+24h], 0FFFFFFFDh
0x1800160a7  jz      short loc_1800160B5
0x1800160a9  jmp     short loc_180016112
0x1800160ab  test    ecx, ecx
0x1800160ad  jnz     short loc_180016112
0x1800160af  cmp     dword ptr [rdi+24h], 0FFFFFFFEh
0x1800160b3  jnz     short loc_180016112
0x1800160b5  test    ebx, ebx
0x1800160b7  jnz     loc_180016152
0x1800160bd  lea     esi, [rbx+10h]
0x1800160c0  mov     ecx, [rdx]
0x1800160c2  cmp     esi, ecx
0x1800160c4  jnb     short loc_18001610C
0x1800160c6  sub     ecx, esi
0x1800160c8  cmp     ecx, 28h ; '('
0x1800160cb  jb      short loc_180016149
0x1800160cd  mov     r15d, esi
0x1800160d0  add     r15, rdx
0x1800160d3  cmp     ecx, [r15+14h]
0x1800160d7  jb      short loc_180016149
0x1800160d9  cmp     dword ptr [r15+14h], 28h ; '('
0x1800160de  jb      short loc_180016149
0x1800160e0  mov     rdx, rdi
0x1800160e3  mov     rcx, r15
0x1800160e6  call    PerflibiIsEqualCounter
0x1800160eb  xor     r8d, r8d
0x1800160ee  test    al, al
0x1800160f0  jnz     short loc_1800160FC
0x1800160f2  add     esi, [r15+14h]
0x1800160f6  mov     rdx, [rbp+var_8]
0x1800160fa  jmp     short loc_1800160C0
0x1800160fc  mov     eax, [r15+10h]
0x180016100  test    eax, eax
0x180016102  jnz     short loc_180016124
0x180016104  mov     [rdi+10h], r8d
0x180016108  mov     rdx, [rbp+var_8]
0x18001610c  mov     ecx, [rbp+arg_10]
0x18001610f  mov     eax, dword ptr [rbp+Block]
0x180016112  add     eax, [rdi+14h]
0x180016115  mov     dword ptr [rbp+Block], eax
0x180016118  cmp     eax, [r14+1Ch]
0x18001611c  jb      loc_180016098
0x180016122  jmp     short loc_18001615A
0x180016124  cmp     [rdi+10h], r8d
0x180016128  jz      short loc_180016108
0x18001612a  cmp     eax, 5
0x18001612d  jnz     short loc_180016134
0x18001612f  mov     [rdi+10h], eax
0x180016132  jmp     short loc_180016108
0x180016134  cmp     dword ptr [rdi+10h], 4C7h
0x18001613b  mov     rdx, [rbp+var_8]
0x18001613f  mov     ecx, [rbp+arg_10]
0x180016142  jnz     short loc_18001610F
0x180016144  mov     [rdi+10h], eax
0x180016147  jmp     short loc_18001610F
0x180016149  mov     dword ptr [rdi+10h], 57h ; 'W'
0x180016150  jmp     short loc_18001610C
0x180016152  mov     [rdi+10h], ebx
0x180016155  jmp     short loc_180016112
0x180016157  mov     ebx, [rdx+0Ch]
0x18001615a  mov     eax, [rbp+var_10]
0x18001615d  inc     eax
0x18001615f  mov     [rbp+var_10], eax
0x180016162  cmp     eax, [r12]
0x180016166  jb      loc_180016064
0x18001616c  jmp     short loc_18001617A
0x18001616e  mov     ebx, 0Eh
0x180016173  jmp     short loc_18001617A
0x180016175  mov     ebx, 216h
0x18001617a  mov     rcx, r12; Block
0x18001617d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016182  mov     eax, ebx
0x180016184  mov     rbx, [rsp+40h+arg_0]
0x18001618c  add     rsp, 40h
0x180016190  pop     r15
0x180016192  pop     r14
0x180016194  pop     r13
0x180016196  pop     r12
0x180016198  pop     rdi
0x180016199  pop     rsi
0x18001619a  pop     rbp
0x18001619b  retn
```
