# CDiskPnpMonitor::RegisterExistingDisks(void)

- ea: `0x18001a6bc`
- end: `0x18001a99a`
- name: `?RegisterExistingDisks@CDiskPnpMonitor@@AEAAJXZ`
- size: `734`
- prototype: `__int64 __fastcall(CDiskPnpMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18001ae24`

## callees

- `0x1800032f8`
- `0x1800034f8`
- `0x180006688`
- `0x1800068b4`
- `0x1800128c8`
- `0x1800161f0`
- `0x180018bd4`
- `0x180019d5c`
- `0x18001a6bc`

## import_xrefs

- `msvcrt!free` at `0x18001a7f9`
- `msvcrt!free` at `0x18001a8ae`
- `msvcrt!free` at `0x18001a92a`
- `msvcrt!free` at `0x18001a979`
- `msvcrt!free` at `0x18001a7f9`
- `msvcrt!free` at `0x18001a8ae`
- `msvcrt!free` at `0x18001a92a`
- `msvcrt!free` at `0x18001a979`
- `SETUPAPI!CM_Get_Device_Interface_ListW` at `0x18001a7eb`
- `SETUPAPI!CM_Get_Device_Interface_ListW` at `0x18001a7eb`
- `SETUPAPI!CM_Get_Device_Interface_List_SizeW` at `0x18001a78e`
- `SETUPAPI!CM_Get_Device_Interface_List_SizeW` at `0x18001a78e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001a7a2`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001a8c9`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001a7a2`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001a8c9`

## string_xrefs

- `0x18001a95f`: `Hr = CONFIGRET_HR( CM_Get_Device_Interface_List_Size( &ListSize, const_cast<LPGUID>(&GUID_DEVINTERFACE_DISK), nullptr, CM_GET_DEVICE_INTERFACE_LIST_PRESENT ) )`
- `0x18001a906`: `Hr = CONFIGRET_HR( ConfigRet )`

## pseudocode

```c
__int64 __fastcall CDiskPnpMonitor::RegisterExistingDisks(CDiskPnpMonitor *this)
{
  __int64 v2; // r8
  USHORT v3; // dx
  USHORT Length; // cx
  USHORT v5; // ax
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int v7; // eax
  signed int v8; // ebx
  char v9; // al
  PZZWSTR v10; // rbx
  CONFIGRET Device_Interface_ListW; // eax
  PZZWSTR i; // rdi
  int v13; // esi
  __int64 v14; // rax
  signed int v16; // eax
  signed int v17; // edi
  const char *v18; // [rsp+30h] [rbp-20h] BYREF
  int v19; // [rsp+38h] [rbp-18h]
  USHORT v20; // [rsp+40h] [rbp-10h]
  USHORT v21; // [rsp+42h] [rbp-Eh]
  int v22; // [rsp+44h] [rbp-Ch]
  char *v23; // [rsp+48h] [rbp-8h]
  ULONG pulLen; // [rsp+98h] [rbp+48h] BYREF
  PZZWSTR Buffer; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v2 + 16) = "CDiskPnpMonitor::RegisterExistingDisks";
  v18 = "CDiskPnpMonitor::RegisterExistingDisks";
  v3 = ++*(_WORD *)(v2 + 8);
  Length = GlobalIndentString.Length;
  v5 = GlobalIndentString.Length;
  if ( v3 < GlobalIndentString.Length )
    v5 = *(_WORD *)(v2 + 8);
  v20 = v5;
  if ( v3 < GlobalIndentString.Length )
    Length = v3;
  v21 = Length;
  v22 = 0;
  v23 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskPnpMonitor::RegisterExistingDisks");
  }
  pulLen = 0;
  for ( Buffer = 0; ; Buffer = 0 )
  {
    Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, &GUID_DEVINTERFACE_DISK, 0, 0);
    if ( !Device_Interface_List_SizeW )
    {
      v19 = 0;
      goto LABEL_15;
    }
    v7 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v19 = v8;
    if ( v8 < 0 )
      break;
