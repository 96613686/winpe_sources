# RasCreateEapAttributesWithResultTLV

- ea: `0x180029094`
- end: `0x18002923c`
- name: `RasCreateEapAttributesWithResultTLV`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180029ba0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180029094`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029144`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029144`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029110`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029129`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029110`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029129`

## string_xrefs

- `0x1800290e3`: `RasCreateEapAttributesWithResultTLV -- Entering.`
- `0x1800291c7`: `RasCreateEapAttributesWithResultTLV: Constructed a response attribute.`
- `0x180029165`: `RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.`
- `0x1800291e5`: `RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.`

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
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
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
    if ( (_QWORD)xmmword_18004D740 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.", v4);
      v7 = xmmword_18004D740;
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
  v8 = *((_QWORD *)&xmmword_18004D740 + 1);
  *(_DWORD *)a1 = 1;
  *(_QWORD *)(a1 + 8) = v5;
  if ( v8 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      v8,
      L"RasCreateEapAttributesWithResultTLV: Constructed a response attribute.");
    if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.", 0);
      v7 = *((_QWORD *)&xmmword_18004D740 + 1);
      goto LABEL_14;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180029094  push    rbx
0x180029096  push    rbp
0x180029097  push    rsi
0x180029098  push    rdi
0x180029099  sub     rsp, 838h
0x1800290a0  mov     rax, cs:__security_cookie
0x1800290a7  xor     rax, rsp
0x1800290aa  mov     [rsp+858h+var_38], rax
0x1800290b2  movzx   ebp, dx
0x1800290b5  mov     rsi, rcx
0x1800290b8  xor     eax, eax
0x1800290ba  lea     rcx, [rsp+858h+var_834]; void *
0x1800290bf  xor     edx, edx; Val
0x1800290c1  mov     [rsp+858h+var_838], eax
0x1800290c5  mov     r8d, 7FCh; Size
0x1800290cb  call    memset_0
0x1800290d0  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800290d7  test    rdx, rdx
0x1800290da  jz      short loc_1800290F6
0x1800290dc  mov     rcx, cs:gRasEapEtwContext
0x1800290e3  lea     r8, aRascreateeapat_2; "RasCreateEapAttributesWithResultTLV -- "...
0x1800290ea  mov     rax, cs:gRasEapTemplateFunc
0x1800290f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f6  test    rsi, rsi
0x1800290f9  jnz     short loc_180029100
0x1800290fb  lea     ebx, [rsi+57h]
0x1800290fe  jmp     short loc_180029155
0x180029100  mov     edx, 10h; uBytes
0x180029105  xorps   xmm0, xmm0
0x180029108  movups  xmmword ptr [rsi], xmm0
0x18002910b  lea     ebx, [rdx+30h]
0x18002910e  mov     ecx, ebx; uFlags
0x180029110  call    cs:__imp_LocalAlloc
0x180029117  nop     dword ptr [rax+rax+00h]
0x18002911c  mov     rdi, rax
0x18002911f  test    rax, rax
0x180029122  jz      short loc_180029150
0x180029124  lea     edx, [rbx-3Ah]; uBytes
0x180029127  mov     ecx, ebx; uFlags
0x180029129  call    cs:__imp_LocalAlloc
0x180029130  nop     dword ptr [rax+rax+00h]
0x180029135  mov     [rdi+8], rax
0x180029139  mov     rcx, rax
0x18002913c  test    rax, rax
0x18002913f  jnz     short loc_180029187
0x180029141  mov     rcx, rdi; hMem
0x180029144  call    cs:__imp_LocalFree
0x18002914b  nop     dword ptr [rax+rax+00h]
0x180029150  mov     ebx, 8
0x180029155  cmp     qword ptr cs:xmmword_18004D740, 0
0x18002915d  jz      loc_18002921D
0x180029163  xor     eax, eax
0x180029165  lea     rdx, aRascreateeapat_0; "RasCreateEapAttributesWithResultTLV: Le"...
0x18002916c  mov     r8d, ebx
0x18002916f  mov     word ptr [rsp+858h+var_838], ax
0x180029174  lea     rcx, [rsp+858h+var_838]
0x180029179  call    FormatRRASErrorString
0x18002917e  mov     rdx, qword ptr cs:xmmword_18004D740
0x180029185  jmp     short loc_180029205
0x180029187  mov     dword ptr [rdi], 1FA6h
0x18002918d  xor     ebx, ebx
0x18002918f  mov     dword ptr [rdi+4], 6
0x180029196  mov     dword ptr [rax], 2000380h
0x18002919c  movzx   eax, bp
0x18002919f  shr     ax, 8
0x1800291a3  mov     [rcx+4], al
0x1800291a6  mov     [rcx+5], bpl
0x1800291aa  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800291b1  mov     dword ptr [rsi], 1
0x1800291b7  mov     [rsi+8], rdi
0x1800291bb  test    rdx, rdx
0x1800291be  jz      short loc_18002921D
0x1800291c0  mov     rcx, cs:gRasEapEtwContext
0x1800291c7  lea     r8, aRascreateeapat_1; "RasCreateEapAttributesWithResultTLV: Co"...
0x1800291ce  mov     rax, cs:gRasEapTemplateFunc
0x1800291d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291da  cmp     qword ptr cs:xmmword_18004D740+8, rbx
0x1800291e1  jz      short loc_18002921D
0x1800291e3  xor     eax, eax
0x1800291e5  lea     rdx, aRascreateeapat_0; "RasCreateEapAttributesWithResultTLV: Le"...
0x1800291ec  xor     r8d, r8d
0x1800291ef  mov     word ptr [rsp+858h+var_838], ax
0x1800291f4  lea     rcx, [rsp+858h+var_838]
0x1800291f9  call    FormatRRASErrorString
0x1800291fe  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029205  mov     rcx, cs:gRasEapEtwContext
0x18002920c  lea     r8, [rsp+858h+var_838]
0x180029211  mov     rax, cs:gRasEapTemplateFunc
0x180029218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002921d  mov     eax, ebx
0x18002921f  mov     rcx, [rsp+858h+var_38]
0x180029227  xor     rcx, rsp; StackCookie
0x18002922a  call    __security_check_cookie
0x18002922f  add     rsp, 838h
0x180029236  pop     rdi
0x180029237  pop     rsi
0x180029238  pop     rbp
0x180029239  pop     rbx
0x18002923a  retn
```
