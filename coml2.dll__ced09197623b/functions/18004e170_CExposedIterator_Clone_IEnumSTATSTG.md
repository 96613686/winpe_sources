# CExposedIterator::Clone(IEnumSTATSTG * *)

- ea: `0x18004e170`
- end: `0x18004e2c1`
- name: `?Clone@CExposedIterator@@UEAAJPEAPEAUIEnumSTATSTG@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(CExposedIterator *__hidden this, struct IEnumSTATSTG **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018914`
- `0x18001a510`
- `0x18001b840`
- `0x18001bf68`
- `0x18002366c`
- `0x1800241f8`
- `0x18003c004`
- `0x18004d418`
- `0x18004e140`
- `0x18004e170`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e214`

## pseudocode

```c
__int64 __fastcall CExposedIterator::Clone(struct CPerContext **this, struct IEnumSTATSTG **a2)
{
  int inited; // ebx
  struct CPerContext *v5; // rcx
  struct CPerContext *v6; // rdx
  CExposedIterator *v7; // rax
  struct IEnumSTATSTG *v8; // rax
  _BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF
  struct IEnumSTATSTG *v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = 0;
  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v10, this[8]);
  inited = CExpParameterValidate::Clone(a2);
  if ( inited >= 0 )
  {
    inited = CExposedIterator::Validate((CExposedIterator *)this);
    if ( inited >= 0 )
    {
      inited = CPerContext::TakeSem(this[8]);
      if ( inited >= 0 )
      {
        v5 = this[8];
        if ( (*((_BYTE *)this[6] + 20) & 0x20) != 0 )
        {
          inited = -2147286782;
          CDfMutex::Release((HANDLE *)v5 + 14);
        }
        else
        {
          v6 = this[7];
          *((_QWORD *)v6 + 4) = *((_QWORD *)v5 + 2);
          *((_QWORD *)v6 + 5) = *((_QWORD *)v5 + 3);
          *((_QWORD *)v6 + 6) = *((_QWORD *)v5 + 4);
          v7 = (CExposedIterator *)CoTaskMemAlloc(0x98u);
          if ( v7 )
            v7 = CExposedIterator::CExposedIterator(v7, this[6], (struct CDfName *)(this + 10), this[7], this[8]);
          Microsoft::WRL::ComPtr<CExposedIterator>::Attach(&v11, v7);
          v8 = v11;
          if ( v11 )
          {
            inited = 0;
            _InterlockedIncrement((volatile signed __int32 *)this[8] + 14);
            *a2 = v8;
          }
          else
          {
            inited = -2147287032;
          }
          CDfMutex::Release((HANDLE *)this[8] + 14);
          if ( this[4] )
          {
            inited = CAsyncConnection::InitClone(
                       (CAsyncConnection *)0x10,
                       (struct IConnectionPointContainer *)8,
                       (struct CAsyncConnection *)(this + 2));
            if ( inited < 0 )
              (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
          }
        }
      }
    }
  }
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v10);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18004e170  mov     rax, rsp
0x18004e173  mov     [rax+10h], rbx
0x18004e177  mov     [rax+18h], rsi
0x18004e17b  push    rdi
0x18004e17c  sub     rsp, 40h
0x18004e180  mov     rsi, rdx
0x18004e183  mov     qword ptr [rax+8], 0
0x18004e18b  mov     rdx, [rcx+40h]; struct CPerContext *
0x18004e18f  mov     rdi, rcx
0x18004e192  lea     rcx, [rax-18h]; this
0x18004e196  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x18004e19b  mov     rcx, rsi; struct IEnumSTATSTG **
0x18004e19e  call    ?Clone@CExpParameterValidate@@SAJPEAPEAUIEnumSTATSTG@@@Z; CExpParameterValidate::Clone(IEnumSTATSTG * *)
0x18004e1a3  mov     ebx, eax
0x18004e1a5  test    eax, eax
0x18004e1a7  js      loc_18004E2A5
0x18004e1ad  mov     rcx, rdi; this
0x18004e1b0  call    ?Validate@CExposedIterator@@QEBAJXZ; CExposedIterator::Validate(void)
0x18004e1b5  mov     ebx, eax
0x18004e1b7  test    eax, eax
0x18004e1b9  js      loc_18004E2A5
0x18004e1bf  mov     rcx, [rdi+40h]; this
0x18004e1c3  call    ?TakeSem@CPerContext@@QEAAJK@Z; CPerContext::TakeSem(ulong)
0x18004e1c8  mov     ebx, eax
0x18004e1ca  test    eax, eax
0x18004e1cc  js      loc_18004E2A5
0x18004e1d2  mov     rax, [rdi+30h]
0x18004e1d6  mov     rcx, [rdi+40h]
0x18004e1da  test    byte ptr [rax+14h], 20h
0x18004e1de  jz      short loc_18004E1F3
0x18004e1e0  add     rcx, 70h ; 'p'; this
0x18004e1e4  mov     ebx, 80030102h
0x18004e1e9  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x18004e1ee  jmp     loc_18004E2A5
0x18004e1f3  mov     rax, [rcx+10h]
0x18004e1f7  mov     rdx, [rdi+38h]
0x18004e1fb  mov     [rdx+20h], rax
0x18004e1ff  mov     rax, [rcx+18h]
0x18004e203  mov     [rdx+28h], rax
0x18004e207  mov     rax, [rcx+20h]
0x18004e20b  mov     ecx, 98h; cb
0x18004e210  mov     [rdx+30h], rax
0x18004e214  call    cs:__imp_CoTaskMemAlloc
0x18004e21a  test    rax, rax
0x18004e21d  jz      short loc_18004E23C
0x18004e21f  mov     rcx, [rdi+40h]
0x18004e223  lea     r8, [rdi+50h]; struct CDfName *
0x18004e227  mov     r9, [rdi+38h]; struct CDFBasis *
0x18004e22b  mov     rdx, [rdi+30h]; struct CPubDocFile *
0x18004e22f  mov     [rsp+48h+var_28], rcx; struct CPerContext *
0x18004e234  mov     rcx, rax; this
0x18004e237  call    ??0CExposedIterator@@QEAA@PEAVCPubDocFile@@PEAVCDfName@@PEAVCDFBasis@@PEAVCPerContext@@@Z; CExposedIterator::CExposedIterator(CPubDocFile *,CDfName *,CDFBasis *,CPerContext *)
0x18004e23c  mov     rdx, rax
0x18004e23f  lea     rcx, [rsp+48h+arg_0]
0x18004e244  call    ?Attach@?$ComPtr@UCExposedIterator@@@WRL@Microsoft@@QEAAXPEAUCExposedIterator@@@Z; Microsoft::WRL::ComPtr<CExposedIterator>::Attach(CExposedIterator *)
0x18004e249  mov     rax, [rsp+48h+arg_0]
0x18004e24e  test    rax, rax
0x18004e251  jnz     short loc_18004E25A
0x18004e253  mov     ebx, 80030008h
0x18004e258  jmp     short loc_18004E267
0x18004e25a  mov     rcx, [rdi+40h]
0x18004e25e  xor     ebx, ebx
0x18004e260  lock inc dword ptr [rcx+38h]
0x18004e264  mov     [rsi], rax
0x18004e267  mov     rcx, [rdi+40h]
0x18004e26b  add     rcx, 70h ; 'p'; this
0x18004e26f  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x18004e274  lea     r8, [rdi+10h]; struct CAsyncConnection *
0x18004e278  cmp     qword ptr [r8+10h], 0
0x18004e27d  jz      short loc_18004E2A5
0x18004e27f  mov     edx, 8; struct IConnectionPointContainer *
0x18004e284  lea     ecx, [rdx+8]; this
0x18004e287  call    ?InitClone@CAsyncConnection@@QEAAJPEAUIConnectionPointContainer@@PEAV1@@Z; CAsyncConnection::InitClone(IConnectionPointContainer *,CAsyncConnection *)
0x18004e28c  mov     ebx, eax
0x18004e28e  test    eax, eax
0x18004e290  jns     short loc_18004E2A5
0x18004e292  mov     rax, ds:0
0x18004e29a  xor     ecx, ecx
0x18004e29c  mov     rax, [rax+10h]
0x18004e2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2a5  lea     rcx, [rsp+48h+var_18]; this
0x18004e2aa  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18004e2af  mov     rsi, [rsp+48h+arg_10]
0x18004e2b4  mov     eax, ebx
0x18004e2b6  mov     rbx, [rsp+48h+arg_8]
0x18004e2bb  add     rsp, 40h
0x18004e2bf  pop     rdi
0x18004e2c0  retn
```
