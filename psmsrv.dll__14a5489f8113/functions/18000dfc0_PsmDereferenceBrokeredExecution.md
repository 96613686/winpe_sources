# PsmDereferenceBrokeredExecution

- ea: `0x18000dfc0`
- end: `0x18000e0ec`
- name: `PsmDereferenceBrokeredExecution`
- size: `300`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000cb34`
- `0x18000dfc0`
- `0x18000e0f4`
- `0x180015dd4`
- `0x1800179d8`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x18000e031`
- `ntdll!NtUpdateWnfStateData` at `0x18000e031`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e05b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e05b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e071`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e071`

## pseudocode

```c
__int64 __fastcall PsmDereferenceBrokeredExecution(__int64 *a1)
{
  unsigned int v1; // ebx
  __int64 v3; // rsi
  int WorkItemNotify; // r14d
  _QWORD *v6; // rcx
  int v7; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_DWORD *)a1 + 4);
  PsmpEndWorkItemExecution(*a1, a1[1], v1);
  if ( (v1 & 3) == 0 )
  {
    v3 = *a1;
    v7 = 0;
    if ( *(_QWORD *)(v3 + 88)
      || (RtlAcquireSRWLockExclusive(v3 + 328),
          WorkItemNotify = PsmpAllocateWorkItemNotify(v3, 0),
          RtlReleaseSRWLockExclusive(v3 + 328),
          WorkItemNotify >= 0) )
    {
      v7 = *(_DWORD *)(v3 + 136);
      NtUpdateWnfStateData(v3 + 88, &v7, 4);
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
            *(_QWORD *)(v3 + 96),
            WorkItemNotify);
          v6 = WPP_GLOBAL_Control;
        }
        if ( (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
          WPP_SF_iD(v6[2], 13, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids, *(_QWORD *)(*a1 + 96), WorkItemNotify);
      }
    }
  }
  return PsmpInternalWorkItemReferenceDestroy(a1);
}

```

## disassembly

```asm
0x18000dfc0  mov     [rsp+arg_8], rbx
0x18000dfc5  mov     [rsp+arg_10], rbp
0x18000dfca  push    rsi
0x18000dfcb  push    rdi
0x18000dfcc  push    r14
0x18000dfce  sub     rsp, 40h
0x18000dfd2  mov     ebx, [rcx+10h]
0x18000dfd5  mov     rdi, rcx
0x18000dfd8  mov     rdx, [rcx+8]
0x18000dfdc  mov     r8d, ebx
0x18000dfdf  mov     rcx, [rcx]
0x18000dfe2  call    PsmpEndWorkItemExecution
0x18000dfe7  test    bl, 3
0x18000dfea  jnz     short loc_18000E037
0x18000dfec  mov     rsi, [rdi]
0x18000dfef  mov     [rsp+58h+arg_0], 0
0x18000dff7  cmp     qword ptr [rsi+58h], 0
0x18000dffc  jz      short loc_18000E051
0x18000dffe  mov     eax, [rsi+88h]
0x18000e004  lea     rdx, [rsp+58h+arg_0]
0x18000e009  xor     r9d, r9d
0x18000e00c  mov     [rsp+58h+var_28], 0
0x18000e014  mov     [rsp+58h+var_30], 0
0x18000e01c  lea     rcx, [rsi+58h]
0x18000e020  mov     [rsp+58h+arg_0], eax
0x18000e024  mov     [rsp+58h+var_38], 0
0x18000e02d  lea     r8d, [r9+4]
0x18000e031  call    cs:__imp_NtUpdateWnfStateData
0x18000e037  mov     rcx, rdi
0x18000e03a  mov     rbx, [rsp+58h+arg_8]
0x18000e03f  mov     rbp, [rsp+58h+arg_10]
0x18000e044  add     rsp, 40h
0x18000e048  pop     r14
0x18000e04a  pop     rdi
0x18000e04b  pop     rsi
0x18000e04c  jmp     PsmpInternalWorkItemReferenceDestroy
0x18000e051  lea     rbx, [rsi+148h]
0x18000e058  mov     rcx, rbx
0x18000e05b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e061  xor     edx, edx
0x18000e063  mov     rcx, rsi
0x18000e066  call    PsmpAllocateWorkItemNotify
0x18000e06b  mov     rcx, rbx
0x18000e06e  mov     r14d, eax
0x18000e071  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e077  test    r14d, r14d
0x18000e07a  jns     short loc_18000DFFE
0x18000e07c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e083  mov     bl, 2
0x18000e085  test    [rcx+1Ch], bl
0x18000e088  jz      short loc_18000E037
0x18000e08a  cmp     [rcx+19h], bl
0x18000e08d  jb      short loc_18000E0B4
0x18000e08f  mov     r9, [rsi+60h]
0x18000e093  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18000e09a  mov     rcx, [rcx+10h]
0x18000e09e  mov     edx, 2Dh ; '-'
0x18000e0a3  mov     dword ptr [rsp+58h+var_38], r14d
0x18000e0a8  call    WPP_SF_iD
0x18000e0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0b4  test    [rcx+1Ch], bl
0x18000e0b7  jz      loc_18000E037
0x18000e0bd  cmp     [rcx+19h], bl
0x18000e0c0  jb      loc_18000E037
0x18000e0c6  mov     r9, [rdi]
0x18000e0c9  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18000e0d0  mov     rcx, [rcx+10h]
0x18000e0d4  mov     edx, 0Dh
0x18000e0d9  mov     dword ptr [rsp+58h+var_38], r14d
0x18000e0de  mov     r9, [r9+60h]
0x18000e0e2  call    WPP_SF_iD
0x18000e0e7  jmp     loc_18000E037
```
