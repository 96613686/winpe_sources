# CActivationContextV6::Activate(HINSTANCE__ *)

- ea: `0x18001b7e4`
- end: `0x18001b917`
- name: `?Activate@CActivationContextV6@@QEAAJPEAUHINSTANCE__@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(CActivationContextV6 *__hidden this, HINSTANCE)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010054`
- `0x180010460`
- `0x180010664`

## callees

- `0x18001b7e4`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x18001b8d2`
- `KERNEL32!ActivateActCtx` at `0x18001b8d2`
- `KERNEL32!CreateActCtxW` at `0x18001b8a3`
- `KERNEL32!CreateActCtxW` at `0x18001b8a3`
- `KERNEL32!GetLastError` at `0x18001b862`
- `KERNEL32!GetLastError` at `0x18001b8b2`
- `KERNEL32!GetLastError` at `0x18001b8dc`
- `KERNEL32!GetLastError` at `0x18001b862`
- `KERNEL32!GetLastError` at `0x18001b8b2`
- `KERNEL32!GetLastError` at `0x18001b8dc`
- `KERNEL32!GetModuleFileNameW` at `0x18001b84f`
- `KERNEL32!GetModuleFileNameW` at `0x18001b84f`

## pseudocode

```c
__int64 __fastcall CActivationContextV6::Activate(CActivationContextV6 *this, HINSTANCE a2)
{
  DWORD ModuleFileNameW; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  HANDLE v6; // rax
  signed int v7; // eax
  signed int v8; // eax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset(&pActCtx, 0, sizeof(pActCtx));
  memset_0(Filename, 0, 0x208u);
  ModuleFileNameW = GetModuleFileNameW(g_hinstDll, Filename, 0x104u);
  if ( ModuleFileNameW )
  {
    v4 = 0;
    if ( ModuleFileNameW != 260 )
      goto LABEL_6;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( !v4 )
  {
LABEL_6:
    pActCtx.cbSize = 56;
    pActCtx.lpSource = Filename;
    pActCtx.dwFlags = 8;
    pActCtx.lpResourceName = (LPCWSTR)2;
    v6 = CreateActCtxW(&pActCtx);
    *(_QWORD *)this = v6;
    if ( v6 != (HANDLE)-1LL )
      goto LABEL_16;
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( !v4 )
    {
LABEL_16:
      if ( !ActivateActCtx(*(HANDLE *)this, (ULONG_PTR *)this + 1) )
      {
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          return (unsigned __int16)v8 | 0x80070000;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001b7e4  mov     [rsp-8+arg_8], rbx
0x18001b7e9  mov     [rsp-8+arg_10], rdi
0x18001b7ee  push    rbp
0x18001b7ef  lea     rbp, [rsp-180h]
0x18001b7f7  sub     rsp, 280h
0x18001b7fe  mov     rax, cs:__security_cookie
0x18001b805  xor     rax, rsp
0x18001b808  mov     [rbp+180h+var_10], rax
0x18001b80f  xorps   xmm0, xmm0
0x18001b812  mov     rdi, rcx
0x18001b815  xor     eax, eax
0x18001b817  lea     rcx, [rsp+280h+Filename]; void *
0x18001b81c  xor     edx, edx; Val
0x18001b81e  mov     [rsp+280h+pActCtx.hModule], rax
0x18001b823  mov     r8d, 208h; Size
0x18001b829  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18001b82e  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18001b833  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18001b838  call    memset_0
0x18001b83d  mov     rcx, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; hModule
0x18001b844  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18001b849  mov     r8d, 104h; nSize
0x18001b84f  call    cs:__imp_GetModuleFileNameW
0x18001b855  test    eax, eax
0x18001b857  jz      short loc_18001B862
0x18001b859  xor     ebx, ebx
0x18001b85b  cmp     eax, 104h
0x18001b860  jnz     short loc_18001B87B
0x18001b862  call    cs:__imp_GetLastError
0x18001b868  mov     ebx, eax
0x18001b86a  test    eax, eax
0x18001b86c  jle     short loc_18001B877
0x18001b86e  movzx   ebx, ax
0x18001b871  or      ebx, 80070000h
0x18001b877  test    ebx, ebx
0x18001b879  jnz     short loc_18001B8F1
0x18001b87b  lea     rax, [rsp+280h+Filename]
0x18001b880  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18001b888  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18001b88d  mov     [rsp+280h+pActCtx.lpSource], rax
0x18001b892  mov     [rsp+280h+pActCtx.dwFlags], 8
0x18001b89a  mov     [rsp+280h+pActCtx.lpResourceName], 2
0x18001b8a3  call    cs:__imp_CreateActCtxW
0x18001b8a9  mov     [rdi], rax
0x18001b8ac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b8b0  jnz     short loc_18001B8CB
0x18001b8b2  call    cs:__imp_GetLastError
0x18001b8b8  mov     ebx, eax
0x18001b8ba  test    eax, eax
0x18001b8bc  jle     short loc_18001B8C7
0x18001b8be  movzx   ebx, ax
0x18001b8c1  or      ebx, 80070000h
0x18001b8c7  test    ebx, ebx
0x18001b8c9  jnz     short loc_18001B8F1
0x18001b8cb  mov     rcx, [rdi]; hActCtx
0x18001b8ce  lea     rdx, [rdi+8]; lpCookie
0x18001b8d2  call    cs:__imp_ActivateActCtx
0x18001b8d8  test    eax, eax
0x18001b8da  jnz     short loc_18001B8F1
0x18001b8dc  call    cs:__imp_GetLastError
0x18001b8e2  mov     ebx, eax
0x18001b8e4  test    eax, eax
0x18001b8e6  jle     short loc_18001B8F1
0x18001b8e8  movzx   ebx, ax
0x18001b8eb  or      ebx, 80070000h
0x18001b8f1  mov     eax, ebx
0x18001b8f3  mov     rcx, [rbp+180h+var_10]
0x18001b8fa  xor     rcx, rsp; StackCookie
0x18001b8fd  call    __security_check_cookie
0x18001b902  lea     r11, [rsp+280h+var_s0]
0x18001b90a  mov     rbx, [r11+18h]
0x18001b90e  mov     rdi, [r11+20h]
0x18001b912  mov     rsp, r11
0x18001b915  pop     rbp
0x18001b916  retn
```
