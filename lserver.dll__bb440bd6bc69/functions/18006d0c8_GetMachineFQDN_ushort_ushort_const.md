# GetMachineFQDN(ushort * *,ushort const *)

- ea: `0x18006d0c8`
- end: `0x18006d33c`
- name: `?GetMachineFQDN@@YAJPEAPEAGPEBG@Z`
- size: `628`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006d6c4`

## callees

- `0x18000d060`
- `0x18006d0c8`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18006d2af`
- `msvcrt!_wcsdup` at `0x18006d2af`
- `NETAPI32!DsGetDcNameW` at `0x18006d18c`
- `NETAPI32!DsGetDcNameW` at `0x18006d18c`
- `NETAPI32!NetApiBufferFree` at `0x18006d2ed`
- `NETAPI32!NetApiBufferFree` at `0x18006d2ed`
- `KERNEL32!GetComputerNameW` at `0x18006d13c`
- `KERNEL32!GetComputerNameW` at `0x18006d13c`
- `KERNEL32!GetLastError` at `0x18006d14c`
- `KERNEL32!GetLastError` at `0x18006d14c`
- `KERNEL32!LocalAlloc` at `0x18006d1fd`
- `KERNEL32!LocalAlloc` at `0x18006d1fd`
- `KERNEL32!LocalFree` at `0x18006d301`
- `KERNEL32!LocalFree` at `0x18006d301`
- `NTDSAPI!DsCrackNamesW` at `0x18006d26e`
- `NTDSAPI!DsCrackNamesW` at `0x18006d26e`
- `NTDSAPI!DsBindW` at `0x18006d1b5`
- `NTDSAPI!DsBindW` at `0x18006d1b5`
- `NTDSAPI!DsUnBindW` at `0x18006d281`
- `NTDSAPI!DsUnBindW` at `0x18006d281`
- `NTDSAPI!DsFreeNameResultW` at `0x18006d2d7`
- `NTDSAPI!DsFreeNameResultW` at `0x18006d2d7`

## pseudocode

```c
__int64 __fastcall GetMachineFQDN(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rdi
  DWORD DcNameW; // ebx
  signed int LastError; // eax
  const WCHAR *DomainName; // rsi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  PDS_NAME_RESULT_ITEMW rItems; // rcx
  unsigned __int16 *v11; // rax
  int v12; // ecx
  DWORD nSize[2]; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE phDS; // [rsp+50h] [rbp-B8h] BYREF
  PDS_NAME_RESULTW pResult; // [rsp+58h] [rbp-B0h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+60h] [rbp-A8h] BYREF
  PDOMAIN_CONTROLLER_INFOW v18[2]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+78h] [rbp-90h] BYREF

  DomainControllerInfo = 0;
  phDS = 0;
  v3 = 0;
  pResult = 0;
  *(_OWORD *)v18 = 0;
  if ( a1 )
  {
    nSize[0] = 261;
    if ( GetComputerNameW(Buffer, nSize) )
    {
      DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x80000020, &DomainControllerInfo);
      if ( !DcNameW )
      {
        DomainName = DomainControllerInfo->DomainName;
        DcNameW = DsBindW(0, DomainName, &phDS);
        if ( !DcNameW )
        {
          v7 = -1;
          v8 = -1;
          do
            ++v8;
          while ( DomainName[v8] );
          do
            ++v7;
          while ( Buffer[v7] );
          v9 = v8 + v7 + 3;
          v3 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * v9);
          if ( v3 )
          {
            StringCchPrintfW(v3, v9, L"%ws\\%ws$", DomainName, Buffer);
            *(_OWORD *)v18 = (unsigned __int64)v3;
            DcNameW = DsCrackNamesW(
                        phDS,
                        DS_NAME_NO_FLAGS,
                        DS_UNKNOWN_NAME,
                        DS_FQDN_1779_NAME,
                        1u,
                        (const LPCWSTR *)v18,
                        &pResult);
            DsUnBindW(&phDS);
            if ( !DcNameW )
            {
              rItems = pResult->rItems;
              if ( rItems->status )
              {
                DcNameW = rItems->status;
                if ( rItems->status == 1 )
                  DcNameW = 3;
              }
              else
              {
                v11 = _wcsdup(rItems->pName);
                v12 = 0;
                *a1 = v11;
                if ( !v11 )
                  v12 = -2147024882;
                DcNameW = v12;
              }
            }
          }
          else
          {
            DcNameW = -2147024882;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      DcNameW = LastError;
      if ( LastError > 0 )
        DcNameW = (unsigned __int16)LastError | 0x80070000;
    }
    if ( pResult )
      DsFreeNameResultW(pResult);
    if ( DomainControllerInfo )
      NetApiBufferFree(DomainControllerInfo);
    if ( v3 )
      LocalFree(v3);
  }
  else
  {
    return (DWORD)-2147024809;
  }
  return DcNameW;
}

```

