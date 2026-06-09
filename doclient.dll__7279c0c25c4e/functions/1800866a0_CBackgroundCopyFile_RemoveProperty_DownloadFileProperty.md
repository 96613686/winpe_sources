# CBackgroundCopyFile::_RemoveProperty(DownloadFileProperty)

- ea: `0x1800866a0`
- end: `0x1800869d9`
- name: `?_RemoveProperty@CBackgroundCopyFile@@AEAAXW4DownloadFileProperty@@@Z`
- size: `825`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18007fc0c`
- `0x180084164`
- `0x1800854d8`

## callees

- `0x1800095a0`
- `0x180009ab4`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001d138`
- `0x1800866a0`
- `0x1800943c4`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800a5c88`
- `0x1800e88e8`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086932`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086932`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008691c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008691c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008689b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008689b`

## string_xrefs

- `0x1800868e7`: `Deleted temporary file: %s`
- `0x180086842`: `CBackgroundCopyFile::_RemoveProperty`
- `0x1800868fc`: `CBackgroundCopyFile::_RemoveProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CBackgroundCopyFile::_RemoveProperty(__int64 a1, __int64 a2)
{
  int v2; // edi
  volatile signed __int32 *v4; // rdi
  volatile signed __int32 *v5; // rbx
  int v6; // edi
  int v7; // edi
  const char **v8; // rsi
  const char *v9; // rax
  const char *v11; // rcx
  int v12; // eax
  const char *v13; // rcx
  HANDLE v14; // rbx
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  HANDLE Token; // [rsp+30h] [rbp-50h] BYREF
  __int128 v21; // [rsp+38h] [rbp-48h]
  CConfigValue *v22[2]; // [rsp+48h] [rbp-38h] BYREF
  char *v23[2]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v24; // [rsp+68h] [rbp-18h]

  v2 = a2;
  *(_OWORD *)v22 = 0;
  if ( (int)CConfigStore::Erase(a1 + 424, a2, v22) < 0 )
  {
    if ( !v2 )
      goto LABEL_4;
  }
  else if ( !v2 )
  {
    CConfigValue::SecureZeroString(v22[0]);
LABEL_4:
    *(_QWORD *)(a1 + 400) = 0;
    v4 = *(volatile signed __int32 **)(a1 + 408);
    *(_QWORD *)(a1 + 408) = 0;
    if ( v4 )
    {
      if ( !_InterlockedDecrement(v4 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( !_InterlockedDecrement(v4 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    goto LABEL_8;
  }
  v6 = v2 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        v21 = (unsigned __int64)(a1 + 264);
        if ( (unsigned int)mtx_do_lock(a1 + 264) )
          std::_Throw_Cpp_error(5);
        if ( *(_DWORD *)(a1 + 340) == 0x7FFFFFFF )
        {
          *(_DWORD *)(a1 + 340) = 2147483646;
          std::_Throw_Cpp_error(6);
        }
        BYTE8(v21) = 1;
        v8 = (const char **)(a1 + 48);
        v9 = (const char *)(a1 + 48);
        if ( *(_QWORD *)(a1 + 72) > 0xFu )
          v9 = *v8;
        LogMessage(5u, "CBackgroundCopyFile::_RemoveProperty", 0x739u, "Clearing local file name:, %s", v9);
        *(_QWORD *)(a1 + 64) = 0;
        if ( *(_QWORD *)(a1 + 72) > 0xFu )
          v8 = (const char **)*v8;
        *(_BYTE *)v8 = 0;
        *(_OWORD *)v23 = *(_OWORD *)(a1 + 80);
        v24 = *(_OWORD *)(a1 + 96);
        *(_BYTE *)(a1 + 80) = 0;
        *(_QWORD *)(a1 + 96) = 0;
        *(_QWORD *)(a1 + 104) = 15;
        if ( a1 == -264 )
          std::_Throw_system_error(1);
        if ( (*(_DWORD *)(a1 + 340))-- == 1 )
        {
          *(_DWORD *)(a1 + 336) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 280));
        }
        BYTE8(v21) = 0;
        if ( (_QWORD)v24 )
        {
          Token = 0;
          CJobSharedData::ImpersonateOwner(*(CJobSharedData **)(a1 + 32), &Token);
          v11 = (const char *)v23;
          if ( *((_QWORD *)&v24 + 1) > 0xFu )
            v11 = v23[0];
          v12 = CFile::Delete(v11);
          v13 = (const char *)v23;
          if ( *((_QWORD *)&v24 + 1) > 0xFu )
            v13 = v23[0];
          LogResult(5u, "CBackgroundCopyFile::_RemoveProperty", 0x744u, v12, "Deleted temporary file: %s", v13);
          v14 = Token;
          if ( Token != (HANDLE)-1LL )
          {
            if ( !SetThreadToken(0, Token) )
              wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
            if ( v14 )
              CloseHandle(v14);
          }
        }
        std::string::~string(v23);
      }
    }
    else
    {
      *(_DWORD *)(a1 + 488) &= ~0x20000u;
    }
  }
  else
  {
    v16 = *(_QWORD *)(a1 + 416);
    if ( v16 )
    {
      *(_QWORD *)(v16 + 16) = 0;
      v17 = (_BYTE *)v16;
      if ( *(_QWORD *)(v16 + 24) > 0xFu )
        v17 = *(_BYTE **)v16;
      *v17 = 0;
      v18 = *(_QWORD *)(v16 + 32);
      if ( v18 != *(_QWORD *)(v16 + 40) )
        *(_QWORD *)(v16 + 40) = v18;
      v19 = (_QWORD *)(v16 + 56);
      *(_QWORD *)(v16 + 72) = 0;
      if ( *(_QWORD *)(v16 + 80) > 7u )
        v19 = (_QWORD *)*v19;
      *(_WORD *)v19 = 0;
      *(_OWORD *)(v16 + 88) = 0;
      *(_OWORD *)(v16 + 104) = 0;
    }
  }
LABEL_8:
  v5 = (volatile signed __int32 *)v22[1];
  if ( v22[1] && !_InterlockedDecrement((volatile signed __int32 *)v22[1] + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
    if ( !_InterlockedDecrement(v5 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
}

```

