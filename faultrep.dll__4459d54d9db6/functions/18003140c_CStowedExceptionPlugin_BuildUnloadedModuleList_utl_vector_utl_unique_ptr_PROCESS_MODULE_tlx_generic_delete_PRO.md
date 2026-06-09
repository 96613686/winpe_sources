# CStowedExceptionPlugin::BuildUnloadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *)

- ea: `0x18003140c`
- end: `0x180031706`
- name: `?BuildUnloadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAX@Z`
- size: `762`
- prototype: `signed int __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180031d50`

## callees

- `0x180002890`
- `0x1800028ec`
- `0x180002e90`
- `0x180003474`
- `0x18003140c`
- `0x180032650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180031672`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180031672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800314a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800314a7`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x18003147a`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x18003147a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003149d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800314fd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003153d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031593`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003149d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800314fd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003153d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031593`

## pseudocode

```c
signed int __fastcall CStowedExceptionPlugin::BuildUnloadedModuleList(__int64 a1, void *a2)
{
  signed int result; // eax
  __int64 v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // rdx
  _WORD *v8; // rax
  unsigned __int64 v9; // rdi
  _OWORD *v10; // rax
  _OWORD *v11; // rbx
  unsigned __int64 v12; // r14
  char v13; // al
  void *v14; // rcx
  unsigned int v15; // [rsp+30h] [rbp-99h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-91h] BYREF
  int Buffer; // [rsp+40h] [rbp-89h] BYREF
  __int64 v18; // [rsp+48h] [rbp-81h] BYREF
  void *Block; // [rsp+50h] [rbp-79h] BYREF
  LPCVOID lpBaseAddress; // [rsp+58h] [rbp-71h] BYREF
  LPCVOID v21; // [rsp+60h] [rbp-69h] BYREF
  LPCVOID v22; // [rsp+68h] [rbp-61h] BYREF
  __int64 v23; // [rsp+70h] [rbp-59h] BYREF
  int v24; // [rsp+78h] [rbp-51h]
  int v25; // [rsp+84h] [rbp-45h]
  _WORD v26[42]; // [rsp+8Ch] [rbp-3Dh] BYREF

  NumberOfBytesRead = 0;
  lpBaseAddress = 0;
  v21 = 0;
  v22 = 0;
  Buffer = 0;
  v15 = 0;
  v18 = 0;
  memset_0(&v23, 0, 0x68u);
  RtlGetUnloadEventTraceEx(&lpBaseAddress, &v21, &v22);
  if ( !ReadProcessMemory(a2, lpBaseAddress, &Buffer, 4u, &NumberOfBytesRead) )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
    return result;
  }
  if ( NumberOfBytesRead != 4 )
    return -2147024597;
  if ( Buffer != 104 )
    return -2147023266;
  if ( !ReadProcessMemory(a2, v21, &v15, 4u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 4 )
    return -2147024597;
  if ( v15 >= 0x1000 )
    v15 = 4096;
  if ( !ReadProcessMemory(a2, v22, &v18, 8u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 8 )
    return -2147024597;
  v5 = v18;
  if ( !v18 )
    return 0;
  v6 = 0;
  if ( !v15 )
    return 0;
  while ( 1 )
  {
    if ( !ReadProcessMemory(a2, (LPCVOID)(v5 + 104LL * v6), &v23, 0x68u, &NumberOfBytesRead) || NumberOfBytesRead != 104 )
      goto LABEL_35;
    v7 = 32;
    v8 = v26;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v7;
    }
    while ( v7 );
    v9 = (32 - v7) & -(__int64)(v7 != 0);
    if ( !v7 )
    {
      v9 = 31;
      v26[31] = 0;
    }
    v10 = operator new((unsigned int)(2 * v9 + 2) + 40LL, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
      break;
    v14 = 0;
LABEL_33:
    if ( v14 )
      operator delete(v14);
LABEL_35:
    if ( ++v6 >= v15 )
      return 0;
    v5 = v18;
  }
  Block = v10;
  v12 = 0;
  *v10 = 0;
  v10[1] = 0;
  *((_QWORD *)v10 + 4) = 0;
  *(_QWORD *)v10 = v23;
  *((_DWORD *)v10 + 2) = v24;
  *((_DWORD *)v10 + 3) = v25;
  *((_WORD *)v10 + 8) = v26[33];
  *((_WORD *)v10 + 9) = v26[32];
  *((_WORD *)v10 + 10) = v26[35];
  *((_WORD *)v10 + 11) = v26[34];
  *((_QWORD *)v10 + 3) = (char *)v10 + 40;
  for ( *((_DWORD *)v10 + 8) = 1; v12 < v9; ++v12 )
    *(_WORD *)(*((_QWORD *)v11 + 3) + 2 * v12) = _o_towlower((unsigned __int16)v26[v12]);
  *(_WORD *)(*((_QWORD *)v11 + 3) + 2 * v9) = 0;
  v13 = utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(
          a1,
          &Block);
  v14 = Block;
  if ( v13 )
    goto LABEL_33;
  if ( Block )
    operator delete(Block);
  return -2147024882;
}

```

