# RasTcpSetProxyArp

- ea: `0x1800689f0`
- end: `0x180068dd9`
- name: `RasTcpSetProxyArp`
- size: `1001`
- prototype: `__int64 __fastcall(DWORD dwAddress)`
- caller_count: `8`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004f4e4`
- `0x180053080`
- `0x180053230`
- `0x180053e5c`
- `0x1800564e0`
- `0x180056f10`
- `0x18005cfc4`
- `0x18005d504`

## callees

- `0x1800682f8`
- `0x1800689f0`
- `0x180069984`
- `0x180071cec`
- `0x1800759b8`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180068b5b`
- `KERNEL32!GetProcessHeap` at `0x180068b5b`
- `KERNEL32!GetLastError` at `0x180068b6d`
- `KERNEL32!GetLastError` at `0x180068b6d`
- `KERNEL32!HeapFree` at `0x180068da9`
- `KERNEL32!HeapFree` at `0x180068da9`
- `IPHLPAPI!CreateProxyArpEntry` at `0x180068cdc`
- `IPHLPAPI!CreateProxyArpEntry` at `0x180068cdc`
- `IPHLPAPI!DeleteProxyArpEntry` at `0x180068d0b`
- `IPHLPAPI!DeleteProxyArpEntry` at `0x180068d0b`

## string_xrefs

- `0x180068cf9`: `CreateProxyArpEntry: ifIndex=%d, 0x%x`
- `0x180068d02`: `CreateProxyArpEntry: ifIndex=%d, 0x%x`
- `0x180068d24`: `DeleteProxyArpEntry: ifIndex=%d, 0x%x`
- `0x180068d7f`: `DeleteProxyArpEntry: ifIndex=%d, 0x%x`

## pseudocode

