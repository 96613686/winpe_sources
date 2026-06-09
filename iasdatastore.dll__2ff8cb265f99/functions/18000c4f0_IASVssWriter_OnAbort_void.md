# IASVssWriter::OnAbort(void)

- ea: `0x18000c4f0`
- end: `0x18000c563`
- name: `?OnAbort@IASVssWriter@@UEAA_NXZ`
- size: `115`
- prototype: `bool __fastcall(IASVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007150`
- `0x18000c4f0`
- `0x18000d990`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000c555`
- `KERNEL32!LeaveCriticalSection` at `0x18000c555`

## pseudocode

```c
char __fastcall IASVssWriter::OnAbort(IASVssWriter *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("OnAbort Event Raised");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids, "NPSDS");
  }
  if ( _InterlockedExchange((volatile __int32 *)this + 16, 0) == 1 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return 1;
}

```

## disassembly

```asm
0x18000c4f0  push    rbx
0x18000c4f2  sub     rsp, 20h
0x18000c4f6  mov     rbx, rcx
0x18000c4f9  mov     rax, cs:WPP_GLOBAL_Control
0x18000c500  lea     rcx, WPP_GLOBAL_Control
0x18000c507  cmp     rax, rcx
0x18000c50a  jz      short loc_18000C547
0x18000c50c  cmp     byte ptr [rax+19h], 4
0x18000c510  jb      short loc_18000C547
0x18000c512  test    byte ptr [rax+1Ch], 10h
0x18000c516  jz      short loc_18000C547
0x18000c518  lea     rcx, aOnabortEventRa; "OnAbort Event Raised"
0x18000c51f  call    WppDbgPrint
0x18000c524  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c52b  lea     r9, aNpsds; "NPSDS"
0x18000c532  mov     edx, 0Eh
0x18000c537  lea     r8, WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids
0x18000c53e  mov     rcx, [rcx+10h]
0x18000c542  call    WPP_SF_s
0x18000c547  xor     ecx, ecx
0x18000c549  xchg    ecx, [rbx+40h]
0x18000c54c  cmp     ecx, 1
0x18000c54f  jnz     short loc_18000C55B
0x18000c551  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000c555  call    cs:__imp_LeaveCriticalSection
0x18000c55b  mov     al, 1
0x18000c55d  add     rsp, 20h
0x18000c561  pop     rbx
0x18000c562  retn
```
