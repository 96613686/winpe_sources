# WSTContextByPointerTableDelete(_WST_CONTEXT *)

- ea: `0x18001cecc`
- end: `0x18001cf52`
- name: `?WSTContextByPointerTableDelete@@YAJPEAU_WST_CONTEXT@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(struct _WST_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016db0`

## callees

- `0x180015aa8`
- `0x18001cecc`
- `0x18001cf58`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001cf44`
- `ntdll!RtlLeaveCriticalSection` at `0x18001cf44`
- `ntdll!RtlEnterCriticalSection` at `0x18001cf2d`
- `ntdll!RtlEnterCriticalSection` at `0x18001cf2d`

## pseudocode

```c
__int64 __fastcall WSTContextByPointerTableDelete(struct _WST_CONTEXT *a1)
{
  struct _RTL_GENERIC_TABLE *v2; // rcx
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qDDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(*((_QWORD *)a1 + 3) + 44LL),
      *(_DWORD *)(*((_QWORD *)a1 + 3) + 40LL),
      (__int64)a1 + 168);
  RtlEnterCriticalSection(&WSTGlobalContextByPointerTableLock);
  v3 = WSTContextByTargetTableDeleteExNoLock(v2, a1);
  RtlLeaveCriticalSection(&WSTGlobalContextByPointerTableLock);
  return v3;
}

```

## disassembly

```asm
0x18001cecc  push    rbx
0x18001cece  sub     rsp, 40h
0x18001ced2  mov     rbx, rcx
0x18001ced5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cedc  lea     rax, WPP_GLOBAL_Control
0x18001cee3  cmp     rcx, rax
0x18001cee6  jz      short loc_18001CF26
0x18001cee8  test    byte ptr [rcx+1Ch], 2
0x18001ceec  jz      short loc_18001CF26
0x18001ceee  mov     r8, [rbx+18h]
0x18001cef2  lea     rax, [rbx+0A8h]
0x18001cef9  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cefd  mov     edx, 0Eh
0x18001cf02  mov     [rsp+48h+var_18], rax; __int64
0x18001cf07  mov     r9, rbx
0x18001cf0a  mov     eax, [r8+28h]
0x18001cf0e  mov     dword ptr [rsp+48h+var_20], eax; char
0x18001cf12  mov     eax, [r8+2Ch]
0x18001cf16  lea     r8, WPP_daa775e63f0b32280135cd3ef20378c2_Traceguids
0x18001cf1d  mov     dword ptr [rsp+48h+var_28], eax; char
0x18001cf21  call    WPP_SF_qDDZ
0x18001cf26  lea     rcx, ?WSTGlobalContextByPointerTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001cf2d  call    cs:__imp_RtlEnterCriticalSection
0x18001cf33  mov     rdx, rbx; struct _WST_CONTEXT *
0x18001cf36  call    ?WSTContextByTargetTableDeleteExNoLock@@YAJPEAU_RTL_GENERIC_TABLE@@PEAU_WST_CONTEXT@@@Z; WSTContextByTargetTableDeleteExNoLock(_RTL_GENERIC_TABLE *,_WST_CONTEXT *)
0x18001cf3b  lea     rcx, ?WSTGlobalContextByPointerTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001cf42  mov     ebx, eax
0x18001cf44  call    cs:__imp_RtlLeaveCriticalSection
0x18001cf4a  mov     eax, ebx
0x18001cf4c  add     rsp, 40h
0x18001cf50  pop     rbx
0x18001cf51  retn
```
