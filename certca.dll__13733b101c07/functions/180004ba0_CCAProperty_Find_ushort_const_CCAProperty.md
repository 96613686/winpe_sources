# CCAProperty::Find(ushort const *,CCAProperty * *)

- ea: `0x180004ba0`
- end: `0x180004c2a`
- name: `?Find@CCAProperty@@QEAAJPEBGPEAPEAV1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(CCAProperty *this, const unsigned __int16 *, struct CCAProperty **)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ef0`
- `0x180003be0`
- `0x180005010`
- `0x18000596c`
- `0x1800113e0`
- `0x180036460`

## callees

- `0x180004ba0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004c03`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004c03`

## pseudocode

```c
__int64 __fastcall CCAProperty::Find(CCAProperty *this, const unsigned __int16 *a2, struct CCAProperty **a3)
{
  CCAProperty *v5; // rbx
  const WCHAR *lpString2; // rax

  v5 = this;
  if ( !a2 || !a3 || !this )
    return 2147500035LL;
  while ( 1 )
  {
    lpString2 = (const WCHAR *)*((_QWORD *)v5 + 1);
    if ( lpString2 )
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, lpString2, -1) == 2 )
        break;
    }
    v5 = (CCAProperty *)*((_QWORD *)v5 + 2);
    if ( !v5 )
    {
      *a3 = 0;
      return 2147943568LL;
    }
  }
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180004ba0  mov     [rsp+arg_0], rbx
0x180004ba5  mov     [rsp+arg_8], rsi
0x180004baa  push    rdi
0x180004bab  sub     rsp, 30h
0x180004baf  mov     rdi, r8
0x180004bb2  mov     rsi, rdx
0x180004bb5  mov     rbx, rcx
0x180004bb8  test    rdx, rdx
0x180004bbb  jz      short loc_180004C23
0x180004bbd  test    r8, r8
0x180004bc0  jz      short loc_180004C23
0x180004bc2  test    rcx, rcx
0x180004bc5  jz      short loc_180004C23
0x180004bc7  mov     rax, [rbx+8]
0x180004bcb  test    rax, rax
0x180004bce  jnz     short loc_180004BE3
0x180004bd0  mov     rbx, [rbx+10h]
0x180004bd4  test    rbx, rbx
0x180004bd7  jnz     short loc_180004BC7
0x180004bd9  mov     [rdi], rbx
0x180004bdc  mov     eax, 80070490h
0x180004be1  jmp     short loc_180004C13
0x180004be3  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180004beb  mov     r9d, 0FFFFFFFFh; cchCount1
0x180004bf1  mov     r8, rsi; lpString1
0x180004bf4  mov     [rsp+38h+lpString2], rax; lpString2
0x180004bf9  mov     edx, 1; dwCmpFlags
0x180004bfe  mov     ecx, 7Fh; Locale
0x180004c03  call    cs:__imp_CompareStringW
0x180004c09  cmp     eax, 2
0x180004c0c  jnz     short loc_180004BD0
0x180004c0e  mov     [rdi], rbx
0x180004c11  xor     eax, eax
0x180004c13  mov     rbx, [rsp+38h+arg_0]
0x180004c18  mov     rsi, [rsp+38h+arg_8]
0x180004c1d  add     rsp, 30h
0x180004c21  pop     rdi
0x180004c22  retn
0x180004c23  mov     eax, 80004003h
0x180004c28  jmp     short loc_180004C13
```
