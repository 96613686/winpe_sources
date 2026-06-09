# Dfdll::CSubscription::~CSubscription(void)

- ea: `0x180008d34`
- end: `0x180008fd0`
- name: `??1CSubscription@Dfdll@@QEAA@XZ`
- size: `668`
- prototype: `void __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `13`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000444c`
- `0x180004580`
- `0x180004bcc`
- `0x180006180`
- `0x180006e60`
- `0x180007040`
- `0x180007130`
- `0x18001f0ce`
- `0x18001f0fe`
- `0x18001f116`
- `0x18001f1be`
- `0x18001f1ca`
- `0x18001f1d6`

## callees

- `0x180008d34`
- `0x180011a8c`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dfdll::CSubscription::~CSubscription(Dfdll::CSubscription *this)
{
  const struct std::nothrow_t *v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx

  Dfdll::CSubscription::Reset(this);
  v3 = *((_QWORD *)this + 22);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  *((_QWORD *)this + 22) = 0;
  v4 = *((_QWORD *)this + 24);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 24) = 0;
  v5 = *((_QWORD *)this + 18);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_QWORD *)this + 18) = 0;
  v6 = *((_QWORD *)this + 20);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *((_QWORD *)this + 20) = 0;
  v7 = *((_QWORD *)this + 16);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 23) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v8 = *((_QWORD *)this + 24);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 23) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 21) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v9 = *((_QWORD *)this + 22);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 21) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 19) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v10 = *((_QWORD *)this + 20);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 19) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 17) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v11 = *((_QWORD *)this + 18);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 15) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v12 = *((_QWORD *)this + 16);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 15) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 13) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v13 = *((_QWORD *)this + 14);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 13) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 11) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v14 = *((_QWORD *)this + 12);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 9) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v15 = *((_QWORD *)this + 10);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 7) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v16 = *((_QWORD *)this + 8);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 7) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 5) = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v17 = *((_QWORD *)this + 6);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v18 = (void *)*((_QWORD *)this + 2);
  if ( v18 )
    operator delete(v18, v2);
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180008d34  mov     [rsp+arg_0], rbx
0x180008d39  mov     [rsp+arg_8], rbp
0x180008d3e  mov     [rsp+arg_10], rsi
0x180008d43  push    rdi
0x180008d44  sub     rsp, 20h
0x180008d48  mov     rbx, rcx
0x180008d4b  call    ?Reset@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::Reset(void)
0x180008d50  mov     rcx, [rbx+0B0h]
0x180008d57  xor     edi, edi
0x180008d59  test    rcx, rcx
0x180008d5c  jz      short loc_180008D6B
0x180008d5e  mov     rax, [rcx]
0x180008d61  mov     rax, [rax+10h]
0x180008d65  call    cs:__guard_dispatch_icall_fptr
0x180008d6b  mov     [rbx+0B0h], rdi
0x180008d72  mov     rcx, [rbx+0C0h]
0x180008d79  test    rcx, rcx
0x180008d7c  jz      short loc_180008D8B
0x180008d7e  mov     rax, [rcx]
0x180008d81  mov     rax, [rax+10h]
0x180008d85  call    cs:__guard_dispatch_icall_fptr
0x180008d8b  mov     [rbx+0C0h], rdi
0x180008d92  mov     rcx, [rbx+90h]
0x180008d99  test    rcx, rcx
0x180008d9c  jz      short loc_180008DAB
0x180008d9e  mov     rax, [rcx]
0x180008da1  mov     rax, [rax+10h]
0x180008da5  call    cs:__guard_dispatch_icall_fptr
0x180008dab  mov     [rbx+90h], rdi
0x180008db2  mov     rcx, [rbx+0A0h]
0x180008db9  test    rcx, rcx
0x180008dbc  jz      short loc_180008DCB
0x180008dbe  mov     rax, [rcx]
0x180008dc1  mov     rax, [rax+10h]
0x180008dc5  call    cs:__guard_dispatch_icall_fptr
0x180008dcb  mov     [rbx+0A0h], rdi
0x180008dd2  mov     rcx, [rbx+80h]
0x180008dd9  test    rcx, rcx
0x180008ddc  jz      short loc_180008DEB
0x180008dde  mov     rax, [rcx]
0x180008de1  mov     rax, [rax+10h]
0x180008de5  call    cs:__guard_dispatch_icall_fptr
0x180008deb  mov     [rbx+80h], rdi
0x180008df2  lea     rbp, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180008df9  mov     [rbx+0B8h], rbp
0x180008e00  mov     rcx, [rbx+0C0h]
0x180008e07  test    rcx, rcx
0x180008e0a  jz      short loc_180008E19
0x180008e0c  mov     rax, [rcx]
0x180008e0f  mov     rax, [rax+10h]
0x180008e13  call    cs:__guard_dispatch_icall_fptr
0x180008e19  mov     [rbx+0C0h], rdi
0x180008e20  lea     rsi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008e27  mov     [rbx+0B8h], rsi
0x180008e2e  mov     [rbx+0A8h], rbp
0x180008e35  mov     rcx, [rbx+0B0h]
0x180008e3c  test    rcx, rcx
0x180008e3f  jz      short loc_180008E4E
0x180008e41  mov     rax, [rcx]
0x180008e44  mov     rax, [rax+10h]
0x180008e48  call    cs:__guard_dispatch_icall_fptr
0x180008e4e  mov     [rbx+0B0h], rdi
0x180008e55  mov     [rbx+0A8h], rsi
0x180008e5c  mov     [rbx+98h], rbp
0x180008e63  mov     rcx, [rbx+0A0h]
0x180008e6a  test    rcx, rcx
0x180008e6d  jz      short loc_180008E7C
0x180008e6f  mov     rax, [rcx]
0x180008e72  mov     rax, [rax+10h]
0x180008e76  call    cs:__guard_dispatch_icall_fptr
0x180008e7c  mov     [rbx+0A0h], rdi
0x180008e83  mov     [rbx+98h], rsi
0x180008e8a  mov     [rbx+88h], rbp
0x180008e91  mov     rcx, [rbx+90h]
0x180008e98  test    rcx, rcx
0x180008e9b  jz      short loc_180008EAA
0x180008e9d  mov     rax, [rcx]
0x180008ea0  mov     rax, [rax+10h]
0x180008ea4  call    cs:__guard_dispatch_icall_fptr
0x180008eaa  mov     [rbx+90h], rdi
0x180008eb1  mov     [rbx+88h], rsi
0x180008eb8  mov     [rbx+78h], rbp
0x180008ebc  mov     rcx, [rbx+80h]
0x180008ec3  test    rcx, rcx
0x180008ec6  jz      short loc_180008ED5
0x180008ec8  mov     rax, [rcx]
0x180008ecb  mov     rax, [rax+10h]
0x180008ecf  call    cs:__guard_dispatch_icall_fptr
0x180008ed5  mov     [rbx+80h], rdi
0x180008edc  mov     [rbx+78h], rsi
0x180008ee0  mov     [rbx+68h], rbp
0x180008ee4  mov     rcx, [rbx+70h]
0x180008ee8  test    rcx, rcx
0x180008eeb  jz      short loc_180008EFA
0x180008eed  mov     rax, [rcx]
0x180008ef0  mov     rax, [rax+10h]
0x180008ef4  call    cs:__guard_dispatch_icall_fptr
0x180008efa  mov     [rbx+70h], rdi
0x180008efe  mov     [rbx+68h], rsi
0x180008f02  mov     [rbx+58h], rbp
0x180008f06  mov     rcx, [rbx+60h]
0x180008f0a  test    rcx, rcx
0x180008f0d  jz      short loc_180008F1C
0x180008f0f  mov     rax, [rcx]
0x180008f12  mov     rax, [rax+10h]
0x180008f16  call    cs:__guard_dispatch_icall_fptr
0x180008f1c  mov     [rbx+60h], rdi
0x180008f20  mov     [rbx+58h], rsi
0x180008f24  mov     [rbx+48h], rbp
0x180008f28  mov     rcx, [rbx+50h]
0x180008f2c  test    rcx, rcx
0x180008f2f  jz      short loc_180008F3E
0x180008f31  mov     rax, [rcx]
0x180008f34  mov     rax, [rax+10h]
0x180008f38  call    cs:__guard_dispatch_icall_fptr
0x180008f3e  mov     [rbx+50h], rdi
0x180008f42  mov     [rbx+48h], rsi
0x180008f46  mov     [rbx+38h], rbp
0x180008f4a  mov     rcx, [rbx+40h]
0x180008f4e  test    rcx, rcx
0x180008f51  jz      short loc_180008F60
0x180008f53  mov     rax, [rcx]
0x180008f56  mov     rax, [rax+10h]
0x180008f5a  call    cs:__guard_dispatch_icall_fptr
0x180008f60  mov     [rbx+40h], rdi
0x180008f64  mov     [rbx+38h], rsi
0x180008f68  mov     [rbx+28h], rbp
0x180008f6c  mov     rcx, [rbx+30h]
0x180008f70  test    rcx, rcx
0x180008f73  jz      short loc_180008F82
0x180008f75  mov     rax, [rcx]
0x180008f78  mov     rax, [rax+10h]
0x180008f7c  call    cs:__guard_dispatch_icall_fptr
0x180008f82  mov     [rbx+30h], rdi
0x180008f86  mov     [rbx+28h], rsi
0x180008f8a  lea     rax, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180008f91  mov     [rbx], rax
0x180008f94  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180008f9b  mov     [rbx+8], rax
0x180008f9f  mov     rcx, [rbx+10h]; void *
0x180008fa3  test    rcx, rcx
0x180008fa6  jz      short loc_180008FAD
0x180008fa8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008fad  mov     [rbx+10h], rdi
0x180008fb1  mov     [rbx+18h], edi
0x180008fb4  mov     [rbx+8], rsi
0x180008fb8  mov     [rbx], rsi
0x180008fbb  mov     rbx, [rsp+28h+arg_0]
0x180008fc0  mov     rbp, [rsp+28h+arg_8]
0x180008fc5  mov     rsi, [rsp+28h+arg_10]
0x180008fca  add     rsp, 20h
0x180008fce  pop     rdi
0x180008fcf  retn
```
