# AssertScopeName

- ea: `0x1800308f4`
- end: `0x180030b8b`
- name: `AssertScopeName`
- size: `663`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800339ec`
- `0x180033aac`
- `0x180034e88`
- `0x1800351bc`
- `0x180035b58`

## callees

- `0x18000ac60`
- `0x1800124e8`
- `0x1800308f4`
- `0x180031e54`
- `0x1800335b0`
- `0x18003a1c4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180030a24`
- `KERNEL32!HeapFree` at `0x180030a24`
- `KERNEL32!HeapAlloc` at `0x1800309d3`
- `KERNEL32!HeapAlloc` at `0x180030a4c`
- `KERNEL32!HeapAlloc` at `0x1800309d3`
- `KERNEL32!HeapAlloc` at `0x180030a4c`

## string_xrefs

- `0x180030b15`: `Updated scope name for "%hs": %ws (%d.%d.%d.%d/%d)`

## pseudocode

```c
__int64 __fastcall AssertScopeName(__int64 a1, unsigned __int16 a2, wchar_t *a3)
{
  __int64 *v6; // rsi
  __int64 *i; // rbx
  wchar_t *v8; // rax
  int v9; // ecx
  int v10; // edx
  __int64 *v11; // rdi
  __int64 *v12; // rax
  __int64 **v13; // rax
  void *v14; // r8
  __int64 v15; // rbx
  __int64 v16; // r8
  wchar_t *v17; // rax
  __int64 v19; // rcx
  unsigned __int8 v20; // al
  int v21; // edi
  int v22; // esi
  int v23; // ebp
  int v24; // r14d
  int v25; // ebx
  __int64 LangName; // rax
  int v27; // [rsp+50h] [rbp-A48h] BYREF
  _BYTE v28[2044]; // [rsp+54h] [rbp-A44h] BYREF
  wchar_t pszDest[256]; // [rsp+850h] [rbp-248h] BYREF

  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v6 = (__int64 *)(a1 + 32);
  for ( i = *(__int64 **)(a1 + 32); ; i = (__int64 *)*i )
  {
    if ( i == v6 )
    {
      i = 0;
      goto LABEL_13;
    }
    if ( a2 == *((_WORD *)i + 8) )
      break;
  }
  if ( !i || !a3 )
  {
LABEL_13:
    v11 = i;
    if ( a3 )
    {
LABEL_14:
      if ( *a3 )
        goto LABEL_16;
    }
    MakePrefixStringW(pszDest);
    a3 = pszDest;
LABEL_16:
    if ( !i )
    {
      v12 = (__int64 *)HeapAlloc(IPRouterHeap, 0, 0x28u);
      v11 = v12;
      if ( !v12 )
        return 8;
      *((_DWORD *)v12 + 8) = 0;
      v12[3] = 0;
      *((_WORD *)v12 + 8) = a2;
      v13 = *(__int64 ***)(a1 + 40);
      if ( *v13 != v6 )
        __fastfail(3u);
      *v11 = (__int64)v6;
      v11[1] = (__int64)v13;
      *v13 = v11;
      *(_QWORD *)(a1 + 40) = v11;
      ++*(_DWORD *)(a1 + 28);
    }
    v14 = (void *)v11[3];
    if ( v14 )
      HeapFree(IPRouterHeap, 0, v14);
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    v17 = (wchar_t *)HeapAlloc(IPRouterHeap, 0, 2 * v16 + 2);
    v11[3] = (__int64)v17;
    if ( v17 )
    {
      do
        ++v15;
      while ( a3[v15] );
      StringCbCopyW(v17, 2 * v15 + 2, a3);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v19 = *(unsigned int *)(a1 + 20);
        LOWORD(v27) = 0;
        v20 = MaskToMaskLen(v19);
        v21 = *(unsigned __int8 *)(a1 + 19);
        v22 = *(unsigned __int8 *)(a1 + 18);
        v23 = *(unsigned __int8 *)(a1 + 17);
        v24 = (unsigned __int8)*(_DWORD *)(a1 + 16);
        v25 = v20;
        LangName = GetLangName(a2);
        FormatRRASErrorString(
          &v27,
          L"Updated scope name for \"%hs\": %ws (%d.%d.%d.%d/%d)",
          LangName,
          a3,
          v24,
          v23,
          v22,
          v21,
          v25);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v27);
      }
      return 0;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v27) = 0;
      do
        ++v15;
      while ( a3[v15] );
      FormatRRASErrorString(&v27, L"Error %d allocating %d bytes for scope name %ws", 8, v15 + 1, a3);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v27);
    }
    return 8;
  }
  v8 = a3;
  do
  {
    v9 = *(wchar_t *)((char *)v8 + i[3] - (_QWORD)a3);
    v10 = *v8 - v9;
    if ( v10 )
      break;
    ++v8;
  }
  while ( v9 );
  if ( v10 )
  {
    v11 = i;
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x1800308f4  mov     [rsp+arg_18], rbx
0x1800308f9  push    rbp
0x1800308fa  push    rsi
0x1800308fb  push    rdi
0x1800308fc  push    r12
0x1800308fe  push    r13
0x180030900  push    r14
0x180030902  push    r15
0x180030904  sub     rsp, 0A60h
0x18003090b  mov     rax, cs:__security_cookie
0x180030912  xor     rax, rsp
0x180030915  mov     [rsp+0A98h+var_48], rax
0x18003091d  mov     r15, r8
0x180030920  movzx   r12d, dx
0x180030924  mov     r14, rcx
0x180030927  xor     r13d, r13d
0x18003092a  xor     edx, edx; Val
0x18003092c  mov     [rsp+0A98h+var_A48], r13d
0x180030931  mov     r8d, 7FCh; Size
0x180030937  lea     rcx, [rsp+0A98h+var_A44]; void *
0x18003093c  call    memset_0
0x180030941  lea     rsi, [r14+20h]
0x180030945  mov     rbx, [rsi]
0x180030948  cmp     rbx, rsi
0x18003094b  jz      short loc_18003098E
0x18003094d  cmp     r12w, [rbx+10h]
0x180030952  jz      short loc_180030959
0x180030954  mov     rbx, [rbx]
0x180030957  jmp     short loc_180030948
0x180030959  test    rbx, rbx
0x18003095c  jz      short loc_180030991
0x18003095e  test    r15, r15
0x180030961  jz      short loc_180030991
0x180030963  mov     r8, [rbx+18h]
0x180030967  mov     rax, r15
0x18003096a  sub     r8, r15
0x18003096d  movzx   edx, word ptr [rax]
0x180030970  movzx   ecx, word ptr [rax+r8]
0x180030975  sub     edx, ecx
0x180030977  jnz     short loc_180030981
0x180030979  add     rax, 2
0x18003097d  test    ecx, ecx
0x18003097f  jnz     short loc_18003096D
0x180030981  test    edx, edx
0x180030983  jz      loc_180030B5E
0x180030989  mov     rdi, rbx
0x18003098c  jmp     short loc_180030999
0x18003098e  mov     rbx, r13
0x180030991  mov     rdi, rbx
0x180030994  test    r15, r15
0x180030997  jz      short loc_18003099F
0x180030999  cmp     [r15], r13w
0x18003099d  jnz     short loc_1800309BC
0x18003099f  mov     r9d, [r14+14h]
0x1800309a3  lea     rcx, [rsp+0A98h+pszDest]; pszDest
0x1800309ab  mov     r8d, [r14+10h]
0x1800309af  call    MakePrefixStringW
0x1800309b4  lea     r15, [rsp+0A98h+pszDest]
0x1800309bc  mov     ebp, 8
0x1800309c1  test    rbx, rbx
0x1800309c4  jnz     short loc_180030A12
0x1800309c6  mov     rcx, cs:IPRouterHeap; hHeap
0x1800309cd  lea     r8d, [rbp+20h]; dwBytes
0x1800309d1  xor     edx, edx; dwFlags
0x1800309d3  call    cs:__imp_HeapAlloc
0x1800309d9  mov     rdi, rax
0x1800309dc  test    rax, rax
0x1800309df  jz      loc_180030AB2
0x1800309e5  mov     [rax+20h], r13d
0x1800309e9  mov     [rax+18h], r13
0x1800309ed  mov     [rax+10h], r12w
0x1800309f2  mov     rax, [rsi+8]
0x1800309f6  cmp     [rax], rsi
0x1800309f9  jz      short loc_180030A00
0x1800309fb  lea     ecx, [rbp-5]
0x1800309fe  int     29h; Win8: RtlFailFast(ecx)
0x180030a00  mov     [rdi], rsi
0x180030a03  mov     [rdi+8], rax
0x180030a07  mov     [rax], rdi
0x180030a0a  mov     [rsi+8], rdi
0x180030a0e  inc     dword ptr [r14+1Ch]
0x180030a12  mov     r8, [rdi+18h]; lpMem
0x180030a16  test    r8, r8
0x180030a19  jz      short loc_180030A2A
0x180030a1b  mov     rcx, cs:IPRouterHeap; hHeap
0x180030a22  xor     edx, edx; dwFlags
0x180030a24  call    cs:__imp_HeapFree
0x180030a2a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030a2e  mov     r8, rbx
0x180030a31  inc     r8
0x180030a34  cmp     [r15+r8*2], r13w
0x180030a39  jnz     short loc_180030A31
0x180030a3b  mov     rcx, cs:IPRouterHeap; hHeap
0x180030a42  lea     r8, ds:2[r8*2]; dwBytes
0x180030a4a  xor     edx, edx; dwFlags
0x180030a4c  call    cs:__imp_HeapAlloc
0x180030a52  mov     [rdi+18h], rax
0x180030a56  test    rax, rax
0x180030a59  jnz     short loc_180030AB9
0x180030a5b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180030a62  jz      short loc_180030AB2
0x180030a64  mov     word ptr [rsp+0A98h+var_A48], r13w
0x180030a6a  inc     rbx
0x180030a6d  cmp     [r15+rbx*2], r13w
0x180030a72  jnz     short loc_180030A6A
0x180030a74  lea     r9, [rbx+1]
0x180030a78  mov     [rsp+0A98h+var_A78], r15
0x180030a7d  mov     r8d, ebp
0x180030a80  lea     rdx, aErrorDAllocati; "Error %d allocating %d bytes for scope "...
0x180030a87  lea     rcx, [rsp+0A98h+var_A48]
0x180030a8c  call    FormatRRASErrorString
0x180030a91  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180030a98  jz      short loc_180030AB2
0x180030a9a  lea     r8, [rsp+0A98h+var_A48]
0x180030a9f  lea     rdx, RasRtrMgrTraceError
0x180030aa6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180030aad  call    McTemplateU0z_EventWriteTransfer
0x180030ab2  mov     eax, ebp
0x180030ab4  jmp     loc_180030B60
0x180030ab9  inc     rbx
0x180030abc  cmp     [r15+rbx*2], r13w
0x180030ac1  jnz     short loc_180030AB9
0x180030ac3  lea     rdx, ds:2[rbx*2]; cbDest
0x180030acb  mov     r8, r15; pszSrc
0x180030ace  mov     rcx, rax; pszDest
0x180030ad1  call    StringCbCopyW
0x180030ad6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180030add  jge     short loc_180030B5E
0x180030adf  mov     ecx, [r14+14h]
0x180030ae3  mov     word ptr [rsp+0A98h+var_A48], r13w
0x180030ae9  call    MaskToMaskLen
0x180030aee  movzx   edi, byte ptr [r14+13h]
0x180030af3  movzx   ecx, r12w
0x180030af7  movzx   esi, byte ptr [r14+12h]
0x180030afc  movzx   ebp, byte ptr [r14+11h]
0x180030b01  mov     r14d, [r14+10h]
0x180030b05  movzx   r14d, r14b
0x180030b09  movzx   ebx, al
0x180030b0c  call    GetLangName
0x180030b11  mov     [rsp+0A98h+var_A58], ebx
0x180030b15  lea     rdx, aUpdatedScopeNa; "Updated scope name for \"%hs\": %ws (%d"...
0x180030b1c  mov     [rsp+0A98h+var_A60], edi
0x180030b20  lea     rcx, [rsp+0A98h+var_A48]
0x180030b25  mov     [rsp+0A98h+var_A68], esi
0x180030b29  mov     r8, rax
0x180030b2c  mov     [rsp+0A98h+var_A70], ebp
0x180030b30  mov     r9, r15
0x180030b33  mov     dword ptr [rsp+0A98h+var_A78], r14d
0x180030b38  call    FormatRRASErrorString
0x180030b3d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180030b44  jge     short loc_180030B5E
0x180030b46  lea     r8, [rsp+0A98h+var_A48]
0x180030b4b  lea     rdx, RasRtrmgrTraceInfo
0x180030b52  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180030b59  call    McTemplateU0z_EventWriteTransfer
0x180030b5e  xor     eax, eax
0x180030b60  mov     rcx, [rsp+0A98h+var_48]
0x180030b68  xor     rcx, rsp; StackCookie
0x180030b6b  call    __security_check_cookie
0x180030b70  mov     rbx, [rsp+0A98h+arg_18]
0x180030b78  add     rsp, 0A60h
0x180030b7f  pop     r15
0x180030b81  pop     r14
0x180030b83  pop     r13
0x180030b85  pop     r12
0x180030b87  pop     rdi
0x180030b88  pop     rsi
0x180030b89  pop     rbp
0x180030b8a  retn
```
