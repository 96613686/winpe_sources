# LdapHasWriteAccess

- ea: `0x180010ed8`
- end: `0x180011057`
- name: `LdapHasWriteAccess`
- size: `383`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d698`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x180010ed8`
- `0x180011134`
- `0x180012e70`
- `0x18001a1e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fb6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180010ff2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180010ff2`

## pseudocode

```c
__int64 __fastcall LdapHasWriteAccess(LDAP *a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // rcx
  __int64 v5; // rbx
  CHAR *lpMultiByteStr; // rax
  CHAR *v7; // rsi
  __int64 v9; // r15
  unsigned int v10; // r14d
  unsigned int i; // edi
  __int64 v12[2]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v13[3]; // [rsp+50h] [rbp-29h] BYREF
  int v14; // [rsp+68h] [rbp-11h]
  int v15; // [rsp+6Ch] [rbp-Dh]
  __int64 v16; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  _QWORD *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  const WCHAR *v20; // [rsp+90h] [rbp+17h]

  v2 = *(_DWORD *)(a2 + 24) == 1;
  v13[0] = L"allowedAttributesEffective";
  v13[1] = 0;
  *(_OWORD *)v12 = 0;
  if ( !v2 )
    return 0;
  if ( *(_DWORD *)(a2 + 40) )
    return 0;
  v13[2] = *(_QWORD *)a2;
  v14 = *(_DWORD *)(a2 + 8);
  v16 = *(_QWORD *)(a2 + 16);
  v18 = v13;
  v20 = L"(objectClass=*)";
  v15 = 0;
  v17 = 1;
  v19 = 0;
  if ( !(unsigned int)LdapSendReceiveUrlRequest(a1, (__int64)v12, 0) )
    return 0;
  v4 = **(_QWORD **)(a2 + 32);
  if ( v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(v4 + 2 * v5) );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  lpMultiByteStr = (CHAR *)operator new((unsigned int)(v5 + 1));
  v7 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    SetLastError(0x8007000E);
    return 0;
  }
  if ( !WideCharToMultiByte(0, 0, **(LPCWCH **)(a2 + 32), -1, lpMultiByteStr, v5 + 1, 0, 0) )
  {
    operator delete(v7);
    return 0;
  }
  v9 = v12[1];
  v10 = 0;
  for ( i = 0; i < LODWORD(v12[0]); ++i )
  {
    if ( *(_DWORD *)(v9 + 16LL * i) == (_DWORD)v5
      && !(unsigned int)Pki_strnicmp(v7, *(PCNZCH *)(v9 + 16LL * i + 8), (unsigned int)v5) )
    {
      v10 = 1;
      break;
    }
  }
  LdapFreeCryptBlobArray(v12);
  operator delete(v7);
  return v10;
}

```

## disassembly

