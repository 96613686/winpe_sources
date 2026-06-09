# ImportHelper::ImportTypeDef(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,void const *,ulong,IMetaModelCommon *,uint,bool,uint *)

- ea: `0x1800b883c`
- end: `0x1800b8c0a`
- name: `?ImportTypeDef@ImportHelper@@SAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@PEBXK1I_NPEAI@Z`
- size: `974`
- prototype: `__int64 __fastcall(struct CMiniMdRW *, struct CMiniMdRW *, struct IMetaModelCommon *, const void *, unsigned int, struct IMetaModelCommon *, unsigned int, bool, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b74b4`

## callees

- `0x1800b83b4`
- `0x1800b8504`
- `0x1800b8644`
- `0x1800b883c`
- `0x1800b9204`
- `0x1800f0d20`
- `0x1800f5910`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800b8b6c`
- `KERNEL32!HeapFree` at `0x1800b8b9e`
- `KERNEL32!HeapFree` at `0x1800b8bd1`
- `KERNEL32!HeapFree` at `0x1800b8b6c`
- `KERNEL32!HeapFree` at `0x1800b8b9e`
- `KERNEL32!HeapFree` at `0x1800b8bd1`
- `KERNEL32!GetProcessHeap` at `0x1800b8b57`
- `KERNEL32!GetProcessHeap` at `0x1800b8b89`
- `KERNEL32!GetProcessHeap` at `0x1800b8bbc`
- `KERNEL32!GetProcessHeap` at `0x1800b8b57`
- `KERNEL32!GetProcessHeap` at `0x1800b8b89`
- `KERNEL32!GetProcessHeap` at `0x1800b8bbc`
- `ole32!IIDFromString` at `0x1800b8a2a`
- `ole32!IIDFromString` at `0x1800b8a2a`

## string_xrefs

- `0x1800b898f`: `ComRuntimeLibrary`
- `0x1800b89ba`: `System.Runtime.InteropServices.GuidAttribute`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ImportHelper::ImportTypeDef(
        struct CMiniMdRW *a1,
        struct CMiniMdRW *a2,
        struct IMetaModelCommon *a3,
        const void *a4,
        unsigned int a5,
        struct IMetaModelCommon *a6,
        unsigned int a7,
        bool a8,
        unsigned int *a9)
{
  void *v11; // r15
  void *v12; // r14
  void *v13; // rsi
  HRESULT NesterHierarchy; // ebx
  struct CMiniMdRW *v15; // r12
  _WORD *v16; // rdx
  __int64 i; // rcx
  __int64 v18; // rcx
  int TDNesterHierarchy; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  CMiniMdRW *v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h]
  char *Str1; // [rsp+48h] [rbp-B8h] BYREF
  _WORD *v28; // [rsp+50h] [rbp-B0h] BYREF
  GUID v29; // [rsp+60h] [rbp-A0h] BYREF
  GUID iid; // [rsp+70h] [rbp-90h] BYREF
  GUID v31; // [rsp+80h] [rbp-80h] BYREF
  GUID v32; // [rsp+90h] [rbp-70h] BYREF
  GUID v33; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v34[68]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v35[68]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _QWORD v36[68]; // [rsp+4F0h] [rbp+3F0h] BYREF
  OLECHAR sz[37]; // [rsp+710h] [rbp+610h] BYREF
  int v38; // [rsp+75Ah] [rbp+65Ah]

  v25 = a2;
  v26 = (__int64)a9;
  v11 = 0;
  v36[0] = 0;
  v36[1] = 0;
  v36[2] = 512;
  v12 = 0;
  v35[0] = 0;
  v35[1] = 0;
  v35[2] = 512;
  v13 = 0;
  v34[0] = 0;
  v34[1] = 0;
  v34[2] = 512;
  v31 = GUID_NULL;
  v32 = GUID_NULL;
  v29 = GUID_NULL;
  v33 = GUID_NULL;
  iid = GUID_NULL;
  v24 = 0;
  if ( a3 )
  {
    NesterHierarchy = (**(__int64 (__fastcall ***)(struct IMetaModelCommon *, _QWORD, GUID *, const void *))a3)(
                        a3,
                        0,
                        &v31,
                        a4);
    if ( NesterHierarchy < 0 )
      goto LABEL_32;
  }
  NesterHierarchy = (**(__int64 (__fastcall ***)(struct IMetaModelCommon *, char **, GUID *, const void *))a6)(
                      a6,
                      &Str1,
                      &v29,
                      a4);
  if ( NesterHierarchy < 0 )
    goto LABEL_32;
  if ( a1 )
  {
    NesterHierarchy = (**(__int64 (__fastcall ***)(struct CMiniMdRW *, _QWORD, GUID *))a1)(a1, 0, &v32);
    if ( NesterHierarchy < 0 )
      goto LABEL_32;
  }
  v15 = v25;
  NesterHierarchy = (**(__int64 (__fastcall ***)(CMiniMdRW *, _QWORD, GUID *))v25)(v25, 0, &v33);
  if ( NesterHierarchy < 0 )
    goto LABEL_32;
  if ( !a3 && !strcmp(Str1, "ComRuntimeLibrary") )
  {
    NesterHierarchy = (*(__int64 (__fastcall **)(struct IMetaModelCommon *, __int64, const char *, _WORD **, CMiniMdRW **))(*(_QWORD *)a6 + 88LL))(
                        a6,
                        1,
                        "System.Runtime.InteropServices.GuidAttribute",
                        &v28,
                        &v25);
    if ( NesterHierarchy != 1 )
    {
      v16 = v28;
      if ( (_DWORD)v25 == 41 || *v28 == 1 )
      {
        for ( i = 1; i <= 36; ++i )
          sz[i] = *((unsigned __int8 *)v16 + i + 2);
        sz[0] = 123;
        v38 = 125;
        NesterHierarchy = IIDFromString(sz, &iid);
      }
    }
    v18 = *(_QWORD *)&iid.Data1 - *(_QWORD *)&LIBID_ComPlusRuntime.Data1;
    if ( *(_QWORD *)&iid.Data1 == *(_QWORD *)&LIBID_ComPlusRuntime.Data1 )
      v18 = *(_QWORD *)iid.Data4 - *(_QWORD *)LIBID_ComPlusRuntime.Data4;
    if ( !v18 )
      goto LABEL_24;
  }
  if ( *(_OWORD *)&v31 != *(_OWORD *)&v32 )
  {
    if ( a3 )
    {
      NesterHierarchy = -2147467263;
      goto LABEL_32;
    }
    goto LABEL_24;
  }
  if ( *(_QWORD *)&v29.Data1 == *(_QWORD *)&v33.Data1 )
  {
    if ( *(_QWORD *)v29.Data4 == *(_QWORD *)v33.Data4 )
    {
      *(_DWORD *)v26 = a7;
      goto LABEL_32;
    }
    if ( *(_OWORD *)&v29 == *(_OWORD *)&v33 )
      goto LABEL_24;
  }
  NesterHierarchy = ImportHelper::CreateModuleRefFromScope(v15, a6, &v24);
  if ( NesterHierarchy >= 0 )
  {
LABEL_24:
    if ( (a7 & 0xFF000000) == 0x2000000 )
      TDNesterHierarchy = ImportHelper::GetTDNesterHierarchy(
                            (_DWORD)a6,
                            a7,
                            (unsigned int)v36,
                            (unsigned int)v34,
                            (__int64)v35);
    else
      TDNesterHierarchy = ImportHelper::GetTRNesterHierarchy(
                            (_DWORD)a6,
                            a7,
                            (unsigned int)v36,
                            (unsigned int)v34,
                            (__int64)v35);
    NesterHierarchy = TDNesterHierarchy;
    if ( TDNesterHierarchy >= 0 )
      NesterHierarchy = ImportHelper::CreateNesterHierarchy(v15, v26);
    v13 = (void *)v34[0];
    v12 = (void *)v35[0];
    v11 = (void *)v36[0];
  }
LABEL_32:
  if ( v13 )
  {
    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, v13);
    v13 = 0;
    v34[0] = 0;
  }
  if ( v12 )
  {
    v21 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v21 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v21;
    }
    HeapFree(v21, 0, v12);
    v35[0] = v13;
  }
  if ( v11 )
  {
    v22 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v22 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v22;
    }
    HeapFree(v22, 0, v11);
    v36[0] = v13;
  }
  return (unsigned int)NesterHierarchy;
}

```

