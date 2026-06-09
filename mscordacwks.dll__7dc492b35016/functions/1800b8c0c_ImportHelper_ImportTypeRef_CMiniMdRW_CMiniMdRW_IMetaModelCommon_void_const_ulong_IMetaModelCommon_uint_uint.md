# ImportHelper::ImportTypeRef(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,void const *,ulong,IMetaModelCommon *,uint,uint *)

- ea: `0x1800b8c0c`
- end: `0x1800b9201`
- name: `?ImportTypeRef@ImportHelper@@SAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@PEBXK1IPEAI@Z`
- size: `1525`
- prototype: `__int64 __fastcall(struct CMiniMdRW *, struct CMiniMdRW *, struct IMetaModelCommon *, const void *, unsigned int, struct IMetaModelCommon *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800b74b4`

## callees

- `0x1800b65f0`
- `0x1800b83b4`
- `0x1800b8504`
- `0x1800b8644`
- `0x1800b8c0c`
- `0x1800b9204`
- `0x1800b92f8`
- `0x1800b93ec`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800b915b`
- `KERNEL32!HeapFree` at `0x1800b918f`
- `KERNEL32!HeapFree` at `0x1800b91c7`
- `KERNEL32!HeapFree` at `0x1800b915b`
- `KERNEL32!HeapFree` at `0x1800b918f`
- `KERNEL32!HeapFree` at `0x1800b91c7`
- `KERNEL32!GetProcessHeap` at `0x1800b9146`
- `KERNEL32!GetProcessHeap` at `0x1800b917a`
- `KERNEL32!GetProcessHeap` at `0x1800b91b2`
- `KERNEL32!GetProcessHeap` at `0x1800b9146`
- `KERNEL32!GetProcessHeap` at `0x1800b917a`
- `KERNEL32!GetProcessHeap` at `0x1800b91b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ImportHelper::ImportTypeRef(
        struct CMiniMdRW *a1,
        struct CMiniMdRW *a2,
        struct IMetaModelCommon *a3,
        const void *a4,
        unsigned int a5,
        struct IMetaModelCommon *a6,
        unsigned int a7,
        unsigned int *a8)
{
  struct IMetaModelCommon *v8; // r9
  _BYTE *v10; // r14
  _BYTE *v11; // rsi
  unsigned int v12; // edi
  char v13; // r13
  int NesterHierarchy; // ebx
  int TDNesterHierarchy; // eax
  char *v16; // rcx
  unsigned int v17; // eax
  struct CMiniMdRW *v18; // r12
  int v19; // eax
  unsigned int v20; // r9d
  struct CMiniMdRW *v21; // rdx
  struct CMiniMdRW *v22; // rcx
  struct IMetaModelCommon *v23; // r8
  _BYTE *v24; // r8
  _BYTE *v25; // rdx
  const char *v26; // rbx
  _DWORD *v27; // r13
  unsigned int v28; // ecx
  __int64 v29; // r15
  _BYTE *v30; // r8
  _BYTE *v31; // rax
  int TypeDefByName; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v34; // rax
  void *v35; // rdi
  HANDLE v36; // rax
  unsigned int v38; // [rsp+28h] [rbp-D8h]
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  struct CMiniMdRW *v40; // [rsp+38h] [rbp-C8h]
  unsigned int v41; // [rsp+40h] [rbp-C0h] BYREF
  char *v42; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h]
  unsigned int v44; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  const char *v46; // [rsp+68h] [rbp-98h] BYREF
  GUID v47; // [rsp+70h] [rbp-90h] BYREF
  GUID v48; // [rsp+80h] [rbp-80h] BYREF
  GUID v49; // [rsp+90h] [rbp-70h] BYREF
  GUID v50; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v51; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  _BYTE v54[520]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v55[3]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v56[520]; // [rsp+2E8h] [rbp+1E8h] BYREF
  LPVOID lpMem; // [rsp+4F0h] [rbp+3F0h] BYREF
  unsigned __int64 v58; // [rsp+4F8h] [rbp+3F8h]
  __int64 v59; // [rsp+500h] [rbp+400h]
  char v60; // [rsp+508h] [rbp+408h] BYREF

  v8 = a3;
  v42 = (char *)a3;
  v40 = a2;
  v43 = (__int64)a8;
  lpMem = 0;
  v58 = 0;
  v59 = 512;
  v10 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 512;
  v11 = 0;
  v55[0] = 0;
  v55[1] = 0;
  v55[2] = 512;
  v48 = GUID_NULL;
  v49 = GUID_NULL;
  v47 = GUID_NULL;
  v50 = GUID_NULL;
  v12 = 0;
  v39 = 0;
  v13 = 0;
  if ( a3 )
  {
    NesterHierarchy = (**(__int64 (__fastcall ***)(struct IMetaModelCommon *, _QWORD, GUID *))a3)(a3, 0, &v48);
    if ( NesterHierarchy < 0 )
      goto LABEL_72;
  }
  NesterHierarchy = (**(__int64 (__fastcall ***)(struct IMetaModelCommon *, _QWORD, GUID *, struct IMetaModelCommon *))a6)(
                      a6,
                      0,
                      &v47,
                      v8);
  if ( NesterHierarchy < 0 )
    goto LABEL_72;
  if ( a1 )
  {
    NesterHierarchy = (**(__int64 (__fastcall ***)(struct CMiniMdRW *, _QWORD, GUID *))a1)(a1, 0, &v49);
    if ( NesterHierarchy < 0 )
      goto LABEL_72;
  }
  NesterHierarchy = (**(__int64 (__fastcall ***)(struct CMiniMdRW *, const char **, GUID *))v40)(v40, &v46, &v50);
  if ( NesterHierarchy < 0 )
    goto LABEL_72;
  if ( (a7 & 0xFF000000) == 0x2000000 )
    TDNesterHierarchy = ImportHelper::GetTDNesterHierarchy(
                          (_DWORD)a6,
                          a7,
                          (unsigned int)&lpMem,
                          (unsigned int)v55,
                          (__int64)&v51);
  else
    TDNesterHierarchy = ImportHelper::GetTRNesterHierarchy(
                          (_DWORD)a6,
                          a7,
                          (unsigned int)&lpMem,
                          (unsigned int)v55,
                          (__int64)&v51);
  NesterHierarchy = TDNesterHierarchy;
  if ( TDNesterHierarchy < 0 )
    goto LABEL_71;
  v45 = v58 >> 2;
  v16 = &v60;
  if ( lpMem )
    v16 = (char *)lpMem;
  NesterHierarchy = (*(__int64 (__fastcall **)(struct IMetaModelCommon *, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)a6 + 8LL))(
                      a6,
                      *(unsigned int *)&v16[4 * (v58 >> 2) - 4],
                      0,
                      0,
                      &v41);
  v10 = v51;
  v11 = (_BYTE *)v55[0];
  if ( NesterHierarchy < 0 )
    goto LABEL_72;
  if ( *(_OWORD *)&v48 != *(_OWORD *)&v49 )
  {
    v20 = v41;
    if ( (v41 & 0xFFFFFF) != 0 )
    {
      if ( (v41 & 0xFF000000) == 0 )
      {
        NesterHierarchy = -2147467263;
        goto LABEL_71;
      }
    }
    else
    {
      v24 = v54;
      if ( v51 )
        v24 = v51;
      v25 = v56;
      if ( v55[0] )
        v25 = (_BYTE *)v55[0];
      v26 = v42;
      if ( (*(int (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v42 + 64LL))(
             v42,
             *(_QWORD *)&v25[8 * v45 - 8],
             *(_QWORD *)&v24[8 * v45 - 8],
             0,
             &v44) < 0 )
        goto LABEL_54;
      NesterHierarchy = (*(__int64 (__fastcall **)(const char *, _QWORD, _QWORD, _QWORD, unsigned __int64 *))(*(_QWORD *)v26 + 72LL))(
                          v26,
                          v44,
                          0,
                          0,
                          &v45);
      if ( NesterHierarchy < 0 )
        goto LABEL_72;
      v20 = v45;
      if ( (v45 & 0xFF000000) == 0x26000000 )
        goto LABEL_46;
      if ( (v45 & 0xFF000000) == 0x23000000 )
      {
        v13 = 1;
        v41 = v45;
      }
      else
      {
LABEL_54:
        v20 = v41;
      }
    }
    if ( (v20 & 0xFF000000) == 0x23000000 )
    {
      if ( !a1 || !*((_DWORD *)a1 + 40) )
      {
        v21 = v40;
        v22 = a1;
        if ( v13 )
        {
          v23 = (struct IMetaModelCommon *)v42;
          goto LABEL_29;
        }
LABEL_28:
        v23 = a6;
LABEL_29:
        NesterHierarchy = ImportHelper::CreateAssemblyRefFromAssemblyRef(v22, v21, v23, v20, &v39);
        if ( NesterHierarchy < 0 )
          goto LABEL_72;
        v12 = v39;
        goto LABEL_58;
      }
    }
    else if ( (v20 & 0xFF000000) != 0x1A000000 )
    {
      goto LABEL_58;
    }
LABEL_46:
    NesterHierarchy = -2147467263;
    goto LABEL_72;
  }
  if ( *(_QWORD *)&v47.Data1 == *(_QWORD *)&v50.Data1 )
  {
    if ( *(_QWORD *)v47.Data4 == *(_QWORD *)v50.Data4 )
    {
      *(_DWORD *)v43 = a7;
LABEL_71:
      v11 = (_BYTE *)v55[0];
      v10 = v51;
      goto LABEL_72;
    }
    if ( *(_OWORD *)&v47 == *(_OWORD *)&v50 )
      goto LABEL_58;
  }
  if ( (v41 & 0xFFFFFF) != 0 )
  {
    v17 = v41 & 0xFF000000;
    if ( (v41 & 0xFF000000) == 0 )
    {
      if ( !a1 && !v42 )
      {
        v12 = 1;
        goto LABEL_58;
      }
      v18 = v40;
      v19 = ImportHelper::CreateModuleRefFromScope(v40, a6, &v39);
LABEL_36:
      NesterHierarchy = v19;
      if ( v19 < 0 )
        goto LABEL_72;
      v12 = v39;
      goto LABEL_59;
    }
    if ( v17 != 587202560 )
    {
      if ( v17 != 436207616 )
        goto LABEL_58;
      NesterHierarchy = (*(__int64 (__fastcall **)(struct IMetaModelCommon *, _QWORD, char **))(*(_QWORD *)a6 + 56LL))(
                          a6,
                          v41,
                          &v42);
      if ( NesterHierarchy < 0 )
        goto LABEL_72;
      v18 = v40;
      if ( !strcmp(v42, v46) )
      {
        v12 = 1;
        goto LABEL_59;
      }
      v19 = ImportHelper::CreateModuleRefFromModuleRef(v40, a6, v41, &v39);
      goto LABEL_36;
    }
    v20 = v41;
    v21 = v40;
    v22 = a1;
    goto LABEL_28;
  }
  v12 = v41;
LABEL_58:
  v18 = v40;
LABEL_59:
  v27 = (_DWORD *)v43;
  if ( (v12 & 0xFF000000) != 0 || (v12 & 0xFFFFFF) == 0 )
    goto LABEL_70;
  v28 = 0;
  v39 = 0;
  NesterHierarchy = 0;
  *(_DWORD *)v43 = 0;
  v29 = (unsigned int)(v52 >> 3) - 1;
  if ( !(unsigned int)(v52 >> 3) )
  {
LABEL_68:
    *v27 = v28;
    goto LABEL_72;
  }
  while ( 1 )
  {
    v30 = v54;
    if ( v10 )
      v30 = v10;
    v31 = v56;
    if ( v11 )
      v31 = v11;
    TypeDefByName = ImportHelper::FindTypeDefByName(
                      v18,
                      *(const char **)&v31[8 * v29],
                      *(const char **)&v30[8 * v29],
                      v28,
                      &v39,
                      v38);
    NesterHierarchy = TypeDefByName;
    if ( TypeDefByName < 0 )
      break;
    v29 = (unsigned int)(v29 - 1);
    v28 = v39;
    if ( (_DWORD)v29 == -1 )
      goto LABEL_68;
  }
  if ( TypeDefByName == -2146234064 )
  {
LABEL_70:
    NesterHierarchy = ImportHelper::CreateNesterHierarchy(v18, (__int64)v27);
    goto LABEL_71;
  }
LABEL_72:
  if ( v11 )
  {
    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, v11);
    v55[0] = 0;
  }
  if ( v10 )
  {
    v34 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v34 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v34;
    }
    HeapFree(v34, 0, v10);
    v51 = 0;
  }
  v35 = lpMem;
  if ( lpMem )
  {
    v36 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v36 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v36;
    }
    HeapFree(v36, 0, v35);
    lpMem = 0;
  }
  return (unsigned int)NesterHierarchy;
}

