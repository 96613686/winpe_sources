# IASVssWriter::OnThaw(void)

- ea: `0x18000c9c0`
- end: `0x18000ca2e`
- name: `?OnThaw@IASVssWriter@@UEAA_NXZ`
- size: `110`
- prototype: `bool __fastcall(IASVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007150`
- `0x18000c9c0`
- `0x18000d990`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ca20`
- `KERNEL32!LeaveCriticalSection` at `0x18000ca20`

## pseudocode

```c
char __fastcall IASVssWriter::OnThaw(IASVssWriter *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("OnThaw Event Raised");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids, "NPSDS");
  }
  _InterlockedExchange((volatile __int32 *)this + 16, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return 1;
}

```

## disassembly

```asm
0x18000c9c0  push    rbx
0x18000c9c2  sub     rsp, 20h
0x18000c9c6  mov     rbx, rcx
0x18000c9c9  mov     rax, cs:WPP_GLOBAL_Control
0x18000c9d0  lea     rcx, WPP_GLOBAL_Control
0x18000c9d7  cmp     rax, rcx
0x18000c9da  jz      short loc_18000CA17
0x18000c9dc  cmp     byte ptr [rax+19h], 4
0x18000c9e0  jb      short loc_18000CA17
0x18000c9e2  test    byte ptr [rax+1Ch], 10h
0x18000c9e6  jz      short loc_18000CA17
0x18000c9e8  lea     rcx, aOnthawEventRai; "OnThaw Event Raised"
0x18000c9ef  call    WppDbgPrint
0x18000c9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9fb  lea     r9, aNpsds; "NPSDS"
0x18000ca02  mov     edx, 10h
0x18000ca07  lea     r8, WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids
0x18000ca0e  mov     rcx, [rcx+10h]
0x18000ca12  call    WPP_SF_s
0x18000ca17  xor     eax, eax
0x18000ca19  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000ca1d  xchg    eax, [rbx+40h]
0x18000ca20  call    cs:__imp_LeaveCriticalSection
0x18000ca26  mov     al, 1
0x18000ca28  add     rsp, 20h
0x18000ca2c  pop     rbx
0x18000ca2d  retn
```
