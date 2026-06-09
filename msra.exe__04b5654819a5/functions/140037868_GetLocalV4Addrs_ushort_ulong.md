# GetLocalV4Addrs(ushort * * *,ulong *)

- ea: `0x140037868`
- end: `0x140037a80`
- name: `?GetLocalV4Addrs@@YAJPEAPEAPEAGPEAK@Z`
- size: `536`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400380dc`

## callees

- `0x140034ce4`
- `0x1400363a4`
- `0x140037868`
- `0x140037a88`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400379c3`
- `KERNEL32!HeapFree` at `0x1400379c3`
- `KERNEL32!GetProcessHeap` at `0x1400378ea`
- `KERNEL32!GetProcessHeap` at `0x140037947`
- `KERNEL32!GetProcessHeap` at `0x1400379af`
- `KERNEL32!GetProcessHeap` at `0x1400378ea`
- `KERNEL32!GetProcessHeap` at `0x140037947`
- `KERNEL32!GetProcessHeap` at `0x1400379af`
- `KERNEL32!HeapAlloc` at `0x140037901`
- `KERNEL32!HeapAlloc` at `0x14003795f`
- `KERNEL32!HeapAlloc` at `0x140037901`
- `KERNEL32!HeapAlloc` at `0x14003795f`
- `ntdll!RtlIpv4AddressToStringW` at `0x14003797e`
- `ntdll!RtlIpv4AddressToStringW` at `0x14003797e`

## string_xrefs

