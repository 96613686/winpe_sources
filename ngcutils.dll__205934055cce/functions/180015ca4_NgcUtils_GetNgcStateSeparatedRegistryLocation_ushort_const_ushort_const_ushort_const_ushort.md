# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180015ca4`
- end: `0x180015e12`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `366`
- prototype: `int(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010b60`
- `0x180013ec4`
- `0x180016be4`
- `0x180017718`
- `0x1800182d4`
- `0x1800183f8`
- `0x1800185d0`
- `0x180018898`
- `0x1800578c0`

## callees

- `0x18000a5b4`
- `0x1800138d4`
- `0x180013dc8`
- `0x180015ca4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015d0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015dc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015dc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015dd6`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015cd5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015d4a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015cd5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015d4a`

## string_xrefs

- `0x180015d59`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180015d9a`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180015df4`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HLOCAL *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _BYTE *v11; // rax
  void *v12; // rbx
  _BYTE *i; // rcx
  unsigned int v14; // eax
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // edi
  int v17; // eax
  int v19; // [rsp+20h] [rbp-58h]
  SIZE_T uBytes; // [rsp+30h] [rbp-48h] BYREF
  HLOCAL hMem[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  LODWORD(uBytes) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(this, a2, 0, 0);
  v9 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    v11 = LocalAlloc(0, (unsigned int)uBytes);
    v12 = v11;
    if ( !v11 )
    {
      v9 = -2147024882;
      v10 = 185;
      goto LABEL_20;
    }
    for ( i = &v11[(unsigned int)uBytes]; v11 != i; ++v11 )
      *v11 = 0;
    v14 = GetPersistedRegistryLocationW(this, a2, v12, (unsigned int)uBytes);
    if ( v14 )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xC0,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
              (const char *)v14,
              (unsigned int)&uBytes);
LABEL_15:
      LocalFree(v12);
      return v16;
    }
    if ( a3 )
    {
      hMem[0] = 0;
      v17 = NgcUtils::CombineSeparateStrings(
              (NgcUtils *)v12,
              v15,
              a3,
              (const unsigned __int16 *)hMem,
              (unsigned __int16 **)&uBytes);
      v16 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
          (const char *)(unsigned int)v17,
          v19);
        if ( hMem[0] )
          LocalFree(hMem[0]);
        goto LABEL_15;
      }
      *a4 = hMem[0];
      LocalFree(v12);
    }
    else
    {
      *a4 = v12;
    }
    return 0;
  }
  if ( PersistedRegistryLocationW > 0 )
    v9 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
    return v9;
  v10 = 182;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
    (const char *)v9,
    (int)&uBytes);
  return v9;
}

```

## disassembly

