# SHFusionInitializeFromModuleID

- ea: `0x18001c298`
- end: `0x18001c39d`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010ea4`
- `0x18001c0c4`

## callees

- `0x180001510`
- `0x18001c298`
- `0x18001c888`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c2f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c2f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001c30b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001c30b`
- `KERNEL32!CreateActCtxW` at `0x18001c33d`
- `KERNEL32!CreateActCtxW` at `0x18001c33d`
- `KERNEL32!ReleaseActCtx` at `0x18001c35b`
- `KERNEL32!ReleaseActCtx` at `0x18001c35b`

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
0x18001c298  mov     [rsp-8+arg_10], rbx
0x18001c29d  mov     [rsp-8+arg_18], rdi
0x18001c2a2  push    rbp
0x18001c2a3  lea     rbp, [rsp-180h]
0x18001c2ab  sub     rsp, 280h
0x18001c2b2  mov     rax, cs:__security_cookie
0x18001c2b9  xor     rax, rsp
0x18001c2bc  mov     [rbp+180h+var_10], rax
0x18001c2c3  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18001c2cb  mov     rbx, rcx
0x18001c2ce  mov     edi, edx
0x18001c2d0  jnz     loc_18001C374
0x18001c2d6  xorps   xmm0, xmm0
0x18001c2d9  xor     eax, eax
0x18001c2db  mov     [rsp+280h+pActCtx.hModule], rax
0x18001c2e0  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18001c2e5  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18001c2ea  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18001c2ef  test    rcx, rcx
0x18001c2f2  jnz     short loc_18001C2FD
0x18001c2f4  call    cs:__imp_GetModuleHandleW
0x18001c2fa  mov     rbx, rax
0x18001c2fd  mov     r8d, 104h; nSize
0x18001c303  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18001c308  mov     rcx, rbx; hModule
0x18001c30b  call    cs:__imp_GetModuleFileNameW
0x18001c311  movzx   ecx, di
0x18001c314  lea     rax, [rsp+280h+Filename]
0x18001c319  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18001c31e  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18001c323  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18001c32b  mov     [rsp+280h+pActCtx.lpSource], rax
0x18001c330  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18001c338  mov     [rsp+280h+pActCtx.hModule], rbx
0x18001c33d  call    cs:__imp_CreateActCtxW
0x18001c343  mov     rcx, rax; hActCtx
0x18001c346  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c34a  jz      short loc_18001C366
0x18001c34c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c350  lock cmpxchg cs:g_hActCtx, rcx
0x18001c359  jz      short loc_18001C361
0x18001c35b  call    cs:__imp_ReleaseActCtx
0x18001c361  call    DelayLoadCC
0x18001c366  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18001c36e  jnz     short loc_18001C374
0x18001c370  xor     eax, eax
0x18001c372  jmp     short loc_18001C379
0x18001c374  mov     eax, 1
0x18001c379  mov     rcx, [rbp+180h+var_10]
0x18001c380  xor     rcx, rsp; StackCookie
0x18001c383  call    __security_check_cookie
0x18001c388  lea     r11, [rsp+280h+var_s0]
0x18001c390  mov     rbx, [r11+20h]
0x18001c394  mov     rdi, [r11+28h]
0x18001c398  mov     rsp, r11
0x18001c39b  pop     rbp
0x18001c39c  retn
```
