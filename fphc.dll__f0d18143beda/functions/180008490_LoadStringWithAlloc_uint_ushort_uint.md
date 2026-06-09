# LoadStringWithAlloc(uint,ushort * *,uint)

- ea: `0x180008490`
- end: `0x180008507`
- name: `?LoadStringWithAlloc@@YAJIPEAPEAGI@Z`
- size: `119`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006970`
- `0x180008130`

## callees

- `0x180008490`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800084cd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800084cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800084a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800084a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084d7`

## pseudocode

```c
__int64 __fastcall LoadStringWithAlloc(UINT uID, LPVOID *a2, unsigned int a3)
{
  unsigned __int16 *v6; // rax
  unsigned int v8; // ebx
  signed int LastError; // eax

  v6 = (unsigned __int16 *)CoTaskMemAlloc(2LL * a3);
  *a2 = v6;
  if ( !v6 )
    return 2147942414LL;
  v8 = 0;
  if ( !LoadStringW(lpSource, uID, v6, a3) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180008490  push    rbx
0x180008492  push    rbp
0x180008493  push    rsi
0x180008494  push    rdi
0x180008495  sub     rsp, 28h
0x180008499  mov     ebp, ecx
0x18000849b  mov     esi, r8d
0x18000849e  mov     ecx, r8d
0x1800084a1  mov     rdi, rdx
0x1800084a4  add     rcx, rcx; cb
0x1800084a7  call    cs:__imp_CoTaskMemAlloc
0x1800084ad  mov     [rdi], rax
0x1800084b0  test    rax, rax
0x1800084b3  jnz     short loc_1800084BC
0x1800084b5  mov     eax, 8007000Eh
0x1800084ba  jmp     short loc_1800084FE
0x1800084bc  mov     rcx, cs:lpSource; hInstance
0x1800084c3  mov     r9d, esi; cchBufferMax
0x1800084c6  mov     r8, rax; lpBuffer
0x1800084c9  mov     edx, ebp; uID
0x1800084cb  xor     ebx, ebx
0x1800084cd  call    cs:__imp_LoadStringW
0x1800084d3  test    eax, eax
0x1800084d5  jnz     short loc_1800084FC
0x1800084d7  call    cs:__imp_GetLastError
0x1800084dd  mov     ebx, eax
0x1800084df  test    eax, eax
0x1800084e1  jle     short loc_1800084EC
0x1800084e3  movzx   ebx, ax
0x1800084e6  or      ebx, 80070000h
0x1800084ec  mov     rcx, [rdi]; pv
0x1800084ef  call    cs:__imp_CoTaskMemFree
0x1800084f5  mov     qword ptr [rdi], 0
0x1800084fc  mov     eax, ebx
0x1800084fe  add     rsp, 28h
0x180008502  pop     rdi
0x180008503  pop     rsi
0x180008504  pop     rbp
0x180008505  pop     rbx
0x180008506  retn
```
