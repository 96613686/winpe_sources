# LsaDbpDsWriteByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *)

- ea: `0x18001287c`
- end: `0x180012a1c`
- name: `?LsaDbpDsWriteByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@@Z`
- size: `416`
- prototype: `int(struct _DSNAME *, unsigned int, struct _ATTRBLOCKSIMPLE *)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180013cbc`
- `0x180014358`
- `0x18001f600`
- `0x1800207bc`
- `0x18002e200`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180010d48`
- `0x180011580`
- `0x18001182c`
- `0x180011d6c`
- `0x18001287c`
- `0x18001f3b4`

## import_xrefs

- `NTDSA!THClearErrors` at `0x1800129d4`
- `NTDSA!THClearErrors` at `0x1800129d4`
- `NTDSA!DirModifyEntry` at `0x1800129c4`
- `NTDSA!DirModifyEntry` at `0x1800129c4`

## pseudocode

```c
__int64 __fastcall LsaDbpDsWriteByDsName(struct _DSNAME *a1, int a2, struct _ATTRBLOCKSIMPLE *a3)
{
  __int64 result; // rax
  _QWORD *v7; // rdi
  unsigned int v8; // ebx
  int i; // r9d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  __int128 *v13; // rax
  __int64 v14; // xmm1_8
  unsigned int v15; // eax
  struct _COMMRES *v16; // [rsp+20h] [rbp-E0h] BYREF
  struct _DSNAME *v17; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v18; // [rsp+38h] [rbp-C8h]
  _QWORD *v19; // [rsp+40h] [rbp-C0h]
  __int16 v20; // [rsp+48h] [rbp-B8h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  _BYTE v23[8]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+78h] [rbp-88h]

  v16 = 0;
  memset_0(&v17, 0, 0x118u);
  result = *(unsigned int *)a3;
  if ( (_DWORD)result )
  {
    v7 = 0;
    if ( (unsigned int)result > 1 )
    {
      v7 = LsaDbpDsAlloc(40 * (int)result - 40);
      if ( !v7 )
        return (unsigned int)-1073741801;
      for ( i = 0; i < *(_DWORD *)a3 - 1; v7[v11 + 4] = *(_QWORD *)(v12 + 24 * v10 + 40) )
      {
        v10 = i++;
        v11 = 5 * v10;
        LOWORD(v7[v11 + 1]) = a2 & 0xFFF;
        v7[v11] = &v7[5 * v10 + 5];
        v12 = *((_QWORD *)a3 + 1);
        *(_OWORD *)&v7[v11 + 2] = *(_OWORD *)(v12 + 24 * v10 + 24);
      }
      v7[5 * i - 5] = 0;
    }
    v19 = v7;
    v20 = a2 & 0xFFF;
    v13 = (__int128 *)*((_QWORD *)a3 + 1);
    v21 = *v13;
    v14 = *((_QWORD *)v13 + 2);
    v18 = *(_WORD *)a3;
    v22 = v14;
    v17 = a1;
    LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v23, a2);
    if ( (a2 & 0x2000) != 0 )
      v24 |= 0x1000u;
    v15 = DirModifyEntry(&v17, &v16);
    if ( v16 )
    {
      v8 = LsaDbpDsMapDsReturnToStatusEx(v15, v16);
    }
    else
    {
      THClearErrors();
      v8 = -1073741801;
    }
    LsaDbpDsContinueTransaction();
    LsaDbpDsFree(v7);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18001287c  mov     [rsp-8+arg_18], rbx
0x180012881  push    rbp
0x180012882  push    rsi
0x180012883  push    rdi
0x180012884  push    r14
0x180012886  push    r15
0x180012888  lea     rbp, [rsp-60h]
0x18001288d  sub     rsp, 160h
0x180012894  mov     rax, cs:__security_cookie
0x18001289b  xor     rax, rsp
0x18001289e  mov     [rbp+80h+var_30], rax
0x1800128a2  mov     rbx, r8
0x1800128a5  mov     [rsp+180h+var_160], 0
0x1800128ae  mov     esi, edx
0x1800128b0  mov     r14, rcx
0x1800128b3  xor     edx, edx; Val
0x1800128b5  lea     rcx, [rsp+180h+var_150]; void *
0x1800128ba  mov     r8d, 118h; Size
0x1800128c0  call    memset_0
0x1800128c5  mov     eax, [rbx]
0x1800128c7  test    eax, eax
0x1800128c9  jz      loc_1800129F9
0x1800128cf  xor     edi, edi
0x1800128d1  mov     r15d, 0FFFh
0x1800128d7  cmp     eax, 1
0x1800128da  jbe     loc_18001296D
0x1800128e0  lea     ecx, [rax+rax*4]
0x1800128e3  lea     ecx, ds:0FFFFFFFFFFFFFFD8h[rcx*8]; unsigned int
0x1800128ea  call    ?LsaDbpDsAlloc@@YAPEAXK@Z; LsaDbpDsAlloc(ulong)
0x1800128ef  mov     rdi, rax
0x1800128f2  test    rax, rax
0x1800128f5  jnz     short loc_180012901
0x1800128f7  mov     ebx, 0C0000017h
0x1800128fc  jmp     loc_1800129F7
0x180012901  mov     eax, [rbx]
0x180012903  xor     r9d, r9d
0x180012906  dec     eax
0x180012908  test    eax, eax
0x18001290a  jle     short loc_18001295D
0x18001290c  movzx   r10d, si
0x180012910  and     r10w, r15w
0x180012914  movsxd  rdx, r9d
0x180012917  inc     r9d
0x18001291a  lea     r8, [rdx+rdx*4]
0x18001291e  mov     [rdi+r8*8+8], r10w
0x180012924  lea     rax, [rdx+1]
0x180012928  lea     rax, [rax+rax*4]
0x18001292c  lea     rcx, [rdi+rax*8]
0x180012930  mov     [rdi+r8*8], rcx
0x180012934  lea     rcx, [rdx+rdx*2]
0x180012938  mov     rax, [rbx+8]
0x18001293c  movups  xmm0, xmmword ptr [rax+rcx*8+18h]
0x180012941  movups  xmmword ptr [rdi+r8*8+10h], xmm0
0x180012947  movsd   xmm1, qword ptr [rax+rcx*8+28h]
0x18001294d  movsd   qword ptr [rdi+r8*8+20h], xmm1
0x180012954  mov     eax, [rbx]
0x180012956  dec     eax
0x180012958  cmp     r9d, eax
0x18001295b  jl      short loc_180012914
0x18001295d  movsxd  rax, r9d
0x180012960  lea     rcx, [rax+rax*4]
0x180012964  mov     qword ptr [rdi+rcx*8-28h], 0
0x18001296d  mov     [rsp+180h+var_140], rdi
0x180012972  lea     rcx, [rsp+180h+var_110]; struct _COMMARG *
0x180012977  movzx   eax, si
0x18001297a  mov     edx, esi; unsigned int
0x18001297c  and     ax, r15w
0x180012980  mov     [rsp+180h+var_138], ax
0x180012985  mov     rax, [rbx+8]
0x180012989  movups  xmm0, xmmword ptr [rax]
0x18001298c  movaps  [rsp+180h+var_130], xmm0
0x180012991  movsd   xmm1, qword ptr [rax+10h]
0x180012996  movzx   eax, word ptr [rbx]
0x180012999  mov     [rsp+180h+var_148], ax
0x18001299e  movsd   [rsp+180h+var_120], xmm1
0x1800129a4  mov     [rsp+180h+var_150], r14
0x1800129a9  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x1800129ae  bt      esi, 0Dh
0x1800129b2  jnb     short loc_1800129BA
0x1800129b4  bts     [rsp+180h+var_108], 0Ch
0x1800129ba  lea     rdx, [rsp+180h+var_160]
0x1800129bf  lea     rcx, [rsp+180h+var_150]
0x1800129c4  call    cs:__imp_DirModifyEntry
0x1800129ca  mov     rdx, [rsp+180h+var_160]; struct _COMMRES *
0x1800129cf  test    rdx, rdx
0x1800129d2  jnz     short loc_1800129E1
0x1800129d4  call    cs:__imp_THClearErrors
0x1800129da  mov     ebx, 0C0000017h
0x1800129df  jmp     short loc_1800129EA
0x1800129e1  mov     ecx, eax; unsigned int
0x1800129e3  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x1800129e8  mov     ebx, eax
0x1800129ea  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x1800129ef  mov     rcx, rdi; void *
0x1800129f2  call    ?LsaDbpDsFree@@YAXPEAX@Z; LsaDbpDsFree(void *)
0x1800129f7  mov     eax, ebx
0x1800129f9  mov     rcx, [rbp+80h+var_30]
0x1800129fd  xor     rcx, rsp; StackCookie
0x180012a00  call    __security_check_cookie
0x180012a05  mov     rbx, [rsp+180h+arg_18]
0x180012a0d  add     rsp, 160h
0x180012a14  pop     r15
0x180012a16  pop     r14
0x180012a18  pop     rdi
0x180012a19  pop     rsi
0x180012a1a  pop     rbp
0x180012a1b  retn
```
