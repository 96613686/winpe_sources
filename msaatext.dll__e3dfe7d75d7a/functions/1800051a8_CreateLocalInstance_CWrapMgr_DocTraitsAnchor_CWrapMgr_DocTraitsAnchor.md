# CreateLocalInstance<CWrapMgr<DocTraitsAnchor>>(CWrapMgr<DocTraitsAnchor> * *)

- ea: `0x1800051a8`
- end: `0x180005276`
- name: `??$CreateLocalInstance@V?$CWrapMgr@VDocTraitsAnchor@@@@@@YAJPEAPEAV?$CWrapMgr@VDocTraitsAnchor@@@@@Z`
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
- `0x1800051a8`
- `0x180014010`

## string_xrefs

- `0x180005242`: `CreateLocalInstance`

## pseudocode

```c
__int64 __fastcall CreateLocalInstance<CWrapMgr<DocTraitsAnchor>>(_QWORD *a1)
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
    *(_QWORD *)v2 = &ATL::CComObject<CWrapMgr<DocTraitsAnchor>>::`vftable';
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
0x1800051a8  mov     [rsp+arg_0], rbx
0x1800051ad  push    rdi
0x1800051ae  sub     rsp, 40h
0x1800051b2  mov     rdi, rcx
0x1800051b5  mov     ecx, 50h ; 'P'; Size
0x1800051ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800051bf  xor     ecx, ecx
0x1800051c1  mov     [rsp+48h+arg_8], rax
0x1800051c6  mov     rbx, rax
0x1800051c9  lea     r9d, [rcx+1]
0x1800051cd  test    rax, rax
0x1800051d0  jz      short loc_18000523D
0x1800051d2  mov     [rax+8], ecx
0x1800051d5  mov     [rax+10h], rcx
0x1800051d9  mov     [rax+18h], rcx
0x1800051dd  mov     [rax+20h], rcx
0x1800051e1  mov     [rax+28h], rcx
0x1800051e5  mov     [rax+30h], rcx
0x1800051e9  mov     [rax+38h], rcx
0x1800051ed  mov     [rax+40h], rcx
0x1800051f1  mov     [rax+48h], ecx
0x1800051f4  lea     rax, ??_7?$CComObject@V?$CWrapMgr@VDocTraitsAnchor@@@@@ATL@@6B@; const ATL::CComObject<CWrapMgr<DocTraitsAnchor>>::`vftable'
0x1800051fb  mov     [rbx], rax
0x1800051fe  lock add cs:dword_180024B28, r9d
0x180005206  test    rbx, rbx
0x180005209  jz      short loc_18000523D
0x18000520b  mov     ecx, [rbx+8]
0x18000520e  cmp     ecx, 7FFFFFFFh
0x180005214  jz      short loc_180005227
0x180005216  lea     eax, [rcx+1]
0x180005219  mov     [rbx+8], eax
0x18000521c  cmp     ecx, 7FFFFFFEh
0x180005222  jz      short loc_180005227
0x180005224  mov     [rbx+8], ecx
0x180005227  mov     rax, [rbx]
0x18000522a  mov     rcx, rbx
0x18000522d  mov     rax, [rax+8]
0x180005231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005236  xor     eax, eax
0x180005238  mov     [rdi], rbx
0x18000523b  jmp     short loc_18000526B
0x18000523d  mov     edx, 71h ; 'q'; Value
0x180005242  lea     rcx, aCreatelocalins; "CreateLocalInstance"
0x180005249  mov     [rsp+48h+var_18], rcx; __int64
0x18000524e  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005255  mov     [rsp+48h+var_20], 8007000Eh; int
0x18000525d  lea     r8d, [rdx-6Eh]
0x180005261  call    InternalTrace
0x180005266  mov     eax, 8007000Eh
0x18000526b  mov     rbx, [rsp+48h+arg_0]
0x180005270  add     rsp, 40h
0x180005274  pop     rdi
0x180005275  retn
```
