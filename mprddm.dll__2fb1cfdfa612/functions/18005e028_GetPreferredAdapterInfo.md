# GetPreferredAdapterInfo

- ea: `0x18005e028`
- end: `0x18005e33b`
- name: `GetPreferredAdapterInfo`
- size: `787`
- prototype: `__int64 __usercall@<rax>(unsigned int *@<rcx>, unsigned int *@<rdx>, unsigned int *@<r8>, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180056300`
- `0x18005cfc4`
- `0x18005d62c`
- `0x18005dbb0`

## callees

- `0x18005cd5c`
- `0x18005e028`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005e10f`
- `KERNEL32!LocalFree` at `0x18005e310`
- `KERNEL32!LocalFree` at `0x18005e10f`
- `KERNEL32!LocalFree` at `0x18005e310`
- `KERNEL32!CompareStringA` at `0x18005e264`
- `KERNEL32!CompareStringA` at `0x18005e264`
- `KERNEL32!GetLastError` at `0x18005e1f3`
- `KERNEL32!GetLastError` at `0x18005e1f3`
- `KERNEL32!LocalAlloc` at `0x18005e0d0`
- `KERNEL32!LocalAlloc` at `0x18005e0d0`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005e0fb`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005e143`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005e0fb`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005e143`

## pseudocode

```c
__int64 __fastcall GetPreferredAdapterInfo(
        unsigned int *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 *a6)
{
  unsigned int v9; // r14d
  __int64 v10; // rsi
  ULONG AdaptersAddresses; // edi
  __int64 v12; // rbx
  const wchar_t *v13; // rdx
  __int64 v14; // r14
  __int64 v15; // rax
  unsigned int *v17; // [rsp+30h] [rbp-D0h]
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v19; // [rsp+48h] [rbp-B8h]
  unsigned int *v20; // [rsp+50h] [rbp-B0h]
  unsigned int *v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  char v23[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v20 = a5;
  v19 = a6;
  v21 = a4;
  v9 = 0;
  v22 = 0;
  LODWORD(uBytes) = 0;
  v10 = -1;
  memset_0(v23, 0, sizeof(v23));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"GetPreferredAdapterInfo");
  while ( 1 )
  {
    AdaptersAddresses = GetAdaptersAddresses(2u, 0xC6u, 0, 0, (PULONG)&uBytes);
    if ( AdaptersAddresses != 111 )
    {
      if ( !(_QWORD)xmmword_1800C9740 )
      {
LABEL_11:
        v12 = 0;
        goto LABEL_12;
      }
      v13 = L"GetAdaptersAddresses call to query buffer size returns %d instead of ERROR_BUFFER_OVERFLOW";
LABEL_10:
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, v13, AdaptersAddresses);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v22);
      goto LABEL_11;
    }
    v10 = (__int64)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !v10 )
    {
      AdaptersAddresses = GetLastError();
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_11;
      v13 = L"Unable to allocate memory for the GetAdaptersAddresses buffer: %d";
      goto LABEL_10;
    }
    AdaptersAddresses = GetAdaptersAddresses(2u, 0xC6u, 0, (PIP_ADAPTER_ADDRESSES)v10, (PULONG)&uBytes);
    if ( AdaptersAddresses != 111 )
      break;
    LocalFree((HLOCAL)v10);
    v12 = 0;
    ++v9;
    LODWORD(uBytes) = 0;
    if ( v9 > 3 )
      goto LABEL_16;
    v10 = 0;
  }
  v12 = v10;
LABEL_16:
  v10 = v12;
LABEL_12:
  if ( AdaptersAddresses )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, L"GetAdaptersAddresses fails with %d\n", AdaptersAddresses);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v22);
    }
  }
  else
  {
    v14 = 0;
    while ( v12 )
    {
      if ( ((*(_DWORD *)(v12 + 268) - 1) & 0xFFFFFFFD) == 0 && *(_DWORD *)(v12 + 104) == 1 )
      {
        v15 = v12;
        if ( v14 )
          v15 = v14;
        v14 = v15;
        if ( !HIDWORD(qword_1800C98F0) || CompareStringA(0x7Fu, 1u, MultiByteStr, -1, *(PCNZCH *)(v12 + 16), -1) == 2 )
          goto LABEL_31;
      }
      v12 = *(_QWORD *)(v12 + 8);
    }
    if ( !HIDWORD(qword_1800C98F0) || !v14 )
    {
      AdaptersAddresses = 1168;
      goto LABEL_35;
    }
    v12 = v14;
LABEL_31:
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, L"Selecting %d as the preferred adapter", *(unsigned int *)(v12 + 4));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v22);
    }
    GetAdapterAddressInfo((struct _IP_ADAPTER_ADDRESSES_LH *)v12, a1, a2, a3, v21, v20, v17, v19);
  }
