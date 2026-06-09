# WriteMultiSzToRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)

- ea: `0x180050924`
- end: `0x180050b26`
- name: `?WriteMultiSzToRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, struct _MPRI_STRING_LIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004a9dc`

## callees

- `0x180050924`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!malloc` at `0x1800509dd`
- `msvcrt!malloc` at `0x1800509dd`
- `msvcrt!free` at `0x180050ae6`
- `msvcrt!free` at `0x180050ae6`
- `msvcrt!wcscpy_s` at `0x180050a6d`
- `msvcrt!wcscpy_s` at `0x180050a6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050ad4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050ad4`

## string_xrefs

- `0x1800509b4`: `WriteMultiSzToRegistry`
- `0x180050a0e`: `WriteMultiSzToRegistry`

## pseudocode

```c
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
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
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
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"%s: malloc (%ws) failed: %d.", L"WriteMultiSzToRegistry", L"TenantIDs", 8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
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
0x180050924  mov     [rsp-8+arg_8], rbx
0x180050929  push    rbp
0x18005092a  push    rsi
0x18005092b  push    rdi
0x18005092c  push    r12
0x18005092e  push    r13
0x180050930  push    r14
0x180050932  push    r15
0x180050934  lea     rbp, [rsp-790h]
0x18005093c  sub     rsp, 890h
0x180050943  mov     rax, cs:__security_cookie
0x18005094a  xor     rax, rsp
0x18005094d  mov     [rbp+7C0h+var_40], rax
0x180050954  mov     r12, r8
0x180050957  mov     r14, rcx
0x18005095a  mov     [rsp+8C0h+hKey], rcx
0x18005095f  xor     esi, esi
0x180050961  mov     [rsp+8C0h+var_890], esi
0x180050965  mov     ebx, esi
0x180050967  mov     r13d, esi
0x18005096a  mov     [rbp+7C0h+var_840], esi
0x18005096d  xor     edx, edx; Val
0x18005096f  mov     r8d, 7FCh; Size
0x180050975  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180050979  call    memset_0
0x18005097e  xorps   xmm0, xmm0
0x180050981  movdqu  [rsp+8C0h+var_878], xmm0
0x180050987  mov     [rsp+8C0h+var_880], rsi
0x18005098c  xorps   xmm1, xmm1
0x18005098f  movdqu  [rsp+8C0h+var_868], xmm1
0x180050995  mov     [rsp+8C0h+var_858], rsi
0x18005099a  mov     [rsp+8C0h+var_850], 0FFFFFFFFh
0x1800509a2  mov     [rsp+8C0h+var_84C], esi
0x1800509a6  cmp     qword ptr cs:xmmword_180078C50+8, rsi
0x1800509ad  jz      short loc_1800509C5
0x1800509af  lea     r8, [rsp+8C0h+var_890]; unsigned int *
0x1800509b4  lea     rdx, aWritemultiszto; "WriteMultiSzToRegistry"
0x1800509bb  lea     rcx, [rsp+8C0h+var_880]; this
0x1800509c0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800509c5  mov     edi, [r12]
0x1800509c9  test    edi, edi
0x1800509cb  jz      short loc_180050A48
0x1800509cd  imul    r13d, edi, 201h
0x1800509d4  inc     r13d
0x1800509d7  mov     ecx, r13d
0x1800509da  add     rcx, rcx; Size
0x1800509dd  call    cs:__imp_malloc
0x1800509e3  mov     rbx, rax
0x1800509e6  test    rax, rax
0x1800509e9  jnz     short loc_180050A48
0x1800509eb  lea     ecx, [rax+8]
0x1800509ee  mov     [rsp+8C0h+var_890], ecx
0x1800509f2  cmp     qword ptr cs:xmmword_180078C50, rsi
0x1800509f9  jz      loc_180050AEC
0x1800509ff  mov     word ptr [rbp+7C0h+var_840], si
0x180050a03  mov     dword ptr [rsp+8C0h+lpData], ecx
0x180050a07  lea     r9, aTenantids; "TenantIDs"
0x180050a0e  lea     r8, aWritemultiszto; "WriteMultiSzToRegistry"
0x180050a15  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x180050a1c  lea     rcx, [rbp+7C0h+var_840]
0x180050a20  call    FormatRRASErrorString
0x180050a25  lea     r8, [rbp+7C0h+var_840]
0x180050a29  mov     rdx, qword ptr cs:xmmword_180078C50
0x180050a30  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180050a37  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a43  jmp     loc_180050AEC
0x180050a48  mov     r15d, esi
0x180050a4b  test    edi, edi
0x180050a4d  jz      short loc_180050AA3
0x180050a4f  mov     r14d, esi
0x180050a52  mov     rsi, rbx
0x180050a55  mov     eax, r14d
0x180050a58  imul    r8, rax, 402h
0x180050a5f  add     r8, [r12+8]; Source
0x180050a64  mov     edx, r13d
0x180050a67  sub     edx, r15d; SizeInWords
0x180050a6a  mov     rcx, rsi; Destination
0x180050a6d  call    cs:__imp_wcscpy_s
0x180050a73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050a77  xor     ecx, ecx
0x180050a79  inc     rax
0x180050a7c  cmp     [rsi+rax*2], cx
0x180050a80  jnz     short loc_180050A79
0x180050a82  lea     rsi, [rsi+rax*2]
0x180050a86  add     rsi, 2
0x180050a8a  inc     r15d
0x180050a8d  add     r15d, eax
0x180050a90  inc     r14d
0x180050a93  mov     edi, [r12]
0x180050a97  cmp     r14d, edi
0x180050a9a  jb      short loc_180050A55
0x180050a9c  mov     r14, [rsp+8C0h+hKey]
0x180050aa1  jmp     short loc_180050AA6
0x180050aa3  mov     rsi, rbx
0x180050aa6  xor     r12d, r12d
0x180050aa9  test    edi, edi
0x180050aab  jz      short loc_180050ADE
0x180050aad  mov     [rsi], r12w
0x180050ab1  lea     eax, ds:2[r15*2]
0x180050ab9  mov     [rsp+8C0h+cbData], eax; cbData
0x180050abd  mov     [rsp+8C0h+lpData], rbx; lpData
0x180050ac2  lea     r9d, [r12+7]; dwType
0x180050ac7  xor     r8d, r8d; Reserved
0x180050aca  lea     rdx, aTenantids; "TenantIDs"
0x180050ad1  mov     rcx, r14; hKey
0x180050ad4  call    cs:__imp_RegSetValueExW
0x180050ada  mov     [rsp+8C0h+var_890], eax
0x180050ade  test    rbx, rbx
0x180050ae1  jz      short loc_180050AEC
0x180050ae3  mov     rcx, rbx; Block
0x180050ae6  call    cs:__imp_free
0x180050aec  mov     ebx, [rsp+8C0h+var_890]
0x180050af0  lea     rcx, [rsp+8C0h+var_880]; this
0x180050af5  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180050afa  mov     eax, ebx
0x180050afc  mov     rcx, [rbp+7C0h+var_40]
0x180050b03  xor     rcx, rsp; StackCookie
0x180050b06  call    __security_check_cookie
0x180050b0b  mov     rbx, [rsp+8C0h+arg_8]
0x180050b13  add     rsp, 890h
0x180050b1a  pop     r15
0x180050b1c  pop     r14
0x180050b1e  pop     r13
0x180050b20  pop     r12
0x180050b22  pop     rdi
0x180050b23  pop     rsi
0x180050b24  pop     rbp
0x180050b25  retn
```
