# KbdHid_WaitForExtendedAttributesQueryCompletion

- ea: `0x140005928`
- end: `0x140005a05`
- name: `KbdHid_WaitForExtendedAttributesQueryCompletion`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003470`

## callees

- `0x140005490`
- `0x140005928`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400059f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400059f7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000599d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400059c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000599d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400059c4`

## pseudocode

```c
__int64 __fastcall KbdHid_WaitForExtendedAttributesQueryCompletion(__int64 a1)
{
  unsigned int v1; // edi
  int v3; // edx
  signed __int32 v4; // ecx
  signed __int32 v5; // r8d
  int v6; // r9d

  v1 = 0;
  v3 = 0;
  v4 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 316), 0, 0);
  v5 = v4;
  if ( !v4 )
  {
LABEL_4:
    v1 = -1073741808;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 27;
LABEL_6:
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_dd(WPP_GLOBAL_Control->DeviceExtension, v3, v5, v6);
      return v1;
    }
    return v1;
  }
  v5 = v4 - 1;
  if ( v4 != 1 )
  {
    if ( v4 == 2 )
      return v1;
    goto LABEL_4;
  }
  if ( !KeGetCurrentIrql() )
  {
    KeWaitForSingleObject((PVOID)(a1 + 320), Executive, 0, 0, 0);
    return v1;
  }
  v1 = -1073741808;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    v6 = 26;
    goto LABEL_6;
  }
  return v1;
}

```

## disassembly

```asm
0x140005928  mov     [rsp+arg_0], rbx
0x14000592d  push    rdi
0x14000592e  sub     rsp, 40h
0x140005932  xor     edi, edi
0x140005934  mov     rbx, rcx
0x140005937  mov     edx, edi
0x140005939  xor     eax, eax
0x14000593b  lock cmpxchg [rcx+13Ch], edx
0x140005943  mov     ecx, eax
0x140005945  mov     r8d, eax
0x140005948  test    eax, eax
0x14000594a  jz      short loc_140005958
0x14000594c  sub     r8d, 1
0x140005950  jz      short loc_14000599D
0x140005952  cmp     r8d, 1
0x140005956  jz      short loc_14000598F
0x140005958  mov     ebx, 0C0000010h
0x14000595d  mov     edi, ebx
0x14000595f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005966  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000596d  jz      short loc_14000598F
0x14000596f  mov     [rsp+48h+var_18], ebx
0x140005973  mov     r9d, 1Bh
0x140005979  mov     [rsp+48h+var_20], ecx
0x14000597d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005984  mov     dl, 2
0x140005986  mov     rcx, [rcx+40h]
0x14000598a  call    WPP_RECORDER_SF_dd
0x14000598f  mov     rbx, [rsp+48h+arg_0]
0x140005994  mov     eax, edi
0x140005996  add     rsp, 40h
0x14000599a  pop     rdi
0x14000599b  retn
0x14000599d  call    cs:__imp_KeGetCurrentIrql
0x1400059a4  nop     dword ptr [rax+rax+00h]
0x1400059a9  test    al, al
0x1400059ab  jz      short loc_1400059E3
0x1400059ad  mov     ebx, 0C0000010h
0x1400059b2  mov     edi, ebx
0x1400059b4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400059bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400059c2  jz      short loc_14000598F
0x1400059c4  call    cs:__imp_KeGetCurrentIrql
0x1400059cb  nop     dword ptr [rax+rax+00h]
0x1400059d0  mov     [rsp+48h+var_18], ebx
0x1400059d4  mov     r9d, 1Ah
0x1400059da  movzx   eax, al
0x1400059dd  mov     [rsp+48h+var_20], eax
0x1400059e1  jmp     short loc_14000597D
0x1400059e3  lea     rcx, [rbx+140h]; Object
0x1400059ea  mov     [rsp+48h+Timeout], rdi; Timeout
0x1400059ef  xor     r9d, r9d; Alertable
0x1400059f2  xor     r8d, r8d; WaitMode
0x1400059f5  xor     edx, edx; WaitReason
0x1400059f7  call    cs:__imp_KeWaitForSingleObject
0x1400059fe  nop     dword ptr [rax+rax+00h]
0x140005a03  jmp     short loc_14000598F
```