```

## disassembly

```asm
0x1800b8c0c  mov     [rsp-8+arg_18], rbx
0x1800b8c11  push    rbp
0x1800b8c12  push    rsi
0x1800b8c13  push    rdi
0x1800b8c14  push    r12
0x1800b8c16  push    r13
0x1800b8c18  push    r14
0x1800b8c1a  push    r15
0x1800b8c1c  lea     rbp, [rsp-620h]
0x1800b8c24  sub     rsp, 720h
0x1800b8c2b  mov     rax, cs:__security_cookie
0x1800b8c32  xor     rax, rsp
0x1800b8c35  mov     [rbp+650h+var_40], rax
0x1800b8c3c  mov     r9, r8
0x1800b8c3f  mov     [rsp+750h+var_708], r8
0x1800b8c44  mov     [rsp+750h+var_718], rdx
0x1800b8c49  mov     r12, rcx
0x1800b8c4c  mov     r15, [rbp+650h+arg_28]
0x1800b8c53  mov     rax, [rbp+650h+arg_38]
0x1800b8c5a  mov     [rsp+750h+var_700], rax
0x1800b8c5f  xor     ecx, ecx
0x1800b8c61  mov     [rbp+650h+lpMem], rcx
0x1800b8c68  mov     [rbp+650h+var_258], rcx
0x1800b8c6f  mov     eax, 200h
0x1800b8c74  mov     [rbp+650h+var_250], rax
0x1800b8c7b  mov     r14d, ecx
0x1800b8c7e  mov     [rbp+650h+var_6A0], rcx
0x1800b8c82  mov     [rbp+650h+var_698], rcx
0x1800b8c86  mov     [rbp+650h+var_690], rax
0x1800b8c8a  mov     esi, ecx
0x1800b8c8c  mov     [rbp+650h+var_480], rcx
0x1800b8c93  mov     [rbp+650h+var_478], rcx
0x1800b8c9a  mov     [rbp+650h+var_470], rax
0x1800b8ca1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b8ca8  movdqa  [rbp+650h+var_6D0], xmm0
0x1800b8cad  movdqa  [rbp+650h+var_6C0], xmm0
0x1800b8cb2  movdqa  [rsp+750h+var_6E0], xmm0
0x1800b8cb8  movdqa  [rbp+650h+var_6B0], xmm0
0x1800b8cbd  mov     edi, ecx
0x1800b8cbf  mov     [rsp+750h+var_720], ecx
0x1800b8cc3  mov     r13b, cl
0x1800b8cc6  test    r8, r8
0x1800b8cc9  jz      short loc_1800B8CEA
0x1800b8ccb  mov     rax, [r8]
0x1800b8cce  lea     r8, [rbp+650h+var_6D0]
0x1800b8cd2  xor     edx, edx
0x1800b8cd4  mov     rcx, r9
0x1800b8cd7  mov     rax, [rax]
0x1800b8cda  call    cs:__guard_dispatch_icall_fptr
0x1800b8ce0  mov     ebx, eax
0x1800b8ce2  test    eax, eax
0x1800b8ce4  js      loc_1800B9135
0x1800b8cea  mov     rax, [r15]
0x1800b8ced  lea     r8, [rsp+750h+var_6E0]
0x1800b8cf2  xor     edx, edx
0x1800b8cf4  mov     rcx, r15
0x1800b8cf7  mov     rax, [rax]
0x1800b8cfa  call    cs:__guard_dispatch_icall_fptr
0x1800b8d00  mov     ebx, eax
0x1800b8d02  test    eax, eax
0x1800b8d04  js      loc_1800B9135
0x1800b8d0a  test    r12, r12
0x1800b8d0d  jz      short loc_1800B8D2F
0x1800b8d0f  mov     rax, [r12]
0x1800b8d13  lea     r8, [rbp+650h+var_6C0]
0x1800b8d17  xor     edx, edx
0x1800b8d19  mov     rcx, r12
0x1800b8d1c  mov     rax, [rax]
0x1800b8d1f  call    cs:__guard_dispatch_icall_fptr
0x1800b8d25  mov     ebx, eax
0x1800b8d27  test    eax, eax
0x1800b8d29  js      loc_1800B9135
0x1800b8d2f  mov     rcx, [rsp+750h+var_718]
0x1800b8d34  mov     rax, [rcx]
0x1800b8d37  lea     r8, [rbp+650h+var_6B0]
0x1800b8d3b  lea     rdx, [rsp+750h+var_6E8]
0x1800b8d40  mov     rax, [rax]
0x1800b8d43  call    cs:__guard_dispatch_icall_fptr
0x1800b8d49  mov     ebx, eax
0x1800b8d4b  test    eax, eax
0x1800b8d4d  js      loc_1800B9135
0x1800b8d53  mov     ecx, [rbp+650h+arg_30]
0x1800b8d59  mov     eax, ecx
0x1800b8d5b  and     eax, 0FF000000h
0x1800b8d60  lea     r9, [rbp+650h+var_480]
0x1800b8d67  lea     r8, [rbp+650h+lpMem]
0x1800b8d6e  mov     edx, ecx
0x1800b8d70  mov     rcx, r15
0x1800b8d73  cmp     eax, 2000000h
0x1800b8d78  lea     rax, [rbp+650h+var_6A0]
0x1800b8d7c  mov     [rsp+750h+var_730], rax
0x1800b8d81  jnz     short loc_1800B8D8A
0x1800b8d83  call    ?GetTDNesterHierarchy@ImportHelper@@CAJPEAVIMetaModelCommon@@IAEAV?$CQuickArray@I@@AEAV?$CQuickArray@PEBD@@2@Z; ImportHelper::GetTDNesterHierarchy(IMetaModelCommon *,uint,CQuickArray<uint> &,CQuickArray<char const *> &,CQuickArray<char const *> &)
0x1800b8d88  jmp     short loc_1800B8D8F
0x1800b8d8a  call    ?GetTRNesterHierarchy@ImportHelper@@CAJPEAVIMetaModelCommon@@IAEAV?$CQuickArray@I@@AEAV?$CQuickArray@PEBD@@2@Z; ImportHelper::GetTRNesterHierarchy(IMetaModelCommon *,uint,CQuickArray<uint> &,CQuickArray<char const *> &,CQuickArray<char const *> &)
0x1800b8d8f  mov     ebx, eax
0x1800b8d91  test    eax, eax
0x1800b8d93  js      loc_1800B912A
0x1800b8d99  mov     rdx, [rbp+650h+var_258]
0x1800b8da0  shr     rdx, 2
0x1800b8da4  mov     [rsp+750h+var_6F0], rdx
0x1800b8da9  lea     rcx, [rbp+650h+var_248]
0x1800b8db0  mov     rax, [rbp+650h+lpMem]
0x1800b8db7  test    rax, rax
0x1800b8dba  cmovnz  rcx, rax
0x1800b8dbe  mov     rax, [r15]
0x1800b8dc1  lea     r8, [rsp+750h+var_710]
0x1800b8dc6  mov     [rsp+750h+var_730], r8
0x1800b8dcb  xor     r9d, r9d
0x1800b8dce  xor     r8d, r8d
0x1800b8dd1  mov     edx, [rcx+rdx*4-4]
0x1800b8dd5  mov     rcx, r15
0x1800b8dd8  mov     rax, [rax+8]
0x1800b8ddc  call    cs:__guard_dispatch_icall_fptr
0x1800b8de2  mov     ebx, eax
0x1800b8de4  mov     r14, [rbp+650h+var_6A0]
0x1800b8de8  mov     rsi, [rbp+650h+var_480]
0x1800b8def  test    eax, eax
0x1800b8df1  js      loc_1800B9135
0x1800b8df7  mov     rax, qword ptr [rbp+650h+var_6D0]
0x1800b8dfb  mov     r8d, 0FFFFFFh
0x1800b8e01  cmp     rax, qword ptr [rbp+650h+var_6C0]
0x1800b8e05  jnz     loc_1800B8F5C
0x1800b8e0b  mov     rax, qword ptr [rbp+650h+var_6D0+8]
0x1800b8e0f  cmp     rax, qword ptr [rbp+650h+var_6C0+8]
0x1800b8e13  jnz     loc_1800B8F5C
0x1800b8e19  mov     rax, qword ptr [rbp+650h+var_6B0+8]
0x1800b8e1d  mov     rcx, qword ptr [rbp+650h+var_6B0]
0x1800b8e21  cmp     qword ptr [rsp+750h+var_6E0], rcx
0x1800b8e26  jnz     short loc_1800B8E55
0x1800b8e28  cmp     qword ptr [rsp+750h+var_6E0+8], rax
0x1800b8e2d  jnz     short loc_1800B8E43
0x1800b8e2f  mov     eax, [rbp+650h+arg_30]
0x1800b8e35  mov     r13, [rsp+750h+var_700]
0x1800b8e3a  mov     [r13+0], eax
0x1800b8e3e  jmp     loc_1800B912A
0x1800b8e43  cmp     qword ptr [rsp+750h+var_6E0], rcx
0x1800b8e48  jnz     short loc_1800B8E55
0x1800b8e4a  cmp     qword ptr [rsp+750h+var_6E0+8], rax
0x1800b8e4f  jz      loc_1800B907E
0x1800b8e55  mov     edx, [rsp+750h+var_710]
0x1800b8e59  test    r8d, edx
0x1800b8e5c  jnz     short loc_1800B8E65
0x1800b8e5e  mov     edi, edx
0x1800b8e60  jmp     loc_1800B907E
0x1800b8e65  mov     eax, edx
0x1800b8e67  and     eax, 0FF000000h
0x1800b8e6c  jnz     short loc_1800B8E9C
0x1800b8e6e  test    r12, r12
0x1800b8e71  jnz     short loc_1800B8E82
0x1800b8e73  cmp     [rsp+750h+var_708], rdi
0x1800b8e78  jnz     short loc_1800B8E82
0x1800b8e7a  lea     edi, [rax+1]
0x1800b8e7d  jmp     loc_1800B907E
0x1800b8e82  lea     r8, [rsp+750h+var_720]; unsigned int *
0x1800b8e87  mov     rdx, r15; struct IMetaModelCommon *
0x1800b8e8a  mov     r12, [rsp+750h+var_718]
0x1800b8e8f  mov     rcx, r12; this
0x1800b8e92  call    ?CreateModuleRefFromScope@ImportHelper@@CAJPEAVCMiniMdRW@@PEAVIMetaModelCommon@@PEAI@Z; ImportHelper::CreateModuleRefFromScope(CMiniMdRW *,IMetaModelCommon *,uint *)
0x1800b8e97  jmp     loc_1800B8F49
0x1800b8e9c  cmp     eax, 23000000h
0x1800b8ea1  jnz     short loc_1800B8ED3
0x1800b8ea3  lea     rax, [rsp+750h+var_720]
0x1800b8ea8  mov     [rsp+750h+var_730], rax; unsigned int *
0x1800b8ead  mov     r9d, edx; unsigned int
0x1800b8eb0  mov     rdx, [rsp+750h+var_718]; struct CMiniMdRW *
0x1800b8eb5  mov     rcx, r12; struct CMiniMdRW *
0x1800b8eb8  mov     r8, r15; struct IMetaModelCommon *
0x1800b8ebb  call    ?CreateAssemblyRefFromAssemblyRef@ImportHelper@@CAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@IPEAI@Z; ImportHelper::CreateAssemblyRefFromAssemblyRef(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,uint,uint *)
0x1800b8ec0  mov     ebx, eax
0x1800b8ec2  test    eax, eax
0x1800b8ec4  js      loc_1800B9135
0x1800b8eca  mov     edi, [rsp+750h+var_720]
0x1800b8ece  jmp     loc_1800B907E
0x1800b8ed3  cmp     eax, 1A000000h
0x1800b8ed8  jnz     loc_1800B907E
0x1800b8ede  mov     rax, [r15]
0x1800b8ee1  lea     r8, [rsp+750h+var_708]
0x1800b8ee6  mov     rcx, r15
0x1800b8ee9  mov     rax, [rax+38h]
0x1800b8eed  call    cs:__guard_dispatch_icall_fptr
0x1800b8ef3  mov     ebx, eax
0x1800b8ef5  test    eax, eax
0x1800b8ef7  js      loc_1800B9135
0x1800b8efd  mov     rax, [rsp+750h+var_708]
0x1800b8f02  mov     r8, [rsp+750h+var_6E8]
0x1800b8f07  sub     r8, rax
0x1800b8f0a  mov     r13d, 1
0x1800b8f10  movzx   ecx, byte ptr [rax]
0x1800b8f13  movzx   edx, byte ptr [rax+r8]
0x1800b8f18  sub     ecx, edx
0x1800b8f1a  jnz     short loc_1800B8F23
0x1800b8f1c  add     rax, r13
0x1800b8f1f  test    edx, edx
0x1800b8f21  jnz     short loc_1800B8F10
0x1800b8f23  mov     r12, [rsp+750h+var_718]
0x1800b8f28  test    ecx, ecx
0x1800b8f2a  jnz     short loc_1800B8F34
0x1800b8f2c  mov     edi, r13d
0x1800b8f2f  jmp     loc_1800B9083
0x1800b8f34  lea     r9, [rsp+750h+var_720]; unsigned int *
0x1800b8f39  mov     r8d, [rsp+750h+var_710]; unsigned int
0x1800b8f3e  mov     rdx, r15; struct IMetaModelCommon *
0x1800b8f41  mov     rcx, r12; this
0x1800b8f44  call    ?CreateModuleRefFromModuleRef@ImportHelper@@CAJPEAVCMiniMdRW@@PEAVIMetaModelCommon@@IPEAI@Z; ImportHelper::CreateModuleRefFromModuleRef(CMiniMdRW *,IMetaModelCommon *,uint,uint *)
0x1800b8f49  mov     ebx, eax
0x1800b8f4b  test    eax, eax
0x1800b8f4d  js      loc_1800B9135
0x1800b8f53  mov     edi, [rsp+750h+var_720]
0x1800b8f57  jmp     loc_1800B9083
0x1800b8f5c  mov     r9d, [rsp+750h+var_710]
0x1800b8f61  test    r8d, r9d
0x1800b8f64  jnz     loc_1800B9064
0x1800b8f6a  lea     r8, [rbp+650h+var_688]
0x1800b8f6e  test    r14, r14
0x1800b8f71  cmovnz  r8, r14
0x1800b8f75  lea     rdx, [rbp+650h+var_468]
0x1800b8f7c  test    rsi, rsi
0x1800b8f7f  cmovnz  rdx, rsi
0x1800b8f83  mov     rbx, [rsp+750h+var_708]
0x1800b8f88  mov     rax, [rbx]
0x1800b8f8b  lea     rcx, [rsp+750h+var_6F8]
0x1800b8f90  mov     [rsp+750h+var_730], rcx
0x1800b8f95  xor     r9d, r9d
0x1800b8f98  mov     rcx, [rsp+750h+var_6F0]
0x1800b8f9d  mov     r8, [r8+rcx*8-8]
0x1800b8fa2  mov     rdx, [rdx+rcx*8-8]
0x1800b8fa7  mov     rcx, rbx
0x1800b8faa  mov     rax, [rax+40h]
0x1800b8fae  call    cs:__guard_dispatch_icall_fptr
0x1800b8fb4  test    eax, eax
0x1800b8fb6  js      loc_1800B905D
0x1800b8fbc  mov     rax, [rbx]
0x1800b8fbf  lea     rcx, [rsp+750h+var_6F0]
0x1800b8fc4  mov     [rsp+750h+var_730], rcx
0x1800b8fc9  xor     r9d, r9d
0x1800b8fcc  xor     r8d, r8d
0x1800b8fcf  mov     edx, [rsp+750h+var_6F8]
0x1800b8fd3  mov     rcx, rbx
0x1800b8fd6  mov     rax, [rax+48h]
0x1800b8fda  call    cs:__guard_dispatch_icall_fptr
0x1800b8fe0  mov     ebx, eax
0x1800b8fe2  test    eax, eax
0x1800b8fe4  js      loc_1800B9135
0x1800b8fea  mov     r9d, dword ptr [rsp+750h+var_6F0]
0x1800b8fef  mov     eax, r9d
0x1800b8ff2  and     eax, 0FF000000h
0x1800b8ff7  cmp     eax, 26000000h
0x1800b8ffc  jnz     short loc_1800B9008
0x1800b8ffe  mov     ebx, 80004001h
0x1800b9003  jmp     loc_1800B9135
0x1800b9008  cmp     eax, 23000000h
0x1800b900d  jnz     short loc_1800B905D
0x1800b900f  mov     r13d, 1
0x1800b9015  mov     [rsp+750h+var_710], r9d
0x1800b901a  mov     eax, r9d
0x1800b901d  and     eax, 0FF000000h
0x1800b9022  cmp     eax, 23000000h
0x1800b9027  jnz     short loc_1800B9077
0x1800b9029  test    r12, r12
0x1800b902c  jz      short loc_1800B9038
0x1800b902e  cmp     [r12+0A0h], edi
0x1800b9036  jnz     short loc_1800B8FFE
0x1800b9038  lea     rax, [rsp+750h+var_720]
0x1800b903d  mov     rdx, [rsp+750h+var_718]
0x1800b9042  mov     rcx, r12
0x1800b9045  mov     [rsp+750h+var_730], rax
0x1800b904a  test    r13b, r13b
0x1800b904d  jz      loc_1800B8EB8
0x1800b9053  mov     r8, [rsp+750h+var_708]
0x1800b9058  jmp     loc_1800B8EBB
0x1800b905d  mov     r9d, [rsp+750h+var_710]
0x1800b9062  jmp     short loc_1800B901A
0x1800b9064  test    r9d, 0FF000000h
0x1800b906b  jnz     short loc_1800B901A
0x1800b906d  mov     ebx, 80004001h
0x1800b9072  jmp     loc_1800B912A
0x1800b9077  cmp     eax, 1A000000h
0x1800b907c  jz      short loc_1800B8FFE
0x1800b907e  mov     r12, [rsp+750h+var_718]
0x1800b9083  mov     r13, [rsp+750h+var_700]
0x1800b9088  test    edi, 0FF000000h
0x1800b908e  jnz     short loc_1800B910D
0x1800b9090  test    edi, 0FFFFFFh
0x1800b9096  jz      short loc_1800B910D
0x1800b9098  xor     ecx, ecx
0x1800b909a  mov     [rsp+750h+var_720], ecx
0x1800b909e  xor     ebx, ebx
0x1800b90a0  and     [r13+0], ecx
0x1800b90a4  mov     r15, [rbp+650h+var_698]
0x1800b90a8  shr     r15, 3
0x1800b90ac  dec     r15d
0x1800b90af  cmp     r15d, 0FFFFFFFFh
0x1800b90b3  jz      short loc_1800B9100
0x1800b90b5  lea     r8, [rbp+650h+var_688]
0x1800b90b9  test    r14, r14
0x1800b90bc  cmovnz  r8, r14
0x1800b90c0  lea     rax, [rbp+650h+var_468]
0x1800b90c7  test    rsi, rsi
0x1800b90ca  cmovnz  rax, rsi
  ... truncated ...
```
