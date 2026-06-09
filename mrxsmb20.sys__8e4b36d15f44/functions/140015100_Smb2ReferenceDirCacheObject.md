# Smb2ReferenceDirCacheObject

- ea: `0x140015100`
- end: `0x140015199`
- name: `Smb2ReferenceDirCacheObject`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b30`
- `0x140005820`
- `0x140014a00`
- `0x140014db0`

## callees

- `0x140015100`
- `0x14002d630`

## import_xrefs

- `rdbss!RxDiagnosticTrace` at `0x140015152`
- `rdbss!RxDiagnosticTrace` at `0x140015152`

## pseudocode

```c
__int64 __fastcall Smb2ReferenceDirCacheObject(__int64 a1)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 36));
  if ( v2 <= 1 )
    __int2c();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids, a1, v2 - 1, v2);
  }
  return RxDiagnosticTrace(*(_QWORD *)(a1 + 8), 8, "Ref %d --> %d", v2 - 1);
}

```

## disassembly

```asm
0x140015100  mov     [rsp+arg_0], rbx
0x140015105  push    rdi
0x140015106  sub     rsp, 30h
0x14001510a  mov     rdi, rcx
0x14001510d  mov     ebx, 1
0x140015112  lock xadd [rcx+24h], ebx
0x140015117  inc     ebx
0x140015119  cmp     ebx, 1
0x14001511c  jbe     short loc_14001516A
0x14001511e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015125  lea     rax, WPP_GLOBAL_Control
0x14001512c  cmp     rcx, rax
0x14001512f  jz      short loc_14001513A
0x140015131  test    dword ptr [rcx+2Ch], 100h
0x140015138  jnz     short loc_14001516E
0x14001513a  mov     rcx, [rdi+8]
0x14001513e  lea     r9d, [rbx-1]
0x140015142  lea     r8, aRefDD; "Ref %d --> %d"
0x140015149  mov     [rsp+38h+var_18], ebx
0x14001514d  mov     edx, 8
0x140015152  call    cs:__imp_RxDiagnosticTrace
0x140015159  nop     dword ptr [rax+rax+00h]
0x14001515e  mov     rbx, [rsp+38h+arg_0]
0x140015163  add     rsp, 30h
0x140015167  pop     rdi
0x140015168  retn
0x14001516a  int     2Ch; Windows NT - assertion failure
0x14001516c  jmp     short loc_14001511E
0x14001516e  cmp     byte ptr [rcx+29h], 4
0x140015172  jb      short loc_14001513A
0x140015174  mov     rcx, [rcx+18h]
0x140015178  lea     eax, [rbx-1]
0x14001517b  mov     edx, 0Bh
0x140015180  mov     [rsp+38h+var_10], ebx
0x140015184  mov     r9, rdi
0x140015187  mov     [rsp+38h+var_18], eax
0x14001518b  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140015192  call    WPP_SF_qdd
0x140015197  jmp     short loc_14001513A
```
