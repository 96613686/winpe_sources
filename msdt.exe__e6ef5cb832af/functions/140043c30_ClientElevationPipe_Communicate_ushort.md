# ClientElevationPipe::Communicate(ushort * *)

- ea: `0x140043c30`
- end: `0x140043e72`
- name: `?Communicate@ClientElevationPipe@@UEAAJPEAPEAG@Z`
- size: `578`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x14000706c`
- `0x14001b578`
- `0x140020420`
- `0x140020c90`
- `0x140043c30`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140043cdc`
- `KERNEL32!GetLastError` at `0x140043cef`
- `KERNEL32!GetLastError` at `0x140043cdc`
- `KERNEL32!GetLastError` at `0x140043cef`
- `KERNEL32!HeapAlloc` at `0x140043c6d`
- `KERNEL32!HeapAlloc` at `0x140043dae`
- `KERNEL32!HeapAlloc` at `0x140043c6d`
- `KERNEL32!HeapAlloc` at `0x140043dae`
- `KERNEL32!HeapFree` at `0x140043e1a`
- `KERNEL32!HeapFree` at `0x140043e3f`
- `KERNEL32!HeapFree` at `0x140043e1a`
- `KERNEL32!HeapFree` at `0x140043e3f`
- `KERNEL32!GetProcessHeap` at `0x140043c54`
- `KERNEL32!GetProcessHeap` at `0x140043d97`
- `KERNEL32!GetProcessHeap` at `0x140043e06`
- `KERNEL32!GetProcessHeap` at `0x140043e2b`
- `KERNEL32!GetProcessHeap` at `0x140043c54`
- `KERNEL32!GetProcessHeap` at `0x140043d97`
- `KERNEL32!GetProcessHeap` at `0x140043e06`
- `KERNEL32!GetProcessHeap` at `0x140043e2b`
- `KERNEL32!ReadFile` at `0x140043ccc`
- `KERNEL32!ReadFile` at `0x140043ccc`

## string_xrefs

- `0x140043c86`: `ClientElevationPipe::Communicate`
- `0x140043df8`: `ClientElevationPipe::Communicate`

## pseudocode

```c
__int64 __fastcall ClientElevationPipe::Communicate(HANDLE *this, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // r14
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rsi
  signed int LastError; // eax
  int v10; // r9d
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // rbp
  __int64 v14; // rax
  HANDLE v15; // rax
  unsigned __int16 *v16; // rax
  Configuration *v17; // rcx
  HANDLE v18; // rax
  HANDLE v19; // rax
  unsigned __int16 *v21; // [rsp+70h] [rbp+18h] BYREF

  v21 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x1000u);
  v6 = v5;
  if ( !v5 )
  {
    v7 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ClientElevationPipe::Communicate", 147, -2147024882);
    return v7;
  }
  *v5 = 0;
  v8 = 0;
  if ( !ReadFile(this[1], v5, 0x1000u, 0, (LPOVERLAPPED)(this + 5)) )
  {
    if ( GetLastError() != 997 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
      {
        v10 = 157;
LABEL_9:
        v11 = v7;
        goto LABEL_23;
      }
    }
    v11 = (*((__int64 (__fastcall **)(HANDLE *, __int64))*this + 4))(this, 1000);
    v7 = v11;
    if ( v11 < 0 )
    {
      v10 = 161;
      goto LABEL_23;
    }
  }
  v12 = DwzStrTok(v6, 0x3Bu, &v21);
  v7 = v12;
  if ( v12 == 1 )
  {
    v7 = -2147467259;
LABEL_15:
    v10 = 172;
    goto LABEL_9;
  }
  if ( v12 < 0 )
    goto LABEL_15;
  v13 = v21;
  v14 = -1;
  do
    ++v14;
  while ( v21[v14] );
  if ( !v14 )
  {
LABEL_26:
    *a2 = v6;
    return v7;
  }
  v15 = GetProcessHeap();
  v16 = (unsigned __int16 *)HeapAlloc(v15, 0, 0x200u);
  v8 = v16;
  if ( !v16 )
  {
    v11 = -2147024882;
    v10 = 175;
    v7 = -2147024882;
    goto LABEL_23;
  }
  v11 = StringCchCopyW(v16, 0x100u, v13);
  v7 = v11;
  if ( v11 >= 0 )
  {
    Configuration::SecurityBoundarySafe(v17, v8);
    goto LABEL_26;
  }
  v10 = 178;
LABEL_23:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ClientElevationPipe::Communicate", v10, v11);
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v6);
  if ( v8 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v8);
  }
  return v7;
}

```

