# MSMPPEKey::insert(IASTL::IASRequest &,ulong,uchar *,int)

- ea: `0x180011514`
- end: `0x1800115c1`
- name: `?insert@MSMPPEKey@@SAXAEAVIASRequest@IASTL@@KPEAEH@Z`
- size: `173`
- prototype: `void __fastcall(struct IASTL::IASRequest *, unsigned int, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ec4c`

## callees

- `0x18000acf4`
- `0x18000c28c`
- `0x18000c808`
- `0x18000d55c`
- `0x180011514`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001153c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001153c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MSMPPEKey::insert(struct IAttributesRaw **a1, bool a2, unsigned __int8 *a3, int a4)
{
  _OWORD *v7; // rax
  _OWORD *v8; // rdx
  int v9; // eax
  _DWORD *v10; // rbx
  LPVOID pv[3]; // [rsp+20h] [rbp-18h] BYREF

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)pv, a2);
  v7 = CoTaskMemAlloc(0x22u);
  v8 = v7;
  if ( !v7 )
    _com_issue_error(-2147024882);
  *v7 = 0;
  v7[1] = 0;
  *((_WORD *)v7 + 16) = 0;
  *((_BYTE *)v7 + 2) = 16;
  *(_OWORD *)((char *)v7 + 3) = *(_OWORD *)a3;
  v9 = 4141 - (a4 != 0);
  v10 = pv[0];
  *((_DWORD *)pv[0] + 2) = v9;
  v10[4] = 6;
  *((_QWORD *)v10 + 4) = v8;
  v10[6] = 34;
  v10[1] = 1;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)pv, a1[1]);
  IASAttributeRelease(v10);
}

```

## disassembly

```asm
0x180011514  mov     [rsp+arg_0], rbx
0x180011519  mov     [rsp+arg_8], rsi
0x18001151e  push    rdi
0x18001151f  sub     rsp, 30h
0x180011523  mov     ebx, r9d
0x180011526  mov     rdi, r8
0x180011529  mov     rsi, rcx
0x18001152c  lea     rcx, [rsp+38h+pv]; this
0x180011531  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180011536  nop
0x180011537  mov     ecx, 22h ; '"'; cb
0x18001153c  call    cs:__imp_CoTaskMemAlloc
0x180011542  mov     rdx, rax
0x180011545  test    rax, rax
0x180011548  jnz     short loc_180011555
0x18001154a  mov     ecx, 8007000Eh; int
0x18001154f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180011555  xorps   xmm0, xmm0
0x180011558  xor     eax, eax
0x18001155a  movups  xmmword ptr [rdx], xmm0
0x18001155d  movups  xmmword ptr [rdx+10h], xmm0
0x180011561  mov     [rdx+20h], ax
0x180011565  mov     byte ptr [rdx+2], 10h
0x180011569  movups  xmm0, xmmword ptr [rdi]
0x18001156c  movdqu  xmmword ptr [rdx+3], xmm0
0x180011571  neg     ebx
0x180011573  sbb     eax, eax
0x180011575  add     eax, 102Dh
0x18001157a  mov     rbx, [rsp+38h+pv]
0x18001157f  mov     [rbx+8], eax
0x180011582  mov     dword ptr [rbx+10h], 6
0x180011589  mov     [rbx+20h], rdx
0x18001158d  mov     dword ptr [rbx+18h], 22h ; '"'
0x180011594  mov     dword ptr [rbx+4], 1
0x18001159b  mov     rdx, [rsi+8]; struct IAttributesRaw *
0x18001159f  lea     rcx, [rsp+38h+pv]; this
0x1800115a4  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x1800115a9  nop
0x1800115aa  mov     rcx, rbx; pv
0x1800115ad  mov     rbx, [rsp+38h+arg_0]
0x1800115b2  mov     rsi, [rsp+38h+arg_8]
0x1800115b7  add     rsp, 30h
0x1800115bb  pop     rdi
0x1800115bc  jmp     IASAttributeRelease
```
