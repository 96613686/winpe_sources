# GetRegString(HKEY__ *,ushort const *,STRU *)

- ea: `0x18000b644`
- end: `0x18000b7c5`
- name: `?GetRegString@@YAJPEAUHKEY__@@PEBGPEAVSTRU@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e488`

## callees

- `0x18000b644`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000b6d7`
- `ADVAPI32!RegQueryValueExW` at `0x18000b72e`
- `ADVAPI32!RegQueryValueExW` at `0x18000b6d7`
- `ADVAPI32!RegQueryValueExW` at `0x18000b72e`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000b6f2`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000b6f2`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000b6a2`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000b6a2`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b78f`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b78f`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000b697`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000b697`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000b7a3`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000b7a3`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b6b4`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b70b`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b76c`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b783`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b6b4`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b70b`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b76c`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b783`

## pseudocode

```c
__int64 __fastcall GetRegString(HKEY hKey, LPCWSTR lpValueName, struct STRU *a3)
{
  BYTE *lpData; // rax
  int v7; // ebx
  BYTE *Ptr; // rax
  _WORD *v9; // rax
  const unsigned __int16 *v10; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v14[56]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v15[256]; // [rsp+70h] [rbp-90h] BYREF

  Type = 0;
  memset_0(v15, 0, sizeof(v15));
  BUFFER::BUFFER((BUFFER *)v14, v15, 0x100u);
  cbData = BUFFER::QuerySize((BUFFER *)v14) - 2;
  lpData = (BYTE *)BUFFER::QueryPtr((BUFFER *)v14);
  v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
  if ( v7 == 234 )
  {
    if ( !BUFFER::Resize((BUFFER *)v14, cbData + 2) )
    {
      v7 = -2147024882;
      goto LABEL_14;
    }
    Ptr = (BYTE *)BUFFER::QueryPtr((BUFFER *)v14);
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Ptr, &cbData);
  }
  if ( v7 )
  {
    if ( v7 == 2 )
    {
      v7 = 1;
    }
    else if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
    }
  }
  else if ( Type == 1 )
  {
    v9 = BUFFER::QueryPtr((BUFFER *)v14);
    v9[cbData] = 0;
    v10 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v14);
    v7 = STRU::Copy(a3, v10);
    if ( v7 >= 0 )
      v7 = 0;
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_14:
  BUFFER::~BUFFER((BUFFER *)v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b644  push    rbp
0x18000b646  push    rbx
0x18000b647  push    rsi
0x18000b648  push    rdi
0x18000b649  push    r14
0x18000b64b  lea     rbp, [rsp-80h]
0x18000b650  sub     rsp, 180h
0x18000b657  mov     rax, cs:__security_cookie
0x18000b65e  xor     rax, rsp
0x18000b661  mov     [rbp+0A0h+var_30], rax
0x18000b665  mov     r14, r8
0x18000b668  mov     [rsp+1A0h+Type], 0
0x18000b670  mov     rsi, rdx
0x18000b673  mov     rdi, rcx
0x18000b676  mov     ebx, 100h
0x18000b67b  lea     rcx, [rsp+1A0h+var_130]; void *
0x18000b680  mov     r8d, ebx; Size
0x18000b683  xor     edx, edx; Val
0x18000b685  call    memset_0
0x18000b68a  mov     r8d, ebx
0x18000b68d  lea     rdx, [rsp+1A0h+var_130]
0x18000b692  lea     rcx, [rsp+1A0h+var_168]
0x18000b697  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000b69d  lea     rcx, [rsp+1A0h+var_168]
0x18000b6a2  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000b6a8  sub     eax, 2
0x18000b6ab  lea     rcx, [rsp+1A0h+var_168]
0x18000b6b0  mov     [rsp+1A0h+cbData], eax
0x18000b6b4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b6ba  lea     rcx, [rsp+1A0h+cbData]
0x18000b6bf  xor     r8d, r8d; lpReserved
0x18000b6c2  mov     [rsp+1A0h+lpcbData], rcx; lpcbData
0x18000b6c7  lea     r9, [rsp+1A0h+Type]; lpType
0x18000b6cc  mov     rcx, rdi; hKey
0x18000b6cf  mov     [rsp+1A0h+lpData], rax; lpData
0x18000b6d4  mov     rdx, rsi; lpValueName
0x18000b6d7  call    cs:__imp_RegQueryValueExW
0x18000b6dd  mov     ebx, eax
0x18000b6df  cmp     eax, 0EAh
0x18000b6e4  jnz     short loc_18000B736
0x18000b6e6  mov     edx, [rsp+1A0h+cbData]
0x18000b6ea  lea     rcx, [rsp+1A0h+var_168]
0x18000b6ef  add     edx, 2
0x18000b6f2  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000b6f8  test    al, al
0x18000b6fa  jnz     short loc_18000B706
0x18000b6fc  mov     ebx, 8007000Eh
0x18000b701  jmp     loc_18000B79E
0x18000b706  lea     rcx, [rsp+1A0h+var_168]
0x18000b70b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b711  lea     rcx, [rsp+1A0h+cbData]
0x18000b716  xor     r8d, r8d; lpReserved
0x18000b719  mov     [rsp+1A0h+lpcbData], rcx; lpcbData
0x18000b71e  lea     r9, [rsp+1A0h+Type]; lpType
0x18000b723  mov     rcx, rdi; hKey
0x18000b726  mov     [rsp+1A0h+lpData], rax; lpData
0x18000b72b  mov     rdx, rsi; lpValueName
0x18000b72e  call    cs:__imp_RegQueryValueExW
0x18000b734  mov     ebx, eax
0x18000b736  test    ebx, ebx
0x18000b738  jz      short loc_18000B755
0x18000b73a  cmp     ebx, 2
0x18000b73d  jnz     short loc_18000B746
0x18000b73f  mov     ebx, 1
0x18000b744  jmp     short loc_18000B79E
0x18000b746  test    ebx, ebx
0x18000b748  jle     short loc_18000B79E
0x18000b74a  movzx   ebx, bx
0x18000b74d  or      ebx, 80070000h
0x18000b753  jmp     short loc_18000B79E
0x18000b755  mov     ebx, 1
0x18000b75a  cmp     [rsp+1A0h+Type], ebx
0x18000b75e  jz      short loc_18000B767
0x18000b760  mov     ebx, 80070057h
0x18000b765  jmp     short loc_18000B79E
0x18000b767  lea     rcx, [rsp+1A0h+var_168]
0x18000b76c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b772  mov     r8d, [rsp+1A0h+cbData]
0x18000b777  lea     rcx, [rsp+1A0h+var_168]
0x18000b77c  xor     edx, edx
0x18000b77e  mov     [rax+r8*2], dx
0x18000b783  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b789  mov     rdx, rax
0x18000b78c  mov     rcx, r14
0x18000b78f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b795  xor     ecx, ecx
0x18000b797  mov     ebx, eax
0x18000b799  test    eax, eax
0x18000b79b  cmovns  ebx, ecx
0x18000b79e  lea     rcx, [rsp+1A0h+var_168]
0x18000b7a3  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b7a9  mov     eax, ebx
0x18000b7ab  mov     rcx, [rbp+0A0h+var_30]
0x18000b7af  xor     rcx, rsp; StackCookie
0x18000b7b2  call    __security_check_cookie
0x18000b7b7  add     rsp, 180h
0x18000b7be  pop     r14
0x18000b7c0  pop     rdi
0x18000b7c1  pop     rsi
0x18000b7c2  pop     rbx
0x18000b7c3  pop     rbp
0x18000b7c4  retn
```
