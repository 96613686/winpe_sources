# ReplaceBootMgFw(wistd::unique_ptr<uchar,wil::process_heap_deleter> &,uint &,PPF_TRANSFORM_CONTEXT *,unsigned __int64 *)

- ea: `0x180017650`
- end: `0x180017a77`
- name: `?ReplaceBootMgFw@@YAJAEAV?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@AEAIPEAUPPF_TRANSFORM_CONTEXT@@PEA_K@Z`
- size: `1063`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned int *, struct PPF_TRANSFORM_CONTEXT *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800107e8`

## callees

- `0x180009c64`
- `0x18000c9a4`
- `0x18000dfa0`
- `0x180017650`
- `0x18001be88`
- `0x1800319dc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800176b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017739`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800177ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001785a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800178a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001790c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001793a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800179a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800179e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800176b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017739`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800177ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001785a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800178a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001790c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001793a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800179a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800179e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800176c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001774d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001786e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800178bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001794e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800179b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800179fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017a2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017a54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800176c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001774d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001786e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800178bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001794e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800179b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800179fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017a2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017a54`

## string_xrefs

- `0x18001769a`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017764`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017885`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800178ee`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall ReplaceBootMgFw(
        unsigned __int8 **a1,
        unsigned int *a2,
        struct PPF_TRANSFORM_CONTEXT *a3,
        _QWORD *a4)
{
  unsigned __int16 **v8; // rax
  int BootMgFwPath; // eax
  unsigned int v10; // ebx
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  int v14; // esi
  void *v15; // rbx
  HANDLE v16; // rax
  void *v17; // rbx
  bool v18; // zf
  HANDLE v19; // rax
  void *v20; // rbx
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  void *v30; // rbx
  HANDLE v31; // rax
  unsigned __int8 *v32; // rax
  void *v33; // rbx
  unsigned __int8 *v34; // rsi
  HANDLE v35; // rax
  HANDLE v36; // rax
  void *v37; // rbx
  HANDLE v38; // rax
  void *v39; // rbx
  HANDLE v40; // rax
  int v41; // [rsp+20h] [rbp-79h]
  int v42; // [rsp+20h] [rbp-79h]
  char *v43; // [rsp+28h] [rbp-71h]
  LPVOID v44; // [rsp+60h] [rbp-39h] BYREF
  LPVOID v45; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v46; // [rsp+70h] [rbp-29h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v48; // [rsp+80h] [rbp-19h]
  int v49; // [rsp+84h] [rbp-15h] BYREF
  unsigned int v50; // [rsp+88h] [rbp-11h] BYREF
  LPVOID *v51; // [rsp+90h] [rbp-9h]
  int v52[2]; // [rsp+98h] [rbp-1h] BYREF
  char v53; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  lpMem = 0;
  v8 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&lpMem);
  BootMgFwPath = PpfhGetBootMgFwPath(v8);
  v10 = BootMgFwPath;
  if ( BootMgFwPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)BootMgFwPath,
      v41);
    v11 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
    return v10;
  }
  v44 = 0;
  v48 = 0;
  v51 = &v44;
  *(_QWORD *)v52 = 0;
  v53 = 1;
  v14 = ((__int64 (__fastcall *)(_QWORD, unsigned __int8 *, _QWORD, LPVOID))off_180072050)(0, *a1, *a2, lpMem);
  if ( v53 )
  {
    v15 = *v51;
    *v51 = *(LPVOID *)v52;
    if ( v15 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
    }
  }
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v14,
      (int)v52);
