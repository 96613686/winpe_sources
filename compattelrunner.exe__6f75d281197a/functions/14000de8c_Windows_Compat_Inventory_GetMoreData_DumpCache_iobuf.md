# Windows::Compat::Inventory::GetMoreData::DumpCache(_iobuf *)

- ea: `0x14000de8c`
- end: `0x14000e0b0`
- name: `?DumpCache@GetMoreData@Inventory@Compat@Windows@@CAJPEAU_iobuf@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(FILE *Stream)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000dbdc`

## callees

- `0x140001e90`
- `0x1400026c0`
- `0x14000a194`
- `0x14000d430`
- `0x14000ddf4`
- `0x14000de8c`
- `0x14000fc78`
- `0x1400108cc`
- `0x1400151b0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e082`

## string_xrefs

- `0x14000df3b`: `AmiCache::Initialize failed [%#x]`
- `0x14000df48`: `Windows::Compat::Inventory::GetMoreData::DumpCache`
- `0x14000e005`: `Windows::Compat::Inventory::GetMoreData::DumpCache`
- `0x14000dff8`: `Cache root key is NULL [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Inventory::GetMoreData::DumpCache(FILE *Stream)
{
  FILE *v1; // r14
  unsigned int v2; // esi
  unsigned __int64 *Instance; // rbx
  unsigned int v4; // r14d
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  HKEY *v9; // r12
  unsigned int v10; // r15d
  unsigned __int64 v11; // rcx
  LPCWSTR *v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned int v16; // eax
  int v17; // [rsp+30h] [rbp-68h] BYREF
  int v18; // [rsp+34h] [rbp-64h] BYREF
  HANDLE hHeap[5]; // [rsp+38h] [rbp-60h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-38h]
  int v22; // [rsp+A8h] [rbp+10h]
  unsigned __int64 *v23; // [rsp+B0h] [rbp+18h]

  v1 = Stream;
  v2 = 0;
  RtlStringArray::RtlStringArray((RtlStringArray *)hHeap);
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      Instance = (unsigned __int64 *)Windows::Compat::Inventory::CacheUtilities::AmiCache::GetInstance();
    }
    else
    {
      Instance = (unsigned __int64 *)operator new(0x50u);
      memset_0(Instance, 0, 0x50u);
      *Instance = (unsigned __int64)&Windows::Compat::Inventory::CacheUtilities::AmiCache::`vftable';
      RtlStringArray::RtlStringArray((RtlStringArray *)(Instance + 1));
      *Instance = (unsigned __int64)&Windows::Compat::Inventory::CacheUtilities::HiveCache::`vftable';
      Instance[9] = 0;
    }
    v23 = Instance;
    (*(void (__fastcall **)(unsigned __int64 *, FILE *))(*Instance + 8))(Instance, v1);
  }
  catch ( ulong v17 )
  {
    v16 = v17;
    if ( v17 > 0 )
      v16 = (unsigned __int16)v17 | 0x80070000;
    v22 = v16;
    goto LABEL_6;
  }
  catch ( long v18 )
  {
    v22 = v18;
LABEL_6:
    v2 = v22;
    if ( v22 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::GetMoreData::DumpCache",
        133,
        "AmiCache::Initialize failed [%#x]",
        v22);
      Instance = v23;
      goto LABEL_25;
    }
    v1 = Stream;
    Instance = v23;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v4 = 0;
    v5 = Instance[3];
    if ( v5 )
    {
      do
      {
        v6 = 0;
        if ( v4 < v5 )
        {
          v7 = Instance[2] * v4;
          if ( !is_mul_ok(Instance[2], v4) || (v8 = Instance[6], v6 = (_QWORD *)(v8 + v7), v8 + v7 < v8) )
            v6 = 0;
        }
        (*(void (__fastcall **)(unsigned __int64 *, _QWORD))(*Instance + 48))(Instance, *v6);
        ++v4;
        v5 = Instance[3];
      }
      while ( v4 < v5 );
    }
  }
  else
  {
    v9 = (HKEY *)Instance[9];
    if ( *v9 )
    {
      v10 = 0;
      v11 = Instance[3];
      if ( v11 )
      {
        do
        {
          v12 = 0;
          if ( v10 < v11 )
          {
            v13 = Instance[2] * v10;
            if ( !is_mul_ok(Instance[2], v10) || (v14 = Instance[6], v12 = (LPCWSTR *)(v14 + v13), v14 + v13 < v14) )
              v12 = 0;
          }
          Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessInventoryProviderData(*v9, *v12, v1);
          ++v10;
          v11 = Instance[3];
        }
        while ( v10 < v11 );
      }
    }
    else
    {
      v2 = -2147418113;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::GetMoreData::DumpCache",
        155,
        "Cache root key is NULL [%#x]",
        -2147418113);
    }
  }
LABEL_25:
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( lpMem )
    HeapFree(hHeap[0], 0, lpMem);
  if ( Instance )
    (*(void (__fastcall **)(unsigned __int64 *, __int64))*Instance)(Instance, 1);
  return v2;
}

```

