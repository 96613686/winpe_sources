# FreeRoutingDomainConfiguration

- ea: `0x1800442f0`
- end: `0x1800444b4`
- name: `FreeRoutingDomainConfiguration`
- size: `452`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002690`
- `0x18000ad04`
- `0x180010e38`
- `0x180013580`
- `0x180043fbc`

## callees

- `0x180032c24`
- `0x180032c70`
- `0x180032cf4`
- `0x180033e60`
- `0x1800442f0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800443d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044464`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800443d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044464`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044483`
- `KERNEL32!GetProcessHeap` at `0x1800443c7`
- `KERNEL32!GetProcessHeap` at `0x180044456`
- `KERNEL32!GetProcessHeap` at `0x180044475`
- `KERNEL32!GetProcessHeap` at `0x1800443c7`
- `KERNEL32!GetProcessHeap` at `0x180044456`
- `KERNEL32!GetProcessHeap` at `0x180044475`

## string_xrefs

- `0x180044341`: `FreeRoutingDomainConfiguration`

## pseudocode

```c
__int64 __fastcall FreeRoutingDomainConfiguration(int a1, __int64 a2)
{
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  void *v10; // rbx
  HANDLE v11; // rax
  void *v12; // rcx
  __int64 v13; // rcx
  HANDLE v14; // rax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  _WORD v18[2]; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v19[2044]; // [rsp+24h] [rbp-814h] BYREF

  v18[1] = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( !a2 )
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      v18[0] = 0;
      FormatRRASErrorString(v18, L"%hs(Line#%d): Invalid parameter.", "FreeRoutingDomainConfiguration", 4990);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, _WORD *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        v18);
    }
    return 0;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v15 = *(void **)(a2 + 8);
    if ( !v15 )
      return 0;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
    goto LABEL_24;
  }
  v5 = v4 - 3;
  if ( !v5 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, (LPVOID)a2);
    return 0;
  }
  v6 = v5 - 4;
  if ( v6 )
  {
    v7 = v6 - 8;
    if ( v7 )
    {
      v8 = v7 - 16;
      if ( v8 )
      {
        v9 = v8 - 96;
        if ( v9 )
        {
          if ( v9 == 16256 )
          {
            v10 = *(void **)(a2 + 96);
            if ( v10 )
            {
              v11 = GetProcessHeap();
              HeapFree(v11, 0, v10);
              *(_QWORD *)(a2 + 96) = 0;
            }
          }
          return 0;
        }
      }
    }
    v12 = *(void **)(a2 + 8);
    if ( !v12 )
      return 0;
    MprCommonFree(v12);
LABEL_24:
    *(_QWORD *)(a2 + 8) = 0;
    return 0;
  }
  FreeEkus(*(LPVOID *)(a2 + 24));
  *(_DWORD *)(a2 + 20) = 0;
  if ( *(_DWORD *)(a2 + 32) )
    FreeCertificateBlob(a2 + 32, 0);
  v13 = *(_QWORD *)(a2 + 56);
  if ( v13 )
  {
    FreeCustomPolicy(v13);
    *(_QWORD *)(a2 + 56) = 0;
  }
  FreeEkus(*(LPVOID *)(a2 + 72));
  if ( *(_DWORD *)(a2 + 80) )
    FreeCertificateBlob(a2 + 80, 0);
  return 0;
}