LABEL_10:
    v17 = v44;
    v18 = v44 == 0;
    v44 = 0;
    if ( !v18 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v17);
    }
    v20 = lpMem;
    if ( lpMem )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v20);
    }
    return (unsigned int)v14;
  }
  v49 = 0;
  v45 = 0;
  v50 = 0;
  v46 = 0;
  v51 = &v45;
  *(_QWORD *)v52 = 0;
  v53 = 1;
  v14 = PpfTxfIntTransformPpfEventLog(
          *a1,
          *a2,
          v44,
          v48,
          0,
          a3,
          (enum PPF_TRANSFORM_RESULT *)&v49,
          (unsigned __int8 **)v52,
          &v50,
          0,
          0,
          &v46);
  if ( v53 )
  {
    v22 = *v51;
    *v51 = *(LPVOID *)v52;
    if ( v22 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
  }
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v14,
      v42);
    v24 = v45;
    v45 = 0;
    if ( v24 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
    }
    goto LABEL_10;
  }
  if ( v49 == 2 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)0xC9280009LL,
      (int)"Could not apply bootmgfw transform",
      v43);
    v26 = v45;
    v45 = 0;
    if ( v26 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v26);
    }
    v28 = v44;
    v44 = 0;
    if ( v28 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
    v30 = lpMem;
    if ( lpMem )
    {
      v31 = GetProcessHeap();
      HeapFree(v31, 0, v30);
    }
    return 3374841865LL;
  }
  else
  {
    v32 = (unsigned __int8 *)v45;
    v33 = 0;
    v45 = 0;
    v34 = *a1;
    *a1 = v32;
    if ( v34 )
    {
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v34);
      v33 = v45;
    }
    *a2 = v50;
    if ( (v46 & 0x80u) != 0 )
      *a4 |= 0x20uLL;
    if ( (v46 & 0x10) != 0 )
      *a4 |= 0x10uLL;
    v45 = 0;
    if ( v33 )
    {
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v33);
    }
    v37 = v44;
    v44 = 0;
    if ( v37 )
    {
      v38 = GetProcessHeap();
      HeapFree(v38, 0, v37);
    }
    v39 = lpMem;
    if ( lpMem )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180017650  push    rbp
