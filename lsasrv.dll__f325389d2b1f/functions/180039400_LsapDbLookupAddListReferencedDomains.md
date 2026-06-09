# LsapDbLookupAddListReferencedDomains

- ea: `0x180039400`
- end: `0x180039657`
- name: `LsapDbLookupAddListReferencedDomains`
- size: `599`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011cdc`
- `0x18003699c`
- `0x180037a54`
- `0x1800381b4`
- `0x1800385a8`
- `0x180038618`
- `0x1800388a0`
- `0x180038e14`
- `0x18003915c`
- `0x180039d24`
- `0x180061e88`
- `0x180064628`
- `0x180086cf8`
- `0x18008d958`
- `0x180097624`
- `0x1800f4928`
- `0x180103000`
- `0x18010313c`
- `0x1801065e4`

## callees

- `0x180039400`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003963b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039649`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003963b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039649`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039474`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800394cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003951f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039474`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800394cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003951f`
- `ntdll!RtlCopyUnicodeString` at `0x1800394ef`
- `ntdll!RtlCopyUnicodeString` at `0x1800394ef`
- `ntdll!RtlLengthSid` at `0x18003950a`
- `ntdll!RtlLengthSid` at `0x18003950a`
- `ntdll!RtlEqualSid` at `0x1800395bc`
- `ntdll!RtlEqualSid` at `0x1800395bc`

## pseudocode

```c
__int64 __fastcall LsapDbLookupAddListReferencedDomains(unsigned int *a1, unsigned __int64 *a2, signed int *a3)
{
  void *v6; // rbp
  signed int v7; // esi
  signed int v8; // edi
  __int64 v9; // r15
  unsigned int v10; // esi
  unsigned int v11; // edi
  HLOCAL v12; // rax
  HLOCAL v13; // rbp
  void *v14; // r15
  WCHAR *v15; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rbp
  unsigned __int64 v18; // rcx
  WCHAR *Buffer; // rax
  const void *v20; // rdi
  ULONG v21; // esi
  HLOCAL v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 result; // rax
  void *v26; // rcx
  struct _UNICODE_STRING DestinationString[2]; // [rsp+20h] [rbp-48h] BYREF

  memset(DestinationString, 0, 24);
  if ( !a1 )
    return 3221225485LL;
  v6 = (void *)a2[2];
  v7 = *a1;
  v8 = 0;
  v9 = *((_QWORD *)a1 + 1);
  *a3 = -1;
  while ( v8 < v7 && v6 )
  {
    v26 = *(void **)(v9 + 24LL * v8 + 16);
    if ( v26 && RtlEqualSid(v26, v6) )
    {
      result = 0;
      *a3 = v8;
      return result;
    }
    ++v8;
  }
  v10 = a1[4];
  if ( *a1 >= v10 )
  {
    v11 = v10 + 32;
    if ( v10 < v10 + 32 )
    {
      v12 = LocalAlloc(0x40u, 24 * v11);
      v13 = v12;
      if ( !v12 )
      {
LABEL_25:
        Buffer = DestinationString[0].Buffer;
        goto LABEL_26;
      }
      v14 = (void *)*((_QWORD *)a1 + 1);
      if ( v14 )
      {
        memcpy_0(v12, *((const void **)a1 + 1), 24 * v10);
        LocalFree(v14);
      }
      *((_QWORD *)a1 + 1) = v13;
      a1[4] = v11;
    }
  }
  v15 = (WCHAR *)a2[1];
  v16 = *a2;
  v17 = *a1;
  *(_QWORD *)&DestinationString[0].Length = *a2;
  DestinationString[0].Buffer = v15;
  if ( !v15 )
  {
LABEL_14:
    v20 = (const void *)a2[2];
    if ( !v20 )
    {
LABEL_17:
      v23 = *((_QWORD *)a1 + 1);
      v24 = 3 * v17;
      result = 0;
      *(struct _UNICODE_STRING *)(v23 + 8 * v24) = DestinationString[0];
      *(_QWORD *)(v23 + 8 * v24 + 16) = *(_QWORD *)&DestinationString[1].Length;
      *a3 = v17;
      ++*a1;
      return result;
    }
    v21 = RtlLengthSid((PSID)a2[2]);
    v22 = LocalAlloc(0x40u, v21);
    *(_QWORD *)&DestinationString[1].Length = v22;
    if ( v22 )
    {
      memcpy_0(v22, v20, v21);
      goto LABEL_17;
    }
    goto LABEL_25;
  }
  v18 = v16 >> 16;
  if ( !(_WORD)v18 )
  {
    DestinationString[0].Buffer = 0;
    goto LABEL_14;
  }
  Buffer = (WCHAR *)LocalAlloc(0x40u, (unsigned __int16)v18);
  DestinationString[0].Buffer = Buffer;
  if ( Buffer )
  {
    RtlCopyUnicodeString(DestinationString, (PCUNICODE_STRING)a2);
    goto LABEL_14;
  }
LABEL_26:
  if ( Buffer )
    LocalFree(Buffer);
  if ( *(_QWORD *)&DestinationString[1].Length )
    LocalFree(*(HLOCAL *)&DestinationString[1].Length);
  return 3221225626LL;
}

```

