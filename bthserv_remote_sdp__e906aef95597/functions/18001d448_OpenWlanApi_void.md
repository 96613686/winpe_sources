# OpenWlanApi(void)

- ea: `0x18001d448`
- end: `0x18001d74c`
- name: `?OpenWlanApi@@YAHXZ`
- size: `772`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001c720`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x18001cf10`
- `0x18001d448`
- `0x18001d754`
- `0x18001db00`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001d6d3`
- `wlanapi!WlanFreeMemory` at `0x18001d6d3`
- `wlanapi!WlanRegisterNotification` at `0x18001d66d`
- `wlanapi!WlanRegisterNotification` at `0x18001d66d`
- `wlanapi!WlanEnumInterfaces` at `0x18001d55c`
- `wlanapi!WlanEnumInterfaces` at `0x18001d55c`
- `wlanapi!WlanOpenHandle` at `0x18001d4d5`
- `wlanapi!WlanOpenHandle` at `0x18001d4d5`

## pseudocode

```c
__int64 OpenWlanApi(void)
{
  unsigned int v0; // edi
  char v1; // bl
  bool v2; // dl
  int v3; // edx
  int v4; // r8d
  DWORD v5; // r9d
  _QWORD *v6; // rcx
  DWORD dwNumberOfItems; // ecx
  bool v8; // dl
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+38h] BYREF
  DWORD pdwPrevNotifSource; // [rsp+98h] [rbp+40h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+A0h] [rbp+48h] BYREF
  void *phClientHandle; // [rsp+A8h] [rbp+50h] BYREF

  pdwNegotiatedVersion = 0;
  v0 = 0;
  ppInterfaceList = 0;
  pdwPrevNotifSource = 0;
  phClientHandle = 0;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  *((_QWORD *)pInterfaceGuid + 12) = phClientHandle;
  if ( v5 )
  {
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    *((_QWORD *)pInterfaceGuid + 12) = 0;
    goto LABEL_43;
  }
  if ( WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList) )
  {
    v6 = WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_24;
  }
  else
  {
    dwNumberOfItems = ppInterfaceList->dwNumberOfItems;
    *((_DWORD *)pInterfaceGuid + 28) = ppInterfaceList->dwNumberOfItems;
    if ( dwNumberOfItems == 1 )
    {
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      *(GUID *)pInterfaceGuid = ppInterfaceList->InterfaceInfo[0].InterfaceGuid;
      *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
      ProcessNotification();
    }
    if ( !WlanRegisterNotification(
            *((HANDLE *)pInterfaceGuid + 12),
            0x18u,
            1,
            AutoConfigNotificationCallback,
            0,
            0,
            &pdwPrevNotifSource) )
    {
      v0 = 1;
      goto LABEL_43;
    }
    v6 = WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_24:
      WPP_RECORDER_AND_TRACE_SF_sD(v6[2], v3, v4, v6[5]);
LABEL_43:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( ppInterfaceList )
  {
    WlanFreeMemory(ppInterfaceList);
    ppInterfaceList = 0;
    v6 = WPP_GLOBAL_Control;
  }
  if ( !v0 )
  {
    CloseWlanApi();
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 == &WPP_GLOBAL_Control || *((_BYTE *)v6 + 25) < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = v1;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(v6[2], v3, v4, v6[5]);
  }
  return v0;
}

