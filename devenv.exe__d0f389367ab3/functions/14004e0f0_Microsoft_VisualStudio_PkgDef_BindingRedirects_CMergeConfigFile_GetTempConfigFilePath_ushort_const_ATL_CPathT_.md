# Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetTempConfigFilePath(ushort const *,ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)

- ea: `0x14004e0f0`
- end: `0x14004e2e0`
- name: `?GetTempConfigFilePath@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEAAJPEBGAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400222b0`

## callees

- `0x140002c10`
- `0x140002dd0`
- `0x140003160`
- `0x140004950`
- `0x140033ab0`
- `0x14004e0f0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x14004e1fc`
- `KERNEL32!GetTempFileNameW` at `0x14004e1fc`
- `KERNEL32!GetTempPathW` at `0x14004e17a`
- `KERNEL32!GetTempPathW` at `0x14004e17a`
- `KERNEL32!GetLastError` at `0x14004e184`
- `KERNEL32!GetLastError` at `0x14004e206`
- `KERNEL32!GetLastError` at `0x14004e184`
- `KERNEL32!GetLastError` at `0x14004e206`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetTempConfigFilePath(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v8; // rax
  unsigned __int16 *v9; // rbx
  DWORD TempPath2W; // eax
  signed int v11; // eax
  unsigned int v12; // esi
  struct ATL::IAtlStringMgr *v13; // rax
  __int64 v14; // rax
  WCHAR *v15; // rdi
  UINT TempFileNameW; // eax
  signed int LastError; // eax
  _QWORD *v18; // rdx
  _QWORD v19[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v20; // [rsp+60h] [rbp+8h] BYREF
  WCHAR *v21; // [rsp+78h] [rbp+20h] BYREF

  if ( *(int *)(a1 + 44) >= 3 )
    return 2147549183LL;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v8 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
  v9 = (unsigned __int16 *)(v8 + 24);
  v20 = (unsigned __int16 *)(v8 + 24);
  if ( ((1 - *(_DWORD *)(v8 + 16)) | (*(_DWORD *)(v8 + 12) - 260)) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v20, 260);
    v9 = v20;
  }
  if ( SafeWrappersDeclarations::g_IsTempPath2Available )
    TempPath2W = SafeWrappersDeclarations::g_pGetTempPath2W(0x104u, v9);
  else
    TempPath2W = GetTempPathW(0x104u, v9);
  if ( TempPath2W )
  {
    if ( TempPath2W < 0x104 )
    {
      v13 = ATL::CAtlStringMgr::GetInstance();
      if ( !v13 )
        ATL::AtlThrowImpl(-2147467259);
      v14 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v13 + 24LL))(v13);
      v15 = (WCHAR *)(v14 + 24);
      v21 = (WCHAR *)(v14 + 24);
      if ( ((1 - *(_DWORD *)(v14 + 16)) | (*(_DWORD *)(v14 + 12) - 260)) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v21, 260);
        v15 = v21;
      }
      TempFileNameW = GetTempFileNameW(v9, a2, 0, v15);
      if ( TempFileNameW )
      {
        if ( TempFileNameW == 111 )
        {
          v12 = -2147024785;
        }
        else
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            v19,
            v15);
          ATL::CSimpleStringT<unsigned short,0>::operator=(a3, v19);
          v18 = (_QWORD *)(v19[0] - 24LL);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
          }
          ++*(_DWORD *)(a1 + 44);
          v12 = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        v12 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v12 = LastError;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
      }
    }
    else
    {
      v12 = -2147418113;
    }
  }
  else
  {
    v11 = GetLastError();
    v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v12 = v11;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
  }
  return v12;
}

