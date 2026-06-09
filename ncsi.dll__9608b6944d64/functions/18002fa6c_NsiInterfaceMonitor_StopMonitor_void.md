# NsiInterfaceMonitor::StopMonitor(void)

- ea: `0x18002fa6c`
- end: `0x18002fb82`
- name: `?StopMonitor@NsiInterfaceMonitor@@QEAAXXZ`
- size: `278`
- prototype: `void __fastcall(NsiInterfaceMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f00c`
- `0x1800451a0`

## callees

- `0x180010200`
- `0x18002fa6c`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18002fb3c`
- `WINNSI!NsiDisconnectFromServer` at `0x18002fb3c`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002faf6`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002faf6`

## pseudocode

```c
void __fastcall NsiInterfaceMonitor::StopMonitor(NsiInterfaceMonitor *this)
{
  __int64 v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 16, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_NDIS_MODULEID, 1, *((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 17, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids);
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
    WPP_SF_(*(_QWORD *)(v2 + 16), 18, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids);
}

```

## disassembly

```asm
0x18002fa6c  mov     [rsp+arg_0], rbx
0x18002fa71  push    rbp
0x18002fa72  sub     rsp, 20h
0x18002fa76  mov     rbx, rcx
0x18002fa79  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa80  lea     rbp, WPP_GLOBAL_Control
0x18002fa87  cmp     rcx, rbp
0x18002fa8a  jz      short loc_18002FAB4
0x18002fa8c  test    byte ptr [rcx+1Ch], 4
0x18002fa90  jz      short loc_18002FAB4
0x18002fa92  cmp     byte ptr [rcx+19h], 5
0x18002fa96  jb      short loc_18002FAB4
0x18002fa98  mov     rcx, [rcx+10h]
0x18002fa9c  lea     r8, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids
0x18002faa3  mov     edx, 0Fh
0x18002faa8  call    WPP_SF_
0x18002faad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fab4  cmp     qword ptr [rbx+18h], 0
0x18002fab9  jz      short loc_18002FB0B
0x18002fabb  cmp     rcx, rbp
0x18002fabe  jz      short loc_18002FAE1
0x18002fac0  test    byte ptr [rcx+1Ch], 4
0x18002fac4  jz      short loc_18002FAE1
0x18002fac6  cmp     byte ptr [rcx+19h], 5
0x18002faca  jb      short loc_18002FAE1
0x18002facc  mov     rcx, [rcx+10h]
0x18002fad0  lea     r8, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids
0x18002fad7  mov     edx, 10h
0x18002fadc  call    WPP_SF_
0x18002fae1  mov     r9, [rbx+18h]
0x18002fae5  lea     rdx, NPI_MS_NDIS_MODULEID
0x18002faec  mov     rcx, [rbx+10h]
0x18002faf0  mov     r8d, 1
0x18002faf6  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002fafc  mov     qword ptr [rbx+18h], 0
0x18002fb04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb0b  cmp     qword ptr [rbx+10h], 0
0x18002fb10  jz      short loc_18002FB51
0x18002fb12  cmp     rcx, rbp
0x18002fb15  jz      short loc_18002FB38
0x18002fb17  test    byte ptr [rcx+1Ch], 4
0x18002fb1b  jz      short loc_18002FB38
0x18002fb1d  cmp     byte ptr [rcx+19h], 5
0x18002fb21  jb      short loc_18002FB38
0x18002fb23  mov     rcx, [rcx+10h]
0x18002fb27  lea     r8, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids
0x18002fb2e  mov     edx, 11h
0x18002fb33  call    WPP_SF_
0x18002fb38  mov     rcx, [rbx+10h]
0x18002fb3c  call    cs:__imp_NsiDisconnectFromServer
0x18002fb42  mov     qword ptr [rbx+10h], 0
0x18002fb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb51  cmp     rcx, rbp
0x18002fb54  jz      short loc_18002FB77
0x18002fb56  test    byte ptr [rcx+1Ch], 4
0x18002fb5a  jz      short loc_18002FB77
0x18002fb5c  cmp     byte ptr [rcx+19h], 5
0x18002fb60  jb      short loc_18002FB77
0x18002fb62  mov     rcx, [rcx+10h]
0x18002fb66  lea     r8, WPP_138f847b5fe0378c56141f64cb80953e_Traceguids
0x18002fb6d  mov     edx, 12h
0x18002fb72  call    WPP_SF_
0x18002fb77  mov     rbx, [rsp+28h+arg_0]
0x18002fb7c  add     rsp, 20h
0x18002fb80  pop     rbp
0x18002fb81  retn
```
