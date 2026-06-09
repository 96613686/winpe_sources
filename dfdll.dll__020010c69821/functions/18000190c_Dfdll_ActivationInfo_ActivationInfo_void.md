# Dfdll::ActivationInfo::~ActivationInfo(void)

- ea: `0x18000190c`
- end: `0x1800019c4`
- name: `??1ActivationInfo@Dfdll@@QEAA@XZ`
- size: `184`
- prototype: `void __fastcall(Dfdll::ActivationInfo *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18000444c`
- `0x180004580`
- `0x18001f0da`
- `0x18001f10a`

## callees

- `0x18000190c`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dfdll::ActivationInfo::~ActivationInfo(Dfdll::ActivationInfo *this, const struct std::nothrow_t *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *((_QWORD *)this + 12) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 13) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v3 = (void *)*((_QWORD *)this + 14);
  if ( v3 )
    operator delete(v3, a2);
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 13) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 12) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 7) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 8) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
    operator delete(v4, a2);
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 8) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 7) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 2) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 3) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
    operator delete(v5, a2);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 3) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 2) = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x18000190c  mov     [rsp+arg_0], rbx
0x180001911  mov     [rsp+arg_8], rbp
0x180001916  mov     [rsp+arg_10], rsi
0x18000191b  push    r14
0x18000191d  sub     rsp, 20h
0x180001921  mov     rbx, rcx
0x180001924  lea     rbp, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x18000192b  mov     [rcx+60h], rbp
0x18000192f  lea     r14, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180001936  mov     [rcx+68h], r14
0x18000193a  mov     rcx, [rcx+70h]; void *
0x18000193e  test    rcx, rcx
0x180001941  jz      short loc_180001948
0x180001943  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001948  and     qword ptr [rbx+70h], 0
0x18000194d  and     dword ptr [rbx+78h], 0
0x180001951  lea     rsi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001958  mov     [rbx+68h], rsi
0x18000195c  mov     [rbx+60h], rsi
0x180001960  mov     [rbx+38h], rbp
0x180001964  mov     [rbx+40h], r14
0x180001968  mov     rcx, [rbx+48h]; void *
0x18000196c  test    rcx, rcx
0x18000196f  jz      short loc_180001976
0x180001971  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001976  and     qword ptr [rbx+48h], 0
0x18000197b  and     dword ptr [rbx+50h], 0
0x18000197f  mov     [rbx+40h], rsi
0x180001983  mov     [rbx+38h], rsi
0x180001987  mov     [rbx+10h], rbp
0x18000198b  mov     [rbx+18h], r14
0x18000198f  mov     rcx, [rbx+20h]; void *
0x180001993  test    rcx, rcx
0x180001996  jz      short loc_18000199D
0x180001998  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000199d  and     qword ptr [rbx+20h], 0
0x1800019a2  and     dword ptr [rbx+28h], 0
0x1800019a6  mov     [rbx+18h], rsi
0x1800019aa  mov     [rbx+10h], rsi
0x1800019ae  mov     rbx, [rsp+28h+arg_0]
0x1800019b3  mov     rbp, [rsp+28h+arg_8]
0x1800019b8  mov     rsi, [rsp+28h+arg_10]
0x1800019bd  add     rsp, 20h
0x1800019c1  pop     r14
0x1800019c3  retn
```
