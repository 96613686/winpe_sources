# VsCoCreateAggregatedManagedObject

- ea: `0x14006af80`
- end: `0x14006b40c`
- name: `VsCoCreateAggregatedManagedObject`
- size: `1164`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, OLECHAR *@<rdx>, OLECHAR *@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002d3e0`

## callees

- `0x140001020`
- `0x14002d3e0`
- `0x140032d20`
- `0x140033ab0`
- `0x14006aa20`
- `0x14006af80`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14006b00c`
- `KERNEL32!LoadLibraryW` at `0x14006b00c`
- `KERNEL32!OutputDebugStringW` at `0x14006b078`
- `KERNEL32!OutputDebugStringW` at `0x14006b078`
- `KERNEL32!FreeLibrary` at `0x14006b088`
- `KERNEL32!FreeLibrary` at `0x14006b088`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b25e`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b273`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b2c7`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b2dc`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b25e`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b273`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b2c7`
- `OLEAUT32!__imp_SysAllocString` at `0x14006b2dc`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b2a2`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b2ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b30b`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b314`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b2a2`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b2ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b30b`
- `OLEAUT32!__imp_SysFreeString` at `0x14006b314`
- `OLEAUT32!__imp_VariantInit` at `0x14006b323`
- `OLEAUT32!__imp_VariantInit` at `0x14006b323`
- `OLEAUT32!__imp_VariantClear` at `0x14006b38d`
- `OLEAUT32!__imp_VariantClear` at `0x14006b38d`

## string_xrefs

- `0x14006afee`: `mscoree.dll`
- `0x14006b05c`: `CorBindToRuntimeEx(...,CLSID_CorRuntimeHost,...) failed with error HR: %#0.8x\n`

## pseudocode