- `0x1400378bc`: `base\diagnosis\ra\racommon\src\rasqm.cpp`
- `0x140037a11`: `base\diagnosis\ra\racommon\src\rasqm.cpp`
- `0x140037a4a`: `base\diagnosis\ra\racommon\src\rasqm.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalV4Addrs(unsigned __int16 ***a1, unsigned int *a2)
{
  signed int v4; // esi
  unsigned __int16 **v5; // rbx
  signed int LocalV4Addrs; // eax
  CEventLogger *v7; // rcx
  int *v8; // rbp
  int v9; // edi
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  CEventLogger *v12; // rcx
  const struct in_addr *v13; // r15
  HANDLE v14; // rax
  WCHAR *v15; // rax
  CEventLogger *v16; // rcx
  PWSTR v17; // rax
  HANDLE v18; // rax
  unsigned int v19; // r9d
  LPVOID lpMem; // [rsp+80h] [rbp+8h] BYREF

  *a1 = 0;
  lpMem = 0;
  v4 = 0;
  *a2 = 0;
  v5 = 0;
  LocalV4Addrs = GetLocalV4Addrs((struct _SOCKET_ADDRESS_LIST **)&lpMem);
  v8 = (int *)lpMem;
  v9 = LocalV4Addrs;
  if ( LocalV4Addrs >= 0 )
  {
    if ( !lpMem )
    {
      CEventLogger::LogError(
        v7,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
        0x417u,
        L"GetLocalV4Addrs",
        0);
      v9 = -2147467259;
LABEL_23:
      FreeStringList(v5, v4);
      return (unsigned int)v9;
    }
    v10 = 8LL * *(int *)lpMem;
    ProcessHeap = GetProcessHeap();
    v5 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, v10);
    if ( v5 )
    {
      if ( *v8 <= 0 )
      {
LABEL_13:
        *a1 = v5;
        v5 = 0;
        *a2 = v4;
        v4 = 0;
      }
      else
      {
        while ( 1 )
        {
          v13 = *(const struct in_addr **)&v8[4 * v4 + 2];
          if ( !v13 )
            break;
          v14 = GetProcessHeap();
          v15 = (WCHAR *)HeapAlloc(v14, 8u, 0x22u);
          v5[v4] = v15;
          if ( !v15 )
          {
            v9 = -2147024882;
            CEventLogger::LogError(
              v16,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
              0x424u,
              L"GetLocalV4Addrs",
              0x8007000E);
            goto LABEL_14;
          }
          v17 = RtlIpv4AddressToStringW(v13 + 1, v15);
          if ( !v17 || *v17 )
          {
            v19 = 1067;
            goto LABEL_21;
          }
          if ( ++v4 >= *v8 )
            goto LABEL_13;
        }
        v19 = 1058;
LABEL_21:
        CEventLogger::LogError(
          v12,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
          v19,
          L"GetLocalV4Addrs",
          0);
        v9 = -2147467259;
      }
    }
    else
    {
      v9 = -2147024882;
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
        0x41Cu,
        L"GetLocalV4Addrs",
        0x8007000E);
    }
  }
  else
  {
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
      0x416u,
      L"GetLocalV4Addrs",
      LocalV4Addrs);
  }
LABEL_14:
  if ( v8 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v8);
  }
  if ( v9 < 0 )
    goto LABEL_23;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140037868  mov     rax, rsp
0x14003786b  push    rbx
0x14003786c  push    rbp
0x14003786d  push    rsi
0x14003786e  push    rdi
0x14003786f  push    r12
0x140037871  push    r13
0x140037873  push    r14
0x140037875  push    r15
0x140037877  sub     rsp, 38h
0x14003787b  xor     r14d, r14d
0x14003787e  mov     r13, rcx
0x140037881  mov     [rcx], r14
0x140037884  mov     r12, rdx
0x140037887  lea     rcx, [rax+8]; struct _SOCKET_ADDRESS_LIST **
0x14003788b  mov     [rax+8], r14
0x14003788f  mov     esi, r14d
0x140037892  mov     [rdx], r14d
0x140037895  mov     ebx, r14d
0x140037898  call    ?GetLocalV4Addrs@@YAJPEAPEAU_SOCKET_ADDRESS_LIST@@@Z; GetLocalV4Addrs(_SOCKET_ADDRESS_LIST * *)
0x14003789d  mov     rbp, [rsp+78h+lpMem]
0x1400378a5  mov     edi, eax
0x1400378a7  test    eax, eax
0x1400378a9  jns     short loc_1400378D9
0x1400378ab  mov     [rsp+78h+var_50], eax; unsigned int
0x1400378af  mov     r9d, 416h; unsigned int
0x1400378b5  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x1400378bc  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x1400378c3  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1400378c8  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400378cf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400378d4  jmp     loc_1400379AA
0x1400378d9  test    rbp, rbp
0x1400378dc  jz      loc_140037A33
0x1400378e2  movsxd  rbx, dword ptr [rbp+0]
0x1400378e6  shl     rbx, 3
0x1400378ea  call    cs:__imp_GetProcessHeap
0x1400378f1  nop     dword ptr [rax+rax+00h]
0x1400378f6  mov     r8, rbx; dwBytes
0x1400378f9  mov     edx, 8; dwFlags
0x1400378fe  mov     rcx, rax; hHeap
0x140037901  call    cs:__imp_HeapAlloc
0x140037908  nop     dword ptr [rax+rax+00h]
0x14003790d  mov     rbx, rax
0x140037910  test    rax, rax
0x140037913  jnz     short loc_14003792A
0x140037915  mov     edi, 8007000Eh
0x14003791a  mov     [rsp+78h+var_50], 8007000Eh
0x140037922  mov     r9d, 41Ch
0x140037928  jmp     short loc_1400378B5
0x14003792a  cmp     [rbp+0], r14d
0x14003792e  jle     short loc_14003799C
0x140037930  movsxd  r14, esi
0x140037933  mov     rax, r14
0x140037936  add     rax, rax
0x140037939  mov     r15, [rbp+rax*8+8]
0x14003793e  test    r15, r15
0x140037941  jz      loc_1400379FC
0x140037947  call    cs:__imp_GetProcessHeap
0x14003794e  nop     dword ptr [rax+rax+00h]
0x140037953  mov     edx, 8; dwFlags
0x140037958  mov     rcx, rax; hHeap
0x14003795b  lea     r8d, [rdx+1Ah]; dwBytes
0x14003795f  call    cs:__imp_HeapAlloc
0x140037966  nop     dword ptr [rax+rax+00h]
0x14003796b  mov     [rbx+r14*8], rax
0x14003796f  xor     r14d, r14d
0x140037972  test    rax, rax
0x140037975  jz      short loc_1400379E4
0x140037977  lea     rcx, [r15+4]; Addr
0x14003797b  mov     rdx, rax; S
0x14003797e  call    cs:__imp_RtlIpv4AddressToStringW
0x140037985  nop     dword ptr [rax+rax+00h]
0x14003798a  test    rax, rax
0x14003798d  jz      short loc_1400379DC
0x14003798f  cmp     r14w, [rax]
0x140037993  jnz     short loc_1400379DC
0x140037995  inc     esi
0x140037997  cmp     esi, [rbp+0]
0x14003799a  jl      short loc_140037930
0x14003799c  mov     [r13+0], rbx
0x1400379a0  mov     rbx, r14
0x1400379a3  mov     [r12], esi
0x1400379a7  mov     esi, r14d
0x1400379aa  test    rbp, rbp
0x1400379ad  jz      short loc_1400379CF
0x1400379af  call    cs:__imp_GetProcessHeap
0x1400379b6  nop     dword ptr [rax+rax+00h]
0x1400379bb  mov     r8, rbp; lpMem
0x1400379be  xor     edx, edx; dwFlags
0x1400379c0  mov     rcx, rax; hHeap
0x1400379c3  call    cs:__imp_HeapFree
0x1400379ca  nop     dword ptr [rax+rax+00h]
0x1400379cf  test    edi, edi
0x1400379d1  jns     loc_140037A6C
0x1400379d7  jmp     loc_140037A62
0x1400379dc  mov     r9d, 42Bh
0x1400379e2  jmp     short loc_140037A05
0x1400379e4  mov     edi, 8007000Eh
0x1400379e9  mov     [rsp+78h+var_50], 8007000Eh
0x1400379f1  mov     r9d, 424h
0x1400379f7  jmp     loc_1400378B5
0x1400379fc  xor     r14d, r14d
0x1400379ff  mov     r9d, 422h; unsigned int
0x140037a05  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x140037a0c  mov     [rsp+78h+var_50], r14d; unsigned int
0x140037a11  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140037a18  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x140037a1d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037a24  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037a29  mov     edi, 80004005h
0x140037a2e  jmp     loc_1400379AA
0x140037a33  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x140037a3a  mov     [rsp+78h+var_50], r14d; unsigned int
0x140037a3f  mov     r9d, 417h; unsigned int
0x140037a45  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x140037a4a  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140037a51  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037a58  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037a5d  mov     edi, 80004005h
0x140037a62  mov     edx, esi; unsigned int
0x140037a64  mov     rcx, rbx; lpMem
0x140037a67  call    ?FreeStringList@@YAJPEAPEAGK@Z; FreeStringList(ushort * *,ulong)
0x140037a6c  mov     eax, edi
0x140037a6e  add     rsp, 38h
0x140037a72  pop     r15
0x140037a74  pop     r14
0x140037a76  pop     r13
0x140037a78  pop     r12
0x140037a7a  pop     rdi
0x140037a7b  pop     rsi
0x140037a7c  pop     rbp
0x140037a7d  pop     rbx
0x140037a7e  retn
```
