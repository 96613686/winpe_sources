# PmSaveUserData(void *,_GUID const *,_GUID const *,ushort *,ulong,uchar *,int)

- ea: `0x18000ce28`
- end: `0x18000cfbe`
- name: `?PmSaveUserData@@YAKPEAXPEBU_GUID@@1PEAGKPEAEH@Z`
- size: `406`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _GUID *, struct _GUID *, unsigned __int16 *, DWORD, unsigned __int8 *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180021270`
- `0x1800213c4`
- `0x180021b40`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000c95c`
- `0x18000ce28`
- `0x18000d5ec`
- `0x1800106ec`
- `0x180013264`
- `0x18001dd30`
- `0x180032d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ceaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ceaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf59`

## pseudocode

```c
__int64 __fastcall PmSaveUserData(
        HANDLE TokenHandle,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        DWORD a5,
        unsigned __int8 *a6,
        int a7)
{
  struct _PM_PROFILE *v7; // rdi
  struct _LIST_ENTRY *v12; // rcx
  unsigned int InterfaceContextHandle; // ebx
  unsigned __int8 *v14; // r14
  const unsigned __int16 *v15; // rdx
  unsigned int Profile; // eax
  GUID v17; // xmm0
  void *v19; // [rsp+30h] [rbp-30h] BYREF
  _L2_NOTIFICATION_DATA v20; // [rsp+38h] [rbp-28h] BYREF
  struct _PM_PROFILE *v21; // [rsp+A8h] [rbp+48h] BYREF

  v7 = 0;
  v19 = 0;
  v21 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 67, WPP_935883eb83d333df730e157613565e66_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    EnterCriticalSection(&stru_180052D40);
    v14 = a6;
    InterfaceContextHandle = StSaveUserData(TokenHandle, a2, a3, a4, a5, a6);
    if ( !InterfaceContextHandle )
    {
      if ( !TokenHandle )
      {
        if ( v14 )
        {
          Profile = PmGetProfile(a2, v15, &v21);
          v7 = v21;
          InterfaceContextHandle = Profile;
          if ( !Profile )
            PmpCheckAndLog1xSqmEvent(v21, 0x20u);
        }
      }
      if ( a7 )
      {
        if ( a2 )
        {
          InterfaceContextHandle = WimGetInterfaceContextHandle(a2, &v19);
          if ( !InterfaceContextHandle )
          {
            v17 = *a2;
            *(_QWORD *)&v20.dwDataSize = 0;
            v20.InterfaceGuid = v17;
            v20.NotificationSource = 1;
            v20.NotificationCode = 65538;
            v20.pData = 0;
            NhNotify(v19, &v20);
          }
        }
      }
    }
    LeaveCriticalSection(&stru_180052D40);
    if ( v7 )
      LpFreeProfile(v7);
    v12 = WPP_GLOBAL_Control;
  }
  else
  {
    InterfaceContextHandle = 87;
  }
  if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v12[1].Blink) >= 4u && (BYTE4(v12[1].Blink) & 1) != 0 )
    WPP_SF_d(v12[1].Flink, 68, WPP_935883eb83d333df730e157613565e66_Traceguids, InterfaceContextHandle);
  return InterfaceContextHandle;
}

```

## disassembly

