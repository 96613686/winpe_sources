# myDoesDSExist(int)

- ea: `0x18000ac20`
- end: `0x18000ade9`
- name: `?myDoesDSExist@@YAJH@Z`
- size: `457`
- prototype: `__int64 __fastcall(int)`
- caller_count: `9`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a630`
- `0x18000a920`
- `0x180012680`
- `0x18002ef70`
- `0x180033f70`
- `0x1800356b8`
- `0x180035bd0`
- `0x180035da8`
- `0x1800365a4`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000a3b0`
- `0x18000ac20`
- `0x180010168`
- `0x180012830`
- `0x180028150`
- `0x1800281d8`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000acb0`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000ad9e`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000acb0`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000ad9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ac4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ac91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ac4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ac91`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ac61`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ac61`

## pseudocode

```c
__int64 __fastcall myDoesDSExist(int a1)
{
  int v1; // eax
  void (*v2)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  enum _DSROLE_PRIMARY_DOMAIN_INFO_LEVEL v3; // edx
  const unsigned __int16 *v4; // rcx
  int PrimaryDomainInformation; // eax
  const unsigned __int16 *v6; // rdx
  struct _GUID *v7; // r8
  const unsigned __int16 *v8; // r9
  int v9; // esi
  unsigned __int16 *v10; // rcx
  unsigned int DcName; // eax
  int v12; // edx
  unsigned int v13; // ecx
  struct _DOMAIN_CONTROLLER_INFOW *v14; // rcx
  int v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-38h]
  const struct _EXCEPTION_POINTERS *v18; // [rsp+40h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+10h] BYREF
  struct _DOMAIN_CONTROLLER_INFOW *v20; // [rsp+70h] [rbp+18h] BYREF
  struct _FILETIME v21; // [rsp+78h] [rbp+20h] BYREF

  v1 = dword_1800C4F10;
  if ( !dword_1800C4F10 )
    goto LABEL_8;
  if ( dword_1800C4444 && a1 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) >= 0 )
    {
      v1 = dword_1800C4F10;
    }
    else
    {
      v1 = 0;
      dword_1800C4F10 = 0;
    }
  }
  if ( !v1 )
  {
LABEL_8:
    v21 = 0;
    GetSystemTimeAsFileTime(&v21);
    FileTime1 = (FILETIME)(*(_QWORD *)&v21 + 150000000LL);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v2 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
      v20 = 0;
      SystemTimeAsFileTime = 0;
      PrimaryDomainInformation = myDsRoleGetPrimaryDomainInformation(
                                   v4,
                                   (void *)v3,
                                   (unsigned __int8 **)&SystemTimeAsFileTime);
      v9 = PrimaryDomainInformation;
      if ( PrimaryDomainInformation )
      {
        CSPrintErrorLineFile(0x52032Cu, PrimaryDomainInformation);
      }
      else
      {
        v10 = (unsigned __int16 *)SystemTimeAsFileTime;
        if ( (*(_DWORD *)SystemTimeAsFileTime.dwLowDateTime & 0xFFFFFFFD) != 0 )
          goto LABEL_14;
        v9 = -2147023541;
        CSPrintErrorLineFileData2(0, 0x58032Cu, -2147023541, -2147023541);
      }
      v10 = (unsigned __int16 *)SystemTimeAsFileTime;
LABEL_14:
      if ( v10 )
        ((void (__fastcall *)(void *))myDsRoleFreeMemory)(v10);
      if ( v9 )
        goto LABEL_24;
      v20 = 0;
      DcName = myDsGetDcName(v10, v6, v7, v8, v17, &v20);
      v9 = DcName;
      if ( DcName )
      {
        v12 = DcName;
        v13 = 7013164;
      }
      else
      {
        v14 = v20;
        if ( (v20->Flags & 0x10) != 0 )
          goto LABEL_22;
        v9 = -2147023545;
        v12 = -2147023545;
        v13 = 7340844;
      }
      CSPrintErrorLineFile(v13, v12);
      v14 = v20;
LABEL_22:
      if ( v14 )
        myNetApiBufferFree(v14);
LABEL_24:
      dword_1800C4F10 = 1;
      _set_se_translator(v2);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &StructuredException `RTTI Type Descriptor', (const StructuredException **)&v18) )
      {
        __eh34_try_continuation(0, &StructuredException `RTTI Type Descriptor', &loc_18000ADA7);
        v9 = myHExceptionCodePrint(v18 + 77, 0, 0x32Cu, 0x7Bu);
      }
    }
    v15 = myHError(v9);
    dword_1800C4444 = v15;
    if ( v15 && v15 != -2147023541 )
      CSPrintErrorLineFileData2(0, 0x86032Cu, v15, -2147023665);
  }
  return (unsigned int)dword_1800C4444;
}

```

## disassembly

```asm
0x18000ac20  mov     [rsp+arg_0], rbx
0x18000ac25  push    rsi
0x18000ac26  sub     rsp, 50h
0x18000ac2a  mov     eax, cs:dword_1800C4F10
0x18000ac30  test    eax, eax
0x18000ac32  jz      short loc_18000AC83
0x18000ac34  cmp     cs:dword_1800C4444, 0
0x18000ac3b  jz      short loc_18000AC7B
0x18000ac3d  test    ecx, ecx
0x18000ac3f  jz      short loc_18000AC7B
0x18000ac41  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000ac4a  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ac4f  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ac55  lea     rdx, [rsp+58h+SystemTimeAsFileTime]; lpFileTime2
0x18000ac5a  lea     rcx, FileTime1; lpFileTime1
0x18000ac61  call    cs:__imp_CompareFileTime
0x18000ac67  test    eax, eax
0x18000ac69  jns     short loc_18000AC75
0x18000ac6b  xor     eax, eax
0x18000ac6d  mov     cs:dword_1800C4F10, eax
0x18000ac73  jmp     short loc_18000AC7B
0x18000ac75  mov     eax, cs:dword_1800C4F10
0x18000ac7b  test    eax, eax
0x18000ac7d  jnz     loc_18000ADD8
0x18000ac83  mov     qword ptr [rsp+58h+arg_18.dwLowDateTime], 0
0x18000ac8c  lea     rcx, [rsp+58h+arg_18]; lpSystemTimeAsFileTime
0x18000ac91  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ac97  mov     rax, qword ptr [rsp+58h+arg_18.dwLowDateTime]
0x18000ac9c  add     rax, 8F0D180h
0x18000aca2  mov     qword ptr cs:FileTime1.dwLowDateTime, rax
0x18000aca9  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18000acb0  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000acb6  mov     rbx, rax
0x18000acb9  mov     [rsp+58h+var_20], rax
0x18000acbe  mov     [rsp+58h+arg_10], 0
0x18000acc7  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000acd0  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000acd9  lea     r8, [rsp+58h+SystemTimeAsFileTime]; unsigned __int8 **
0x18000acde  call    ?myDsRoleGetPrimaryDomainInformation@@YAKPEBGW4_DSROLE_PRIMARY_DOMAIN_INFO_LEVEL@@PEAPEAE@Z; myDsRoleGetPrimaryDomainInformation(ushort const *,_DSROLE_PRIMARY_DOMAIN_INFO_LEVEL,uchar * *)
0x18000ace3  mov     esi, eax
0x18000ace5  mov     [rsp+58h+var_28], eax
0x18000ace9  test    eax, eax
0x18000aceb  jz      short loc_18000ACFB
0x18000aced  mov     edx, eax; int
0x18000acef  mov     ecx, 52032Ch; unsigned int
0x18000acf4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000acf9  jmp     short loc_18000AD23
0x18000acfb  mov     rcx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x18000ad00  test    dword ptr [rcx], 0FFFFFFFDh
0x18000ad06  jnz     short loc_18000AD28
0x18000ad08  mov     esi, 8007054Bh
0x18000ad0d  mov     [rsp+58h+var_28], esi
0x18000ad11  mov     edx, 58032Ch; unsigned int
0x18000ad16  xor     ecx, ecx; unsigned __int16 *
0x18000ad18  mov     r9d, esi; int
0x18000ad1b  mov     r8d, esi; int
0x18000ad1e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000ad23  mov     rcx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]; void *
0x18000ad28  test    rcx, rcx
0x18000ad2b  jz      short loc_18000AD32
0x18000ad2d  call    ?myDsRoleFreeMemory@@YAXPEAX@Z; myDsRoleFreeMemory(void *)
0x18000ad32  test    esi, esi
0x18000ad34  jnz     short loc_18000AD91
0x18000ad36  mov     [rsp+58h+arg_10], 0
0x18000ad3f  lea     rax, [rsp+58h+arg_10]
0x18000ad44  mov     [rsp+58h+var_30], rax; struct _DOMAIN_CONTROLLER_INFOW **
0x18000ad49  call    ?myDsGetDcName@@YAKPEBG0PEAU_GUID@@0KPEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z; myDsGetDcName(ushort const *,ushort const *,_GUID *,ushort const *,ulong,_DOMAIN_CONTROLLER_INFOW * *)
0x18000ad4e  mov     esi, eax
0x18000ad50  mov     [rsp+58h+var_28], eax
0x18000ad54  test    eax, eax
0x18000ad56  jz      short loc_18000AD61
0x18000ad58  mov     edx, eax
0x18000ad5a  mov     ecx, 6B032Ch
0x18000ad5f  jmp     short loc_18000AD7D
0x18000ad61  mov     rcx, [rsp+58h+arg_10]
0x18000ad66  mov     eax, [rcx+38h]
0x18000ad69  test    al, 10h
0x18000ad6b  jnz     short loc_18000AD87
0x18000ad6d  mov     esi, 80070547h
0x18000ad72  mov     [rsp+58h+var_28], esi
0x18000ad76  mov     edx, esi; int
0x18000ad78  mov     ecx, 70032Ch; unsigned int
0x18000ad7d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000ad82  mov     rcx, [rsp+58h+arg_10]; void *
0x18000ad87  test    rcx, rcx
0x18000ad8a  jz      short loc_18000AD91
0x18000ad8c  call    ?myNetApiBufferFree@@YAKPEAX@Z; myNetApiBufferFree(void *)
0x18000ad91  mov     cs:dword_1800C4F10, 1
0x18000ad9b  mov     rcx, rbx
0x18000ad9e  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000ada4  nop
0x18000ada5  jmp     short loc_18000ADAB
0x18000ada7  mov     esi, [rsp+58h+var_28]
0x18000adab  mov     ecx, esi; int
0x18000adad  call    ?myHError@@YAJJ@Z; myHError(long)
0x18000adb2  mov     cs:dword_1800C4444, eax
0x18000adb8  test    eax, eax
0x18000adba  jz      short loc_18000ADD8
0x18000adbc  cmp     eax, 8007054Bh
0x18000adc1  jz      short loc_18000ADD8
0x18000adc3  mov     r9d, 800704CFh; int
0x18000adc9  mov     r8d, eax; int
0x18000adcc  mov     edx, 86032Ch; unsigned int
0x18000add1  xor     ecx, ecx; unsigned __int16 *
0x18000add3  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000add8  mov     eax, cs:dword_1800C4444
0x18000adde  mov     rbx, [rsp+58h+arg_0]
0x18000ade3  add     rsp, 50h
0x18000ade7  pop     rsi
0x18000ade8  retn
```
