# GetSecurityDescriptor

- ea: `0x14000a3b4`
- end: `0x14000a4a7`
- name: `GetSecurityDescriptor`
- size: `243`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009a08`

## callees

- `0x14000a3b4`

## import_xrefs

- `ADVAPI32!GetKernelObjectSecurity` at `0x14000a3e4`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000a46d`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000a3e4`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000a46d`
- `KERNEL32!LocalAlloc` at `0x14000a423`
- `KERNEL32!LocalAlloc` at `0x14000a423`
- `KERNEL32!LocalFree` at `0x14000a445`
- `KERNEL32!LocalFree` at `0x14000a445`
- `KERNEL32!GetLastError` at `0x14000a3f8`
- `KERNEL32!GetLastError` at `0x14000a47d`
- `KERNEL32!GetLastError` at `0x14000a3f8`
- `KERNEL32!GetLastError` at `0x14000a47d`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor(HANDLE Handle, _QWORD *a2)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  HLOCAL v6; // rdi
  signed int v7; // eax
  DWORD nLengthNeeded; // [rsp+70h] [rbp+18h] BYREF

  nLengthNeeded = 0;
  v4 = -2147418113;
  if ( !GetKernelObjectSecurity(Handle, 7u, 0, 0, &nLengthNeeded) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_7;
    }
    v6 = LocalAlloc(0x40u, nLengthNeeded);
    if ( !v6 )
    {
      v4 = -2147024882;
LABEL_7:
      *a2 = 0;
      LocalFree(0);
      return v4;
    }
    v4 = 0;
    if ( !GetKernelObjectSecurity(Handle, 7u, v6, nLengthNeeded, &nLengthNeeded) )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
    }
    *a2 = v6;
  }
  return v4;
}

```

## disassembly

```asm
0x14000a3b4  push    rbx
0x14000a3b6  push    rbp
0x14000a3b7  push    rsi
0x14000a3b8  push    rdi
0x14000a3b9  sub     rsp, 38h
0x14000a3bd  xor     r9d, r9d; nLength
0x14000a3c0  mov     [rsp+58h+nLengthNeeded], 0
0x14000a3c8  mov     rsi, rdx
0x14000a3cb  lea     rax, [rsp+58h+nLengthNeeded]
0x14000a3d0  xor     r8d, r8d; pSecurityDescriptor
0x14000a3d3  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14000a3d8  mov     rbp, rcx
0x14000a3db  mov     ebx, 8000FFFFh
0x14000a3e0  lea     edx, [r9+7]; RequestedInformation
0x14000a3e4  call    cs:__imp_GetKernelObjectSecurity
0x14000a3eb  nop     dword ptr [rax+rax+00h]
0x14000a3f0  test    eax, eax
0x14000a3f2  jnz     loc_14000A49B
0x14000a3f8  call    cs:__imp_GetLastError
0x14000a3ff  nop     dword ptr [rax+rax+00h]
0x14000a404  mov     ebx, eax
0x14000a406  cmp     eax, 7Ah ; 'z'
0x14000a409  jz      short loc_14000A41A
0x14000a40b  test    eax, eax
0x14000a40d  jle     short loc_14000A43C
0x14000a40f  movzx   ebx, ax
0x14000a412  or      ebx, 80070000h
0x14000a418  jmp     short loc_14000A43C
0x14000a41a  mov     edx, [rsp+58h+nLengthNeeded]; uBytes
0x14000a41e  mov     ecx, 40h ; '@'; uFlags
0x14000a423  call    cs:__imp_LocalAlloc
0x14000a42a  nop     dword ptr [rax+rax+00h]
0x14000a42f  mov     rdi, rax
0x14000a432  test    rax, rax
0x14000a435  jnz     short loc_14000A453
0x14000a437  mov     ebx, 8007000Eh
0x14000a43c  xor     ecx, ecx; hMem
0x14000a43e  mov     qword ptr [rsi], 0
0x14000a445  call    cs:__imp_LocalFree
0x14000a44c  nop     dword ptr [rax+rax+00h]
0x14000a451  jmp     short loc_14000A49B
0x14000a453  mov     r9d, [rsp+58h+nLengthNeeded]; nLength
0x14000a458  lea     rax, [rsp+58h+nLengthNeeded]
0x14000a45d  xor     ebx, ebx
0x14000a45f  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14000a464  mov     r8, rdi; pSecurityDescriptor
0x14000a467  mov     rcx, rbp; Handle
0x14000a46a  lea     edx, [rbx+7]; RequestedInformation
0x14000a46d  call    cs:__imp_GetKernelObjectSecurity
0x14000a474  nop     dword ptr [rax+rax+00h]
0x14000a479  test    eax, eax
0x14000a47b  jnz     short loc_14000A498
0x14000a47d  call    cs:__imp_GetLastError
0x14000a484  nop     dword ptr [rax+rax+00h]
0x14000a489  mov     ebx, eax
0x14000a48b  test    eax, eax
0x14000a48d  jle     short loc_14000A498
0x14000a48f  movzx   ebx, ax
0x14000a492  or      ebx, 80070000h
0x14000a498  mov     [rsi], rdi
0x14000a49b  mov     eax, ebx
0x14000a49d  add     rsp, 38h
0x14000a4a1  pop     rdi
0x14000a4a2  pop     rsi
0x14000a4a3  pop     rbp
0x14000a4a4  pop     rbx
0x14000a4a5  retn
```
