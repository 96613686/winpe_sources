# MSChap2Success::insert(IASTL::IASRequest &,uchar,uchar *)

- ea: `0x180011190`
- end: `0x180011265`
- name: `?insert@MSChap2Success@@SAXAEAVIASRequest@IASTL@@EPEAE@Z`
- size: `213`
- prototype: `void __fastcall(struct IASTL::IASRequest *, unsigned __int8, unsigned __int8 *)`
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
- `0x180011190`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800111b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800111b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MSChap2Success::insert(struct IAttributesRaw **a1, bool a2, unsigned __int8 *a3)
{
  _BYTE *v6; // rax
  _BYTE *v7; // rdx
  unsigned __int64 i; // r8
  _DWORD *v9; // rbx
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, a2);
  v6 = CoTaskMemAlloc(0x2Bu);
  if ( !v6 )
    _com_issue_error(-2147024882);
  *v6 = a2;
  v6[1] = 83;
  v6[2] = 61;
  v7 = v6 + 3;
  for ( i = 0; i < 0x14; ++i )
  {
    *v7 = (a3[i] >> 4) + 55 + ((unsigned __int8)(a3[i] >> 4) < 0xAu ? 0xF9 : 0);
    v7[1] = (a3[i] & 0xF) + ((a3[i] & 0xFu) < 0xA ? 48 : 55);
    v7 += 2;
  }
  v9 = pv;
  *((_DWORD *)pv + 2) = 4145;
  v9[4] = 6;
  *((_QWORD *)v9 + 4) = v6;
  v9[6] = 43;
  v9[1] = 1;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, a1[1]);
  IASAttributeRelease(v9);
}

```

## disassembly

```asm
0x180011190  mov     [rsp+arg_0], rbx
0x180011195  mov     [rsp+arg_8], rsi
0x18001119a  push    rdi
0x18001119b  sub     rsp, 20h
0x18001119f  mov     rsi, r8
0x1800111a2  mov     bl, dl
0x1800111a4  mov     rdi, rcx
0x1800111a7  lea     rcx, [rsp+28h+pv]; this
0x1800111ac  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x1800111b1  nop
0x1800111b2  mov     ecx, 2Bh ; '+'; cb
0x1800111b7  call    cs:__imp_CoTaskMemAlloc
0x1800111bd  mov     r9, rax
0x1800111c0  test    rax, rax
0x1800111c3  jnz     short loc_1800111D0
0x1800111c5  mov     ecx, 8007000Eh; int
0x1800111ca  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800111d0  mov     [rax], bl
0x1800111d2  mov     byte ptr [rax+1], 53h ; 'S'
0x1800111d6  lea     rdx, [rax+2]
0x1800111da  mov     byte ptr [rdx], 3Dh ; '='
0x1800111dd  inc     rdx
0x1800111e0  xor     r8d, r8d
0x1800111e3  mov     cl, [rsi+r8]
0x1800111e7  shr     cl, 4
0x1800111ea  cmp     cl, 0Ah
0x1800111ed  sbb     al, al
0x1800111ef  and     al, 0F9h
0x1800111f1  add     cl, 37h ; '7'
0x1800111f4  add     al, cl
0x1800111f6  mov     [rdx], al
0x1800111f8  mov     cl, [rsi+r8]
0x1800111fc  and     cl, 0Fh
0x1800111ff  cmp     cl, 0Ah
0x180011202  sbb     al, al
0x180011204  and     al, 0F9h
0x180011206  add     al, 37h ; '7'
0x180011208  add     al, cl
0x18001120a  mov     [rdx+1], al
0x18001120d  lea     rdx, [rdx+2]
0x180011211  inc     r8
0x180011214  cmp     r8, 14h
0x180011218  jb      short loc_1800111E3
0x18001121a  mov     rbx, [rsp+28h+pv]
0x18001121f  mov     dword ptr [rbx+8], 1031h
0x180011226  mov     dword ptr [rbx+10h], 6
0x18001122d  mov     [rbx+20h], r9
0x180011231  mov     dword ptr [rbx+18h], 2Bh ; '+'
0x180011238  mov     dword ptr [rbx+4], 1
0x18001123f  mov     rdx, [rdi+8]; struct IAttributesRaw *
0x180011243  lea     rcx, [rsp+28h+pv]; this
0x180011248  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18001124d  nop
0x18001124e  mov     rcx, rbx; pv
0x180011251  mov     rbx, [rsp+28h+arg_0]
0x180011256  mov     rsi, [rsp+28h+arg_8]
0x18001125b  add     rsp, 20h
0x18001125f  pop     rdi
0x180011260  jmp     IASAttributeRelease
```
