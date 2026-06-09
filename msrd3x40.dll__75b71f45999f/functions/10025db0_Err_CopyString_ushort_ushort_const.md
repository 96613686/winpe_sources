# Err::CopyString(ushort * &,ushort const *)

- ea: `0x10025db0`
- end: `0x10025e56`
- name: `?CopyString@Err@@AAEXAAPAGPBG@Z`
- size: `166`
- prototype: `void __thiscall(Err *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `21`
- callee_count: `6`
- tags: ``

## callers

- `0x1001dfc0`
- `0x10021d70`
- `0x10022030`
- `0x10023bb0`
- `0x10025e60`
- `0x10025f50`
- `0x100270d0`
- `0x10036160`
- `0x10036620`
- `0x10036dc0`
- `0x10037710`
- `0x10051a30`
- `0x10053400`
- `0x100536a0`
- `0x10053950`
- `0x10055260`
- `0x10056280`
- `0x10056b70`
- `0x10057e90`
- `0x10058160`
- `0x10059d00`

## callees

- `0x100084f0`
- `0x1000f750`
- `0x10025db0`
- `0x1005e3b0`
- `0x1005e7f3`
- `0x1005f064`

## pseudocode

```c
void __thiscall Err::CopyString(Err *this, wchar_t *pszDest, const unsigned __int16 *cchDest)
{
  unsigned int v3; // edi
  const wchar_t *v4; // [esp+0h] [ebp-2Ch]
  size_t v5; // [esp+4h] [ebp-28h]

  if ( cchDest )
  {
    v3 = 2 * wcslen(cchDest) + 2;
    *(_DWORD *)pszDest = operator new[](v3);
    if ( v3 >> 1 )
      StringCopyWorkerW(pszDest, (size_t)cchDest, (size_t *)pszDest, v4, v5);
  }
  else
  {
    *(_DWORD *)pszDest = 0;
  }
}

```

## disassembly

```asm
0x10025db0  mov     edi, edi
0x10025db2  push    ebp
0x10025db3  mov     ebp, esp
0x10025db5  push    0FFFFFFFFh
0x10025db7  push    offset ?ReportLockConflict@Table@@AAEXJPBGAAVErr@@@Z_SEH
0x10025dbc  mov     eax, large fs:0
0x10025dc2  push    eax
0x10025dc3  sub     esp, 14h
0x10025dc6  push    esi
0x10025dc7  push    edi; cchToCopy
0x10025dc8  mov     eax, ___security_cookie
0x10025dcd  xor     eax, ebp
0x10025dcf  push    eax; pszSrc
0x10025dd0  lea     eax, [ebp+var_C]
0x10025dd3  mov     large fs:0, eax
0x10025dd9  mov     [ebp+var_20], 1
0x10025de0  mov     esi, [ebp+cchDest]
0x10025de3  mov     [ebp+var_4], 0
0x10025dea  test    esi, esi
0x10025dec  jz      short loc_10025E3A
0x10025dee  mov     eax, esi
0x10025df0  lea     edx, [eax+2]
0x10025df3  mov     cx, [eax]
0x10025df6  add     eax, 2
0x10025df9  test    cx, cx
0x10025dfc  jnz     short loc_10025DF3
0x10025dfe  sub     eax, edx
0x10025e00  sar     eax, 1
0x10025e02  lea     edi, ds:2[eax*2]
0x10025e09  push    edi; unsigned int
0x10025e0a  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10025e0f  mov     ecx, [ebp+pszDest]
0x10025e12  add     esp, 4
0x10025e15  shr     edi, 1
0x10025e17  mov     [ecx], eax
0x10025e19  jz      short loc_10025E43
0x10025e1b  push    ecx; pcchNewDestLength
0x10025e1c  push    esi; cchDest
0x10025e1d  push    ecx; pszDest
0x10025e1e  mov     edx, edi
0x10025e20  mov     ecx, eax
0x10025e22  call    StringCopyWorkerW
0x10025e27  mov     ecx, [ebp+var_C]
0x10025e2a  mov     large fs:0, ecx
0x10025e31  pop     ecx
0x10025e32  pop     edi
0x10025e33  pop     esi
0x10025e34  mov     esp, ebp
0x10025e36  pop     ebp
0x10025e37  retn    8
0x10025e3a  mov     eax, [ebp+pszDest]
0x10025e3d  mov     dword ptr [eax], 0
0x10025e43  mov     ecx, [ebp+var_C]
0x10025e46  mov     large fs:0, ecx
0x10025e4d  pop     ecx
0x10025e4e  pop     edi
0x10025e4f  pop     esi
0x10025e50  mov     esp, ebp
0x10025e52  pop     ebp
0x10025e53  retn    8
0x100606e0  lea     ecx, [ebp+var_20]; this
0x100606e3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100606ed  nop
0x100606ee  nop
0x100606ef  mov     edx, [esp-4+cchDest]
0x100606f3  lea     eax, [edx+0Ch]
0x100606f6  mov     ecx, [edx-20h]
0x100606f9  xor     ecx, eax; StackCookie
0x100606fb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060700  mov     eax, offset stru_10063558
0x10060705  jmp     ___CxxFrameHandler3
```
