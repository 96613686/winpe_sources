# DiscpSelectISIDForTarget

- ea: `0x18000b444`
- end: `0x18000b71a`
- name: `DiscpSelectISIDForTarget`
- size: `726`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180009f14`

## callees

- `0x180009cb8`
- `0x18000b444`
- `0x180019038`
- `0x1800192e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b5b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b61e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b5b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b61e`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b494`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b50f`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b525`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b494`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b50f`
- `ISCSIUM!DiscpAllocMemory` at `0x18000b525`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b4bc`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b55b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b564`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6c7`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6de`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6ec`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6fa`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b4bc`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b55b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b564`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6c7`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6de`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6ec`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b6fa`

## pseudocode

```c
__int64 __fastcall DiscpSelectISIDForTarget(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 v3; // rsi
  unsigned int IScsiSessionList; // ebx
  __int64 v6; // rax
  char *v7; // r15
  __int64 v8; // r14
  __int64 v9; // rax
  unsigned int v10; // r12d
  unsigned __int64 v11; // rdi
  __int64 v12; // rdi
  __int128 *v13; // r8
  __int16 v14; // ax
  __int16 v15; // cx
  int v16; // r9d
  __int16 v17; // dx
  __int128 *v18; // rdi
  __int128 *v19; // rcx
  unsigned int v21; // [rsp+28h] [rbp-28h]
  unsigned int v22; // [rsp+28h] [rbp-28h]
  unsigned int v23; // [rsp+30h] [rbp-20h] BYREF
  __int128 v24; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v25; // [rsp+98h] [rbp+48h] BYREF
  int v26; // [rsp+9Ch] [rbp+4Ch]
  _WORD *v27; // [rsp+A0h] [rbp+50h]
  unsigned int v28; // [rsp+A8h] [rbp+58h] BYREF

  v27 = a3;
  v26 = HIDWORD(a2);
  v3 = 0;
  v23 = 0;
  v28 = 0;
  v25 = 0;
  v24 = 0;
  IScsiSessionList = DiscpGetIScsiSessionList(&v25, &v23, 0);
  if ( IScsiSessionList != 122 )
  {
LABEL_6:
    v7 = 0;
    v8 = 0;
    if ( !IScsiSessionList )
    {
      if ( !a1 )
        goto LABEL_15;
      LOBYTE(v21) = 0;
      v25 = 0;
      IScsiSessionList = DiscpReportPeristentLogins(&v28, 0, &v25, 0, 0, v21);
      if ( IScsiSessionList == 122 )
      {
        while ( 1 )
        {
          v8 = 0;
          v7 = (char *)DiscpAllocMemory(v25);
          if ( !v7 )
            break;
          v9 = DiscpAllocMemory(2 * v28);
          v8 = v9;
          if ( !v9 )
            break;
          LOBYTE(v22) = 0;
          IScsiSessionList = DiscpReportPeristentLogins(&v28, v7, &v25, v28, v9, v22);
          if ( IScsiSessionList != 122 )
            goto LABEL_14;
          DiscpFreeMemory(v7);
          DiscpFreeMemory(v8);
        }
        IScsiSessionList = 8;
        goto LABEL_41;
      }
LABEL_14:
      if ( !IScsiSessionList )
      {
LABEL_15:
        v10 = 0;
        *((_QWORD *)&v24 + 1) = &v24;
        for ( *(_QWORD *)&v24 = &v24; v10 < v23; ++v10 )
        {
          v11 = (unsigned __int64)v10 << 6;
          if ( a1 )
          {
            if ( !(unsigned int)_o__wcsicmp(a1, *(_QWORD *)(v11 + v3 + 32)) )
            {
LABEL_20:
              IScsiSessionList = DiscpInsertToSparseBitmap(
                                   &v24,
                                   (unsigned __int16)(*(unsigned __int8 *)(v11 + v3 + 45)
                                                    + (*(unsigned __int8 *)(v11 + v3 + 44) << 8)));
              if ( IScsiSessionList )
                goto LABEL_38;
            }
          }
          else if ( !*(_QWORD *)(v11 + v3 + 32) )
          {
            goto LABEL_20;
          }
        }
        if ( a1 && (v12 = 0, v28) )
        {
          while ( 1 )
          {
            if ( !(unsigned int)_o__wcsicmp(a1, &v7[2080 * (unsigned int)v12]) )
            {
              IScsiSessionList = DiscpInsertToSparseBitmap(&v24, *(unsigned __int16 *)(v8 + 2 * v12));
              if ( IScsiSessionList )
                break;
            }
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= v28 )
              goto LABEL_27;
          }
        }
        else
        {
LABEL_27:
          v13 = (__int128 *)v24;
          IScsiSessionList = 0;
          v14 = 0;
          if ( (__int128 *)v24 != &v24 )
          {
            while ( 1 )
            {
              v15 = *((_WORD *)v13 + 10);
              if ( v15 != v14 )
                break;
              v16 = *((_DWORD *)v13 + 4);
              if ( v16 != -1 )
              {
                v17 = 0;
                while ( _bittest(&v16, (unsigned __int8)v17) )
                {
                  if ( (unsigned __int16)++v17 >= 0x20u )
                    goto LABEL_33;
                }
                *v27 = v17 + v15;
                goto LABEL_38;
              }
LABEL_33:
              v13 = *(__int128 **)v13;
              v14 = v15 + 32;
              if ( v13 == &v24 )
              {
                if ( v15 != -32 )
                  break;
                IScsiSessionList = 1450;
                goto LABEL_38;
              }
            }
          }
          *v27 = v14;
        }
LABEL_38:
        v18 = (__int128 *)v24;
        while ( v18 != &v24 )
        {
          v19 = v18;
          v18 = *(__int128 **)v18;
          DiscpFreeMemory(v19);
        }
      }
    }
LABEL_41:
    if ( v3 )
      DiscpFreeMemory(v3);
    if ( v7 )
      DiscpFreeMemory(v7);
    if ( v8 )
      DiscpFreeMemory(v8);
    return IScsiSessionList;
  }
  while ( 1 )
  {
    v6 = DiscpAllocMemory(v25);
    v3 = v6;
    if ( !v6 )
      return 8;
    IScsiSessionList = DiscpGetIScsiSessionList(&v25, &v23, v6);
    if ( IScsiSessionList != 122 )
      goto LABEL_6;
    DiscpFreeMemory(v3);
  }
}

```

