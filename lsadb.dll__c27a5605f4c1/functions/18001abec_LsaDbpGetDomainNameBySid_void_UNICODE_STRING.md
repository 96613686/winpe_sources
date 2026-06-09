# LsaDbpGetDomainNameBySid(void *,_UNICODE_STRING *)

- ea: `0x18001abec`
- end: `0x18001ace2`
- name: `?LsaDbpGetDomainNameBySid@@YAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(void *Src, PUNICODE_STRING DestinationString)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a6d8`
- `0x18001a894`
- `0x18001cc08`
- `0x18001e138`

## callees

- `0x180001670`
- `0x18001abec`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001acb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001acb9`
- `ntdll!RtlInitUnicodeString` at `0x18001acae`
- `ntdll!RtlInitUnicodeString` at `0x18001acae`
- `ntdll!RtlLengthSid` at `0x18001ac2e`
- `ntdll!RtlLengthSid` at `0x18001ac40`
- `ntdll!RtlLengthSid` at `0x18001ac2e`
- `ntdll!RtlLengthSid` at `0x18001ac40`
- `NTDSA!FindNetbiosDomainName` at `0x18001ac67`
- `NTDSA!FindNetbiosDomainName` at `0x18001ac9c`
- `NTDSA!FindNetbiosDomainName` at `0x18001ac67`
- `NTDSA!FindNetbiosDomainName` at `0x18001ac9c`

## pseudocode

```c
__int64 __fastcall LsaDbpGetDomainNameBySid(void *Src, PUNICODE_STRING DestinationString)
{
  ULONG v4; // ebx
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  int NetbiosDomainName; // ebx
  ULONG v9; // [rsp+20h] [rbp-50h] BYREF
  _OWORD v10[4]; // [rsp+28h] [rbp-48h] BYREF

  memset(v10, 0, 60);
  LODWORD(v10[0]) = 58;
  v9 = 0;
  v4 = 28;
  if ( RtlLengthSid(Src) <= 0x1C )
    v4 = RtlLengthSid(Src);
  v9 = v4;
  memcpy_0((char *)&v10[1] + 8, Src, v4);
  DWORD1(v10[0]) = v4;
  if ( (int)FindNetbiosDomainName(v10, 0, &v9) < 0 )
    return (unsigned int)-1073741601;
  v5 = (WCHAR *)LocalAlloc(0x40u, 2LL * v9);
  v6 = v5;
  if ( v5 )
  {
    NetbiosDomainName = FindNetbiosDomainName(v10, v5, &v9);
    if ( NetbiosDomainName >= 0 )
    {
      RtlInitUnicodeString(DestinationString, v6);
      return (unsigned int)NetbiosDomainName;
    }
    LocalFree(v6);
    return (unsigned int)-1073741601;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x18001abec  mov     [rsp-18h+arg_10], rbx
0x18001abf1  push    rbp
0x18001abf2  push    rsi
0x18001abf3  push    rdi
0x18001abf4  mov     rbp, rsp
0x18001abf7  sub     rsp, 70h
0x18001abfb  mov     rax, cs:__security_cookie
0x18001ac02  xor     rax, rsp
0x18001ac05  mov     [rbp+var_8], rax
0x18001ac09  xorps   xmm0, xmm0
0x18001ac0c  xor     eax, eax
0x18001ac0e  movups  [rbp+var_48], xmm0
0x18001ac12  mov     dword ptr [rbp+var_48], 3Ah ; ':'
0x18001ac19  mov     rsi, rdx
0x18001ac1c  movups  xmmword ptr [rbp+var_28], xmm0
0x18001ac20  mov     rdi, rcx
0x18001ac23  mov     [rbp+var_50], eax
0x18001ac26  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x18001ac2a  movups  [rbp+var_38], xmm0
0x18001ac2e  call    cs:__imp_RtlLengthSid
0x18001ac34  mov     ebx, 1Ch
0x18001ac39  cmp     eax, ebx
0x18001ac3b  ja      short loc_18001AC48
0x18001ac3d  mov     rcx, rdi; Sid
0x18001ac40  call    cs:__imp_RtlLengthSid
0x18001ac46  mov     ebx, eax
0x18001ac48  mov     r8d, ebx; Size
0x18001ac4b  lea     rcx, [rbp+var_38+8]; void *
0x18001ac4f  mov     rdx, rdi; Src
0x18001ac52  mov     [rbp+var_50], ebx
0x18001ac55  call    memcpy_0
0x18001ac5a  lea     r8, [rbp+var_50]
0x18001ac5e  mov     dword ptr [rbp+var_48+4], ebx
0x18001ac61  xor     edx, edx
0x18001ac63  lea     rcx, [rbp+var_48]
0x18001ac67  call    cs:__imp_FindNetbiosDomainName
0x18001ac6d  test    eax, eax
0x18001ac6f  js      short loc_18001ACBF
0x18001ac71  mov     edx, [rbp+var_50]
0x18001ac74  mov     ecx, 40h ; '@'; uFlags
0x18001ac79  add     rdx, rdx; uBytes
0x18001ac7c  call    cs:__imp_LocalAlloc
0x18001ac82  mov     rdi, rax
0x18001ac85  test    rax, rax
0x18001ac88  jnz     short loc_18001AC91
0x18001ac8a  mov     ebx, 0C0000017h
0x18001ac8f  jmp     short loc_18001ACC4
0x18001ac91  lea     r8, [rbp+var_50]
0x18001ac95  mov     rdx, rdi
0x18001ac98  lea     rcx, [rbp+var_48]
0x18001ac9c  call    cs:__imp_FindNetbiosDomainName
0x18001aca2  mov     ebx, eax
0x18001aca4  test    eax, eax
0x18001aca6  js      short loc_18001ACB6
0x18001aca8  mov     rdx, rdi; SourceString
0x18001acab  mov     rcx, rsi; DestinationString
0x18001acae  call    cs:__imp_RtlInitUnicodeString
0x18001acb4  jmp     short loc_18001ACC4
0x18001acb6  mov     rcx, rdi; hMem
0x18001acb9  call    cs:__imp_LocalFree
0x18001acbf  mov     ebx, 0C00000DFh
0x18001acc4  mov     eax, ebx
0x18001acc6  mov     rcx, [rbp+var_8]
0x18001acca  xor     rcx, rsp; StackCookie
0x18001accd  call    __security_check_cookie
0x18001acd2  mov     rbx, [rsp+70h+arg_10]
0x18001acda  add     rsp, 70h
0x18001acde  pop     rdi
0x18001acdf  pop     rsi
0x18001ace0  pop     rbp
0x18001ace1  retn
```
