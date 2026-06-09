# CContextMenuOverExplorerCommands::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x180014c90`
- end: `0x180014f4f`
- name: `?GetCommandString@CContextMenuOverExplorerCommands@@UEAAJ_KIPEAIPEADI@Z`
- size: `703`
- prototype: `int(CContextMenuOverExplorerCommands *__hidden this, unsigned __int64, unsigned int, unsigned int *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013220`
- `0x180014c90`
- `0x180014f58`
- `0x180014fcc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014eb4`
- `SHCORE!SHUnicodeToAnsi` at `0x180014e7a`
- `SHCORE!SHUnicodeToAnsi` at `0x180014ed2`
- `SHCORE!SHUnicodeToAnsi` at `0x180014e7a`
- `SHCORE!SHUnicodeToAnsi` at `0x180014ed2`
- `SHCORE!SHStrDupA` at `0x180014dbd`
- `SHCORE!SHStrDupA` at `0x180014dbd`
- `SHLWAPI!__imp_StrCmpICW` at `0x180014d96`
- `SHLWAPI!__imp_StrCmpICW` at `0x180014dda`
- `SHLWAPI!__imp_StrCmpICW` at `0x180014d96`
- `SHLWAPI!__imp_StrCmpICW` at `0x180014dda`

## pseudocode