## disassembly

```asm
0x18000b444  mov     [rsp-38h+arg_0], rbx
0x18000b449  mov     [rsp-38h+arg_10], r8
0x18000b44e  mov     [rsp-38h+arg_8], rdx
0x18000b453  push    rbp
0x18000b454  push    rsi
0x18000b455  push    rdi
0x18000b456  push    r12
0x18000b458  push    r13
0x18000b45a  push    r14
0x18000b45c  push    r15
0x18000b45e  mov     rbp, rsp
0x18000b461  sub     rsp, 50h
0x18000b465  xor     esi, esi
0x18000b467  lea     rdx, [rbp+var_20]
0x18000b46b  mov     r13, rcx
0x18000b46e  mov     [rbp+var_20], esi
0x18000b471  xorps   xmm0, xmm0
0x18000b474  mov     [rbp+arg_18], esi
0x18000b477  lea     rcx, [rbp+arg_8]
0x18000b47b  mov     dword ptr [rbp+arg_8], esi
0x18000b47e  xor     r8d, r8d
0x18000b481  movups  [rbp+var_18], xmm0
0x18000b485  call    DiscpGetIScsiSessionList
0x18000b48a  mov     ebx, eax
0x18000b48c  cmp     eax, 7Ah ; 'z'
0x18000b48f  jnz     short loc_18000B4CE
0x18000b491  mov     ecx, dword ptr [rbp+arg_8]
0x18000b494  call    cs:__imp_DiscpAllocMemory
0x18000b49a  mov     rsi, rax
0x18000b49d  test    rax, rax
0x18000b4a0  jz      short loc_18000B4C4
0x18000b4a2  mov     r8, rax
0x18000b4a5  lea     rdx, [rbp+var_20]
0x18000b4a9  lea     rcx, [rbp+arg_8]
0x18000b4ad  call    DiscpGetIScsiSessionList
0x18000b4b2  mov     ebx, eax
0x18000b4b4  cmp     eax, 7Ah ; 'z'
0x18000b4b7  jnz     short loc_18000B4CE
0x18000b4b9  mov     rcx, rsi
0x18000b4bc  call    cs:__imp_DiscpFreeMemory
0x18000b4c2  jmp     short loc_18000B491
0x18000b4c4  mov     ebx, 8
0x18000b4c9  jmp     loc_18000B700
0x18000b4ce  xor     r15d, r15d
0x18000b4d1  xor     r14d, r14d
0x18000b4d4  test    ebx, ebx
0x18000b4d6  jnz     loc_18000B6D6
0x18000b4dc  test    r13, r13
0x18000b4df  jz      loc_18000B57E
0x18000b4e5  mov     [rsp+50h+var_28], r14b
0x18000b4ea  lea     r8, [rbp+arg_8]
0x18000b4ee  xor     r9d, r9d
0x18000b4f1  mov     [rsp+50h+var_30], r14
0x18000b4f6  xor     edx, edx
0x18000b4f8  mov     dword ptr [rbp+arg_8], r14d
0x18000b4fc  lea     rcx, [rbp+arg_18]
0x18000b500  call    DiscpReportPeristentLogins
0x18000b505  mov     ebx, eax
0x18000b507  cmp     eax, 7Ah ; 'z'
0x18000b50a  jnz     short loc_18000B576
0x18000b50c  mov     ecx, dword ptr [rbp+arg_8]
0x18000b50f  call    cs:__imp_DiscpAllocMemory
0x18000b515  xor     r14d, r14d
0x18000b518  mov     r15, rax
0x18000b51b  test    rax, rax
0x18000b51e  jz      short loc_18000B56C
0x18000b520  mov     ecx, [rbp+arg_18]
0x18000b523  add     ecx, ecx
0x18000b525  call    cs:__imp_DiscpAllocMemory
0x18000b52b  mov     r14, rax
0x18000b52e  test    rax, rax
0x18000b531  jz      short loc_18000B56C
0x18000b533  mov     r9d, [rbp+arg_18]
0x18000b537  lea     r8, [rbp+arg_8]
0x18000b53b  mov     [rsp+50h+var_28], 0
0x18000b540  lea     rcx, [rbp+arg_18]
0x18000b544  mov     rdx, r15
0x18000b547  mov     [rsp+50h+var_30], rax
0x18000b54c  call    DiscpReportPeristentLogins
0x18000b551  mov     ebx, eax
0x18000b553  cmp     eax, 7Ah ; 'z'
0x18000b556  jnz     short loc_18000B576
0x18000b558  mov     rcx, r15
0x18000b55b  call    cs:__imp_DiscpFreeMemory
0x18000b561  mov     rcx, r14
0x18000b564  call    cs:__imp_DiscpFreeMemory
0x18000b56a  jmp     short loc_18000B50C
0x18000b56c  mov     ebx, 8
0x18000b571  jmp     loc_18000B6D6
0x18000b576  test    ebx, ebx
0x18000b578  jnz     loc_18000B6D6
0x18000b57e  lea     rax, [rbp+var_18]
0x18000b582  xor     r12d, r12d
0x18000b585  mov     qword ptr [rbp+var_18+8], rax
0x18000b589  lea     rax, [rbp+var_18]
0x18000b58d  mov     qword ptr [rbp+var_18], rax
0x18000b591  lea     r10d, [r12+1]
0x18000b596  cmp     [rbp+var_20], r12d
0x18000b59a  jbe     short loc_18000B602
0x18000b59c  mov     edi, r12d
0x18000b59f  shl     rdi, 6
0x18000b5a3  test    r13, r13
0x18000b5a6  jnz     short loc_18000B5B1
0x18000b5a8  cmp     [rdi+rsi+20h], r13
0x18000b5ad  jz      short loc_18000B5C3
0x18000b5af  jmp     short loc_18000B5F1
0x18000b5b1  mov     rdx, [rdi+rsi+20h]
0x18000b5b6  mov     rcx, r13
0x18000b5b9  call    cs:__imp__o__wcsicmp
0x18000b5bf  test    eax, eax
0x18000b5c1  jnz     short loc_18000B5EB
0x18000b5c3  movzx   edx, byte ptr [rdi+rsi+2Ch]
0x18000b5c8  mov     ecx, 100h
0x18000b5cd  movzx   eax, byte ptr [rdi+rsi+2Dh]
0x18000b5d2  imul    edx, ecx
0x18000b5d5  lea     rcx, [rbp+var_18]
0x18000b5d9  add     dx, ax
0x18000b5dc  call    DiscpInsertToSparseBitmap
0x18000b5e1  mov     ebx, eax
0x18000b5e3  test    eax, eax
0x18000b5e5  jnz     loc_18000B6BB
0x18000b5eb  mov     r10d, 1
0x18000b5f1  add     r12d, r10d
0x18000b5f4  cmp     r12d, [rbp+var_20]
0x18000b5f8  jb      short loc_18000B59C
0x18000b5fa  test    ebx, ebx
0x18000b5fc  jnz     loc_18000B6BB
0x18000b602  test    r13, r13
0x18000b605  jz      short loc_18000B64E
0x18000b607  xor     edi, edi
0x18000b609  cmp     [rbp+arg_18], edi
0x18000b60c  jbe     short loc_18000B64E
0x18000b60e  mov     r12d, edi
0x18000b611  mov     rcx, r13
0x18000b614  imul    rdx, r12, 820h
0x18000b61b  add     rdx, r15
0x18000b61e  call    cs:__imp__o__wcsicmp
0x18000b624  test    eax, eax
0x18000b626  jnz     short loc_18000B63C
0x18000b628  movzx   edx, word ptr [r14+rdi*2]
0x18000b62d  lea     rcx, [rbp+var_18]
0x18000b631  call    DiscpInsertToSparseBitmap
0x18000b636  mov     ebx, eax
0x18000b638  test    eax, eax
0x18000b63a  jnz     short loc_18000B6BB
0x18000b63c  mov     r10d, 1
0x18000b642  add     edi, r10d
0x18000b645  cmp     edi, [rbp+arg_18]
0x18000b648  jb      short loc_18000B60E
0x18000b64a  test    ebx, ebx
0x18000b64c  jnz     short loc_18000B6BB
0x18000b64e  mov     r8, qword ptr [rbp+var_18]
0x18000b652  lea     rcx, [rbp+var_18]
0x18000b656  xor     ebx, ebx
0x18000b658  xor     eax, eax
0x18000b65a  cmp     r8, rcx
0x18000b65d  jz      short loc_18000B6B4
0x18000b65f  movzx   ecx, word ptr [r8+14h]
0x18000b664  cmp     cx, ax
0x18000b667  jnz     short loc_18000B6B4
0x18000b669  mov     r9d, [r8+10h]
0x18000b66d  cmp     r9d, 0FFFFFFFFh
0x18000b671  jz      short loc_18000B688
0x18000b673  xor     edx, edx
0x18000b675  movzx   eax, dl
0x18000b678  bt      r9d, eax
0x18000b67c  jnb     short loc_18000B6A8
0x18000b67e  add     dx, r10w
0x18000b682  cmp     dx, 20h ; ' '
0x18000b686  jb      short loc_18000B675
0x18000b688  mov     r8, [r8]
0x18000b68b  lea     rdx, [rbp+var_18]
0x18000b68f  lea     eax, [rcx+20h]
0x18000b692  cmp     r8, rdx
0x18000b695  jnz     short loc_18000B65F
0x18000b697  mov     edx, 0FFE0h
0x18000b69c  cmp     cx, dx
0x18000b69f  jnz     short loc_18000B6B4
0x18000b6a1  mov     ebx, 5AAh
0x18000b6a6  jmp     short loc_18000B6BB
0x18000b6a8  add     cx, dx
0x18000b6ab  mov     rdx, [rbp+arg_10]
0x18000b6af  mov     [rdx], cx
0x18000b6b2  jmp     short loc_18000B6BB
0x18000b6b4  mov     rdx, [rbp+arg_10]
0x18000b6b8  mov     [rdx], ax
0x18000b6bb  mov     rdi, qword ptr [rbp+var_18]
0x18000b6bf  jmp     short loc_18000B6CD
0x18000b6c1  mov     rcx, rdi
0x18000b6c4  mov     rdi, [rdi]
0x18000b6c7  call    cs:__imp_DiscpFreeMemory
0x18000b6cd  lea     rax, [rbp+var_18]
0x18000b6d1  cmp     rdi, rax
0x18000b6d4  jnz     short loc_18000B6C1
0x18000b6d6  test    rsi, rsi
0x18000b6d9  jz      short loc_18000B6E4
0x18000b6db  mov     rcx, rsi
0x18000b6de  call    cs:__imp_DiscpFreeMemory
0x18000b6e4  test    r15, r15
0x18000b6e7  jz      short loc_18000B6F2
0x18000b6e9  mov     rcx, r15
0x18000b6ec  call    cs:__imp_DiscpFreeMemory
0x18000b6f2  test    r14, r14
0x18000b6f5  jz      short loc_18000B700
0x18000b6f7  mov     rcx, r14
0x18000b6fa  call    cs:__imp_DiscpFreeMemory
0x18000b700  mov     eax, ebx
0x18000b702  mov     rbx, [rsp+50h+arg_0]
0x18000b70a  add     rsp, 50h
0x18000b70e  pop     r15
0x18000b710  pop     r14
0x18000b712  pop     r13
0x18000b714  pop     r12
0x18000b716  pop     rdi
0x18000b717  pop     rsi
0x18000b718  pop     rbp
0x18000b719  retn
```