```asm
0x180010ed8  push    rbp
0x180010eda  push    rbx
0x180010edb  push    rsi
0x180010edc  push    rdi
0x180010edd  push    r12
0x180010edf  push    r14
0x180010ee1  push    r15
0x180010ee3  lea     rbp, [rsp-27h]
0x180010ee8  sub     rsp, 0A0h
0x180010eef  xor     r12d, r12d
0x180010ef2  lea     rax, aAllowedattribu; "allowedAttributesEffective"
0x180010ef9  cmp     dword ptr [rdx+18h], 1
0x180010efd  xorps   xmm0, xmm0
0x180010f00  mov     rdi, rdx
0x180010f03  mov     [rbp+57h+var_80], rax
0x180010f07  mov     [rbp+57h+var_78], r12
0x180010f0b  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180010f0f  jnz     loc_180010FBC
0x180010f15  cmp     [rdx+28h], r12d
0x180010f19  jnz     loc_180010FBC
0x180010f1f  mov     rax, [rdx]
0x180010f22  mov     r9d, 3A98h
0x180010f28  mov     [rbp+57h+var_70], rax
0x180010f2c  xor     r8d, r8d
0x180010f2f  mov     eax, [rdx+8]
0x180010f32  mov     [rbp+57h+var_68], eax
0x180010f35  mov     rax, [rdx+10h]
0x180010f39  lea     rdx, [rbp+57h+var_70]
0x180010f3d  mov     [rbp+57h+var_60], rax
0x180010f41  lea     rax, [rbp+57h+var_80]
0x180010f45  mov     [rbp+57h+var_50], rax
0x180010f49  lea     rax, aObjectclass; "(objectClass=*)"
0x180010f50  mov     [rbp+57h+var_40], rax
0x180010f54  lea     rax, [rbp+57h+var_90]
0x180010f58  mov     qword ptr [rsp+0D0h+cbMultiByte], r12; __int64
0x180010f5d  mov     [rsp+0D0h+lpMultiByteStr], rax; __int64
0x180010f62  mov     [rbp+57h+var_64], r12d
0x180010f66  mov     [rbp+57h+var_58], 1
0x180010f6e  mov     [rbp+57h+var_48], r12
0x180010f72  call    LdapSendReceiveUrlRequest
0x180010f77  test    eax, eax
0x180010f79  jz      short loc_180010FBC
0x180010f7b  mov     rax, [rdi+20h]
0x180010f7f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180010f83  mov     rcx, [rax]
0x180010f86  test    rcx, rcx
0x180010f89  jz      short loc_180010F9A
0x180010f8b  mov     rbx, r15
0x180010f8e  inc     rbx
0x180010f91  cmp     [rcx+rbx*2], r12w
0x180010f96  jnz     short loc_180010F8E
0x180010f98  jmp     short loc_180010F9D
0x180010f9a  mov     ebx, r12d
0x180010f9d  lea     r14d, [rbx+1]
0x180010fa1  mov     ecx, r14d; uBytes
0x180010fa4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010fa9  mov     rsi, rax
0x180010fac  test    rax, rax
0x180010faf  jnz     short loc_180010FD0
0x180010fb1  mov     ecx, 8007000Eh; dwErrCode
0x180010fb6  call    cs:__imp_SetLastError
0x180010fbc  xor     eax, eax
0x180010fbe  add     rsp, 0A0h
0x180010fc5  pop     r15
0x180010fc7  pop     r14
0x180010fc9  pop     r12
0x180010fcb  pop     rdi
0x180010fcc  pop     rsi
0x180010fcd  pop     rbx
0x180010fce  pop     rbp
0x180010fcf  retn
0x180010fd0  mov     r8, [rdi+20h]
0x180010fd4  mov     r9d, r15d; cchWideChar
0x180010fd7  mov     [rsp+0D0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180010fdc  xor     edx, edx; dwFlags
0x180010fde  mov     [rsp+0D0h+lpDefaultChar], r12; lpDefaultChar
0x180010fe3  xor     ecx, ecx; CodePage
0x180010fe5  mov     [rsp+0D0h+cbMultiByte], r14d; cbMultiByte
0x180010fea  mov     r8, [r8]; lpWideCharStr
0x180010fed  mov     [rsp+0D0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180010ff2  call    cs:__imp_WideCharToMultiByte
0x180010ff8  test    eax, eax
0x180010ffa  jnz     short loc_180011006
0x180010ffc  mov     rcx, rsi; hMem
0x180010fff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011004  jmp     short loc_180010FBC
0x180011006  mov     r15, [rbp+57h+var_90+8]
0x18001100a  mov     r14d, r12d
0x18001100d  mov     edi, r12d
0x180011010  cmp     edi, dword ptr [rbp+57h+var_90]
0x180011013  jnb     short loc_18001103E
0x180011015  mov     edx, edi
0x180011017  add     rdx, rdx
0x18001101a  cmp     [r15+rdx*8], ebx
0x18001101e  jnz     short loc_180011034
0x180011020  mov     rdx, [r15+rdx*8+8]; lpString2
0x180011025  mov     rcx, rsi; lpString1
0x180011028  mov     r8d, ebx
0x18001102b  call    Pki_strnicmp
0x180011030  test    eax, eax
0x180011032  jz      short loc_180011038
0x180011034  inc     edi
0x180011036  jmp     short loc_180011010
0x180011038  mov     r14d, 1
0x18001103e  lea     rcx, [rbp+57h+var_90]
0x180011042  call    LdapFreeCryptBlobArray
0x180011047  mov     rcx, rsi; hMem
0x18001104a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001104f  mov     eax, r14d
0x180011052  jmp     loc_180010FBE
```
