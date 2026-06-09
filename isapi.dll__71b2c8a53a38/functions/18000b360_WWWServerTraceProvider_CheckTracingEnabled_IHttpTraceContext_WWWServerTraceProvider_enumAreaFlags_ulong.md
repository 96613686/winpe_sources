# WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)

- ea: `0x18000b360`
- end: `0x18000b3c8`
- name: `?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b3d0`
- `0x18000c2b4`
- `0x180012188`

## callees

- `0x18000b360`
- `0x180013010`

## pseudocode

```c
_BOOL8 __fastcall WWWServerTraceProvider::CheckTracingEnabled(
        int (__fastcall ***a1)(_QWORD, GUID **),
        int a2,
        unsigned int a3)
{
  int (__fastcall **v4)(_QWORD, GUID **); // rax
  GUID *v7; // [rsp+20h] [rbp-28h] BYREF
  __int128 v8; // [rsp+28h] [rbp-20h]

  v7 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v4 = *a1;
  v8 = 0;
  return (*v4)(a1, &v7) >= 0 && DWORD2(v8) && DWORD1(v8) >= a3 && ((_DWORD)v8 == a2 || (a2 & (unsigned int)v8) == a2);
}

```

## disassembly

```asm
0x18000b360  mov     [rsp+arg_0], rbx
0x18000b365  push    rdi
0x18000b366  sub     rsp, 40h
0x18000b36a  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000b371  mov     ebx, edx
0x18000b373  mov     [rsp+48h+var_28], rax
0x18000b378  lea     rdx, [rsp+48h+var_28]
0x18000b37d  mov     rax, [rcx]
0x18000b380  xorps   xmm0, xmm0
0x18000b383  mov     edi, r8d
0x18000b386  movdqu  [rsp+48h+var_20], xmm0
0x18000b38c  mov     rax, [rax]
0x18000b38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b394  test    eax, eax
0x18000b396  js      short loc_18000B3BB
0x18000b398  cmp     dword ptr [rsp+48h+var_20+8], 0
0x18000b39d  jz      short loc_18000B3BB
0x18000b39f  cmp     dword ptr [rsp+48h+var_20+4], edi
0x18000b3a3  jb      short loc_18000B3BB
0x18000b3a5  mov     rax, qword ptr [rsp+48h+var_20]
0x18000b3aa  cmp     eax, ebx
0x18000b3ac  jz      short loc_18000B3B4
0x18000b3ae  and     eax, ebx
0x18000b3b0  cmp     eax, ebx
0x18000b3b2  jnz     short loc_18000B3BB
0x18000b3b4  mov     eax, 1
0x18000b3b9  jmp     short loc_18000B3BD
0x18000b3bb  xor     eax, eax
0x18000b3bd  mov     rbx, [rsp+48h+arg_0]
0x18000b3c2  add     rsp, 40h
0x18000b3c6  pop     rdi
0x18000b3c7  retn
```
