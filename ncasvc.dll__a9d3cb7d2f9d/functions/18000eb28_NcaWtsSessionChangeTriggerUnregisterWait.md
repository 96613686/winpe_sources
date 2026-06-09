# NcaWtsSessionChangeTriggerUnregisterWait

- ea: `0x18000eb28`
- end: `0x18000ebe9`
- name: `NcaWtsSessionChangeTriggerUnregisterWait`
- size: `193`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e984`
- `0x180011bc0`
- `0x180013990`
- `0x180015900`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18000b3a8`
- `0x18000eb28`

## pseudocode

```c
__int64 __fastcall NcaWtsSessionChangeTriggerUnregisterWait(struct _LIST_ENTRY *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = 0;
    a1[2].Blink = 0;
    NcaSrcLnkdTriggerUnregisterWait(&stru_180028E18, a1);
    goto LABEL_9;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    WPP_SF_d(v2[2], 26, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids, 87);
LABEL_9:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(v2[2], 27, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x18000eb28  mov     [rsp+arg_0], rbx
0x18000eb2d  mov     [rsp+arg_8], rsi
0x18000eb32  push    rdi
0x18000eb33  sub     rsp, 20h
0x18000eb37  mov     rdi, rcx
0x18000eb3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb41  lea     rsi, WPP_GLOBAL_Control
0x18000eb48  cmp     rcx, rsi
0x18000eb4b  jz      short loc_18000EB6F
0x18000eb4d  test    byte ptr [rcx+1Ch], 8
0x18000eb51  jz      short loc_18000EB6F
0x18000eb53  mov     rcx, [rcx+10h]
0x18000eb57  lea     r8, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids
0x18000eb5e  mov     edx, 19h
0x18000eb63  call    WPP_SF_
0x18000eb68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb6f  test    rdi, rdi
0x18000eb72  jnz     short loc_18000EB9A
0x18000eb74  lea     ebx, [rdi+57h]
0x18000eb77  cmp     rcx, rsi
0x18000eb7a  jz      short loc_18000EBD6
0x18000eb7c  test    byte ptr [rcx+1Ch], 1
0x18000eb80  jz      short loc_18000EBB6
0x18000eb82  mov     rcx, [rcx+10h]
0x18000eb86  lea     edx, [rdi+1Ah]
0x18000eb89  mov     r9d, ebx
0x18000eb8c  lea     r8, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids
0x18000eb93  call    WPP_SF_d
0x18000eb98  jmp     short loc_18000EBAF
0x18000eb9a  xor     ebx, ebx
0x18000eb9c  lea     rcx, stru_180028E18; lpCriticalSection
0x18000eba3  mov     rdx, rdi; struct _LIST_ENTRY *
0x18000eba6  mov     [rdi+28h], rbx
0x18000ebaa  call    NcaSrcLnkdTriggerUnregisterWait
0x18000ebaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebb6  cmp     rcx, rsi
0x18000ebb9  jz      short loc_18000EBD6
0x18000ebbb  test    byte ptr [rcx+1Ch], 8
0x18000ebbf  jz      short loc_18000EBD6
0x18000ebc1  mov     rcx, [rcx+10h]
0x18000ebc5  lea     r8, WPP_4f36e67baeb930cfe336c8f232ca1ef1_Traceguids
0x18000ebcc  mov     edx, 1Bh
0x18000ebd1  call    WPP_SF_
0x18000ebd6  mov     rsi, [rsp+28h+arg_8]
0x18000ebdb  mov     eax, ebx
0x18000ebdd  mov     rbx, [rsp+28h+arg_0]
0x18000ebe2  add     rsp, 20h
0x18000ebe6  pop     rdi
0x18000ebe7  retn
```
