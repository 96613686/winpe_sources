# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x18002d730`
- end: `0x18002d7a8`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `120`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001ae0c`
- `0x180026d9c`
- `0x18002d730`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  _QWORD *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
  }
  KpsServiceData = a1;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 11, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
}

```

## disassembly

```asm
0x18002d730  mov     [rsp+arg_0], rbx
0x18002d735  push    rdi
0x18002d736  sub     rsp, 20h
0x18002d73a  mov     rbx, rcx
0x18002d73d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d744  lea     rdi, WPP_GLOBAL_Control
0x18002d74b  cmp     rcx, rdi
0x18002d74e  jz      short loc_18002D775
0x18002d750  test    byte ptr [rcx+1Ch], 20h
0x18002d754  jz      short loc_18002D775
0x18002d756  mov     rcx, [rcx+10h]
0x18002d75a  lea     r8, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002d761  mov     edx, 0Ah
0x18002d766  mov     r9, rbx
0x18002d769  call    WPP_SF_q
0x18002d76e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d775  mov     cs:?KpsServiceData@@3U_KPS_SERVICE_DATA@@A, rbx; _KPS_SERVICE_DATA KpsServiceData
0x18002d77c  cmp     rcx, rdi
0x18002d77f  jz      short loc_18002D79C
0x18002d781  test    byte ptr [rcx+1Ch], 20h
0x18002d785  jz      short loc_18002D79C
0x18002d787  mov     rcx, [rcx+10h]
0x18002d78b  lea     r8, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002d792  mov     edx, 0Bh
0x18002d797  call    WPP_SF_
0x18002d79c  mov     rbx, [rsp+28h+arg_0]
0x18002d7a1  add     rsp, 20h
0x18002d7a5  pop     rdi
0x18002d7a6  retn
```
