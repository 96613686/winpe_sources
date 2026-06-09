# Config::XmlConfig::SetParameterValue(Config::Parameter *,ATL::CComVariant &)

- ea: `0x140062a54`
- end: `0x140062f2d`
- name: `?SetParameterValue@XmlConfig@Config@@AEAAPEAVFrsStatus@@PEAVParameter@2@AEAVCComVariant@ATL@@@Z`
- size: `1241`
- prototype: `struct FrsStatus *(Config::XmlConfig *__hidden this, struct Parameter *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005fe5c`

## callees

- `0x14000cb00`
- `0x140048b10`
- `0x140048b44`
- `0x140048c10`
- `0x140048cd4`
- `0x140048e60`
- `0x140048f84`
- `0x140049078`
- `0x140062a54`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140062ab5`
- `KERNEL32!GetCurrentThreadId` at `0x140062b04`
- `KERNEL32!GetCurrentThreadId` at `0x140062b81`
- `KERNEL32!GetCurrentThreadId` at `0x140062bfe`
- `KERNEL32!GetCurrentThreadId` at `0x140062cb8`
- `KERNEL32!GetCurrentThreadId` at `0x140062d38`
- `KERNEL32!GetCurrentThreadId` at `0x140062db7`
- `KERNEL32!GetCurrentThreadId` at `0x140062e34`
- `KERNEL32!GetCurrentThreadId` at `0x140062ab5`
- `KERNEL32!GetCurrentThreadId` at `0x140062b04`
- `KERNEL32!GetCurrentThreadId` at `0x140062b81`
- `KERNEL32!GetCurrentThreadId` at `0x140062bfe`
- `KERNEL32!GetCurrentThreadId` at `0x140062cb8`
- `KERNEL32!GetCurrentThreadId` at `0x140062d38`
- `KERNEL32!GetCurrentThreadId` at `0x140062db7`
- `KERNEL32!GetCurrentThreadId` at `0x140062e34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140062c75`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140062ca0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140062c75`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140062ca0`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062b1e`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062b9b`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062c18`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062cd5`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062d55`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062dd1`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062e4e`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062b1e`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062b9b`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062c18`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062cd5`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062d55`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062dd1`
- `OLEAUT32!__imp_VariantChangeType` at `0x140062e4e`

## string_xrefs

- `0x140062aeb`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062b53`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062bd0`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062c4d`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062d0a`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062d8a`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062e06`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062e83`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140062ac7`: `Config::XmlConfig::SetParameterValue`
- `0x140062b30`: `Config::XmlConfig::SetParameterValue`
- `0x140062bad`: `Config::XmlConfig::SetParameterValue`
- `0x140062c2a`: `Config::XmlConfig::SetParameterValue`
- `0x140062ce7`: `Config::XmlConfig::SetParameterValue`
- `0x140062d67`: `Config::XmlConfig::SetParameterValue`
- `0x140062de3`: `Config::XmlConfig::SetParameterValue`
- `0x140062e60`: `Config::XmlConfig::SetParameterValue`
- `0x140062ec5`: `Config::XmlConfig::SetParameterValue`

## pseudocode

