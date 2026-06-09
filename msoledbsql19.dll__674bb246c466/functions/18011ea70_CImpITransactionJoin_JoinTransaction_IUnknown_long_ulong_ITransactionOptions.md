# CImpITransactionJoin::JoinTransaction(IUnknown *,long,ulong,ITransactionOptions *)

- ea: `0x18011ea70`
- end: `0x18011f0a3`
- name: `?JoinTransaction@CImpITransactionJoin@@UEAAJPEAUIUnknown@@JKPEAUITransactionOptions@@@Z`
- size: `1587`
- prototype: `int(CImpITransactionJoin *__hidden this, struct IUnknown *, int, unsigned int, struct ITransactionOptions *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003d80`
- `0x180008c80`
- `0x180009340`
- `0x180009700`
- `0x180075800`
- `0x18011ea70`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateGuid` at `0x18011ee10`
- `ole32!CoCreateGuid` at `0x18011ee10`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011eedd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011ef0d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011eedd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011ef0d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011eee9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011ef19`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011eee9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011ef19`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18011eb9f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18011eb9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CImpITransactionJoin::JoinTransaction(
        CImpITransactionJoin *this,
        struct IUnknown *a2,
        int a3,
        int a4,
        struct ITransactionOptions *a5)
{
  __int64 v9; // rbx
  _QWORD *v10; // r14
  HRESULT v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v15; // eax
  unsigned int v16; // r9d
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  char v25; // [rsp+40h] [rbp-61h]
  __int64 v26; // [rsp+48h] [rbp-59h]
  __int64 v27; // [rsp+50h] [rbp-51h]
  int v28; // [rsp+58h] [rbp-49h] BYREF
  __int64 v29; // [rsp+60h] [rbp-41h] BYREF
  __int128 v30; // [rsp+68h] [rbp-39h] BYREF
  __int128 v31; // [rsp+78h] [rbp-29h]
  __int64 v32; // [rsp+88h] [rbp-19h]
  int v33; // [rsp+90h] [rbp-11h]
  GUID pguid; // [rsp+98h] [rbp-9h] BYREF

  v29 = -1;
  if ( (bidGblFlags & 4) != 0 && off_180266670[0] )
    bidScopeEnterW(&v29, off_180266670[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  pguid = 0;
  v9 = *((_QWORD *)this + 1);
  v10 = *(_QWORD **)(v9 + 840);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v9 + 24) + 32LL) + 8LL))(*(_QWORD *)(v9 + 24) + 32LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v10[11] + 32LL) + 8LL))(v10[11] + 32LL);
  v26 = *(_QWORD *)(v9 + 24);
  v27 = v10[11];
  v25 = 0;
  if ( !g_AllocatorInUse )
  {
    v28 = 0;
    (*(void (__fastcall **)(struct ISOSHost *, int *))(*(_QWORD *)g_pISOSHost + 24LL))(g_pISOSHost, &v28);
    if ( !v28 )
    {
      (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 200LL))(g_pISOSHost);
      v25 = 1;
    }
  }
  SetErrorInfo(0, 0);
  if ( !a2 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 848LL) & 8) != 0 )
    {
      v22 = CDBConnection::EnlistTransaction((CDBConnection *)v10, 0, &IID_ITransactionJoin);
      v12 = v22;
      if ( v22 < 0 )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) != 0 )
          v22 = bidTraceHR(off_1802605E0[0], 350217, (unsigned int)v22);
        CError::PostSqlErrors(g_pCError, v22, &IID_ITransactionJoin, (struct CErrorData *)(v10 + 17));
        goto LABEL_80;
      }
      *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) &= ~8u;
    }
    goto LABEL_79;
  }
  if ( a4 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v11 = bidTraceHR(off_1802605E0[0], 219145, 2147799051LL);
    else
      v11 = -2147168245;
LABEL_12:
    v12 = CError::PostHResult(g_pCError, v11, &IID_ITransactionJoin);
LABEL_80:
    if ( (bidGblFlags & 2) != 0 && off_180263920[0] )
      bidTraceW(off_1802605E0[0], 362496, off_180263920[0], v12);
    goto LABEL_83;
  }
  if ( a3 != -1 )
  {
    if ( a3 <= 0x10000 )
    {
      if ( a3 == 0x10000 || a3 == 16 || a3 == 256 || a3 == 4096 )
        goto LABEL_19;
LABEL_29:
      if ( (bidGblFlags & 2) != 0 )
        v11 = bidTraceHR(off_1802605E0[0], 227337, 2147799048LL);
      else
        v11 = -2147168248;
      goto LABEL_12;
    }
    if ( a3 != 0x100000 )
    {
      if ( a3 != 0x1000000 )
        goto LABEL_29;
      v13 = v10[229];
      if ( !v13 || *(_BYTE *)(v13 + 1310) < 9u )
        goto LABEL_29;
    }
  }
LABEL_19:
  if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 848LL) & 1) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v11 = bidTraceHR(off_1802605E0[0], 236553, 2147799059LL);
    else
      v11 = -2147168237;
    goto LABEL_12;
  }
  if ( v10[9] )
  {
    v12 = -2147168227;
    if ( (bidGblFlags & 2) != 0 )
      v15 = bidTraceHR(off_1802605E0[0], 245769, 2147799069LL);
    else
      v15 = -2147168227;
    v16 = 40707;
LABEL_38:
    CError::PostError(g_pCError, v15, &IID_ITransactionJoin, v16, 0);
    goto LABEL_80;
  }
  v17 = v10[229];
  if ( (*(_BYTE *)(v17 + 416) & 1) != 0 )
  {
    if ( *(int *)(v17 + 376) > 0 )
    {
      v15 = -2147467259;
      v12 = -2147467259;
      if ( (bidGblFlags & 2) != 0 )
        v15 = bidTraceHR(off_1802605E0[0], 257033, 2147500037LL);
      v16 = 40733;
      goto LABEL_38;
    }
  }
  else if ( *(_DWORD *)(*(_QWORD *)(v17 + 24) + 792LL) )
  {
    v15 = -2147467259;
    v12 = -2147467259;
    if ( (bidGblFlags & 2) != 0 )
      v15 = bidTraceHR(off_1802605E0[0], 268297, 2147500037LL);
    v16 = 40709;
    goto LABEL_38;
  }
  if ( a5 )
  {
    v18 = ((__int64 (__fastcall *)(struct ITransactionOptions *, __int128 *))a5->lpVtbl->GetOptions)(a5, &v30);
    v12 = v18;
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_83;
      _mm_lfence();
      bidTraceHR(off_1802605E0[0], 281609, (unsigned int)v18);
      goto LABEL_80;
    }
    if ( (_DWORD)v30 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v11 = bidTraceHR(off_1802605E0[0], 289801, 2147799063LL);
      else
        v11 = -2147168233;
      goto LABEL_12;
    }
  }
  v11 = CoCreateGuid(&pguid);
  if ( v11 < 0 )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 )
      v11 = bidTraceHR(off_1802605E0[0], 302089, (unsigned int)v11);
    goto LABEL_12;
  }
  v19 = CDBConnection::EnlistTransaction((CDBConnection *)v10, a2, &IID_ITransactionJoin);
  v12 = v19;
  if ( v19 >= 0 )
  {
    if ( *((_QWORD *)this + 1) == -856 )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      *(GUID *)(*((_QWORD *)this + 1) + 856LL) = pguid;
    }
    v21 = *((_QWORD *)this + 1) + 896LL;
    if ( a5 )
    {
      if ( *((_QWORD *)this + 1) == -896 )
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      else
      {
        *(_OWORD *)v21 = v30;
        *(_OWORD *)(v21 + 16) = v31;
        *(_QWORD *)(v21 + 32) = v32;
        *(_DWORD *)(v21 + 40) = v33;
      }
      *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) |= 8u;
    }
    else
    {
      *(_OWORD *)v21 = 0;
      *(_OWORD *)(v21 + 16) = 0;
      *(_QWORD *)(v21 + 32) = 0;
      *(_DWORD *)(v21 + 40) = 0;
      *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) |= 8u;
    }
LABEL_79:
    v12 = 0;
    goto LABEL_80;
  }
  _mm_lfence();
  if ( (bidGblFlags & 2) != 0 )
    v19 = bidTraceHR(off_1802605E0[0], 313353, (unsigned int)v19);
  CError::PostSqlErrors(g_pCError, v19, &IID_ITransactionJoin, (struct CErrorData *)(v10 + 17));
  v20 = CDBConnection::EnlistTransaction((CDBConnection *)v10, 0, &IID_ITransactionJoin);
  if ( (bidGblFlags & 2) != 0 )
  {
    _mm_lfence();
    bidTraceHR(off_1802605E0[0], 320521, v20);
    goto LABEL_80;
  }
LABEL_83:
  if ( v25 )
    (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 208LL))(g_pISOSHost);
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v27 + 32) + 24LL))(v27 + 32);
    v23 = v26;
LABEL_88:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v23 + 32) + 24LL))(v23 + 32);
    goto LABEL_89;
  }
  v23 = v26;
  if ( v26 )
    goto LABEL_88;
LABEL_89:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v29);
  return v12;
}

```

