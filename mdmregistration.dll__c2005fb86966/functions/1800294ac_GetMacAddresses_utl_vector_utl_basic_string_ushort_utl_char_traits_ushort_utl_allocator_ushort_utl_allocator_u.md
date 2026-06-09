# GetMacAddresses(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)

- ea: `0x1800294ac`
- end: `0x180029797`
- name: `?GetMacAddresses@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180022e74`

## callees

- `0x1800026d0`
- `0x180002ae0`
- `0x1800294ac`
- `0x1800297a0`
- `0x18002cd68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800295e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800295e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800296af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029752`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800296af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800295cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002969b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002973e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800295cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002969b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002973e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296fb`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800294ea`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800294ea`
- `DEVOBJ!DevObjGetClassDevs` at `0x180029528`
- `DEVOBJ!DevObjGetClassDevs` at `0x180029528`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800296e7`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800296e7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180029599`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180029637`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180029599`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180029637`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180029556`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180029715`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180029761`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180029556`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180029715`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180029761`

## pseudocode

```c
__int64 __fastcall GetMacAddresses(__int64 a1)
{
  __int64 DeviceInfoList; // rax
  __int64 v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned int v7; // esi
  __int64 i; // r9
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  char *v11; // rax
  char *v12; // rbx
  __int64 v13; // rcx
  HANDLE v14; // rax
  HANDLE v15; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-39h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-31h] BYREF
  _WORD v18[8]; // [rsp+48h] [rbp-21h] BYREF
  _OWORD v19[2]; // [rsp+58h] [rbp-11h] BYREF
  _OWORD v20[3]; // [rsp+78h] [rbp+Fh] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
    return 2147942414LL;
  if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_NDIS_LAN_CLASS, 0, 18, 0, 0) )
  {
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      memset(v19, 0, sizeof(v19));
      LODWORD(v19[0]) = 32;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v3, 0, &GUID_NDIS_LAN_CLASS, i, v19) )
        break;
      LODWORD(dwBytes) = 0;
      if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v3, v19, 0, 0, &dwBytes, 0)
        && GetLastError() == 122
        && (unsigned int)dwBytes >= 8 )
      {
        v9 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v11 = (char *)HeapAlloc(ProcessHeap, 0, v9);
        v12 = v11;
        v13 = v3;
        if ( !v11 )
          goto LABEL_24;
        *(_DWORD *)v11 = 8;
        memset(v20, 0, sizeof(v20));
        LODWORD(v20[0]) = 48;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v3, v19, v11, (unsigned int)dwBytes, 0, v20) )
        {
          Block[0] = v18;
          Block[1] = v18;
          v18[0] = 0;
          if ( (int)GetMacAdressFromDriver(v12 + 4, Block) >= 0
            && !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
                                   a1,
                                   Block) )
          {
            if ( Block[0] != v18 )
              operator delete(Block[0]);
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v12);
            v13 = v3;
LABEL_24:
            DevObjDestroyDeviceInfoList(v13);
            return 2147942414LL;
          }
          if ( Block[0] != v18 )
            operator delete(Block[0]);
        }
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v12);
      }
      ++v7;
    }
    if ( GetLastError() != 259 )
      goto LABEL_3;
    DevObjDestroyDeviceInfoList(v3);
    return 0;
  }
  else
  {
LABEL_3:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    DevObjDestroyDeviceInfoList(v3);
    return v5;
  }
}

```

## disassembly

