# CFileListener::MergeProperties(CLocationWriter *,ISimpleTableRead2 *,ulong *,ulong,ISimpleTableWrite2 *,ulong *,ulong)

- ea: `0x18000c680`
- end: `0x18000cb22`
- name: `?MergeProperties@CFileListener@@AEAAJPEAVCLocationWriter@@PEAUISimpleTableRead2@@PEAKKPEAUISimpleTableWrite2@@2K@Z`
- size: `1186`
- prototype: `int(CFileListener *__hidden this, struct CLocationWriter *, struct ISimpleTableRead2 *, unsigned int *, unsigned int, struct ISimpleTableWrite2 *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c4f4`

## callees

- `0x18000c680`
- `0x18000ccc0`
- `0x18002e130`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c7cc`
- `msvcrt!_wcsicmp` at `0x18000c816`
- `msvcrt!_wcsicmp` at `0x18000c7cc`
- `msvcrt!_wcsicmp` at `0x18000c816`
- `IisRTL!PuDbgPrintW` at `0x18000c912`
- `IisRTL!PuDbgPrintW` at `0x18000ca65`
- `IisRTL!PuDbgPrintW` at `0x18000caf3`
- `IisRTL!PuDbgPrintW` at `0x18000c912`
- `IisRTL!PuDbgPrintW` at `0x18000ca65`
- `IisRTL!PuDbgPrintW` at `0x18000caf3`

## string_xrefs

- `0x18000cae7`: `[CFileListener::MergeProperties] CLocationWriter::AddProperty from a location in table %s failed with hr = 0x%x. Location = %s, Property ID: %d.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::MergeProperties(
        CFileListener *this,
        struct CLocationWriter *a2,
        struct ISimpleTableRead2 *a3,
        unsigned int *a4,
        unsigned int a5,
        struct ISimpleTableWrite2 *a6,
        unsigned int *a7,
        unsigned int a8)
{
  struct ISimpleTableRead2 *v8; // rbx
  unsigned int v11; // edi
  unsigned int v12; // esi
  int v13; // eax
  int v14; // r14d
  int v15; // eax
  int v16; // ebx
  CFileListener *v17; // rcx
  _DWORD *v18; // rdx
  __int64 v19; // r8
  CFileListener *v20; // rcx
  int v21; // eax
  __int64 v22; // r8
  const wchar_t *v23; // rax
  void *v25; // [rsp+28h] [rbp-D8h]
  wchar_t **v26; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+38h] [rbp-C8h]
  int v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+38h] [rbp-C8h]
  int v31; // [rsp+40h] [rbp-C0h]
  int v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+48h] [rbp-B8h]
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-ACh] BYREF
  struct ISimpleTableRead2 *v36; // [rsp+58h] [rbp-A8h]
  struct ISimpleTableRead2 *v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v38; // [rsp+68h] [rbp-98h]
  unsigned int *v39; // [rsp+70h] [rbp-90h]
  wchar_t *String1[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  int *v42; // [rsp+A8h] [rbp-58h]
  _DWORD *v43; // [rsp+B8h] [rbp-48h]
  _DWORD *v44; // [rsp+C0h] [rbp-40h]
  wchar_t *String2[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v46; // [rsp+F0h] [rbp-10h]
  int *v47; // [rsp+F8h] [rbp-8h]
  _DWORD *v48; // [rsp+108h] [rbp+8h]
  unsigned int v49[10]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v50[10]; // [rsp+148h] [rbp+48h] BYREF

  v8 = a3;
  v38 = a4;
  v36 = a3;
  v39 = a7;
  v37 = 0;
  memset_0(String2, 0, 0x48u);
  memset_0(String1, 0, 0x50u);
  v11 = *a4;
  v12 = *a7;
  v13 = 1;
  v14 = 1;
  v35 = v11;
  v34 = v12;
  while ( 1 )
  {
    if ( !v13 )
      goto LABEL_6;
    v25 = String2;
    v15 = (*(__int64 (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, __int64))(*(_QWORD *)v8 + 32LL))(v8, v11, 9);
    v16 = v15;
    if ( v15 == -2145318890 || a5 != *v48 )
      break;
    if ( v15 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v32 = *v47;
        v27 = v15;
        LODWORD(v25) = v11;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          3918,
          "CFileListener::MergeProperties",
          L"[CFileListener::MergeProperties] GetColumnValues on row %d from table %s failed with hr = 0x%x. Location = %s,"
           " Property ID: %d.\n",
          v25,
          L"MBProperty",
          v27,
          v46,
          v32);
      }
      return (unsigned int)v16;
    }
LABEL_6:
    if ( v14 )
    {
      v26 = String1;
      v25 = v49;
      v16 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, _QWORD, __int64))(*(_QWORD *)a6 + 96LL))(
              a6,
              v12,
              10);
      if ( v16 == -2145318890 || (v17 = (CFileListener *)a8, a8 != *v43) )
      {
        v21 = CFileListener::MergeRemainingProperties(v17, a2, v36, 1, &v35, a5);
        v11 = v35;
        v16 = v21;
        goto LABEL_34;
      }
      if ( v16 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v33 = *v42;
          v28 = v16;
          LODWORD(v25) = v12;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            3958,
            "CFileListener::MergeProperties",
            L"[CFileListener::MergeProperties] GetColumnValues on row %d from table %s failed with hr = 0x%x. Location = %"
             "s, Property ID: %d.\n",
            v25,
            L"MBPropertyDiff",
            v28,
            v41,
            v33);
        }
        return (unsigned int)v16;
      }
    }
    if ( _wcsicmp(String1[0], String2[0]) >= 0 )
    {
      if ( _wcsicmp(String1[0], String2[0]) > 0 )
      {
        v16 = CLocationWriter::AddProperty(a2, 1, (void **)String2, v50);
        if ( v16 >= 0 )
        {
          v14 = 0;
          v35 = ++v11;
          v13 = 1;
          goto LABEL_25;
        }
        if ( (g_dwDebugFlags & 3) == 0 )
          return (unsigned int)v16;
        v22 = 4034;
        v31 = *v47;
        v30 = v46;
        v23 = L"MBProperty";
LABEL_47:
        LODWORD(v26) = v16;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          v22,
          "CFileListener::MergeProperties",
          L"[CFileListener::MergeProperties] CLocationWriter::AddProperty from a location in table %s failed with hr = 0x%"
           "x. Location = %s, Property ID: %d.\n",
          v23,
          v26,
          v30,
          v31);
        return (unsigned int)v16;
      }
      v18 = v44;
      if ( *v44 == 1 || *v44 == 2 )
      {
        v16 = CLocationWriter::AddProperty(a2, 0, (void **)String1, v49);
        if ( v16 < 0 )
        {
          if ( (g_dwDebugFlags & 3) == 0 )
            return (unsigned int)v16;
          v22 = 4064;
          goto LABEL_46;
        }
      }
      else if ( *v44 != 3 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v19 = 4088;
          goto LABEL_40;
        }
        return (unsigned int)-2147024883;
      }
      ++v12;
      v14 = 1;
      ++v11;
      v13 = 1;
      v35 = v11;
      goto LABEL_24;
    }
    v18 = v44;
    if ( *v44 != 1 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v19 = 4010;
LABEL_40:
        v29 = *v42;
        LODWORD(v25) = *v18;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          v19,
          "CFileListener::MergeProperties",
          L"[CFileListener::MergeProperties] Unexpected directive:%d. Location = %s, Property ID: %d.\n",
          v25,
          v41,
          v29);
      }
      return (unsigned int)-2147024883;
    }
    v16 = CLocationWriter::AddProperty(a2, 0, (void **)String1, v49);
    if ( v16 < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        return (unsigned int)v16;
      v22 = 3992;
LABEL_46:
      v31 = *v42;
      v30 = v41;
      v23 = L"MBPropertyDiff";
      goto LABEL_47;
    }
    v13 = 0;
    ++v12;
    v14 = 1;
