# NDXGI::CDevice::SetDisplayModeCB(void *,_D3DDDICB_SETDISPLAYMODE *)

- ea: `0x1800851d0`
- end: `0x1800854ce`
- name: `?SetDisplayModeCB@CDevice@NDXGI@@KAJPEAXPEAU_D3DDDICB_SETDISPLAYMODE@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this, struct _D3DDDICB_SETDISPLAYMODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180022630`
- `0x1800851d0`
- `0x1800854d4`
- `0x1800a7328`
- `0x1800a9d20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800853de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800853de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800853d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800853d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180085413`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180085413`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::SetDisplayModeCB(NDXGI::CDevice *this, struct _D3DDDICB_SETDISPLAYMODE *a2)
{
  __int64 v4; // rsi
  char v5; // r15
  bool v6; // r8
  int v7; // ecx
  bool v8; // r14
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // ebx
  unsigned int v12; // edx
  RTL_SRWLOCK *v14; // r14
  __int64 v15; // rax
  int v16; // ecx
  bool v17; // cf
  int v18; // ecx
  unsigned int v19; // ecx
  DWORD CurrentThreadId; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v21[8]; // [rsp+28h] [rbp-60h] BYREF
  _DWORD v22[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v23; // [rsp+38h] [rbp-50h]
  int v24; // [rsp+48h] [rbp-40h]

  v23 = 0;
  v24 = 0;
  v22[0] = *((_DWORD *)this + 26);
  v22[1] = *(_DWORD *)a2;
  if ( *((_BYTE *)this + 898) )
  {
    v4 = *((_QWORD *)this + 186);
  }
  else
  {
    v14 = (RTL_SRWLOCK *)((char *)this + 1416);
    AcquireSRWLockShared((PSRWLOCK)this + 177);
    CurrentThreadId = GetCurrentThreadId();
    v15 = std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::find(
            (char *)this + 1424,
            v21,
            &CurrentThreadId);
    if ( *(_QWORD *)v15 == *((_QWORD *)this + 179) )
      v4 = 0;
    else
      v4 = *(_QWORD *)(*(_QWORD *)v15 + 24LL);
    if ( v14 )
      ReleaseSRWLockShared(v14);
  }
  v5 = 0;
  v6 = 0;
  v7 = *(_DWORD *)(v4 + 40);
  if ( (*(_BYTE *)(v4 + 52) & 1) != 0 )
  {
    v5 = 1;
    v6 = (*(_BYTE *)(v4 + 8) & 4) == 0;
  }
  v8 = (*(_BYTE *)(v4 + 52) & 2) != 0;
  v9 = (unsigned int)(*(_DWORD *)(v4 + 36) - 1);
  if ( *(_DWORD *)(v4 + 36) == 1 )
  {
    LODWORD(v23) = 1;
  }
  else if ( *(_DWORD *)(v4 + 36) == 2 )
  {
    LODWORD(v23) = 2;
  }
  else
  {
    LODWORD(v23) = 3;
  }
  v10 = v7 - 1;
  if ( v10 )
  {
    v16 = v10 - 1;
    if ( v16 )
    {
      if ( v16 == 1 )
        DWORD1(v23) = 3;
      else
        DWORD1(v23) = 4;
    }
    else
    {
      DWORD1(v23) = 2;
    }
  }
  else
  {
    DWORD1(v23) = 1;
  }
  if ( v6 )
    BYTE12(v23) |= 1u;
  v11 = CallAndLogImpl<long (*)(_D3DKMT_SETDISPLAYMODE const *),_D3DKMT_SETDISPLAYMODE *>(
          *(_QWORD *)(*((_QWORD *)this + 12) + 160LL),
          v9,
          v22);
  if ( v11 <= -1071774970 )
  {
    if ( v11 != -1071774970 && v11 != -1073741811 )
    {
      if ( v11 == -1073741801 || v11 == -1073741523 )
      {
LABEL_47:
        v12 = -2147024882;
        goto LABEL_33;
      }
      if ( v11 != -1071775744 )
      {
        if ( v11 == -1071775739 )
        {
          v17 = ((unsigned __int8)v5 | v8) != 0;
LABEL_56:
          v18 = v17 ? 0x879C020 : 0;
LABEL_57:
          v19 = v18 - 2147467259;
          v12 = -2005530512;
          if ( *((int *)this + 312) >= 0 )
            v12 = v19;
          goto LABEL_21;
        }
        if ( v11 != -1071775488 )
        {
          if ( v11 != -1071774972 )
          {
LABEL_20:
            v12 = NDXGI::CDevice::NTStatusToHResult(this, v11);
            goto LABEL_21;
          }
          goto LABEL_49;
        }
        goto LABEL_47;
      }
    }
LABEL_49:
    v17 = v5 != 0;
    goto LABEL_56;
  }
  if ( v11 == -1071774925 || v11 == -1071774920 || v11 == -1071774912 || v11 == -1071774910 )
    goto LABEL_49;
  if ( v11 == -1071774893 )
  {
    v18 = v8 ? 0x879C01D : 0;
    goto LABEL_57;
  }
  if ( v11 != -1071774891 )
    goto LABEL_20;
  v12 = -2005530502;
LABEL_33:
  if ( *((int *)this + 312) < 0 )
    v12 = -2005530512;
LABEL_21:
  *(_DWORD *)v4 = v12;
  *(_DWORD *)(v4 + 4) = v11;
  switch ( v12 )
  {
    case 0x88760870:
      return 0;
    case 0x8876087A:
      *((_DWORD *)a2 + 1) = DWORD2(v23);
      return v12;
    case 0x887A0022:
      if ( !v8 )
        return v12;
      return 0;
    case 0x887A0025:
      return 0;
  }
  return v12;
}

```

