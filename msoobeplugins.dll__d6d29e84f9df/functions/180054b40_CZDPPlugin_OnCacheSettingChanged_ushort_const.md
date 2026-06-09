# CZDPPlugin::OnCacheSettingChanged(ushort const *)

- ea: `0x180054b40`
- end: `0x180054cb4`
- name: `?OnCacheSettingChanged@CZDPPlugin@@UEAAJPEBG@Z`
- size: `372`
- prototype: `int(CZDPPlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180054b40`
- `0x180054ecc`
- `0x180054fb0`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054b75`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054ba1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054bcd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054bf9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054b75`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054ba1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054bcd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054bf9`

## string_xrefs

- `0x180054c5b`: `ZDP Plugin: Detected background task completed (ZDP Status -> ZDP_Finished)`
- `0x180054c90`: `Launching ZDP background task in response to %s setting change`

## pseudocode

```c
__int64 __fastcall CZDPPlugin::OnCacheSettingChanged(CZDPPlugin *this, const unsigned __int16 *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  v9 = 0;
  if ( CompareStringW(0x400u, 0, a2, -1, L"NETWORKSTATUS", -1) == 2
    || CompareStringW(0x400u, 0, a2, -1, L"EULAACCEPT", -1) == 2
    || CompareStringW(0x400u, 0, a2, -1, L"RETAILDEMO", -1) == 2 )
  {
    if ( CZDPPlugin::_ShouldLaunchZDPBackgroundTaskForCurrentState((CZDPPlugin *)((char *)this - 40)) )
    {
      UnattendLogW(0, L"Launching ZDP background task in response to %s setting change", a2);
      return (unsigned int)CZDPPlugin::_LaunchZDPBackgroundTask((CZDPPlugin *)((char *)this - 40));
    }
  }
  else if ( CompareStringW(0x400u, 0, a2, -1, L"ZDPSTATUS", -1) == 2
         && (*(int (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this - 1) + 24LL))((char *)this - 8, &v9) >= 0 )
  {
    v5 = *((_QWORD *)this + 3);
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, v9);
      if ( v6 < 0 )
        UnattendLogW(2, L"Callback failed to process ZDP Status change [hr=0x%08X]", (unsigned int)v6);
    }
    if ( v9 == 4 )
    {
      UnattendLogW(0, L"ZDP Plugin: Detected background task completed (ZDP Status -> ZDP_Finished)");
      v7 = *((_QWORD *)this + 2);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180054b40  push    rbx
0x180054b42  push    rbp
0x180054b43  push    rsi
0x180054b44  push    rdi
0x180054b45  sub     rsp, 38h
0x180054b49  or      ebp, 0FFFFFFFFh
0x180054b4c  lea     rax, aNetworkstatus; "NETWORKSTATUS"
0x180054b53  mov     rdi, rdx
0x180054b56  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180054b5a  mov     rbx, rcx
0x180054b5d  mov     [rsp+58h+lpString2], rax; lpString2
0x180054b62  mov     r8, rdx; lpString1
0x180054b65  xor     esi, esi
0x180054b67  mov     r9d, ebp; cchCount1
0x180054b6a  mov     [rsp+58h+arg_10], esi
0x180054b6e  xor     edx, edx; dwCmpFlags
0x180054b70  mov     ecx, 400h; Locale
0x180054b75  call    cs:__imp_CompareStringW
0x180054b7b  cmp     eax, 2
0x180054b7e  jz      loc_180054C80
0x180054b84  lea     rax, aEulaaccept; "EULAACCEPT"
0x180054b8b  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180054b8f  mov     r9d, ebp; cchCount1
0x180054b92  mov     [rsp+58h+lpString2], rax; lpString2
0x180054b97  mov     r8, rdi; lpString1
0x180054b9a  xor     edx, edx; dwCmpFlags
0x180054b9c  mov     ecx, 400h; Locale
0x180054ba1  call    cs:__imp_CompareStringW
0x180054ba7  cmp     eax, 2
0x180054baa  jz      loc_180054C80
0x180054bb0  lea     rax, aRetaildemo_0; "RETAILDEMO"
0x180054bb7  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180054bbb  mov     r9d, ebp; cchCount1
0x180054bbe  mov     [rsp+58h+lpString2], rax; lpString2
0x180054bc3  mov     r8, rdi; lpString1
0x180054bc6  xor     edx, edx; dwCmpFlags
0x180054bc8  mov     ecx, 400h; Locale
0x180054bcd  call    cs:__imp_CompareStringW
0x180054bd3  cmp     eax, 2
0x180054bd6  jz      loc_180054C80
0x180054bdc  lea     rax, aZdpstatus; "ZDPSTATUS"
0x180054be3  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180054be7  mov     r9d, ebp; cchCount1
0x180054bea  mov     [rsp+58h+lpString2], rax; lpString2
0x180054bef  mov     r8, rdi; lpString1
0x180054bf2  xor     edx, edx; dwCmpFlags
0x180054bf4  mov     ecx, 400h; Locale
0x180054bf9  call    cs:__imp_CompareStringW
0x180054bff  cmp     eax, 2
0x180054c02  jnz     loc_180054CA9
0x180054c08  lea     rcx, [rbx-8]
0x180054c0c  mov     rax, [rcx]
0x180054c0f  lea     rdx, [rsp+58h+arg_10]
0x180054c14  mov     rax, [rax+18h]
0x180054c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c1d  test    eax, eax
0x180054c1f  js      loc_180054CA9
0x180054c25  mov     rcx, [rbx+18h]
0x180054c29  test    rcx, rcx
0x180054c2c  jz      short loc_180054C54
0x180054c2e  mov     rax, [rcx]
0x180054c31  mov     edx, [rsp+58h+arg_10]
0x180054c35  mov     rax, [rax+18h]
0x180054c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c3e  test    eax, eax
0x180054c40  jns     short loc_180054C54
0x180054c42  mov     r8d, eax
0x180054c45  lea     rdx, aCallbackFailed; "Callback failed to process ZDP Status c"...
0x180054c4c  lea     ecx, [rsi+2]
0x180054c4f  call    UnattendLogW
0x180054c54  cmp     [rsp+58h+arg_10], 4
0x180054c59  jnz     short loc_180054CA9
0x180054c5b  lea     rdx, aZdpPluginDetec; "ZDP Plugin: Detected background task co"...
0x180054c62  xor     ecx, ecx
0x180054c64  call    UnattendLogW
0x180054c69  mov     rcx, [rbx+10h]
0x180054c6d  test    rcx, rcx
0x180054c70  jz      short loc_180054CA9
0x180054c72  mov     rax, [rcx]
0x180054c75  mov     rax, [rax+28h]
0x180054c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c7e  jmp     short loc_180054CA9
0x180054c80  lea     rcx, [rbx-28h]; this
0x180054c84  call    ?_ShouldLaunchZDPBackgroundTaskForCurrentState@CZDPPlugin@@AEAA_NXZ; CZDPPlugin::_ShouldLaunchZDPBackgroundTaskForCurrentState(void)
0x180054c89  test    al, al
0x180054c8b  jz      short loc_180054CA9
0x180054c8d  mov     r8, rdi
0x180054c90  lea     rdx, aLaunchingZdpBa_0; "Launching ZDP background task in respon"...
0x180054c97  xor     ecx, ecx
0x180054c99  call    UnattendLogW
0x180054c9e  lea     rcx, [rbx-28h]; this
0x180054ca2  call    ?_LaunchZDPBackgroundTask@CZDPPlugin@@AEAAJXZ; CZDPPlugin::_LaunchZDPBackgroundTask(void)
0x180054ca7  mov     esi, eax
0x180054ca9  mov     eax, esi
0x180054cab  add     rsp, 38h
0x180054caf  pop     rdi
0x180054cb0  pop     rsi
0x180054cb1  pop     rbp
0x180054cb2  pop     rbx
0x180054cb3  retn
```
