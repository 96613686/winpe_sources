# SHFusionInitializeFromModuleID

- ea: `0x180029890`
- end: `0x180029995`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017a14`
- `0x180029800`

## callees

- `0x180029890`
- `0x180029c34`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180029903`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180029903`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800298ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800298ec`
- `KERNEL32!ReleaseActCtx` at `0x180029953`
- `KERNEL32!ReleaseActCtx` at `0x180029953`
- `KERNEL32!CreateActCtxW` at `0x180029935`
- `KERNEL32!CreateActCtxW` at `0x180029935`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE v4; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  ModuleHandleW = hModule;
  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCWSTR)a2;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v4 = CreateActCtxW(&pActCtx);
  if ( v4 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180029890  mov     [rsp-8+arg_10], rbx
0x180029895  mov     [rsp-8+arg_18], rdi
0x18002989a  push    rbp
0x18002989b  lea     rbp, [rsp-180h]
0x1800298a3  sub     rsp, 280h
0x1800298aa  mov     rax, cs:__security_cookie
0x1800298b1  xor     rax, rsp
0x1800298b4  mov     [rbp+180h+var_10], rax
0x1800298bb  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800298c3  mov     rbx, rcx
0x1800298c6  mov     edi, edx
0x1800298c8  jnz     loc_18002996C
0x1800298ce  xorps   xmm0, xmm0
0x1800298d1  xor     eax, eax
0x1800298d3  mov     [rsp+280h+pActCtx.hModule], rax
0x1800298d8  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x1800298dd  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x1800298e2  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x1800298e7  test    rcx, rcx
0x1800298ea  jnz     short loc_1800298F5
0x1800298ec  call    cs:__imp_GetModuleHandleW
0x1800298f2  mov     rbx, rax
0x1800298f5  mov     r8d, 104h; nSize
0x1800298fb  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180029900  mov     rcx, rbx; hModule
0x180029903  call    cs:__imp_GetModuleFileNameW
0x180029909  movzx   ecx, di
0x18002990c  lea     rax, [rsp+280h+Filename]
0x180029911  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180029916  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18002991b  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180029923  mov     [rsp+280h+pActCtx.lpSource], rax
0x180029928  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180029930  mov     [rsp+280h+pActCtx.hModule], rbx
0x180029935  call    cs:__imp_CreateActCtxW
0x18002993b  mov     rcx, rax; hActCtx
0x18002993e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029942  jz      short loc_18002995E
0x180029944  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029948  lock cmpxchg cs:g_hActCtx, rcx
0x180029951  jz      short loc_180029959
0x180029953  call    cs:__imp_ReleaseActCtx
0x180029959  call    DelayLoadCC
0x18002995e  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180029966  jnz     short loc_18002996C
0x180029968  xor     eax, eax
0x18002996a  jmp     short loc_180029971
0x18002996c  mov     eax, 1
0x180029971  mov     rcx, [rbp+180h+var_10]
0x180029978  xor     rcx, rsp; StackCookie
0x18002997b  call    __security_check_cookie
0x180029980  lea     r11, [rsp+280h+var_s0]
0x180029988  mov     rbx, [r11+20h]
0x18002998c  mov     rdi, [r11+28h]
0x180029990  mov     rsp, r11
0x180029993  pop     rbp
0x180029994  retn
```
