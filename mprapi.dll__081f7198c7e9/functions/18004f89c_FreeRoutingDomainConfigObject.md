# FreeRoutingDomainConfigObject

- ea: `0x18004f89c`
- end: `0x18004fa3f`
- name: `FreeRoutingDomainConfigObject`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180048d84`

## callees

- `0x18004f714`
- `0x18004f89c`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f99c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f99c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f9a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f9a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f9b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f9b2`

## string_xrefs

- `0x18004f92e`: `FreeRoutingDomainConfigObject`
- `0x18004f966`: `FreeRoutingDomainConfigObject`
- `0x18004f9d5`: `FreeRoutingDomainConfigObject`

## pseudocode

```c
__int64 __fastcall FreeRoutingDomainConfigObject(HLOCAL *a1)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned __int8 *v3; // rdx
  int v4; // esi
  HLOCAL v5; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h]
  __int128 v12; // [rsp+60h] [rbp-A0h]
  __int64 v13; // [rsp+70h] [rbp-90h]
  int v14; // [rsp+78h] [rbp-88h]
  int v15; // [rsp+7Ch] [rbp-84h]
  int v16; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v9 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  v14 = -1;
  v15 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v10,
      L"FreeRoutingDomainConfigObject",
      &v9,
      v2,
      (struct _GUID *)((char *)*a1 + 524));
  if ( a1 && (v3 = (unsigned __int8 *)*a1) != 0 )
  {
    if ( *v3 == 1 )
    {
      v4 = *((_DWORD *)v3 + 163);
      FreeMpriRoutingDomainConfigEx1Object(v3 + 8);
      v5 = *a1;
      if ( *a1 )
      {
        if ( v4 >= 0 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v5);
        }
        else
        {
          LocalFree(*a1);
        }
      }
      *a1 = 0;
    }
    else if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"%s: Invalid Revision: %d.", L"FreeRoutingDomainConfigObject", *v3);
LABEL_15:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v16);
    }
  }
  else
  {
    v9 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"%hs(Line#%d): Invalid parameter.", "FreeRoutingDomainConfigObject", 5169);
      goto LABEL_15;
    }
  }
  v7 = v9;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
  return v7;
}

```

## disassembly

```asm
0x18004f89c  push    rbp
0x18004f89e  push    rbx
0x18004f89f  push    rsi
0x18004f8a0  push    rdi
0x18004f8a1  lea     rbp, [rsp-798h]
0x18004f8a9  sub     rsp, 898h
0x18004f8b0  mov     rax, cs:__security_cookie
0x18004f8b7  xor     rax, rsp
0x18004f8ba  mov     [rbp+7B0h+var_30], rax
0x18004f8c1  mov     rbx, rcx
0x18004f8c4  mov     [rsp+8B0h+var_870], 0
0x18004f8cc  xor     eax, eax
0x18004f8ce  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18004f8d2  xor     edx, edx; Val
0x18004f8d4  mov     [rbp+7B0h+var_830], eax
0x18004f8d7  mov     r8d, 7FCh; Size
0x18004f8dd  call    memset_0
0x18004f8e2  cmp     qword ptr cs:xmmword_180078C60+8, 0
0x18004f8ea  xorps   xmm0, xmm0
0x18004f8ed  xorps   xmm1, xmm1
0x18004f8f0  mov     [rsp+8B0h+var_868], 0
0x18004f8f9  movdqu  [rsp+8B0h+var_860], xmm0
0x18004f8ff  mov     [rsp+8B0h+var_840], 0
0x18004f908  movdqu  [rsp+8B0h+var_850], xmm1
0x18004f90e  mov     [rsp+8B0h+var_838], 0FFFFFFFFh
0x18004f916  mov     [rsp+8B0h+var_834], 0
0x18004f91e  jz      short loc_18004F944
0x18004f920  mov     rax, [rbx]
0x18004f923  lea     r8, [rsp+8B0h+var_870]; unsigned int *
0x18004f928  add     rax, 20Ch
0x18004f92e  lea     rdx, aFreeroutingdom_0; "FreeRoutingDomainConfigObject"
0x18004f935  lea     rcx, [rsp+8B0h+var_868]; this
0x18004f93a  mov     [rsp+8B0h+var_890], rax; struct _GUID *
0x18004f93f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004f944  test    rbx, rbx
0x18004f947  jz      short loc_18004F9C1
0x18004f949  mov     rdx, [rbx]
0x18004f94c  test    rdx, rdx
0x18004f94f  jz      short loc_18004F9C1
0x18004f951  cmp     byte ptr [rdx], 1
0x18004f954  jz      short loc_18004F97E
0x18004f956  cmp     qword ptr cs:xmmword_180078C50, 0
0x18004f95e  jz      loc_18004FA14
0x18004f964  xor     eax, eax
0x18004f966  lea     r8, aFreeroutingdom_0; "FreeRoutingDomainConfigObject"
0x18004f96d  mov     word ptr [rbp+7B0h+var_830], ax
0x18004f971  movzx   r9d, byte ptr [rdx]
0x18004f975  lea     rdx, aSInvalidRevisi; "%s: Invalid Revision: %d."
0x18004f97c  jmp     short loc_18004F9ED
0x18004f97e  lea     rcx, [rdx+8]
0x18004f982  mov     esi, [rcx+284h]
0x18004f988  call    FreeMpriRoutingDomainConfigEx1Object
0x18004f98d  mov     rdi, [rbx]
0x18004f990  test    rdi, rdi
0x18004f993  jz      short loc_18004F9B8
0x18004f995  test    esi, esi
0x18004f997  jns     short loc_18004F9A4
0x18004f999  mov     rcx, rdi; hMem
0x18004f99c  call    cs:__imp_LocalFree
0x18004f9a2  jmp     short loc_18004F9B8
0x18004f9a4  call    cs:__imp_GetProcessHeap
0x18004f9aa  mov     r8, rdi; lpMem
0x18004f9ad  xor     edx, edx; dwFlags
0x18004f9af  mov     rcx, rax; hHeap
0x18004f9b2  call    cs:__imp_HeapFree
0x18004f9b8  mov     qword ptr [rbx], 0
0x18004f9bf  jmp     short loc_18004FA14
0x18004f9c1  cmp     qword ptr cs:xmmword_180078C50, 0
0x18004f9c9  mov     [rsp+8B0h+var_870], 57h ; 'W'
0x18004f9d1  jz      short loc_18004FA14
0x18004f9d3  xor     eax, eax
0x18004f9d5  lea     r8, aFreeroutingdom; "FreeRoutingDomainConfigObject"
0x18004f9dc  mov     word ptr [rbp+7B0h+var_830], ax
0x18004f9e0  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004f9e7  mov     r9d, 1431h
0x18004f9ed  lea     rcx, [rbp+7B0h+var_830]
0x18004f9f1  call    FormatRRASErrorString
0x18004f9f6  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004f9fd  lea     r8, [rbp+7B0h+var_830]
0x18004fa01  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004fa08  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fa0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa14  mov     ebx, [rsp+8B0h+var_870]
0x18004fa18  lea     rcx, [rsp+8B0h+var_868]; this
0x18004fa1d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004fa22  mov     eax, ebx
0x18004fa24  mov     rcx, [rbp+7B0h+var_30]
0x18004fa2b  xor     rcx, rsp; StackCookie
0x18004fa2e  call    __security_check_cookie
0x18004fa33  add     rsp, 898h
0x18004fa3a  pop     rdi
0x18004fa3b  pop     rsi
0x18004fa3c  pop     rbx
0x18004fa3d  pop     rbp
0x18004fa3e  retn
```
