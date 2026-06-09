# DataStoreServer::Initialize(void)

- ea: `0x180008d7c`
- end: `0x1800093c4`
- name: `?Initialize@DataStoreServer@@QEAAJXZ`
- size: `1608`
- prototype: `__int64 __fastcall(DataStoreServer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800067a8`

## callees

- `0x180007150`
- `0x1800071ac`
- `0x180008d7c`
- `0x18000a19c`
- `0x18000d064`
- `0x18000d990`
- `0x18000dd10`
- `0x180010010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x180008dc2`
- `KERNEL32!TryEnterCriticalSection` at `0x180008dc2`
- `KERNEL32!SwitchToThread` at `0x180008db9`
- `KERNEL32!SwitchToThread` at `0x180008db9`
- `KERNEL32!EnterCriticalSection` at `0x180008dd1`
- `KERNEL32!EnterCriticalSection` at `0x180008dd1`
- `KERNEL32!LeaveCriticalSection` at `0x180009374`
- `KERNEL32!LeaveCriticalSection` at `0x180009374`
- `KERNEL32!GetLastError` at `0x18000924f`
- `KERNEL32!GetLastError` at `0x18000924f`
- `KERNEL32!GetModuleHandleW` at `0x180008ecb`
- `KERNEL32!GetModuleHandleW` at `0x180008ecb`
- `ole32!CoTaskMemFree` at `0x1800092d0`
- `ole32!CoTaskMemFree` at `0x1800092f4`
- `ole32!CoTaskMemFree` at `0x180009318`
- `ole32!CoTaskMemFree` at `0x1800092d0`
- `ole32!CoTaskMemFree` at `0x1800092f4`
- `ole32!CoTaskMemFree` at `0x180009318`

## string_xrefs

