# QueryServiceConfigWithAlloc

- ea: `0x1800036f8`
- end: `0x180003883`
- name: `QueryServiceConfigWithAlloc`
- size: `395`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct _QUERY_SERVICE_CONFIGW **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002fc4`

## callees

- `0x1800036f8`
- `0x1800048f6`
- `0x180005010`

## import_xrefs

- `ADVAPI32!QueryServiceConfigW` at `0x180003788`
- `ADVAPI32!QueryServiceConfigW` at `0x180003827`
- `ADVAPI32!QueryServiceConfigW` at `0x180003788`
- `ADVAPI32!QueryServiceConfigW` at `0x180003827`
- `KERNEL32!GetLastError` at `0x180003796`
- `KERNEL32!GetLastError` at `0x180003841`
- `KERNEL32!GetLastError` at `0x180003796`
- `KERNEL32!GetLastError` at `0x180003841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800037ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800037ad`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180003737`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800037cc`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180003737`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800037cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003863`

## pseudocode

```c
__int64 __fastcall QueryServiceConfigWithAlloc(SC_HANDLE hService, struct _QUERY_SERVICE_CONFIGW **a2)
{
  struct _QUERY_SERVICE_CONFIGW *v4; // rdi
  size_t v5; // rbx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rsi
  signed int v8; // ebx
  signed int LastError; // eax
  LPMALLOC ppMalloc; // [rsp+60h] [rbp+40h] BYREF
  LPMALLOC v12; // [rsp+68h] [rbp+48h] BYREF

  v4 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemAlloc(0x2C0u);
  if ( !v4 )
    return (unsigned int)-2147024882;
  v5 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(LPMALLOC, struct _QUERY_SERVICE_CONFIGW *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v4);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(v4, 0, v5);
  LODWORD(ppMalloc) = 0;
  if ( !QueryServiceConfigW(hService, v4, 0x2C0u, (LPDWORD)&ppMalloc) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_13;
    v6 = (unsigned int)ppMalloc;
    v4 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemRealloc(v4, (unsigned int)ppMalloc);
    if ( !v4 )
    {
      v8 = -2147024882;
      goto LABEL_17;
    }
    v12 = 0;
    if ( CoGetMalloc(1u, &v12) >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(LPMALLOC, struct _QUERY_SERVICE_CONFIGW *))v12->lpVtbl->GetSize)(v12, v4);
      ((void (__fastcall *)(LPMALLOC))v12->lpVtbl->Release)(v12);
      if ( v7 > v6 )
        memset_0((char *)v4 + v6, 0, v7 - v6);
    }
    LODWORD(v12) = 0;
    if ( !QueryServiceConfigW(hService, v4, (DWORD)ppMalloc, (LPDWORD)&v12) )
    {
LABEL_13:
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      goto LABEL_17;
    }
  }
  v8 = 0;
  *a2 = v4;
  v4 = 0;