```

## disassembly

```asm
0x18001d448  push    rbp
0x18001d44a  push    rbx
0x18001d44b  push    rdi
0x18001d44c  push    r13
0x18001d44e  push    r14
0x18001d450  push    r15
0x18001d452  mov     rbp, rsp
0x18001d455  sub     rsp, 58h
0x18001d459  and     [rbp+pdwNegotiatedVersion], 0
0x18001d45d  xor     edi, edi
0x18001d45f  and     [rbp+ppInterfaceList], rdi
0x18001d463  and     [rbp+arg_8], 0
0x18001d467  and     [rbp+phClientHandle], rdi
0x18001d46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d472  lea     r14, WPP_GLOBAL_Control
0x18001d479  lea     ebx, [rdi+1]
0x18001d47c  cmp     rcx, r14
0x18001d47f  jz      short loc_18001D48B
0x18001d481  cmp     byte ptr [rcx+19h], 4
0x18001d485  jb      short loc_18001D48B
0x18001d487  mov     dl, bl
0x18001d489  jmp     short loc_18001D48D
0x18001d48b  xor     dl, dl
0x18001d48d  lea     r15, WPP_RECORDER_INITIALIZED
0x18001d494  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001d49b  lea     r13, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001d4a2  setnz   r8b
0x18001d4a6  test    dl, dl
0x18001d4a8  jnz     short loc_18001D4AF
0x18001d4aa  test    r8b, r8b
0x18001d4ad  jz      short loc_18001D4C8
0x18001d4af  mov     r9, [rcx+28h]
0x18001d4b3  mov     rcx, [rcx+10h]
0x18001d4b7  mov     [rsp+58h+var_20], r13
0x18001d4bc  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Bh
0x18001d4c3  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001d4c8  xor     edx, edx; pReserved
0x18001d4ca  lea     r9, [rbp+phClientHandle]; phClientHandle
0x18001d4ce  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18001d4d2  lea     ecx, [rdx+2]; dwClientVersion
0x18001d4d5  call    cs:__imp_WlanOpenHandle
0x18001d4dc  nop     dword ptr [rax+rax+00h]
0x18001d4e1  mov     rcx, [rbp+phClientHandle]
0x18001d4e5  mov     r9d, eax
0x18001d4e8  mov     rax, cs:pInterfaceGuid
0x18001d4ef  mov     [rax+60h], rcx
0x18001d4f3  test    r9d, r9d
0x18001d4f6  jz      short loc_18001D552
0x18001d4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4ff  cmp     rcx, r14
0x18001d502  jz      short loc_18001D50E
0x18001d504  cmp     byte ptr [rcx+19h], 3
0x18001d508  jb      short loc_18001D50E
0x18001d50a  mov     dl, bl
0x18001d50c  jmp     short loc_18001D510
0x18001d50e  xor     dl, dl
0x18001d510  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001d517  setnz   r8b
0x18001d51b  test    dl, dl
0x18001d51d  jnz     short loc_18001D524
0x18001d51f  test    r8b, r8b
0x18001d522  jz      short loc_18001D542
0x18001d524  mov     [rsp+58h+var_10], r9d
0x18001d529  mov     r9, [rcx+28h]
0x18001d52d  mov     rcx, [rcx+10h]
0x18001d531  mov     [rsp+58h+var_20], r13
0x18001d536  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Ch
0x18001d53d  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001d542  mov     rax, cs:pInterfaceGuid
0x18001d549  and     [rax+60h], rdi
0x18001d54d  jmp     loc_18001D6C0
0x18001d552  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18001d556  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x18001d55a  xor     edx, edx; pReserved
0x18001d55c  call    cs:__imp_WlanEnumInterfaces
0x18001d563  nop     dword ptr [rax+rax+00h]
0x18001d568  test    eax, eax
0x18001d56a  jz      short loc_18001D5BE
0x18001d56c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d573  cmp     rcx, r14
0x18001d576  jz      short loc_18001D582
0x18001d578  cmp     byte ptr [rcx+19h], 3
0x18001d57c  jb      short loc_18001D582
0x18001d57e  mov     dl, bl
0x18001d580  jmp     short loc_18001D584
0x18001d582  xor     dl, dl
0x18001d584  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001d58b  setnz   r8b
0x18001d58f  test    dl, dl
0x18001d591  jnz     short loc_18001D59C
0x18001d593  test    r8b, r8b
0x18001d596  jz      loc_18001D6C7
0x18001d59c  mov     [rsp+58h+var_10], eax
0x18001d5a0  mov     [rsp+58h+var_20], r13
0x18001d5a5  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Dh
0x18001d5ac  mov     r9, [rcx+28h]
0x18001d5b0  mov     rcx, [rcx+10h]
0x18001d5b4  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001d5b9  jmp     loc_18001D6C0
0x18001d5be  mov     rax, [rbp+ppInterfaceList]
0x18001d5c2  mov     ecx, [rax]
0x18001d5c4  mov     rax, cs:pInterfaceGuid
0x18001d5cb  mov     [rax+70h], ecx
0x18001d5ce  cmp     ecx, ebx
0x18001d5d0  jnz     short loc_18001D640
0x18001d5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5d9  cmp     rcx, r14
0x18001d5dc  jz      short loc_18001D5E8
0x18001d5de  cmp     byte ptr [rcx+19h], 4
0x18001d5e2  jb      short loc_18001D5E8
0x18001d5e4  mov     dl, bl
0x18001d5e6  jmp     short loc_18001D5EA
0x18001d5e8  xor     dl, dl
0x18001d5ea  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001d5f1  setnz   r8b
0x18001d5f5  test    dl, dl
0x18001d5f7  jnz     short loc_18001D5FE
0x18001d5f9  test    r8b, r8b
0x18001d5fc  jz      short loc_18001D617
0x18001d5fe  mov     r9, [rcx+28h]
0x18001d602  mov     rcx, [rcx+10h]
0x18001d606  mov     [rsp+58h+var_20], r13
0x18001d60b  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Eh
0x18001d612  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001d617  mov     rax, [rbp+ppInterfaceList]
0x18001d61b  movups  xmm0, xmmword ptr [rax+8]
0x18001d61f  mov     rax, cs:pInterfaceGuid
0x18001d626  movdqu  xmmword ptr [rax], xmm0
0x18001d62a  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001d62f  mov     cl, al
0x18001d631  mov     rax, cs:pInterfaceGuid
0x18001d638  mov     [rax+78h], cl
0x18001d63b  call    ?ProcessNotification@@YAXXZ; ProcessNotification(void)
0x18001d640  mov     rcx, cs:pInterfaceGuid
0x18001d647  lea     rax, [rbp+arg_8]
0x18001d64b  mov     [rsp+58h+pdwPrevNotifSource], rax; pdwPrevNotifSource
0x18001d650  lea     r9, ?AutoConfigNotificationCallback@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18001d657  and     [rsp+58h+var_30], rdi
0x18001d65c  mov     r8d, ebx; bIgnoreDuplicate
0x18001d65f  and     [rsp+58h+var_38], rdi
0x18001d664  mov     edx, 18h; dwNotifSource
0x18001d669  mov     rcx, [rcx+60h]; hClientHandle
0x18001d66d  call    cs:__imp_WlanRegisterNotification
0x18001d674  nop     dword ptr [rax+rax+00h]
0x18001d679  test    eax, eax
0x18001d67b  jz      short loc_18001D6BE
0x18001d67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d684  cmp     rcx, r14
0x18001d687  jz      short loc_18001D693
0x18001d689  cmp     byte ptr [rcx+19h], 3
0x18001d68d  jb      short loc_18001D693
0x18001d68f  mov     dl, bl
0x18001d691  jmp     short loc_18001D695
0x18001d693  xor     dl, dl
0x18001d695  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001d69c  setnz   r8b
0x18001d6a0  test    dl, dl
0x18001d6a2  jnz     short loc_18001D6A9
0x18001d6a4  test    r8b, r8b
0x18001d6a7  jz      short loc_18001D6C7
0x18001d6a9  mov     [rsp+58h+var_10], eax
0x18001d6ad  mov     [rsp+58h+var_20], r13
0x18001d6b2  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Fh
0x18001d6b9  jmp     loc_18001D5AC
0x18001d6be  mov     edi, ebx
0x18001d6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6c7  mov     rax, [rbp+ppInterfaceList]
0x18001d6cb  test    rax, rax
0x18001d6ce  jz      short loc_18001D6EB
0x18001d6d0  mov     rcx, rax; pMemory
0x18001d6d3  call    cs:__imp_WlanFreeMemory
0x18001d6da  nop     dword ptr [rax+rax+00h]
0x18001d6df  and     [rbp+ppInterfaceList], 0
0x18001d6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6eb  test    edi, edi
0x18001d6ed  jnz     short loc_18001D6FB
0x18001d6ef  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001d6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6fb  cmp     rcx, r14
0x18001d6fe  jz      short loc_18001D706
0x18001d700  cmp     byte ptr [rcx+19h], 4
0x18001d704  jnb     short loc_18001D708
0x18001d706  xor     bl, bl
0x18001d708  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001d70f  setnz   r8b
0x18001d713  test    bl, bl
0x18001d715  jnz     short loc_18001D71C
0x18001d717  test    r8b, r8b
0x18001d71a  jz      short loc_18001D73B
0x18001d71c  mov     r9, [rcx+28h]
0x18001d720  mov     dl, bl
0x18001d722  mov     rcx, [rcx+10h]
0x18001d726  mov     [rsp+58h+var_10], edi
0x18001d72a  mov     [rsp+58h+var_20], r13
0x18001d72f  mov     word ptr [rsp+58h+pdwPrevNotifSource], 20h ; ' '
0x18001d736  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001d73b  mov     eax, edi
0x18001d73d  add     rsp, 58h
0x18001d741  pop     r15
0x18001d743  pop     r14
0x18001d745  pop     r13
0x18001d747  pop     rdi
0x18001d748  pop     rbx
0x18001d749  pop     rbp
0x18001d74a  retn
```
