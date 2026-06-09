# isInternalClientIpLocal(ushort *)

- ea: `0x180092118`
- end: `0x1800923ff`
- name: `?isInternalClientIpLocal@@YAEPEAG@Z`
- size: `743`
- prototype: `unsigned __int8 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008f5d0`

## callees

- `0x180037994`
- `0x180092118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092252`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092252`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800922f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092350`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800923c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800922f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092350`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800923c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092307`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092307`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800923dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800923dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009221f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009221f`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800922dd`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18009232e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800922dd`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18009232e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800921b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800921fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800921b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800921fd`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800922a1`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800922a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009215c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800921df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009215c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800921df`

## pseudocode

```c
bool __fastcall isInternalClientIpLocal(unsigned __int16 *a1)
{
  bool v2; // si
  unsigned __int64 v3; // rbx
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // r14
  unsigned __int64 i; // r11
  signed int LastError; // eax
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  signed int v10; // eax
  bool v11; // sf
  IP_ADAPTER_ADDRESSES_LH *v12; // rbx
  ULONG AdaptersAddresses; // edi
  DWORD v14; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  IP_ADAPTER_ADDRESSES_LH *v17; // rcx
  PIP_ADAPTER_UNICAST_ADDRESS_LH j; // rax
  LPSOCKADDR lpSockaddr; // rdx
  HANDLE v20; // rax
  DWORD nSize; // [rsp+70h] [rbp+40h] BYREF
  struct in_addr Addr; // [rsp+78h] [rbp+48h] BYREF
  LPCWSTR Terminator; // [rsp+80h] [rbp+50h] BYREF

  if ( a1 && *a1 )
  {
    v2 = 0;
    v3 = -1;
    do
      ++v3;
    while ( a1[v3] );
    v4 = (unsigned __int16 *)CoTaskMemAlloc(2 * v3 + 2);
    v5 = v4;
    if ( !v4 )
      goto LABEL_25;
    StringCchCopyW(v4, v3 + 1, a1);
    for ( i = 0; i < v3; ++i )
    {
      if ( v5[i] == 46 )
      {
        v5[i] = 0;
        break;
      }
    }
    nSize = 0;
    if ( GetComputerNameExW(ComputerNameDnsHostname, 0, &nSize) )
    {
LABEL_24:
      CoTaskMemFree(v5);
      if ( v2 )
        return v2;
LABEL_25:
      Addr = 0;
      Terminator = 0;
      if ( RtlIpv4StringToAddressW(a1, 1u, &Terminator, &Addr) < 0 || *Terminator )
        return v2;
      nSize = 0;
      v12 = 0;
      AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, 0, &nSize);
      if ( AdaptersAddresses == 111 )
      {
        v14 = nSize;
        ProcessHeap = GetProcessHeap();
        v12 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(ProcessHeap, 0, v14);
        if ( !v12 )
        {
LABEL_31:
          if ( v12 )
          {
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v12);
          }
          return v2;
        }
        AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, v12, &nSize);
      }
      if ( !AdaptersAddresses )
      {
        if ( v12 )
        {
          v17 = v12;
          do
          {
            if ( v2 )
              break;
            for ( j = v17->FirstUnicastAddress; j && !v2; j = j->Next )
            {
              lpSockaddr = j->Address.lpSockaddr;
              if ( lpSockaddr->sa_family == 2 && Addr == *(_DWORD *)&lpSockaddr->sa_data[2] )
                v2 = 1;
            }
            v17 = v17->Next;
          }
          while ( v17 );
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v12);
        }
        return v2;
      }
      goto LABEL_31;
    }
    LastError = GetLastError();
    if ( LastError == 234 )
    {
      v8 = (WCHAR *)CoTaskMemAlloc(2LL * (nSize + 1));
      v9 = v8;
      if ( !v8 )
      {
        v10 = -2147024882;
        goto LABEL_21;
      }
      if ( GetComputerNameExW(ComputerNameDnsHostname, v8, &nSize) )
      {
        v10 = 0;
        goto LABEL_21;
      }
      CoTaskMemFree(v9);
      v9 = 0;
      LastError = GetLastError();
    }
    else
    {
      v9 = 0;
    }
    v11 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_22;
    v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_21:
    v11 = v10 < 0;
LABEL_22:
    if ( !v11 )
    {
      v2 = (unsigned int)_o__wcsicmp(v5, v9) == 0;
      CoTaskMemFree(v9);
    }
    goto LABEL_24;
  }
  return 0;
}

