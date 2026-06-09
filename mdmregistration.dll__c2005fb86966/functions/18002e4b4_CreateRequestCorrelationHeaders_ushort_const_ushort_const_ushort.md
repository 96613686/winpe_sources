# CreateRequestCorrelationHeaders(ushort const *,ushort const *,ushort * * *)

- ea: `0x18002e4b4`
- end: `0x18002e6f1`
- name: `?CreateRequestCorrelationHeaders@@YAJPEBG0PEAPEAPEAG@Z`
- size: `573`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001f594`
- `0x180021458`

## callees

- `0x18000b0f4`
- `0x180019814`
- `0x180021dd4`
- `0x18002e4b4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e569`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e5d3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e569`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e5d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e504`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e5a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e616`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e504`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e5a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e4e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e593`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e5ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e4e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e593`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e5ff`

## string_xrefs

- `0x18002e51c`: `onecoreuap\admin\enterprisemgmt\enrollactivities\lib\mmpjsonparser.cpp`
- `0x18002e6ba`: `onecoreuap\admin\enterprisemgmt\enrollactivities\lib\mmpjsonparser.cpp`

## pseudocode

```c
__int64 __fastcall CreateRequestCorrelationHeaders(wchar_t *Source, wchar_t *a2, unsigned __int16 ***a3)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 **v7; // rdi
  unsigned int v8; // ebx
  size_t v10; // rax
  SIZE_T v11; // r12
  HANDLE v12; // rax
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  size_t v15; // rax
  SIZE_T v16; // r15
  HANDLE v17; // rax
  unsigned __int16 *v18; // rax
  int v19; // eax
  unsigned __int64 v20; // r9
  int v21; // eax
  unsigned __int16 **v22; // [rsp+20h] [rbp-10h] BYREF
  __int64 v23; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]

  if ( !a2 || !Source )
    return 2147942487LL;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v7 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\mmpjsonparser.cpp",
      (const char *)0x8007000ELL,
      (int)v22);
    return v8;
  }
  v22 = 0;
  v23 = 0;
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<int (*)(void *),&int SafeHeapFree(void *)>,wil::function_deleter<int (*)(void *),&int SafeHeapFree(void *)>,unsigned __int64>::reset(&v22);
  v22 = v7;
  v23 = 2;
  v10 = wcsnlen(a2, 0x81u);
  v11 = 2 * (v10 + 10);
  if ( !is_mul_ok(v10 + 10, 2u) )
  {
    v14 = 128;
    goto LABEL_19;
  }
  v12 = GetProcessHeap();
  v13 = (unsigned __int16 *)HeapAlloc(v12, 8u, v11);
  *v7 = v13;
  if ( !v13 )
  {
    v8 = -2147024882;
    v14 = 130;
LABEL_20:
    v20 = v8;
    goto LABEL_21;
  }
  v15 = wcsnlen(Source, 0x27u);
  v16 = 2 * (v15 + 22);
  if ( !is_mul_ok(v15 + 22, 2u) )
  {
    v14 = 133;
LABEL_19:
    v8 = -2147024362;
    goto LABEL_20;
  }
  v17 = GetProcessHeap();
  v18 = (unsigned __int16 *)HeapAlloc(v17, 8u, v16);
  v7[1] = v18;
  if ( !v18 )
  {
    v8 = -2147024882;
    v14 = 135;
    goto LABEL_20;
  }
  v19 = StringCbPrintfW(*v7, v11, L"MS-CV: %s", a2);
  v8 = v19;
  if ( v19 < 0 )
  {
    v20 = (unsigned int)v19;
    v14 = 141;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\mmpjsonparser.cpp",
      (const char *)v20,
      (int)v22);
    wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<int (*)(void *),&int SafeHeapFree(void *)>,wil::function_deleter<int (*)(void *),&int SafeHeapFree(void *)>,unsigned __int64>::reset(&v22);
    return v8;
  }
  v21 = StringCbPrintfW(v7[1], v16, L"client-request-id: %s", Source);
  v8 = v21;
  if ( v21 < 0 )
  {
    v20 = (unsigned int)v21;
    v14 = 147;
    goto LABEL_21;
  }
  v22 = 0;
  v23 = 0;
  *a3 = v7;
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<int (*)(void *),&int SafeHeapFree(void *)>,wil::function_deleter<int (*)(void *),&int SafeHeapFree(void *)>,unsigned __int64>::reset(&v22);
  return 0;
}

```

