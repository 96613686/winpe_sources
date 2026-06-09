# NcaServiceOnShutdownCallback(void *,uchar)

- ea: `0x1800048e0`
- end: `0x18000497e`
- name: `?NcaServiceOnShutdownCallback@@YAXPEAXE@Z`
- size: `158`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800048e0`
- `0x180004984`
- `0x180004f04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000494a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000494a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000495d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000495d`

## pseudocode

```c
void __fastcall NcaServiceOnShutdownCallback(void *a1)
{
  PVOID *v1; // rcx

  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 4) != 0 )
      WPP_SF_(v1[2], 20, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  }
  if ( hObject )
  {
    WaitForSingleObject(hObject, 0xFFFFFFFF);
    CloseHandle(hObject);
    hObject = 0;
  }
  NcaServiceShutdown();
}

```

## disassembly

```asm
0x1800048e0  push    rbx
0x1800048e2  sub     rsp, 20h
0x1800048e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048ed  lea     rbx, WPP_GLOBAL_Control
0x1800048f4  cmp     rcx, rbx
0x1800048f7  jz      short loc_18000493B
0x1800048f9  test    byte ptr [rcx+1Ch], 8
0x1800048fd  jz      short loc_18000491B
0x1800048ff  mov     rcx, [rcx+10h]
0x180004903  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x18000490a  mov     edx, 13h
0x18000490f  call    WPP_SF_
0x180004914  mov     rcx, cs:WPP_GLOBAL_Control
0x18000491b  cmp     rcx, rbx
0x18000491e  jz      short loc_18000493B
0x180004920  test    byte ptr [rcx+1Ch], 4
0x180004924  jz      short loc_18000493B
0x180004926  mov     rcx, [rcx+10h]
0x18000492a  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004931  mov     edx, 14h
0x180004936  call    WPP_SF_
0x18000493b  mov     rcx, cs:hObject; hHandle
0x180004942  test    rcx, rcx
0x180004945  jz      short loc_180004974
0x180004947  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000494a  call    cs:__imp_WaitForSingleObject
0x180004951  nop     dword ptr [rax+rax+00h]
0x180004956  mov     rcx, cs:hObject; hObject
0x18000495d  call    cs:__imp_CloseHandle
0x180004964  nop     dword ptr [rax+rax+00h]
0x180004969  mov     cs:hObject, 0
0x180004974  add     rsp, 20h
0x180004978  pop     rbx
0x180004979  jmp     ?NcaServiceShutdown@@YAXXZ; NcaServiceShutdown(void)
```
