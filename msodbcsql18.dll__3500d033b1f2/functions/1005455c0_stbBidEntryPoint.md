# stbBidEntryPoint

- ea: `0x1005455c0`
- end: `0x100545719`
- name: `stbBidEntryPoint`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1005455c0`
- `0x100546450`
- `0x10054888c`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x10054560e`
- `KERNEL32!LoadLibraryW` at `0x10054560e`
- `KERNEL32!GetProcAddress` at `0x100545643`
- `KERNEL32!GetProcAddress` at `0x100545643`
- `KERNEL32!FreeLibrary` at `0x100545672`
- `KERNEL32!FreeLibrary` at `0x100545672`

## string_xrefs

- `0x100545639`: `DllBidEntryPoint`

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

  if ( !a2 || (v13 = dword_1005DA928, dword_1005DA928 = 1, v13) )
  {
    bidReplaceStubs();
    return 0;
  }
  else
  {
    if ( dword_1005DA91C )
    {
      LibraryW = LoadLibraryW(lpOutputString);
      qword_1005DA930 = LibraryW;
    }
    else
    {
      LibraryW = qword_1005DA930;
    }
    if ( LibraryW )
    {
      bidpEntryPoint = GetProcAddress(LibraryW, "DllBidEntryPoint");
      v16 = (__int64 (__fastcall *)(int, int, int, int, __int64))bidpEntryPoint;
      if ( !bidpEntryPoint )
      {
        v16 = ImplBidEntryPoint;
        bidpEntryPoint = ImplBidEntryPoint;
        if ( qword_1005DA930 )
        {
          FreeLibrary(qword_1005DA930);
          qword_1005DA930 = 0;
          v16 = (__int64 (__fastcall *)(int, int, int, int, __int64))bidpEntryPoint;
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
      bidpEntryPoint = ImplBidEntryPoint;
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
0x1005455c0  mov     [rsp+arg_0], rbx
0x1005455c5  mov     [rsp+arg_8], rbp
0x1005455ca  mov     [rsp+arg_10], rsi
0x1005455cf  push    rdi
0x1005455d0  sub     rsp, 50h
0x1005455d4  mov     esi, r9d
0x1005455d7  mov     rbp, r8
0x1005455da  mov     edi, edx
0x1005455dc  mov     rbx, rcx
0x1005455df  test    edx, edx
0x1005455e1  jz      loc_1005456FD
0x1005455e7  mov     eax, cs:dword_1005DA928
0x1005455ed  mov     cs:dword_1005DA928, 1
0x1005455f7  test    eax, eax
0x1005455f9  jnz     loc_1005456FD
0x1005455ff  cmp     cs:dword_1005DA91C, eax
0x100545605  jz      short loc_10054561D
0x100545607  mov     rcx, cs:lpOutputString; lpLibFileName
0x10054560e  call    cs:__imp_LoadLibraryW
0x100545614  mov     cs:qword_1005DA930, rax
0x10054561b  jmp     short loc_100545624
0x10054561d  mov     rax, cs:qword_1005DA930
0x100545624  test    rax, rax
0x100545627  jnz     short loc_100545639
0x100545629  lea     r10, ImplBidEntryPoint
0x100545630  mov     cs:_bidpEntryPoint, r10
0x100545637  jmp     short loc_100545687
0x100545639  lea     rdx, aDllbidentrypoi; "DllBidEntryPoint"
0x100545640  mov     rcx, rax; hModule
0x100545643  call    cs:__imp_GetProcAddress
0x100545649  mov     cs:_bidpEntryPoint, rax
0x100545650  mov     r10, rax
0x100545653  test    rax, rax
0x100545656  jnz     short loc_100545687
0x100545658  mov     rcx, cs:qword_1005DA930; hLibModule
0x10054565f  lea     r10, ImplBidEntryPoint
0x100545666  mov     cs:_bidpEntryPoint, r10
0x10054566d  test    rcx, rcx
0x100545670  jz      short loc_100545687
0x100545672  call    cs:__imp_FreeLibrary
0x100545678  and     cs:qword_1005DA930, 0
0x100545680  mov     r10, cs:_bidpEntryPoint
0x100545687  mov     rax, [rsp+58h+arg_40]
0x10054568f  mov     r9d, esi
0x100545692  mov     [rsp+58h+var_18], rax
0x100545697  mov     r8, rbp
0x10054569a  mov     rax, [rsp+58h+arg_38]
0x1005456a2  mov     edx, edi
0x1005456a4  mov     [rsp+58h+var_20], rax
0x1005456a9  mov     rcx, rbx
0x1005456ac  mov     rax, [rsp+58h+arg_30]
0x1005456b4  mov     [rsp+58h+var_28], rax
0x1005456b9  mov     rax, [rsp+58h+arg_28]
0x1005456c1  mov     [rsp+58h+var_30], rax
0x1005456c6  mov     rax, [rsp+58h+arg_20]
0x1005456ce  mov     [rsp+58h+var_38], rax
0x1005456d3  mov     rax, r10
0x1005456d6  call    cs:__guard_dispatch_icall_fptr
0x1005456dc  mov     edi, eax
0x1005456de  test    eax, eax
0x1005456e0  jz      short loc_1005456F5
0x1005456e2  call    _bidReplaceStubs
0x1005456e7  lea     rcx, BidUnload; Func
0x1005456ee  call    _onexit
0x1005456f3  jmp     short loc_1005456F9
0x1005456f5  or      qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1005456f9  mov     eax, edi
0x1005456fb  jmp     short loc_100545704
0x1005456fd  call    _bidReplaceStubs
0x100545702  xor     eax, eax
0x100545704  mov     rbx, [rsp+58h+arg_0]
0x100545709  mov     rbp, [rsp+58h+arg_8]
0x10054570e  mov     rsi, [rsp+58h+arg_10]
0x100545713  add     rsp, 50h
0x100545717  pop     rdi
0x100545718  retn
```
