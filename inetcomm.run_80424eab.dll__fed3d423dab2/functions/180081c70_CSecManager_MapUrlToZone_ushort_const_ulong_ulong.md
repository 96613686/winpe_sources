# CSecManager::MapUrlToZone(ushort const *,ulong *,ulong)

- ea: `0x180081c70`
- end: `0x180081e04`
- name: `?MapUrlToZone@CSecManager@@UEAAJPEBGPEAKK@Z`
- size: `404`
- prototype: `int(CSecManager *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180021ccc`
- `0x1800227b0`
- `0x180081bd8`
- `0x180081c70`
- `0x180082058`
- `0x180082080`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x180081d0f`
- `SHLWAPI!StrCmpIW` at `0x180081d0f`
- `KERNEL32!CompareStringW` at `0x180081d41`
- `KERNEL32!CompareStringW` at `0x180081d68`
- `KERNEL32!CompareStringW` at `0x180081dda`
- `KERNEL32!CompareStringW` at `0x180081d41`
- `KERNEL32!CompareStringW` at `0x180081d68`
- `KERNEL32!CompareStringW` at `0x180081dda`

## pseudocode

```c
__int64 __fastcall CSecManager::MapUrlToZone(
        CSecManager *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int a4)
{
  const WCHAR *v6; // rbx
  CSecManager *v8; // rbp
  int v9; // edi
  unsigned int Zone; // eax
  const WCHAR *v11; // rdx
  int v13; // [rsp+80h] [rbp+18h] BYREF

  v6 = a2;
  if ( !a3 || !a2 )
    return (unsigned int)-2147024809;
  v8 = (CSecManager *)((char *)this - 32);
  *a3 = 0;
  v13 = 4;
  if ( !(unsigned int)CSecManager::_IsWebPreviewMode((CSecManager *)((char *)this - 32))
    || (int)CSecManager::_EnsureDefaultSecurityManager(v8) < 0 )
  {
    v11 = (const WCHAR *)*((_QWORD *)this + 3);
    v9 = 0;
    if ( v11 && !StrCmpIW(v6, v11) )
    {
      Zone = *((_DWORD *)this + 8);
      goto LABEL_7;
    }
    if ( CompareStringW(0x7Fu, 1u, v6, 6, L"shell:", 6) == 2 || CompareStringW(0x7Fu, 1u, v6, 4, L"res:", 4) == 2 )
    {
      v13 = 3;
    }
    else
    {
      Zone = CSecManager::DwGetZone(v8);
      v13 = Zone;
      if ( Zone > 0x2710 )
      {
        Zone = 4;
        goto LABEL_7;
      }
      if ( Zone == 4 )
        goto LABEL_7;
    }
    if ( (unsigned int)IsMHTMLUrlW(v6) )
      v6 += GetMhtmlPrefixLength();
    if ( CompareStringW(0x7Fu, 1u, v6, 4, L"mid:", 4) != 2 )
      return (unsigned int)-2146697199;
LABEL_6:
    Zone = v13;
LABEL_7:
    *a3 = Zone;
    return (unsigned int)v9;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, int *, _QWORD))(**((_QWORD **)this + 2) + 40LL))(
         *((_QWORD *)this + 2),
         v6,
         &v13,
         a4);
  if ( v9 >= 0 )
    goto LABEL_6;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180081c70  mov     rax, rsp
