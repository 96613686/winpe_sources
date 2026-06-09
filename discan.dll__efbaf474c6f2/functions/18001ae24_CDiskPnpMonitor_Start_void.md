# CDiskPnpMonitor::Start(void)

- ea: `0x18001ae24`
- end: `0x18001b0f0`
- name: `?Start@CDiskPnpMonitor@@QEAAJXZ`
- size: `716`
- prototype: `__int64 __fastcall(CDiskPnpMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180016750`
- `0x180016d24`

## callees

- `0x180002e20`
- `0x1800032f8`
- `0x180006688`
- `0x180006874`
- `0x1800068b4`
- `0x180009088`
- `0x1800136c0`
- `0x180018e80`
- `0x180018ed8`
- `0x18001a6bc`
- `0x18001ae24`
- `0x1800375ee`
- `0x180037620`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x18001af03`
- `KERNEL32!ResetEvent` at `0x18001af03`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001af7e`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001af7e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001b025`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001b025`

## string_xrefs

- `0x18001b067`: `Hr = CONFIGRET_HR( CM_Register_Notification( &CmNotifyFilter, this, DeviceNotifyCallback, &DiskNotifyHandle ) )`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDiskPnpMonitor::Start(CDiskPnpMonitor *this)
{
  __int64 v2; // r8
  USHORT v3; // dx
  USHORT Length; // cx
  USHORT v5; // ax
  __int64 v6; // rdx
  CONFIGRET v7; // eax
  int v8; // eax
  signed int v9; // ebx
  signed int v10; // eax
  _QWORD v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h]
  char v15; // [rsp+4Ch] [rbp-B4h]
  __int64 *v16; // [rsp+50h] [rbp-B0h] BYREF
  const char *v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[4]; // [rsp+74h] [rbp-8Ch] BYREF
  int v22; // [rsp+78h] [rbp-88h]
  GUID v23; // [rsp+80h] [rbp-80h]

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v2 + 16) = "CDiskPnpMonitor::Start";
  v17 = "CDiskPnpMonitor::Start";
  v3 = ++*(_WORD *)(v2 + 8);
  Length = GlobalIndentString.Length;
  v5 = GlobalIndentString.Length;
  if ( v3 < GlobalIndentString.Length )
    v5 = *(_WORD *)(v2 + 8);
  LOWORD(v12[0]) = v5;
  if ( v3 < GlobalIndentString.Length )
    Length = v3;
  WORD1(v12[0]) = Length;
  HIDWORD(v12[0]) = 0;
  v12[1] = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskPnpMonitor::Start");
  }
  *((_DWORD *)this + 6) = 1;
  ResetEvent(*((HANDLE *)this + 1));
  v20 = 416;
  memset_0(v21, 0, 0x19Cu);
  v22 = 0;
  v23 = GUID_DEVINTERFACE_DISK;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v19, (__int64)this);
  v16 = &v19;
  v12[0] = *((_QWORD *)this + 1);
  v7 = CM_Register_Notification(&v20, v6, &CDiskPnpMonitor::DeviceNotifyCallback, &v13);
  if ( !v7 )
  {
    v18 = 0;
LABEL_11:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids, v13);
    }
    v8 = CDiskPnpMonitor::RegisterExistingDisks(this);
    v9 = v8;
    v18 = v8;
    if ( v8 >= 0 )
    {
      v16 = 0;
      *((_DWORD *)this + 6) = 0;
      *((_QWORD *)this + 30) = CHandleT<void *,NtHandleTrait>::Detach(&v13);
      v18 = 0;
      v9 = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
        (unsigned int)"Hr = RegisterExistingDisks()",
        v8);
    }
    goto LABEL_29;
  }
  v10 = CM_MapCrToWin32Err(v7, 0xDu);
  v9 = v10;
  if ( v10 > 0 )
    v9 = (unsigned __int16)v10 | 0x80070000;
  v18 = v9;
  if ( v9 >= 0 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
      (unsigned int)"Hr = CONFIGRET_HR( CM_Register_Notification( &CmNotifyFilter, this, DeviceNotifyCallback, &DiskNotifyHandle ) )",
      v9);
  }
