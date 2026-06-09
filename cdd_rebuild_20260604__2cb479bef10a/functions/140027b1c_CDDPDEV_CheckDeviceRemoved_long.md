# CDDPDEV::CheckDeviceRemoved(long)

- ea: `0x140027b1c`
- end: `0x140027bc6`
- name: `?CheckDeviceRemoved@CDDPDEV@@QEAAXJ@Z`
- size: `170`
- prototype: `void __fastcall(CDDPDEV *__hidden this, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e35c`
- `0x140011510`
- `0x14001b448`
- `0x14001f778`
- `0x140021d5c`
- `0x140030dc0`

## callees

- `0x140027b1c`
- `0x14002c038`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x140027b61`
- `watchdog!WdLogSingleEntry2` at `0x140027b61`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140027b77`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140027b77`

## pseudocode

```c
void __fastcall CDDPDEV::CheckDeviceRemoved(CDDPDEV *this, int a2)
{
  _QWORD *v3; // rax

  if ( a2 == -1073741130 || a2 == -1071775232 )
  {
    *((_DWORD *)this + 686) |= 0x400u;
    if ( a2 == -1071775232 && (*((_DWORD *)this + 686) & 0x200) == 0 )
    {
      WdLogSingleEntry2(4, this, *((unsigned int *)this + 196));
      WdLogGlobalForLineNumber = 2068;
      v3 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v3[3] = gCddImageInfo;
      v3[4] = (unsigned int)dword_14003E570;
      v3[5] = 215857758;
      WdLogGlobalForLineNumber = 2068;
      *((_DWORD *)this + 686) |= 0x200u;
      TriggerGdiModeReset(this, 51);
    }
  }
}

```

## disassembly

```asm
0x140027b1c  push    rbx
0x140027b1e  sub     rsp, 20h
0x140027b22  mov     rbx, rcx
0x140027b25  mov     ecx, 0C01E0200h
0x140027b2a  cmp     edx, 0C00002B6h
0x140027b30  jz      short loc_140027B3A
0x140027b32  cmp     edx, ecx
0x140027b34  jnz     loc_140027BBF
0x140027b3a  bts     dword ptr [rbx+0AB8h], 0Ah
0x140027b42  mov     eax, [rbx+0AB8h]
0x140027b48  cmp     edx, ecx
0x140027b4a  jnz     short loc_140027BBF
0x140027b4c  bt      eax, 9
0x140027b50  jb      short loc_140027BBF
0x140027b52  mov     r8d, [rbx+310h]
0x140027b59  mov     rdx, rbx
0x140027b5c  mov     ecx, 4
0x140027b61  call    cs:__imp_WdLogSingleEntry2
0x140027b68  nop     dword ptr [rax+rax+00h]
0x140027b6d  mov     cs:WdLogGlobalForLineNumber, 814h
0x140027b77  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140027b7e  nop     dword ptr [rax+rax+00h]
0x140027b83  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140027b8a  mov     edx, 33h ; '3'
0x140027b8f  mov     [rax+18h], rcx
0x140027b93  mov     ecx, cs:dword_14003E570
0x140027b99  mov     [rax+20h], rcx
0x140027b9d  mov     rcx, rbx
0x140027ba0  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140027ba8  mov     cs:WdLogGlobalForLineNumber, 814h
0x140027bb2  bts     dword ptr [rbx+0AB8h], 9
0x140027bba  call    ?TriggerGdiModeReset@@YAXPEAUCDDPDEV@@W4_DXGK_DIAG_CODE_POINT_TYPE@@@Z; TriggerGdiModeReset(CDDPDEV *,_DXGK_DIAG_CODE_POINT_TYPE)
0x140027bbf  add     rsp, 20h
0x140027bc3  pop     rbx
0x140027bc4  retn
```
