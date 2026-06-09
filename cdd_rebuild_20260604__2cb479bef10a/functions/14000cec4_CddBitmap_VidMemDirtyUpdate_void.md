# CddBitmap::VidMemDirtyUpdate(void)

- ea: `0x14000cec4`
- end: `0x14000cf77`
- name: `?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(CddBitmap *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000a254`
- `0x14000d63c`
- `0x140019458`
- `0x1400200e8`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x140033548`

## callees

- `0x14000cec4`
- `0x140010670`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000cef5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cef5`
- `ntoskrnl!KeSetEvent` at `0x14000cf19`
- `ntoskrnl!KeSetEvent` at `0x14000cf19`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000cf42`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000cf42`
- `watchdog!WdLogSingleEntry0` at `0x14000cf2c`
- `watchdog!WdLogSingleEntry0` at `0x14000cf2c`

## pseudocode

```c
void __fastcall CddBitmap::VidMemDirtyUpdate(CddBitmap *this)
{
  PRKEVENT *v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax

  *((_DWORD *)this + 32) |= 8u;
  if ( *(_BYTE *)(*((_QWORD *)this + 1) + 2752LL) )
  {
    *(_BYTE *)(*((_QWORD *)this + 1) + 2752LL) = 0;
    v1 = (PRKEVENT *)*((_QWORD *)this + 1);
    if ( KeGetCurrentIrql() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 759;
      v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
      v4[3] = gCddImageInfo;
      v4[4] = (unsigned int)dword_14003E570;
      v4[5] = 215857758;
      WdLogGlobalForLineNumber = 759;
    }
    GetConnectedStandbyProcessName((struct CDDPDEV *)v1);
    KeSetEvent(v1[327], 0, 0);
  }
}

```

## disassembly

```asm
0x14000cec4  push    rbx
0x14000cec6  sub     rsp, 20h
0x14000ceca  or      dword ptr [rcx+80h], 8
0x14000ced1  mov     rax, [rcx+8]
0x14000ced5  mov     dl, [rax+0AC0h]
0x14000cedb  test    dl, dl
0x14000cedd  jnz     short loc_14000CEE6
0x14000cedf  add     rsp, 20h
0x14000cee3  pop     rbx
0x14000cee4  retn
0x14000cee6  mov     rax, [rcx+8]
0x14000ceea  mov     byte ptr [rax+0AC0h], 0
0x14000cef1  mov     rbx, [rcx+8]
0x14000cef5  call    cs:__imp_KeGetCurrentIrql
0x14000cefc  nop     dword ptr [rax+rax+00h]
0x14000cf01  test    al, al
0x14000cf03  jnz     short loc_14000CF27
0x14000cf05  mov     rcx, rbx; struct CDDPDEV *
0x14000cf08  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x14000cf0d  mov     rcx, [rbx+0A38h]; Event
0x14000cf14  xor     r8d, r8d; Wait
0x14000cf17  xor     edx, edx; Increment
0x14000cf19  call    cs:__imp_KeSetEvent
0x14000cf20  nop     dword ptr [rax+rax+00h]
0x14000cf25  jmp     short loc_14000CEDF
0x14000cf27  mov     ecx, 1
0x14000cf2c  call    cs:__imp_WdLogSingleEntry0
0x14000cf33  nop     dword ptr [rax+rax+00h]
0x14000cf38  mov     cs:WdLogGlobalForLineNumber, 2F7h
0x14000cf42  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000cf49  nop     dword ptr [rax+rax+00h]
0x14000cf4e  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000cf55  mov     [rax+18h], rdx
0x14000cf59  mov     edx, cs:dword_14003E570
0x14000cf5f  mov     [rax+20h], rdx
0x14000cf63  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000cf6b  mov     cs:WdLogGlobalForLineNumber, 2F7h
0x14000cf75  jmp     short loc_14000CF05
```
