# RasCreateEapAttributesWithResultTLV

- ea: `0x1800281c8`
- end: `0x18002835d`
- name: `RasCreateEapAttributesWithResultTLV`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180028c84`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800281c8`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002826c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002826c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028244`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028257`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028244`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028257`

## string_xrefs

- `0x180028217`: `RasCreateEapAttributesWithResultTLV -- Entering.`
- `0x1800282e9`: `RasCreateEapAttributesWithResultTLV: Constructed a response attribute.`
- `0x180028287`: `RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.`
- `0x180028307`: `RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.`

## pseudocode

```c
__int64 __fastcall RasCreateEapAttributesWithResultTLV(__int64 a1, __int16 a2)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rdi
  _BYTE *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-834h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
      L"RasCreateEapAttributesWithResultTLV -- Entering.");
  if ( !a1 )
  {
    v4 = 87;
    goto LABEL_9;
  }
  *(_OWORD *)a1 = 0;
  v5 = LocalAlloc(0x40u, 0x10u);
  if ( !v5 )
  {
LABEL_8:
    v4 = 8;
LABEL_9:
    if ( (_QWORD)xmmword_18004C740 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.", v4);
      v7 = xmmword_18004C740;
LABEL_14:
      ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v7, &v10);
      return v4;
    }
    return v4;
  }
  v6 = LocalAlloc(0x40u, 6u);
  *((_QWORD *)v5 + 1) = v6;
  if ( !v6 )
  {
    LocalFree(v5);
    goto LABEL_8;
  }
  *v5 = 8102;
  v4 = 0;
  v5[1] = 6;
  *(_DWORD *)v6 = 33555328;
  v6[4] = HIBYTE(a2);
  v6[5] = a2;
  v8 = *((_QWORD *)&xmmword_18004C740 + 1);
  *(_DWORD *)a1 = 1;
  *(_QWORD *)(a1 + 8) = v5;
  if ( v8 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      v8,
      L"RasCreateEapAttributesWithResultTLV: Constructed a response attribute.");
    if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.", 0);
      v7 = *((_QWORD *)&xmmword_18004C740 + 1);
      goto LABEL_14;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800281c8  push    rbx
0x1800281ca  push    rbp
0x1800281cb  push    rsi
0x1800281cc  push    rdi
0x1800281cd  sub     rsp, 838h
0x1800281d4  mov     rax, cs:__security_cookie
0x1800281db  xor     rax, rsp
0x1800281de  mov     [rsp+858h+var_38], rax
0x1800281e6  movzx   ebp, dx
0x1800281e9  mov     rsi, rcx
0x1800281ec  xor     eax, eax
0x1800281ee  lea     rcx, [rsp+858h+var_834]; void *
0x1800281f3  xor     edx, edx; Val
0x1800281f5  mov     [rsp+858h+var_838], eax
0x1800281f9  mov     r8d, 7FCh; Size
0x1800281ff  call    memset_0
0x180028204  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x18002820b  test    rdx, rdx
0x18002820e  jz      short loc_18002822A
0x180028210  mov     rcx, cs:gRasEapEtwContext
0x180028217  lea     r8, aRascreateeapat_2; "RasCreateEapAttributesWithResultTLV -- "...
0x18002821e  mov     rax, cs:gRasEapTemplateFunc
0x180028225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002822a  test    rsi, rsi
0x18002822d  jnz     short loc_180028234
0x18002822f  lea     ebx, [rsi+57h]
0x180028232  jmp     short loc_180028277
0x180028234  mov     edx, 10h; uBytes
0x180028239  xorps   xmm0, xmm0
0x18002823c  movups  xmmword ptr [rsi], xmm0
0x18002823f  lea     ebx, [rdx+30h]
0x180028242  mov     ecx, ebx; uFlags
0x180028244  call    cs:__imp_LocalAlloc
0x18002824a  mov     rdi, rax
0x18002824d  test    rax, rax
0x180028250  jz      short loc_180028272
0x180028252  lea     edx, [rbx-3Ah]; uBytes
0x180028255  mov     ecx, ebx; uFlags
0x180028257  call    cs:__imp_LocalAlloc
0x18002825d  mov     [rdi+8], rax
0x180028261  mov     rcx, rax
0x180028264  test    rax, rax
0x180028267  jnz     short loc_1800282A9
0x180028269  mov     rcx, rdi; hMem
0x18002826c  call    cs:__imp_LocalFree
0x180028272  mov     ebx, 8
0x180028277  cmp     qword ptr cs:xmmword_18004C740, 0
0x18002827f  jz      loc_18002833F
0x180028285  xor     eax, eax
0x180028287  lea     rdx, aRascreateeapat_0; "RasCreateEapAttributesWithResultTLV: Le"...
0x18002828e  mov     r8d, ebx
0x180028291  mov     word ptr [rsp+858h+var_838], ax
0x180028296  lea     rcx, [rsp+858h+var_838]
0x18002829b  call    FormatRRASErrorString
0x1800282a0  mov     rdx, qword ptr cs:xmmword_18004C740
0x1800282a7  jmp     short loc_180028327
0x1800282a9  mov     dword ptr [rdi], 1FA6h
0x1800282af  xor     ebx, ebx
0x1800282b1  mov     dword ptr [rdi+4], 6
0x1800282b8  mov     dword ptr [rax], 2000380h
0x1800282be  movzx   eax, bp
0x1800282c1  shr     ax, 8
0x1800282c5  mov     [rcx+4], al
0x1800282c8  mov     [rcx+5], bpl
0x1800282cc  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x1800282d3  mov     dword ptr [rsi], 1
0x1800282d9  mov     [rsi+8], rdi
0x1800282dd  test    rdx, rdx
0x1800282e0  jz      short loc_18002833F
0x1800282e2  mov     rcx, cs:gRasEapEtwContext
0x1800282e9  lea     r8, aRascreateeapat_1; "RasCreateEapAttributesWithResultTLV: Co"...
0x1800282f0  mov     rax, cs:gRasEapTemplateFunc
0x1800282f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282fc  cmp     qword ptr cs:xmmword_18004C740+8, rbx
0x180028303  jz      short loc_18002833F
0x180028305  xor     eax, eax
0x180028307  lea     rdx, aRascreateeapat_0; "RasCreateEapAttributesWithResultTLV: Le"...
0x18002830e  xor     r8d, r8d
0x180028311  mov     word ptr [rsp+858h+var_838], ax
0x180028316  lea     rcx, [rsp+858h+var_838]
0x18002831b  call    FormatRRASErrorString
0x180028320  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028327  mov     rcx, cs:gRasEapEtwContext
0x18002832e  lea     r8, [rsp+858h+var_838]
0x180028333  mov     rax, cs:gRasEapTemplateFunc
0x18002833a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002833f  mov     eax, ebx
0x180028341  mov     rcx, [rsp+858h+var_38]
0x180028349  xor     rcx, rsp; StackCookie
0x18002834c  call    __security_check_cookie
0x180028351  add     rsp, 838h
0x180028358  pop     rdi
0x180028359  pop     rsi
0x18002835a  pop     rbp
0x18002835b  pop     rbx
0x18002835c  retn
```
