# MF::DeviceEnumeration::OpenKSDevice(ulong,void * *)

- ea: `0x180070834`
- end: `0x180070e4f`
- name: `?OpenKSDevice@DeviceEnumeration@MF@@YAJKPEAPEAX@Z`
- size: `1563`
- prototype: `__int64 __fastcall(MF::DeviceEnumeration *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006f528`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180070834`
- `0x180120030`
- `0x18012003c`
- `0x180128588`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a97`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070a85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070a85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070a24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070a24`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180070c8e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180070d5c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180070c8e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180070d5c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180070919`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180070919`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x1800709ec`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x1800709ec`

## string_xrefs

- `0x180070849`: `MF::DeviceEnumeration::OpenKSDevice`

## pseudocode

```c
__int64 __fastcall MF::DeviceEnumeration::OpenKSDevice(MF::DeviceEnumeration *this, _QWORD *a2, void **a3)
{
  CallStackTracing *v4; // rcx
  int v5; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  CONFIGRET Device_Interface_List_SizeW; // eax
  WCHAR *v9; // rax
  WCHAR *v10; // rsi
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  CONFIGRET Device_Interface_ListW; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  signed int v23; // eax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  signed int v26; // eax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackScopeTrace v30; // [rsp+70h] [rbp+8h] BYREF
  ULONG pulLen; // [rsp+78h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+18h] BYREF

  pulLen = 0;
  ppv = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v30, "MF::DeviceEnumeration::OpenKSDevice", 831);
  if ( !a2 )
  {
    v4 = CallStackTracing::s_wpInstance;
    v5 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v4 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v4->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MF::DeviceEnumeration::OpenKSDevice", 831, -2147467261);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v7 = 31;
LABEL_86:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids, 0, v5);
      goto LABEL_87;
    }
    goto LABEL_87;
  }
  *a2 = -1;
  Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(
                                  &pulLen,
                                  &GUID_3c0d501a_140b_11d1_b40f_00a0c9223196,
                                  0,
                                  0);
  if ( Device_Interface_List_SizeW )
  {
    v26 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
    v5 = v26;
    if ( v26 > 0 )
      v5 = (unsigned __int16)v26 | 0x80070000;
    if ( v5 < 0 )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v27->m_fEnabled )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( v28->m_result != v5 )
          CallStackContext::TraceFailure(v28, "MF::DeviceEnumeration::OpenKSDevice", 908, v5);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v7 = 38;
        goto LABEL_86;
      }
    }
    goto LABEL_87;
  }
  v9 = (WCHAR *)operator new[](saturated_mul(pulLen, 2u));
  v10 = v9;
  if ( v9 )
  {
    Device_Interface_ListW = CM_Get_Device_Interface_ListW(&GUID_3c0d501a_140b_11d1_b40f_00a0c9223196, 0, v9, pulLen, 0);
    if ( Device_Interface_ListW || !*v10 )
    {
      v23 = CM_MapCrToWin32Err(Device_Interface_ListW, 0xDu);
      v5 = v23;
      if ( v23 > 0 )
        v5 = (unsigned __int16)v23 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_73;
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v24->m_fEnabled )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( v25->m_result != v5 )
          CallStackContext::TraceFailure(v25, "MF::DeviceEnumeration::OpenKSDevice", 902, v5);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_73;
      v18 = 37;
    }
    else
    {
      v5 = CoCreateInstance(&CLSID_DeviceBroker, 0, 1u, &GUID_8604b268_34a6_4b1a_a59f_cdbd8379fd98, &ppv);
      if ( v5 == -2147221164 )
      {
        if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 33, &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids);
        *a2 = -1;
        FileW = CreateFileW(v10, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
        *a2 = FileW;
        if ( FileW != (HANDLE)-1LL )
          goto LABEL_73;
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
          goto LABEL_73;
        v16 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v16 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v16->m_fEnabled )
        {
          v17 = CallStackTracing::GetThreadRelativeContext(v16);
          if ( v17->m_result != v5 )
            CallStackContext::TraceFailure(v17, "MF::DeviceEnumeration::OpenKSDevice", 883, v5);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_73;
        v18 = 34;
      }
      else if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, _QWORD, _DWORD, _QWORD *))(*(_QWORD *)ppv + 24LL))(
               ppv,
               v10,
               1073741952,
               0,
               0,
               a2);
        if ( v5 >= 0 )
          goto LABEL_73;
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v21->m_fEnabled )
        {
          v22 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( v22->m_result != v5 )
            CallStackContext::TraceFailure(v22, "MF::DeviceEnumeration::OpenKSDevice", 895, v5);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_73;
        v18 = 36;
      }
      else
      {
        v19 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v19 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v19->m_fEnabled )
        {
          v20 = CallStackTracing::GetThreadRelativeContext(v19);
          if ( v20->m_result != v5 )
            CallStackContext::TraceFailure(v20, "MF::DeviceEnumeration::OpenKSDevice", 888, v5);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_73;
        v18 = 35;
      }
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids, 0, v5);
LABEL_73:
    operator delete(v10);
    goto LABEL_87;
  }
  v11 = CallStackTracing::s_wpInstance;
  v5 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v11 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v11->m_fEnabled )
  {
    v12 = CallStackTracing::GetThreadRelativeContext(v11);
    if ( v12->m_result != -2147024882 )
      CallStackContext::TraceFailure(v12, "MF::DeviceEnumeration::OpenKSDevice", 847, -2147024882);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v7 = 32;
    goto LABEL_86;
  }
