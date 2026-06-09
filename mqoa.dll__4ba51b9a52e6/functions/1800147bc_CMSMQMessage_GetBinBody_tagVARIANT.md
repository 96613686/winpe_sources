# CMSMQMessage::GetBinBody(tagVARIANT *)

- ea: `0x1800147bc`
- end: `0x18001488a`
- name: `?GetBinBody@CMSMQMessage@@IEAAJPEAUtagVARIANT@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(CMSMQMessage *this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800180f0`

## callees

- `0x18000cb34`
- `0x1800147bc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800147d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800147d7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800147fc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800147fc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001484f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001484f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001483c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001483c`

## pseudocode

```c
__int64 __fastcall CMSMQMessage::GetBinBody(CMSMQMessage *this, struct tagVARIANT *a2)
{
  ULONG v4; // eax
  SAFEARRAY *v5; // rsi
  __int64 result; // rax
  HRESULT v7; // edi
  unsigned int i; // ebx
  void *v9; // r8
  HRESULT v10; // eax
  __int64 v11; // rcx
  LONG rgIndices; // [rsp+40h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+18h] BYREF

  VariantClear(a2);
  v4 = *((_DWORD *)this + 62);
  rgsabound.lLbound = 0;
  rgsabound.cElements = v4;
  v5 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  if ( *((_QWORD *)this + 30) )
  {
    for ( i = 0; i < *((_DWORD *)this + 62); ++i )
    {
      v9 = (void *)(*((_QWORD *)this + 28) + i);
      rgIndices = i;
      v7 = SafeArrayPutElement(v5, &rgIndices, v9);
      if ( v7 < 0 )
      {
        v10 = SafeArrayDestroy(v5);
        if ( v10 >= 0 )
          v11 = (unsigned int)v7;
        else
          v11 = (unsigned int)v10;
        return CreateErrorHelper(v11, 1);
      }
    }
  }
  a2->vt = 8209;
  result = (unsigned int)v7;
  a2->llVal = (LONGLONG)v5;
  return result;
}

```

## disassembly

```asm
0x1800147bc  mov     [rsp+arg_8], rbx
0x1800147c1  mov     [rsp+arg_18], rbp
0x1800147c6  push    rsi
0x1800147c7  push    rdi
0x1800147c8  push    r14
0x1800147ca  sub     rsp, 20h
0x1800147ce  mov     rbp, rcx
0x1800147d1  mov     r14, rdx
0x1800147d4  mov     rcx, rdx; pvarg
0x1800147d7  call    cs:__imp_VariantClear
0x1800147dd  mov     eax, [rbp+0F8h]
0x1800147e3  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x1800147e8  mov     ecx, 11h; vt
0x1800147ed  mov     [rsp+38h+rgsabound.lLbound], 0
0x1800147f5  mov     [rsp+38h+rgsabound.cElements], eax
0x1800147f9  lea     edx, [rcx-10h]; cDims
0x1800147fc  call    cs:__imp_SafeArrayCreate
0x180014802  mov     rsi, rax
0x180014805  test    rax, rax
0x180014808  jnz     short loc_180014811
0x18001480a  mov     eax, 8007000Eh
0x18001480f  jmp     short loc_180014877
0x180014811  xor     edi, edi
0x180014813  cmp     [rbp+0F0h], rdi
0x18001481a  jz      short loc_18001486B
0x18001481c  xor     ebx, ebx
0x18001481e  cmp     ebx, [rbp+0F8h]
0x180014824  jnb     short loc_18001486B
0x180014826  mov     r8d, ebx
0x180014829  lea     rdx, [rsp+38h+rgIndices]; rgIndices
0x18001482e  add     r8, [rbp+0E0h]; pv
0x180014835  mov     rcx, rsi; psa
0x180014838  mov     [rsp+38h+rgIndices], ebx
0x18001483c  call    cs:__imp_SafeArrayPutElement
0x180014842  mov     edi, eax
0x180014844  test    eax, eax
0x180014846  js      short loc_18001484C
0x180014848  inc     ebx
0x18001484a  jmp     short loc_18001481E
0x18001484c  mov     rcx, rsi; psa
0x18001484f  call    cs:__imp_SafeArrayDestroy
0x180014855  mov     edx, 1
0x18001485a  test    eax, eax
0x18001485c  jns     short loc_180014867
0x18001485e  mov     ecx, eax
0x180014860  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180014865  jmp     short loc_180014877
0x180014867  mov     ecx, edi
0x180014869  jmp     short loc_180014860
0x18001486b  mov     word ptr [r14], 2011h
0x180014871  mov     eax, edi
0x180014873  mov     [r14+8], rsi
0x180014877  mov     rbx, [rsp+38h+arg_8]
0x18001487c  mov     rbp, [rsp+38h+arg_18]
0x180014881  add     rsp, 20h
0x180014885  pop     r14
0x180014887  pop     rdi
0x180014888  pop     rsi
0x180014889  retn
```
