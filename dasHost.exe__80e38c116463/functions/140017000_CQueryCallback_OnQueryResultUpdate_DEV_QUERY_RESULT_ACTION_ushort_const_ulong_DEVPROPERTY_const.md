# CQueryCallback::OnQueryResultUpdate(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)

- ea: `0x140017000`
- end: `0x14001736f`
- name: `?OnQueryResultUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z`
- size: `879`
- prototype: `__int64 __fastcall(__int64, unsigned int, const unsigned __int16 *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x140017380`
- `0x140017390`

## callees

- `0x140009060`
- `0x140009090`
- `0x140009e3c`
- `0x14000a8ac`
- `0x1400137f8`
- `0x140017000`
- `0x14001a830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001733f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001733f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400172ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400172ef`

## pseudocode

```c
__int64 __fastcall CQueryCallback::OnQueryResultUpdate(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned int i; // ebx
  bool v9; // zf
  __int64 v10; // rdx
  unsigned int v11; // ecx
  __int64 v12; // rax
  unsigned int j; // ecx
  __int64 v14; // rdx
  unsigned int v15; // ecx
  __int64 v16; // rax
  unsigned int ResultUpdateStub; // ebx
  unsigned int v18; // edx
  const unsigned __int16 *v19; // r14
  unsigned __int16 *v20; // rdi
  _WORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rcx
  const unsigned __int16 *v25; // rax
  __int64 v26; // r10
  __int64 v27; // rcx
  const unsigned __int16 *v28; // rax
  unsigned __int64 v29; // rsi
  unsigned __int16 *v30; // rax
  __int128 Buf1; // [rsp+30h] [rbp-88h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-78h]

  if ( a2 == 1 )
  {
    for ( i = 2; *(_DWORD *)(a1 + 44) <= 1u && i <= 4 || *(_DWORD *)(a1 + 44) == 2 && i <= 4; ++i )
    {
      v9 = *(_DWORD *)(a1 + 44) == 2;
      v33 = i;
      if ( v9 )
        Buf1 = DAF_PropertyNamespace_RequiredAepServiceKeys;
      else
        Buf1 = DAF_PropertyNamespace_RequiredAepKeys;
      if ( (*(_DWORD *)(a1 + 92) & 2) == 0 )
      {
        if ( !*(_DWORD *)(a1 + 72) )
          continue;
        v10 = *(_QWORD *)(a1 + 80);
        v11 = 0;
        while ( 1 )
        {
          v12 = 32LL * v11;
          if ( *(_DWORD *)(v12 + v10 + 16) == i && *(_OWORD *)(v12 + v10) == Buf1 )
            break;
          if ( ++v11 >= *(_DWORD *)(a1 + 72) )
            goto LABEL_16;
        }
      }
      for ( j = 0; j < a4; ++j )
      {
        if ( *(_DWORD *)(a5 + 48LL * j + 16) == i && *(_OWORD *)(a5 + 48LL * j) == Buf1 )
          goto LABEL_16;
      }
      if ( i != 4 || memcmp_0(&Buf1, DEVPKEY_Aep_FriendlyName, 0x10u) || !*(_DWORD *)(a1 + 72) )
        return (unsigned int)-2140930028;
      v14 = *(_QWORD *)(a1 + 80);
      v15 = 0;
      while ( 1 )
      {
        v16 = 32LL * v15;
        if ( *(_DWORD *)(v16 + v14 + 16) == 19
          && *(_QWORD *)(v16 + v14) == DEVPKEY_Aep_GeneratedFriendlyName
          && *(_QWORD *)(v16 + v14 + 8) == 0xDFEC811076A6618BuLL )
        {
          break;
        }
        if ( ++v15 >= *(_DWORD *)(a1 + 72) )
          return (unsigned int)-2140930028;
      }
      v18 = 0;
      if ( !a4 )
        return (unsigned int)-2140930028;
      while ( *(_DWORD *)(a5 + 48LL * v18 + 16) != 19
           || *(_QWORD *)(a5 + 48LL * v18) != DEVPKEY_Aep_GeneratedFriendlyName
           || *(_QWORD *)(a5 + 48LL * v18 + 8) != 0xDFEC811076A6618BuLL )
      {
        if ( ++v18 >= a4 )
          return (unsigned int)-2140930028;
      }
LABEL_16:
      ;
    }
  }
  v19 = *(const unsigned __int16 **)(a1 + 56);
  v20 = 0;
  if ( !v19 )
  {
    ResultUpdateStub = -2147024809;
    goto LABEL_62;
  }
  v21 = *(_WORD **)(a1 + 56);
  v22 = 0x7FFFFFFF;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v22;
  }
  while ( v22 );
  ResultUpdateStub = v22 == 0 ? 0x80070057 : 0;
  if ( !v22 )
  {
LABEL_62:
    if ( !ResultUpdateStub )
    {
      AcquireSRWLockShared((PSRWLOCK)(a1 + 96));
      if ( (*(_BYTE *)(a1 + 92) & 1) == 0 && *(_DWORD *)(a1 + 108) == 1 || *(_DWORD *)(a1 + 108) == 2 )
      {
        ResultUpdateStub = -2140930027;
      }
      else if ( *(_DWORD *)(a1 + 104) )
      {
        ResultUpdateStub = OnQueryResultUpdateStub(a2, v20, a4, a5, *(_QWORD *)(a1 + 48));
      }
      else
      {
        ResultUpdateStub = -2140930029;
      }
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 96));
    }
    goto LABEL_71;
  }
  v23 = (2 * (0x7FFFFFFF - v22)) & -(__int64)(v22 != 0);
  if ( a3 )
  {
    v24 = 0x7FFFFFFF;
    v25 = a3;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    ResultUpdateStub = v24 == 0 ? 0x80070057 : 0;
    if ( v24 )
    {
      v26 = (2 * (0x7FFFFFFF - v24)) & -(__int64)(v24 != 0);
      goto LABEL_50;
    }
  }
  else
  {
    ResultUpdateStub = -2147024809;
  }
  v26 = 0;
LABEL_50:
  if ( !ResultUpdateStub )
  {
    v27 = 0x7FFFFFFF;
    v28 = L"#";
    do
    {
      if ( !*v28 )
        break;
      ++v28;
      --v27;
    }
    while ( v27 );
    ResultUpdateStub = v27 == 0 ? 0x80070057 : 0;
    if ( !v27 )
      return ResultUpdateStub;
    v29 = v26 + 2 + v23 + (-(__int64)(v27 != 0) & (2 * (0x7FFFFFFF - v27)));
    v30 = (unsigned __int16 *)DAF_user_alloc(v29);
    v20 = v30;
    if ( !v30 )
      return (unsigned int)-2147024882;
    ResultUpdateStub = StringCbCopyW(v30, v29, v19);
    if ( ResultUpdateStub
      || (ResultUpdateStub = StringCbCatW(v20, v29, L"#")) != 0
      || (ResultUpdateStub = StringCbCatW(v20, v29, a3)) != 0 )
    {
      MIDL_user_free(v20);
      v20 = 0;
    }
    goto LABEL_62;
  }
LABEL_71:
  if ( v20 )
    MIDL_user_free(v20);
  return ResultUpdateStub;
}

```

