# MREXTTEXTOUT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180079c10`
- end: `0x180079d95`
- name: `?bPlay@MREXTTEXTOUT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `389`
- prototype: `int(MREXTTEXTOUT *__hidden this, void *, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016350`

## callees

- `0x18002d540`
- `0x180032f20`
- `0x180035a34`
- `0x180079c10`
- `0x18007f800`

## import_xrefs

- `GDI32!ExtTextOutA` at `0x180079cf1`
- `GDI32!ExtTextOutA` at `0x180079cf1`
- `GDI32!ExtTextOutW` at `0x180079d3e`
- `GDI32!ExtTextOutW` at `0x180079d3e`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180079c97`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180079c97`

## pseudocode

```c
__int64 __fastcall MREXTTEXTOUT::bPlay(MREXTTEXTOUT *this, HDC a2, struct tagHANDLETABLE *a3)
{
  int v5; // edx
  UINT v6; // esi
  UINT c; // edx
  const INT *lpDx; // r8
  __int64 result; // rax
  const INT *v10; // rax
  int v11; // esi
  int v12; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+44h] [rbp-34h]

  if ( (unsigned int)MREXTTEXTOUT::bCheckRecord(this, a3) )
  {
    v5 = *((_DWORD *)this + 6);
    if ( v5 == 2 || SetGraphicsMode(a2, v5) && (unsigned int)SetFontXform(a2) )
    {
      if ( *(_DWORD *)this == 83 )
      {
        v6 = *((_DWORD *)this + 11);
        if ( (*((_BYTE *)this + 52) & 0x10) != 0 )
        {
          v12 = 60677712;
          v13 = 1;
          RtlLogUnexpectedCodepath(&v12);
          c = (unsigned int)(*((_DWORD *)this + 1) - *((_DWORD *)this + 12)) >> 1;
          if ( v6 < c )
            c = v6;
        }
        else
        {
          c = *((_DWORD *)this + 11);
        }
        if ( *((_DWORD *)this + 18) )
          lpDx = (const INT *)((char *)this + *((unsigned int *)this + 18));
        else
          lpDx = 0;
        LODWORD(result) = ExtTextOutA(
                            a2,
                            *((_DWORD *)this + 9),
                            *((_DWORD *)this + 10),
                            *((_DWORD *)this + 13),
                            (const RECT *)((char *)this + 56),
                            (LPCSTR)this + *((unsigned int *)this + 12),
                            c,
                            lpDx);
      }
      else
      {
        if ( *((_DWORD *)this + 18) )
          v10 = (const INT *)((char *)this + *((unsigned int *)this + 18));
        else
          v10 = 0;
        LODWORD(result) = ExtTextOutW(
                            a2,
                            *((_DWORD *)this + 9),
                            *((_DWORD *)this + 10),
                            *((_DWORD *)this + 13),
                            (const RECT *)((char *)this + 56),
                            (LPCWSTR)((char *)this + *((unsigned int *)this + 12)),
                            *((_DWORD *)this + 11),
                            v10);
      }
      v11 = result;
      if ( *((_DWORD *)this + 6) == 2 )
        return (unsigned int)result;
      if ( SetGraphicsMode(a2, 2) )
        return v11 & (unsigned int)-((unsigned int)SetFontXform(a2) != 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180079c10  push    rbx
0x180079c12  push    rsi
0x180079c13  push    rdi
0x180079c14  sub     rsp, 60h
0x180079c18  mov     rax, cs:__security_cookie
0x180079c1f  xor     rax, rsp
0x180079c22  mov     [rsp+78h+var_28], rax
0x180079c27  mov     rdi, rdx
0x180079c2a  mov     rbx, rcx
0x180079c2d  mov     rdx, r8; struct tagHANDLETABLE *
0x180079c30  call    ?bCheckRecord@MREXTTEXTOUT@@QEAAHPEAUtagHANDLETABLE@@@Z; MREXTTEXTOUT::bCheckRecord(tagHANDLETABLE *)
0x180079c35  test    eax, eax
0x180079c37  jz      loc_180079D7D
0x180079c3d  mov     edx, [rbx+18h]; iMode
0x180079c40  cmp     edx, 2
0x180079c43  jz      short loc_180079C6F
0x180079c45  mov     rcx, rdi; hdc
0x180079c48  call    SetGraphicsMode
0x180079c4d  test    eax, eax
0x180079c4f  jz      loc_180079D7D
0x180079c55  movss   xmm2, dword ptr [rbx+20h]
0x180079c5a  mov     rcx, rdi; hdc
0x180079c5d  movss   xmm1, dword ptr [rbx+1Ch]
0x180079c62  call    SetFontXform
0x180079c67  test    eax, eax
0x180079c69  jz      loc_180079D7D
0x180079c6f  cmp     dword ptr [rbx], 53h ; 'S'
0x180079c72  jnz     loc_180079CFF
0x180079c78  mov     esi, [rbx+2Ch]
0x180079c7b  test    byte ptr [rbx+34h], 10h
0x180079c7f  jz      short loc_180079CB2
0x180079c81  lea     rcx, [rsp+78h+var_38]
0x180079c86  mov     [rsp+78h+var_38], 39DDE50h
0x180079c8e  mov     [rsp+78h+var_34], 1
0x180079c97  call    cs:__imp_RtlLogUnexpectedCodepath
0x180079c9e  nop     dword ptr [rax+rax+00h]
0x180079ca3  mov     edx, [rbx+4]
0x180079ca6  sub     edx, [rbx+30h]
0x180079ca9  shr     edx, 1
0x180079cab  cmp     esi, edx
0x180079cad  cmovb   edx, esi
0x180079cb0  jmp     short loc_180079CB4
0x180079cb2  mov     edx, esi
0x180079cb4  cmp     dword ptr [rbx+48h], 0
0x180079cb8  jz      short loc_180079CC3
0x180079cba  mov     r8d, [rbx+48h]
0x180079cbe  add     r8, rbx
0x180079cc1  jmp     short loc_180079CC6
0x180079cc3  xor     r8d, r8d
0x180079cc6  mov     ecx, [rbx+30h]
0x180079cc9  lea     rax, [rbx+38h]
0x180079ccd  mov     r9d, [rbx+34h]; options
0x180079cd1  add     rcx, rbx
0x180079cd4  mov     [rsp+78h+lpDx], r8; lpDx
0x180079cd9  mov     r8d, [rbx+28h]; y
0x180079cdd  mov     [rsp+78h+c], edx; c
0x180079ce1  mov     edx, [rbx+24h]; x
0x180079ce4  mov     [rsp+78h+lpString], rcx; lpString
0x180079ce9  mov     rcx, rdi; hdc
0x180079cec  mov     [rsp+78h+lprect], rax; lprect
0x180079cf1  call    cs:__imp_ExtTextOutA
0x180079cf8  nop     dword ptr [rax+rax+00h]
0x180079cfd  jmp     short loc_180079D4A
0x180079cff  cmp     dword ptr [rbx+48h], 0
0x180079d03  jz      short loc_180079D0D
0x180079d05  mov     eax, [rbx+48h]
0x180079d08  add     rax, rbx
0x180079d0b  jmp     short loc_180079D0F
0x180079d0d  xor     eax, eax
0x180079d0f  mov     r8d, [rbx+30h]
0x180079d13  lea     rcx, [rbx+38h]
0x180079d17  mov     r9d, [rbx+34h]; options
0x180079d1b  add     r8, rbx
0x180079d1e  mov     edx, [rbx+24h]; x
0x180079d21  mov     [rsp+78h+lpDx], rax; lpDx
0x180079d26  mov     eax, [rbx+2Ch]
0x180079d29  mov     [rsp+78h+c], eax; c
0x180079d2d  mov     [rsp+78h+lpString], r8; lpString
0x180079d32  mov     r8d, [rbx+28h]; y
0x180079d36  mov     [rsp+78h+lprect], rcx; lprect
0x180079d3b  mov     rcx, rdi; hdc
0x180079d3e  call    cs:__imp_ExtTextOutW
0x180079d45  nop     dword ptr [rax+rax+00h]
0x180079d4a  cmp     dword ptr [rbx+18h], 2
0x180079d4e  mov     esi, eax
0x180079d50  jz      short loc_180079D79
0x180079d52  mov     edx, 2; iMode
0x180079d57  mov     rcx, rdi; hdc
0x180079d5a  call    SetGraphicsMode
0x180079d5f  test    eax, eax
0x180079d61  jz      short loc_180079D7D
0x180079d63  xorps   xmm2, xmm2
0x180079d66  xorps   xmm1, xmm1
0x180079d69  mov     rcx, rdi; hdc
0x180079d6c  call    SetFontXform
0x180079d71  neg     eax
0x180079d73  sbb     eax, eax
0x180079d75  and     eax, esi
0x180079d77  jmp     short loc_180079D7F
0x180079d79  mov     eax, esi
0x180079d7b  jmp     short loc_180079D7F
0x180079d7d  xor     eax, eax
0x180079d7f  mov     rcx, [rsp+78h+var_28]
0x180079d84  xor     rcx, rsp; StackCookie
0x180079d87  call    __security_check_cookie
0x180079d8c  add     rsp, 60h
0x180079d90  pop     rdi
0x180079d91  pop     rsi
0x180079d92  pop     rbx
0x180079d93  retn
```
