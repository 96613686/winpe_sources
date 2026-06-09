# TdhpGetEventMapInfoManifest(_GUID *,wchar_t *,ulong,_EVENT_MAP_INFO * *,ulong *)

- ea: `0x1800087c8`
- end: `0x180008967`
- name: `?TdhpGetEventMapInfoManifest@@YAKPEAU_GUID@@PEA_WKPEAPEAU_EVENT_MAP_INFO@@PEAK@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct _GUID *, wchar_t *, int, struct _EVENT_MAP_INFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800074e8`

## callees

- `0x180007e78`
- `0x18000872c`
- `0x1800087c8`
- `0x180009570`
- `0x180009a34`
- `0x180017c40`
- `0x18004c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TdhpGetEventMapInfoManifest(
        struct _GUID *a1,
        wchar_t *a2,
        int a3,
        struct _EVENT_MAP_INFO **a4,
        unsigned int *a5)
{
  unsigned int Map; // ebx
  __int64 v10; // rax
  _WORD *v11; // rcx
  void **v13; // [rsp+40h] [rbp-31h] BYREF
  struct PUBLISHER_LOOKUP_ENTRY near **v14; // [rsp+48h] [rbp-29h] BYREF
  int v15; // [rsp+50h] [rbp-21h]
  char v16; // [rsp+54h] [rbp-1Dh]
  void ***v17; // [rsp+58h] [rbp-19h]
  const void *v18; // [rsp+60h] [rbp-11h] BYREF
  void **v19; // [rsp+68h] [rbp-9h] BYREF
  __int128 v20; // [rsp+70h] [rbp-1h]
  __int128 v21; // [rsp+80h] [rbp+Fh]

  v20 = 0;
  v21 = 0;
  v19 = &PublisherManifestTdhConfig::`vftable';
  v13 = &ModuleLoaderImpl::`vftable';
  v17 = &v13;
  v14 = &g_EnvironmentTable;
  v15 = 2;
  v16 = 0;
  v18 = 0;
  if ( PublisherManifestTdhConfig::ReadConfig((PublisherManifestTdhConfig *)&v19, a1) == 2 )
  {
    if ( v16 )
      ((void (__fastcall *)(void ***, const void **))(*v17)[1])(v17, &v18);
    Map = 1168;
  }
  else if ( *((_QWORD *)&v20 + 1) )
  {
    v10 = 260;
    v11 = (_WORD *)*((_QWORD *)&v20 + 1);
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
      {
        Map = 87;
        if ( v16 )
          ((void (__fastcall *)(void ***, const void **))(*v17)[1])(v17, &v18);
        goto LABEL_20;
      }
    }
    if ( *((_QWORD *)&v21 + 1)
      && (Map = PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(&v14, *((_QWORD *)&v21 + 1))) != 0 )
    {
      if ( v16 )
        ((void (__fastcall *)(void ***, const void **))(*v17)[1])(v17, &v18);
    }
    else
    {
      Map = PmresGetMap((__int64)a1, *((__int64 *)&v20 + 1), v18, a2, a3, (__int64 *)a4, a5);
      if ( v16 )
        ((void (__fastcall *)(void ***, const void **))(*v17)[1])(v17, &v18);
    }
  }
  else
  {
    PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(&v14);
    Map = 4316;
  }
LABEL_20:
  v19 = &PublisherManifestConfig::`vftable';
  PublisherManifestConfig::Free((PublisherManifestConfig *)&v19);
  return Map;
}

