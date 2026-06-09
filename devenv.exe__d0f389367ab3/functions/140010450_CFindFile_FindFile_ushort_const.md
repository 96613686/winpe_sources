# CFindFile::FindFile(ushort const *)

- ea: `0x140010450`
- end: `0x1400106e0`
- name: `?FindFile@CFindFile@@QEAAHPEBG@Z`
- size: `656`
- prototype: `__int64 __fastcall(CFindFile *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140010f70`
- `0x14002a810`
- `0x14002b2b0`
- `0x1400467d0`

## callees

- `0x140002dd0`
- `0x140003160`
- `0x140004950`
- `0x14000fc60`
- `0x14000fe10`
- `0x140010450`
- `0x1400106e0`
- `0x140033ab0`

## import_xrefs

- `KERNEL32!FindFirstFileExW` at `0x14001056e`
- `KERNEL32!FindFirstFileExW` at `0x14001056e`
- `KERNEL32!SetLastError` at `0x140010602`
- `KERNEL32!SetLastError` at `0x140010602`
- `VCRUNTIME140!wcsrchr` at `0x140010648`
- `VCRUNTIME140!wcsrchr` at `0x140010669`
- `VCRUNTIME140!wcsrchr` at `0x140010648`
- `VCRUNTIME140!wcsrchr` at `0x140010669`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400104e0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400105cb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400104e0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400105cb`
- `SHLWAPI!PathRemoveBlanksW` at `0x1400104c5`
- `SHLWAPI!PathRemoveBlanksW` at `0x1400104c5`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x1400105b1`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x1400105b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFindFile::FindFile(CFindFile *this, const unsigned __int16 *a2)
{
  const wchar_t *v4; // rdx
  WCHAR *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // esi
  LPWSTR v8; // rax
  int v9; // ecx
  _WORD *v10; // rdx
  __int64 v11; // r8
  const WCHAR *v12; // rcx
  signed __int64 v13; // r9
  __int16 v14; // ax
  _WORD *v15; // rax
  HANDLE FirstFile; // rax
  wchar_t **v17; // rdi
  wchar_t *v18; // rbx
  int v19; // eax
  LPWSTR v20; // rdx
  wchar_t *v22; // rax
  __int64 v23; // rbx
  wchar_t *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  _QWORD *v27; // rdx
  __int64 v28; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR pszPath; // [rsp+70h] [rbp+40h] BYREF

  CFindFile::Close(this);
  pszPath = 0;
  v4 = L"*.*";
  if ( a2 )
    v4 = a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &pszPath,
    v4);
  v5 = pszPath;
  v6 = *((unsigned int *)pszPath - 4);
  if ( (int)v6 < 0 )
    goto LABEL_42;
  v7 = 1;
  if ( ((1 - *((_DWORD *)pszPath - 2)) | (*((_DWORD *)pszPath - 3) - (int)v6)) < 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&pszPath, v6);
    v5 = pszPath;
  }
  PathRemoveBlanksW(v5);
  v8 = pszPath;
  if ( pszPath )
  {
    v9 = wcsnlen(pszPath, *((int *)pszPath - 3));
    if ( v9 < 0 )
      goto LABEL_42;
    v8 = pszPath;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 > *((_DWORD *)v8 - 3) )
    goto LABEL_42;
  *((_DWORD *)v8 - 4) = v9;
  pszPath[v9] = 0;
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveBackslash(&pszPath);
  v10 = (_WORD *)((char *)this + 44);
  v11 = 260;
  v12 = pszPath;
  v13 = (char *)pszPath - ((char *)this + 44);
  do
  {
    if ( v11 == -2147483386 )
      break;
    v14 = *(_WORD *)((char *)v10 + v13);
    if ( !v14 )
      break;
    *v10++ = v14;
    --v11;
  }
  while ( v11 );
  v15 = v10 - 1;
  if ( v11 )
    v15 = v10;
  *v15 = 0;
  FirstFile = FindFirstFileExW(v12, FindExInfoBasic, this, FindExSearchNameMatch, 0, 0);
  *((_QWORD *)this + 75) = FirstFile;
  if ( FirstFile == (HANDLE)-1LL )
    goto LABEL_26;
  v17 = (wchar_t **)((char *)this + 592);
  if ( ((1 - *(_DWORD *)(*((_QWORD *)this + 74) - 8LL)) | (*(_DWORD *)(*((_QWORD *)this + 74) - 12LL) - 260)) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((char *)this + 592, 260);
  v18 = _wfullpath(*v17, pszPath, 0x104u);
  if ( *v17 )
  {
    v19 = wcsnlen(*v17, *((int *)*v17 - 3));
    if ( v19 < 0 )
      goto LABEL_42;
  }
  else
  {
    v19 = 0;
  }
  if ( v19 > *((_DWORD *)*v17 - 3) )
LABEL_42:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*v17 - 4) = v19;
  (*v17)[v19] = 0;
  if ( !v18 )
  {
    CFindFile::Close(this);
    SetLastError(0x7Bu);
LABEL_26:
    v7 = 0;
    goto LABEL_27;
  }
  v22 = wcsrchr(*v17, 0x5Cu);
  if ( v22 )
    v23 = v22 - *v17;
  else
    LODWORD(v23) = -1;
  v24 = wcsrchr(*v17, 0x2Fu);
  if ( v24 )
  {
    v25 = v24 - *v17;
    if ( (int)v25 >= 0 )
    {
LABEL_37:
      if ( (int)v25 > (int)v23 )
        LODWORD(v23) = v25;
      v26 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
              (char *)this + 592,
              &v28,
              (unsigned int)v23);
      ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 592, v26);
      v27 = (_QWORD *)(v28 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 - 24 + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 8LL))(*v27);
      }
      goto LABEL_41;
    }
  }
  else
  {
    LODWORD(v25) = -1;
  }
  if ( (int)v23 >= 0 )
    goto LABEL_37;
