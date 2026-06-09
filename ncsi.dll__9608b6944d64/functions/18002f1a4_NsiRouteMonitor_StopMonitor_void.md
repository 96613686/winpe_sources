# NsiRouteMonitor::StopMonitor(void)

- ea: `0x18002f1a4`
- end: `0x18002f310`
- name: `?StopMonitor@NsiRouteMonitor@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(NsiRouteMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f00c`
- `0x1800451a0`

## callees

- `0x180010200`
- `0x18002f1a4`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18002f2c8`
- `WINNSI!NsiDisconnectFromServer` at `0x18002f2c8`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f233`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f286`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f233`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18002f286`

## pseudocode

```c
void __fastcall NsiRouteMonitor::StopMonitor(NsiRouteMonitor *this)
{
  __int64 v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_92d2190571663d1d4ac29dda00bb35dd_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 18, WPP_92d2190571663d1d4ac29dda00bb35dd_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_IPV4_MODULEID, 16, *((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 4) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 19, WPP_92d2190571663d1d4ac29dda00bb35dd_Traceguids);
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 2), &NPI_MS_IPV6_MODULEID, 16, *((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) )
  {
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v2 + 16), 20, WPP_92d2190571663d1d4ac29dda00bb35dd_Traceguids);
    NsiDisconnectFromServer(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 4) != 0 && *(_BYTE *)(v2 + 25) >= 5u )
    WPP_SF_(*(_QWORD *)(v2 + 16), 21, WPP_92d2190571663d1d4ac29dda00bb35dd_Traceguids);
}

```

## disassembly

```asm
0x18002f1a4  mov     [rsp+arg_0], rbx
0x18002f1a9  mov     [rsp+arg_8], r14
0x18002f1ae  push    r15
0x18002f1b0  sub     rsp, 20h
0x18002f1b4  mov     rbx, rcx
0x18002f1b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1be  lea     r14, WPP_GLOBAL_Control
0x18002f1c5  lea     r15, WPP_92d2190571663d1d4ac29dda00bb35dd_Traceguids
0x18002f1cc  cmp     rcx, r14
0x18002f1cf  jz      short loc_18002F1F5
0x18002f1d1  test    byte ptr [rcx+1Ch], 4
0x18002f1d5  jz      short loc_18002F1F5
0x18002f1d7  cmp     byte ptr [rcx+19h], 5
0x18002f1db  jb      short loc_18002F1F5
0x18002f1dd  mov     rcx, [rcx+10h]
0x18002f1e1  mov     edx, 11h
0x18002f1e6  mov     r8, r15
0x18002f1e9  call    WPP_SF_
0x18002f1ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1f5  cmp     qword ptr [rbx+18h], 0
0x18002f1fa  jz      short loc_18002F248
0x18002f1fc  cmp     rcx, r14
0x18002f1ff  jz      short loc_18002F21E
0x18002f201  test    byte ptr [rcx+1Ch], 4
0x18002f205  jz      short loc_18002F21E
0x18002f207  cmp     byte ptr [rcx+19h], 5
0x18002f20b  jb      short loc_18002F21E
0x18002f20d  mov     rcx, [rcx+10h]
0x18002f211  mov     edx, 12h
0x18002f216  mov     r8, r15
0x18002f219  call    WPP_SF_
0x18002f21e  mov     r9, [rbx+18h]
0x18002f222  lea     rdx, NPI_MS_IPV4_MODULEID
0x18002f229  mov     rcx, [rbx+10h]
0x18002f22d  mov     r8d, 10h
0x18002f233  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002f239  mov     qword ptr [rbx+18h], 0
0x18002f241  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f248  cmp     qword ptr [rbx+20h], 0
0x18002f24d  jz      short loc_18002F29B
0x18002f24f  cmp     rcx, r14
0x18002f252  jz      short loc_18002F271
0x18002f254  test    byte ptr [rcx+1Ch], 4
0x18002f258  jz      short loc_18002F271
0x18002f25a  cmp     byte ptr [rcx+19h], 5
0x18002f25e  jb      short loc_18002F271
0x18002f260  mov     rcx, [rcx+10h]
0x18002f264  mov     edx, 13h
0x18002f269  mov     r8, r15
0x18002f26c  call    WPP_SF_
0x18002f271  mov     r9, [rbx+20h]
0x18002f275  lea     rdx, NPI_MS_IPV6_MODULEID
0x18002f27c  mov     rcx, [rbx+10h]
0x18002f280  mov     r8d, 10h
0x18002f286  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18002f28c  mov     qword ptr [rbx+20h], 0
0x18002f294  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f29b  cmp     qword ptr [rbx+10h], 0
0x18002f2a0  jz      short loc_18002F2DD
0x18002f2a2  cmp     rcx, r14
0x18002f2a5  jz      short loc_18002F2C4
0x18002f2a7  test    byte ptr [rcx+1Ch], 4
0x18002f2ab  jz      short loc_18002F2C4
0x18002f2ad  cmp     byte ptr [rcx+19h], 5
0x18002f2b1  jb      short loc_18002F2C4
0x18002f2b3  mov     rcx, [rcx+10h]
0x18002f2b7  mov     edx, 14h
0x18002f2bc  mov     r8, r15
0x18002f2bf  call    WPP_SF_
0x18002f2c4  mov     rcx, [rbx+10h]
0x18002f2c8  call    cs:__imp_NsiDisconnectFromServer
0x18002f2ce  mov     qword ptr [rbx+10h], 0
0x18002f2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2dd  cmp     rcx, r14
0x18002f2e0  jz      short loc_18002F2FF
0x18002f2e2  test    byte ptr [rcx+1Ch], 4
0x18002f2e6  jz      short loc_18002F2FF
0x18002f2e8  cmp     byte ptr [rcx+19h], 5
0x18002f2ec  jb      short loc_18002F2FF
0x18002f2ee  mov     rcx, [rcx+10h]
0x18002f2f2  mov     edx, 15h
0x18002f2f7  mov     r8, r15
0x18002f2fa  call    WPP_SF_
0x18002f2ff  mov     rbx, [rsp+28h+arg_0]
0x18002f304  mov     r14, [rsp+28h+arg_8]
0x18002f309  add     rsp, 20h
0x18002f30d  pop     r15
0x18002f30f  retn
```