## disassembly

```asm
0x18006d0c8  mov     rax, rsp
0x18006d0cb  mov     [rax+10h], rbx
0x18006d0cf  mov     [rax+18h], rsi
0x18006d0d3  mov     [rax+20h], rdi
0x18006d0d7  push    rbp
0x18006d0d8  push    r14
0x18006d0da  push    r15
0x18006d0dc  lea     rbp, [rax-1A8h]
0x18006d0e3  sub     rsp, 290h
0x18006d0ea  mov     rax, cs:__security_cookie
0x18006d0f1  xor     rax, rsp
0x18006d0f4  mov     [rbp+1A0h+var_20], rax
0x18006d0fb  xor     r15d, r15d
0x18006d0fe  xorps   xmm0, xmm0
0x18006d101  mov     [rsp+2A0h+var_248], r15
0x18006d106  mov     r14, rcx
0x18006d109  mov     [rsp+2A0h+phDS], r15
0x18006d10e  mov     edi, r15d
0x18006d111  mov     [rsp+2A0h+pResult], r15
0x18006d116  movups  xmmword ptr [rsp+2A0h+var_248+8], xmm0
0x18006d11b  test    rcx, rcx
0x18006d11e  jnz     short loc_18006D12A
0x18006d120  mov     ebx, 80070057h
0x18006d125  jmp     loc_18006D30D
0x18006d12a  lea     rdx, [rsp+2A0h+nSize]; nSize
0x18006d12f  mov     [rsp+2A0h+nSize], 105h
0x18006d137  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18006d13c  call    cs:__imp_GetComputerNameW
0x18006d143  nop     dword ptr [rax+rax+00h]
0x18006d148  test    eax, eax
0x18006d14a  jnz     short loc_18006D170
0x18006d14c  call    cs:__imp_GetLastError
0x18006d153  nop     dword ptr [rax+rax+00h]
0x18006d158  mov     ebx, eax
0x18006d15a  test    eax, eax
0x18006d15c  jle     loc_18006D2CD
0x18006d162  movzx   ebx, ax
0x18006d165  or      ebx, 80070000h
0x18006d16b  jmp     loc_18006D2CD
0x18006d170  lea     rax, [rsp+2A0h+var_248]
0x18006d175  xor     r9d, r9d; SiteName
0x18006d178  mov     [rsp+2A0h+DomainControllerInfo], rax; DomainControllerInfo
0x18006d17d  xor     r8d, r8d; DomainGuid
0x18006d180  xor     edx, edx; DomainName
0x18006d182  mov     [rsp+2A0h+Flags], 80000020h; Flags
0x18006d18a  xor     ecx, ecx; ComputerName
0x18006d18c  call    cs:__imp_DsGetDcNameW
0x18006d193  nop     dword ptr [rax+rax+00h]
0x18006d198  mov     ebx, eax
0x18006d19a  test    eax, eax
0x18006d19c  jnz     loc_18006D2CD
0x18006d1a2  mov     rax, [rsp+2A0h+var_248]
0x18006d1a7  lea     r8, [rsp+2A0h+phDS]; phDS
0x18006d1ac  xor     ecx, ecx; DomainControllerName
0x18006d1ae  mov     rsi, [rax+28h]
0x18006d1b2  mov     rdx, rsi; DnsDomainName
0x18006d1b5  call    cs:__imp_DsBindW
0x18006d1bc  nop     dword ptr [rax+rax+00h]
0x18006d1c1  mov     ebx, eax
0x18006d1c3  test    eax, eax
0x18006d1c5  jnz     loc_18006D2CD
0x18006d1cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006d1cf  mov     rcx, rax
0x18006d1d2  inc     rcx
0x18006d1d5  cmp     [rsi+rcx*2], r15w
0x18006d1da  jnz     short loc_18006D1D2
0x18006d1dc  lea     rdx, [rsp+2A0h+Buffer]
0x18006d1e1  inc     rax
0x18006d1e4  cmp     [rdx+rax*2], r15w
0x18006d1e9  jnz     short loc_18006D1E1
0x18006d1eb  lea     rbx, [rax+3]
0x18006d1ef  add     rbx, rcx
0x18006d1f2  mov     ecx, 40h ; '@'; uFlags
0x18006d1f7  mov     ebx, ebx
0x18006d1f9  lea     rdx, [rbx+rbx]; uBytes
0x18006d1fd  call    cs:__imp_LocalAlloc
0x18006d204  nop     dword ptr [rax+rax+00h]
0x18006d209  mov     rdi, rax
0x18006d20c  test    rax, rax
0x18006d20f  jnz     short loc_18006D21B
0x18006d211  mov     ebx, 8007000Eh
0x18006d216  jmp     loc_18006D2CD
0x18006d21b  lea     rax, [rsp+2A0h+Buffer]
0x18006d220  mov     r9, rsi
0x18006d223  lea     r8, aWsWs; "%ws\\%ws$"
0x18006d22a  mov     qword ptr [rsp+2A0h+Flags], rax
0x18006d22f  mov     rdx, rbx; unsigned __int64
0x18006d232  mov     rcx, rdi; unsigned __int16 *
0x18006d235  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d23a  mov     rcx, [rsp+2A0h+phDS]; hDS
0x18006d23f  lea     rax, [rsp+2A0h+pResult]
0x18006d244  mov     [rsp+2A0h+ppResult], rax; ppResult
0x18006d249  mov     esi, 1
0x18006d24e  lea     rax, [rsp+2A0h+var_248+8]
0x18006d253  mov     [rsp+2A0h+var_248+8], rdi
0x18006d258  mov     [rsp+2A0h+DomainControllerInfo], rax; rpNames
0x18006d25d  mov     r9d, esi; formatDesired
0x18006d260  xor     r8d, r8d; formatOffered
0x18006d263  mov     [rsp+2A0h+Flags], esi; cNames
0x18006d267  xor     edx, edx; flags
0x18006d269  mov     qword ptr [rsp+2A0h+var_238], r15
0x18006d26e  call    cs:__imp_DsCrackNamesW
0x18006d275  nop     dword ptr [rax+rax+00h]
0x18006d27a  lea     rcx, [rsp+2A0h+phDS]; phDS
0x18006d27f  mov     ebx, eax
0x18006d281  call    cs:__imp_DsUnBindW
0x18006d288  nop     dword ptr [rax+rax+00h]
0x18006d28d  test    ebx, ebx
0x18006d28f  jnz     short loc_18006D2CD
0x18006d291  mov     rax, [rsp+2A0h+pResult]
0x18006d296  mov     rcx, [rax+8]
0x18006d29a  cmp     [rcx], r15d
0x18006d29d  jz      short loc_18006D2AB
0x18006d29f  mov     ebx, [rcx]
0x18006d2a1  lea     eax, [rsi+2]
0x18006d2a4  cmp     ebx, esi
0x18006d2a6  cmovz   ebx, eax
0x18006d2a9  jmp     short loc_18006D2CD
0x18006d2ab  mov     rcx, [rcx+10h]; String
0x18006d2af  call    cs:__imp__wcsdup
0x18006d2b6  nop     dword ptr [rax+rax+00h]
0x18006d2bb  mov     ecx, ebx
0x18006d2bd  mov     ebx, 8007000Eh
0x18006d2c2  test    rax, rax
0x18006d2c5  mov     [r14], rax
0x18006d2c8  cmovz   ecx, ebx
0x18006d2cb  mov     ebx, ecx
0x18006d2cd  mov     rcx, [rsp+2A0h+pResult]; pResult
0x18006d2d2  test    rcx, rcx
0x18006d2d5  jz      short loc_18006D2E3
0x18006d2d7  call    cs:__imp_DsFreeNameResultW
0x18006d2de  nop     dword ptr [rax+rax+00h]
0x18006d2e3  mov     rcx, [rsp+2A0h+var_248]; Buffer
0x18006d2e8  test    rcx, rcx
0x18006d2eb  jz      short loc_18006D2F9
0x18006d2ed  call    cs:__imp_NetApiBufferFree
0x18006d2f4  nop     dword ptr [rax+rax+00h]
0x18006d2f9  test    rdi, rdi
0x18006d2fc  jz      short loc_18006D30D
0x18006d2fe  mov     rcx, rdi; hMem
0x18006d301  call    cs:__imp_LocalFree
0x18006d308  nop     dword ptr [rax+rax+00h]
0x18006d30d  mov     eax, ebx
0x18006d30f  mov     rcx, [rbp+1A0h+var_20]
0x18006d316  xor     rcx, rsp; StackCookie
0x18006d319  call    __security_check_cookie
0x18006d31e  lea     r11, [rsp+2A0h+var_10]
0x18006d326  mov     rbx, [r11+28h]
0x18006d32a  mov     rsi, [r11+30h]
0x18006d32e  mov     rdi, [r11+38h]
0x18006d332  mov     rsp, r11
0x18006d335  pop     r15
0x18006d337  pop     r14
0x18006d339  pop     rbp
0x18006d33a  retn
```
