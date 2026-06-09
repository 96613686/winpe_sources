# CreateLocalInstance<CSinkWrapACP>(CSinkWrapACP * *)

- ea: `0x18000527c`
- end: `0x180005349`
- name: `??$CreateLocalInstance@VCSinkWrapACP@@@@YAJPEAPEAVCSinkWrapACP@@@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800071ac`

## callees

- `0x180001370`
- `0x1800026d0`
- `0x18000527c`
- `0x180014010`

## string_xrefs

- `0x180005315`: `CreateLocalInstance`

## pseudocode

```c
__int64 __fastcall CreateLocalInstance<CSinkWrapACP>(_QWORD *a1)
{
  _DWORD *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  _DWORD *v5; // rbx
  int v6; // ecx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-28h]

  v2 = operator new(0x30u);
  v5 = v2;
  if ( v2 )
  {
    v2[6] = 0;
    *((_QWORD *)v2 + 4) = 0;
    *((_QWORD *)v2 + 5) = 0;
    *(_QWORD *)v2 = &ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPSink'};
    *((_QWORD *)v2 + 1) = &ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPServices'};
    *((_QWORD *)v2 + 2) = &ATL::CComObject<CSinkWrapACP>::`vftable'{for `IServiceProvider'};
    _InterlockedAdd(&dword_180024B28, 1u);
    v6 = v2[6];
    if ( v6 != 0x7FFFFFFF )
    {
      v2[6] = v6 + 1;
      if ( v6 != 2147483646 )
        v2[6] = v6;
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
0x18000527c  mov     [rsp+arg_0], rbx
0x180005281  push    rdi
0x180005282  sub     rsp, 40h
0x180005286  mov     rdi, rcx
0x180005289  mov     ecx, 30h ; '0'; Size
0x18000528e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005293  xor     ecx, ecx
0x180005295  mov     [rsp+48h+arg_8], rax
0x18000529a  mov     rbx, rax
0x18000529d  lea     r9d, [rcx+1]
0x1800052a1  test    rax, rax
0x1800052a4  jz      short loc_180005310
0x1800052a6  mov     [rax+18h], ecx
0x1800052a9  mov     [rax+20h], rcx
0x1800052ad  mov     [rax+28h], rcx
0x1800052b1  lea     rax, ??_7?$CComObject@VCSinkWrapACP@@@ATL@@6BITextStoreACPSink@@@; const ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPSink'}
0x1800052b8  mov     [rbx], rax
0x1800052bb  lea     rax, ??_7?$CComObject@VCSinkWrapACP@@@ATL@@6BITextStoreACPServices@@@; const ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPServices'}
0x1800052c2  mov     [rbx+8], rax
0x1800052c6  lea     rax, ??_7?$CComObject@VCSinkWrapACP@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CSinkWrapACP>::`vftable'{for `IServiceProvider'}
0x1800052cd  mov     [rbx+10h], rax
0x1800052d1  lock add cs:dword_180024B28, r9d
0x1800052d9  test    rbx, rbx
0x1800052dc  jz      short loc_180005310
0x1800052de  mov     ecx, [rbx+18h]
0x1800052e1  cmp     ecx, 7FFFFFFFh
0x1800052e7  jz      short loc_1800052FA
0x1800052e9  lea     eax, [rcx+1]
0x1800052ec  mov     [rbx+18h], eax
0x1800052ef  cmp     ecx, 7FFFFFFEh
0x1800052f5  jz      short loc_1800052FA
0x1800052f7  mov     [rbx+18h], ecx
0x1800052fa  mov     rax, [rbx]
0x1800052fd  mov     rcx, rbx
0x180005300  mov     rax, [rax+8]
0x180005304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005309  xor     eax, eax
0x18000530b  mov     [rdi], rbx
0x18000530e  jmp     short loc_18000533E
0x180005310  mov     edx, 71h ; 'q'; Value
0x180005315  lea     rcx, aCreatelocalins; "CreateLocalInstance"
0x18000531c  mov     [rsp+48h+var_18], rcx; __int64
0x180005321  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005328  mov     [rsp+48h+var_20], 8007000Eh; int
0x180005330  lea     r8d, [rdx-6Eh]
0x180005334  call    InternalTrace
0x180005339  mov     eax, 8007000Eh
0x18000533e  mov     rbx, [rsp+48h+arg_0]
0x180005343  add     rsp, 40h
0x180005347  pop     rdi
0x180005348  retn
```
