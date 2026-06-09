# DsrSidInit(tagVARIANT *,uchar * *)

- ea: `0x18002bae0`
- end: `0x18002bca1`
- name: `?DsrSidInit@@YAKPEAUtagVARIANT@@PEAPEAE@Z`
- size: `449`
- prototype: `HRESULT __fastcall(struct tagVARIANT *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c064`

## callees

- `0x180009350`
- `0x18002bae0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002bbe0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002bbe0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002bc42`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002bc42`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002bc5c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002bc5c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002bb4d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002bb4d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002bb88`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002bb88`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002bb61`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002bb61`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002bb38`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002bc20`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002bb38`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002bc20`

## string_xrefs

- `0x18002bb09`: `DsrSidInit: entered.`
- `0x18002bb6b`: `DsrSidInit: %x unable to get lbound`
- `0x18002bb92`: `DsrSidInit: %x unable to get ubound`
- `0x18002bb9e`: `DsrSidInit: Dim=%d, Low=%d, High=%d`
- `0x18002bc7d`: `DsrSidInit: %x Integer underflow`
- `0x18002bbcd`: `DsrSidInit: %x Integer overflow`
- `0x18002bbee`: `DsrSidInit: Unable to alloc`
- `0x18002bc2e`: `DsrSidInit: copied %d bytes`
- `0x18002bc48`: `DsrSidInit: Sid Length: %d`
- `0x18002bc6b`: `DsrSidInit: Sid SA Count: %d`

## pseudocode

```c
HRESULT __fastcall DsrSidInit(struct tagVARIANT *a1, unsigned __int8 **a2)
{
  SAFEARRAY *parray; // rbx
  HRESULT result; // eax
  SAFEARRAY *v5; // rdi
  UINT Dim; // ebx
  HRESULT LBound; // eax
  const char *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned __int8 *v12; // rbx
  int v13; // eax
  unsigned __int8 *i; // r8
  DWORD LengthSid; // eax
  PUCHAR SidSubAuthorityCount; // rax
  __int128 pv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  LONG rgIndices; // [rsp+70h] [rbp+20h] BYREF
  LONG plLbound; // [rsp+80h] [rbp+30h] BYREF
  LONG plUbound; // [rsp+88h] [rbp+38h] BYREF

  parray = a1->parray;
  plLbound = 0;
  plUbound = 0;
  v18 = 0;
  rgIndices = 0;
  pv = 0;
  DsrTraceEx(0, "DsrSidInit: entered.");
  rgIndices = 0;
  result = SafeArrayGetElement(parray, &rgIndices, &pv);
  if ( result >= 0 )
  {
    v5 = (SAFEARRAY *)*((_QWORD *)&pv + 1);
    Dim = SafeArrayGetDim(*((SAFEARRAY **)&pv + 1));
    LBound = SafeArrayGetLBound(v5, 1u, &plLbound);
    if ( LBound < 0 )
    {
      v8 = "DsrSidInit: %x unable to get lbound";
LABEL_4:
      v9 = (unsigned int)LBound;
      v10 = (unsigned int)LBound;
      return DsrTraceEx(v10, v8, v9);
    }
    LBound = SafeArrayGetUBound(v5, 1u, &plUbound);
    if ( LBound < 0 )
    {
      v8 = "DsrSidInit: %x unable to get ubound";
      goto LABEL_4;
    }
    DsrTraceEx(0, "DsrSidInit: Dim=%d, Low=%d, High=%d", Dim, plLbound, plUbound);
    if ( plUbound < (unsigned int)plLbound )
    {
      v8 = "DsrSidInit: %x Integer underflow";
      goto LABEL_19;
    }
    v11 = plUbound - plLbound;
    if ( v11 + 2 < v11 )
    {
      v8 = "DsrSidInit: %x Integer overflow";
LABEL_19:
      v10 = 2147942934LL;
      v9 = 2147942934LL;
      return DsrTraceEx(v10, v8, v9);
    }
    v12 = (unsigned __int8 *)GlobalAlloc(0x40u, v11 + 2);
    if ( v12 )
    {
      v13 = plLbound;
      for ( i = &v12[plLbound]; ; i = &v12[rgIndices + 1] )
      {
        rgIndices = v13;
        if ( SafeArrayGetElement(v5, &rgIndices, i) < 0 )
          break;
        v13 = rgIndices + 1;
      }
      DsrTraceEx(0, "DsrSidInit: copied %d bytes", rgIndices);
      *a2 = v12;
      LengthSid = GetLengthSid(v12);
      DsrTraceEx(0, "DsrSidInit: Sid Length: %d", LengthSid);
      SidSubAuthorityCount = GetSidSubAuthorityCount(v12);
      if ( SidSubAuthorityCount )
        DsrTraceEx(0, "DsrSidInit: Sid SA Count: %d", *SidSubAuthorityCount);
      return 0;
    }
    else
    {
      return DsrTraceEx(8, "DsrSidInit: Unable to alloc");
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002bae0  mov     [rsp-18h+arg_8], rbx
0x18002bae5  push    rbp
0x18002bae6  push    rsi
0x18002bae7  push    rdi
0x18002bae8  mov     rbp, rsp
0x18002baeb  sub     rsp, 50h
0x18002baef  mov     rbx, [rcx+8]
0x18002baf3  mov     rsi, rdx
0x18002baf6  xorps   xmm0, xmm0
0x18002baf9  mov     [rbp+plLbound], 0
0x18002bb00  xor     eax, eax
0x18002bb02  mov     [rbp+plUbound], 0
0x18002bb09  lea     rdx, aDsrsidinitEnte; "DsrSidInit: entered."
0x18002bb10  mov     [rbp+var_10], rax
0x18002bb14  xor     ecx, ecx
0x18002bb16  mov     [rbp+rgIndices], 0
0x18002bb1d  movups  [rbp+pv], xmm0
0x18002bb21  call    DsrTraceEx
0x18002bb26  lea     r8, [rbp+pv]; pv
0x18002bb2a  mov     [rbp+rgIndices], 0
0x18002bb31  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002bb35  mov     rcx, rbx; psa
0x18002bb38  call    cs:__imp_SafeArrayGetElement
0x18002bb3e  test    eax, eax
0x18002bb40  js      loc_18002BC94
0x18002bb46  mov     rdi, qword ptr [rbp+pv+8]
0x18002bb4a  mov     rcx, rdi; psa
0x18002bb4d  call    cs:__imp_SafeArrayGetDim
0x18002bb53  lea     r8, [rbp+plLbound]; plLbound
0x18002bb57  mov     edx, 1; nDim
0x18002bb5c  mov     rcx, rdi; psa
0x18002bb5f  mov     ebx, eax
0x18002bb61  call    cs:__imp_SafeArrayGetLBound
0x18002bb67  test    eax, eax
0x18002bb69  jns     short loc_18002BB7C
0x18002bb6b  lea     rdx, aDsrsidinitXUna; "DsrSidInit: %x unable to get lbound"
0x18002bb72  mov     r8d, eax
0x18002bb75  mov     ecx, eax
0x18002bb77  jmp     loc_18002BC8F
0x18002bb7c  lea     r8, [rbp+plUbound]; plUbound
0x18002bb80  mov     edx, 1; nDim
0x18002bb85  mov     rcx, rdi; psa
0x18002bb88  call    cs:__imp_SafeArrayGetUBound
0x18002bb8e  test    eax, eax
0x18002bb90  jns     short loc_18002BB9B
0x18002bb92  lea     rdx, aDsrsidinitXUna_0; "DsrSidInit: %x unable to get ubound"
0x18002bb99  jmp     short loc_18002BB72
0x18002bb9b  mov     eax, [rbp+plUbound]
0x18002bb9e  lea     rdx, aDsrsidinitDimD; "DsrSidInit: Dim=%d, Low=%d, High=%d"
0x18002bba5  mov     r9d, [rbp+plLbound]
0x18002bba9  mov     r8d, ebx
0x18002bbac  xor     ecx, ecx
0x18002bbae  mov     [rsp+50h+var_30], eax
0x18002bbb2  call    DsrTraceEx
0x18002bbb7  mov     eax, [rbp+plUbound]
0x18002bbba  cmp     eax, [rbp+plLbound]
0x18002bbbd  jb      loc_18002BC7D
0x18002bbc3  sub     eax, [rbp+plLbound]
0x18002bbc6  lea     ecx, [rax+2]
0x18002bbc9  cmp     ecx, eax
0x18002bbcb  jnb     short loc_18002BBD9
0x18002bbcd  lea     rdx, aDsrsidinitXInt_0; "DsrSidInit: %x Integer overflow"
0x18002bbd4  jmp     loc_18002BC84
0x18002bbd9  mov     edx, ecx; dwBytes
0x18002bbdb  mov     ecx, 40h ; '@'; uFlags
0x18002bbe0  call    cs:__imp_GlobalAlloc
0x18002bbe6  mov     rbx, rax
0x18002bbe9  test    rax, rax
0x18002bbec  jnz     short loc_18002BC02
0x18002bbee  lea     rdx, aDsrsidinitUnab; "DsrSidInit: Unable to alloc"
0x18002bbf5  lea     ecx, [rax+8]
0x18002bbf8  call    DsrTraceEx
0x18002bbfd  jmp     loc_18002BC94
0x18002bc02  mov     eax, [rbp+plLbound]
0x18002bc05  lea     r8, [rbx+rax]
0x18002bc09  jmp     short loc_18002BC16
0x18002bc0b  mov     eax, [rbp+rgIndices]
0x18002bc0e  inc     eax
0x18002bc10  mov     r8d, eax
0x18002bc13  add     r8, rbx; pv
0x18002bc16  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002bc1a  mov     [rbp+rgIndices], eax
0x18002bc1d  mov     rcx, rdi; psa
0x18002bc20  call    cs:__imp_SafeArrayGetElement
0x18002bc26  test    eax, eax
0x18002bc28  jns     short loc_18002BC0B
0x18002bc2a  mov     r8d, [rbp+rgIndices]
0x18002bc2e  lea     rdx, aDsrsidinitCopi; "DsrSidInit: copied %d bytes"
0x18002bc35  xor     ecx, ecx
0x18002bc37  call    DsrTraceEx
0x18002bc3c  mov     rcx, rbx; pSid
0x18002bc3f  mov     [rsi], rbx
0x18002bc42  call    cs:__imp_GetLengthSid
0x18002bc48  lea     rdx, aDsrsidinitSidL; "DsrSidInit: Sid Length: %d"
0x18002bc4f  xor     ecx, ecx
0x18002bc51  mov     r8d, eax
0x18002bc54  call    DsrTraceEx
0x18002bc59  mov     rcx, rbx; pSid
0x18002bc5c  call    cs:__imp_GetSidSubAuthorityCount
0x18002bc62  test    rax, rax
0x18002bc65  jz      short loc_18002BC79
0x18002bc67  movzx   r8d, byte ptr [rax]
0x18002bc6b  lea     rdx, aDsrsidinitSidS; "DsrSidInit: Sid SA Count: %d"
0x18002bc72  xor     ecx, ecx
0x18002bc74  call    DsrTraceEx
0x18002bc79  xor     eax, eax
0x18002bc7b  jmp     short loc_18002BC94
0x18002bc7d  lea     rdx, aDsrsidinitXInt; "DsrSidInit: %x Integer underflow"
0x18002bc84  mov     ecx, 80070216h
0x18002bc89  mov     r8d, 80070216h
0x18002bc8f  call    DsrTraceEx
0x18002bc94  mov     rbx, [rsp+50h+arg_8]
0x18002bc99  add     rsp, 50h
0x18002bc9d  pop     rdi
0x18002bc9e  pop     rsi
0x18002bc9f  pop     rbp
0x18002bca0  retn
```