## disassembly

```asm
0x1800866a0  mov     [rsp-28h+arg_8], rbx
0x1800866a5  mov     [rsp-28h+arg_10], rsi
0x1800866aa  push    rbp
0x1800866ab  push    rdi
0x1800866ac  push    r12
0x1800866ae  push    r14
0x1800866b0  push    r15
0x1800866b2  mov     rbp, rsp
0x1800866b5  sub     rsp, 80h
0x1800866bc  mov     rax, cs:__security_cookie
0x1800866c3  xor     rax, rsp
0x1800866c6  mov     [rbp+var_8], rax
0x1800866ca  mov     edi, edx
0x1800866cc  mov     rbx, rcx
0x1800866cf  xorps   xmm1, xmm1
0x1800866d2  movdqu  xmmword ptr [rbp+var_38], xmm1
0x1800866d7  add     rcx, 1A8h
0x1800866de  lea     r8, [rbp+var_38]
0x1800866e2  call    ?Erase@CConfigStore@@QEAAJHAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigStore::Erase(int,std::shared_ptr<CConfigValue> &)
0x1800866e7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800866eb  xor     r14d, r14d
0x1800866ee  test    eax, eax
0x1800866f0  js      loc_1800867C1
0x1800866f6  test    edi, edi
0x1800866f8  jnz     loc_1800867C9
0x1800866fe  mov     rcx, [rbp+var_38]; this
0x180086702  call    ?SecureZeroString@CConfigValue@@QEAAXXZ; CConfigValue::SecureZeroString(void)
0x180086707  mov     [rbx+190h], r14
0x18008670e  mov     rdi, [rbx+198h]
0x180086715  mov     [rbx+198h], r14
0x18008671c  test    rdi, rdi
0x18008671f  jz      short loc_180086759
0x180086721  mov     eax, r15d
0x180086724  lock xadd [rdi+8], eax
0x180086729  add     eax, r15d
0x18008672c  jnz     short loc_180086759
0x18008672e  mov     rax, [rdi]
0x180086731  mov     rcx, rdi
0x180086734  mov     rax, [rax]
0x180086737  call    _guard_dispatch_icall
0x18008673c  mov     eax, r15d
0x18008673f  lock xadd [rdi+0Ch], eax
0x180086744  add     eax, r15d
0x180086747  jnz     short loc_180086759
0x180086749  mov     rax, [rdi]
0x18008674c  mov     rcx, rdi
0x18008674f  mov     rax, [rax+8]
0x180086753  call    _guard_dispatch_icall
0x180086758  nop
0x180086759  mov     rbx, [rbp+var_38+8]
0x18008675d  test    rbx, rbx
0x180086760  jz      short loc_180086799
0x180086762  mov     eax, r15d
0x180086765  lock xadd [rbx+8], eax
0x18008676a  add     eax, r15d
0x18008676d  jnz     short loc_180086799
0x18008676f  mov     rax, [rbx]
0x180086772  mov     rcx, rbx
0x180086775  mov     rax, [rax]
0x180086778  call    _guard_dispatch_icall
0x18008677d  mov     eax, r15d
0x180086780  lock xadd [rbx+0Ch], eax
0x180086785  add     eax, r15d
0x180086788  jnz     short loc_180086799
0x18008678a  mov     rax, [rbx]
0x18008678d  mov     rcx, rbx
0x180086790  mov     rax, [rax+8]
0x180086794  call    _guard_dispatch_icall
0x180086799  mov     rcx, [rbp+var_8]
0x18008679d  xor     rcx, rsp; StackCookie
0x1800867a0  call    __security_check_cookie
0x1800867a5  lea     r11, [rsp+80h+var_s0]
0x1800867ad  mov     rbx, [r11+38h]
0x1800867b1  mov     rsi, [r11+40h]
0x1800867b5  mov     rsp, r11
0x1800867b8  pop     r15
0x1800867ba  pop     r14
0x1800867bc  pop     r12
0x1800867be  pop     rdi
0x1800867bf  pop     rbp
0x1800867c0  retn
0x1800867c1  test    edi, edi
0x1800867c3  jz      loc_180086707
0x1800867c9  sub     edi, 1
0x1800867cc  jz      loc_180086955
0x1800867d2  sub     edi, 1
0x1800867d5  jz      loc_180086948
0x1800867db  cmp     edi, 1
0x1800867de  jnz     loc_180086759
0x1800867e4  xorps   xmm0, xmm0
0x1800867e7  movups  [rbp+var_48], xmm0
0x1800867eb  lea     rdi, [rbx+108h]
0x1800867f2  mov     qword ptr [rbp+var_48], rdi
0x1800867f6  mov     byte ptr [rbp+var_48+8], r14b
0x1800867fa  mov     rcx, rdi
0x1800867fd  call    mtx_do_lock
0x180086802  test    eax, eax
0x180086804  jnz     loc_1800869B6
0x18008680a  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180086811  jz      loc_1800869C1
0x180086817  lea     r12d, [rax+1]
0x18008681b  mov     byte ptr [rbp+var_48+8], r12b
0x18008681f  lea     rsi, [rbx+30h]
0x180086823  mov     rax, rsi
0x180086826  cmp     qword ptr [rsi+18h], 0Fh
0x18008682b  jbe     short loc_180086830
0x18008682d  mov     rax, [rsi]
0x180086830  mov     [rsp+80h+var_60], rax
0x180086835  lea     r9, aClearingLocalF; "Clearing local file name:, %s"
0x18008683c  mov     r8d, 739h; unsigned int
0x180086842  lea     rdx, aCbackgroundcop_39; "CBackgroundCopyFile::_RemoveProperty"
0x180086849  mov     ecx, 5; unsigned __int8
0x18008684e  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180086853  mov     [rsi+10h], r14
0x180086857  cmp     qword ptr [rsi+18h], 0Fh
0x18008685c  jbe     short loc_180086861
0x18008685e  mov     rsi, [rsi]
0x180086861  mov     [rsi], r14b
0x180086864  movups  xmm0, xmmword ptr [rbx+50h]
0x180086868  movups  xmmword ptr [rbp+var_28], xmm0
0x18008686c  movups  xmm1, xmmword ptr [rbx+60h]
0x180086870  movups  [rbp+var_18], xmm1
0x180086874  mov     [rbx+50h], r14b
0x180086878  mov     [rbx+60h], r14
0x18008687c  mov     qword ptr [rbx+68h], 0Fh
0x180086884  test    rdi, rdi
0x180086887  jz      loc_1800869AD
0x18008688d  add     [rdi+4Ch], r15d
0x180086891  jnz     short loc_1800868A1
0x180086893  mov     [rdi+48h], r15d
0x180086897  lea     rcx, [rdi+10h]; SRWLock
0x18008689b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800868a1  mov     byte ptr [rbp+var_48+8], r14b
0x1800868a5  cmp     qword ptr [rbp+var_18], r14
0x1800868a9  jz      loc_180086939
0x1800868af  mov     [rbp+Token], r14
0x1800868b3  lea     rdx, [rbp+Token]; int
0x1800868b7  mov     rcx, [rbx+20h]; this
0x1800868bb  call    ?ImpersonateOwner@CJobSharedData@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; CJobSharedData::ImpersonateOwner(void)
0x1800868c0  nop
0x1800868c1  lea     rcx, [rbp+var_28]
0x1800868c5  cmp     qword ptr [rbp+var_18+8], 0Fh
0x1800868ca  cmova   rcx, [rbp+var_28]; char *
0x1800868cf  call    ?Delete@CFile@@SAJPEBD@Z; CFile::Delete(char const *)
0x1800868d4  lea     rcx, [rbp+var_28]
0x1800868d8  cmp     qword ptr [rbp+var_18+8], 0Fh
0x1800868dd  cmova   rcx, [rbp+var_28]
0x1800868e2  mov     [rsp+80h+var_58], rcx
0x1800868e7  lea     rcx, aDeletedTempora; "Deleted temporary file: %s"
0x1800868ee  mov     [rsp+80h+var_60], rcx; char *
0x1800868f3  mov     r9d, eax; int
0x1800868f6  mov     r8d, 744h; unsigned int
0x1800868fc  lea     rdx, aCbackgroundcop_39; "CBackgroundCopyFile::_RemoveProperty"
0x180086903  mov     ecx, 5; unsigned __int8
0x180086908  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x18008690d  nop
0x18008690e  mov     rbx, [rbp+Token]
0x180086912  cmp     rbx, r15
0x180086915  jz      short loc_180086939
0x180086917  mov     rdx, rbx; Token
0x18008691a  xor     ecx, ecx; Thread
0x18008691c  call    cs:__imp_SetThreadToken
0x180086922  test    eax, eax
0x180086924  jz      loc_1800869D3
0x18008692a  test    rbx, rbx
0x18008692d  jz      short loc_180086939
0x18008692f  mov     rcx, rbx; hObject
0x180086932  call    cs:__imp_CloseHandle
0x180086938  nop
0x180086939  lea     rcx, [rbp+var_28]; void *
0x18008693d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180086942  nop
0x180086943  jmp     loc_180086759
0x180086948  btr     dword ptr [rbx+1E8h], 11h
0x180086950  jmp     loc_180086759
0x180086955  mov     rax, [rbx+1A0h]
0x18008695c  test    rax, rax
0x18008695f  jz      loc_180086759
0x180086965  mov     [rax+10h], r14
0x180086969  mov     rcx, rax
0x18008696c  cmp     qword ptr [rax+18h], 0Fh
0x180086971  jbe     short loc_180086976
0x180086973  mov     rcx, [rax]
0x180086976  mov     [rcx], r14b
0x180086979  mov     rcx, [rax+20h]
0x18008697d  cmp     rcx, [rax+28h]
0x180086981  jz      short loc_180086987
0x180086983  mov     [rax+28h], rcx
0x180086987  lea     rcx, [rax+38h]
0x18008698b  mov     [rcx+10h], r14
0x18008698f  cmp     qword ptr [rcx+18h], 7
0x180086994  jbe     short loc_180086999
0x180086996  mov     rcx, [rcx]
0x180086999  mov     [rcx], r14w
0x18008699d  xorps   xmm0, xmm0
0x1800869a0  movups  xmmword ptr [rax+58h], xmm0
0x1800869a4  movups  xmmword ptr [rax+68h], xmm0
0x1800869a8  jmp     loc_180086759
0x1800869ad  mov     ecx, r12d
0x1800869b0  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800869b6  mov     ecx, 5; int
0x1800869bb  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800869c1  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800869c8  mov     ecx, 6; int
0x1800869cd  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800869d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
