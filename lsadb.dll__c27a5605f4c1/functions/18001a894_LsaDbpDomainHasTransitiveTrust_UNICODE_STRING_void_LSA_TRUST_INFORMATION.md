# LsaDbpDomainHasTransitiveTrust(_UNICODE_STRING *,void *,_LSA_TRUST_INFORMATION *)

- ea: `0x18001a894`
- end: `0x18001a9f3`
- name: `?LsaDbpDomainHasTransitiveTrust@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_TRUST_INFORMATION@@@Z`
- size: `351`
- prototype: `int(struct _UNICODE_STRING *, void *, struct _LSA_TRUST_INFORMATION *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c938`
- `0x18001de20`

## callees

- `0x18001a894`
- `0x18001abec`
- `0x18001ace8`
- `0x18001ae84`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a96f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a994`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a96f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a994`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a9a2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a9a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a8d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a97c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a8d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a97c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a94d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a94d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9e2`
- `ntdll!RtlInitUnicodeString` at `0x18001a8be`
- `ntdll!RtlInitUnicodeString` at `0x18001a9c4`
- `ntdll!RtlInitUnicodeString` at `0x18001a8be`
- `ntdll!RtlInitUnicodeString` at `0x18001a9c4`

## pseudocode

```c
__int64 __fastcall LsaDbpDomainHasTransitiveTrust(
        struct _UNICODE_STRING *a1,
        void *a2,
        struct _LSA_TRUST_INFORMATION *a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi
  int DomainSidByNetbiosName; // ebx
  HLOCAL v9; // rdi
  DWORD LengthSid; // eax
  DWORD v11; // eax
  struct _UNICODE_STRING v12; // xmm0
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF

  hMem = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( a1 )
  {
    v6 = (unsigned __int16 *)LocalAlloc(0x40u, a1->Length + 2LL);
    v7 = v6;
    if ( !v6 )
    {
      DomainSidByNetbiosName = -1073741801;
      goto LABEL_18;
    }
    memcpy_0(v6, a1->Buffer, a1->Length);
    v7[(unsigned __int64)a1->Length >> 1] = 0;
    DomainSidByNetbiosName = LsaDbpGetDomainSidByNetbiosName(v7, &hMem);
    if ( DomainSidByNetbiosName == -1073741601 )
      DomainSidByNetbiosName = LsaDbpGetDomainSidByDnsName(v7, &hMem);
    v9 = hMem;
    if ( DomainSidByNetbiosName >= 0 )
      DomainSidByNetbiosName = LsaDbpGetDomainNameBySid(hMem, &DestinationString);
    LocalFree(v7);
    if ( DomainSidByNetbiosName < 0 )
      goto LABEL_16;
    goto LABEL_14;
  }
  DomainSidByNetbiosName = LsaDbpGetDomainNameBySid(a2, &DestinationString);
  if ( DomainSidByNetbiosName < 0 )
    goto LABEL_18;
  LengthSid = GetLengthSid(a2);
  v9 = LocalAlloc(0x40u, LengthSid);
  if ( v9 )
  {
    v11 = GetLengthSid(a2);
    CopySid(v11, v9, a2);
LABEL_14:
    if ( a3 )
    {
      v12 = DestinationString;
      a3->Sid = v9;
      v9 = 0;
      a3->Name = (LSA_UNICODE_STRING)v12;
      RtlInitUnicodeString(&DestinationString, 0);
    }
    goto LABEL_16;
  }
  DomainSidByNetbiosName = -1073741801;
LABEL_16:
  if ( v9 )
    LocalFree(v9);
LABEL_18:
  if ( DestinationString.Buffer )
    LocalFree(DestinationString.Buffer);
  return (unsigned int)DomainSidByNetbiosName;
}