```

## disassembly

```asm
0x14004e0f0  mov     [rsp+arg_8], rbx
0x14004e0f5  push    rbp
0x14004e0f6  push    rsi
0x14004e0f7  push    rdi
0x14004e0f8  push    r14
0x14004e0fa  push    r15
0x14004e0fc  sub     rsp, 30h
0x14004e100  mov     r14, r8
0x14004e103  mov     rbp, rdx
0x14004e106  mov     rsi, rcx
0x14004e109  cmp     dword ptr [rcx+2Ch], 3
0x14004e10d  jl      short loc_14004E119
0x14004e10f  mov     eax, 8000FFFFh
0x14004e114  jmp     loc_14004E2B5
0x14004e119  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004e11e  mov     rcx, rax
0x14004e121  test    rax, rax
0x14004e124  jz      loc_14004E2D5
0x14004e12a  mov     rax, [rax]
0x14004e12d  call    qword ptr [rax+18h]
0x14004e130  lea     rbx, [rax+18h]
0x14004e134  mov     [rsp+58h+arg_0], rbx
0x14004e139  mov     ecx, 1
0x14004e13e  sub     ecx, [rbx-8]
0x14004e141  mov     eax, [rbx-0Ch]
0x14004e144  mov     r15d, 104h
0x14004e14a  sub     eax, r15d
0x14004e14d  or      eax, ecx
0x14004e14f  jge     short loc_14004E163
0x14004e151  mov     edx, r15d
0x14004e154  lea     rcx, [rsp+58h+arg_0]
0x14004e159  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14004e15e  mov     rbx, [rsp+58h+arg_0]
0x14004e163  mov     rdx, rbx; lpBuffer
0x14004e166  mov     ecx, r15d; nBufferLength
0x14004e169  cmp     cs:?g_IsTempPath2Available@SafeWrappersDeclarations@@3_NA, 0; bool SafeWrappersDeclarations::g_IsTempPath2Available
0x14004e170  jz      short loc_14004E17A
0x14004e172  call    cs:?g_pGetTempPath2W@SafeWrappersDeclarations@@3P6AKKPEAG@ZEA; ulong (*SafeWrappersDeclarations::g_pGetTempPath2W)(ulong,ushort *)
0x14004e178  jmp     short loc_14004E180
0x14004e17a  call    cs:__imp_GetTempPathW
0x14004e180  test    eax, eax
0x14004e182  jnz     short loc_14004E19D
0x14004e184  call    cs:__imp_GetLastError
0x14004e18a  movzx   esi, ax
0x14004e18d  or      esi, 80070000h
0x14004e193  test    eax, eax
0x14004e195  cmovle  esi, eax
0x14004e198  jmp     loc_14004E295
0x14004e19d  cmp     eax, r15d
0x14004e1a0  jb      short loc_14004E1AC
0x14004e1a2  mov     esi, 8000FFFFh
0x14004e1a7  jmp     loc_14004E295
0x14004e1ac  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004e1b1  mov     rcx, rax
0x14004e1b4  test    rax, rax
0x14004e1b7  jz      loc_14004E2C6
0x14004e1bd  mov     rax, [rax]
0x14004e1c0  call    qword ptr [rax+18h]
0x14004e1c3  lea     rdi, [rax+18h]
0x14004e1c7  mov     [rsp+58h+arg_18], rdi
0x14004e1cc  mov     ecx, 1
0x14004e1d1  sub     ecx, [rdi-8]
0x14004e1d4  mov     eax, [rdi-0Ch]
0x14004e1d7  sub     eax, r15d
0x14004e1da  or      eax, ecx
0x14004e1dc  jge     short loc_14004E1F0
0x14004e1de  mov     edx, r15d
0x14004e1e1  lea     rcx, [rsp+58h+arg_18]
0x14004e1e6  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14004e1eb  mov     rdi, [rsp+58h+arg_18]
0x14004e1f0  mov     r9, rdi; lpTempFileName
0x14004e1f3  xor     r8d, r8d; uUnique
0x14004e1f6  mov     rdx, rbp; lpPrefixString
0x14004e1f9  mov     rcx, rbx; lpPathName
0x14004e1fc  call    cs:__imp_GetTempFileNameW
0x14004e202  test    eax, eax
0x14004e204  jnz     short loc_14004E21C
0x14004e206  call    cs:__imp_GetLastError
0x14004e20c  movzx   esi, ax
0x14004e20f  or      esi, 80070000h
0x14004e215  test    eax, eax
0x14004e217  cmovle  esi, eax
0x14004e21a  jmp     short loc_14004E277
0x14004e21c  cmp     eax, 6Fh ; 'o'
0x14004e21f  jnz     short loc_14004E228
0x14004e221  mov     esi, 8007006Fh
0x14004e226  jmp     short loc_14004E277
0x14004e228  mov     rdx, rdi
0x14004e22b  lea     rcx, [rsp+58h+var_38]
0x14004e230  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004e235  nop
0x14004e236  lea     rdx, [rsp+58h+var_38]
0x14004e23b  mov     rcx, r14
0x14004e23e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004e243  nop
0x14004e244  nop     dword ptr [rax+00h]
0x14004e248  nop     dword ptr [rax+rax+00000000h]
0x14004e250  mov     rdx, [rsp+58h+var_38]
0x14004e255  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004e259  or      eax, 0FFFFFFFFh
0x14004e25c  lock xadd [rdx+10h], eax
0x14004e261  sub     eax, 1
0x14004e264  jg      short loc_14004E272
0x14004e266  lfence
0x14004e269  mov     rcx, [rdx]
0x14004e26c  mov     rax, [rcx]
0x14004e26f  call    qword ptr [rax+8]
0x14004e272  inc     dword ptr [rsi+2Ch]
0x14004e275  xor     esi, esi
0x14004e277  lea     rdx, [rdi-18h]
0x14004e27b  or      eax, 0FFFFFFFFh
0x14004e27e  lock xadd [rdx+10h], eax
0x14004e283  sub     eax, 1
0x14004e286  jg      short loc_14004E295
0x14004e288  lfence
0x14004e28b  mov     rcx, [rdx]
0x14004e28e  mov     rax, [rcx]
0x14004e291  call    qword ptr [rax+8]
0x14004e294  nop
0x14004e295  lea     rdx, [rbx-18h]
0x14004e299  or      ecx, 0FFFFFFFFh
0x14004e29c  lock xadd [rdx+10h], ecx
0x14004e2a1  sub     ecx, 1
0x14004e2a4  jg      short loc_14004E2B3
0x14004e2a6  lfence
0x14004e2a9  mov     rcx, [rdx]
0x14004e2ac  mov     r8, [rcx]
0x14004e2af  call    qword ptr [r8+8]
0x14004e2b3  mov     eax, esi
0x14004e2b5  mov     rbx, [rsp+58h+arg_8]
0x14004e2ba  add     rsp, 30h
0x14004e2be  pop     r15
0x14004e2c0  pop     r14
0x14004e2c2  pop     rdi
0x14004e2c3  pop     rsi
0x14004e2c4  pop     rbp
0x14004e2c5  retn
0x14004e2c6  mov     ecx, 80004005h; int
0x14004e2cb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004e2d1  jmp     short loc_14004E2D4
0x14004e2d4  nop
0x14004e2d5  mov     ecx, 80004005h; int
0x14004e2da  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
