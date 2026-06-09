# ProcessSaveGlobalConfigInfo

- ea: `0x18003cac0`
- end: `0x18003ccdf`
- name: `ProcessSaveGlobalConfigInfo`
- size: `543`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034cd0`
- `0x180034e88`
- `0x180034f44`
- `0x1800350e0`
- `0x1800351bc`
- `0x18003bfb0`

## callees

- `0x18000ac60`
- `0x18001d134`
- `0x18001e4c0`
- `0x18003cac0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18003cc5c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003cc6b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003cc5c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003cc6b`
- `ntdll!RtlReleaseResource` at `0x18003cc25`
- `ntdll!RtlReleaseResource` at `0x18003cc32`
- `ntdll!RtlReleaseResource` at `0x18003cc25`
- `ntdll!RtlReleaseResource` at `0x18003cc32`
- `KERNEL32!HeapAlloc` at `0x18003cbb3`
- `KERNEL32!HeapAlloc` at `0x18003cbb3`

## string_xrefs

- `0x18003cb2f`: `ProcessSaveGlobalConfigInfo`
- `0x18003cb94`: `ProcessSaveGlobalConfigInfo: Error %d getting size of global info`
- `0x18003cbd3`: `ProcessSaveGlobalConfigInfo: Error allocating %d bytes`
- `0x18003cc0d`: `ProcessSaveGlobalConfigInfo: Error %d getting global configuration`
- `0x18003cc80`: `ProcessSaveGlobalConfigInfo: Error %d saving global information`

## pseudocode

```c
__int64 __fastcall ProcessSaveGlobalConfigInfo(unsigned int a1)
{
  unsigned int SizeOfGlobalInfo; // ebx
  const wchar_t *v3; // rdx
  LPVOID v4; // rax
  LPVOID v5; // rdi
  unsigned int GlobalConfiguration; // eax
  struct _GUID v8; // [rsp+28h] [rbp-D8h] BYREF
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v9 = 0;
  v8 = GUID_NULL;
  memset_0(v10, 0, sizeof(v10));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"Entered: %ws", L"ProcessSaveGlobalConfigInfo");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v9);
  }
  SizeOfGlobalInfo = GetSizeOfGlobalInfo(&v8);
  if ( SizeOfGlobalInfo )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return SizeOfGlobalInfo;
    LOWORD(v9) = 0;
    v3 = L"ProcessSaveGlobalConfigInfo: Error %d getting size of global info";
  }
  else
  {
    SizeOfGlobalInfo = 8;
    v4 = HeapAlloc(IPRouterHeap, 8u, 0);
    v5 = v4;
    if ( !v4 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return SizeOfGlobalInfo;
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"ProcessSaveGlobalConfigInfo: Error allocating %d bytes", 0);
      goto LABEL_17;
    }
    GlobalConfiguration = GetGlobalConfiguration(v4, 0, &v8, a1);
    SizeOfGlobalInfo = GlobalConfiguration;
    if ( GlobalConfiguration )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return SizeOfGlobalInfo;
      LOWORD(v9) = 0;
      FormatRRASErrorString(
        &v9,
        L"ProcessSaveGlobalConfigInfo: Error %d getting global configuration",
        GlobalConfiguration);
      goto LABEL_17;
    }
    RtlReleaseResource(&stru_18008C4A0);
    RtlReleaseResource(&Resource);
    SizeOfGlobalInfo = ((__int64 (__fastcall *)(__int64, LPVOID, _QWORD))SaveGlobalInfo)(33, v5, 0);
    RtlAcquireResourceExclusive(&Resource, 1u);
    RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
    if ( !SizeOfGlobalInfo || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return SizeOfGlobalInfo;
    v3 = L"ProcessSaveGlobalConfigInfo: Error %d saving global information";
    LOWORD(v9) = 0;
  }
  FormatRRASErrorString(&v9, v3, SizeOfGlobalInfo);
LABEL_17:
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v9);
  return SizeOfGlobalInfo;
}

