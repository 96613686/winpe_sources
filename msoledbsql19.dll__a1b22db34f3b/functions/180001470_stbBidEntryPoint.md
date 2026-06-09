# stbBidEntryPoint

- ea: `0x180001470`
- end: `0x1800015d1`
- name: `stbBidEntryPoint`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001470`
- `0x180002740`
- `0x180003ba0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180001522`
- `KERNEL32!FreeLibrary` at `0x180001522`
- `KERNEL32!LoadLibraryW` at `0x1800014be`
- `KERNEL32!LoadLibraryW` at `0x1800014be`
- `KERNEL32!GetProcAddress` at `0x1800014f3`
- `KERNEL32!GetProcAddress` at `0x1800014f3`

## string_xrefs

- `0x1800014e9`: `DllBidEntryPoint`

## pseudocode

```c
__int64 __fastcall stbBidEntryPoint(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int v13; // eax
  HMODULE LibraryW; // rax
  unsigned int v15; // eax
  __int64 (__fastcall *v16)(int, int, int, int, __int64); // r10
  unsigned int v17; // edi

  if ( !a2 || (v13 = dword_18024E830, dword_18024E830 = 1, v13) )
  {
    bidReplaceStubs();
    return 0;
  }
  else
  {
    if ( dword_18024E82C )
    {
      LibraryW = LoadLibraryW(lpOutputString);
      hLibModule = LibraryW;
    }
    else
    {
      LibraryW = hLibModule;
    }
    if ( LibraryW )
    {
      bidpEntryPoint = (__int64 (__fastcall *)(int, int, int, int, __int64, __int64, __int64, __int64, __int64))GetProcAddress(LibraryW, "DllBidEntryPoint");
      v16 = (__int64 (__fastcall *)(int, int, int, int, __int64))bidpEntryPoint;
      if ( !bidpEntryPoint )
      {
        v16 = ImplBidEntryPoint;
        bidpEntryPoint = (__int64 (__fastcall *)(int, int, int, int, __int64, __int64, __int64, __int64, __int64))ImplBidEntryPoint;
        if ( hLibModule )
        {
          FreeLibrary(hLibModule);
          v16 = (__int64 (__fastcall *)(int, int, int, int, __int64))bidpEntryPoint;
          hLibModule = 0;
        }
      }
      v15 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64))v16)(
              a1,
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              a9);
    }
    else
    {
      bidpEntryPoint = (__int64 (__fastcall *)(int, int, int, int, __int64, __int64, __int64, __int64, __int64))ImplBidEntryPoint;
      v15 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64))ImplBidEntryPoint)(
              a1,
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              a9);
    }
    v17 = v15;
    if ( v15 )
    {
      bidReplaceStubs();
      onexit(BidUnload);
    }
    else
    {
      *a1 = -1;
    }
    return v17;
  }
}

```

## disassembly

```asm
0x180001470  mov     [rsp+arg_0], rbx
0x180001475  mov     [rsp+arg_8], rbp
0x18000147a  mov     [rsp+arg_10], rsi
0x18000147f  push    rdi
0x180001480  sub     rsp, 50h
0x180001484  mov     esi, r9d
0x180001487  mov     rbp, r8
0x18000148a  mov     edi, edx
0x18000148c  mov     rbx, rcx
0x18000148f  test    edx, edx
0x180001491  jz      loc_1800015B5
0x180001497  mov     eax, cs:dword_18024E830
0x18000149d  mov     cs:dword_18024E830, 1
0x1800014a7  test    eax, eax
0x1800014a9  jnz     loc_1800015B5
0x1800014af  cmp     cs:dword_18024E82C, eax
0x1800014b5  jz      short loc_1800014CD
0x1800014b7  mov     rcx, cs:lpOutputString; lpLibFileName
0x1800014be  call    cs:__imp_LoadLibraryW
0x1800014c4  mov     cs:hLibModule, rax
0x1800014cb  jmp     short loc_1800014D4
0x1800014cd  mov     rax, cs:hLibModule
0x1800014d4  test    rax, rax
0x1800014d7  jnz     short loc_1800014E9
0x1800014d9  lea     r10, ImplBidEntryPoint
0x1800014e0  mov     cs:_bidpEntryPoint, r10
0x1800014e7  jmp     short loc_18000153A
0x1800014e9  lea     rdx, ProcName; "DllBidEntryPoint"
0x1800014f0  mov     rcx, rax; hModule
0x1800014f3  call    cs:__imp_GetProcAddress
0x1800014f9  mov     cs:_bidpEntryPoint, rax
0x180001500  mov     r10, rax
0x180001503  test    rax, rax
0x180001506  jnz     short loc_18000153A
0x180001508  mov     rcx, cs:hLibModule; hLibModule
0x18000150f  lea     r10, ImplBidEntryPoint
0x180001516  mov     cs:_bidpEntryPoint, r10
0x18000151d  test    rcx, rcx
0x180001520  jz      short loc_18000153A
0x180001522  call    cs:__imp_FreeLibrary
0x180001528  mov     r10, cs:_bidpEntryPoint
0x18000152f  mov     cs:hLibModule, 0
0x18000153a  mov     rax, [rsp+58h+arg_40]
0x180001542  mov     r9d, esi
0x180001545  mov     [rsp+58h+var_18], rax
0x18000154a  mov     r8, rbp
0x18000154d  mov     rax, [rsp+58h+arg_38]
0x180001555  mov     edx, edi
0x180001557  mov     [rsp+58h+var_20], rax
0x18000155c  mov     rcx, rbx
0x18000155f  mov     rax, [rsp+58h+arg_30]
0x180001567  mov     [rsp+58h+var_28], rax
0x18000156c  mov     rax, [rsp+58h+arg_28]
0x180001574  mov     [rsp+58h+var_30], rax
0x180001579  mov     rax, [rsp+58h+arg_20]
0x180001581  mov     [rsp+58h+var_38], rax
0x180001586  mov     rax, r10
0x180001589  call    cs:__guard_dispatch_icall_fptr
0x18000158f  mov     edi, eax
0x180001591  test    eax, eax
0x180001593  jz      short loc_1800015AA
0x180001595  call    _bidReplaceStubs
0x18000159a  lea     rcx, BidUnload; Func
0x1800015a1  call    _onexit
0x1800015a6  mov     eax, edi
0x1800015a8  jmp     short loc_1800015BC
0x1800015aa  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800015b1  mov     eax, edi
0x1800015b3  jmp     short loc_1800015BC
0x1800015b5  call    _bidReplaceStubs
0x1800015ba  xor     eax, eax
0x1800015bc  mov     rbx, [rsp+58h+arg_0]
0x1800015c1  mov     rbp, [rsp+58h+arg_8]
0x1800015c6  mov     rsi, [rsp+58h+arg_10]
0x1800015cb  add     rsp, 50h
0x1800015cf  pop     rdi
0x1800015d0  retn
```
