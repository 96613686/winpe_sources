# NsiTcpRetransmitMonitor::StopMonitor(void)

- ea: `0x18002fb88`
- end: `0x18002fc9e`
- name: `?StopMonitor@NsiTcpRetransmitMonitor@@QEAAXXZ`
- size: `278`
- prototype: `void __fastcall(NsiTcpRetransmitMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f00c`
- `0x1800451a0`

## callees

- `0x180010200`
- `0x18002fb88`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18002fc58`
- `WINNSI!NsiDisconnectFromServer` at `0x18002fc58`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002fc12`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002fc12`

## pseudocode

```c
void __fastcall NsiTcpRetransmitMonitor::StopMonitor(NsiTcpRetransmitMonitor *this)
{
  __int64 v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, &WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 16, &WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), NPI_MS_TCP_MODULEID, 32, *((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 17, &WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids);
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
    WPP_SF_(*(_QWORD *)(v2 + 16), 18, &WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids);
}

```

## disassembly

```asm
0x18002fb88  mov     [rsp+arg_0], rbx
0x18002fb8d  push    rbp
0x18002fb8e  sub     rsp, 20h
0x18002fb92  mov     rbx, rcx
0x18002fb95  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb9c  lea     rbp, WPP_GLOBAL_Control
0x18002fba3  cmp     rcx, rbp
0x18002fba6  jz      short loc_18002FBD0
0x18002fba8  test    byte ptr [rcx+1Ch], 4
0x18002fbac  jz      short loc_18002FBD0
0x18002fbae  cmp     byte ptr [rcx+19h], 5
0x18002fbb2  jb      short loc_18002FBD0
0x18002fbb4  mov     rcx, [rcx+10h]
0x18002fbb8  lea     r8, WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids
0x18002fbbf  mov     edx, 0Fh
0x18002fbc4  call    WPP_SF_
0x18002fbc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbd0  cmp     qword ptr [rbx+18h], 0
0x18002fbd5  jz      short loc_18002FC27
0x18002fbd7  cmp     rcx, rbp
0x18002fbda  jz      short loc_18002FBFD
0x18002fbdc  test    byte ptr [rcx+1Ch], 4
0x18002fbe0  jz      short loc_18002FBFD
0x18002fbe2  cmp     byte ptr [rcx+19h], 5
0x18002fbe6  jb      short loc_18002FBFD
0x18002fbe8  mov     rcx, [rcx+10h]
0x18002fbec  lea     r8, WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids
0x18002fbf3  mov     edx, 10h
0x18002fbf8  call    WPP_SF_
0x18002fbfd  mov     r9, [rbx+18h]
0x18002fc01  lea     rdx, NPI_MS_TCP_MODULEID
0x18002fc08  mov     rcx, [rbx+10h]
0x18002fc0c  mov     r8d, 20h ; ' '
0x18002fc12  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002fc18  mov     qword ptr [rbx+18h], 0
0x18002fc20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc27  cmp     qword ptr [rbx+10h], 0
0x18002fc2c  jz      short loc_18002FC6D
0x18002fc2e  cmp     rcx, rbp
0x18002fc31  jz      short loc_18002FC54
0x18002fc33  test    byte ptr [rcx+1Ch], 4
0x18002fc37  jz      short loc_18002FC54
0x18002fc39  cmp     byte ptr [rcx+19h], 5
0x18002fc3d  jb      short loc_18002FC54
0x18002fc3f  mov     rcx, [rcx+10h]
0x18002fc43  lea     r8, WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids
0x18002fc4a  mov     edx, 11h
0x18002fc4f  call    WPP_SF_
0x18002fc54  mov     rcx, [rbx+10h]
0x18002fc58  call    cs:__imp_NsiDisconnectFromServer
0x18002fc5e  mov     qword ptr [rbx+10h], 0
0x18002fc66  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc6d  cmp     rcx, rbp
0x18002fc70  jz      short loc_18002FC93
0x18002fc72  test    byte ptr [rcx+1Ch], 4
0x18002fc76  jz      short loc_18002FC93
0x18002fc78  cmp     byte ptr [rcx+19h], 5
0x18002fc7c  jb      short loc_18002FC93
0x18002fc7e  mov     rcx, [rcx+10h]
0x18002fc82  lea     r8, WPP_efad94ca4a753ed5a1a128fbe2c67d14_Traceguids
0x18002fc89  mov     edx, 12h
0x18002fc8e  call    WPP_SF_
0x18002fc93  mov     rbx, [rsp+28h+arg_0]
0x18002fc98  add     rsp, 20h
0x18002fc9c  pop     rbp
0x18002fc9d  retn
```
