# CCAProperty::DeleteChain(CCAProperty * *)

- ea: `0x18000cfc0`
- end: `0x18000d036`
- name: `?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z`
- size: `118`
- prototype: `__int64 __fastcall(struct CCAProperty **)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000af94`
- `0x18000b800`
- `0x18000c160`
- `0x18000cfc0`
- `0x18000d03c`
- `0x1800113e0`
- `0x180035478`
- `0x1800356b8`
- `0x180036460`

## callees

- `0x180005944`
- `0x18000cfc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d017`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d017`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d02b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d02b`

## pseudocode

```c
__int64 __fastcall CCAProperty::DeleteChain(struct CCAProperty **a1)
{
  __int64 v2; // rcx
  __int64 v4; // rbx
  unsigned __int16 *v5; // rcx

  if ( !a1 )
    return 2147500035LL;
  v2 = (__int64)*a1;
  if ( v2 )
  {
    CCAProperty::DeleteChain((struct CCAProperty **)(v2 + 16));
    v4 = (__int64)*a1;
    if ( v4 )
    {
      if ( *(_QWORD *)v4 )
      {
        LocalFree(*(HLOCAL *)v4);
        *(_QWORD *)v4 = 0;
      }
      v5 = *(unsigned __int16 **)(v4 + 8);
      if ( v5 )
      {
        CertFreeString(v5);
        *(_QWORD *)(v4 + 8) = 0;
      }
      *(_QWORD *)(v4 + 16) = 0;
      operator delete((void *)v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cfc0  push    rbx
0x18000cfc2  sub     rsp, 20h
0x18000cfc6  mov     rbx, rcx
0x18000cfc9  test    rcx, rcx
0x18000cfcc  jz      short loc_18000D024
0x18000cfce  mov     rcx, [rcx]
0x18000cfd1  test    rcx, rcx
0x18000cfd4  jnz     short loc_18000CFDE
0x18000cfd6  xor     eax, eax
0x18000cfd8  add     rsp, 20h
0x18000cfdc  pop     rbx
0x18000cfdd  retn
0x18000cfde  add     rcx, 10h; struct CCAProperty **
0x18000cfe2  call    ?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z; CCAProperty::DeleteChain(CCAProperty * *)
0x18000cfe7  mov     rbx, [rbx]
0x18000cfea  test    rbx, rbx
0x18000cfed  jz      short loc_18000CFD6
0x18000cfef  mov     rcx, [rbx]; hMem
0x18000cff2  mov     [rsp+28h+arg_0], rdi
0x18000cff7  xor     edi, edi
0x18000cff9  test    rcx, rcx
0x18000cffc  jnz     short loc_18000D02B
0x18000cffe  mov     rcx, [rbx+8]; unsigned __int16 *
0x18000d002  test    rcx, rcx
0x18000d005  jz      short loc_18000D010
0x18000d007  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18000d00c  mov     [rbx+8], rdi
0x18000d010  mov     rcx, rbx
0x18000d013  mov     [rbx+10h], rdi
0x18000d017  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d01d  mov     rdi, [rsp+28h+arg_0]
0x18000d022  jmp     short loc_18000CFD6
0x18000d024  mov     eax, 80004003h
0x18000d029  jmp     short loc_18000CFD8
0x18000d02b  call    cs:__imp_LocalFree
0x18000d031  mov     [rbx], rdi
0x18000d034  jmp     short loc_18000CFFE
```
