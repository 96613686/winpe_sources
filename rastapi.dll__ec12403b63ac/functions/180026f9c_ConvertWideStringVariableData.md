# ConvertWideStringVariableData

- ea: `0x180026f9c`
- end: `0x180027139`
- name: `ConvertWideStringVariableData`
- size: `413`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800240a8`
- `0x1800244ec`
- `0x180024e60`

## callees

- `0x180026f9c`
- `0x180029266`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800270d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800270d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800270c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800270c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027093`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027093`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180027023`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180027067`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180027023`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180027067`
- `rtutils!TracePrintfA` at `0x18002712e`
- `rtutils!TracePrintfA` at `0x18002712e`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180026fed`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180027039`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180026fed`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180027039`

## pseudocode

```c
void __fastcall ConvertWideStringVariableData(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rdx
  WCHAR *v5; // r14
  int v6; // ebx
  UINT ACP; // eax
  unsigned int v8; // eax
  size_t cbMultiByte; // rbp
  CHAR *lpMultiByteStr; // rsi
  UINT v11; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  bool v14; // zf
  CHAR MultiByteStr[64]; // [rsp+40h] [rbp-78h] BYREF

  v2 = *a2;
  if ( !*a2 )
    return;
  v4 = a2[1];
  if ( *(_DWORD *)(a1 + 8) <= (unsigned int)v4 )
    return;
  v5 = (WCHAR *)(a1 + v4);
  if ( *(_DWORD *)(a1 + 8) < (unsigned int)v4 + v2 )
    v2 = *(_DWORD *)(a1 + 8) - v4;
  v6 = v2 >> 1;
  ACP = GetACP();
  v8 = WideCharToMultiByte(ACP, 0x400u, v5, v6, 0, 0, 0, 0);
  cbMultiByte = v8;
  if ( v8 <= 0x40 )
  {
    lpMultiByteStr = MultiByteStr;
LABEL_7:
    v11 = GetACP();
    WideCharToMultiByte(v11, 0x400u, v5, v6, lpMultiByteStr, cbMultiByte, 0, 0);
    memcpy_0(v5, lpMultiByteStr, cbMultiByte);
    if ( lpMultiByteStr != MultiByteStr )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMultiByteStr);
    }
    *a2 = cbMultiByte;
    return;
  }
  v13 = GetProcessHeap();
  lpMultiByteStr = (CHAR *)HeapAlloc(v13, 8u, cbMultiByte);
  if ( lpMultiByteStr )
    goto LABEL_7;
  v14 = gIsndpspEtwTracingAvailable == 0;
  *(_QWORD *)a2 = 0;
  if ( v14 )
  {
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "ConvertWideStringVariableData: Failed to allocate memory");
  }
  else if ( qword_18003EC48 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
      gNdpspEtwContext,
      qword_18003EC48,
      L"ConvertWideStringVariableData: Failed to allocate memory");
  }
}

