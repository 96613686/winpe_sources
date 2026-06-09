# MREXTTEXTOUT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180075280`
- end: `0x1800753ee`
- name: `?bPlay@MREXTTEXTOUT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `366`
- prototype: `__int64 __fastcall(MREXTTEXTOUT *this, HDC, struct tagHANDLETABLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800305e0`

## callees

- `0x180024500`
- `0x180029790`
- `0x18002bb20`
- `0x180075280`
- `0x18007ac50`

## import_xrefs

- `GDI32!ExtTextOutA` at `0x180075357`
- `GDI32!ExtTextOutA` at `0x180075357`
- `GDI32!ExtTextOutW` at `0x18007539e`
- `GDI32!ExtTextOutW` at `0x18007539e`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180075303`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180075303`

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

  if ( (unsigned int)MREXTTEXTOUT::bCheckRecord((unsigned __int64)this, a3) )
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
0x180075280  push    rbx
0x180075282  push    rsi
0x180075283  push    rdi
0x180075284  sub     rsp, 60h
0x180075288  mov     rax, cs:__security_cookie
0x18007528f  xor     rax, rsp
0x180075292  mov     [rsp+78h+var_28], rax
0x180075297  mov     rdi, rdx
0x18007529a  mov     rbx, rcx
0x18007529d  mov     rdx, r8; struct tagHANDLETABLE *
0x1800752a0  call    ?bCheckRecord@MREXTTEXTOUT@@QEAAHPEAUtagHANDLETABLE@@@Z; MREXTTEXTOUT::bCheckRecord(tagHANDLETABLE *)
0x1800752a5  test    eax, eax
0x1800752a7  jz      loc_1800753D7
0x1800752ad  mov     edx, [rbx+18h]; iMode
0x1800752b0  cmp     edx, 2
0x1800752b3  jz      short loc_1800752DF
0x1800752b5  mov     rcx, rdi; hdc
0x1800752b8  call    SetGraphicsMode
0x1800752bd  test    eax, eax
0x1800752bf  jz      loc_1800753D7
0x1800752c5  movss   xmm2, dword ptr [rbx+20h]
0x1800752ca  mov     rcx, rdi; hdc
0x1800752cd  movss   xmm1, dword ptr [rbx+1Ch]
0x1800752d2  call    SetFontXform
0x1800752d7  test    eax, eax
0x1800752d9  jz      loc_1800753D7
0x1800752df  cmp     dword ptr [rbx], 53h ; 'S'
0x1800752e2  jnz     short loc_18007535F
0x1800752e4  mov     esi, [rbx+2Ch]
0x1800752e7  test    byte ptr [rbx+34h], 10h
0x1800752eb  jz      short loc_180075318
0x1800752ed  lea     rcx, [rsp+78h+var_38]
0x1800752f2  mov     [rsp+78h+var_38], 39DDE50h
0x1800752fa  mov     [rsp+78h+var_34], 1
0x180075303  call    cs:__imp_RtlLogUnexpectedCodepath
0x180075309  mov     edx, [rbx+4]
0x18007530c  sub     edx, [rbx+30h]
0x18007530f  shr     edx, 1
0x180075311  cmp     esi, edx
0x180075313  cmovb   edx, esi
0x180075316  jmp     short loc_18007531A
0x180075318  mov     edx, esi
0x18007531a  cmp     dword ptr [rbx+48h], 0
0x18007531e  jz      short loc_180075329
0x180075320  mov     r8d, [rbx+48h]
0x180075324  add     r8, rbx
0x180075327  jmp     short loc_18007532C
0x180075329  xor     r8d, r8d
0x18007532c  mov     ecx, [rbx+30h]
0x18007532f  lea     rax, [rbx+38h]
0x180075333  mov     r9d, [rbx+34h]; options
0x180075337  add     rcx, rbx
0x18007533a  mov     [rsp+78h+lpDx], r8; lpDx
0x18007533f  mov     r8d, [rbx+28h]; y
0x180075343  mov     [rsp+78h+c], edx; c
0x180075347  mov     edx, [rbx+24h]; x
0x18007534a  mov     [rsp+78h+lpString], rcx; lpString
0x18007534f  mov     rcx, rdi; hdc
0x180075352  mov     [rsp+78h+lprect], rax; lprect
0x180075357  call    cs:__imp_ExtTextOutA
0x18007535d  jmp     short loc_1800753A4
0x18007535f  cmp     dword ptr [rbx+48h], 0
0x180075363  jz      short loc_18007536D
0x180075365  mov     eax, [rbx+48h]
0x180075368  add     rax, rbx
0x18007536b  jmp     short loc_18007536F
0x18007536d  xor     eax, eax
0x18007536f  mov     r8d, [rbx+30h]
0x180075373  lea     rcx, [rbx+38h]
0x180075377  mov     r9d, [rbx+34h]; options
0x18007537b  add     r8, rbx
0x18007537e  mov     edx, [rbx+24h]; x
0x180075381  mov     [rsp+78h+lpDx], rax; lpDx
0x180075386  mov     eax, [rbx+2Ch]
0x180075389  mov     [rsp+78h+c], eax; c
0x18007538d  mov     [rsp+78h+lpString], r8; lpString
0x180075392  mov     r8d, [rbx+28h]; y
0x180075396  mov     [rsp+78h+lprect], rcx; lprect
0x18007539b  mov     rcx, rdi; hdc
0x18007539e  call    cs:__imp_ExtTextOutW
0x1800753a4  cmp     dword ptr [rbx+18h], 2
0x1800753a8  mov     esi, eax
0x1800753aa  jz      short loc_1800753D3
0x1800753ac  mov     edx, 2; iMode
0x1800753b1  mov     rcx, rdi; hdc
0x1800753b4  call    SetGraphicsMode
0x1800753b9  test    eax, eax
0x1800753bb  jz      short loc_1800753D7
0x1800753bd  xorps   xmm2, xmm2
0x1800753c0  xorps   xmm1, xmm1
0x1800753c3  mov     rcx, rdi; hdc
0x1800753c6  call    SetFontXform
0x1800753cb  neg     eax
0x1800753cd  sbb     eax, eax
0x1800753cf  and     eax, esi
0x1800753d1  jmp     short loc_1800753D9
0x1800753d3  mov     eax, esi
0x1800753d5  jmp     short loc_1800753D9
0x1800753d7  xor     eax, eax
0x1800753d9  mov     rcx, [rsp+78h+var_28]
0x1800753de  xor     rcx, rsp; StackCookie
0x1800753e1  call    __security_check_cookie
0x1800753e6  add     rsp, 60h
0x1800753ea  pop     rdi
0x1800753eb  pop     rsi
0x1800753ec  pop     rbx
0x1800753ed  retn
```
