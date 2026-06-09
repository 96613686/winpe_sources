# UninstallPackage(ushort const *,ushort const *)

- ea: `0x140008b10`
- end: `0x140008cb3`
- name: `?UninstallPackage@@YAHPEBG0@Z`
- size: `419`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140004444`
- `0x140004ca8`
- `0x140006384`
- `0x14000810c`
- `0x1400087bc`
- `0x140008b10`
- `0x140009820`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140008bc0`
- `KERNEL32!GlobalFree` at `0x140008bd9`
- `KERNEL32!GlobalFree` at `0x140008c05`
- `KERNEL32!GlobalFree` at `0x140008c3e`
- `KERNEL32!GlobalFree` at `0x140008c8d`
- `KERNEL32!GlobalFree` at `0x140008bc0`
- `KERNEL32!GlobalFree` at `0x140008bd9`
- `KERNEL32!GlobalFree` at `0x140008c05`
- `KERNEL32!GlobalFree` at `0x140008c3e`
- `KERNEL32!GlobalFree` at `0x140008c8d`
- `msi!__imp_MsiLoadStringW` at `0x140008b8a`
- `msi!__imp_MsiLoadStringW` at `0x140008b8a`
- `msi!__imp_MsiMessageBoxW` at `0x140008bac`
- `msi!__imp_MsiMessageBoxW` at `0x140008bac`

## string_xrefs

- `0x140008c58`: `REMOVE=ALL`

## pseudocode

```c
__int64 __fastcall UninstallPackage(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HGLOBAL v3; // rcx
  int StringW; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _BYTE hMem[22]; // [rsp+30h] [rbp-40h] BYREF
  HGLOBAL v9; // [rsp+48h] [rbp-28h] BYREF
  int v10; // [rsp+50h] [rbp-20h]
  char v11; // [rsp+58h] [rbp-18h] BYREF

  if ( g_INSTALLUILEVEL == -1 )
  {
    *(_DWORD *)&hMem[8] = 1;
    *(_QWORD *)hMem = &hMem[16];
    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(hMem, 1024) )
    {
      if ( *(int *)&hMem[8] > 1 )
      {
        v3 = *(HGLOBAL *)hMem;
LABEL_15:
        GlobalFree(v3);
        return 14;
      }
      return 14;
    }
    StringW = MsiLoadStringW(-1, 24, *(_QWORD *)hMem, *(unsigned int *)&hMem[8], 0);
    if ( StringW && (unsigned int)MsiMessageBoxW(0, *(_QWORD *)hMem, 0, 65540, StringW, 0) != 6 )
    {
      if ( *(int *)&hMem[8] > 1 )
        GlobalFree(*(HGLOBAL *)hMem);
      return 1602;
    }
    if ( *(int *)&hMem[8] > 1 )
      GlobalFree(*(HGLOBAL *)hMem);
  }
  v10 = 1;
  v9 = &v11;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v9, 39) )
  {
    if ( v10 > 1 )
    {
      v3 = v9;
      goto LABEL_15;
    }
    return 14;
  }
  if ( IsGUID(a2) )
  {
    if ( StringCchCopyW((unsigned __int16 *)v9, v10, a2) < 0 )
    {
      if ( v10 > 1 )
        GlobalFree(v9);
      return 1627;
    }
    v6 = ConfigureOrRemoveProduct((const WCHAR *)v9, 1);
  }
  else
  {
    *(_OWORD *)hMem = *(_OWORD *)L"REMOVE=ALL";
    *(_QWORD *)&hMem[14] = *(_QWORD *)L"ALL";
    v6 = DoInstallPackage(a2, (const unsigned __int16 *)hMem, INSTALLUILEVEL_BASIC);
  }
  v7 = v6;
  if ( v10 > 1 )
    GlobalFree(v9);
  return v7;
}

```

## disassembly

