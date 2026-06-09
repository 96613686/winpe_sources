# _CWorkerThread::ReportVolumeUnavailability_::_1_::catch$3

- ea: `0x18001261c`
- end: `0x18001266d`
- name: `_CWorkerThread::ReportVolumeUnavailability_::_1_::catch$3`
- size: `81`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ca14`
- `0x18001261c`

## pseudocode

```c
__int64 __fastcall CWorkerThread::ReportVolumeUnavailability_::_1_::catch_3(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
      *(unsigned int *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18001261c  mov     [rsp+arg_8], rdx
0x180012621  push    rbp
0x180012622  sub     rsp, 20h
0x180012626  mov     rbp, rdx
0x180012629  lea     rax, WPP_GLOBAL_Control
0x180012630  mov     rcx, cs:WPP_GLOBAL_Control
0x180012637  cmp     rcx, rax
0x18001263a  jz      short loc_18001265C
0x18001263c  test    byte ptr [rcx+1Ch], 1
0x180012640  jz      short loc_18001265C
0x180012642  mov     edx, 2Fh ; '/'
0x180012647  mov     r9d, [rbp+20h]
0x18001264b  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180012652  mov     rcx, [rcx+10h]
0x180012656  call    WPP_SF_d
0x18001265b  nop
0x18001265c  mov     rax, 0
0x180012666  add     rsp, 20h
0x18001266a  pop     rbp
0x18001266b  retn
```
