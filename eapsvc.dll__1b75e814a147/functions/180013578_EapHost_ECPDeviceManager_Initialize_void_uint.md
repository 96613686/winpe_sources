# EapHost::ECPDeviceManager::Initialize(void *,uint)

- ea: `0x180013578`
- end: `0x180013749`
- name: `?Initialize@ECPDeviceManager@EapHost@@QEAAXPEAXI@Z`
- size: `465`
- prototype: `void __fastcall(LPVOID *ppv, void *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f2c8`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x180013578`
- `0x180013aac`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800135ed`
- `ntdll!EtwEventEnabled` at `0x1800136c1`
- `ntdll!EtwEventEnabled` at `0x1800135ed`
- `ntdll!EtwEventEnabled` at `0x1800136c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800135c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800135c3`

## string_xrefs

- `0x1800136ce`: `Could not create IUMBusDriver while initializing ECPDeviceManager: 0x%x`

## pseudocode

```c
void __fastcall EapHost::ECPDeviceManager::Initialize(LPVOID *ppv, void *a2, int a3)
{
  unsigned int Instance; // ebx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  _BYTE v9[16]; // [rsp+30h] [rbp-838h] BYREF
  char *v10; // [rsp+40h] [rbp-828h]
  int v11; // [rsp+48h] [rbp-820h]
  int v12; // [rsp+4Ch] [rbp-81Ch]
  char v13[2048]; // [rsp+50h] [rbp-818h] BYREF

  ppv[1] = a2;
  *((_DWORD *)ppv + 24) = a3;
  Instance = CoCreateInstance(
               &GUID_9197e04d_2b9f_4849_8bf7_75294eb5c043,
               0,
               0x17u,
               &GUID_712f2e95_9b00_4c34_b049_bd3c9c1402cc,
               ppv);
  if ( Instance )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v13,
                0x800u,
                "Could not create IUMBusDriver while initializing ECPDeviceManager: 0x%x",
                Instance) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v13);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, Instance);
    SystemError::Throw<long>((__int64)&byte_180018CBC, Instance);
  }
  EapHost::FDNotification::Initialize((EapHost::FDNotification *)(ppv + 2), a2);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v13, 0x800u, "ECPDeviceManager successfully initialized") >= 0
    && Microsoft_Windows_EapHostEnableBits < (char)Instance )
  {
    v8 = -1;
    do
      ++v8;
    while ( v13[v8] );
    v12 = 0;
    v11 = v8 + 1;
    v10 = v13;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v6,
      v7,
      (__int64)v9);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
}

```

## disassembly

