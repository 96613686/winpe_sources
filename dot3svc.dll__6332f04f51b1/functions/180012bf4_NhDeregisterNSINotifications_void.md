# NhDeregisterNSINotifications(void)

- ea: `0x180012bf4`
- end: `0x180012cbd`
- name: `?NhDeregisterNSINotifications@@YAXXZ`
- size: `201`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000b9fc`

## callees

- `0x18000c230`
- `0x180012bf4`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x180012c79`
- `WINNSI!NsiDisconnectFromServer` at `0x180012c79`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180012c52`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180012c52`

## pseudocode

```c
void NhDeregisterNSINotifications(void)
{
  struct _LIST_ENTRY *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 60, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_NsiNotificationHandle )
  {
    NsiRpcDeregisterChangeNotification(g_NsiServerHandle, &NPI_MS_NDIS_MODULEID, 0);
    v0 = WPP_GLOBAL_Control;
    g_NsiNotificationHandle = 0;
  }
  if ( g_NsiServerHandle )
  {
    NsiDisconnectFromServer(g_NsiServerHandle);
    v0 = WPP_GLOBAL_Control;
    g_NsiNotificationHandle = 0;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v0[1].Blink) >= 4u && (BYTE4(v0[1].Blink) & 1) != 0 )
    WPP_SF_(v0[1].Flink, 61, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids);
}

```

## disassembly

```asm
0x180012bf4  push    rbx
0x180012bf6  sub     rsp, 20h
0x180012bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c01  lea     rbx, WPP_GLOBAL_Control
0x180012c08  cmp     rcx, rbx
0x180012c0b  jz      short loc_180012C35
0x180012c0d  cmp     byte ptr [rcx+19h], 4
0x180012c11  jb      short loc_180012C35
0x180012c13  test    byte ptr [rcx+1Ch], 1
0x180012c17  jz      short loc_180012C35
0x180012c19  mov     rcx, [rcx+10h]
0x180012c1d  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x180012c24  mov     edx, 3Ch ; '<'
0x180012c29  call    WPP_SF_
0x180012c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c35  mov     r9, cs:?g_NsiNotificationHandle@@3PEAXEA; void * g_NsiNotificationHandle
0x180012c3c  test    r9, r9
0x180012c3f  jz      short loc_180012C6A
0x180012c41  mov     rcx, cs:?g_NsiServerHandle@@3PEAXEA; void * g_NsiServerHandle
0x180012c48  lea     rdx, NPI_MS_NDIS_MODULEID
0x180012c4f  xor     r8d, r8d
0x180012c52  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180012c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c5f  mov     cs:?g_NsiNotificationHandle@@3PEAXEA, 0; void * g_NsiNotificationHandle
0x180012c6a  mov     rax, cs:?g_NsiServerHandle@@3PEAXEA; void * g_NsiServerHandle
0x180012c71  test    rax, rax
0x180012c74  jz      short loc_180012C91
0x180012c76  mov     rcx, rax
0x180012c79  call    cs:__imp_NsiDisconnectFromServer
0x180012c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c86  mov     cs:?g_NsiNotificationHandle@@3PEAXEA, 0; void * g_NsiNotificationHandle
0x180012c91  cmp     rcx, rbx
0x180012c94  jz      short loc_180012CB7
0x180012c96  cmp     byte ptr [rcx+19h], 4
0x180012c9a  jb      short loc_180012CB7
0x180012c9c  test    byte ptr [rcx+1Ch], 1
0x180012ca0  jz      short loc_180012CB7
0x180012ca2  mov     rcx, [rcx+10h]
0x180012ca6  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x180012cad  mov     edx, 3Dh ; '='
0x180012cb2  call    WPP_SF_
0x180012cb7  add     rsp, 20h
0x180012cbb  pop     rbx
0x180012cbc  retn
```