LABEL_41:
  *((_DWORD *)this + 152) = 1;
LABEL_27:
  v20 = pszPath - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
  }
  return v7;
}

```

## disassembly

```asm
0x140010450  mov     [rsp-28h+arg_0], rbx
0x140010455  push    rbp
0x140010456  push    rsi
0x140010457  push    rdi
0x140010458  push    r14
0x14001045a  push    r15
0x14001045c  mov     rbp, rsp
0x14001045f  sub     rsp, 30h
0x140010463  mov     rbx, rdx
0x140010466  mov     r14, rcx
0x140010469  call    ?Close@CFindFile@@QEAAXXZ; CFindFile::Close(void)
0x14001046e  xor     r15d, r15d
0x140010471  mov     [rbp+pszPath], r15
0x140010475  lea     rdx, asc_140071878; "*.*"
0x14001047c  test    rbx, rbx
0x14001047f  cmovnz  rdx, rbx
0x140010483  lea     rcx, [rbp+pszPath]
0x140010487  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001048c  mov     rcx, [rbp+pszPath]
0x140010490  mov     edx, [rcx-10h]
0x140010493  test    edx, edx
0x140010495  js      loc_1400106D5
0x14001049b  nop     dword ptr [rax+rax+00h]
0x1400104a0  lea     esi, [r15+1]
0x1400104a4  mov     r8d, esi
0x1400104a7  sub     r8d, [rcx-8]
0x1400104ab  mov     eax, [rcx-0Ch]
0x1400104ae  sub     eax, edx
0x1400104b0  or      eax, r8d
0x1400104b3  jge     short loc_1400104C5
0x1400104b5  lfence
0x1400104b8  lea     rcx, [rbp+pszPath]
0x1400104bc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400104c1  mov     rcx, [rbp+pszPath]; pszPath
0x1400104c5  call    cs:__imp_PathRemoveBlanksW
0x1400104cb  mov     rax, [rbp+pszPath]
0x1400104cf  test    rax, rax
0x1400104d2  jnz     short loc_1400104D9
0x1400104d4  mov     ecx, r15d
0x1400104d7  jmp     short loc_1400104F5
0x1400104d9  movsxd  rdx, dword ptr [rax-0Ch]; MaxCount
0x1400104dd  mov     rcx, rax; Source
0x1400104e0  call    cs:__imp_wcsnlen
0x1400104e6  mov     rcx, rax
0x1400104e9  test    eax, eax
0x1400104eb  js      loc_1400106D5
0x1400104f1  mov     rax, [rbp+pszPath]
0x1400104f5  cmp     ecx, [rax-0Ch]
0x1400104f8  jg      loc_1400106D5
0x1400104fe  mov     [rax-10h], ecx
0x140010501  mov     ecx, ecx
0x140010503  mov     rax, [rbp+pszPath]
0x140010507  mov     [rax+rcx*2], r15w
0x14001050c  lea     rcx, [rbp+pszPath]
0x140010510  call    ?RemoveBackslash@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveBackslash(void)
0x140010515  lea     rdx, [r14+2Ch]
0x140010519  mov     ebx, 104h
0x14001051e  mov     r8d, ebx
0x140010521  mov     rcx, [rbp+pszPath]; lpFileName
0x140010525  mov     r9, rcx
0x140010528  sub     r9, rdx
0x14001052b  lea     rax, [r8+7FFFFEFAh]
0x140010532  test    rax, rax
0x140010535  jz      short loc_14001054D
0x140010537  movzx   eax, word ptr [r9+rdx]
0x14001053c  test    ax, ax
0x14001053f  jz      short loc_14001054D
0x140010541  mov     [rdx], ax
0x140010544  add     rdx, 2
0x140010548  sub     r8, rsi
0x14001054b  jnz     short loc_14001052B
0x14001054d  lea     rax, [rdx-2]
0x140010551  test    r8, r8
0x140010554  cmovnz  rax, rdx
0x140010558  mov     [rax], r15w
0x14001055c  mov     [rsp+30h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x140010561  mov     [rsp+30h+lpSearchFilter], r15; lpSearchFilter
0x140010566  xor     r9d, r9d; fSearchOp
0x140010569  mov     r8, r14; lpFindFileData
0x14001056c  mov     edx, esi; fInfoLevelId
0x14001056e  call    cs:__imp_FindFirstFileExW
0x140010574  mov     [r14+258h], rax
0x14001057b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001057f  jz      loc_140010608
0x140010585  lea     rdi, [r14+250h]
0x14001058c  mov     rax, [rdi]
0x14001058f  mov     edx, esi
0x140010591  sub     edx, [rax-8]
0x140010594  mov     ecx, [rax-0Ch]
0x140010597  sub     ecx, ebx
0x140010599  or      ecx, edx
0x14001059b  jge     short loc_1400105A7
0x14001059d  mov     edx, ebx
0x14001059f  mov     rcx, rdi
0x1400105a2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400105a7  mov     r8, rbx; BufferCount
0x1400105aa  mov     rdx, [rbp+pszPath]; Path
0x1400105ae  mov     rcx, [rdi]; Buffer
0x1400105b1  call    cs:__imp__wfullpath
0x1400105b7  mov     rbx, rax
0x1400105ba  mov     rcx, [rdi]; Source
0x1400105bd  test    rcx, rcx
0x1400105c0  jnz     short loc_1400105C7
0x1400105c2  mov     eax, r15d
0x1400105c5  jmp     short loc_1400105D9
0x1400105c7  movsxd  rdx, dword ptr [rcx-0Ch]; MaxCount
0x1400105cb  call    cs:__imp_wcsnlen
0x1400105d1  test    eax, eax
0x1400105d3  js      loc_1400106D5
0x1400105d9  mov     rcx, [rdi]
0x1400105dc  cmp     eax, [rcx-0Ch]
0x1400105df  jg      loc_1400106D5
0x1400105e5  mov     [rcx-10h], eax
0x1400105e8  mov     ecx, eax
0x1400105ea  mov     rax, [rdi]
0x1400105ed  mov     [rax+rcx*2], r15w
0x1400105f2  test    rbx, rbx
0x1400105f5  jnz     short loc_140010640
0x1400105f7  mov     rcx, r14; this
0x1400105fa  call    ?Close@CFindFile@@QEAAXXZ; CFindFile::Close(void)
0x1400105ff  lea     ecx, [rbx+7Bh]; dwErrCode
0x140010602  call    cs:__imp_SetLastError
0x140010608  mov     esi, r15d
0x14001060b  mov     rdx, [rbp+pszPath]
0x14001060f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010613  or      ecx, 0FFFFFFFFh
0x140010616  lock xadd [rdx+10h], ecx
0x14001061b  sub     ecx, 1
0x14001061e  jg      short loc_14001062D
0x140010620  lfence
0x140010623  mov     rcx, [rdx]
0x140010626  mov     r8, [rcx]
0x140010629  call    qword ptr [r8+8]
0x14001062d  mov     eax, esi
0x14001062f  mov     rbx, [rsp+30h+arg_0]
0x140010634  add     rsp, 30h
0x140010638  pop     r15
0x14001063a  pop     r14
0x14001063c  pop     rdi
0x14001063d  pop     rsi
0x14001063e  pop     rbp
0x14001063f  retn
0x140010640  mov     edx, 5Ch ; '\'; Ch
0x140010645  mov     rcx, [rdi]; Str
0x140010648  call    cs:__imp_wcsrchr
0x14001064e  mov     rbx, rax
0x140010651  test    rax, rax
0x140010654  jnz     short loc_14001065B
0x140010656  or      ebx, 0FFFFFFFFh
0x140010659  jmp     short loc_140010661
0x14001065b  sub     rbx, [rdi]
0x14001065e  sar     rbx, 1
0x140010661  mov     edx, 2Fh ; '/'; Ch
0x140010666  mov     rcx, [rdi]; Str
0x140010669  call    cs:__imp_wcsrchr
0x14001066f  test    rax, rax
0x140010672  jnz     short loc_140010679
0x140010674  or      eax, 0FFFFFFFFh
0x140010677  jmp     short loc_140010683
0x140010679  sub     rax, [rdi]
0x14001067c  sar     rax, 1
0x14001067f  test    eax, eax
0x140010681  jns     short loc_140010687
0x140010683  test    ebx, ebx
0x140010685  js      short loc_1400106C9
0x140010687  cmp     eax, ebx
0x140010689  cmovg   ebx, eax
0x14001068c  mov     r8d, ebx
0x14001068f  lea     rdx, [rbp+arg_8]
0x140010693  mov     rcx, rdi
0x140010696  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x14001069b  nop
0x14001069c  mov     rdx, rax
0x14001069f  mov     rcx, rdi
0x1400106a2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400106a7  nop
0x1400106a8  mov     rdx, [rbp+arg_8]
0x1400106ac  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400106b0  or      eax, 0FFFFFFFFh
0x1400106b3  lock xadd [rdx+10h], eax
0x1400106b8  sub     eax, 1
0x1400106bb  jg      short loc_1400106C9
0x1400106bd  lfence
0x1400106c0  mov     rcx, [rdx]
0x1400106c3  mov     rax, [rcx]
0x1400106c6  call    qword ptr [rax+8]
0x1400106c9  mov     [r14+260h], esi
0x1400106d0  jmp     loc_14001060B
0x1400106d5  mov     ecx, 80070057h; int
0x1400106da  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
