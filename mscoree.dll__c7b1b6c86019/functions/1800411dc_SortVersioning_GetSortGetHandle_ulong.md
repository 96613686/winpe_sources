# SortVersioning::GetSortGetHandle(ulong)

- ea: `0x1800411dc`
- end: `0x1800413cc`
- name: `?GetSortGetHandle@SortVersioning@@YAP6APEAUsorting_handle@1@PEBGPEBU_nlsversioninfo@@K@ZK@Z`
- size: `496`
- prototype: `struct SortVersioning::sorting_handle *(*__fastcall(SortVersioning *__hidden this, unsigned int))(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180040a20`
- `0x18004176c`

## callees

- `0x1800411dc`
- `0x180041658`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18004123a`
- `KERNEL32!EncodePointer` at `0x18004124b`
- `KERNEL32!EncodePointer` at `0x18004132f`
- `KERNEL32!EncodePointer` at `0x180041343`
- `KERNEL32!EncodePointer` at `0x18004137f`
- `KERNEL32!EncodePointer` at `0x18004138f`
- `KERNEL32!EncodePointer` at `0x18004123a`
- `KERNEL32!EncodePointer` at `0x18004124b`
- `KERNEL32!EncodePointer` at `0x18004132f`
- `KERNEL32!EncodePointer` at `0x180041343`
- `KERNEL32!EncodePointer` at `0x18004137f`
- `KERNEL32!EncodePointer` at `0x18004138f`
- `KERNEL32!DecodePointer` at `0x180041359`
- `KERNEL32!DecodePointer` at `0x180041369`
- `KERNEL32!DecodePointer` at `0x1800413a8`
- `KERNEL32!DecodePointer` at `0x180041359`
- `KERNEL32!DecodePointer` at `0x180041369`
- `KERNEL32!DecodePointer` at `0x1800413a8`

## string_xrefs

- `0x180041223`: `nlssorting.dll`
- `0x180041315`: `nlssorting.dll`
- `0x180041277`: `Sort00000000.dll`

## pseudocode

```c
struct SortVersioning::sorting_handle *(*__fastcall SortVersioning::GetSortGetHandle(
        SortVersioning *this))(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int)
{
  PVOID v1; // rax
  __int64 *v2; // r8
  unsigned int v3; // r9d
  __int64 v4; // rax
  HINSTANCE SortModuleAndInvariant; // rax
  PVOID v6; // rbx
  PVOID v7; // rax
  PVOID v8; // rdi
  PVOID v10; // [rsp+20h] [rbp-40h] BYREF
  PVOID Ptr; // [rsp+28h] [rbp-38h] BYREF
  __int128 i; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h]
  __int64 v14; // [rsp+48h] [rbp-18h] BYREF
  __int16 v15; // [rsp+50h] [rbp-10h]

  if ( (_DWORD)this == 393216 )
  {
    if ( qword_18005FFB8 == -1 )
    {
      Ptr = 0;
      qword_18005FFB8 = (__int64)SortVersioning::LoadSortModuleAndInvariant(
                                   (SortVersioning *)L"nlssorting.dll",
                                   (const unsigned __int16 *)0x60000,
                                   (unsigned int)&v10,
                                   (struct SortVersioning::sorting_handle *(**)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int))&Ptr,
                                   0);
      qword_180061B38 = EncodePointer(Ptr);
      v1 = EncodePointer(v10);
      qword_180061B30 = v1;
    }
    else
    {
      v1 = qword_180061B30;
    }
  }
  else if ( qword_18005FFC0 == -1 )
  {
    v2 = &v14;
    v13 = *(_QWORD *)L"0000.dll";
    v3 = (unsigned int)this;
    v14 = 0x6C006C0064002ELL;
    v15 = 0;
    for ( i = *(_OWORD *)L"Sort00000000.dll"; v3; *(_WORD *)v2 = a0123456789abcd[v4] )
    {
      if ( v2 == (__int64 *)&i )
        break;
      v4 = v3 & 0xF;
      v3 >>= 4;
      v2 = (__int64 *)((char *)v2 - 2);
    }
    Ptr = 0;
    qword_18005FFC0 = (__int64)SortVersioning::LoadSortModuleAndInvariant(
                                 (SortVersioning *)&i,
                                 (const unsigned __int16 *)(unsigned int)this,
                                 (unsigned int)&v10,
                                 (struct SortVersioning::sorting_handle *(**)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int))&Ptr,
                                 0);
    if ( qword_18005FFC0 )
    {
      v8 = v10;
      v6 = Ptr;
    }
    else if ( qword_18005FFB8 == -1 )
    {
      SortModuleAndInvariant = SortVersioning::LoadSortModuleAndInvariant(
                                 (SortVersioning *)L"nlssorting.dll",
                                 (const unsigned __int16 *)0x60000,
                                 (unsigned int)&v10,
                                 (struct SortVersioning::sorting_handle *(**)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int))&Ptr,
                                 (void (**)(struct SortVersioning::sorting_handle *))v10);
      v6 = Ptr;
      qword_18005FFB8 = (__int64)SortModuleAndInvariant;
      v7 = EncodePointer(Ptr);
      v8 = v10;
      qword_180061B38 = v7;
      qword_180061B30 = EncodePointer(v10);
    }
    else
    {
      v6 = DecodePointer(qword_180061B38);
      v8 = DecodePointer(qword_180061B30);
    }
    qword_180061B48 = EncodePointer(v6);
    v1 = EncodePointer(v8);
    qword_180061B40 = (__int64)v1;
  }
  else
  {
    v1 = (PVOID)qword_180061B40;
  }
  return (struct SortVersioning::sorting_handle *(*)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int))DecodePointer(v1);
}

