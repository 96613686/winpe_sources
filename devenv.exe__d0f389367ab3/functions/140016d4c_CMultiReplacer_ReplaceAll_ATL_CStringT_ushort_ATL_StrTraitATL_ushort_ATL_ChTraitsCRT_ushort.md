# CMultiReplacer::ReplaceAll(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x140016d4c`
- end: `0x140016e8a`
- name: `?ReplaceAll@CMultiReplacer@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `318`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140016bec`
- `0x14001b180`
- `0x14001eda0`
- `0x140052e5c`

## callees

- `0x140002c10`
- `0x140002dd0`
- `0x140004950`
- `0x140016d4c`
- `0x140016e8c`
- `0x140022e40`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140016d76`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140016d76`
- `ADVAPI32!RevertToSelf` at `0x140016e56`
- `ADVAPI32!RevertToSelf` at `0x140016e56`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140016dda`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140016dda`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140016e0d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140016e0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMultiReplacer::ReplaceAll(__int64 a1, const wchar_t **a2)
{
  bool v4; // di
  struct ATL::IAtlStringMgr *Instance; // rax
  WCHAR *v6; // rbx
  DWORD v7; // esi
  signed int v8; // ebp
  int v9; // eax
  WCHAR *v11; // [rsp+60h] [rbp+18h] BYREF

  (**(void (__fastcall ***)(__int64))a1)(a1);
  CMultiReplacer::ReplaceWithRegKeyLookup(a1, a2);
  v4 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 80));
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v6 = (WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  v11 = v6;
  v7 = 520;
  while ( 1 )
  {
    if ( (((1 - *((_DWORD *)v6 - 2)) | (*((_DWORD *)v6 - 3) - v7)) & 0x80000000) != 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v11, v7);
      v6 = v11;
    }
    v8 = ExpandEnvironmentStringsW(*a2, v6, v7);
    if ( !v8 )
      CLogger::LogError(L"Error while expanding environment variables.", -2147467259, 0);
    if ( v8 <= v7 )
      break;
    v7 = v8;
    if ( v8 < 0 )
      goto LABEL_18;
  }
  v9 = wcsnlen(v6, *((int *)v6 - 3));
  if ( v9 < 0 || v9 > *((_DWORD *)v6 - 3) )
LABEL_18:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v6 - 4) = v9;
  v6[v9] = 0;
  ATL::CSimpleStringT<unsigned short,0>::operator=(a2, &v11);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
  }
  if ( v4 )
    RevertToSelf();
  return CMultiReplacer::UnwrapProtectedEnvironmentVariables(a2);
}

```

## disassembly

```asm
0x140016d4c  mov     [rsp+arg_8], rbx
0x140016d51  push    rbp
0x140016d52  push    rsi
0x140016d53  push    rdi
0x140016d54  push    r14
0x140016d56  push    r15
0x140016d58  sub     rsp, 20h
0x140016d5c  mov     r14, rdx
0x140016d5f  mov     rbx, rcx
0x140016d62  mov     rax, [rcx]
0x140016d65  call    qword ptr [rax]
0x140016d67  mov     rdx, r14
0x140016d6a  mov     rcx, rbx
0x140016d6d  call    ?ReplaceWithRegKeyLookup@CMultiReplacer@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CMultiReplacer::ReplaceWithRegKeyLookup(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140016d72  mov     rcx, [rbx+50h]; hToken
0x140016d76  call    cs:__imp_ImpersonateLoggedOnUser
0x140016d7c  xor     r15d, r15d
0x140016d7f  test    eax, eax
0x140016d81  setnz   dil
0x140016d85  mov     [rsp+48h+arg_0], dil
0x140016d8a  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140016d8f  mov     rcx, rax
0x140016d92  test    rax, rax
0x140016d95  jz      loc_140016E71
0x140016d9b  mov     rax, [rax]
0x140016d9e  call    qword ptr [rax+18h]
0x140016da1  lea     rbx, [rax+18h]
0x140016da5  mov     [rsp+48h+arg_10], rbx
0x140016daa  mov     esi, 208h
0x140016daf  mov     ecx, 1
0x140016db4  sub     ecx, [rbx-8]
0x140016db7  mov     eax, [rbx-0Ch]
0x140016dba  sub     eax, esi
0x140016dbc  or      eax, ecx
0x140016dbe  jge     short loc_140016DD1
0x140016dc0  mov     edx, esi
0x140016dc2  lea     rcx, [rsp+48h+arg_10]
0x140016dc7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140016dcc  mov     rbx, [rsp+48h+arg_10]
0x140016dd1  mov     r8d, esi; nSize
0x140016dd4  mov     rdx, rbx; lpDst
0x140016dd7  mov     rcx, [r14]; lpSrc
0x140016dda  call    cs:__imp_ExpandEnvironmentStringsW
0x140016de0  mov     ebp, eax
0x140016de2  test    eax, eax
0x140016de4  jnz     short loc_140016DFA
0x140016de6  xor     r8d, r8d; unsigned __int16 *
0x140016de9  mov     edx, 80004005h; int
0x140016dee  lea     rcx, aErrorWhileExpa; "Error while expanding environment varia"...
0x140016df5  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140016dfa  cmp     ebp, esi
0x140016dfc  jbe     short loc_140016E06
0x140016dfe  mov     esi, ebp
0x140016e00  test    ebp, ebp
0x140016e02  js      short loc_140016E7F
0x140016e04  jmp     short loc_140016DAF
0x140016e06  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x140016e0a  mov     rcx, rbx; Source
0x140016e0d  call    cs:__imp_wcsnlen
0x140016e13  test    eax, eax
0x140016e15  js      short loc_140016E7F
0x140016e17  cmp     eax, [rbx-0Ch]
0x140016e1a  jg      short loc_140016E7F
0x140016e1c  mov     [rbx-10h], eax
0x140016e1f  cdqe
0x140016e21  mov     [rbx+rax*2], r15w
0x140016e26  lea     rdx, [rsp+48h+arg_10]
0x140016e2b  mov     rcx, r14
0x140016e2e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140016e33  lea     rdx, [rbx-18h]
0x140016e37  or      eax, 0FFFFFFFFh
0x140016e3a  lock xadd [rdx+10h], eax
0x140016e3f  sub     eax, 1
0x140016e42  jg      short loc_140016E51
0x140016e44  lfence
0x140016e47  mov     rcx, [rdx]
0x140016e4a  mov     rax, [rcx]
0x140016e4d  call    qword ptr [rax+8]
0x140016e50  nop
0x140016e51  test    dil, dil
0x140016e54  jz      short loc_140016E5C
0x140016e56  call    cs:__imp_RevertToSelf
0x140016e5c  mov     rcx, r14
0x140016e5f  mov     rbx, [rsp+48h+arg_8]
0x140016e64  add     rsp, 20h
0x140016e68  pop     r15
0x140016e6a  pop     r14
0x140016e6c  pop     rdi
0x140016e6d  pop     rsi
0x140016e6e  pop     rbp
0x140016e6f  jmp     short ?UnwrapProtectedEnvironmentVariables@CMultiReplacer@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CMultiReplacer::UnwrapProtectedEnvironmentVariables(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140016e71  mov     ecx, 80004005h; int
0x140016e76  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140016e7c  jmp     short $+2
0x140016e7e  nop
0x140016e7f  mov     ecx, 80070057h; int
0x140016e84  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
