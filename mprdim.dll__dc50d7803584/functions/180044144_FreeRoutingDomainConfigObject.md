# FreeRoutingDomainConfigObject

- ea: `0x180044144`
- end: `0x1800442e7`
- name: `FreeRoutingDomainConfigObject`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003d3f4`

## callees

- `0x180043fbc`
- `0x180044144`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004425a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004425a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044244`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044244`
- `KERNEL32!GetProcessHeap` at `0x18004424c`
- `KERNEL32!GetProcessHeap` at `0x18004424c`

## string_xrefs

- `0x1800441d6`: `FreeRoutingDomainConfigObject`
- `0x18004420e`: `FreeRoutingDomainConfigObject`
- `0x18004427d`: `FreeRoutingDomainConfigObject`

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
  unsigned __int16 *v9; // [rsp+28h] [rbp-D8h]
  unsigned int v10; // [rsp+30h] [rbp-D0h]
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h]
  __int128 v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+7Ch] [rbp-84h]
  int v18; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v11 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v16 = -1;
  v17 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"FreeRoutingDomainConfigObject",
      &v11,
      v2,
      (struct _GUID *)((char *)*a1 + 524),
      v9,
      v10);
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
    else if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"%s: Invalid Revision: %d.", L"FreeRoutingDomainConfigObject", *v3);
LABEL_15:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v18);
    }
  }
  else
  {
    v11 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"%hs(Line#%d): Invalid parameter.", "FreeRoutingDomainConfigObject", 5169);
      goto LABEL_15;
    }
  }
  v7 = v11;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
  return v7;
}

```

## disassembly

```asm
0x180044144  push    rbp
0x180044146  push    rbx
0x180044147  push    rsi
0x180044148  push    rdi
0x180044149  lea     rbp, [rsp-798h]
0x180044151  sub     rsp, 898h
0x180044158  mov     rax, cs:__security_cookie
0x18004415f  xor     rax, rsp
0x180044162  mov     [rbp+7B0h+var_30], rax
0x180044169  mov     rbx, rcx
0x18004416c  mov     [rsp+8B0h+var_870], 0
0x180044174  xor     eax, eax
0x180044176  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18004417a  xor     edx, edx; Val
0x18004417c  mov     [rbp+7B0h+var_830], eax
0x18004417f  mov     r8d, 7FCh; Size
0x180044185  call    memset_0
0x18004418a  cmp     qword ptr cs:xmmword_1800710A0+8, 0
0x180044192  xorps   xmm0, xmm0
0x180044195  xorps   xmm1, xmm1
0x180044198  mov     [rsp+8B0h+var_868], 0
0x1800441a1  movdqu  [rsp+8B0h+var_860], xmm0
0x1800441a7  mov     [rsp+8B0h+var_840], 0
0x1800441b0  movdqu  [rsp+8B0h+var_850], xmm1
0x1800441b6  mov     [rsp+8B0h+var_838], 0FFFFFFFFh
0x1800441be  mov     [rsp+8B0h+var_834], 0
0x1800441c6  jz      short loc_1800441EC
0x1800441c8  mov     rax, [rbx]
0x1800441cb  lea     r8, [rsp+8B0h+var_870]; unsigned int *
0x1800441d0  add     rax, 20Ch
0x1800441d6  lea     rdx, aFreeroutingdom_0; "FreeRoutingDomainConfigObject"
0x1800441dd  lea     rcx, [rsp+8B0h+var_868]; this
0x1800441e2  mov     [rsp+8B0h+var_890], rax; struct _GUID *
0x1800441e7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800441ec  test    rbx, rbx
0x1800441ef  jz      short loc_180044269
0x1800441f1  mov     rdx, [rbx]
0x1800441f4  test    rdx, rdx
0x1800441f7  jz      short loc_180044269
0x1800441f9  cmp     byte ptr [rdx], 1
0x1800441fc  jz      short loc_180044226
0x1800441fe  cmp     qword ptr cs:xmmword_180071090, 0
0x180044206  jz      loc_1800442BC
0x18004420c  xor     eax, eax
0x18004420e  lea     r8, aFreeroutingdom_0; "FreeRoutingDomainConfigObject"
0x180044215  mov     word ptr [rbp+7B0h+var_830], ax
0x180044219  movzx   r9d, byte ptr [rdx]
0x18004421d  lea     rdx, aSInvalidRevisi; "%s: Invalid Revision: %d."
0x180044224  jmp     short loc_180044295
0x180044226  lea     rcx, [rdx+8]
0x18004422a  mov     esi, [rcx+284h]
0x180044230  call    FreeMpriRoutingDomainConfigEx1Object
0x180044235  mov     rdi, [rbx]
0x180044238  test    rdi, rdi
0x18004423b  jz      short loc_180044260
0x18004423d  test    esi, esi
0x18004423f  jns     short loc_18004424C
0x180044241  mov     rcx, rdi; hMem
0x180044244  call    cs:__imp_LocalFree
0x18004424a  jmp     short loc_180044260
0x18004424c  call    cs:__imp_GetProcessHeap
0x180044252  mov     r8, rdi; lpMem
0x180044255  xor     edx, edx; dwFlags
0x180044257  mov     rcx, rax; hHeap
0x18004425a  call    cs:__imp_HeapFree
0x180044260  mov     qword ptr [rbx], 0
0x180044267  jmp     short loc_1800442BC
0x180044269  cmp     qword ptr cs:xmmword_180071090, 0
0x180044271  mov     [rsp+8B0h+var_870], 57h ; 'W'
0x180044279  jz      short loc_1800442BC
0x18004427b  xor     eax, eax
0x18004427d  lea     r8, aFreeroutingdom; "FreeRoutingDomainConfigObject"
0x180044284  mov     word ptr [rbp+7B0h+var_830], ax
0x180044288  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004428f  mov     r9d, 1431h
0x180044295  lea     rcx, [rbp+7B0h+var_830]
0x180044299  call    FormatRRASErrorString
0x18004429e  mov     rdx, qword ptr cs:xmmword_180071090
0x1800442a5  lea     r8, [rbp+7B0h+var_830]
0x1800442a9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800442b0  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800442b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442bc  mov     ebx, [rsp+8B0h+var_870]
0x1800442c0  lea     rcx, [rsp+8B0h+var_868]; this
0x1800442c5  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800442ca  mov     eax, ebx
0x1800442cc  mov     rcx, [rbp+7B0h+var_30]
0x1800442d3  xor     rcx, rsp; StackCookie
0x1800442d6  call    __security_check_cookie
0x1800442db  add     rsp, 898h
0x1800442e2  pop     rdi
0x1800442e3  pop     rsi
0x1800442e4  pop     rbx
0x1800442e5  pop     rbp
0x1800442e6  retn
```
