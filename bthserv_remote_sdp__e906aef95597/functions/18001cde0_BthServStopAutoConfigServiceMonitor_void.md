# BthServStopAutoConfigServiceMonitor(void)

- ea: `0x18001cde0`
- end: `0x18001cf09`
- name: `?BthServStopAutoConfigServiceMonitor@@YAXXZ`
- size: `297`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000b6d8`
- `0x18000bce8`
- `0x18001d1a8`

## callees

- `0x180012004`
- `0x18001cde0`
- `0x18001cf10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce9b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ce74`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ce74`

## pseudocode

```c
void BthServStopAutoConfigServiceMonitor(void)
{
  _BYTE *v0; // rcx
  char v1; // bl
  bool v2; // dl
  HLOCAL v3; // rax
  SC_HANDLE v4; // rcx

  v0 = WPP_GLOBAL_Control;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v0 = WPP_GLOBAL_Control;
  }
  v3 = pInterfaceGuid;
  if ( pInterfaceGuid )
  {
    if ( *((_QWORD *)pInterfaceGuid + 12) )
    {
      v4 = (SC_HANDLE)*((_QWORD *)pInterfaceGuid + 13);
      if ( v4 )
      {
        CloseServiceHandle(v4);
        *((_QWORD *)pInterfaceGuid + 13) = 0;
      }
      CloseWlanApi();
      v3 = pInterfaceGuid;
    }
    LocalFree(v3);
    pInterfaceGuid = 0;
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 == (_BYTE *)&WPP_GLOBAL_Control || v0[25] < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v0 + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v0 + 5));
}

```

## disassembly

```asm
0x18001cde0  mov     [rsp+arg_0], rbx
0x18001cde5  mov     [rsp+arg_8], rbp
0x18001cdea  mov     [rsp+arg_10], rsi
0x18001cdef  push    r14
0x18001cdf1  sub     rsp, 50h
0x18001cdf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdfc  lea     rsi, WPP_GLOBAL_Control
0x18001ce03  mov     bl, 1
0x18001ce05  cmp     rcx, rsi
0x18001ce08  jz      short loc_18001CE14
0x18001ce0a  cmp     byte ptr [rcx+19h], 4
0x18001ce0e  jb      short loc_18001CE14
0x18001ce10  mov     dl, bl
0x18001ce12  jmp     short loc_18001CE16
0x18001ce14  xor     dl, dl
0x18001ce16  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001ce1d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001ce24  lea     r14, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001ce2b  setnz   r8b
0x18001ce2f  test    dl, dl
0x18001ce31  jnz     short loc_18001CE38
0x18001ce33  test    r8b, r8b
0x18001ce36  jz      short loc_18001CE58
0x18001ce38  mov     r9, [rcx+28h]
0x18001ce3c  mov     rcx, [rcx+10h]
0x18001ce40  mov     [rsp+58h+var_20], r14
0x18001ce45  mov     [rsp+58h+var_28], 38h ; '8'
0x18001ce4c  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ce51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce58  mov     rax, cs:pInterfaceGuid
0x18001ce5f  test    rax, rax
0x18001ce62  jz      short loc_18001CEB6
0x18001ce64  cmp     qword ptr [rax+60h], 0
0x18001ce69  jz      short loc_18001CE98
0x18001ce6b  mov     rcx, [rax+68h]; hSCObject
0x18001ce6f  test    rcx, rcx
0x18001ce72  jz      short loc_18001CE8C
0x18001ce74  call    cs:__imp_CloseServiceHandle
0x18001ce7b  nop     dword ptr [rax+rax+00h]
0x18001ce80  mov     rax, cs:pInterfaceGuid
0x18001ce87  and     qword ptr [rax+68h], 0
0x18001ce8c  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001ce91  mov     rax, cs:pInterfaceGuid
0x18001ce98  mov     rcx, rax; hMem
0x18001ce9b  call    cs:__imp_LocalFree
0x18001cea2  nop     dword ptr [rax+rax+00h]
0x18001cea7  and     cs:pInterfaceGuid, 0
0x18001ceaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ceb6  cmp     rcx, rsi
0x18001ceb9  jz      short loc_18001CEC1
0x18001cebb  cmp     byte ptr [rcx+19h], 4
0x18001cebf  jnb     short loc_18001CEC3
0x18001cec1  xor     bl, bl
0x18001cec3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001ceca  setnz   r8b
0x18001cece  test    bl, bl
0x18001ced0  jnz     short loc_18001CED7
0x18001ced2  test    r8b, r8b
0x18001ced5  jz      short loc_18001CEF2
0x18001ced7  mov     r9, [rcx+28h]
0x18001cedb  mov     dl, bl
0x18001cedd  mov     rcx, [rcx+10h]
0x18001cee1  mov     [rsp+58h+var_20], r14
0x18001cee6  mov     [rsp+58h+var_28], 39h ; '9'
0x18001ceed  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001cef2  mov     rbx, [rsp+58h+arg_0]
0x18001cef7  mov     rbp, [rsp+58h+arg_8]
0x18001cefc  mov     rsi, [rsp+58h+arg_10]
0x18001cf01  add     rsp, 50h
0x18001cf05  pop     r14
0x18001cf07  retn
```
