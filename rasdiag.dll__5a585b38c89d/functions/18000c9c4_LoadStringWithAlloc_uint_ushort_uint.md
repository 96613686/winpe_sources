# LoadStringWithAlloc(uint,ushort * *,uint)

- ea: `0x18000c9c4`
- end: `0x18000ca83`
- name: `?LoadStringWithAlloc@@YAJIPEAPEAGI@Z`
- size: `191`
- prototype: `__int64 __fastcall(UINT uID, LPVOID *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007828`

## callees

- `0x18000c9c4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c9fd`
- `KERNEL32!SetLastError` at `0x18000c9fd`
- `KERNEL32!GetLastError` at `0x18000ca38`
- `KERNEL32!GetLastError` at `0x18000ca38`
- `USER32!LoadStringW` at `0x18000ca28`
- `USER32!LoadStringW` at `0x18000ca28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ca5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ca5b`

## pseudocode

```c
__int64 __fastcall LoadStringWithAlloc(UINT uID, LPVOID *a2, unsigned int a3)
{
  unsigned __int16 *v6; // rax
  __int64 result; // rax
  unsigned int v8; // ebx
  signed int LastError; // eax

  if ( !a2 )
    return 2147942487LL;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2LL * a3);
  if ( v6 )
  {
    *a2 = v6;
    v8 = 0;
    if ( !LoadStringW(hInstance, uID, v6, a3) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( *a2 )
        CoTaskMemFree(*a2);
      *a2 = 0;
    }
    return v8;
  }
  else
  {
    SetLastError(8u);
    result = 2147942414LL;
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c9c4  push    rbx
0x18000c9c6  push    rbp
0x18000c9c7  push    rsi
0x18000c9c8  push    rdi
0x18000c9c9  push    r14
0x18000c9cb  sub     rsp, 20h
0x18000c9cf  mov     ebp, r8d
0x18000c9d2  mov     rdi, rdx
0x18000c9d5  mov     r14d, ecx
0x18000c9d8  test    rdx, rdx
0x18000c9db  jz      loc_18000CA72
0x18000c9e1  mov     ecx, ebp
0x18000c9e3  add     rcx, rcx; cb
0x18000c9e6  call    cs:__imp_CoTaskMemAlloc
0x18000c9ed  nop     dword ptr [rax+rax+00h]
0x18000c9f2  mov     rsi, rax
0x18000c9f5  test    rax, rax
0x18000c9f8  jnz     short loc_18000CA13
0x18000c9fa  lea     ecx, [rax+8]; dwErrCode
0x18000c9fd  call    cs:__imp_SetLastError
0x18000ca04  nop     dword ptr [rax+rax+00h]
0x18000ca09  mov     eax, 8007000Eh
0x18000ca0e  mov     [rdi], rsi
0x18000ca11  jmp     short loc_18000CA77
0x18000ca13  mov     [rdi], rsi
0x18000ca16  mov     r9d, ebp; cchBufferMax
0x18000ca19  mov     rcx, cs:hInstance; hInstance
0x18000ca20  mov     r8, rsi; lpBuffer
0x18000ca23  mov     edx, r14d; uID
0x18000ca26  xor     ebx, ebx
0x18000ca28  call    cs:__imp_LoadStringW
0x18000ca2f  nop     dword ptr [rax+rax+00h]
0x18000ca34  test    eax, eax
0x18000ca36  jnz     short loc_18000CA6E
0x18000ca38  call    cs:__imp_GetLastError
0x18000ca3f  nop     dword ptr [rax+rax+00h]
0x18000ca44  mov     ebx, eax
0x18000ca46  test    eax, eax
0x18000ca48  jle     short loc_18000CA53
0x18000ca4a  movzx   ebx, ax
0x18000ca4d  or      ebx, 80070000h
0x18000ca53  mov     rcx, [rdi]; pv
0x18000ca56  test    rcx, rcx
0x18000ca59  jz      short loc_18000CA67
0x18000ca5b  call    cs:__imp_CoTaskMemFree
0x18000ca62  nop     dword ptr [rax+rax+00h]
0x18000ca67  mov     qword ptr [rdi], 0
0x18000ca6e  mov     eax, ebx
0x18000ca70  jmp     short loc_18000CA77
0x18000ca72  mov     eax, 80070057h
0x18000ca77  add     rsp, 20h
0x18000ca7b  pop     r14
0x18000ca7d  pop     rdi
0x18000ca7e  pop     rsi
0x18000ca7f  pop     rbp
0x18000ca80  pop     rbx
0x18000ca81  retn
```
