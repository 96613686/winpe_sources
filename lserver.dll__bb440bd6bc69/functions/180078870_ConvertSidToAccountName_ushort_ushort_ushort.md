# ConvertSidToAccountName(ushort *,ushort * *,ushort * *)

- ea: `0x180078870`
- end: `0x180078a43`
- name: `?ConvertSidToAccountName@@YAJPEAGPEAPEAG1@Z`
- size: `467`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800385d8`
- `0x180078280`

## callees

- `0x180005665`
- `0x180078870`

## import_xrefs

- `msvcrt!malloc` at `0x180078940`
- `msvcrt!malloc` at `0x180078974`
- `msvcrt!malloc` at `0x180078940`
- `msvcrt!malloc` at `0x180078974`
- `msvcrt!free` at `0x180078a0d`
- `msvcrt!free` at `0x180078a25`
- `msvcrt!free` at `0x180078a0d`
- `msvcrt!free` at `0x180078a25`
- `ADVAPI32!LookupAccountSidW` at `0x180078904`
- `ADVAPI32!LookupAccountSidW` at `0x1800789bc`
- `ADVAPI32!LookupAccountSidW` at `0x180078904`
- `ADVAPI32!LookupAccountSidW` at `0x1800789bc`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800788ac`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800788ac`
- `KERNEL32!GetLastError` at `0x1800788bc`
- `KERNEL32!GetLastError` at `0x180078914`
- `KERNEL32!GetLastError` at `0x1800789cc`
- `KERNEL32!GetLastError` at `0x1800788bc`
- `KERNEL32!GetLastError` at `0x180078914`
- `KERNEL32!GetLastError` at `0x1800789cc`
- `KERNEL32!LocalFree` at `0x1800789f0`
- `KERNEL32!LocalFree` at `0x1800789f0`

## pseudocode

```c
__int64 __fastcall ConvertSidToAccountName(unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  signed int v3; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  size_t v8; // rdi
  unsigned __int16 *v9; // rax
  size_t v10; // rdi
  void *v11; // rax
  signed int v12; // eax
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp+30h] BYREF
  int v15; // [rsp+74h] [rbp+34h]
  DWORD cchName; // [rsp+78h] [rbp+38h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+80h] [rbp+40h] BYREF
  PSID Sid; // [rsp+88h] [rbp+48h] BYREF

  v15 = HIDWORD(a1);
  v3 = 0;
  peUse = SidTypeGroup;
  *a2 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  Sid = 0;
  *a3 = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-32-576", &Sid) )
    goto LABEL_8;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_8:
    if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
      goto LABEL_9;
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_9:
      v8 = 2LL * cchName;
      v9 = (unsigned __int16 *)malloc(v8);
      *a2 = v9;
      if ( v9
        && (memset_0(v9, 0, v8),
            v10 = 2LL * cchReferencedDomainName,
            v11 = malloc(v10),
            (*a3 = (unsigned __int16 *)v11) != 0) )
      {
        memset_0(v11, 0, v10);
        if ( !LookupAccountSidW(0, Sid, *a2, &cchName, *a3, &cchReferencedDomainName, &peUse) )
        {
          v12 = GetLastError();
          v3 = v12;
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
        }
      }
      else
      {
        v3 = 14;
      }
    }
  }
  if ( Sid )
    LocalFree(Sid);
  Sid = 0;
  if ( v3 < 0 )
  {
    if ( *a2 )
      free(*a2);
    *a2 = 0;
    if ( *a3 )
      free(*a3);
    *a3 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180078870  mov     qword ptr [rsp-28h+arg_0], rcx
0x180078875  push    rbp
0x180078876  push    rbx
0x180078877  push    rsi
0x180078878  push    rdi
0x180078879  push    r14
0x18007887b  mov     rbp, rsp
0x18007887e  sub     rsp, 40h
0x180078882  xor     ebx, ebx
0x180078884  mov     [rbp+arg_10], 2
0x18007888b  and     [rdx], rbx
0x18007888e  lea     rcx, aS1532576; "S-1-5-32-576"
0x180078895  and     [rbp+cchName], ebx
0x180078898  mov     rsi, rdx
0x18007889b  and     [rbp+arg_0], ebx
0x18007889e  lea     rdx, [rbp+Sid]; Sid
0x1800788a2  and     [rbp+Sid], rbx
0x1800788a6  mov     r14, r8
0x1800788a9  and     [r8], rbx
0x1800788ac  call    cs:__imp_ConvertStringSidToSidW
0x1800788b3  nop     dword ptr [rax+rax+00h]
0x1800788b8  test    eax, eax
0x1800788ba  jnz     short loc_1800788DF
0x1800788bc  call    cs:__imp_GetLastError
0x1800788c3  nop     dword ptr [rax+rax+00h]
0x1800788c8  mov     ebx, eax
0x1800788ca  test    eax, eax
0x1800788cc  jle     short loc_1800788D7
0x1800788ce  movzx   ebx, ax
0x1800788d1  or      ebx, 80070000h
0x1800788d7  test    ebx, ebx
0x1800788d9  js      loc_1800789E7
0x1800788df  mov     rdx, [rbp+Sid]; Sid
0x1800788e3  lea     rax, [rbp+arg_10]
0x1800788e7  mov     [rsp+40h+peUse], rax; peUse
0x1800788ec  lea     r9, [rbp+cchName]; cchName
0x1800788f0  lea     rax, [rbp+arg_0]
0x1800788f4  xor     r8d, r8d; Name
0x1800788f7  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800788fc  xor     ecx, ecx; lpSystemName
0x1800788fe  and     [rsp+40h+ReferencedDomainName], 0
0x180078904  call    cs:__imp_LookupAccountSidW
0x18007890b  nop     dword ptr [rax+rax+00h]
0x180078910  test    eax, eax
0x180078912  jz      short loc_180078937
0x180078914  call    cs:__imp_GetLastError
0x18007891b  nop     dword ptr [rax+rax+00h]
0x180078920  mov     ebx, eax
0x180078922  test    eax, eax
0x180078924  jle     short loc_18007892F
0x180078926  movzx   ebx, ax
0x180078929  or      ebx, 80070000h
0x18007892f  test    ebx, ebx
0x180078931  js      loc_1800789E7
0x180078937  mov     edi, [rbp+cchName]
0x18007893a  add     rdi, rdi
0x18007893d  mov     rcx, rdi; Size
0x180078940  call    cs:__imp_malloc
0x180078947  nop     dword ptr [rax+rax+00h]
0x18007894c  mov     [rsi], rax
0x18007894f  test    rax, rax
0x180078952  jnz     short loc_18007895E
0x180078954  mov     ebx, 0Eh
0x180078959  jmp     loc_1800789E7
0x18007895e  mov     r8, rdi; Size
0x180078961  xor     edx, edx; Val
0x180078963  mov     rcx, rax; void *
0x180078966  call    memset_0
0x18007896b  mov     edi, [rbp+arg_0]
0x18007896e  add     rdi, rdi
0x180078971  mov     rcx, rdi; Size
0x180078974  call    cs:__imp_malloc
0x18007897b  nop     dword ptr [rax+rax+00h]
0x180078980  mov     [r14], rax
0x180078983  test    rax, rax
0x180078986  jz      short loc_180078954
0x180078988  mov     r8, rdi; Size
0x18007898b  xor     edx, edx; Val
0x18007898d  mov     rcx, rax; void *
0x180078990  call    memset_0
0x180078995  mov     r8, [rsi]; Name
0x180078998  lea     rax, [rbp+arg_10]
0x18007899c  mov     rdx, [rbp+Sid]; Sid
0x1800789a0  lea     r9, [rbp+cchName]; cchName
0x1800789a4  mov     [rsp+40h+peUse], rax; peUse
0x1800789a9  xor     ecx, ecx; lpSystemName
0x1800789ab  lea     rax, [rbp+arg_0]
0x1800789af  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800789b4  mov     rax, [r14]
0x1800789b7  mov     [rsp+40h+ReferencedDomainName], rax; ReferencedDomainName
0x1800789bc  call    cs:__imp_LookupAccountSidW
0x1800789c3  nop     dword ptr [rax+rax+00h]
0x1800789c8  test    eax, eax
0x1800789ca  jnz     short loc_1800789E7
0x1800789cc  call    cs:__imp_GetLastError
0x1800789d3  nop     dword ptr [rax+rax+00h]
0x1800789d8  mov     ebx, eax
0x1800789da  test    eax, eax
0x1800789dc  jle     short loc_1800789E7
0x1800789de  movzx   ebx, ax
0x1800789e1  or      ebx, 80070000h
0x1800789e7  mov     rcx, [rbp+Sid]; hMem
0x1800789eb  test    rcx, rcx
0x1800789ee  jz      short loc_1800789FC
0x1800789f0  call    cs:__imp_LocalFree
0x1800789f7  nop     dword ptr [rax+rax+00h]
0x1800789fc  and     [rbp+Sid], 0
0x180078a01  test    ebx, ebx
0x180078a03  jns     short loc_180078A35
0x180078a05  mov     rcx, [rsi]; Block
0x180078a08  test    rcx, rcx
0x180078a0b  jz      short loc_180078A19
0x180078a0d  call    cs:__imp_free
0x180078a14  nop     dword ptr [rax+rax+00h]
0x180078a19  and     qword ptr [rsi], 0
0x180078a1d  mov     rcx, [r14]; Block
0x180078a20  test    rcx, rcx
0x180078a23  jz      short loc_180078A31
0x180078a25  call    cs:__imp_free
0x180078a2c  nop     dword ptr [rax+rax+00h]
0x180078a31  and     qword ptr [r14], 0
0x180078a35  mov     eax, ebx
0x180078a37  add     rsp, 40h
0x180078a3b  pop     r14
0x180078a3d  pop     rdi
0x180078a3e  pop     rsi
0x180078a3f  pop     rbx
0x180078a40  pop     rbp
0x180078a41  retn
```
