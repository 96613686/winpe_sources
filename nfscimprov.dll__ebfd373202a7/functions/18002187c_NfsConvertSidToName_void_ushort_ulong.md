# NfsConvertSidToName(void *,ushort *,ulong *)

- ea: `0x18002187c`
- end: `0x1800219f6`
- name: `?NfsConvertSidToName@@YAKPEAXPEAGPEAK@Z`
- size: `378`
- prototype: `unsigned int __fastcall(PSID Sid, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180019940`

## callees

- `0x180006a8c`
- `0x18002187c`
- `0x1800219fc`

## import_xrefs

- `msvcrt!malloc` at `0x18002190e`
- `msvcrt!malloc` at `0x18002192c`
- `msvcrt!malloc` at `0x18002190e`
- `msvcrt!malloc` at `0x18002192c`
- `msvcrt!free` at `0x1800219cd`
- `msvcrt!free` at `0x1800219d6`
- `msvcrt!free` at `0x1800219cd`
- `msvcrt!free` at `0x1800219d6`
- `KERNEL32!GetLastError` at `0x1800218df`
- `KERNEL32!GetLastError` at `0x180021969`
- `KERNEL32!GetLastError` at `0x1800218df`
- `KERNEL32!GetLastError` at `0x180021969`
- `ADVAPI32!LookupAccountSidW` at `0x1800218d1`
- `ADVAPI32!LookupAccountSidW` at `0x18002195f`
- `ADVAPI32!LookupAccountSidW` at `0x1800218d1`
- `ADVAPI32!LookupAccountSidW` at `0x18002195f`

## pseudocode

```c
__int64 __fastcall NfsConvertSidToName(PSID Sid, unsigned __int16 *a2, unsigned int *a3)
{
  DWORD LastError; // ebx
  WCHAR *v7; // r15
  WCHAR *ReferencedDomainName; // r14
  DWORD v9; // ecx
  __int64 v10; // rdi
  int v11; // eax
  DWORD cchName; // [rsp+88h] [rbp+48h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+50h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+98h] [rbp+58h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  LastError = 0;
  v7 = 0;
  ReferencedDomainName = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse)
    || (LastError = GetLastError(), LastError != 122) )
  {
    v9 = cchName;
    LODWORD(v10) = cchReferencedDomainName;
LABEL_14:
    if ( !a2 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v9 = cchName;
  v10 = cchReferencedDomainName;
  if ( !a2 || *a3 - cchName < cchReferencedDomainName )
  {
    LastError = 122;
    goto LABEL_14;
  }
  v7 = (WCHAR *)malloc(2LL * cchName);
  if ( v7 && (ReferencedDomainName = (WCHAR *)malloc(2 * v10)) != 0 )
  {
    LastError = 0;
    if ( LookupAccountSidW(0, Sid, v7, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse)
      || (LastError = GetLastError()) == 0 )
    {
      v11 = StringCchPrintfW(a2, *a3, L"%s\\%s", ReferencedDomainName, v7);
      if ( v11 < 0 )
        LastError = NfsGetErrorFromHr(v11);
    }
  }
  else
  {
    LastError = 14;
  }
LABEL_15:
  a2[*a3 - 1] = 0;
  v9 = cchName;
  LODWORD(v10) = cchReferencedDomainName;
LABEL_16:
  if ( a3 )
    *a3 = v10 + v9;
  free(v7);
  free(ReferencedDomainName);
  return LastError;
}

```

## disassembly

