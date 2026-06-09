# RasTcpSetProxyArp

- ea: `0x18006b414`
- end: `0x18006b80a`
- name: `RasTcpSetProxyArp`
- size: `1014`
- prototype: `DWORD __fastcall(DWORD dwAddress, int, int, unsigned int)`
- caller_count: `8`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180050d54`
- `0x180054b80`
- `0x180054d50`
- `0x180055a04`
- `0x1800582b0`
- `0x180058dac`
- `0x18005f264`
- `0x18005f834`

## callees

- `0x18006ac5c`
- `0x18006b414`
- `0x18006c3c4`
- `0x1800755b8`
- `0x180079774`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18006b573`
- `KERNEL32!GetProcessHeap` at `0x18006b573`
- `KERNEL32!GetLastError` at `0x18006b590`
- `KERNEL32!GetLastError` at `0x18006b590`
- `KERNEL32!HeapFree` at `0x18006b7d3`
- `KERNEL32!HeapFree` at `0x18006b7d3`
- `IPHLPAPI!CreateProxyArpEntry` at `0x18006b6fb`
- `IPHLPAPI!CreateProxyArpEntry` at `0x18006b6fb`
- `IPHLPAPI!DeleteProxyArpEntry` at `0x18006b72f`
- `IPHLPAPI!DeleteProxyArpEntry` at `0x18006b72f`

## string_xrefs

- `0x18006b71d`: `CreateProxyArpEntry: ifIndex=%d, 0x%x`
- `0x18006b726`: `CreateProxyArpEntry: ifIndex=%d, 0x%x`
- `0x18006b74d`: `DeleteProxyArpEntry: ifIndex=%d, 0x%x`
- `0x18006b7a4`: `DeleteProxyArpEntry: ifIndex=%d, 0x%x`

## pseudocode