0x180081c73  push    rbx
0x180081c74  push    rbp
0x180081c75  push    rsi
0x180081c76  push    rdi
0x180081c77  push    r14
0x180081c79  push    r15
0x180081c7b  sub     rsp, 38h
0x180081c7f  mov     edi, r9d
0x180081c82  mov     r14, r8
0x180081c85  mov     rbx, rdx
0x180081c88  mov     rsi, rcx
0x180081c8b  test    r8, r8
0x180081c8e  jz      loc_180081DF0
0x180081c94  test    rdx, rdx
0x180081c97  jz      loc_180081DF0
0x180081c9d  lea     rbp, [rcx-20h]
0x180081ca1  mov     dword ptr [r8], 0
0x180081ca8  mov     r15d, 4
0x180081cae  mov     rcx, rbp; this
0x180081cb1  mov     [rax+18h], r15d
0x180081cb5  call    ?_IsWebPreviewMode@CSecManager@@AEAAHXZ; CSecManager::_IsWebPreviewMode(void)
0x180081cba  test    eax, eax
0x180081cbc  jz      short loc_180081D01
0x180081cbe  mov     rcx, rbp; this
0x180081cc1  call    ?_EnsureDefaultSecurityManager@CSecManager@@AEAAJXZ; CSecManager::_EnsureDefaultSecurityManager(void)
0x180081cc6  test    eax, eax
0x180081cc8  js      short loc_180081D01
0x180081cca  mov     rcx, [rsi+10h]
0x180081cce  lea     r8, [rsp+68h+arg_10]
0x180081cd6  mov     r9d, edi
0x180081cd9  mov     rdx, rbx
0x180081cdc  mov     rax, [rcx]
0x180081cdf  mov     rax, [rax+28h]
0x180081ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ce8  mov     edi, eax
0x180081cea  test    eax, eax
0x180081cec  js      loc_180081DF5
0x180081cf2  mov     eax, [rsp+68h+arg_10]
0x180081cf9  mov     [r14], eax
0x180081cfc  jmp     loc_180081DF5
0x180081d01  mov     rdx, [rsi+18h]; psz2
0x180081d05  xor     edi, edi
0x180081d07  test    rdx, rdx
0x180081d0a  jz      short loc_180081D1E
0x180081d0c  mov     rcx, rbx; psz1
0x180081d0f  call    cs:__imp_StrCmpIW
0x180081d15  test    eax, eax
0x180081d17  jnz     short loc_180081D1E
0x180081d19  mov     eax, [rsi+20h]
0x180081d1c  jmp     short loc_180081CF9
0x180081d1e  mov     r9d, 6; cchCount1
0x180081d24  lea     rax, aShell; "shell:"
0x180081d2b  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x180081d30  mov     r8, rbx; lpString1
0x180081d33  mov     [rsp+68h+lpString2], rax; lpString2
0x180081d38  lea     esi, [r9-5]
0x180081d3c  mov     edx, esi; dwCmpFlags
0x180081d3e  lea     ecx, [rsi+7Eh]; Locale
0x180081d41  call    cs:__imp_CompareStringW
0x180081d47  cmp     eax, 2
0x180081d4a  jz      short loc_180081D9C
0x180081d4c  lea     rax, aRes_0; "res:"
0x180081d53  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x180081d58  mov     r9d, r15d; cchCount1
0x180081d5b  mov     [rsp+68h+lpString2], rax; lpString2
0x180081d60  mov     r8, rbx; lpString1
0x180081d63  lea     ecx, [rsi+7Eh]; Locale
0x180081d66  mov     edx, esi; dwCmpFlags
0x180081d68  call    cs:__imp_CompareStringW
0x180081d6e  cmp     eax, 2
0x180081d71  jz      short loc_180081D9C
0x180081d73  mov     rcx, rbp; this
0x180081d76  call    ?DwGetZone@CSecManager@@AEAAKXZ; CSecManager::DwGetZone(void)
0x180081d7b  mov     [rsp+68h+arg_10], eax
0x180081d82  cmp     eax, 2710h
0x180081d87  jbe     short loc_180081D91
0x180081d89  mov     eax, r15d
0x180081d8c  jmp     loc_180081CF9
0x180081d91  cmp     eax, r15d
0x180081d94  jz      loc_180081CF9
0x180081d9a  jmp     short loc_180081DA7
0x180081d9c  mov     [rsp+68h+arg_10], 3
0x180081da7  mov     rcx, rbx; psz1
0x180081daa  call    ?IsMHTMLUrlW@@YAHPEBG@Z; IsMHTMLUrlW(ushort const *)
0x180081daf  test    eax, eax
0x180081db1  jz      short loc_180081DBC
0x180081db3  call    ?GetMhtmlPrefixLength@@YA_KXZ; GetMhtmlPrefixLength(void)
0x180081db8  lea     rbx, [rbx+rax*2]
0x180081dbc  lea     rax, aMid; "mid:"
0x180081dc3  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x180081dc8  mov     r9d, r15d; cchCount1
0x180081dcb  mov     [rsp+68h+lpString2], rax; lpString2
0x180081dd0  mov     r8, rbx; lpString1
0x180081dd3  mov     edx, esi; dwCmpFlags
0x180081dd5  mov     ecx, 7Fh; Locale
0x180081dda  call    cs:__imp_CompareStringW
0x180081de0  cmp     eax, 2
0x180081de3  jz      loc_180081CF2
0x180081de9  mov     edi, 800C0011h
0x180081dee  jmp     short loc_180081DF5
0x180081df0  mov     edi, 80070057h
0x180081df5  mov     eax, edi
0x180081df7  add     rsp, 38h
0x180081dfb  pop     r15
0x180081dfd  pop     r14
0x180081dff  pop     rdi
0x180081e00  pop     rsi
0x180081e01  pop     rbp
0x180081e02  pop     rbx
0x180081e03  retn
```