```c
struct FrsStatus *__fastcall Config::XmlConfig::SetParameterValue(
        Config::XmlConfig *this,
        struct Parameter *a2,
        VARIANTARG *a3)
{
  DWORD v5; // eax
  __int64 v6; // rbx
  DWORD v7; // ebx
  unsigned int v8; // eax
  DWORD v9; // ebx
  unsigned int v10; // eax
  DWORD v11; // ebx
  unsigned int v12; // eax
  int v13; // edx
  DWORD v14; // ebx
  unsigned int v15; // eax
  DWORD v16; // ebx
  unsigned int v17; // eax
  DWORD CurrentThreadId; // ebx
  unsigned int v19; // eax
  DWORD v20; // ebx
  unsigned int v21; // eax
  const wchar_t *v23; // [rsp+50h] [rbp-28h] BYREF
  int v24; // [rsp+58h] [rbp-20h]
  int v25; // [rsp+5Ch] [rbp-1Ch]
  const wchar_t *v26; // [rsp+60h] [rbp-18h]
  Config::XmlConfig *v27; // [rsp+80h] [rbp+8h] BYREF

  v27 = this;
  if ( *((_DWORD *)a2 + 2) != 1 )
  {
    switch ( *((_DWORD *)a2 + 2) )
    {
      case 2:
        CurrentThreadId = GetCurrentThreadId();
        v19 = VariantChangeType(a3, a3, 0, 8u);
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               v19,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               922,
               CurrentThreadId,
               0);
        if ( !v6 )
        {
          Config::PathParam::Set(a2, a3->bstrVal);
          return (struct FrsStatus *)v6;
        }
        break;
      case 3:
        v16 = GetCurrentThreadId();
        v17 = VariantChangeType(a3, a3, 0, 0x13u);
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               v17,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               869,
               v16,
               0);
        if ( !v6 )
        {
          Config::DWordParam::Set(a2, a3->cyVal.Lo);
          return (struct FrsStatus *)v6;
        }
        break;
      case 4:
        v14 = GetCurrentThreadId();
        v15 = VariantChangeType(a3, a3, 0, 0x15u);
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               v15,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               882,
               v14,
               0);
        if ( !v6 )
        {
          Config::QWordParam::Set(a2, a3->ullVal);
          return (struct FrsStatus *)v6;
        }
        break;
      case 5:
        v11 = GetCurrentThreadId();
        v12 = VariantChangeType(a3, a3, 0, 8u);
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               v12,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               895,
               v11,
               0);
        if ( !v6 )
        {
          if ( (unsigned int)_o__wcsicmp(a3->llVal, L"true") )
          {
            if ( (unsigned int)_o__wcsicmp(a3->llVal, L"false") )
            {
LABEL_32:
              *((_DWORD *)a2 + 7) |= 8u;
              return (struct FrsStatus *)v6;
            }
            v13 = 0;
          }
          else
          {
            v13 = 1;
          }
          Config::BoolParam::Set(a2, v13);
          return (struct FrsStatus *)v6;
        }
        break;
      case 6:
        v9 = GetCurrentThreadId();
        v10 = VariantChangeType(a3, a3, 0, 8u);
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               v10,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               930,
               v9,
               0);
        if ( !v6 )
        {
          Config::GuidParam::SetGuid(a2, a3->bstrVal);
          return (struct FrsStatus *)v6;
        }
        break;
      case 7:
        v7 = GetCurrentThreadId();
        v8 = VariantChangeType(a3, a3, 0, 8u);
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               v8,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               938,
               v7,
               0);
        if ( !v6 )
        {
          Config::DateTimeParam::SetDateTime(a2, a3->bstrVal);
          return (struct FrsStatus *)v6;
        }
        break;
      default:
        v5 = GetCurrentThreadId();
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               2147942487LL,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
               "Config::XmlConfig::SetParameterValue",
               945,
               v5,
               0);
        goto LABEL_27;
    }
LABEL_28:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v24 = 954;
      v23 = L"Config::XmlConfig::SetParameterValue";
      v25 = 4;
      v26 = L"CXML";
      LODWORD(v27) = a3->vt;
      dbgobj::DbgPrint<unsigned short,unsigned int>(&v23, L"Invalid value or type, variant type:%?", &v27);
    }
    goto LABEL_32;
  }
  v20 = GetCurrentThreadId();
  v21 = VariantChangeType(a3, a3, 0, 8u);
  v6 = FrsStatusList::PushNewError(
         "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
         v21,
         0,
         4,
         "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
         "Config::XmlConfig::SetParameterValue",
         914,
         v20,
         0);
  if ( v6 )
    goto LABEL_28;
  Config::StringParam::Set(a2, a3->bstrVal);
LABEL_27:
  if ( v6 )
    goto LABEL_28;
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x140062a54  mov     rax, rsp
0x140062a57  mov     [rax+10h], rbx
0x140062a5b  mov     [rax+18h], rbp
0x140062a5f  mov     [rax+20h], rsi
0x140062a63  mov     [rax+8], rcx
0x140062a67  push    rdi
0x140062a68  sub     rsp, 70h
0x140062a6c  mov     ecx, [rdx+8]
0x140062a6f  mov     rsi, r8
0x140062a72  mov     rdi, rdx
0x140062a75  mov     ebp, 8
0x140062a7a  sub     ecx, 1
0x140062a7d  jz      loc_140062E34
0x140062a83  sub     ecx, 1
0x140062a86  jz      loc_140062DB7
0x140062a8c  sub     ecx, 1
0x140062a8f  jz      loc_140062D38
0x140062a95  sub     ecx, 1
0x140062a98  jz      loc_140062CB8
0x140062a9e  sub     ecx, 1
0x140062aa1  jz      loc_140062BFE
0x140062aa7  sub     ecx, 1
0x140062aaa  jz      loc_140062B81
0x140062ab0  cmp     ecx, 1
0x140062ab3  jz      short loc_140062B04
0x140062ab5  call    cs:__imp_GetCurrentThreadId
0x140062abc  nop     dword ptr [rax+rax+00h]
0x140062ac1  and     [rsp+78h+var_38], 0
0x140062ac7  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062ace  mov     [rsp+78h+var_40], eax
0x140062ad2  lea     r9d, [rbp-4]
0x140062ad6  mov     [rsp+78h+var_48], 3B1h
0x140062ade  xor     r8d, r8d
0x140062ae1  mov     [rsp+78h+var_50], rcx
0x140062ae6  mov     edx, 80070057h
0x140062aeb  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062af2  mov     [rsp+78h+var_58], rcx
0x140062af7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062afc  mov     rbx, rax
0x140062aff  jmp     loc_140062EA8
0x140062b04  call    cs:__imp_GetCurrentThreadId
0x140062b0b  nop     dword ptr [rax+rax+00h]
0x140062b10  mov     r9d, ebp; vt
0x140062b13  xor     r8d, r8d; wFlags
0x140062b16  mov     rdx, rsi; pvarSrc
0x140062b19  mov     rcx, rsi; pvargDest
0x140062b1c  mov     ebx, eax
0x140062b1e  call    cs:__imp_VariantChangeType
0x140062b25  nop     dword ptr [rax+rax+00h]
0x140062b2a  and     [rsp+78h+var_38], 0
0x140062b30  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062b37  mov     [rsp+78h+var_40], ebx
0x140062b3b  mov     r9d, 4
0x140062b41  mov     [rsp+78h+var_48], 3AAh
0x140062b49  xor     r8d, r8d
0x140062b4c  mov     [rsp+78h+var_50], rcx
0x140062b51  mov     edx, eax
0x140062b53  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062b5a  mov     [rsp+78h+var_58], rcx
0x140062b5f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062b64  mov     rbx, rax
0x140062b67  test    rax, rax
0x140062b6a  jnz     loc_140062EAD
0x140062b70  mov     rdx, [rsi+8]; unsigned __int16 *
0x140062b74  mov     rcx, rdi; this
0x140062b77  call    ?SetDateTime@DateTimeParam@Config@@QEAAHPEBG@Z; Config::DateTimeParam::SetDateTime(ushort const *)
0x140062b7c  jmp     loc_140062F13
0x140062b81  call    cs:__imp_GetCurrentThreadId
0x140062b88  nop     dword ptr [rax+rax+00h]
0x140062b8d  mov     r9d, ebp; vt
0x140062b90  xor     r8d, r8d; wFlags
0x140062b93  mov     rdx, rsi; pvarSrc
0x140062b96  mov     rcx, rsi; pvargDest
0x140062b99  mov     ebx, eax
0x140062b9b  call    cs:__imp_VariantChangeType
0x140062ba2  nop     dword ptr [rax+rax+00h]
0x140062ba7  and     [rsp+78h+var_38], 0
0x140062bad  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062bb4  mov     [rsp+78h+var_40], ebx
0x140062bb8  mov     r9d, 4
0x140062bbe  mov     [rsp+78h+var_48], 3A2h
0x140062bc6  xor     r8d, r8d
0x140062bc9  mov     [rsp+78h+var_50], rcx
0x140062bce  mov     edx, eax
0x140062bd0  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062bd7  mov     [rsp+78h+var_58], rcx
0x140062bdc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062be1  mov     rbx, rax
0x140062be4  test    rax, rax
0x140062be7  jnz     loc_140062EAD
0x140062bed  mov     rdx, [rsi+8]; unsigned __int16 *
0x140062bf1  mov     rcx, rdi; this
0x140062bf4  call    ?SetGuid@GuidParam@Config@@QEAAHPEBG@Z; Config::GuidParam::SetGuid(ushort const *)
0x140062bf9  jmp     loc_140062F13
0x140062bfe  call    cs:__imp_GetCurrentThreadId
0x140062c05  nop     dword ptr [rax+rax+00h]
0x140062c0a  mov     r9d, ebp; vt
0x140062c0d  xor     r8d, r8d; wFlags
0x140062c10  mov     rdx, rsi; pvarSrc
0x140062c13  mov     rcx, rsi; pvargDest
0x140062c16  mov     ebx, eax
0x140062c18  call    cs:__imp_VariantChangeType
0x140062c1f  nop     dword ptr [rax+rax+00h]
0x140062c24  and     [rsp+78h+var_38], 0
0x140062c2a  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062c31  mov     [rsp+78h+var_40], ebx
0x140062c35  mov     r9d, 4
0x140062c3b  mov     [rsp+78h+var_48], 37Fh
0x140062c43  xor     r8d, r8d
0x140062c46  mov     [rsp+78h+var_50], rcx
0x140062c4b  mov     edx, eax
0x140062c4d  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062c54  mov     [rsp+78h+var_58], rcx
0x140062c59  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062c5e  mov     rbx, rax
0x140062c61  test    rax, rax
0x140062c64  jnz     loc_140062EAD
0x140062c6a  mov     rcx, [rsi+8]
0x140062c6e  lea     rdx, aTrue; "true"
0x140062c75  call    cs:__imp__o__wcsicmp
0x140062c7c  nop     dword ptr [rax+rax+00h]
0x140062c81  test    eax, eax
0x140062c83  jnz     short loc_140062C95
0x140062c85  lea     edx, [rbx+1]; int
0x140062c88  mov     rcx, rdi; this
0x140062c8b  call    ?Set@BoolParam@Config@@QEAAHH@Z; Config::BoolParam::Set(int)
0x140062c90  jmp     loc_140062F13
0x140062c95  mov     rcx, [rsi+8]
0x140062c99  lea     rdx, aFalse; "false"
0x140062ca0  call    cs:__imp__o__wcsicmp
0x140062ca7  nop     dword ptr [rax+rax+00h]
0x140062cac  test    eax, eax
0x140062cae  jnz     loc_140062F10
0x140062cb4  xor     edx, edx
0x140062cb6  jmp     short loc_140062C88
0x140062cb8  call    cs:__imp_GetCurrentThreadId
0x140062cbf  nop     dword ptr [rax+rax+00h]
0x140062cc4  mov     r9d, 15h; vt
0x140062cca  xor     r8d, r8d; wFlags
0x140062ccd  mov     rdx, rsi; pvarSrc
0x140062cd0  mov     rcx, rsi; pvargDest
0x140062cd3  mov     ebx, eax
0x140062cd5  call    cs:__imp_VariantChangeType
0x140062cdc  nop     dword ptr [rax+rax+00h]
0x140062ce1  and     [rsp+78h+var_38], 0
0x140062ce7  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062cee  mov     [rsp+78h+var_40], ebx
0x140062cf2  mov     r9d, 4
0x140062cf8  mov     [rsp+78h+var_48], 372h
0x140062d00  xor     r8d, r8d
0x140062d03  mov     [rsp+78h+var_50], rcx
0x140062d08  mov     edx, eax
0x140062d0a  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062d11  mov     [rsp+78h+var_58], rcx
0x140062d16  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062d1b  mov     rbx, rax
0x140062d1e  test    rax, rax
0x140062d21  jnz     loc_140062EAD
0x140062d27  mov     rdx, [rsi+8]; unsigned __int64
0x140062d2b  mov     rcx, rdi; this
0x140062d2e  call    ?Set@QWordParam@Config@@QEAAH_K@Z; Config::QWordParam::Set(unsigned __int64)
0x140062d33  jmp     loc_140062F13
0x140062d38  call    cs:__imp_GetCurrentThreadId
0x140062d3f  nop     dword ptr [rax+rax+00h]
0x140062d44  mov     r9d, 13h; vt
0x140062d4a  xor     r8d, r8d; wFlags
0x140062d4d  mov     rdx, rsi; pvarSrc
0x140062d50  mov     rcx, rsi; pvargDest
0x140062d53  mov     ebx, eax
0x140062d55  call    cs:__imp_VariantChangeType
0x140062d5c  nop     dword ptr [rax+rax+00h]
0x140062d61  and     [rsp+78h+var_38], 0
0x140062d67  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062d6e  mov     [rsp+78h+var_40], ebx
0x140062d72  mov     r9d, 4
0x140062d78  mov     [rsp+78h+var_48], 365h
0x140062d80  xor     r8d, r8d
0x140062d83  mov     [rsp+78h+var_50], rcx
0x140062d88  mov     edx, eax
0x140062d8a  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062d91  mov     [rsp+78h+var_58], rcx
0x140062d96  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062d9b  mov     rbx, rax
0x140062d9e  test    rax, rax
0x140062da1  jnz     loc_140062EAD
0x140062da7  mov     edx, [rsi+8]; unsigned int
0x140062daa  mov     rcx, rdi; this
0x140062dad  call    ?Set@DWordParam@Config@@QEAAHK@Z; Config::DWordParam::Set(ulong)
0x140062db2  jmp     loc_140062F13
0x140062db7  call    cs:__imp_GetCurrentThreadId
0x140062dbe  nop     dword ptr [rax+rax+00h]
0x140062dc3  mov     r9d, ebp; vt
0x140062dc6  xor     r8d, r8d; wFlags
0x140062dc9  mov     rdx, rsi; pvarSrc
0x140062dcc  mov     rcx, rsi; pvargDest
0x140062dcf  mov     ebx, eax
0x140062dd1  call    cs:__imp_VariantChangeType
0x140062dd8  nop     dword ptr [rax+rax+00h]
0x140062ddd  and     [rsp+78h+var_38], 0
0x140062de3  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062dea  mov     [rsp+78h+var_40], ebx
0x140062dee  mov     r9d, 4
0x140062df4  mov     [rsp+78h+var_48], 39Ah
0x140062dfc  xor     r8d, r8d
0x140062dff  mov     [rsp+78h+var_50], rcx
0x140062e04  mov     edx, eax
0x140062e06  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062e0d  mov     [rsp+78h+var_58], rcx
0x140062e12  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062e17  mov     rbx, rax
0x140062e1a  test    rax, rax
0x140062e1d  jnz     loc_140062EAD
0x140062e23  mov     rdx, [rsi+8]; unsigned __int16 *
0x140062e27  mov     rcx, rdi; this
0x140062e2a  call    ?Set@PathParam@Config@@QEAAHPEBG@Z; Config::PathParam::Set(ushort const *)
0x140062e2f  jmp     loc_140062F13
0x140062e34  call    cs:__imp_GetCurrentThreadId
0x140062e3b  nop     dword ptr [rax+rax+00h]
0x140062e40  mov     r9d, ebp; vt
0x140062e43  xor     r8d, r8d; wFlags
0x140062e46  mov     rdx, rsi; pvarSrc
0x140062e49  mov     rcx, rsi; pvargDest
0x140062e4c  mov     ebx, eax
0x140062e4e  call    cs:__imp_VariantChangeType
0x140062e55  nop     dword ptr [rax+rax+00h]
0x140062e5a  and     [rsp+78h+var_38], 0
0x140062e60  lea     rcx, aConfigXmlconfi_16; "Config::XmlConfig::SetParameterValue"
0x140062e67  mov     [rsp+78h+var_40], ebx
0x140062e6b  mov     r9d, 4
0x140062e71  mov     [rsp+78h+var_48], 392h
0x140062e79  xor     r8d, r8d
0x140062e7c  mov     [rsp+78h+var_50], rcx
0x140062e81  mov     edx, eax
0x140062e83  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140062e8a  mov     [rsp+78h+var_58], rcx
0x140062e8f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140062e94  mov     rbx, rax
0x140062e97  test    rax, rax
0x140062e9a  jnz     short loc_140062EAD
0x140062e9c  mov     rdx, [rsi+8]; unsigned __int16 *
0x140062ea0  mov     rcx, rdi; this
0x140062ea3  call    ?Set@StringParam@Config@@QEAAHPEBG@Z; Config::StringParam::Set(ushort const *)
0x140062ea8  test    rbx, rbx
0x140062eab  jz      short loc_140062F13
0x140062ead  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140062eb4  test    rax, rax
0x140062eb7  jz      short loc_140062F10
0x140062eb9  cmp     dword ptr [rax+40h], 0
0x140062ebd  jz      short loc_140062F10
0x140062ebf  cmp     dword ptr [rax+38h], 4
0x140062ec3  jl      short loc_140062F10
0x140062ec5  lea     rax, aConfigXmlconfi_13; "Config::XmlConfig::SetParameterValue"
0x140062ecc  mov     [rsp+78h+var_20], 3BAh
0x140062ed4  mov     [rsp+78h+var_28], rax
0x140062ed9  lea     r8, [rsp+78h+arg_0]
0x140062ee1  lea     rax, aCxml; "CXML"
0x140062ee8  mov     [rsp+78h+var_1C], 4
0x140062ef0  mov     [rsp+78h+var_18], rax
0x140062ef5  lea     rdx, aInvalidValueOr; "Invalid value or type, variant type:%?"
0x140062efc  movzx   eax, word ptr [rsi]
0x140062eff  lea     rcx, [rsp+78h+var_28]
0x140062f04  mov     dword ptr [rsp+78h+arg_0], eax
0x140062f0b  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140062f10  or      [rdi+1Ch], ebp
0x140062f13  lea     r11, [rsp+78h+var_8]
0x140062f18  mov     rax, rbx
0x140062f1b  mov     rbx, [r11+18h]
0x140062f1f  mov     rbp, [r11+20h]
0x140062f23  mov     rsi, [r11+28h]
0x140062f27  mov     rsp, r11
0x140062f2a  pop     rdi
0x140062f2b  retn
```