```

## disassembly

```asm
0x1800442f0  mov     [rsp+arg_0], rbx
0x1800442f5  push    rdi
0x1800442f6  sub     rsp, 830h
0x1800442fd  mov     rax, cs:__security_cookie
0x180044304  xor     rax, rsp
0x180044307  mov     [rsp+838h+var_18], rax
0x18004430f  mov     rdi, rdx
0x180044312  mov     ebx, ecx
0x180044314  xor     eax, eax
0x180044316  lea     rcx, [rsp+838h+var_814]; void *
0x18004431b  xor     edx, edx; Val
0x18004431d  mov     [rsp+838h+var_816], ax
0x180044322  mov     r8d, 7FCh; Size
0x180044328  call    memset_0
0x18004432d  test    rdi, rdi
0x180044330  jnz     short loc_180044388
0x180044332  cmp     qword ptr cs:xmmword_180071090, rdi
0x180044339  jz      loc_180044491
0x18004433f  xor     eax, eax
0x180044341  lea     r8, aFreeroutingdom_1; "FreeRoutingDomainConfiguration"
0x180044348  mov     r9d, 137Eh
0x18004434e  mov     [rsp+838h+var_818], ax
0x180044353  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004435a  lea     rcx, [rsp+838h+var_818]
0x18004435f  call    FormatRRASErrorString
0x180044364  mov     rdx, qword ptr cs:xmmword_180071090
0x18004436b  lea     r8, [rsp+838h+var_818]
0x180044370  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044377  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004437e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044383  jmp     loc_180044491
0x180044388  sub     ebx, 1
0x18004438b  jz      loc_18004446C
0x180044391  sub     ebx, 3
0x180044394  jz      loc_180044456
0x18004439a  sub     ebx, 4
0x18004439d  jz      short loc_1800443FF
0x18004439f  sub     ebx, 8
0x1800443a2  jz      short loc_1800443E8
0x1800443a4  sub     ebx, 10h
0x1800443a7  jz      short loc_1800443E8
0x1800443a9  sub     ebx, 60h ; '`'
0x1800443ac  jz      short loc_1800443E8
0x1800443ae  cmp     ebx, 3F80h
0x1800443b4  jnz     loc_180044491
0x1800443ba  mov     rbx, [rdi+60h]
0x1800443be  test    rbx, rbx
0x1800443c1  jz      loc_180044491
0x1800443c7  call    cs:__imp_GetProcessHeap
0x1800443cd  mov     r8, rbx; lpMem
0x1800443d0  xor     edx, edx; dwFlags
0x1800443d2  mov     rcx, rax; hHeap
0x1800443d5  call    cs:__imp_HeapFree
0x1800443db  mov     qword ptr [rdi+60h], 0
0x1800443e3  jmp     loc_180044491
0x1800443e8  mov     rcx, [rdi+8]; lpMem
0x1800443ec  test    rcx, rcx
0x1800443ef  jz      loc_180044491
0x1800443f5  call    MprCommonFree
0x1800443fa  jmp     loc_180044489
0x1800443ff  mov     edx, [rdi+14h]
0x180044402  mov     rcx, [rdi+18h]; lpMem
0x180044406  call    FreeEkus
0x18004440b  lea     rcx, [rdi+20h]
0x18004440f  mov     dword ptr [rdi+14h], 0
0x180044416  cmp     dword ptr [rcx], 0
0x180044419  jz      short loc_180044422
0x18004441b  xor     edx, edx
0x18004441d  call    FreeCertificateBlob
0x180044422  mov     rcx, [rdi+38h]
0x180044426  test    rcx, rcx
0x180044429  jz      short loc_180044438
0x18004442b  call    FreeCustomPolicy
0x180044430  mov     qword ptr [rdi+38h], 0
0x180044438  mov     edx, [rdi+40h]
0x18004443b  mov     rcx, [rdi+48h]; lpMem
0x18004443f  call    FreeEkus
0x180044444  lea     rcx, [rdi+50h]
0x180044448  cmp     dword ptr [rcx], 0
0x18004444b  jz      short loc_180044491
0x18004444d  xor     edx, edx
0x18004444f  call    FreeCertificateBlob
0x180044454  jmp     short loc_180044491
0x180044456  call    cs:__imp_GetProcessHeap
0x18004445c  mov     r8, rdi; lpMem
0x18004445f  xor     edx, edx; dwFlags
0x180044461  mov     rcx, rax; hHeap
0x180044464  call    cs:__imp_HeapFree
0x18004446a  jmp     short loc_180044491
0x18004446c  mov     rbx, [rdi+8]
0x180044470  test    rbx, rbx
0x180044473  jz      short loc_180044491
0x180044475  call    cs:__imp_GetProcessHeap
0x18004447b  mov     r8, rbx; lpMem
0x18004447e  xor     edx, edx; dwFlags
0x180044480  mov     rcx, rax; hHeap
0x180044483  call    cs:__imp_HeapFree
0x180044489  mov     qword ptr [rdi+8], 0
0x180044491  xor     eax, eax
0x180044493  mov     rcx, [rsp+838h+var_18]
0x18004449b  xor     rcx, rsp; StackCookie
0x18004449e  call    __security_check_cookie
0x1800444a3  mov     rbx, [rsp+838h+arg_0]
0x1800444ab  add     rsp, 830h
0x1800444b2  pop     rdi
0x1800444b3  retn
```
