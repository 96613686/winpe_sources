# SaveTrackingOptions

- ea: `0x1800157a4`
- end: `0x1800159b8`
- name: `SaveTrackingOptions`
- size: `532`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012a40`
- `0x1800130d4`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000d94c`
- `0x18000da1c`
- `0x1800157a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015950`
- `KERNEL32!GetLastError` at `0x180015986`
- `KERNEL32!GetLastError` at `0x180015990`
- `KERNEL32!GetLastError` at `0x180015950`
- `KERNEL32!GetLastError` at `0x180015986`
- `KERNEL32!GetLastError` at `0x180015990`
- `USER32!PostMessageW` at `0x180015946`
- `USER32!PostMessageW` at `0x180015946`
- `USER32!FindWindowW` at `0x18001592d`
- `USER32!FindWindowW` at `0x18001592d`
- `ADVAPI32!RegCloseKey` at `0x18001591e`
- `ADVAPI32!RegCloseKey` at `0x1800159a0`
- `ADVAPI32!RegCloseKey` at `0x18001591e`
- `ADVAPI32!RegCloseKey` at `0x1800159a0`

## string_xrefs

- `0x18001584b`: `NotifyIncomingCompletion`
- `0x180015866`: `NotifyOutgoingCompletion`

## pseudocode

