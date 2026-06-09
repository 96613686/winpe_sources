# NsiAddressMonitor::StopMonitor(void)

- ea: `0x18002f318`
- end: `0x18002f484`
- name: `?StopMonitor@NsiAddressMonitor@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(NsiAddressMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f00c`
- `0x1800451a0`

## callees

- `0x180010200`
- `0x18002f318`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18002f43c`
- `WINNSI!NsiDisconnectFromServer` at `0x18002f43c`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f3a7`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f3fa`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f3a7`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f3fa`

## pseudocode

```c
void __fastcall NsiAddressMonitor::StopMonitor(NsiAddressMonitor *this)
{
  __int64 v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_37a3f4b501a3362353453b6f1caed5a7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 18, WPP_37a3f4b501a3362353453b6f1caed5a7_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_IPV4_MODULEID, 10, *((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 4) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 19, WPP_37a3f4b501a3362353453b6f1caed5a7_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_IPV6_MODULEID, 10, *((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 20, WPP_37a3f4b501a3362353453b6f1caed5a7_Traceguids);
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
    WPP_SF_(*(_QWORD *)(v2 + 16), 21, WPP_37a3f4b501a3362353453b6f1caed5a7_Traceguids);
}

```

## disassembly

```asm
0x18002f318  mov     [rsp+arg_0], rbx
0x18002f31d  mov     [rsp+arg_8], r14
0x18002f322  push    r15
0x18002f324  sub     rsp, 20h
0x18002f328  mov     rbx, rcx
0x18002f32b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f332  lea     r14, WPP_GLOBAL_Control
0x18002f339  lea     r15, WPP_37a3f4b501a3362353453b6f1caed5a7_Traceguids
0x18002f340  cmp     rcx, r14
0x18002f343  jz      short loc_18002F369
0x18002f345  test    byte ptr [rcx+1Ch], 4
0x18002f349  jz      short loc_18002F369
0x18002f34b  cmp     byte ptr [rcx+19h], 5
0x18002f34f  jb      short loc_18002F369
0x18002f351  mov     rcx, [rcx+10h]
0x18002f355  mov     edx, 11h
0x18002f35a  mov     r8, r15
0x18002f35d  call    WPP_SF_
0x18002f362  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f369  cmp     qword ptr [rbx+18h], 0
0x18002f36e  jz      short loc_18002F3BC
0x18002f370  cmp     rcx, r14
0x18002f373  jz      short loc_18002F392
0x18002f375  test    byte ptr [rcx+1Ch], 4
0x18002f379  jz      short loc_18002F392
0x18002f37b  cmp     byte ptr [rcx+19h], 5
0x18002f37f  jb      short loc_18002F392
0x18002f381  mov     rcx, [rcx+10h]
0x18002f385  mov     edx, 12h
0x18002f38a  mov     r8, r15
0x18002f38d  call    WPP_SF_
0x18002f392  mov     r9, [rbx+18h]
0x18002f396  lea     rdx, NPI_MS_IPV4_MODULEID
0x18002f39d  mov     rcx, [rbx+10h]
0x18002f3a1  mov     r8d, 0Ah
0x18002f3a7  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002f3ad  mov     qword ptr [rbx+18h], 0
0x18002f3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3bc  cmp     qword ptr [rbx+20h], 0
0x18002f3c1  jz      short loc_18002F40F
0x18002f3c3  cmp     rcx, r14
0x18002f3c6  jz      short loc_18002F3E5
0x18002f3c8  test    byte ptr [rcx+1Ch], 4
0x18002f3cc  jz      short loc_18002F3E5
0x18002f3ce  cmp     byte ptr [rcx+19h], 5
0x18002f3d2  jb      short loc_18002F3E5
0x18002f3d4  mov     rcx, [rcx+10h]
0x18002f3d8  mov     edx, 13h
0x18002f3dd  mov     r8, r15
0x18002f3e0  call    WPP_SF_
0x18002f3e5  mov     r9, [rbx+20h]
0x18002f3e9  lea     rdx, NPI_MS_IPV6_MODULEID
0x18002f3f0  mov     rcx, [rbx+10h]
0x18002f3f4  mov     r8d, 0Ah
0x18002f3fa  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002f400  mov     qword ptr [rbx+20h], 0
0x18002f408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f40f  cmp     qword ptr [rbx+10h], 0
0x18002f414  jz      short loc_18002F451
0x18002f416  cmp     rcx, r14
0x18002f419  jz      short loc_18002F438
0x18002f41b  test    byte ptr [rcx+1Ch], 4
0x18002f41f  jz      short loc_18002F438
0x18002f421  cmp     byte ptr [rcx+19h], 5
0x18002f425  jb      short loc_18002F438
0x18002f427  mov     rcx, [rcx+10h]
0x18002f42b  mov     edx, 14h
0x18002f430  mov     r8, r15
0x18002f433  call    WPP_SF_
0x18002f438  mov     rcx, [rbx+10h]
0x18002f43c  call    cs:__imp_NsiDisconnectFromServer
0x18002f442  mov     qword ptr [rbx+10h], 0
0x18002f44a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f451  cmp     rcx, r14
0x18002f454  jz      short loc_18002F473
0x18002f456  test    byte ptr [rcx+1Ch], 4
0x18002f45a  jz      short loc_18002F473
0x18002f45c  cmp     byte ptr [rcx+19h], 5
0x18002f460  jb      short loc_18002F473
0x18002f462  mov     rcx, [rcx+10h]
0x18002f466  mov     edx, 15h
0x18002f46b  mov     r8, r15
0x18002f46e  call    WPP_SF_
0x18002f473  mov     rbx, [rsp+28h+arg_0]
0x18002f478  mov     r14, [rsp+28h+arg_8]
0x18002f47d  add     rsp, 20h
0x18002f481  pop     r15
0x18002f483  retn
```
