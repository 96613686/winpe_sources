# MSChapError::insert(IASTL::IASRequest &,uchar,ulong)

- ea: `0x18001137c`
- end: `0x18001146d`
- name: `?insert@MSChapError@@SAXAEAVIASRequest@IASTL@@EK@Z`
- size: `241`
- prototype: `void __fastcall(struct IASTL::IASRequest *, unsigned __int8, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010680`

## callees

- `0x180001f26`
- `0x18000acf4`
- `0x18000c28c`
- `0x18000c808`
- `0x18000d55c`
- `0x18001137c`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800113c5`
- `msvcrt!sprintf_s` at `0x1800113c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800113e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800113e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MSChapError::insert(struct IAttributesRaw **a1, bool a2, int a3)
{
  __int64 v6; // rdi
  _BYTE *v7; // rax
  _BYTE *v8; // rsi
  _DWORD *v9; // rbx
  LPVOID pv; // [rsp+20h] [rbp-48h] BYREF
  char Buffer[32]; // [rsp+28h] [rbp-40h] BYREF

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, a2);
  sprintf_s(Buffer, 0x20u, "E=%lu R=0 V=3", a3);
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  v7 = CoTaskMemAlloc((unsigned int)v6 + 1LL);
  v8 = v7;
  if ( !v7 )
    _com_issue_error(-2147024882);
  *v7 = a2;
  memcpy_0(v7 + 1, Buffer, (unsigned int)v6);
  v9 = pv;
  *((_DWORD *)pv + 2) = 4121;
  v9[4] = 6;
  *((_QWORD *)v9 + 4) = v8;
  v9[6] = v6 + 1;
  v9[1] = 2;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, a1[1]);
  IASAttributeRelease(v9);
}

```

## disassembly

```asm
0x18001137c  mov     [rsp+arg_8], rbx
0x180011381  mov     [rsp+arg_18], rbp
0x180011386  push    rsi
0x180011387  push    rdi
0x180011388  push    r14
0x18001138a  sub     rsp, 50h
0x18001138e  mov     rax, cs:__security_cookie
0x180011395  xor     rax, rsp
0x180011398  mov     [rsp+68h+var_20], rax
0x18001139d  mov     ebx, r8d
0x1800113a0  mov     bpl, dl
0x1800113a3  mov     r14, rcx
0x1800113a6  lea     rcx, [rsp+68h+pv]; this
0x1800113ab  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x1800113b0  nop
0x1800113b1  mov     r9d, ebx
0x1800113b4  lea     r8, aELuR0V3; "E=%lu R=0 V=3"
0x1800113bb  mov     edx, 20h ; ' '; BufferCount
0x1800113c0  lea     rcx, [rsp+68h+Buffer]; Buffer
0x1800113c5  call    cs:__imp_sprintf_s
0x1800113cb  lea     rax, [rsp+68h+Buffer]
0x1800113d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800113d4  inc     rdi
0x1800113d7  cmp     byte ptr [rax+rdi], 0
0x1800113db  jnz     short loc_1800113D4
0x1800113dd  mov     ebx, edi
0x1800113df  lea     rcx, [rbx+1]; cb
0x1800113e3  call    cs:__imp_CoTaskMemAlloc
0x1800113e9  mov     rsi, rax
0x1800113ec  test    rax, rax
0x1800113ef  jnz     short loc_1800113FC
0x1800113f1  mov     ecx, 8007000Eh; int
0x1800113f6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800113fc  mov     [rax], bpl
0x1800113ff  lea     rcx, [rax+1]; void *
0x180011403  mov     r8, rbx; Size
0x180011406  lea     rdx, [rsp+68h+Buffer]; Src
0x18001140b  call    memcpy_0
0x180011410  mov     rbx, [rsp+68h+pv]
0x180011415  mov     dword ptr [rbx+8], 1019h
0x18001141c  mov     dword ptr [rbx+10h], 6
0x180011423  mov     [rbx+20h], rsi
0x180011427  lea     eax, [rdi+1]
0x18001142a  mov     [rbx+18h], eax
0x18001142d  mov     dword ptr [rbx+4], 2
0x180011434  mov     rdx, [r14+8]; struct IAttributesRaw *
0x180011438  lea     rcx, [rsp+68h+pv]; this
0x18001143d  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x180011442  nop
0x180011443  mov     rcx, rbx; pv
0x180011446  call    IASAttributeRelease
0x18001144b  mov     rcx, [rsp+68h+var_20]
0x180011450  xor     rcx, rsp; StackCookie
0x180011453  call    __security_check_cookie
0x180011458  lea     r11, [rsp+68h+var_18]
0x18001145d  mov     rbx, [r11+28h]
0x180011461  mov     rbp, [r11+38h]
0x180011465  mov     rsp, r11
0x180011468  pop     r14
0x18001146a  pop     rdi
0x18001146b  pop     rsi
0x18001146c  retn
```