```asm
0x180013578  mov     [rsp+arg_8], rbx
0x18001357d  mov     [rsp+arg_10], rsi
0x180013582  push    rdi
0x180013583  sub     rsp, 860h
0x18001358a  mov     rax, cs:__security_cookie
0x180013591  xor     rax, rsp
0x180013594  mov     [rsp+868h+var_18], rax
0x18001359c  mov     [rcx+8], rdx
0x1800135a0  lea     r9, _GUID_712f2e95_9b00_4c34_b049_bd3c9c1402cc; riid
0x1800135a7  mov     [rcx+60h], r8d
0x1800135ab  mov     rsi, rdx
0x1800135ae  xor     edx, edx; pUnkOuter
0x1800135b0  mov     [rsp+868h+ppv], rcx; ppv
0x1800135b5  mov     rdi, rcx
0x1800135b8  lea     rcx, _GUID_9197e04d_2b9f_4849_8bf7_75294eb5c043; rclsid
0x1800135bf  lea     r8d, [rdx+17h]; dwClsContext
0x1800135c3  call    cs:__imp_CoCreateInstance
0x1800135c9  mov     ebx, eax
0x1800135cb  test    eax, eax
0x1800135cd  jnz     loc_1800136B3
0x1800135d3  lea     rcx, [rdi+10h]; this
0x1800135d7  mov     rdx, rsi; void *
0x1800135da  call    ?Initialize@FDNotification@EapHost@@QEAAXPEAX@Z; EapHost::FDNotification::Initialize(void *)
0x1800135df  mov     rcx, cs:eaphost_Context
0x1800135e6  lea     rdx, DebugInfoEvent
0x1800135ed  call    cs:__imp_EtwEventEnabled
0x1800135f3  test    al, al
0x1800135f5  jz      short loc_180013660
0x1800135f7  lea     r8, aEcpdevicemanag; "ECPDeviceManager successfully initializ"...
0x1800135fe  mov     edx, 800h; unsigned __int64
0x180013603  lea     rcx, [rsp+868h+var_818]; char *
0x180013608  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001360d  test    eax, eax
0x18001360f  js      short loc_180013660
0x180013611  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180013617  jge     short loc_180013660
0x180013619  lea     rcx, [rsp+868h+var_818]
0x18001361e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013622  inc     rax
0x180013625  cmp     byte ptr [rcx+rax], 0
0x180013629  jnz     short loc_180013622
0x18001362b  inc     eax
0x18001362d  mov     [rsp+868h+var_81C], 0
0x180013635  lea     rcx, [rsp+868h+var_818]
0x18001363a  mov     [rsp+868h+var_820], eax
0x18001363e  lea     rax, [rsp+868h+var_838]
0x180013643  mov     [rsp+868h+var_828], rcx
0x180013648  lea     rdx, DebugInfoEvent
0x18001364f  mov     [rsp+868h+ppv], rax
0x180013654  lea     rcx, eaphost_Context
0x18001365b  call    McGenEventWrite_EtwEventWriteTransfer
0x180013660  mov     rcx, cs:WPP_GLOBAL_Control
0x180013667  lea     rax, WPP_GLOBAL_Control
0x18001366e  cmp     rcx, rax
0x180013671  jz      short loc_18001368E
0x180013673  test    byte ptr [rcx+1Ch], 4
0x180013677  jz      short loc_18001368E
0x180013679  mov     rcx, [rcx+10h]
0x18001367d  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180013684  mov     edx, 0Bh
0x180013689  call    WPP_SF_
0x18001368e  mov     rcx, [rsp+868h+var_18]
0x180013696  xor     rcx, rsp; StackCookie
0x180013699  call    __security_check_cookie
0x18001369e  lea     r11, [rsp+868h+var_8]
0x1800136a6  mov     rbx, [r11+18h]
0x1800136aa  mov     rsi, [r11+20h]
0x1800136ae  mov     rsp, r11
0x1800136b1  pop     rdi
0x1800136b2  retn
0x1800136b3  mov     rcx, cs:eaphost_Context
0x1800136ba  lea     rdx, DebugErrorEvent
0x1800136c1  call    cs:__imp_EtwEventEnabled
0x1800136c7  test    al, al
0x1800136c9  jz      short loc_180013709
0x1800136cb  mov     r9d, ebx
0x1800136ce  lea     r8, aCouldNotCreate; "Could not create IUMBusDriver while ini"...
0x1800136d5  mov     edx, 800h; unsigned __int64
0x1800136da  lea     rcx, [rsp+868h+var_818]; char *
0x1800136df  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800136e4  test    eax, eax
0x1800136e6  js      short loc_180013709
0x1800136e8  test    cs:byte_180020AC1, 8
0x1800136ef  jz      short loc_180013709
0x1800136f1  lea     r8, [rsp+868h+var_818]
0x1800136f6  lea     rdx, DebugErrorEvent
0x1800136fd  lea     rcx, eaphost_Context
0x180013704  call    McTemplateU0s_EtwEventWriteTransfer
0x180013709  mov     rcx, cs:WPP_GLOBAL_Control
0x180013710  lea     rax, WPP_GLOBAL_Control
0x180013717  cmp     rcx, rax
0x18001371a  jz      short loc_18001373A
0x18001371c  test    byte ptr [rcx+1Ch], 1
0x180013720  jz      short loc_18001373A
0x180013722  mov     rcx, [rcx+10h]
0x180013726  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x18001372d  mov     edx, 0Ah
0x180013732  mov     r9d, ebx
0x180013735  call    WPP_SF_d
0x18001373a  mov     edx, ebx
0x18001373c  lea     rcx, byte_180018CBC
0x180013743  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