```asm
0x180015ca4  push    rbx
0x180015ca6  push    rbp
0x180015ca7  push    rsi
0x180015ca8  push    rdi
0x180015ca9  push    r14
0x180015cab  push    r15
0x180015cad  sub     rsp, 48h
0x180015cb1  mov     rsi, r9
0x180015cb4  mov     dword ptr [rsp+78h+uBytes], 0
0x180015cbc  mov     rbp, r8
0x180015cbf  lea     rax, [rsp+78h+uBytes]
0x180015cc4  xor     r9d, r9d
0x180015cc7  mov     qword ptr [rsp+78h+var_58], rax; int
0x180015ccc  xor     r8d, r8d
0x180015ccf  mov     r14, rdx
0x180015cd2  mov     r15, rcx
0x180015cd5  call    cs:__imp_GetPersistedRegistryLocationW
0x180015cdb  mov     ebx, eax
0x180015cdd  cmp     eax, 0EAh
0x180015ce2  jz      short loc_180015D03
0x180015ce4  test    eax, eax
0x180015ce6  jle     short loc_180015CF1
0x180015ce8  movzx   ebx, ax
0x180015ceb  or      ebx, 80070000h
0x180015cf1  test    ebx, ebx
0x180015cf3  jns     loc_180015E03
0x180015cf9  mov     edx, 0B6h
0x180015cfe  jmp     loc_180015DEF
0x180015d03  mov     edi, dword ptr [rsp+78h+uBytes]
0x180015d07  xor     ecx, ecx; uFlags
0x180015d09  mov     edx, edi; uBytes
0x180015d0b  call    cs:__imp_LocalAlloc
0x180015d11  mov     rbx, rax
0x180015d14  test    rax, rax
0x180015d17  jz      loc_180015DE5
0x180015d1d  lea     rcx, [rdi+rax]
0x180015d21  cmp     rax, rcx
0x180015d24  jz      short loc_180015D32
0x180015d26  xor     edx, edx
0x180015d28  mov     [rax], dl
0x180015d2a  inc     rax
0x180015d2d  cmp     rax, rcx
0x180015d30  jnz     short loc_180015D26
0x180015d32  mov     r9d, dword ptr [rsp+78h+uBytes]
0x180015d37  lea     rax, [rsp+78h+uBytes]
0x180015d3c  mov     r8, rbx
0x180015d3f  mov     qword ptr [rsp+78h+var_58], rax; int
0x180015d44  mov     rdx, r14
0x180015d47  mov     rcx, r15
0x180015d4a  call    cs:__imp_GetPersistedRegistryLocationW
0x180015d50  test    eax, eax
0x180015d52  jz      short loc_180015D71
0x180015d54  mov     rcx, [rsp+78h]; this
0x180015d59  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015d60  mov     r9d, eax; char *
0x180015d63  mov     edx, 0C0h; void *
0x180015d68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015d6d  mov     edi, eax
0x180015d6f  jmp     short loc_180015DBE
0x180015d71  test    rbp, rbp
0x180015d74  jz      short loc_180015DDE
0x180015d76  lea     r9, [rsp+78h+hMem]; unsigned __int16 *
0x180015d7b  mov     [rsp+78h+hMem], 0
0x180015d84  mov     r8, rbp; unsigned __int16 *
0x180015d87  mov     rcx, rbx; this
0x180015d8a  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180015d8f  mov     edi, eax
0x180015d91  test    eax, eax
0x180015d93  jns     short loc_180015DCB
0x180015d95  mov     rcx, [rsp+78h]; this
0x180015d9a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015da1  mov     r9d, eax; char *
0x180015da4  mov     edx, 0C9h; void *
0x180015da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015dae  mov     rcx, [rsp+78h+hMem]; hMem
0x180015db3  test    rcx, rcx
0x180015db6  jz      short loc_180015DBE
0x180015db8  call    cs:__imp_LocalFree
0x180015dbe  mov     rcx, rbx; hMem
0x180015dc1  call    cs:__imp_LocalFree
0x180015dc7  mov     eax, edi
0x180015dc9  jmp     short loc_180015E05
0x180015dcb  mov     rax, [rsp+78h+hMem]
0x180015dd0  mov     rcx, rbx; hMem
0x180015dd3  mov     [rsi], rax
0x180015dd6  call    cs:__imp_LocalFree
0x180015ddc  jmp     short loc_180015DE1
0x180015dde  mov     [rsi], rbx
0x180015de1  xor     eax, eax
0x180015de3  jmp     short loc_180015E05
0x180015de5  mov     ebx, 8007000Eh
0x180015dea  mov     edx, 0B9h; void *
0x180015def  mov     rcx, [rsp+78h]; this
0x180015df4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015dfb  mov     r9d, ebx; char *
0x180015dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e03  mov     eax, ebx
0x180015e05  add     rsp, 48h
0x180015e09  pop     r15
0x180015e0b  pop     r14
0x180015e0d  pop     rdi
0x180015e0e  pop     rsi
0x180015e0f  pop     rbp
0x180015e10  pop     rbx
0x180015e11  retn
```
