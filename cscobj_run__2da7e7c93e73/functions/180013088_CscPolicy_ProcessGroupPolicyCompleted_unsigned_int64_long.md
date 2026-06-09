# CscPolicy_ProcessGroupPolicyCompleted(unsigned __int64,long)

- ea: `0x180013088`
- end: `0x1800130e4`
- name: `?CscPolicy_ProcessGroupPolicyCompleted@@YAK_KJ@Z`
- size: `92`
- prototype: `unsigned int __fastcall(unsigned __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012120`
- `0x180013a44`

## callees

- `0x18000f5a4`
- `0x180013088`

## import_xrefs

- `USERENV!ProcessGroupPolicyCompleted` at `0x1800130dd`

## pseudocode

```c
DWORD __fastcall CscPolicy_ProcessGroupPolicyCompleted(ASYNCCOMPLETIONHANDLE a1, unsigned __int16 a2)
{
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids);
  return ProcessGroupPolicyCompleted((REFGPEXTENSIONID)qword_18003AD48, a1, a2);
}

```

## disassembly

```asm
0x180013088  mov     [rsp+arg_0], rbx
0x18001308d  push    rdi
0x18001308e  sub     rsp, 20h
0x180013092  mov     ebx, edx
0x180013094  mov     rdi, rcx
0x180013097  mov     rcx, cs:WPP_GLOBAL_Control
0x18001309e  lea     rax, WPP_GLOBAL_Control
0x1800130a5  cmp     rcx, rax
0x1800130a8  jz      short loc_1800130C5
0x1800130aa  test    byte ptr [rcx+1Ch], 80h
0x1800130ae  jz      short loc_1800130C5
0x1800130b0  mov     rcx, [rcx+10h]
0x1800130b4  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800130bb  mov     edx, 0Ah
0x1800130c0  call    WPP_SF_
0x1800130c5  movzx   r8d, bx
0x1800130c9  lea     rcx, qword_18003AD48
0x1800130d0  mov     rdx, rdi
0x1800130d3  mov     rbx, [rsp+28h+arg_0]
0x1800130d8  add     rsp, 20h
0x1800130dc  pop     rdi
0x1800130dd  jmp     cs:__imp_ProcessGroupPolicyCompleted
```