```

## disassembly

```asm
0x1800087c8  push    rbp
0x1800087ca  push    rbx
0x1800087cb  push    rsi
0x1800087cc  push    r12
0x1800087ce  push    r13
0x1800087d0  push    r14
0x1800087d2  push    r15
0x1800087d4  lea     rbp, [rsp-1Fh]
0x1800087d9  sub     rsp, 90h
0x1800087e0  mov     r14, r9
0x1800087e3  mov     r15d, r8d
0x1800087e6  mov     r12, rdx
0x1800087e9  mov     rsi, rcx
0x1800087ec  xorps   xmm0, xmm0
0x1800087ef  movdqu  [rbp+4Fh+var_50], xmm0
0x1800087f4  xorps   xmm1, xmm1
0x1800087f7  movdqu  [rbp+4Fh+var_40], xmm1
0x1800087fc  lea     rax, ??_7PublisherManifestTdhConfig@@6B@; const PublisherManifestTdhConfig::`vftable'
0x180008803  mov     [rbp+4Fh+var_58], rax
0x180008807  lea     rax, ??_7ModuleLoaderImpl@@6B@; const ModuleLoaderImpl::`vftable'
0x18000880e  mov     [rbp+4Fh+var_80], rax
0x180008812  lea     rax, [rbp+4Fh+var_80]
0x180008816  mov     [rbp+4Fh+var_68], rax
0x18000881a  lea     rax, ?g_EnvironmentTable@@3PAUPUBLISHER_LOOKUP_ENTRY@@A; PUBLISHER_LOOKUP_ENTRY near * g_EnvironmentTable
0x180008821  mov     [rbp+4Fh+var_78], rax
0x180008825  mov     [rbp+4Fh+var_70], 2
0x18000882c  xor     r13d, r13d
0x18000882f  mov     [rbp+4Fh+var_6C], r13b
0x180008833  mov     [rbp+4Fh+var_60], r13
0x180008837  mov     rdx, rcx; struct _GUID *
0x18000883a  lea     rcx, [rbp+4Fh+var_58]; this
0x18000883e  call    ?ReadConfig@PublisherManifestTdhConfig@@UEAAKAEBU_GUID@@@Z; PublisherManifestTdhConfig::ReadConfig(_GUID const &)
0x180008843  cmp     eax, 2
0x180008846  jnz     short loc_18000886D
0x180008848  cmp     [rbp+4Fh+var_6C], r13b
0x18000884c  jz      short loc_180008863
0x18000884e  mov     rcx, [rbp+4Fh+var_68]
0x180008852  mov     rax, [rcx]
0x180008855  lea     rdx, [rbp+4Fh+var_60]
0x180008859  mov     rax, [rax+8]
0x18000885d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008862  nop
0x180008863  mov     ebx, 490h
0x180008868  jmp     loc_18000893E
0x18000886d  cmp     qword ptr [rbp+4Fh+var_50+8], r13
0x180008871  jnz     short loc_180008886
0x180008873  lea     rcx, [rbp+4Fh+var_78]
0x180008877  call    ??1?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAA@XZ; PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(void)
0x18000887c  mov     ebx, 10DCh
0x180008881  jmp     loc_18000893E
0x180008886  mov     eax, 104h
0x18000888b  mov     rcx, qword ptr [rbp+4Fh+var_50+8]
0x18000888f  cmp     [rcx], r13w
0x180008893  jz      short loc_1800088C6
0x180008895  add     rcx, 2
0x180008899  sub     rax, 1
0x18000889d  jnz     short loc_18000888F
0x18000889f  neg     rax
0x1800088a2  sbb     ebx, ebx
0x1800088a4  not     ebx
0x1800088a6  and     ebx, 57h
0x1800088a9  cmp     [rbp+4Fh+var_6C], r13b
0x1800088ad  jz      short loc_1800088C4
0x1800088af  mov     rcx, [rbp+4Fh+var_68]
0x1800088b3  mov     rax, [rcx]
0x1800088b6  lea     rdx, [rbp+4Fh+var_60]
0x1800088ba  mov     rax, [rax+8]
0x1800088be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c3  nop
0x1800088c4  jmp     short loc_18000893E
0x1800088c6  mov     rdx, qword ptr [rbp+4Fh+var_40+8]
0x1800088ca  test    rdx, rdx
0x1800088cd  jz      short loc_1800088FB
0x1800088cf  lea     rcx, [rbp+4Fh+var_78]
0x1800088d3  call    ?LookupNLoad@?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(wchar_t const *)
0x1800088d8  mov     ebx, eax
0x1800088da  test    eax, eax
0x1800088dc  jz      short loc_1800088FB
0x1800088de  cmp     [rbp+4Fh+var_6C], r13b
0x1800088e2  jz      short loc_1800088F9
0x1800088e4  mov     rcx, [rbp+4Fh+var_68]
0x1800088e8  mov     rdx, [rcx]
0x1800088eb  mov     rax, [rdx+8]
0x1800088ef  lea     rdx, [rbp+4Fh+var_60]
0x1800088f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f8  nop
0x1800088f9  jmp     short loc_18000893E
0x1800088fb  mov     rax, [rbp+4Fh+arg_20]
0x1800088ff  mov     [rsp+0C0h+var_90], rax
0x180008904  mov     [rsp+0C0h+var_98], r14
0x180008909  mov     [rsp+0C0h+var_A0], r15
0x18000890e  mov     r9, r12
0x180008911  mov     r8, [rbp+4Fh+var_60]
0x180008915  mov     rdx, qword ptr [rbp+4Fh+var_50+8]
0x180008919  mov     rcx, rsi
0x18000891c  call    PmresGetMap
0x180008921  mov     ebx, eax
0x180008923  cmp     [rbp+4Fh+var_6C], r13b
0x180008927  jz      short loc_18000893E
0x180008929  mov     rcx, [rbp+4Fh+var_68]
0x18000892d  mov     rax, [rcx]
0x180008930  lea     rdx, [rbp+4Fh+var_60]
0x180008934  mov     rax, [rax+8]
0x180008938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000893d  nop
0x18000893e  lea     rax, ??_7PublisherManifestConfig@@6B@; const PublisherManifestConfig::`vftable'
0x180008945  mov     [rbp+4Fh+var_58], rax
0x180008949  lea     rcx, [rbp+4Fh+var_58]; this
0x18000894d  call    ?Free@PublisherManifestConfig@@AEAAXXZ; PublisherManifestConfig::Free(void)
0x180008952  mov     eax, ebx
0x180008954  add     rsp, 90h
0x18000895b  pop     r15
0x18000895d  pop     r14
0x18000895f  pop     r13
0x180008961  pop     r12
0x180008963  pop     rsi
0x180008964  pop     rbx
0x180008965  pop     rbp
0x180008966  retn
```
