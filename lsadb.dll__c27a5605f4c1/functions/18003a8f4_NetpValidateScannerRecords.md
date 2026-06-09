# NetpValidateScannerRecords

- ea: `0x18003a8f4`
- end: `0x18003ab78`
- name: `NetpValidateScannerRecords`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800399dc`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180037b0c`
- `0x18003a8f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003aa44`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003aa44`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003aa93`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003aad0`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003ab0e`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003aa93`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003aad0`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003ab0e`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003a980`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003a99c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003a9b9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003a980`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003a99c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003a9b9`
- `DNSAPI!DnsValidateName_W` at `0x18003a9e6`
- `DNSAPI!DnsValidateName_W` at `0x18003a9e6`

## pseudocode

```c
__int64 __fastcall NetpValidateScannerRecords(__int64 a1)
{
  unsigned int v2; // r14d
  __int64 v3; // rsi
  __int64 v4; // rbx
  const WCHAR *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  void *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rsi
  unsigned int v13; // ebx
  unsigned __int8 NewElement[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-C8h] BYREF
  struct _RTL_AVL_TABLE v17; // [rsp+40h] [rbp-C0h] BYREF
  struct _RTL_AVL_TABLE v18; // [rsp+B0h] [rbp-50h] BYREF
  struct _RTL_AVL_TABLE Table; // [rsp+120h] [rbp+20h] BYREF

  Buffer = 0;
  NewElement[0] = 0;
  memset_0(&Table, 0, sizeof(Table));
  memset_0(&v18, 0, sizeof(v18));
  memset_0(&v17, 0, sizeof(v17));
  RtlInitializeGenericTableAvl(
    &Table,
    (PRTL_AVL_COMPARE_ROUTINE)NetpAvlCompareDnsDomainName,
    NetpAvlTableAllocate,
    NetpAvlTableFree,
    0);
  RtlInitializeGenericTableAvl(
    &v18,
    (PRTL_AVL_COMPARE_ROUTINE)NetpAvlCompareNetbiosDomainName,
    NetpAvlTableAllocate,
    NetpAvlTableFree,
    0);
  RtlInitializeGenericTableAvl(&v17, NetpAvlCompareSid, NetpAvlTableAllocate, NetpAvlTableFree, 0);
  v2 = 0;
  if ( *(_DWORD *)a1 )
  {
    do
    {
      v3 = *(_QWORD *)(a1 + 8);
      v4 = 32LL * v2;
      v5 = *(const WCHAR **)(v4 + v3 + 16);
      if ( !v5 )
        goto LABEL_27;
      if ( DnsValidateName_W(v5, DnsNameDomain) )
        goto LABEL_27;
      v6 = *(_QWORD *)(v4 + v3 + 16);
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(v6 + 2 * v7) );
      if ( v7 && *(_WORD *)(v6 + 2 * v7 - 2) == 46 )
        goto LABEL_27;
      v8 = *(_QWORD *)(v4 + v3 + 24);
      if ( v8 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)(v8 + 2 * v9) );
        if ( v9 > 0xF )
          goto LABEL_27;
      }
      v10 = *(void **)(v4 + v3 + 8);
      if ( v10 )
      {
        if ( !IsValidSid(v10) )
        {
LABEL_27:
          v13 = -1073741811;
          goto LABEL_26;
        }
      }
      ++v2;
    }
    while ( v2 < *(_DWORD *)a1 );
    v11 = 0;
    if ( !*(_DWORD *)a1 )
      goto LABEL_25;
    while ( 1 )
    {
      v12 = 32LL * v11;
      Buffer = v12 + *(_QWORD *)(a1 + 8);
      if ( !RtlInsertElementGenericTableAvl(&Table, &Buffer, 8u, NewElement) )
        break;
      if ( !NewElement[0] )
        goto LABEL_27;
      if ( *(_QWORD *)(v12 + *(_QWORD *)(a1 + 8) + 24) )
      {
        Buffer = v12 + *(_QWORD *)(a1 + 8);
        if ( !RtlInsertElementGenericTableAvl(&v18, &Buffer, 8u, NewElement) )
          break;
        if ( !NewElement[0] )
          goto LABEL_27;
      }
      if ( *(_QWORD *)(v12 + *(_QWORD *)(a1 + 8) + 8) )
      {
        Buffer = v12 + *(_QWORD *)(a1 + 8);
        if ( !RtlInsertElementGenericTableAvl(&v17, &Buffer, 8u, NewElement) )
          break;
        if ( !NewElement[0] )
          goto LABEL_27;
      }
      if ( ++v11 >= *(_DWORD *)a1 )
        goto LABEL_25;
    }
    v13 = -1073741801;
  }
  else
  {
LABEL_25:
    v13 = 0;
  }
LABEL_26:
  NetpAvlTableFreeAllElements(&v17);
  NetpAvlTableFreeAllElements(&v18);
  NetpAvlTableFreeAllElements(&Table);
  return v13;
}

```