## disassembly

```asm
0x18002e4b4  mov     [rsp-28h+arg_0], rbx
0x18002e4b9  mov     [rsp-28h+arg_10], rsi
0x18002e4be  push    rbp
0x18002e4bf  push    rdi
0x18002e4c0  push    r12
0x18002e4c2  push    r14
0x18002e4c4  push    r15
0x18002e4c6  mov     rbp, rsp
0x18002e4c9  sub     rsp, 30h
0x18002e4cd  mov     r14, r8
0x18002e4d0  mov     rbx, rdx
0x18002e4d3  mov     rsi, rcx
0x18002e4d6  test    rdx, rdx
0x18002e4d9  jz      loc_18002E6D4
0x18002e4df  test    rcx, rcx
0x18002e4e2  jz      loc_18002E6D4
0x18002e4e8  call    cs:__imp_GetProcessHeap
0x18002e4ef  nop     dword ptr [rax+rax+00h]
0x18002e4f4  mov     r8d, 10h; dwBytes
0x18002e4fa  mov     rcx, rax; hHeap
0x18002e4fd  lea     r15d, [r8-8]
0x18002e501  mov     edx, r15d; dwFlags
0x18002e504  call    cs:__imp_HeapAlloc
0x18002e50b  nop     dword ptr [rax+rax+00h]
0x18002e510  mov     rdi, rax
0x18002e513  test    rax, rax
0x18002e516  jnz     short loc_18002E53A
0x18002e518  mov     rcx, [rbp+28h]; this
0x18002e51c  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002e523  mov     ebx, 8007000Eh
0x18002e528  lea     edx, [rax+7Ah]; void *
0x18002e52b  mov     r9d, ebx; char *
0x18002e52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e533  mov     eax, ebx
0x18002e535  jmp     loc_18002E6D9
0x18002e53a  lea     rcx, [rbp+var_10]
0x18002e53e  mov     [rbp+var_10], 0
0x18002e546  mov     [rbp+var_8], 0
0x18002e54e  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@Z@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<int (*)(void *),&SafeHeapFree(void *)>,wil::function_deleter<int (*)(void *),&SafeHeapFree(void *)>,unsigned __int64>::reset(void)
0x18002e553  mov     r12d, 2
0x18002e559  mov     [rbp+var_10], rdi
0x18002e55d  mov     rcx, rbx; Source
0x18002e560  mov     [rbp+var_8], r12
0x18002e564  lea     edx, [r12+7Fh]; MaxCount
0x18002e569  call    cs:__imp_wcsnlen
0x18002e570  nop     dword ptr [rax+rax+00h]
0x18002e575  mov     [rbp+arg_8], 0
0x18002e57d  lea     rcx, [rax+0Ah]
0x18002e581  mov     eax, r12d
0x18002e584  mul     rcx
0x18002e587  mov     r12, rax
0x18002e58a  test    rdx, rdx
0x18002e58d  jnz     loc_18002E6A9
0x18002e593  call    cs:__imp_GetProcessHeap
0x18002e59a  nop     dword ptr [rax+rax+00h]
0x18002e59f  mov     r8, r12; dwBytes
0x18002e5a2  mov     edx, r15d; dwFlags
0x18002e5a5  mov     rcx, rax; hHeap
0x18002e5a8  call    cs:__imp_HeapAlloc
0x18002e5af  nop     dword ptr [rax+rax+00h]
0x18002e5b4  mov     [rdi], rax
0x18002e5b7  test    rax, rax
0x18002e5ba  jnz     short loc_18002E5CB
0x18002e5bc  mov     ebx, 8007000Eh
0x18002e5c1  mov     edx, 82h
0x18002e5c6  jmp     loc_18002E6B3
0x18002e5cb  mov     edx, 27h ; '''; MaxCount
0x18002e5d0  mov     rcx, rsi; Source
0x18002e5d3  call    cs:__imp_wcsnlen
0x18002e5da  nop     dword ptr [rax+rax+00h]
0x18002e5df  mov     [rbp+arg_8], 0
0x18002e5e7  lea     rcx, [rax+16h]
0x18002e5eb  mov     eax, 2
0x18002e5f0  mul     rcx
0x18002e5f3  mov     r15, rax
0x18002e5f6  test    rdx, rdx
0x18002e5f9  jnz     loc_18002E6A2
0x18002e5ff  call    cs:__imp_GetProcessHeap
0x18002e606  nop     dword ptr [rax+rax+00h]
0x18002e60b  mov     r8, r15; dwBytes
0x18002e60e  mov     edx, 8; dwFlags
0x18002e613  mov     rcx, rax; hHeap
0x18002e616  call    cs:__imp_HeapAlloc
0x18002e61d  nop     dword ptr [rax+rax+00h]
0x18002e622  mov     [rdi+8], rax
0x18002e626  test    rax, rax
0x18002e629  jnz     short loc_18002E637
0x18002e62b  mov     ebx, 8007000Eh
0x18002e630  mov     edx, 87h
0x18002e635  jmp     short loc_18002E6B3
0x18002e637  mov     rcx, [rdi]; unsigned __int16 *
0x18002e63a  lea     r8, aMsCvS; "MS-CV: %s"
0x18002e641  mov     r9, rbx
0x18002e644  mov     rdx, r12; unsigned __int64
0x18002e647  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e64c  mov     ebx, eax
0x18002e64e  test    eax, eax
0x18002e650  jns     short loc_18002E65C
0x18002e652  mov     r9d, eax
0x18002e655  mov     edx, 8Dh
0x18002e65a  jmp     short loc_18002E6B6
0x18002e65c  mov     rcx, [rdi+8]; unsigned __int16 *
0x18002e660  lea     r8, aClientRequestI; "client-request-id: %s"
0x18002e667  mov     r9, rsi
0x18002e66a  mov     rdx, r15; unsigned __int64
0x18002e66d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e672  mov     ebx, eax
0x18002e674  test    eax, eax
0x18002e676  jns     short loc_18002E682
0x18002e678  mov     r9d, eax
0x18002e67b  mov     edx, 93h
0x18002e680  jmp     short loc_18002E6B6
0x18002e682  lea     rcx, [rbp+var_10]
0x18002e686  mov     [rbp+var_10], 0
0x18002e68e  mov     [rbp+var_8], 0
0x18002e696  mov     [r14], rdi
0x18002e699  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@Z@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<int (*)(void *),&SafeHeapFree(void *)>,wil::function_deleter<int (*)(void *),&SafeHeapFree(void *)>,unsigned __int64>::reset(void)
0x18002e69e  xor     eax, eax
0x18002e6a0  jmp     short loc_18002E6D9
0x18002e6a2  mov     edx, 85h
0x18002e6a7  jmp     short loc_18002E6AE
0x18002e6a9  mov     edx, 80h; void *
0x18002e6ae  mov     ebx, 80070216h
0x18002e6b3  mov     r9d, ebx; char *
0x18002e6b6  mov     rcx, [rbp+28h]; this
0x18002e6ba  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002e6c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6c6  lea     rcx, [rbp+var_10]
0x18002e6ca  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@Z@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<int (*)(void *),&SafeHeapFree(void *)>,wil::function_deleter<int (*)(void *),&SafeHeapFree(void *)>,unsigned __int64>::reset(void)
0x18002e6cf  jmp     loc_18002E533
0x18002e6d4  mov     eax, 80070057h
0x18002e6d9  mov     rbx, [rsp+30h+arg_0]
0x18002e6de  mov     rsi, [rsp+30h+arg_10]
0x18002e6e3  add     rsp, 30h
0x18002e6e7  pop     r15
0x18002e6e9  pop     r14
0x18002e6eb  pop     r12
0x18002e6ed  pop     rdi
0x18002e6ee  pop     rbp
0x18002e6ef  retn
```