LABEL_87:
  CallStackScopeTrace::~CallStackScopeTrace(&v30);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180070834  mov     rax, rsp
0x180070837  mov     [rax+20h], rbx
0x18007083b  push    rbp
0x18007083c  push    rsi
0x18007083d  push    rdi
0x18007083e  push    r14
0x180070840  push    r15
0x180070842  sub     rsp, 40h
0x180070846  mov     rdi, rdx
0x180070849  lea     r14, aMfDeviceenumer; "MF::DeviceEnumeration::OpenKSDevice"
0x180070850  xor     ebp, ebp
0x180070852  lea     rcx, [rax+8]; this
0x180070856  mov     esi, 33Fh
0x18007085b  mov     [rax+10h], ebp
0x18007085e  mov     r8d, esi; int
0x180070861  mov     [rax+18h], rbp
0x180070865  mov     rdx, r14; char *
0x180070868  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007086d  test    rdi, rdi
0x180070870  jnz     loc_180070900
0x180070876  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007087d  mov     ebx, 80004003h
0x180070882  test    rcx, rcx
0x180070885  jnz     short loc_1800708C5
0x180070887  mov     rax, cs:stru_1801FC290.__vftable
0x18007088e  lea     rcx, stru_1801FC290
0x180070895  mov     edx, 7F0h
0x18007089a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800708a1  mov     rax, [rax+8]
0x1800708a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800708aa  test    eax, eax
0x1800708ac  jnz     short loc_1800708BE
0x1800708ae  lea     rcx, stru_1801F8A30
0x1800708b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800708bc  jmp     short loc_1800708C5
0x1800708be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800708c5  cmp     [rcx+8], bpl
0x1800708c9  jz      short loc_1800708E9
0x1800708cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800708d0  cmp     [rax+7CCh], ebx
0x1800708d6  jz      short loc_1800708E9
0x1800708d8  mov     r9d, ebx; int
0x1800708db  mov     r8d, esi; int
0x1800708de  mov     rdx, r14; char *
0x1800708e1  mov     rcx, rax; this
0x1800708e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800708e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800708f0  jb      loc_180070E16
0x1800708f6  mov     edx, 1Fh
0x1800708fb  jmp     loc_180070DF8
0x180070900  or      r15, 0FFFFFFFFFFFFFFFFh
0x180070904  lea     rdx, _GUID_3c0d501a_140b_11d1_b40f_00a0c9223196; InterfaceClassGuid
0x18007090b  xor     r9d, r9d; ulFlags
0x18007090e  mov     [rdi], r15
0x180070911  xor     r8d, r8d; pDeviceID
0x180070914  lea     rcx, [rsp+68h+pulLen]; pulLen
0x180070919  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x18007091f  test    eax, eax
0x180070921  jnz     loc_180070D55
0x180070927  mov     ecx, [rsp+68h+pulLen]
0x18007092b  lea     eax, [r15+3]
0x18007092f  mul     rcx
0x180070932  cmovb   rax, r15
0x180070936  mov     rcx, rax; unsigned __int64
0x180070939  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007093e  mov     rsi, rax
0x180070941  test    rax, rax
0x180070944  jnz     loc_1800709D7
0x18007094a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070951  mov     ebx, 8007000Eh
0x180070956  test    rcx, rcx
0x180070959  jnz     short loc_180070999
0x18007095b  mov     rax, cs:stru_1801FC290.__vftable
0x180070962  lea     rcx, stru_1801FC290
0x180070969  mov     edx, 7F0h
0x18007096e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070975  mov     rax, [rax+8]
0x180070979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007097e  test    eax, eax
0x180070980  jnz     short loc_180070992
0x180070982  lea     rcx, stru_1801F8A30
0x180070989  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070990  jmp     short loc_180070999
0x180070992  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180070999  cmp     [rcx+8], bpl
0x18007099d  jz      short loc_1800709C0
0x18007099f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800709a4  cmp     [rax+7CCh], ebx
0x1800709aa  jz      short loc_1800709C0
0x1800709ac  mov     r9d, ebx; int
0x1800709af  mov     r8d, 34Fh; int
0x1800709b5  mov     rdx, r14; char *
0x1800709b8  mov     rcx, rax; this
0x1800709bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800709c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800709c7  jb      loc_180070E16
0x1800709cd  mov     edx, 20h ; ' '
0x1800709d2  jmp     loc_180070DF8
0x1800709d7  mov     r9d, [rsp+68h+pulLen]; BufferLen
0x1800709dc  lea     rcx, _GUID_3c0d501a_140b_11d1_b40f_00a0c9223196; InterfaceClassGuid
0x1800709e3  mov     r8, rsi; Buffer
0x1800709e6  mov     [rsp+68h+ulFlags], ebp; ulFlags
0x1800709ea  xor     edx, edx; pDeviceID
0x1800709ec  call    cs:__imp_CM_Get_Device_Interface_ListW
0x1800709f2  test    eax, eax
0x1800709f4  jnz     loc_180070C87
0x1800709fa  cmp     [rsi], bp
0x1800709fd  jz      loc_180070C87
0x180070a03  xor     edx, edx; pUnkOuter
0x180070a05  lea     rax, [rsp+68h+ppv]
0x180070a0d  lea     r9, _GUID_8604b268_34a6_4b1a_a59f_cdbd8379fd98; riid
0x180070a14  mov     qword ptr [rsp+68h+ulFlags], rax; ppv
0x180070a19  lea     rcx, CLSID_DeviceBroker; rclsid
0x180070a20  lea     r8d, [rdx+1]; dwClsContext
0x180070a24  call    cs:__imp_CoCreateInstance
0x180070a2a  mov     ebx, eax
0x180070a2c  cmp     eax, 80040154h
0x180070a31  jnz     loc_180070B3C
0x180070a37  cmp     cs:byte_1801FD28B, 20h ; ' '
0x180070a3e  jb      short loc_180070A5F
0x180070a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a47  lea     r8, WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids
0x180070a4e  mov     edx, 21h ; '!'
0x180070a53  mov     rcx, [rcx+88h]
0x180070a5a  call    WPP_SF_
0x180070a5f  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x180070a64  xor     r9d, r9d; lpSecurityAttributes
0x180070a67  mov     [rsp+68h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180070a6f  xor     r8d, r8d; dwShareMode
0x180070a72  mov     edx, 0C0000000h; dwDesiredAccess
0x180070a77  mov     [rsp+68h+ulFlags], 3; dwCreationDisposition
0x180070a7f  mov     rcx, rsi; lpFileName
0x180070a82  mov     [rdi], r15
0x180070a85  call    cs:__imp_CreateFileW
0x180070a8b  mov     [rdi], rax
0x180070a8e  cmp     rax, r15
0x180070a91  jnz     loc_180070D48
0x180070a97  call    cs:__imp_GetLastError
0x180070a9d  mov     ebx, eax
0x180070a9f  test    eax, eax
0x180070aa1  jle     short loc_180070AAC
0x180070aa3  movzx   ebx, ax
0x180070aa6  or      ebx, 80070000h
0x180070aac  test    ebx, ebx
0x180070aae  jns     loc_180070D48
0x180070ab4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070abb  test    rcx, rcx
0x180070abe  jnz     short loc_180070AFE
0x180070ac0  mov     rax, cs:stru_1801FC290.__vftable
0x180070ac7  lea     rcx, stru_1801FC290
0x180070ace  mov     edx, 7F0h
0x180070ad3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070ada  mov     rax, [rax+8]
0x180070ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ae3  test    eax, eax
0x180070ae5  jnz     short loc_180070AF7
0x180070ae7  lea     rcx, stru_1801F8A30
0x180070aee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070af5  jmp     short loc_180070AFE
0x180070af7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180070afe  cmp     [rcx+8], bpl
0x180070b02  jz      short loc_180070B25
0x180070b04  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070b09  cmp     [rax+7CCh], ebx
0x180070b0f  jz      short loc_180070B25
0x180070b11  mov     r9d, ebx; int
0x180070b14  mov     r8d, 373h; int
0x180070b1a  mov     rdx, r14; char *
0x180070b1d  mov     rcx, rax; this
0x180070b20  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070b25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070b2c  jb      loc_180070D48
0x180070b32  mov     edx, 22h ; '"'
0x180070b37  jmp     loc_180070D2A
0x180070b3c  test    ebx, ebx
0x180070b3e  jns     loc_180070BCC
0x180070b44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070b4b  test    rcx, rcx
0x180070b4e  jnz     short loc_180070B8E
0x180070b50  mov     rax, cs:stru_1801FC290.__vftable
0x180070b57  lea     rcx, stru_1801FC290
0x180070b5e  mov     edx, 7F0h
0x180070b63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070b6a  mov     rax, [rax+8]
0x180070b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b73  test    eax, eax
0x180070b75  jnz     short loc_180070B87
0x180070b77  lea     rcx, stru_1801F8A30
0x180070b7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070b85  jmp     short loc_180070B8E
0x180070b87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180070b8e  cmp     [rcx+8], bpl
0x180070b92  jz      short loc_180070BB5
0x180070b94  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070b99  cmp     [rax+7CCh], ebx
0x180070b9f  jz      short loc_180070BB5
0x180070ba1  mov     r9d, ebx; int
0x180070ba4  mov     r8d, 378h; int
0x180070baa  mov     rdx, r14; char *
0x180070bad  mov     rcx, rax; this
0x180070bb0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070bb5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070bbc  jb      loc_180070D48
0x180070bc2  mov     edx, 23h ; '#'
0x180070bc7  jmp     loc_180070D2A
0x180070bcc  mov     rcx, [rsp+68h+ppv]
0x180070bd4  xor     r9d, r9d
0x180070bd7  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rdi
0x180070bdc  mov     r8d, 40000080h
0x180070be2  mov     rdx, rsi
0x180070be5  mov     [rsp+68h+ulFlags], ebp
0x180070be9  mov     rax, [rcx]
0x180070bec  mov     rax, [rax+18h]
0x180070bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bf5  mov     ebx, eax
0x180070bf7  test    eax, eax
0x180070bf9  jns     loc_180070D48
0x180070bff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070c06  test    rcx, rcx
0x180070c09  jnz     short loc_180070C49
0x180070c0b  mov     rax, cs:stru_1801FC290.__vftable
0x180070c12  lea     rcx, stru_1801FC290
0x180070c19  mov     edx, 7F0h
0x180070c1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070c25  mov     rax, [rax+8]
0x180070c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c2e  test    eax, eax
0x180070c30  jnz     short loc_180070C42
0x180070c32  lea     rcx, stru_1801F8A30
0x180070c39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070c40  jmp     short loc_180070C49
0x180070c42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180070c49  cmp     [rcx+8], bpl
0x180070c4d  jz      short loc_180070C70
0x180070c4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070c54  cmp     [rax+7CCh], ebx
0x180070c5a  jz      short loc_180070C70
0x180070c5c  mov     r9d, ebx; int
0x180070c5f  mov     r8d, 37Fh; int
0x180070c65  mov     rdx, r14; char *
0x180070c68  mov     rcx, rax; this
0x180070c6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070c70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070c77  jb      loc_180070D48
0x180070c7d  mov     edx, 24h ; '$'
0x180070c82  jmp     loc_180070D2A
0x180070c87  mov     edx, 0Dh; DefaultErr
0x180070c8c  mov     ecx, eax; CmReturnCode
0x180070c8e  call    cs:__imp_CM_MapCrToWin32Err
0x180070c94  mov     ebx, eax
0x180070c96  test    eax, eax
0x180070c98  jle     short loc_180070CA3
0x180070c9a  movzx   ebx, ax
0x180070c9d  or      ebx, 80070000h
0x180070ca3  test    ebx, ebx
0x180070ca5  jns     loc_180070D48
0x180070cab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070cb2  test    rcx, rcx
0x180070cb5  jnz     short loc_180070CF5
0x180070cb7  mov     rax, cs:stru_1801FC290.__vftable
0x180070cbe  lea     rcx, stru_1801FC290
0x180070cc5  mov     edx, 7F0h
0x180070cca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070cd1  mov     rax, [rax+8]
0x180070cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070cda  test    eax, eax
0x180070cdc  jnz     short loc_180070CEE
0x180070cde  lea     rcx, stru_1801F8A30
0x180070ce5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070cec  jmp     short loc_180070CF5
0x180070cee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180070cf5  cmp     [rcx+8], bpl
0x180070cf9  jz      short loc_180070D1C
0x180070cfb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070d00  cmp     [rax+7CCh], ebx
0x180070d06  jz      short loc_180070D1C
0x180070d08  mov     r9d, ebx; int
0x180070d0b  mov     r8d, 386h; int
0x180070d11  mov     rdx, r14; char *
0x180070d14  mov     rcx, rax; this
0x180070d17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070d1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070d23  jb      short loc_180070D48
0x180070d25  mov     edx, 25h ; '%'
0x180070d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180070d31  lea     r8, WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids
0x180070d38  xor     r9d, r9d
0x180070d3b  mov     [rsp+68h+ulFlags], ebx
0x180070d3f  mov     rcx, [rcx+10h]
0x180070d43  call    WPP_SF_qD
0x180070d48  mov     rcx, rsi; void *
0x180070d4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070d50  jmp     loc_180070E16
0x180070d55  mov     edx, 0Dh; DefaultErr
0x180070d5a  mov     ecx, eax; CmReturnCode
0x180070d5c  call    cs:__imp_CM_MapCrToWin32Err
0x180070d62  mov     ebx, eax
0x180070d64  test    eax, eax
0x180070d66  jle     short loc_180070D71
0x180070d68  movzx   ebx, ax
  ... truncated ...
```
