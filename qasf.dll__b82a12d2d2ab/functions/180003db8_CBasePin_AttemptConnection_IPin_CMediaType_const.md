# CBasePin::AttemptConnection(IPin *,CMediaType const *)

- ea: `0x180003db8`
- end: `0x180003eca`
- name: `?AttemptConnection@CBasePin@@IEAAJPEAUIPin@@PEBVCMediaType@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(CBasePin *__hidden this, struct IPin *, const struct CMediaType *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003984`

## callees

- `0x180003db8`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CBasePin::AttemptConnection(CBasePin *this, struct IPin *a2, const struct CMediaType *a3)
{
  int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rcx

  v6 = (*(__int64 (__fastcall **)(CBasePin *))(*(_QWORD *)this + 80LL))(this);
  v7 = *(_QWORD *)this;
  if ( v6 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CBasePin *, const struct CMediaType *))(v7 + 64))(this, a3);
    v6 = v8;
    if ( v8 )
    {
      if ( v8 >= 0 || v8 == -2147467259 || v8 == -2147024809 )
        v6 = -2147220950;
    }
    else
    {
      *((_QWORD *)this + 6) = a2;
      ((void (__fastcall *)(struct IPin *))a2->lpVtbl->AddRef)(a2);
      v6 = (*(__int64 (__fastcall **)(CBasePin *, const struct CMediaType *))(*(_QWORD *)this + 72LL))(this, a3);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(struct IPin *, unsigned __int64, const struct CMediaType *))a2->lpVtbl->ReceiveConnection)(
               a2,
               ((unsigned __int64)this + 24) & -(__int64)(this != 0),
               a3);
        if ( v6 >= 0 )
        {
          result = (*(__int64 (__fastcall **)(CBasePin *, struct IPin *))(*(_QWORD *)this + 96LL))(this, a2);
          v6 = result;
          if ( (int)result >= 0 )
            return result;
          ((void (__fastcall *)(struct IPin *))a2->lpVtbl->Disconnect)(a2);
        }
      }
    }
    (*(void (__fastcall **)(CBasePin *))(*(_QWORD *)this + 88LL))(this);
    v10 = *((_QWORD *)this + 6);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 6) = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(CBasePin *))(v7 + 88))(this);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003db8  push    rbx
0x180003dba  push    rbp
0x180003dbb  push    rsi
0x180003dbc  push    rdi
0x180003dbd  sub     rsp, 28h
0x180003dc1  mov     rax, [rcx]
0x180003dc4  mov     rbp, r8
0x180003dc7  mov     rsi, rdx
0x180003dca  mov     rdi, rcx
0x180003dcd  mov     rax, [rax+50h]
0x180003dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd6  mov     ebx, eax
0x180003dd8  mov     rcx, rdi
0x180003ddb  mov     rax, [rdi]
0x180003dde  test    ebx, ebx
0x180003de0  jns     short loc_180003DF0
0x180003de2  mov     rax, [rax+58h]
0x180003de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003deb  jmp     loc_180003EBF
0x180003df0  mov     rax, [rax+40h]
0x180003df4  mov     rdx, rbp
0x180003df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dfc  mov     ebx, eax
0x180003dfe  test    eax, eax
0x180003e00  jnz     short loc_180003E7E
0x180003e02  mov     [rdi+30h], rsi
0x180003e06  mov     rcx, rsi
0x180003e09  mov     rax, [rsi]
0x180003e0c  mov     rax, [rax+8]
0x180003e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e15  mov     rax, [rdi]
0x180003e18  mov     rdx, rbp
0x180003e1b  mov     rcx, rdi
0x180003e1e  mov     rax, [rax+48h]
0x180003e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e27  mov     ebx, eax
0x180003e29  test    eax, eax
0x180003e2b  js      short loc_180003E93
0x180003e2d  mov     r9, [rsi]
0x180003e30  lea     rcx, [rdi+18h]
0x180003e34  mov     rax, rdi
0x180003e37  mov     r8, rbp
0x180003e3a  neg     rax
0x180003e3d  mov     rax, [r9+20h]
0x180003e41  sbb     rdx, rdx
0x180003e44  and     rdx, rcx
0x180003e47  mov     rcx, rsi
0x180003e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e4f  mov     ebx, eax
0x180003e51  test    eax, eax
0x180003e53  js      short loc_180003E93
0x180003e55  mov     rax, [rdi]
0x180003e58  mov     rdx, rsi
0x180003e5b  mov     rcx, rdi
0x180003e5e  mov     rax, [rax+60h]
0x180003e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e67  mov     ebx, eax
0x180003e69  test    eax, eax
0x180003e6b  jns     short loc_180003EC1
0x180003e6d  mov     rax, [rsi]
0x180003e70  mov     rcx, rsi
0x180003e73  mov     rax, [rax+28h]
0x180003e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7c  jmp     short loc_180003E93
0x180003e7e  jns     short loc_180003E8E
0x180003e80  cmp     eax, 80004005h
0x180003e85  jz      short loc_180003E8E
0x180003e87  cmp     eax, 80070057h
0x180003e8c  jnz     short loc_180003E93
0x180003e8e  mov     ebx, 8004022Ah
0x180003e93  mov     rax, [rdi]
0x180003e96  mov     rcx, rdi
0x180003e99  mov     rax, [rax+58h]
0x180003e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea2  mov     rcx, [rdi+30h]
0x180003ea6  test    rcx, rcx
0x180003ea9  jz      short loc_180003EBF
0x180003eab  mov     rax, [rcx]
0x180003eae  mov     rax, [rax+10h]
0x180003eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb7  mov     qword ptr [rdi+30h], 0
0x180003ebf  mov     eax, ebx
0x180003ec1  add     rsp, 28h
0x180003ec5  pop     rdi
0x180003ec6  pop     rsi
0x180003ec7  pop     rbp
0x180003ec8  pop     rbx
0x180003ec9  retn
```
