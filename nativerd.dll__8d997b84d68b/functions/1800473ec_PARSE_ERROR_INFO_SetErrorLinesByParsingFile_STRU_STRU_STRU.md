# PARSE_ERROR_INFO::SetErrorLinesByParsingFile(STRU *,STRU *,STRU *)

- ea: `0x1800473ec`
- end: `0x1800475e5`
- name: `?SetErrorLinesByParsingFile@PARSE_ERROR_INFO@@AEAAJPEAVSTRU@@00@Z`
- size: `505`
- prototype: `__int64 __fastcall(PARSE_ERROR_INFO *__hidden this, struct STRU *, struct STRU *, struct STRU *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800101b4`

## callees

- `0x18000b8cc`
- `0x180016440`
- `0x18001c250`
- `0x18001fe34`
- `0x1800412fc`
- `0x1800473ec`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004759f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004759f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800475ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800475ba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800474c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800474c1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180047444`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180047444`
- `iisutil!MakePathCanonicalizationProof` at `0x1800474ad`
- `iisutil!MakePathCanonicalizationProof` at `0x1800474ad`

## pseudocode

```c
__int64 __fastcall PARSE_ERROR_INFO::SetErrorLinesByParsingFile(
        PARSE_ERROR_INFO *this,
        struct STRU *a2,
        struct STRU *a3,
        struct STRU *a4)
{
  const unsigned __int16 **v8; // rdx
  const unsigned __int16 *v9; // rcx
  signed int PathCanonicalizationProof; // ebx
  const unsigned __int16 *Str; // rax
  HANDLE v12; // rsi
  signed int LastError; // eax
  CONFIG_XML_DOM *v14; // rax
  CONFIG_XML_DOM *v15; // rax
  CONFIG_XML_DOM *v16; // rdi
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+58h] [rbp-A8h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  _BYTE v23[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v24[264]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v24, 0, 0x208u);
  STRU::STRU((STRU *)v23, v24, 0x104u);
  v18[0] = &PARSE_ERROR_INFO::`vftable';
  v21 = 0;
  v22 = 0;
  v18[1] = 1;
  v19 = 0;
  v20 = 0;
  if ( !*((_DWORD *)this + 3) || SMALL_STRU::IsEmpty((PARSE_ERROR_INFO *)((char *)this + 32)) )
  {
    PathCanonicalizationProof = -2147024809;
  }
  else
  {
    v9 = &szDomain;
    if ( *v8 )
      v9 = *v8;
    PathCanonicalizationProof = MakePathCanonicalizationProof(v9, (struct STRU *)v23);
    if ( PathCanonicalizationProof >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v23);
      v12 = FILE_HELPER::CreateFileAndWriteEvent(
              L"PARSE_ERROR_INFO::SetErrorLinesByParsingFile",
              Str,
              0,
              1,
              3u,
              0x80u,
              (char *)0xFFFFFFFFFFFFFFFFLL);
      if ( v12 == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        PathCanonicalizationProof = LastError;
        if ( LastError > 0 )
          PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v14 = (CONFIG_XML_DOM *)operator new(0x90u);
        if ( v14 && (v15 = CONFIG_XML_DOM::CONFIG_XML_DOM(v14), (v16 = v15) != 0) )
        {
          PathCanonicalizationProof = (*(__int64 (__fastcall **)(CONFIG_XML_DOM *, HANDLE, _QWORD *, _QWORD, _DWORD))(*(_QWORD *)v15 + 8LL))(
                                        v15,
                                        v12,
                                        v18,
                                        0,
                                        0);
          if ( PathCanonicalizationProof >= 0 )
            PathCanonicalizationProof = (*(__int64 (__fastcall **)(CONFIG_XML_DOM *, _QWORD, struct STRU *, struct STRU *, struct STRU *))(*(_QWORD *)v16 + 24LL))(
                                          v16,
                                          *((unsigned int *)this + 3),
                                          a2,
                                          a3,
                                          a4);
          (*(void (__fastcall **)(CONFIG_XML_DOM *))(*(_QWORD *)v16 + 56LL))(v16);
        }
        else
        {
          PathCanonicalizationProof = -2147024888;
        }
        CloseHandle(v12);
      }
    }
  }
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v18);
  STRU::~STRU((STRU *)v23);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x1800473ec  push    rbp
