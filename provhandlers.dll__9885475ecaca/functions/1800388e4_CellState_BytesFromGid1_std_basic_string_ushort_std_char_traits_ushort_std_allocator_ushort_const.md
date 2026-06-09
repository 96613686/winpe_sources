# CellState::BytesFromGid1(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800388e4`
- end: `0x180038afa`
- name: `?BytesFromGid1@CellState@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `534`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180039ae4`

## callees

- `0x18000e1f8`
- `0x180012d80`
- `0x180024e34`
- `0x1800388e4`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!_errno` at `0x1800389b4`
- `msvcrt!_errno` at `0x1800389b4`
- `msvcrt!wcstol` at `0x1800389ac`
- `msvcrt!wcstol` at `0x1800389ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038a61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038a61`

## string_xrefs

- `0x180038aa6`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180038abe`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180038ad6`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180038ae8`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall CellState::BytesFromGid1(_QWORD *a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  int v5; // r15d
  unsigned __int64 v6; // rdi
  const wchar_t *v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // rcx
  wchar_t **v10; // rdx
  const wchar_t *v11; // r8
  char v12; // al
  char v13; // cl
  wchar_t *String[2]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+40h] [rbp-20h]
  unsigned __int64 v17; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v4 = *(_QWORD *)(a2 + 16);
  if ( (v4 & 1) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      (const char *)0x80070057LL,
      0);
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  std::vector<unsigned char>::resize(a1, v4 >> 1);
  v5 = 1;
  v6 = 0;
  if ( *(_QWORD *)(a2 + 16) > 1u )
  {
    while ( 1 )
    {
      v17 = 7;
      v16 = 0;
      LOWORD(String[0]) = 0;
      std::wstring::assign((void **)String, (void **)a2, v6, 2u);
      v5 |= 2u;
      v7 = (const wchar_t *)String;
      if ( v17 >= 8 )
        v7 = String[0];
      v8 = wcstol(v7, 0, 16);
      if ( *_errno() )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x200,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
          (const char *)0x80070057LL,
          v5);
      if ( v8 )
        break;
      v9 = 2;
      if ( v16 < 2 )
        v9 = v16;
      v10 = String;
      if ( v17 >= 8 )
        v10 = (wchar_t **)String[0];
      if ( v9 )
      {
        v11 = L"00";
        while ( *(_WORD *)v10 == *v11 )
        {
          v10 = (wchar_t **)((char *)v10 + 2);
          ++v11;
          if ( !--v9 )
            goto LABEL_15;
        }
      }
      else
      {
LABEL_15:
        if ( v16 == 2 )
          break;
      }
      v12 = 1;
LABEL_18:
      if ( v12 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x201,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
          (const char *)0x80070057LL,
          v5);
      v13 = v8;
      if ( v8 > 0xFF )
        v13 = -1;
      *(_BYTE *)((v6 >> 1) + *a1) = v13;
      if ( v8 > 0xFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x202,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
          v8 > 0xFF ? (const char *)0x80070216LL : 0,
          v5);
      if ( v17 >= 8 )
        operator delete(String[0]);
      v6 += 2LL;
      if ( v6 + 1 >= *(_QWORD *)(a2 + 16) )
        return a1;
    }
    v12 = 0;
    goto LABEL_18;
  }
  return a1;
}