## disassembly

```asm
0x18011ea70  push    rbp
0x18011ea72  push    rbx
0x18011ea73  push    rsi
0x18011ea74  push    rdi
0x18011ea75  push    r12
0x18011ea77  push    r13
0x18011ea79  push    r14
0x18011ea7b  push    r15
0x18011ea7d  lea     rbp, [rsp-17h]
0x18011ea82  sub     rsp, 0B8h
0x18011ea89  mov     rax, cs:__security_cookie
0x18011ea90  xor     rax, rsp
0x18011ea93  mov     [rbp+4Fh+var_48], rax
0x18011ea97  mov     r12d, r9d
0x18011ea9a  mov     edi, r8d
0x18011ea9d  mov     r13, rdx
0x18011eaa0  mov     rsi, rcx
0x18011eaa3  mov     r15, [rbp+4Fh+arg_20]
0x18011eaa7  mov     [rbp+4Fh+var_90], 0FFFFFFFFFFFFFFFFh
0x18011eaaf  test    byte ptr cs:_bidGblFlags, 4
0x18011eab6  jz      short loc_18011EAED
0x18011eab8  mov     rax, cs:off_180266670; "<ITransactionJoin::JoinTransaction|OLED"...
0x18011eabf  test    rax, rax
0x18011eac2  jz      short loc_18011EAED
0x18011eac4  mov     r8, [rcx+8]
0x18011eac8  mov     [rsp+0F0h+var_C0], r15
0x18011eacd  mov     [rsp+0F0h+var_C8], r9d
0x18011ead2  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18011ead6  mov     r9, rdx
0x18011ead9  mov     r8d, [r8+34h]
0x18011eadd  mov     rdx, cs:off_180266670; "<ITransactionJoin::JoinTransaction|OLED"...
0x18011eae4  lea     rcx, [rbp+4Fh+var_90]
0x18011eae8  call    _bidScopeEnterW
0x18011eaed  xorps   xmm0, xmm0
0x18011eaf0  xor     eax, eax
0x18011eaf2  movups  [rbp+4Fh+var_88], xmm0
0x18011eaf6  movups  [rbp+4Fh+var_78], xmm0
0x18011eafa  mov     [rbp+4Fh+var_68], rax
0x18011eafe  mov     [rbp+4Fh+var_60], eax
0x18011eb01  movups  xmmword ptr [rbp+4Fh+pguid.Data1], xmm0
0x18011eb05  mov     rbx, [rsi+8]
0x18011eb09  mov     r14, [rbx+348h]
0x18011eb10  movups  [rbp+4Fh+var_A8], xmm0
0x18011eb14  mov     rcx, [rbx+18h]
0x18011eb18  add     rcx, 20h ; ' '
0x18011eb1c  mov     rax, [rcx]
0x18011eb1f  mov     rax, [rax+8]
0x18011eb23  call    cs:__guard_dispatch_icall_fptr
0x18011eb29  mov     rcx, [r14+58h]
0x18011eb2d  add     rcx, 20h ; ' '
0x18011eb31  mov     rax, [rcx]
0x18011eb34  mov     rax, [rax+8]
0x18011eb38  call    cs:__guard_dispatch_icall_fptr
0x18011eb3e  mov     rax, [rbx+18h]
0x18011eb42  mov     qword ptr [rbp+4Fh+var_A8], rax
0x18011eb46  mov     rax, [r14+58h]
0x18011eb4a  mov     qword ptr [rbp+4Fh+var_A8+8], rax
0x18011eb4e  mov     [rbp+4Fh+var_B0], 0
0x18011eb52  cmp     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, 0; AllocatorEnum g_AllocatorInUse
0x18011eb59  jnz     short loc_18011EB9B
0x18011eb5b  mov     [rbp+4Fh+var_98], 0
0x18011eb62  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x18011eb69  mov     rax, [rcx]
0x18011eb6c  lea     rdx, [rbp+4Fh+var_98]
0x18011eb70  mov     rax, [rax+18h]
0x18011eb74  call    cs:__guard_dispatch_icall_fptr
0x18011eb7a  cmp     [rbp+4Fh+var_98], 0
0x18011eb7e  jnz     short loc_18011EB9B
0x18011eb80  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x18011eb87  mov     rax, [rcx]
0x18011eb8a  mov     rax, [rax+0C8h]
0x18011eb91  call    cs:__guard_dispatch_icall_fptr
0x18011eb97  mov     [rbp+4Fh+var_B0], 1
0x18011eb9b  xor     edx, edx; perrinfo
0x18011eb9d  xor     ecx, ecx; dwReserved
0x18011eb9f  call    cs:__imp_SetErrorInfo
0x18011eba5  test    r13, r13
0x18011eba8  jz      loc_18011EF7E
0x18011ebae  test    r12d, r12d
0x18011ebb1  jz      short loc_18011EBF6
0x18011ebb3  test    byte ptr cs:_bidGblFlags, 2
0x18011ebba  jz      short loc_18011EBD5
0x18011ebbc  mov     edx, 35809h
0x18011ebc1  mov     r8d, 8004D00Bh
0x18011ebc7  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ebce  call    _bidTraceHR
0x18011ebd3  jmp     short loc_18011EBDA
0x18011ebd5  mov     eax, 8004D00Bh
0x18011ebda  lea     r8, IID_ITransactionJoin; struct _GUID *
0x18011ebe1  mov     edx, eax; int
0x18011ebe3  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011ebea  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18011ebef  mov     ebx, eax
0x18011ebf1  jmp     loc_18011EFED
0x18011ebf6  cmp     edi, 0FFFFFFFFh
0x18011ebf9  jz      short loc_18011EC1A
0x18011ebfb  cmp     edi, 10000h
0x18011ec01  jg      short loc_18011EC4D
0x18011ec03  jz      short loc_18011EC1A
0x18011ec05  cmp     edi, 10h
0x18011ec08  jz      short loc_18011EC1A
0x18011ec0a  cmp     edi, 100h
0x18011ec10  jz      short loc_18011EC1A
0x18011ec12  cmp     edi, 1000h
0x18011ec18  jnz     short loc_18011EC7F
0x18011ec1a  mov     rax, [rsi+8]
0x18011ec1e  test    byte ptr [rax+350h], 1
0x18011ec25  jz      loc_18011ECB8
0x18011ec2b  test    byte ptr cs:_bidGblFlags, 2
0x18011ec32  jz      short loc_18011ECAE
0x18011ec34  mov     edx, 39C09h
0x18011ec39  mov     r8d, 8004D013h
0x18011ec3f  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ec46  call    _bidTraceHR
0x18011ec4b  jmp     short loc_18011EBDA
0x18011ec4d  cmp     edi, 100000h
0x18011ec53  jz      short loc_18011EC1A
0x18011ec55  cmp     edi, 1000000h
0x18011ec5b  jnz     short loc_18011EC7F
0x18011ec5d  mov     rax, [r14+728h]
0x18011ec64  test    rax, rax
0x18011ec67  jz      short loc_18011EC79
0x18011ec69  cmp     byte ptr [rax+51Eh], 9
0x18011ec70  jb      short loc_18011EC79
0x18011ec72  mov     eax, 1
0x18011ec77  jmp     short loc_18011EC7B
0x18011ec79  xor     eax, eax
0x18011ec7b  test    eax, eax
0x18011ec7d  jnz     short loc_18011EC1A
0x18011ec7f  test    byte ptr cs:_bidGblFlags, 2
0x18011ec86  jz      short loc_18011ECA4
0x18011ec88  mov     edx, 37809h
0x18011ec8d  mov     r8d, 8004D008h
0x18011ec93  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ec9a  call    _bidTraceHR
0x18011ec9f  jmp     loc_18011EBDA
0x18011eca4  mov     eax, 8004D008h
0x18011eca9  jmp     loc_18011EBDA
0x18011ecae  mov     eax, 8004D013h
0x18011ecb3  jmp     loc_18011EBDA
0x18011ecb8  cmp     qword ptr [r14+48h], 0
0x18011ecbd  jz      short loc_18011ED0E
0x18011ecbf  mov     ebx, 8004D01Dh
0x18011ecc4  test    byte ptr cs:_bidGblFlags, 2
0x18011eccb  jz      short loc_18011ECE3
0x18011eccd  mov     r8d, ebx
0x18011ecd0  mov     edx, 3C009h
0x18011ecd5  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ecdc  call    _bidTraceHR
0x18011ece1  jmp     short loc_18011ECE5
0x18011ece3  mov     eax, ebx
0x18011ece5  mov     r9d, 9F03h; unsigned int
0x18011eceb  mov     [rsp+0F0h+var_D0], 0; struct tagDISPPARAMS *
0x18011ecf4  lea     r8, IID_ITransactionJoin; struct _GUID *
0x18011ecfb  mov     edx, eax; int
0x18011ecfd  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011ed04  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x18011ed09  jmp     loc_18011EFED
0x18011ed0e  mov     rax, [r14+728h]
0x18011ed15  test    byte ptr [rax+1A0h], 1
0x18011ed1c  jz      short loc_18011ED53
0x18011ed1e  cmp     dword ptr [rax+178h], 0
0x18011ed25  jle     short loc_18011ED8F
0x18011ed27  mov     eax, 80004005h
0x18011ed2c  mov     ebx, eax
0x18011ed2e  test    byte ptr cs:_bidGblFlags, 2
0x18011ed35  jz      short loc_18011ED4B
0x18011ed37  mov     r8d, eax
0x18011ed3a  mov     edx, 3EC09h
0x18011ed3f  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ed46  call    _bidTraceHR
0x18011ed4b  mov     r9d, 9F1Dh
0x18011ed51  jmp     short loc_18011ECEB
0x18011ed53  mov     rax, [rax+18h]
0x18011ed57  cmp     dword ptr [rax+318h], 0
0x18011ed5e  jz      short loc_18011ED8F
0x18011ed60  mov     eax, 80004005h
0x18011ed65  mov     ebx, eax
0x18011ed67  test    byte ptr cs:_bidGblFlags, 2
0x18011ed6e  jz      short loc_18011ED84
0x18011ed70  mov     r8d, eax
0x18011ed73  mov     edx, 41809h
0x18011ed78  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ed7f  call    _bidTraceHR
0x18011ed84  mov     r9d, 9F05h
0x18011ed8a  jmp     loc_18011ECEB
0x18011ed8f  test    r15, r15
0x18011ed92  jz      short loc_18011EE0C
0x18011ed94  mov     rax, [r15]
0x18011ed97  lea     rdx, [rbp+4Fh+var_88]
0x18011ed9b  mov     rcx, r15
0x18011ed9e  mov     rax, [rax+20h]
0x18011eda2  call    cs:__guard_dispatch_icall_fptr
0x18011eda8  mov     ebx, eax
0x18011edaa  test    eax, eax
0x18011edac  jns     short loc_18011EDD7
0x18011edae  test    byte ptr cs:_bidGblFlags, 2
0x18011edb5  jz      loc_18011F01E
0x18011edbb  lfence
0x18011edbe  mov     r8d, eax
0x18011edc1  mov     edx, 44C09h
0x18011edc6  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011edcd  call    _bidTraceHR
0x18011edd2  jmp     loc_18011EFED
0x18011edd7  cmp     dword ptr [rbp+4Fh+var_88], 0
0x18011eddb  jz      short loc_18011EE0C
0x18011eddd  test    byte ptr cs:_bidGblFlags, 2
0x18011ede4  jz      short loc_18011EE02
0x18011ede6  mov     edx, 46C09h
0x18011edeb  mov     r8d, 8004D017h
0x18011edf1  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011edf8  call    _bidTraceHR
0x18011edfd  jmp     loc_18011EBDA
0x18011ee02  mov     eax, 8004D017h
0x18011ee07  jmp     loc_18011EBDA
0x18011ee0c  lea     rcx, [rbp+4Fh+pguid]; pguid
0x18011ee10  call    cs:__imp_CoCreateGuid
0x18011ee16  test    eax, eax
0x18011ee18  jns     short loc_18011EE43
0x18011ee1a  lfence
0x18011ee1d  test    byte ptr cs:_bidGblFlags, 2
0x18011ee24  jz      loc_18011EBDA
0x18011ee2a  mov     r8d, eax
0x18011ee2d  mov     edx, 49C09h
0x18011ee32  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ee39  call    _bidTraceHR
0x18011ee3e  jmp     loc_18011EBDA
0x18011ee43  lea     r8, IID_ITransactionJoin; struct _GUID *
0x18011ee4a  mov     rdx, r13; struct IUnknown *
0x18011ee4d  mov     rcx, r14; this
0x18011ee50  call    ?EnlistTransaction@CDBConnection@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; CDBConnection::EnlistTransaction(IUnknown *,_GUID const *)
0x18011ee55  mov     ebx, eax
0x18011ee57  test    eax, eax
0x18011ee59  jns     short loc_18011EED1
0x18011ee5b  lfence
0x18011ee5e  test    byte ptr cs:_bidGblFlags, 2
0x18011ee65  jz      short loc_18011EE7B
0x18011ee67  mov     r8d, eax
0x18011ee6a  mov     edx, 4C809h
0x18011ee6f  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011ee76  call    _bidTraceHR
0x18011ee7b  lea     r9, [r14+88h]; struct CErrorData *
0x18011ee82  lea     r8, IID_ITransactionJoin; struct _GUID *
0x18011ee89  mov     edx, eax; int
0x18011ee8b  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011ee92  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x18011ee97  lea     r8, IID_ITransactionJoin; struct _GUID *
0x18011ee9e  xor     edx, edx; struct IUnknown *
0x18011eea0  mov     rcx, r14; this
0x18011eea3  call    ?EnlistTransaction@CDBConnection@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; CDBConnection::EnlistTransaction(IUnknown *,_GUID const *)
0x18011eea8  test    byte ptr cs:_bidGblFlags, 2
0x18011eeaf  jz      loc_18011F01E
0x18011eeb5  lfence
0x18011eeb8  mov     r8d, eax
0x18011eebb  mov     edx, 4E409h
0x18011eec0  mov     rcx, cs:off_1802605E0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011eec7  call    _bidTraceHR
0x18011eecc  jmp     loc_18011EFED
0x18011eed1  mov     rax, [rsi+8]
0x18011eed5  add     rax, 358h
0x18011eedb  jnz     short loc_18011EEF1
0x18011eedd  call    cs:__imp__errno
0x18011eee3  mov     dword ptr [rax], 16h
0x18011eee9  call    cs:__imp__invalid_parameter_noinfo
0x18011eeef  jmp     short loc_18011EEF8
0x18011eef1  movups  xmm0, xmmword ptr [rbp+4Fh+pguid.Data1]
0x18011eef5  movups  xmmword ptr [rax], xmm0
0x18011eef8  mov     rcx, [rsi+8]
0x18011eefc  add     rcx, 380h
0x18011ef03  test    r15, r15
0x18011ef06  jz      short loc_18011EF5E
0x18011ef08  test    rcx, rcx
0x18011ef0b  jnz     short loc_18011EF2F
0x18011ef0d  call    cs:__imp__errno
0x18011ef13  mov     dword ptr [rax], 16h
0x18011ef19  call    cs:__imp__invalid_parameter_noinfo
0x18011ef1f  mov     rax, [rsi+8]
0x18011ef23  or      dword ptr [rax+350h], 8
0x18011ef2a  jmp     loc_18011EFEB
0x18011ef2f  movups  xmm0, [rbp+4Fh+var_88]
0x18011ef33  movups  xmmword ptr [rcx], xmm0
0x18011ef36  movups  xmm1, [rbp+4Fh+var_78]
0x18011ef3a  movups  xmmword ptr [rcx+10h], xmm1
0x18011ef3e  movsd   xmm0, [rbp+4Fh+var_68]
0x18011ef43  movsd   qword ptr [rcx+20h], xmm0
0x18011ef48  mov     eax, [rbp+4Fh+var_60]
0x18011ef4b  mov     [rcx+28h], eax
0x18011ef4e  mov     rax, [rsi+8]
0x18011ef52  or      dword ptr [rax+350h], 8
0x18011ef59  jmp     loc_18011EFEB
0x18011ef5e  xorps   xmm0, xmm0
0x18011ef61  xor     eax, eax
0x18011ef63  movups  xmmword ptr [rcx], xmm0
0x18011ef66  movups  xmmword ptr [rcx+10h], xmm0
0x18011ef6a  mov     [rcx+20h], rax
0x18011ef6e  mov     [rcx+28h], eax
0x18011ef71  mov     rax, [rsi+8]
0x18011ef75  or      dword ptr [rax+350h], 8
0x18011ef7c  jmp     short loc_18011EFEB
0x18011ef7e  mov     rax, [rsi+8]
  ... truncated ...
```