```c
__int64 __fastcall SaveTrackingOptions(int *a1, __int64 a2)
{
  void *v3; // rcx
  HKEY v5; // rax
  HKEY v6; // rbx
  HWND WindowW; // rax
  DWORD LastError; // eax
  DWORD v9; // edi

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids);
  }
  if ( !a1 )
    return 87;
  v5 = OpenRegistryKey((__int64)v3, a2, 1, 2u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids, LastError);
      return GetLastError();
    }
LABEL_25:
    v9 = GetLastError();
    if ( v6 )
      RegCloseKey(v6);
    return v9;
  }
  if ( !(unsigned int)SetRegistryDword(v5, L"DeviceToMonitor", *a1)
    || !(unsigned int)SetRegistryDword(v6, L"NotifyProgress", a1[1])
    || !(unsigned int)SetRegistryDword(v6, L"NotifyIncomingCompletion", a1[2])
    || !(unsigned int)SetRegistryDword(v6, L"NotifyOutgoingCompletion", a1[3])
    || !(unsigned int)SetRegistryDword(v6, L"MonitorOnSend", a1[4])
    || !(unsigned int)SetRegistryDword(v6, L"MonitorOnReceive", a1[5])
    || !(unsigned int)SetRegistryDword(v6, L"SoundOnRing", a1[6])
    || !(unsigned int)SetRegistryDword(v6, L"SoundOnReceive", a1[7])
    || !(unsigned int)SetRegistryDword(v6, L"SoundOnSent", a1[8])
    || !(unsigned int)SetRegistryDword(v6, L"SoundOnError", a1[9]) )
  {
    goto LABEL_25;
  }
  RegCloseKey(v6);
  WindowW = FindWindowW(L"FaxMonWinClass{3FD224BA-8556-47fb-B260-3E451BAE2793}", 0);
  if ( WindowW )
    PostMessageW(WindowW, 0x4C9u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800157a4  mov     [rsp+arg_0], rbx
0x1800157a9  mov     [rsp+arg_8], rbp
0x1800157ae  push    rdi
0x1800157af  sub     rsp, 20h
0x1800157b3  mov     rdi, rcx
0x1800157b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157bd  lea     rbp, WPP_GLOBAL_Control
0x1800157c4  cmp     rcx, rbp
0x1800157c7  jz      short loc_1800157EA
0x1800157c9  test    byte ptr [rcx+1Ch], 2
0x1800157cd  jz      short loc_1800157EA
0x1800157cf  cmp     byte ptr [rcx+19h], 5
0x1800157d3  jb      short loc_1800157EA
0x1800157d5  mov     rcx, [rcx+10h]
0x1800157d9  lea     r8, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids
0x1800157e0  mov     edx, 19h
0x1800157e5  call    WPP_SF_
0x1800157ea  test    rdi, rdi
0x1800157ed  jnz     short loc_1800157F7
0x1800157ef  lea     eax, [rdi+57h]
0x1800157f2  jmp     loc_1800159A8
0x1800157f7  mov     r9d, 2
0x1800157fd  lea     r8d, [r9-1]
0x180015801  call    OpenRegistryKey
0x180015806  mov     rbx, rax
0x180015809  test    rax, rax
0x18001580c  jz      loc_180015950
0x180015812  mov     r8d, [rdi]
0x180015815  lea     rdx, aDevicetomonito; "DeviceToMonitor"
0x18001581c  mov     rcx, rax
0x18001581f  call    SetRegistryDword
0x180015824  test    eax, eax
0x180015826  jz      loc_180015990
0x18001582c  mov     r8d, [rdi+4]
0x180015830  lea     rdx, aNotifyprogress; "NotifyProgress"
0x180015837  mov     rcx, rbx
0x18001583a  call    SetRegistryDword
0x18001583f  test    eax, eax
0x180015841  jz      loc_180015990
0x180015847  mov     r8d, [rdi+8]
0x18001584b  lea     rdx, aNotifyincoming; "NotifyIncomingCompletion"
0x180015852  mov     rcx, rbx
0x180015855  call    SetRegistryDword
0x18001585a  test    eax, eax
0x18001585c  jz      loc_180015990
0x180015862  mov     r8d, [rdi+0Ch]
0x180015866  lea     rdx, aNotifyoutgoing; "NotifyOutgoingCompletion"
0x18001586d  mov     rcx, rbx
0x180015870  call    SetRegistryDword
0x180015875  test    eax, eax
0x180015877  jz      loc_180015990
0x18001587d  mov     r8d, [rdi+10h]
0x180015881  lea     rdx, aMonitoronsend; "MonitorOnSend"
0x180015888  mov     rcx, rbx
0x18001588b  call    SetRegistryDword
0x180015890  test    eax, eax
0x180015892  jz      loc_180015990
0x180015898  mov     r8d, [rdi+14h]
0x18001589c  lea     rdx, aMonitoronrecei; "MonitorOnReceive"
0x1800158a3  mov     rcx, rbx
0x1800158a6  call    SetRegistryDword
0x1800158ab  test    eax, eax
0x1800158ad  jz      loc_180015990
0x1800158b3  mov     r8d, [rdi+18h]
0x1800158b7  lea     rdx, aSoundonring; "SoundOnRing"
0x1800158be  mov     rcx, rbx
0x1800158c1  call    SetRegistryDword
0x1800158c6  test    eax, eax
0x1800158c8  jz      loc_180015990
0x1800158ce  mov     r8d, [rdi+1Ch]
0x1800158d2  lea     rdx, aSoundonreceive; "SoundOnReceive"
0x1800158d9  mov     rcx, rbx
0x1800158dc  call    SetRegistryDword
0x1800158e1  test    eax, eax
0x1800158e3  jz      loc_180015990
0x1800158e9  mov     r8d, [rdi+20h]
0x1800158ed  lea     rdx, aSoundonsent; "SoundOnSent"
0x1800158f4  mov     rcx, rbx
0x1800158f7  call    SetRegistryDword
0x1800158fc  test    eax, eax
0x1800158fe  jz      loc_180015990
0x180015904  mov     r8d, [rdi+24h]
0x180015908  lea     rdx, aSoundonerror; "SoundOnError"
0x18001590f  mov     rcx, rbx
0x180015912  call    SetRegistryDword
0x180015917  test    eax, eax
0x180015919  jz      short loc_180015990
0x18001591b  mov     rcx, rbx; hKey
0x18001591e  call    cs:__imp_RegCloseKey
0x180015924  xor     edx, edx; lpWindowName
0x180015926  lea     rcx, ClassName; "FaxMonWinClass{3FD224BA-8556-47fb-B260-"...
0x18001592d  call    cs:__imp_FindWindowW
0x180015933  test    rax, rax
0x180015936  jz      short loc_18001594C
0x180015938  xor     r9d, r9d; lParam
0x18001593b  xor     r8d, r8d; wParam
0x18001593e  mov     edx, 4C9h; Msg
0x180015943  mov     rcx, rax; hWnd
0x180015946  call    cs:__imp_PostMessageW
0x18001594c  xor     eax, eax
0x18001594e  jmp     short loc_1800159A8
0x180015950  call    cs:__imp_GetLastError
0x180015956  mov     rcx, cs:WPP_GLOBAL_Control
0x18001595d  cmp     rcx, rbp
0x180015960  jz      short loc_180015990
0x180015962  test    byte ptr [rcx+1Ch], 2
0x180015966  jz      short loc_180015990
0x180015968  cmp     byte ptr [rcx+19h], 2
0x18001596c  jb      short loc_180015990
0x18001596e  mov     rcx, [rcx+10h]
0x180015972  lea     r8, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids
0x180015979  mov     edx, 1Ah
0x18001597e  mov     r9d, eax
0x180015981  call    WPP_SF_d
0x180015986  call    cs:__imp_GetLastError
0x18001598c  mov     edi, eax
0x18001598e  jmp     short loc_1800159A6
0x180015990  call    cs:__imp_GetLastError
0x180015996  mov     edi, eax
0x180015998  test    rbx, rbx
0x18001599b  jz      short loc_1800159A6
0x18001599d  mov     rcx, rbx; hKey
0x1800159a0  call    cs:__imp_RegCloseKey
0x1800159a6  mov     eax, edi
0x1800159a8  mov     rbx, [rsp+28h+arg_0]
0x1800159ad  mov     rbp, [rsp+28h+arg_8]
0x1800159b2  add     rsp, 20h
0x1800159b6  pop     rdi
0x1800159b7  retn
```
