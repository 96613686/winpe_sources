# HResultFromFileStatus(ulong,TLMString<64,64,32767> &)

- ea: `0x180004f60`
- end: `0x1800051af`
- name: `?HResultFromFileStatus@@YAJKAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003970`
- `0x1800048f0`
- `0x180006660`

## callees

- `0x180002d80`
- `0x180004f60`
- `0x1800055b0`
- `0x180005720`
- `0x18000b324`
- `0x18000c680`
- `0x18000e7fc`
- `0x18000e878`
- `0x18000fcd0`
- `0x180011135`
- `0x18001e194`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180005000`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180005000`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000514b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000514b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1800050ff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1800050ff`

## string_xrefs

- `0x18000503c`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x18000512a`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HResultFromFileStatus(int a1, __int64 a2)
{
  _WORD *v4; // rdi
  wchar_t *v5; // rcx
  __int64 v6; // rbx
  unsigned __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rsi
  unsigned __int64 v10; // rax
  unsigned int *v11; // rax
  unsigned int v12; // [rsp+20h] [rbp-89h] BYREF
  _DWORD v13[3]; // [rsp+24h] [rbp-85h] BYREF
  void **v14; // [rsp+30h] [rbp-79h] BYREF
  LPWSTR pszPath; // [rsp+38h] [rbp-71h]
  unsigned int v16; // [rsp+40h] [rbp-69h]
  int v17; // [rsp+44h] [rbp-65h]
  wchar_t v18[68]; // [rsp+48h] [rbp-61h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( a1 == 3 )
    goto LABEL_19;
  if ( (unsigned int)a1 <= 0x56 )
  {
    if ( a1 == 86 )
      return 2147750405LL;
    if ( a1 != 2 )
    {
      if ( a1 != 5 )
      {
        if ( a1 != 54 )
        {
          if ( a1 != 58 )
          {
            if ( a1 == 65 )
              return 2147750405LL;
            goto LABEL_15;
          }
          return 2147750406LL;
        }
        return 2147750400LL;
      }
      return 2147750405LL;
    }
LABEL_19:
    if ( GetDriveTypeW(*(LPCWSTR *)(a2 + 8)) != 4 )
    {
      v4 = *(_WORD **)(a2 + 8);
      v14 = &CLMString::`vftable';
      v5 = v18;
      pszPath = v18;
      v16 = 65;
      if ( !v4 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
          (const char *)0x80070057LL,
          v12);
      v6 = -1;
      v7 = -1;
      do
        ++v7;
      while ( v4[v7] );
      v8 = 0xFFFFFFFFLL;
      if ( v7 > 0xFFFFFFFF )
        goto LABEL_41;
      v9 = (unsigned int)v7;
      v12 = v7;
      v10 = (unsigned int)v7 + 1LL;
      if ( v10 > 0xFFFFFFFF )
        goto LABEL_41;
      if ( (unsigned int)v10 > 0x41 )
      {
        v11 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                &v12,
                v13);
        CLMString::GrowInConstructor((CLMString *)&v14, *v11);
        v5 = pszPath;
      }
      v8 = 2 * v9;
      if ( !is_mul_ok(2u, v9) )
LABEL_41:
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v5, v8);
      memcpy_0(v5, v4, (unsigned int)v8);
      v17 = v9;
      pszPath[v9] = 0;
      v14 = &TLMString<64,64,32767>::`vftable';
      if ( v16 < 0x104 )
        TLMString<192,64,32767>::GrowString(&v14, 260);
      if ( PathStripToRootW(pszPath) )
      {
        do
          ++v6;
        while ( pszPath[v6] );
        if ( (unsigned int)v6 >= v16 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0xFE,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            v12);
        v17 = v6;
        pszPath[(unsigned int)v6] = 0;
        if ( !PathFileExistsW(pszPath) )
        {
          v14 = &TLMString<64,64,32767>::`vftable';
          CLMString::DeleteBuf((CLMString *)&v14, v18);
          return 2147750406LL;
        }
        v14 = &TLMString<64,64,32767>::`vftable';
        CLMString::DeleteBuf((CLMString *)&v14, v18);
      }
      else
      {
        TLMString<64,64,32767>::~TLMString<64,64,32767>((wchar_t *)&v14);
      }
    }
    return 2147750401LL;
  }
  switch ( a1 )
  {
    case 148:
    case 170:
      return 2147750400LL;
    case 1251:
      return 2147750406LL;
    case 1326:
      return 2147750405LL;
    case 4350:
      return 2147750406LL;
  }
LABEL_15:
  if ( a1 > 0 )
    return (unsigned __int16)a1 | 0x80070000;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180004f60  push    rbp
0x180004f62  push    rbx
0x180004f63  push    rsi
0x180004f64  push    rdi
0x180004f65  lea     rbp, [rsp-3Fh]
0x180004f6a  sub     rsp, 0E8h
0x180004f71  mov     rax, cs:__security_cookie
0x180004f78  xor     rax, rsp
0x180004f7b  mov     [rbp+57h+var_30], rax
0x180004f7f  mov     rdi, rdx
0x180004f82  cmp     ecx, 3
0x180004f85  jz      short loc_180004FFC
0x180004f87  cmp     ecx, 56h ; 'V'
0x180004f8a  ja      short loc_180004FB5
0x180004f8c  jz      short loc_180004FAB
0x180004f8e  cmp     ecx, 2
0x180004f91  jz      short loc_180004FFC
0x180004f93  cmp     ecx, 5
0x180004f96  jz      short loc_180004FAB
0x180004f98  cmp     ecx, 36h ; '6'
0x180004f9b  jz      short loc_180004FF2
0x180004f9d  cmp     ecx, 3Ah ; ':'
0x180004fa0  jz      loc_180005197
0x180004fa6  cmp     ecx, 41h ; 'A'
0x180004fa9  jnz     short loc_180004FDE
0x180004fab  mov     eax, 80041205h
0x180004fb0  jmp     loc_18000516D
0x180004fb5  mov     eax, ecx
0x180004fb7  sub     eax, 94h
0x180004fbc  jz      short loc_180004FF2
0x180004fbe  sub     eax, 16h
0x180004fc1  jz      short loc_180004FF2
0x180004fc3  sub     eax, 439h
0x180004fc8  jz      loc_180005197
0x180004fce  sub     eax, 4Bh ; 'K'
0x180004fd1  jz      short loc_180004FAB
0x180004fd3  cmp     eax, 0BD0h
0x180004fd8  jz      loc_180005197
0x180004fde  test    ecx, ecx
0x180004fe0  jle     short loc_180004FEB
0x180004fe2  movzx   ecx, cx
0x180004fe5  or      ecx, 80070000h
0x180004feb  mov     eax, ecx
0x180004fed  jmp     loc_18000516D
0x180004ff2  mov     eax, 80041200h
0x180004ff7  jmp     loc_18000516D
0x180004ffc  mov     rcx, [rdx+8]; lpRootPathName
0x180005000  call    cs:__imp_GetDriveTypeW
0x180005006  cmp     eax, 4
0x180005009  jz      loc_180005168
0x18000500f  mov     rdi, [rdi+8]
0x180005013  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000501a  mov     [rbp+57h+var_D0], rax
0x18000501e  lea     rcx, [rbp+57h+var_B8]
0x180005022  mov     [rbp+57h+pszPath], rcx
0x180005026  mov     [rbp+57h+var_C0], 41h ; 'A'
0x18000502d  test    rdi, rdi
0x180005030  jnz     short loc_18000504E
0x180005032  mov     rcx, [rbp+5Fh]; this
0x180005036  mov     r9d, 80070057h; char *
0x18000503c  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180005043  mov     edx, 91h; void *
0x180005048  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000504e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005055  mov     rax, rbx
0x180005058  nop     dword ptr [rax+rax+00000000h]
0x180005060  inc     rax
0x180005063  cmp     word ptr [rdi+rax*2], 0
0x180005068  jnz     short loc_180005060
0x18000506a  mov     edx, 0FFFFFFFFh
0x18000506f  cmp     rax, rdx
0x180005072  ja      loc_1800051A9
0x180005078  mov     esi, eax
0x18000507a  mov     [rsp+100h+var_E0], esi; unsigned int
0x18000507e  lea     rax, [rsi+1]
0x180005082  cmp     rax, rdx
0x180005085  ja      loc_1800051A9
0x18000508b  cmp     eax, 41h ; 'A'
0x18000508e  jbe     short loc_1800050AE
0x180005090  lea     rdx, [rsp+100h+var_DC]
0x180005095  lea     rcx, [rsp+100h+var_E0]
0x18000509a  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18000509f  mov     edx, [rax]; unsigned int
0x1800050a1  lea     rcx, [rbp+57h+var_D0]; this
0x1800050a5  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x1800050aa  mov     rcx, [rbp+57h+pszPath]; void *
0x1800050ae  lea     rdx, [rsi+rsi]
0x1800050b2  mov     rax, rdx
0x1800050b5  shr     rax, 20h
0x1800050b9  test    eax, eax
0x1800050bb  jnz     loc_1800051A9
0x1800050c1  mov     r8d, edx; Size
0x1800050c4  mov     rdx, rdi; Src
0x1800050c7  call    memcpy_0
0x1800050cc  mov     [rbp+57h+var_BC], esi
0x1800050cf  xor     ecx, ecx
0x1800050d1  mov     rax, [rbp+57h+pszPath]
0x1800050d5  mov     [rax+rsi*2], cx
0x1800050d9  lea     rdi, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x1800050e0  mov     [rbp+57h+var_D0], rdi
0x1800050e4  cmp     [rbp+57h+var_C0], 104h
0x1800050eb  jnb     short loc_1800050FB
0x1800050ed  mov     edx, 104h
0x1800050f2  lea     rcx, [rbp+57h+var_D0]
0x1800050f6  call    ?GrowString@?$TLMString@$0MA@$0EA@$0HPPP@@@EEAAXI@Z; TLMString<192,64,32767>::GrowString(uint)
0x1800050fb  mov     rcx, [rbp+57h+pszPath]; pszPath
0x1800050ff  call    cs:__imp_PathStripToRootW
0x180005105  test    eax, eax
0x180005107  jz      loc_18000519E
0x18000510d  mov     rdx, [rbp+57h+pszPath]
0x180005111  inc     rbx
0x180005114  cmp     word ptr [rdx+rbx*2], 0
0x180005119  jnz     short loc_180005111
0x18000511b  cmp     ebx, [rbp+57h+var_C0]
0x18000511e  jb      short loc_18000513C
0x180005120  mov     rcx, [rbp+5Fh]; this
0x180005124  mov     r9d, 0CEh; char *
0x18000512a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180005131  mov     edx, 0FEh; void *
0x180005136  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000513c  mov     [rbp+57h+var_BC], ebx
0x18000513f  mov     ecx, ebx
0x180005141  xor     eax, eax
0x180005143  mov     [rdx+rcx*2], ax
0x180005147  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18000514b  call    cs:__imp_PathFileExistsW
0x180005151  nop
0x180005152  test    eax, eax
0x180005154  jz      short loc_180005185
0x180005156  mov     [rbp+57h+var_D0], rdi
0x18000515a  lea     rdx, [rbp+57h+var_B8]; wchar_t *
0x18000515e  lea     rcx, [rbp+57h+var_D0]; this
0x180005162  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180005167  nop
0x180005168  mov     eax, 80041201h
0x18000516d  mov     rcx, [rbp+57h+var_30]
0x180005171  xor     rcx, rsp; StackCookie
0x180005174  call    __security_check_cookie
0x180005179  add     rsp, 0E8h
0x180005180  pop     rdi
0x180005181  pop     rsi
0x180005182  pop     rbx
0x180005183  pop     rbp
0x180005184  retn
0x180005185  mov     [rbp+57h+var_D0], rdi
0x180005189  lea     rdx, [rbp+57h+var_B8]; wchar_t *
0x18000518d  lea     rcx, [rbp+57h+var_D0]; this
0x180005191  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180005196  nop
0x180005197  mov     eax, 80041206h
0x18000519c  jmp     short loc_18000516D
0x18000519e  lea     rcx, [rbp+57h+var_D0]
0x1800051a2  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800051a7  jmp     short loc_180005168
0x1800051a9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