```asm
0x1800294ac  mov     [rsp-8+arg_8], rbx
0x1800294b1  mov     [rsp-8+arg_10], rsi
0x1800294b6  push    rbp
0x1800294b7  push    rdi
0x1800294b8  push    r14
0x1800294ba  lea     rbp, [rsp-47h]
0x1800294bf  sub     rsp, 0B0h
0x1800294c6  mov     rax, cs:__security_cookie
0x1800294cd  xor     rax, rsp
0x1800294d0  mov     [rbp+57h+var_18], rax
0x1800294d4  mov     r14, rcx
0x1800294d7  mov     [rsp+0C0h+var_A0], 0
0x1800294e0  xor     ecx, ecx
0x1800294e2  xor     r9d, r9d
0x1800294e5  xor     r8d, r8d
0x1800294e8  xor     edx, edx
0x1800294ea  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800294f1  nop     dword ptr [rax+rax+00h]
0x1800294f6  mov     rdi, rax
0x1800294f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800294fd  jz      loc_18002976D
0x180029503  mov     [rsp+0C0h+var_98], 0
0x18002950c  lea     rdx, GUID_NDIS_LAN_CLASS
0x180029513  mov     r9d, 12h
0x180029519  mov     [rsp+0C0h+var_A0], 0
0x180029522  xor     r8d, r8d
0x180029525  mov     rcx, rax
0x180029528  call    cs:__imp_DevObjGetClassDevs
0x18002952f  nop     dword ptr [rax+rax+00h]
0x180029534  test    eax, eax
0x180029536  jnz     short loc_180029569
0x180029538  call    cs:__imp_GetLastError
0x18002953f  nop     dword ptr [rax+rax+00h]
0x180029544  mov     ebx, eax
0x180029546  test    eax, eax
0x180029548  jle     short loc_180029553
0x18002954a  movzx   ebx, ax
0x18002954d  or      ebx, 80070000h
0x180029553  mov     rcx, rdi
0x180029556  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002955d  nop     dword ptr [rax+rax+00h]
0x180029562  mov     eax, ebx
0x180029564  jmp     loc_180029772
0x180029569  xor     esi, esi
0x18002956b  xor     r9d, r9d
0x18002956e  jmp     loc_1800296C0
0x180029573  lea     rax, [rbp+57h+dwBytes]
0x180029577  mov     [rsp+0C0h+var_98], 0
0x180029580  xor     r9d, r9d
0x180029583  mov     [rsp+0C0h+var_A0], rax
0x180029588  xor     r8d, r8d
0x18002958b  mov     dword ptr [rbp+57h+dwBytes], 0
0x180029592  lea     rdx, [rbp+57h+var_68]
0x180029596  mov     rcx, rdi
0x180029599  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800295a0  nop     dword ptr [rax+rax+00h]
0x1800295a5  test    eax, eax
0x1800295a7  jnz     loc_1800296BB
0x1800295ad  call    cs:__imp_GetLastError
0x1800295b4  nop     dword ptr [rax+rax+00h]
0x1800295b9  cmp     eax, 7Ah ; 'z'
0x1800295bc  jnz     loc_1800296BB
0x1800295c2  cmp     dword ptr [rbp+57h+dwBytes], 8
0x1800295c6  jb      loc_1800296BB
0x1800295cc  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x1800295cf  call    cs:__imp_GetProcessHeap
0x1800295d6  nop     dword ptr [rax+rax+00h]
0x1800295db  mov     r8d, ebx; dwBytes
0x1800295de  xor     edx, edx; dwFlags
0x1800295e0  mov     rcx, rax; hHeap
0x1800295e3  call    cs:__imp_HeapAlloc
0x1800295ea  nop     dword ptr [rax+rax+00h]
0x1800295ef  mov     rbx, rax
0x1800295f2  mov     rcx, rdi
0x1800295f5  test    rax, rax
0x1800295f8  jz      loc_180029761
0x1800295fe  mov     dword ptr [rax], 8
0x180029604  lea     rdx, [rbp+57h+var_68]
0x180029608  mov     r9d, dword ptr [rbp+57h+dwBytes]
0x18002960c  lea     rax, [rbp+57h+var_48]
0x180029610  xorps   xmm0, xmm0
0x180029613  mov     [rsp+0C0h+var_98], rax
0x180029618  movups  [rbp+57h+var_48], xmm0
0x18002961c  mov     r8, rbx
0x18002961f  mov     [rsp+0C0h+var_A0], 0
0x180029628  movups  [rbp+57h+var_38], xmm0
0x18002962c  mov     dword ptr [rbp+57h+var_48], 30h ; '0'
0x180029633  movups  [rbp+57h+var_28], xmm0
0x180029637  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18002963e  nop     dword ptr [rax+rax+00h]
0x180029643  test    eax, eax
0x180029645  jz      short loc_18002969B
0x180029647  lea     rax, [rbp+57h+var_78]
0x18002964b  mov     [rbp+57h+Block], rax
0x18002964f  lea     rcx, [rbx+4]
0x180029653  lea     rax, [rbp+57h+var_78]
0x180029657  mov     [rbp+57h+var_80], rax
0x18002965b  lea     rdx, [rbp+57h+Block]
0x18002965f  xor     eax, eax
0x180029661  mov     [rbp+57h+var_78], ax
0x180029665  call    ?GetMacAdressFromDriver@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetMacAdressFromDriver(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002966a  test    eax, eax
0x18002966c  js      short loc_180029682
0x18002966e  lea     rdx, [rbp+57h+Block]
0x180029672  mov     rcx, r14
0x180029675  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18002967a  test    al, al
0x18002967c  jz      loc_180029725
0x180029682  mov     rcx, [rbp+57h+Block]; Block
0x180029686  lea     rax, [rbp+57h+var_78]
0x18002968a  cmp     rcx, rax
0x18002968d  jz      short loc_18002969B
0x18002968f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029696  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002969b  call    cs:__imp_GetProcessHeap
0x1800296a2  nop     dword ptr [rax+rax+00h]
0x1800296a7  mov     r8, rbx; lpMem
0x1800296aa  xor     edx, edx; dwFlags
0x1800296ac  mov     rcx, rax; hHeap
0x1800296af  call    cs:__imp_HeapFree
0x1800296b6  nop     dword ptr [rax+rax+00h]
0x1800296bb  inc     esi
0x1800296bd  mov     r9d, esi
0x1800296c0  xorps   xmm0, xmm0
0x1800296c3  lea     rax, [rbp+57h+var_68]
0x1800296c7  movups  [rbp+57h+var_68], xmm0
0x1800296cb  lea     r8, GUID_NDIS_LAN_CLASS
0x1800296d2  mov     dword ptr [rbp+57h+var_68], 20h ; ' '
0x1800296d9  xor     edx, edx
0x1800296db  mov     [rsp+0C0h+var_A0], rax
0x1800296e0  mov     rcx, rdi
0x1800296e3  movups  [rbp+57h+var_58], xmm0
0x1800296e7  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800296ee  nop     dword ptr [rax+rax+00h]
0x1800296f3  test    eax, eax
0x1800296f5  jnz     loc_180029573
0x1800296fb  call    cs:__imp_GetLastError
0x180029702  nop     dword ptr [rax+rax+00h]
0x180029707  cmp     eax, 103h
0x18002970c  jnz     loc_180029538
0x180029712  mov     rcx, rdi
0x180029715  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002971c  nop     dword ptr [rax+rax+00h]
0x180029721  xor     eax, eax
0x180029723  jmp     short loc_180029772
0x180029725  mov     rcx, [rbp+57h+Block]; Block
0x180029729  lea     rax, [rbp+57h+var_78]
0x18002972d  cmp     rcx, rax
0x180029730  jz      short loc_18002973E
0x180029732  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029739  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002973e  call    cs:__imp_GetProcessHeap
0x180029745  nop     dword ptr [rax+rax+00h]
0x18002974a  mov     r8, rbx; lpMem
0x18002974d  xor     edx, edx; dwFlags
0x18002974f  mov     rcx, rax; hHeap
0x180029752  call    cs:__imp_HeapFree
0x180029759  nop     dword ptr [rax+rax+00h]
0x18002975e  mov     rcx, rdi
0x180029761  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180029768  nop     dword ptr [rax+rax+00h]
0x18002976d  mov     eax, 8007000Eh
0x180029772  mov     rcx, [rbp+57h+var_18]
0x180029776  xor     rcx, rsp; StackCookie
0x180029779  call    __security_check_cookie
0x18002977e  lea     r11, [rsp+0C0h+var_10]
0x180029786  mov     rbx, [r11+28h]
0x18002978a  mov     rsi, [r11+30h]
0x18002978e  mov     rsp, r11
0x180029791  pop     r14
0x180029793  pop     rdi
0x180029794  pop     rbp
0x180029795  retn
```