```c
DWORD __fastcall RasTcpSetProxyArp(DWORD dwAddress, int a2, int a3, unsigned int a4)
{
  __int64 v8; // rax
  DWORD result; // eax
  const char *v10; // r9
  HANDLE ProcessHeap; // rax
  __int64 v12; // rdx
  void *v13; // r14
  _DWORD *v14; // rbx
  int v15; // esi
  int v16; // edx
  int v17; // ecx
  DWORD v18; // r8d
  const wchar_t *v19; // rdx
  const CHAR *v20; // rcx
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v22; // [rsp+48h] [rbp-B8h]
  _OWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+74h] [rbp-8Ch]
  __int128 v26; // [rsp+84h] [rbp-7Ch]
  int v27; // [rsp+94h] [rbp-6Ch]
  int v28; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  lpMem = 0;
  v28 = 0;
  memset(v23, 0, sizeof(v23));
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  if ( (_QWORD)unk_1800D1080
    || __PAIR128__(*((unsigned __int64 *)&unk_1800D1080 + 1), 0) != (unsigned __int64)MEMORY[0x1800D1090]
    || (v8 = *((_QWORD *)&MEMORY[0x1800D1090] + 1)) != 0 && a4 != 1 )
  {
    result = NsiGetRoutingDomainIdForCompartment(a4, v23);
    if ( result )
      return result;
    v8 = *((_QWORD *)&MEMORY[0x1800D1090] + 1);
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      LOWORD(v28) = 0;
      LOWORD(v24) = 0;
      v10 = "TRUE";
      if ( !a2 )
        v10 = "FALSE";
      FormatRRASErrorString(&v28, L"RasTcpSetProxyArp(IP Addr: 0x%x, fAddAddress: %hs)", dwAddress, v10);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&MEMORY[0x1800D1090] + 1),
        &v28,
        v23,
        0,
        &v24);
    }
  }
  else
  {
    TraceHlp("RasTcpSetProxyArp(IP Addr: 0x%x, fAddAddress: %hs)");
  }
  ProcessHeap = GetProcessHeap();
  v22 = ProcessHeap;
  v13 = ProcessHeap;
  if ( !ProcessHeap )
  {
    result = GetLastError();
    if ( !gIsIphlpEtwTracingAvailable )
      return TraceHlp("GetProcessHeap failed and returned %d");
    if ( (_QWORD)MEMORY[0x1800D1090] )
    {
      LOWORD(v28) = 0;
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v28, L"GetProcessHeap failed and returned %d", result);
      return ((__int64 (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
               gIphlpEtwContext,
               MEMORY[0x1800D1090],
               &v28,
               v23,
               0,
               &v24);
    }
    return result;
  }
  result = AllocateAndGetIpAddrTable(&lpMem, v12, ProcessHeap);
  v14 = lpMem;
  if ( result )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( (_QWORD)MEMORY[0x1800D1090] )
      {
        LOWORD(v28) = 0;
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v28, L"AllocateAndGetIpAddrTable failed and returned %d", result);
        result = ((__int64 (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
                   gIphlpEtwContext,
                   MEMORY[0x1800D1090],
                   &v28,
                   v23,
                   0,
                   &v24);
      }
    }
    else
    {
      result = TraceHlp("AllocateAndGetIpAddrTable failed and returned %d");
    }
    goto LABEL_40;
  }
  v15 = 0;
  if ( *(_DWORD *)lpMem )
  {
    while ( 1 )
    {
      v16 = v14[6 * v15 + 1];
      v17 = v14[6 * v15 + 3];
      result = v16 - 1;
      if ( (unsigned int)(v16 - 1) > 0xFFFFFFFD )
        goto LABEL_38;
      if ( a3 == v16 )
        goto LABEL_38;
      result = v17 & dwAddress;
      if ( (v17 & dwAddress) != (v16 & v17) )
        goto LABEL_38;
      v18 = v14[6 * v15 + 2];
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
        if ( (_QWORD)MEMORY[0x1800D1090] )
        {
          v19 = L"CreateProxyArpEntry: ifIndex=%d, 0x%x";
LABEL_35:
          LOWORD(v28) = 0;
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v28, v19, (unsigned int)v14[6 * v15 + 2], result);
          result = ((__int64 (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
                     gIphlpEtwContext,
                     MEMORY[0x1800D1090],
                     &v28,
                     v23,
                     0,
                     &v24);
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
        if ( (_QWORD)MEMORY[0x1800D1090] )
        {
          v19 = L"DeleteProxyArpEntry: ifIndex=%d, 0x%x";
          goto LABEL_35;
        }
      }
LABEL_38:
      if ( (unsigned int)++v15 >= *v14 )
      {
        v13 = v22;
        break;
      }
    }
  }
LABEL_40:
  if ( v14 )
    return HeapFree(v13, 0, v14);
  return result;
}

```

## disassembly

