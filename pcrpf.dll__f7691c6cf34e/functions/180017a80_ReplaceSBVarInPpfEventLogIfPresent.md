# ReplaceSBVarInPpfEventLogIfPresent

- ea: `0x180017a80`
- end: `0x180017f4b`
- name: `ReplaceSBVarInPpfEventLogIfPresent`
- size: `1227`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, SIZE_T dwBytes@<rdx>, __int16, __int16, char *, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800107e8`
- `0x180017458`

## callees

- `0x180009c64`
- `0x18000dfa0`
- `0x180013e6c`
- `0x180017a80`
- `0x18001aff0`
- `0x18001be88`
- `0x18002d5ec`
- `0x180032844`
- `0x1800570b0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017e1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017e1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017c0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017c87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ed3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017c0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017c87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017c23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017c6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017c9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017ee7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017c23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017c6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017c9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017ee7`

## string_xrefs

- `0x180017ac7`: `ReplaceSBVarInPpfEventLogIfPresent`
- `0x180017ad1`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017b4f`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017c3a`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017d63`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017dc6`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017f34`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReplaceSBVarInPpfEventLogIfPresent(
        unsigned __int8 *Src,
        SIZE_T dwBytes,
        struct _GUID *a3,
        const unsigned __int16 *a4,
        __int16 a5,
        __int16 a6,
        char *a7,
        LPVOID *Size,
        _DWORD *a9)
{
  SIZE_T v11; // r15
  LPVOID *v13; // r13
  int EfiVariable; // ebx
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  void *v17; // rdi
  HANDLE v18; // rax
  int v20; // edi
  void *v21; // rbx
  HANDLE v22; // rax
  void *v23; // rbx
  bool v24; // zf
  HANDLE v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  __int64 v30; // rdx
  void *v31; // rbx
  HANDLE v32; // rax
  HANDLE v33; // rax
  void *v34; // rax
  void *v35; // rbx
  HANDLE v36; // rax
  void *v37; // rbx
  HANDLE v38; // rax
  void *v39; // rbx
  HANDLE v40; // rax
  char *v41; // [rsp+28h] [rbp-79h]
  unsigned int v42; // [rsp+60h] [rbp-41h] BYREF
  unsigned int v43; // [rsp+64h] [rbp-3Dh] BYREF
  char *v44; // [rsp+68h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-31h] BYREF
  LPVOID v46; // [rsp+78h] [rbp-29h] BYREF
  LPVOID v47; // [rsp+80h] [rbp-21h] BYREF
  LPVOID *p_lpMem; // [rsp+88h] [rbp-19h]
  void *v49; // [rsp+90h] [rbp-11h] BYREF
  char v50; // [rsp+98h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v11 = (unsigned int)dwBytes;
  v13 = Size;
  *Size = 0;
  *a9 = 0;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
    0x47u,
    "ReplaceSBVarInPpfEventLogIfPresent",
    "Replacing SB var '%ws' with its current value",
    a4);
  lpMem = 0;
  v42 = 0;
  p_lpMem = &lpMem;
  v49 = 0;
  v50 = 1;
  EfiVariable = PpfhGetEfiVariable(a3, a4, &v49, &v42);
  if ( v50 )
  {
    v15 = *p_lpMem;
    *p_lpMem = v49;
    if ( v15 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v15);
    }
  }
  if ( EfiVariable < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)EfiVariable);
    v17 = lpMem;
    lpMem = 0;
    if ( v17 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v17);
    }
    return (unsigned int)EfiVariable;
  }
  v47 = 0;
  v43 = 0;
  p_lpMem = &v47;
  v49 = 0;
  v50 = 1;
  v20 = ((__int64 (__fastcall *)(struct _GUID *, const unsigned __int16 *, LPVOID, _QWORD, _DWORD, __int16, __int16, void **, unsigned int *))off_180072078)(
          a3,
          a4,
          lpMem,
          v42,
          0,
          a5,
          a6,
          &v49,
          &v43);
  if ( v50 )
  {
    v21 = *p_lpMem;
    *p_lpMem = v49;
    if ( v21 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v21);
    }
  }
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v20);
LABEL_13:
    v23 = v47;
    v24 = v47 == 0;
    v47 = 0;
    if ( !v24 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v23);
    }
    v26 = lpMem;
    lpMem = 0;
    if ( v26 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v26);
    }
    return (unsigned int)v20;
  }
  LODWORD(v44) = 0;
  v46 = 0;
  LODWORD(Size) = 0;
  p_lpMem = &v46;
  v49 = 0;
  v50 = 1;
  v20 = PpfTxfIntTransformPpfEventLog(
          Src,
          v11,
          v47,
          v43,
          1,
          (struct PPF_TRANSFORM_CONTEXT *)a7,
          (enum PPF_TRANSFORM_RESULT *)&v44,
          (unsigned __int8 **)&v49,
          (unsigned int *)&Size,
          0,
          0,
          0);
  if ( v50 )
  {
    v28 = *p_lpMem;
    *p_lpMem = v49;
    if ( v28 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
  }
  if ( v20 < 0 )
  {
    v30 = 85;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v20);
    goto LABEL_24;
  }
  if ( (_DWORD)v44 == 2 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
    {
      v20 = -920125431;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5A,
        (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)0xC9280009LL,
        (unsigned __int64)"SB var not measured in boot TCG log",
        v41);
      goto LABEL_24;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)0x8007000DLL,
      (int)"SB var not measured in boot TCG log",
      v41);
    LODWORD(Size) = v11;
    v33 = GetProcessHeap();
    v34 = HeapAlloc(v33, 0, v11);
    v35 = v46;
    v46 = v34;
    if ( v35 )
    {
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v35);
      v34 = v46;
    }
    if ( !v34 )
    {
      v20 = -2147024882;
      v30 = 98;
      goto LABEL_23;
    }
    memcpy_0(v34, Src, (unsigned int)Size);
  }
  else if ( (((_DWORD)v44 - 1) & 0xFFFFFFFD) != 0 )
  {
    LODWORD(v41) = (_DWORD)v44;
    v20 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x69,
      (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)0x8000FFFFLL,
      (unsigned __int64)"Transform cannot be applied. Result: %u",
      v41);
