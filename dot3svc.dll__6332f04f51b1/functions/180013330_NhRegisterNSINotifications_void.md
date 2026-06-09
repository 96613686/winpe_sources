# NhRegisterNSINotifications(void)

- ea: `0x180013330`
- end: `0x180013466`
- name: `?NhRegisterNSINotifications@@YAKXZ`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000aac0`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180013330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001334a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001334a`
- `WINNSI!NsiDisconnectFromServer` at `0x180013417`
- `WINNSI!NsiDisconnectFromServer` at `0x180013417`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x1800133cd`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x1800133cd`
- `WINNSI!NsiConnectToServer` at `0x180013338`
- `WINNSI!NsiConnectToServer` at `0x180013338`

## pseudocode

```c
__int64 NhRegisterNSINotifications(void)
{
  void *v0; // rax
  DWORD LastError; // eax
  DWORD v2; // ebx

  v0 = (void *)NsiConnectToServer(0);
  g_NsiServerHandle = v0;
  if ( v0 )
  {
    v2 = NsiRpcRegisterChangeNotification(
           v0,
           &NPI_MS_NDIS_MODULEID,
           1,
           &NhNSINotificationHandler,
           0,
           0,
           &g_NsiNotificationHandle);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 58, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids, v2);
      }
      NsiDisconnectFromServer(g_NsiServerHandle);
      g_NsiServerHandle = 0;
    }
    else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
           && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
           && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 59, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids);
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 57, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180013330  push    rbx
0x180013332  sub     rsp, 40h
0x180013336  xor     ecx, ecx
0x180013338  call    cs:__imp_NsiConnectToServer
0x18001333e  mov     cs:?g_NsiServerHandle@@3PEAXEA, rax; void * g_NsiServerHandle
0x180013345  test    rax, rax
0x180013348  jnz     short loc_18001339C
0x18001334a  call    cs:__imp_GetLastError
0x180013350  mov     ebx, eax
0x180013352  mov     r10, cs:WPP_GLOBAL_Control
0x180013359  lea     rcx, WPP_GLOBAL_Control
0x180013360  cmp     r10, rcx
0x180013363  jz      loc_18001345E
0x180013369  cmp     byte ptr [r10+19h], 1
0x18001336e  jb      loc_18001345E
0x180013374  test    byte ptr [r10+1Ch], 1
0x180013379  jz      loc_18001345E
0x18001337f  mov     rcx, [r10+10h]
0x180013383  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x18001338a  mov     edx, 39h ; '9'
0x18001338f  mov     r9d, eax
0x180013392  call    WPP_SF_d
0x180013397  jmp     loc_18001345E
0x18001339c  lea     rcx, ?g_NsiNotificationHandle@@3PEAXEA; void * g_NsiNotificationHandle
0x1800133a3  mov     r8d, 1
0x1800133a9  mov     [rsp+48h+var_18], rcx
0x1800133ae  lea     r9, ?NhNSINotificationHandler@@YAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z; NhNSINotificationHandler(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)
0x1800133b5  mov     [rsp+48h+var_20], 0
0x1800133be  lea     rdx, NPI_MS_NDIS_MODULEID
0x1800133c5  mov     rcx, rax
0x1800133c8  mov     [rsp+48h+var_28], 0
0x1800133cd  call    cs:__imp_NsiRpcRegisterChangeNotification
0x1800133d3  mov     ebx, eax
0x1800133d5  test    eax, eax
0x1800133d7  jz      short loc_18001342A
0x1800133d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800133e0  lea     rcx, WPP_GLOBAL_Control
0x1800133e7  cmp     rax, rcx
0x1800133ea  jz      short loc_180013410
0x1800133ec  cmp     byte ptr [rax+19h], 1
0x1800133f0  jb      short loc_180013410
0x1800133f2  test    byte ptr [rax+1Ch], 1
0x1800133f6  jz      short loc_180013410
0x1800133f8  mov     rcx, [rax+10h]
0x1800133fc  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x180013403  mov     edx, 3Ah ; ':'
0x180013408  mov     r9d, ebx
0x18001340b  call    WPP_SF_d
0x180013410  mov     rcx, cs:?g_NsiServerHandle@@3PEAXEA; void * g_NsiServerHandle
0x180013417  call    cs:__imp_NsiDisconnectFromServer
0x18001341d  mov     cs:?g_NsiServerHandle@@3PEAXEA, 0; void * g_NsiServerHandle
0x180013428  jmp     short loc_18001345E
0x18001342a  mov     rax, cs:WPP_GLOBAL_Control
0x180013431  lea     rcx, WPP_GLOBAL_Control
0x180013438  cmp     rax, rcx
0x18001343b  jz      short loc_18001345E
0x18001343d  cmp     byte ptr [rax+19h], 4
0x180013441  jb      short loc_18001345E
0x180013443  test    byte ptr [rax+1Ch], 1
0x180013447  jz      short loc_18001345E
0x180013449  mov     rcx, [rax+10h]
0x18001344d  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x180013454  mov     edx, 3Bh ; ';'
0x180013459  call    WPP_SF_
0x18001345e  mov     eax, ebx
0x180013460  add     rsp, 40h
0x180013464  pop     rbx
0x180013465  retn
```
