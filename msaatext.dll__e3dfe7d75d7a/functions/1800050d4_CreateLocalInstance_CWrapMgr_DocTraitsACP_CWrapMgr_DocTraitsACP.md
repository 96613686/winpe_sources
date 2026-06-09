# CreateLocalInstance<CWrapMgr<DocTraitsACP>>(CWrapMgr<DocTraitsACP> * *)

- ea: `0x1800050d4`
- end: `0x1800051a2`
- name: `??$CreateLocalInstance@V?$CWrapMgr@VDocTraitsACP@@@@@@YAJPEAPEAV?$CWrapMgr@VDocTraitsACP@@@@@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b400`

## callees

- `0x180001370`
- `0x1800026d0`
- `0x1800050d4`
- `0x180014010`

## string_xrefs

- `0x18000516e`: `CreateLocalInstance`

## pseudocode

```c
__int64 __fastcall CreateLocalInstance<CWrapMgr<DocTraitsACP>>(_QWORD *a1)
{
  _DWORD *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  _DWORD *v5; // rbx
  int v6; // ecx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-28h]

  v2 = operator new(0x50u);
  v5 = v2;
  if ( v2 )
  {
    v2[2] = 0;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
    *((_QWORD *)v2 + 5) = 0;
    *((_QWORD *)v2 + 6) = 0;
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    v2[18] = 0;
    *(_QWORD *)v2 = &ATL::CComObject<CWrapMgr<DocTraitsACP>>::`vftable';
    _InterlockedAdd(&dword_180024B28, 1u);
    v6 = v2[2];
    if ( v6 != 0x7FFFFFFF )
    {
      v2[2] = v6 + 1;
      if ( v6 != 2147483646 )
        v2[2] = v6;
    }
    (*(void (__fastcall **)(_DWORD *, __int64, __int64, __int64))(*(_QWORD *)v2 + 8LL))(v2, v3, v4, 1);
    result = 0;
    *a1 = v5;
  }
  else
  {
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x71u,
      3u,
      1,
      v8,
      -2147024882,
      (wchar_t *)L"CreateLocalInstance");
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800050d4  mov     [rsp+arg_0], rbx
0x1800050d9  push    rdi
0x1800050da  sub     rsp, 40h
0x1800050de  mov     rdi, rcx
0x1800050e1  mov     ecx, 50h ; 'P'; Size
0x1800050e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050eb  xor     ecx, ecx
0x1800050ed  mov     [rsp+48h+arg_8], rax
0x1800050f2  mov     rbx, rax
0x1800050f5  lea     r9d, [rcx+1]
0x1800050f9  test    rax, rax
0x1800050fc  jz      short loc_180005169
0x1800050fe  mov     [rax+8], ecx
0x180005101  mov     [rax+10h], rcx
0x180005105  mov     [rax+18h], rcx
0x180005109  mov     [rax+20h], rcx
0x18000510d  mov     [rax+28h], rcx
0x180005111  mov     [rax+30h], rcx
0x180005115  mov     [rax+38h], rcx
0x180005119  mov     [rax+40h], rcx
0x18000511d  mov     [rax+48h], ecx
0x180005120  lea     rax, ??_7?$CComObject@V?$CWrapMgr@VDocTraitsACP@@@@@ATL@@6B@; const ATL::CComObject<CWrapMgr<DocTraitsACP>>::`vftable'
0x180005127  mov     [rbx], rax
0x18000512a  lock add cs:dword_180024B28, r9d
0x180005132  test    rbx, rbx
0x180005135  jz      short loc_180005169
0x180005137  mov     ecx, [rbx+8]
0x18000513a  cmp     ecx, 7FFFFFFFh
0x180005140  jz      short loc_180005153
0x180005142  lea     eax, [rcx+1]
0x180005145  mov     [rbx+8], eax
0x180005148  cmp     ecx, 7FFFFFFEh
0x18000514e  jz      short loc_180005153
0x180005150  mov     [rbx+8], ecx
0x180005153  mov     rax, [rbx]
0x180005156  mov     rcx, rbx
0x180005159  mov     rax, [rax+8]
0x18000515d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005162  xor     eax, eax
0x180005164  mov     [rdi], rbx
0x180005167  jmp     short loc_180005197
0x180005169  mov     edx, 71h ; 'q'; Value
0x18000516e  lea     rcx, aCreatelocalins; "CreateLocalInstance"
0x180005175  mov     [rsp+48h+var_18], rcx; __int64
0x18000517a  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005181  mov     [rsp+48h+var_20], 8007000Eh; int
0x180005189  lea     r8d, [rdx-6Eh]
0x18000518d  call    InternalTrace
0x180005192  mov     eax, 8007000Eh
0x180005197  mov     rbx, [rsp+48h+arg_0]
0x18000519c  add     rsp, 40h
0x1800051a0  pop     rdi
0x1800051a1  retn
```
