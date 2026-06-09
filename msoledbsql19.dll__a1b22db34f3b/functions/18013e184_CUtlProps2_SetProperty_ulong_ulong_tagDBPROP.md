# CUtlProps2::SetProperty(ulong,ulong,tagDBPROP *)

- ea: `0x18013e184`
- end: `0x18013e4af`
- name: `?SetProperty@CUtlProps2@@AEAAJKKPEAUtagDBPROP@@@Z`
- size: `811`
- prototype: `int(CUtlProps2 *__hidden this, unsigned int, unsigned int, struct tagDBPROP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18013dd5c`

## callees

- `0x180003030`
- `0x180003d80`
- `0x1801355e0`
- `0x180136b44`
- `0x180136c2c`
- `0x180136de8`
- `0x18013e184`
- `0x1801ad6a0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18013e2dd`
- `OLEAUT32!__imp_VariantClear` at `0x18013e303`
- `OLEAUT32!__imp_VariantClear` at `0x18013e2dd`
- `OLEAUT32!__imp_VariantClear` at `0x18013e303`
- `OLEAUT32!__imp_VariantCopy` at `0x18013e2f0`
- `OLEAUT32!__imp_VariantCopy` at `0x18013e3a7`
- `OLEAUT32!__imp_VariantCopy` at `0x18013e2f0`
- `OLEAUT32!__imp_VariantCopy` at `0x18013e3a7`

## pseudocode

