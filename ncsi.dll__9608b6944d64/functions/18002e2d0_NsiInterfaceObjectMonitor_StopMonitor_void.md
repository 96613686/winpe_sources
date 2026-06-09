# NsiInterfaceObjectMonitor::StopMonitor(void)

- ea: `0x18002e2d0`
- end: `0x18002e43c`
- name: `?StopMonitor@NsiInterfaceObjectMonitor@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(NsiInterfaceObjectMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f00c`
- `0x1800451a0`

## callees

- `0x180010200`
- `0x18002e2d0`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18002e3f4`
- `WINNSI!NsiDisconnectFromServer` at `0x18002e3f4`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002e35f`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002e3b2`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002e35f`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002e3b2`

## pseudocode

```c
void __fastcall NsiInterfaceObjectMonitor::StopMonitor(NsiInterfaceObjectMonitor *this)
{
  __int64 v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_6854ba6a7a923d57f0889934fcf0aaf7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 18, WPP_6854ba6a7a923d57f0889934fcf0aaf7_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_IPV4_MODULEID, 7, *((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 4) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 19, WPP_6854ba6a7a923d57f0889934fcf0aaf7_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_IPV6_MODULEID, 7, *((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 20, WPP_6854ba6a7a923d57f0889934fcf0aaf7_Traceguids);
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
    WPP_SF_(*(_QWORD *)(v2 + 16), 21, WPP_6854ba6a7a923d57f0889934fcf0aaf7_Traceguids);
}

```

## disassembly

```asm
0x18002e2d0  mov     [rsp+arg_0], rbx
0x18002e2d5  mov     [rsp+arg_8], r14
0x18002e2da  push    r15
0x18002e2dc  sub     rsp, 20h
0x18002e2e0  mov     rbx, rcx
0x18002e2e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2ea  lea     r14, WPP_GLOBAL_Control
0x18002e2f1  lea     r15, WPP_6854ba6a7a923d57f0889934fcf0aaf7_Traceguids
0x18002e2f8  cmp     rcx, r14
0x18002e2fb  jz      short loc_18002E321
0x18002e2fd  test    byte ptr [rcx+1Ch], 4
0x18002e301  jz      short loc_18002E321
0x18002e303  cmp     byte ptr [rcx+19h], 5
0x18002e307  jb      short loc_18002E321
0x18002e309  mov     rcx, [rcx+10h]
0x18002e30d  mov     edx, 11h
0x18002e312  mov     r8, r15
0x18002e315  call    WPP_SF_
0x18002e31a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e321  cmp     qword ptr [rbx+18h], 0
0x18002e326  jz      short loc_18002E374
0x18002e328  cmp     rcx, r14
0x18002e32b  jz      short loc_18002E34A
0x18002e32d  test    byte ptr [rcx+1Ch], 4
0x18002e331  jz      short loc_18002E34A
0x18002e333  cmp     byte ptr [rcx+19h], 5
0x18002e337  jb      short loc_18002E34A
0x18002e339  mov     rcx, [rcx+10h]
0x18002e33d  mov     edx, 12h
0x18002e342  mov     r8, r15
0x18002e345  call    WPP_SF_
0x18002e34a  mov     r9, [rbx+18h]
0x18002e34e  lea     rdx, NPI_MS_IPV4_MODULEID
0x18002e355  mov     rcx, [rbx+10h]
0x18002e359  mov     r8d, 7
0x18002e35f  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002e365  mov     qword ptr [rbx+18h], 0
0x18002e36d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e374  cmp     qword ptr [rbx+20h], 0
0x18002e379  jz      short loc_18002E3C7
0x18002e37b  cmp     rcx, r14
0x18002e37e  jz      short loc_18002E39D
0x18002e380  test    byte ptr [rcx+1Ch], 4
0x18002e384  jz      short loc_18002E39D
0x18002e386  cmp     byte ptr [rcx+19h], 5
0x18002e38a  jb      short loc_18002E39D
0x18002e38c  mov     rcx, [rcx+10h]
0x18002e390  mov     edx, 13h
0x18002e395  mov     r8, r15
0x18002e398  call    WPP_SF_
0x18002e39d  mov     r9, [rbx+20h]
0x18002e3a1  lea     rdx, NPI_MS_IPV6_MODULEID
0x18002e3a8  mov     rcx, [rbx+10h]
0x18002e3ac  mov     r8d, 7
0x18002e3b2  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002e3b8  mov     qword ptr [rbx+20h], 0
0x18002e3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3c7  cmp     qword ptr [rbx+10h], 0
0x18002e3cc  jz      short loc_18002E409
0x18002e3ce  cmp     rcx, r14
0x18002e3d1  jz      short loc_18002E3F0
0x18002e3d3  test    byte ptr [rcx+1Ch], 4
0x18002e3d7  jz      short loc_18002E3F0
0x18002e3d9  cmp     byte ptr [rcx+19h], 5
0x18002e3dd  jb      short loc_18002E3F0
0x18002e3df  mov     rcx, [rcx+10h]
0x18002e3e3  mov     edx, 14h
0x18002e3e8  mov     r8, r15
0x18002e3eb  call    WPP_SF_
0x18002e3f0  mov     rcx, [rbx+10h]
0x18002e3f4  call    cs:__imp_NsiDisconnectFromServer
0x18002e3fa  mov     qword ptr [rbx+10h], 0
0x18002e402  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e409  cmp     rcx, r14
0x18002e40c  jz      short loc_18002E42B
0x18002e40e  test    byte ptr [rcx+1Ch], 4
0x18002e412  jz      short loc_18002E42B
0x18002e414  cmp     byte ptr [rcx+19h], 5
0x18002e418  jb      short loc_18002E42B
0x18002e41a  mov     rcx, [rcx+10h]
0x18002e41e  mov     edx, 15h
0x18002e423  mov     r8, r15
0x18002e426  call    WPP_SF_
0x18002e42b  mov     rbx, [rsp+28h+arg_0]
0x18002e430  mov     r14, [rsp+28h+arg_8]
0x18002e435  add     rsp, 20h
0x18002e439  pop     r15
0x18002e43b  retn
```
