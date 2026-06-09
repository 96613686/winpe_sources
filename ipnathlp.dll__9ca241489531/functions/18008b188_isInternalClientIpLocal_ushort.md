# isInternalClientIpLocal(ushort *)

- ea: `0x18008b188`
- end: `0x18008b3fc`
- name: `?isInternalClientIpLocal@@YAEPEAG@Z`
- size: `628`
- prototype: `bool __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180088910`

## callees

- `0x180034eb8`
- `0x18008b188`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008b298`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008b298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b31b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b366`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b3d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b31b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b366`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008b3d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b329`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b329`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b3e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008b3e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b26b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b26b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18008b30b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18008b34a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18008b30b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18008b34a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008b21a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008b255`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008b21a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008b255`
- `ntdll!RtlIpv4StringToAddressW` at `0x18008b2d5`
- `ntdll!RtlIpv4StringToAddressW` at `0x18008b2d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b2a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b2a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b23d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b23d`

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
0x18008b188  push    rbp
0x18008b18a  push    rbx
0x18008b18b  push    rsi
0x18008b18c  push    rdi
0x18008b18d  push    r12
0x18008b18f  push    r14
0x18008b191  push    r15
0x18008b193  mov     rbp, rsp
0x18008b196  sub     rsp, 30h
0x18008b19a  xor     r15d, r15d
0x18008b19d  mov     rdi, rcx
0x18008b1a0  test    rcx, rcx
0x18008b1a3  jz      loc_18008B3EB
0x18008b1a9  cmp     r15w, [rcx]
0x18008b1ad  jz      loc_18008B3EB
0x18008b1b3  mov     sil, r15b
0x18008b1b6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008b1ba  inc     rbx
0x18008b1bd  cmp     [rcx+rbx*2], r15w
0x18008b1c2  jnz     short loc_18008B1BA
0x18008b1c4  lea     rcx, ds:2[rbx*2]; cb
0x18008b1cc  call    cs:__imp_CoTaskMemAlloc
0x18008b1d2  mov     r14, rax
0x18008b1d5  mov     r12d, 1
0x18008b1db  test    rax, rax
0x18008b1de  jz      loc_18008B2BF
0x18008b1e4  lea     rdx, [rbx+1]; unsigned __int64
0x18008b1e8  mov     r8, rdi; unsigned __int16 *
0x18008b1eb  mov     rcx, rax; unsigned __int16 *
0x18008b1ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008b1f3  mov     r11, r15
0x18008b1f6  cmp     r11, rbx
0x18008b1f9  jnb     short loc_18008B20D
0x18008b1fb  cmp     word ptr [r14+r11*2], 2Eh ; '.'
0x18008b201  jz      short loc_18008B208
0x18008b203  add     r11, r12
0x18008b206  jmp     short loc_18008B1F6
0x18008b208  mov     [r14+r11*2], r15w
0x18008b20d  lea     r8, [rbp+nSize]; nSize
0x18008b211  mov     [rbp+nSize], r15d
0x18008b215  xor     edx, edx; lpBuffer
0x18008b217  mov     ecx, r12d; NameType
0x18008b21a  call    cs:__imp_GetComputerNameExW
0x18008b220  test    eax, eax
0x18008b222  jnz     loc_18008B2AD
0x18008b228  call    cs:__imp_GetLastError
0x18008b22e  cmp     eax, 0EAh
0x18008b233  jnz     short loc_18008B27F
0x18008b235  mov     ecx, [rbp+nSize]
0x18008b238  inc     ecx
0x18008b23a  add     rcx, rcx; cb
0x18008b23d  call    cs:__imp_CoTaskMemAlloc
0x18008b243  mov     rbx, rax
0x18008b246  test    rax, rax
0x18008b249  jz      short loc_18008B278
0x18008b24b  lea     r8, [rbp+nSize]; nSize
0x18008b24f  mov     rdx, rax; lpBuffer
0x18008b252  mov     ecx, r12d; NameType
0x18008b255  call    cs:__imp_GetComputerNameExW
0x18008b25b  test    eax, eax
0x18008b25d  jnz     short loc_18008B273
0x18008b25f  mov     rcx, rbx; pv
0x18008b262  call    cs:__imp_CoTaskMemFree
0x18008b268  mov     rbx, r15
0x18008b26b  call    cs:__imp_GetLastError
0x18008b271  jmp     short loc_18008B282
0x18008b273  mov     eax, r15d
0x18008b276  jmp     short loc_18008B28E
0x18008b278  mov     eax, 8007000Eh
0x18008b27d  jmp     short loc_18008B28E
0x18008b27f  mov     rbx, r15
0x18008b282  test    eax, eax
0x18008b284  jle     short loc_18008B290
0x18008b286  movzx   eax, ax
0x18008b289  or      eax, 80070000h
0x18008b28e  test    eax, eax
0x18008b290  js      short loc_18008B2AD
0x18008b292  mov     rdx, rbx
0x18008b295  mov     rcx, r14
0x18008b298  call    cs:__imp__o__wcsicmp
0x18008b29e  test    eax, eax
0x18008b2a0  mov     rcx, rbx; pv
0x18008b2a3  setz    sil
0x18008b2a7  call    cs:__imp_CoTaskMemFree
0x18008b2ad  mov     rcx, r14; pv
0x18008b2b0  call    cs:__imp_CoTaskMemFree
0x18008b2b6  test    sil, sil
0x18008b2b9  jnz     loc_18008B3E6
0x18008b2bf  lea     r9, [rbp+Addr]; Addr
0x18008b2c3  mov     dword ptr [rbp+Addr.S_un], r15d
0x18008b2c7  lea     r8, [rbp+Terminator]; Terminator
0x18008b2cb  mov     [rbp+Terminator], r15
0x18008b2cf  mov     dl, r12b; Strict
0x18008b2d2  mov     rcx, rdi; S
0x18008b2d5  call    cs:__imp_RtlIpv4StringToAddressW
0x18008b2db  test    eax, eax
0x18008b2dd  js      loc_18008B3E6
0x18008b2e3  mov     rax, [rbp+Terminator]
0x18008b2e7  cmp     [rax], r15w
0x18008b2eb  jnz     loc_18008B3E6
0x18008b2f1  lea     rax, [rbp+nSize]
0x18008b2f5  mov     [rbp+nSize], r15d
0x18008b2f9  xor     r9d, r9d; AdapterAddresses
0x18008b2fc  mov     [rsp+30h+SizePointer], rax; SizePointer
0x18008b301  xor     r8d, r8d; Reserved
0x18008b304  xor     edx, edx; Flags
0x18008b306  xor     ecx, ecx; Family
0x18008b308  mov     rbx, r15
0x18008b30b  call    cs:__imp_GetAdaptersAddresses
0x18008b311  mov     edi, eax
0x18008b313  cmp     eax, 6Fh ; 'o'
0x18008b316  jnz     short loc_18008B352
0x18008b318  mov     ebx, [rbp+nSize]
0x18008b31b  call    cs:__imp_GetProcessHeap
0x18008b321  mov     r8d, ebx; dwBytes
0x18008b324  xor     edx, edx; dwFlags
0x18008b326  mov     rcx, rax; hHeap
0x18008b329  call    cs:__imp_HeapAlloc
0x18008b32f  mov     rbx, rax
0x18008b332  test    rax, rax
0x18008b335  jz      short loc_18008B398
0x18008b337  lea     rax, [rbp+nSize]
0x18008b33b  mov     r9, rbx; AdapterAddresses
0x18008b33e  xor     r8d, r8d; Reserved
0x18008b341  mov     [rsp+30h+SizePointer], rax; SizePointer
0x18008b346  xor     edx, edx; Flags
0x18008b348  xor     ecx, ecx; Family
0x18008b34a  call    cs:__imp_GetAdaptersAddresses
0x18008b350  mov     edi, eax
0x18008b352  test    edi, edi
0x18008b354  jz      short loc_18008B381
0x18008b356  jle     short loc_18008B361
0x18008b358  movzx   edi, di
0x18008b35b  or      edi, 80070000h
0x18008b361  test    rbx, rbx
0x18008b364  jz      short loc_18008B37D
0x18008b366  call    cs:__imp_GetProcessHeap
0x18008b36c  mov     r8, rbx; lpMem
0x18008b36f  xor     edx, edx; dwFlags
0x18008b371  mov     rcx, rax; hHeap
0x18008b374  call    cs:__imp_HeapFree
0x18008b37a  mov     rbx, r15
0x18008b37d  test    edi, edi
0x18008b37f  js      short loc_18008B3E6
0x18008b381  test    rbx, rbx
0x18008b384  jz      short loc_18008B3E6
0x18008b386  mov     r8d, dword ptr [rbp+Addr.S_un]
0x18008b38a  mov     rcx, rbx
0x18008b38d  cmp     sil, r12b
0x18008b390  jz      short loc_18008B3D2
0x18008b392  mov     rax, [rcx+18h]
0x18008b396  jmp     short loc_18008B3C4
0x18008b398  mov     edi, 8
0x18008b39d  jmp     short loc_18008B358
0x18008b39f  cmp     sil, r12b
0x18008b3a2  jz      short loc_18008B3C9
0x18008b3a4  mov     rdx, [rax+10h]
0x18008b3a8  mov     r9d, 2
0x18008b3ae  cmp     r9w, [rdx]
0x18008b3b2  jnz     short loc_18008B3C0
0x18008b3b4  cmp     r8d, [rdx+4]
0x18008b3b8  movzx   esi, sil
0x18008b3bc  cmovz   esi, r12d
0x18008b3c0  mov     rax, [rax+8]
0x18008b3c4  test    rax, rax
0x18008b3c7  jnz     short loc_18008B39F
0x18008b3c9  mov     rcx, [rcx+8]
0x18008b3cd  test    rcx, rcx
0x18008b3d0  jnz     short loc_18008B38D
0x18008b3d2  call    cs:__imp_GetProcessHeap
0x18008b3d8  mov     r8, rbx; lpMem
0x18008b3db  xor     edx, edx; dwFlags
0x18008b3dd  mov     rcx, rax; hHeap
0x18008b3e0  call    cs:__imp_HeapFree
0x18008b3e6  mov     al, sil
0x18008b3e9  jmp     short loc_18008B3ED
0x18008b3eb  xor     al, al
0x18008b3ed  add     rsp, 30h
0x18008b3f1  pop     r15
0x18008b3f3  pop     r14
0x18008b3f5  pop     r12
0x18008b3f7  pop     rdi
0x18008b3f8  pop     rsi
0x18008b3f9  pop     rbx
0x18008b3fa  pop     rbp
0x18008b3fb  retn
```
