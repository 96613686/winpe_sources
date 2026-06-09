# RepoMan::FileStream::Write(void const *,ulong,ulong *)

- ea: `0x18018c790`
- end: `0x18018c8ed`
- name: `?Write@FileStream@RepoMan@@UEAAJPEBXKPEAK@Z`
- size: `349`
- prototype: `int(RepoMan::FileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800136dc`
- `0x180013960`
- `0x180013b14`
- `0x1800248a4`
- `0x180024d50`
- `0x180024de8`
- `0x1800255cc`
- `0x180025984`
- `0x180025b60`
- `0x18018c790`
- `0x18019a840`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!ftell` at `0x18018c7e8`
- `api-ms-win-crt-stdio-l1-1-0!ftell` at `0x18018c7e8`
- `api-ms-win-crt-stdio-l1-1-0!ferror` at `0x18018c89e`
- `api-ms-win-crt-stdio-l1-1-0!ferror` at `0x18018c89e`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18018c7d6`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18018c7d6`

## string_xrefs

- `0x18018c836`: `failed to write `

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RepoMan::FileStream::Write(FILE **this, const void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v7; // esi
  int v8; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  _BYTE v20[240]; // [rsp+40h] [rbp-148h] BYREF
  _BYTE v21[32]; // [rsp+130h] [rbp-58h] BYREF

  if ( a4 )
    *a4 = 0;
  v7 = fwrite(a2, 1u, a3, this[8]);
  if ( v7 != a3 )
  {
    std::ostringstream::ostringstream(v20);
    v10 = std::operator<<<std::char_traits<char>>((__int64)v20, (__int64)"failed to write ");
    v11 = std::ostream::operator<<(v10, a3);
    v12 = std::operator<<<std::char_traits<char>>(v11, (__int64)" bytes at offset: ");
    v13 = std::ostream::operator<<(v12, this[2]);
    v14 = std::operator<<<std::char_traits<char>>(v13, (__int64)" to : '");
    v15 = std::operator<<<char>(v14, this + 4);
    v16 = std::operator<<<std::char_traits<char>>(v15, (__int64)"' with error: ");
    v17 = ferror(this[8]);
    std::ostream::operator<<(v16, v17);
    v18 = std::ostringstream::str(v20, v21);
    v19 = std::string::c_str(v18);
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      162,
      (unsigned int)"src\\repoman\\src\\inc\\FileSystem.hpp",
      v19,
      -1941503468,
      8);
  }
  v8 = ftell(this[8]);
  this[2] = (FILE *)v8;
  if ( v8 > (unsigned __int64)this[3] )
    this[3] = (FILE *)v8;
  if ( a4 )
    *a4 = v7;
  return 0;
}

```

## disassembly

```asm
0x18018c790  push    rbx
0x18018c792  push    rsi
0x18018c793  push    rdi
0x18018c794  push    r14
0x18018c796  sub     rsp, 168h
0x18018c79d  mov     rax, cs:__security_cookie
0x18018c7a4  xor     rax, rsp
0x18018c7a7  mov     [rsp+188h+var_38], rax
0x18018c7af  mov     rdi, r9
0x18018c7b2  mov     r14d, r8d
0x18018c7b5  mov     rax, rdx
0x18018c7b8  mov     rbx, rcx
0x18018c7bb  test    r9, r9
0x18018c7be  jz      short loc_18018C7C7
0x18018c7c0  mov     dword ptr [r9], 0
0x18018c7c7  mov     r8, r14; ElementCount
0x18018c7ca  mov     r9, [rcx+40h]; Stream
0x18018c7ce  mov     edx, 1; ElementSize
0x18018c7d3  mov     rcx, rax; Buffer
0x18018c7d6  call    cs:__imp_fwrite
0x18018c7dc  mov     rsi, rax
0x18018c7df  cmp     eax, r14d
0x18018c7e2  jnz     short loc_18018C82B
0x18018c7e4  mov     rcx, [rbx+40h]; Stream
0x18018c7e8  call    cs:__imp_ftell
0x18018c7ee  movsxd  rcx, eax
0x18018c7f1  mov     [rbx+10h], rcx
0x18018c7f5  cmp     rcx, [rbx+18h]
0x18018c7f9  jbe     short loc_18018C7FF
0x18018c7fb  mov     [rbx+18h], rcx
0x18018c7ff  test    rdi, rdi
0x18018c802  jz      short loc_18018C806
0x18018c804  mov     [rdi], esi
0x18018c806  xor     eax, eax
0x18018c808  jmp     short loc_18018C80E
0x18018c80a  mov     eax, [rsp+188h+var_158]
0x18018c80e  mov     rcx, [rsp+188h+var_38]
0x18018c816  xor     rcx, rsp; StackCookie
0x18018c819  call    __security_check_cookie
0x18018c81e  add     rsp, 168h
0x18018c825  pop     r14
0x18018c827  pop     rdi
0x18018c828  pop     rsi
0x18018c829  pop     rbx
0x18018c82a  retn
0x18018c82b  lea     rcx, [rsp+188h+var_148]
0x18018c830  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18018c835  nop
0x18018c836  lea     rdx, aFailedToWrite; "failed to write "
0x18018c83d  lea     rcx, [rsp+188h+var_148]
0x18018c842  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018c847  mov     edx, r14d
0x18018c84a  mov     rcx, rax
0x18018c84d  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z; std::ostream::operator<<(ulong)
0x18018c852  lea     rdx, aBytesAtOffset; " bytes at offset: "
0x18018c859  mov     rcx, rax
0x18018c85c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018c861  mov     rdx, [rbx+10h]
0x18018c865  mov     rcx, rax
0x18018c868  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z; std::ostream::operator<<(unsigned __int64)
0x18018c86d  lea     rdx, aTo; " to : '"
0x18018c874  mov     rcx, rax
0x18018c877  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018c87c  lea     rdx, [rbx+20h]
0x18018c880  mov     rcx, rax
0x18018c883  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x18018c888  lea     rdx, aWithError; "' with error: "
0x18018c88f  mov     rcx, rax
0x18018c892  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018c897  mov     rdi, rax
0x18018c89a  mov     rcx, [rbx+40h]; Stream
0x18018c89e  call    cs:__imp_ferror
0x18018c8a4  mov     edx, eax
0x18018c8a6  mov     rcx, rdi
0x18018c8a9  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x18018c8ae  lea     rdx, [rsp+188h+var_58]
0x18018c8b6  lea     rcx, [rsp+188h+var_148]
0x18018c8bb  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::ostringstream::str(void)
0x18018c8c0  nop
0x18018c8c1  mov     rcx, rax
0x18018c8c4  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x18018c8c9  mov     r8, rax
0x18018c8cc  mov     [rsp+188h+var_168], 8
0x18018c8d4  mov     r9d, 8C470214h
0x18018c8da  lea     rdx, aSrcRepomanSrcI_17; "src\\repoman\\src\\inc\\FileSystem.hpp"
0x18018c8e1  mov     ecx, 0A2h
0x18018c8e6  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
