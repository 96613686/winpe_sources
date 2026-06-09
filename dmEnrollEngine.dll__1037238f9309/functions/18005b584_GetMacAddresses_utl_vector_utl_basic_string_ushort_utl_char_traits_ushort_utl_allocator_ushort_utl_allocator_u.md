# GetMacAddresses(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)

- ea: `0x18005b584`
- end: `0x18005b7e7`
- name: `?GetMacAddresses@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `611`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800141d0`

## callees

- `0x18000d770`
- `0x180016508`
- `0x180017c08`
- `0x18002e1a0`
- `0x18004c594`
- `0x180059d54`
- `0x180059e40`
- `0x18005b584`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b6b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b6b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b6c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7c9`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18005b5c2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18005b5c2`
- `DEVOBJ!DevObjGetClassDevs` at `0x18005b5fa`
- `DEVOBJ!DevObjGetClassDevs` at `0x18005b5fa`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18005b656`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18005b656`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18005b68a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18005b717`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18005b68a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18005b717`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18005b61c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18005b79a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18005b7dd`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18005b61c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18005b79a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18005b7dd`

## pseudocode

```c
__int64 __fastcall GetMacAddresses(__int64 a1)
{
  __int64 DeviceInfoList; // rax
  __int64 v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned int i; // r14d
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  void *v13; // rcx
  SIZE_T dwBytes; // [rsp+30h] [rbp-39h] BYREF
  void *v15[4]; // [rsp+38h] [rbp-31h] BYREF
  _OWORD v16[2]; // [rsp+58h] [rbp-11h] BYREF
  _OWORD v17[3]; // [rsp+78h] [rbp+Fh] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
    return 2147942414LL;
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_NDIS_LAN_CLASS, 0, 18, 0, 0) )
    goto LABEL_3;
  for ( i = 0; ; ++i )
  {
    memset(v16, 0, sizeof(v16));
    LODWORD(v16[0]) = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(v3, 0, &GUID_NDIS_LAN_CLASS, i, v16) )
      break;
    LODWORD(dwBytes) = 0;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v3, v16, 0, 0, &dwBytes, 0)
      && GetLastError() == 122
      && (unsigned int)dwBytes >= 8 )
    {
      v8 = dwBytes;
      ProcessHeap = GetProcessHeap();
      v10 = HeapAlloc(ProcessHeap, 0, v8);
      CTContainer_PolicyHeapMem::DestroyMem(0);
      if ( !v10 )
      {
        v13 = 0;
        goto LABEL_23;
      }
      *v10 = 8;
      memset(v17, 0, sizeof(v17));
      LODWORD(v17[0]) = 48;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v3, v16, v10, (unsigned int)dwBytes, 0, v17) )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v15);
        if ( (int)GetMacAdressFromDriver(v10 + 1, v15) >= 0 )
        {
          v12 = *(_QWORD *)(a1 + 8);
          if ( v12 == *(_QWORD *)(a1 + 16)
            || !(unsigned __int8)utl::allocator_traits<utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::construct<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &>(
                                   v11,
                                   v12,
                                   v15) )
          {
            if ( !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_PushBackOne2<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &>(
                                     a1,
                                     v15) )
            {
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v15);
              v13 = v10;
LABEL_23:
              CTContainer_PolicyHeapMem::DestroyMem(v13);
              DevObjDestroyDeviceInfoList(v3);
              return 2147942414LL;
            }
          }
          else
          {
            *(_QWORD *)(a1 + 8) += 32LL;
          }
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v15);
      }
      CTContainer_PolicyHeapMem::DestroyMem(v10);
    }
  }
  if ( GetLastError() == 259 )
  {
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
0x18005b584  mov     [rsp-8+arg_8], rbx
0x18005b589  mov     [rsp-8+arg_10], rsi
0x18005b58e  push    rbp
0x18005b58f  push    rdi
0x18005b590  push    r14
0x18005b592  lea     rbp, [rsp-47h]
0x18005b597  sub     rsp, 0B0h
0x18005b59e  mov     rax, cs:__security_cookie
0x18005b5a5  xor     rax, rsp
0x18005b5a8  mov     [rbp+57h+var_18], rax
0x18005b5ac  mov     rsi, rcx
0x18005b5af  mov     [rsp+0C0h+var_A0], 0
0x18005b5b8  xor     ecx, ecx
0x18005b5ba  xor     r9d, r9d
0x18005b5bd  xor     r8d, r8d
0x18005b5c0  xor     edx, edx
0x18005b5c2  call    cs:__imp_DevObjCreateDeviceInfoList
0x18005b5c8  mov     rdi, rax
0x18005b5cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b5cf  jz      loc_18005B7A0
0x18005b5d5  mov     [rsp+0C0h+var_98], 0
0x18005b5de  lea     rdx, GUID_NDIS_LAN_CLASS
0x18005b5e5  mov     r9d, 12h
0x18005b5eb  mov     [rsp+0C0h+var_A0], 0
0x18005b5f4  xor     r8d, r8d
0x18005b5f7  mov     rcx, rax
0x18005b5fa  call    cs:__imp_DevObjGetClassDevs
0x18005b600  test    eax, eax
0x18005b602  jnz     short loc_18005B629
0x18005b604  call    cs:__imp_GetLastError
0x18005b60a  mov     ebx, eax
0x18005b60c  test    eax, eax
0x18005b60e  jle     short loc_18005B619
0x18005b610  movzx   ebx, ax
0x18005b613  or      ebx, 80070000h
0x18005b619  mov     rcx, rdi
0x18005b61c  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18005b622  mov     eax, ebx
0x18005b624  jmp     loc_18005B7A5
0x18005b629  xor     r14d, r14d
0x18005b62c  xorps   xmm0, xmm0
0x18005b62f  lea     rax, [rbp+57h+var_68]
0x18005b633  movups  [rbp+57h+var_68], xmm0
0x18005b637  mov     r9d, r14d
0x18005b63a  mov     dword ptr [rbp+57h+var_68], 20h ; ' '
0x18005b641  lea     r8, GUID_NDIS_LAN_CLASS
0x18005b648  mov     [rsp+0C0h+var_A0], rax
0x18005b64d  xor     edx, edx
0x18005b64f  mov     rcx, rdi
0x18005b652  movups  [rbp+57h+var_58], xmm0
0x18005b656  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18005b65c  test    eax, eax
0x18005b65e  jz      loc_18005B7C9
0x18005b664  lea     rax, [rbp+57h+dwBytes]
0x18005b668  mov     [rsp+0C0h+var_98], 0
0x18005b671  xor     r9d, r9d
0x18005b674  mov     [rsp+0C0h+var_A0], rax
0x18005b679  xor     r8d, r8d
0x18005b67c  mov     dword ptr [rbp+57h+dwBytes], 0
0x18005b683  lea     rdx, [rbp+57h+var_68]
0x18005b687  mov     rcx, rdi
0x18005b68a  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18005b690  test    eax, eax
0x18005b692  jnz     loc_18005B77A
0x18005b698  call    cs:__imp_GetLastError
0x18005b69e  cmp     eax, 7Ah ; 'z'
0x18005b6a1  jnz     loc_18005B77A
0x18005b6a7  cmp     dword ptr [rbp+57h+dwBytes], 8
0x18005b6ab  jb      loc_18005B77A
0x18005b6b1  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x18005b6b4  call    cs:__imp_GetProcessHeap
0x18005b6ba  mov     r8d, ebx; dwBytes
0x18005b6bd  xor     edx, edx; dwFlags
0x18005b6bf  mov     rcx, rax; hHeap
0x18005b6c2  call    cs:__imp_HeapAlloc
0x18005b6c8  xor     ecx, ecx; lpMem
0x18005b6ca  mov     rbx, rax
0x18005b6cd  call    ?DestroyMem@CTContainer_PolicyHeapMem@@SAHPEAX@Z; CTContainer_PolicyHeapMem::DestroyMem(void *)
0x18005b6d2  test    rbx, rbx
0x18005b6d5  jz      loc_18005B790
0x18005b6db  mov     dword ptr [rbx], 8
0x18005b6e1  lea     rax, [rbp+57h+var_48]
0x18005b6e5  mov     r9d, dword ptr [rbp+57h+dwBytes]
0x18005b6e9  lea     rdx, [rbp+57h+var_68]
0x18005b6ed  xorps   xmm0, xmm0
0x18005b6f0  mov     [rsp+0C0h+var_98], rax
0x18005b6f5  movups  [rbp+57h+var_48], xmm0
0x18005b6f9  mov     r8, rbx
0x18005b6fc  mov     dword ptr [rbp+57h+var_48], 30h ; '0'
0x18005b703  mov     rcx, rdi
0x18005b706  mov     [rsp+0C0h+var_A0], 0
0x18005b70f  movups  [rbp+57h+var_38], xmm0
0x18005b713  movups  [rbp+57h+var_28], xmm0
0x18005b717  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18005b71d  test    eax, eax
0x18005b71f  jz      short loc_18005B772
0x18005b721  lea     rcx, [rbp+57h+var_88]
0x18005b725  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18005b72a  lea     rdx, [rbp+57h+var_88]
0x18005b72e  lea     rcx, [rbx+4]
0x18005b732  call    ?GetMacAdressFromDriver@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetMacAdressFromDriver(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18005b737  test    eax, eax
0x18005b739  js      short loc_18005B769
0x18005b73b  mov     rdx, [rsi+8]
0x18005b73f  cmp     rdx, [rsi+10h]
0x18005b743  jz      short loc_18005B759
0x18005b745  lea     r8, [rbp+57h+var_88]
0x18005b749  call    ??$construct@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEBV12@@?$allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@AEBV31@@Z; utl::allocator_traits<utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::construct<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &>(utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18005b74e  test    al, al
0x18005b750  jz      short loc_18005B759
0x18005b752  add     qword ptr [rsi+8], 20h ; ' '
0x18005b757  jmp     short loc_18005B769
0x18005b759  lea     rdx, [rbp+57h+var_88]
0x18005b75d  mov     rcx, rsi
0x18005b760  call    ??$_PushBackOne2@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_PushBackOne2<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18005b765  test    al, al
0x18005b767  jz      short loc_18005B782
0x18005b769  lea     rcx, [rbp+57h+var_88]
0x18005b76d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005b772  mov     rcx, rbx; lpMem
0x18005b775  call    ?DestroyMem@CTContainer_PolicyHeapMem@@SAHPEAX@Z; CTContainer_PolicyHeapMem::DestroyMem(void *)
0x18005b77a  inc     r14d
0x18005b77d  jmp     loc_18005B62C
0x18005b782  lea     rcx, [rbp+57h+var_88]
0x18005b786  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005b78b  mov     rcx, rbx
0x18005b78e  jmp     short loc_18005B792
0x18005b790  xor     ecx, ecx; lpMem
0x18005b792  call    ?DestroyMem@CTContainer_PolicyHeapMem@@SAHPEAX@Z; CTContainer_PolicyHeapMem::DestroyMem(void *)
0x18005b797  mov     rcx, rdi
0x18005b79a  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18005b7a0  mov     eax, 8007000Eh
0x18005b7a5  mov     rcx, [rbp+57h+var_18]
0x18005b7a9  xor     rcx, rsp; StackCookie
0x18005b7ac  call    __security_check_cookie
0x18005b7b1  lea     r11, [rsp+0C0h+var_10]
0x18005b7b9  mov     rbx, [r11+28h]
0x18005b7bd  mov     rsi, [r11+30h]
0x18005b7c1  mov     rsp, r11
0x18005b7c4  pop     r14
0x18005b7c6  pop     rdi
0x18005b7c7  pop     rbp
0x18005b7c8  retn
0x18005b7c9  call    cs:__imp_GetLastError
0x18005b7cf  cmp     eax, 103h
0x18005b7d4  jnz     loc_18005B604
0x18005b7da  mov     rcx, rdi
0x18005b7dd  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18005b7e3  xor     eax, eax
0x18005b7e5  jmp     short loc_18005B7A5
```
