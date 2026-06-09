# CRegistry::GetValue(wchar_t const *,CLMString &)

- ea: `0x180005ee0`
- end: `0x1800061c0`
- name: `?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z`
- size: `736`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, struct CLMString *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052a0`
- `0x18000ec40`

## callees

- `0x180002eb4`
- `0x180005ee0`
- `0x18000fcd0`
- `0x18001e194`
- `0x18001e230`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006091`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006091`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005fe1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005fe1`

## string_xrefs

- `0x180005fb5`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x180006014`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x180006033`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18000615c`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, LPBYTE *a3)
{
  HKEY v6; // rcx
  LSTATUS v7; // eax
  WCHAR *v8; // r8
  unsigned int v9; // r14d
  WCHAR *Buffer; // rax
  DWORD v11; // eax
  unsigned int v12; // eax
  _DWORD *v13; // r15
  DWORD v14; // ecx
  unsigned __int64 v15; // rbx
  WCHAR *v16; // rdx
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // r9
  WCHAR v20; // ax
  DWORD v21; // eax
  DWORD v22; // ecx
  unsigned int lpData; // [rsp+20h] [rbp-268h]
  DWORD cbData; // [rsp+30h] [rbp-258h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-254h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  SetLastError(0);
  Type[0] = 0;
  v6 = (HKEY)*((_QWORD *)this + 22);
  if ( !v6 )
  {
    SetLastError(6u);
    return 0;
  }
  cbData = 520;
  v7 = RegQueryValueExW(v6, a2, 0, Type, (LPBYTE)Data, &cbData);
  v9 = v7;
  if ( v7 && v7 != 234 || Type[0] - 1 > 1 && Type[0] != 7 )
  {
    SetLastError(v7);
    return 0;
  }
  try
  {
    if ( Type[0] == 2 )
    {
      if ( v7 == 234 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      Buffer = CLMString::GetBuffer((CLMString *)a3, 260);
      v11 = ExpandEnvironmentStringsW(Data, Buffer, 0x104u);
      cbData = v11;
      if ( v11 - 1 > 0x102 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      v12 = 2 * v11;
      cbData = v12;
      v13 = a3 + 2;
    }
    else
    {
      v13 = a3 + 2;
      v14 = *((_DWORD *)a3 + 4);
      if ( v7 == 234 )
      {
        if ( cbData >> 1 > v14 )
          (*(void (__fastcall **)(LPBYTE *))*a3)(a3);
        v9 = RegQueryValueExW(*((HKEY *)this + 22), a2, 0, Type, a3[1], &cbData);
        v12 = cbData;
      }
      else
      {
        v12 = cbData;
        v15 = cbData;
        v16 = (WCHAR *)(cbData >> 1);
        if ( (unsigned int)v16 > v14 )
        {
          (*(void (__fastcall **)(LPBYTE *))*a3)(a3);
          v12 = cbData;
        }
        v17 = v15 >> 1;
        if ( v17 )
        {
          v18 = 2147483646;
          v16 = Data;
          v8 = (WCHAR *)a3[1];
          v19 = 0;
          while ( v18 )
          {
            v20 = *v16;
            if ( !*v16 )
              break;
            ++v16;
            *v8++ = v20;
            --v18;
            if ( !--v17 )
            {
              --v8;
              v19 = 2147942522LL;
              break;
            }
          }
          *v8 = 0;
          v12 = cbData;
        }
        else
        {
          v19 = 2147942487LL;
        }
        if ( (int)v19 < 0 )
          wil::details::in1diag3::_Throw_Hr(retaddr, v16, (__int64)v8, (const char *)v19, lpData);
      }
    }
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
        (const char *)v9,
        lpData);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>();
  }
  v21 = v12 >> 1;
  cbData = v21;
  if ( v21 )
  {
    v22 = v21 - 1;
    if ( v21 - 1 > *v13 - 1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        lpData);
    *((_DWORD *)a3 + 5) = v22;
    *(_WORD *)&a3[1][2 * v22] = 0;
    return 1;
  }
  else
  {
    *((_DWORD *)a3 + 5) = 0;
    *(_WORD *)a3[1] = 0;
    return 1;
  }
}

```

## disassembly

