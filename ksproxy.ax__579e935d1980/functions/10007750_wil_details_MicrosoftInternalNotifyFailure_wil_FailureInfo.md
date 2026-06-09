# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x10007750`
- end: `0x1000781d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YGXPAUFailureInfo@2@@Z`
- size: `205`
- prototype: `void __stdcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10007750`
- `0x1002d510`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100077c8`
- `KERNEL32!GetProcAddress` at `0x100077c8`
- `KERNEL32!GetModuleHandleW` at `0x100077b3`
- `KERNEL32!GetModuleHandleW` at `0x100077b3`

## string_xrefs

- `0x100077ae`: `kernelbase.dll`

## pseudocode

```c
void __stdcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  CD3DSurfaceAllocator *WilFailureNotifyWatchers; // edi
  HMODULE ModuleHandleW; // eax
  _DWORD v4[2]; // [esp+4h] [ebp-24h] BYREF
  char v5; // [esp+Ch] [ebp-1Ch]
  __int16 v6; // [esp+Eh] [ebp-1Ah]
  __int16 v7; // [esp+10h] [ebp-18h]
  int v8; // [esp+14h] [ebp-14h]
  int v9; // [esp+18h] [ebp-10h]
  int v10; // [esp+1Ch] [ebp-Ch]
  __int64 v11; // [esp+20h] [ebp-8h] BYREF

  WilFailureNotifyWatchers = `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v8 = 0;
  v4[0] = *((_DWORD *)this + 2);
  v4[1] = *((_DWORD *)this + 5);
  v5 = *(_BYTE *)this;
  v6 = wil::g_moduleFailureReportFlags;
  v7 = *((_WORD *)this + 20);
  v9 = *((_DWORD *)this + 9);
  v10 = *((_DWORD *)this + 19);
  v11 = 0;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    WilFailureNotifyWatchers = (CD3DSurfaceAllocator *)GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = WilFailureNotifyWatchers;
  if ( WilFailureNotifyWatchers )
LABEL_6:
    ((void (__thiscall *)(CD3DSurfaceAllocator *, _DWORD, _DWORD *, __int64 *))WilFailureNotifyWatchers)(
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
0x10007750  mov     edi, edi
0x10007752  push    ebp
0x10007753  mov     ebp, esp
0x10007755  sub     esp, 24h
0x10007758  push    esi
0x10007759  mov     esi, [ebp+this]
0x1000775c  xorps   xmm0, xmm0
0x1000775f  push    edi
0x10007760  mov     edi, ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA
0x10007766  mov     [ebp+var_14], 0
0x1000776d  mov     eax, [esi+8]
0x10007770  mov     [ebp+var_24], eax
0x10007773  mov     eax, [esi+14h]
0x10007776  mov     [ebp+var_20], eax
0x10007779  mov     al, [esi]
0x1000777b  mov     [ebp+var_1C], al
0x1000777e  mov     ax, ?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x10007784  mov     [ebp+var_1A], ax
0x10007788  mov     ax, [esi+28h]
0x1000778c  mov     [ebp+var_18], ax
0x10007790  mov     eax, [esi+24h]
0x10007793  mov     [ebp+var_10], eax
0x10007796  mov     eax, [esi+4Ch]
0x10007799  mov     [ebp+var_C], eax
0x1000779c  movlpd  [ebp+var_8], xmm0
0x100077a1  test    edi, edi
0x100077a3  jnz     short loc_100077DA
0x100077a5  mov     eax, ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x100077aa  test    eax, eax
0x100077ac  jnz     short loc_100077C2
0x100077ae  push    offset aKernelbaseDll; "kernelbase.dll"
0x100077b3  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x100077b9  mov     ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A, eax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x100077be  test    eax, eax
0x100077c0  jz      short loc_100077D0
0x100077c2  push    offset aWilfailurenoti; "WilFailureNotifyWatchers"
0x100077c7  push    eax; hModule
0x100077c8  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100077ce  mov     edi, eax
0x100077d0  mov     ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA, edi
0x100077d6  test    edi, edi
0x100077d8  jz      short loc_100077EE
0x100077da  lea     eax, [ebp+var_8]
0x100077dd  mov     ecx, edi; this
0x100077df  push    eax
0x100077e0  lea     eax, [ebp+var_24]
0x100077e3  push    eax
0x100077e4  push    0
0x100077e6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100077ec  call    edi ; ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA
0x100077ee  mov     eax, dword ptr [ebp+var_8]
0x100077f1  mov     [esi+10h], eax
0x100077f4  movzx   eax, byte ptr [ebp+var_8+4]
0x100077f8  sub     eax, 1
0x100077fb  jz      short loc_10007813
0x100077fd  sub     eax, 1
0x10007800  jz      short loc_1000780D
0x10007802  sub     eax, 1
0x10007805  jnz     short loc_10007817
0x10007807  or      dword ptr [esi+4], 4
0x1000780b  jmp     short loc_10007817
0x1000780d  or      dword ptr [esi+4], 2
0x10007811  jmp     short loc_10007817
0x10007813  or      dword ptr [esi+4], 1
0x10007817  pop     edi
0x10007818  pop     esi
0x10007819  leave
0x1000781a  retn    4
```