```

## disassembly

```asm
0x1800388e4  mov     [rsp-28h+arg_10], rbx
0x1800388e9  mov     [rsp-28h+arg_18], rsi
0x1800388ee  push    rbp
0x1800388ef  push    rdi
0x1800388f0  push    r13
0x1800388f2  push    r14
0x1800388f4  push    r15
0x1800388f6  mov     rbp, rsp
0x1800388f9  sub     rsp, 60h
0x1800388fd  mov     rax, cs:__security_cookie
0x180038904  xor     rax, rsp
0x180038907  mov     [rbp+var_10], rax
0x18003890b  mov     r14, rdx
0x18003890e  mov     rbx, rcx
0x180038911  mov     [rbp+var_38], rcx
0x180038915  mov     [rbp+var_40], 0
0x18003891c  mov     rdx, [rdx+10h]
0x180038920  mov     rcx, [rbp+28h]; this
0x180038924  test    dl, 1
0x180038927  jnz     loc_180038AD0
0x18003892d  mov     qword ptr [rbx], 0
0x180038934  mov     qword ptr [rbx+8], 0
0x18003893c  mov     qword ptr [rbx+10h], 0
0x180038944  shr     rdx, 1
0x180038947  mov     rcx, rbx
0x18003894a  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18003894f  mov     r15d, 1
0x180038955  mov     [rbp+var_40], r15d
0x180038959  xor     edi, edi
0x18003895b  cmp     [r14+10h], r15
0x18003895f  jbe     loc_180038A78
0x180038965  lea     r13d, [r15+1]
0x180038969  mov     [rbp+var_18], 7
0x180038971  mov     [rbp+var_20], 0
0x180038979  xor     eax, eax
0x18003897b  mov     word ptr [rbp+String], ax
0x18003897f  mov     r9, r13
0x180038982  mov     r8, rdi
0x180038985  mov     rdx, r14
0x180038988  lea     rcx, [rbp+String]; void *
0x18003898c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180038991  or      r15d, r13d
0x180038994  mov     [rbp+var_40], r15d
0x180038998  lea     rcx, [rbp+String]
0x18003899c  cmp     [rbp+var_18], 8
0x1800389a1  cmovnb  rcx, [rbp+String]; String
0x1800389a6  xor     edx, edx; EndPtr
0x1800389a8  lea     r8d, [rdx+10h]; Radix
0x1800389ac  call    cs:__imp_wcstol
0x1800389b2  mov     esi, eax
0x1800389b4  call    cs:__imp__errno
0x1800389ba  mov     rcx, [rbp+28h]; this
0x1800389be  cmp     dword ptr [rax], 0
0x1800389c1  jnz     loc_180038AB8
0x1800389c7  test    esi, esi
0x1800389c9  jnz     short loc_180038A11
0x1800389cb  mov     r9, [rbp+var_20]
0x1800389cf  mov     rcx, r13
0x1800389d2  cmp     r9, r13
0x1800389d5  cmovb   rcx, r9
0x1800389d9  lea     rdx, [rbp+String]
0x1800389dd  cmp     [rbp+var_18], 8
0x1800389e2  cmovnb  rdx, [rbp+String]
0x1800389e7  test    rcx, rcx
0x1800389ea  jz      short loc_180038A08
0x1800389ec  lea     r8, a00; "00"
0x1800389f3  movzx   eax, word ptr [r8]
0x1800389f7  cmp     [rdx], ax
0x1800389fa  jnz     short loc_180038A0D
0x1800389fc  add     rdx, r13
0x1800389ff  add     r8, r13
0x180038a02  sub     rcx, 1
0x180038a06  jnz     short loc_1800389F3
0x180038a08  cmp     r9, r13
0x180038a0b  jz      short loc_180038A11
0x180038a0d  mov     al, 1
0x180038a0f  jmp     short loc_180038A13
0x180038a11  xor     al, al
0x180038a13  mov     rcx, [rbp+28h]; this
0x180038a17  test    al, al
0x180038a19  jnz     loc_180038AA0
0x180038a1f  mov     rax, rdi
0x180038a22  shr     rax, 1
0x180038a25  mov     rdx, [rbx]
0x180038a28  mov     r8d, 0FFh
0x180038a2e  cmp     esi, r8d
0x180038a31  mov     cl, sil
0x180038a34  jbe     short loc_180038A39
0x180038a36  mov     cl, r8b
0x180038a39  cmp     r8d, esi
0x180038a3c  sbb     r9d, r9d
0x180038a3f  and     r9d, 80070216h; char *
0x180038a46  mov     [rax+rdx], cl
0x180038a49  mov     rcx, [rbp+28h]; this
0x180038a4d  cmp     esi, r8d
0x180038a50  ja      loc_180038AE8
0x180038a56  cmp     [rbp+var_18], 8
0x180038a5b  jb      short loc_180038A67
0x180038a5d  mov     rcx, [rbp+String]
0x180038a61  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038a67  add     rdi, r13
0x180038a6a  lea     rax, [rdi+1]
0x180038a6e  cmp     rax, [r14+10h]
0x180038a72  jb      loc_180038969
0x180038a78  mov     rax, rbx
0x180038a7b  mov     rcx, [rbp+var_10]
0x180038a7f  xor     rcx, rsp; StackCookie
0x180038a82  call    __security_check_cookie
0x180038a87  lea     r11, [rsp+60h+var_s0]
0x180038a8c  mov     rbx, [r11+40h]
0x180038a90  mov     rsi, [r11+48h]
0x180038a94  mov     rsp, r11
0x180038a97  pop     r15
0x180038a99  pop     r14
0x180038a9b  pop     r13
0x180038a9d  pop     rdi
0x180038a9e  pop     rbp
0x180038a9f  retn
0x180038aa0  mov     r9d, 80070057h; char *
0x180038aa6  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180038aad  mov     edx, 201h; void *
0x180038ab2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ab8  mov     r9d, 80070057h; char *
0x180038abe  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180038ac5  mov     edx, 200h; void *
0x180038aca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ad0  mov     r9d, 80070057h; char *
0x180038ad6  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180038add  mov     edx, 1F6h; void *
0x180038ae2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ae8  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180038aef  mov     edx, 202h; void *
0x180038af4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
