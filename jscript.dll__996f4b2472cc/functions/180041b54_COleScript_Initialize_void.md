# COleScript::Initialize(void)

- ea: `0x180041b54`
- end: `0x180041c48`
- name: `?Initialize@COleScript@@QEAAHXZ`
- size: `244`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800412b0`
- `0x1800686c0`
- `0x180068770`
- `0x180078e20`

## callees

- `0x180041b54`
- `0x180098010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180041b7a`
- `KERNEL32!LoadLibraryExW` at `0x180041b7a`
- `KERNEL32!GetProcAddress` at `0x180041b9c`
- `KERNEL32!GetProcAddress` at `0x180041bb9`
- `KERNEL32!GetProcAddress` at `0x180041b9c`
- `KERNEL32!GetProcAddress` at `0x180041bb9`
- `KERNEL32!InitializeCriticalSection` at `0x180041c13`
- `KERNEL32!InitializeCriticalSection` at `0x180041c13`

## string_xrefs

- `0x180041bab`: `AmsiScanString`
- `0x180041b73`: `amsi.dll`
- `0x180041b92`: `AmsiInitialize`

## pseudocode

```c
__int64 __fastcall COleScript::Initialize(COleScript *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v4; // rax

  Library = LoadLibraryExW(L"amsi.dll", 0, 0x800u);
  *((_QWORD *)this + 125) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AmsiInitialize");
    v4 = GetProcAddress(*((HMODULE *)this + 125), "AmsiScanString");
    *((_QWORD *)this + 122) = v4;
    if ( ProcAddress )
    {
      if ( v4 && ((int (__fastcall *)(_QWORD, char *))ProcAddress)(*((_QWORD *)this + 23), (char *)this + 968) < 0 )
        *((_QWORD *)this + 121) = 0;
    }
  }
  *((_DWORD *)this + 140) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  return *((unsigned int *)this + 140);
}

```

## disassembly

```asm
0x180041b54  mov     [rsp+arg_10], rbx
0x180041b59  mov     [rsp+arg_18], rsi
0x180041b5e  mov     [rsp+arg_0], rcx
0x180041b63  push    rdi
0x180041b64  sub     rsp, 20h
0x180041b68  mov     rdi, rcx
0x180041b6b  xor     edx, edx; hFile
0x180041b6d  mov     r8d, 800h; dwFlags
0x180041b73  lea     rcx, LibFileName; "amsi.dll"
0x180041b7a  call    cs:__imp_LoadLibraryExW
0x180041b81  nop     dword ptr [rax+rax+00h]
0x180041b86  mov     [rdi+3E8h], rax
0x180041b8d  test    rax, rax
0x180041b90  jz      short loc_180041BFA
0x180041b92  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x180041b99  mov     rcx, rax; hModule
0x180041b9c  call    cs:__imp_GetProcAddress
0x180041ba3  nop     dword ptr [rax+rax+00h]
0x180041ba8  mov     rsi, rax
0x180041bab  lea     rdx, aAmsiscanstring; "AmsiScanString"
0x180041bb2  mov     rcx, [rdi+3E8h]; hModule
0x180041bb9  call    cs:__imp_GetProcAddress
0x180041bc0  nop     dword ptr [rax+rax+00h]
0x180041bc5  mov     [rdi+3D0h], rax
0x180041bcc  test    rsi, rsi
0x180041bcf  jz      short loc_180041BFA
0x180041bd1  test    rax, rax
0x180041bd4  jz      short loc_180041BFA
0x180041bd6  lea     rbx, [rdi+3C8h]
0x180041bdd  mov     rdx, rbx
0x180041be0  mov     rcx, [rdi+0B8h]
0x180041be7  mov     rax, rsi
0x180041bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bef  test    eax, eax
0x180041bf1  jns     short loc_180041BFA
0x180041bf3  mov     qword ptr [rbx], 0
0x180041bfa  lea     rbx, [rdi+230h]
0x180041c01  mov     [rsp+28h+arg_8], rbx
0x180041c06  mov     dword ptr [rbx], 1
0x180041c0c  lea     rcx, [rdi+238h]; lpCriticalSection
0x180041c13  call    cs:__imp_InitializeCriticalSection
0x180041c1a  nop     dword ptr [rax+rax+00h]
0x180041c1f  jmp     short loc_180041C35
0x180041c21  mov     rax, [rsp+28h+arg_0]
0x180041c26  mov     dword ptr [rax+230h], 0
0x180041c30  mov     rbx, [rsp+28h+arg_8]
0x180041c35  mov     eax, [rbx]
0x180041c37  mov     rbx, [rsp+28h+arg_10]
0x180041c3c  mov     rsi, [rsp+28h+arg_18]
0x180041c41  add     rsp, 20h
0x180041c45  pop     rdi
0x180041c46  retn
```
