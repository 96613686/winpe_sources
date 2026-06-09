# myGetAccountNameFromSID(void *,ushort * *,ushort * *)

- ea: `0x180018060`
- end: `0x1800181c3`
- name: `?myGetAccountNameFromSID@@YAJPEAXPEAPEAG1@Z`
- size: `355`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180018620`

## callees

- `0x180008400`
- `0x180012450`
- `0x180018060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018100`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018125`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018100`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181aa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800180c9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001816d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800180c9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001816d`

## pseudocode

```c
__int64 __fastcall myGetAccountNameFromSID(PSID Sid, unsigned __int16 **a2, unsigned __int16 **a3)
{
  WCHAR *ReferencedDomainName; // rsi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  WCHAR *v9; // rdi
  unsigned int v10; // ecx
  int v11; // edx
  DWORD cchReferencedDomainName; // [rsp+78h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+80h] [rbp+18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+88h] [rbp+20h] BYREF

  ReferencedDomainName = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    v7 = myHLastError();
    v8 = v7;
    if ( v7 != -2147024774 )
    {
      v9 = 0;
      v10 = 628294042;
LABEL_8:
      v11 = v7;
LABEL_9:
      CSPrintErrorLineFile(v10, v11);
      goto LABEL_21;
    }
  }
  v9 = (WCHAR *)LocalAlloc(0, 2LL * cchName);
  if ( !v9 )
  {
    v11 = -2147024882;
    v10 = 628818330;
    v8 = -2147024882;
    goto LABEL_9;
  }
  ReferencedDomainName = (WCHAR *)LocalAlloc(0, 2LL * cchReferencedDomainName);
  if ( !ReferencedDomainName )
  {
    v11 = -2147024882;
    v10 = 629277082;
    v8 = -2147024882;
    goto LABEL_9;
  }
  if ( !LookupAccountSidW(0, Sid, v9, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v7 = myHLastError();
    v8 = v7;
    v10 = 630129050;
    goto LABEL_8;
  }
  if ( a3 )
  {
    *a3 = ReferencedDomainName;
    ReferencedDomainName = 0;
  }
  if ( a2 )
  {
    *a2 = v9;
    v9 = 0;
  }
  v8 = 0;
LABEL_21:
  LocalFree(ReferencedDomainName);
  LocalFree(v9);
  return v8;
}

```

## disassembly

```asm
0x180018060  mov     [rsp+arg_0], rbx
0x180018065  push    rbp
0x180018066  push    rsi
0x180018067  push    rdi
0x180018068  push    r14
0x18001806a  push    r15
0x18001806c  sub     rsp, 40h
0x180018070  xor     esi, esi
0x180018072  mov     r14, r8
0x180018075  mov     r15, rdx
0x180018078  mov     rbp, rcx
0x18001807b  test    rdx, rdx
0x18001807e  jz      short loc_180018083
0x180018080  mov     [rdx], rsi
0x180018083  test    r14, r14
0x180018086  jz      short loc_18001808B
0x180018088  mov     [r8], rsi
0x18001808b  lea     rax, [rsp+68h+arg_18]
0x180018093  mov     [rsp+68h+cchName], esi
0x18001809a  mov     [rsp+68h+peUse], rax; peUse
0x18001809f  lea     r9, [rsp+68h+cchName]; cchName
0x1800180a7  lea     rax, [rsp+68h+arg_8]
0x1800180ac  mov     [rsp+68h+arg_8], esi
0x1800180b0  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800180b5  xor     r8d, r8d; Name
0x1800180b8  mov     rdx, rbp; Sid
0x1800180bb  mov     [rsp+68h+ReferencedDomainName], rsi; ReferencedDomainName
0x1800180c0  xor     ecx, ecx; lpSystemName
0x1800180c2  mov     [rsp+68h+arg_18], esi
0x1800180c9  call    cs:__imp_LookupAccountSidW
0x1800180cf  test    eax, eax
0x1800180d1  jnz     short loc_1800180F4
0x1800180d3  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800180d8  mov     ebx, eax
0x1800180da  cmp     eax, 8007007Ah
0x1800180df  jz      short loc_1800180F4
0x1800180e1  xor     edi, edi
0x1800180e3  mov     ecx, 2573019Ah; unsigned int
0x1800180e8  mov     edx, eax; int
0x1800180ea  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800180ef  jmp     loc_18001819E
0x1800180f4  mov     edx, [rsp+68h+cchName]
0x1800180fb  xor     ecx, ecx; uFlags
0x1800180fd  add     rdx, rdx; uBytes
0x180018100  call    cs:__imp_LocalAlloc
0x180018106  mov     rdi, rax
0x180018109  test    rax, rax
0x18001810c  jnz     short loc_18001811C
0x18001810e  mov     edx, 8007000Eh
0x180018113  mov     ecx, 257B019Ah
0x180018118  mov     ebx, edx
0x18001811a  jmp     short loc_1800180EA
0x18001811c  mov     edx, [rsp+68h+arg_8]
0x180018120  xor     ecx, ecx; uFlags
0x180018122  add     rdx, rdx; uBytes
0x180018125  call    cs:__imp_LocalAlloc
0x18001812b  mov     rsi, rax
0x18001812e  test    rax, rax
0x180018131  jnz     short loc_180018141
0x180018133  mov     edx, 8007000Eh
0x180018138  mov     ecx, 2582019Ah
0x18001813d  mov     ebx, edx
0x18001813f  jmp     short loc_1800180EA
0x180018141  lea     rax, [rsp+68h+arg_18]
0x180018149  mov     r8, rdi; Name
0x18001814c  mov     [rsp+68h+peUse], rax; peUse
0x180018151  lea     r9, [rsp+68h+cchName]; cchName
0x180018159  lea     rax, [rsp+68h+arg_8]
0x18001815e  mov     rdx, rbp; Sid
0x180018161  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180018166  xor     ecx, ecx; lpSystemName
0x180018168  mov     [rsp+68h+ReferencedDomainName], rsi; ReferencedDomainName
0x18001816d  call    cs:__imp_LookupAccountSidW
0x180018173  test    eax, eax
0x180018175  jnz     short loc_180018188
0x180018177  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001817c  mov     ebx, eax
0x18001817e  mov     ecx, 258F019Ah
0x180018183  jmp     loc_1800180E8
0x180018188  test    r14, r14
0x18001818b  jz      short loc_180018192
0x18001818d  mov     [r14], rsi
0x180018190  xor     esi, esi
0x180018192  test    r15, r15
0x180018195  jz      short loc_18001819C
0x180018197  mov     [r15], rdi
0x18001819a  xor     edi, edi
0x18001819c  xor     ebx, ebx
0x18001819e  mov     rcx, rsi; hMem
0x1800181a1  call    cs:__imp_LocalFree
0x1800181a7  mov     rcx, rdi; hMem
0x1800181aa  call    cs:__imp_LocalFree
0x1800181b0  mov     eax, ebx
0x1800181b2  mov     rbx, [rsp+68h+arg_0]
0x1800181b7  add     rsp, 40h
0x1800181bb  pop     r15
0x1800181bd  pop     r14
0x1800181bf  pop     rdi
0x1800181c0  pop     rsi
0x1800181c1  pop     rbp
0x1800181c2  retn
```
