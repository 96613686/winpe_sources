# WriteMultiSzToRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)

- ea: `0x180045228`
- end: `0x18004542a`
- name: `?WriteMultiSzToRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z`
- size: `514`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, struct _MPRI_STRING_LIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003f420`

## callees

- `0x180045228`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180045371`
- `msvcrt!wcscpy_s` at `0x180045371`
- `msvcrt!malloc` at `0x1800452e1`
- `msvcrt!malloc` at `0x1800452e1`
- `msvcrt!free` at `0x1800453ea`
- `msvcrt!free` at `0x1800453ea`
- `ADVAPI32!RegSetValueExW` at `0x1800453d8`
- `ADVAPI32!RegSetValueExW` at `0x1800453d8`

## string_xrefs

- `0x1800452b8`: `WriteMultiSzToRegistry`
- `0x180045312`: `WriteMultiSzToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteMultiSzToRegistry(HKEY a1, const unsigned __int16 *a2, struct _MPRI_STRING_LIST *a3)
{
  HKEY v4; // r14
  BYTE *lpData; // rbx
  unsigned int v6; // r13d
  void (*v7)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v8; // edi
  int v9; // r15d
  unsigned int v10; // r14d
  wchar_t *v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h]
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h]
  __int128 v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  int v23; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v4 = a1;
  hKey = a1;
  v15 = 0;
  lpData = 0;
  v6 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v17, L"WriteMultiSzToRegistry", &v15, v7);
  v8 = *(_DWORD *)a3;
  if ( !*(_DWORD *)a3 || (v6 = 513 * v8 + 1, (lpData = (BYTE *)malloc(2LL * v6)) != 0) )
  {
    v9 = 0;
    if ( v8 )
    {
      v10 = 0;
      v11 = (wchar_t *)lpData;
      do
      {
        wcscpy_s(v11, v6 - v9, (const wchar_t *)(*((_QWORD *)a3 + 1) + 1026LL * v10));
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        v11 += v12 + 1;
        v9 += v12 + 1;
        ++v10;
        v8 = *(_DWORD *)a3;
      }
      while ( v10 < *(_DWORD *)a3 );
      v4 = hKey;
    }
    else
    {
      v11 = (wchar_t *)lpData;
    }
    if ( v8 )
    {
      *v11 = 0;
      v15 = RegSetValueExW(v4, L"TenantIDs", 0, 7u, lpData, 2 * v9 + 2);
    }
    if ( lpData )
      free(lpData);
  }
  else
  {
    v15 = 8;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"%s: malloc (%ws) failed: %d.", L"WriteMultiSzToRegistry", L"TenantIDs", 8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v23);
    }
  }
  v13 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v13;
}

```

## disassembly