```c
__int64 __fastcall CUtlProps2::SetProperty(CUtlProps2 *this, unsigned int a2, unsigned int a3, struct tagDBPROP *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // r10
  __int64 v10; // r15
  unsigned int v11; // edx
  HRESULT v12; // ebx
  __int64 v13; // rdi
  __int64 dwPropertyID; // r8
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rbx
  HRESULT v18; // eax
  CEXAutoBackupFile *v19; // rax
  CEXAutoBackupFile *v20; // rax
  int v22; // [rsp+30h] [rbp-68h] BYREF
  VARIANTARG pvargSrc; // [rsp+38h] [rbp-60h] BYREF

  v7 = 0;
  v8 = 3LL * a2;
  v9 = *((_QWORD *)this + 6);
  v10 = *(_QWORD *)(32LL * a2 + *((_QWORD *)this + 4) + 16) + 16LL * a3;
  v11 = *(_DWORD *)(v9 + 24LL * a2);
  if ( v11 )
  {
    do
    {
      if ( **(_DWORD **)(*(_QWORD *)(v9 + 8 * v8 + 8) + 8LL * v7) == a4->dwPropertyID )
        break;
      ++v7;
    }
    while ( v7 < v11 );
  }
  if ( v7 < v11 )
  {
    v13 = *(_QWORD *)(v9 + 8 * v8 + 16) + 56LL * v7;
    if ( !a4->vValue.vt )
    {
      dwPropertyID = a4->dwPropertyID;
      v15 = *(_QWORD *)this;
      v22 = 0;
      memset(&pvargSrc, 0, sizeof(pvargSrc));
      (*(void (__fastcall **)(CUtlProps2 *, _QWORD, __int64, int *, VARIANTARG *))(v15 + 88))(
        this,
        a2,
        dwPropertyID,
        &v22,
        &pvargSrc);
      if ( !v22 )
      {
        _mm_lfence();
        if ( (*(unsigned int (__fastcall **)(CUtlProps2 *, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)this + 56LL))(
               this,
               a2,
               v7,
               &pvargSrc) )
        {
LABEL_9:
          a4->dwStatus = 8;
          return (unsigned int)-2147467259;
        }
      }
      _mm_lfence();
      if ( (*(_DWORD *)(v10 + 12) & 0x100) != 0 )
      {
        _mm_lfence();
        v16 = *(_QWORD *)(v13 + 24);
        if ( v16 )
        {
          CColumnIds::~CColumnIds(*(CColumnIds **)(v13 + 24));
          if ( !*(_DWORD *)(v16 + 20) )
            (*(void (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 104LL))(g_pMO, v16);
        }
        *(_QWORD *)(v13 + 24) = 0;
      }
      VariantClear((VARIANTARG *)(v13 + 32));
      *(_DWORD *)(v13 + 4) &= ~1u;
      v12 = VariantCopy((VARIANTARG *)(v13 + 32), &pvargSrc);
      *(_DWORD *)v13 = v22;
      VariantClear(&pvargSrc);
      *(_DWORD *)(v13 + 12) = (v12 >> 31) & 7;
      goto LABEL_39;
    }
    if ( !a4->dwOptions )
    {
      _mm_lfence();
      if ( (*(unsigned int (__fastcall **)(CUtlProps2 *, _QWORD, _QWORD, VARIANT *))(*(_QWORD *)this + 56LL))(
             this,
             a2,
             v7,
             &a4->vValue) )
      {
        goto LABEL_9;
      }
    }
    if ( (*(_DWORD *)(v10 + 12) & 0x100) != 0 )
    {
      if ( (unsigned int)CompareDBIDs(&a4->colid, &DB_NULLID) )
      {
        v19 = *(CEXAutoBackupFile **)(v13 + 24);
        if ( !v19 )
        {
          v20 = (CEXAutoBackupFile *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO
                                                                                                  + 112LL))(
                                       g_pMO,
                                       24);
          if ( v20 )
          {
            *(_OWORD *)v20 = 0;
            *((_QWORD *)v20 + 2) = 0;
            v19 = CEXAutoBackupFile::CEXAutoBackupFile(v20);
          }
          else
          {
            v19 = 0;
          }
          *(_QWORD *)(v13 + 24) = v19;
        }
        *(_DWORD *)(v13 + 12) = 7;
        if ( !v19 )
        {
          if ( (bidGblFlags & 2) != 0 )
            v12 = bidTraceHR(off_180260758[0], 2521097, 2147942414LL);
          else
            v12 = -2147024882;
LABEL_39:
          if ( v12 < 0 )
            return (unsigned int)v12;
          goto LABEL_34;
        }
        _mm_lfence();
        v12 = CColumnIds::AddColumnId(*(CColumnIds **)(v13 + 24), a4);
        if ( v12 < 0 )
          return (unsigned int)v12;
LABEL_33:
        *(_DWORD *)(v13 + 4) |= 1u;
        *(_DWORD *)(v13 + 12) = 0;
LABEL_34:
        a4->dwStatus = 0;
        return (unsigned int)v12;
      }
      _mm_lfence();
      v17 = *(_QWORD *)(v13 + 24);
      if ( v17 )
      {
        CColumnIds::~CColumnIds(*(CColumnIds **)(v13 + 24));
        if ( !*(_DWORD *)(v17 + 20) )
          (*(void (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 104LL))(g_pMO, v17);
      }
      *(_QWORD *)(v13 + 24) = 0;
      *(_DWORD *)v13 = a4->dwOptions;
      v18 = VariantCopy((VARIANTARG *)(v13 + 32), &a4->vValue);
    }
    else
    {
      _mm_lfence();
      *(_DWORD *)v13 = a4->dwOptions;
      v18 = (*(__int64 (__fastcall **)(CUtlProps2 *, _QWORD, _QWORD, __int64, VARIANT *))(*(_QWORD *)this + 64LL))(
              this,
              a2,
              v7,
              v13 + 32,
              &a4->vValue);
    }
    v12 = v18;
    if ( v18 < 0 )
    {
      *(_DWORD *)(v13 + 12) = 7;
      return (unsigned int)v12;
    }
    goto LABEL_33;
  }
  v12 = -2147467259;
  a4->dwStatus = 1;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18013e184  mov     [rsp+arg_10], rbx
0x18013e189  push    rbp
0x18013e18a  push    rsi
0x18013e18b  push    rdi
0x18013e18c  push    r12
0x18013e18e  push    r13
0x18013e190  push    r14
0x18013e192  push    r15
0x18013e194  sub     rsp, 60h
0x18013e198  mov     rax, cs:__security_cookie
0x18013e19f  xor     rax, rsp
0x18013e1a2  mov     [rsp+98h+var_48], rax
0x18013e1a7  mov     r14, rcx
0x18013e1aa  mov     r12d, edx
0x18013e1ad  mov     ecx, edx
0x18013e1af  xor     r13d, r13d
0x18013e1b2  shl     rcx, 5
0x18013e1b6  mov     rsi, r9
0x18013e1b9  mov     r15d, r8d
0x18013e1bc  mov     ebx, r13d
0x18013e1bf  mov     rax, [r14+20h]
0x18013e1c3  lea     r9, [r12+r12*2]
0x18013e1c7  mov     r10, [r14+30h]
0x18013e1cb  shl     r15, 4
0x18013e1cf  add     r15, [rcx+rax+10h]
0x18013e1d4  mov     edx, [r10+r9*8]
0x18013e1d8  test    edx, edx
0x18013e1da  jz      short loc_18013E1F5
0x18013e1dc  mov     r8d, [rsi]
0x18013e1df  mov     r11, [r10+r9*8+8]
0x18013e1e4  mov     eax, ebx
0x18013e1e6  mov     rcx, [r11+rax*8]
0x18013e1ea  cmp     [rcx], r8d
0x18013e1ed  jz      short loc_18013E1F5
0x18013e1ef  inc     ebx
0x18013e1f1  cmp     ebx, edx
0x18013e1f3  jb      short loc_18013E1E4
0x18013e1f5  cmp     ebx, edx
0x18013e1f7  jb      short loc_18013E20A
0x18013e1f9  mov     ebx, 80004005h
0x18013e1fe  mov     dword ptr [rsi+8], 1
0x18013e205  jmp     loc_18013E42D
0x18013e20a  mov     eax, ebx
0x18013e20c  lea     rbp, [rsi+30h]
0x18013e210  imul    rdi, rax, 38h ; '8'
0x18013e214  add     rdi, [r10+r9*8+10h]
0x18013e219  cmp     [rbp+0], r13w
0x18013e21e  jnz     loc_18013E319
0x18013e224  mov     r8d, [rsi]
0x18013e227  lea     rcx, [rsp+98h+pvargSrc]
0x18013e22c  xor     eax, eax
0x18013e22e  mov     [rsp+98h+var_78], rcx
0x18013e233  mov     qword ptr [rsp+98h+pvargSrc+10h], rax
0x18013e238  lea     r9, [rsp+98h+var_68]
0x18013e23d  mov     rax, [r14]
0x18013e240  xorps   xmm0, xmm0
0x18013e243  mov     edx, r12d
0x18013e246  mov     [rsp+98h+var_68], r13d
0x18013e24b  mov     rcx, r14
0x18013e24e  movups  xmmword ptr [rsp+98h+pvargSrc], xmm0
0x18013e253  mov     rax, [rax+58h]
0x18013e257  call    cs:__guard_dispatch_icall_fptr
0x18013e25d  cmp     [rsp+98h+var_68], r13d
0x18013e262  jnz     short loc_18013E297
0x18013e264  lfence
0x18013e267  mov     rax, [r14]
0x18013e26a  lea     r9, [rsp+98h+pvargSrc]
0x18013e26f  mov     r8d, ebx
0x18013e272  mov     edx, r12d
0x18013e275  mov     rcx, r14
0x18013e278  mov     rax, [rax+38h]
0x18013e27c  call    cs:__guard_dispatch_icall_fptr
0x18013e282  test    eax, eax
0x18013e284  jz      short loc_18013E297
0x18013e286  mov     dword ptr [rsi+8], 8
0x18013e28d  mov     ebx, 80004005h
0x18013e292  jmp     loc_18013E42D
0x18013e297  lfence
0x18013e29a  test    dword ptr [r15+0Ch], 100h
0x18013e2a2  jz      short loc_18013E2D9
0x18013e2a4  lfence
0x18013e2a7  mov     rbx, [rdi+18h]
0x18013e2ab  test    rbx, rbx
0x18013e2ae  jz      short loc_18013E2D5
0x18013e2b0  mov     rcx, rbx; this
0x18013e2b3  call    ??1CColumnIds@@QEAA@XZ; CColumnIds::~CColumnIds(void)
0x18013e2b8  cmp     [rbx+14h], r13d
0x18013e2bc  jnz     short loc_18013E2D5
0x18013e2be  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18013e2c5  mov     rdx, rbx
0x18013e2c8  mov     rax, [rcx]
0x18013e2cb  mov     rax, [rax+68h]
0x18013e2cf  call    cs:__guard_dispatch_icall_fptr
0x18013e2d5  mov     [rdi+18h], r13
0x18013e2d9  lea     rcx, [rdi+20h]; pvarg
0x18013e2dd  call    cs:__imp_VariantClear
0x18013e2e3  and     dword ptr [rdi+4], 0FFFFFFFEh
0x18013e2e7  lea     rdx, [rsp+98h+pvargSrc]; pvargSrc
0x18013e2ec  lea     rcx, [rdi+20h]; pvargDest
0x18013e2f0  call    cs:__imp_VariantCopy
0x18013e2f6  mov     ebx, eax
0x18013e2f8  lea     rcx, [rsp+98h+pvargSrc]; pvarg
0x18013e2fd  mov     eax, [rsp+98h+var_68]
0x18013e301  mov     [rdi], eax
0x18013e303  call    cs:__imp_VariantClear
0x18013e309  mov     eax, ebx
0x18013e30b  sar     eax, 1Fh
0x18013e30e  and     eax, 7
0x18013e311  mov     [rdi+0Ch], eax
0x18013e314  jmp     loc_18013E47D
0x18013e319  cmp     [rsi+4], r13d
0x18013e31d  jnz     short loc_18013E343
0x18013e31f  lfence
0x18013e322  mov     rax, [r14]
0x18013e325  mov     r9, rbp
0x18013e328  mov     r8d, ebx
0x18013e32b  mov     edx, r12d
0x18013e32e  mov     rcx, r14
0x18013e331  mov     rax, [rax+38h]
0x18013e335  call    cs:__guard_dispatch_icall_fptr
0x18013e33b  test    eax, eax
0x18013e33d  jnz     loc_18013E286
0x18013e343  test    dword ptr [r15+0Ch], 100h
0x18013e34b  jz      loc_18013E483
0x18013e351  lea     rcx, [rsi+10h]; struct tagDBID *
0x18013e355  lea     rdx, DB_NULLID; struct tagDBID *
0x18013e35c  call    ?CompareDBIDs@@YAJPEBUtagDBID@@0@Z; CompareDBIDs(tagDBID const *,tagDBID const *)
0x18013e361  test    eax, eax
0x18013e363  jnz     short loc_18013E3BC
0x18013e365  lfence
0x18013e368  mov     rbx, [rdi+18h]
0x18013e36c  test    rbx, rbx
0x18013e36f  jz      short loc_18013E396
0x18013e371  mov     rcx, rbx; this
0x18013e374  call    ??1CColumnIds@@QEAA@XZ; CColumnIds::~CColumnIds(void)
0x18013e379  cmp     [rbx+14h], r13d
0x18013e37d  jnz     short loc_18013E396
0x18013e37f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18013e386  mov     rdx, rbx
0x18013e389  mov     rax, [rcx]
0x18013e38c  mov     rax, [rax+68h]
0x18013e390  call    cs:__guard_dispatch_icall_fptr
0x18013e396  mov     [rdi+18h], r13
0x18013e39a  lea     rdx, [rsi+30h]; pvargSrc
0x18013e39e  mov     eax, [rsi+4]
0x18013e3a1  lea     rcx, [rdi+20h]; pvargDest
0x18013e3a5  mov     [rdi], eax
0x18013e3a7  call    cs:__imp_VariantCopy
0x18013e3ad  mov     ebx, eax
0x18013e3af  test    eax, eax
0x18013e3b1  jns     short loc_18013E421
0x18013e3b3  mov     dword ptr [rdi+0Ch], 7
0x18013e3ba  jmp     short loc_18013E42D
0x18013e3bc  mov     rax, [rdi+18h]
0x18013e3c0  test    rax, rax
0x18013e3c3  jnz     short loc_18013E400
0x18013e3c5  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18013e3cc  mov     edx, 18h
0x18013e3d1  mov     rax, [rcx]
0x18013e3d4  mov     rax, [rax+70h]
0x18013e3d8  call    cs:__guard_dispatch_icall_fptr
0x18013e3de  test    rax, rax
0x18013e3e1  jz      short loc_18013E3F9
0x18013e3e3  xor     ecx, ecx
0x18013e3e5  xorps   xmm0, xmm0
0x18013e3e8  movups  xmmword ptr [rax], xmm0
0x18013e3eb  mov     [rax+10h], rcx
0x18013e3ef  mov     rcx, rax; this
0x18013e3f2  call    ??0CEXAutoBackupFile@@QEAA@XZ; CEXAutoBackupFile::CEXAutoBackupFile(void)
0x18013e3f7  jmp     short loc_18013E3FC
0x18013e3f9  mov     rax, r13
0x18013e3fc  mov     [rdi+18h], rax
0x18013e400  mov     dword ptr [rdi+0Ch], 7
0x18013e407  test    rax, rax
0x18013e40a  jz      short loc_18013E454
0x18013e40c  lfence
0x18013e40f  mov     rcx, [rdi+18h]; this
0x18013e413  mov     rdx, rsi; struct tagDBPROP *
0x18013e416  call    ?AddColumnId@CColumnIds@@QEAAJPEAUtagDBPROP@@@Z; CColumnIds::AddColumnId(tagDBPROP *)
0x18013e41b  mov     ebx, eax
0x18013e41d  test    eax, eax
0x18013e41f  js      short loc_18013E42D
0x18013e421  or      dword ptr [rdi+4], 1
0x18013e425  mov     [rdi+0Ch], r13d
0x18013e429  mov     [rsi+8], r13d
0x18013e42d  mov     eax, ebx
0x18013e42f  mov     rcx, [rsp+98h+var_48]
0x18013e434  xor     rcx, rsp; StackCookie
0x18013e437  call    __security_check_cookie
0x18013e43c  mov     rbx, [rsp+98h+arg_10]
0x18013e444  add     rsp, 60h
0x18013e448  pop     r15
0x18013e44a  pop     r14
0x18013e44c  pop     r13
0x18013e44e  pop     r12
0x18013e450  pop     rdi
0x18013e451  pop     rsi
0x18013e452  pop     rbp
0x18013e453  retn
0x18013e454  test    byte ptr cs:_bidGblFlags, 2
0x18013e45b  jz      short loc_18013E478
0x18013e45d  mov     rcx, cs:off_180260758; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x18013e464  mov     edx, 267809h
0x18013e469  mov     r8d, 8007000Eh
0x18013e46f  call    _bidTraceHR
0x18013e474  mov     ebx, eax
0x18013e476  jmp     short loc_18013E47D
0x18013e478  mov     ebx, 8007000Eh
0x18013e47d  test    ebx, ebx
0x18013e47f  js      short loc_18013E42D
0x18013e481  jmp     short loc_18013E429
0x18013e483  lfence
0x18013e486  mov     eax, [rsi+4]
0x18013e489  lea     r9, [rdi+20h]
0x18013e48d  mov     [rdi], eax
0x18013e48f  mov     r8d, ebx
0x18013e492  mov     rax, [r14]
0x18013e495  mov     edx, r12d
0x18013e498  mov     rcx, r14
0x18013e49b  mov     [rsp+98h+var_78], rbp
0x18013e4a0  mov     rax, [rax+40h]
0x18013e4a4  call    cs:__guard_dispatch_icall_fptr
0x18013e4aa  jmp     loc_18013E3AD
```
