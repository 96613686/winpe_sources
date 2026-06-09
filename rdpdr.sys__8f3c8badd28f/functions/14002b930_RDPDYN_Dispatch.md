# RDPDYN_Dispatch

- ea: `0x14002b930`
- end: `0x14002ba93`
- name: `RDPDYN_Dispatch`
- size: `355`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400254c0`

## callees

- `0x140001f10`
- `0x14000324c`
- `0x14000327c`
- `0x14000472c`
- `0x14000487c`
- `0x14001ad48`
- `0x14001ae20`
- `0x14002b930`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002b9fc`
- `ntoskrnl!IofCompleteRequest` at `0x14002b9fc`

## pseudocode

```c
__int64 __fastcall RDPDYN_Dispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  UCHAR MajorFunction; // al
  unsigned int v5; // edi
  PDEVICE_OBJECT v6; // rcx
  __int64 v8; // rcx
  PDEVICE_OBJECT v10; // rcx
  PDEVICE_OBJECT v11; // rcx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids,
      CurrentStackLocation->MajorFunction);
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction )
  {
    switch ( MajorFunction )
    {
      case 2u:
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
        return RDPDYN_Close(v10, a2);
      case 0xEu:
        v8 = (__int64)a2->Tail.Overlay.CurrentStackLocation;
        if ( *(_DWORD *)(v8 + 24) == 2236420 )
        {
          return (unsigned int)RDPDYN_HandleGetNextDevMgmtEventIOCTL(v8, (__int64)a2);
        }
        else
        {
          if ( *(_DWORD *)(v8 + 24) != 2236428 )
          {
            v5 = -1073741808;
            a2->IoStatus.Information = 0;
            goto LABEL_16;
          }
          return (unsigned int)RDPDYN_HandleClientMsgIOCTL(v8, a2);
        }
      case 0x12u:
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
        return RDPDYN_Cleanup(v6, a2);
      default:
        v5 = -1073741637;
LABEL_16:
        a2->IoStatus.Status = v5;
        IofCompleteRequest(a2, 0);
        return v5;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
    return RDPDYN_Create(v11, a2);
  }
}

```

## disassembly

```asm
0x14002b930  mov     [rsp+arg_0], rbx
0x14002b935  mov     [rsp+arg_8], rbp
0x14002b93a  push    rdi
0x14002b93b  sub     rsp, 20h
0x14002b93f  mov     rdi, [rdx+0B8h]
0x14002b946  mov     rbx, rdx
0x14002b949  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b950  lea     rbp, WPP_GLOBAL_Control
0x14002b957  cmp     rcx, rbp
0x14002b95a  jz      short loc_14002B97B
0x14002b95c  cmp     byte ptr [rcx+29h], 4
0x14002b960  jb      short loc_14002B97B
0x14002b962  movzx   r9d, byte ptr [rdi]
0x14002b966  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14002b96d  mov     rcx, [rcx+18h]
0x14002b971  mov     edx, 0Bh
0x14002b976  call    WPP_SF_d
0x14002b97b  mov     al, [rdi]
0x14002b97d  test    al, al
0x14002b97f  jz      loc_14002BA53
0x14002b985  cmp     al, 2
0x14002b987  jz      loc_14002BA22
0x14002b98d  mov     edx, 0Eh
0x14002b992  cmp     al, dl
0x14002b994  jz      short loc_14002B9D0
0x14002b996  cmp     al, 12h
0x14002b998  jz      short loc_14002B9A1
0x14002b99a  mov     edi, 0C00000BBh
0x14002b99f  jmp     short loc_14002B9F4
0x14002b9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b9a8  cmp     rcx, rbp
0x14002b9ab  jz      short loc_14002B9C3
0x14002b9ad  cmp     byte ptr [rcx+29h], 4
0x14002b9b1  jb      short loc_14002B9C3
0x14002b9b3  mov     rcx, [rcx+18h]
0x14002b9b7  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14002b9be  call    WPP_SF_
0x14002b9c3  mov     rdx, rbx
0x14002b9c6  call    RDPDYN_Cleanup
0x14002b9cb  jmp     loc_14002BA82
0x14002b9d0  mov     rcx, [rbx+0B8h]
0x14002b9d7  mov     edx, [rcx+18h]
0x14002b9da  sub     edx, 222004h
0x14002b9e0  jz      short loc_14002BA14
0x14002b9e2  cmp     edx, 8
0x14002b9e5  jz      short loc_14002BA0A
0x14002b9e7  mov     edi, 0C0000010h
0x14002b9ec  mov     qword ptr [rbx+38h], 0
0x14002b9f4  xor     edx, edx; PriorityBoost
0x14002b9f6  mov     [rbx+30h], edi
0x14002b9f9  mov     rcx, rbx; Irp
0x14002b9fc  call    cs:__imp_IofCompleteRequest
0x14002ba03  nop     dword ptr [rax+rax+00h]
0x14002ba08  jmp     short loc_14002BA1E
0x14002ba0a  mov     rdx, rbx
0x14002ba0d  call    RDPDYN_HandleClientMsgIOCTL
0x14002ba12  jmp     short loc_14002BA1C
0x14002ba14  mov     rdx, rbx
0x14002ba17  call    RDPDYN_HandleGetNextDevMgmtEventIOCTL
0x14002ba1c  mov     edi, eax
0x14002ba1e  mov     eax, edi
0x14002ba20  jmp     short loc_14002BA82
0x14002ba22  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba29  cmp     rcx, rbp
0x14002ba2c  jz      short loc_14002BA49
0x14002ba2e  cmp     byte ptr [rcx+29h], 4
0x14002ba32  jb      short loc_14002BA49
0x14002ba34  mov     rcx, [rcx+18h]
0x14002ba38  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14002ba3f  mov     edx, 0Dh
0x14002ba44  call    WPP_SF_
0x14002ba49  mov     rdx, rbx
0x14002ba4c  call    RDPDYN_Close
0x14002ba51  jmp     short loc_14002BA82
0x14002ba53  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba5a  cmp     rcx, rbp
0x14002ba5d  jz      short loc_14002BA7A
0x14002ba5f  cmp     byte ptr [rcx+29h], 4
0x14002ba63  jb      short loc_14002BA7A
0x14002ba65  mov     rcx, [rcx+18h]
0x14002ba69  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14002ba70  mov     edx, 0Ch
0x14002ba75  call    WPP_SF_
0x14002ba7a  mov     rdx, rbx
0x14002ba7d  call    RDPDYN_Create
0x14002ba82  mov     rbx, [rsp+28h+arg_0]
0x14002ba87  mov     rbp, [rsp+28h+arg_8]
0x14002ba8c  add     rsp, 20h
0x14002ba90  pop     rdi
0x14002ba91  retn
```