```asm
0x18000ce28  mov     [rsp-28h+arg_0], rbx
0x18000ce2d  mov     [rsp-28h+arg_8], rsi
0x18000ce32  push    rbp
0x18000ce33  push    rdi
0x18000ce34  push    r12
0x18000ce36  push    r14
0x18000ce38  push    r15
0x18000ce3a  mov     rbp, rsp
0x18000ce3d  sub     rsp, 60h
0x18000ce41  xor     edi, edi
0x18000ce43  mov     [rbp+var_30], 0
0x18000ce4b  mov     [rbp+arg_18], rdi
0x18000ce4f  mov     rbx, r9
0x18000ce52  mov     r12, r8
0x18000ce55  mov     rsi, rdx
0x18000ce58  mov     r15, rcx
0x18000ce5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce62  lea     rax, WPP_GLOBAL_Control
0x18000ce69  cmp     rcx, rax
0x18000ce6c  jz      short loc_18000CE94
0x18000ce6e  cmp     byte ptr [rcx+19h], 4
0x18000ce72  jb      short loc_18000CE94
0x18000ce74  test    byte ptr [rcx+1Ch], 1
0x18000ce78  jz      short loc_18000CE94
0x18000ce7a  mov     rcx, [rcx+10h]
0x18000ce7e  lea     edx, [rdi+43h]
0x18000ce81  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ce88  call    WPP_SF_
0x18000ce8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce94  test    rbx, rbx
0x18000ce97  jnz     short loc_18000CEA3
0x18000ce99  mov     ebx, 57h ; 'W'
0x18000ce9e  jmp     loc_18000CF73
0x18000cea3  lea     rcx, stru_180052D40; lpCriticalSection
0x18000ceaa  call    cs:__imp_EnterCriticalSection
0x18000ceb0  mov     eax, [rbp+arg_20]
0x18000ceb3  mov     r9, rbx; unsigned __int16 *
0x18000ceb6  mov     r14, [rbp+arg_28]
0x18000ceba  mov     r8, r12; struct _GUID *
0x18000cebd  mov     [rsp+60h+var_38], r14; unsigned __int8 *
0x18000cec2  mov     rdx, rsi; rguid
0x18000cec5  mov     rcx, r15; TokenHandle
0x18000cec8  mov     [rsp+60h+var_40], eax; unsigned int
0x18000cecc  call    ?StSaveUserData@@YAKPEAXPEBU_GUID@@1PEBGKPEAE@Z; StSaveUserData(void *,_GUID const *,_GUID const *,ushort const *,ulong,uchar *)
0x18000ced1  mov     ebx, eax
0x18000ced3  test    eax, eax
0x18000ced5  jnz     short loc_18000CF52
0x18000ced7  test    r15, r15
0x18000ceda  jnz     short loc_18000CF02
0x18000cedc  test    r14, r14
0x18000cedf  jz      short loc_18000CF02
0x18000cee1  lea     r8, [rbp+arg_18]; struct _PM_PROFILE **
0x18000cee5  mov     rcx, rsi; struct _GUID *
0x18000cee8  call    ?PmGetProfile@@YAKPEAU_GUID@@PEBGPEAPEAU_PM_PROFILE@@@Z; PmGetProfile(_GUID *,ushort const *,_PM_PROFILE * *)
0x18000ceed  mov     rdi, [rbp+arg_18]
0x18000cef1  mov     ebx, eax
0x18000cef3  test    eax, eax
0x18000cef5  jnz     short loc_18000CF02
0x18000cef7  lea     edx, [rax+20h]; unsigned int
0x18000cefa  mov     rcx, rdi; struct _PM_PROFILE *
0x18000cefd  call    ?PmpCheckAndLog1xSqmEvent@@YAKPEAU_PM_PROFILE@@K@Z; PmpCheckAndLog1xSqmEvent(_PM_PROFILE *,ulong)
0x18000cf02  cmp     [rbp+arg_30], 0
0x18000cf06  jz      short loc_18000CF52
0x18000cf08  test    rsi, rsi
0x18000cf0b  jz      short loc_18000CF52
0x18000cf0d  lea     rdx, [rbp+var_30]; void **
0x18000cf11  mov     rcx, rsi; struct _GUID *
0x18000cf14  call    ?WimGetInterfaceContextHandle@@YAKPEBU_GUID@@PEAPEAX@Z; WimGetInterfaceContextHandle(_GUID const *,void * *)
0x18000cf19  mov     ebx, eax
0x18000cf1b  test    eax, eax
0x18000cf1d  jnz     short loc_18000CF52
0x18000cf1f  movups  xmm0, xmmword ptr [rsi]
0x18000cf22  mov     rcx, [rbp+var_30]; void *
0x18000cf26  lea     rdx, [rbp+var_28]; struct _L2_NOTIFICATION_DATA *
0x18000cf2a  mov     qword ptr [rbp+var_28.dwDataSize], 0
0x18000cf32  movdqu  xmmword ptr [rbp+var_28.InterfaceGuid.Data1], xmm0
0x18000cf37  mov     [rbp+var_28.NotificationSource], 1
0x18000cf3e  mov     [rbp+var_28.NotificationCode], 10002h
0x18000cf45  mov     [rbp+var_28.pData], 0
0x18000cf4d  call    ?NhNotify@@YAKPEAXPEAU_L2_NOTIFICATION_DATA@@@Z; NhNotify(void *,_L2_NOTIFICATION_DATA *)
0x18000cf52  lea     rcx, stru_180052D40; lpCriticalSection
0x18000cf59  call    cs:__imp_LeaveCriticalSection
0x18000cf5f  test    rdi, rdi
0x18000cf62  jz      short loc_18000CF6C
0x18000cf64  mov     rcx, rdi; lpMem
0x18000cf67  call    LpFreeProfile
0x18000cf6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf73  lea     rax, WPP_GLOBAL_Control
0x18000cf7a  cmp     rcx, rax
0x18000cf7d  jz      short loc_18000CFA3
0x18000cf7f  cmp     byte ptr [rcx+19h], 4
0x18000cf83  jb      short loc_18000CFA3
0x18000cf85  test    byte ptr [rcx+1Ch], 1
0x18000cf89  jz      short loc_18000CFA3
0x18000cf8b  mov     rcx, [rcx+10h]
0x18000cf8f  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000cf96  mov     edx, 44h ; 'D'
0x18000cf9b  mov     r9d, ebx
0x18000cf9e  call    WPP_SF_d
0x18000cfa3  lea     r11, [rsp+60h+var_s0]
0x18000cfa8  mov     eax, ebx
0x18000cfaa  mov     rbx, [r11+30h]
0x18000cfae  mov     rsi, [r11+38h]
0x18000cfb2  mov     rsp, r11
0x18000cfb5  pop     r15
0x18000cfb7  pop     r14
0x18000cfb9  pop     r12
0x18000cfbb  pop     rdi
0x18000cfbc  pop     rbp
0x18000cfbd  retn
```