LABEL_17:
  CoTaskMemFree(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800036f8  mov     [rsp-28h+arg_0], rbx
0x1800036fd  push    rbp
0x1800036fe  push    rsi
0x1800036ff  push    rdi
0x180003700  push    r14
0x180003702  push    r15
0x180003704  mov     rbp, rsp
0x180003707  sub     rsp, 20h
0x18000370b  mov     r14, rcx
0x18000370e  mov     esi, 2C0h
0x180003713  mov     ecx, esi; cb
0x180003715  mov     r15, rdx
0x180003718  call    cs:__imp_CoTaskMemAlloc
0x18000371e  mov     rdi, rax
0x180003721  test    rax, rax
0x180003724  jz      loc_18000386B
0x18000372a  xor     ebx, ebx
0x18000372c  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x180003730  mov     [rbp+ppMalloc], rbx
0x180003734  lea     ecx, [rbx+1]; dwMemContext
0x180003737  call    cs:__imp_CoGetMalloc
0x18000373d  test    eax, eax
0x18000373f  js      short loc_180003767
0x180003741  mov     rcx, [rbp+ppMalloc]
0x180003745  mov     rdx, rdi
0x180003748  mov     rax, [rcx]
0x18000374b  mov     rax, [rax+30h]
0x18000374f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003754  mov     rcx, [rbp+ppMalloc]
0x180003758  mov     rbx, rax
0x18000375b  mov     rdx, [rcx]
0x18000375e  mov     rax, [rdx+10h]
0x180003762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003767  mov     r8, rbx; Size
0x18000376a  xor     edx, edx; Val
0x18000376c  mov     rcx, rdi; void *
0x18000376f  call    memset_0
0x180003774  lea     r9, [rbp+ppMalloc]; pcbBytesNeeded
0x180003778  mov     dword ptr [rbp+ppMalloc], 0
0x18000377f  mov     r8d, esi; cbBufSize
0x180003782  mov     rdx, rdi; lpServiceConfig
0x180003785  mov     rcx, r14; hService
0x180003788  call    cs:__imp_QueryServiceConfigW
0x18000378e  test    eax, eax
0x180003790  jnz     loc_180003831
0x180003796  call    cs:__imp_GetLastError
0x18000379c  cmp     eax, 7Ah ; 'z'
0x18000379f  jnz     loc_180003841
0x1800037a5  mov     ebx, dword ptr [rbp+ppMalloc]
0x1800037a8  mov     rcx, rdi; pv
0x1800037ab  mov     edx, ebx; cb
0x1800037ad  call    cs:__imp_CoTaskMemRealloc
0x1800037b3  mov     rdi, rax
0x1800037b6  test    rax, rax
0x1800037b9  jz      short loc_18000383A
0x1800037bb  lea     rdx, [rbp+arg_18]; ppMalloc
0x1800037bf  mov     [rbp+arg_18], 0
0x1800037c7  mov     ecx, 1; dwMemContext
0x1800037cc  call    cs:__imp_CoGetMalloc
0x1800037d2  test    eax, eax
0x1800037d4  js      short loc_180003812
0x1800037d6  mov     rcx, [rbp+arg_18]
0x1800037da  mov     rdx, rdi
0x1800037dd  mov     rax, [rcx]
0x1800037e0  mov     rax, [rax+30h]
0x1800037e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e9  mov     rcx, [rbp+arg_18]
0x1800037ed  mov     rsi, rax
0x1800037f0  mov     rdx, [rcx]
0x1800037f3  mov     rax, [rdx+10h]
0x1800037f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fc  cmp     rsi, rbx
0x1800037ff  jbe     short loc_180003812
0x180003801  sub     rsi, rbx
0x180003804  lea     rcx, [rbx+rdi]; void *
0x180003808  mov     r8, rsi; Size
0x18000380b  xor     edx, edx; Val
0x18000380d  call    memset_0
0x180003812  mov     r8d, dword ptr [rbp+ppMalloc]; cbBufSize
0x180003816  lea     r9, [rbp+arg_18]; pcbBytesNeeded
0x18000381a  mov     rdx, rdi; lpServiceConfig
0x18000381d  mov     dword ptr [rbp+arg_18], 0
0x180003824  mov     rcx, r14; hService
0x180003827  call    cs:__imp_QueryServiceConfigW
0x18000382d  test    eax, eax
0x18000382f  jz      short loc_180003841
0x180003831  xor     ebx, ebx
0x180003833  mov     [r15], rdi
0x180003836  xor     edi, edi
0x180003838  jmp     short loc_180003860
0x18000383a  mov     ebx, 8007000Eh
0x18000383f  jmp     short loc_180003860
0x180003841  call    cs:__imp_GetLastError
0x180003847  mov     ebx, eax
0x180003849  test    eax, eax
0x18000384b  jle     short loc_180003856
0x18000384d  movzx   ebx, ax
0x180003850  or      ebx, 80070000h
0x180003856  test    ebx, ebx
0x180003858  mov     eax, 80004005h
0x18000385d  cmovns  ebx, eax
0x180003860  mov     rcx, rdi; pv
0x180003863  call    cs:__imp_CoTaskMemFree
0x180003869  jmp     short loc_180003870
0x18000386b  mov     ebx, 8007000Eh
0x180003870  mov     eax, ebx
0x180003872  mov     rbx, [rsp+20h+arg_0]
0x180003877  add     rsp, 20h
0x18000387b  pop     r15
0x18000387d  pop     r14
0x18000387f  pop     rdi
0x180003880  pop     rsi
0x180003881  pop     rbp
0x180003882  retn
```