```

## disassembly

```asm
0x18001a894  push    rbx
0x18001a896  push    rbp
0x18001a897  push    rsi
0x18001a898  push    rdi
0x18001a899  sub     rsp, 38h
0x18001a89d  mov     rsi, rdx
0x18001a8a0  mov     [rsp+58h+hMem], 0
0x18001a8a9  mov     rbx, rcx
0x18001a8ac  xorps   xmm0, xmm0
0x18001a8af  xor     edx, edx; SourceString
0x18001a8b1  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18001a8b6  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18001a8bb  mov     rbp, r8
0x18001a8be  call    cs:__imp_RtlInitUnicodeString
0x18001a8c4  test    rbx, rbx
0x18001a8c7  jz      loc_18001A959
0x18001a8cd  movzx   edx, word ptr [rbx]
0x18001a8d0  mov     ecx, 40h ; '@'; uFlags
0x18001a8d5  add     rdx, 2; uBytes
0x18001a8d9  call    cs:__imp_LocalAlloc
0x18001a8df  mov     rsi, rax
0x18001a8e2  test    rax, rax
0x18001a8e5  jnz     short loc_18001A8F1
0x18001a8e7  mov     ebx, 0C0000017h
0x18001a8ec  jmp     loc_18001A9D8
0x18001a8f1  movzx   r8d, word ptr [rbx]; Size
0x18001a8f5  mov     rcx, rsi; void *
0x18001a8f8  mov     rdx, [rbx+8]; Src
0x18001a8fc  call    memcpy_0
0x18001a901  movzx   ecx, word ptr [rbx]
0x18001a904  lea     rdx, [rsp+58h+hMem]; void **
0x18001a909  shr     rcx, 1
0x18001a90c  xor     eax, eax
0x18001a90e  mov     [rsi+rcx*2], ax
0x18001a912  mov     rcx, rsi; unsigned __int16 *
0x18001a915  call    ?LsaDbpGetDomainSidByNetbiosName@@YAJPEBGPEAPEAX@Z; LsaDbpGetDomainSidByNetbiosName(ushort const *,void * *)
0x18001a91a  mov     ebx, eax
0x18001a91c  cmp     eax, 0C00000DFh
0x18001a921  jnz     short loc_18001A932
0x18001a923  lea     rdx, [rsp+58h+hMem]; void **
0x18001a928  mov     rcx, rsi; unsigned __int16 *
0x18001a92b  call    ?LsaDbpGetDomainSidByDnsName@@YAJPEBGPEAPEAX@Z; LsaDbpGetDomainSidByDnsName(ushort const *,void * *)
0x18001a930  mov     ebx, eax
0x18001a932  mov     rdi, [rsp+58h+hMem]
0x18001a937  test    ebx, ebx
0x18001a939  js      short loc_18001A94A
0x18001a93b  lea     rdx, [rsp+58h+DestinationString]; DestinationString
0x18001a940  mov     rcx, rdi; Src
0x18001a943  call    ?LsaDbpGetDomainNameBySid@@YAJPEAXPEAU_UNICODE_STRING@@@Z; LsaDbpGetDomainNameBySid(void *,_UNICODE_STRING *)
0x18001a948  mov     ebx, eax
0x18001a94a  mov     rcx, rsi; hMem
0x18001a94d  call    cs:__imp_LocalFree
0x18001a953  test    ebx, ebx
0x18001a955  js      short loc_18001A9CA
0x18001a957  jmp     short loc_18001A9A8
0x18001a959  lea     rdx, [rsp+58h+DestinationString]; DestinationString
0x18001a95e  mov     rcx, rsi; Src
0x18001a961  call    ?LsaDbpGetDomainNameBySid@@YAJPEAXPEAU_UNICODE_STRING@@@Z; LsaDbpGetDomainNameBySid(void *,_UNICODE_STRING *)
0x18001a966  mov     ebx, eax
0x18001a968  test    eax, eax
0x18001a96a  js      short loc_18001A9D8
0x18001a96c  mov     rcx, rsi; pSid
0x18001a96f  call    cs:__imp_GetLengthSid
0x18001a975  mov     edx, eax; uBytes
0x18001a977  mov     ecx, 40h ; '@'; uFlags
0x18001a97c  call    cs:__imp_LocalAlloc
0x18001a982  mov     rdi, rax
0x18001a985  test    rax, rax
0x18001a988  jnz     short loc_18001A991
0x18001a98a  mov     ebx, 0C0000017h
0x18001a98f  jmp     short loc_18001A9CA
0x18001a991  mov     rcx, rsi; pSid
0x18001a994  call    cs:__imp_GetLengthSid
0x18001a99a  mov     r8, rsi; pSourceSid
0x18001a99d  mov     rdx, rdi; pDestinationSid
0x18001a9a0  mov     ecx, eax; nDestinationSidLength
0x18001a9a2  call    cs:__imp_CopySid
0x18001a9a8  test    rbp, rbp
0x18001a9ab  jz      short loc_18001A9CA
0x18001a9ad  movups  xmm0, xmmword ptr [rsp+58h+DestinationString.Length]
0x18001a9b2  mov     [rbp+10h], rdi
0x18001a9b6  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18001a9bb  xor     edi, edi
0x18001a9bd  xor     edx, edx; SourceString
0x18001a9bf  movdqu  xmmword ptr [rbp+0], xmm0
0x18001a9c4  call    cs:__imp_RtlInitUnicodeString
0x18001a9ca  test    rdi, rdi
0x18001a9cd  jz      short loc_18001A9D8
0x18001a9cf  mov     rcx, rdi; hMem
0x18001a9d2  call    cs:__imp_LocalFree
0x18001a9d8  mov     rcx, [rsp+58h+DestinationString.Buffer]; hMem
0x18001a9dd  test    rcx, rcx
0x18001a9e0  jz      short loc_18001A9E8
0x18001a9e2  call    cs:__imp_LocalFree
0x18001a9e8  mov     eax, ebx
0x18001a9ea  add     rsp, 38h
0x18001a9ee  pop     rdi
0x18001a9ef  pop     rsi
0x18001a9f0  pop     rbp
0x18001a9f1  pop     rbx
0x18001a9f2  retn
```