## disassembly

```asm
0x1800b883c  mov     [rsp-8+arg_18], rbx
0x1800b8841  push    rbp
0x1800b8842  push    rsi
0x1800b8843  push    rdi
0x1800b8844  push    r12
0x1800b8846  push    r13
0x1800b8848  push    r14
0x1800b884a  push    r15
0x1800b884c  lea     rbp, [rsp-670h]
0x1800b8854  sub     rsp, 770h
0x1800b885b  mov     rax, cs:__security_cookie
0x1800b8862  xor     rax, rsp
0x1800b8865  mov     [rbp+6A0h+var_40], rax
0x1800b886c  mov     r13, r8
0x1800b886f  mov     [rsp+7A0h+var_768], rdx
0x1800b8874  mov     r12, rcx
0x1800b8877  mov     rdi, [rbp+6A0h+arg_28]
0x1800b887e  mov     rax, [rbp+6A0h+arg_40]
0x1800b8885  mov     [rsp+7A0h+var_760], rax
0x1800b888a  xor     ecx, ecx
0x1800b888c  mov     r15d, ecx
0x1800b888f  mov     [rbp+6A0h+var_2B0], rcx
0x1800b8896  mov     [rbp+6A0h+var_2A8], rcx
0x1800b889d  mov     eax, 200h
0x1800b88a2  mov     [rbp+6A0h+var_2A0], rax
0x1800b88a9  mov     r14d, ecx
0x1800b88ac  mov     [rbp+6A0h+var_4D0], rcx
0x1800b88b3  mov     [rbp+6A0h+var_4C8], rcx
0x1800b88ba  mov     [rbp+6A0h+var_4C0], rax
0x1800b88c1  mov     esi, ecx
0x1800b88c3  mov     [rbp+6A0h+var_6F0], rcx
0x1800b88c7  mov     [rbp+6A0h+var_6E8], rcx
0x1800b88cb  mov     [rbp+6A0h+var_6E0], rax
0x1800b88cf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b88d6  movdqa  [rbp+6A0h+var_720], xmm0
0x1800b88db  movdqa  [rbp+6A0h+var_710], xmm0
0x1800b88e0  movdqa  [rsp+7A0h+var_740], xmm0
0x1800b88e6  movdqa  [rbp+6A0h+var_700], xmm0
0x1800b88eb  movdqu  xmmword ptr [rsp+7A0h+iid.Data1], xmm0
0x1800b88f1  mov     [rsp+7A0h+var_770], ecx
0x1800b88f5  test    r8, r8
0x1800b88f8  jz      short loc_1800B8919
0x1800b88fa  mov     rax, [r8]
0x1800b88fd  lea     r8, [rbp+6A0h+var_720]
0x1800b8901  xor     edx, edx
0x1800b8903  mov     rcx, r13
0x1800b8906  mov     rax, [rax]
0x1800b8909  call    cs:__guard_dispatch_icall_fptr
0x1800b890f  mov     ebx, eax
0x1800b8911  test    eax, eax
0x1800b8913  js      loc_1800B8B46
0x1800b8919  mov     rax, [rdi]
0x1800b891c  lea     r8, [rsp+7A0h+var_740]
0x1800b8921  lea     rdx, [rsp+7A0h+Str1]
0x1800b8926  mov     rcx, rdi
0x1800b8929  mov     rax, [rax]
0x1800b892c  call    cs:__guard_dispatch_icall_fptr
0x1800b8932  mov     ebx, eax
0x1800b8934  test    eax, eax
0x1800b8936  js      loc_1800B8B46
0x1800b893c  test    r12, r12
0x1800b893f  jz      short loc_1800B8961
0x1800b8941  mov     rax, [r12]
0x1800b8945  lea     r8, [rbp+6A0h+var_710]
0x1800b8949  xor     edx, edx
0x1800b894b  mov     rcx, r12
0x1800b894e  mov     rax, [rax]
0x1800b8951  call    cs:__guard_dispatch_icall_fptr
0x1800b8957  mov     ebx, eax
0x1800b8959  test    eax, eax
0x1800b895b  js      loc_1800B8B46
0x1800b8961  mov     r12, [rsp+7A0h+var_768]
0x1800b8966  mov     rax, [r12]
0x1800b896a  lea     r8, [rbp+6A0h+var_700]
0x1800b896e  xor     edx, edx
0x1800b8970  mov     rcx, r12
0x1800b8973  mov     rax, [rax]
0x1800b8976  call    cs:__guard_dispatch_icall_fptr
0x1800b897c  mov     ebx, eax
0x1800b897e  test    eax, eax
0x1800b8980  js      loc_1800B8B46
0x1800b8986  test    r13, r13
0x1800b8989  jnz     loc_1800B8A58
0x1800b898f  lea     rdx, aComruntimelibr; "ComRuntimeLibrary"
0x1800b8996  mov     rcx, [rsp+7A0h+Str1]; Str1
0x1800b899b  call    strcmp
0x1800b89a0  test    eax, eax
0x1800b89a2  jnz     loc_1800B8A58
0x1800b89a8  mov     rax, [rdi]
0x1800b89ab  lea     rcx, [rsp+7A0h+var_768]
0x1800b89b0  mov     [rsp+7A0h+var_780], rcx
0x1800b89b5  lea     r9, [rsp+7A0h+var_750]
0x1800b89ba  lea     r8, aSystemRuntimeI_3; "System.Runtime.InteropServices.GuidAttr"...
0x1800b89c1  lea     edx, [r13+1]
0x1800b89c5  mov     rcx, rdi
0x1800b89c8  mov     rax, [rax+58h]
0x1800b89cc  call    cs:__guard_dispatch_icall_fptr
0x1800b89d2  mov     ebx, eax
0x1800b89d4  lea     r8d, [r13+1]
0x1800b89d8  cmp     eax, r8d
0x1800b89db  jz      short loc_1800B8A32
0x1800b89dd  mov     rdx, [rsp+7A0h+var_750]
0x1800b89e2  cmp     dword ptr [rsp+7A0h+var_768], 29h ; ')'
0x1800b89e7  jz      short loc_1800B89EF
0x1800b89e9  cmp     [rdx], r8w
0x1800b89ed  jnz     short loc_1800B8A32
0x1800b89ef  mov     rcx, r8
0x1800b89f2  movzx   eax, byte ptr [rdx+rcx+2]
0x1800b89f7  mov     [rbp+rcx*2+6A0h+sz], ax
0x1800b89ff  add     rcx, r8
0x1800b8a02  cmp     rcx, 24h ; '$'
0x1800b8a06  jle     short loc_1800B89F2
0x1800b8a08  mov     eax, 7Bh ; '{'
0x1800b8a0d  mov     [rbp+6A0h+sz], ax
0x1800b8a14  mov     [rbp+6A0h+var_46], 7Dh ; '}'
0x1800b8a1e  lea     rdx, [rsp+7A0h+iid]; lpiid
0x1800b8a23  lea     rcx, [rbp+6A0h+sz]; lpsz
0x1800b8a2a  call    cs:__imp_IIDFromString
0x1800b8a30  mov     ebx, eax
0x1800b8a32  mov     rcx, qword ptr [rsp+7A0h+iid.Data1]
0x1800b8a37  sub     rcx, qword ptr cs:LIBID_ComPlusRuntime.Data1
0x1800b8a3e  jnz     short loc_1800B8A4C
0x1800b8a40  mov     rcx, qword ptr [rsp+7A0h+iid.Data4]
0x1800b8a45  sub     rcx, qword ptr cs:LIBID_ComPlusRuntime.Data4
0x1800b8a4c  xor     eax, eax
0x1800b8a4e  test    rcx, rcx
0x1800b8a51  setz    al
0x1800b8a54  test    eax, eax
0x1800b8a56  jnz     short loc_1800B8AC4
0x1800b8a58  mov     rax, qword ptr [rbp+6A0h+var_720]
0x1800b8a5c  cmp     rax, qword ptr [rbp+6A0h+var_710]
0x1800b8a60  jnz     loc_1800B8AF9
0x1800b8a66  mov     rax, qword ptr [rbp+6A0h+var_720+8]
0x1800b8a6a  cmp     rax, qword ptr [rbp+6A0h+var_710+8]
0x1800b8a6e  jnz     loc_1800B8AF9
0x1800b8a74  mov     rax, qword ptr [rbp+6A0h+var_700+8]
0x1800b8a78  mov     rcx, qword ptr [rbp+6A0h+var_700]
0x1800b8a7c  cmp     qword ptr [rsp+7A0h+var_740], rcx
0x1800b8a81  jnz     short loc_1800B8AAA
0x1800b8a83  cmp     qword ptr [rsp+7A0h+var_740+8], rax
0x1800b8a88  jnz     short loc_1800B8A9C
0x1800b8a8a  mov     eax, [rbp+6A0h+arg_30]
0x1800b8a90  mov     rcx, [rsp+7A0h+var_760]
0x1800b8a95  mov     [rcx], eax
0x1800b8a97  jmp     loc_1800B8B46
0x1800b8a9c  cmp     qword ptr [rsp+7A0h+var_740], rcx
0x1800b8aa1  jnz     short loc_1800B8AAA
0x1800b8aa3  cmp     qword ptr [rsp+7A0h+var_740+8], rax
0x1800b8aa8  jz      short loc_1800B8AC4
0x1800b8aaa  lea     r8, [rsp+7A0h+var_770]; unsigned int *
0x1800b8aaf  mov     rdx, rdi; struct IMetaModelCommon *
0x1800b8ab2  mov     rcx, r12; this
0x1800b8ab5  call    ?CreateModuleRefFromScope@ImportHelper@@CAJPEAVCMiniMdRW@@PEAVIMetaModelCommon@@PEAI@Z; ImportHelper::CreateModuleRefFromScope(CMiniMdRW *,IMetaModelCommon *,uint *)
0x1800b8aba  mov     ebx, eax
0x1800b8abc  test    eax, eax
0x1800b8abe  js      loc_1800B8B46
0x1800b8ac4  mov     edx, [rbp+6A0h+arg_30]
0x1800b8aca  mov     eax, edx
0x1800b8acc  and     eax, 0FF000000h
0x1800b8ad1  lea     r9, [rbp+6A0h+var_6F0]
0x1800b8ad5  lea     r8, [rbp+6A0h+var_2B0]
0x1800b8adc  mov     rcx, rdi
0x1800b8adf  cmp     eax, 2000000h
0x1800b8ae4  lea     rax, [rbp+6A0h+var_4D0]
0x1800b8aeb  mov     [rsp+7A0h+var_780], rax
0x1800b8af0  jnz     short loc_1800B8B05
0x1800b8af2  call    ?GetTDNesterHierarchy@ImportHelper@@CAJPEAVIMetaModelCommon@@IAEAV?$CQuickArray@I@@AEAV?$CQuickArray@PEBD@@2@Z; ImportHelper::GetTDNesterHierarchy(IMetaModelCommon *,uint,CQuickArray<uint> &,CQuickArray<char const *> &,CQuickArray<char const *> &)
0x1800b8af7  jmp     short loc_1800B8B0A
0x1800b8af9  test    r13, r13
0x1800b8afc  jz      short loc_1800B8AC4
0x1800b8afe  mov     ebx, 80004001h
0x1800b8b03  jmp     short loc_1800B8B46
0x1800b8b05  call    ?GetTRNesterHierarchy@ImportHelper@@CAJPEAVIMetaModelCommon@@IAEAV?$CQuickArray@I@@AEAV?$CQuickArray@PEBD@@2@Z; ImportHelper::GetTRNesterHierarchy(IMetaModelCommon *,uint,CQuickArray<uint> &,CQuickArray<char const *> &,CQuickArray<char const *> &)
0x1800b8b0a  mov     ebx, eax
0x1800b8b0c  test    eax, eax
0x1800b8b0e  js      short loc_1800B8B34
0x1800b8b10  mov     rcx, [rsp+7A0h+var_760]
0x1800b8b15  mov     [rsp+7A0h+var_780], rcx; __int64
0x1800b8b1a  mov     r9d, [rsp+7A0h+var_770]
0x1800b8b1f  lea     r8, [rbp+6A0h+var_4D0]
0x1800b8b26  lea     rdx, [rbp+6A0h+var_6F0]
0x1800b8b2a  mov     rcx, r12; this
0x1800b8b2d  call    ?CreateNesterHierarchy@ImportHelper@@SAJPEAVCMiniMdRW@@AEAV?$CQuickArray@PEBD@@1IPEAI@Z; ImportHelper::CreateNesterHierarchy(CMiniMdRW *,CQuickArray<char const *> &,CQuickArray<char const *> &,uint,uint *)
0x1800b8b32  mov     ebx, eax
0x1800b8b34  mov     rsi, [rbp+6A0h+var_6F0]
0x1800b8b38  mov     r14, [rbp+6A0h+var_4D0]
0x1800b8b3f  mov     r15, [rbp+6A0h+var_2B0]
0x1800b8b46  test    rsi, rsi
0x1800b8b49  jz      short loc_1800B8B78
0x1800b8b4b  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800b8b52  test    rax, rax
0x1800b8b55  jnz     short loc_1800B8B64
0x1800b8b57  call    cs:__imp_GetProcessHeap
0x1800b8b5d  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800b8b64  mov     r8, rsi; lpMem
0x1800b8b67  xor     edx, edx; dwFlags
0x1800b8b69  mov     rcx, rax; hHeap
0x1800b8b6c  call    cs:__imp_HeapFree
0x1800b8b72  xor     esi, esi
0x1800b8b74  mov     [rbp+6A0h+var_6F0], rsi
0x1800b8b78  test    r14, r14
0x1800b8b7b  jz      short loc_1800B8BAB
0x1800b8b7d  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800b8b84  test    rax, rax
0x1800b8b87  jnz     short loc_1800B8B96
0x1800b8b89  call    cs:__imp_GetProcessHeap
0x1800b8b8f  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800b8b96  mov     r8, r14; lpMem
0x1800b8b99  xor     edx, edx; dwFlags
0x1800b8b9b  mov     rcx, rax; hHeap
0x1800b8b9e  call    cs:__imp_HeapFree
0x1800b8ba4  mov     [rbp+6A0h+var_4D0], rsi
0x1800b8bab  test    r15, r15
0x1800b8bae  jz      short loc_1800B8BDE
0x1800b8bb0  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800b8bb7  test    rax, rax
0x1800b8bba  jnz     short loc_1800B8BC9
0x1800b8bbc  call    cs:__imp_GetProcessHeap
0x1800b8bc2  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800b8bc9  mov     r8, r15; lpMem
0x1800b8bcc  xor     edx, edx; dwFlags
0x1800b8bce  mov     rcx, rax; hHeap
0x1800b8bd1  call    cs:__imp_HeapFree
0x1800b8bd7  mov     [rbp+6A0h+var_2B0], rsi
0x1800b8bde  mov     eax, ebx
0x1800b8be0  mov     rcx, [rbp+6A0h+var_40]
0x1800b8be7  xor     rcx, rsp; StackCookie
0x1800b8bea  call    __security_check_cookie
0x1800b8bef  mov     rbx, [rsp+7A0h+arg_18]
0x1800b8bf7  add     rsp, 770h
0x1800b8bfe  pop     r15
0x1800b8c00  pop     r14
0x1800b8c02  pop     r13
0x1800b8c04  pop     r12
0x1800b8c06  pop     rdi
0x1800b8c07  pop     rsi
0x1800b8c08  pop     rbp
0x1800b8c09  retn
```
