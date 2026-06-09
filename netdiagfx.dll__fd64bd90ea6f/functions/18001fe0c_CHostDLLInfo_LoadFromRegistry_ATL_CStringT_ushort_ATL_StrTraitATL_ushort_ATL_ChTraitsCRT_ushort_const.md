# CHostDLLInfo::LoadFromRegistry(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18001fe0c`
- end: `0x18002001b`
- name: `?LoadFromRegistry@CHostDLLInfo@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f924`
- `0x180020024`

## callees

- `0x1800017f4`
- `0x180008248`
- `0x18000ff94`
- `0x18001f0a4`
- `0x18001fe0c`
- `0x180021094`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18001fee8`
- `ADVAPI32!RegEnumValueW` at `0x18001fee8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHostDLLInfo::LoadFromRegistry(_QWORD *a1, LPCWSTR *a2)
{
  _QWORD *v2; // r13
  int v3; // eax
  unsigned int v4; // edi
  int v5; // r14d
  DWORD i; // r15d
  int v7; // eax
  HKEY v8; // rax
  __int64 v9; // r12
  __int64 *v10; // rsi
  bool v11; // al
  __int64 v12; // rcx
  __int64 v13; // r12
  int v15; // eax
  int v16; // [rsp+40h] [rbp-298h]
  DWORD cchValueName; // [rsp+44h] [rbp-294h] BYREF
  DWORD v18; // [rsp+48h] [rbp-290h]
  __int64 v19; // [rsp+50h] [rbp-288h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-280h]
  _QWORD *v21; // [rsp+60h] [rbp-278h]
  HKEY hKey[5]; // [rsp+68h] [rbp-270h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-248h] BYREF

  v2 = a1;
  v21 = a1;
  memset(hKey, 0, 24);
  v3 = ATL::CRegKey::Open(hKey, HKEY_LOCAL_MACHINE, *a2, 0x20019u);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v5 = 0;
    v16 = 0;
    cchValueName = 0;
    for ( i = 0; ; ++i )
    {
      v18 = i;
      if ( v4 )
        break;
      cchValueName = 260;
      v7 = RegEnumValueW(hKey[0], i, ValueName, &cchValueName, 0, 0, 0, 0);
      v4 = v7;
      v20 = v7;
      if ( v7 )
      {
        if ( v7 != 259 )
        {
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          if ( v5 >= 0 )
            v5 = v7;
          v16 = v5;
        }
      }
      else
      {
        v19 = 0;
        try
        {
          v8 = (HKEY)operator new(8u);
          hKey[3] = v8;
          if ( v8 )
            v9 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                   (__int64)v8,
                   (__int64)ValueName);
          else
            v9 = 0;
          v19 = v9;
          v10 = v2 + 3;
          v11 = (unsigned __int64)&v19 < v2[4] && *v10 <= (unsigned __int64)&v19;
          v12 = v2[5];
          if ( v11 )
          {
            v13 = *v10;
            if ( v2[4] == v12 )
              std::vector<ProblemNode *>::_Reserve(v2 + 3);
            *(_QWORD *)v2[4] = *(_QWORD *)(*v10 + 8 * (((__int64)&v19 - v13) >> 3));
          }
          else
          {
            if ( v2[4] == v12 )
              std::vector<ProblemNode *>::_Reserve(v2 + 3);
            *(_QWORD *)v2[4] = v9;
          }
          v2[4] += 8LL;
        }
        catch ( exception )
        {
          if ( v19 )
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(
              v19,
              1);
          v15 = v16;
          if ( v16 >= 0 )
            v15 = -2147024882;
          v16 = v15;
          v5 = v15;
          v4 = v20;
          i = v18;
          v2 = v21;
          continue;
        }
      }
    }
    v4 = v5;
  }
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x18001fe0c  mov     [rsp+arg_10], rsi
0x18001fe11  push    rdi
0x18001fe12  push    r12
0x18001fe14  push    r13
0x18001fe16  push    r14
0x18001fe18  push    r15
0x18001fe1a  sub     rsp, 2B0h
0x18001fe21  mov     rax, cs:__security_cookie
0x18001fe28  xor     rax, rsp
0x18001fe2b  mov     [rsp+2D8h+var_38], rax
0x18001fe33  mov     r13, rcx
0x18001fe36  mov     [rsp+2D8h+var_278], rcx
0x18001fe3b  mov     [rsp+2D8h+hKey], 0
0x18001fe44  mov     [rsp+2D8h+var_268], 0
0x18001fe4d  mov     [rsp+2D8h+var_260], 0
0x18001fe56  mov     r9d, 20019h; unsigned int
0x18001fe5c  mov     r8, [rdx]; lpSubKey
0x18001fe5f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001fe66  lea     rcx, [rsp+2D8h+hKey]; this
0x18001fe6b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001fe70  mov     edi, eax
0x18001fe72  test    eax, eax
0x18001fe74  jz      short loc_18001FE8A
0x18001fe76  jle     loc_18001FFE6
0x18001fe7c  movzx   edi, ax
0x18001fe7f  or      edi, 80070000h
0x18001fe85  jmp     loc_18001FFE6
0x18001fe8a  xor     r14d, r14d
0x18001fe8d  mov     [rsp+2D8h+var_298], r14d
0x18001fe92  mov     [rsp+2D8h+cchValueName], r14d
0x18001fe97  xor     r15d, r15d
0x18001fe9a  mov     [rsp+2D8h+var_290], r15d
0x18001fe9f  test    edi, edi
0x18001fea1  jnz     loc_18001FFE3
0x18001fea7  mov     [rsp+2D8h+cchValueName], 104h
0x18001feaf  mov     [rsp+2D8h+lpcbData], 0; lpcbData
0x18001feb8  mov     [rsp+2D8h+lpData], 0; lpData
0x18001fec1  mov     [rsp+2D8h+lpType], 0; lpType
0x18001feca  mov     [rsp+2D8h+lpReserved], 0; lpReserved
0x18001fed3  lea     r9, [rsp+2D8h+cchValueName]; lpcchValueName
0x18001fed8  lea     r8, [rsp+2D8h+ValueName]; lpValueName
0x18001fee0  mov     edx, r15d; dwIndex
0x18001fee3  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18001fee8  call    cs:__imp_RegEnumValueW
0x18001feee  mov     edi, eax
0x18001fef0  mov     [rsp+2D8h+var_280], eax
0x18001fef4  test    eax, eax
0x18001fef6  jnz     loc_18001FFBC
0x18001fefc  mov     [rsp+2D8h+var_288], 0
0x18001ff05  lea     ecx, [rax+8]; Size
0x18001ff08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ff0d  mov     [rsp+2D8h+var_258], rax
0x18001ff15  test    rax, rax
0x18001ff18  jz      short loc_18001FF2F
0x18001ff1a  lea     rdx, [rsp+2D8h+ValueName]
0x18001ff22  mov     rcx, rax
0x18001ff25  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001ff2a  mov     r12, rax
0x18001ff2d  jmp     short loc_18001FF32
0x18001ff2f  xor     r12d, r12d
0x18001ff32  mov     [rsp+2D8h+var_288], r12
0x18001ff37  lea     rsi, [r13+18h]
0x18001ff3b  lea     rax, [rsp+2D8h+var_288]
0x18001ff40  cmp     rax, [rsi+8]
0x18001ff44  jnb     short loc_18001FF54
0x18001ff46  lea     rax, [rsp+2D8h+var_288]
0x18001ff4b  cmp     [rsi], rax
0x18001ff4e  ja      short loc_18001FF54
0x18001ff50  mov     al, 1
0x18001ff52  jmp     short loc_18001FF56
0x18001ff54  xor     al, al
0x18001ff56  mov     rcx, [rsi+10h]
0x18001ff5a  test    al, al
0x18001ff5c  jz      short loc_18001FF8B
0x18001ff5e  mov     r12, [rsi]
0x18001ff61  cmp     [rsi+8], rcx
0x18001ff65  jnz     short loc_18001FF6F
0x18001ff67  mov     rcx, rsi
0x18001ff6a  call    ?_Reserve@?$vector@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@IEAAX_K@Z; std::vector<ProblemNode *>::_Reserve(unsigned __int64)
0x18001ff6f  lea     rdx, [rsp+2D8h+var_288]
0x18001ff74  sub     rdx, r12
0x18001ff77  sar     rdx, 3
0x18001ff7b  mov     rax, [rsi]
0x18001ff7e  mov     rcx, [rsi+8]
0x18001ff82  mov     rax, [rax+rdx*8]
0x18001ff86  mov     [rcx], rax
0x18001ff89  jmp     short loc_18001FFA0
0x18001ff8b  cmp     [rsi+8], rcx
0x18001ff8f  jnz     short loc_18001FF99
0x18001ff91  mov     rcx, rsi
0x18001ff94  call    ?_Reserve@?$vector@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@IEAAX_K@Z; std::vector<ProblemNode *>::_Reserve(unsigned __int64)
0x18001ff99  mov     rax, [rsi+8]
0x18001ff9d  mov     [rax], r12
0x18001ffa0  add     qword ptr [rsi+8], 8
0x18001ffa5  jmp     short loc_18001FFDB
0x18001ffa7  mov     r14d, [rsp+2D8h+var_298]
0x18001ffac  mov     edi, [rsp+2D8h+var_280]
0x18001ffb0  mov     r15d, [rsp+2D8h+var_290]
0x18001ffb5  mov     r13, [rsp+2D8h+var_278]
0x18001ffba  jmp     short loc_18001FFDB
0x18001ffbc  cmp     eax, 103h
0x18001ffc1  jz      short loc_18001FFDB
0x18001ffc3  test    eax, eax
0x18001ffc5  jle     short loc_18001FFCF
0x18001ffc7  movzx   eax, ax
0x18001ffca  or      eax, 80070000h
0x18001ffcf  test    r14d, r14d
0x18001ffd2  cmovns  r14d, eax
0x18001ffd6  mov     [rsp+2D8h+var_298], r14d
0x18001ffdb  inc     r15d
0x18001ffde  jmp     loc_18001FE9A
0x18001ffe3  mov     edi, r14d
0x18001ffe6  lea     rcx, [rsp+2D8h+hKey]; this
0x18001ffeb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fff0  mov     eax, edi
0x18001fff2  mov     rcx, [rsp+2D8h+var_38]
0x18001fffa  xor     rcx, rsp; StackCookie
0x18001fffd  call    __security_check_cookie
0x180020002  mov     rsi, [rsp+2D8h+arg_10]
0x18002000a  add     rsp, 2B0h
0x180020011  pop     r15
0x180020013  pop     r14
0x180020015  pop     r13
0x180020017  pop     r12
0x180020019  pop     rdi
0x18002001a  retn
```
