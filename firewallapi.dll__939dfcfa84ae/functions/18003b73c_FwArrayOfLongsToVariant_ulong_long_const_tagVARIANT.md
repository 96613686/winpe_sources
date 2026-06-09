# FwArrayOfLongsToVariant(ulong,long const *,tagVARIANT *)

- ea: `0x18003b73c`
- end: `0x18003b836`
- name: `?FwArrayOfLongsToVariant@@YAJKPEBJPEAUtagVARIANT@@@Z`
- size: `250`
- prototype: `int(unsigned int, const int *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b83c`

## callees

- `0x1800294b0`
- `0x18003b73c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003b76e`
- `OLEAUT32!__imp_VariantInit` at `0x18003b76e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003b79b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003b79b`
- `fwbase!FwReportReturnError` at `0x18003b7bd`
- `fwbase!FwReportReturnError` at `0x18003b7d2`
- `fwbase!FwReportReturnError` at `0x18003b7bd`
- `fwbase!FwReportReturnError` at `0x18003b7d2`

## pseudocode

```c
__int64 __fastcall FwArrayOfLongsToVariant(ULONG a1, const int *a2, struct tagVARIANT *a3)
{
  SAFEARRAY *v6; // rax
  LONGLONG v7; // rdx
  _WORD *pvData; // r10
  ULONG v10; // r9d
  __int64 v11; // r8
  __int64 v12; // rcx
  int v13; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-18h] BYREF

  rgsabound = 0;
  VariantInit(a3);
  if ( a1 )
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = a1;
    v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v7 = (LONGLONG)v6;
    if ( !v6 )
    {
      FwReportReturnError("FwArrayOfLongsToVariant", 2147942414LL);
      return FwReportReturnError("FwArrayOfLongsToVariant", 2147942414LL);
    }
    pvData = v6->pvData;
    v10 = 0;
    v11 = 0;
    do
    {
      v12 = 3 * v11;
      ++v10;
      pvData[4 * v12] = 3;
      v13 = a2[v11++];
      *(_DWORD *)&pvData[4 * v12 + 4] = v13;
    }
    while ( v10 < a1 );
    a3->vt = 8204;
    a3->llVal = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18003b73c  mov     [rsp+arg_0], rbx
0x18003b741  mov     [rsp+arg_8], rsi
0x18003b746  push    rdi
0x18003b747  sub     rsp, 30h
0x18003b74b  mov     rax, cs:__security_cookie
0x18003b752  xor     rax, rsp
0x18003b755  mov     [rsp+38h+var_10], rax
0x18003b75a  mov     edi, ecx
0x18003b75c  mov     qword ptr [rsp+38h+rgsabound.cElements], 0
0x18003b765  mov     rcx, r8; pvarg
0x18003b768  mov     rbx, r8
0x18003b76b  mov     rsi, rdx
0x18003b76e  call    cs:__imp_VariantInit
0x18003b775  nop     dword ptr [rax+rax+00h]
0x18003b77a  test    edi, edi
0x18003b77c  jz      loc_18003B816
0x18003b782  mov     ecx, 0Ch; vt
0x18003b787  mov     [rsp+38h+rgsabound.lLbound], 0
0x18003b78f  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x18003b794  mov     [rsp+38h+rgsabound.cElements], edi
0x18003b798  lea     edx, [rcx-0Bh]; cDims
0x18003b79b  call    cs:__imp_SafeArrayCreate
0x18003b7a2  nop     dword ptr [rax+rax+00h]
0x18003b7a7  mov     rdx, rax
0x18003b7aa  test    rax, rax
0x18003b7ad  jnz     short loc_18003B7E0
0x18003b7af  mov     ebx, 8007000Eh
0x18003b7b4  lea     rcx, aFwarrayoflongs; "FwArrayOfLongsToVariant"
0x18003b7bb  mov     edx, ebx
0x18003b7bd  call    cs:__imp_FwReportReturnError
0x18003b7c4  nop     dword ptr [rax+rax+00h]
0x18003b7c9  mov     edx, ebx
0x18003b7cb  lea     rcx, aFwarrayoflongs; "FwArrayOfLongsToVariant"
0x18003b7d2  call    cs:__imp_FwReportReturnError
0x18003b7d9  nop     dword ptr [rax+rax+00h]
0x18003b7de  jmp     short loc_18003B818
0x18003b7e0  mov     r10, [rax+10h]
0x18003b7e4  xor     r9d, r9d
0x18003b7e7  test    edi, edi
0x18003b7e9  jz      short loc_18003B80D
0x18003b7eb  xor     r8d, r8d
0x18003b7ee  lea     rcx, [r8+r8*2]
0x18003b7f2  inc     r9d
0x18003b7f5  mov     word ptr [r10+rcx*8], 3
0x18003b7fc  mov     eax, [rsi+r8*4]
0x18003b800  inc     r8
0x18003b803  mov     [r10+rcx*8+8], eax
0x18003b808  cmp     r9d, edi
0x18003b80b  jb      short loc_18003B7EE
0x18003b80d  mov     word ptr [rbx], 200Ch
0x18003b812  mov     [rbx+8], rdx
0x18003b816  xor     eax, eax
0x18003b818  mov     rcx, [rsp+38h+var_10]
0x18003b81d  xor     rcx, rsp; StackCookie
0x18003b820  call    __security_check_cookie
0x18003b825  mov     rbx, [rsp+38h+arg_0]
0x18003b82a  mov     rsi, [rsp+38h+arg_8]
0x18003b82f  add     rsp, 30h
0x18003b833  pop     rdi
0x18003b834  retn
```
