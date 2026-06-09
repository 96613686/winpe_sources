# ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAt(int)

- ea: `0x180031f18`
- end: `0x180031f93`
- name: `?RemoveAt@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHH@Z`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800307d4`
- `0x180032044`

## callees

- `0x1800048c0`
- `0x18000be84`
- `0x180031f18`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180031f6a`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180031f6a`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAt(
        __int64 a1,
        int a2)
{
  __int64 v2; // rdi
  int v4; // edx
  errno_t v5; // eax

  v2 = a2;
  if ( a2 < 0 || a2 >= *(_DWORD *)(a1 + 8) )
    return 0;
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(*(_QWORD *)a1 + 8LL * a2);
  v4 = *(_DWORD *)(a1 + 8);
  if ( (_DWORD)v2 != v4 - 1 )
  {
    v5 = memmove_s(
           (void *const)(*(_QWORD *)a1 + 8 * v2),
           8LL * (v4 - (int)v2),
           (const void *const)(*(_QWORD *)a1 + 8 * v2 + 8),
           8LL * (v4 - (int)v2 - 1));
    ATL::AtlCrtErrorCheck(v5);
  }
  --*(_DWORD *)(a1 + 8);
  return 1;
}

```

## disassembly

```asm
0x180031f18  mov     [rsp+arg_0], rbx
0x180031f1d  mov     [rsp+arg_8], rsi
0x180031f22  push    rdi
0x180031f23  sub     rsp, 20h
0x180031f27  movsxd  rdi, edx
0x180031f2a  mov     rbx, rcx
0x180031f2d  test    edx, edx
0x180031f2f  js      short loc_180031F81
0x180031f31  cmp     edi, [rcx+8]
0x180031f34  jge     short loc_180031F81
0x180031f36  mov     rax, [rcx]
0x180031f39  lea     rcx, [rax+rdi*8]
0x180031f3d  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180031f42  mov     edx, [rbx+8]
0x180031f45  lea     eax, [rdx-1]
0x180031f48  cmp     edi, eax
0x180031f4a  jz      short loc_180031F77
0x180031f4c  mov     rax, [rbx]
0x180031f4f  sub     edx, edi
0x180031f51  lea     rcx, [rax+rdi*8]; Destination
0x180031f55  lea     eax, [rdx-1]
0x180031f58  movsxd  rdx, edx
0x180031f5b  movsxd  r9, eax
0x180031f5e  lea     r8, [rcx+8]; Source
0x180031f62  shl     r9, 3; SourceSize
0x180031f66  shl     rdx, 3; DestinationSize
0x180031f6a  call    cs:__imp_memmove_s
0x180031f70  mov     ecx, eax; int
0x180031f72  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180031f77  dec     dword ptr [rbx+8]
0x180031f7a  mov     eax, 1
0x180031f7f  jmp     short loc_180031F83
0x180031f81  xor     eax, eax
0x180031f83  mov     rbx, [rsp+28h+arg_0]
0x180031f88  mov     rsi, [rsp+28h+arg_8]
0x180031f8d  add     rsp, 20h
0x180031f91  pop     rdi
0x180031f92  retn
```