```asm
0x180005ee0  mov     [rsp+arg_18], rbx
0x180005ee5  push    rsi
0x180005ee6  push    rdi
0x180005ee7  push    r12
0x180005ee9  push    r14
0x180005eeb  push    r15
0x180005eed  sub     rsp, 260h
0x180005ef4  mov     rax, cs:__security_cookie
0x180005efb  xor     rax, rsp
0x180005efe  mov     [rsp+288h+var_38], rax
0x180005f06  mov     rsi, r8
0x180005f09  mov     rbx, rdx
0x180005f0c  mov     rdi, rcx
0x180005f0f  xor     ecx, ecx; dwErrCode
0x180005f11  call    cs:__imp_SetLastError
0x180005f17  xor     r12d, r12d
0x180005f1a  mov     [rsp+288h+Type], r12d
0x180005f1f  mov     rcx, [rdi+0B0h]; hKey
0x180005f26  test    rcx, rcx
0x180005f29  jnz     short loc_180005F3B
0x180005f2b  mov     ecx, 6; dwErrCode
0x180005f30  call    cs:__imp_SetLastError
0x180005f36  jmp     loc_180006196
0x180005f3b  mov     [rsp+288h+cbData], 208h
0x180005f43  lea     rax, [rsp+288h+cbData]
0x180005f48  mov     [rsp+288h+lpcbData], rax; lpcbData
0x180005f4d  lea     rax, [rsp+288h+Data]
0x180005f52  mov     [rsp+288h+lpData], rax; unsigned int
0x180005f57  lea     r9, [rsp+288h+Type]; lpType
0x180005f5c  xor     r8d, r8d; lpReserved
0x180005f5f  mov     rdx, rbx; lpValueName
0x180005f62  call    cs:__imp_RegQueryValueExW
0x180005f68  mov     r14d, eax
0x180005f6b  test    eax, eax
0x180005f6d  jz      short loc_180005F76
0x180005f6f  cmp     eax, 0EAh
0x180005f74  jnz     short loc_180005F87
0x180005f76  mov     ecx, [rsp+288h+Type]
0x180005f7a  lea     eax, [rcx-1]
0x180005f7d  cmp     eax, 1
0x180005f80  jbe     short loc_180005F95
0x180005f82  cmp     ecx, 7
0x180005f85  jz      short loc_180005F95
0x180005f87  mov     ecx, r14d; dwErrCode
0x180005f8a  call    cs:__imp_SetLastError
0x180005f90  jmp     loc_180006196
0x180005f95  cmp     ecx, 2
0x180005f98  jnz     loc_180006044
0x180005f9e  cmp     r14d, 0EAh
0x180005fa5  jnz     short loc_180005FC6
0x180005fa7  mov     rcx, [rsp+288h]; this
0x180005faf  mov     r9d, 0CEh; char *
0x180005fb5  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180005fbc  mov     edx, 2E3h; void *
0x180005fc1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180005fc6  mov     edx, 104h; int
0x180005fcb  mov     rcx, rsi; this
0x180005fce  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180005fd3  mov     r8d, 104h; nSize
0x180005fd9  mov     rdx, rax; lpDst
0x180005fdc  lea     rcx, [rsp+288h+Data]; lpSrc
0x180005fe1  call    cs:__imp_ExpandEnvironmentStringsW
0x180005fe7  mov     [rsp+288h+cbData], eax
0x180005feb  lea     ecx, [rax-1]
0x180005fee  cmp     ecx, 102h
0x180005ff4  ja      short loc_180006025
0x180005ff6  add     eax, eax
0x180005ff8  mov     [rsp+288h+cbData], eax
0x180005ffc  lea     r15, [rsi+10h]
0x180006000  test    r14d, r14d
0x180006003  jz      loc_18000613A
0x180006009  mov     rcx, [rsp+288h]; this
0x180006011  mov     r9d, r14d; char *
0x180006014  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000601b  mov     edx, 2FDh; void *
0x180006020  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180006025  mov     rcx, [rsp+288h]; this
0x18000602d  mov     r9d, 0CEh; char *
0x180006033  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000603a  mov     edx, 2E9h; void *
0x18000603f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180006044  lea     r15, [rsi+10h]
0x180006048  mov     ecx, [r15]
0x18000604b  cmp     r14d, 0EAh
0x180006052  jnz     short loc_1800060A3
0x180006054  mov     edx, [rsp+288h+cbData]
0x180006058  shr     edx, 1
0x18000605a  cmp     edx, ecx
0x18000605c  jbe     short loc_18000606C
0x18000605e  mov     rax, [rsi]
0x180006061  mov     rcx, rsi
0x180006064  mov     rax, [rax]
0x180006067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606c  lea     rax, [rsp+288h+cbData]
0x180006071  mov     [rsp+288h+lpcbData], rax; lpcbData
0x180006076  mov     rax, [rsi+8]
0x18000607a  mov     [rsp+288h+lpData], rax; lpData
0x18000607f  lea     r9, [rsp+288h+Type]; lpType
0x180006084  xor     r8d, r8d; lpReserved
0x180006087  mov     rdx, rbx; lpValueName
0x18000608a  mov     rcx, [rdi+0B0h]; hKey
0x180006091  call    cs:__imp_RegQueryValueExW
0x180006097  mov     r14d, eax
0x18000609a  mov     eax, [rsp+288h+cbData]
0x18000609e  jmp     loc_180006000
0x1800060a3  mov     eax, [rsp+288h+cbData]
0x1800060a7  mov     ebx, eax
0x1800060a9  mov     edx, eax
0x1800060ab  shr     edx, 1
0x1800060ad  cmp     edx, ecx
0x1800060af  jbe     short loc_1800060C3
0x1800060b1  mov     rax, [rsi]
0x1800060b4  mov     rcx, rsi
0x1800060b7  mov     rax, [rax]
0x1800060ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bf  mov     eax, [rsp+288h+cbData]
0x1800060c3  shr     rbx, 1
0x1800060c6  jz      short loc_18000611D
0x1800060c8  mov     ecx, 7FFFFFFEh
0x1800060cd  lea     rdx, [rsp+288h+Data]
0x1800060d2  mov     r8, [rsi+8]
0x1800060d6  mov     r9d, r12d
0x1800060d9  nop     dword ptr [rax+00000000h]
0x1800060e0  test    rcx, rcx
0x1800060e3  jz      short loc_180006113
0x1800060e5  movzx   eax, word ptr [rdx]
0x1800060e8  test    ax, ax
0x1800060eb  jz      short loc_180006104
0x1800060ed  add     rdx, 2
0x1800060f1  mov     [r8], ax
0x1800060f5  add     r8, 2
0x1800060f9  dec     rcx
0x1800060fc  sub     rbx, 1
0x180006100  jnz     short loc_1800060E0
0x180006102  jmp     short loc_180006109
0x180006104  test    rbx, rbx
0x180006107  jnz     short loc_180006113
0x180006109  sub     r8, 2
0x18000610d  mov     r9d, 8007007Ah
0x180006113  mov     [r8], r12w
0x180006117  mov     eax, [rsp+288h+cbData]
0x18000611b  jmp     short loc_180006123
0x18000611d  mov     r9d, 80070057h; char *
0x180006123  mov     rcx, [rsp+288h]; this
0x18000612b  test    r9d, r9d
0x18000612e  jns     loc_180006000
0x180006134  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000613a  shr     eax, 1
0x18000613c  mov     [rsp+288h+cbData], eax
0x180006140  jz      short loc_180006183
0x180006142  lea     ecx, [rax-1]
0x180006145  mov     eax, [r15]
0x180006148  dec     eax
0x18000614a  cmp     ecx, eax
0x18000614c  jbe     short loc_18000616E
0x18000614e  mov     rcx, [rsp+288h]; this
0x180006156  mov     r9d, 0CEh; char *
0x18000615c  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180006163  mov     edx, 13Bh; void *
0x180006168  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000616e  mov     [rsi+14h], ecx
0x180006171  mov     edx, ecx
0x180006173  mov     rcx, [rsi+8]
0x180006177  mov     [rcx+rdx*2], r12w
0x18000617c  mov     eax, 1
0x180006181  jmp     short loc_180006198
0x180006183  mov     [rsi+14h], r12d
0x180006187  mov     rcx, [rsi+8]
0x18000618b  mov     [rcx], r12w
0x18000618f  mov     eax, 1
0x180006194  jmp     short loc_180006198
0x180006196  xor     eax, eax
0x180006198  mov     rcx, [rsp+288h+var_38]
0x1800061a0  xor     rcx, rsp; StackCookie
0x1800061a3  call    __security_check_cookie
0x1800061a8  mov     rbx, [rsp+288h+arg_18]
0x1800061b0  add     rsp, 260h
0x1800061b7  pop     r15
0x1800061b9  pop     r14
0x1800061bb  pop     r12
0x1800061bd  pop     rdi
0x1800061be  pop     rsi
0x1800061bf  retn
```