```c
__int64 __fastcall VsCoCreateAggregatedManagedObject(
        OLECHAR *psz,
        OLECHAR *a2,
        OLECHAR *a3,
        __int64 a4,
        void *a5,
        _QWORD *a6)
{
  HMODULE LibraryW; // r14
  signed int v11; // ebx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r14
  __int64 v16; // rdx
  unsigned int v17; // edi
  signed int v18; // eax
  __int64 v19; // rbx
  OLECHAR *v20; // r14
  BSTR v21; // rax
  OLECHAR *v22; // r15
  __int64 v23; // rbx
  OLECHAR *v24; // rdi
  BSTR v25; // rax
  OLECHAR *v26; // r14
  VARIANTARG pvarg; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v33; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Buffer[128]; // [rsp+80h] [rbp-80h] BYREF

  v29 = a5;
  if ( __PAIR128__((unsigned __int64)psz, (unsigned __int64)a2) == 0 || !a3 || !a6 )
    return 2147500035LL;
  *(_QWORD *)&v33.Data1 = 0;
  *(_QWORD *)v33.Data4 = 0;
  v32 = 0;
  v31 = 0;
  *a6 = 0;
  LibraryW = LoadLibraryW(L"mscoree.dll");
  if ( !LibraryW )
  {
    v11 = -2147467259;
LABEL_59:
    v17 = v11;
    goto LABEL_60;
  }
  v12 = LegacyActivationShim::CorBindToRuntimeEx(
          0,
          0,
          0,
          (unsigned int)&CLSID_CorRuntimeHost,
          &IID_ICorRuntimeHost,
          &v33,
          *(void ***)&pvarg.vt);
  v11 = v12;
  if ( v12 < 0 )
  {
    _mm_lfence();
    swprintf_s(
      Buffer,
      0x80u,
      L"CorBindToRuntimeEx(...,CLSID_CorRuntimeHost,...) failed with error HR: %#0.8x\n",
      (unsigned int)v12,
      -1);
    OutputDebugStringW(Buffer);
LABEL_9:
    FreeLibrary(LibraryW);
    goto LABEL_10;
  }
  if ( v12 == 1 )
    goto LABEL_9;
LABEL_10:
  if ( v11 < 0 )
    goto LABEL_59;
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v33.Data1 + 80LL))(*(_QWORD *)&v33.Data1);
  if ( v11 < 0 )
    goto LABEL_59;
  if ( !a4 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *))(**(_QWORD **)&v33.Data1 + 104LL))(
            *(_QWORD *)&v33.Data1,
            v33.Data4);
    if ( v11 < 0 )
      goto LABEL_59;
    v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v33.Data4)(
            *(_QWORD *)v33.Data4,
            &GUID_05f696dc_2b29_3663_ad8b_c4389cf2a713,
            &v32);
    if ( v11 < 0 )
      goto LABEL_59;
    if ( a2 )
    {
      v19 = v32;
      v20 = SysAllocString(a3);
      if ( !v20 )
        goto LABEL_70;
      v21 = SysAllocString(a2);
      v22 = v21;
      if ( !v21 )
        goto LABEL_70;
      v11 = (*(__int64 (__fastcall **)(__int64, BSTR, OLECHAR *, __int64 *))(*(_QWORD *)v19 + 296LL))(
              v19,
              v21,
              v20,
              &v31);
      SysFreeString(v22);
      SysFreeString(v20);
    }
    if ( !psz )
      goto LABEL_50;
    if ( v11 >= 0 && a2 )
      goto LABEL_51;
    v23 = v32;
    v24 = SysAllocString(a3);
    if ( v24 )
    {
      v25 = SysAllocString(psz);
      v26 = v25;
      if ( v25 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, BSTR, OLECHAR *, __int64 *))(*(_QWORD *)v23 + 304LL))(
                v23,
                v25,
                v24,
                &v31);
        SysFreeString(v26);
        SysFreeString(v24);
LABEL_50:
        if ( v11 < 0 )
          goto LABEL_59;
LABEL_51:
        VariantInit(&pvarg);
        v11 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v31 + 112LL))(v31, &pvarg);
        if ( v11 >= 0 )
        {
          v11 = -2147467259;
          if ( pvarg.vt == 9 || pvarg.vt == 13 )
          {
            if ( pvarg.llVal )
            {
              v11 = (**(__int64 (__fastcall ***)(LONGLONG, LPVOID, _QWORD *))pvarg.llVal)(pvarg.llVal, v29, a6);
              if ( v11 >= 0 )
                v11 = *a6 == 0 ? 0x8000FFFF : 0;
            }
            else
            {
              v11 = -2147418113;
            }
          }
          VariantClear(&pvarg);
        }
        goto LABEL_59;
      }
    }
LABEL_70:
    ATL::AtlThrowImpl(-2147024882);
  }
  v13 = qword_14009D740;
  if ( qword_14009D740 )
    goto LABEL_32;
  v29 = 0;
  v11 = VsLoaderCoCreateInstanceUnknown(&CLSID_VsManagedObjectAggregatorPrivate, 0, 1u, &v29);
  if ( v11 < 0 )
  {
    if ( v29 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
    goto LABEL_59;
  }
  v14 = 0;
  v30 = 0;
  if ( v29 )
  {
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v29)(v29, &GUID_7e6b77ad_5886_4869_8a73_d2bc79472c54, &v30) >= 0 )
    {
      v14 = v30;
    }
    else
    {
      v14 = 0;
      v30 = 0;
    }
  }
  v13 = qword_14009D740;
  if ( qword_14009D740 != v14 )
  {
    v15 = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v14 = v30;
      v13 = qword_14009D740;
    }
    v16 = v13;
    v13 = v15;
    qword_14009D740 = v15;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v14 = v30;
      v13 = qword_14009D740;
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v13 = qword_14009D740;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
    v13 = qword_14009D740;
  }
  if ( v13 )
  {
LABEL_32:
    if ( a2 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, __int64, OLECHAR *, OLECHAR *, _QWORD *))(*(_QWORD *)v13 + 24LL))(
              v13,
              a4,
              a2,
              a3,
              a6);
      v13 = qword_14009D740;
      v11 = v18;
    }
    if ( psz && (v11 < 0 || !a2) )
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, OLECHAR *, OLECHAR *, _QWORD *))(*(_QWORD *)v13 + 32LL))(
              v13,
              a4,
              psz,
              a3,
              a6);
    goto LABEL_59;
  }
  v17 = -2147418113;
LABEL_60:
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( *(_QWORD *)v33.Data4 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33.Data4 + 16LL))(*(_QWORD *)v33.Data4);
  if ( *(_QWORD *)&v33.Data1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v33.Data1 + 16LL))(*(_QWORD *)&v33.Data1);
  return v17;
}

```