LABEL_15:
    v9 = ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Buffer, pulLen);
    v10 = Buffer;
    if ( !v9 )
    {
      v17 = -2147024882;
      v19 = -2147024882;
      goto LABEL_38;
    }
    Device_Interface_ListW = CM_Get_Device_Interface_ListW(&GUID_DEVINTERFACE_DISK, 0, Buffer, pulLen, 0);
    if ( Device_Interface_ListW != 26 )
    {
      if ( !Device_Interface_ListW )
      {
        v19 = 0;
LABEL_20:
        for ( i = v10; *i; i += v14 + 1 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v26,
            i);
          v13 = CDiskPnpMonitor::NewDiskDevice(this, &v26, 0);
          v19 = v13;
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
          if ( v13 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
              (_DWORD)i,
              v13);
          }
          v14 = -1;
          do
            ++v14;
          while ( i[v14] );
        }
        v19 = 0;
        free(v10);
        CHResultImp::~CHResultImp((CHResultImp *)&v18);
        return 0;
      }
      v16 = CM_MapCrToWin32Err(Device_Interface_ListW, 0xDu);
      v17 = v16;
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      v19 = v17;
      if ( v17 >= 0 )
        goto LABEL_20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
          (unsigned int)"Hr = CONFIGRET_HR( ConfigRet )",
          v17);
      }