- `0x180009071`: `DataStoreServer::Initialize() failed to LoadDnaryXML():%!hresult!`
- `0x18000923c`: `DataStoreServer::Initialize() failed to Load IasXML from resource):%!hresult!`
- `0x1800091ec`: `DataStoreServer::Initialize() failed to Load IasTemplatesXML from resource):%!hresult!`
- `0x180008fc5`: `IDR_DNARY_XML_RES.XML`
- `0x18000900d`: ` DataStoreServer::LoadDnaryXML failed`
- `0x1800090a8`: `IDR_IAS_XML_RES.XML`
- `0x1800090e9`: ` DataStoreServer::LoadIASXML failed`
- `0x180009150`: `IDR_IASTEMPLATES_XML_RES.XML`
- `0x18000918c`: `DataStoreServer::LoadIasTemplatesFromResource failed: %!hresult!`
- `0x180008e63`: `\ias.xml`
- `0x180008e89`: `\iastemplates.xml`
- `0x180008e40`: `\dnary.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DataStoreServer::Initialize(DataStoreServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v3; // ebx
  signed int v4; // ebx
  LSTATUS DatabasePath; // eax
  bool v6; // cc
  HMODULE ModuleHandleW; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  DataStoreServer *v11; // rcx
  int XMLResource; // eax
  DataStoreServer *v13; // rcx
  _BYTE *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  DataStoreServer *v17; // rcx
  int v18; // eax
  signed int LastError; // esi
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  unsigned int v24; // [rsp+30h] [rbp-278h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-270h]
  WCHAR ModuleName[264]; // [rsp+40h] [rbp-268h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
  v3 = 0;
  while ( !TryEnterCriticalSection(v2) )
  {
    if ( ++v3 >= 100 )
    {
      EnterCriticalSection(v2);
      break;
    }
    SwitchToThread();
  }
  if ( !*((_QWORD *)this + 272) )
  {
    v4 = (**(__int64 (__fastcall ***)(DataStoreServer *))this)(this);
    if ( v4 < 0 )
      goto LABEL_75;
  }
  v24 = 260;
  DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\dnary.xsd", (BYTE *)this + 1094, &v24);
  v6 = DatabasePath <= 0;
  if ( DatabasePath )
    goto LABEL_87;
  v24 = 260;
  DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\dnary.xml", (BYTE *)this + 1616, &v24);
  v6 = DatabasePath <= 0;
  if ( DatabasePath
    || (v24 = 260,
        DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\ias.xml", (BYTE *)this + 50, &v24),
        v6 = DatabasePath <= 0,
        DatabasePath)
    || (v24 = 260,
        DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\iastemplates.xml", (BYTE *)this + 572, &v24),
        v6 = DatabasePath <= 0,
        DatabasePath) )
  {
LABEL_87:
    if ( v6 )
      v4 = DatabasePath;
    else
      v4 = (unsigned __int16)DatabasePath | 0x80070000;
    goto LABEL_90;
  }
  ModuleName[0] = 0;
  v4 = (*(__int64 (__fastcall **)(DataStoreServer *, WCHAR *, __int64))(*(_QWORD *)this + 8LL))(this, ModuleName, 261);
  if ( v4 < 0 )
  {
LABEL_75:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_76;
  }
  ModuleHandleW = GetModuleHandleW(ModuleName);
  *((_QWORD *)this + 273) = ModuleHandleW;
  if ( !ModuleHandleW )
  {
    LastError = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer::Initialize() failed GetModuleHandleW :0x%x");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    else
      v4 = LastError;
    goto LABEL_91;
  }
  v8 = *((_QWORD *)this + 268);
  if ( v8 )
  {
    *((_QWORD *)this + 268) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *((_QWORD *)this + 269);
  if ( v9 )
  {
    *((_QWORD *)this + 269) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = *((_QWORD *)this + 270);
  if ( v10 )
  {
    *((_QWORD *)this + 270) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = (DataStoreServer *)*((_QWORD *)this + 271);
  if ( v11 )
  {
    *((_QWORD *)this + 271) = 0;
    (*(void (__fastcall **)(DataStoreServer *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  *((_QWORD *)this + 274) = 0;
  *((_DWORD *)this + 554) = 0;
  *((_QWORD *)this + 275) = 0;
  *((_DWORD *)this + 555) = 0;
  *((_QWORD *)this + 276) = 0;
  *((_DWORD *)this + 556) = 0;
  XMLResource = DataStoreServer::LoadXMLResource(
                  v11,
                  *((HINSTANCE *)this + 273),
                  L"IDR_DNARY_XML_RES.XML",
                  (unsigned int *)this + 556,
                  (void **)this + 276);
  v4 = XMLResource;
  if ( XMLResource )
  {
    if ( XMLResource > 0 )
      v4 = (unsigned __int16)XMLResource | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    v13 = (DataStoreServer *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint(" DataStoreServer::LoadDnaryXML failed");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      v14 = WPP_GLOBAL_Control;
    }
    if ( v4 < 0 )
    {
LABEL_31:
      if ( v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 2u && (v14[28] & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::Initialize() failed to LoadDnaryXML():%!hresult!");
        v15 = 13;
LABEL_63:
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
LABEL_90:
        v14 = WPP_GLOBAL_Control;
        goto LABEL_91;
      }
      goto LABEL_91;
    }
  }
  else
  {
    v4 = 0;
    v14 = WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)this + 276) )
    goto LABEL_31;
  v4 = 0;
  v16 = DataStoreServer::LoadXMLResource(
          v13,
          *((HINSTANCE *)this + 273),
          L"IDR_IAS_XML_RES.XML",
          (unsigned int *)this + 554,
          (void **)this + 274);
  if ( !v16 )
    goto LABEL_45;
  if ( v16 > 0 )
    v4 = (unsigned __int16)v16 | 0x80070000;
  else
    v4 = v16;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint(" DataStoreServer::LoadIASXML failed");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
LABEL_45:
    v14 = WPP_GLOBAL_Control;
  }
  if ( v4 >= 0 && *((_QWORD *)this + 274) )
  {
    v4 = 0;
    v18 = DataStoreServer::LoadXMLResource(
            v17,
            *((HINSTANCE *)this + 273),
            L"IDR_IASTEMPLATES_XML_RES.XML",
            (unsigned int *)this + 555,
            (void **)this + 275);
    if ( v18 )
    {
      if ( v18 > 0 )
        v4 = (unsigned __int16)v18 | 0x80070000;
      else
        v4 = v18;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_57;
      }
      WppDbgPrint("DataStoreServer::LoadIasTemplatesFromResource failed: %!hresult!");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
    }
    v14 = WPP_GLOBAL_Control;
LABEL_57:
    if ( v4 >= 0 && *((_QWORD *)this + 275) )
      goto LABEL_92;
    if ( v14 == (_BYTE *)&WPP_GLOBAL_Control || v14[25] < 2u || (v14[28] & 0x10) == 0 )
      goto LABEL_91;
    WppDbgPrint("DataStoreServer::Initialize() failed to Load IasTemplatesXML from resource):%!hresult!");
    v15 = 15;
    goto LABEL_63;
  }
  if ( v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 2u && (v14[28] & 0x10) != 0 )
  {
    WppDbgPrint("DataStoreServer::Initialize() failed to Load IasXML from resource):%!hresult!");
    v15 = 14;
    goto LABEL_63;
  }
LABEL_91:
  if ( v4 >= 0 )
  {
LABEL_92:
    *((_BYTE *)this + 48) = 1;
    goto LABEL_86;
  }
LABEL_76:
  v20 = (void *)*((_QWORD *)this + 274);
  if ( v20 )
  {
    CoTaskMemFree(v20);
    *((_QWORD *)this + 274) = 0;
    v14 = WPP_GLOBAL_Control;
  }
  v21 = (void *)*((_QWORD *)this + 275);
  if ( v21 )
  {
    CoTaskMemFree(v21);
    *((_QWORD *)this + 275) = 0;
    v14 = WPP_GLOBAL_Control;
  }
  v22 = (void *)*((_QWORD *)this + 276);
  if ( v22 )
  {
    CoTaskMemFree(v22);
    *((_QWORD *)this + 276) = 0;
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 2u && (v14[28] & 0x10) != 0 )
  {
    WppDbgPrint("DataStoreServer::Initialize() failed:0x%x");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
  }
LABEL_86:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008d7c  push    rbx
0x180008d7e  push    rbp
0x180008d7f  push    rsi
0x180008d80  push    rdi
0x180008d81  push    r12
0x180008d83  push    r13
0x180008d85  push    r14
0x180008d87  push    r15
0x180008d89  sub     rsp, 268h
0x180008d90  mov     rax, cs:__security_cookie
0x180008d97  xor     rax, rsp
0x180008d9a  mov     [rsp+2A8h+var_58], rax
0x180008da2  mov     rdi, rcx
0x180008da5  lea     rsi, [rcx+8]
0x180008da9  mov     [rsp+2A8h+lpCriticalSection], rsi
0x180008dae  xor     ebx, ebx
0x180008db0  jmp     short loc_180008DBF
0x180008db2  inc     ebx
0x180008db4  cmp     ebx, 64h ; 'd'
0x180008db7  jge     short loc_180008DCE
0x180008db9  call    cs:__imp_SwitchToThread
0x180008dbf  mov     rcx, rsi; lpCriticalSection
0x180008dc2  call    cs:__imp_TryEnterCriticalSection
0x180008dc8  test    eax, eax
0x180008dca  jz      short loc_180008DB2
0x180008dcc  jmp     short loc_180008DD7
0x180008dce  mov     rcx, rsi; lpCriticalSection
0x180008dd1  call    cs:__imp_EnterCriticalSection
0x180008dd7  lea     rdx, [rdi+880h]
0x180008dde  lea     r15, WPP_GLOBAL_Control
0x180008de5  cmp     qword ptr [rdx], 0
0x180008de9  jnz     short loc_180008E05
0x180008deb  xor     esi, esi
0x180008ded  mov     rax, [rdi]
0x180008df0  mov     rcx, rdi
0x180008df3  mov     rax, [rax]
0x180008df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dfb  mov     ebx, eax
0x180008dfd  test    eax, eax
0x180008dff  js      loc_1800092BD
0x180008e05  mov     ebx, 104h
0x180008e0a  mov     [rsp+2A8h+var_278], ebx
0x180008e0e  lea     rdx, [rdi+446h]; Destination
0x180008e15  lea     r8, [rsp+2A8h+var_278]
0x180008e1a  lea     rcx, aDnaryXsd; "\\dnary.xsd"
0x180008e21  call    _anonymous_namespace___GetDatabasePath
0x180008e26  mov     esi, eax
0x180008e28  test    eax, eax
0x180008e2a  jnz     loc_1800093A0
0x180008e30  mov     [rsp+2A8h+var_278], ebx
0x180008e34  lea     rdx, [rdi+650h]; Destination
0x180008e3b  lea     r8, [rsp+2A8h+var_278]
0x180008e40  lea     rcx, aDnaryXml; "\\dnary.xml"
0x180008e47  call    _anonymous_namespace___GetDatabasePath
0x180008e4c  mov     esi, eax
0x180008e4e  test    eax, eax
0x180008e50  jnz     loc_1800093A0
0x180008e56  mov     [rsp+2A8h+var_278], ebx
0x180008e5a  lea     rdx, [rdi+32h]; Destination
0x180008e5e  lea     r8, [rsp+2A8h+var_278]
0x180008e63  lea     rcx, aIasXml; "\\ias.xml"
0x180008e6a  call    _anonymous_namespace___GetDatabasePath
0x180008e6f  mov     esi, eax
0x180008e71  test    eax, eax
0x180008e73  jnz     loc_1800093A0
0x180008e79  mov     [rsp+2A8h+var_278], ebx
0x180008e7d  lea     rdx, [rdi+23Ch]; Destination
0x180008e84  lea     r8, [rsp+2A8h+var_278]
0x180008e89  lea     rcx, aIastemplatesXm; "\\iastemplates.xml"
0x180008e90  call    _anonymous_namespace___GetDatabasePath
0x180008e95  mov     esi, eax
0x180008e97  test    eax, eax
0x180008e99  jnz     loc_1800093A0
0x180008e9f  mov     [rsp+2A8h+ModuleName], ax
0x180008ea4  mov     rax, [rdi]
0x180008ea7  lea     r8d, [rbx+1]
0x180008eab  lea     rdx, [rsp+2A8h+ModuleName]
0x180008eb0  mov     rcx, rdi
0x180008eb3  mov     rax, [rax+8]
0x180008eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebc  mov     ebx, eax
0x180008ebe  test    eax, eax
0x180008ec0  js      loc_1800092BD
0x180008ec6  lea     rcx, [rsp+2A8h+ModuleName]; lpModuleName
0x180008ecb  call    cs:__imp_GetModuleHandleW
0x180008ed1  mov     [rdi+888h], rax
0x180008ed8  test    rax, rax
0x180008edb  jz      loc_18000924F
0x180008ee1  mov     rcx, [rdi+860h]
0x180008ee8  test    rcx, rcx
0x180008eeb  jz      short loc_180008F05
0x180008eed  mov     qword ptr [rdi+860h], 0
0x180008ef8  mov     rax, [rcx]
0x180008efb  mov     rax, [rax+10h]
0x180008eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f04  nop
0x180008f05  mov     rcx, [rdi+868h]
0x180008f0c  test    rcx, rcx
0x180008f0f  jz      short loc_180008F29
0x180008f11  mov     qword ptr [rdi+868h], 0
0x180008f1c  mov     rax, [rcx]
0x180008f1f  mov     rax, [rax+10h]
0x180008f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f28  nop
0x180008f29  mov     rcx, [rdi+870h]
0x180008f30  test    rcx, rcx
0x180008f33  jz      short loc_180008F4D
0x180008f35  mov     qword ptr [rdi+870h], 0
0x180008f40  mov     rax, [rcx]
0x180008f43  mov     rax, [rax+10h]
0x180008f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4c  nop
0x180008f4d  mov     rcx, [rdi+878h]
0x180008f54  test    rcx, rcx
0x180008f57  jz      short loc_180008F71
0x180008f59  mov     qword ptr [rdi+878h], 0
0x180008f64  mov     rax, [rcx]
0x180008f67  mov     rax, [rax+10h]
0x180008f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f70  nop
0x180008f71  lea     r13, [rdi+890h]
0x180008f78  mov     qword ptr [r13+0], 0
0x180008f80  lea     r12, [rdi+8A8h]
0x180008f87  mov     dword ptr [r12], 0
0x180008f8f  mov     qword ptr [rdi+898h], 0
0x180008f9a  mov     dword ptr [rdi+8ACh], 0
0x180008fa4  lea     r15, [rdi+8A0h]
0x180008fab  mov     qword ptr [r15], 0
0x180008fb2  lea     r9, [rdi+8B0h]; unsigned int *
0x180008fb9  mov     dword ptr [r9], 0
0x180008fc0  mov     [rsp+2A8h+var_288], r15; void **
0x180008fc5  lea     r8, aIdrDnaryXmlRes; "IDR_DNARY_XML_RES.XML"
0x180008fcc  mov     rdx, [rdi+888h]; HINSTANCE
0x180008fd3  call    ?LoadXMLResource@DataStoreServer@@AEAAKPEAUHINSTANCE__@@PEBGAEAKAEAPEAX@Z; DataStoreServer::LoadXMLResource(HINSTANCE__ *,ushort const *,ulong &,void * &)
0x180008fd8  mov     ebx, eax
0x180008fda  mov     ebp, 80070000h
0x180008fdf  test    eax, eax
0x180008fe1  jz      loc_18000908C
0x180008fe7  jle     short loc_180008FEE
0x180008fe9  movzx   ebx, ax
0x180008fec  or      ebx, ebp
0x180008fee  mov     rax, cs:WPP_GLOBAL_Control
0x180008ff5  lea     rcx, WPP_GLOBAL_Control
0x180008ffc  cmp     rax, rcx
0x180008fff  jz      short loc_180009043
0x180009001  cmp     byte ptr [rax+19h], 2
0x180009005  jb      short loc_180009043
0x180009007  test    byte ptr [rax+1Ch], 10h
0x18000900b  jz      short loc_180009043
0x18000900d  lea     rcx, aDatastoreserve_15; " DataStoreServer::LoadDnaryXML failed"
0x180009014  call    WppDbgPrint
0x180009019  mov     edx, 3Ch ; '<'
0x18000901e  lea     r9, aNpsds; "NPSDS"
0x180009025  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000902c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009033  mov     rcx, [rcx+10h]
0x180009037  call    WPP_SF_s
0x18000903c  mov     rax, cs:WPP_GLOBAL_Control
0x180009043  mov     r14d, ebx
0x180009046  test    ebx, ebx
0x180009048  jns     short loc_180009098
0x18000904a  lea     r15, WPP_GLOBAL_Control
0x180009051  cmp     rax, r15
0x180009054  jz      loc_1800093B6
0x18000905a  cmp     byte ptr [rax+19h], 2
0x18000905e  jb      loc_1800093B6
0x180009064  test    byte ptr [rax+1Ch], 10h
0x180009068  jz      loc_1800093B6
0x18000906e  mov     edx, r14d
0x180009071  lea     rcx, aDatastoreserve_10; "DataStoreServer::Initialize() failed to"...
0x180009078  call    WppDbgPrint
0x18000907d  mov     edx, 0Dh
0x180009082  mov     dword ptr [rsp+2A8h+var_288], r14d
0x180009087  jmp     loc_180009201
0x18000908c  xor     r14d, r14d
0x18000908f  xor     ebx, ebx
0x180009091  mov     rax, cs:WPP_GLOBAL_Control
0x180009098  cmp     qword ptr [r15], 0
0x18000909c  jz      short loc_18000904A
0x18000909e  xor     ebx, ebx
0x1800090a0  mov     [rsp+2A8h+var_288], r13; void **
0x1800090a5  mov     r9, r12; unsigned int *
0x1800090a8  lea     r8, aIdrIasXmlResXm; "IDR_IAS_XML_RES.XML"
0x1800090af  mov     rdx, [rdi+888h]; HINSTANCE
0x1800090b6  call    ?LoadXMLResource@DataStoreServer@@AEAAKPEAUHINSTANCE__@@PEBGAEAKAEAPEAX@Z; DataStoreServer::LoadXMLResource(HINSTANCE__ *,ushort const *,ulong &,void * &)
0x1800090bb  test    eax, eax
0x1800090bd  jz      short loc_18000911A
0x1800090bf  jg      short loc_1800090C5
0x1800090c1  mov     ebx, eax
0x1800090c3  jmp     short loc_1800090CA
0x1800090c5  movzx   ebx, ax
0x1800090c8  or      ebx, ebp
0x1800090ca  mov     rax, cs:WPP_GLOBAL_Control
0x1800090d1  lea     r15, WPP_GLOBAL_Control
0x1800090d8  cmp     rax, r15
0x1800090db  jz      short loc_180009128
0x1800090dd  cmp     byte ptr [rax+19h], 2
0x1800090e1  jb      short loc_180009128
0x1800090e3  test    byte ptr [rax+1Ch], 10h
0x1800090e7  jz      short loc_180009128
0x1800090e9  lea     rcx, aDatastoreserve_19; " DataStoreServer::LoadIASXML failed"
0x1800090f0  call    WppDbgPrint
0x1800090f5  mov     edx, 3Dh ; '='
0x1800090fa  lea     r9, aNpsds; "NPSDS"
0x180009101  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180009108  mov     rcx, cs:WPP_GLOBAL_Control
0x18000910f  mov     rcx, [rcx+10h]
0x180009113  call    WPP_SF_s
0x180009118  jmp     short loc_180009121
0x18000911a  lea     r15, WPP_GLOBAL_Control
0x180009121  mov     rax, cs:WPP_GLOBAL_Control
0x180009128  test    ebx, ebx
0x18000912a  js      loc_18000921D
0x180009130  cmp     qword ptr [r13+0], 0
0x180009135  jz      loc_18000921D
0x18000913b  xor     ebx, ebx
0x18000913d  lea     r14, [rdi+898h]
0x180009144  mov     [rsp+2A8h+var_288], r14; void **
0x180009149  lea     r9, [rdi+8ACh]; unsigned int *
0x180009150  lea     r8, aIdrIastemplate; "IDR_IASTEMPLATES_XML_RES.XML"
0x180009157  mov     rdx, [rdi+888h]; HINSTANCE
0x18000915e  call    ?LoadXMLResource@DataStoreServer@@AEAAKPEAUHINSTANCE__@@PEBGAEAKAEAPEAX@Z; DataStoreServer::LoadXMLResource(HINSTANCE__ *,ushort const *,ulong &,void * &)
0x180009163  test    eax, eax
0x180009165  jz      short loc_1800091B8
0x180009167  jg      short loc_18000916D
0x180009169  mov     ebx, eax
0x18000916b  jmp     short loc_180009172
0x18000916d  movzx   ebx, ax
0x180009170  or      ebx, ebp
0x180009172  mov     rax, cs:WPP_GLOBAL_Control
0x180009179  cmp     rax, r15
0x18000917c  jz      short loc_1800091BF
0x18000917e  cmp     byte ptr [rax+19h], 2
0x180009182  jb      short loc_1800091BF
0x180009184  test    byte ptr [rax+1Ch], 10h
0x180009188  jz      short loc_1800091BF
0x18000918a  mov     edx, ebx
0x18000918c  lea     rcx, aDatastoreserve_11; "DataStoreServer::LoadIasTemplatesFromRe"...
0x180009193  call    WppDbgPrint
0x180009198  mov     edx, 3Eh ; '>'
0x18000919d  mov     dword ptr [rsp+2A8h+var_288], ebx
0x1800091a1  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x1800091a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091af  mov     rcx, [rcx+10h]
0x1800091b3  call    WPP_SF_sd
0x1800091b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800091bf  test    ebx, ebx
0x1800091c1  js      short loc_1800091CD
0x1800091c3  cmp     qword ptr [r14], 0
0x1800091c7  jnz     loc_1800093BE
0x1800091cd  cmp     rax, r15
0x1800091d0  jz      loc_1800093B6
0x1800091d6  cmp     byte ptr [rax+19h], 2
0x1800091da  jb      loc_1800093B6
0x1800091e0  test    byte ptr [rax+1Ch], 10h
0x1800091e4  jz      loc_1800093B6
0x1800091ea  mov     edx, ebx
0x1800091ec  lea     rcx, aDatastoreserve_14; "DataStoreServer::Initialize() failed to"...
0x1800091f3  call    WppDbgPrint
0x1800091f8  mov     edx, 0Fh
0x1800091fd  mov     dword ptr [rsp+2A8h+var_288], ebx
0x180009201  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180009208  mov     rcx, cs:WPP_GLOBAL_Control
0x18000920f  mov     rcx, [rcx+10h]
0x180009213  call    WPP_SF_sd
0x180009218  jmp     loc_1800093AF
0x18000921d  cmp     rax, r15
0x180009220  jz      loc_1800093B6
0x180009226  cmp     byte ptr [rax+19h], 2
0x18000922a  jb      loc_1800093B6
0x180009230  test    byte ptr [rax+1Ch], 10h
0x180009234  jz      loc_1800093B6
0x18000923a  mov     edx, ebx
0x18000923c  lea     rcx, aDatastoreserve; "DataStoreServer::Initialize() failed to"...
0x180009243  call    WppDbgPrint
0x180009248  mov     edx, 0Eh
0x18000924d  jmp     short loc_1800091FD
0x18000924f  call    cs:__imp_GetLastError
0x180009255  mov     esi, eax
0x180009257  mov     rax, cs:WPP_GLOBAL_Control
0x18000925e  cmp     rax, r15
0x180009261  jz      short loc_1800092A4
0x180009263  cmp     byte ptr [rax+19h], 2
0x180009267  jb      short loc_1800092A4
0x180009269  test    byte ptr [rax+1Ch], 10h
0x18000926d  jz      short loc_1800092A4
0x18000926f  mov     edx, esi
0x180009271  lea     rcx, aDatastoreserve_8; "DataStoreServer::Initialize() failed Ge"...
0x180009278  call    WppDbgPrint
0x18000927d  mov     edx, 0Ch
0x180009282  mov     dword ptr [rsp+2A8h+var_288], esi
0x180009286  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000928d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009294  mov     rcx, [rcx+10h]
0x180009298  call    WPP_SF_sd
0x18000929d  mov     rax, cs:WPP_GLOBAL_Control
0x1800092a4  test    esi, esi
0x1800092a6  jg      short loc_1800092AF
0x1800092a8  mov     ebx, esi
0x1800092aa  jmp     loc_1800093B6
  ... truncated ...
```