```asm
0x140008b10  mov     [rsp-8+arg_0], rbx
0x140008b15  mov     [rsp-8+arg_10], rdi
0x140008b1a  push    rbp
0x140008b1b  mov     rbp, rsp
0x140008b1e  sub     rsp, 70h
0x140008b22  mov     rax, cs:__security_cookie
0x140008b29  xor     rax, rsp
0x140008b2c  mov     [rbp+var_10], rax
0x140008b30  cmp     cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A, 0FFFFFFFFh; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x140008b37  mov     rbx, rdx
0x140008b3a  mov     edi, 1
0x140008b3f  jnz     loc_140008BDF
0x140008b45  lea     rax, [rbp+var_30]
0x140008b49  mov     dword ptr [rbp+hMem+8], edi
0x140008b4c  mov     edx, 400h
0x140008b51  mov     [rbp+hMem], rax
0x140008b55  lea     rcx, [rbp+hMem]
0x140008b59  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x140008b5e  test    al, al
0x140008b60  jnz     short loc_140008B74
0x140008b62  cmp     dword ptr [rbp+hMem+8], edi
0x140008b65  jle     loc_140008C0B
0x140008b6b  mov     rcx, [rbp+hMem]
0x140008b6f  jmp     loc_140008C05
0x140008b74  mov     r9d, dword ptr [rbp+hMem+8]
0x140008b78  xor     eax, eax
0x140008b7a  mov     r8, [rbp+hMem]
0x140008b7e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140008b82  mov     word ptr [rsp+70h+var_50], ax
0x140008b87  lea     edx, [rax+18h]
0x140008b8a  call    cs:__imp_MsiLoadStringW
0x140008b90  test    eax, eax
0x140008b92  jz      short loc_140008BD0
0x140008b94  mov     rdx, [rbp+hMem]
0x140008b98  xor     ecx, ecx
0x140008b9a  mov     [rsp+70h+var_48], cx
0x140008b9f  mov     r9d, 10004h
0x140008ba5  xor     r8d, r8d
0x140008ba8  mov     [rsp+70h+var_50], eax
0x140008bac  call    cs:__imp_MsiMessageBoxW
0x140008bb2  cmp     eax, 6
0x140008bb5  jz      short loc_140008BD0
0x140008bb7  cmp     dword ptr [rbp+hMem+8], edi
0x140008bba  jle     short loc_140008BC6
0x140008bbc  mov     rcx, [rbp+hMem]; hMem
0x140008bc0  call    cs:__imp_GlobalFree
0x140008bc6  mov     eax, 642h
0x140008bcb  jmp     loc_140008C95
0x140008bd0  cmp     dword ptr [rbp+hMem+8], edi
0x140008bd3  jle     short loc_140008BDF
0x140008bd5  mov     rcx, [rbp+hMem]; hMem
0x140008bd9  call    cs:__imp_GlobalFree
0x140008bdf  lea     rax, [rbp+var_18]
0x140008be3  mov     [rbp+var_20], edi
0x140008be6  mov     edx, 27h ; '''
0x140008beb  mov     [rbp+var_28], rax
0x140008bef  lea     rcx, [rbp+var_28]
0x140008bf3  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x140008bf8  test    al, al
0x140008bfa  jnz     short loc_140008C15
0x140008bfc  cmp     [rbp+var_20], edi
0x140008bff  jle     short loc_140008C0B
0x140008c01  mov     rcx, [rbp+var_28]; hMem
0x140008c05  call    cs:__imp_GlobalFree
0x140008c0b  mov     eax, 0Eh
0x140008c10  jmp     loc_140008C95
0x140008c15  mov     rcx, rbx; unsigned __int16 *
0x140008c18  call    ?IsGUID@@YA_NPEBG@Z; IsGUID(ushort const *)
0x140008c1d  test    al, al
0x140008c1f  jz      short loc_140008C58
0x140008c21  movsxd  rdx, [rbp+var_20]; unsigned __int64
0x140008c25  mov     r8, rbx; unsigned __int16 *
0x140008c28  mov     rcx, [rbp+var_28]; unsigned __int16 *
0x140008c2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008c31  test    eax, eax
0x140008c33  jns     short loc_140008C4B
0x140008c35  cmp     [rbp+var_20], edi
0x140008c38  jle     short loc_140008C44
0x140008c3a  mov     rcx, [rbp+var_28]; hMem
0x140008c3e  call    cs:__imp_GlobalFree
0x140008c44  mov     eax, 65Bh
0x140008c49  jmp     short loc_140008C95
0x140008c4b  mov     rcx, [rbp+var_28]
0x140008c4f  mov     edx, edi
0x140008c51  call    ?ConfigureOrRemoveProduct@@YAHPEBGW4Bool@@@Z; ConfigureOrRemoveProduct(ushort const *,Bool)
0x140008c56  jmp     short loc_140008C82
0x140008c58  movups  xmm0, xmmword ptr cs:aRemoveAll; "REMOVE=ALL"
0x140008c5f  lea     rdx, [rbp+hMem]; unsigned __int16 *
0x140008c63  mov     r8d, 3; enum tagINSTALLUILEVEL
0x140008c69  movsd   xmm1, qword ptr cs:aRemoveAll+0Eh; "ALL"
0x140008c71  mov     rcx, rbx; unsigned __int16 *
0x140008c74  movups  xmmword ptr [rbp+hMem], xmm0
0x140008c78  movsd   [rbp+hMem+0Eh], xmm1
0x140008c7d  call    ?DoInstallPackage@@YAHPEBG0W4tagINSTALLUILEVEL@@@Z; DoInstallPackage(ushort const *,ushort const *,tagINSTALLUILEVEL)
0x140008c82  mov     ebx, eax
0x140008c84  cmp     [rbp+var_20], edi
0x140008c87  jle     short loc_140008C93
0x140008c89  mov     rcx, [rbp+var_28]; hMem
0x140008c8d  call    cs:__imp_GlobalFree
0x140008c93  mov     eax, ebx
0x140008c95  mov     rcx, [rbp+var_10]
0x140008c99  xor     rcx, rsp; StackCookie
0x140008c9c  call    __security_check_cookie
0x140008ca1  lea     r11, [rsp+70h+var_s0]
0x140008ca6  mov     rbx, [r11+10h]
0x140008caa  mov     rdi, [r11+20h]
0x140008cae  mov     rsp, r11
0x140008cb1  pop     rbp
0x140008cb2  retn
```