## disassembly

```asm
0x18003140c  mov     [rsp-8+arg_10], rbx
0x180031411  push    rbp
0x180031412  push    rsi
0x180031413  push    rdi
0x180031414  push    r12
0x180031416  push    r13
0x180031418  push    r14
0x18003141a  push    r15
0x18003141c  lea     rbp, [rsp-27h]
0x180031421  sub     rsp, 0F0h
0x180031428  mov     rax, cs:__security_cookie
0x18003142f  xor     rax, rsp
0x180031432  mov     [rbp+57h+var_40], rax
0x180031436  xor     r13d, r13d
0x180031439  mov     r15, rdx
0x18003143c  mov     r12, rcx
0x18003143f  mov     [rsp+120h+NumberOfBytesRead], r13
0x180031444  xor     edx, edx; Val
0x180031446  mov     [rbp+57h+lpBaseAddress], r13
0x18003144a  lea     rcx, [rbp+57h+var_B0]; void *
0x18003144e  mov     [rbp+57h+var_C0], r13
0x180031452  lea     r8d, [r13+68h]; Size
0x180031456  mov     [rbp+57h+var_B8], r13
0x18003145a  mov     [rsp+120h+Buffer], r13d
0x18003145f  mov     [rsp+120h+var_F0], r13d
0x180031464  mov     [rsp+120h+var_D8], r13
0x180031469  call    memset_0
0x18003146e  lea     r8, [rbp+57h+var_B8]
0x180031472  lea     rdx, [rbp+57h+var_C0]
0x180031476  lea     rcx, [rbp+57h+lpBaseAddress]
0x18003147a  call    cs:__imp_RtlGetUnloadEventTraceEx
0x180031480  mov     rdx, [rbp+57h+lpBaseAddress]; lpBaseAddress
0x180031484  lea     rax, [rsp+120h+NumberOfBytesRead]
0x180031489  lea     ebx, [r13+4]
0x18003148d  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031492  mov     r9d, ebx; nSize
0x180031495  lea     r8, [rsp+120h+Buffer]; lpBuffer
0x18003149a  mov     rcx, r15; hProcess
0x18003149d  call    cs:__imp_ReadProcessMemory
0x1800314a3  test    eax, eax
0x1800314a5  jnz     short loc_1800314C8
0x1800314a7  call    cs:__imp_GetLastError
0x1800314ad  test    eax, eax
0x1800314af  jle     short loc_1800314B9
0x1800314b1  movzx   eax, ax
0x1800314b4  or      eax, 80070000h
0x1800314b9  test    eax, eax
0x1800314bb  mov     ecx, 80004005h
0x1800314c0  cmovns  eax, ecx
0x1800314c3  jmp     loc_1800316DF
0x1800314c8  cmp     [rsp+120h+NumberOfBytesRead], rbx
0x1800314cd  jnz     loc_1800316DA
0x1800314d3  cmp     [rsp+120h+Buffer], 68h ; 'h'
0x1800314d8  jz      short loc_1800314E4
0x1800314da  mov     eax, 8007065Eh
0x1800314df  jmp     loc_1800316DF
0x1800314e4  mov     rdx, [rbp+57h+var_C0]; lpBaseAddress
0x1800314e8  lea     rax, [rsp+120h+NumberOfBytesRead]
0x1800314ed  mov     r9, rbx; nSize
0x1800314f0  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800314f5  lea     r8, [rsp+120h+var_F0]; lpBuffer
0x1800314fa  mov     rcx, r15; hProcess
0x1800314fd  call    cs:__imp_ReadProcessMemory
0x180031503  test    eax, eax
0x180031505  jz      short loc_1800314A7
0x180031507  cmp     [rsp+120h+NumberOfBytesRead], rbx
0x18003150c  jnz     loc_1800316DA
0x180031512  mov     eax, 1000h
0x180031517  cmp     [rsp+120h+var_F0], eax
0x18003151b  jb      short loc_180031521
0x18003151d  mov     [rsp+120h+var_F0], eax
0x180031521  mov     rdx, [rbp+57h+var_B8]; lpBaseAddress
0x180031525  lea     rax, [rsp+120h+NumberOfBytesRead]
0x18003152a  mov     r9d, 8; nSize
0x180031530  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031535  lea     r8, [rsp+120h+var_D8]; lpBuffer
0x18003153a  mov     rcx, r15; hProcess
0x18003153d  call    cs:__imp_ReadProcessMemory
0x180031543  test    eax, eax
0x180031545  jz      loc_1800314A7
0x18003154b  cmp     [rsp+120h+NumberOfBytesRead], 8
0x180031551  jnz     loc_1800316DA
0x180031557  mov     rcx, [rsp+120h+var_D8]
0x18003155c  test    rcx, rcx
0x18003155f  jz      loc_1800316D6
0x180031565  mov     esi, r13d
0x180031568  cmp     [rsp+120h+var_F0], r13d
0x18003156d  jbe     loc_1800316D6
0x180031573  mov     eax, esi
0x180031575  lea     r8, [rbp+57h+var_B0]; lpBuffer
0x180031579  imul    rdx, rax, 68h ; 'h'
0x18003157d  lea     rax, [rsp+120h+NumberOfBytesRead]
0x180031582  mov     r9d, 68h ; 'h'; nSize
0x180031588  add     rdx, rcx; lpBaseAddress
0x18003158b  mov     [rsp+120h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031590  mov     rcx, r15; hProcess
0x180031593  call    cs:__imp_ReadProcessMemory
0x180031599  test    eax, eax
0x18003159b  jz      loc_1800316C4
0x1800315a1  cmp     [rsp+120h+NumberOfBytesRead], 68h ; 'h'
0x1800315a7  jnz     loc_1800316C4
0x1800315ad  mov     edx, 20h ; ' '
0x1800315b2  lea     rax, [rbp+57h+var_94]
0x1800315b6  cmp     [rax], r13w
0x1800315ba  jz      short loc_1800315C6
0x1800315bc  add     rax, 2
0x1800315c0  sub     rdx, 1
0x1800315c4  jnz     short loc_1800315B6
0x1800315c6  mov     ecx, 20h ; ' '
0x1800315cb  mov     rax, rdx
0x1800315ce  sub     rcx, rdx
0x1800315d1  neg     rax
0x1800315d4  sbb     rdi, rdi
0x1800315d7  and     rdi, rcx
0x1800315da  test    rdx, rdx
0x1800315dd  jnz     short loc_1800315E7
0x1800315df  lea     edi, [rdx+1Fh]
0x1800315e2  mov     [rbp+57h+var_56], r13w
0x1800315e7  lea     ecx, ds:2[rdi*2]
0x1800315ee  add     rcx, 28h ; '('; unsigned __int64
0x1800315f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800315f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800315fe  mov     rbx, rax
0x180031601  test    rax, rax
0x180031604  jz      loc_1800316B7
0x18003160a  xor     eax, eax
0x18003160c  mov     [rbp+57h+Block], rbx
0x180031610  xorps   xmm0, xmm0
0x180031613  mov     r14, r13
0x180031616  movups  xmmword ptr [rbx], xmm0
0x180031619  movups  xmmword ptr [rbx+10h], xmm0
0x18003161d  mov     [rbx+20h], rax
0x180031621  mov     rcx, [rbp+57h+var_B0]
0x180031625  mov     [rbx], rcx
0x180031628  mov     ecx, [rbp+57h+var_A8]
0x18003162b  mov     [rbx+8], ecx
0x18003162e  mov     eax, [rbp+57h+var_9C]
0x180031631  mov     [rbx+0Ch], eax
0x180031634  mov     eax, [rbp+57h+var_54]
0x180031637  shr     eax, 10h
0x18003163a  mov     [rbx+10h], ax
0x18003163e  movzx   eax, word ptr [rbp+57h+var_54]
0x180031642  mov     [rbx+12h], ax
0x180031646  mov     eax, [rbp+57h+var_50]
0x180031649  shr     eax, 10h
0x18003164c  mov     [rbx+14h], ax
0x180031650  movzx   eax, word ptr [rbp+57h+var_50]
0x180031654  mov     [rbx+16h], ax
0x180031658  lea     rax, [rbx+28h]
0x18003165c  mov     [rbx+18h], rax
0x180031660  mov     dword ptr [rbx+20h], 1
0x180031667  test    rdi, rdi
0x18003166a  jz      short loc_180031689
0x18003166c  movzx   ecx, [rbp+r14*2+57h+var_94]
0x180031672  call    cs:__imp__o_towlower
0x180031678  mov     rcx, [rbx+18h]
0x18003167c  mov     [rcx+r14*2], ax
0x180031681  inc     r14
0x180031684  cmp     r14, rdi
0x180031687  jb      short loc_18003166C
0x180031689  mov     rcx, [rbx+18h]
0x18003168d  lea     rdx, [rbp+57h+Block]
0x180031691  mov     [rcx+rdi*2], r13w
0x180031696  mov     rcx, r12
0x180031699  call    ?push_back@?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@2@@Z; utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>> &&)
0x18003169e  mov     rcx, [rbp+57h+Block]; Block
0x1800316a2  test    al, al
0x1800316a4  jnz     short loc_1800316BA
0x1800316a6  test    rcx, rcx
0x1800316a9  jz      short loc_1800316B0
0x1800316ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800316b0  mov     eax, 8007000Eh
0x1800316b5  jmp     short loc_1800316DF
0x1800316b7  mov     rcx, r13; Block
0x1800316ba  test    rcx, rcx
0x1800316bd  jz      short loc_1800316C4
0x1800316bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800316c4  inc     esi
0x1800316c6  cmp     esi, [rsp+120h+var_F0]
0x1800316ca  jnb     short loc_1800316D6
0x1800316cc  mov     rcx, [rsp+120h+var_D8]
0x1800316d1  jmp     loc_180031573
0x1800316d6  xor     eax, eax
0x1800316d8  jmp     short loc_1800316DF
0x1800316da  mov     eax, 8007012Bh
0x1800316df  mov     rcx, [rbp+57h+var_40]
0x1800316e3  xor     rcx, rsp; StackCookie
0x1800316e6  call    __security_check_cookie
0x1800316eb  mov     rbx, [rsp+120h+arg_10]
0x1800316f3  add     rsp, 0F0h
0x1800316fa  pop     r15
0x1800316fc  pop     r14
0x1800316fe  pop     r13
0x180031700  pop     r12
0x180031702  pop     rdi
0x180031703  pop     rsi
0x180031704  pop     rbp
0x180031705  retn
```