LABEL_29:
  CAutoSetEvent::~CAutoSetEvent((CAutoSetEvent *)v12);
  CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___::_CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___((__int64 *)&v16);
  CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>::~CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>(&v13);
  CHResultImp::~CHResultImp((CHResultImp *)&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ae24  mov     [rsp-8+arg_8], rbx
0x18001ae29  mov     [rsp-8+arg_10], rdi
0x18001ae2e  push    rbp
0x18001ae2f  push    r14
0x18001ae31  push    r15
0x18001ae33  lea     rbp, [rsp-120h]
0x18001ae3b  sub     rsp, 220h
0x18001ae42  mov     rax, cs:__security_cookie
0x18001ae49  xor     rax, rsp
0x18001ae4c  mov     [rbp+130h+var_20], rax
0x18001ae53  mov     rdi, rcx
0x18001ae56  mov     edx, cs:_tls_index
0x18001ae5c  mov     rax, gs:58h
0x18001ae65  mov     r8, [rax+rdx*8]
0x18001ae69  mov     eax, 10h
0x18001ae6e  lea     r9, aCdiskpnpmonito_0; "CDiskPnpMonitor::Start"
0x18001ae75  mov     [rax+r8], r9
0x18001ae79  mov     [rsp+230h+var_1D8], r9
0x18001ae7e  mov     edx, 8
0x18001ae83  mov     r14d, 1
0x18001ae89  add     [rdx+r8], r14w
0x18001ae8e  movzx   edx, word ptr [rdx+r8]
0x18001ae93  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001ae9a  movzx   eax, cx
0x18001ae9d  cmp     dx, cx
0x18001aea0  cmovb   ax, dx
0x18001aea4  mov     word ptr [rsp+230h+var_200], ax
0x18001aea9  cmovb   cx, dx
0x18001aead  mov     word ptr [rsp+230h+var_200+2], cx
0x18001aeb2  xor     eax, eax
0x18001aeb4  mov     dword ptr [rsp+230h+var_200+4], eax
0x18001aeb8  mov     rax, cs:off_180047060; "                                       "...
0x18001aebf  mov     [rsp+230h+var_1F8], rax
0x18001aec4  lea     r15, WPP_GLOBAL_Control
0x18001aecb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aed2  cmp     rcx, r15
0x18001aed5  jz      short loc_18001AEFB
0x18001aed7  test    [rcx+1Ch], r14b
0x18001aedb  jz      short loc_18001AEFB
0x18001aedd  cmp     byte ptr [rcx+19h], 5
0x18001aee1  jb      short loc_18001AEFB
0x18001aee3  lea     edx, [r14+0Ch]
0x18001aee7  mov     [rsp+230h+var_210], r9; __int64
0x18001aeec  lea     r9, [rsp+230h+var_200]
0x18001aef1  mov     rcx, [rcx+10h]; LoggerHandle
0x18001aef5  call    WPP_SF_aZs
0x18001aefa  nop
0x18001aefb  mov     [rdi+18h], r14d
0x18001aeff  mov     rcx, [rdi+8]; hEvent
0x18001af03  call    cs:__imp_ResetEvent
0x18001af09  mov     [rsp+230h+var_1C0], 1A0h
0x18001af11  xor     edx, edx; Val
0x18001af13  mov     r8d, 19Ch; Size
0x18001af19  lea     rcx, [rsp+230h+var_1BC]; void *
0x18001af1e  call    memset_0
0x18001af23  mov     [rsp+230h+var_1B8], 0
0x18001af2b  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_DISK.Data1
0x18001af32  movdqu  [rbp+130h+var_1B0], xmm0
0x18001af37  mov     [rsp+230h+var_1F0], 0
0x18001af40  mov     [rsp+230h+var_1E8], 0
0x18001af48  mov     [rsp+230h+var_1E4], 0
0x18001af4d  mov     rdx, rdi
0x18001af50  lea     rcx, [rsp+230h+var_1C8]
0x18001af55  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001af5a  lea     rcx, [rsp+230h+var_1C8]
0x18001af5f  mov     [rsp+230h+var_1E0], rcx
0x18001af64  mov     rax, [rdi+8]
0x18001af68  mov     [rsp+230h+var_200], rax
0x18001af6d  lea     r9, [rsp+230h+var_1F0]
0x18001af72  lea     r8, ?DeviceNotifyCallback@CDiskPnpMonitor@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; CDiskPnpMonitor::DeviceNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18001af79  lea     rcx, [rsp+230h+var_1C0]
0x18001af7e  call    cs:__imp_CM_Register_Notification
0x18001af84  test    eax, eax
0x18001af86  jnz     loc_18001B01E
0x18001af8c  mov     [rsp+230h+var_1D0], eax
0x18001af90  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af97  cmp     rcx, r15
0x18001af9a  jz      short loc_18001AFC2
0x18001af9c  test    [rcx+1Ch], r14b
0x18001afa0  jz      short loc_18001AFC2
0x18001afa2  cmp     byte ptr [rcx+19h], 4
0x18001afa6  jb      short loc_18001AFC2
0x18001afa8  mov     edx, 0Dh
0x18001afad  mov     r9, [rsp+230h+var_1F0]
0x18001afb2  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001afb9  mov     rcx, [rcx+10h]
0x18001afbd  call    WPP_SF_q
0x18001afc2  mov     rcx, rdi; this
0x18001afc5  call    ?RegisterExistingDisks@CDiskPnpMonitor@@AEAAJXZ; CDiskPnpMonitor::RegisterExistingDisks(void)
0x18001afca  mov     ebx, eax
0x18001afcc  mov     [rsp+230h+var_1D0], eax
0x18001afd0  test    eax, eax
0x18001afd2  jns     loc_18001B070
0x18001afd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afdf  cmp     rcx, r15
0x18001afe2  jz      loc_18001B09B
0x18001afe8  test    [rcx+1Ch], r14b
0x18001afec  jz      loc_18001B09B
0x18001aff2  cmp     byte ptr [rcx+19h], 2
0x18001aff6  jb      loc_18001B09B
0x18001affc  mov     edx, 0Eh
0x18001b001  mov     dword ptr [rsp+230h+var_210], eax
0x18001b005  lea     r9, aHrRegisterexis; "Hr = RegisterExistingDisks()"
0x18001b00c  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001b013  mov     rcx, [rcx+10h]
0x18001b017  call    WPP_SF_sd
0x18001b01c  jmp     short loc_18001B09B
0x18001b01e  mov     edx, 0Dh; DefaultErr
0x18001b023  mov     ecx, eax; CmReturnCode
0x18001b025  call    cs:__imp_CM_MapCrToWin32Err
0x18001b02b  mov     ebx, eax
0x18001b02d  test    eax, eax
0x18001b02f  jle     short loc_18001B03A
0x18001b031  movzx   ebx, ax
0x18001b034  or      ebx, 80070000h
0x18001b03a  mov     [rsp+230h+var_1D0], ebx
0x18001b03e  test    ebx, ebx
0x18001b040  jns     loc_18001AF90
0x18001b046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b04d  cmp     rcx, r15
0x18001b050  jz      short loc_18001B09B
0x18001b052  test    [rcx+1Ch], r14b
0x18001b056  jz      short loc_18001B09B
0x18001b058  cmp     byte ptr [rcx+19h], 2
0x18001b05c  jb      short loc_18001B09B
0x18001b05e  mov     edx, 0Ch
0x18001b063  mov     dword ptr [rsp+230h+var_210], ebx
0x18001b067  lea     r9, aHrConfigretHrC_1; "Hr = CONFIGRET_HR( CM_Register_Notifica"...
0x18001b06e  jmp     short loc_18001B00C
0x18001b070  mov     [rsp+230h+var_1E0], 0
0x18001b079  mov     dword ptr [rdi+18h], 0
0x18001b080  lea     rcx, [rsp+230h+var_1F0]
0x18001b085  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18001b08a  mov     [rdi+0F0h], rax
0x18001b091  mov     [rsp+230h+var_1D0], 0
0x18001b099  xor     ebx, ebx
0x18001b09b  lea     rcx, [rsp+230h+var_200]; this
0x18001b0a0  call    ??1CAutoSetEvent@@QEAA@XZ; CAutoSetEvent::~CAutoSetEvent(void)
0x18001b0a5  nop
0x18001b0a6  lea     rcx, [rsp+230h+var_1E0]
0x18001b0ab  call    CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b______CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___
0x18001b0b0  nop
0x18001b0b1  lea     rcx, [rsp+230h+var_1F0]
0x18001b0b6  call    ??1?$CHandleT@PEAUHCMNOTIFICATION__@@UCCmNotificationHandleTrait@@@@QEAA@XZ; CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>::~CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>(void)
0x18001b0bb  nop
0x18001b0bc  lea     rcx, [rsp+230h+var_1D8]; this
0x18001b0c1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001b0c6  mov     eax, ebx
0x18001b0c8  mov     rcx, [rbp+130h+var_20]
0x18001b0cf  xor     rcx, rsp; StackCookie
0x18001b0d2  call    __security_check_cookie
0x18001b0d7  lea     r11, [rsp+230h+var_10]
0x18001b0df  mov     rbx, [r11+28h]
0x18001b0e3  mov     rdi, [r11+30h]
0x18001b0e7  mov     rsp, r11
0x18001b0ea  pop     r15
0x18001b0ec  pop     r14
0x18001b0ee  pop     rbp
0x18001b0ef  retn
```
