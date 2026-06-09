# FreeRoutingDomainConfiguration

- ea: `0x18004fa50`
- end: `0x18004fc10`
- name: `FreeRoutingDomainConfiguration`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f714`

## callees

- `0x180028980`
- `0x18002ed78`
- `0x18002edb4`
- `0x18004fa50`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fb27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fbb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fbd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fb27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fbb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fbd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fbc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fbdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fbc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fbdf`

## string_xrefs

- `0x18004faa1`: `FreeRoutingDomainConfiguration`

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
  void *v13; // rcx
  HANDLE v14; // rax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  _WORD v18[2]; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v19[2044]; // [rsp+24h] [rbp-814h] BYREF

  v18[1] = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( !a2 )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      v18[0] = 0;
      FormatRRASErrorString(v18, L"%hs(Line#%d): Invalid parameter.", "FreeRoutingDomainConfiguration", 4990);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, _WORD *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
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
    FreeCertificateBlob(a2 + 32);
  v13 = *(void **)(a2 + 56);
  if ( v13 )
  {
    MprCommonFree(v13);
    *(_QWORD *)(a2 + 56) = 0;
  }
  FreeEkus(*(LPVOID *)(a2 + 72));
  if ( *(_DWORD *)(a2 + 80) )
    FreeCertificateBlob(a2 + 80);
  return 0;
}

```

## disassembly

```asm
0x18004fa50  mov     [rsp+arg_0], rbx
0x18004fa55  push    rdi
0x18004fa56  sub     rsp, 830h
0x18004fa5d  mov     rax, cs:__security_cookie
0x18004fa64  xor     rax, rsp
0x18004fa67  mov     [rsp+838h+var_18], rax
0x18004fa6f  mov     rdi, rdx
0x18004fa72  mov     ebx, ecx
0x18004fa74  xor     eax, eax
0x18004fa76  lea     rcx, [rsp+838h+var_814]; void *
0x18004fa7b  xor     edx, edx; Val
0x18004fa7d  mov     [rsp+838h+var_816], ax
0x18004fa82  mov     r8d, 7FCh; Size
0x18004fa88  call    memset_0
0x18004fa8d  test    rdi, rdi
0x18004fa90  jnz     short loc_18004FAE8
0x18004fa92  cmp     qword ptr cs:xmmword_180078C50, rdi
0x18004fa99  jz      loc_18004FBED
0x18004fa9f  xor     eax, eax
0x18004faa1  lea     r8, aFreeroutingdom_1; "FreeRoutingDomainConfiguration"
0x18004faa8  mov     r9d, 137Eh
0x18004faae  mov     [rsp+838h+var_818], ax
0x18004fab3  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004faba  lea     rcx, [rsp+838h+var_818]
0x18004fabf  call    FormatRRASErrorString
0x18004fac4  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004facb  lea     r8, [rsp+838h+var_818]
0x18004fad0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004fad7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fae3  jmp     loc_18004FBED
0x18004fae8  sub     ebx, 1
0x18004faeb  jz      loc_18004FBC8
0x18004faf1  sub     ebx, 3
0x18004faf4  jz      loc_18004FBB2
0x18004fafa  sub     ebx, 4
0x18004fafd  jz      short loc_18004FB5F
0x18004faff  sub     ebx, 8
0x18004fb02  jz      short loc_18004FB48
0x18004fb04  sub     ebx, 10h
0x18004fb07  jz      short loc_18004FB48
0x18004fb09  sub     ebx, 60h ; '`'
0x18004fb0c  jz      short loc_18004FB48
0x18004fb0e  cmp     ebx, 3F80h
0x18004fb14  jnz     loc_18004FBED
0x18004fb1a  mov     rbx, [rdi+60h]
0x18004fb1e  test    rbx, rbx
0x18004fb21  jz      loc_18004FBED
0x18004fb27  call    cs:__imp_GetProcessHeap
0x18004fb2d  mov     r8, rbx; lpMem
0x18004fb30  xor     edx, edx; dwFlags
0x18004fb32  mov     rcx, rax; hHeap
0x18004fb35  call    cs:__imp_HeapFree
0x18004fb3b  mov     qword ptr [rdi+60h], 0
0x18004fb43  jmp     loc_18004FBED
0x18004fb48  mov     rcx, [rdi+8]; lpMem
0x18004fb4c  test    rcx, rcx
0x18004fb4f  jz      loc_18004FBED
0x18004fb55  call    MprCommonFree
0x18004fb5a  jmp     loc_18004FBE5
0x18004fb5f  mov     edx, [rdi+14h]
0x18004fb62  mov     rcx, [rdi+18h]; lpMem
0x18004fb66  call    FreeEkus
0x18004fb6b  lea     rcx, [rdi+20h]
0x18004fb6f  mov     dword ptr [rdi+14h], 0
0x18004fb76  cmp     dword ptr [rcx], 0
0x18004fb79  jz      short loc_18004FB80
0x18004fb7b  call    FreeCertificateBlob
0x18004fb80  mov     rcx, [rdi+38h]; lpMem
0x18004fb84  test    rcx, rcx
0x18004fb87  jz      short loc_18004FB96
0x18004fb89  call    MprCommonFree
0x18004fb8e  mov     qword ptr [rdi+38h], 0
0x18004fb96  mov     edx, [rdi+40h]
0x18004fb99  mov     rcx, [rdi+48h]; lpMem
0x18004fb9d  call    FreeEkus
0x18004fba2  lea     rcx, [rdi+50h]
0x18004fba6  cmp     dword ptr [rcx], 0
0x18004fba9  jz      short loc_18004FBED
0x18004fbab  call    FreeCertificateBlob
0x18004fbb0  jmp     short loc_18004FBED
0x18004fbb2  call    cs:__imp_GetProcessHeap
0x18004fbb8  mov     r8, rdi; lpMem
0x18004fbbb  xor     edx, edx; dwFlags
0x18004fbbd  mov     rcx, rax; hHeap
0x18004fbc0  call    cs:__imp_HeapFree
0x18004fbc6  jmp     short loc_18004FBED
0x18004fbc8  mov     rbx, [rdi+8]
0x18004fbcc  test    rbx, rbx
0x18004fbcf  jz      short loc_18004FBED
0x18004fbd1  call    cs:__imp_GetProcessHeap
0x18004fbd7  mov     r8, rbx; lpMem
0x18004fbda  xor     edx, edx; dwFlags
0x18004fbdc  mov     rcx, rax; hHeap
0x18004fbdf  call    cs:__imp_HeapFree
0x18004fbe5  mov     qword ptr [rdi+8], 0
0x18004fbed  xor     eax, eax
0x18004fbef  mov     rcx, [rsp+838h+var_18]
0x18004fbf7  xor     rcx, rsp; StackCookie
0x18004fbfa  call    __security_check_cookie
0x18004fbff  mov     rbx, [rsp+838h+arg_0]
0x18004fc07  add     rsp, 830h
0x18004fc0e  pop     rdi
0x18004fc0f  retn
```
