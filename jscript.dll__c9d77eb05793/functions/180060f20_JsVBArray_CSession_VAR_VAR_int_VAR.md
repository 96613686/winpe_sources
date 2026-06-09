# JsVBArray(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x180060f20`
- end: `0x180060fce`
- name: `?JsVBArray@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `174`
- prototype: `__int64 __usercall@<rax>(struct CSession *this@<rcx>, struct VAR *@<rdx>, struct VAR *@<r8>, int@<r9d>, struct VAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005f8e0`

## callees

- `0x18000a0c8`
- `0x180060f20`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180060f9b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180060f9b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180060f85`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180060f85`

## pseudocode

```c
__int64 __fastcall JsVBArray(struct CSession *this, struct VAR *a2, struct VAR *a3, int a4, struct VAR *a5)
{
  HRESULT v7; // ebx
  SAFEARRAY **v8; // rcx
  __int16 v9; // ax
  int v11; // eax
  unsigned int v12; // ecx
  SAFEARRAY *ppsaOut; // [rsp+20h] [rbp-38h] BYREF

  ppsaOut = 0;
  if ( a4 <= 0 )
    return (unsigned int)-2146823275;
  v8 = (SAFEARRAY **)((char *)a5 + 24 * a4 - 24);
  v9 = *(_WORD *)v8;
  if ( *(_WORD *)v8 == 128 )
  {
    v8 = (SAFEARRAY **)*((_QWORD *)a5 + 3 * a4 - 2);
    v9 = *(_WORD *)v8;
  }
  if ( v9 != 8204 )
    return (unsigned int)-2146823275;
  v7 = SafeArrayCopy(v8[1], &ppsaOut);
  if ( v7 < 0 )
  {
    if ( ppsaOut )
      SafeArrayDestroy(ppsaOut);
    return (unsigned int)v7;
  }
  *((_QWORD *)a3 + 1) = ppsaOut;
  *(_WORD *)a3 = 8204;
  v11 = VAR::MoveToHeap((VARIANTARG *)a3, this);
  v12 = 0;
  if ( v11 < 0 )
    return (unsigned int)v11;
  return v12;
}

```

## disassembly

```asm
0x180060f20  push    rbx
0x180060f22  push    rbp
0x180060f23  push    rsi
0x180060f24  push    rdi
0x180060f25  sub     rsp, 38h
0x180060f29  mov     [rsp+58h+ppsaOut], 0
0x180060f32  mov     rdi, r8
0x180060f35  mov     rsi, rcx
0x180060f38  test    r9d, r9d
0x180060f3b  jg      short loc_180060F44
0x180060f3d  mov     ebx, 800A1395h
0x180060f42  jmp     short loc_180060FA1
0x180060f44  mov     r8, [rsp+58h+arg_20]
0x180060f4c  movsxd  rax, r9d
0x180060f4f  mov     r9d, 80h
0x180060f55  lea     rcx, [r8-18h]
0x180060f59  lea     rdx, [rax+rax*2]
0x180060f5d  lea     rcx, [rcx+rdx*8]
0x180060f61  movzx   eax, word ptr [rcx]
0x180060f64  cmp     ax, r9w
0x180060f68  jnz     short loc_180060F72
0x180060f6a  mov     rcx, [r8+rdx*8-10h]
0x180060f6f  movzx   eax, word ptr [rcx]
0x180060f72  mov     ebp, 200Ch
0x180060f77  cmp     ax, bp
0x180060f7a  jnz     short loc_180060F3D
0x180060f7c  mov     rcx, [rcx+8]; psa
0x180060f80  lea     rdx, [rsp+58h+ppsaOut]; ppsaOut
0x180060f85  call    cs:__imp_SafeArrayCopy
0x180060f8b  mov     ebx, eax
0x180060f8d  test    eax, eax
0x180060f8f  jns     short loc_180060FA5
0x180060f91  mov     rcx, [rsp+58h+ppsaOut]; psa
0x180060f96  test    rcx, rcx
0x180060f99  jz      short loc_180060FA1
0x180060f9b  call    cs:__imp_SafeArrayDestroy
0x180060fa1  mov     eax, ebx
0x180060fa3  jmp     short loc_180060FC5
0x180060fa5  mov     rax, [rsp+58h+ppsaOut]
0x180060faa  mov     rdx, rsi; this
0x180060fad  mov     rcx, rdi; pvarg
0x180060fb0  mov     [rdi+8], rax
0x180060fb4  mov     [rdi], bp
0x180060fb7  call    ?MoveToHeap@VAR@@QEAAJPEAVCSession@@@Z; VAR::MoveToHeap(CSession *)
0x180060fbc  xor     ecx, ecx
0x180060fbe  test    eax, eax
0x180060fc0  cmovs   ecx, eax
0x180060fc3  mov     eax, ecx
0x180060fc5  add     rsp, 38h
0x180060fc9  pop     rdi
0x180060fca  pop     rsi
0x180060fcb  pop     rbp
0x180060fcc  pop     rbx
0x180060fcd  retn
```