LABEL_24:
    v34 = v12;
LABEL_25:
    v8 = v36;
  }
  v16 = (**(__int64 (__fastcall ***)(struct ISimpleTableWrite2 *, GUID *, struct ISimpleTableRead2 **))a6)(
          a6,
          &IID_ISimpleTableRead2,
          &v37);
  if ( v16 < 0 )
    return (unsigned int)v16;
  v16 = CFileListener::MergeRemainingProperties(v20, a2, v37, 0, &v34, a8);
  (*(void (__fastcall **)(struct ISimpleTableRead2 *))(*(_QWORD *)v37 + 16LL))(v37);
  v12 = v34;
LABEL_34:
  if ( v16 >= 0 )
  {
    *v38 = v11;
    *v39 = v12;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000c680  mov     [rsp-8+arg_0], rbx
0x18000c685  push    rbp
0x18000c686  push    rsi
0x18000c687  push    rdi
0x18000c688  push    r12
0x18000c68a  push    r13
0x18000c68c  push    r14
0x18000c68e  push    r15
0x18000c690  lea     rbp, [rsp-80h]
0x18000c695  sub     rsp, 180h
0x18000c69c  mov     rax, cs:__security_cookie
0x18000c6a3  xor     rax, rsp
0x18000c6a6  mov     [rbp+0B0h+var_40], rax
0x18000c6aa  mov     rsi, [rbp+0B0h+arg_30]
0x18000c6b1  lea     rcx, [rbp+0B0h+String2]; void *
0x18000c6b5  mov     r12, [rbp+0B0h+arg_28]
0x18000c6bc  mov     rbx, r8
0x18000c6bf  mov     r15, rdx
0x18000c6c2  mov     [rsp+1B0h+var_148], r9
0x18000c6c7  xor     edx, edx; Val
0x18000c6c9  mov     [rsp+1B0h+var_158], rbx
0x18000c6ce  mov     rdi, r9
0x18000c6d1  mov     [rsp+1B0h+var_140], rsi
0x18000c6d6  mov     [rsp+1B0h+var_150], 0
0x18000c6df  lea     r8d, [rdx+48h]; Size
0x18000c6e3  call    memset_0
0x18000c6e8  xor     edx, edx; Val
0x18000c6ea  lea     rcx, [rbp+0B0h+String1]; void *
0x18000c6ee  lea     r8d, [rdx+50h]; Size
0x18000c6f2  call    memset_0
0x18000c6f7  mov     edi, [rdi]
0x18000c6f9  mov     ecx, 1
0x18000c6fe  mov     esi, [rsi]
0x18000c700  mov     eax, ecx
0x18000c702  mov     r13d, [rbp+0B0h+arg_20]
0x18000c709  mov     r14d, ecx
0x18000c70c  mov     [rsp+1B0h+var_15C], edi
0x18000c710  mov     [rsp+1B0h+var_160], esi
0x18000c714  test    eax, eax
0x18000c716  jz      short loc_18000C764
0x18000c718  mov     rax, [rbx]
0x18000c71b  lea     rcx, [rbp+0B0h+String2]
0x18000c71f  mov     qword ptr [rsp+1B0h+var_188], rcx
0x18000c724  xor     r9d, r9d
0x18000c727  lea     rcx, [rbp+0B0h+var_68]
0x18000c72b  mov     edx, edi
0x18000c72d  mov     [rsp+1B0h+var_190], rcx
0x18000c732  mov     rcx, rbx
0x18000c735  mov     rax, [rax+20h]
0x18000c739  lea     r8d, [r9+9]
0x18000c73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c742  mov     ebx, eax
0x18000c744  cmp     eax, 80210816h
0x18000c749  jz      loc_18000C91D
0x18000c74f  mov     rcx, [rbp+0B0h+var_A8]
0x18000c753  cmp     r13d, [rcx]
0x18000c756  jnz     loc_18000C91D
0x18000c75c  test    eax, eax
0x18000c75e  js      loc_18000C8B7
0x18000c764  test    r14d, r14d
0x18000c767  jz      short loc_18000C7C4
0x18000c769  mov     rax, [r12]
0x18000c76d  lea     rcx, [rbp+0B0h+String1]
0x18000c771  mov     [rsp+1B0h+var_180], rcx
0x18000c776  xor     r9d, r9d
0x18000c779  lea     rcx, [rbp+0B0h+var_90]
0x18000c77d  mov     edx, esi
0x18000c77f  mov     qword ptr [rsp+1B0h+var_188], rcx
0x18000c784  mov     rcx, r12
0x18000c787  mov     rax, [rax+60h]
0x18000c78b  lea     r8d, [r9+0Ah]
0x18000c78f  mov     [rsp+1B0h+var_190], 0
0x18000c798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c79d  mov     ebx, eax
0x18000c79f  cmp     eax, 80210816h
0x18000c7a4  jz      loc_18000C9BE
0x18000c7aa  mov     rax, [rbp+0B0h+var_F8]
0x18000c7ae  mov     ecx, [rbp+0B0h+arg_38]
0x18000c7b4  cmp     ecx, [rax]
0x18000c7b6  jnz     loc_18000C9BE
0x18000c7bc  test    ebx, ebx
0x18000c7be  js      loc_18000C97F
0x18000c7c4  mov     rdx, [rbp+0B0h+String2]; String2
0x18000c7c8  mov     rcx, [rbp+0B0h+String1]; String1
0x18000c7cc  call    cs:__imp__wcsicmp
0x18000c7d2  test    eax, eax
0x18000c7d4  jns     short loc_18000C80E
0x18000c7d6  mov     rdx, [rbp+0B0h+var_F0]
0x18000c7da  mov     ecx, [rdx]
0x18000c7dc  sub     ecx, 1
0x18000c7df  jnz     loc_18000CA19
0x18000c7e5  lea     r9, [rbp+0B0h+var_90]; unsigned int *
0x18000c7e9  xor     edx, edx; int
0x18000c7eb  lea     r8, [rbp+0B0h+String1]; void **
0x18000c7ef  mov     rcx, r15; this
0x18000c7f2  call    ?AddProperty@CLocationWriter@@QEAAJHPEAPEAXPEAK@Z; CLocationWriter::AddProperty(int,void * *,ulong *)
0x18000c7f7  mov     ebx, eax
0x18000c7f9  test    eax, eax
0x18000c7fb  js      loc_18000CA01
0x18000c801  xor     eax, eax
0x18000c803  inc     esi
0x18000c805  lea     r14d, [rax+1]
0x18000c809  jmp     loc_18000C8A9
0x18000c80e  mov     rdx, [rbp+0B0h+String2]; String2
0x18000c812  mov     rcx, [rbp+0B0h+String1]; String1
0x18000c816  call    cs:__imp__wcsicmp
0x18000c81c  test    eax, eax
0x18000c81e  jle     short loc_18000C84E
0x18000c820  lea     r9, [rbp+0B0h+var_68]; unsigned int *
0x18000c824  mov     edx, 1; int
0x18000c829  lea     r8, [rbp+0B0h+String2]; void **
0x18000c82d  mov     rcx, r15; this
0x18000c830  call    ?AddProperty@CLocationWriter@@QEAAJHPEAPEAXPEAK@Z; CLocationWriter::AddProperty(int,void * *,ulong *)
0x18000c835  mov     ebx, eax
0x18000c837  test    eax, eax
0x18000c839  js      loc_18000CA75
0x18000c83f  xor     r14d, r14d
0x18000c842  inc     edi
0x18000c844  mov     [rsp+1B0h+var_15C], edi
0x18000c848  lea     eax, [r14+1]
0x18000c84c  jmp     short loc_18000C8AD
0x18000c84e  mov     rdx, [rbp+0B0h+var_F0]
0x18000c852  mov     ecx, [rdx]
0x18000c854  sub     ecx, 1
0x18000c857  jz      short loc_18000C87B
0x18000c859  sub     ecx, 1
0x18000c85c  jz      short loc_18000C87B
0x18000c85e  cmp     ecx, 1
0x18000c861  jz      short loc_18000C897
0x18000c863  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c86a  jz      loc_18000CA6B
0x18000c870  mov     r8d, 0FF8h
0x18000c876  jmp     loc_18000CA2B
0x18000c87b  lea     r9, [rbp+0B0h+var_90]; unsigned int *
0x18000c87f  xor     edx, edx; int
0x18000c881  lea     r8, [rbp+0B0h+String1]; void **
0x18000c885  mov     rcx, r15; this
0x18000c888  call    ?AddProperty@CLocationWriter@@QEAAJHPEAPEAXPEAK@Z; CLocationWriter::AddProperty(int,void * *,ulong *)
0x18000c88d  mov     ebx, eax
0x18000c88f  test    eax, eax
0x18000c891  js      loc_18000CAA0
0x18000c897  mov     ecx, 1
0x18000c89c  add     esi, ecx
0x18000c89e  mov     r14d, ecx
0x18000c8a1  add     edi, ecx
0x18000c8a3  mov     eax, ecx
0x18000c8a5  mov     [rsp+1B0h+var_15C], edi
0x18000c8a9  mov     [rsp+1B0h+var_160], esi
0x18000c8ad  mov     rbx, [rsp+1B0h+var_158]
0x18000c8b2  jmp     loc_18000C714
0x18000c8b7  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c8be  jz      loc_18000CAF9
0x18000c8c4  mov     rax, [rbp+0B0h+var_B8]
0x18000c8c8  mov     r8d, 0F4Eh
0x18000c8ce  mov     ecx, [rax]
0x18000c8d0  mov     rax, [rbp+0B0h+var_C0]
0x18000c8d4  mov     [rsp+1B0h+var_168], ecx
0x18000c8d8  mov     [rsp+1B0h+var_170], rax
0x18000c8dd  lea     rax, aMbproperty_0; "MBProperty"
0x18000c8e4  mov     dword ptr [rsp+1B0h+var_178], ebx
0x18000c8e8  mov     [rsp+1B0h+var_180], rax
0x18000c8ed  mov     [rsp+1B0h+var_188], edi
0x18000c8f1  mov     rcx, cs:g_pDebug
0x18000c8f8  lea     rax, aCfilelistenerM_8; "[CFileListener::MergeProperties] GetCol"...
0x18000c8ff  lea     r9, aCfilelistenerM_6; "CFileListener::MergeProperties"
0x18000c906  mov     [rsp+1B0h+var_190], rax
0x18000c90b  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000c912  call    cs:__imp_PuDbgPrintW
0x18000c918  jmp     loc_18000CAF9
0x18000c91d  mov     rax, [r12]
0x18000c921  lea     r8, [rsp+1B0h+var_150]
0x18000c926  lea     rdx, IID_ISimpleTableRead2
0x18000c92d  mov     rcx, r12
0x18000c930  mov     rax, [rax]
0x18000c933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c938  mov     ebx, eax
0x18000c93a  test    eax, eax
0x18000c93c  js      loc_18000CAF9
0x18000c942  mov     eax, [rbp+0B0h+arg_38]
0x18000c948  xor     r9d, r9d; int
0x18000c94b  mov     r8, [rsp+1B0h+var_150]; struct ISimpleTableRead2 *
0x18000c950  mov     rdx, r15; struct CLocationWriter *
0x18000c953  mov     [rsp+1B0h+var_188], eax; unsigned int
0x18000c957  lea     rax, [rsp+1B0h+var_160]
0x18000c95c  mov     [rsp+1B0h+var_190], rax; unsigned int *
0x18000c961  call    ?MergeRemainingProperties@CFileListener@@AEAAJPEAVCLocationWriter@@PEAUISimpleTableRead2@@HPEAKK@Z; CFileListener::MergeRemainingProperties(CLocationWriter *,ISimpleTableRead2 *,int,ulong *,ulong)
0x18000c966  mov     rcx, [rsp+1B0h+var_150]
0x18000c96b  mov     ebx, eax
0x18000c96d  mov     rax, [rcx]
0x18000c970  mov     rax, [rax+10h]
0x18000c974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c979  mov     esi, [rsp+1B0h+var_160]
0x18000c97d  jmp     short loc_18000C9E6
0x18000c97f  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c986  jz      loc_18000CAF9
0x18000c98c  mov     rax, [rbp+0B0h+var_108]
0x18000c990  mov     r8d, 0F76h
0x18000c996  mov     ecx, [rax]
0x18000c998  mov     rax, [rbp+0B0h+var_110]
0x18000c99c  mov     [rsp+1B0h+var_168], ecx
0x18000c9a0  mov     [rsp+1B0h+var_170], rax
0x18000c9a5  lea     rax, aMbpropertydiff; "MBPropertyDiff"
0x18000c9ac  mov     dword ptr [rsp+1B0h+var_178], ebx
0x18000c9b0  mov     [rsp+1B0h+var_180], rax
0x18000c9b5  mov     [rsp+1B0h+var_188], esi
0x18000c9b9  jmp     loc_18000C8F1
0x18000c9be  mov     r8, [rsp+1B0h+var_158]; struct ISimpleTableRead2 *
0x18000c9c3  lea     rax, [rsp+1B0h+var_15C]
0x18000c9c8  mov     [rsp+1B0h+var_188], r13d; unsigned int
0x18000c9cd  mov     r9d, 1; int
0x18000c9d3  mov     rdx, r15; struct CLocationWriter *
0x18000c9d6  mov     [rsp+1B0h+var_190], rax; unsigned int *
0x18000c9db  call    ?MergeRemainingProperties@CFileListener@@AEAAJPEAVCLocationWriter@@PEAUISimpleTableRead2@@HPEAKK@Z; CFileListener::MergeRemainingProperties(CLocationWriter *,ISimpleTableRead2 *,int,ulong *,ulong)
0x18000c9e0  mov     edi, [rsp+1B0h+var_15C]
0x18000c9e4  mov     ebx, eax
0x18000c9e6  test    ebx, ebx
0x18000c9e8  js      loc_18000CAF9
0x18000c9ee  mov     rax, [rsp+1B0h+var_148]
0x18000c9f3  mov     [rax], edi
0x18000c9f5  mov     rax, [rsp+1B0h+var_140]
0x18000c9fa  mov     [rax], esi
0x18000c9fc  jmp     loc_18000CAF9
0x18000ca01  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ca08  jz      loc_18000CAF9
0x18000ca0e  mov     r8d, 0F98h
0x18000ca14  jmp     loc_18000CAAF
0x18000ca19  sub     ecx, 1
0x18000ca1c  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ca23  jz      short loc_18000CA6B
0x18000ca25  mov     r8d, 0FAAh
0x18000ca2b  mov     rax, [rbp+0B0h+var_108]
0x18000ca2f  lea     r9, aCfilelistenerM_6; "CFileListener::MergeProperties"
0x18000ca36  mov     ecx, [rax]
0x18000ca38  mov     rax, [rbp+0B0h+var_110]
0x18000ca3c  mov     dword ptr [rsp+1B0h+var_178], ecx
0x18000ca40  mov     rcx, cs:g_pDebug
0x18000ca47  mov     [rsp+1B0h+var_180], rax
0x18000ca4c  mov     eax, [rdx]
0x18000ca4e  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ca55  mov     [rsp+1B0h+var_188], eax
0x18000ca59  lea     rax, aCfilelistenerM_2; "[CFileListener::MergeProperties] Unexpe"...
0x18000ca60  mov     [rsp+1B0h+var_190], rax
0x18000ca65  call    cs:__imp_PuDbgPrintW
0x18000ca6b  mov     ebx, 8007000Dh
0x18000ca70  jmp     loc_18000CAF9
0x18000ca75  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ca7c  jz      short loc_18000CAF9
0x18000ca7e  mov     rax, [rbp+0B0h+var_B8]
0x18000ca82  mov     r8d, 0FC2h
0x18000ca88  mov     ecx, [rax]
0x18000ca8a  mov     rax, [rbp+0B0h+var_C0]
0x18000ca8e  mov     dword ptr [rsp+1B0h+var_170], ecx
0x18000ca92  mov     [rsp+1B0h+var_178], rax
0x18000ca97  lea     rax, aMbproperty_0; "MBProperty"
0x18000ca9e  jmp     short loc_18000CAC9
0x18000caa0  test    byte ptr cs:g_dwDebugFlags, 3
0x18000caa7  jz      short loc_18000CAF9
0x18000caa9  mov     r8d, 0FE0h
0x18000caaf  mov     rax, [rbp+0B0h+var_108]
0x18000cab3  mov     ecx, [rax]
0x18000cab5  mov     rax, [rbp+0B0h+var_110]
0x18000cab9  mov     dword ptr [rsp+1B0h+var_170], ecx
0x18000cabd  mov     [rsp+1B0h+var_178], rax
0x18000cac2  lea     rax, aMbpropertydiff; "MBPropertyDiff"
0x18000cac9  mov     rcx, cs:g_pDebug
0x18000cad0  lea     r9, aCfilelistenerM_6; "CFileListener::MergeProperties"
0x18000cad7  mov     dword ptr [rsp+1B0h+var_180], ebx
0x18000cadb  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000cae2  mov     qword ptr [rsp+1B0h+var_188], rax
0x18000cae7  lea     rax, aCfilelistenerM_12; "[CFileListener::MergeProperties] CLocat"...
0x18000caee  mov     [rsp+1B0h+var_190], rax
0x18000caf3  call    cs:__imp_PuDbgPrintW
0x18000caf9  mov     eax, ebx
0x18000cafb  mov     rcx, [rbp+0B0h+var_40]
0x18000caff  xor     rcx, rsp; StackCookie
0x18000cb02  call    __security_check_cookie
0x18000cb07  mov     rbx, [rsp+1B0h+arg_0]
0x18000cb0f  add     rsp, 180h
0x18000cb16  pop     r15
0x18000cb18  pop     r14
0x18000cb1a  pop     r13
0x18000cb1c  pop     r12
0x18000cb1e  pop     rdi
0x18000cb1f  pop     rsi
0x18000cb20  pop     rbp
0x18000cb21  retn
```