```asm
0x18002187c  mov     r11, rsp
0x18002187f  mov     [r11+8], rbx
0x180021883  push    rbp
0x180021884  push    rsi
0x180021885  push    rdi
0x180021886  push    r12
0x180021888  push    r13
0x18002188a  push    r14
0x18002188c  push    r15
0x18002188e  mov     rbp, rsp
0x180021891  sub     rsp, 40h
0x180021895  xor     edi, edi
0x180021897  lea     rax, [rbp+arg_18]
0x18002189b  mov     [r11-48h], rax
0x18002189f  lea     r9, [rbp+cchName]; cchName
0x1800218a3  lea     rax, [rbp+arg_10]
0x1800218a7  mov     [rbp+cchName], edi
0x1800218aa  mov     r12, rdx
0x1800218ad  mov     [r11-50h], rax
0x1800218b1  mov     rsi, r8
0x1800218b4  mov     [r11-58h], rdi
0x1800218b8  mov     r13, rcx
0x1800218bb  mov     [rbp+arg_10], edi
0x1800218be  mov     rdx, rcx; Sid
0x1800218c1  mov     [rbp+arg_18], edi
0x1800218c4  xor     r8d, r8d; Name
0x1800218c7  xor     ecx, ecx; lpSystemName
0x1800218c9  mov     ebx, edi
0x1800218cb  mov     r15d, edi
0x1800218ce  mov     r14d, edi
0x1800218d1  call    cs:__imp_LookupAccountSidW
0x1800218d7  test    eax, eax
0x1800218d9  jnz     loc_1800219A4
0x1800218df  call    cs:__imp_GetLastError
0x1800218e5  mov     ebx, eax
0x1800218e7  cmp     eax, 7Ah ; 'z'
0x1800218ea  jnz     loc_1800219A4
0x1800218f0  mov     ecx, [rbp+cchName]
0x1800218f3  mov     edi, [rbp+arg_10]
0x1800218f6  test    r12, r12
0x1800218f9  jz      loc_18002199D
0x1800218ff  mov     eax, [rsi]
0x180021901  sub     eax, ecx
0x180021903  cmp     eax, edi
0x180021905  jb      loc_18002199D
0x18002190b  add     rcx, rcx; Size
0x18002190e  call    cs:__imp_malloc
0x180021914  mov     r15, rax
0x180021917  test    rax, rax
0x18002191a  jnz     short loc_180021926
0x18002191c  mov     ebx, 0Eh
0x180021921  jmp     loc_1800219AF
0x180021926  mov     rcx, rdi
0x180021929  add     rcx, rcx; Size
0x18002192c  call    cs:__imp_malloc
0x180021932  mov     r14, rax
0x180021935  test    rax, rax
0x180021938  jz      short loc_18002191C
0x18002193a  lea     rax, [rbp+arg_18]
0x18002193e  mov     r8, r15; Name
0x180021941  mov     [rsp+40h+peUse], rax; peUse
0x180021946  lea     r9, [rbp+cchName]; cchName
0x18002194a  lea     rax, [rbp+arg_10]
0x18002194e  mov     rdx, r13; Sid
0x180021951  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180021956  xor     ecx, ecx; lpSystemName
0x180021958  mov     [rsp+40h+ReferencedDomainName], r14; ReferencedDomainName
0x18002195d  xor     ebx, ebx
0x18002195f  call    cs:__imp_LookupAccountSidW
0x180021965  test    eax, eax
0x180021967  jnz     short loc_180021975
0x180021969  call    cs:__imp_GetLastError
0x18002196f  mov     ebx, eax
0x180021971  test    eax, eax
0x180021973  jnz     short loc_1800219AF
0x180021975  mov     edx, [rsi]; unsigned __int64
0x180021977  lea     r8, aSS; "%s\\%s"
0x18002197e  mov     r9, r14
0x180021981  mov     [rsp+40h+ReferencedDomainName], r15
0x180021986  mov     rcx, r12; unsigned __int16 *
0x180021989  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002198e  test    eax, eax
0x180021990  jns     short loc_1800219AF
0x180021992  mov     ecx, eax; int
0x180021994  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x180021999  mov     ebx, eax
0x18002199b  jmp     short loc_1800219AF
0x18002199d  mov     ebx, 7Ah ; 'z'
0x1800219a2  jmp     short loc_1800219AA
0x1800219a4  mov     ecx, [rbp+cchName]
0x1800219a7  mov     edi, [rbp+arg_10]
0x1800219aa  test    r12, r12
0x1800219ad  jz      short loc_1800219C0
0x1800219af  mov     ecx, [rsi]
0x1800219b1  dec     ecx
0x1800219b3  xor     eax, eax
0x1800219b5  mov     [r12+rcx*2], ax
0x1800219ba  mov     ecx, [rbp+cchName]
0x1800219bd  mov     edi, [rbp+arg_10]
0x1800219c0  test    rsi, rsi
0x1800219c3  jz      short loc_1800219CA
0x1800219c5  lea     eax, [rdi+rcx]
0x1800219c8  mov     [rsi], eax
0x1800219ca  mov     rcx, r15; Block
0x1800219cd  call    cs:__imp_free
0x1800219d3  mov     rcx, r14; Block
0x1800219d6  call    cs:__imp_free
0x1800219dc  mov     eax, ebx
0x1800219de  mov     rbx, [rsp+40h+arg_0]
0x1800219e6  add     rsp, 40h
0x1800219ea  pop     r15
0x1800219ec  pop     r14
0x1800219ee  pop     r13
0x1800219f0  pop     r12
0x1800219f2  pop     rdi
0x1800219f3  pop     rsi
0x1800219f4  pop     rbp
0x1800219f5  retn
```
