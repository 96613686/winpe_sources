# ClassCheckMediaState

- ea: `0x14000ffd0`
- end: `0x140010031`
- name: `ClassCheckMediaState`
- size: `97`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000fd00`
- `0x140035b14`
- `0x14005f210`

## callees

- `0x14000ffd0`
- `0x140010040`
- `0x14001feac`

## pseudocode

```c
void __stdcall ClassCheckMediaState(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // rdx

  MediaChangeDetectionInfo = FdoExtension->MediaChangeDetectionInfo;
  if ( MediaChangeDetectionInfo )
  {
    ClasspSendMediaStateIrp(
      FdoExtension,
      MediaChangeDetectionInfo,
      (unsigned int)_InterlockedDecrement(&MediaChangeDetectionInfo->MediaChangeCountDown));
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
}

```

## disassembly

```asm
0x14000ffd0  sub     rsp, 28h
0x14000ffd4  mov     rdx, [rcx+288h]
0x14000ffdb  test    rdx, rdx
0x14000ffde  jz      short loc_14000FFF8
0x14000ffe0  or      r8d, 0FFFFFFFFh
0x14000ffe4  lock xadd [rdx+40h], r8d
0x14000ffea  dec     r8d
0x14000ffed  call    ClasspSendMediaStateIrp
0x14000fff2  add     rsp, 28h
0x14000fff6  retn
0x14000fff8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ffff  lea     rax, WPP_GLOBAL_Control
0x140010006  cmp     rcx, rax
0x140010009  jz      short loc_14000FFF2
0x14001000b  test    dword ptr [rcx+2Ch], 1000h
0x140010012  jz      short loc_14000FFF2
0x140010014  cmp     byte ptr [rcx+29h], 4
0x140010018  jb      short loc_14000FFF2
0x14001001a  mov     rcx, [rcx+18h]
0x14001001e  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140010025  mov     edx, 35h ; '5'
0x14001002a  call    WPP_SF_
0x14001002f  jmp     short loc_14000FFF2
```