```c
__int64 __fastcall CContextMenuOverExplorerCommands::GetCommandString(
        LPCWSTR *this,
        const WCHAR *a2,
        unsigned int a3,
        unsigned int *a4,
        PSTR pszDst,
        int cchBuf)
{
  signed int v10; // ebx
  PCWSTR *v11; // r15
  BOOL v12; // ebp
  PCWSTR v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdx
  PSTR v16; // rax
  _WORD *v17; // rcx
  LPCWSTR v19; // rcx
  LPCWSTR v20; // rdx
  LPCWSTR v21; // rcx
  LPWSTR ppwsz; // [rsp+90h] [rbp+8h] BYREF

  v10 = CContextMenuOverExplorerCommands::_EnsureParentCommand((CContextMenuOverExplorerCommands *)(this - 4));
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    if ( (a3 & 4) != 0 )
    {
      v11 = this + 8;
      v12 = StrCmpICW(a2, this[8]) == 0;
    }
    else
    {
      ppwsz = 0;
      if ( SHStrDupA((LPCSTR)a2, &ppwsz) < 0 )
      {
LABEL_36:
        v21 = this[4];
        if ( v21 )
          return (unsigned int)(*(__int64 (__fastcall **)(LPCWSTR, const WCHAR *, _QWORD, unsigned int *, PSTR, int))(*(_QWORD *)v21 + 40LL))(
                                 v21,
                                 a2,
                                 a3,
                                 a4,
                                 pszDst,
                                 cchBuf);
        else
          return (unsigned int)-2147467259;
      }
      v11 = this + 8;
      v12 = StrCmpICW(ppwsz, this[8]) == 0;
      CoTaskMemFree(ppwsz);
    }
  }
  else
  {
    v11 = this + 8;
    v12 = *((_DWORD *)this + 20) == (_DWORD)a2;
  }
  if ( !v12 )
    goto LABEL_36;
  if ( !a3 )
    goto LABEL_9;
  if ( a3 != 1 )
  {
    if ( a3 == 2 )
      return 0;
    if ( a3 == 4 )
    {
LABEL_9:
      v13 = *v11;
      if ( a3 )
      {
        v14 = 2147483646;
        v15 = (unsigned int)cchBuf;
        if ( (unsigned int)(cchBuf - 1) > 0x7FFFFFFE )
        {
          v10 = -2147024809;
          if ( cchBuf )
            *(_WORD *)pszDst = 0;
        }
        else
        {
          v16 = pszDst;
          do
          {
            if ( !v14 )
              break;
            if ( !*v13 )
              break;
            *(_WORD *)v16 = *v13++;
            v16 += 2;
            --v14;
            --v15;
          }
          while ( v15 );
          v17 = v16 - 2;
          if ( v15 )
            v17 = v16;
          v10 = v15 == 0 ? 0x8007007A : 0;
          *v17 = 0;
        }
      }
      else
      {
        return SHUnicodeToAnsi(*v11, pszDst, cchBuf) == 0 ? 0x80004005 : 0;
      }
      return (unsigned int)v10;
    }
    if ( a3 != 5 )
    {
      if ( a3 != 6 )
        return (unsigned int)-2147467263;
      return 0;
    }
  }
  if ( (int)CContextMenuOverExplorerCommands::_EnsureShellItemArray((CContextMenuOverExplorerCommands *)(this - 4)) >= 0 )
  {
    v19 = this[2];
    v20 = this[7];
    ppwsz = 0;
    v10 = (*(__int64 (__fastcall **)(LPCWSTR, LPCWSTR, LPWSTR *))(*(_QWORD *)v19 + 40LL))(v19, v20, &ppwsz);
    if ( v10 >= 0 )
    {
      if ( a3 == 1 )
        v10 = SHUnicodeToAnsi(ppwsz, pszDst, cchBuf) == 0 ? 0x80004005 : 0;
      else
        v10 = StringCchCopyW((unsigned __int16 *)pszDst, (unsigned int)cchBuf, ppwsz);
      CoTaskMemFree(ppwsz);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014c90  push    rbx
0x180014c92  push    rbp
0x180014c93  push    rsi
0x180014c94  push    rdi
0x180014c95  push    r12
0x180014c97  push    r13
0x180014c99  push    r14
0x180014c9b  push    r15
0x180014c9d  sub     rsp, 48h
0x180014ca1  mov     rdi, rcx
0x180014ca4  mov     r13, r9
0x180014ca7  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x180014cab  mov     esi, r8d
0x180014cae  mov     r14, rdx
0x180014cb1  call    ?_EnsureParentCommand@CContextMenuOverExplorerCommands@@AEAAJXZ; CContextMenuOverExplorerCommands::_EnsureParentCommand(void)
0x180014cb6  xor     r10d, r10d
0x180014cb9  mov     ebx, eax
0x180014cbb  test    eax, eax
0x180014cbd  js      loc_180014D73
0x180014cc3  cmp     r14, 10000h
0x180014cca  jnb     loc_180014D86
0x180014cd0  cmp     [rdi+50h], r14d
0x180014cd4  lea     r15, [rdi+40h]
0x180014cd8  mov     ebp, r10d
0x180014cdb  setz    bpl
0x180014cdf  test    ebp, ebp
0x180014ce1  jz      loc_180014F08
0x180014ce7  mov     eax, esi
0x180014ce9  test    esi, esi
0x180014ceb  jz      short loc_180014D08
0x180014ced  sub     eax, 1
0x180014cf0  jz      loc_180014E1A
0x180014cf6  sub     eax, 1
0x180014cf9  jz      loc_180014E12
0x180014cff  sub     eax, 2
0x180014d02  jnz     loc_180014DFE
0x180014d08  mov     r9, [r15]
0x180014d0b  test    esi, esi
0x180014d0d  jz      loc_180014EBF
0x180014d13  mov     eax, [rsp+88h+cchBuf]
0x180014d1a  mov     ecx, 7FFFFFFEh
0x180014d1f  mov     edx, eax
0x180014d21  dec     eax
0x180014d23  cmp     eax, ecx
0x180014d25  ja      loc_180014EE9
0x180014d2b  mov     rax, [rsp+88h+pszDst]
0x180014d33  test    rcx, rcx
0x180014d36  jz      short loc_180014D57
0x180014d38  movzx   r8d, word ptr [r9]
0x180014d3c  test    r8w, r8w
0x180014d40  jz      short loc_180014D57
0x180014d42  mov     [rax], r8w
0x180014d46  add     r9, 2
0x180014d4a  add     rax, 2
0x180014d4e  dec     rcx
0x180014d51  sub     rdx, 1
0x180014d55  jnz     short loc_180014D33
0x180014d57  test    rdx, rdx
0x180014d5a  lea     rcx, [rax-2]
0x180014d5e  cmovnz  rcx, rax
0x180014d62  neg     rdx
0x180014d65  sbb     ebx, ebx
0x180014d67  not     ebx
0x180014d69  and     ebx, 8007007Ah
0x180014d6f  mov     [rcx], r10w
0x180014d73  mov     eax, ebx
0x180014d75  add     rsp, 48h
0x180014d79  pop     r15
0x180014d7b  pop     r14
0x180014d7d  pop     r13
0x180014d7f  pop     r12
0x180014d81  pop     rdi
0x180014d82  pop     rsi
0x180014d83  pop     rbp
0x180014d84  pop     rbx
0x180014d85  retn
0x180014d86  mov     rcx, r14; psz
0x180014d89  test    sil, 4
0x180014d8d  jz      short loc_180014DAD
0x180014d8f  lea     r15, [rdi+40h]
0x180014d93  mov     rdx, [r15]; pszStr2
0x180014d96  call    cs:__imp_StrCmpICW
0x180014d9c  xor     r10d, r10d
0x180014d9f  test    eax, eax
0x180014da1  mov     ebp, r10d
0x180014da4  setz    bpl
0x180014da8  jmp     loc_180014CDF
0x180014dad  lea     rdx, [rsp+88h+ppwsz]; ppwsz
0x180014db5  mov     [rsp+88h+ppwsz], r10
0x180014dbd  call    cs:__imp_SHStrDupA
0x180014dc3  test    eax, eax
0x180014dc5  js      loc_180014F08
0x180014dcb  mov     rcx, [rsp+88h+ppwsz]; pszStr1
0x180014dd3  lea     r15, [rdi+40h]
0x180014dd7  mov     rdx, [r15]; pszStr2
0x180014dda  call    cs:__imp_StrCmpICW
0x180014de0  mov     rcx, [rsp+88h+ppwsz]; pv
0x180014de8  xor     ebp, ebp
0x180014dea  test    eax, eax
0x180014dec  setz    bpl
0x180014df0  call    cs:__imp_CoTaskMemFree
0x180014df6  xor     r10d, r10d
0x180014df9  jmp     loc_180014CDF
0x180014dfe  sub     eax, 1
0x180014e01  jz      short loc_180014E1A
0x180014e03  cmp     eax, 1
0x180014e06  jz      short loc_180014E12
0x180014e08  mov     ebx, 80004001h
0x180014e0d  jmp     loc_180014D73
0x180014e12  mov     ebx, r10d
0x180014e15  jmp     loc_180014D73
0x180014e1a  lea     rcx, [rdi-20h]; this
0x180014e1e  call    ?_EnsureShellItemArray@CContextMenuOverExplorerCommands@@AEAAJXZ; CContextMenuOverExplorerCommands::_EnsureShellItemArray(void)
0x180014e23  test    eax, eax
0x180014e25  js      loc_180014D73
0x180014e2b  mov     rcx, [rdi+10h]
0x180014e2f  lea     r8, [rsp+88h+ppwsz]
0x180014e37  mov     rdx, [rdi+38h]
0x180014e3b  mov     [rsp+88h+ppwsz], 0
0x180014e47  mov     rax, [rcx]
0x180014e4a  mov     rax, [rax+28h]
0x180014e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e53  mov     ebx, eax
0x180014e55  test    eax, eax
0x180014e57  js      loc_180014D73
0x180014e5d  cmp     esi, 1
0x180014e60  jnz     short loc_180014E8E
0x180014e62  mov     r8d, [rsp+88h+cchBuf]; cchBuf
0x180014e6a  mov     rdx, [rsp+88h+pszDst]; pszDst
0x180014e72  mov     rcx, [rsp+88h+ppwsz]; pwszSrc
0x180014e7a  call    cs:__imp_SHUnicodeToAnsi
0x180014e80  neg     eax
0x180014e82  sbb     ebx, ebx
0x180014e84  not     ebx
0x180014e86  and     ebx, 80004005h
0x180014e8c  jmp     short loc_180014EAC
0x180014e8e  mov     edx, [rsp+88h+cchBuf]; unsigned __int64
0x180014e95  mov     r8, [rsp+88h+ppwsz]; unsigned __int16 *
0x180014e9d  mov     rcx, [rsp+88h+pszDst]; unsigned __int16 *
0x180014ea5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014eaa  mov     ebx, eax
0x180014eac  mov     rcx, [rsp+88h+ppwsz]; pv
0x180014eb4  call    cs:__imp_CoTaskMemFree
0x180014eba  jmp     loc_180014D73
0x180014ebf  mov     r8d, [rsp+88h+cchBuf]; cchBuf
0x180014ec7  mov     rcx, r9; pwszSrc
0x180014eca  mov     rdx, [rsp+88h+pszDst]; pszDst
0x180014ed2  call    cs:__imp_SHUnicodeToAnsi
0x180014ed8  neg     eax
0x180014eda  sbb     ebx, ebx
0x180014edc  not     ebx
0x180014ede  and     ebx, 80004005h
0x180014ee4  jmp     loc_180014D73
0x180014ee9  mov     ebx, 80070057h
0x180014eee  test    rdx, rdx
0x180014ef1  jz      loc_180014D73
0x180014ef7  mov     rax, [rsp+88h+pszDst]
0x180014eff  mov     [rax], r10w
0x180014f03  jmp     loc_180014D73
0x180014f08  mov     rcx, [rdi+20h]
0x180014f0c  test    rcx, rcx
0x180014f0f  jz      short loc_180014F45
0x180014f11  mov     rax, [rcx]
0x180014f14  mov     r9, r13
0x180014f17  mov     edx, [rsp+88h+cchBuf]
0x180014f1e  mov     r8d, esi
0x180014f21  mov     [rsp+88h+var_60], edx
0x180014f25  mov     rdx, [rsp+88h+pszDst]
0x180014f2d  mov     rax, [rax+28h]
0x180014f31  mov     [rsp+88h+var_68], rdx
0x180014f36  mov     rdx, r14
0x180014f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f3e  mov     ebx, eax
0x180014f40  jmp     loc_180014D73
0x180014f45  mov     ebx, 80004005h
0x180014f4a  jmp     loc_180014D73
```
