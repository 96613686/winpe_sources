# WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)

- ea: `0x180004b80`
- end: `0x180004bdc`
- name: `?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a20`
- `0x180003f80`
- `0x180004440`
- `0x1800060a0`
- `0x1800071c0`
- `0x1800084b0`

## callees

- `0x180004b80`
- `0x18000d010`

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
  return (*v3)(a1, &v6) >= 0 && DWORD2(v7) && DWORD1(v7) >= a3 && ((_DWORD)v7 == 8 || (v7 & 8) != 0);
}

```

## disassembly

```asm
0x180004b80  push    rbx
0x180004b82  sub     rsp, 40h
0x180004b86  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004b8d  xorps   xmm0, xmm0
0x180004b90  mov     [rsp+48h+var_28], rax
0x180004b95  lea     rdx, [rsp+48h+var_28]
0x180004b9a  mov     rax, [rcx]
0x180004b9d  mov     ebx, r8d
0x180004ba0  movdqu  [rsp+48h+var_20], xmm0
0x180004ba6  mov     rax, [rax]
0x180004ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bae  test    eax, eax
0x180004bb0  js      short loc_180004BB9
0x180004bb2  cmp     dword ptr [rsp+48h+var_20+8], 0
0x180004bb7  jnz     short loc_180004BC1
0x180004bb9  xor     eax, eax
0x180004bbb  add     rsp, 40h
0x180004bbf  pop     rbx
0x180004bc0  retn
0x180004bc1  cmp     dword ptr [rsp+48h+var_20+4], ebx
0x180004bc5  jb      short loc_180004BB9
0x180004bc7  mov     rax, qword ptr [rsp+48h+var_20]
0x180004bcc  cmp     eax, 8
0x180004bcf  jz      short loc_180004BD5
0x180004bd1  test    al, 8
0x180004bd3  jz      short loc_180004BB9
0x180004bd5  mov     eax, 1
0x180004bda  jmp     short loc_180004BBB
```
