# Dfdll::CFile::ReadToEnd(Dfdll::CString &)

- ea: `0x1800116ac`
- end: `0x18001179a`
- name: `?ReadToEnd@CFile@Dfdll@@QEAAJAEAVCString@2@@Z`
- size: `238`
- prototype: `__int64 __fastcall(Dfdll::CFile *this, struct Dfdll::CString *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001179c`

## callees

- `0x180002238`
- `0x18001140c`
- `0x1800116ac`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CFile::ReadToEnd(Dfdll::CFile *this, struct Dfdll::CString *a2)
{
  const struct std::nothrow_t *v3; // rdx
  int v4; // ebx
  unsigned int v5; // esi
  unsigned __int16 *v6; // rcx
  unsigned __int16 *v7; // r14
  void **v9; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-18h]
  unsigned int v11; // [rsp+30h] [rbp-10h]

  v10 = 0;
  v11 = 0;
  v9 = &Dfdll::CBuffer<unsigned char>::`vftable';
  v4 = Dfdll::CFile::ReadToEnd(this, &v9);
  if ( v4 < 0 )
  {
    v9 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v10 )
      operator delete(v10, v3);
    return (unsigned int)v4;
  }
  v5 = v11;
  v6 = v10;
  v7 = v10;
  if ( *((_DWORD *)a2 + 8) )
  {
    v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a2 + 1) + 40LL))((char *)a2 + 8, 0);
    if ( v4 < 0 )
      goto LABEL_11;
    v6 = v10;
  }
  *((_DWORD *)a2 + 8) = 0;
  if ( !v7 )
  {
    v4 = -2147024809;
    goto LABEL_12;
  }
  v4 = Dfdll::CString::Append(a2, v7, v5 >> 1);
  if ( v4 < 0 )
  {
LABEL_11:
    v6 = v10;
LABEL_12:
    v9 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v6 )
      operator delete(v6, v3);
    return (unsigned int)v4;
  }
  v4 = 0;
  v9 = &Dfdll::CBuffer<unsigned char>::`vftable';
  if ( v10 )
    operator delete(v10, v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800116ac  mov     [rsp-18h+arg_0], rbx
0x1800116b1  mov     [rsp-18h+arg_8], rsi
0x1800116b6  mov     [rsp-18h+arg_10], rdi
0x1800116bb  push    rbp
0x1800116bc  push    r12
0x1800116be  push    r14
0x1800116c0  mov     rbp, rsp
0x1800116c3  sub     rsp, 40h
0x1800116c7  mov     rdi, rdx
0x1800116ca  and     [rbp+var_18], 0
0x1800116cf  and     [rbp+var_10], 0
0x1800116d3  lea     r12, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x1800116da  mov     [rbp+var_20], r12
0x1800116de  lea     rdx, [rbp+var_20]
0x1800116e2  call    ?ReadToEnd@CFile@Dfdll@@QEAAJAEAV?$CBuffer@E@2@@Z; Dfdll::CFile::ReadToEnd(Dfdll::CBuffer<uchar> &)
0x1800116e7  mov     ebx, eax
0x1800116e9  test    eax, eax
0x1800116eb  jns     short loc_180011702
0x1800116ed  mov     [rbp+var_20], r12
0x1800116f1  mov     rcx, [rbp+var_18]; void *
0x1800116f5  test    rcx, rcx
0x1800116f8  jz      short loc_180011700
0x1800116fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800116ff  nop
0x180011700  jmp     short loc_18001177F
0x180011702  mov     esi, [rbp+var_10]
0x180011705  mov     rcx, [rbp+var_18]
0x180011709  mov     r14, rcx
0x18001170c  cmp     dword ptr [rdi+20h], 0
0x180011710  jbe     short loc_18001172F
0x180011712  lea     rcx, [rdi+8]
0x180011716  mov     rax, [rcx]
0x180011719  xor     edx, edx
0x18001171b  mov     rax, [rax+28h]
0x18001171f  call    cs:__guard_dispatch_icall_fptr
0x180011725  mov     ebx, eax
0x180011727  test    eax, eax
0x180011729  js      short loc_180011755
0x18001172b  mov     rcx, [rbp+var_18]
0x18001172f  and     dword ptr [rdi+20h], 0
0x180011733  test    r14, r14
0x180011736  jnz     short loc_18001173F
0x180011738  mov     ebx, 80070057h
0x18001173d  jmp     short loc_180011759
0x18001173f  shr     esi, 1
0x180011741  mov     r8d, esi; unsigned int
0x180011744  mov     rdx, r14; unsigned __int16 *
0x180011747  mov     rcx, rdi; this
0x18001174a  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x18001174f  mov     ebx, eax
0x180011751  test    eax, eax
0x180011753  jns     short loc_18001176A
0x180011755  mov     rcx, [rbp+var_18]; void *
0x180011759  mov     [rbp+var_20], r12
0x18001175d  test    rcx, rcx
0x180011760  jz      short loc_180011768
0x180011762  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011767  nop
0x180011768  jmp     short loc_18001177F
0x18001176a  xor     ebx, ebx
0x18001176c  mov     [rbp+var_20], r12
0x180011770  mov     rcx, [rbp+var_18]; void *
0x180011774  test    rcx, rcx
0x180011777  jz      short loc_18001177F
0x180011779  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001177e  nop
0x18001177f  mov     eax, ebx
0x180011781  mov     rbx, [rsp+40h+arg_0]
0x180011786  mov     rsi, [rsp+40h+arg_8]
0x18001178b  mov     rdi, [rsp+40h+arg_10]
0x180011790  add     rsp, 40h
0x180011794  pop     r14
0x180011796  pop     r12
0x180011798  pop     rbp
0x180011799  retn
```
