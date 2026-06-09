# HrFindComponents(INetCfg *,ulong,_GUID const * *,ushort const * const *,INetCfgComponent * *)

- ea: `0x1800373a0`
- end: `0x1800374f5`
- name: `?HrFindComponents@@YAJPEAUINetCfg@@KPEAPEBU_GUID@@PEBQEBGPEAPEAUINetCfgComponent@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct INetCfg *, __int64, const struct _GUID **, const unsigned __int16 *const *, struct INetCfgComponent **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800356d0`

## callees

- `0x1800373a0`
- `0x18005112a`
- `0x180053010`

## import_xrefs

- `rtutils!TracePrintfW` at `0x18003742c`
- `rtutils!TracePrintfW` at `0x18003747b`
- `rtutils!TracePrintfW` at `0x1800374e0`
- `rtutils!TracePrintfW` at `0x18003742c`
- `rtutils!TracePrintfW` at `0x18003747b`
- `rtutils!TracePrintfW` at `0x1800374e0`

## string_xrefs

- `0x180037417`: `HrFindComponents `
- `0x1800374d6`: `HrFindComponents`

## pseudocode

```c
__int64 __fastcall HrFindComponents(
        struct INetCfg *a1,
        __int64 a2,
        const struct _GUID **a3,
        const unsigned __int16 *const *a4,
        struct INetCfgComponent **a5)
{
  struct INetCfgComponent **v5; // rsi
  int v7; // ebx
  __int64 v8; // rdi
  struct INetCfgVtbl *lpVtbl; // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 i; // rdi
  struct INetCfgComponent *v13; // rcx
  const unsigned __int16 *const *v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = a4;
  v5 = a5;
  memset_0(a5, 0, 0x50u);
  v7 = 0;
  v8 = 0;
  while ( v7 >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    v10 = *((_QWORD *)&CRasBindObject::c_apguidComponentClasses.Data1 + v8);
    v15 = 0;
    v11 = ((__int64 (__fastcall *)(struct INetCfg *, __int64, GUID *, const unsigned __int16 *const **))lpVtbl->QueryNetCfgClass)(
            a1,
            v10,
            &IID_INetCfgClass,
            &v15);
    v7 = v11;
    if ( v11 < 0 )
    {
      TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrFindComponents ", (unsigned int)v11);
    }
    else
    {
      TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "HrFindComponents ", (unsigned int)v11);
      if ( v15 )
      {
        v7 = (*((__int64 (__fastcall **)(const unsigned __int16 *const *, const unsigned __int16 *const near *const, struct INetCfgComponent **))*v15
              + 3))(
               v15,
               (&CRasBindObject::c_apszComponentIds)[v8],
               &v5[v8]);
        if ( v15 )
          (*((void (__fastcall **)(const unsigned __int16 *const *))*v15 + 2))(v15);
      }
    }
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= 0xA )
    {
      if ( v7 >= 0 )
      {
        v7 = 0;
        TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "HrFindComponents", 0);
        return (unsigned int)v7;
      }
      break;
    }
  }
  for ( i = 0; i != 10; ++i )
  {
    v13 = v5[i];
    if ( v13 )
      ((void (__fastcall *)(struct INetCfgComponent *))v13->lpVtbl->Release)(v13);
    v5[i] = 0;
  }
  TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrFindComponents", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800373a0  mov     [rsp+arg_18], r9
0x1800373a5  push    rbx
0x1800373a6  push    rbp
0x1800373a7  push    rsi
0x1800373a8  push    rdi
0x1800373a9  push    r14
0x1800373ab  push    r15
0x1800373ad  sub     rsp, 38h
0x1800373b1  mov     rsi, [rsp+68h+arg_20]
0x1800373b9  xor     edx, edx; Val
0x1800373bb  mov     r14, rcx
0x1800373be  mov     rcx, rsi; void *
0x1800373c1  lea     r8d, [rdx+50h]; Size
0x1800373c5  call    memset_0
0x1800373ca  xor     ebx, ebx
0x1800373cc  lea     r15, __ImageBase
0x1800373d3  xor     edi, edi
0x1800373d5  test    ebx, ebx
0x1800373d7  js      loc_180037494
0x1800373dd  mov     rax, [r14]
0x1800373e0  lea     r9, [rsp+68h+arg_18]
0x1800373e8  mov     rdx, qword ptr rva ?c_apguidComponentClasses@CRasBindObject@@1PAPEBU_GUID@@A.Data1[r15+rdi*8]; _GUID const * near * CRasBindObject::c_apguidComponentClasses ...
0x1800373f0  lea     r8, IID_INetCfgClass
0x1800373f7  mov     rcx, r14
0x1800373fa  mov     [rsp+68h+arg_18], 0
0x180037406  mov     rax, [rax+48h]
0x18003740a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003740f  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180037415  mov     ebx, eax
0x180037417  lea     r8, aHrfindcomponen_0; "HrFindComponents "
0x18003741e  mov     r9d, eax
0x180037421  test    eax, eax
0x180037423  js      short loc_180037474
0x180037425  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x18003742c  call    cs:__imp_TracePrintfW
0x180037432  mov     rcx, [rsp+68h+arg_18]
0x18003743a  test    rcx, rcx
0x18003743d  jz      short loc_180037481
0x18003743f  mov     rax, [rcx]
0x180037442  lea     r8, [rsi+rdi*8]
0x180037446  mov     rdx, ds:rva ?c_apszComponentIds@CRasBindObject@@1QBQEBGB[r15+rdi*8]; ushort const * const near * const CRasBindObject::c_apszComponentIds ...
0x18003744e  mov     rax, [rax+18h]
0x180037452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037457  mov     rcx, [rsp+68h+arg_18]
0x18003745f  mov     ebx, eax
0x180037461  test    rcx, rcx
0x180037464  jz      short loc_180037481
0x180037466  mov     rax, [rcx]
0x180037469  mov     rax, [rax+10h]
0x18003746d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037472  jmp     short loc_180037481
0x180037474  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x18003747b  call    cs:__imp_TracePrintfW
0x180037481  inc     edi
0x180037483  cmp     edi, 0Ah
0x180037486  jb      loc_1800373D5
0x18003748c  test    ebx, ebx
0x18003748e  js      short loc_180037494
0x180037490  xor     ebx, ebx
0x180037492  jmp     short loc_1800374C0
0x180037494  xor     edi, edi
0x180037496  mov     rcx, [rsi+rdi*8]
0x18003749a  test    rcx, rcx
0x18003749d  jz      short loc_1800374AB
0x18003749f  mov     rax, [rcx]
0x1800374a2  mov     rax, [rax+10h]
0x1800374a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374ab  mov     qword ptr [rsi+rdi*8], 0
0x1800374b3  inc     rdi
0x1800374b6  cmp     rdi, 0Ah
0x1800374ba  jnz     short loc_180037496
0x1800374bc  test    ebx, ebx
0x1800374be  js      short loc_1800374C9
0x1800374c0  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x1800374c7  jmp     short loc_1800374D0
0x1800374c9  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x1800374d0  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x1800374d6  lea     r8, aHrfindcomponen; "HrFindComponents"
0x1800374dd  mov     r9d, ebx
0x1800374e0  call    cs:__imp_TracePrintfW
0x1800374e6  mov     eax, ebx
0x1800374e8  add     rsp, 38h
0x1800374ec  pop     r15
0x1800374ee  pop     r14
0x1800374f0  pop     rdi
0x1800374f1  pop     rsi
0x1800374f2  pop     rbp
0x1800374f3  pop     rbx
0x1800374f4  retn
```
