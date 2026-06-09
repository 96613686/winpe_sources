# WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)

- ea: `0x180002b88`
- end: `0x180002bd6`
- name: `?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012c0`
- `0x180005394`

## callees

- `0x180002b88`
- `0x180008010`

## pseudocode

```c
_BOOL8 __fastcall WWWServerTraceProvider::CheckTracingEnabled(
        int (__fastcall ***a1)(_QWORD, GUID **),
        __int64 a2,
        unsigned int a3)
{
  int (__fastcall **v3)(_QWORD, GUID **); // rax
  GUID *v6; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+28h] [rbp-20h]

  v6 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v3 = *a1;
  v7 = 0;
  return (*v3)(a1, &v6) >= 0 && DWORD2(v7) && DWORD1(v7) >= a3;
}

```

## disassembly

```asm
0x180002b88  push    rbx
0x180002b8a  sub     rsp, 40h
0x180002b8e  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002b95  xorps   xmm0, xmm0
0x180002b98  mov     [rsp+48h+var_28], rax
0x180002b9d  lea     rdx, [rsp+48h+var_28]
0x180002ba2  mov     rax, [rcx]
0x180002ba5  mov     ebx, r8d
0x180002ba8  movdqu  [rsp+48h+var_20], xmm0
0x180002bae  mov     rax, [rax]
0x180002bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb6  test    eax, eax
0x180002bb8  js      short loc_180002BCE
0x180002bba  cmp     dword ptr [rsp+48h+var_20+8], 0
0x180002bbf  jz      short loc_180002BCE
0x180002bc1  cmp     dword ptr [rsp+48h+var_20+4], ebx
0x180002bc5  jb      short loc_180002BCE
0x180002bc7  mov     eax, 1
0x180002bcc  jmp     short loc_180002BD0
0x180002bce  xor     eax, eax
0x180002bd0  add     rsp, 40h
0x180002bd4  pop     rbx
0x180002bd5  retn
```
