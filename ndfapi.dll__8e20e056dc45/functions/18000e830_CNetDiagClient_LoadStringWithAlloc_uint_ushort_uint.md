# CNetDiagClient::LoadStringWithAlloc(uint,ushort * *,uint)

- ea: `0x18000e830`
- end: `0x18000e8b3`
- name: `?LoadStringWithAlloc@CNetDiagClient@@IEAAJIPEAPEAGI@Z`
- size: `131`
- prototype: `__int64 __fastcall(CNetDiagClient *this, UINT, LPVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180019af8`

## callees

- `0x18000e830`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e87c`
- `KERNEL32!GetLastError` at `0x18000e87c`
- `USER32!LoadStringW` at `0x18000e872`
- `USER32!LoadStringW` at `0x18000e872`
- `ole32!CoTaskMemAlloc` at `0x18000e849`
- `ole32!CoTaskMemAlloc` at `0x18000e849`
- `ole32!CoTaskMemFree` at `0x18000e894`
- `ole32!CoTaskMemFree` at `0x18000e894`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::LoadStringWithAlloc(CNetDiagClient *this, UINT a2, LPVOID *a3)
{
  unsigned __int16 *v5; // rax
  unsigned int v7; // ebx
  signed int LastError; // eax

  v5 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  *a3 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  if ( !LoadStringW(hInstance, a2, v5, 1024) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    CoTaskMemFree(*a3);
    *a3 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000e830  mov     [rsp+arg_0], rbx
0x18000e835  mov     [rsp+arg_8], rsi
0x18000e83a  push    rdi
0x18000e83b  sub     rsp, 20h
0x18000e83f  mov     ecx, 800h; cb
0x18000e844  mov     rdi, r8
0x18000e847  mov     esi, edx
0x18000e849  call    cs:__imp_CoTaskMemAlloc
0x18000e84f  mov     [rdi], rax
0x18000e852  test    rax, rax
0x18000e855  jnz     short loc_18000E85E
0x18000e857  mov     eax, 8007000Eh
0x18000e85c  jmp     short loc_18000E8A3
0x18000e85e  mov     rcx, cs:hInstance; hInstance
0x18000e865  mov     r9d, 400h; cchBufferMax
0x18000e86b  mov     r8, rax; lpBuffer
0x18000e86e  mov     edx, esi; uID
0x18000e870  xor     ebx, ebx
0x18000e872  call    cs:__imp_LoadStringW
0x18000e878  test    eax, eax
0x18000e87a  jnz     short loc_18000E8A1
0x18000e87c  call    cs:__imp_GetLastError
0x18000e882  mov     ebx, eax
0x18000e884  test    eax, eax
0x18000e886  jle     short loc_18000E891
0x18000e888  movzx   ebx, ax
0x18000e88b  or      ebx, 80070000h
0x18000e891  mov     rcx, [rdi]; pv
0x18000e894  call    cs:__imp_CoTaskMemFree
0x18000e89a  mov     qword ptr [rdi], 0
0x18000e8a1  mov     eax, ebx
0x18000e8a3  mov     rbx, [rsp+28h+arg_0]
0x18000e8a8  mov     rsi, [rsp+28h+arg_8]
0x18000e8ad  add     rsp, 20h
0x18000e8b1  pop     rdi
0x18000e8b2  retn
```
