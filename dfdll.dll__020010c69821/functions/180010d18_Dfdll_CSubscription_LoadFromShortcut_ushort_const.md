# Dfdll::CSubscription::LoadFromShortcut(ushort const *)

- ea: `0x180010d18`
- end: `0x180010ea7`
- name: `?LoadFromShortcut@CSubscription@Dfdll@@QEAAJPEBG@Z`
- size: `399`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180004580`
- `0x180004bcc`
- `0x180006e60`
- `0x180007130`

## callees

- `0x18000a040`
- `0x18000c954`
- `0x180010d18`
- `0x180011a8c`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::LoadFromShortcut(Dfdll::CSubscription *this, const unsigned __int16 *a2)
{
  int DefinitionIdentityFromShortcutFile; // ebx
  const struct std::nothrow_t *v5; // rdx
  const struct std::nothrow_t *v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  void **v9; // [rsp+30h] [rbp-30h] BYREF
  void **v10; // [rsp+38h] [rbp-28h]
  void *v11; // [rsp+40h] [rbp-20h]
  int v12; // [rsp+48h] [rbp-18h]
  int v13; // [rsp+50h] [rbp-10h]

  DefinitionIdentityFromShortcutFile = Dfdll::CSubscription::Reset(this);
  if ( DefinitionIdentityFromShortcutFile < 0 )
    return (unsigned int)DefinitionIdentityFromShortcutFile;
  DefinitionIdentityFromShortcutFile = Dfdll::CSubscription::EnsureInitialization(this);
  if ( DefinitionIdentityFromShortcutFile < 0 )
    return (unsigned int)DefinitionIdentityFromShortcutFile;
  v9 = &Dfdll::CString::`vftable';
  v11 = 0;
  v12 = 0;
  v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v13 = 0;
  DefinitionIdentityFromShortcutFile = Dfdll::CShortcutFile::GetDefinitionIdentityFromShortcutFile(
                                         a2,
                                         (struct Dfdll::CString *)&v9);
  if ( DefinitionIdentityFromShortcutFile < 0 )
  {
    v9 = &Dfdll::CString::`vftable';
    v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v11 )
      operator delete(v11, v5);
    return (unsigned int)DefinitionIdentityFromShortcutFile;
  }
  if ( !v13 )
  {
    DefinitionIdentityFromShortcutFile = -2147024809;
    goto LABEL_9;
  }
  DefinitionIdentityFromShortcutFile = Dfdll::CSubscription::EnsureInitialization(this);
  if ( DefinitionIdentityFromShortcutFile < 0
    || (DefinitionIdentityFromShortcutFile = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, char *))(**((_QWORD **)this + 18) + 24LL))(
                                               *((_QWORD *)this + 18),
                                               0,
                                               v11,
                                               (char *)this + 48),
        DefinitionIdentityFromShortcutFile < 0) )
  {
LABEL_9:
    v9 = &Dfdll::CString::`vftable';
    v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v11 )
      operator delete(v11, v5);
    return (unsigned int)DefinitionIdentityFromShortcutFile;
  }
  DefinitionIdentityFromShortcutFile = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 20) + 136LL))(
                                         *((_QWORD *)this + 20),
                                         (char *)this + 64);
  if ( DefinitionIdentityFromShortcutFile >= 0 )
  {
    DefinitionIdentityFromShortcutFile = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 8)
                                                                                            + 64LL))(
                                           *((_QWORD *)this + 8),
                                           1,
                                           (char *)this + 48);
    if ( DefinitionIdentityFromShortcutFile >= 0 )
    {
      DefinitionIdentityFromShortcutFile = 0;
      v9 = &Dfdll::CString::`vftable';
      v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v11 )
        operator delete(v11, v8);
    }
    else
    {
      v9 = &Dfdll::CString::`vftable';
      v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v11 )
        operator delete(v11, v8);
    }
  }
  else
  {
    v9 = &Dfdll::CString::`vftable';
    v10 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v11 )
      operator delete(v11, v7);
  }
  return (unsigned int)DefinitionIdentityFromShortcutFile;
}

```

## disassembly

```asm
0x180010d18  mov     [rsp-18h+arg_0], rbx
0x180010d1d  mov     [rsp-18h+arg_8], rsi
0x180010d22  mov     [rsp-18h+arg_10], rdi
0x180010d27  push    rbp
0x180010d28  push    r12
0x180010d2a  push    r15
0x180010d2c  mov     rbp, rsp
0x180010d2f  sub     rsp, 60h
0x180010d33  mov     rsi, rdx
0x180010d36  mov     rdi, rcx
0x180010d39  call    ?Reset@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::Reset(void)
0x180010d3e  mov     ebx, eax
0x180010d40  test    eax, eax
0x180010d42  js      short loc_180010DC2
0x180010d44  mov     rcx, rdi; this
0x180010d47  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180010d4c  mov     ebx, eax
0x180010d4e  test    eax, eax
0x180010d50  js      short loc_180010DC2
0x180010d52  lea     r15, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180010d59  mov     [rbp+var_30], r15
0x180010d5d  and     [rbp+var_20], 0
0x180010d62  and     [rbp+var_18], 0
0x180010d66  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180010d6d  mov     [rbp+var_28], r12
0x180010d71  and     [rbp+var_10], 0
0x180010d75  lea     rdx, [rbp+var_30]; struct Dfdll::CString *
0x180010d79  mov     rcx, rsi; unsigned __int16 *
0x180010d7c  call    ?GetDefinitionIdentityFromShortcutFile@CShortcutFile@Dfdll@@SAJPEBGAEAVCString@2@@Z; Dfdll::CShortcutFile::GetDefinitionIdentityFromShortcutFile(ushort const *,Dfdll::CString &)
0x180010d81  mov     ebx, eax
0x180010d83  test    eax, eax
0x180010d85  jns     short loc_180010DA0
0x180010d87  mov     [rbp+var_30], r15
0x180010d8b  mov     [rbp+var_28], r12
0x180010d8f  mov     rcx, [rbp+var_20]; void *
0x180010d93  test    rcx, rcx
0x180010d96  jz      short loc_180010D9E
0x180010d98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010d9d  nop
0x180010d9e  jmp     short loc_180010DC2
0x180010da0  cmp     [rbp+var_10], 0
0x180010da4  jnz     short loc_180010DDE
0x180010da6  mov     ebx, 80070057h
0x180010dab  mov     [rbp+var_30], r15
0x180010daf  mov     [rbp+var_28], r12
0x180010db3  mov     rcx, [rbp+var_20]; void *
0x180010db7  test    rcx, rcx
0x180010dba  jz      short loc_180010DC2
0x180010dbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010dc1  nop
0x180010dc2  mov     eax, ebx
0x180010dc4  lea     r11, [rsp+60h+var_s0]
0x180010dc9  mov     rbx, [r11+20h]
0x180010dcd  mov     rsi, [r11+28h]
0x180010dd1  mov     rdi, [r11+30h]
0x180010dd5  mov     rsp, r11
0x180010dd8  pop     r15
0x180010dda  pop     r12
0x180010ddc  pop     rbp
0x180010ddd  retn
0x180010dde  mov     rcx, rdi; this
0x180010de1  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180010de6  mov     ebx, eax
0x180010de8  test    eax, eax
0x180010dea  js      short loc_180010DAB
0x180010dec  mov     rcx, [rdi+90h]
0x180010df3  mov     rax, [rcx]
0x180010df6  lea     r9, [rdi+30h]
0x180010dfa  mov     r8, [rbp+var_20]
0x180010dfe  xor     edx, edx
0x180010e00  mov     rax, [rax+18h]
0x180010e04  call    cs:__guard_dispatch_icall_fptr
0x180010e0a  mov     ebx, eax
0x180010e0c  test    eax, eax
0x180010e0e  js      short loc_180010DAB
0x180010e10  mov     rcx, [rdi+0A0h]
0x180010e17  mov     rax, [rcx]
0x180010e1a  lea     rdx, [rdi+40h]
0x180010e1e  mov     rax, [rax+88h]
0x180010e25  call    cs:__guard_dispatch_icall_fptr
0x180010e2b  mov     ebx, eax
0x180010e2d  test    eax, eax
0x180010e2f  jns     short loc_180010E4D
0x180010e31  mov     [rbp+var_30], r15
0x180010e35  mov     [rbp+var_28], r12
0x180010e39  mov     rcx, [rbp+var_20]; void *
0x180010e3d  test    rcx, rcx
0x180010e40  jz      short loc_180010E48
0x180010e42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010e47  nop
0x180010e48  jmp     loc_180010DC2
0x180010e4d  mov     rcx, [rdi+40h]
0x180010e51  mov     rax, [rcx]
0x180010e54  lea     r8, [rdi+30h]
0x180010e58  mov     edx, 1
0x180010e5d  mov     rax, [rax+40h]
0x180010e61  call    cs:__guard_dispatch_icall_fptr
0x180010e67  mov     ebx, eax
0x180010e69  test    eax, eax
0x180010e6b  jns     short loc_180010E89
0x180010e6d  mov     [rbp+var_30], r15
0x180010e71  mov     [rbp+var_28], r12
0x180010e75  mov     rcx, [rbp+var_20]; void *
0x180010e79  test    rcx, rcx
0x180010e7c  jz      short loc_180010E84
0x180010e7e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010e83  nop
0x180010e84  jmp     loc_180010DC2
0x180010e89  xor     ebx, ebx
0x180010e8b  mov     [rbp+var_30], r15
0x180010e8f  mov     [rbp+var_28], r12
0x180010e93  mov     rcx, [rbp+var_20]; void *
0x180010e97  test    rcx, rcx
0x180010e9a  jz      short loc_180010EA2
0x180010e9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010ea1  nop
0x180010ea2  jmp     loc_180010DC2
```