## disassembly

```asm
0x180039400  mov     rax, rsp
0x180039403  push    rbx
0x180039404  push    r12
0x180039406  push    r13
0x180039408  push    r14
0x18003940a  sub     rsp, 48h
0x18003940e  xor     r13d, r13d
0x180039411  xorps   xmm0, xmm0
0x180039414  mov     [rax-48h], r13
0x180039418  mov     r12, r8
0x18003941b  mov     r14, rdx
0x18003941e  mov     rbx, rcx
0x180039421  movdqu  xmmword ptr [rax-40h], xmm0
0x180039426  test    rcx, rcx
0x180039429  jz      loc_1800395D5
0x18003942f  mov     [rax+8], rbp
0x180039433  mov     rbp, [rdx+10h]
0x180039437  mov     [rax+10h], rsi
0x18003943b  mov     esi, [rcx]
0x18003943d  mov     [rax+18h], rdi
0x180039441  mov     edi, r13d
0x180039444  mov     [rax-28h], r15
0x180039448  mov     r15, [rcx+8]
0x18003944c  mov     dword ptr [r8], 0FFFFFFFFh
0x180039453  cmp     edi, esi
0x180039455  jl      loc_180039598
0x18003945b  mov     esi, [rbx+10h]
0x18003945e  cmp     [rbx], esi
0x180039460  jb      short loc_1800394A0
0x180039462  lea     edi, [rsi+20h]
0x180039465  cmp     esi, edi
0x180039467  jnb     short loc_1800394A0
0x180039469  lea     edx, [rdi+rdi*2]
0x18003946c  mov     ecx, 40h ; '@'; uFlags
0x180039471  shl     edx, 3; uBytes
0x180039474  call    cs:__imp_LocalAlloc
0x18003947b  nop     dword ptr [rax+rax+00h]
0x180039480  mov     rbp, rax
0x180039483  test    rax, rax
0x180039486  jz      loc_1800395F1
0x18003948c  mov     r15, [rbx+8]
0x180039490  test    r15, r15
0x180039493  jnz     loc_180039611
0x180039499  mov     [rbx+8], rbp
0x18003949d  mov     [rbx+10h], edi
0x1800394a0  mov     rax, [r14+8]
0x1800394a4  mov     rcx, [r14]
0x1800394a7  mov     ebp, [rbx]
0x1800394a9  mov     qword ptr [rsp+68h+DestinationString.Length], rcx
0x1800394ae  mov     [rsp+68h+DestinationString.Buffer], rax
0x1800394b3  test    rax, rax
0x1800394b6  jz      short loc_1800394FB
0x1800394b8  shr     rcx, 10h
0x1800394bc  test    cx, cx
0x1800394bf  jz      loc_1800395E7
0x1800394c5  movzx   edx, cx; uBytes
0x1800394c8  mov     ecx, 40h ; '@'; uFlags
0x1800394cd  call    cs:__imp_LocalAlloc
0x1800394d4  nop     dword ptr [rax+rax+00h]
0x1800394d9  mov     [rsp+68h+DestinationString.Buffer], rax
0x1800394de  test    rax, rax
0x1800394e1  jz      loc_1800395F6
0x1800394e7  mov     rdx, r14; SourceString
0x1800394ea  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800394ef  call    cs:__imp_RtlCopyUnicodeString
0x1800394f6  nop     dword ptr [rax+rax+00h]
0x1800394fb  mov     rdi, [r14+10h]
0x1800394ff  mov     r15d, r13d
0x180039502  test    rdi, rdi
0x180039505  jz      short loc_180039547
0x180039507  mov     rcx, rdi; Sid
0x18003950a  call    cs:__imp_RtlLengthSid
0x180039511  nop     dword ptr [rax+rax+00h]
0x180039516  mov     edx, eax; uBytes
0x180039518  mov     ecx, 40h ; '@'; uFlags
0x18003951d  mov     esi, eax
0x18003951f  call    cs:__imp_LocalAlloc
0x180039526  nop     dword ptr [rax+rax+00h]
0x18003952b  mov     [rsp+68h+hMem], rax
0x180039530  test    rax, rax
0x180039533  jz      loc_1800395F1
0x180039539  mov     r8d, esi; Size
0x18003953c  mov     rdx, rdi; Src
0x18003953f  mov     rcx, rax; void *
0x180039542  call    memcpy_0
0x180039547  mov     rcx, [rbx+8]
0x18003954b  lea     rdx, ds:0[rbp*2]
0x180039553  movups  xmm0, xmmword ptr [rsp+68h+DestinationString.Length]
0x180039558  add     rdx, rbp
0x18003955b  mov     eax, r15d
0x18003955e  movups  xmmword ptr [rcx+rdx*8], xmm0
0x180039562  movsd   xmm1, [rsp+68h+hMem]
0x180039568  movsd   qword ptr [rcx+rdx*8+10h], xmm1
0x18003956e  mov     [r12], ebp
0x180039572  inc     dword ptr [rbx]
0x180039574  mov     rdi, [rsp+68h+arg_10]
0x18003957c  mov     rsi, [rsp+68h+arg_8]
0x180039581  mov     rbp, [rsp+68h+arg_0]
0x180039586  mov     r15, [rsp+68h+var_28]
0x18003958b  add     rsp, 48h
0x18003958f  pop     r14
0x180039591  pop     r13
0x180039593  pop     r12
0x180039595  pop     rbx
0x180039596  retn
0x180039598  test    rbp, rbp
0x18003959b  jz      loc_18003945B
0x1800395a1  movsxd  rax, edi
0x1800395a4  lea     rcx, [rax+rax*2]
0x1800395a8  mov     rcx, [r15+rcx*8+10h]; Sid1
0x1800395ad  test    rcx, rcx
0x1800395b0  jnz     short loc_1800395B9
0x1800395b2  inc     edi
0x1800395b4  jmp     loc_180039453
0x1800395b9  mov     rdx, rbp; Sid2
0x1800395bc  call    cs:__imp_RtlEqualSid
0x1800395c3  nop     dword ptr [rax+rax+00h]
0x1800395c8  test    al, al
0x1800395ca  jz      short loc_1800395B2
0x1800395cc  mov     eax, r13d
0x1800395cf  mov     [r12], edi
0x1800395d3  jmp     short loc_180039574
0x1800395d5  mov     eax, 0C000000Dh
0x1800395da  add     rsp, 48h
0x1800395de  pop     r14
0x1800395e0  pop     r13
0x1800395e2  pop     r12
0x1800395e4  pop     rbx
0x1800395e5  retn
0x1800395e7  mov     [rsp+68h+DestinationString.Buffer], r13
0x1800395ec  jmp     loc_1800394FB
0x1800395f1  mov     rax, [rsp+68h+DestinationString.Buffer]
0x1800395f6  mov     ebx, 0C000009Ah
0x1800395fb  test    rax, rax
0x1800395fe  jnz     short loc_180039638
0x180039600  mov     rcx, [rsp+68h+hMem]; hMem
0x180039605  test    rcx, rcx
0x180039608  jnz     short loc_180039649
0x18003960a  mov     eax, ebx
0x18003960c  jmp     loc_180039574
0x180039611  lea     r8d, [rsi+rsi*2]
0x180039615  mov     rdx, r15; Src
0x180039618  shl     r8d, 3; Size
0x18003961c  mov     rcx, rbp; void *
0x18003961f  call    memcpy_0
0x180039624  mov     rcx, r15; hMem
0x180039627  call    cs:__imp_LocalFree
0x18003962e  nop     dword ptr [rax+rax+00h]
0x180039633  jmp     loc_180039499
0x180039638  mov     rcx, rax; hMem
0x18003963b  call    cs:__imp_LocalFree
0x180039642  nop     dword ptr [rax+rax+00h]
0x180039647  jmp     short loc_180039600
0x180039649  call    cs:__imp_LocalFree
0x180039650  nop     dword ptr [rax+rax+00h]
0x180039655  jmp     short loc_18003960A
```
