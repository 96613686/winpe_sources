# CExposedIterator::Release(void)

- ea: `0x180024720`
- end: `0x180024806`
- name: `?Release@CExposedIterator@@UEAAKXZ`
- size: `230`
- prototype: `unsigned int __fastcall(CExposedIterator *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e3f0`

## callees

- `0x180018680`
- `0x180018914`
- `0x18001a510`
- `0x18001b840`
- `0x18001b89c`
- `0x18001bf68`
- `0x18001c268`
- `0x18002366c`
- `0x180024720`
- `0x18004e0a4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247a7`

## pseudocode

```c
__int64 __fastcall CExposedIterator::Release(CExposedIterator *this)
{
  unsigned __int32 v2; // edi
  HANDLE *v3; // rbp
  CPerContext *v4; // rcx
  int v5; // r14d
  int v6; // eax
  _QWORD *v7; // rdx
  _QWORD *v8; // r8
  __int64 v9; // rsi
  CSmAllocator *TlsSmAllocator; // rax
  _BYTE v12[56]; // [rsp+20h] [rbp-38h] BYREF

  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v12, *((struct CPerContext **)this + 8));
  if ( (int)CExposedIterator::Validate(this) >= 0 )
  {
    v3 = (HANDLE *)*((_QWORD *)this + 8);
    v2 = _InterlockedDecrement((volatile signed __int32 *)this + 18);
    if ( !v2 )
    {
      v4 = (CPerContext *)*((_QWORD *)this + 8);
      v5 = 0;
      if ( v4 )
      {
        v6 = CPerContext::TakeSem(v4);
        v7 = (_QWORD *)*((_QWORD *)this + 8);
        v5 = v6;
        v8 = (_QWORD *)*((_QWORD *)this + 7);
        v8[4] = v7[2];
        v8[5] = v7[3];
        v8[6] = v7[4];
      }
      v9 = *((_QWORD *)this + 4);
      CExposedIterator::~CExposedIterator(this);
      CoTaskMemFree(this);
      if ( v3 )
      {
        if ( (unsigned int)CPerContext::Release((CPerContext *)v3) )
        {
          if ( v5 >= 0 )
            CDfMutex::Release(v3 + 14);
        }
        else
        {
          TlsSmAllocator = GetTlsSmAllocator();
          CSmAllocator::Uninit(TlsSmAllocator);
        }
      }
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  else
  {
    v2 = 0;
  }
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v12);
  return v2;
}

```

## disassembly

```asm
0x180024720  push    rbx
0x180024722  push    rbp
0x180024723  push    rsi
0x180024724  push    rdi
0x180024725  push    r14
0x180024727  sub     rsp, 30h
0x18002472b  mov     rdx, [rcx+40h]; struct CPerContext *
0x18002472f  mov     rbx, rcx
0x180024732  lea     rcx, [rsp+58h+var_38]; this
0x180024737  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x18002473c  mov     rcx, rbx; this
0x18002473f  call    ?Validate@CExposedIterator@@QEBAJXZ; CExposedIterator::Validate(void)
0x180024744  test    eax, eax
0x180024746  jns     short loc_18002474F
0x180024748  xor     edi, edi
0x18002474a  jmp     loc_1800247EF
0x18002474f  mov     rbp, [rbx+40h]
0x180024753  or      edi, 0FFFFFFFFh
0x180024756  lock xadd [rbx+48h], edi
0x18002475b  sub     edi, 1
0x18002475e  jnz     loc_1800247EF
0x180024764  mov     rcx, [rbx+40h]; this
0x180024768  xor     r14d, r14d
0x18002476b  test    rcx, rcx
0x18002476e  jz      short loc_180024798
0x180024770  call    ?TakeSem@CPerContext@@QEAAJK@Z; CPerContext::TakeSem(ulong)
0x180024775  mov     rdx, [rbx+40h]
0x180024779  mov     r14d, eax
0x18002477c  mov     r8, [rbx+38h]
0x180024780  mov     rcx, [rdx+10h]
0x180024784  mov     [r8+20h], rcx
0x180024788  mov     rcx, [rdx+18h]
0x18002478c  mov     [r8+28h], rcx
0x180024790  mov     rcx, [rdx+20h]
0x180024794  mov     [r8+30h], rcx
0x180024798  mov     rsi, [rbx+20h]
0x18002479c  mov     rcx, rbx; this
0x18002479f  call    ??1CExposedIterator@@QEAA@XZ; CExposedIterator::~CExposedIterator(void)
0x1800247a4  mov     rcx, rbx; pv
0x1800247a7  call    cs:__imp_CoTaskMemFree
0x1800247ad  test    rbp, rbp
0x1800247b0  jz      short loc_1800247DB
0x1800247b2  mov     rcx, rbp; this
0x1800247b5  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x1800247ba  test    eax, eax
0x1800247bc  jnz     short loc_1800247CD
0x1800247be  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x1800247c3  mov     rcx, rax; this
0x1800247c6  call    ?Uninit@CSmAllocator@@QEAAJXZ; CSmAllocator::Uninit(void)
0x1800247cb  jmp     short loc_1800247DB
0x1800247cd  test    r14d, r14d
0x1800247d0  js      short loc_1800247DB
0x1800247d2  lea     rcx, [rbp+70h]; this
0x1800247d6  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x1800247db  test    rsi, rsi
0x1800247de  jz      short loc_1800247EF
0x1800247e0  mov     rdx, [rsi]
0x1800247e3  mov     rcx, rsi
0x1800247e6  mov     rax, [rdx+10h]
0x1800247ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ef  lea     rcx, [rsp+58h+var_38]; this
0x1800247f4  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x1800247f9  mov     eax, edi
0x1800247fb  add     rsp, 30h
0x1800247ff  pop     r14
0x180024801  pop     rdi
0x180024802  pop     rsi
0x180024803  pop     rbp
0x180024804  pop     rbx
0x180024805  retn
```
