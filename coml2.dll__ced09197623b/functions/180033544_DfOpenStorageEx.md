# DfOpenStorageEx

- ea: `0x180033544`
- end: `0x180033809`
- name: `DfOpenStorageEx`
- size: `709`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int@<edx>, unsigned int@<r8d>, int, __int64, __int64, struct _GUID *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033280`
- `0x180039ef0`

## callees

- `0x18001f7e0`
- `0x180026bc4`
- `0x180033544`
- `0x180033810`
- `0x180039a04`
- `0x180042800`
- `0x180053d30`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x1800335ce`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x1800335ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003366f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003366f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800337ba`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800337ba`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180033665`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180033665`

## pseudocode

```c
__int64 __fastcall DfOpenStorageEx(
        unsigned __int16 *a1,
        int a2,
        unsigned int a3,
        int a4,
        int a5,
        __int64 a6,
        void *a7,
        struct _GUID *a8,
        void **a9)
{
  int v13; // edi
  int IsNffAppropriate; // eax
  int v15; // ebx
  unsigned __int16 *v16; // rax
  DWORD FullPathNameW; // eax
  DWORD LastError; // eax
  __int64 v20; // rax
  struct IStorage *v21; // rbx
  struct IStorage *ReservedForOle; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  void *v25; // [rsp+50h] [rbp-B0h]
  void **v26; // [rsp+58h] [rbp-A8h]
  LPWSTR FilePart; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v25 = a7;
  FilePart = 0;
  v26 = a9;
  ReservedForOle = (struct IStorage *)NtCurrentTeb()->ReservedForOle;
  if ( !ReservedForOle )
  {
    v13 = InternalTlsAllocData(&ReservedForOle);
    if ( v13 < 0 )
      return (unsigned int)v13;
  }
  if ( a4 != 4 )
  {
    if ( !a4 )
      goto LABEL_8;
    if ( a4 == 5 )
      goto LABEL_21;
    goto LABEL_14;
  }
  if ( a2 )
    return (unsigned int)-2147286953;
  IsNffAppropriate = CNtfsStorage::IsNffAppropriate(a1);
  v13 = IsNffAppropriate;
  if ( IsNffAppropriate >= 0 )
  {
    a4 = 3;
LABEL_14:
    FullPathNameW = GetFullPathNameW(a1, 0x104u, Buffer, &FilePart);
    if ( !FullPathNameW )
    {
      LastError = GetLastError();
      if ( !LastError )
        return (unsigned int)-2147286788;
      return (unsigned int)Win32ErrorToScode(LastError);
    }
    if ( FullPathNameW > 0x104 )
      return (unsigned int)-2147287037;
LABEL_21:
    if ( a4 != 5 )
    {
      if ( a4 == 3 )
        return (unsigned int)NFFOpen(Buffer, a3, a3, a2, v25, a8, v26);
      return (unsigned int)-2147286953;
    }
    goto LABEL_8;
  }
  if ( IsNffAppropriate != -2147287039 )
    return (unsigned int)v13;
LABEL_8:
  v15 = 0;
  ReservedForOle = 0;
  LODWORD(v24) = 0;
  if ( !a2 )
  {
    v13 = DfOpenDocfile(a1, 0, a3, 0, v25, (__int64)&v24, a5, &ReservedForOle);
    if ( v13 < 0 )
      return (unsigned int)v13;
    v15 = v24;
    goto LABEL_29;
  }
  v16 = 0;
  if ( (a5 & 0x100) == 0 )
    v16 = a1;
  a1 = v16;
  v13 = DfCreateDocfile(v16, a3, a5, &ReservedForOle);
  if ( v13 >= 0 )
  {
LABEL_29:
    v20 = *(_QWORD *)&IID_IStorage.Data1 - *(_QWORD *)&a8->Data1;
    if ( *(_QWORD *)&IID_IStorage.Data1 == *(_QWORD *)&a8->Data1 )
      v20 = *(_QWORD *)IID_IStorage.Data4 - *(_QWORD *)a8->Data4;
    if ( v20 )
    {
      v21 = ReservedForOle;
      v13 = ((__int64 (__fastcall *)(struct IStorage *, struct _GUID *, void **))ReservedForOle->lpVtbl->QueryInterface)(
              ReservedForOle,
              a8,
              v26);
      ((void (__fastcall *)(struct IStorage *))v21->lpVtbl->Release)(v21);
      if ( a2 && v13 < 0 && a1 )
        DeleteFileW(a1);
    }
    else
    {
      *v26 = ReservedForOle;
      if ( a6 && !a2 )
        *(_DWORD *)(a6 + 4) = v15;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180033544  mov     [rsp-8+arg_8], rbx
0x180033549  push    rbp
0x18003354a  push    rsi
0x18003354b  push    rdi
0x18003354c  push    r12
0x18003354e  push    r13
0x180033550  push    r14
0x180033552  push    r15
0x180033554  lea     rbp, [rsp-190h]
0x18003355c  sub     rsp, 290h
0x180033563  mov     rax, cs:__security_cookie
0x18003356a  xor     rax, rsp
0x18003356d  mov     [rbp+1C0h+var_40], rax
0x180033574  mov     rax, [rbp+1C0h+arg_30]
0x18003357b  mov     rsi, rcx
0x18003357e  mov     r15, [rbp+1C0h+arg_28]
0x180033585  mov     ebx, r9d
0x180033588  mov     r12, [rbp+1C0h+arg_38]
0x18003358f  mov     r13d, r8d
0x180033592  mov     [rsp+2C0h+var_270], rax
0x180033597  mov     r14d, edx
0x18003359a  mov     rax, [rbp+1C0h+arg_40]
0x1800335a1  mov     [rsp+2C0h+FilePart], 0
0x1800335aa  mov     [rsp+2C0h+var_268], rax
0x1800335af  mov     rax, gs:30h
0x1800335b8  mov     rcx, [rax+1758h]
0x1800335bf  mov     [rsp+2C0h+var_280], rcx
0x1800335c4  test    rcx, rcx
0x1800335c7  jnz     short loc_1800335DE
0x1800335c9  lea     rcx, [rsp+2C0h+var_280]
0x1800335ce  call    cs:__imp_InternalTlsAllocData
0x1800335d4  mov     edi, eax
0x1800335d6  test    eax, eax
0x1800335d8  js      loc_1800337DD
0x1800335de  cmp     ebx, 4
0x1800335e1  jnz     short loc_180033648
0x1800335e3  test    r14d, r14d
0x1800335e6  jnz     loc_1800336B5
0x1800335ec  mov     rcx, rsi; unsigned __int16 *
0x1800335ef  call    ?IsNffAppropriate@CNtfsStorage@@SAJPEBG@Z; CNtfsStorage::IsNffAppropriate(ushort const *)
0x1800335f4  mov     edi, eax
0x1800335f6  test    eax, eax
0x1800335f8  js      short loc_180033600
0x1800335fa  lea     ebx, [r14+3]
0x1800335fe  jmp     short loc_180033651
0x180033600  cmp     eax, 80030001h
0x180033605  jnz     loc_1800337DD
0x18003360b  xor     ebx, ebx
0x18003360d  mov     [rsp+2C0h+var_280], 0
0x180033616  mov     dword ptr [rsp+2C0h+var_278], ebx
0x18003361a  test    r14d, r14d
0x18003361d  jz      loc_180033719
0x180033623  mov     ecx, [rbp+1C0h+arg_20]
0x180033629  mov     eax, ebx
0x18003362b  bt      ecx, 8
0x18003362f  cmovnb  rax, rsi
0x180033633  mov     rsi, rax
0x180033636  test    r15, r15
0x180033639  jz      loc_1800336EA
0x18003363f  mov     r9d, [r15+4]
0x180033643  jmp     loc_1800336F0
0x180033648  test    ebx, ebx
0x18003364a  jz      short loc_18003360B
0x18003364c  cmp     ebx, 5
0x18003364f  jz      short loc_1800336A7
0x180033651  mov     edi, 104h
0x180033656  lea     r9, [rsp+2C0h+FilePart]; lpFilePart
0x18003365b  mov     edx, edi; nBufferLength
0x18003365d  lea     r8, [rsp+2C0h+Buffer]; lpBuffer
0x180033662  mov     rcx, rsi; lpFileName
0x180033665  call    cs:__imp_GetFullPathNameW
0x18003366b  test    eax, eax
0x18003366d  jnz     short loc_180033691
0x18003366f  call    cs:__imp_GetLastError
0x180033675  test    eax, eax
0x180033677  jz      short loc_180033687
0x180033679  mov     ecx, eax; unsigned int
0x18003367b  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x180033680  mov     edi, eax
0x180033682  jmp     loc_1800337DD
0x180033687  mov     edi, 800300FCh
0x18003368c  jmp     loc_1800337DD
0x180033691  cmp     eax, edi
0x180033693  jbe     short loc_18003369F
0x180033695  mov     edi, 80030003h
0x18003369a  jmp     loc_1800337DD
0x18003369f  test    ebx, ebx
0x1800336a1  jz      loc_18003360B
0x1800336a7  cmp     ebx, 5
0x1800336aa  jz      loc_18003360B
0x1800336b0  cmp     ebx, 3
0x1800336b3  jz      short loc_1800336BF
0x1800336b5  mov     edi, 80030057h
0x1800336ba  jmp     loc_1800337DD
0x1800336bf  mov     rcx, [rsp+2C0h+var_268]
0x1800336c4  mov     r9d, r14d; int
0x1800336c7  mov     rax, [rsp+2C0h+var_270]
0x1800336cc  mov     edx, r13d; unsigned int
0x1800336cf  mov     [rsp+2C0h+var_290], rcx; void **
0x1800336d4  lea     rcx, [rsp+2C0h+Buffer]; unsigned __int16 *
0x1800336d9  mov     [rsp+2C0h+var_298], r12; struct _GUID *
0x1800336de  mov     [rsp+2C0h+var_2A0], rax; void *
0x1800336e3  call    ?NFFOpen@@YAJPEBGKKHPEAXAEBU_GUID@@PEAPEAX@Z; NFFOpen(ushort const *,ulong,ulong,int,void *,_GUID const &,void * *)
0x1800336e8  jmp     short loc_180033680
0x1800336ea  mov     r9d, 200h
0x1800336f0  mov     r8, [rsp+2C0h+var_270]
0x1800336f5  lea     rax, [rsp+2C0h+var_280]
0x1800336fa  mov     [rsp+2C0h+var_298], rax; struct IStorage **
0x1800336ff  mov     edx, r13d; unsigned int
0x180033702  mov     dword ptr [rsp+2C0h+var_2A0], ecx; int
0x180033706  mov     rcx, rsi; unsigned __int16 *
0x180033709  call    DfCreateDocfile
0x18003370e  mov     edi, eax
0x180033710  test    eax, eax
0x180033712  jns     short loc_18003375F
0x180033714  jmp     loc_1800337DD
0x180033719  lea     rax, [rsp+2C0h+var_280]
0x18003371e  xor     r9d, r9d; unsigned __int16 **
0x180033721  mov     [rsp+2C0h+var_288], rax; struct IStorage **
0x180033726  mov     r8d, r13d; unsigned int
0x180033729  mov     eax, [rbp+1C0h+arg_20]
0x18003372f  xor     edx, edx; void *
0x180033731  mov     dword ptr [rsp+2C0h+var_290], eax; int
0x180033735  mov     rcx, rsi; unsigned __int16 *
0x180033738  lea     rax, [rsp+2C0h+var_278]
0x18003373d  mov     [rsp+2C0h+var_298], rax; __int64
0x180033742  mov     rax, [rsp+2C0h+var_270]
0x180033747  mov     [rsp+2C0h+var_2A0], rax; void *
0x18003374c  call    DfOpenDocfile
0x180033751  mov     edi, eax
0x180033753  test    eax, eax
0x180033755  js      loc_1800337DD
0x18003375b  mov     ebx, dword ptr [rsp+2C0h+var_278]
0x18003375f  mov     rax, qword ptr cs:IID_IStorage.Data1
0x180033766  sub     rax, [r12]
0x18003376a  jnz     short loc_180033778
0x18003376c  mov     rax, qword ptr cs:IID_IStorage.Data4
0x180033773  sub     rax, [r12+8]
0x180033778  test    rax, rax
0x18003377b  jz      short loc_1800337C2
0x18003377d  mov     rbx, [rsp+2C0h+var_280]
0x180033782  mov     rdx, r12
0x180033785  mov     r8, [rsp+2C0h+var_268]
0x18003378a  mov     rcx, rbx
0x18003378d  mov     rax, [rbx]
0x180033790  mov     rax, [rax]
0x180033793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033798  mov     edi, eax
0x18003379a  mov     rcx, rbx
0x18003379d  mov     rax, [rbx]
0x1800337a0  mov     rax, [rax+10h]
0x1800337a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a9  test    r14d, r14d
0x1800337ac  jz      short loc_1800337DD
0x1800337ae  test    edi, edi
0x1800337b0  jns     short loc_1800337DD
0x1800337b2  test    rsi, rsi
0x1800337b5  jz      short loc_1800337DD
0x1800337b7  mov     rcx, rsi; lpFileName
0x1800337ba  call    cs:__imp_DeleteFileW
0x1800337c0  jmp     short loc_1800337DD
0x1800337c2  mov     rcx, [rsp+2C0h+var_268]
0x1800337c7  mov     rax, [rsp+2C0h+var_280]
0x1800337cc  mov     [rcx], rax
0x1800337cf  test    r15, r15
0x1800337d2  jz      short loc_1800337DD
0x1800337d4  test    r14d, r14d
0x1800337d7  jnz     short loc_1800337DD
0x1800337d9  mov     [r15+4], ebx
0x1800337dd  mov     eax, edi
0x1800337df  mov     rcx, [rbp+1C0h+var_40]
0x1800337e6  xor     rcx, rsp; StackCookie
0x1800337e9  call    __security_check_cookie
0x1800337ee  mov     rbx, [rsp+2C0h+arg_8]
0x1800337f6  add     rsp, 290h
0x1800337fd  pop     r15
0x1800337ff  pop     r14
0x180033801  pop     r13
0x180033803  pop     r12
0x180033805  pop     rdi
0x180033806  pop     rsi
0x180033807  pop     rbp
0x180033808  retn
```