## disassembly

```asm
0x140017000  mov     [rsp+arg_8], edx
0x140017004  push    rbx
0x140017005  push    rbp
0x140017006  push    rsi
0x140017007  push    rdi
0x140017008  push    r12
0x14001700a  push    r13
0x14001700c  push    r14
0x14001700e  push    r15
0x140017010  sub     rsp, 78h
0x140017014  mov     r15, [rsp+0B8h+arg_20]
0x14001701c  xor     r11d, r11d
0x14001701f  movaps  [rsp+0B8h+var_58], xmm6
0x140017024  mov     r13d, r9d
0x140017027  movaps  [rsp+0B8h+var_68], xmm7
0x14001702c  mov     r12, r8
0x14001702f  mov     rbp, rcx
0x140017032  cmp     edx, 1
0x140017035  jnz     loc_140017187
0x14001703b  movups  xmm6, cs:DAF_PropertyNamespace_RequiredAepServiceKeys
0x140017042  mov     rdi, cs:qword_1400215B0
0x140017049  lea     ebx, [rdx+1]
0x14001704c  movups  xmm7, cs:DAF_PropertyNamespace_RequiredAepKeys
0x140017053  mov     rsi, cs:DEVPKEY_Aep_GeneratedFriendlyName
0x14001705a  cmp     dword ptr [rbp+2Ch], 1
0x14001705e  ja      short loc_140017065
0x140017060  cmp     ebx, 4
0x140017063  jbe     short loc_140017078
0x140017065  cmp     dword ptr [rbp+2Ch], 2
0x140017069  jnz     loc_140017187
0x14001706f  cmp     ebx, 4
0x140017072  ja      loc_140017187
0x140017078  cmp     dword ptr [rbp+2Ch], 2
0x14001707c  mov     [rsp+0B8h+var_78], ebx
0x140017080  jnz     short loc_14001708A
0x140017082  movdqu  [rsp+0B8h+Buf1], xmm6
0x140017088  jmp     short loc_140017090
0x14001708a  movdqu  [rsp+0B8h+Buf1], xmm7
0x140017090  mov     eax, [rbp+5Ch]
0x140017093  mov     r8, qword ptr [rsp+0B8h+Buf1+8]
0x140017098  mov     r9, qword ptr [rsp+0B8h+Buf1]
0x14001709d  test    al, 2
0x14001709f  jnz     short loc_1400170D2
0x1400170a1  cmp     [rbp+48h], r11d
0x1400170a5  jbe     short loc_1400170CE
0x1400170a7  mov     rdx, [rbp+50h]
0x1400170ab  mov     ecx, r11d
0x1400170ae  mov     eax, ecx
0x1400170b0  shl     rax, 5
0x1400170b4  cmp     [rax+rdx+10h], ebx
0x1400170b8  jnz     short loc_1400170C7
0x1400170ba  cmp     [rax+rdx], r9
0x1400170be  jnz     short loc_1400170C7
0x1400170c0  cmp     [rax+rdx+8], r8
0x1400170c5  jz      short loc_1400170D2
0x1400170c7  inc     ecx
0x1400170c9  cmp     ecx, [rbp+48h]
0x1400170cc  jb      short loc_1400170AE
0x1400170ce  inc     ebx
0x1400170d0  jmp     short loc_14001705A
0x1400170d2  mov     ecx, r11d
0x1400170d5  cmp     ecx, r13d
0x1400170d8  jnb     short loc_1400170FB
0x1400170da  mov     eax, ecx
0x1400170dc  lea     rdx, [rax+rax*2]
0x1400170e0  add     rdx, rdx
0x1400170e3  cmp     [r15+rdx*8+10h], ebx
0x1400170e8  jnz     short loc_1400170F7
0x1400170ea  cmp     [r15+rdx*8], r9
0x1400170ee  jnz     short loc_1400170F7
0x1400170f0  cmp     [r15+rdx*8+8], r8
0x1400170f5  jz      short loc_1400170CE
0x1400170f7  inc     ecx
0x1400170f9  jmp     short loc_1400170D5
0x1400170fb  cmp     ebx, 4
0x1400170fe  jnz     short loc_14001714A
0x140017100  lea     r8d, [rbx+0Ch]; Size
0x140017104  lea     rdx, DEVPKEY_Aep_FriendlyName; Buf2
0x14001710b  lea     rcx, [rsp+0B8h+Buf1]; Buf1
0x140017110  call    memcmp_0
0x140017115  xor     r11d, r11d
0x140017118  test    eax, eax
0x14001711a  jnz     short loc_14001714A
0x14001711c  cmp     [rbp+48h], r11d
0x140017120  jbe     short loc_14001714A
0x140017122  mov     rdx, [rbp+50h]
0x140017126  mov     ecx, r11d
0x140017129  mov     eax, ecx
0x14001712b  shl     rax, 5
0x14001712f  cmp     dword ptr [rax+rdx+10h], 13h
0x140017134  jnz     short loc_140017143
0x140017136  cmp     [rax+rdx], rsi
0x14001713a  jnz     short loc_140017143
0x14001713c  cmp     [rax+rdx+8], rdi
0x140017141  jz      short loc_140017154
0x140017143  inc     ecx
0x140017145  cmp     ecx, [rbp+48h]
0x140017148  jb      short loc_140017129
0x14001714a  mov     ebx, 80640014h
0x14001714f  jmp     loc_140017352
0x140017154  mov     edx, r11d
0x140017157  test    r13d, r13d
0x14001715a  jz      short loc_14001714A
0x14001715c  mov     eax, edx
0x14001715e  lea     rcx, [rax+rax*2]
0x140017162  add     rcx, rcx
0x140017165  cmp     dword ptr [r15+rcx*8+10h], 13h
0x14001716b  jnz     short loc_14001717E
0x14001716d  cmp     [r15+rcx*8], rsi
0x140017171  jnz     short loc_14001717E
0x140017173  cmp     [r15+rcx*8+8], rdi
0x140017178  jz      loc_1400170CE
0x14001717e  inc     edx
0x140017180  cmp     edx, r13d
0x140017183  jb      short loc_14001715C
0x140017185  jmp     short loc_14001714A
0x140017187  mov     r14, [rbp+38h]
0x14001718b  mov     rdi, r11
0x14001718e  test    r14, r14
0x140017191  jz      loc_1400172E2
0x140017197  mov     edx, 7FFFFFFFh
0x14001719c  mov     rax, r14
0x14001719f  mov     ecx, edx
0x1400171a1  cmp     [rax], r11w
0x1400171a5  jz      short loc_1400171B1
0x1400171a7  add     rax, 2
0x1400171ab  sub     rcx, 1
0x1400171af  jnz     short loc_1400171A1
0x1400171b1  mov     rax, rcx
0x1400171b4  mov     r8d, 80070057h
0x1400171ba  neg     rax
0x1400171bd  sbb     ebx, ebx
0x1400171bf  not     ebx
0x1400171c1  and     ebx, r8d
0x1400171c4  test    rcx, rcx
0x1400171c7  jz      loc_1400172E7
0x1400171cd  mov     rax, rdx
0x1400171d0  sub     rax, rcx
0x1400171d3  add     rax, rax
0x1400171d6  neg     rcx
0x1400171d9  sbb     r9, r9
0x1400171dc  and     r9, rax
0x1400171df  test    r12, r12
0x1400171e2  jz      short loc_140017220
0x1400171e4  mov     rcx, rdx
0x1400171e7  mov     rax, r12
0x1400171ea  cmp     [rax], r11w
0x1400171ee  jz      short loc_1400171FA
0x1400171f0  add     rax, 2
0x1400171f4  sub     rcx, 1
0x1400171f8  jnz     short loc_1400171EA
0x1400171fa  mov     rax, rcx
0x1400171fd  neg     rax
0x140017200  sbb     ebx, ebx
0x140017202  not     ebx
0x140017204  and     ebx, r8d
0x140017207  test    rcx, rcx
0x14001720a  jz      short loc_140017223
0x14001720c  mov     rax, rdx
0x14001720f  sub     rax, rcx
0x140017212  add     rax, rax
0x140017215  neg     rcx
0x140017218  sbb     r10, r10
0x14001721b  and     r10, rax
0x14001721e  jmp     short loc_140017226
0x140017220  mov     ebx, r8d
0x140017223  mov     r10, r11
0x140017226  test    ebx, ebx
0x140017228  jnz     loc_140017345
0x14001722e  mov     rcx, rdx
0x140017231  lea     rax, asc_140024788; "#"
0x140017238  cmp     [rax], r11w
0x14001723c  jz      short loc_140017248
0x14001723e  add     rax, 2
0x140017242  sub     rcx, 1
0x140017246  jnz     short loc_140017238
0x140017248  mov     rax, rcx
0x14001724b  neg     rax
0x14001724e  sbb     ebx, ebx
0x140017250  not     ebx
0x140017252  and     ebx, r8d
0x140017255  test    rcx, rcx
0x140017258  jz      loc_140017352
0x14001725e  sub     rdx, rcx
0x140017261  neg     rcx
0x140017264  sbb     rax, rax
0x140017267  add     r10, 2
0x14001726b  lea     rsi, [rdx+rdx]
0x14001726f  and     rsi, rax
0x140017272  add     rsi, r9
0x140017275  add     rsi, r10
0x140017278  mov     rcx, rsi
0x14001727b  call    DAF_user_alloc
0x140017280  mov     rdi, rax
0x140017283  test    rax, rax
0x140017286  jnz     short loc_140017292
0x140017288  mov     ebx, 8007000Eh
0x14001728d  jmp     loc_140017352
0x140017292  mov     r8, r14; unsigned __int16 *
0x140017295  mov     rdx, rsi; unsigned __int64
0x140017298  mov     rcx, rdi; unsigned __int16 *
0x14001729b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400172a0  mov     ebx, eax
0x1400172a2  test    eax, eax
0x1400172a4  jnz     short loc_1400172D2
0x1400172a6  lea     r8, asc_140024788; "#"
0x1400172ad  mov     rdx, rsi; unsigned __int64
0x1400172b0  mov     rcx, rdi; unsigned __int16 *
0x1400172b3  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400172b8  mov     ebx, eax
0x1400172ba  test    eax, eax
0x1400172bc  jnz     short loc_1400172D2
0x1400172be  mov     r8, r12; unsigned __int16 *
0x1400172c1  mov     rdx, rsi; unsigned __int64
0x1400172c4  mov     rcx, rdi; unsigned __int16 *
0x1400172c7  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400172cc  mov     ebx, eax
0x1400172ce  test    eax, eax
0x1400172d0  jz      short loc_1400172E7
0x1400172d2  mov     rcx, rdi; void *
0x1400172d5  call    MIDL_user_free
0x1400172da  xor     r11d, r11d
0x1400172dd  mov     edi, r11d
0x1400172e0  jmp     short loc_1400172E7
0x1400172e2  mov     ebx, 80070057h
0x1400172e7  test    ebx, ebx
0x1400172e9  jnz     short loc_140017345
0x1400172eb  lea     rcx, [rbp+60h]; SRWLock
0x1400172ef  call    cs:__imp_AcquireSRWLockShared
0x1400172f5  test    byte ptr [rbp+5Ch], 1
0x1400172f9  jnz     short loc_140017301
0x1400172fb  cmp     dword ptr [rbp+6Ch], 1
0x1400172ff  jz      short loc_140017307
0x140017301  cmp     dword ptr [rbp+6Ch], 2
0x140017305  jnz     short loc_14001730E
0x140017307  mov     ebx, 80640015h
0x14001730c  jmp     short loc_14001733B
0x14001730e  cmp     dword ptr [rbp+68h], 0
0x140017312  jz      short loc_140017336
0x140017314  mov     rax, [rbp+30h]
0x140017318  mov     r9, r15
0x14001731b  mov     ecx, [rsp+0B8h+arg_8]
0x140017322  mov     r8d, r13d
0x140017325  mov     rdx, rdi
0x140017328  mov     [rsp+0B8h+var_98], rax
0x14001732d  call    ?OnQueryResultUpdateStub@@YAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@PEAX@Z; OnQueryResultUpdateStub(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const,void *)
0x140017332  mov     ebx, eax
0x140017334  jmp     short loc_14001733B
0x140017336  mov     ebx, 80640013h
0x14001733b  lea     rcx, [rbp+60h]; SRWLock
0x14001733f  call    cs:__imp_ReleaseSRWLockShared
0x140017345  test    rdi, rdi
0x140017348  jz      short loc_140017352
0x14001734a  mov     rcx, rdi; void *
0x14001734d  call    MIDL_user_free
0x140017352  movaps  xmm6, [rsp+0B8h+var_58]
0x140017357  mov     eax, ebx
0x140017359  movaps  xmm7, [rsp+0B8h+var_68]
0x14001735e  add     rsp, 78h
0x140017362  pop     r15
0x140017364  pop     r14
0x140017366  pop     r13
0x140017368  pop     r12
0x14001736a  pop     rdi
0x14001736b  pop     rsi
0x14001736c  pop     rbp
0x14001736d  pop     rbx
0x14001736e  retn
```