0x180017652  push    rbx
0x180017653  push    rsi
0x180017654  push    rdi
0x180017655  push    r12
0x180017657  push    r13
0x180017659  push    r14
0x18001765b  push    r15
0x18001765d  lea     rbp, [rsp-1Fh]
0x180017662  sub     rsp, 0B8h
0x180017669  mov     rdi, r9
0x18001766c  mov     r12, r8
0x18001766f  mov     r15, rdx
0x180017672  mov     r14, rcx
0x180017675  xor     r13d, r13d
0x180017678  mov     [rbp+57h+lpMem], r13
0x18001767c  lea     rcx, [rbp+57h+lpMem]
0x180017680  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x180017685  mov     rcx, rax; unsigned __int16 **
0x180017688  call    ?PpfhGetBootMgFwPath@@YAJPEAPEAG@Z; PpfhGetBootMgFwPath(ushort * *)
0x18001768d  mov     ebx, eax
0x18001768f  test    eax, eax
0x180017691  jns     short loc_1800176DC
0x180017693  mov     rcx, [rbp+5Fh]; this
0x180017697  mov     r9d, eax; char *
0x18001769a  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800176a1  mov     edx, 0A3h; void *
0x1800176a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800176ab  nop
0x1800176ac  mov     rdi, [rbp+57h+lpMem]
0x1800176b0  test    rdi, rdi
0x1800176b3  jz      short loc_1800176D5
0x1800176b5  call    cs:__imp_GetProcessHeap
0x1800176bc  nop     dword ptr [rax+rax+00h]
0x1800176c1  mov     rcx, rax; hHeap
0x1800176c4  mov     r8, rdi; lpMem
0x1800176c7  xor     edx, edx; dwFlags
0x1800176c9  call    cs:__imp_HeapFree
0x1800176d0  nop     dword ptr [rax+rax+00h]
0x1800176d5  mov     eax, ebx
0x1800176d7  jmp     loc_180017A62
0x1800176dc  mov     [rbp+57h+var_90], r13
0x1800176e0  mov     [rbp+57h+var_70], r13d
0x1800176e4  lea     rax, [rbp+57h+var_90]
0x1800176e8  mov     [rbp+57h+var_60], rax
0x1800176ec  mov     qword ptr [rbp+57h+var_58], r13
0x1800176f0  mov     [rbp+57h+var_50], 1
0x1800176f4  lea     rax, [rbp+57h+var_70]
0x1800176f8  mov     [rsp+0F0h+var_C8], rax
0x1800176fd  lea     rax, [rbp+57h+var_58]
0x180017701  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180017706  mov     r9, [rbp+57h+lpMem]
0x18001770a  mov     r8d, [r15]
0x18001770d  mov     rdx, [r14]
0x180017710  xor     ecx, ecx
0x180017712  mov     rax, cs:off_180072050
0x180017719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001771e  mov     esi, eax
0x180017720  cmp     [rbp+57h+var_50], r13b
0x180017724  jz      short loc_180017759
0x180017726  mov     rdx, [rbp+57h+var_60]
0x18001772a  mov     rbx, [rdx]
0x18001772d  mov     rcx, qword ptr [rbp+57h+var_58]
0x180017731  mov     [rdx], rcx
0x180017734  test    rbx, rbx
0x180017737  jz      short loc_180017759
0x180017739  call    cs:__imp_GetProcessHeap
0x180017740  nop     dword ptr [rax+rax+00h]
0x180017745  mov     rcx, rax; hHeap
0x180017748  mov     r8, rbx; lpMem
0x18001774b  xor     edx, edx; dwFlags
0x18001774d  call    cs:__imp_HeapFree
0x180017754  nop     dword ptr [rax+rax+00h]
0x180017759  test    esi, esi
0x18001775b  jns     short loc_1800177D4
0x18001775d  mov     rcx, [rbp+5Fh]; this
0x180017761  mov     r9d, esi; char *
0x180017764  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001776b  mov     edx, 0A7h; void *
0x180017770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017775  nop
0x180017776  mov     rbx, [rbp+57h+var_90]
0x18001777a  test    rbx, rbx
0x18001777d  mov     [rbp+57h+var_90], r13
0x180017781  jz      short loc_1800177A4
0x180017783  call    cs:__imp_GetProcessHeap
0x18001778a  nop     dword ptr [rax+rax+00h]
0x18001778f  mov     rcx, rax; hHeap
0x180017792  mov     r8, rbx; lpMem
0x180017795  xor     edx, edx; dwFlags
0x180017797  call    cs:__imp_HeapFree
0x18001779e  nop     dword ptr [rax+rax+00h]
0x1800177a3  nop
0x1800177a4  mov     rbx, [rbp+57h+lpMem]
0x1800177a8  test    rbx, rbx
0x1800177ab  jz      short loc_1800177CD
0x1800177ad  call    cs:__imp_GetProcessHeap
0x1800177b4  nop     dword ptr [rax+rax+00h]
0x1800177b9  mov     rcx, rax; hHeap
0x1800177bc  mov     r8, rbx; lpMem
0x1800177bf  xor     edx, edx; dwFlags
0x1800177c1  call    cs:__imp_HeapFree
0x1800177c8  nop     dword ptr [rax+rax+00h]
0x1800177cd  mov     eax, esi
0x1800177cf  jmp     loc_180017A62
0x1800177d4  mov     [rbp+57h+var_6C], r13d
0x1800177d8  mov     [rbp+57h+var_88], r13
0x1800177dc  mov     [rbp+57h+var_68], r13d
0x1800177e0  mov     [rbp+57h+var_80], r13d
0x1800177e4  lea     rax, [rbp+57h+var_88]
0x1800177e8  mov     [rbp+57h+var_60], rax
0x1800177ec  mov     qword ptr [rbp+57h+var_58], r13
0x1800177f0  mov     [rbp+57h+var_50], 1
0x1800177f4  lea     rax, [rbp+57h+var_80]
0x1800177f8  mov     [rsp+0F0h+var_98], rax
0x1800177fd  mov     [rsp+0F0h+var_A0], r13
0x180017802  mov     [rsp+0F0h+var_A8], r13
0x180017807  lea     rax, [rbp+57h+var_68]
0x18001780b  mov     [rsp+0F0h+var_B0], rax
0x180017810  lea     rax, [rbp+57h+var_58]
0x180017814  mov     [rsp+0F0h+var_B8], rax
0x180017819  lea     rax, [rbp+57h+var_6C]
0x18001781d  mov     [rsp+0F0h+var_C0], rax
0x180017822  mov     [rsp+0F0h+var_C8], r12; char *
0x180017827  mov     [rsp+0F0h+var_D0], r13d; int
0x18001782c  mov     r9d, [rbp+57h+var_70]
0x180017830  mov     r8, [rbp+57h+var_90]
0x180017834  mov     edx, [r15]
0x180017837  mov     rcx, [r14]
0x18001783a  call    PpfTxfIntTransformPpfEventLog
0x18001783f  mov     esi, eax
0x180017841  cmp     [rbp+57h+var_50], r13b
0x180017845  jz      short loc_18001787A
0x180017847  mov     rdx, [rbp+57h+var_60]
0x18001784b  mov     rbx, [rdx]
0x18001784e  mov     rcx, qword ptr [rbp+57h+var_58]
0x180017852  mov     [rdx], rcx
0x180017855  test    rbx, rbx
0x180017858  jz      short loc_18001787A
0x18001785a  call    cs:__imp_GetProcessHeap
0x180017861  nop     dword ptr [rax+rax+00h]
0x180017866  mov     rcx, rax; hHeap
0x180017869  mov     r8, rbx; lpMem
0x18001786c  xor     edx, edx; dwFlags
0x18001786e  call    cs:__imp_HeapFree
0x180017875  nop     dword ptr [rax+rax+00h]
0x18001787a  test    esi, esi
0x18001787c  jns     short loc_1800178CC
0x18001787e  mov     rcx, [rbp+5Fh]; this
0x180017882  mov     r9d, esi; char *
0x180017885  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001788c  mov     edx, 0AEh; void *
0x180017891  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017896  mov     rbx, [rbp+57h+var_88]
0x18001789a  mov     [rbp+57h+var_88], r13
0x18001789e  test    rbx, rbx
0x1800178a1  jz      loc_180017776
0x1800178a7  call    cs:__imp_GetProcessHeap
0x1800178ae  nop     dword ptr [rax+rax+00h]
0x1800178b3  mov     rcx, rax; hHeap
0x1800178b6  mov     r8, rbx; lpMem
0x1800178b9  xor     edx, edx; dwFlags
0x1800178bb  call    cs:__imp_HeapFree
0x1800178c2  nop     dword ptr [rax+rax+00h]
0x1800178c7  jmp     loc_180017776
0x1800178cc  cmp     [rbp+57h+var_6C], 2
0x1800178d0  jnz     loc_18001798B
0x1800178d6  mov     rcx, [rbp+5Fh]; this
0x1800178da  lea     rax, aCouldNotApplyB; "Could not apply bootmgfw transform"
0x1800178e1  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800178e6  mov     edi, 0C9280009h
0x1800178eb  mov     r9d, edi; char *
0x1800178ee  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800178f5  mov     edx, 0B1h; void *
0x1800178fa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800178ff  mov     rbx, [rbp+57h+var_88]
0x180017903  mov     [rbp+57h+var_88], r13
0x180017907  test    rbx, rbx
0x18001790a  jz      short loc_18001792D
0x18001790c  call    cs:__imp_GetProcessHeap
0x180017913  nop     dword ptr [rax+rax+00h]
0x180017918  mov     rcx, rax; hHeap
0x18001791b  mov     r8, rbx; lpMem
0x18001791e  xor     edx, edx; dwFlags
0x180017920  call    cs:__imp_HeapFree
0x180017927  nop     dword ptr [rax+rax+00h]
0x18001792c  nop
0x18001792d  mov     rbx, [rbp+57h+var_90]
0x180017931  mov     [rbp+57h+var_90], r13
0x180017935  test    rbx, rbx
0x180017938  jz      short loc_18001795B
0x18001793a  call    cs:__imp_GetProcessHeap
0x180017941  nop     dword ptr [rax+rax+00h]
0x180017946  mov     rcx, rax; hHeap
0x180017949  mov     r8, rbx; lpMem
0x18001794c  xor     edx, edx; dwFlags
0x18001794e  call    cs:__imp_HeapFree
0x180017955  nop     dword ptr [rax+rax+00h]
0x18001795a  nop
0x18001795b  mov     rbx, [rbp+57h+lpMem]
0x18001795f  test    rbx, rbx
0x180017962  jz      short loc_180017984
0x180017964  call    cs:__imp_GetProcessHeap
0x18001796b  nop     dword ptr [rax+rax+00h]
0x180017970  mov     rcx, rax; hHeap
0x180017973  mov     r8, rbx; lpMem
0x180017976  xor     edx, edx; dwFlags
0x180017978  call    cs:__imp_HeapFree
0x18001797f  nop     dword ptr [rax+rax+00h]
0x180017984  mov     eax, edi
0x180017986  jmp     loc_180017A62
0x18001798b  mov     rax, [rbp+57h+var_88]
0x18001798f  mov     rbx, r13
0x180017992  mov     [rbp+57h+var_88], rbx
0x180017996  mov     rsi, [r14]
0x180017999  mov     [r14], rax
0x18001799c  test    rsi, rsi
0x18001799f  jz      short loc_1800179C5
0x1800179a1  call    cs:__imp_GetProcessHeap
0x1800179a8  nop     dword ptr [rax+rax+00h]
0x1800179ad  mov     rcx, rax; hHeap
0x1800179b0  mov     r8, rsi; lpMem
0x1800179b3  xor     edx, edx; dwFlags
0x1800179b5  call    cs:__imp_HeapFree
0x1800179bc  nop     dword ptr [rax+rax+00h]
0x1800179c1  mov     rbx, [rbp+57h+var_88]
0x1800179c5  mov     eax, [rbp+57h+var_68]
0x1800179c8  mov     [r15], eax
0x1800179cb  test    byte ptr [rbp+57h+var_80], 80h
0x1800179cf  jz      short loc_1800179D5
0x1800179d1  or      qword ptr [rdi], 20h
0x1800179d5  test    byte ptr [rbp+57h+var_80], 10h
0x1800179d9  jz      short loc_1800179DF
0x1800179db  or      qword ptr [rdi], 10h
0x1800179df  mov     [rbp+57h+var_88], r13
0x1800179e3  test    rbx, rbx
0x1800179e6  jz      short loc_180017A09
0x1800179e8  call    cs:__imp_GetProcessHeap
0x1800179ef  nop     dword ptr [rax+rax+00h]
0x1800179f4  mov     rcx, rax; hHeap
0x1800179f7  mov     r8, rbx; lpMem
0x1800179fa  xor     edx, edx; dwFlags
0x1800179fc  call    cs:__imp_HeapFree
0x180017a03  nop     dword ptr [rax+rax+00h]
0x180017a08  nop
0x180017a09  mov     rbx, [rbp+57h+var_90]
0x180017a0d  mov     [rbp+57h+var_90], r13
0x180017a11  test    rbx, rbx
0x180017a14  jz      short loc_180017A37
0x180017a16  call    cs:__imp_GetProcessHeap
0x180017a1d  nop     dword ptr [rax+rax+00h]
0x180017a22  mov     rcx, rax; hHeap
0x180017a25  mov     r8, rbx; lpMem
0x180017a28  xor     edx, edx; dwFlags
0x180017a2a  call    cs:__imp_HeapFree
0x180017a31  nop     dword ptr [rax+rax+00h]
0x180017a36  nop
0x180017a37  mov     rbx, [rbp+57h+lpMem]
0x180017a3b  test    rbx, rbx
0x180017a3e  jz      short loc_180017A60
0x180017a40  call    cs:__imp_GetProcessHeap
0x180017a47  nop     dword ptr [rax+rax+00h]
0x180017a4c  mov     rcx, rax; hHeap
0x180017a4f  mov     r8, rbx; lpMem
0x180017a52  xor     edx, edx; dwFlags
0x180017a54  call    cs:__imp_HeapFree
0x180017a5b  nop     dword ptr [rax+rax+00h]
0x180017a60  xor     eax, eax
0x180017a62  add     rsp, 0B8h
0x180017a69  pop     r15
0x180017a6b  pop     r14
0x180017a6d  pop     r13
0x180017a6f  pop     r12
0x180017a71  pop     rdi
0x180017a72  pop     rsi
0x180017a73  pop     rbx
0x180017a74  pop     rbp
0x180017a75  retn
```