```

## disassembly

```asm
0x18003cac0  mov     [rsp-8+arg_8], rbx
0x18003cac5  mov     [rsp-8+arg_10], rsi
0x18003caca  push    rbp
0x18003cacb  push    rdi
0x18003cacc  push    r15
0x18003cace  lea     rbp, [rsp-750h]
0x18003cad6  sub     rsp, 850h
0x18003cadd  mov     rax, cs:__security_cookie
0x18003cae4  xor     rax, rsp
0x18003cae7  mov     [rbp+760h+var_20], rax
0x18003caee  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003caf5  mov     esi, ecx
0x18003caf7  mov     dword ptr [rsp+860h+dwBytes], 0
0x18003caff  xor     eax, eax
0x18003cb01  lea     rcx, [rsp+860h+var_81C]; void *
0x18003cb06  xor     edx, edx; Val
0x18003cb08  mov     [rsp+860h+var_820], eax
0x18003cb0c  mov     r8d, 7FCh; Size
0x18003cb12  movdqu  xmmword ptr [rsp+860h+var_838.Data1], xmm0
0x18003cb18  call    memset_0
0x18003cb1d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003cb24  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003cb2b  jge     short loc_18003CB69
0x18003cb2d  xor     eax, eax
0x18003cb2f  lea     r8, aProcesssaveglo_2; "ProcessSaveGlobalConfigInfo"
0x18003cb36  lea     rdx, aEnteredWs; "Entered: %ws"
0x18003cb3d  mov     word ptr [rsp+860h+var_820], ax
0x18003cb42  lea     rcx, [rsp+860h+var_820]
0x18003cb47  call    FormatRRASErrorString
0x18003cb4c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003cb53  jge     short loc_18003CB69
0x18003cb55  lea     r8, [rsp+860h+var_820]
0x18003cb5a  mov     rcx, r15
0x18003cb5d  lea     rdx, RasRtrmgrTraceInfo
0x18003cb64  call    McTemplateU0z_EventWriteTransfer
0x18003cb69  lea     r8, [rsp+860h+dwBytes]
0x18003cb6e  mov     edx, esi
0x18003cb70  lea     rcx, [rsp+860h+var_838]; struct _GUID *
0x18003cb75  call    GetSizeOfGlobalInfo
0x18003cb7a  mov     ebx, eax
0x18003cb7c  test    eax, eax
0x18003cb7e  jz      short loc_18003CBA0
0x18003cb80  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cb87  jz      loc_18003CCB6
0x18003cb8d  xor     edx, edx
0x18003cb8f  mov     word ptr [rsp+860h+var_820], dx
0x18003cb94  lea     rdx, aProcesssaveglo_1; "ProcessSaveGlobalConfigInfo: Error %d g"...
0x18003cb9b  jmp     loc_18003CC8C
0x18003cba0  mov     r8d, dword ptr [rsp+860h+dwBytes]; dwBytes
0x18003cba5  mov     ebx, 8
0x18003cbaa  mov     rcx, cs:IPRouterHeap; hHeap
0x18003cbb1  mov     edx, ebx; dwFlags
0x18003cbb3  call    cs:__imp_HeapAlloc
0x18003cbb9  mov     rdi, rax
0x18003cbbc  test    rax, rax
0x18003cbbf  jnz     short loc_18003CBE4
0x18003cbc1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cbc8  jz      loc_18003CCB6
0x18003cbce  mov     r8d, dword ptr [rsp+860h+dwBytes]
0x18003cbd3  lea     rdx, aProcesssaveglo_3; "ProcessSaveGlobalConfigInfo: Error allo"...
0x18003cbda  mov     word ptr [rsp+860h+var_820], ax
0x18003cbdf  jmp     loc_18003CC8F
0x18003cbe4  mov     edx, dword ptr [rsp+860h+dwBytes]
0x18003cbe8  lea     r8, [rsp+860h+var_838]
0x18003cbed  mov     r9d, esi
0x18003cbf0  mov     rcx, rdi
0x18003cbf3  call    GetGlobalConfiguration
0x18003cbf8  mov     ebx, eax
0x18003cbfa  test    eax, eax
0x18003cbfc  jz      short loc_18003CC1E
0x18003cbfe  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cc05  jz      loc_18003CCB6
0x18003cc0b  xor     ecx, ecx
0x18003cc0d  lea     rdx, aProcesssaveglo; "ProcessSaveGlobalConfigInfo: Error %d g"...
0x18003cc14  mov     word ptr [rsp+860h+var_820], cx
0x18003cc19  mov     r8d, eax
0x18003cc1c  jmp     short loc_18003CC8F
0x18003cc1e  lea     rcx, stru_18008C4A0; Resource
0x18003cc25  call    cs:__imp_RtlReleaseResource
0x18003cc2b  lea     rcx, Resource; Resource
0x18003cc32  call    cs:__imp_RtlReleaseResource
0x18003cc38  mov     r8d, dword ptr [rsp+860h+dwBytes]
0x18003cc3d  mov     rdx, rdi
0x18003cc40  mov     rax, cs:SaveGlobalInfo
0x18003cc47  mov     ecx, 21h ; '!'
0x18003cc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc51  mov     dl, 1; Wait
0x18003cc53  lea     rcx, Resource; Resource
0x18003cc5a  mov     ebx, eax
0x18003cc5c  call    cs:__imp_RtlAcquireResourceExclusive
0x18003cc62  mov     dl, 1; Wait
0x18003cc64  lea     rcx, stru_18008C4A0; Resource
0x18003cc6b  call    cs:__imp_RtlAcquireResourceExclusive
0x18003cc71  test    ebx, ebx
0x18003cc73  jz      short loc_18003CCB6
0x18003cc75  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cc7c  jz      short loc_18003CCB6
0x18003cc7e  xor     eax, eax
0x18003cc80  lea     rdx, aProcesssaveglo_0; "ProcessSaveGlobalConfigInfo: Error %d s"...
0x18003cc87  mov     word ptr [rsp+860h+var_820], ax
0x18003cc8c  mov     r8d, ebx
0x18003cc8f  lea     rcx, [rsp+860h+var_820]
0x18003cc94  call    FormatRRASErrorString
0x18003cc99  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003cca0  jz      short loc_18003CCB6
0x18003cca2  lea     r8, [rsp+860h+var_820]
0x18003cca7  mov     rcx, r15
0x18003ccaa  lea     rdx, RasRtrMgrTraceError
0x18003ccb1  call    McTemplateU0z_EventWriteTransfer
0x18003ccb6  mov     eax, ebx
0x18003ccb8  mov     rcx, [rbp+760h+var_20]
0x18003ccbf  xor     rcx, rsp; StackCookie
0x18003ccc2  call    __security_check_cookie
0x18003ccc7  lea     r11, [rsp+860h+var_10]
0x18003cccf  mov     rbx, [r11+28h]
0x18003ccd3  mov     rsi, [r11+30h]
0x18003ccd7  mov     rsp, r11
0x18003ccda  pop     r15
0x18003ccdc  pop     rdi
0x18003ccdd  pop     rbp
0x18003ccde  retn
```