```

## disassembly

```asm
0x1800411dc  mov     [rsp-8+arg_8], rbx
0x1800411e1  mov     [rsp-8+arg_10], rdi
0x1800411e6  push    rbp
0x1800411e7  mov     rbp, rsp
0x1800411ea  sub     rsp, 60h
0x1800411ee  mov     rax, cs:__security_cookie
0x1800411f5  xor     rax, rsp
0x1800411f8  mov     [rbp+var_8], rax
0x1800411fc  mov     edi, 60000h
0x180041201  cmp     ecx, edi
0x180041203  jnz     short loc_180041269
0x180041205  cmp     cs:qword_18005FFB8, 0FFFFFFFFFFFFFFFFh
0x18004120d  jnz     short loc_18004125D
0x18004120f  xor     ebx, ebx
0x180041211  lea     r9, [rbp+Ptr]; struct SortVersioning::sorting_handle *(**)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int)
0x180041215  lea     r8, [rbp+var_40]; unsigned int
0x180041219  mov     [rbp+var_40], rbx
0x18004121d  mov     edx, edi; unsigned __int16 *
0x18004121f  mov     [rbp+Ptr], rbx
0x180041223  lea     rcx, aNlssortingDll; "nlssorting.dll"
0x18004122a  call    ?LoadSortModuleAndInvariant@SortVersioning@@YAPEAUHINSTANCE__@@PEBGKPEAP6APEAUsorting_handle@1@0PEBU_nlsversioninfo@@K@ZPEAP6AXPEAU31@@Z@Z; SortVersioning::LoadSortModuleAndInvariant(ushort const *,ulong,SortVersioning::sorting_handle * (**)(ushort const *,_nlsversioninfo const *,ulong),void (**)(SortVersioning::sorting_handle *))
0x18004122f  mov     rcx, [rbp+Ptr]; Ptr
0x180041233  mov     cs:qword_18005FFB8, rax
0x18004123a  call    cs:__imp_EncodePointer
0x180041240  mov     rcx, [rbp+var_40]; Ptr
0x180041244  mov     cs:qword_180061B38, rax
0x18004124b  call    cs:__imp_EncodePointer
0x180041251  mov     cs:qword_180061B30, rax
0x180041258  jmp     loc_1800413A5
0x18004125d  mov     rax, cs:qword_180061B30
0x180041264  jmp     loc_1800413A5
0x180041269  cmp     cs:qword_18005FFC0, 0FFFFFFFFFFFFFFFFh
0x180041271  jnz     loc_18004139E
0x180041277  movups  xmm0, xmmword ptr cs:aSort00000000Dl; "Sort00000000.dll"
0x18004127e  lea     r8, [rbp+var_18]
0x180041282  xor     ebx, ebx
0x180041284  movsd   xmm1, qword ptr cs:aSort00000000Dl+10h; "0000.dll"
0x18004128c  mov     rax, 6C006C0064002Eh
0x180041296  movsd   [rbp+var_20], xmm1
0x18004129b  mov     r9d, ecx
0x18004129e  mov     [rbp+var_18], rax
0x1800412a2  mov     [rbp+var_10], bx
0x1800412a6  movups  [rbp+var_30], xmm0
0x1800412aa  test    ecx, ecx
0x1800412ac  jz      short loc_1800412DA
0x1800412ae  lea     rax, [rbp+var_30]
0x1800412b2  cmp     r8, rax
0x1800412b5  jz      short loc_1800412DA
0x1800412b7  mov     eax, r9d
0x1800412ba  lea     r10, a0123456789abcd; "0123456789abcdef"
0x1800412c1  and     eax, 0Fh
0x1800412c4  shr     r9d, 4
0x1800412c8  sub     r8, 2
0x1800412cc  movzx   eax, word ptr [r10+rax*2]
0x1800412d1  mov     [r8], ax
0x1800412d5  test    r9d, r9d
0x1800412d8  jnz     short loc_1800412AE
0x1800412da  mov     edx, ecx; unsigned __int16 *
0x1800412dc  mov     [rbp+var_40], rbx
0x1800412e0  lea     rcx, [rbp+var_30]; this
0x1800412e4  mov     [rbp+Ptr], rbx
0x1800412e8  lea     r9, [rbp+Ptr]; struct SortVersioning::sorting_handle *(**)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int)
0x1800412ec  lea     r8, [rbp+var_40]; unsigned int
0x1800412f0  call    ?LoadSortModuleAndInvariant@SortVersioning@@YAPEAUHINSTANCE__@@PEBGKPEAP6APEAUsorting_handle@1@0PEBU_nlsversioninfo@@K@ZPEAP6AXPEAU31@@Z@Z; SortVersioning::LoadSortModuleAndInvariant(ushort const *,ulong,SortVersioning::sorting_handle * (**)(ushort const *,_nlsversioninfo const *,ulong),void (**)(SortVersioning::sorting_handle *))
0x1800412f5  mov     cs:qword_18005FFC0, rax
0x1800412fc  test    rax, rax
0x1800412ff  jnz     short loc_180041374
0x180041301  cmp     cs:qword_18005FFB8, 0FFFFFFFFFFFFFFFFh
0x180041309  jnz     short loc_180041352
0x18004130b  lea     r9, [rbp+Ptr]; struct SortVersioning::sorting_handle *(**)(const unsigned __int16 *, const struct _nlsversioninfo *, unsigned int)
0x18004130f  mov     edx, edi; unsigned __int16 *
0x180041311  lea     r8, [rbp+var_40]; unsigned int
0x180041315  lea     rcx, aNlssortingDll; "nlssorting.dll"
0x18004131c  call    ?LoadSortModuleAndInvariant@SortVersioning@@YAPEAUHINSTANCE__@@PEBGKPEAP6APEAUsorting_handle@1@0PEBU_nlsversioninfo@@K@ZPEAP6AXPEAU31@@Z@Z; SortVersioning::LoadSortModuleAndInvariant(ushort const *,ulong,SortVersioning::sorting_handle * (**)(ushort const *,_nlsversioninfo const *,ulong),void (**)(SortVersioning::sorting_handle *))
0x180041321  mov     rbx, [rbp+Ptr]
0x180041325  mov     rcx, rbx; Ptr
0x180041328  mov     cs:qword_18005FFB8, rax
0x18004132f  call    cs:__imp_EncodePointer
0x180041335  mov     rdi, [rbp+var_40]
0x180041339  mov     rcx, rdi; Ptr
0x18004133c  mov     cs:qword_180061B38, rax
0x180041343  call    cs:__imp_EncodePointer
0x180041349  mov     cs:qword_180061B30, rax
0x180041350  jmp     short loc_18004137C
0x180041352  mov     rcx, cs:qword_180061B38; Ptr
0x180041359  call    cs:__imp_DecodePointer
0x18004135f  mov     rcx, cs:qword_180061B30; Ptr
0x180041366  mov     rbx, rax
0x180041369  call    cs:__imp_DecodePointer
0x18004136f  mov     rdi, rax
0x180041372  jmp     short loc_18004137C
0x180041374  mov     rdi, [rbp+var_40]
0x180041378  mov     rbx, [rbp+Ptr]
0x18004137c  mov     rcx, rbx; Ptr
0x18004137f  call    cs:__imp_EncodePointer
0x180041385  mov     rcx, rdi; Ptr
0x180041388  mov     cs:qword_180061B48, rax
0x18004138f  call    cs:__imp_EncodePointer
0x180041395  mov     cs:qword_180061B40, rax
0x18004139c  jmp     short loc_1800413A5
0x18004139e  mov     rax, cs:qword_180061B40
0x1800413a5  mov     rcx, rax; Ptr
0x1800413a8  call    cs:__imp_DecodePointer
0x1800413ae  mov     rcx, [rbp+var_8]
0x1800413b2  xor     rcx, rsp; StackCookie
0x1800413b5  call    __security_check_cookie
0x1800413ba  lea     r11, [rsp+60h+var_s0]
0x1800413bf  mov     rbx, [r11+18h]
0x1800413c3  mov     rdi, [r11+20h]
0x1800413c7  mov     rsp, r11
0x1800413ca  pop     rbp
0x1800413cb  retn
```