```c
unsigned int __fastcall RasTcpSetProxyArp(DWORD dwAddress, int a2, int a3, NET_IF_COMPARTMENT_ID a4)
{
  __int64 v8; // rax
  unsigned int result; // eax
  const char *v10; // r9
  HANDLE ProcessHeap; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  void *v14; // r14
  _DWORD *v15; // rbx
  __int64 v16; // rsi
  int v17; // edx
  DWORD v18; // r8d
  const wchar_t *v19; // rdx
  const CHAR *v20; // rcx
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v22[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+68h] [rbp-98h] BYREF
  __int128 v24; // [rsp+6Ch] [rbp-94h]
  __int128 v25; // [rsp+7Ch] [rbp-84h]
  int v26; // [rsp+8Ch] [rbp-74h]
  int v27; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  lpMem = 0;
  v27 = 0;
  memset(v22, 0, sizeof(v22));
  memset_0(v28, 0, sizeof(v28));
  v23 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  if ( unk_1800CA080
    || __PAIR128__(xmmword_1800CA088, 0) != *((unsigned __int64 *)&xmmword_1800CA088 + 1)
    || (v8 = unk_1800CA098) != 0 && a4 != 1 )
  {
    result = NsiGetRoutingDomainIdForCompartment(a4, v22);
    if ( result )
      return result;
    v8 = unk_1800CA098;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      v10 = "TRUE";
      LOWORD(v27) = 0;
      LOWORD(v23) = 0;
      if ( !a2 )
        v10 = "FALSE";
      FormatRRASErrorString(&v27, L"RasTcpSetProxyArp(IP Addr: 0x%x, fAddAddress: %hs)", dwAddress, v10);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800CA098,
        &v27,
        v22,
        0,
        &v23);
    }
  }
  else
  {
    TraceHlp("RasTcpSetProxyArp(IP Addr: 0x%x, fAddAddress: %hs)");
  }
  ProcessHeap = GetProcessHeap();
  v14 = ProcessHeap;
  if ( !ProcessHeap )
  {
    result = GetLastError();
    if ( !gIsIphlpEtwTracingAvailable )
      return TraceHlp("GetProcessHeap failed and returned %d");
    if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
    {
      LOWORD(v27) = 0;
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v27, L"GetProcessHeap failed and returned %d", result);
      return ((__int64 (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
               gIphlpEtwContext,
               *((_QWORD *)&xmmword_1800CA088 + 1),
               &v27,
               v22,
               0,
               &v23);
    }
    return result;
  }
  result = AllocateAndGetIpAddrTable(&lpMem, v12, ProcessHeap, v13, a4);
  v15 = lpMem;
  if ( result )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
      {
        LOWORD(v27) = 0;
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v27, L"AllocateAndGetIpAddrTable failed and returned %d", result);
        result = ((__int64 (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
                   gIphlpEtwContext,
                   *((_QWORD *)&xmmword_1800CA088 + 1),
                   &v27,
                   v22,
                   0,
                   &v23);
      }
    }
    else
    {
      result = TraceHlp("AllocateAndGetIpAddrTable failed and returned %d");
    }
    goto LABEL_39;
  }
  v16 = 0;
  if ( *(_DWORD *)lpMem )
  {
    do
    {
      v17 = v15[6 * v16 + 1];
      result = v17 - 1;
      if ( (unsigned int)(v17 - 1) > 0xFFFFFFFD )
        goto LABEL_38;
      if ( a3 == v17 )
        goto LABEL_38;
      result = v17 & v15[6 * v16 + 3];
      if ( (dwAddress & v15[6 * v16 + 3]) != result )
        goto LABEL_38;
      v18 = v15[6 * v16 + 2];
      if ( a2 )
      {
        result = CreateProxyArpEntry(dwAddress, 0xFFFFFFFF, v18);
        if ( !gIsIphlpEtwTracingAvailable )
        {
          v20 = "CreateProxyArpEntry: ifIndex=%d, 0x%x";
LABEL_37:
          result = TraceHlp(v20);
          goto LABEL_38;
        }
        if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
        {
          v19 = L"CreateProxyArpEntry: ifIndex=%d, 0x%x";
LABEL_35:
          LOWORD(v27) = 0;
          LOWORD(v23) = 0;
          FormatRRASErrorString(&v27, v19, (unsigned int)v15[6 * v16 + 2], result);
          result = ((__int64 (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
                     gIphlpEtwContext,
                     *((_QWORD *)&xmmword_1800CA088 + 1),
                     &v27,
                     v22,
                     0,
                     &v23);
        }
      }
      else
      {
        result = DeleteProxyArpEntry(dwAddress, 0xFFFFFFFF, v18);
        if ( !gIsIphlpEtwTracingAvailable )
        {
          v20 = "DeleteProxyArpEntry: ifIndex=%d, 0x%x";
          goto LABEL_37;
        }
        if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
        {
          v19 = L"DeleteProxyArpEntry: ifIndex=%d, 0x%x";
          goto LABEL_35;
        }
      }
LABEL_38:
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < *v15 );
  }
LABEL_39:
  if ( v15 )
    return HeapFree(v14, 0, v15);
  return result;
}

```

## disassembly

