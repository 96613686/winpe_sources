# GetLocalSystemAccount(ushort * *)

- ea: `0x180077d60`
- end: `0x180077e12`
- name: `?GetLocalSystemAccount@@YAJPEAPEAG@Z`
- size: `178`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180077fd4`

## callees

- `0x180077d60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180077dcd`
- `KERNEL32!GetLastError` at `0x180077dcd`
- `KERNEL32!LocalAlloc` at `0x180077d95`
- `KERNEL32!LocalAlloc` at `0x180077d95`
- `KERNEL32!LocalFree` at `0x180077df4`
- `KERNEL32!LocalFree` at `0x180077df4`
- `Secur32!GetComputerObjectNameW` at `0x180077d7e`
- `Secur32!GetComputerObjectNameW` at `0x180077dbd`
- `Secur32!GetComputerObjectNameW` at `0x180077d7e`
- `Secur32!GetComputerObjectNameW` at `0x180077dbd`

## pseudocode

```c
__int64 __fastcall GetLocalSystemAccount(HLOCAL *a1)
{
  unsigned int v2; // ebx
  unsigned __int16 *v3; // rax
  signed int LastError; // eax
  ULONG nSize; // [rsp+30h] [rbp+8h] BYREF

  nSize = 0;
  v2 = 0;
  GetComputerObjectNameW(NameSamCompatible, 0, &nSize);
  v3 = (unsigned __int16 *)LocalAlloc(0, 2LL * (nSize + 1));
  *a1 = v3;
  if ( !v3 )
  {
    v2 = -2147024882;
LABEL_7:
    if ( *a1 )
    {
      LocalFree(*a1);
      *a1 = 0;
    }
    return v2;
  }
  if ( !GetComputerObjectNameW(NameSamCompatible, v3, &nSize) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 )
      goto LABEL_7;
  }
  return v2;
}

```

## disassembly

```asm
0x180077d60  mov     [rsp+arg_8], rbx
0x180077d65  push    rdi
0x180077d66  sub     rsp, 20h
0x180077d6a  and     [rsp+28h+nSize], 0
0x180077d6f  lea     r8, [rsp+28h+nSize]; nSize
0x180077d74  mov     rdi, rcx
0x180077d77  xor     ebx, ebx
0x180077d79  xor     edx, edx; lpNameBuffer
0x180077d7b  lea     ecx, [rbx+2]; NameFormat
0x180077d7e  call    cs:__imp_GetComputerObjectNameW
0x180077d85  nop     dword ptr [rax+rax+00h]
0x180077d8a  mov     edx, [rsp+28h+nSize]
0x180077d8e  xor     ecx, ecx; uFlags
0x180077d90  inc     edx
0x180077d92  add     rdx, rdx; uBytes
0x180077d95  call    cs:__imp_LocalAlloc
0x180077d9c  nop     dword ptr [rax+rax+00h]
0x180077da1  mov     [rdi], rax
0x180077da4  test    rax, rax
0x180077da7  jnz     short loc_180077DB0
0x180077da9  mov     ebx, 8007000Eh
0x180077dae  jmp     short loc_180077DEC
0x180077db0  lea     r8, [rsp+28h+nSize]; nSize
0x180077db5  mov     rdx, rax; lpNameBuffer
0x180077db8  mov     ecx, 2; NameFormat
0x180077dbd  call    cs:__imp_GetComputerObjectNameW
0x180077dc4  nop     dword ptr [rax+rax+00h]
0x180077dc9  test    al, al
0x180077dcb  jnz     short loc_180077E04
0x180077dcd  call    cs:__imp_GetLastError
0x180077dd4  nop     dword ptr [rax+rax+00h]
0x180077dd9  mov     ebx, eax
0x180077ddb  test    eax, eax
0x180077ddd  jle     short loc_180077DE8
0x180077ddf  movzx   ebx, ax
0x180077de2  or      ebx, 80070000h
0x180077de8  test    ebx, ebx
0x180077dea  jz      short loc_180077E04
0x180077dec  mov     rcx, [rdi]; hMem
0x180077def  test    rcx, rcx
0x180077df2  jz      short loc_180077E04
0x180077df4  call    cs:__imp_LocalFree
0x180077dfb  nop     dword ptr [rax+rax+00h]
0x180077e00  and     qword ptr [rdi], 0
0x180077e04  mov     eax, ebx
0x180077e06  mov     rbx, [rsp+28h+arg_8]
0x180077e0b  add     rsp, 20h
0x180077e0f  pop     rdi
0x180077e10  retn
```
