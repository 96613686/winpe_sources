# FIStreamCreate

- ea: `0x140014730`
- end: `0x1400148c6`
- name: `FIStreamCreate`
- size: `406`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e5a0`
- `0x1400138d4`

## callees

- `0x140002538`
- `0x140003d80`
- `0x140014730`

## import_xrefs

- `ntoskrnl!PfFileInfoNotify` at `0x140014872`
- `ntoskrnl!PfFileInfoNotify` at `0x140014872`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400147e8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400147e8`
- `ntoskrnl!rand` at `0x140014754`
- `ntoskrnl!rand` at `0x140014754`
- `FLTMGR!FltAllocateContext` at `0x140014798`
- `FLTMGR!FltAllocateContext` at `0x140014798`

## pseudocode

```c
NTSTATUS __fastcall FIStreamCreate(PFLT_CONTEXT *a1)
{
  int v1; // edi
  __int32 v2; // ebx
  NTSTATUS result; // eax
  _QWORD *v5; // rax
  _DWORD v6[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+3Ch] [rbp-3Ch]
  int v8; // [rsp+44h] [rbp-34h]
  PFLT_CONTEXT ReturnedContext; // [rsp+88h] [rbp+10h] BYREF

  v1 = dword_1400099E4;
  ReturnedContext = 0;
  v2 = _InterlockedExchange(&dword_1400099EC, 0);
  if ( rand() % (unsigned int)dword_1400099E8 < v1 + v2 )
    return -1073741546;
  result = FltAllocateContext((PFLT_FILTER)FIGlobals, 8u, 0x50u, PagedPool, &ReturnedContext);
  if ( result >= 0 )
  {
    memset(ReturnedContext, 0, 0x50u);
    *((_DWORD *)ReturnedContext + 14) |= 1u;
    v5 = ReturnedContext;
    *((_QWORD *)ReturnedContext + 1) = ReturnedContext;
    *v5 = v5;
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)ReturnedContext + 2);
    FILockInitialize((char *)ReturnedContext + 40);
    v7 = 0;
    *((_DWORD *)ReturnedContext + 15) = dword_1400093D0
                                      + ((((MEMORY[0xFFFFF78000000004] * HIDWORD(MEMORY[0xFFFFF78000000320])) << 8)
                                        + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24)) >> 10);
    v8 = 0;
    v6[0] = 15;
    v6[1] = 7;
    v6[2] = 8;
    PfFileInfoNotify(v6);
    *((_DWORD *)ReturnedContext + 16) = HIDWORD(v7);
    _InterlockedIncrement(&dword_1400093AC);
    if ( (unsigned int)xmmword_1400093B0 < dword_1400093AC )
      LODWORD(xmmword_1400093B0) = dword_1400093AC;
    *a1 = ReturnedContext;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140014730  push    rbx
0x140014732  push    rbp
0x140014733  push    rsi
0x140014734  push    rdi
0x140014735  sub     rsp, 58h
0x140014739  mov     edi, cs:dword_1400099E4
0x14001473f  xor     ebp, ebp
0x140014741  mov     [rsp+78h+arg_8], rbp
0x140014749  mov     ebx, ebp
0x14001474b  xchg    ebx, cs:dword_1400099EC
0x140014751  mov     rsi, rcx
0x140014754  call    cs:__imp_rand
0x14001475b  nop     dword ptr [rax+rax+00h]
0x140014760  xor     edx, edx
0x140014762  div     cs:dword_1400099E8
0x140014768  lea     eax, [rdi+rbx]
0x14001476b  cmp     edx, eax
0x14001476d  jb      loc_1400148BF
0x140014773  mov     rcx, cs:FIGlobals; Filter
0x14001477a  lea     rax, [rsp+78h+arg_8]
0x140014782  mov     edx, 8; ContextType
0x140014787  mov     [rsp+78h+ReturnedContext], rax; ReturnedContext
0x14001478c  mov     r9d, 1; PoolType
0x140014792  mov     r8d, 50h ; 'P'; ContextSize
0x140014798  call    cs:__imp_FltAllocateContext
0x14001479f  nop     dword ptr [rax+rax+00h]
0x1400147a4  test    eax, eax
0x1400147a6  js      loc_1400148B5
0x1400147ac  mov     rcx, [rsp+78h+arg_8]; void *
0x1400147b4  xor     edx, edx; Val
0x1400147b6  mov     r8d, 50h ; 'P'; Size
0x1400147bc  call    memset
0x1400147c1  mov     rax, [rsp+78h+arg_8]
0x1400147c9  or      dword ptr [rax+38h], 1
0x1400147cd  mov     rax, [rsp+78h+arg_8]
0x1400147d5  mov     [rax+8], rax
0x1400147d9  mov     [rax], rax
0x1400147dc  mov     rcx, [rsp+78h+arg_8]
0x1400147e4  add     rcx, 10h; RunRef
0x1400147e8  call    cs:__imp_ExInitializeRundownProtection
0x1400147ef  nop     dword ptr [rax+rax+00h]
0x1400147f4  mov     rcx, [rsp+78h+arg_8]
0x1400147fc  add     rcx, 28h ; '('
0x140014800  call    FILockInitialize
0x140014805  mov     rcx, 0FFFFF78000000320h
0x14001480f  mov     rax, 0FFFFF78000000004h
0x140014819  mov     rcx, [rcx]
0x14001481c  mov     eax, [rax]
0x14001481e  mov     edx, ecx
0x140014820  imul    rdx, rax
0x140014824  shr     rcx, 20h
0x140014828  imul    rcx, rax
0x14001482c  mov     rax, [rsp+78h+arg_8]
0x140014834  shr     rdx, 18h
0x140014838  shl     rcx, 8
0x14001483c  add     rdx, rcx
0x14001483f  mov     [rsp+78h+var_3C], rbp
0x140014844  shr     rdx, 0Ah
0x140014848  lea     rcx, [rsp+78h+var_48]
0x14001484d  add     edx, cs:dword_1400093D0
0x140014853  mov     [rax+3Ch], edx
0x140014856  mov     [rsp+78h+var_34], ebp
0x14001485a  mov     [rsp+78h+var_48], 0Fh
0x140014862  mov     [rsp+78h+var_44], 7
0x14001486a  mov     [rsp+78h+var_40], 8
0x140014872  call    cs:__imp_PfFileInfoNotify
0x140014879  nop     dword ptr [rax+rax+00h]
0x14001487e  mov     rcx, [rsp+78h+arg_8]
0x140014886  mov     eax, dword ptr [rsp+78h+var_3C+4]
0x14001488a  mov     [rcx+40h], eax
0x14001488d  lock inc cs:dword_1400093AC
0x140014894  mov     eax, cs:dword_1400093AC
0x14001489a  cmp     dword ptr cs:xmmword_1400093B0, eax
0x1400148a0  jnb     short loc_1400148A8
0x1400148a2  mov     dword ptr cs:xmmword_1400093B0, eax
0x1400148a8  mov     rax, [rsp+78h+arg_8]
0x1400148b0  mov     [rsi], rax
0x1400148b3  xor     eax, eax
0x1400148b5  add     rsp, 58h
0x1400148b9  pop     rdi
0x1400148ba  pop     rsi
0x1400148bb  pop     rbp
0x1400148bc  pop     rbx
0x1400148bd  retn
0x1400148bf  mov     eax, 0C0000116h
0x1400148c4  jmp     short loc_1400148B5
```