```

## disassembly

```asm
0x180092118  push    rbp
0x18009211a  push    rbx
0x18009211b  push    rsi
0x18009211c  push    rdi
0x18009211d  push    r12
0x18009211f  push    r14
0x180092121  push    r15
0x180092123  mov     rbp, rsp
0x180092126  sub     rsp, 30h
0x18009212a  xor     r15d, r15d
0x18009212d  mov     rdi, rcx
0x180092130  test    rcx, rcx
0x180092133  jz      loc_1800923ED
0x180092139  cmp     r15w, [rcx]
0x18009213d  jz      loc_1800923ED
0x180092143  mov     sil, r15b
0x180092146  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009214a  inc     rbx
0x18009214d  cmp     [rcx+rbx*2], r15w
0x180092152  jnz     short loc_18009214A
0x180092154  lea     rcx, ds:2[rbx*2]; cb
0x18009215c  call    cs:__imp_CoTaskMemAlloc
0x180092163  nop     dword ptr [rax+rax+00h]
0x180092168  mov     r14, rax
0x18009216b  mov     r12d, 1
0x180092171  test    rax, rax
0x180092174  jz      loc_18009228B
0x18009217a  lea     rdx, [rbx+1]; unsigned __int64
0x18009217e  mov     r8, rdi; unsigned __int16 *
0x180092181  mov     rcx, rax; unsigned __int16 *
0x180092184  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180092189  mov     r11, r15
0x18009218c  cmp     r11, rbx
0x18009218f  jnb     short loc_1800921A3
0x180092191  cmp     word ptr [r14+r11*2], 2Eh ; '.'
0x180092197  jz      short loc_18009219E
0x180092199  add     r11, r12
0x18009219c  jmp     short loc_18009218C
0x18009219e  mov     [r14+r11*2], r15w
0x1800921a3  lea     r8, [rbp+nSize]; nSize
0x1800921a7  mov     [rbp+nSize], r15d
0x1800921ab  xor     edx, edx; lpBuffer
0x1800921ad  mov     ecx, r12d; NameType
0x1800921b0  call    cs:__imp_GetComputerNameExW
0x1800921b7  nop     dword ptr [rax+rax+00h]
0x1800921bc  test    eax, eax
0x1800921be  jnz     loc_180092273
0x1800921c4  call    cs:__imp_GetLastError
0x1800921cb  nop     dword ptr [rax+rax+00h]
0x1800921d0  cmp     eax, 0EAh
0x1800921d5  jnz     short loc_180092239
0x1800921d7  mov     ecx, [rbp+nSize]
0x1800921da  inc     ecx
0x1800921dc  add     rcx, rcx; cb
0x1800921df  call    cs:__imp_CoTaskMemAlloc
0x1800921e6  nop     dword ptr [rax+rax+00h]
0x1800921eb  mov     rbx, rax
0x1800921ee  test    rax, rax
0x1800921f1  jz      short loc_180092232
0x1800921f3  lea     r8, [rbp+nSize]; nSize
0x1800921f7  mov     rdx, rax; lpBuffer
0x1800921fa  mov     ecx, r12d; NameType
0x1800921fd  call    cs:__imp_GetComputerNameExW
0x180092204  nop     dword ptr [rax+rax+00h]
0x180092209  test    eax, eax
0x18009220b  jnz     short loc_18009222D
0x18009220d  mov     rcx, rbx; pv
0x180092210  call    cs:__imp_CoTaskMemFree
0x180092217  nop     dword ptr [rax+rax+00h]
0x18009221c  mov     rbx, r15
0x18009221f  call    cs:__imp_GetLastError
0x180092226  nop     dword ptr [rax+rax+00h]
0x18009222b  jmp     short loc_18009223C
0x18009222d  mov     eax, r15d
0x180092230  jmp     short loc_180092248
0x180092232  mov     eax, 8007000Eh
0x180092237  jmp     short loc_180092248
0x180092239  mov     rbx, r15
0x18009223c  test    eax, eax
0x18009223e  jle     short loc_18009224A
0x180092240  movzx   eax, ax
0x180092243  or      eax, 80070000h
0x180092248  test    eax, eax
0x18009224a  js      short loc_180092273
0x18009224c  mov     rdx, rbx
0x18009224f  mov     rcx, r14
0x180092252  call    cs:__imp__o__wcsicmp
0x180092259  nop     dword ptr [rax+rax+00h]
0x18009225e  test    eax, eax
0x180092260  mov     rcx, rbx; pv
0x180092263  setz    sil
0x180092267  call    cs:__imp_CoTaskMemFree
0x18009226e  nop     dword ptr [rax+rax+00h]
0x180092273  mov     rcx, r14; pv
0x180092276  call    cs:__imp_CoTaskMemFree
0x18009227d  nop     dword ptr [rax+rax+00h]
0x180092282  test    sil, sil
0x180092285  jnz     loc_1800923E8
0x18009228b  lea     r9, [rbp+Addr]; Addr
0x18009228f  mov     dword ptr [rbp+Addr.S_un], r15d
0x180092293  lea     r8, [rbp+Terminator]; Terminator
0x180092297  mov     [rbp+Terminator], r15
0x18009229b  mov     dl, r12b; Strict
0x18009229e  mov     rcx, rdi; S
0x1800922a1  call    cs:__imp_RtlIpv4StringToAddressW
0x1800922a8  nop     dword ptr [rax+rax+00h]
0x1800922ad  test    eax, eax
0x1800922af  js      loc_1800923E8
0x1800922b5  mov     rax, [rbp+Terminator]
0x1800922b9  cmp     [rax], r15w
0x1800922bd  jnz     loc_1800923E8
0x1800922c3  lea     rax, [rbp+nSize]
0x1800922c7  mov     [rbp+nSize], r15d
0x1800922cb  xor     r9d, r9d; AdapterAddresses
0x1800922ce  mov     [rsp+30h+SizePointer], rax; SizePointer
0x1800922d3  xor     r8d, r8d; Reserved
0x1800922d6  xor     edx, edx; Flags
0x1800922d8  xor     ecx, ecx; Family
0x1800922da  mov     rbx, r15
0x1800922dd  call    cs:__imp_GetAdaptersAddresses
0x1800922e4  nop     dword ptr [rax+rax+00h]
0x1800922e9  mov     edi, eax
0x1800922eb  cmp     eax, 6Fh ; 'o'
0x1800922ee  jnz     short loc_18009233C
0x1800922f0  mov     ebx, [rbp+nSize]
0x1800922f3  call    cs:__imp_GetProcessHeap
0x1800922fa  nop     dword ptr [rax+rax+00h]
0x1800922ff  mov     r8d, ebx; dwBytes
0x180092302  xor     edx, edx; dwFlags
0x180092304  mov     rcx, rax; hHeap
0x180092307  call    cs:__imp_HeapAlloc
0x18009230e  nop     dword ptr [rax+rax+00h]
0x180092313  mov     rbx, rax
0x180092316  test    rax, rax
0x180092319  jz      short loc_18009238E
0x18009231b  lea     rax, [rbp+nSize]
0x18009231f  mov     r9, rbx; AdapterAddresses
0x180092322  xor     r8d, r8d; Reserved
0x180092325  mov     [rsp+30h+SizePointer], rax; SizePointer
0x18009232a  xor     edx, edx; Flags
0x18009232c  xor     ecx, ecx; Family
0x18009232e  call    cs:__imp_GetAdaptersAddresses
0x180092335  nop     dword ptr [rax+rax+00h]
0x18009233a  mov     edi, eax
0x18009233c  test    edi, edi
0x18009233e  jz      short loc_180092377
0x180092340  jle     short loc_18009234B
0x180092342  movzx   edi, di
0x180092345  or      edi, 80070000h
0x18009234b  test    rbx, rbx
0x18009234e  jz      short loc_180092373
0x180092350  call    cs:__imp_GetProcessHeap
0x180092357  nop     dword ptr [rax+rax+00h]
0x18009235c  mov     r8, rbx; lpMem
0x18009235f  xor     edx, edx; dwFlags
0x180092361  mov     rcx, rax; hHeap
0x180092364  call    cs:__imp_HeapFree
0x18009236b  nop     dword ptr [rax+rax+00h]
0x180092370  mov     rbx, r15
0x180092373  test    edi, edi
0x180092375  js      short loc_1800923E8
0x180092377  test    rbx, rbx
0x18009237a  jz      short loc_1800923E8
0x18009237c  mov     r8d, dword ptr [rbp+Addr.S_un]
0x180092380  mov     rcx, rbx
0x180092383  cmp     sil, r12b
0x180092386  jz      short loc_1800923C8
0x180092388  mov     rax, [rcx+18h]
0x18009238c  jmp     short loc_1800923BA
0x18009238e  mov     edi, 8
0x180092393  jmp     short loc_180092342
0x180092395  cmp     sil, r12b
0x180092398  jz      short loc_1800923BF
0x18009239a  mov     rdx, [rax+10h]
0x18009239e  mov     r9d, 2
0x1800923a4  cmp     r9w, [rdx]
0x1800923a8  jnz     short loc_1800923B6
0x1800923aa  cmp     r8d, [rdx+4]
0x1800923ae  movzx   esi, sil
0x1800923b2  cmovz   esi, r12d
0x1800923b6  mov     rax, [rax+8]
0x1800923ba  test    rax, rax
0x1800923bd  jnz     short loc_180092395
0x1800923bf  mov     rcx, [rcx+8]
0x1800923c3  test    rcx, rcx
0x1800923c6  jnz     short loc_180092383
0x1800923c8  call    cs:__imp_GetProcessHeap
0x1800923cf  nop     dword ptr [rax+rax+00h]
0x1800923d4  mov     r8, rbx; lpMem
0x1800923d7  xor     edx, edx; dwFlags
0x1800923d9  mov     rcx, rax; hHeap
0x1800923dc  call    cs:__imp_HeapFree
0x1800923e3  nop     dword ptr [rax+rax+00h]
0x1800923e8  mov     al, sil
0x1800923eb  jmp     short loc_1800923EF
0x1800923ed  xor     al, al
0x1800923ef  add     rsp, 30h
0x1800923f3  pop     r15
0x1800923f5  pop     r14
0x1800923f7  pop     r12
0x1800923f9  pop     rdi
0x1800923fa  pop     rsi
0x1800923fb  pop     rbx
0x1800923fc  pop     rbp
0x1800923fd  retn
```
