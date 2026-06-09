# ReadyToRunInfo::TryLookupTypeTokenFromName(NameHandle *,uint *)

- ea: `0x1800a027c`
- end: `0x1800a073b`
- name: `?TryLookupTypeTokenFromName@ReadyToRunInfo@@QEAAHPEAVNameHandle@@PEAI@Z`
- size: `1215`
- prototype: `__int64 __fastcall(ReadyToRunInfo *__hidden this, struct NameHandle *, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180094a48`

## callees

- `0x18000cdac`
- `0x1800210f0`
- `0x18002127c`
- `0x180066ed0`
- `0x180072918`
- `0x180072d4c`
- `0x1800a027c`
- `0x1800a073c`
- `0x1800a07e4`
- `0x1800a08d4`
- `0x1800a0ac8`
- `0x1800a0cc0`
- `0x1800a33bc`
- `0x1800f0d20`
- `0x1800f21d0`
- `0x1800f5910`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800a03be`
- `KERNEL32!HeapFree` at `0x1800a0456`
- `KERNEL32!HeapFree` at `0x1800a03be`
- `KERNEL32!HeapFree` at `0x1800a0456`
- `KERNEL32!GetProcessHeap` at `0x1800a03a9`
- `KERNEL32!GetProcessHeap` at `0x1800a0441`
- `KERNEL32!GetProcessHeap` at `0x1800a03a9`
- `KERNEL32!GetProcessHeap` at `0x1800a0441`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadyToRunInfo::TryLookupTypeTokenFromName(
        ReadyToRunInfo *this,
        struct NameHandle *a2,
        unsigned int *a3)
{
  unsigned __int64 *v4; // rbx
  char *v5; // r13
  int v6; // edi
  const char *v7; // r12
  const char *v8; // r14
  unsigned __int64 v9; // rcx
  __int64 *v10; // rax
  struct IMDInternalImport *v11; // rax
  unsigned int v12; // edi
  int v13; // r15d
  char *Sep; // rax
  char *v15; // rdi
  size_t v16; // rbx
  char *v17; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  char v20; // al
  int v21; // r9d
  int v22; // r8d
  __int64 v23; // rdx
  int v24; // edx
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  char v28; // al
  int v29; // r8d
  __int64 v30; // r9
  unsigned int v31; // ebx
  struct IMDInternalImport *MDImport; // rax
  NativeFormat::NativeReader *v33; // rax
  unsigned int v34; // r15d
  __int64 *v35; // rdi
  __int64 *v36; // rbx
  struct IMDInternalImport *v37; // rdi
  struct IMDInternalImport *v38; // rax
  ReadyToRunInfo *v39; // rcx
  __int64 *v40; // rax
  struct IMDInternalImport *v41; // rax
  ReadyToRunInfo *v42; // rcx
  int v43; // ebx
  unsigned __int64 *v44; // rdi
  __int64 *v45; // rax
  struct IMDInternalImport *v46; // rax
  ReadyToRunInfo *v47; // rcx
  __int64 *v48; // rax
  struct IMDInternalImport *v49; // rbx
  struct IMDInternalImport *v50; // rax
  ReadyToRunInfo *v51; // rcx
  unsigned int v52; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 *v53; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v54; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-B8h]
  unsigned int v56; // [rsp+50h] [rbp-B0h] BYREF
  char *v57[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *Str2; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v59; // [rsp+70h] [rbp-90h]
  __int128 v60; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v61; // [rsp+88h] [rbp-78h]
  char v62; // [rsp+8Ch] [rbp-74h]
  LPVOID lpMem[68]; // [rsp+90h] [rbp-70h] BYREF

  v59 = a3;
  v4 = (unsigned __int64 *)this;
  v53 = (unsigned __int64 *)this;
  v5 = (char *)this + 120;
  v6 = 0;
  if ( !*((_QWORD *)this + 15) )
    return 0;
  v7 = 0;
  v8 = 0;
  v52 = 0;
  if ( *((_DWORD *)a2 + 6) == 1912602624 || (v9 = *((_QWORD *)a2 + 2)) == 0 )
  {
    v7 = (const char *)*((_QWORD *)a2 + 1);
    v8 = byte_180134FF8;
    v13 = 1839446340;
    if ( *(_QWORD *)a2 )
    {
      v8 = *(const char **)a2;
    }
    else
    {
      lpMem[0] = 0;
      lpMem[1] = 0;
      lpMem[2] = (LPVOID)512;
      Sep = ns::FindSep(v7);
      v15 = Sep;
      if ( Sep )
      {
        v16 = Sep - v7;
        v17 = (char *)CQuickMemoryBase<512,128>::AllocNoThrow(lpMem, Sep - v7 + 1);
        v8 = v17;
        if ( !v17 )
        {
          v25 = lpMem[0];
          if ( lpMem[0] )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v25);
            lpMem[0] = 0;
          }
          return 0;
        }
        memmove(v17, v7, v16);
        v8[v16] = 0;
        v7 = v15 + 1;
      }
      v18 = lpMem[0];
      v6 = 0;
      if ( lpMem[0] )
      {
        v19 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v19 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v19;
        }
        HeapFree(v19, 0, v18);
        lpMem[0] = 0;
      }
      if ( !v8 )
        goto LABEL_26;
    }
    v20 = *v8;
    if ( *v8 )
    {
      v21 = 1839446340;
      v22 = 0;
      LODWORD(v23) = 0;
      do
      {
        v21 = v20 ^ (__ROL4__(v21, 5) + v21);
        if ( !v8[(unsigned int)(v23 + 1)] )
          break;
        v22 = v8[(unsigned int)(v23 + 1)] ^ (__ROL4__(v22, 5) + v22);
        v23 = (unsigned int)(v23 + 2);
        v20 = v8[v23];
      }
      while ( v20 );
      v24 = (v21 + __ROL4__(v21, 8)) ^ (v22 + __ROL4__(v22, 8));
      goto LABEL_27;
    }
LABEL_26:
    v24 = 0;
LABEL_27:
    if ( v7 )
    {
      v28 = *v7;
      if ( *v7 )
      {
        v29 = 0;
        LODWORD(v30) = 0;
        do
        {
          v13 = v28 ^ (__ROL4__(v13, 5) + v13);
          if ( !v7[(unsigned int)(v30 + 1)] )
            break;
          v29 = v7[(unsigned int)(v30 + 1)] ^ (__ROL4__(v29, 5) + v29);
          v30 = (unsigned int)(v30 + 2);
          v28 = v7[v30];
        }
        while ( v28 );
        v6 = (v13 + __ROL4__(v13, 8)) ^ (v29 + __ROL4__(v29, 8));
      }
    }
    v12 = v24 ^ v6;
    if ( *((_DWORD *)a2 + 10) )
    {
      v31 = *((_DWORD *)a2 + 14);
      MDImport = Module::GetMDImport(*((Module **)a2 + 8));
      if ( !GetVersionResilientTypeHashCode(MDImport, v31, (int *)&v52) )
        return 0;
      v12 ^= v52;
    }
    v4 = v53;
    goto LABEL_37;
  }
  v10 = DacInstantiateClassByVTable(v9, 1576, 1);
  v11 = Module::GetMDImport((Module *)v10);
  if ( !GetVersionResilientTypeHashCode(v11, *((_DWORD *)a2 + 6), (int *)&v52) )
    return 0;
  v12 = v52;
LABEL_37:
  NativeFormat::NativeHashtable::GetParserForBucket(v5, &v54, (v12 >> 8) & *((_DWORD *)v5 + 3), &v52);
  v57[0] = (char *)v54;
  LODWORD(v57[1]) = v55;
  v60 = *(_OWORD *)v57;
  v61 = v52;
  v62 = v12;
  v54 = 0;
  v55 = 0;
  while ( NativeFormat::NativeHashtable::Enumerator::GetNext(
            (NativeFormat::NativeHashtable::Enumerator *)&v60,
            (struct NativeFormat::NativeParser *)&v54) )
  {
    v33 = (NativeFormat::NativeReader *)DacInstantiateTypeByAddressHelper(v54, 0x10u, 1, 1);
    v55 = NativeFormat::NativeReader::DecodeUnsigned(v33, v55, &v52);
    v34 = (v52 | 0x4000000) >> 1;
    if ( (v52 & 1) != 0 )
      v34 = (v52 | 0x4E000000) >> 1;
    if ( *((_DWORD *)a2 + 6) == 1912602624 || !*((_QWORD *)a2 + 2) )
    {
      v40 = DacInstantiateClassByVTable(*v4, 1576, 1);
      v41 = Module::GetMDImport((Module *)v40);
      if ( (unsigned int)ReadyToRunInfo::GetTypeNameFromToken(v42, v41, v34, (const char **)&Str2, (const char **)v57)
        && !strcmp(v7, Str2)
        && !strcmp(v8, v57[0]) )
      {
        v43 = *((_DWORD *)a2 + 10);
        v44 = v53;
        v45 = DacInstantiateClassByVTable(*v53, 1576, 1);
        v46 = Module::GetMDImport((Module *)v45);
        if ( (v43 != 0) == (unsigned int)ReadyToRunInfo::GetEnclosingToken(v47, v46, v34, &v56) )
        {
          if ( !v43
            || (v48 = DacInstantiateClassByVTable(*v44, 1576, 1),
                v49 = Module::GetMDImport((Module *)v48),
                v50 = Module::GetMDImport(*((Module **)a2 + 8)),
                ReadyToRunInfo::CompareTypeNameOfTokens(v51, *((_DWORD *)a2 + 14), v50, v56, v49)) )
          {
LABEL_52:
            *v59 = v34;
            return 1;
          }
        }
        v4 = v44;
      }
    }
    else
    {
      v35 = DacInstantiateClassByVTable(*v4, 1576, 1);
      v36 = DacInstantiateClassByVTable(*((_QWORD *)a2 + 2), 1576, 1);
      v37 = Module::GetMDImport((Module *)v35);
      v38 = Module::GetMDImport((Module *)v36);
      if ( ReadyToRunInfo::CompareTypeNameOfTokens(v39, *((_DWORD *)a2 + 6), v38, v34, v37) )
        goto LABEL_52;
      v4 = v53;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a027c  mov     [rsp-8+arg_18], rbx
0x1800a0281  push    rbp
0x1800a0282  push    rsi
0x1800a0283  push    rdi
0x1800a0284  push    r12
0x1800a0286  push    r13
0x1800a0288  push    r14
0x1800a028a  push    r15
0x1800a028c  lea     rbp, [rsp-1C0h]
0x1800a0294  sub     rsp, 2C0h
0x1800a029b  mov     rax, cs:__security_cookie
0x1800a02a2  xor     rax, rsp
0x1800a02a5  mov     [rbp+1F0h+var_40], rax
0x1800a02ac  mov     [rsp+2F0h+var_280], r8
0x1800a02b1  mov     rsi, rdx
0x1800a02b4  mov     rbx, rcx
0x1800a02b7  mov     [rsp+2F0h+var_2B8], rcx
0x1800a02bc  lea     r13, [rcx+78h]
0x1800a02c0  xor     edi, edi
0x1800a02c2  cmp     [r13+0], rdi
0x1800a02c6  jz      loc_1800A0461
0x1800a02cc  mov     r12d, edi
0x1800a02cf  mov     r14d, edi
0x1800a02d2  mov     [rsp+2F0h+var_2C0], edi
0x1800a02d6  cmp     dword ptr [rdx+18h], 72000000h
0x1800a02dd  jz      short loc_1800A031E
0x1800a02df  mov     rcx, [rdx+10h]; unsigned __int64
0x1800a02e3  test    rcx, rcx
0x1800a02e6  jz      short loc_1800A031E
0x1800a02e8  mov     r8b, 1
0x1800a02eb  mov     edx, 628h
0x1800a02f0  call    DacInstantiateClassByVTable
0x1800a02f5  mov     rcx, rax; this
0x1800a02f8  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x1800a02fd  mov     rcx, rax; struct IMDInternalImport *
0x1800a0300  lea     r8, [rsp+2F0h+var_2C0]; int *
0x1800a0305  mov     edx, [rsi+18h]; unsigned int
0x1800a0308  call    ?GetVersionResilientTypeHashCode@@YA_NPEAUIMDInternalImport@@IPEAH@Z; GetVersionResilientTypeHashCode(IMDInternalImport *,uint,int *)
0x1800a030d  test    al, al
0x1800a030f  jz      loc_1800A0461
0x1800a0315  mov     edi, [rsp+2F0h+var_2C0]
0x1800a0319  jmp     loc_1800A051E
0x1800a031e  mov     r12, [rdx+8]
0x1800a0322  lea     r14, byte_180134FF8
0x1800a0329  mov     r15d, 6DA3B944h
0x1800a032f  cmp     [rdx], rdi
0x1800a0332  jz      short loc_1800A033C
0x1800a0334  mov     r14, [rdx]
0x1800a0337  jmp     loc_1800A03D1
0x1800a033c  mov     [rbp+1F0h+lpMem], rdi
0x1800a0340  mov     [rbp+1F0h+var_258], rdi
0x1800a0344  mov     [rbp+1F0h+var_250], 200h
0x1800a034c  mov     rcx, r12; char *
0x1800a034f  call    ?FindSep@ns@@SAPEADPEBD@Z; ns::FindSep(char const *)
0x1800a0354  mov     rdi, rax
0x1800a0357  test    rax, rax
0x1800a035a  jz      short loc_1800A0392
0x1800a035c  mov     rbx, rax
0x1800a035f  sub     rbx, r12
0x1800a0362  lea     rdx, [rbx+1]
0x1800a0366  lea     rcx, [rbp+1F0h+lpMem]
0x1800a036a  call    ?AllocNoThrow@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAPEAX_K@Z; CQuickMemoryBase<512,128>::AllocNoThrow(unsigned __int64)
0x1800a036f  mov     r14, rax
0x1800a0372  test    rax, rax
0x1800a0375  jz      loc_1800A042C
0x1800a037b  mov     r8, rbx; Size
0x1800a037e  mov     rdx, r12; Src
0x1800a0381  mov     rcx, rax; void *
0x1800a0384  call    memmove
0x1800a0389  mov     byte ptr [r14+rbx], 0
0x1800a038e  lea     r12, [rdi+1]
0x1800a0392  mov     rbx, [rbp+1F0h+lpMem]
0x1800a0396  xor     edi, edi
0x1800a0398  test    rbx, rbx
0x1800a039b  jz      short loc_1800A03C8
0x1800a039d  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a03a4  test    rax, rax
0x1800a03a7  jnz     short loc_1800A03B6
0x1800a03a9  call    cs:__imp_GetProcessHeap
0x1800a03af  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a03b6  mov     r8, rbx; lpMem
0x1800a03b9  xor     edx, edx; dwFlags
0x1800a03bb  mov     rcx, rax; hHeap
0x1800a03be  call    cs:__imp_HeapFree
0x1800a03c4  mov     [rbp+1F0h+lpMem], rdi
0x1800a03c8  test    r14, r14
0x1800a03cb  jz      loc_1800A048D
0x1800a03d1  mov     al, [r14]
0x1800a03d4  test    al, al
0x1800a03d6  jz      loc_1800A048D
0x1800a03dc  mov     r9d, r15d
0x1800a03df  mov     r8d, edi
0x1800a03e2  mov     edx, edi
0x1800a03e4  mov     ecx, r9d
0x1800a03e7  rol     ecx, 5
0x1800a03ea  add     r9d, ecx
0x1800a03ed  movsx   eax, al
0x1800a03f0  xor     r9d, eax
0x1800a03f3  lea     eax, [rdx+1]
0x1800a03f6  movsx   eax, byte ptr [rax+r14]
0x1800a03fb  test    al, al
0x1800a03fd  jz      short loc_1800A0416
0x1800a03ff  mov     ecx, r8d
0x1800a0402  rol     ecx, 5
0x1800a0405  add     r8d, ecx
0x1800a0408  xor     r8d, eax
0x1800a040b  add     edx, 2
0x1800a040e  mov     al, [rdx+r14]
0x1800a0412  test    al, al
0x1800a0414  jnz     short loc_1800A03E4
0x1800a0416  mov     edx, r8d
0x1800a0419  rol     edx, 8
0x1800a041c  add     edx, r8d
0x1800a041f  mov     eax, r9d
0x1800a0422  rol     eax, 8
0x1800a0425  add     eax, r9d
0x1800a0428  xor     edx, eax
0x1800a042a  jmp     short loc_1800A048F
0x1800a042c  mov     rbx, [rbp+1F0h+lpMem]
0x1800a0430  test    rbx, rbx
0x1800a0433  jz      short loc_1800A0461
0x1800a0435  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a043c  test    rax, rax
0x1800a043f  jnz     short loc_1800A044E
0x1800a0441  call    cs:__imp_GetProcessHeap
0x1800a0447  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a044e  mov     r8, rbx; lpMem
0x1800a0451  xor     edx, edx; dwFlags
0x1800a0453  mov     rcx, rax; hHeap
0x1800a0456  call    cs:__imp_HeapFree
0x1800a045c  and     [rbp+1F0h+lpMem], 0
0x1800a0461  xor     eax, eax
0x1800a0463  mov     rcx, [rbp+1F0h+var_40]
0x1800a046a  xor     rcx, rsp; StackCookie
0x1800a046d  call    __security_check_cookie
0x1800a0472  mov     rbx, [rsp+2F0h+arg_18]
0x1800a047a  add     rsp, 2C0h
0x1800a0481  pop     r15
0x1800a0483  pop     r14
0x1800a0485  pop     r13
0x1800a0487  pop     r12
0x1800a0489  pop     rdi
0x1800a048a  pop     rsi
0x1800a048b  pop     rbp
0x1800a048c  retn
0x1800a048d  mov     edx, edi
0x1800a048f  test    r12, r12
0x1800a0492  jz      short loc_1800A04EA
0x1800a0494  mov     al, [r12]
0x1800a0498  test    al, al
0x1800a049a  jz      short loc_1800A04EA
0x1800a049c  mov     r8d, edi
0x1800a049f  mov     r9d, edi
0x1800a04a2  mov     ecx, r15d
0x1800a04a5  rol     ecx, 5
0x1800a04a8  add     r15d, ecx
0x1800a04ab  movsx   eax, al
0x1800a04ae  xor     r15d, eax
0x1800a04b1  lea     eax, [r9+1]
0x1800a04b5  movsx   eax, byte ptr [rax+r12]
0x1800a04ba  test    al, al
0x1800a04bc  jz      short loc_1800A04D6
0x1800a04be  mov     ecx, r8d
0x1800a04c1  rol     ecx, 5
0x1800a04c4  add     r8d, ecx
0x1800a04c7  xor     r8d, eax
0x1800a04ca  add     r9d, 2
0x1800a04ce  mov     al, [r9+r12]
0x1800a04d2  test    al, al
0x1800a04d4  jnz     short loc_1800A04A2
0x1800a04d6  mov     edi, r8d
0x1800a04d9  rol     edi, 8
0x1800a04dc  add     edi, r8d
0x1800a04df  mov     eax, r15d
0x1800a04e2  rol     eax, 8
0x1800a04e5  add     eax, r15d
0x1800a04e8  xor     edi, eax
0x1800a04ea  xor     edi, edx
0x1800a04ec  cmp     dword ptr [rsi+28h], 0
0x1800a04f0  jz      short loc_1800A0519
0x1800a04f2  mov     ebx, [rsi+38h]
0x1800a04f5  mov     rcx, [rsi+40h]; this
0x1800a04f9  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x1800a04fe  mov     rcx, rax; struct IMDInternalImport *
0x1800a0501  lea     r8, [rsp+2F0h+var_2C0]; int *
0x1800a0506  mov     edx, ebx; unsigned int
0x1800a0508  call    ?GetVersionResilientTypeHashCode@@YA_NPEAUIMDInternalImport@@IPEAH@Z; GetVersionResilientTypeHashCode(IMDInternalImport *,uint,int *)
0x1800a050d  test    al, al
0x1800a050f  jz      loc_1800A0461
0x1800a0515  xor     edi, [rsp+2F0h+var_2C0]
0x1800a0519  mov     rbx, [rsp+2F0h+var_2B8]
0x1800a051e  mov     eax, edi
0x1800a0520  shr     eax, 8
0x1800a0523  mov     r8d, [r13+0Ch]
0x1800a0527  and     r8d, eax
0x1800a052a  lea     r9, [rsp+2F0h+var_2C0]
0x1800a052f  lea     rdx, [rsp+2F0h+var_2B0]
0x1800a0534  mov     rcx, r13
0x1800a0537  call    ?GetParserForBucket@NativeHashtable@NativeFormat@@AEAA?AVNativeParser@2@IPEAI@Z; NativeFormat::NativeHashtable::GetParserForBucket(uint,uint *)
0x1800a053c  mov     rax, [rsp+2F0h+var_2B0]
0x1800a0541  mov     [rsp+2F0h+var_298], rax
0x1800a0546  mov     eax, [rsp+2F0h+var_2A8]
0x1800a054a  mov     dword ptr [rsp+2F0h+var_298+8], eax
0x1800a054e  movups  xmm0, xmmword ptr [rsp+2F0h+var_298]
0x1800a0553  movdqu  [rsp+2F0h+var_278], xmm0
0x1800a0559  mov     eax, [rsp+2F0h+var_2C0]
0x1800a055d  mov     [rbp+1F0h+var_268], eax
0x1800a0560  mov     [rbp+1F0h+var_264], dil
0x1800a0564  xor     r13d, r13d
0x1800a0567  mov     [rsp+2F0h+var_2B0], r13
0x1800a056c  mov     [rsp+2F0h+var_2A8], r13d
0x1800a0571  lea     rdx, [rsp+2F0h+var_2B0]; struct NativeFormat::NativeParser *
0x1800a0576  lea     rcx, [rsp+2F0h+var_278]; this
0x1800a057b  call    ?GetNext@Enumerator@NativeHashtable@NativeFormat@@QEAA_NAEAVNativeParser@3@@Z; NativeFormat::NativeHashtable::Enumerator::GetNext(NativeFormat::NativeParser &)
0x1800a0580  test    al, al
0x1800a0582  jz      loc_1800A0461
0x1800a0588  mov     r9b, 1; bool
0x1800a058b  mov     r8b, r9b; bool
0x1800a058e  mov     edx, 10h; unsigned int
0x1800a0593  mov     rcx, [rsp+2F0h+var_2B0]; unsigned __int64
0x1800a0598  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800a059d  lea     r8, [rsp+2F0h+var_2C0]; unsigned int *
0x1800a05a2  mov     edx, [rsp+2F0h+var_2A8]; unsigned int
0x1800a05a6  mov     rcx, rax; this
0x1800a05a9  call    ?DecodeUnsigned@NativeReader@NativeFormat@@QEAAIIPEAI@Z; NativeFormat::NativeReader::DecodeUnsigned(uint,uint *)
0x1800a05ae  mov     [rsp+2F0h+var_2A8], eax
0x1800a05b2  mov     r15d, [rsp+2F0h+var_2C0]
0x1800a05b7  mov     ecx, r15d
0x1800a05ba  mov     eax, r15d
0x1800a05bd  or      eax, 4E000000h
0x1800a05c2  shr     eax, 1
0x1800a05c4  bts     r15d, 1Ah
0x1800a05c9  shr     r15d, 1
0x1800a05cc  and     cl, 1
0x1800a05cf  cmovnz  r15d, eax
0x1800a05d3  cmp     dword ptr [rsi+18h], 72000000h
0x1800a05da  jz      short loc_1800A0641
0x1800a05dc  cmp     [rsi+10h], r13
0x1800a05e0  jz      short loc_1800A0641
0x1800a05e2  mov     r8b, 1
0x1800a05e5  mov     edx, 628h
0x1800a05ea  mov     rcx, [rbx]; unsigned __int64
0x1800a05ed  call    DacInstantiateClassByVTable
0x1800a05f2  mov     rdi, rax
0x1800a05f5  mov     r8b, 1
0x1800a05f8  mov     edx, 628h
0x1800a05fd  mov     rcx, [rsi+10h]; unsigned __int64
0x1800a0601  call    DacInstantiateClassByVTable
0x1800a0606  mov     rbx, rax
0x1800a0609  mov     rcx, rdi; this
0x1800a060c  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x1800a0611  mov     rdi, rax
0x1800a0614  mov     rcx, rbx; this
0x1800a0617  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x1800a061c  mov     r8, rax; struct IMDInternalImport *
0x1800a061f  mov     [rsp+2F0h+var_2D0], rdi; struct IMDInternalImport *
0x1800a0624  mov     r9d, r15d; unsigned int
0x1800a0627  mov     edx, [rsi+18h]; unsigned int
0x1800a062a  call    ?CompareTypeNameOfTokens@ReadyToRunInfo@@AEAAHIPEAUIMDInternalImport@@I0@Z; ReadyToRunInfo::CompareTypeNameOfTokens(uint,IMDInternalImport *,uint,IMDInternalImport *)
0x1800a062f  test    eax, eax
0x1800a0631  jnz     loc_1800A0729
0x1800a0637  mov     rbx, [rsp+2F0h+var_2B8]
0x1800a063c  jmp     loc_1800A0571
0x1800a0641  mov     r8b, 1
0x1800a0644  mov     edi, 628h
0x1800a0649  mov     edx, edi
0x1800a064b  mov     rcx, [rbx]; unsigned __int64
0x1800a064e  call    DacInstantiateClassByVTable
0x1800a0653  mov     rcx, rax; this
0x1800a0656  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x1800a065b  mov     rdx, rax; struct IMDInternalImport *
0x1800a065e  lea     rax, [rsp+2F0h+var_298]
0x1800a0663  mov     [rsp+2F0h+var_2D0], rax; char **
0x1800a0668  lea     r9, [rsp+2F0h+Str2]; char **
0x1800a066d  mov     r8d, r15d; unsigned int
0x1800a0670  call    ?GetTypeNameFromToken@ReadyToRunInfo@@AEAAHPEAUIMDInternalImport@@IPEAPEBD1@Z; ReadyToRunInfo::GetTypeNameFromToken(IMDInternalImport *,uint,char const * *,char const * *)
0x1800a0675  test    eax, eax
0x1800a0677  jz      loc_1800A0571
0x1800a067d  mov     rdx, [rsp+2F0h+Str2]; Str2
0x1800a0682  mov     rcx, r12; Str1
0x1800a0685  call    strcmp
0x1800a068a  test    eax, eax
0x1800a068c  jnz     loc_1800A0571
0x1800a0692  mov     rdx, [rsp+2F0h+var_298]; Str2
0x1800a0697  mov     rcx, r14; Str1
0x1800a069a  call    strcmp
0x1800a069f  test    eax, eax
0x1800a06a1  jnz     loc_1800A0571
0x1800a06a7  mov     ebx, [rsi+28h]
0x1800a06aa  mov     r8b, 1
0x1800a06ad  mov     edx, edi
0x1800a06af  mov     rdi, [rsp+2F0h+var_2B8]
0x1800a06b4  mov     rcx, [rdi]; unsigned __int64
0x1800a06b7  call    DacInstantiateClassByVTable
0x1800a06bc  mov     rcx, rax; this
0x1800a06bf  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x1800a06c4  mov     rdx, rax; struct IMDInternalImport *
0x1800a06c7  lea     r9, [rsp+2F0h+var_2A0]; unsigned int *
0x1800a06cc  mov     r8d, r15d; unsigned int
0x1800a06cf  call    ?GetEnclosingToken@ReadyToRunInfo@@AEAAHPEAUIMDInternalImport@@IPEAI@Z; ReadyToRunInfo::GetEnclosingToken(IMDInternalImport *,uint,uint *)
  ... truncated ...
```