## disassembly

```asm
0x140043c30  mov     [rsp+arg_0], rbx
0x140043c35  mov     [rsp+arg_8], rbp
0x140043c3a  push    rsi
0x140043c3b  push    rdi
0x140043c3c  push    r12
0x140043c3e  push    r14
0x140043c40  push    r15
0x140043c42  sub     rsp, 30h
0x140043c46  xor     r12d, r12d
0x140043c49  mov     r15, rdx
0x140043c4c  mov     [rsp+58h+arg_10], r12
0x140043c51  mov     rdi, rcx
0x140043c54  call    cs:__imp_GetProcessHeap
0x140043c5b  nop     dword ptr [rax+rax+00h]
0x140043c60  mov     ebx, 1000h
0x140043c65  xor     edx, edx; dwFlags
0x140043c67  mov     rcx, rax; hHeap
0x140043c6a  mov     r8d, ebx; dwBytes
0x140043c6d  call    cs:__imp_HeapAlloc
0x140043c74  nop     dword ptr [rax+rax+00h]
0x140043c79  mov     r14, rax
0x140043c7c  test    rax, rax
0x140043c7f  jnz     short loc_140043CAF
0x140043c81  mov     eax, 8007000Eh
0x140043c86  lea     r8, aClientelevatio; "ClientElevationPipe::Communicate"
0x140043c8d  mov     r9d, 93h
0x140043c93  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x140043c97  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043c9e  mov     ebx, eax
0x140043ca0  lea     ecx, [r12+1]; Level
0x140043ca5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043caa  jmp     loc_140043E58
0x140043caf  mov     [rax], r12w
0x140043cb3  xor     r9d, r9d; lpNumberOfBytesRead
0x140043cb6  mov     rcx, [rdi+8]; hFile
0x140043cba  lea     rax, [rdi+28h]
0x140043cbe  mov     r8d, ebx; nNumberOfBytesToRead
0x140043cc1  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x140043cc6  mov     rdx, r14; lpBuffer
0x140043cc9  mov     rsi, r12
0x140043ccc  call    cs:__imp_ReadFile
0x140043cd3  nop     dword ptr [rax+rax+00h]
0x140043cd8  test    eax, eax
0x140043cda  jnz     short loc_140043D4A
0x140043cdc  call    cs:__imp_GetLastError
0x140043ce3  nop     dword ptr [rax+rax+00h]
0x140043ce8  cmp     eax, 3E5h
0x140043ced  jz      short loc_140043D20
0x140043cef  call    cs:__imp_GetLastError
0x140043cf6  nop     dword ptr [rax+rax+00h]
0x140043cfb  mov     ebx, eax
0x140043cfd  test    eax, eax
0x140043cff  jle     short loc_140043D0A
0x140043d01  movzx   ebx, ax
0x140043d04  or      ebx, 80070000h
0x140043d0a  test    ebx, ebx
0x140043d0c  jns     short loc_140043D20
0x140043d0e  mov     edi, 1
0x140043d13  mov     r9d, 9Dh
0x140043d19  mov     eax, ebx
0x140043d1b  jmp     loc_140043DED
0x140043d20  mov     rax, [rdi]
0x140043d23  mov     edx, 3E8h
0x140043d28  mov     rcx, rdi
0x140043d2b  mov     rax, [rax+20h]
0x140043d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043d34  mov     ebx, eax
0x140043d36  test    eax, eax
0x140043d38  jns     short loc_140043D4A
0x140043d3a  mov     edi, 1
0x140043d3f  mov     r9d, 0A1h
0x140043d45  jmp     loc_140043DED
0x140043d4a  mov     edx, 3Bh ; ';'; unsigned __int16
0x140043d4f  lea     r8, [rsp+58h+arg_10]; unsigned __int16 **
0x140043d54  mov     rcx, r14; unsigned __int16 *
0x140043d57  call    ?DwzStrTok@@YAJPEAGGPEAPEAG@Z; DwzStrTok(ushort *,ushort,ushort * *)
0x140043d5c  mov     edi, 1
0x140043d61  mov     ebx, eax
0x140043d63  cmp     eax, edi
0x140043d65  jnz     short loc_140043D6E
0x140043d67  mov     ebx, 80004005h
0x140043d6c  jmp     short loc_140043D72
0x140043d6e  test    eax, eax
0x140043d70  jns     short loc_140043D7A
0x140043d72  mov     r9d, 0ACh
0x140043d78  jmp     short loc_140043D19
0x140043d7a  mov     rbp, [rsp+58h+arg_10]
0x140043d7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140043d83  inc     rax
0x140043d86  cmp     [rbp+rax*2+0], r12w
0x140043d8c  jnz     short loc_140043D83
0x140043d8e  test    rax, rax
0x140043d91  jz      loc_140043E55
0x140043d97  call    cs:__imp_GetProcessHeap
0x140043d9e  nop     dword ptr [rax+rax+00h]
0x140043da3  xor     edx, edx; dwFlags
0x140043da5  mov     r8d, 200h; dwBytes
0x140043dab  mov     rcx, rax; hHeap
0x140043dae  call    cs:__imp_HeapAlloc
0x140043db5  nop     dword ptr [rax+rax+00h]
0x140043dba  mov     rsi, rax
0x140043dbd  test    rax, rax
0x140043dc0  jnz     short loc_140043DD1
0x140043dc2  mov     eax, 8007000Eh
0x140043dc7  mov     r9d, 0AFh
0x140043dcd  mov     ebx, eax
0x140043dcf  jmp     short loc_140043DED
0x140043dd1  mov     r8, rbp; unsigned __int16 *
0x140043dd4  mov     edx, 100h; unsigned __int64
0x140043dd9  mov     rcx, rsi; unsigned __int16 *
0x140043ddc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140043de1  mov     ebx, eax
0x140043de3  test    eax, eax
0x140043de5  jns     short loc_140043E4D
0x140043de7  mov     r9d, 0B2h
0x140043ded  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043df4  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x140043df8  lea     r8, aClientelevatio; "ClientElevationPipe::Communicate"
0x140043dff  mov     ecx, edi; Level
0x140043e01  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043e06  call    cs:__imp_GetProcessHeap
0x140043e0d  nop     dword ptr [rax+rax+00h]
0x140043e12  mov     r8, r14; lpMem
0x140043e15  xor     edx, edx; dwFlags
0x140043e17  mov     rcx, rax; hHeap
0x140043e1a  call    cs:__imp_HeapFree
0x140043e21  nop     dword ptr [rax+rax+00h]
0x140043e26  test    rsi, rsi
0x140043e29  jz      short loc_140043E58
0x140043e2b  call    cs:__imp_GetProcessHeap
0x140043e32  nop     dword ptr [rax+rax+00h]
0x140043e37  mov     r8, rsi; lpMem
0x140043e3a  xor     edx, edx; dwFlags
0x140043e3c  mov     rcx, rax; hHeap
0x140043e3f  call    cs:__imp_HeapFree
0x140043e46  nop     dword ptr [rax+rax+00h]
0x140043e4b  jmp     short loc_140043E58
0x140043e4d  mov     rdx, rsi; unsigned __int16 *
0x140043e50  call    ?SecurityBoundarySafe@Configuration@@QEAAXPEAG@Z; Configuration::SecurityBoundarySafe(ushort *)
0x140043e55  mov     [r15], r14
0x140043e58  mov     rbp, [rsp+58h+arg_8]
0x140043e5d  mov     eax, ebx
0x140043e5f  mov     rbx, [rsp+58h+arg_0]
0x140043e64  add     rsp, 30h
0x140043e68  pop     r15
0x140043e6a  pop     r14
0x140043e6c  pop     r12
0x140043e6e  pop     rdi
0x140043e6f  pop     rsi
0x140043e70  retn
```
