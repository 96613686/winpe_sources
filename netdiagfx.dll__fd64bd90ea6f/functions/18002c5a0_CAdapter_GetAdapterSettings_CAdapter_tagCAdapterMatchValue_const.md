# CAdapter::_GetAdapterSettings(CAdapter::tagCAdapterMatchValue const *)

- ea: `0x18002c5a0`
- end: `0x18002c6d9`
- name: `?_GetAdapterSettings@CAdapter@@IEAAJPEBUtagCAdapterMatchValue@1@@Z`
- size: `313`
- prototype: `__int64 __fastcall(LPVOID *this, const struct CAdapter::tagCAdapterMatchValue *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002503c`

## callees

- `0x18002c5a0`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18002c670`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18002c670`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18002c65c`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18002c65c`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002c5e7`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002c5e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002c5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002c5ff`

## pseudocode

```c
__int64 __fastcall CAdapter::_GetAdapterSettings(LPVOID *this, const struct CAdapter::tagCAdapterMatchValue *a2)
{
  IP_ADAPTER_ADDRESSES_LH *v4; // rax
  signed int AdaptersAddresses; // eax
  signed int v6; // ebx
  const GUID *v7; // rcx
  ULONG v8; // eax
  NTSTATUS v9; // eax
  LPVOID v10; // rcx
  ULONG InterfaceIndex; // [rsp+50h] [rbp+8h] BYREF
  ULONG SizePointer; // [rsp+60h] [rbp+18h] BYREF
  NET_LUID InterfaceLuid; // [rsp+68h] [rbp+20h] BYREF

  CoTaskMemFree(*this);
  v4 = 0;
  *this = 0;
  this[1] = 0;
  SizePointer = 0;
  while ( 1 )
  {
    AdaptersAddresses = GetAdaptersAddresses(0, 0x86u, 0, v4, &SizePointer);
    v6 = AdaptersAddresses;
    if ( !AdaptersAddresses )
    {
      v6 = 0;
      goto LABEL_11;
    }
    if ( AdaptersAddresses != 111 )
      break;
    v4 = (IP_ADAPTER_ADDRESSES_LH *)CoTaskMemRealloc(*this, SizePointer);
    *this = v4;
    if ( !v4 )
    {
      v6 = -2147024882;
LABEL_9:
      CoTaskMemFree(*this);
      *this = 0;
      this[1] = 0;
      return (unsigned int)v6;
    }
  }
  if ( AdaptersAddresses > 0 )
    v6 = (unsigned __int16)AdaptersAddresses | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_9;
LABEL_11:
  v7 = *(const GUID **)a2;
  v8 = 0;
  InterfaceIndex = 0;
  if ( v7 )
  {
    InterfaceLuid.Value = 0;
    v9 = ConvertInterfaceGuidToLuid(v7, &InterfaceLuid);
    if ( v9 || (v9 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex)) != 0 )
    {
      if ( v9 == 87 )
        return (unsigned int)-2147024894;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      else
        v6 = v9;
    }
    v8 = InterfaceIndex;
  }
  else if ( *((_DWORD *)a2 + 2) )
  {
    v8 = *((_DWORD *)a2 + 2);
    InterfaceIndex = v8;
  }
  if ( v6 >= 0 )
  {
    v10 = *this;
    v6 = -2147024894;
    while ( v10 )
    {
      if ( *((_DWORD *)v10 + 1) == v8 || !v8 )
      {
        this[1] = v10;
        return 0;
      }
      v10 = (LPVOID)*((_QWORD *)v10 + 1);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c5a0  push    rbx
0x18002c5a2  push    rsi
0x18002c5a3  push    rdi
0x18002c5a4  sub     rsp, 30h
0x18002c5a8  mov     rdi, rcx
0x18002c5ab  mov     rsi, rdx
0x18002c5ae  mov     rcx, [rcx]; pv
0x18002c5b1  call    cs:__imp_CoTaskMemFree
0x18002c5b7  xor     eax, eax
0x18002c5b9  mov     qword ptr [rdi], 0
0x18002c5c0  mov     qword ptr [rdi+8], 0
0x18002c5c8  mov     [rsp+48h+arg_10], 0
0x18002c5d0  lea     rcx, [rsp+48h+arg_10]
0x18002c5d5  mov     r9, rax; AdapterAddresses
0x18002c5d8  mov     [rsp+48h+SizePointer], rcx; SizePointer
0x18002c5dd  xor     r8d, r8d; Reserved
0x18002c5e0  xor     ecx, ecx; Family
0x18002c5e2  mov     edx, 86h; Flags
0x18002c5e7  call    cs:__imp_GetAdaptersAddresses
0x18002c5ed  mov     ebx, eax
0x18002c5ef  test    eax, eax
0x18002c5f1  jz      short loc_18002C642
0x18002c5f3  cmp     eax, 6Fh ; 'o'
0x18002c5f6  jnz     short loc_18002C614
0x18002c5f8  mov     edx, [rsp+48h+arg_10]; cb
0x18002c5fc  mov     rcx, [rdi]; pv
0x18002c5ff  call    cs:__imp_CoTaskMemRealloc
0x18002c605  mov     [rdi], rax
0x18002c608  test    rax, rax
0x18002c60b  jnz     short loc_18002C5D0
0x18002c60d  mov     ebx, 8007000Eh
0x18002c612  jmp     short loc_18002C625
0x18002c614  test    eax, eax
0x18002c616  jle     short loc_18002C621
0x18002c618  movzx   ebx, ax
0x18002c61b  or      ebx, 80070000h
0x18002c621  test    ebx, ebx
0x18002c623  jns     short loc_18002C644
0x18002c625  mov     rcx, [rdi]; pv
0x18002c628  call    cs:__imp_CoTaskMemFree
0x18002c62e  mov     qword ptr [rdi], 0
0x18002c635  mov     qword ptr [rdi+8], 0
0x18002c63d  jmp     loc_18002C6CF
0x18002c642  xor     ebx, ebx
0x18002c644  mov     rcx, [rsi]; InterfaceGuid
0x18002c647  xor     eax, eax
0x18002c649  mov     [rsp+48h+InterfaceIndex], eax
0x18002c64d  test    rcx, rcx
0x18002c650  jz      short loc_18002C69D
0x18002c652  lea     rdx, [rsp+48h+InterfaceLuid]; InterfaceLuid
0x18002c657  mov     qword ptr [rsp+48h+InterfaceLuid], rax
0x18002c65c  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18002c662  test    eax, eax
0x18002c664  jnz     short loc_18002C67A
0x18002c666  lea     rdx, [rsp+48h+InterfaceIndex]; InterfaceIndex
0x18002c66b  lea     rcx, [rsp+48h+InterfaceLuid]; InterfaceLuid
0x18002c670  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18002c676  test    eax, eax
0x18002c678  jz      short loc_18002C697
0x18002c67a  cmp     eax, 57h ; 'W'
0x18002c67d  jnz     short loc_18002C686
0x18002c67f  mov     ebx, 80070002h
0x18002c684  jmp     short loc_18002C6CF
0x18002c686  test    eax, eax
0x18002c688  jg      short loc_18002C68E
0x18002c68a  mov     ebx, eax
0x18002c68c  jmp     short loc_18002C697
0x18002c68e  movzx   ebx, ax
0x18002c691  or      ebx, 80070000h
0x18002c697  mov     eax, [rsp+48h+InterfaceIndex]
0x18002c69b  jmp     short loc_18002C6A9
0x18002c69d  cmp     [rsi+8], eax
0x18002c6a0  jz      short loc_18002C6A9
0x18002c6a2  mov     eax, [rsi+8]
0x18002c6a5  mov     [rsp+48h+InterfaceIndex], eax
0x18002c6a9  test    ebx, ebx
0x18002c6ab  js      short loc_18002C6CF
0x18002c6ad  mov     rcx, [rdi]
0x18002c6b0  mov     ebx, 80070002h
0x18002c6b5  test    rcx, rcx
0x18002c6b8  jz      short loc_18002C6CF
0x18002c6ba  cmp     [rcx+4], eax
0x18002c6bd  jz      short loc_18002C6C9
0x18002c6bf  test    eax, eax
0x18002c6c1  jz      short loc_18002C6C9
0x18002c6c3  mov     rcx, [rcx+8]
0x18002c6c7  jmp     short loc_18002C6B5
0x18002c6c9  mov     [rdi+8], rcx
0x18002c6cd  xor     ebx, ebx
0x18002c6cf  mov     eax, ebx
0x18002c6d1  add     rsp, 30h
0x18002c6d5  pop     rdi
0x18002c6d6  pop     rsi
0x18002c6d7  pop     rbx
0x18002c6d8  retn
```