## disassembly

```asm
0x14006af80  push    rbp
0x14006af82  push    rbx
0x14006af83  push    rsi
0x14006af84  push    rdi
0x14006af85  push    r12
0x14006af87  push    r13
0x14006af89  push    r14
0x14006af8b  push    r15
0x14006af8d  lea     rbp, [rsp-98h]
0x14006af95  sub     rsp, 198h
0x14006af9c  mov     rax, cs:__security_cookie
0x14006afa3  xor     rax, rsp
0x14006afa6  mov     [rbp+0D0h+var_50], rax
0x14006afad  mov     rax, [rbp+0D0h+arg_20]
0x14006afb4  xor     ebx, ebx
0x14006afb6  mov     rsi, [rbp+0D0h+arg_28]
0x14006afbd  mov     r15, r9
0x14006afc0  mov     [rsp+1D0h+var_188], rax
0x14006afc5  mov     r12, r8
0x14006afc8  mov     rdi, rdx
0x14006afcb  mov     r13, rcx
0x14006afce  test    rcx, rcx
0x14006afd1  jnz     short loc_14006AFDC
0x14006afd3  test    rdx, rdx
0x14006afd6  jz      loc_14006B3D9
0x14006afdc  test    r12, r12
0x14006afdf  jz      loc_14006B3D9
0x14006afe5  test    rsi, rsi
0x14006afe8  jz      loc_14006B3D9
0x14006afee  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x14006aff5  mov     qword ptr [rsp+1D0h+var_168.Data1], rbx
0x14006affa  mov     qword ptr [rsp+1D0h+var_168.Data4], rbx
0x14006afff  mov     [rsp+1D0h+var_170], rbx
0x14006b004  mov     [rsp+1D0h+var_178], rbx
0x14006b009  mov     [rsi], rbx
0x14006b00c  call    cs:__imp_LoadLibraryW
0x14006b012  mov     r14, rax
0x14006b015  test    rax, rax
0x14006b018  jnz     short loc_14006B024
0x14006b01a  mov     ebx, 80004005h
0x14006b01f  jmp     loc_14006B393
0x14006b024  lea     rax, [rsp+1D0h+var_168]
0x14006b029  xor     r8d, r8d; unsigned __int16 *
0x14006b02c  mov     [rsp+1D0h+var_1A8], rax; struct _GUID *
0x14006b031  lea     r9, CLSID_CorRuntimeHost; unsigned int
0x14006b038  lea     rax, IID_ICorRuntimeHost
0x14006b03f  xor     edx, edx; struct ICLRRuntimeInfo *
0x14006b041  xor     ecx, ecx; Source
0x14006b043  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14006b048  call    ?CorBindToRuntimeEx@LegacyActivationShim@@YAJPEBG0KAEBU_GUID@@1PEAPEAX@Z; LegacyActivationShim::CorBindToRuntimeEx(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x14006b04d  mov     ebx, eax
0x14006b04f  test    eax, eax
0x14006b051  jns     short loc_14006B080
0x14006b053  lfence
0x14006b056  or      [rsp+1D0h+var_1B0], 0FFFFFFFFFFFFFFFFh
0x14006b05c  lea     r8, aCorbindtorunti; "CorBindToRuntimeEx(...,CLSID_CorRuntime"...
0x14006b063  mov     r9d, eax
0x14006b066  lea     rcx, [rbp+0D0h+Buffer]; Buffer
0x14006b06a  mov     edx, 80h; BufferCount
0x14006b06f  call    swprintf_s
0x14006b074  lea     rcx, [rbp+0D0h+Buffer]; lpOutputString
0x14006b078  call    cs:__imp_OutputDebugStringW
0x14006b07e  jmp     short loc_14006B085
0x14006b080  cmp     ebx, 1
0x14006b083  jnz     short loc_14006B08E
0x14006b085  mov     rcx, r14; hLibModule
0x14006b088  call    cs:__imp_FreeLibrary
0x14006b08e  test    ebx, ebx
0x14006b090  js      loc_14006B393
0x14006b096  mov     rcx, qword ptr [rsp+1D0h+var_168.Data1]
0x14006b09b  mov     rax, [rcx]
0x14006b09e  call    qword ptr [rax+50h]
0x14006b0a1  mov     ebx, eax
0x14006b0a3  test    eax, eax
0x14006b0a5  js      loc_14006B393
0x14006b0ab  test    r15, r15
0x14006b0ae  jz      loc_14006B217
0x14006b0b4  mov     rcx, cs:qword_14009D740
0x14006b0bb  test    rcx, rcx
0x14006b0be  jnz     loc_14006B1C4
0x14006b0c4  and     [rsp+1D0h+var_188], rcx
0x14006b0c9  lea     r8d, [rcx+1]
0x14006b0cd  lea     rcx, CLSID_VsManagedObjectAggregatorPrivate; rclsid
0x14006b0d4  xor     edx, edx
0x14006b0d6  lea     r9, [rsp+1D0h+var_188]
0x14006b0db  call    VsLoaderCoCreateInstanceUnknown
0x14006b0e0  mov     ebx, eax
0x14006b0e2  test    eax, eax
0x14006b0e4  jns     short loc_14006B0FF
0x14006b0e6  mov     rcx, [rsp+1D0h+var_188]
0x14006b0eb  test    rcx, rcx
0x14006b0ee  jz      loc_14006B393
0x14006b0f4  mov     rax, [rcx]
0x14006b0f7  call    qword ptr [rax+10h]
0x14006b0fa  jmp     loc_14006B393
0x14006b0ff  mov     r9, [rsp+1D0h+var_188]
0x14006b104  xor     eax, eax
0x14006b106  mov     [rsp+1D0h+var_180], rax
0x14006b10b  test    r9, r9
0x14006b10e  jz      short loc_14006B136
0x14006b110  mov     rax, [r9]
0x14006b113  lea     r8, [rsp+1D0h+var_180]
0x14006b118  lea     rdx, _GUID_7e6b77ad_5886_4869_8a73_d2bc79472c54
0x14006b11f  mov     rcx, r9
0x14006b122  call    qword ptr [rax]
0x14006b124  test    eax, eax
0x14006b126  jns     short loc_14006B131
0x14006b128  xor     eax, eax
0x14006b12a  mov     [rsp+1D0h+var_180], rax
0x14006b12f  jmp     short loc_14006B136
0x14006b131  mov     rax, [rsp+1D0h+var_180]
0x14006b136  mov     rcx, cs:qword_14009D740
0x14006b13d  cmp     rcx, rax
0x14006b140  jz      short loc_14006B186
0x14006b142  mov     r14, rax
0x14006b145  test    rax, rax
0x14006b148  jz      short loc_14006B15F
0x14006b14a  mov     rdx, [rax]
0x14006b14d  mov     rcx, rax
0x14006b150  call    qword ptr [rdx+8]
0x14006b153  mov     rax, [rsp+1D0h+var_180]
0x14006b158  mov     rcx, cs:qword_14009D740
0x14006b15f  mov     rdx, rcx
0x14006b162  mov     rcx, r14
0x14006b165  mov     cs:qword_14009D740, rcx
0x14006b16c  test    rdx, rdx
0x14006b16f  jz      short loc_14006B186
0x14006b171  mov     rax, [rdx]
0x14006b174  mov     rcx, rdx
0x14006b177  call    qword ptr [rax+10h]
0x14006b17a  mov     rax, [rsp+1D0h+var_180]
0x14006b17f  mov     rcx, cs:qword_14009D740
0x14006b186  test    rax, rax
0x14006b189  jz      short loc_14006B19B
0x14006b18b  mov     rdx, [rax]
0x14006b18e  mov     rcx, rax
0x14006b191  call    qword ptr [rdx+10h]
0x14006b194  mov     rcx, cs:qword_14009D740
0x14006b19b  mov     r9, [rsp+1D0h+var_188]
0x14006b1a0  test    r9, r9
0x14006b1a3  jz      short loc_14006B1B5
0x14006b1a5  mov     rax, [r9]
0x14006b1a8  mov     rcx, r9
0x14006b1ab  call    qword ptr [rax+10h]
0x14006b1ae  mov     rcx, cs:qword_14009D740
0x14006b1b5  test    rcx, rcx
0x14006b1b8  jnz     short loc_14006B1C4
0x14006b1ba  mov     edi, 8000FFFFh
0x14006b1bf  jmp     loc_14006B395
0x14006b1c4  test    rdi, rdi
0x14006b1c7  jz      short loc_14006B1E6
0x14006b1c9  mov     rax, [rcx]
0x14006b1cc  mov     r9, r12
0x14006b1cf  mov     r8, rdi
0x14006b1d2  mov     [rsp+1D0h+var_1B0], rsi
0x14006b1d7  mov     rdx, r15
0x14006b1da  call    qword ptr [rax+18h]
0x14006b1dd  mov     rcx, cs:qword_14009D740
0x14006b1e4  mov     ebx, eax
0x14006b1e6  test    r13, r13
0x14006b1e9  jz      loc_14006B393
0x14006b1ef  test    ebx, ebx
0x14006b1f1  js      short loc_14006B1FC
0x14006b1f3  test    rdi, rdi
0x14006b1f6  jnz     loc_14006B393
0x14006b1fc  mov     rax, [rcx]
0x14006b1ff  mov     r9, r12
0x14006b202  mov     r8, r13
0x14006b205  mov     [rsp+1D0h+var_1B0], rsi
0x14006b20a  mov     rdx, r15
0x14006b20d  call    qword ptr [rax+20h]
0x14006b210  mov     ebx, eax
0x14006b212  jmp     loc_14006B393
0x14006b217  mov     rcx, qword ptr [rsp+1D0h+var_168.Data1]
0x14006b21c  lea     rdx, [rsp+1D0h+var_168.Data4]
0x14006b221  mov     rax, [rcx]
0x14006b224  call    qword ptr [rax+68h]
0x14006b227  mov     ebx, eax
0x14006b229  test    eax, eax
0x14006b22b  js      loc_14006B393
0x14006b231  mov     rcx, qword ptr [rsp+1D0h+var_168.Data4]
0x14006b236  lea     r8, [rsp+1D0h+var_170]
0x14006b23b  lea     rdx, _GUID_05f696dc_2b29_3663_ad8b_c4389cf2a713
0x14006b242  mov     rax, [rcx]
0x14006b245  call    qword ptr [rax]
0x14006b247  mov     ebx, eax
0x14006b249  test    eax, eax
0x14006b24b  js      loc_14006B393
0x14006b251  test    rdi, rdi
0x14006b254  jz      short loc_14006B2B1
0x14006b256  mov     rbx, [rsp+1D0h+var_170]
0x14006b25b  mov     rcx, r12; psz
0x14006b25e  call    cs:__imp_SysAllocString
0x14006b264  mov     r14, rax
0x14006b267  test    rax, rax
0x14006b26a  jz      loc_14006B401
0x14006b270  mov     rcx, rdi; psz
0x14006b273  call    cs:__imp_SysAllocString
0x14006b279  mov     r15, rax
0x14006b27c  test    rax, rax
0x14006b27f  jz      loc_14006B401
0x14006b285  mov     r10, [rbx]
0x14006b288  lea     r9, [rsp+1D0h+var_178]
0x14006b28d  mov     r8, r14
0x14006b290  mov     rdx, rax
0x14006b293  mov     rcx, rbx
0x14006b296  call    qword ptr [r10+128h]
0x14006b29d  mov     rcx, r15; bstrString
0x14006b2a0  mov     ebx, eax
0x14006b2a2  call    cs:__imp_SysFreeString
0x14006b2a8  mov     rcx, r14; bstrString
0x14006b2ab  call    cs:__imp_SysFreeString
0x14006b2b1  test    r13, r13
0x14006b2b4  jz      short loc_14006B31A
0x14006b2b6  test    ebx, ebx
0x14006b2b8  js      short loc_14006B2BF
0x14006b2ba  test    rdi, rdi
0x14006b2bd  jnz     short loc_14006B31E
0x14006b2bf  mov     rbx, [rsp+1D0h+var_170]
0x14006b2c4  mov     rcx, r12; psz
0x14006b2c7  call    cs:__imp_SysAllocString
0x14006b2cd  mov     rdi, rax
0x14006b2d0  test    rax, rax
0x14006b2d3  jz      loc_14006B401
0x14006b2d9  mov     rcx, r13; psz
0x14006b2dc  call    cs:__imp_SysAllocString
0x14006b2e2  mov     r14, rax
0x14006b2e5  test    rax, rax
0x14006b2e8  jz      loc_14006B401
0x14006b2ee  mov     r10, [rbx]
0x14006b2f1  lea     r9, [rsp+1D0h+var_178]
0x14006b2f6  mov     r8, rdi
0x14006b2f9  mov     rdx, rax
0x14006b2fc  mov     rcx, rbx
0x14006b2ff  call    qword ptr [r10+130h]
0x14006b306  mov     rcx, r14; bstrString
0x14006b309  mov     ebx, eax
0x14006b30b  call    cs:__imp_SysFreeString
0x14006b311  mov     rcx, rdi; bstrString
0x14006b314  call    cs:__imp_SysFreeString
0x14006b31a  test    ebx, ebx
0x14006b31c  js      short loc_14006B393
0x14006b31e  lea     rcx, [rsp+1D0h+pvarg]; pvarg
0x14006b323  call    cs:__imp_VariantInit
0x14006b329  mov     rcx, [rsp+1D0h+var_178]
0x14006b32e  lea     rdx, [rsp+1D0h+pvarg]
0x14006b333  mov     rax, [rcx]
0x14006b336  call    qword ptr [rax+70h]
0x14006b339  mov     ebx, eax
0x14006b33b  test    eax, eax
0x14006b33d  js      short loc_14006B393
0x14006b33f  cmp     word ptr [rsp+1D0h+pvarg], 9
0x14006b345  mov     ebx, 80004005h
0x14006b34a  jz      short loc_14006B354
0x14006b34c  cmp     word ptr [rsp+1D0h+pvarg], 0Dh
0x14006b352  jnz     short loc_14006B388
0x14006b354  mov     rcx, qword ptr [rsp+1D0h+pvarg+8]
0x14006b359  test    rcx, rcx
0x14006b35c  jz      short loc_14006B383
0x14006b35e  mov     rax, [rcx]
0x14006b361  mov     r8, rsi
0x14006b364  mov     rdx, [rsp+1D0h+var_188]
0x14006b369  call    qword ptr [rax]
0x14006b36b  mov     ebx, eax
0x14006b36d  test    eax, eax
0x14006b36f  js      short loc_14006B388
0x14006b371  mov     rax, [rsi]
0x14006b374  neg     rax
0x14006b377  sbb     ebx, ebx
0x14006b379  not     ebx
0x14006b37b  and     ebx, 8000FFFFh
0x14006b381  jmp     short loc_14006B388
0x14006b383  mov     ebx, 8000FFFFh
0x14006b388  lea     rcx, [rsp+1D0h+pvarg]; pvarg
0x14006b38d  call    cs:__imp_VariantClear
0x14006b393  mov     edi, ebx
0x14006b395  mov     rcx, [rsp+1D0h+var_178]
0x14006b39a  test    rcx, rcx
0x14006b39d  jz      short loc_14006B3A5
0x14006b39f  mov     rax, [rcx]
0x14006b3a2  call    qword ptr [rax+10h]
0x14006b3a5  mov     rcx, [rsp+1D0h+var_170]
0x14006b3aa  test    rcx, rcx
0x14006b3ad  jz      short loc_14006B3B5
0x14006b3af  mov     rax, [rcx]
0x14006b3b2  call    qword ptr [rax+10h]
0x14006b3b5  mov     rcx, qword ptr [rsp+1D0h+var_168.Data4]
0x14006b3ba  test    rcx, rcx
0x14006b3bd  jz      short loc_14006B3C5
0x14006b3bf  mov     rdx, [rcx]
0x14006b3c2  call    qword ptr [rdx+10h]
0x14006b3c5  mov     rcx, qword ptr [rsp+1D0h+var_168.Data1]
0x14006b3ca  test    rcx, rcx
0x14006b3cd  jz      short loc_14006B3D5
0x14006b3cf  mov     rdx, [rcx]
0x14006b3d2  call    qword ptr [rdx+10h]
0x14006b3d5  mov     eax, edi
0x14006b3d7  jmp     short loc_14006B3DE
0x14006b3d9  mov     eax, 80004003h
0x14006b3de  mov     rcx, [rbp+0D0h+var_50]
  ... truncated ...
```
