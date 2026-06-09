# ProcessToBeRunUpdateHpkpJob

- ea: `0x180001868`
- end: `0x180001c98`
- name: `ProcessToBeRunUpdateHpkpJob`
- size: `1072`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180005460`

## callees

- `0x180001284`
- `0x1800015a4`
- `0x180001824`
- `0x180001868`
- `0x1800033a0`
- `0x1800068b0`
- `0x18000d788`
- `0x1800100d4`
- `0x180010608`
- `0x1800108b4`
- `0x18001094c`
- `0x180010a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001c76`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001c76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001b9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001b9a`
- `CRYPT32!CertFreeCTLContext` at `0x180001c39`
- `CRYPT32!CertFreeCTLContext` at `0x180001c4b`
- `CRYPT32!CertFreeCTLContext` at `0x180001c39`
- `CRYPT32!CertFreeCTLContext` at `0x180001c4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018c7`

## pseudocode

```c
int __fastcall ProcessToBeRunUpdateHpkpJob(__int64 a1)
{
  unsigned __int64 v1; // r13
  __int64 v2; // rbx
  void *v3; // r12
  _QWORD *v4; // r15
  DWORD cCTLEntry; // esi
  DWORD v6; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // r14d
  __int64 v10; // rax
  void *v11; // rbx
  PCCTL_CONTEXT v12; // r15
  __int64 v13; // rbx
  __int64 v14; // r13
  char *v15; // rcx
  HLOCAL *v16; // r14
  PCCTL_CONTEXT v17; // r10
  HLOCAL *v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rbx
  __int64 j; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r12
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 HpkpDomainEntry; // rax
  char *v29; // rdx
  unsigned int i; // ebx
  int result; // eax
  DWORD v32; // [rsp+30h] [rbp-39h]
  unsigned int v33; // [rsp+30h] [rbp-39h]
  void *v34; // [rsp+38h] [rbp-31h]
  DWORD v35; // [rsp+40h] [rbp-29h]
  int v36; // [rsp+44h] [rbp-25h]
  DWORD v37; // [rsp+48h] [rbp-21h]
  char *hMem; // [rsp+50h] [rbp-19h]
  PCCTL_CONTEXT pCtlContext; // [rsp+58h] [rbp-11h] BYREF
  PCCTL_CONTEXT v40; // [rsp+60h] [rbp-9h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-1h] BYREF
  __int128 v42; // [rsp+70h] [rbp+7h] BYREF
  int v44; // [rsp+D8h] [rbp+6Fh]
  unsigned int v45; // [rsp+E0h] [rbp+77h]
  DWORD v46; // [rsp+E8h] [rbp+7Fh]

  v1 = (unsigned int)dword_180020410;
  v36 = dword_180020410;
  v2 = (unsigned int)dword_180020410;
  v40 = 0;
  v45 = dword_180020410;
  v3 = 0;
  pCtlContext = 0;
  v4 = 0;
  hMem = 0;
  cCTLEntry = 0;
  v34 = 0;
  v6 = 0;
  *(_QWORD *)&v42 = 0;
  v32 = 0;
  v35 = 0;
  v46 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  GetHpkpCtls(&v40, &pCtlContext);
  if ( v40 )
  {
    v44 = 0;
    cCTLEntry = v40->pCtlInfo->cCTLEntry;
    v1 = cCTLEntry + (unsigned int)v1;
    v36 = v1;
    v9 = cCTLEntry;
    v32 = cCTLEntry;
    v35 = cCTLEntry;
  }
  else
  {
    v9 = 0;
    v44 = 1;
  }
  if ( pCtlContext )
  {
    v6 = pCtlContext->pCtlInfo->cCTLEntry;
    v2 = v6 + (unsigned int)v2;
    v45 = v2;
    v46 = v6;
  }
  else
  {
    v44 = 1;
  }
  v37 = v6;
  if ( !(_DWORD)v1 )
    goto LABEL_16;
  hMem = (char *)PkiZeroAlloc(160 * v1);
  if ( hMem )
  {
    v10 = PkiZeroAlloc(8 * v1);
    v34 = (void *)v10;
    v11 = (void *)v10;
    if ( !v10 )
      goto LABEL_56;
    if ( v9 )
    {
      v12 = v40;
      v13 = 0;
      v14 = v10;
      do
      {
        v15 = &hMem[160 * v13];
        *(_QWORD *)(v14 + 8 * v13) = v15;
        SetHpkpDomainEntryFromCtlEntry(v15, &v12->pCtlInfo->rgCTLEntry[v13]);
        LODWORD(v3) = (_DWORD)v3 + 1;
        ++v13;
      }
      while ( (unsigned int)v3 < v9 );
      cCTLEntry = v32;
      v4 = (_QWORD *)v42;
      LODWORD(v1) = v36;
      v3 = v34;
    }
    else
    {
      v3 = (void *)v10;
    }
    v2 = v45;
LABEL_16:
    v16 = 0;
    v33 = 0;
    if ( (_DWORD)v2 )
    {
      v16 = (HLOCAL *)PkiZeroAlloc(16 * v2);
      if ( !v16 )
      {
LABEL_55:
        v11 = v34;
        goto LABEL_56;
      }
      v4 = (_QWORD *)PkiZeroAlloc(8 * v2);
      if ( !v4 )
      {
LABEL_51:
        if ( v16 )
        {
          for ( i = 0; i < v33; ++i )
            PkiFree(*(&v16[2 * i] + 2 * v37));
          PkiFree(v16);
        }
        goto LABEL_55;
      }
      v8 = 0;
      if ( v6 )
      {
        v17 = pCtlContext;
        v7 = 0;
        do
        {
          v8 = (unsigned int)(v8 + 1);
          v18 = &v16[2 * v7];
          v19 = v7;
          v4[v7++] = v18;
          *v18 = &v17->pCtlInfo->rgCTLEntry[v19];
        }
        while ( (unsigned int)v8 < v6 );
      }
    }
    v20 = ::hMem;
    while ( 2 )
    {
      if ( v20 )
      {
        for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
        {
          v22 = v4[j];
          if ( **(_DWORD **)v22 == 16 )
          {
            v23 = *(_QWORD **)(*(_QWORD *)v22 + 8LL);
            v24 = *v23 - v20[6];
            if ( *v23 == v20[6] )
              v24 = v23[1] - v20[7];
            if ( !v24 )
              goto LABEL_34;
          }
        }
        if ( v6 < v45 )
        {
          v1 = (unsigned __int64)&v16[2 * v6];
          v25 = v6;
          if ( !(unsigned int)SetHpkpHeaderEntryFromPendingEntry(v1, v20, v7, v8) )
            goto LABEL_51;
          ++v6;
          v4[v25] = v1;
          ++v33;
          LODWORD(v1) = v36;
          v46 = v6;
          v44 = 1;
LABEL_34:
          v26 = v20[4];
          *(_QWORD *)&v42 = 0;
          *((_QWORD *)&v42 + 1) = v26;
          if ( v26 )
          {
            v27 = -1;
            do
              ++v27;
            while ( *(_BYTE *)(v26 + v27) );
          }
          else
          {
            LODWORD(v27) = 0;
          }
          v3 = v34;
          LODWORD(v42) = v27;
          if ( !(_DWORD)v27 )
          {
LABEL_46:
            v20 = (_QWORD *)*v20;
            continue;
          }
          HpkpDomainEntry = FindHpkpDomainEntry(v34, cCTLEntry, &v42, v8);
          if ( HpkpDomainEntry )
          {
            if ( !(unsigned int)UpdateHpkpDomainEntryFromPendingEntry(HpkpDomainEntry, v20) )
              goto LABEL_46;
            goto LABEL_45;
          }
          if ( cCTLEntry < (unsigned int)v1 )
          {
            v7 = cCTLEntry;
            v29 = &hMem[160 * cCTLEntry++];
            v35 = cCTLEntry;
            *(_OWORD *)v29 = v42;
            *((_OWORD *)v29 + 1) = 0;
            *((_OWORD *)v29 + 2) = 0;
            *((_OWORD *)v29 + 3) = 0;
            *((_QWORD *)v29 + 2) = v20[1];
            *((_QWORD *)v29 + 3) = v20[2];
            *((_DWORD *)v29 + 8) = *((_DWORD *)v20 + 6);
            *((_DWORD *)v29 + 9) = *(_DWORD *)(v20[5] + 8LL);
            *((_DWORD *)v29 + 10) = *(_DWORD *)(v20[5] + 12LL);
            *((_OWORD *)v29 + 3) = *((_OWORD *)v20 + 3);
            *((_QWORD *)v34 + v7) = v29;
LABEL_45:
            v44 = 1;
            goto LABEL_46;
          }
        }
        SetLastError(0x8000FFFF);
      }
      else if ( (unsigned int)RemoveExpiredOrNotInUseHpkpEntry(v3, &SystemTimeAsFileTime) || v44 )
      {
        EncodeAndSetHpkpCtls((_DWORD)v3, v35, (_DWORD)v4, v46, (__int64)&SystemTimeAsFileTime);
      }
      goto LABEL_51;
    }
  }
  v11 = 0;
LABEL_56:
  PkiFree(hMem);
  PkiFree(v11);
  PkiFree(v4);
  if ( pCtlContext )
    CertFreeCTLContext(pCtlContext);
  if ( v40 )
    CertFreeCTLContext(v40);
  FreePendingHpkp();
  result = FreeUpdateHpkpJob(a1);
  qword_180020400 = 0;
  if ( g_hTestHpkpEvent )
    return SetEvent(g_hTestHpkpEvent);
  return result;
}

```