## disassembly

```asm
0x1800851d0  mov     [rsp+arg_10], rbx
0x1800851d5  push    rsi
0x1800851d6  push    rdi
0x1800851d7  push    r12
0x1800851d9  push    r14
0x1800851db  push    r15
0x1800851dd  sub     rsp, 60h
0x1800851e1  mov     rax, cs:__security_cookie
0x1800851e8  xor     rax, rsp
0x1800851eb  mov     [rsp+88h+var_38], rax
0x1800851f0  mov     r12, rdx
0x1800851f3  mov     rdi, rcx
0x1800851f6  xorps   xmm0, xmm0
0x1800851f9  movdqu  [rsp+88h+var_50], xmm0
0x1800851ff  mov     [rsp+88h+var_40], 0
0x180085207  mov     eax, [rcx+68h]
0x18008520a  mov     [rsp+88h+var_58], eax
0x18008520e  mov     eax, [rdx]
0x180085210  mov     [rsp+88h+var_54], eax
0x180085214  cmp     byte ptr [rcx+382h], 0
0x18008521b  jz      loc_1800853C7
0x180085221  mov     rsi, [rcx+5D0h]
0x180085228  xor     r15b, r15b
0x18008522b  xor     r8b, r8b
0x18008522e  xor     al, al
0x180085230  mov     edx, [rsi+24h]
0x180085233  mov     ecx, [rsi+28h]
0x180085236  mov     r9d, 1
0x18008523c  test    [rsi+34h], r9b
0x180085240  jnz     loc_180085422
0x180085246  mov     r10d, 2
0x18008524c  test    [rsi+34h], r10b
0x180085250  movzx   r14d, al
0x180085254  cmovnz  r14d, r9d
0x180085258  sub     edx, r9d
0x18008525b  jnz     loc_180085436
0x180085261  mov     dword ptr [rsp+88h+var_50], r9d
0x180085266  sub     ecx, r9d
0x180085269  jnz     loc_18008544C
0x18008526f  mov     dword ptr [rsp+88h+var_50+4], r9d
0x180085274  test    r8b, r8b
0x180085277  jnz     loc_18008546B
0x18008527d  mov     rcx, [rdi+60h]
0x180085281  lea     r8, [rsp+88h+var_58]
0x180085286  mov     rcx, [rcx+0A0h]
0x18008528d  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_SETDISPLAYMODE@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_SETDISPLAYMODE@@@ZPEBDPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_SETDISPLAYMODE const *),_D3DKMT_SETDISPLAYMODE *>(long (*)(_D3DKMT_SETDISPLAYMODE const *),char const *,_D3DKMT_SETDISPLAYMODE *)
0x180085292  mov     ebx, eax
0x180085294  mov     eax, 0C01E0306h
0x180085299  cmp     ebx, eax
0x18008529b  jg      loc_180085363
0x1800852a1  jz      loc_18008549E
0x1800852a7  cmp     ebx, 0C000000Dh
0x1800852ad  jz      loc_18008549E
0x1800852b3  cmp     ebx, 0C0000017h
0x1800852b9  jz      loc_180085482
0x1800852bf  cmp     ebx, 0C000012Dh
0x1800852c5  jz      loc_180085482
0x1800852cb  cmp     ebx, 0C01E0000h
0x1800852d1  jz      loc_18008549E
0x1800852d7  cmp     ebx, 0C01E0005h
0x1800852dd  jz      loc_180085475
0x1800852e3  cmp     ebx, 0C01E0100h
0x1800852e9  jz      loc_180085482
0x1800852ef  cmp     ebx, 0C01E0304h
0x1800852f5  jz      loc_18008549E
0x1800852fb  mov     edx, ebx; int
0x1800852fd  mov     rcx, rdi; this
0x180085300  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x180085305  mov     edx, eax
0x180085307  mov     r8d, 88760870h
0x18008530d  mov     [rsi], edx
0x18008530f  mov     [rsi+4], ebx
0x180085312  cmp     edx, r8d
0x180085315  jz      loc_1800854AF
0x18008531b  cmp     edx, 8876087Ah
0x180085321  jz      loc_1800854B6
0x180085327  cmp     edx, 887A0022h
0x18008532d  jz      loc_1800854A6
0x180085333  cmp     edx, 887A0025h
0x180085339  jz      loc_1800854AF
0x18008533f  mov     eax, edx
0x180085341  mov     rcx, [rsp+88h+var_38]
0x180085346  xor     rcx, rsp; StackCookie
0x180085349  call    __security_check_cookie
0x18008534e  mov     rbx, [rsp+88h+arg_10]
0x180085356  add     rsp, 60h
0x18008535a  pop     r15
0x18008535c  pop     r14
0x18008535e  pop     r12
0x180085360  pop     rdi
0x180085361  pop     rsi
0x180085362  retn
0x180085363  cmp     ebx, 0C01E0333h
0x180085369  jz      loc_18008549E
0x18008536f  cmp     ebx, 0C01E0338h
0x180085375  jz      loc_18008549E
0x18008537b  cmp     ebx, 0C01E0340h
0x180085381  jz      loc_18008549E
0x180085387  cmp     ebx, 0C01E0342h
0x18008538d  jz      loc_18008549E
0x180085393  cmp     ebx, 0C01E0353h
0x180085399  jz      loc_18008548C
0x18008539f  cmp     ebx, 0C01E0355h
0x1800853a5  jnz     loc_1800852FB
0x1800853ab  mov     edx, 8876087Ah
0x1800853b0  mov     eax, [rdi+4E0h]
0x1800853b6  mov     r8d, 88760870h
0x1800853bc  test    eax, eax
0x1800853be  cmovs   edx, r8d
0x1800853c2  jmp     loc_18008530D
0x1800853c7  lea     r14, [rcx+588h]
0x1800853ce  mov     rcx, r14; SRWLock
0x1800853d1  call    cs:__imp_AcquireSRWLockShared
0x1800853d7  lea     rbx, [rdi+590h]
0x1800853de  call    cs:__imp_GetCurrentThreadId
0x1800853e4  mov     [rsp+88h+var_68], eax
0x1800853e8  lea     r8, [rsp+88h+var_68]
0x1800853ed  lea     rdx, [rsp+88h+var_60]
0x1800853f2  mov     rcx, rbx
0x1800853f5  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::find(ulong const &)
0x1800853fa  mov     rsi, [rax]
0x1800853fd  cmp     rsi, [rbx+8]
0x180085401  jz      short loc_18008541E
0x180085403  mov     rsi, [rsi+18h]
0x180085407  test    r14, r14
0x18008540a  jz      loc_180085228
0x180085410  mov     rcx, r14; SRWLock
0x180085413  call    cs:__imp_ReleaseSRWLockShared
0x180085419  jmp     loc_180085228
0x18008541e  xor     esi, esi
0x180085420  jmp     short loc_180085407
0x180085422  mov     r15b, r9b
0x180085425  test    byte ptr [rsi+8], 4
0x180085429  movzx   r8d, r8b
0x18008542d  cmovz   r8d, r9d
0x180085431  jmp     loc_180085246
0x180085436  cmp     edx, r9d
0x180085439  jz      loc_1800EDCF0
0x18008543f  mov     dword ptr [rsp+88h+var_50], 3
0x180085447  jmp     loc_180085266
0x18008544c  sub     ecx, r9d
0x18008544f  jz      loc_1800EDD07
0x180085455  cmp     ecx, r9d
0x180085458  jz      loc_1800EDCFA
0x18008545e  mov     dword ptr [rsp+88h+var_50+4], 4
0x180085466  jmp     loc_180085274
0x18008546b  or      byte ptr [rsp+88h+var_50+0Ch], r9b
0x180085470  jmp     loc_18008527D
0x180085475  mov     al, r14b
0x180085478  or      al, r15b
0x18008547b  neg     al
0x18008547d  jmp     loc_1800EDD11
0x180085482  mov     edx, 8007000Eh
0x180085487  jmp     loc_1800853B0
0x18008548c  mov     al, r14b
0x18008548f  neg     al
0x180085491  sbb     ecx, ecx
0x180085493  and     ecx, 879C01Dh
0x180085499  jmp     loc_1800EDD19
0x18008549e  neg     r15b
0x1800854a1  jmp     loc_1800EDD11
0x1800854a6  test    r14b, r14b
0x1800854a9  jz      loc_18008533F
0x1800854af  xor     edx, edx
0x1800854b1  jmp     loc_18008533F
0x1800854b6  mov     eax, dword ptr [rsp+88h+var_50+8]
0x1800854ba  mov     [r12+4], eax
0x1800854bf  jmp     loc_18008533F
0x1800854c4  mov     eax, 8007000Eh
0x1800854c9  jmp     loc_180085341
0x1800edcf0  mov     dword ptr [rsp+88h+var_50], r10d
0x1800edcf5  jmp     loc_180085266
0x1800edcfa  mov     dword ptr [rsp+88h+var_50+4], 3
0x1800edd02  jmp     loc_180085274
0x1800edd07  mov     dword ptr [rsp+88h+var_50+4], r10d
0x1800edd0c  jmp     loc_180085274
0x1800edd11  sbb     ecx, ecx
0x1800edd13  and     ecx, 879C020h
0x1800edd19  mov     r8d, 88760870h
0x1800edd1f  add     ecx, 80004005h
0x1800edd25  mov     eax, [rdi+4E0h]
0x1800edd2b  mov     edx, r8d
0x1800edd2e  test    eax, eax
0x1800edd30  cmovns  edx, ecx
0x1800edd33  jmp     loc_18008530D
```
