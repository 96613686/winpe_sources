# WWWIsapiExtensionTraceProvider::CheckTracingEnabled(IHttpTraceContext *,ulong)

- ea: `0x18000b30c`
- end: `0x18000b359`
- name: `?CheckTracingEnabled@WWWIsapiExtensionTraceProvider@@SAHPEAVIHttpTraceContext@@K@Z`
- size: `77`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b3d0`
- `0x18000bd8c`
- `0x18000f440`

## callees

- `0x18000b30c`
- `0x180013010`

## pseudocode

```c
_BOOL8 __fastcall WWWIsapiExtensionTraceProvider::CheckTracingEnabled(
        int (__fastcall ***a1)(struct IHttpTraceContext *, GUID **),
        unsigned int a2)
{
  int (__fastcall **v3)(struct IHttpTraceContext *, GUID **); // rax
  GUID *v5; // [rsp+20h] [rbp-28h] BYREF
  __int128 v6; // [rsp+28h] [rbp-20h]

  v5 = &`WWWIsapiExtensionTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v3 = *a1;
  v6 = 0;
  return (*v3)((struct IHttpTraceContext *)a1, &v5) >= 0 && DWORD2(v6) && DWORD1(v6) >= a2;
}

```

## disassembly

```asm
0x18000b30c  push    rbx
0x18000b30e  sub     rsp, 40h
0x18000b312  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWIsapiExtensionTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWIsapiExtensionTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000b319  mov     ebx, edx
0x18000b31b  mov     [rsp+48h+var_28], rax
0x18000b320  lea     rdx, [rsp+48h+var_28]
0x18000b325  mov     rax, [rcx]
0x18000b328  xorps   xmm0, xmm0
0x18000b32b  movdqu  [rsp+48h+var_20], xmm0
0x18000b331  mov     rax, [rax]
0x18000b334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b339  test    eax, eax
0x18000b33b  js      short loc_18000B351
0x18000b33d  cmp     dword ptr [rsp+48h+var_20+8], 0
0x18000b342  jz      short loc_18000B351
0x18000b344  cmp     dword ptr [rsp+48h+var_20+4], ebx
0x18000b348  jb      short loc_18000B351
0x18000b34a  mov     eax, 1
0x18000b34f  jmp     short loc_18000B353
0x18000b351  xor     eax, eax
0x18000b353  add     rsp, 40h
0x18000b357  pop     rbx
0x18000b358  retn
```
