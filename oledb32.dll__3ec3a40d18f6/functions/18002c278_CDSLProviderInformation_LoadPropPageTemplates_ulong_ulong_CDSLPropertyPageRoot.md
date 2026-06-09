# CDSLProviderInformation::LoadPropPageTemplates(ulong *,ulong,CDSLPropertyPageRoot * *)

- ea: `0x18002c278`
- end: `0x18002c321`
- name: `?LoadPropPageTemplates@CDSLProviderInformation@@IEAAXPEAKKPEAPEAVCDSLPropertyPageRoot@@@Z`
- size: `169`
- prototype: `void __fastcall(CDSLProviderInformation *__hidden this, unsigned int *, unsigned int, struct CDSLPropertyPageRoot **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002c1b8`

## callees

- `0x18002c278`
- `0x180056394`
- `0x18007e6ca`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002c2a8`
- `ole32!CoTaskMemAlloc` at `0x18002c2be`
- `ole32!CoTaskMemAlloc` at `0x18002c2a8`
- `ole32!CoTaskMemAlloc` at `0x18002c2be`
- `ole32!CoTaskMemFree` at `0x18002c2d1`
- `ole32!CoTaskMemFree` at `0x18002c2d1`

## pseudocode

```c
void __fastcall CDSLProviderInformation::LoadPropPageTemplates(
        CDSLProviderInformation *this,
        unsigned int *a2,
        unsigned int a3,
        struct CDSLPropertyPageRoot **a4)
{
  LPVOID v8; // rax
  void *v9; // rax
  CDSLProviderInformation *v10; // rcx
  __int64 i; // rdi

  if ( !*((_QWORD *)this + 5) )
  {
    *((_DWORD *)this + 18) = 0;
    v8 = CoTaskMemAlloc(8LL * a3);
    *((_QWORD *)this + 8) = v8;
    if ( v8 )
    {
      v9 = CoTaskMemAlloc(104LL * a3);
      *((_QWORD *)this + 5) = v9;
      if ( v9 )
      {
        *((_DWORD *)this + 12) = a3;
        memset_0(v9, 0, 104LL * a3);
        for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
          CDSLProviderInformation::LoadPropPageTemplate(
            v10,
            (struct _PROPSHEETPAGEW *)(*((_QWORD *)this + 5) + 104LL * (unsigned int)i),
            a2[i],
            a4[i]);
      }
      else
      {
        CoTaskMemFree(*((LPVOID *)this + 8));
        *((_QWORD *)this + 8) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x18002c278  push    rbx
0x18002c27a  push    rsi
0x18002c27b  push    rdi
0x18002c27c  push    r14
0x18002c27e  push    r15
0x18002c280  sub     rsp, 20h
0x18002c284  cmp     qword ptr [rcx+28h], 0
0x18002c289  mov     r14, r9
0x18002c28c  mov     esi, r8d
0x18002c28f  mov     r15, rdx
0x18002c292  mov     rbx, rcx
0x18002c295  jnz     short loc_18002C315
0x18002c297  mov     dword ptr [rcx+48h], 0
0x18002c29e  mov     edi, esi
0x18002c2a0  lea     rcx, ds:0[rsi*8]; cb
0x18002c2a8  call    cs:__imp_CoTaskMemAlloc
0x18002c2ae  mov     [rbx+40h], rax
0x18002c2b2  test    rax, rax
0x18002c2b5  jz      short loc_18002C315
0x18002c2b7  imul    rdi, 68h ; 'h'
0x18002c2bb  mov     rcx, rdi; cb
0x18002c2be  call    cs:__imp_CoTaskMemAlloc
0x18002c2c4  mov     [rbx+28h], rax
0x18002c2c8  test    rax, rax
0x18002c2cb  jnz     short loc_18002C2E1
0x18002c2cd  mov     rcx, [rbx+40h]; pv
0x18002c2d1  call    cs:__imp_CoTaskMemFree
0x18002c2d7  mov     qword ptr [rbx+40h], 0
0x18002c2df  jmp     short loc_18002C315
0x18002c2e1  mov     r8, rdi; Size
0x18002c2e4  mov     [rbx+30h], esi
0x18002c2e7  xor     edx, edx; Val
0x18002c2e9  mov     rcx, rax; void *
0x18002c2ec  call    memset_0
0x18002c2f1  xor     edi, edi
0x18002c2f3  test    esi, esi
0x18002c2f5  jz      short loc_18002C315
0x18002c2f7  mov     r9, [r14+rdi*8]; struct CDSLPropertyPageRoot *
0x18002c2fb  mov     r8d, edi
0x18002c2fe  imul    rdx, r8, 68h ; 'h'
0x18002c302  mov     r8d, [r15+rdi*4]; unsigned int
0x18002c306  add     rdx, [rbx+28h]; struct _PROPSHEETPAGEW *
0x18002c30a  call    ?LoadPropPageTemplate@CDSLProviderInformation@@IEAAXPEAU_PROPSHEETPAGEW@@KPEAVCDSLPropertyPageRoot@@@Z; CDSLProviderInformation::LoadPropPageTemplate(_PROPSHEETPAGEW *,ulong,CDSLPropertyPageRoot *)
0x18002c30f  inc     edi
0x18002c311  cmp     edi, esi
0x18002c313  jb      short loc_18002C2F7
0x18002c315  add     rsp, 20h
0x18002c319  pop     r15
0x18002c31b  pop     r14
0x18002c31d  pop     rdi
0x18002c31e  pop     rsi
0x18002c31f  pop     rbx
0x18002c320  retn
```