## disassembly

```asm
0x180001868  mov     [rsp-8+arg_0], rcx
0x18000186d  push    rbp
0x18000186e  push    rbx
0x18000186f  push    rsi
0x180001870  push    rdi
0x180001871  push    r12
0x180001873  push    r13
0x180001875  push    r14
0x180001877  push    r15
0x180001879  lea     rbp, [rsp-1Fh]
0x18000187e  sub     rsp, 88h
0x180001885  mov     r13d, cs:dword_180020410
0x18000188c  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001890  xor     eax, eax
0x180001892  mov     [rbp+57h+var_7C], r13d
0x180001896  mov     ebx, r13d
0x180001899  mov     [rbp+57h+var_60], rax
0x18000189d  mov     [rbp+57h+arg_10], ebx
0x1800018a0  mov     r12d, eax
0x1800018a3  mov     [rbp+57h+pCtlContext], rax
0x1800018a7  mov     r15d, eax
0x1800018aa  mov     [rbp+57h+hMem], rax
0x1800018ae  mov     esi, eax
0x1800018b0  mov     [rbp+57h+var_88], rax
0x1800018b4  mov     edi, eax
0x1800018b6  mov     qword ptr [rbp+57h+var_50], rax
0x1800018ba  mov     [rbp+57h+var_90], eax
0x1800018bd  mov     [rbp+57h+var_80], eax
0x1800018c0  mov     [rbp+57h+arg_18], eax
0x1800018c3  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800018c7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800018cd  lea     rdx, [rbp+57h+pCtlContext]
0x1800018d1  lea     rcx, [rbp+57h+var_60]
0x1800018d5  call    _GetHpkpCtls
0x1800018da  mov     rax, [rbp+57h+var_60]
0x1800018de  test    rax, rax
0x1800018e1  jz      short loc_1800018FF
0x1800018e3  mov     rax, [rax+18h]
0x1800018e7  mov     [rbp+57h+arg_8], edi
0x1800018ea  mov     esi, [rax+60h]
0x1800018ed  add     r13d, esi
0x1800018f0  mov     [rbp+57h+var_7C], r13d
0x1800018f4  mov     r14d, esi
0x1800018f7  mov     [rbp+57h+var_90], esi
0x1800018fa  mov     [rbp+57h+var_80], esi
0x1800018fd  jmp     short loc_180001909
0x1800018ff  xor     r14d, r14d
0x180001902  mov     [rbp+57h+arg_8], 1
0x180001909  mov     rax, [rbp+57h+pCtlContext]
0x18000190d  test    rax, rax
0x180001910  jz      short loc_180001923
0x180001912  mov     rax, [rax+18h]
0x180001916  mov     edi, [rax+60h]
0x180001919  add     ebx, edi
0x18000191b  mov     [rbp+57h+arg_10], ebx
0x18000191e  mov     [rbp+57h+arg_18], edi
0x180001921  jmp     short loc_18000192A
0x180001923  mov     [rbp+57h+arg_8], 1
0x18000192a  mov     [rbp+57h+var_78], edi
0x18000192d  test    r13d, r13d
0x180001930  jz      loc_1800019CC
0x180001936  lea     rcx, ds:0[r13*4]
0x18000193e  add     rcx, r13
0x180001941  shl     rcx, 5; uBytes
0x180001945  call    PkiZeroAlloc
0x18000194a  mov     [rbp+57h+hMem], rax
0x18000194e  test    rax, rax
0x180001951  jz      loc_180001C90
0x180001957  lea     rcx, ds:0[r13*8]; uBytes
0x18000195f  call    PkiZeroAlloc
0x180001964  mov     [rbp+57h+var_88], rax
0x180001968  mov     rbx, rax
0x18000196b  test    rax, rax
0x18000196e  jz      loc_180001C14
0x180001974  test    r14d, r14d
0x180001977  jz      short loc_1800019C6
0x180001979  mov     r15, [rbp+57h+var_60]
0x18000197d  xor     ebx, ebx
0x18000197f  mov     rsi, [rbp+57h+hMem]
0x180001983  mov     r13, rax
0x180001986  lea     rcx, [rbx+rbx*4]
0x18000198a  mov     rdx, rbx
0x18000198d  shl     rcx, 5
0x180001991  add     rcx, rsi
0x180001994  shl     rdx, 5
0x180001998  mov     [r13+rbx*8+0], rcx
0x18000199d  mov     rax, [r15+18h]
0x1800019a1  add     rdx, [rax+68h]
0x1800019a5  call    _SetHpkpDomainEntryFromCtlEntry
0x1800019aa  inc     r12d
0x1800019ad  inc     rbx
0x1800019b0  cmp     r12d, r14d
0x1800019b3  jb      short loc_180001986
0x1800019b5  mov     esi, [rbp+57h+var_90]
0x1800019b8  mov     r15, qword ptr [rbp+57h+var_50]
0x1800019bc  mov     r13d, [rbp+57h+var_7C]
0x1800019c0  mov     r12, [rbp+57h+var_88]
0x1800019c4  jmp     short loc_1800019C9
0x1800019c6  mov     r12, rax
0x1800019c9  mov     ebx, [rbp+57h+arg_10]
0x1800019cc  xor     r14d, r14d
0x1800019cf  mov     [rbp+57h+var_90], r14d
0x1800019d3  test    ebx, ebx
0x1800019d5  jz      short loc_180001A46
0x1800019d7  mov     rcx, rbx
0x1800019da  shl     rcx, 4; uBytes
0x1800019de  call    PkiZeroAlloc
0x1800019e3  mov     r14, rax
0x1800019e6  test    rax, rax
0x1800019e9  jz      loc_180001C10
0x1800019ef  lea     rcx, ds:0[rbx*8]; uBytes
0x1800019f7  call    PkiZeroAlloc
0x1800019fc  mov     r15, rax
0x1800019ff  test    rax, rax
0x180001a02  jz      loc_180001BE2
0x180001a08  mov     r11d, [rbp+57h+var_78]
0x180001a0c  xor     r9d, r9d
0x180001a0f  test    r11d, r11d
0x180001a12  jz      short loc_180001A46
0x180001a14  mov     r10, [rbp+57h+pCtlContext]
0x180001a18  xor     r8d, r8d
0x180001a1b  mov     rdx, r8
0x180001a1e  mov     rcx, r8
0x180001a21  shl     rdx, 4
0x180001a25  inc     r9d
0x180001a28  add     rdx, r14
0x180001a2b  shl     rcx, 5
0x180001a2f  mov     [r15+r8*8], rdx
0x180001a33  inc     r8
0x180001a36  mov     rax, [r10+18h]
0x180001a3a  add     rcx, [rax+68h]
0x180001a3e  mov     [rdx], rcx
0x180001a41  cmp     r9d, r11d
0x180001a44  jb      short loc_180001A1B
0x180001a46  mov     rbx, cs:hMem
0x180001a4d  test    rbx, rbx
0x180001a50  jz      loc_180001BA2
0x180001a56  xor     edx, edx
0x180001a58  cmp     edx, edi
0x180001a5a  jnb     short loc_180001A86
0x180001a5c  mov     rcx, [r15+rdx*8]
0x180001a60  mov     rax, [rcx]
0x180001a63  cmp     dword ptr [rax], 10h
0x180001a66  jnz     short loc_180001A82
0x180001a68  mov     rcx, [rax+8]
0x180001a6c  mov     rax, [rcx]
0x180001a6f  sub     rax, [rbx+30h]
0x180001a73  jnz     short loc_180001A7D
0x180001a75  mov     rax, [rcx+8]
0x180001a79  sub     rax, [rbx+38h]
0x180001a7d  test    rax, rax
0x180001a80  jz      short loc_180001AC6
0x180001a82  inc     edx
0x180001a84  jmp     short loc_180001A58
0x180001a86  cmp     edi, [rbp+57h+arg_10]
0x180001a89  jnb     loc_180001B95
0x180001a8f  mov     r13d, edi
0x180001a92  mov     rdx, rbx
0x180001a95  shl     r13, 4
0x180001a99  add     r13, r14
0x180001a9c  mov     r12d, edi
0x180001a9f  mov     rcx, r13
0x180001aa2  call    _SetHpkpHeaderEntryFromPendingEntry
0x180001aa7  test    eax, eax
0x180001aa9  jz      loc_180001BE2
0x180001aaf  inc     edi
0x180001ab1  mov     [r15+r12*8], r13
0x180001ab5  inc     [rbp+57h+var_90]
0x180001ab8  mov     r13d, [rbp+57h+var_7C]
0x180001abc  mov     [rbp+57h+arg_18], edi
0x180001abf  mov     [rbp+57h+arg_8], 1
0x180001ac6  mov     rcx, [rbx+20h]
0x180001aca  mov     qword ptr [rbp+57h+var_50], 0
0x180001ad2  mov     qword ptr [rbp+57h+var_50+8], rcx
0x180001ad6  test    rcx, rcx
0x180001ad9  jz      short loc_180001AEA
0x180001adb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001adf  inc     rax
0x180001ae2  cmp     byte ptr [rcx+rax], 0
0x180001ae6  jnz     short loc_180001ADF
0x180001ae8  jmp     short loc_180001AEC
0x180001aea  xor     eax, eax
0x180001aec  mov     r12, [rbp+57h+var_88]
0x180001af0  mov     dword ptr [rbp+57h+var_50], eax
0x180001af3  test    eax, eax
0x180001af5  jz      loc_180001B8D
0x180001afb  lea     r8, [rbp+57h+var_50]
0x180001aff  mov     edx, esi
0x180001b01  mov     rcx, r12
0x180001b04  call    _FindHpkpDomainEntry
0x180001b09  test    rax, rax
0x180001b0c  jz      short loc_180001B1F
0x180001b0e  mov     rdx, rbx
0x180001b11  mov     rcx, rax
0x180001b14  call    _UpdateHpkpDomainEntryFromPendingEntry
0x180001b19  test    eax, eax
0x180001b1b  jnz     short loc_180001B86
0x180001b1d  jmp     short loc_180001B8D
0x180001b1f  cmp     esi, r13d
0x180001b22  jnb     short loc_180001B95
0x180001b24  movups  xmm0, [rbp+57h+var_50]
0x180001b28  mov     r8d, esi
0x180001b2b  xorps   xmm1, xmm1
0x180001b2e  lea     rdx, [r8+r8*4]
0x180001b32  shl     rdx, 5
0x180001b36  add     rdx, [rbp+57h+hMem]
0x180001b3a  inc     esi
0x180001b3c  mov     [rbp+57h+var_80], esi
0x180001b3f  movdqu  xmmword ptr [rdx], xmm0
0x180001b43  movups  xmmword ptr [rdx+10h], xmm1
0x180001b47  movups  xmmword ptr [rdx+20h], xmm1
0x180001b4b  movups  xmmword ptr [rdx+30h], xmm1
0x180001b4f  mov     rax, [rbx+8]
0x180001b53  mov     [rdx+10h], rax
0x180001b57  mov     rax, [rbx+10h]
0x180001b5b  mov     [rdx+18h], rax
0x180001b5f  mov     eax, [rbx+18h]
0x180001b62  mov     [rdx+20h], eax
0x180001b65  mov     rax, [rbx+28h]
0x180001b69  mov     ecx, [rax+8]
0x180001b6c  mov     [rdx+24h], ecx
0x180001b6f  mov     rax, [rbx+28h]
0x180001b73  mov     ecx, [rax+0Ch]
0x180001b76  mov     [rdx+28h], ecx
0x180001b79  movups  xmm0, xmmword ptr [rbx+30h]
0x180001b7d  movdqu  xmmword ptr [rdx+30h], xmm0
0x180001b82  mov     [r12+r8*8], rdx
0x180001b86  mov     [rbp+57h+arg_8], 1
0x180001b8d  mov     rbx, [rbx]
0x180001b90  jmp     loc_180001A4D
0x180001b95  mov     ecx, 8000FFFFh; dwErrCode
0x180001b9a  call    cs:__imp_SetLastError
0x180001ba0  jmp     short loc_180001BE2
0x180001ba2  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x180001ba6  mov     r8, r15
0x180001ba9  lea     r9, [rbp+57h+arg_18]
0x180001bad  mov     [rsp+0C0h+lpFileTime2], rax; lpFileTime2
0x180001bb2  lea     rdx, [rbp+57h+var_80]
0x180001bb6  mov     rcx, r12; Base
0x180001bb9  call    _RemoveExpiredOrNotInUseHpkpEntry
0x180001bbe  test    eax, eax
0x180001bc0  jnz     short loc_180001BC7
0x180001bc2  cmp     [rbp+57h+arg_8], eax
0x180001bc5  jz      short loc_180001BE2
0x180001bc7  mov     r9d, [rbp+57h+arg_18]
0x180001bcb  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x180001bcf  mov     edx, [rbp+57h+var_80]
0x180001bd2  mov     r8, r15
0x180001bd5  mov     rcx, r12
0x180001bd8  mov     [rsp+0C0h+lpFileTime2], rax
0x180001bdd  call    _EncodeAndSetHpkpCtls
0x180001be2  test    r14, r14
0x180001be5  jz      short loc_180001C10
0x180001be7  mov     edi, [rbp+57h+var_90]
0x180001bea  xor     ebx, ebx
0x180001bec  test    edi, edi
0x180001bee  jz      short loc_180001C08
0x180001bf0  mov     esi, [rbp+57h+var_78]
0x180001bf3  lea     ecx, [rbx+rsi]
0x180001bf6  add     rcx, rcx
0x180001bf9  mov     rcx, [r14+rcx*8]; hMem
0x180001bfd  call    PkiFree
0x180001c02  inc     ebx
0x180001c04  cmp     ebx, edi
0x180001c06  jb      short loc_180001BF3
0x180001c08  mov     rcx, r14; hMem
0x180001c0b  call    PkiFree
0x180001c10  mov     rbx, [rbp+57h+var_88]
0x180001c14  mov     rcx, [rbp+57h+hMem]; hMem
0x180001c18  call    PkiFree
0x180001c1d  mov     rcx, rbx; hMem
0x180001c20  call    PkiFree
0x180001c25  mov     rcx, r15; hMem
0x180001c28  call    PkiFree
0x180001c2d  mov     rax, [rbp+57h+pCtlContext]
0x180001c31  test    rax, rax
0x180001c34  jz      short loc_180001C3F
0x180001c36  mov     rcx, rax; pCtlContext
0x180001c39  call    cs:__imp_CertFreeCTLContext
0x180001c3f  mov     rax, [rbp+57h+var_60]
0x180001c43  test    rax, rax
0x180001c46  jz      short loc_180001C51
0x180001c48  mov     rcx, rax; pCtlContext
0x180001c4b  call    cs:__imp_CertFreeCTLContext
0x180001c51  call    FreePendingHpkp
0x180001c56  mov     rcx, [rbp+57h+arg_0]
0x180001c5a  call    FreeUpdateHpkpJob
0x180001c5f  mov     rcx, cs:g_hTestHpkpEvent; hEvent
0x180001c66  mov     cs:qword_180020400, 0
0x180001c71  test    rcx, rcx
0x180001c74  jz      short loc_180001C7C
0x180001c76  call    cs:__imp_SetEvent
0x180001c7c  add     rsp, 88h
0x180001c83  pop     r15
0x180001c85  pop     r14
0x180001c87  pop     r13
0x180001c89  pop     r12
0x180001c8b  pop     rdi
0x180001c8c  pop     rsi
0x180001c8d  pop     rbx
  ... truncated ...
```
