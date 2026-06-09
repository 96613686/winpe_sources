# HrOnCommandProperties(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x18001cb40`
- end: `0x18001cda9`
- name: `?HrOnCommandProperties@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(_QWORD *, HWND)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180019360`

## callees

- `0x180007de0`
- `0x180018d74`
- `0x18001bc10`
- `0x18001c91c`
- `0x18001c9f8`
- `0x18001cb40`
- `0x18001cdb0`
- `0x18001ce7c`
- `0x18001d580`
- `0x18001e1e0`
- `0x180034ba0`
- `0x180040a5c`
- `0x180049e0c`
- `0x18004bf00`
- `0x18004c388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cc0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cc0d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001cd04`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001cd04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc16`
- `ole32!StringFromGUID2` at `0x18001ccf0`
- `ole32!StringFromGUID2` at `0x18001ccf0`

## pseudocode

```c
__int64 __fastcall HrOnCommandProperties(_QWORD *a1, HWND a2)
{
  __int64 *v4; // rsi
  int v5; // ebx
  HANDLE MutexW; // rdi
  __int64 v7; // rax
  unsigned int v8; // r9d
  __int64 v10; // rdx
  int Win32Error; // eax
  struct IUnknown *v12; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v13[42]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+190h] [rbp+90h] BYREF

  v12 = 0;
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "NetworkConnectionAction");
  v13[0] = &NetworkLegacyUxTelemetry::NetworkConnectionAction::`vftable';
  NetworkLegacyUxTelemetry::NetworkConnectionAction::StartActivity(
    (NetworkLegacyUxTelemetry::NetworkConnectionAction *)v13,
    L"ShowProperties");
  v4 = (__int64 *)*a1;
  if ( *a1 == a1[1] )
  {
    v5 = 0;
    goto LABEL_13;
  }
  MutexW = 0;
  v7 = *v4;
  if ( !*v4 )
  {
    v5 = -2147024809;
LABEL_33:
    v8 = 1100;
    goto LABEL_9;
  }
  if ( (*(_BYTE *)(v7 + 44) & 0x20) == 0 || !*(_DWORD *)(v7 + 48) )
  {
    if ( (((*(_DWORD *)(v7 + 48) - 3) & 0xFFFFFFFB) != 0 || (unsigned int)FHasPermission(0xEu))
      && (!(unsigned int)IsMediaRASType((enum tagNETCON_MEDIATYPE)*(_DWORD *)(*v4 + 48))
       || (unsigned int)FHasPermission((*(_DWORD *)(v10 + 44) & 1u) + 15) == 1) )
    {
      v5 = HrNetConFromPidl(*a1, &v12, 1);
      if ( v5 >= 0 )
      {
        SetLUAParent(v12, a2);
        StringFromGUID2((const GUID *const)(*v4 + 28), sz, 39);
        MutexW = CreateMutexW(0, 1, sz);
        if ( !MutexW || GetLastError() == 183 )
        {
          if ( GetLastError() == 183 )
          {
            ActivateDialog(0, v12);
            goto LABEL_10;
          }
          Win32Error = HrFromLastWin32Error();
        }
        else
        {
          Win32Error = HrRaiseConnectionPropertiesInternal(a2);
        }
        v5 = Win32Error;
        if ( Win32Error >= 0 )
          goto LABEL_10;
      }
      if ( v5 == -2147418113 )
        goto LABEL_8;
      if ( v5 == -2147220764 )
        goto LABEL_10;
      if ( v5 != -2147024891 )
      {
        if ( v5 == -2147024882 )
        {
          v8 = 1101;
          goto LABEL_9;
        }
        if ( v5 == -2147024156 )
          goto LABEL_10;
        goto LABEL_33;
      }
    }
    else
    {
      v5 = -2147024891;
    }
    v8 = 1096;
    goto LABEL_9;
  }
  v5 = -2147418113;
LABEL_8:
  v8 = 1106;
LABEL_9:
  NcMsgBox(hInst, a2, 0x424u, v8, 0x30u);
LABEL_10:
  if ( MutexW )
  {
    ReleaseMutex(MutexW);
    CloseHandle(MutexW);
  }
  ReleaseObj(v12);
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v13,
    (unsigned int)v5);
LABEL_13:
  NetworkLegacyUxTelemetry::NetworkConnectionAction::~NetworkConnectionAction((NetworkLegacyUxTelemetry::NetworkConnectionAction *)v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001cb40  mov     [rsp-8+arg_10], rbx
0x18001cb45  push    rbp
0x18001cb46  push    rsi
0x18001cb47  push    rdi
0x18001cb48  push    r14
0x18001cb4a  push    r15
0x18001cb4c  lea     rbp, [rsp-0F0h]
0x18001cb54  sub     rsp, 1F0h
0x18001cb5b  mov     rax, cs:__security_cookie
0x18001cb62  xor     rax, rsp
0x18001cb65  mov     [rbp+110h+var_30], rax
0x18001cb6c  mov     r15, rdx
0x18001cb6f  mov     r14, rcx
0x18001cb72  mov     [rsp+210h+var_1E0], 0
0x18001cb7b  lea     rdx, aNetworkconnect; "NetworkConnectionAction"
0x18001cb82  lea     rcx, [rsp+210h+var_1D0]
0x18001cb87  call    ??0?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001cb8c  lea     rax, ??_7NetworkConnectionAction@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::NetworkConnectionAction::`vftable'
0x18001cb93  mov     [rsp+210h+var_1D0], rax
0x18001cb98  lea     rdx, aShowproperties; "ShowProperties"
0x18001cb9f  lea     rcx, [rsp+210h+var_1D0]; this
0x18001cba4  call    ?StartActivity@NetworkConnectionAction@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z; NetworkLegacyUxTelemetry::NetworkConnectionAction::StartActivity(ushort const *)
0x18001cba9  mov     rsi, [r14]
0x18001cbac  cmp     rsi, [r14+8]
0x18001cbb0  jnz     short loc_18001CBB6
0x18001cbb2  xor     ebx, ebx
0x18001cbb4  jmp     short loc_18001CC33
0x18001cbb6  xor     edi, edi
0x18001cbb8  mov     rax, [rsi]
0x18001cbbb  test    rax, rax
0x18001cbbe  jnz     short loc_18001CBCA
0x18001cbc0  mov     ebx, 80070057h
0x18001cbc5  jmp     loc_18001CD92
0x18001cbca  test    byte ptr [rax+2Ch], 20h
0x18001cbce  jz      loc_18001CC65
0x18001cbd4  cmp     [rax+30h], edi
0x18001cbd7  jz      loc_18001CC65
0x18001cbdd  mov     ebx, 8000FFFFh
0x18001cbe2  mov     r9d, 452h; unsigned int
0x18001cbe8  mov     [rsp+210h+uType], 30h ; '0'; uType
0x18001cbf0  mov     r8d, 424h; unsigned int
0x18001cbf6  mov     rdx, r15; hWnd
0x18001cbf9  mov     rcx, cs:hInst; hModule
0x18001cc00  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001cc05  test    rdi, rdi
0x18001cc08  jz      short loc_18001CC1C
0x18001cc0a  mov     rcx, rdi; hMutex
0x18001cc0d  call    cs:__imp_ReleaseMutex
0x18001cc13  mov     rcx, rdi; hObject
0x18001cc16  call    cs:__imp_CloseHandle
0x18001cc1c  mov     rcx, [rsp+210h+var_1E0]; struct IUnknown *
0x18001cc21  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001cc26  mov     edx, ebx
0x18001cc28  lea     rcx, [rsp+210h+var_1D0]
0x18001cc2d  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001cc32  nop
0x18001cc33  lea     rcx, [rsp+210h+var_1D0]; this
0x18001cc38  call    ??1NetworkConnectionAction@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::NetworkConnectionAction::~NetworkConnectionAction(void)
0x18001cc3d  mov     eax, ebx
0x18001cc3f  mov     rcx, [rbp+110h+var_30]
0x18001cc46  xor     rcx, rsp; StackCookie
0x18001cc49  call    __security_check_cookie
0x18001cc4e  mov     rbx, [rsp+210h+arg_10]
0x18001cc56  add     rsp, 1F0h
0x18001cc5d  pop     r15
0x18001cc5f  pop     r14
0x18001cc61  pop     rdi
0x18001cc62  pop     rsi
0x18001cc63  pop     rbp
0x18001cc64  retn
0x18001cc65  mov     eax, [rax+30h]
0x18001cc68  sub     eax, 3
0x18001cc6b  test    eax, 0FFFFFFFBh
0x18001cc70  jnz     short loc_18001CC90
0x18001cc72  mov     ecx, 0Eh; unsigned int
0x18001cc77  call    ?FHasPermission@@YAHK@Z; FHasPermission(ulong)
0x18001cc7c  test    eax, eax
0x18001cc7e  jnz     short loc_18001CC90
0x18001cc80  mov     ebx, 80070005h
0x18001cc85  mov     r9d, 448h
0x18001cc8b  jmp     loc_18001CBE8
0x18001cc90  mov     rdx, [rsi]
0x18001cc93  mov     ecx, [rdx+30h]; enum tagNETCON_MEDIATYPE
0x18001cc96  call    ?IsMediaRASType@@YAHW4tagNETCON_MEDIATYPE@@@Z; IsMediaRASType(tagNETCON_MEDIATYPE)
0x18001cc9b  test    eax, eax
0x18001cc9d  jz      short loc_18001CCB2
0x18001cc9f  mov     ecx, [rdx+2Ch]
0x18001cca2  and     ecx, 1
0x18001cca5  add     ecx, 0Fh; unsigned int
0x18001cca8  call    ?FHasPermission@@YAHK@Z; FHasPermission(ulong)
0x18001ccad  cmp     eax, 1
0x18001ccb0  jnz     short loc_18001CC80
0x18001ccb2  mov     r8d, 1
0x18001ccb8  lea     rdx, [rsp+210h+var_1E0]
0x18001ccbd  mov     rcx, [r14]
0x18001ccc0  call    ?HrNetConFromPidl@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEAPEAUINetConnection@@H@Z; HrNetConFromPidl(CPConFoldPidl<ConFoldPidl_v3> const &,INetConnection * *,int)
0x18001ccc5  mov     ebx, eax
0x18001ccc7  test    eax, eax
0x18001ccc9  js      loc_18001CD5A
0x18001cccf  mov     rdx, r15; HWND
0x18001ccd2  mov     rcx, [rsp+210h+var_1E0]; struct IUnknown *
0x18001ccd7  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x18001ccdc  mov     rcx, [rsi]
0x18001ccdf  add     rcx, 1Ch; rguid
0x18001cce3  mov     r8d, 27h ; '''; cchMax
0x18001cce9  lea     rdx, [rbp+110h+sz]; lpsz
0x18001ccf0  call    cs:__imp_StringFromGUID2
0x18001ccf6  lea     r8, [rbp+110h+sz]; lpName
0x18001ccfd  mov     edx, 1; bInitialOwner
0x18001cd02  xor     ecx, ecx; lpMutexAttributes
0x18001cd04  call    cs:__imp_CreateMutexW
0x18001cd0a  mov     rdi, rax
0x18001cd0d  mov     esi, 0B7h
0x18001cd12  test    rax, rax
0x18001cd15  jz      short loc_18001CD30
0x18001cd17  call    cs:__imp_GetLastError
0x18001cd1d  cmp     eax, esi
0x18001cd1f  jz      short loc_18001CD30
0x18001cd21  mov     r8, [r14]
0x18001cd24  xor     edx, edx
0x18001cd26  mov     rcx, r15; HWND
0x18001cd29  call    ?HrRaiseConnectionPropertiesInternal@@YAJPEAUHWND__@@IAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@@Z; HrRaiseConnectionPropertiesInternal(HWND__ *,uint,CPConFoldPidl<ConFoldPidl_v3> const &)
0x18001cd2e  jmp     short loc_18001CD50
0x18001cd30  call    cs:__imp_GetLastError
0x18001cd36  cmp     eax, esi
0x18001cd38  jnz     short loc_18001CD4B
0x18001cd3a  mov     rdx, [rsp+210h+var_1E0]
0x18001cd3f  xor     ecx, ecx
0x18001cd41  call    ?ActivateDialog@@YAXW4DIALOG_TYPE@@PEAUINetConnection@@@Z; ActivateDialog(DIALOG_TYPE,INetConnection *)
0x18001cd46  jmp     loc_18001CC05
0x18001cd4b  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001cd50  mov     ebx, eax
0x18001cd52  test    eax, eax
0x18001cd54  jns     loc_18001CC05
0x18001cd5a  cmp     ebx, 8000FFFFh
0x18001cd60  jz      loc_18001CBE2
0x18001cd66  cmp     ebx, 800402E4h
0x18001cd6c  jz      loc_18001CC05
0x18001cd72  cmp     ebx, 80070005h
0x18001cd78  jz      loc_18001CC85
0x18001cd7e  cmp     ebx, 8007000Eh
0x18001cd84  jz      short loc_18001CD9D
0x18001cd86  cmp     ebx, 800702E4h
0x18001cd8c  jz      loc_18001CC05
0x18001cd92  mov     r9d, 44Ch
0x18001cd98  jmp     loc_18001CBE8
0x18001cd9d  mov     r9d, 44Dh
0x18001cda3  jmp     loc_18001CBE8
```
