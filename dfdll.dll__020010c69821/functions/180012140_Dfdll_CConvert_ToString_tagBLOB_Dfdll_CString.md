# Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)

- ea: `0x180012140`
- end: `0x1800122cb`
- name: `?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z`
- size: `395`
- prototype: `static int(struct tagBLOB *, struct Dfdll::CString *)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18000949c`
- `0x18000972c`
- `0x180009c44`
- `0x180009e0c`
- `0x18000a2ac`
- `0x180010f34`

## callees

- `0x180001fc8`
- `0x180002238`
- `0x1800026bc`
- `0x180012140`
- `0x180012b30`
- `0x1800140a0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CConvert::ToString(struct tagBLOB *a1, struct Dfdll::CString *a2)
{
  ULONG v4; // edi
  const struct std::nothrow_t *v5; // rdx
  int v6; // ebx
  BYTE *pBlobData; // r14
  unsigned int v8; // ecx
  unsigned __int16 *v9; // r14
  const struct std::nothrow_t *v10; // rdx
  void **v12; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v13; // [rsp+28h] [rbp-18h]
  ULONG v14; // [rsp+30h] [rbp-10h]
  void *v15; // [rsp+60h] [rbp+20h] BYREF

  v4 = a1->cbSize >> 1;
  v13 = 0;
  v14 = 0;
  v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v6 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v12, v4);
  if ( v6 < 0 )
  {
    v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v13 )
      operator delete(v13, v5);
    return (unsigned int)v6;
  }
  pBlobData = a1->pBlobData;
  if ( !pBlobData )
    goto LABEL_6;
  if ( v4 )
  {
    if ( !v14 || v14 < v4 )
    {
LABEL_6:
      v6 = -2147024809;
      goto LABEL_7;
    }
    v15 = 0;
    v6 = ((__int64 (__fastcall *)(void ***, _QWORD, void **))v12[8])(&v12, 0, &v15);
    if ( v6 < 0 )
    {
LABEL_7:
      v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v13 )
        operator delete(v13, v5);
      return (unsigned int)v6;
    }
    v8 = ((__int64 (__fastcall *)(void ***))v12[9])(&v12);
    if ( v8 )
    {
      v5 = (const struct std::nothrow_t *)(0xFFFFFFFF % v8);
      if ( v4 > 0xFFFFFFFF / v8 )
      {
        v6 = -2147024362;
        goto LABEL_7;
      }
      v8 *= v4;
    }
    memmove(v15, pBlobData, v8);
  }
  v9 = v13;
  if ( !v13 )
  {
    v6 = Dfdll::CString::AssignNULL(a2);
LABEL_24:
    if ( v6 < 0 )
      goto LABEL_25;
    goto LABEL_28;
  }
  if ( *((_DWORD *)a2 + 8) )
  {
    v6 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a2 + 1) + 40LL))((char *)a2 + 8, 0);
    if ( v6 < 0 )
    {
LABEL_25:
      v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v13 )
        operator delete(v13, v10);
      return (unsigned int)v6;
    }
  }
  *((_DWORD *)a2 + 8) = 0;
  v6 = Dfdll::CString::Append(a2, (struct std::nothrow_t *)v9, v4);
  if ( v6 < 0 )
    goto LABEL_24;
LABEL_28:
  v6 = 0;
  v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v13 )
    operator delete(v13, v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012140  mov     [rsp-18h+arg_8], rbx
0x180012145  mov     [rsp-18h+arg_10], rsi
0x18001214a  mov     [rsp-18h+arg_18], rdi
0x18001214f  push    rbp
0x180012150  push    r12
0x180012152  push    r14
0x180012154  mov     rbp, rsp
0x180012157  sub     rsp, 40h
0x18001215b  mov     rsi, rdx
0x18001215e  mov     r14, rcx
0x180012161  mov     edi, [rcx]
0x180012163  shr     edi, 1
0x180012165  and     [rbp+var_18], 0
0x18001216a  and     [rbp+var_10], 0
0x18001216e  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180012175  mov     [rbp+var_20], r12
0x180012179  mov     edx, edi; unsigned int
0x18001217b  lea     rcx, [rbp+var_20]; this
0x18001217f  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180012184  mov     ebx, eax
0x180012186  test    eax, eax
0x180012188  jns     short loc_1800121A2
0x18001218a  mov     [rbp+var_20], r12
0x18001218e  mov     rcx, [rbp+var_18]; void *
0x180012192  test    rcx, rcx
0x180012195  jz      short loc_18001219D
0x180012197  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001219c  nop
0x18001219d  jmp     loc_1800122B0
0x1800121a2  mov     r14, [r14+8]
0x1800121a6  test    r14, r14
0x1800121a9  jnz     short loc_1800121C8
0x1800121ab  mov     ebx, 80070057h
0x1800121b0  mov     [rbp+var_20], r12
0x1800121b4  mov     rcx, [rbp+var_18]; void *
0x1800121b8  test    rcx, rcx
0x1800121bb  jz      short loc_1800121C3
0x1800121bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800121c2  nop
0x1800121c3  jmp     loc_1800122B0
0x1800121c8  test    edi, edi
0x1800121ca  jz      short loc_180012236
0x1800121cc  mov     eax, [rbp+var_10]
0x1800121cf  test    eax, eax
0x1800121d1  jz      short loc_1800121AB
0x1800121d3  cmp     eax, edi
0x1800121d5  jb      short loc_1800121AB
0x1800121d7  and     [rbp+arg_0], 0
0x1800121dc  mov     rax, [rbp+var_20]
0x1800121e0  lea     r8, [rbp+arg_0]
0x1800121e4  xor     edx, edx
0x1800121e6  lea     rcx, [rbp+var_20]
0x1800121ea  mov     rax, [rax+40h]
0x1800121ee  call    cs:__guard_dispatch_icall_fptr
0x1800121f4  mov     ebx, eax
0x1800121f6  test    eax, eax
0x1800121f8  js      short loc_1800121B0
0x1800121fa  mov     rax, [rbp+var_20]
0x1800121fe  lea     rcx, [rbp+var_20]
0x180012202  mov     rax, [rax+48h]
0x180012206  call    cs:__guard_dispatch_icall_fptr
0x18001220c  mov     ecx, eax
0x18001220e  test    eax, eax
0x180012210  jz      short loc_180012227
0x180012212  xor     edx, edx
0x180012214  or      eax, 0FFFFFFFFh
0x180012217  div     ecx
0x180012219  cmp     edi, eax
0x18001221b  jbe     short loc_180012224
0x18001221d  mov     ebx, 80070216h
0x180012222  jmp     short loc_1800121B0
0x180012224  imul    ecx, edi
0x180012227  mov     r8d, ecx; Size
0x18001222a  mov     rdx, r14; Src
0x18001222d  mov     rcx, [rbp+arg_0]; void *
0x180012231  call    memmove
0x180012236  mov     r14, [rbp+var_18]
0x18001223a  test    r14, r14
0x18001223d  jnz     short loc_18001224B
0x18001223f  mov     rcx, rsi; this
0x180012242  call    ?AssignNULL@CString@Dfdll@@IEAAJXZ; Dfdll::CString::AssignNULL(void)
0x180012247  mov     ebx, eax
0x180012249  jmp     short loc_180012282
0x18001224b  cmp     dword ptr [rsi+20h], 0
0x18001224f  jbe     short loc_18001226A
0x180012251  lea     rcx, [rsi+8]
0x180012255  mov     rax, [rcx]
0x180012258  xor     edx, edx
0x18001225a  mov     rax, [rax+28h]
0x18001225e  call    cs:__guard_dispatch_icall_fptr
0x180012264  mov     ebx, eax
0x180012266  test    eax, eax
0x180012268  js      short loc_180012286
0x18001226a  and     dword ptr [rsi+20h], 0
0x18001226e  mov     r8d, edi; unsigned int
0x180012271  mov     rdx, r14; unsigned __int16 *
0x180012274  mov     rcx, rsi; this
0x180012277  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x18001227c  mov     ebx, eax
0x18001227e  test    eax, eax
0x180012280  jns     short loc_18001229B
0x180012282  test    ebx, ebx
0x180012284  jns     short loc_18001229B
0x180012286  mov     [rbp+var_20], r12
0x18001228a  mov     rcx, [rbp+var_18]; void *
0x18001228e  test    rcx, rcx
0x180012291  jz      short loc_180012299
0x180012293  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012298  nop
0x180012299  jmp     short loc_1800122B0
0x18001229b  xor     ebx, ebx
0x18001229d  mov     [rbp+var_20], r12
0x1800122a1  mov     rcx, [rbp+var_18]; void *
0x1800122a5  test    rcx, rcx
0x1800122a8  jz      short loc_1800122B0
0x1800122aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800122af  nop
0x1800122b0  mov     eax, ebx
0x1800122b2  mov     rbx, [rsp+40h+arg_8]
0x1800122b7  mov     rsi, [rsp+40h+arg_10]
0x1800122bc  mov     rdi, [rsp+40h+arg_18]
0x1800122c1  add     rsp, 40h
0x1800122c5  pop     r14
0x1800122c7  pop     r12
0x1800122c9  pop     rbp
0x1800122ca  retn
```