```asm
0x180045228  mov     [rsp-8+arg_8], rbx
0x18004522d  push    rbp
0x18004522e  push    rsi
0x18004522f  push    rdi
0x180045230  push    r12
0x180045232  push    r13
0x180045234  push    r14
0x180045236  push    r15
0x180045238  lea     rbp, [rsp-790h]
0x180045240  sub     rsp, 890h
0x180045247  mov     rax, cs:__security_cookie
0x18004524e  xor     rax, rsp
0x180045251  mov     [rbp+7C0h+var_40], rax
0x180045258  mov     r12, r8
0x18004525b  mov     r14, rcx
0x18004525e  mov     [rsp+8C0h+hKey], rcx
0x180045263  xor     esi, esi
0x180045265  mov     [rsp+8C0h+var_890], esi
0x180045269  mov     ebx, esi
0x18004526b  mov     r13d, esi
0x18004526e  mov     [rbp+7C0h+var_840], esi
0x180045271  xor     edx, edx; Val
0x180045273  mov     r8d, 7FCh; Size
0x180045279  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18004527d  call    memset_0
0x180045282  xorps   xmm0, xmm0
0x180045285  movdqu  [rsp+8C0h+var_878], xmm0
0x18004528b  mov     [rsp+8C0h+var_880], rsi
0x180045290  xorps   xmm1, xmm1
0x180045293  movdqu  [rsp+8C0h+var_868], xmm1
0x180045299  mov     [rsp+8C0h+var_858], rsi
0x18004529e  mov     [rsp+8C0h+var_850], 0FFFFFFFFh
0x1800452a6  mov     [rsp+8C0h+var_84C], esi
0x1800452aa  cmp     qword ptr cs:xmmword_180071090+8, rsi
0x1800452b1  jz      short loc_1800452C9
0x1800452b3  lea     r8, [rsp+8C0h+var_890]; unsigned int *
0x1800452b8  lea     rdx, aWritemultiszto; "WriteMultiSzToRegistry"
0x1800452bf  lea     rcx, [rsp+8C0h+var_880]; this
0x1800452c4  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800452c9  mov     edi, [r12]
0x1800452cd  test    edi, edi
0x1800452cf  jz      short loc_18004534C
0x1800452d1  imul    r13d, edi, 201h
0x1800452d8  inc     r13d
0x1800452db  mov     ecx, r13d
0x1800452de  add     rcx, rcx; Size
0x1800452e1  call    cs:__imp_malloc
0x1800452e7  mov     rbx, rax
0x1800452ea  test    rax, rax
0x1800452ed  jnz     short loc_18004534C
0x1800452ef  lea     ecx, [rax+8]
0x1800452f2  mov     [rsp+8C0h+var_890], ecx
0x1800452f6  cmp     qword ptr cs:xmmword_180071090, rsi
0x1800452fd  jz      loc_1800453F0
0x180045303  mov     word ptr [rbp+7C0h+var_840], si
0x180045307  mov     dword ptr [rsp+8C0h+lpData], ecx
0x18004530b  lea     r9, aTenantids; "TenantIDs"
0x180045312  lea     r8, aWritemultiszto; "WriteMultiSzToRegistry"
0x180045319  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x180045320  lea     rcx, [rbp+7C0h+var_840]
0x180045324  call    FormatRRASErrorString
0x180045329  lea     r8, [rbp+7C0h+var_840]
0x18004532d  mov     rdx, qword ptr cs:xmmword_180071090
0x180045334  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004533b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180045342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045347  jmp     loc_1800453F0
0x18004534c  mov     r15d, esi
0x18004534f  test    edi, edi
0x180045351  jz      short loc_1800453A7
0x180045353  mov     r14d, esi
0x180045356  mov     rsi, rbx
0x180045359  mov     eax, r14d
0x18004535c  imul    r8, rax, 402h
0x180045363  add     r8, [r12+8]; Source
0x180045368  mov     edx, r13d
0x18004536b  sub     edx, r15d; SizeInWords
0x18004536e  mov     rcx, rsi; Destination
0x180045371  call    cs:__imp_wcscpy_s
0x180045377  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004537b  xor     ecx, ecx
0x18004537d  inc     rax
0x180045380  cmp     [rsi+rax*2], cx
0x180045384  jnz     short loc_18004537D
0x180045386  lea     rsi, [rsi+rax*2]
0x18004538a  add     rsi, 2
0x18004538e  inc     r15d
0x180045391  add     r15d, eax
0x180045394  inc     r14d
0x180045397  mov     edi, [r12]
0x18004539b  cmp     r14d, edi
0x18004539e  jb      short loc_180045359
0x1800453a0  mov     r14, [rsp+8C0h+hKey]
0x1800453a5  jmp     short loc_1800453AA
0x1800453a7  mov     rsi, rbx
0x1800453aa  xor     r12d, r12d
0x1800453ad  test    edi, edi
0x1800453af  jz      short loc_1800453E2
0x1800453b1  mov     [rsi], r12w
0x1800453b5  lea     eax, ds:2[r15*2]
0x1800453bd  mov     [rsp+8C0h+cbData], eax; cbData
0x1800453c1  mov     [rsp+8C0h+lpData], rbx; lpData
0x1800453c6  lea     r9d, [r12+7]; dwType
0x1800453cb  xor     r8d, r8d; Reserved
0x1800453ce  lea     rdx, aTenantids; "TenantIDs"
0x1800453d5  mov     rcx, r14; hKey
0x1800453d8  call    cs:__imp_RegSetValueExW
0x1800453de  mov     [rsp+8C0h+var_890], eax
0x1800453e2  test    rbx, rbx
0x1800453e5  jz      short loc_1800453F0
0x1800453e7  mov     rcx, rbx; Block
0x1800453ea  call    cs:__imp_free
0x1800453f0  mov     ebx, [rsp+8C0h+var_890]
0x1800453f4  lea     rcx, [rsp+8C0h+var_880]; this
0x1800453f9  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800453fe  mov     eax, ebx
0x180045400  mov     rcx, [rbp+7C0h+var_40]
0x180045407  xor     rcx, rsp; StackCookie
0x18004540a  call    __security_check_cookie
0x18004540f  mov     rbx, [rsp+8C0h+arg_8]
0x180045417  add     rsp, 890h
0x18004541e  pop     r15
0x180045420  pop     r14
0x180045422  pop     r13
0x180045424  pop     r12
0x180045426  pop     rdi
0x180045427  pop     rsi
0x180045428  pop     rbp
0x180045429  retn
```