## disassembly

```asm
0x14000de8c  mov     rax, rsp
0x14000de8f  mov     [rax+8], rcx
0x14000de93  push    rbx
0x14000de94  push    rsi
0x14000de95  push    r12
0x14000de97  push    r14
0x14000de99  push    r15
0x14000de9b  sub     rsp, 70h
0x14000de9f  mov     r14, rcx
0x14000dea2  xor     esi, esi
0x14000dea4  mov     [rax+18h], rsi
0x14000dea8  lea     rcx, [rax-60h]; this
0x14000deac  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x14000deb1  nop
0x14000deb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x14000deb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x14000debe  test    al, al
0x14000dec0  jz      short loc_14000DECC
0x14000dec2  call    ?GetInstance@AmiCache@CacheUtilities@Inventory@Compat@Windows@@SAPEAV12345@XZ; Windows::Compat::Inventory::CacheUtilities::AmiCache::GetInstance(void)
0x14000dec7  mov     rbx, rax
0x14000deca  jmp     short loc_14000DF0F
0x14000decc  mov     r15d, 50h ; 'P'
0x14000ded2  mov     ecx, r15d; Size
0x14000ded5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000deda  mov     rbx, rax
0x14000dedd  mov     r8d, r15d; Size
0x14000dee0  xor     edx, edx; Val
0x14000dee2  mov     rcx, rax; void *
0x14000dee5  call    memset_0
0x14000deea  lea     rax, ??_7AmiCache@CacheUtilities@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::CacheUtilities::AmiCache::`vftable'
0x14000def1  mov     [rbx], rax
0x14000def4  lea     rcx, [rbx+8]; this
0x14000def8  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x14000defd  lea     rax, ??_7HiveCache@CacheUtilities@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::CacheUtilities::HiveCache::`vftable'
0x14000df04  mov     [rbx], rax
0x14000df07  mov     qword ptr [rbx+48h], 0
0x14000df0f  mov     rcx, rbx
0x14000df12  mov     [rsp+98h+arg_10], rbx
0x14000df1a  mov     rax, [rbx]
0x14000df1d  mov     rdx, r14
0x14000df20  mov     rax, [rax+8]
0x14000df24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df29  nop
0x14000df2a  jmp     short loc_14000DF76
0x14000df2c  mov     esi, [rsp+98h+arg_8]
0x14000df33  test    esi, esi
0x14000df35  jns     short loc_14000DF66
0x14000df37  mov     [rsp+98h+var_78], esi
0x14000df3b  lea     r9, aAmicacheInitia; "AmiCache::Initialize failed [%#x]"
0x14000df42  mov     r8d, 85h
0x14000df48  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::GetMoreData"...
0x14000df4f  mov     ecx, 1
0x14000df54  call    AslLogCallPrintf
0x14000df59  mov     rbx, [rsp+98h+arg_10]
0x14000df61  jmp     loc_14000E067
0x14000df66  mov     r14, [rsp+98h+arg_0]
0x14000df6e  mov     rbx, [rsp+98h+arg_10]
0x14000df76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x14000df7d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x14000df82  test    al, al
0x14000df84  jz      short loc_14000DFE4
0x14000df86  xor     r14d, r14d
0x14000df89  mov     rcx, [rbx+18h]
0x14000df8d  test    rcx, rcx
0x14000df90  jz      loc_14000E067
0x14000df96  mov     rax, [rbx]
0x14000df99  mov     r8, [rax+30h]
0x14000df9d  mov     eax, r14d
0x14000dfa0  xor     edx, edx
0x14000dfa2  cmp     rax, rcx
0x14000dfa5  jnb     short loc_14000DFC2
0x14000dfa7  mul     qword ptr [rbx+10h]
0x14000dfab  mov     rcx, rax
0x14000dfae  test    rdx, rdx
0x14000dfb1  jnz     short loc_14000DFC0
0x14000dfb3  mov     rax, [rbx+30h]
0x14000dfb7  lea     rdx, [rax+rcx]
0x14000dfbb  cmp     rdx, rax
0x14000dfbe  jnb     short loc_14000DFC2
0x14000dfc0  xor     edx, edx
0x14000dfc2  mov     rdx, [rdx]
0x14000dfc5  mov     rcx, rbx
0x14000dfc8  mov     rax, r8
0x14000dfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfd0  inc     r14d
0x14000dfd3  mov     rcx, [rbx+18h]
0x14000dfd7  mov     eax, r14d
0x14000dfda  cmp     rax, rcx
0x14000dfdd  jb      short loc_14000DF96
0x14000dfdf  jmp     loc_14000E067
0x14000dfe4  mov     r12, [rbx+48h]
0x14000dfe8  cmp     qword ptr [r12], 0
0x14000dfed  jnz     short loc_14000E018
0x14000dfef  mov     esi, 8000FFFFh
0x14000dff4  mov     [rsp+98h+var_78], esi
0x14000dff8  lea     r9, aCacheRootKeyIs; "Cache root key is NULL [%#x]"
0x14000dfff  mov     r8d, 9Bh
0x14000e005  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::GetMoreData"...
0x14000e00c  mov     ecx, 1
0x14000e011  call    AslLogCallPrintf
0x14000e016  jmp     short loc_14000E067
0x14000e018  xor     r15d, r15d
0x14000e01b  mov     rcx, [rbx+18h]
0x14000e01f  test    rcx, rcx
0x14000e022  jz      short loc_14000E067
0x14000e024  mov     eax, r15d
0x14000e027  xor     edx, edx
0x14000e029  cmp     rax, rcx
0x14000e02c  jnb     short loc_14000E049
0x14000e02e  mul     qword ptr [rbx+10h]
0x14000e032  mov     rcx, rax
0x14000e035  test    rdx, rdx
0x14000e038  jnz     short loc_14000E047
0x14000e03a  mov     rax, [rbx+30h]
0x14000e03e  lea     rdx, [rax+rcx]
0x14000e042  cmp     rdx, rax
0x14000e045  jnb     short loc_14000E049
0x14000e047  xor     edx, edx
0x14000e049  mov     r8, r14; Stream
0x14000e04c  mov     rdx, [rdx]; lpSubKey
0x14000e04f  mov     rcx, [r12]; hKey
0x14000e053  call    ?ProcessInventoryProviderData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@SAXPEAUHKEY__@@PEBGPEAU_iobuf@@@Z; Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessInventoryProviderData(HKEY__ *,ushort const *,_iobuf *)
0x14000e058  inc     r15d
0x14000e05b  mov     rcx, [rbx+18h]
0x14000e05f  mov     eax, r15d
0x14000e062  cmp     rax, rcx
0x14000e065  jb      short loc_14000E024
0x14000e067  lea     rcx, [rsp+98h+hHeap]; this
0x14000e06c  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x14000e071  mov     r8, [rsp+98h+lpMem]; lpMem
0x14000e076  test    r8, r8
0x14000e079  jz      short loc_14000E089
0x14000e07b  xor     edx, edx; dwFlags
0x14000e07d  mov     rcx, [rsp+98h+hHeap]; hHeap
0x14000e082  call    cs:__imp_HeapFree
0x14000e088  nop
0x14000e089  test    rbx, rbx
0x14000e08c  jz      short loc_14000E0A1
0x14000e08e  mov     r8, [rbx]
0x14000e091  mov     edx, 1
0x14000e096  mov     rcx, rbx
0x14000e099  mov     rax, [r8]
0x14000e09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0a1  mov     eax, esi
0x14000e0a3  add     rsp, 70h
0x14000e0a7  pop     r15
0x14000e0a9  pop     r14
0x14000e0ab  pop     r12
0x14000e0ad  pop     rsi
0x14000e0ae  pop     rbx
0x14000e0af  retn
```
