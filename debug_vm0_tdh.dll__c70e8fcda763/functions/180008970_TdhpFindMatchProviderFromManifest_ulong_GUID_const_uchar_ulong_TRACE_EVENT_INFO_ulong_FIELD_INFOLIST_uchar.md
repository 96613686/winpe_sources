# TdhpFindMatchProviderFromManifest(ulong,_GUID const *,uchar,ulong *,_TRACE_EVENT_INFO * * *,ulong *,FIELD_INFOLIST *,uchar *)

- ea: `0x180008970`
- end: `0x180008c55`
- name: `?TdhpFindMatchProviderFromManifest@@YAKKPEBU_GUID@@EPEAKPEAPEAPEAU_TRACE_EVENT_INFO@@1PEAUFIELD_INFOLIST@@PEAE@Z`
- size: `741`
- prototype: `__int64 __fastcall(int, struct _GUID *, char, unsigned int *, struct _TRACE_EVENT_INFO ***, unsigned int *, struct FIELD_INFOLIST *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180004fb0`
- `0x180018198`

## callees

- `0x1800086f4`
- `0x18000872c`
- `0x180008970`
- `0x180008c5c`
- `0x180009570`
- `0x180009a34`
- `0x180009b80`
- `0x180009bdc`
- `0x180009c7c`
- `0x1800137e8`
- `0x180017c40`
- `0x18001c764`
- `0x1800207c0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c34`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TdhpFindMatchProviderFromManifest(
        int a1,
        struct _GUID *a2,
        char a3,
        unsigned int *a4,
        struct _TRACE_EVENT_INFO ***a5,
        unsigned int *a6,
        struct FIELD_INFOLIST *a7,
        unsigned __int8 *a8)
{
  __int64 v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  unsigned int v14; // edi
  __int64 i; // rdi
  void *v17; // rdi
  HANDLE ProcessHeap; // rax
  struct PUBLISHER_LOOKUP_ENTRY near **v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h]
  char v21; // [rsp+5Ch] [rbp-A4h]
  void ***v22; // [rsp+60h] [rbp-A0h]
  int v23[2]; // [rsp+68h] [rbp-98h] BYREF
  void **v24; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v25; // [rsp+78h] [rbp-88h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  int v27[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v28; // [rsp+90h] [rbp-70h]
  __int128 v29; // [rsp+A0h] [rbp-60h]
  _QWORD v30[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-40h] BYREF
  int v32; // [rsp+C8h] [rbp-38h]
  char v33; // [rsp+CCh] [rbp-34h]
  _QWORD *v34; // [rsp+D0h] [rbp-30h]
  int v35[50]; // [rsp+D8h] [rbp-28h] BYREF

  v26 = (__int64)a4;
  v25 = a6;
  v28 = 0;
  v29 = 0;
  *(_QWORD *)v27 = &PublisherManifestTdhConfig::`vftable';
  v24 = &ModuleLoaderImpl::`vftable';
  v30[0] = &ManifestResourceLoaderImpl::`vftable';
  v30[1] = a2;
  v22 = &v24;
  v19 = &g_EnvironmentTable;
  v20 = 2;
  v21 = 0;
  PublisherManifestResource::PublisherManifestResource((PublisherManifestResource *)v35);
  v34 = v30;
  v31 = v11;
  v32 = v12;
  v33 = 0;
  *(_QWORD *)v23 = 0;
  *a5 = 0;
  if ( !PublisherManifestTdhConfig::ReadConfig((PublisherManifestTdhConfig *)v27, a2) )
  {
    if ( *((_QWORD *)&v29 + 1) )
    {
      v13 = PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(&v19, *((_QWORD *)&v29 + 1));
      if ( v13 )
      {
        PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(&v31);
        PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(&v19);
        goto LABEL_17;
      }
    }
    if ( *((_QWORD *)&v28 + 1) )
    {
      v13 = PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(&v31);
      if ( !v13 )
      {
        v13 = PmresEnumEvents(
                a1,
                (__int64)v27,
                *(const void **)v23,
                (PublisherManifestResource *)v35,
                a2,
                a3,
                (unsigned int *)v26,
                a5,
                v25);
        if ( !v13 )
        {
          if ( !a7 || !a8 || *a8 )
          {
LABEL_13:
            if ( v33 )
              (*(void (__fastcall **)(_QWORD *, int *))(*v34 + 8LL))(v34, v35);
            PublisherManifestResource::~PublisherManifestResource((PublisherManifestResource *)v35);
            if ( v21 )
              ((void (__fastcall *)(void ***, int *))(*v22)[1])(v22, v23);
            goto LABEL_17;
          }
          v14 = 0;
          while ( 1 )
          {
            v13 = FillFieldInfoListFromResource(
                    *(const void **)v23,
                    (PublisherManifestResource *)v35,
                    (__int64)a7 + 16 * v14);
            *a8 = 1;
            if ( v13 )
              break;
            if ( ++v14 >= 5 )
              goto LABEL_13;
          }
          for ( i = 0; i != 5; ++i )
            TdhpClearFieldInfoList((struct FIELD_INFOLIST *)((char *)a7 + 16 * i));
        }
      }
    }
    else
    {
      v13 = 4316;
    }
    v17 = *a5;
    if ( *a5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v17);
      *a5 = 0;
    }
    goto LABEL_13;
  }
  if ( v33 )
    (*(void (__fastcall **)(_QWORD *, int *))(*v34 + 8LL))(v34, v35);
  PublisherManifestResource::~PublisherManifestResource((PublisherManifestResource *)v35);
  if ( v21 )
    ((void (__fastcall *)(void ***, int *))(*v22)[1])(v22, v23);
  v13 = -1073217792;
LABEL_17:
  *(_QWORD *)v27 = &PublisherManifestConfig::`vftable';
  PublisherManifestConfig::Free((PublisherManifestConfig *)v27);
  return v13;
}

