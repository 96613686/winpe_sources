# CUtlProps::GetPropValue(ulong,ulong,tagVARIANT *)

- ea: `0x18002bc9c`
- end: `0x18002bd74`
- name: `?GetPropValue@CUtlProps@@QEAAHKKPEAUtagVARIANT@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CUtlProps *__hidden this, unsigned int, unsigned int, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b0c0`
- `0x18001b128`
- `0x18001c0e0`
- `0x18002c9fc`

## callees

- `0x18002bc9c`
- `0x18002c9c4`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002bd5c`
- `OLEAUT32!__imp_VariantCopy` at `0x18002bd5c`

## pseudocode

```c
__int64 __fastcall CUtlProps::GetPropValue(CUtlProps *this, __int64 a2, __int64 a3, struct tagVARIANT *a4)
{
  unsigned int v5; // edi
  __int64 result; // rax
  __int64 v8; // rdx
  unsigned int UPropValIndex; // eax
  HRESULT v10; // eax
  int v11; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+48h] [rbp+10h] BYREF

  v12 = 0;
  v11 = 0;
  v5 = a3;
  result = (*(__int64 (__fastcall **)(CUtlProps *, _QWORD, __int64, unsigned int *))(*(_QWORD *)this + 16LL))(
             this,
             0,
             a3,
             &v12);
  if ( (_DWORD)result )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
    if ( (*(_DWORD *)(v8 + 24LL * v12 + 8) & 0x400) != 0 || (*(_BYTE *)(v8 + 24LL * v12 + 12) & 1) != 0 )
    {
      UPropValIndex = CUtlProps::GetUPropValIndex(this, 0, v5);
      v10 = VariantCopy(
              a4,
              (const VARIANTARG *)(*(_QWORD *)(*((_QWORD *)this + 3) + 16LL) + 16LL + 48LL * UPropValIndex));
      if ( v10 < 0 )
        ThrowHR(v10);
    }
    else
    {
      (*(void (__fastcall **)(CUtlProps *, _QWORD, _QWORD, int *, struct tagVARIANT *))(*(_QWORD *)this + 40LL))(
        this,
        0,
        v5,
        &v11,
        a4);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002bc9c  mov     rax, rsp
0x18002bc9f  mov     [rax+18h], rbx
0x18002bca3  mov     [rax+20h], rsi
0x18002bca7  mov     [rax+10h], edx
0x18002bcaa  push    rdi
0x18002bcab  sub     rsp, 30h
0x18002bcaf  mov     dword ptr [rax+10h], 0
0x18002bcb6  mov     rsi, r9
0x18002bcb9  mov     dword ptr [rax+8], 0
0x18002bcc0  lea     r9, [rsp+38h+arg_8]
0x18002bcc5  mov     rax, [rcx]
0x18002bcc8  xor     edx, edx
0x18002bcca  mov     edi, r8d
0x18002bccd  mov     rbx, rcx
0x18002bcd0  mov     rax, [rax+10h]
0x18002bcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcd9  test    eax, eax
0x18002bcdb  jz      short loc_18002BD21
0x18002bcdd  mov     eax, [rsp+38h+arg_8]
0x18002bce1  lea     rcx, [rax+rax*2]
0x18002bce5  mov     rax, [rbx+10h]
0x18002bce9  mov     rdx, [rax+10h]
0x18002bced  test    dword ptr [rdx+rcx*8+8], 400h
0x18002bcf5  jnz     short loc_18002BD32
0x18002bcf7  test    byte ptr [rdx+rcx*8+0Ch], 1
0x18002bcfc  jnz     short loc_18002BD32
0x18002bcfe  mov     rax, [rbx]
0x18002bd01  lea     r9, [rsp+38h+arg_0]
0x18002bd06  mov     r8d, edi
0x18002bd09  mov     [rsp+38h+var_18], rsi
0x18002bd0e  xor     edx, edx
0x18002bd10  mov     rcx, rbx
0x18002bd13  mov     rax, [rax+28h]
0x18002bd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd1c  mov     eax, 1
0x18002bd21  mov     rbx, [rsp+38h+arg_10]
0x18002bd26  mov     rsi, [rsp+38h+arg_18]
0x18002bd2b  add     rsp, 30h
0x18002bd2f  pop     rdi
0x18002bd30  retn
0x18002bd32  mov     r8d, edi; unsigned int
0x18002bd35  xor     edx, edx; unsigned int
0x18002bd37  mov     rcx, rbx; this
0x18002bd3a  call    ?GetUPropValIndex@CUtlProps@@QEAAKKK@Z; CUtlProps::GetUPropValIndex(ulong,ulong)
0x18002bd3f  mov     r8d, eax
0x18002bd42  mov     rax, [rbx+18h]
0x18002bd46  lea     rdx, [r8+r8*2]
0x18002bd4a  mov     rcx, [rax+10h]
0x18002bd4e  add     rcx, 10h
0x18002bd52  shl     rdx, 4
0x18002bd56  add     rdx, rcx; pvargSrc
0x18002bd59  mov     rcx, rsi; pvargDest
0x18002bd5c  call    cs:__imp_VariantCopy
0x18002bd63  nop     dword ptr [rax+rax+00h]
0x18002bd68  test    eax, eax
0x18002bd6a  jns     short loc_18002BD1C
0x18002bd6c  mov     ecx, eax; int
0x18002bd6e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
