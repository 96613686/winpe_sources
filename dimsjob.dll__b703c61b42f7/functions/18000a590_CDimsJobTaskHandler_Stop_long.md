# CDimsJobTaskHandler::Stop(long *)

- ea: `0x18000a590`
- end: `0x18000a5d5`
- name: `?Stop@CDimsJobTaskHandler@@UEAAJPEAJ@Z`
- size: `69`
- prototype: `__int64 __fastcall(CDimsJobTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000a338`
- `0x18000a590`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Stop(CDimsJobTaskHandler *this, int *a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids);
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000a590  push    rbx
0x18000a592  sub     rsp, 20h
0x18000a596  mov     rbx, rdx
0x18000a599  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5a0  lea     rax, WPP_GLOBAL_Control
0x18000a5a7  cmp     rcx, rax
0x18000a5aa  jz      short loc_18000A5C7
0x18000a5ac  test    byte ptr [rcx+1Ch], 10h
0x18000a5b0  jz      short loc_18000A5C7
0x18000a5b2  mov     rcx, [rcx+10h]
0x18000a5b6  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000a5bd  mov     edx, 15h
0x18000a5c2  call    WPP_SF_
0x18000a5c7  mov     dword ptr [rbx], 0
0x18000a5cd  xor     eax, eax
0x18000a5cf  add     rsp, 20h
0x18000a5d3  pop     rbx
0x18000a5d4  retn
```