LABEL_35:
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    LocalFree((HLOCAL)v10);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x18005e028  push    rbp
0x18005e02a  push    rbx
0x18005e02b  push    rsi
0x18005e02c  push    rdi
0x18005e02d  push    r12
0x18005e02f  push    r13
0x18005e031  push    r14
0x18005e033  push    r15
0x18005e035  lea     rbp, [rsp-778h]
0x18005e03d  sub     rsp, 878h
0x18005e044  mov     rax, cs:__security_cookie
0x18005e04b  xor     rax, rsp
0x18005e04e  mov     [rbp+7B0h+var_50], rax
0x18005e055  mov     rax, [rbp+7B0h+arg_20]
0x18005e05c  mov     r13, r8
0x18005e05f  mov     [rsp+8B0h+var_860], rax
0x18005e064  mov     r12, rdx
0x18005e067  mov     rax, [rbp+7B0h+arg_28]
0x18005e06e  mov     r15, rcx
0x18005e071  mov     [rsp+8B0h+var_868], rax
0x18005e076  lea     rcx, [rsp+8B0h+var_84C]; void *
0x18005e07b  xor     eax, eax
0x18005e07d  mov     [rsp+8B0h+var_858], r9
0x18005e082  xor     r14d, r14d
0x18005e085  mov     [rsp+8B0h+var_850], eax
0x18005e089  xor     edx, edx; Val
0x18005e08b  mov     dword ptr [rsp+8B0h+uBytes], r14d
0x18005e090  mov     r8d, 7FCh; Size
0x18005e096  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005e09a  call    memset_0
0x18005e09f  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005e0a6  test    rdx, rdx
0x18005e0a9  jz      short loc_18005E12A
0x18005e0ab  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e0b2  lea     r8, aGetpreferredad; "GetPreferredAdapterInfo"
0x18005e0b9  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0c5  jmp     short loc_18005E12A
0x18005e0c7  mov     edx, dword ptr [rsp+8B0h+uBytes]; uBytes
0x18005e0cb  mov     ecx, 40h ; '@'; uFlags
0x18005e0d0  call    cs:__imp_LocalAlloc
0x18005e0d6  mov     rsi, rax
0x18005e0d9  test    rax, rax
0x18005e0dc  jz      loc_18005E1F3
0x18005e0e2  xor     r8d, r8d; Reserved
0x18005e0e5  lea     rax, [rsp+8B0h+uBytes]
0x18005e0ea  mov     r9, rsi; AdapterAddresses
0x18005e0ed  mov     [rsp+8B0h+SizePointer], rax; SizePointer
0x18005e0f2  mov     edx, 0C6h; Flags
0x18005e0f7  lea     ecx, [r8+2]; Family
0x18005e0fb  call    cs:__imp_GetAdaptersAddresses
0x18005e101  mov     edi, eax
0x18005e103  cmp     eax, 6Fh ; 'o'
0x18005e106  jnz     loc_18005E1EB
0x18005e10c  mov     rcx, rsi; hMem
0x18005e10f  call    cs:__imp_LocalFree
0x18005e115  xor     ebx, ebx
0x18005e117  inc     r14d
0x18005e11a  mov     dword ptr [rsp+8B0h+uBytes], ebx
0x18005e11e  cmp     r14d, 3
0x18005e122  ja      loc_18005E1EE
0x18005e128  xor     esi, esi
0x18005e12a  xor     r9d, r9d; AdapterAddresses
0x18005e12d  lea     rax, [rsp+8B0h+uBytes]
0x18005e132  xor     r8d, r8d; Reserved
0x18005e135  mov     [rsp+8B0h+SizePointer], rax; SizePointer
0x18005e13a  mov     edx, 0C6h; Flags
0x18005e13f  lea     ecx, [r9+2]; Family
0x18005e143  call    cs:__imp_GetAdaptersAddresses
0x18005e149  mov     edi, eax
0x18005e14b  cmp     eax, 6Fh ; 'o'
0x18005e14e  jz      loc_18005E0C7
0x18005e154  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005e15c  jz      short loc_18005E198
0x18005e15e  lea     rdx, aGetadaptersadd; "GetAdaptersAddresses call to query buff"...
0x18005e165  xor     eax, eax
0x18005e167  lea     rcx, [rsp+8B0h+var_850]
0x18005e16c  mov     r8d, edi
0x18005e16f  mov     word ptr [rsp+8B0h+var_850], ax
0x18005e174  call    FormatRRASErrorString
0x18005e179  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005e180  lea     r8, [rsp+8B0h+var_850]
0x18005e185  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e18c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e198  xor     ebx, ebx
0x18005e19a  test    edi, edi
0x18005e19c  jz      short loc_18005E211
0x18005e19e  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005e1a6  jz      loc_18005E303
0x18005e1ac  xor     eax, eax
0x18005e1ae  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses fails with %d\n"
0x18005e1b5  mov     r8d, edi
0x18005e1b8  mov     word ptr [rsp+8B0h+var_850], ax
0x18005e1bd  lea     rcx, [rsp+8B0h+var_850]
0x18005e1c2  call    FormatRRASErrorString
0x18005e1c7  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005e1ce  lea     r8, [rsp+8B0h+var_850]
0x18005e1d3  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e1da  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1e6  jmp     loc_18005E303
0x18005e1eb  mov     rbx, rsi
0x18005e1ee  mov     rsi, rbx
0x18005e1f1  jmp     short loc_18005E19A
0x18005e1f3  call    cs:__imp_GetLastError
0x18005e1f9  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005e201  mov     edi, eax
0x18005e203  jz      short loc_18005E198
0x18005e205  lea     rdx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x18005e20c  jmp     loc_18005E165
0x18005e211  xor     r14d, r14d
0x18005e214  jmp     short loc_18005E273
0x18005e216  mov     eax, [rbx+10Ch]
0x18005e21c  dec     eax
0x18005e21e  test    eax, 0FFFFFFFDh
0x18005e223  jnz     short loc_18005E26F
0x18005e225  cmp     dword ptr [rbx+68h], 1
0x18005e229  jnz     short loc_18005E26F
0x18005e22b  test    r14, r14
0x18005e22e  mov     rax, rbx
0x18005e231  cmovnz  rax, r14
0x18005e235  cmp     dword ptr cs:qword_1800C98F0+4, 0
0x18005e23c  mov     r14, rax
0x18005e23f  jz      short loc_18005E288
0x18005e241  mov     rax, [rbx+10h]
0x18005e245  lea     r8, MultiByteStr; lpString1
0x18005e24c  or      r9d, 0FFFFFFFFh; cchCount1
0x18005e250  mov     [rsp+8B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005e258  mov     [rsp+8B0h+SizePointer], rax; lpString2
0x18005e25d  lea     edx, [r9+2]; dwCmpFlags
0x18005e261  lea     ecx, [rdx+7Eh]; Locale
0x18005e264  call    cs:__imp_CompareStringA
0x18005e26a  cmp     eax, 2
0x18005e26d  jz      short loc_18005E288
0x18005e26f  mov     rbx, [rbx+8]
0x18005e273  test    rbx, rbx
0x18005e276  jnz     short loc_18005E216
0x18005e278  cmp     dword ptr cs:qword_1800C98F0+4, ebx
0x18005e27e  jz      short loc_18005E2FE
0x18005e280  test    r14, r14
0x18005e283  jz      short loc_18005E2FE
0x18005e285  mov     rbx, r14
0x18005e288  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005e290  jz      short loc_18005E2CD
0x18005e292  xor     eax, eax
0x18005e294  lea     rdx, aSelectingDAsTh; "Selecting %d as the preferred adapter"
0x18005e29b  mov     word ptr [rsp+8B0h+var_850], ax
0x18005e2a0  lea     rcx, [rsp+8B0h+var_850]
0x18005e2a5  mov     r8d, [rbx+4]
0x18005e2a9  call    FormatRRASErrorString
0x18005e2ae  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005e2b5  lea     r8, [rsp+8B0h+var_850]
0x18005e2ba  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e2c1  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2cd  mov     rax, [rsp+8B0h+var_868]
0x18005e2d2  mov     r9, r13; unsigned int *
0x18005e2d5  mov     [rsp+8B0h+var_878], rax; unsigned __int8 *
0x18005e2da  mov     r8, r12; unsigned int *
0x18005e2dd  mov     rax, [rsp+8B0h+var_860]
0x18005e2e2  mov     rdx, r15; unsigned int *
0x18005e2e5  mov     qword ptr [rsp+8B0h+cchCount2], rax; unsigned int *
0x18005e2ea  mov     rcx, rbx; struct _IP_ADAPTER_ADDRESSES_LH *
0x18005e2ed  mov     rax, [rsp+8B0h+var_858]
0x18005e2f2  mov     [rsp+8B0h+SizePointer], rax; unsigned int *
0x18005e2f7  call    ?GetAdapterAddressInfo@@YAKPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAK11111PEAE@Z; GetAdapterAddressInfo(_IP_ADAPTER_ADDRESSES_LH *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,uchar *)
0x18005e2fc  jmp     short loc_18005E303
0x18005e2fe  mov     edi, 490h
0x18005e303  lea     rax, [rsi-1]
0x18005e307  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005e30b  ja      short loc_18005E316
0x18005e30d  mov     rcx, rsi; hMem
0x18005e310  call    cs:__imp_LocalFree
0x18005e316  mov     eax, edi
0x18005e318  mov     rcx, [rbp+7B0h+var_50]
0x18005e31f  xor     rcx, rsp; StackCookie
0x18005e322  call    __security_check_cookie
0x18005e327  add     rsp, 878h
0x18005e32e  pop     r15
0x18005e330  pop     r14
0x18005e332  pop     r13
0x18005e334  pop     r12
0x18005e336  pop     rdi
0x18005e337  pop     rsi
0x18005e338  pop     rbx
0x18005e339  pop     rbp
0x18005e33a  retn
```