```

## disassembly

```asm
0x180026f9c  mov     [rsp+arg_10], rbx
0x180026fa1  push    rbp
0x180026fa2  push    rsi
0x180026fa3  push    rdi
0x180026fa4  push    r14
0x180026fa6  push    r15
0x180026fa8  sub     rsp, 90h
0x180026faf  mov     rax, cs:__security_cookie
0x180026fb6  xor     rax, rsp
0x180026fb9  mov     [rsp+0B8h+var_38], rax
0x180026fc1  mov     ebx, [rdx]
0x180026fc3  mov     rdi, rdx
0x180026fc6  test    ebx, ebx
0x180026fc8  jz      loc_18002709B
0x180026fce  mov     edx, [rdx+4]
0x180026fd1  cmp     [rcx+8], edx
0x180026fd4  jbe     loc_18002709B
0x180026fda  lea     eax, [rdx+rbx]
0x180026fdd  lea     r14, [rcx+rdx]
0x180026fe1  cmp     [rcx+8], eax
0x180026fe4  jnb     short loc_180026FEB
0x180026fe6  mov     ebx, [rcx+8]
0x180026fe9  sub     ebx, edx
0x180026feb  shr     ebx, 1
0x180026fed  call    cs:__imp_GetACP
0x180026ff3  mov     [rsp+0B8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180026ffc  mov     r9d, ebx; cchWideChar
0x180026fff  mov     [rsp+0B8h+lpDefaultChar], 0; lpDefaultChar
0x180027008  mov     ecx, eax; CodePage
0x18002700a  mov     [rsp+0B8h+cbMultiByte], 0; cbMultiByte
0x180027012  mov     r8, r14; lpWideCharStr
0x180027015  mov     edx, 400h; dwFlags
0x18002701a  mov     [rsp+0B8h+lpMultiByteStr], 0; lpMultiByteStr
0x180027023  call    cs:__imp_WideCharToMultiByte
0x180027029  mov     ebp, eax
0x18002702b  cmp     eax, 40h ; '@'
0x18002702e  ja      loc_1800270C2
0x180027034  lea     rsi, [rsp+0B8h+MultiByteStr]
0x180027039  call    cs:__imp_GetACP
0x18002703f  mov     [rsp+0B8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180027048  mov     r9d, ebx; cchWideChar
0x18002704b  mov     [rsp+0B8h+lpDefaultChar], 0; lpDefaultChar
0x180027054  mov     ecx, eax; CodePage
0x180027056  mov     [rsp+0B8h+cbMultiByte], ebp; cbMultiByte
0x18002705a  mov     r8, r14; lpWideCharStr
0x18002705d  mov     edx, 400h; dwFlags
0x180027062  mov     [rsp+0B8h+lpMultiByteStr], rsi; lpMultiByteStr
0x180027067  call    cs:__imp_WideCharToMultiByte
0x18002706d  mov     r8, rbp; Size
0x180027070  mov     rdx, rsi; Src
0x180027073  mov     rcx, r14; void *
0x180027076  call    memcpy_0
0x18002707b  lea     rax, [rsp+0B8h+MultiByteStr]
0x180027080  cmp     rsi, rax
0x180027083  jz      short loc_180027099
0x180027085  call    cs:__imp_GetProcessHeap
0x18002708b  mov     r8, rsi; lpMem
0x18002708e  xor     edx, edx; dwFlags
0x180027090  mov     rcx, rax; hHeap
0x180027093  call    cs:__imp_HeapFree
0x180027099  mov     [rdi], ebp
0x18002709b  mov     rcx, [rsp+0B8h+var_38]
0x1800270a3  xor     rcx, rsp; StackCookie
0x1800270a6  call    __security_check_cookie
0x1800270ab  mov     rbx, [rsp+0B8h+arg_10]
0x1800270b3  add     rsp, 90h
0x1800270ba  pop     r15
0x1800270bc  pop     r14
0x1800270be  pop     rdi
0x1800270bf  pop     rsi
0x1800270c0  pop     rbp
0x1800270c1  retn
0x1800270c2  call    cs:__imp_GetProcessHeap
0x1800270c8  mov     r8, rbp; dwBytes
0x1800270cb  mov     edx, 8; dwFlags
0x1800270d0  mov     rcx, rax; hHeap
0x1800270d3  call    cs:__imp_HeapAlloc
0x1800270d9  mov     rsi, rax
0x1800270dc  test    rax, rax
0x1800270df  jnz     loc_180027039
0x1800270e5  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x1800270eb  mov     [rdi], rax
0x1800270ee  jz      short loc_180027118
0x1800270f0  mov     rdx, cs:qword_18003EC48
0x1800270f7  test    rdx, rdx
0x1800270fa  jz      short loc_18002709B
0x1800270fc  mov     rcx, cs:gNdpspEtwContext
0x180027103  lea     r8, aConvertwidestr; "ConvertWideStringVariableData: Failed t"...
0x18002710a  mov     rax, cs:gNdpspTemplateFunc
0x180027111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027116  jmp     short loc_18002709B
0x180027118  mov     ecx, cs:dwTraceId; dwTraceID
0x18002711e  cmp     ecx, 0FFFFFFFFh
0x180027121  jz      loc_18002709B
0x180027127  lea     rdx, aConvertwidestr_0; "ConvertWideStringVariableData: Failed t"...
0x18002712e  call    cs:__imp_TracePrintfA
0x180027134  jmp     loc_18002709B
```
