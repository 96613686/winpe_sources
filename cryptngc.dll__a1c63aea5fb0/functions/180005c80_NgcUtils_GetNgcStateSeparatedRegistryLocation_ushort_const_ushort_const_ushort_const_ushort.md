# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180005c80`
- end: `0x180006148`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `1224`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e764`

## callees

- `0x180005c80`
- `0x180006538`
- `0x180028418`
- `0x180031894`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005dd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005dfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005dd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005dfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005cd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005cd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e6d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005cb7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005d0e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005cb7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005d0e`

## string_xrefs

- `0x180005dba`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180005e8e`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800060a5`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800060ce`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180005d98`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180005de6`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180005ed7`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x1800060fa`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180006118`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v9; // ebx
  _BYTE *v10; // rax
  _WORD *v11; // rdi
  _BYTE *i; // rcx
  unsigned int v13; // eax
  __int64 v14; // r8
  _WORD *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // esi
  __int64 v18; // rdx
  const unsigned __int16 *v19; // r15
  const unsigned __int16 *v20; // rax
  const char *v21; // r9
  __int64 v22; // rdx
  _WORD *v24; // rbx
  const unsigned __int16 *v25; // rax
  unsigned __int64 v26; // rbx
  _WORD *v27; // rbp
  unsigned int v28; // ebx
  __int64 v29; // r10
  _WORD *v30; // rdx
  __int64 v31; // rcx
  unsigned __int64 v32; // r8
  _WORD *v33; // r9
  _WORD *v34; // rcx
  unsigned __int64 v35; // rcx
  _WORD *v36; // rax
  unsigned __int64 v37; // rax
  _WORD *v38; // r8
  __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  _WORD *v41; // rcx
  int v42; // r9d
  unsigned __int64 v43; // rcx
  _WORD *v44; // rax
  _WORD *v45; // rdx
  unsigned __int64 v46; // rbx
  _WORD *v47; // rcx
  int v48; // [rsp+20h] [rbp-38h]
  unsigned int uBytes[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  uBytes[0] = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(this, a2, 0, 0);
  v9 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    v10 = LocalAlloc(0, uBytes[0]);
    v11 = v10;
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)0x8007000ELL,
        (int)uBytes);
      return 2147942414LL;
    }
    for ( i = &v10[uBytes[0]]; v10 != i; ++v10 )
      *v10 = 0;
    v13 = GetPersistedRegistryLocationW(this, a2, v11, uBytes[0]);
    if ( !v13 )
    {
      if ( !a3 )
      {
        *(_QWORD *)a4 = v11;
        return 0;
      }
      v14 = 260;
      v15 = v11;
      v16 = 260;
      while ( *v15 )
      {
        ++v15;
        if ( !--v16 )
        {
          v17 = -2147024809;
          v18 = 179;
          goto LABEL_24;
        }
      }
      v19 = L"\\";
      v20 = L"\\";
      v21 = (const char *)(260 - v16);
      v22 = 260;
      while ( *v20 )
      {
        ++v20;
        if ( !--v22 )
        {
          v17 = -2147024809;
          v18 = 185;
          goto LABEL_24;
        }
      }
      v25 = a3;
      while ( *v25 )
      {
        ++v25;
        if ( !--v14 )
        {
          v17 = -2147024809;
          v18 = 191;
          goto LABEL_24;
        }
      }
      v26 = (unsigned __int64)&v21[260 - v22 - v14 + 261];
      if ( v26 == -1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF89,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v21);
      v27 = LocalAlloc(0, 2 * v26 + 2);
      if ( !v27 )
      {
        v17 = -2147024882;
        v18 = 199;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
          (const char *)v17,
          (int)uBytes);
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
          (const char *)v17,
          v48);
        LocalFree(v11);
        return v17;
      }
      *v27 = 0;
      v27[v26] = 0;
      if ( v26 )
      {
        if ( v26 > 0x7FFFFFFF )
        {
          v17 = -2147024809;
          *v27 = 0;
        }
        else
        {
          v29 = 2147483646;
          v30 = v11;
          v31 = 2147483646;
          v32 = v26;
          v33 = v27;
          do
          {
            if ( !v31 )
              break;
            if ( !*v30 )
              break;
            *v33++ = *v30++;
            --v31;
            --v32;
          }
          while ( v32 );
          v34 = v33 - 1;
          v17 = -2147024774;
          if ( v32 )
          {
            v34 = v33;
            v17 = 0;
          }
          *v34 = 0;
          if ( v32 )
          {
            v35 = v26;
            v36 = v27;
            do
            {
              if ( !*v36 )
                break;
              ++v36;
              --v35;
            }
            while ( v35 );
            v17 = -2147024809;
            if ( v35 )
            {
              v37 = v26 - v35;
              v38 = &v27[v26 - v35];
              v39 = 2147483646;
              v40 = v26 - v37;
              if ( v26 != v37 )
              {
                do
                {
                  if ( !v39 )
                    break;
                  if ( !*v19 )
                    break;
                  *v38++ = *v19++;
                  --v39;
                  --v40;
                }
                while ( v40 );
              }
              v41 = v38 - 1;
              v42 = -2147024774;
              if ( v40 )
              {
                v41 = v38;
                v42 = 0;
              }
              *v41 = 0;
              if ( v40 )
              {
                v43 = v26;
                v44 = v27;
                do
                {
                  if ( !*v44 )
                    break;
                  ++v44;
                  --v43;
                }
                while ( v43 );
                if ( !v43 )
                  goto LABEL_68;
                v45 = &v27[v26 - v43];
                v46 = v43;
                do
                {
                  if ( !v29 )
                    break;
                  if ( !*a3 )
                    break;
                  *v45++ = *a3++;
                  --v29;
                  --v46;
                }
                while ( v46 );
                v47 = v45 - 1;
                v17 = -2147024774;
                if ( v46 )
                {
                  v47 = v45;
                  v17 = 0;
                }
                *v47 = 0;
                if ( !v46 )
                {
LABEL_68:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xD7,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
                    (const char *)v17,
                    (int)uBytes);
                  LocalFree(v27);
                  goto LABEL_16;
                }
                v24 = v27;
                goto LABEL_26;
              }
              v17 = v42;
            }
            else
            {
              v17 = -2147024809;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD2,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
              (const char *)v17,
              (int)uBytes);
            LocalFree(v27);
            goto LABEL_16;
          }
        }
      }
      else
      {
        v17 = -2147024809;
      }
      v24 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
        (const char *)v17,
        (int)uBytes);
      LocalFree(v27);
      if ( (v17 & 0x80000000) != 0 )
        goto LABEL_16;