```asm
0x1800689f0  mov     [rsp-8+arg_8], rbx
0x1800689f5  push    rbp
0x1800689f6  push    rsi
0x1800689f7  push    rdi
0x1800689f8  push    r12
0x1800689fa  push    r13
0x1800689fc  push    r14
0x1800689fe  push    r15
0x180068a00  lea     rbp, [rsp-7A0h]
0x180068a08  sub     rsp, 8A0h
0x180068a0f  mov     rax, cs:__security_cookie
0x180068a16  xor     rax, rsp
0x180068a19  mov     [rbp+7D0h+var_40], rax
0x180068a20  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180068a27  mov     r13d, r8d
0x180068a2a  mov     [rsp+8D0h+lpMem], 0
0x180068a33  mov     r12d, edx
0x180068a36  mov     r15d, ecx
0x180068a39  xor     eax, eax
0x180068a3b  lea     rcx, [rbp+7D0h+var_83C]; void *
0x180068a3f  xor     edx, edx; Val
0x180068a41  mov     [rbp+7D0h+var_840], eax
0x180068a44  mov     r8d, 7FCh; Size
0x180068a4a  mov     ebx, r9d
0x180068a4d  movdqu  [rsp+8D0h+var_888], xmm0
0x180068a53  call    memset_0
0x180068a58  xor     eax, eax
0x180068a5a  xorps   xmm0, xmm0
0x180068a5d  cmp     qword ptr cs:unk_1800CA080, rax
0x180068a64  mov     [rsp+8D0h+var_868], eax
0x180068a68  movups  [rsp+8D0h+var_864], xmm0
0x180068a6d  mov     [rbp+7D0h+var_844], eax
0x180068a70  movups  [rsp+8D0h+var_854], xmm0
0x180068a75  movups  [rsp+8D0h+var_878], xmm0
0x180068a7a  jnz     short loc_180068A9F
0x180068a7c  cmp     qword ptr cs:xmmword_1800CA088, rax
0x180068a83  jnz     short loc_180068A9F
0x180068a85  cmp     qword ptr cs:xmmword_1800CA088+8, rax
0x180068a8c  jnz     short loc_180068A9F
0x180068a8e  mov     rax, qword ptr cs:unk_1800CA098
0x180068a95  test    rax, rax
0x180068a98  jz      short loc_180068ABA
0x180068a9a  cmp     ebx, 1
0x180068a9d  jz      short loc_180068ABA
0x180068a9f  lea     rdx, [rsp+8D0h+var_888]
0x180068aa4  mov     ecx, ebx
0x180068aa6  call    NsiGetRoutingDomainIdForCompartment
0x180068aab  test    eax, eax
0x180068aad  jnz     loc_180068DAF
0x180068ab3  mov     rax, qword ptr cs:unk_1800CA098
0x180068aba  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180068ac1  jz      short loc_180068B37
0x180068ac3  test    rax, rax
0x180068ac6  jz      loc_180068B5B
0x180068acc  xor     eax, eax
0x180068ace  lea     r9, aTrue; "TRUE"
0x180068ad5  mov     word ptr [rbp+7D0h+var_840], ax
0x180068ad9  lea     rdx, aRastcpsetproxy; "RasTcpSetProxyArp(IP Addr: 0x%x, fAddAd"...
0x180068ae0  mov     word ptr [rsp+8D0h+var_868], ax
0x180068ae5  lea     rcx, [rbp+7D0h+var_840]
0x180068ae9  lea     rax, aFalse; "FALSE"
0x180068af0  test    r12d, r12d
0x180068af3  mov     r8d, r15d
0x180068af6  cmovz   r9, rax
0x180068afa  call    FormatRRASErrorString
0x180068aff  mov     rdx, qword ptr cs:unk_1800CA098
0x180068b06  lea     rax, [rsp+8D0h+var_868]
0x180068b0b  mov     rcx, cs:gIphlpEtwContext
0x180068b12  lea     r9, [rsp+8D0h+var_888]
0x180068b17  mov     [rsp+8D0h+var_8A8], rax
0x180068b1c  lea     r8, [rbp+7D0h+var_840]
0x180068b20  mov     rax, cs:gIphlpParamTemplateFunc
0x180068b27  mov     [rsp+8D0h+var_8B0], 0
0x180068b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b35  jmp     short loc_180068B5B
0x180068b37  test    r12d, r12d
0x180068b3a  lea     rax, aFalse; "FALSE"
0x180068b41  lea     r8, aTrue; "TRUE"
0x180068b48  mov     edx, r15d
0x180068b4b  cmovz   r8, rax
0x180068b4f  lea     rcx, aRastcpsetproxy_0; "RasTcpSetProxyArp(IP Addr: 0x%x, fAddAd"...
0x180068b56  call    TraceHlp
0x180068b5b  call    cs:__imp_GetProcessHeap
0x180068b61  mov     r14, rax
0x180068b64  test    rax, rax
0x180068b67  jnz     loc_180068BF1
0x180068b6d  call    cs:__imp_GetLastError
0x180068b73  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180068b7a  jz      short loc_180068BDE
0x180068b7c  cmp     qword ptr cs:xmmword_1800CA088+8, r14
0x180068b83  jz      loc_180068DAF
0x180068b89  xor     ecx, ecx
0x180068b8b  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x180068b92  mov     word ptr [rbp+7D0h+var_840], cx
0x180068b96  mov     r8d, eax
0x180068b99  mov     word ptr [rsp+8D0h+var_868], cx
0x180068b9e  lea     rcx, [rbp+7D0h+var_840]
0x180068ba2  call    FormatRRASErrorString
0x180068ba7  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180068bae  lea     rax, [rsp+8D0h+var_868]
0x180068bb3  mov     rcx, cs:gIphlpEtwContext
0x180068bba  lea     r9, [rsp+8D0h+var_888]
0x180068bbf  mov     [rsp+8D0h+var_8A8], rax
0x180068bc4  lea     r8, [rbp+7D0h+var_840]
0x180068bc8  mov     rax, cs:gIphlpParamTemplateFunc
0x180068bcf  mov     [rsp+8D0h+var_8B0], r14
0x180068bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068bd9  jmp     loc_180068DAF
0x180068bde  mov     edx, eax
0x180068be0  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x180068be7  call    TraceHlp
0x180068bec  jmp     loc_180068DAF
0x180068bf1  mov     r8, r14
0x180068bf4  mov     dword ptr [rsp+8D0h+var_8B0], ebx
0x180068bf8  lea     rcx, [rsp+8D0h+lpMem]
0x180068bfd  call    AllocateAndGetIpAddrTable
0x180068c02  mov     rbx, [rsp+8D0h+lpMem]
0x180068c07  test    eax, eax
0x180068c09  jz      loc_180068C92
0x180068c0f  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180068c16  jz      short loc_180068C7F
0x180068c18  cmp     qword ptr cs:xmmword_1800CA088+8, 0
0x180068c20  jz      loc_180068D9C
0x180068c26  xor     ecx, ecx
0x180068c28  lea     rdx, aAllocateandget_8; "AllocateAndGetIpAddrTable failed and re"...
0x180068c2f  mov     word ptr [rbp+7D0h+var_840], cx
0x180068c33  mov     r8d, eax
0x180068c36  mov     word ptr [rsp+8D0h+var_868], cx
0x180068c3b  lea     rcx, [rbp+7D0h+var_840]
0x180068c3f  call    FormatRRASErrorString
0x180068c44  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180068c4b  lea     rax, [rsp+8D0h+var_868]
0x180068c50  mov     rcx, cs:gIphlpEtwContext
0x180068c57  lea     r9, [rsp+8D0h+var_888]
0x180068c5c  mov     [rsp+8D0h+var_8A8], rax
0x180068c61  lea     r8, [rbp+7D0h+var_840]
0x180068c65  mov     rax, cs:gIphlpParamTemplateFunc
0x180068c6c  mov     [rsp+8D0h+var_8B0], 0
0x180068c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c7a  jmp     loc_180068D9C
0x180068c7f  mov     edx, eax
0x180068c81  lea     rcx, aAllocateandget_2; "AllocateAndGetIpAddrTable failed and re"...
0x180068c88  call    TraceHlp
0x180068c8d  jmp     loc_180068D9C
0x180068c92  xor     esi, esi
0x180068c94  cmp     [rbx], esi
0x180068c96  jbe     loc_180068D9C
0x180068c9c  lea     rdi, [rsi+rsi*2]
0x180068ca0  mov     edx, [rbx+rdi*8+4]
0x180068ca4  lea     eax, [rdx-1]
0x180068ca7  cmp     eax, 0FFFFFFFDh
0x180068caa  ja      loc_180068D92
0x180068cb0  cmp     r13d, edx
0x180068cb3  jz      loc_180068D92
0x180068cb9  mov     ecx, [rbx+rdi*8+0Ch]
0x180068cbd  mov     eax, ecx
0x180068cbf  and     eax, edx
0x180068cc1  and     ecx, r15d
0x180068cc4  cmp     ecx, eax
0x180068cc6  jnz     loc_180068D92
0x180068ccc  mov     r8d, [rbx+rdi*8+8]; dwIfIndex
0x180068cd1  or      edx, 0FFFFFFFFh; dwMask
0x180068cd4  mov     ecx, r15d; dwAddress
0x180068cd7  test    r12d, r12d
0x180068cda  jz      short loc_180068D0B
0x180068cdc  call    cs:__imp_CreateProxyArpEntry
0x180068ce2  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180068ce9  jz      short loc_180068D02
0x180068ceb  cmp     qword ptr cs:xmmword_1800CA088+8, 0
0x180068cf3  jz      loc_180068D92
0x180068cf9  lea     rdx, aCreateproxyarp; "CreateProxyArpEntry: ifIndex=%d, 0x%x"
0x180068d00  jmp     short loc_180068D2B
0x180068d02  lea     rcx, aCreateproxyarp_0; "CreateProxyArpEntry: ifIndex=%d, 0x%x"
0x180068d09  jmp     short loc_180068D86
0x180068d0b  call    cs:__imp_DeleteProxyArpEntry
0x180068d11  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180068d18  jz      short loc_180068D7F
0x180068d1a  cmp     qword ptr cs:xmmword_1800CA088+8, 0
0x180068d22  jz      short loc_180068D92
0x180068d24  lea     rdx, aDeleteproxyarp; "DeleteProxyArpEntry: ifIndex=%d, 0x%x"
0x180068d2b  xor     ecx, ecx
0x180068d2d  mov     r9d, eax
0x180068d30  mov     word ptr [rbp+7D0h+var_840], cx
0x180068d34  mov     word ptr [rsp+8D0h+var_868], cx
0x180068d39  lea     rcx, [rbp+7D0h+var_840]
0x180068d3d  mov     r8d, [rbx+rdi*8+8]
0x180068d42  call    FormatRRASErrorString
0x180068d47  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180068d4e  lea     rax, [rsp+8D0h+var_868]
0x180068d53  mov     rcx, cs:gIphlpEtwContext
0x180068d5a  lea     r9, [rsp+8D0h+var_888]
0x180068d5f  mov     [rsp+8D0h+var_8A8], rax
0x180068d64  lea     r8, [rbp+7D0h+var_840]
0x180068d68  mov     rax, cs:gIphlpParamTemplateFunc
0x180068d6f  mov     [rsp+8D0h+var_8B0], 0
0x180068d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d7d  jmp     short loc_180068D92
0x180068d7f  lea     rcx, aDeleteproxyarp_0; "DeleteProxyArpEntry: ifIndex=%d, 0x%x"
0x180068d86  mov     edx, [rbx+rdi*8+8]
0x180068d8a  mov     r8d, eax
0x180068d8d  call    TraceHlp
0x180068d92  inc     esi
0x180068d94  cmp     esi, [rbx]
0x180068d96  jb      loc_180068C9C
0x180068d9c  test    rbx, rbx
0x180068d9f  jz      short loc_180068DAF
0x180068da1  mov     r8, rbx; lpMem
0x180068da4  xor     edx, edx; dwFlags
0x180068da6  mov     rcx, r14; hHeap
0x180068da9  call    cs:__imp_HeapFree
0x180068daf  mov     rcx, [rbp+7D0h+var_40]
0x180068db6  xor     rcx, rsp; StackCookie
0x180068db9  call    __security_check_cookie
0x180068dbe  mov     rbx, [rsp+8D0h+arg_8]
0x180068dc6  add     rsp, 8A0h
0x180068dcd  pop     r15
0x180068dcf  pop     r14
0x180068dd1  pop     r13
0x180068dd3  pop     r12
0x180068dd5  pop     rdi
0x180068dd6  pop     rsi
0x180068dd7  pop     rbp
0x180068dd8  retn
```
