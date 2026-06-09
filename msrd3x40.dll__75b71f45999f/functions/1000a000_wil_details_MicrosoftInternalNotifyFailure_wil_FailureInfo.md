# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1000a000`
- end: `0x1000a123`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YGXPAUFailureInfo@2@@Z`
- size: `291`
- prototype: `void __stdcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1000a000`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a09f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a09f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a08a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a08a`

## string_xrefs

- `0x1000a085`: `kernelbase.dll`

## pseudocode

```c
void __stdcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC WilFailureNotifyWatchers; // edi
  HMODULE ModuleHandleW; // eax
  unsigned int v4[2]; // [esp+Ch] [ebp-30h] BYREF
  char v5; // [esp+14h] [ebp-28h]
  __int16 v6; // [esp+16h] [ebp-26h]
  __int16 v7; // [esp+18h] [ebp-24h]
  int v8; // [esp+1Ch] [ebp-20h]
  int v9; // [esp+20h] [ebp-1Ch]
  int v10; // [esp+24h] [ebp-18h]
  __int64 v11; // [esp+28h] [ebp-14h] BYREF
  int v12; // [esp+38h] [ebp-4h]

  v8 = 0;
  v11 = 0;
  v4[0] = *((_DWORD *)this + 2);
  v4[1] = *((_DWORD *)this + 5);
  v5 = *(_BYTE *)this;
  v6 = wil::g_moduleFailureReportFlags;
  v7 = *((_WORD *)this + 20);
  v9 = *((_DWORD *)this + 9);
  v10 = *((_DWORD *)this + 19);
  v12 = 0;
  WilFailureNotifyWatchers = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    WilFailureNotifyWatchers = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (int)WilFailureNotifyWatchers;
  if ( WilFailureNotifyWatchers )
LABEL_6:
    ((void (__thiscall *)(FARPROC, _DWORD, unsigned int *, __int64 *))WilFailureNotifyWatchers)(
      WilFailureNotifyWatchers,
      0,
      v4,
      &v11);
  *((_DWORD *)this + 4) = v11;
  switch ( BYTE4(v11) )
  {
    case 1u:
      *((_DWORD *)this + 1) |= 1u;
      break;
    case 2u:
      *((_DWORD *)this + 1) |= 2u;
      break;
    case 3u:
      *((_DWORD *)this + 1) |= 4u;
      break;
  }
}

```

## disassembly

```asm
0x1000a000  mov     edi, edi
0x1000a002  push    ebp
0x1000a003  mov     ebp, esp
0x1000a005  push    0FFFFFFFFh
0x1000a007  push    offset ??1Database@@MAE@XZ_SEH
0x1000a00c  mov     eax, large fs:0
0x1000a012  push    eax
0x1000a013  sub     esp, 24h
0x1000a016  push    esi
0x1000a017  push    edi
0x1000a018  mov     eax, ___security_cookie
0x1000a01d  xor     eax, ebp
0x1000a01f  push    eax
0x1000a020  lea     eax, [ebp+var_C]
0x1000a023  mov     large fs:0, eax
0x1000a029  mov     esi, [ebp+this]
0x1000a02c  xorps   xmm0, xmm0
0x1000a02f  mov     [ebp+var_20], 0
0x1000a036  movlpd  [ebp+var_14], xmm0
0x1000a03b  mov     eax, [esi+8]
0x1000a03e  mov     [ebp+var_30], eax
0x1000a041  mov     eax, [esi+14h]
0x1000a044  mov     [ebp+var_2C], eax
0x1000a047  mov     al, [esi]
0x1000a049  mov     [ebp+var_28], al
0x1000a04c  movzx   eax, ?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1000a053  mov     [ebp+var_26], ax
0x1000a057  movzx   eax, word ptr [esi+28h]
0x1000a05b  mov     [ebp+var_24], ax
0x1000a05f  mov     eax, [esi+24h]
0x1000a062  mov     [ebp+var_1C], eax
0x1000a065  mov     eax, [esi+4Ch]
0x1000a068  mov     [ebp+var_18], eax
0x1000a06b  mov     [ebp+var_4], 0
0x1000a072  mov     edi, ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA
0x1000a078  test    edi, edi
0x1000a07a  jnz     short loc_1000A0B1
0x1000a07c  mov     eax, ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1000a081  test    eax, eax
0x1000a083  jnz     short loc_1000A099
0x1000a085  push    offset aKernelbaseDll; "kernelbase.dll"
0x1000a08a  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000a090  mov     ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A, eax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1000a095  test    eax, eax
0x1000a097  jz      short loc_1000A0A7
0x1000a099  push    offset aWilfailurenoti; "WilFailureNotifyWatchers"
0x1000a09e  push    eax; hModule
0x1000a09f  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000a0a5  mov     edi, eax
0x1000a0a7  mov     ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA, edi
0x1000a0ad  test    edi, edi
0x1000a0af  jz      short loc_1000A0C5
0x1000a0b1  lea     eax, [ebp+var_14]
0x1000a0b4  mov     ecx, edi
0x1000a0b6  push    eax
0x1000a0b7  lea     eax, [ebp+var_30]
0x1000a0ba  push    eax; unsigned int
0x1000a0bb  push    0; void *
0x1000a0bd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000a0c3  call    edi ; ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA
0x1000a0c5  mov     eax, dword ptr [ebp+var_14]
0x1000a0c8  mov     [esi+10h], eax
0x1000a0cb  movzx   eax, byte ptr [ebp+var_14+4]
0x1000a0cf  sub     eax, 1
0x1000a0d2  jz      short loc_1000A10C
0x1000a0d4  sub     eax, 1
0x1000a0d7  jz      short loc_1000A0F5
0x1000a0d9  sub     eax, 1
0x1000a0dc  jnz     short loc_1000A110
0x1000a0de  or      dword ptr [esi+4], 4
0x1000a0e2  mov     ecx, [ebp+var_C]
0x1000a0e5  mov     large fs:0, ecx
0x1000a0ec  pop     ecx
0x1000a0ed  pop     edi
0x1000a0ee  pop     esi
0x1000a0ef  mov     esp, ebp
0x1000a0f1  pop     ebp
0x1000a0f2  retn    4
0x1000a0f5  or      dword ptr [esi+4], 2
0x1000a0f9  mov     ecx, [ebp+var_C]
0x1000a0fc  mov     large fs:0, ecx
0x1000a103  pop     ecx
0x1000a104  pop     edi
0x1000a105  pop     esi
0x1000a106  mov     esp, ebp
0x1000a108  pop     ebp
0x1000a109  retn    4
0x1000a10c  or      dword ptr [esi+4], 1
0x1000a110  mov     ecx, [ebp+var_C]
0x1000a113  mov     large fs:0, ecx
0x1000a11a  pop     ecx
0x1000a11b  pop     edi
0x1000a11c  pop     esi
0x1000a11d  mov     esp, ebp
0x1000a11f  pop     ebp
0x1000a120  retn    4
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f660  nop
0x1005f661  nop
0x1005f662  mov     edx, [esp-4+arg_4]
0x1005f666  lea     eax, [edx+0Ch]
0x1005f669  mov     ecx, [edx-30h]
0x1005f66c  xor     ecx, eax; StackCookie
0x1005f66e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f673  mov     eax, offset stru_10062AD4
0x1005f678  jmp     ___CxxFrameHandler3
```