0x1800473ee  push    rbx
0x1800473ef  push    rsi
0x1800473f0  push    rdi
0x1800473f1  push    r12
0x1800473f3  push    r13
0x1800473f5  push    r14
0x1800473f7  push    r15
0x1800473f9  lea     rbp, [rsp-1E8h]
0x180047401  sub     rsp, 2E8h
0x180047408  mov     rax, cs:__security_cookie
0x18004740f  xor     rax, rsp
0x180047412  mov     [rbp+220h+var_50], rax
0x180047419  mov     r12, r8
0x18004741c  mov     r15, rdx
0x18004741f  mov     r14, rcx
0x180047422  xor     edx, edx; Val
0x180047424  mov     r8d, 208h; Size
0x18004742a  lea     rcx, [rbp+220h+var_260]; void *
0x18004742e  mov     r13, r9
0x180047431  call    memset_0
0x180047436  mov     r8d, 104h
0x18004743c  lea     rdx, [rbp+220h+var_260]
0x180047440  lea     rcx, [rbp+220h+var_2A0]
0x180047444  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004744a  xor     edi, edi
0x18004744c  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180047453  xorps   xmm0, xmm0
0x180047456  xorps   xmm1, xmm1
0x180047459  mov     esi, 1
0x18004745e  mov     [rsp+320h+var_2E0], rax
0x180047463  movdqa  [rsp+320h+var_2C0], xmm0
0x180047469  movdqa  [rsp+320h+var_2B0], xmm1
0x18004746f  mov     [rsp+320h+var_2D8], rsi
0x180047474  mov     [rsp+320h+var_2D0], edi
0x180047478  mov     [rsp+320h+var_2C8], rdi
0x18004747d  cmp     [r14+0Ch], edi
0x180047481  jz      loc_1800475A7
0x180047487  lea     rdx, [r14+20h]
0x18004748b  mov     rcx, rdx; this
0x18004748e  call    ?IsEmpty@SMALL_STRU@@QEBA_NXZ; SMALL_STRU::IsEmpty(void)
0x180047493  test    al, al
0x180047495  jnz     loc_1800475A7
0x18004749b  cmp     [rdx], rdi
0x18004749e  lea     rcx, szDomain
0x1800474a5  cmovnz  rcx, [rdx]
0x1800474a9  lea     rdx, [rbp+220h+var_2A0]
0x1800474ad  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x1800474b3  mov     ebx, eax
0x1800474b5  test    eax, eax
0x1800474b7  js      loc_1800475AC
0x1800474bd  lea     rcx, [rbp+220h+var_2A0]
0x1800474c1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800474c7  mov     [rsp+320h+var_2F0], 0FFFFFFFFFFFFFFFFh; void *
0x1800474d0  lea     rcx, aParseErrorInfo; "PARSE_ERROR_INFO::SetErrorLinesByParsin"...
0x1800474d7  mov     rdx, rax; unsigned __int16 *
0x1800474da  mov     [rsp+320h+var_2F8], 80h; unsigned int
0x1800474e2  mov     r9d, esi; unsigned int
0x1800474e5  mov     [rsp+320h+var_300], 3; unsigned int
0x1800474ed  mov     r8d, 80000000h; unsigned int
0x1800474f3  call    ?CreateFileAndWriteEvent@FILE_HELPER@@SAPEAXPEBG0KKKKPEAX@Z; FILE_HELPER::CreateFileAndWriteEvent(ushort const *,ushort const *,ulong,ulong,ulong,ulong,void *)
0x1800474f8  mov     rsi, rax
0x1800474fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800474ff  jnz     short loc_18004751F
0x180047501  call    cs:__imp_GetLastError
0x180047507  mov     ebx, eax
0x180047509  test    eax, eax
0x18004750b  jle     loc_1800475AC
0x180047511  movzx   ebx, ax
0x180047514  or      ebx, 80070000h
0x18004751a  jmp     loc_1800475AC
0x18004751f  mov     ecx, 90h; Size
0x180047524  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047529  test    rax, rax
0x18004752c  jz      short loc_180047597
0x18004752e  mov     rcx, rax; this
0x180047531  call    ??0CONFIG_XML_DOM@@QEAA@XZ; CONFIG_XML_DOM::CONFIG_XML_DOM(void)
0x180047536  mov     rdi, rax
0x180047539  test    rax, rax
0x18004753c  jz      short loc_180047597
0x18004753e  mov     rax, [rax]
0x180047541  lea     r8, [rsp+320h+var_2E0]
0x180047546  xor     r9d, r9d
0x180047549  mov     [rsp+320h+var_300], 0
0x180047551  mov     rdx, rsi
0x180047554  mov     rcx, rdi
0x180047557  mov     rax, [rax+8]
0x18004755b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047560  mov     ebx, eax
0x180047562  test    eax, eax
0x180047564  js      short loc_180047586
0x180047566  mov     rax, [rdi]
0x180047569  mov     r9, r12
0x18004756c  mov     edx, [r14+0Ch]
0x180047570  mov     r8, r15
0x180047573  mov     rcx, rdi
0x180047576  mov     qword ptr [rsp+320h+var_300], r13
0x18004757b  mov     rax, [rax+18h]
0x18004757f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047584  mov     ebx, eax
0x180047586  mov     rax, [rdi]
0x180047589  mov     rcx, rdi
0x18004758c  mov     rax, [rax+38h]
0x180047590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047595  jmp     short loc_18004759C
0x180047597  mov     ebx, 80070008h
0x18004759c  mov     rcx, rsi; hObject
0x18004759f  call    cs:__imp_CloseHandle
0x1800475a5  jmp     short loc_1800475AC
0x1800475a7  mov     ebx, 80070057h
0x1800475ac  lea     rcx, [rsp+320h+var_2E0]; this
0x1800475b1  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x1800475b6  lea     rcx, [rbp+220h+var_2A0]
0x1800475ba  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800475c0  mov     eax, ebx
0x1800475c2  mov     rcx, [rbp+220h+var_50]
0x1800475c9  xor     rcx, rsp; StackCookie
0x1800475cc  call    __security_check_cookie
0x1800475d1  add     rsp, 2E8h
0x1800475d8  pop     r15
0x1800475da  pop     r14
0x1800475dc  pop     r13
0x1800475de  pop     r12
0x1800475e0  pop     rdi
0x1800475e1  pop     rsi
0x1800475e2  pop     rbx
0x1800475e3  pop     rbp
0x1800475e4  retn
```