LABEL_38:
      free(v10);
      CHResultImp::~CHResultImp((CHResultImp *)&v18);
      return (unsigned int)v17;
    }
    free(v10);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
      (unsigned int)"Hr = CONFIGRET_HR( CM_Get_Device_Interface_List_Size( &ListSize, const_cast<LPGUID>(&GUID_DEVINTERFA"
                    "CE_DISK), nullptr, CM_GET_DEVICE_INTERFACE_LIST_PRESENT ) )",
      v8);
  }
  free(0);
  CHResultImp::~CHResultImp((CHResultImp *)&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001a6bc  push    rbp
0x18001a6be  push    rbx
0x18001a6bf  push    rsi
0x18001a6c0  push    rdi
0x18001a6c1  push    r13
0x18001a6c3  push    r14
0x18001a6c5  push    r15
0x18001a6c7  mov     rbp, rsp
0x18001a6ca  sub     rsp, 50h
0x18001a6ce  mov     r14, rcx
0x18001a6d1  mov     edx, cs:_tls_index
0x18001a6d7  mov     rax, gs:58h
0x18001a6e0  mov     r8, [rax+rdx*8]
0x18001a6e4  mov     eax, 10h
0x18001a6e9  lea     r9, aCdiskpnpmonito_3; "CDiskPnpMonitor::RegisterExistingDisks"
0x18001a6f0  mov     [rax+r8], r9
0x18001a6f4  mov     [rbp+var_20], r9
0x18001a6f8  mov     edx, 8
0x18001a6fd  inc     word ptr [rdx+r8]
0x18001a702  movzx   edx, word ptr [rdx+r8]
0x18001a707  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001a70e  movzx   eax, cx
0x18001a711  cmp     dx, cx
0x18001a714  cmovb   ax, dx
0x18001a718  mov     [rbp+var_10], ax
0x18001a71c  cmovb   cx, dx
0x18001a720  mov     [rbp+var_E], cx
0x18001a724  xor     eax, eax
0x18001a726  mov     [rbp+var_C], eax
0x18001a729  mov     rax, cs:off_180047060; "                                       "...
0x18001a730  mov     [rbp+var_8], rax
0x18001a734  lea     r13, WPP_GLOBAL_Control
0x18001a73b  mov     edi, 0Dh
0x18001a740  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a747  cmp     rcx, r13
0x18001a74a  jz      short loc_18001A76D
0x18001a74c  test    byte ptr [rcx+1Ch], 1
0x18001a750  jz      short loc_18001A76D
0x18001a752  cmp     byte ptr [rcx+19h], 5
0x18001a756  jb      short loc_18001A76D
0x18001a758  mov     edx, edi
0x18001a75a  mov     qword ptr [rsp+50h+ulFlags], r9; __int64
0x18001a75f  lea     r9, [rbp+var_10]
0x18001a763  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a767  call    WPP_SF_aZs
0x18001a76c  nop
0x18001a76d  xor     r15d, r15d
0x18001a770  mov     [rbp+pulLen], r15d
0x18001a774  mov     [rbp+Buffer], r15
0x18001a778  mov     esi, 80070000h
0x18001a77d  xor     r9d, r9d; ulFlags
0x18001a780  xor     r8d, r8d; pDeviceID
0x18001a783  lea     rdx, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x18001a78a  lea     rcx, [rbp+pulLen]; pulLen
0x18001a78e  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x18001a794  test    eax, eax
0x18001a796  jnz     short loc_18001A79E
0x18001a798  mov     [rbp+var_18], r15d
0x18001a79c  jmp     short loc_18001A7BE
0x18001a79e  mov     edx, edi; DefaultErr
0x18001a7a0  mov     ecx, eax; CmReturnCode
0x18001a7a2  call    cs:__imp_CM_MapCrToWin32Err
0x18001a7a8  mov     ebx, eax
0x18001a7aa  test    eax, eax
0x18001a7ac  jle     short loc_18001A7B3
0x18001a7ae  movzx   ebx, ax
0x18001a7b1  or      ebx, esi
0x18001a7b3  mov     [rbp+var_18], ebx
0x18001a7b6  test    ebx, ebx
0x18001a7b8  js      loc_18001A93E
0x18001a7be  mov     edx, [rbp+pulLen]
0x18001a7c1  lea     rcx, [rbp+Buffer]
0x18001a7c5  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18001a7ca  mov     rbx, [rbp+Buffer]
0x18001a7ce  test    al, al
0x18001a7d0  jz      loc_18001A91F
0x18001a7d6  mov     [rsp+50h+ulFlags], r15d; ulFlags
0x18001a7db  mov     r9d, [rbp+pulLen]; BufferLen
0x18001a7df  mov     r8, rbx; Buffer
0x18001a7e2  xor     edx, edx; pDeviceID
0x18001a7e4  lea     rcx, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x18001a7eb  call    cs:__imp_CM_Get_Device_Interface_ListW
0x18001a7f1  cmp     eax, 1Ah
0x18001a7f4  jnz     short loc_18001A808
0x18001a7f6  mov     rcx, rbx; Block
0x18001a7f9  call    cs:__imp_free
0x18001a7ff  mov     [rbp+Buffer], r15
0x18001a803  jmp     loc_18001A77D
0x18001a808  test    eax, eax
0x18001a80a  jnz     loc_18001A8C5
0x18001a810  mov     [rbp+var_18], r15d
0x18001a814  mov     rdi, rbx
0x18001a817  cmp     [rbx], r15w
0x18001a81b  jz      loc_18001A8A7
0x18001a821  mov     rdx, rdi
0x18001a824  lea     rcx, [rbp+arg_18]
0x18001a828  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001a82d  nop
0x18001a82e  xor     r8d, r8d
0x18001a831  lea     rdx, [rbp+arg_18]
0x18001a835  mov     rcx, r14
0x18001a838  call    ?NewDiskDevice@CDiskPnpMonitor@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4NewDiskDeviceHandlerType@1@@Z; CDiskPnpMonitor::NewDiskDevice(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CDiskPnpMonitor::NewDiskDeviceHandlerType)
0x18001a83d  mov     esi, eax
0x18001a83f  mov     [rbp+var_18], eax
0x18001a842  mov     rcx, [rbp+arg_18]
0x18001a846  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a84a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a84f  test    esi, esi
0x18001a851  jns     short loc_18001A887
0x18001a853  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a85a  cmp     rcx, r13
0x18001a85d  jz      short loc_18001A887
0x18001a85f  test    byte ptr [rcx+1Ch], 1
0x18001a863  jz      short loc_18001A887
0x18001a865  cmp     byte ptr [rcx+19h], 2
0x18001a869  jb      short loc_18001A887
0x18001a86b  mov     edx, 27h ; '''
0x18001a870  mov     [rsp+50h+ulFlags], esi
0x18001a874  mov     r9, rdi
0x18001a877  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a87e  mov     rcx, [rcx+10h]
0x18001a882  call    WPP_SF_Sd
0x18001a887  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a88b  inc     rax
0x18001a88e  cmp     [rdi+rax*2], r15w
0x18001a893  jnz     short loc_18001A88B
0x18001a895  lea     rdi, [rdi+rax*2]
0x18001a899  add     rdi, 2
0x18001a89d  cmp     [rdi], r15w
0x18001a8a1  jnz     loc_18001A821
0x18001a8a7  mov     [rbp+var_18], r15d
0x18001a8ab  mov     rcx, rbx; Block
0x18001a8ae  call    cs:__imp_free
0x18001a8b4  nop
0x18001a8b5  lea     rcx, [rbp+var_20]; this
0x18001a8b9  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001a8be  xor     eax, eax
0x18001a8c0  jmp     loc_18001A98B
0x18001a8c5  mov     edx, edi; DefaultErr
0x18001a8c7  mov     ecx, eax; CmReturnCode
0x18001a8c9  call    cs:__imp_CM_MapCrToWin32Err
0x18001a8cf  mov     edi, eax
0x18001a8d1  test    eax, eax
0x18001a8d3  jle     short loc_18001A8DA
0x18001a8d5  movzx   edi, ax
0x18001a8d8  or      edi, esi
0x18001a8da  mov     [rbp+var_18], edi
0x18001a8dd  test    edi, edi
0x18001a8df  jns     loc_18001A814
0x18001a8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8ec  cmp     rcx, r13
0x18001a8ef  jz      short loc_18001A927
0x18001a8f1  test    byte ptr [rcx+1Ch], 1
0x18001a8f5  jz      short loc_18001A927
0x18001a8f7  cmp     byte ptr [rcx+19h], 2
0x18001a8fb  jb      short loc_18001A927
0x18001a8fd  mov     edx, 26h ; '&'
0x18001a902  mov     [rsp+50h+ulFlags], edi
0x18001a906  lea     r9, aHrConfigretHrC_0; "Hr = CONFIGRET_HR( ConfigRet )"
0x18001a90d  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a914  mov     rcx, [rcx+10h]
0x18001a918  call    WPP_SF_sd
0x18001a91d  jmp     short loc_18001A927
0x18001a91f  mov     edi, 8007000Eh
0x18001a924  mov     [rbp+var_18], edi
0x18001a927  mov     rcx, rbx; Block
0x18001a92a  call    cs:__imp_free
0x18001a930  nop
0x18001a931  lea     rcx, [rbp+var_20]; this
0x18001a935  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001a93a  mov     eax, edi
0x18001a93c  jmp     short loc_18001A98B
0x18001a93e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a945  cmp     rcx, r13
0x18001a948  jz      short loc_18001A977
0x18001a94a  test    byte ptr [rcx+1Ch], 1
0x18001a94e  jz      short loc_18001A977
0x18001a950  cmp     byte ptr [rcx+19h], 2
0x18001a954  jb      short loc_18001A977
0x18001a956  mov     edx, 25h ; '%'
0x18001a95b  mov     [rsp+50h+ulFlags], ebx
0x18001a95f  lea     r9, aHrConfigretHrC; "Hr = CONFIGRET_HR( CM_Get_Device_Interf"...
0x18001a966  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a96d  mov     rcx, [rcx+10h]
0x18001a971  call    WPP_SF_sd
0x18001a976  nop
0x18001a977  xor     ecx, ecx; Block
0x18001a979  call    cs:__imp_free
0x18001a97f  nop
0x18001a980  lea     rcx, [rbp+var_20]; this
0x18001a984  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001a989  mov     eax, ebx
0x18001a98b  add     rsp, 50h
0x18001a98f  pop     r15
0x18001a991  pop     r14
0x18001a993  pop     r13
0x18001a995  pop     rdi
0x18001a996  pop     rsi
0x18001a997  pop     rbx
0x18001a998  pop     rbp
0x18001a999  retn
```
