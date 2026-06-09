# WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)

- ea: `0x180003a5c`
- end: `0x180003a9b`
- name: `?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001580`
- `0x180003aa4`
- `0x180003f24`

## callees

- `0x180003a5c`
- `0x180005010`

## pseudocode

```c
_BOOL8 __fastcall WWWServerTraceProvider::CheckTracingEnabled(int (__fastcall ***a1)(_QWORD, GUID **))
{
  int (__fastcall **v1)(_QWORD, GUID **); // rax
  GUID *v3; // [rsp+20h] [rbp-28h] BYREF
  __int128 v4; // [rsp+28h] [rbp-20h]

  v3 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v1 = *a1;
  v4 = 0;
  return (*v1)(a1, &v3) >= 0 && DWORD2(v4) != 0;
}

```

## disassembly

```asm
0x180003a5c  sub     rsp, 48h
0x180003a60  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003a67  xorps   xmm0, xmm0
0x180003a6a  mov     [rsp+48h+var_28], rax
0x180003a6f  lea     rdx, [rsp+48h+var_28]
0x180003a74  mov     rax, [rcx]
0x180003a77  movdqu  [rsp+48h+var_20], xmm0
0x180003a7d  mov     rax, [rax]
0x180003a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a85  test    eax, eax
0x180003a87  js      short loc_180003A94
0x180003a89  xor     eax, eax
0x180003a8b  cmp     dword ptr [rsp+48h+var_20+8], eax
0x180003a8f  setnz   al
0x180003a92  jmp     short loc_180003A96
0x180003a94  xor     eax, eax
0x180003a96  add     rsp, 48h
0x180003a9a  retn
```
