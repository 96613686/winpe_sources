# EnableWWWServerProvider(IHttpTraceContext *,int)

- ea: `0x180001f1c`
- end: `0x180001f7a`
- name: `?EnableWWWServerProvider@@YAJPEAVIHttpTraceContext@@H@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f90`
- `0x1800023cc`
- `0x180002798`
- `0x180003130`

## callees

- `0x180001f1c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall EnableWWWServerProvider(struct IHttpTraceContext *a1, int a2)
{
  GUID *v3; // [rsp+30h] [rbp-28h] BYREF
  __int64 v4; // [rsp+38h] [rbp-20h]
  int v5; // [rsp+40h] [rbp-18h]
  int v6; // [rsp+44h] [rbp-14h]

  v6 = 0;
  v3 = &GUID_IIS_WWW_SERVER_TRACE_PROVIDER;
  if ( a2 )
  {
    v4 = 0x50000FFFELL;
    v5 = 1;
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  return (*(__int64 (__fastcall **)(struct IHttpTraceContext *, void *, GUID **, __int64))(*(_QWORD *)a1 + 8LL))(
           a1,
           g_pModuleContext,
           &v3,
           1);
}

```

## disassembly

```asm
0x180001f1c  sub     rsp, 58h
0x180001f20  xor     r8d, r8d
0x180001f23  lea     rax, GUID_IIS_WWW_SERVER_TRACE_PROVIDER
0x180001f2a  mov     [rsp+58h+var_14], r8d
0x180001f2f  mov     [rsp+58h+var_28], rax
0x180001f34  lea     r9d, [r8+1]
0x180001f38  test    edx, edx
0x180001f3a  jz      short loc_180001F53
0x180001f3c  mov     dword ptr [rsp+58h+var_20], 0FFFEh
0x180001f44  mov     dword ptr [rsp+58h+var_20+4], 5
0x180001f4c  mov     [rsp+58h+var_18], r9d
0x180001f51  jmp     short loc_180001F5D
0x180001f53  mov     [rsp+58h+var_20], r8
0x180001f58  mov     [rsp+58h+var_18], r8d
0x180001f5d  mov     rax, [rcx]
0x180001f60  lea     r8, [rsp+58h+var_28]
0x180001f65  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180001f6c  mov     rax, [rax+8]
0x180001f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f75  add     rsp, 58h
0x180001f79  retn
```
