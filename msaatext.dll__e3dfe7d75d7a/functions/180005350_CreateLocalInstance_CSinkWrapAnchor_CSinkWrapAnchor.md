# CreateLocalInstance<CSinkWrapAnchor>(CSinkWrapAnchor * *)

- ea: `0x180005350`
- end: `0x18000541d`
- name: `??$CreateLocalInstance@VCSinkWrapAnchor@@@@YAJPEAPEAVCSinkWrapAnchor@@@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074c8`

## callees

- `0x180001370`
- `0x1800026d0`
- `0x180005350`
- `0x180014010`

## string_xrefs

- `0x1800053e9`: `CreateLocalInstance`

## pseudocode

```c
__int64 __fastcall CreateLocalInstance<CSinkWrapAnchor>(_QWORD *a1)
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
    *(_QWORD *)v2 = &ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorSink'};
    *((_QWORD *)v2 + 1) = &ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorServices'};
    *((_QWORD *)v2 + 2) = &ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `IServiceProvider'};
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
0x180005350  mov     [rsp+arg_0], rbx
0x180005355  push    rdi
0x180005356  sub     rsp, 40h
0x18000535a  mov     rdi, rcx
0x18000535d  mov     ecx, 30h ; '0'; Size
0x180005362  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005367  xor     ecx, ecx
0x180005369  mov     [rsp+48h+arg_8], rax
0x18000536e  mov     rbx, rax
0x180005371  lea     r9d, [rcx+1]
0x180005375  test    rax, rax
0x180005378  jz      short loc_1800053E4
0x18000537a  mov     [rax+18h], ecx
0x18000537d  mov     [rax+20h], rcx
0x180005381  mov     [rax+28h], rcx
0x180005385  lea     rax, ??_7?$CComObject@VCSinkWrapAnchor@@@ATL@@6BITextStoreAnchorSink@@@; const ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorSink'}
0x18000538c  mov     [rbx], rax
0x18000538f  lea     rax, ??_7?$CComObject@VCSinkWrapAnchor@@@ATL@@6BITextStoreAnchorServices@@@; const ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorServices'}
0x180005396  mov     [rbx+8], rax
0x18000539a  lea     rax, ??_7?$CComObject@VCSinkWrapAnchor@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `IServiceProvider'}
0x1800053a1  mov     [rbx+10h], rax
0x1800053a5  lock add cs:dword_180024B28, r9d
0x1800053ad  test    rbx, rbx
0x1800053b0  jz      short loc_1800053E4
0x1800053b2  mov     ecx, [rbx+18h]
0x1800053b5  cmp     ecx, 7FFFFFFFh
0x1800053bb  jz      short loc_1800053CE
0x1800053bd  lea     eax, [rcx+1]
0x1800053c0  mov     [rbx+18h], eax
0x1800053c3  cmp     ecx, 7FFFFFFEh
0x1800053c9  jz      short loc_1800053CE
0x1800053cb  mov     [rbx+18h], ecx
0x1800053ce  mov     rax, [rbx]
0x1800053d1  mov     rcx, rbx
0x1800053d4  mov     rax, [rax+8]
0x1800053d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053dd  xor     eax, eax
0x1800053df  mov     [rdi], rbx
0x1800053e2  jmp     short loc_180005412
0x1800053e4  mov     edx, 71h ; 'q'; Value
0x1800053e9  lea     rcx, aCreatelocalins; "CreateLocalInstance"
0x1800053f0  mov     [rsp+48h+var_18], rcx; __int64
0x1800053f5  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x1800053fc  mov     [rsp+48h+var_20], 8007000Eh; int
0x180005404  lea     r8d, [rdx-6Eh]
0x180005408  call    InternalTrace
0x18000540d  mov     eax, 8007000Eh
0x180005412  mov     rbx, [rsp+48h+arg_0]
0x180005417  add     rsp, 40h
0x18000541b  pop     rdi
0x18000541c  retn
```
