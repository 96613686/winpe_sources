# ConsolePropertySheetHandler::_InitializeGlobalStateInfo(wchar_t const *)

- ea: `0x180013ce0`
- end: `0x180013df8`
- name: `?_InitializeGlobalStateInfo@ConsolePropertySheetHandler@@AEAAJPEB_W@Z`
- size: `280`
- prototype: `int(ConsolePropertySheetHandler *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800137e0`

## callees

- `0x180005e60`
- `0x180007a68`
- `0x1800103b4`
- `0x1800114d4`
- `0x180011c68`
- `0x180013ce0`
- `0x1800178fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dde`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013d65`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013d65`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x180013d1e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x180013d1e`

## pseudocode

```c
__int64 __fastcall ConsolePropertySheetHandler::_InitializeGlobalStateInfo(
        ConsolePropertySheetHandler *this,
        const wchar_t *a2)
{
  BOOL BoolUSValueW; // eax
  struct _CONSOLE_STATE_INFO *v4; // rcx
  __int64 v5; // r11
  HRESULT v6; // ebx
  int v7; // eax
  wchar_t *v8; // r8
  unsigned __int64 v9; // r9
  struct _CONSOLE_STATE_INFO *v10; // rcx
  int LinkValues; // eax
  wchar_t *v13; // [rsp+20h] [rbp-48h]
  unsigned __int64 v14; // [rsp+28h] [rbp-40h]
  wchar_t *v15; // [rsp+30h] [rbp-38h]
  unsigned __int64 v16; // [rsp+38h] [rbp-30h]
  int *v17; // [rsp+40h] [rbp-28h]
  int *v18; // [rsp+48h] [rbp-20h]
  unsigned __int16 *v19; // [rsp+50h] [rbp-18h]
  ConsolePropertySheetHandler *v20; // [rsp+70h] [rbp+8h] BYREF
  LPWSTR ppwsz; // [rsp+80h] [rbp+18h] BYREF

  v20 = this;
  gpStateInfo = (struct _CONSOLE_STATE_INFO *)qword_1800237F0;
  g_fHostedInFileProperties = 1;
  BoolUSValueW = SHRegGetBoolUSValueW(L"Console", L"ForceV2", 0, 1);
  v4 = gpStateInfo;
  *((_DWORD *)gpStateInfo + 53) = BoolUSValueW;
  InitRegistryValues(v4);
  *(_DWORD *)(v5 + 96) |= 0x80u;
  GetRegistryValues((struct _CONSOLE_STATE_INFO *)v5);
  ppwsz = 0;
  v6 = SHStrDupW(a2, &ppwsz);
  if ( v6 >= 0 )
  {
    v7 = StringCchCopyW(ppwsz, 0x104u, a2);
    v10 = (struct _CONSOLE_STATE_INFO *)ppwsz;
    v6 = v7;
    if ( v7 < 0 )
    {
      CoTaskMemFree(ppwsz);
    }
    else
    {
      LODWORD(v20) = 0;
      *((_QWORD *)gpStateInfo + 25) = ppwsz;
      ppwsz = 0;
      LinkValues = ShortcutSerialization::s_GetLinkValues(
                     v10,
                     (int *const)&v20,
                     v8,
                     v9,
                     v13,
                     v14,
                     v15,
                     v16,
                     v17,
                     v18,
                     v19);
      v6 = LinkValues | 0x10000000;
      if ( LinkValues >= 0 )
      {
        InitializeFonts();
        return (unsigned int)FindFontAndUpdateState();
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013ce0  mov     [rsp+arg_8], rbx
0x180013ce5  mov     [rsp+arg_0], rcx
0x180013cea  push    rdi
0x180013ceb  sub     rsp, 60h
0x180013cef  mov     rdi, rdx
0x180013cf2  lea     rax, qword_1800237F0
0x180013cf9  mov     r9d, 1; fDefault
0x180013cff  mov     cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA, rax; _CONSOLE_STATE_INFO * gpStateInfo
0x180013d06  lea     rdx, pszValue; "ForceV2"
0x180013d0d  mov     cs:?g_fHostedInFileProperties@@3HA, r9d; int g_fHostedInFileProperties
0x180013d14  xor     r8d, r8d; fIgnoreHKCU
0x180013d17  lea     rcx, aConsole; "Console"
0x180013d1e  call    cs:__imp_SHRegGetBoolUSValueW
0x180013d25  nop     dword ptr [rax+rax+00h]
0x180013d2a  mov     r11, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180013d31  mov     rcx, r11; struct _CONSOLE_STATE_INFO *
0x180013d34  mov     [r11+0D4h], eax
0x180013d3b  call    ?InitRegistryValues@@YAXPEAU_CONSOLE_STATE_INFO@@@Z; InitRegistryValues(_CONSOLE_STATE_INFO *)
0x180013d40  bts     dword ptr [r11+60h], 7
0x180013d46  mov     rcx, r11; struct _CONSOLE_STATE_INFO *
0x180013d49  call    ?GetRegistryValues@@YAKPEAU_CONSOLE_STATE_INFO@@@Z; GetRegistryValues(_CONSOLE_STATE_INFO *)
0x180013d4e  lea     rdx, [rsp+68h+ppwsz]; ppwsz
0x180013d56  mov     [rsp+68h+ppwsz], 0
0x180013d62  mov     rcx, rdi; psz
0x180013d65  call    cs:__imp_SHStrDupW
0x180013d6c  nop     dword ptr [rax+rax+00h]
0x180013d71  mov     ebx, eax
0x180013d73  test    eax, eax
0x180013d75  js      short loc_180013DEA
0x180013d77  mov     rcx, [rsp+68h+ppwsz]; wchar_t *
0x180013d7f  mov     r8, rdi; wchar_t *
0x180013d82  mov     edx, 104h; unsigned __int64
0x180013d87  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180013d8c  mov     rcx, [rsp+68h+ppwsz]; struct _CONSOLE_STATE_INFO *
0x180013d94  mov     ebx, eax
0x180013d96  test    eax, eax
0x180013d98  js      short loc_180013DDE
0x180013d9a  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180013da1  lea     rdx, [rsp+68h+arg_0]; int *
0x180013da6  mov     dword ptr [rsp+68h+arg_0], 0
0x180013dae  mov     [rax+0C8h], rcx
0x180013db5  mov     [rsp+68h+ppwsz], 0
0x180013dc1  call    ?s_GetLinkValues@ShortcutSerialization@@SAJPEAU_CONSOLE_STATE_INFO@@QEAHPEA_W_K232311QEAG@Z; ShortcutSerialization::s_GetLinkValues(_CONSOLE_STATE_INFO *,int * const,wchar_t *,unsigned __int64,wchar_t *,unsigned __int64,wchar_t *,unsigned __int64,int * const,int * const,ushort * const)
0x180013dc6  mov     ebx, eax
0x180013dc8  or      ebx, 10000000h
0x180013dce  jl      short loc_180013DEA
0x180013dd0  call    ?InitializeFonts@@YAXXZ; InitializeFonts(void)
0x180013dd5  call    ?FindFontAndUpdateState@@YAJXZ; FindFontAndUpdateState(void)
0x180013dda  mov     ebx, eax
0x180013ddc  jmp     short loc_180013DEA
0x180013dde  call    cs:__imp_CoTaskMemFree
0x180013de5  nop     dword ptr [rax+rax+00h]
0x180013dea  mov     eax, ebx
0x180013dec  mov     rbx, [rsp+68h+arg_8]
0x180013df1  add     rsp, 60h
0x180013df5  pop     rdi
0x180013df6  retn
```
