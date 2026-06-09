# MSChapMPPEKeys::insert(IASTL::IASRequest &,uchar *,uchar *,uchar *)

- ea: `0x180011474`
- end: `0x18001150c`
- name: `?insert@MSChapMPPEKeys@@SAXAEAVIASRequest@IASTL@@PEAE11@Z`
- size: `152`
- prototype: `void __fastcall(struct IASTL::IASRequest *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eea8`

## callees

- `0x18000acf4`
- `0x18000c28c`
- `0x18000c808`
- `0x18000d55c`
- `0x180011474`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011499`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MSChapMPPEKeys::insert(
        struct IAttributesRaw **a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  char *v8; // rax
  _DWORD *v9; // rbx
  LPVOID pv[7]; // [rsp+20h] [rbp-38h] BYREF

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)pv, (bool)a2);
  v8 = (char *)CoTaskMemAlloc(0x20u);
  if ( !v8 )
    _com_issue_error(-2147024882);
  *(_QWORD *)v8 = *(_QWORD *)a2;
  *(_OWORD *)(v8 + 8) = *(_OWORD *)a3;
  *((_QWORD *)v8 + 3) = *(_QWORD *)a4;
  v9 = pv[0];
  *((_DWORD *)pv[0] + 2) = 4126;
  v9[4] = 6;
  *((_QWORD *)v9 + 4) = v8;
  v9[6] = 32;
  v9[1] = 1;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)pv, a1[1]);
  IASAttributeRelease(v9);
}

```

## disassembly

```asm
0x180011474  push    rbx
0x180011476  push    rbp
0x180011477  push    rsi
0x180011478  push    rdi
0x180011479  sub     rsp, 38h
0x18001147d  mov     rbx, r9
0x180011480  mov     rdi, r8
0x180011483  mov     rsi, rdx
0x180011486  mov     rbp, rcx
0x180011489  lea     rcx, [rsp+58h+pv]; this
0x18001148e  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180011493  nop
0x180011494  mov     ecx, 20h ; ' '; cb
0x180011499  call    cs:__imp_CoTaskMemAlloc
0x18001149f  mov     r10, rax
0x1800114a2  test    rax, rax
0x1800114a5  jnz     short loc_1800114B2
0x1800114a7  mov     ecx, 8007000Eh; int
0x1800114ac  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800114b2  mov     rax, [rsi]
0x1800114b5  mov     [r10], rax
0x1800114b8  movaps  xmm0, xmmword ptr [rdi]
0x1800114bb  movdqu  xmmword ptr [r10+8], xmm0
0x1800114c1  mov     rax, [rbx]
0x1800114c4  mov     [r10+18h], rax
0x1800114c8  mov     rbx, [rsp+58h+pv]
0x1800114cd  mov     dword ptr [rbx+8], 101Eh
0x1800114d4  mov     dword ptr [rbx+10h], 6
0x1800114db  mov     [rbx+20h], r10
0x1800114df  mov     dword ptr [rbx+18h], 20h ; ' '
0x1800114e6  mov     dword ptr [rbx+4], 1
0x1800114ed  mov     rdx, [rbp+8]; struct IAttributesRaw *
0x1800114f1  lea     rcx, [rsp+58h+pv]; this
0x1800114f6  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x1800114fb  nop
0x1800114fc  mov     rcx, rbx; pv
0x1800114ff  add     rsp, 38h
0x180011503  pop     rdi
0x180011504  pop     rsi
0x180011505  pop     rbp
0x180011506  pop     rbx
0x180011507  jmp     IASAttributeRelease
```