LABEL_26:
      *(_QWORD *)a4 = v24;
      LocalFree(v11);
      return 0;
    }
    v28 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
            (const char *)v13,
            (unsigned int)uBytes);
    LocalFree(v11);
    return v28;
  }
  else
  {
    if ( PersistedRegistryLocationW > 0 )
      v9 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)v9,
        (int)uBytes);
    return v9;
  }
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_10], rbx
0x180005c85  mov     [rsp+arg_18], rbp
0x180005c8a  push    rsi
0x180005c8b  push    r12
0x180005c8d  push    r14
0x180005c8f  sub     rsp, 40h
0x180005c93  mov     r12, r9
0x180005c96  mov     [rsp+58h+uBytes], 0
0x180005c9e  mov     r14, r8
0x180005ca1  lea     rax, [rsp+58h+uBytes]
0x180005ca6  xor     r9d, r9d
0x180005ca9  mov     qword ptr [rsp+58h+var_38], rax; int
0x180005cae  xor     r8d, r8d
0x180005cb1  mov     rsi, rdx
0x180005cb4  mov     rbp, rcx
0x180005cb7  call    cs:__imp_GetPersistedRegistryLocationW
0x180005cbd  mov     ebx, eax
0x180005cbf  cmp     eax, 0EAh
0x180005cc4  jnz     loc_180005F03
0x180005cca  mov     ebx, [rsp+58h+uBytes]
0x180005cce  xor     ecx, ecx; uFlags
0x180005cd0  mov     edx, ebx; uBytes
0x180005cd2  mov     [rsp+58h+arg_0], rdi
0x180005cd7  call    cs:__imp_LocalAlloc
0x180005cdd  mov     rdi, rax
0x180005ce0  test    rax, rax
0x180005ce3  jz      loc_180005D93
0x180005ce9  lea     rcx, [rbx+rax]
0x180005ced  cmp     rax, rcx
0x180005cf0  jnz     loc_180005EC0
0x180005cf6  mov     r9d, [rsp+58h+uBytes]
0x180005cfb  lea     rax, [rsp+58h+uBytes]
0x180005d00  mov     r8, rdi
0x180005d03  mov     qword ptr [rsp+58h+var_38], rax; int
0x180005d08  mov     rdx, rsi
0x180005d0b  mov     rcx, rbp
0x180005d0e  call    cs:__imp_GetPersistedRegistryLocationW
0x180005d14  test    eax, eax
0x180005d16  jnz     loc_180005ED2
0x180005d1c  mov     [rsp+58h+arg_8], r15
0x180005d21  test    r14, r14
0x180005d24  jz      loc_180005EFD
0x180005d2a  mov     r8d, 104h
0x180005d30  mov     rax, rdi
0x180005d33  mov     ecx, r8d
0x180005d36  cmp     word ptr [rax], 0
0x180005d3a  jz      short loc_180005D55
0x180005d3c  add     rax, 2
0x180005d40  sub     rcx, 1
0x180005d44  jnz     short loc_180005D36
0x180005d46  mov     esi, 80070057h
0x180005d4b  mov     edx, 0B3h
0x180005d50  jmp     loc_180005E89
0x180005d55  lea     r15, asc_180050E74; "\\"
0x180005d5c  mov     r9, r8
0x180005d5f  mov     rax, r15
0x180005d62  sub     r9, rcx; char *
0x180005d65  mov     rdx, r8
0x180005d68  nop     dword ptr [rax+rax+00000000h]
0x180005d70  cmp     word ptr [rax], 0
0x180005d74  jz      loc_180005E23
0x180005d7a  add     rax, 2
0x180005d7e  sub     rdx, 1
0x180005d82  jnz     short loc_180005D70
0x180005d84  mov     esi, 80070057h
0x180005d89  mov     edx, 0B9h
0x180005d8e  jmp     loc_180005E89
0x180005d93  mov     rcx, [rsp+58h]; this
0x180005d98  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005d9f  mov     esi, 8007000Eh
0x180005da4  mov     edx, 0B9h; void *
0x180005da9  mov     r9d, esi; char *
0x180005dac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005db1  mov     eax, esi
0x180005db3  jmp     short loc_180005E0A
0x180005db5  mov     rcx, [rsp+58h]; this
0x180005dba  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005dc1  mov     r9d, esi; char *
0x180005dc4  mov     edx, 0CDh; void *
0x180005dc9  xor     ebx, ebx
0x180005dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005dd0  mov     rcx, rbp; hMem
0x180005dd3  call    cs:__imp_LocalFree
0x180005dd9  test    esi, esi
0x180005ddb  jns     loc_180005EA5
0x180005de1  mov     rcx, [rsp+58h]; this
0x180005de6  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005ded  mov     r9d, esi; char *
0x180005df0  mov     edx, 0C9h; void *
0x180005df5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005dfa  mov     rcx, rdi; hMem
0x180005dfd  call    cs:__imp_LocalFree
0x180005e03  mov     eax, esi
0x180005e05  mov     r15, [rsp+58h+arg_8]
0x180005e0a  mov     rdi, [rsp+58h+arg_0]
0x180005e0f  mov     rbx, [rsp+58h+arg_10]
0x180005e14  mov     rbp, [rsp+58h+arg_18]
0x180005e19  add     rsp, 40h
0x180005e1d  pop     r14
0x180005e1f  pop     r12
0x180005e21  pop     rsi
0x180005e22  retn
0x180005e23  mov     rcx, r8
0x180005e26  mov     rax, r14
0x180005e29  sub     rcx, rdx
0x180005e2c  nop     dword ptr [rax+00h]
0x180005e30  cmp     word ptr [rax], 0
0x180005e34  jz      short loc_180005E4C
0x180005e36  add     rax, 2
0x180005e3a  sub     r8, 1
0x180005e3e  jnz     short loc_180005E30
0x180005e40  mov     esi, 80070057h
0x180005e45  mov     edx, 0BFh
0x180005e4a  jmp     short loc_180005E89
0x180005e4c  sub     rcx, r8
0x180005e4f  lea     rbx, [rcx+105h]
0x180005e56  add     rbx, r9
0x180005e59  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005e5d  jz      loc_180006113
0x180005e63  lea     rdx, ds:2[rbx*2]; uBytes
0x180005e6b  xor     ecx, ecx; uFlags
0x180005e6d  call    cs:__imp_LocalAlloc
0x180005e73  mov     rbp, rax
0x180005e76  test    rax, rax
0x180005e79  jnz     loc_180005F1F
0x180005e7f  mov     esi, 8007000Eh
0x180005e84  mov     edx, 0C7h; void *
0x180005e89  mov     rcx, [rsp+58h]; this
0x180005e8e  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005e95  mov     r9d, esi; char *
0x180005e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e9d  jmp     loc_180005DE1
0x180005ea2  mov     rbx, rbp
0x180005ea5  mov     rcx, rdi; hMem
0x180005ea8  mov     [r12], rbx
0x180005eac  call    cs:__imp_LocalFree
0x180005eb2  xor     eax, eax
0x180005eb4  jmp     loc_180005E05
0x180005ec0  xor     edx, edx
0x180005ec2  mov     [rax], dl
0x180005ec4  inc     rax
0x180005ec7  cmp     rax, rcx
0x180005eca  jz      loc_180005CF6
0x180005ed0  jmp     short loc_180005EC0
0x180005ed2  mov     rcx, [rsp+58h]; this
0x180005ed7  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005ede  mov     r9d, eax; char *
0x180005ee1  mov     edx, 0C0h; void *
0x180005ee6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180005eeb  mov     rcx, rdi; hMem
0x180005eee  mov     ebx, eax
0x180005ef0  call    cs:__imp_LocalFree
0x180005ef6  mov     eax, ebx
0x180005ef8  jmp     loc_180005E0A
0x180005efd  mov     [r12], rdi
0x180005f01  jmp     short loc_180005EB2
0x180005f03  test    eax, eax
0x180005f05  jle     short loc_180005F10
0x180005f07  movzx   ebx, ax
0x180005f0a  or      ebx, 80070000h
0x180005f10  test    ebx, ebx
0x180005f12  js      loc_1800060F5
0x180005f18  mov     eax, ebx
0x180005f1a  jmp     loc_180005E0F
0x180005f1f  xor     eax, eax
0x180005f21  mov     [rbp+0], ax
0x180005f25  mov     [rbp+rbx*2+0], ax
0x180005f2a  test    rbx, rbx
0x180005f2d  jz      loc_180006131
0x180005f33  cmp     rbx, 7FFFFFFFh
0x180005f3a  ja      loc_18000612A
0x180005f40  mov     r10d, 7FFFFFFEh
0x180005f46  mov     rdx, rdi
0x180005f49  mov     ecx, r10d
0x180005f4c  mov     r8, rbx
0x180005f4f  mov     r9, rbp
0x180005f52  test    rcx, rcx
0x180005f55  jz      short loc_180005F74
0x180005f57  movzx   eax, word ptr [rdx]
0x180005f5a  test    ax, ax
0x180005f5d  jz      short loc_180005F74
0x180005f5f  mov     [r9], ax
0x180005f63  add     rdx, 2
0x180005f67  add     r9, 2
0x180005f6b  dec     rcx
0x180005f6e  sub     r8, 1
0x180005f72  jnz     short loc_180005F52
0x180005f74  test    r8, r8
0x180005f77  lea     rcx, [r9-2]
0x180005f7b  mov     esi, 8007007Ah
0x180005f80  cmovnz  rcx, r9
0x180005f84  xor     eax, eax
0x180005f86  test    r8, r8
0x180005f89  cmovnz  esi, eax
0x180005f8c  mov     [rcx], ax
0x180005f8f  jz      loc_180005DB5
0x180005f95  mov     rcx, rbx
0x180005f98  mov     rax, rbp
0x180005f9b  nop     dword ptr [rax+rax+00h]
0x180005fa0  cmp     word ptr [rax], 0
0x180005fa4  jz      short loc_180005FB0
0x180005fa6  add     rax, 2
0x180005faa  sub     rcx, 1
0x180005fae  jnz     short loc_180005FA0
0x180005fb0  xor     eax, eax
0x180005fb2  mov     esi, 80070057h
0x180005fb7  test    rcx, rcx
0x180005fba  mov     edx, esi
0x180005fbc  cmovnz  edx, eax
0x180005fbf  jz      loc_1800060C7
0x180005fc5  mov     rax, rbx
0x180005fc8  sub     rax, rcx
0x180005fcb  test    rcx, rcx
0x180005fce  jz      loc_1800060C7
0x180005fd4  mov     rdx, rbx
0x180005fd7  lea     r8, [rbp+rax*2+0]
0x180005fdc  mov     rcx, r10
0x180005fdf  sub     rdx, rax
0x180005fe2  jz      short loc_180006007
0x180005fe4  test    rcx, rcx
0x180005fe7  jz      short loc_180006007
0x180005fe9  movzx   eax, word ptr [r15]
0x180005fed  test    ax, ax
0x180005ff0  jz      short loc_180006007
0x180005ff2  mov     [r8], ax
0x180005ff6  add     r15, 2
0x180005ffa  add     r8, 2
0x180005ffe  dec     rcx
0x180006001  sub     rdx, 1
0x180006005  jnz     short loc_180005FE4
0x180006007  xor     eax, eax
0x180006009  lea     rcx, [r8-2]
0x18000600d  test    rdx, rdx
0x180006010  mov     r9d, 8007007Ah
0x180006016  cmovnz  rcx, r8
0x18000601a  cmovnz  r9d, eax
0x18000601e  mov     [rcx], ax
0x180006021  jz      loc_1800060F0
0x180006027  mov     rcx, rbx
0x18000602a  mov     rax, rbp
0x18000602d  nop     dword ptr [rax]
0x180006030  cmp     word ptr [rax], 0
0x180006034  jz      short loc_180006040
0x180006036  add     rax, 2
0x18000603a  sub     rcx, 1
0x18000603e  jnz     short loc_180006030
0x180006040  xor     eax, eax
0x180006042  test    rcx, rcx
0x180006045  cmovnz  esi, eax
0x180006048  jz      short loc_1800060A0
0x18000604a  mov     rax, rbx
0x18000604d  sub     rax, rcx
0x180006050  test    rcx, rcx
0x180006053  jz      short loc_1800060A0
0x180006055  lea     rdx, [rbp+rax*2+0]
0x18000605a  sub     rbx, rax
0x18000605d  jz      short loc_180006082
0x18000605f  nop
0x180006060  test    r10, r10
0x180006063  jz      short loc_180006082
0x180006065  movzx   eax, word ptr [r14]
0x180006069  test    ax, ax
0x18000606c  jz      short loc_180006082
0x18000606e  mov     [rdx], ax
0x180006071  add     r14, 2
0x180006075  add     rdx, 2
0x180006079  dec     r10
0x18000607c  sub     rbx, 1
0x180006080  jnz     short loc_180006060
0x180006082  xor     eax, eax
0x180006084  lea     rcx, [rdx-2]
0x180006088  test    rbx, rbx
0x18000608b  mov     esi, 8007007Ah
0x180006090  cmovnz  rcx, rdx
0x180006094  cmovnz  esi, eax
0x180006097  mov     [rcx], ax
0x18000609a  jnz     loc_180005EA2
0x1800060a0  mov     rcx, [rsp+58h]; this
0x1800060a5  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800060ac  mov     r9d, esi; char *
0x1800060af  mov     edx, 0D7h; void *
0x1800060b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060b9  mov     rcx, rbp; hMem
0x1800060bc  call    cs:__imp_LocalFree
0x1800060c2  jmp     loc_180005DE1
0x1800060c7  mov     esi, edx
0x1800060c9  mov     rcx, [rsp+58h]; this
0x1800060ce  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800060d5  mov     r9d, esi; char *
0x1800060d8  mov     edx, 0D2h; void *
0x1800060dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060e2  mov     rcx, rbp; hMem
0x1800060e5  call    cs:__imp_LocalFree
0x1800060eb  jmp     loc_180005DE1
0x1800060f0  mov     esi, r9d
0x1800060f3  jmp     short loc_1800060C9
0x1800060f5  mov     rcx, [rsp+58h]; this
0x1800060fa  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006101  mov     r9d, ebx; char *
0x180006104  mov     edx, 0B6h; void *
  ... truncated ...
```