## disassembly

```asm
0x18003a8f4  push    rbp
0x18003a8f6  push    rbx
0x18003a8f7  push    rsi
0x18003a8f8  push    rdi
0x18003a8f9  push    r14
0x18003a8fb  push    r15
0x18003a8fd  lea     rbp, [rsp-0A8h]
0x18003a905  sub     rsp, 1A8h
0x18003a90c  mov     rax, cs:__security_cookie
0x18003a913  xor     rax, rsp
0x18003a916  mov     [rbp+0D0h+var_40], rax
0x18003a91d  xor     r15d, r15d
0x18003a920  mov     rdi, rcx
0x18003a923  xor     edx, edx; Val
0x18003a925  mov     [rsp+1D0h+Buffer], r15
0x18003a92a  lea     rcx, [rbp+0D0h+Table]; void *
0x18003a92e  mov     [rsp+1D0h+NewElement], r15b
0x18003a933  lea     ebx, [r15+68h]
0x18003a937  mov     r8d, ebx; Size
0x18003a93a  call    memset_0
0x18003a93f  mov     r8d, ebx; Size
0x18003a942  lea     rcx, [rbp+0D0h+var_120]; void *
0x18003a946  xor     edx, edx; Val
0x18003a948  call    memset_0
0x18003a94d  mov     r8d, ebx; Size
0x18003a950  lea     rcx, [rsp+1D0h+var_190]; void *
0x18003a955  xor     edx, edx; Val
0x18003a957  call    memset_0
0x18003a95c  lea     rsi, NetpAvlTableFree
0x18003a963  mov     [rsp+1D0h+TableContext], r15; TableContext
0x18003a968  lea     rbx, NetpAvlTableAllocate
0x18003a96f  mov     r9, rsi; FreeRoutine
0x18003a972  mov     r8, rbx; AllocateRoutine
0x18003a975  lea     rdx, NetpAvlCompareDnsDomainName; CompareRoutine
0x18003a97c  lea     rcx, [rbp+0D0h+Table]; Table
0x18003a980  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003a986  mov     r9, rsi; FreeRoutine
0x18003a989  mov     [rsp+1D0h+TableContext], r15; TableContext
0x18003a98e  mov     r8, rbx; AllocateRoutine
0x18003a991  lea     rdx, NetpAvlCompareNetbiosDomainName; CompareRoutine
0x18003a998  lea     rcx, [rbp+0D0h+var_120]; Table
0x18003a99c  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003a9a2  mov     r9, rsi; FreeRoutine
0x18003a9a5  mov     [rsp+1D0h+TableContext], r15; TableContext
0x18003a9aa  mov     r8, rbx; AllocateRoutine
0x18003a9ad  lea     rdx, NetpAvlCompareSid; CompareRoutine
0x18003a9b4  lea     rcx, [rsp+1D0h+var_190]; Table
0x18003a9b9  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003a9bf  mov     r14d, r15d
0x18003a9c2  cmp     [rdi], r15d
0x18003a9c5  jbe     loc_18003AB2A
0x18003a9cb  mov     rsi, [rdi+8]
0x18003a9cf  mov     ebx, r14d
0x18003a9d2  shl     rbx, 5
0x18003a9d6  mov     rcx, [rbx+rsi+10h]; pszName
0x18003a9db  test    rcx, rcx
0x18003a9de  jz      loc_18003AB6A
0x18003a9e4  xor     edx, edx; Format
0x18003a9e6  call    cs:__imp_DnsValidateName_W
0x18003a9ec  test    eax, eax
0x18003a9ee  jnz     loc_18003AB6A
0x18003a9f4  mov     rcx, [rbx+rsi+10h]
0x18003a9f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a9fd  inc     rax
0x18003aa00  cmp     [rcx+rax*2], r15w
0x18003aa05  jnz     short loc_18003A9FD
0x18003aa07  test    rax, rax
0x18003aa0a  jz      short loc_18003AA18
0x18003aa0c  cmp     word ptr [rcx+rax*2-2], 2Eh ; '.'
0x18003aa12  jz      loc_18003AB6A
0x18003aa18  mov     rcx, [rbx+rsi+18h]
0x18003aa1d  test    rcx, rcx
0x18003aa20  jz      short loc_18003AA3A
0x18003aa22  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003aa26  inc     rax
0x18003aa29  cmp     [rcx+rax*2], r15w
0x18003aa2e  jnz     short loc_18003AA26
0x18003aa30  cmp     rax, 0Fh
0x18003aa34  ja      loc_18003AB6A
0x18003aa3a  mov     rcx, [rbx+rsi+8]; pSid
0x18003aa3f  test    rcx, rcx
0x18003aa42  jz      short loc_18003AA52
0x18003aa44  call    cs:__imp_IsValidSid
0x18003aa4a  test    eax, eax
0x18003aa4c  jz      loc_18003AB6A
0x18003aa52  inc     r14d
0x18003aa55  cmp     r14d, [rdi]
0x18003aa58  jb      loc_18003A9CB
0x18003aa5e  mov     ebx, r15d
0x18003aa61  cmp     [rdi], r15d
0x18003aa64  jbe     loc_18003AB2A
0x18003aa6a  mov     r14d, 8
0x18003aa70  mov     rcx, [rdi+8]
0x18003aa74  lea     r9, [rsp+1D0h+NewElement]; NewElement
0x18003aa79  mov     esi, ebx
0x18003aa7b  lea     rdx, [rsp+1D0h+Buffer]; Buffer
0x18003aa80  shl     rsi, 5
0x18003aa84  mov     r8d, r14d; BufferSize
0x18003aa87  add     rcx, rsi
0x18003aa8a  mov     [rsp+1D0h+Buffer], rcx
0x18003aa8f  lea     rcx, [rbp+0D0h+Table]; Table
0x18003aa93  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003aa99  test    rax, rax
0x18003aa9c  jz      loc_18003AB71
0x18003aaa2  cmp     [rsp+1D0h+NewElement], r15b
0x18003aaa7  jz      loc_18003AB6A
0x18003aaad  mov     rcx, [rdi+8]
0x18003aab1  add     rcx, rsi
0x18003aab4  cmp     [rcx+18h], r15
0x18003aab8  jz      short loc_18003AAEA
0x18003aaba  mov     [rsp+1D0h+Buffer], rcx
0x18003aabf  lea     r9, [rsp+1D0h+NewElement]; NewElement
0x18003aac4  lea     rcx, [rbp+0D0h+var_120]; Table
0x18003aac8  mov     r8d, r14d; BufferSize
0x18003aacb  lea     rdx, [rsp+1D0h+Buffer]; Buffer
0x18003aad0  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003aad6  test    rax, rax
0x18003aad9  jz      loc_18003AB71
0x18003aadf  cmp     [rsp+1D0h+NewElement], r15b
0x18003aae4  jz      loc_18003AB6A
0x18003aaea  mov     rcx, [rdi+8]
0x18003aaee  add     rcx, rsi
0x18003aaf1  cmp     [rcx+8], r15
0x18003aaf5  jz      short loc_18003AB20
0x18003aaf7  mov     [rsp+1D0h+Buffer], rcx
0x18003aafc  lea     r9, [rsp+1D0h+NewElement]; NewElement
0x18003ab01  lea     rcx, [rsp+1D0h+var_190]; Table
0x18003ab06  mov     r8d, r14d; BufferSize
0x18003ab09  lea     rdx, [rsp+1D0h+Buffer]; Buffer
0x18003ab0e  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003ab14  test    rax, rax
0x18003ab17  jz      short loc_18003AB71
0x18003ab19  cmp     [rsp+1D0h+NewElement], r15b
0x18003ab1e  jz      short loc_18003AB6A
0x18003ab20  inc     ebx
0x18003ab22  cmp     ebx, [rdi]
0x18003ab24  jb      loc_18003AA70
0x18003ab2a  mov     ebx, r15d
0x18003ab2d  lea     rcx, [rsp+1D0h+var_190]; Table
0x18003ab32  call    NetpAvlTableFreeAllElements
0x18003ab37  lea     rcx, [rbp+0D0h+var_120]; Table
0x18003ab3b  call    NetpAvlTableFreeAllElements
0x18003ab40  lea     rcx, [rbp+0D0h+Table]; Table
0x18003ab44  call    NetpAvlTableFreeAllElements
0x18003ab49  mov     eax, ebx
0x18003ab4b  mov     rcx, [rbp+0D0h+var_40]
0x18003ab52  xor     rcx, rsp; StackCookie
0x18003ab55  call    __security_check_cookie
0x18003ab5a  add     rsp, 1A8h
0x18003ab61  pop     r15
0x18003ab63  pop     r14
0x18003ab65  pop     rdi
0x18003ab66  pop     rsi
0x18003ab67  pop     rbx
0x18003ab68  pop     rbp
0x18003ab69  retn
0x18003ab6a  mov     ebx, 0C000000Dh
0x18003ab6f  jmp     short loc_18003AB2D
0x18003ab71  mov     ebx, 0C0000017h
0x18003ab76  jmp     short loc_18003AB2D
```
