# CTaskHandler::FinalRelease(void)

- ea: `0x1800061ec`
- end: `0x18000625b`
- name: `?FinalRelease@CTaskHandler@@QEAAXXZ`
- size: `111`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800021e0`
- `0x1800022e4`

## callees

- `0x1800061ec`
- `0x1800064d4`
- `0x1800067a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180006254`
- `fhsvcctl!FhServiceClosePipe` at `0x180006208`
- `fhsvcctl!FhServiceClosePipe` at `0x180006208`

## pseudocode

```c
void __fastcall CTaskHandler::FinalRelease(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // eax

  CTaskHandler::InterlockedExitMaintenanceMode(this, 1);
  if ( this[1].SpinCount )
  {
    v2 = FhServiceClosePipe();
    if ( v2 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids,
        (unsigned int)v2);
    }
    this[1].SpinCount = 0;
  }
  DeleteCriticalSection(this + 2);
}

```

## disassembly

```asm
0x1800061ec  push    rbx
0x1800061ee  sub     rsp, 20h
0x1800061f2  mov     edx, 1; int
0x1800061f7  mov     rbx, rcx
0x1800061fa  call    ?InterlockedExitMaintenanceMode@CTaskHandler@@AEAAXH@Z; CTaskHandler::InterlockedExitMaintenanceMode(int)
0x1800061ff  mov     rcx, [rbx+48h]
0x180006203  test    rcx, rcx
0x180006206  jz      short loc_18000624B
0x180006208  call    cs:__imp_FhServiceClosePipe
0x18000620e  test    eax, eax
0x180006210  jns     short loc_180006243
0x180006212  mov     rcx, cs:WPP_GLOBAL_Control
0x180006219  lea     rdx, WPP_GLOBAL_Control
0x180006220  cmp     rcx, rdx
0x180006223  jz      short loc_180006243
0x180006225  test    byte ptr [rcx+1Ch], 1
0x180006229  jz      short loc_180006243
0x18000622b  mov     rcx, [rcx+10h]
0x18000622f  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x180006236  mov     edx, 0Ch
0x18000623b  mov     r9d, eax
0x18000623e  call    WPP_SF_d
0x180006243  mov     qword ptr [rbx+48h], 0
0x18000624b  lea     rcx, [rbx+50h]
0x18000624f  add     rsp, 20h
0x180006253  pop     rbx
0x180006254  jmp     cs:__imp_DeleteCriticalSection
```