```asm
0x18006b414  mov     [rsp-8+arg_8], rbx
0x18006b419  push    rbp
0x18006b41a  push    rsi
0x18006b41b  push    rdi
0x18006b41c  push    r12
0x18006b41e  push    r13
0x18006b420  push    r14
0x18006b422  push    r15
0x18006b424  lea     rbp, [rsp-7B0h]
0x18006b42c  sub     rsp, 8B0h
0x18006b433  mov     rax, cs:__security_cookie
0x18006b43a  xor     rax, rsp
0x18006b43d  mov     [rbp+7E0h+var_40], rax
0x18006b444  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006b44b  mov     r13d, r8d
0x18006b44e  mov     r12d, edx
0x18006b451  mov     r15d, ecx
0x18006b454  xor     edi, edi
0x18006b456  xor     edx, edx; Val
0x18006b458  mov     [rsp+8E0h+lpMem], rdi
0x18006b45d  mov     r8d, 7FCh; Size
0x18006b463  mov     [rbp+7E0h+var_840], edi
0x18006b466  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18006b46a  mov     ebx, r9d
0x18006b46d  movdqu  [rsp+8E0h+var_890], xmm0
0x18006b473  call    memset_0
0x18006b478  xorps   xmm0, xmm0
0x18006b47b  mov     [rsp+8E0h+var_870], edi
0x18006b47f  xor     eax, eax
0x18006b481  cmp     qword ptr cs:unk_1800D1080, rdi
0x18006b488  movups  [rsp+8E0h+var_86C], xmm0
0x18006b48d  mov     [rbp+7E0h+var_84C], eax
0x18006b490  movups  [rbp+7E0h+var_85C], xmm0
0x18006b494  movups  [rsp+8E0h+var_880], xmm0
0x18006b499  jnz     short loc_18006B4BE
0x18006b49b  cmp     qword ptr cs:xmmword_1800D1088, rdi
0x18006b4a2  jnz     short loc_18006B4BE
0x18006b4a4  cmp     qword ptr cs:xmmword_1800D1088+8, rdi
0x18006b4ab  jnz     short loc_18006B4BE
0x18006b4ad  mov     rax, qword ptr cs:unk_1800D1098
0x18006b4b4  test    rax, rax
0x18006b4b7  jz      short loc_18006B4D9
0x18006b4b9  cmp     ebx, 1
0x18006b4bc  jz      short loc_18006B4D9
0x18006b4be  lea     rdx, [rsp+8E0h+var_890]
0x18006b4c3  mov     ecx, ebx
0x18006b4c5  call    NsiGetRoutingDomainIdForCompartment
0x18006b4ca  test    eax, eax
0x18006b4cc  jnz     loc_18006B7DF
0x18006b4d2  mov     rax, qword ptr cs:unk_1800D1098
0x18006b4d9  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x18006b4df  jz      short loc_18006B54F
0x18006b4e1  test    rax, rax
0x18006b4e4  jz      loc_18006B573
0x18006b4ea  lea     rax, aFalse; "FALSE"
0x18006b4f1  mov     word ptr [rbp+7E0h+var_840], di
0x18006b4f5  test    r12d, r12d
0x18006b4f8  mov     word ptr [rsp+8E0h+var_870], di
0x18006b4fd  lea     r9, aTrue; "TRUE"
0x18006b504  mov     r8d, r15d
0x18006b507  cmovz   r9, rax
0x18006b50b  lea     rdx, aRastcpsetproxy; "RasTcpSetProxyArp(IP Addr: 0x%x, fAddAd"...
0x18006b512  lea     rcx, [rbp+7E0h+var_840]
0x18006b516  call    FormatRRASErrorString
0x18006b51b  mov     rdx, qword ptr cs:unk_1800D1098
0x18006b522  lea     rax, [rsp+8E0h+var_870]
0x18006b527  mov     rcx, cs:gIphlpEtwContext
0x18006b52e  lea     r9, [rsp+8E0h+var_890]
0x18006b533  mov     [rsp+8E0h+var_8B8], rax
0x18006b538  lea     r8, [rbp+7E0h+var_840]
0x18006b53c  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b543  mov     [rsp+8E0h+var_8C0], rdi
0x18006b548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b54d  jmp     short loc_18006B573
0x18006b54f  test    r12d, r12d
0x18006b552  lea     rax, aFalse; "FALSE"
0x18006b559  lea     r8, aTrue; "TRUE"
0x18006b560  mov     edx, r15d
0x18006b563  cmovz   r8, rax
0x18006b567  lea     rcx, aRastcpsetproxy_0; "RasTcpSetProxyArp(IP Addr: 0x%x, fAddAd"...
0x18006b56e  call    TraceHlp
0x18006b573  call    cs:__imp_GetProcessHeap
0x18006b57a  nop     dword ptr [rax+rax+00h]
0x18006b57f  mov     [rsp+8E0h+var_898], rax
0x18006b584  mov     r14, rax
0x18006b587  test    rax, rax
0x18006b58a  jnz     loc_18006B617
0x18006b590  call    cs:__imp_GetLastError
0x18006b597  nop     dword ptr [rax+rax+00h]
0x18006b59c  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x18006b5a2  jz      short loc_18006B604
0x18006b5a4  cmp     qword ptr cs:xmmword_1800D1088+8, rdi
0x18006b5ab  jz      loc_18006B7DF
0x18006b5b1  mov     r8d, eax
0x18006b5b4  mov     word ptr [rbp+7E0h+var_840], di
0x18006b5b8  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x18006b5bf  mov     word ptr [rsp+8E0h+var_870], di
0x18006b5c4  lea     rcx, [rbp+7E0h+var_840]
0x18006b5c8  call    FormatRRASErrorString
0x18006b5cd  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006b5d4  lea     rax, [rsp+8E0h+var_870]
0x18006b5d9  mov     rcx, cs:gIphlpEtwContext
0x18006b5e0  lea     r9, [rsp+8E0h+var_890]
0x18006b5e5  mov     [rsp+8E0h+var_8B8], rax
0x18006b5ea  lea     r8, [rbp+7E0h+var_840]
0x18006b5ee  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b5f5  mov     [rsp+8E0h+var_8C0], rdi
0x18006b5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5ff  jmp     loc_18006B7DF
0x18006b604  mov     edx, eax
0x18006b606  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x18006b60d  call    TraceHlp
0x18006b612  jmp     loc_18006B7DF
0x18006b617  mov     r8, rax
0x18006b61a  mov     dword ptr [rsp+8E0h+var_8C0], ebx
0x18006b61e  lea     rcx, [rsp+8E0h+lpMem]
0x18006b623  call    AllocateAndGetIpAddrTable
0x18006b628  mov     rbx, [rsp+8E0h+lpMem]
0x18006b62d  test    eax, eax
0x18006b62f  jz      short loc_18006B6AC
0x18006b631  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x18006b637  jz      short loc_18006B699
0x18006b639  cmp     qword ptr cs:xmmword_1800D1088+8, rdi
0x18006b640  jz      loc_18006B7C6
0x18006b646  mov     r8d, eax
0x18006b649  mov     word ptr [rbp+7E0h+var_840], di
0x18006b64d  lea     rdx, aAllocateandget_8; "AllocateAndGetIpAddrTable failed and re"...
0x18006b654  mov     word ptr [rsp+8E0h+var_870], di
0x18006b659  lea     rcx, [rbp+7E0h+var_840]
0x18006b65d  call    FormatRRASErrorString
0x18006b662  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006b669  lea     rax, [rsp+8E0h+var_870]
0x18006b66e  mov     rcx, cs:gIphlpEtwContext
0x18006b675  lea     r9, [rsp+8E0h+var_890]
0x18006b67a  mov     [rsp+8E0h+var_8B8], rax
0x18006b67f  lea     r8, [rbp+7E0h+var_840]
0x18006b683  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b68a  mov     [rsp+8E0h+var_8C0], rdi
0x18006b68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b694  jmp     loc_18006B7C6
0x18006b699  mov     edx, eax
0x18006b69b  lea     rcx, aAllocateandget_2; "AllocateAndGetIpAddrTable failed and re"...
0x18006b6a2  call    TraceHlp
0x18006b6a7  jmp     loc_18006B7C6
0x18006b6ac  mov     esi, edi
0x18006b6ae  cmp     [rbx], edi
0x18006b6b0  jbe     loc_18006B7C6
0x18006b6b6  xor     r14d, r14d
0x18006b6b9  mov     eax, esi
0x18006b6bb  lea     rdi, [rax+rax*2]
0x18006b6bf  mov     edx, [rbx+rdi*8+4]
0x18006b6c3  mov     ecx, [rbx+rdi*8+0Ch]
0x18006b6c7  lea     eax, [rdx-1]
0x18006b6ca  cmp     eax, 0FFFFFFFDh
0x18006b6cd  ja      loc_18006B7B7
0x18006b6d3  cmp     r13d, edx
0x18006b6d6  jz      loc_18006B7B7
0x18006b6dc  mov     eax, r15d
0x18006b6df  and     eax, ecx
0x18006b6e1  and     ecx, edx
0x18006b6e3  cmp     eax, ecx
0x18006b6e5  jnz     loc_18006B7B7
0x18006b6eb  mov     r8d, [rbx+rdi*8+8]; dwIfIndex
0x18006b6f0  or      edx, 0FFFFFFFFh; dwMask
0x18006b6f3  mov     ecx, r15d; dwAddress
0x18006b6f6  test    r12d, r12d
0x18006b6f9  jz      short loc_18006B72F
0x18006b6fb  call    cs:__imp_CreateProxyArpEntry
0x18006b702  nop     dword ptr [rax+rax+00h]
0x18006b707  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006b70e  jz      short loc_18006B726
0x18006b710  cmp     qword ptr cs:xmmword_1800D1088+8, r14
0x18006b717  jz      loc_18006B7B7
0x18006b71d  lea     rdx, aCreateproxyarp; "CreateProxyArpEntry: ifIndex=%d, 0x%x"
0x18006b724  jmp     short loc_18006B754
0x18006b726  lea     rcx, aCreateproxyarp_0; "CreateProxyArpEntry: ifIndex=%d, 0x%x"
0x18006b72d  jmp     short loc_18006B7AB
0x18006b72f  call    cs:__imp_DeleteProxyArpEntry
0x18006b736  nop     dword ptr [rax+rax+00h]
0x18006b73b  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006b742  jz      short loc_18006B7A4
0x18006b744  cmp     qword ptr cs:xmmword_1800D1088+8, r14
0x18006b74b  jz      short loc_18006B7B7
0x18006b74d  lea     rdx, aDeleteproxyarp; "DeleteProxyArpEntry: ifIndex=%d, 0x%x"
0x18006b754  mov     word ptr [rbp+7E0h+var_840], r14w
0x18006b759  lea     rcx, [rbp+7E0h+var_840]
0x18006b75d  mov     word ptr [rsp+8E0h+var_870], r14w
0x18006b763  mov     r9d, eax
0x18006b766  mov     r8d, [rbx+rdi*8+8]
0x18006b76b  call    FormatRRASErrorString
0x18006b770  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006b777  lea     rax, [rsp+8E0h+var_870]
0x18006b77c  mov     rcx, cs:gIphlpEtwContext
0x18006b783  lea     r9, [rsp+8E0h+var_890]
0x18006b788  mov     [rsp+8E0h+var_8B8], rax
0x18006b78d  lea     r8, [rbp+7E0h+var_840]
0x18006b791  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b798  mov     [rsp+8E0h+var_8C0], r14
0x18006b79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7a2  jmp     short loc_18006B7B7
0x18006b7a4  lea     rcx, aDeleteproxyarp_0; "DeleteProxyArpEntry: ifIndex=%d, 0x%x"
0x18006b7ab  mov     edx, [rbx+rdi*8+8]
0x18006b7af  mov     r8d, eax
0x18006b7b2  call    TraceHlp
0x18006b7b7  inc     esi
0x18006b7b9  cmp     esi, [rbx]
0x18006b7bb  jb      loc_18006B6B9
0x18006b7c1  mov     r14, [rsp+8E0h+var_898]
0x18006b7c6  test    rbx, rbx
0x18006b7c9  jz      short loc_18006B7DF
0x18006b7cb  mov     r8, rbx; lpMem
0x18006b7ce  xor     edx, edx; dwFlags
0x18006b7d0  mov     rcx, r14; hHeap
0x18006b7d3  call    cs:__imp_HeapFree
0x18006b7da  nop     dword ptr [rax+rax+00h]
0x18006b7df  mov     rcx, [rbp+7E0h+var_40]
0x18006b7e6  xor     rcx, rsp; StackCookie
0x18006b7e9  call    __security_check_cookie
0x18006b7ee  mov     rbx, [rsp+8E0h+arg_8]
0x18006b7f6  add     rsp, 8B0h
0x18006b7fd  pop     r15
0x18006b7ff  pop     r14
0x18006b801  pop     r13
0x18006b803  pop     r12
0x18006b805  pop     rdi
0x18006b806  pop     rsi
0x18006b807  pop     rbp
0x18006b808  retn
```