```

## disassembly

```asm
0x180008970  mov     [rsp-8+arg_0], rbx
0x180008975  push    rbp
0x180008976  push    rsi
0x180008977  push    rdi
0x180008978  push    r12
0x18000897a  push    r13
0x18000897c  push    r14
0x18000897e  push    r15
0x180008980  lea     rbp, [rsp-0B0h]
0x180008988  sub     rsp, 1B0h
0x18000898f  mov     rax, cs:__security_cookie
0x180008996  xor     rax, rsp
0x180008999  mov     [rbp+0E0h+var_40], rax
0x1800089a0  mov     [rbp+0E0h+var_160], r9
0x1800089a4  mov     r12b, r8b
0x1800089a7  mov     rdi, rdx
0x1800089aa  mov     r13d, ecx
0x1800089ad  mov     r14, [rbp+0E0h+arg_20]
0x1800089b4  mov     rax, [rbp+0E0h+arg_28]
0x1800089bb  mov     [rsp+1E0h+var_168], rax
0x1800089c0  mov     r15, [rbp+0E0h+arg_30]
0x1800089c7  mov     rsi, [rbp+0E0h+arg_38]
0x1800089ce  xorps   xmm0, xmm0
0x1800089d1  movdqu  [rbp+0E0h+var_150], xmm0
0x1800089d6  xorps   xmm1, xmm1
0x1800089d9  movdqu  [rbp+0E0h+var_140], xmm1
0x1800089de  lea     rax, ??_7PublisherManifestTdhConfig@@6B@; const PublisherManifestTdhConfig::`vftable'
0x1800089e5  mov     qword ptr [rbp+0E0h+var_158], rax
0x1800089e9  lea     rax, ??_7ModuleLoaderImpl@@6B@; const ModuleLoaderImpl::`vftable'
0x1800089f0  mov     [rsp+1E0h+var_170], rax
0x1800089f5  lea     rax, ??_7ManifestResourceLoaderImpl@@6B@; const ManifestResourceLoaderImpl::`vftable'
0x1800089fc  mov     [rbp+0E0h+var_130], rax
0x180008a00  mov     [rbp+0E0h+var_128], rdx
0x180008a04  lea     rax, [rsp+1E0h+var_170]
0x180008a09  mov     [rsp+1E0h+var_180], rax
0x180008a0e  lea     r8, ?g_EnvironmentTable@@3PAUPUBLISHER_LOOKUP_ENTRY@@A; PUBLISHER_LOOKUP_ENTRY near * g_EnvironmentTable
0x180008a15  mov     [rsp+1E0h+var_190], r8
0x180008a1a  mov     edx, 2
0x180008a1f  mov     [rsp+1E0h+var_188], edx
0x180008a23  xor     ebx, ebx
0x180008a25  mov     [rsp+1E0h+var_184], bl
0x180008a29  lea     rcx, [rbp+0E0h+var_108]; this
0x180008a2d  call    ??0PublisherManifestResource@@QEAA@XZ; PublisherManifestResource::PublisherManifestResource(void)
0x180008a32  lea     rcx, [rbp+0E0h+var_130]
0x180008a36  mov     [rbp+0E0h+var_110], rcx
0x180008a3a  mov     [rbp+0E0h+var_120], r8
0x180008a3e  mov     [rbp+0E0h+var_118], edx
0x180008a41  mov     [rbp+0E0h+var_114], bl
0x180008a44  mov     qword ptr [rsp+1E0h+var_178], rbx
0x180008a49  mov     [r14], rbx
0x180008a4c  mov     rdx, rdi; struct _GUID *
0x180008a4f  lea     rcx, [rbp+0E0h+var_158]; this
0x180008a53  call    ?ReadConfig@PublisherManifestTdhConfig@@UEAAKAEBU_GUID@@@Z; PublisherManifestTdhConfig::ReadConfig(_GUID const &)
0x180008a58  test    eax, eax
0x180008a5a  jnz     loc_180008B9C
0x180008a60  mov     rdx, qword ptr [rbp+0E0h+var_140+8]
0x180008a64  test    rdx, rdx
0x180008a67  jz      short loc_180008A7D
0x180008a69  lea     rcx, [rsp+1E0h+var_190]
0x180008a6e  call    ?LookupNLoad@?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(wchar_t const *)
0x180008a73  mov     ebx, eax
0x180008a75  test    eax, eax
0x180008a77  jnz     loc_180008BE6
0x180008a7d  mov     rdx, qword ptr [rbp+0E0h+var_150+8]
0x180008a81  test    rdx, rdx
0x180008a84  jz      loc_180008BFF
0x180008a8a  lea     rcx, [rbp+0E0h+var_120]
0x180008a8e  call    ?LookupNLoad@?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(wchar_t const *)
0x180008a93  mov     ebx, eax
0x180008a95  test    eax, eax
0x180008a97  jnz     loc_180008C20
0x180008a9d  mov     rax, [rsp+1E0h+var_168]
0x180008aa2  mov     [rsp+1E0h+var_1A0], rax; unsigned int *
0x180008aa7  mov     [rsp+1E0h+var_1A8], r14; __int64
0x180008aac  mov     rax, [rbp+0E0h+var_160]
0x180008ab0  mov     [rsp+1E0h+var_1B0], rax; __int64
0x180008ab5  mov     [rsp+1E0h+var_1B8], r12b; char
0x180008aba  mov     [rsp+1E0h+var_1C0], rdi; __int64
0x180008abf  lea     r9, [rbp+0E0h+var_108]; int
0x180008ac3  mov     r8, qword ptr [rsp+1E0h+var_178]; int
0x180008ac8  lea     rdx, [rbp+0E0h+var_158]; int
0x180008acc  mov     ecx, r13d; int
0x180008acf  call    PmresEnumEvents
0x180008ad4  mov     ebx, eax
0x180008ad6  test    eax, eax
0x180008ad8  jnz     loc_180008C20
0x180008ade  test    r15, r15
0x180008ae1  jz      short loc_180008B1A
0x180008ae3  test    rsi, rsi
0x180008ae6  jz      short loc_180008B1A
0x180008ae8  cmp     [rsi], al
0x180008aea  jnz     short loc_180008B1A
0x180008aec  xor     edi, edi
0x180008aee  mov     r8d, edi
0x180008af1  shl     r8, 4
0x180008af5  add     r8, r15
0x180008af8  lea     rdx, [rbp+0E0h+var_108]
0x180008afc  mov     rcx, qword ptr [rsp+1E0h+var_178]
0x180008b01  call    FillFieldInfoListFromResource
0x180008b06  mov     ebx, eax
0x180008b08  mov     byte ptr [rsi], 1
0x180008b0b  test    eax, eax
0x180008b0d  jnz     loc_180008C06
0x180008b13  inc     edi
0x180008b15  cmp     edi, 5
0x180008b18  jb      short loc_180008AEE
0x180008b1a  cmp     [rbp+0E0h+var_114], 0
0x180008b1e  jz      short loc_180008B34
0x180008b20  mov     rcx, [rbp+0E0h+var_110]
0x180008b24  mov     rax, [rcx]
0x180008b27  lea     rdx, [rbp+0E0h+var_108]
0x180008b2b  mov     rax, [rax+8]
0x180008b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b34  lea     rcx, [rbp+0E0h+var_108]; this
0x180008b38  call    ??1PublisherManifestResource@@QEAA@XZ; PublisherManifestResource::~PublisherManifestResource(void)
0x180008b3d  nop
0x180008b3e  cmp     [rsp+1E0h+var_184], 0
0x180008b43  jz      short loc_180008B5C
0x180008b45  mov     rcx, [rsp+1E0h+var_180]
0x180008b4a  mov     rax, [rcx]
0x180008b4d  lea     rdx, [rsp+1E0h+var_178]
0x180008b52  mov     rax, [rax+8]
0x180008b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b5b  nop
0x180008b5c  lea     rax, ??_7PublisherManifestConfig@@6B@; const PublisherManifestConfig::`vftable'
0x180008b63  mov     qword ptr [rbp+0E0h+var_158], rax
0x180008b67  lea     rcx, [rbp+0E0h+var_158]; this
0x180008b6b  call    ?Free@PublisherManifestConfig@@AEAAXXZ; PublisherManifestConfig::Free(void)
0x180008b70  mov     eax, ebx
0x180008b72  mov     rcx, [rbp+0E0h+var_40]
0x180008b79  xor     rcx, rsp; StackCookie
0x180008b7c  call    __security_check_cookie
0x180008b81  mov     rbx, [rsp+1E0h+arg_0]
0x180008b89  add     rsp, 1B0h
0x180008b90  pop     r15
0x180008b92  pop     r14
0x180008b94  pop     r13
0x180008b96  pop     r12
0x180008b98  pop     rdi
0x180008b99  pop     rsi
0x180008b9a  pop     rbp
0x180008b9b  retn
0x180008b9c  cmp     [rbp+0E0h+var_114], bl
0x180008b9f  jz      short loc_180008BB5
0x180008ba1  mov     rcx, [rbp+0E0h+var_110]
0x180008ba5  mov     rax, [rcx]
0x180008ba8  lea     rdx, [rbp+0E0h+var_108]
0x180008bac  mov     rax, [rax+8]
0x180008bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb5  lea     rcx, [rbp+0E0h+var_108]; this
0x180008bb9  call    ??1PublisherManifestResource@@QEAA@XZ; PublisherManifestResource::~PublisherManifestResource(void)
0x180008bbe  nop
0x180008bbf  cmp     [rsp+1E0h+var_184], bl
0x180008bc3  jz      short loc_180008BDC
0x180008bc5  mov     rcx, [rsp+1E0h+var_180]
0x180008bca  mov     rax, [rcx]
0x180008bcd  lea     rdx, [rsp+1E0h+var_178]
0x180008bd2  mov     rax, [rax+8]
0x180008bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bdb  nop
0x180008bdc  mov     ebx, 0C007FF00h
0x180008be1  jmp     loc_180008B5C
0x180008be6  lea     rcx, [rbp+0E0h+var_120]
0x180008bea  call    ??1?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAA@XZ; PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(void)
0x180008bef  nop
0x180008bf0  lea     rcx, [rsp+1E0h+var_190]
0x180008bf5  call    ??1?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAA@XZ; PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(void)
0x180008bfa  jmp     loc_180008B5C
0x180008bff  mov     ebx, 10DCh
0x180008c04  jmp     short loc_180008C20
0x180008c06  xor     edi, edi
0x180008c08  mov     rcx, rdi
0x180008c0b  shl     rcx, 4
0x180008c0f  add     rcx, r15; struct FIELD_INFOLIST *
0x180008c12  call    ?TdhpClearFieldInfoList@@YAXPEAUFIELD_INFOLIST@@@Z; TdhpClearFieldInfoList(FIELD_INFOLIST *)
0x180008c17  inc     rdi
0x180008c1a  cmp     rdi, 5
0x180008c1e  jnz     short loc_180008C08
0x180008c20  test    ebx, ebx
0x180008c22  jz      loc_180008B1A
0x180008c28  mov     rdi, [r14]
0x180008c2b  test    rdi, rdi
0x180008c2e  jz      loc_180008B1A
0x180008c34  call    cs:__imp_GetProcessHeap
0x180008c3a  mov     r8, rdi; lpMem
0x180008c3d  xor     edx, edx; dwFlags
0x180008c3f  mov     rcx, rax; hHeap
0x180008c42  call    cs:__imp_HeapFree
0x180008c48  mov     qword ptr [r14], 0
0x180008c4f  jmp     loc_180008B1A
```
