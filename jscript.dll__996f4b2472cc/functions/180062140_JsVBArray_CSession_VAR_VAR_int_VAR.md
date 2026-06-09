# JsVBArray(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x180062140`
- end: `0x1800621e9`
- name: `?JsVBArray@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct CSession *this, struct VAR *, struct VAR *, int, struct VAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180060af0`

## callees

- `0x180006e54`
- `0x1800076e0`
- `0x180062140`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800621af`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800621af`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180062193`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180062193`

## pseudocode

```c
__int64 __fastcall JsVBArray(struct CSession *this, struct VAR *a2, struct VAR *a3, int a4, struct VAR *a5)
{
  HRESULT v7; // ebx
  struct VAR *v8; // rax
  int v10; // eax
  unsigned int v11; // ecx
  SAFEARRAY *ppsaOut; // [rsp+20h] [rbp-38h] BYREF

  ppsaOut = 0;
  if ( a4 <= 0 )
    return (unsigned int)-2146823275;
  v8 = VAR::PvarCutHeap((struct VAR *)((char *)a5 + 24 * a4 - 24));
  if ( *(_WORD *)v8 != 8204 )
    return (unsigned int)-2146823275;
  v7 = SafeArrayCopy(*((SAFEARRAY **)v8 + 1), &ppsaOut);
  if ( v7 < 0 )
  {
    if ( ppsaOut )
      SafeArrayDestroy(ppsaOut);
    return (unsigned int)v7;
  }
  *((_QWORD *)a3 + 1) = ppsaOut;
  *(_WORD *)a3 = 8204;
  v10 = VAR::MoveToHeap((VARIANTARG *)a3, this);
  v11 = 0;
  if ( v10 < 0 )
    return (unsigned int)v10;
  return v11;
}

```

## disassembly

```asm
0x180062140  push    rbx
0x180062142  push    rbp
0x180062143  push    rsi
0x180062144  push    rdi
0x180062145  sub     rsp, 38h
0x180062149  mov     [rsp+58h+ppsaOut], 0
0x180062152  mov     rdi, r8
0x180062155  mov     rsi, rcx
0x180062158  test    r9d, r9d
0x18006215b  jg      short loc_180062164
0x18006215d  mov     ebx, 800A1395h
0x180062162  jmp     short loc_1800621BB
0x180062164  movsxd  rax, r9d
0x180062167  lea     rcx, [rax+rax*2]
0x18006216b  mov     rax, [rsp+58h+arg_20]
0x180062173  lea     rcx, [rcx-3]
0x180062177  lea     rcx, [rax+rcx*8]; this
0x18006217b  call    ?PvarCutHeap@VAR@@QEAAPEAV1@XZ; VAR::PvarCutHeap(void)
0x180062180  mov     ebp, 200Ch
0x180062185  cmp     [rax], bp
0x180062188  jnz     short loc_18006215D
0x18006218a  mov     rcx, [rax+8]; psa
0x18006218e  lea     rdx, [rsp+58h+ppsaOut]; ppsaOut
0x180062193  call    cs:__imp_SafeArrayCopy
0x18006219a  nop     dword ptr [rax+rax+00h]
0x18006219f  mov     ebx, eax
0x1800621a1  test    eax, eax
0x1800621a3  jns     short loc_1800621BF
0x1800621a5  mov     rcx, [rsp+58h+ppsaOut]; psa
0x1800621aa  test    rcx, rcx
0x1800621ad  jz      short loc_1800621BB
0x1800621af  call    cs:__imp_SafeArrayDestroy
0x1800621b6  nop     dword ptr [rax+rax+00h]
0x1800621bb  mov     eax, ebx
0x1800621bd  jmp     short loc_1800621DF
0x1800621bf  mov     rax, [rsp+58h+ppsaOut]
0x1800621c4  mov     rdx, rsi; this
0x1800621c7  mov     rcx, rdi; pvarg
0x1800621ca  mov     [rdi+8], rax
0x1800621ce  mov     [rdi], bp
0x1800621d1  call    ?MoveToHeap@VAR@@QEAAJPEAVCSession@@@Z; VAR::MoveToHeap(CSession *)
0x1800621d6  xor     ecx, ecx
0x1800621d8  test    eax, eax
0x1800621da  cmovs   ecx, eax
0x1800621dd  mov     eax, ecx
0x1800621df  add     rsp, 38h
0x1800621e3  pop     rdi
0x1800621e4  pop     rsi
0x1800621e5  pop     rbp
0x1800621e6  pop     rbx
0x1800621e7  retn
```