LABEL_24:
    v31 = v46;
    v24 = v46 == 0;
    v46 = 0;
    if ( !v24 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
    }
    goto LABEL_13;
  }
  *v13 = v46;
  *a9 = (_DWORD)Size;
  v46 = 0;
  v37 = v47;
  v47 = 0;
  if ( v37 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v37);
  }
  v39 = lpMem;
  lpMem = 0;
  if ( v39 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v39);
  }
  return 0;
}

```

## disassembly

```asm
0x180017a80  push    rbp
0x180017a82  push    rbx
0x180017a83  push    rsi
0x180017a84  push    rdi
0x180017a85  push    r12
0x180017a87  push    r13
0x180017a89  push    r14
0x180017a8b  push    r15
0x180017a8d  lea     rbp, [rsp-7]
0x180017a92  sub     rsp, 0A8h
0x180017a99  mov     rsi, r9
0x180017a9c  mov     r12, r8
0x180017a9f  mov     r15d, edx
0x180017aa2  mov     r14, rcx
0x180017aa5  xor     edi, edi
0x180017aa7  mov     r13, [rbp+3Fh+Size]
0x180017aae  mov     [r13+0], rdi
0x180017ab2  mov     rax, [rbp+3Fh+arg_40]
0x180017ab9  mov     [rax], edi
0x180017abb  mov     qword ptr [rsp+0E0h+var_C0], r9; int
0x180017ac0  lea     r9, aReplacingSbVar; "Replacing SB var '%ws' with its current"...
0x180017ac7  lea     r8, aReplacesbvarin; "ReplaceSBVarInPpfEventLogIfPresent"
0x180017ace  lea     edx, [rdi+47h]; unsigned int
0x180017ad1  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180017ad8  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180017add  mov     [rbp+3Fh+lpMem], rdi
0x180017ae1  mov     [rbp+3Fh+var_80], edi
0x180017ae4  lea     rax, [rbp+3Fh+lpMem]
0x180017ae8  mov     [rbp+3Fh+var_58], rax
0x180017aec  mov     [rbp+3Fh+var_50], rdi
0x180017af0  mov     [rbp+3Fh+var_48], 1
0x180017af4  lea     r9, [rbp+3Fh+var_80]; unsigned int *
0x180017af8  lea     r8, [rbp+3Fh+var_50]; void **
0x180017afc  mov     rdx, rsi; unsigned __int16 *
0x180017aff  mov     rcx, r12; struct _GUID *
0x180017b02  call    ?PpfhGetEfiVariable@@YAJPEAU_GUID@@PEBGPEAPEAXPEAI@Z; PpfhGetEfiVariable(_GUID *,ushort const *,void * *,uint *)
0x180017b07  mov     ebx, eax
0x180017b09  cmp     [rbp+3Fh+var_48], dil
0x180017b0d  jz      short loc_180017B44
0x180017b0f  mov     rdx, [rbp+3Fh+var_58]
0x180017b13  mov     rdi, [rdx]
0x180017b16  mov     rcx, [rbp+3Fh+var_50]
0x180017b1a  mov     [rdx], rcx
0x180017b1d  test    rdi, rdi
0x180017b20  jz      short loc_180017B42
0x180017b22  call    cs:__imp_GetProcessHeap
0x180017b29  nop     dword ptr [rax+rax+00h]
0x180017b2e  mov     rcx, rax; hHeap
0x180017b31  mov     r8, rdi; lpMem
0x180017b34  xor     edx, edx; dwFlags
0x180017b36  call    cs:__imp_HeapFree
0x180017b3d  nop     dword ptr [rax+rax+00h]
0x180017b42  xor     edi, edi
0x180017b44  test    ebx, ebx
0x180017b46  jns     short loc_180017B99
0x180017b48  mov     rcx, [rbp+47h]; this
0x180017b4c  mov     r9d, ebx; char *
0x180017b4f  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180017b56  mov     edx, 4Bh ; 'K'; void *
0x180017b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b60  nop
0x180017b61  mov     rdi, [rbp+3Fh+lpMem]
0x180017b65  mov     [rbp+3Fh+lpMem], 0
0x180017b6d  test    rdi, rdi
0x180017b70  jz      short loc_180017B92
0x180017b72  call    cs:__imp_GetProcessHeap
0x180017b79  nop     dword ptr [rax+rax+00h]
0x180017b7e  mov     rcx, rax; hHeap
0x180017b81  mov     r8, rdi; lpMem
0x180017b84  xor     edx, edx; dwFlags
0x180017b86  call    cs:__imp_HeapFree
0x180017b8d  nop     dword ptr [rax+rax+00h]
0x180017b92  mov     eax, ebx
0x180017b94  jmp     loc_180017EF5
0x180017b99  mov     [rbp+3Fh+var_60], rdi
0x180017b9d  mov     [rbp+3Fh+var_7C], edi
0x180017ba0  lea     rax, [rbp+3Fh+var_60]
0x180017ba4  mov     [rbp+3Fh+var_58], rax
0x180017ba8  mov     [rbp+3Fh+var_50], rdi
0x180017bac  mov     [rbp+3Fh+var_48], 1
0x180017bb0  lea     rax, [rbp+3Fh+var_7C]
0x180017bb4  mov     [rsp+0E0h+var_A0], rax
0x180017bb9  lea     rax, [rbp+3Fh+var_50]
0x180017bbd  mov     [rsp+0E0h+var_A8], rax
0x180017bc2  movzx   ecx, [rbp+3Fh+arg_28]
0x180017bc6  mov     word ptr [rsp+0E0h+var_B0], cx
0x180017bcb  movzx   ecx, [rbp+3Fh+arg_20]
0x180017bcf  mov     word ptr [rsp+0E0h+var_B8], cx
0x180017bd4  mov     [rsp+0E0h+var_C0], edi; int
0x180017bd8  mov     r9d, [rbp+3Fh+var_80]
0x180017bdc  mov     r8, [rbp+3Fh+lpMem]
0x180017be0  mov     rdx, rsi
0x180017be3  mov     rcx, r12
0x180017be6  mov     rax, cs:off_180072078
0x180017bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bf2  mov     edi, eax
0x180017bf4  xor     esi, esi
0x180017bf6  cmp     [rbp+3Fh+var_48], sil
0x180017bfa  jz      short loc_180017C2F
0x180017bfc  mov     rdx, [rbp+3Fh+var_58]
0x180017c00  mov     rbx, [rdx]
0x180017c03  mov     rcx, [rbp+3Fh+var_50]
0x180017c07  mov     [rdx], rcx
0x180017c0a  test    rbx, rbx
0x180017c0d  jz      short loc_180017C2F
0x180017c0f  call    cs:__imp_GetProcessHeap
0x180017c16  nop     dword ptr [rax+rax+00h]
0x180017c1b  mov     rcx, rax; hHeap
0x180017c1e  mov     r8, rbx; lpMem
0x180017c21  xor     edx, edx; dwFlags
0x180017c23  call    cs:__imp_HeapFree
0x180017c2a  nop     dword ptr [rax+rax+00h]
0x180017c2f  test    edi, edi
0x180017c31  jns     short loc_180017CAE
0x180017c33  mov     rcx, [rbp+47h]; this
0x180017c37  mov     r9d, edi; char *
0x180017c3a  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180017c41  mov     edx, 4Fh ; 'O'; void *
0x180017c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c4b  nop
0x180017c4c  mov     rbx, [rbp+3Fh+var_60]
0x180017c50  test    rbx, rbx
0x180017c53  mov     [rbp+3Fh+var_60], rsi
0x180017c57  jz      short loc_180017C7A
0x180017c59  call    cs:__imp_GetProcessHeap
0x180017c60  nop     dword ptr [rax+rax+00h]
0x180017c65  mov     rcx, rax; hHeap
0x180017c68  mov     r8, rbx; lpMem
0x180017c6b  xor     edx, edx; dwFlags
0x180017c6d  call    cs:__imp_HeapFree
0x180017c74  nop     dword ptr [rax+rax+00h]
0x180017c79  nop
0x180017c7a  mov     rbx, [rbp+3Fh+lpMem]
0x180017c7e  mov     [rbp+3Fh+lpMem], rsi
0x180017c82  test    rbx, rbx
0x180017c85  jz      short loc_180017CA7
0x180017c87  call    cs:__imp_GetProcessHeap
0x180017c8e  nop     dword ptr [rax+rax+00h]
0x180017c93  mov     rcx, rax; hHeap
0x180017c96  mov     r8, rbx; lpMem
0x180017c99  xor     edx, edx; dwFlags
0x180017c9b  call    cs:__imp_HeapFree
0x180017ca2  nop     dword ptr [rax+rax+00h]
0x180017ca7  mov     eax, edi
0x180017ca9  jmp     loc_180017EF5
0x180017cae  mov     dword ptr [rbp+3Fh+var_78], esi
0x180017cb1  mov     [rbp+3Fh+var_68], rsi
0x180017cb5  mov     dword ptr [rbp+3Fh+Size], esi
0x180017cbb  lea     rax, [rbp+3Fh+var_68]
0x180017cbf  mov     [rbp+3Fh+var_58], rax
0x180017cc3  mov     [rbp+3Fh+var_50], rsi
0x180017cc7  mov     [rbp+3Fh+var_48], 1
0x180017ccb  mov     [rsp+0E0h+var_88], rsi
0x180017cd0  mov     [rsp+0E0h+var_90], rsi
0x180017cd5  mov     [rsp+0E0h+var_98], rsi
0x180017cda  lea     rax, [rbp+3Fh+Size]
0x180017ce1  mov     [rsp+0E0h+var_A0], rax
0x180017ce6  lea     rax, [rbp+3Fh+var_50]
0x180017cea  mov     [rsp+0E0h+var_A8], rax
0x180017cef  lea     rax, [rbp+3Fh+var_78]
0x180017cf3  mov     [rsp+0E0h+var_B0], rax
0x180017cf8  mov     rax, [rbp+3Fh+arg_30]
0x180017cfc  mov     [rsp+0E0h+var_B8], rax; char *
0x180017d01  mov     [rsp+0E0h+var_C0], 1; int
0x180017d09  mov     r9d, [rbp+3Fh+var_7C]
0x180017d0d  mov     r8, [rbp+3Fh+var_60]
0x180017d11  mov     edx, r15d
0x180017d14  mov     rcx, r14
0x180017d17  call    PpfTxfIntTransformPpfEventLog
0x180017d1c  mov     edi, eax
0x180017d1e  cmp     [rbp+3Fh+var_48], sil
0x180017d22  jz      short loc_180017D57
0x180017d24  mov     rdx, [rbp+3Fh+var_58]
0x180017d28  mov     rbx, [rdx]
0x180017d2b  mov     rcx, [rbp+3Fh+var_50]
0x180017d2f  mov     [rdx], rcx
0x180017d32  test    rbx, rbx
0x180017d35  jz      short loc_180017D57
0x180017d37  call    cs:__imp_GetProcessHeap
0x180017d3e  nop     dword ptr [rax+rax+00h]
0x180017d43  mov     rcx, rax; hHeap
0x180017d46  mov     r8, rbx; lpMem
0x180017d49  xor     edx, edx; dwFlags
0x180017d4b  call    cs:__imp_HeapFree
0x180017d52  nop     dword ptr [rax+rax+00h]
0x180017d57  test    edi, edi
0x180017d59  jns     short loc_180017DAA
0x180017d5b  mov     edx, 55h ; 'U'; void *
0x180017d60  mov     r9d, edi; char *
0x180017d63  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180017d6a  mov     rcx, [rbp+47h]; this
0x180017d6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d73  nop
0x180017d74  mov     rbx, [rbp+3Fh+var_68]
0x180017d78  test    rbx, rbx
0x180017d7b  mov     [rbp+3Fh+var_68], rsi
0x180017d7f  jz      loc_180017C4C
0x180017d85  call    cs:__imp_GetProcessHeap
0x180017d8c  nop     dword ptr [rax+rax+00h]
0x180017d91  mov     rcx, rax; hHeap
0x180017d94  mov     r8, rbx; lpMem
0x180017d97  xor     edx, edx; dwFlags
0x180017d99  call    cs:__imp_HeapFree
0x180017da0  nop     dword ptr [rax+rax+00h]
0x180017da5  jmp     loc_180017C4C
0x180017daa  mov     edx, dword ptr [rbp+3Fh+var_78]
0x180017dad  cmp     edx, 2
0x180017db0  jnz     loc_180017F0A
0x180017db6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180017dbd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x180017dc2  mov     rcx, [rbp+47h]; this
0x180017dc6  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180017dcd  test    al, al
0x180017dcf  lea     rax, aSbVarNotMeasur; "SB var not measured in boot TCG log"
0x180017dd6  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180017ddb  jz      short loc_180017DF1
0x180017ddd  mov     edi, 0C9280009h
0x180017de2  mov     r9d, edi; char *
0x180017de5  mov     edx, 5Ah ; 'Z'; void *
0x180017dea  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017def  jmp     short loc_180017D74
0x180017df1  mov     r9d, 8007000Dh; char *
0x180017df7  mov     edx, 5Eh ; '^'; void *
0x180017dfc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017e01  mov     dword ptr [rbp+3Fh+Size], r15d
0x180017e08  call    cs:__imp_GetProcessHeap
0x180017e0f  nop     dword ptr [rax+rax+00h]
0x180017e14  mov     r8, r15; dwBytes
0x180017e17  xor     edx, edx; dwFlags
0x180017e19  mov     rcx, rax; hHeap
0x180017e1c  call    cs:__imp_HeapAlloc
0x180017e23  nop     dword ptr [rax+rax+00h]
0x180017e28  mov     rbx, [rbp+3Fh+var_68]
0x180017e2c  mov     [rbp+3Fh+var_68], rax
0x180017e30  test    rbx, rbx
0x180017e33  jz      short loc_180017E59
0x180017e35  call    cs:__imp_GetProcessHeap
0x180017e3c  nop     dword ptr [rax+rax+00h]
0x180017e41  mov     rcx, rax; hHeap
0x180017e44  mov     r8, rbx; lpMem
0x180017e47  xor     edx, edx; dwFlags
0x180017e49  call    cs:__imp_HeapFree
0x180017e50  nop     dword ptr [rax+rax+00h]
0x180017e55  mov     rax, [rbp+3Fh+var_68]
0x180017e59  test    rax, rax
0x180017e5c  jnz     short loc_180017E6B
0x180017e5e  mov     edi, 8007000Eh
0x180017e63  lea     edx, [rax+62h]
0x180017e66  jmp     loc_180017D60
0x180017e6b  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x180017e72  mov     rdx, r14; Src
0x180017e75  mov     rcx, rax; void *
0x180017e78  call    memcpy_0
0x180017e7d  mov     rax, [rbp+3Fh+var_68]
0x180017e81  mov     [r13+0], rax
0x180017e85  mov     eax, dword ptr [rbp+3Fh+Size]
0x180017e8b  mov     rcx, [rbp+3Fh+arg_40]
0x180017e92  mov     [rcx], eax
0x180017e94  mov     [rbp+3Fh+var_68], rsi
0x180017e98  mov     rbx, [rbp+3Fh+var_60]
0x180017e9c  mov     [rbp+3Fh+var_60], rsi
0x180017ea0  test    rbx, rbx
0x180017ea3  jz      short loc_180017EC6
0x180017ea5  call    cs:__imp_GetProcessHeap
0x180017eac  nop     dword ptr [rax+rax+00h]
0x180017eb1  mov     rcx, rax; hHeap
0x180017eb4  mov     r8, rbx; lpMem
0x180017eb7  xor     edx, edx; dwFlags
0x180017eb9  call    cs:__imp_HeapFree
0x180017ec0  nop     dword ptr [rax+rax+00h]
0x180017ec5  nop
0x180017ec6  mov     rbx, [rbp+3Fh+lpMem]
0x180017eca  mov     [rbp+3Fh+lpMem], rsi
0x180017ece  test    rbx, rbx
0x180017ed1  jz      short loc_180017EF3
0x180017ed3  call    cs:__imp_GetProcessHeap
0x180017eda  nop     dword ptr [rax+rax+00h]
0x180017edf  mov     rcx, rax; hHeap
0x180017ee2  mov     r8, rbx; lpMem
0x180017ee5  xor     edx, edx; dwFlags
0x180017ee7  call    cs:__imp_HeapFree
0x180017eee  nop     dword ptr [rax+rax+00h]
0x180017ef3  xor     eax, eax
0x180017ef5  add     rsp, 0A8h
0x180017efc  pop     r15
0x180017efe  pop     r14
0x180017f00  pop     r13
0x180017f02  pop     r12
0x180017f04  pop     rdi
0x180017f05  pop     rsi
0x180017f06  pop     rbx
0x180017f07  pop     rbp
0x180017f08  retn
0x180017f0a  lea     eax, [rdx-1]
0x180017f0d  test    eax, 0FFFFFFFDh
0x180017f12  jz      loc_180017E7D
0x180017f18  mov     rcx, [rbp+47h]; this
0x180017f1c  mov     dword ptr [rsp+0E0h+var_B8], edx; char *
0x180017f20  lea     rax, aTransformCanno; "Transform cannot be applied. Result: %u"
0x180017f27  mov     qword ptr [rsp+0E0h+var_C0], rax; int
  ... truncated ...
```
