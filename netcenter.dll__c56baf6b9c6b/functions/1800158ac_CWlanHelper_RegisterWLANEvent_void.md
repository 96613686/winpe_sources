# CWlanHelper::RegisterWLANEvent(void)

- ea: `0x1800158ac`
- end: `0x1800159bb`
- name: `?RegisterWLANEvent@CWlanHelper@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(PVOID pCallbackContext)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf2c`
- `0x180019d98`

## callees

- `0x180014274`
- `0x1800158ac`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x1800158ef`
- `wlanapi!WlanOpenHandle` at `0x1800158ef`
- `wlanapi!WlanRegisterNotification` at `0x18001592b`
- `wlanapi!WlanRegisterNotification` at `0x18001592b`

## pseudocode

```c
__int64 __fastcall CWlanHelper::RegisterWLANEvent(char *pCallbackContext)
{
  HANDLE *v1; // rbx
  signed int v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  DWORD pdwNegotiatedVersion; // [rsp+50h] [rbp+8h] BYREF
  DWORD pdwPrevNotifSource; // [rsp+58h] [rbp+10h] BYREF

  v1 = (HANDLE *)(pCallbackContext + 16);
  if ( *((_QWORD *)pCallbackContext + 2) )
    return 2147500037LL;
  pdwNegotiatedVersion = 0;
  pdwPrevNotifSource = 0;
  v4 = WlanOpenHandle(1u, 0, &pdwNegotiatedVersion, (PHANDLE)pCallbackContext + 2);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_384ee4f638c731eee71d92814a6a0ad2_Traceguids,
        (unsigned int)v4);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = 0;
  }
  else
  {
    v5 = WlanRegisterNotification(*v1, 0x18u, 1, WLANNotificationCallback, pCallbackContext, 0, &pdwPrevNotifSource);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_d(v7[2], 11, &WPP_384ee4f638c731eee71d92814a6a0ad2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800158ac  mov     [rsp+arg_10], rbx
0x1800158b1  mov     [rsp+arg_18], rbp
0x1800158b6  push    rdi
0x1800158b7  sub     rsp, 40h
0x1800158bb  lea     rbx, [rcx+10h]
0x1800158bf  mov     rdi, rcx
0x1800158c2  cmp     qword ptr [rbx], 0
0x1800158c6  jz      short loc_1800158D2
0x1800158c8  mov     eax, 80004005h
0x1800158cd  jmp     loc_1800159AB
0x1800158d2  xor     edx, edx; pReserved
0x1800158d4  mov     [rsp+48h+pdwNegotiatedVersion], 0
0x1800158dc  mov     r9, rbx; phClientHandle
0x1800158df  mov     [rsp+48h+arg_8], 0
0x1800158e7  lea     r8, [rsp+48h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1800158ec  lea     ecx, [rdx+1]; dwClientVersion
0x1800158ef  call    cs:__imp_WlanOpenHandle
0x1800158f5  lea     rbp, WPP_GLOBAL_Control
0x1800158fc  test    eax, eax
0x1800158fe  jnz     short loc_180015949
0x180015900  mov     rcx, [rbx]; hClientHandle
0x180015903  lea     rax, [rsp+48h+arg_8]
0x180015908  mov     [rsp+48h+pdwPrevNotifSource], rax; pdwPrevNotifSource
0x18001590d  lea     r9, ?WLANNotificationCallback@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x180015914  mov     edx, 18h; dwNotifSource
0x180015919  mov     [rsp+48h+pReserved], 0; pReserved
0x180015922  mov     [rsp+48h+pCallbackContext], rdi; pCallbackContext
0x180015927  lea     r8d, [rdx-17h]; bIgnoreDuplicate
0x18001592b  call    cs:__imp_WlanRegisterNotification
0x180015931  mov     ebx, eax
0x180015933  test    eax, eax
0x180015935  jle     short loc_180015940
0x180015937  movzx   ebx, ax
0x18001593a  or      ebx, 80070000h
0x180015940  mov     rcx, cs:WPP_GLOBAL_Control
0x180015947  jmp     short loc_180015986
0x180015949  jle     short loc_180015953
0x18001594b  movzx   eax, ax
0x18001594e  or      eax, 80070000h
0x180015953  mov     rcx, cs:WPP_GLOBAL_Control
0x18001595a  cmp     rcx, rbp
0x18001595d  jz      short loc_180015984
0x18001595f  test    byte ptr [rcx+1Ch], 8
0x180015963  jz      short loc_180015984
0x180015965  mov     rcx, [rcx+10h]
0x180015969  lea     r8, WPP_384ee4f638c731eee71d92814a6a0ad2_Traceguids
0x180015970  mov     edx, 0Ah
0x180015975  mov     r9d, eax
0x180015978  call    WPP_SF_d
0x18001597d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015984  xor     ebx, ebx
0x180015986  cmp     rcx, rbp
0x180015989  jz      short loc_1800159A9
0x18001598b  test    byte ptr [rcx+1Ch], 8
0x18001598f  jz      short loc_1800159A9
0x180015991  mov     rcx, [rcx+10h]
0x180015995  lea     r8, WPP_384ee4f638c731eee71d92814a6a0ad2_Traceguids
0x18001599c  mov     edx, 0Bh
0x1800159a1  mov     r9d, ebx
0x1800159a4  call    WPP_SF_d
0x1800159a9  mov     eax, ebx
0x1800159ab  mov     rbx, [rsp+48h+arg_10]
0x1800159b0  mov     rbp, [rsp+48h+arg_18]
0x1800159b5  add     rsp, 40h
0x1800159b9  pop     rdi
0x1800159ba  retn
```
