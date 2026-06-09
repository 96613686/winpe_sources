# PcQoSPUpdateFlowPrivate

- ea: `0x14000c460`
- end: `0x14000c53e`
- name: `PcQoSPUpdateFlowPrivate`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callees

- `0x140003ab0`
- `0x14000c164`
- `0x14000c460`
- `0x14000c75c`

## pseudocode

```c
__int64 __fastcall PcQoSPUpdateFlowPrivate(__int64 *a1)
{
  __int64 v2; // rcx
  ULONG v3; // r8d
  unsigned int v4; // edi
  KAFFINITY v5; // rbx
  int updated; // eax
  void *Src; // [rsp+20h] [rbp-48h]
  __int64 v9; // [rsp+28h] [rbp-40h]
  __int64 v10; // [rsp+30h] [rbp-38h]
  __int64 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF
  __int64 v13; // [rsp+78h] [rbp+10h] BYREF
  __int64 v14; // [rsp+80h] [rbp+18h] BYREF

  v2 = *a1;
  LODWORD(v14) = 0;
  LOWORD(v13) = 0;
  LOWORD(v12) = 0;
  v3 = *(_DWORD *)(v2 + 64) + 80;
  if ( *(_DWORD *)(v2 + 64) >= 0xFFFFFFB0 )
  {
    v4 = -1073741675;
  }
  else if ( a1[1] >= (unsigned __int64)v3 )
  {
    v5 = a1[2];
    updated = PcpUpdateFlow(v5, 0, v3, 2, (char *)v2, 0, 0, &v14, &v13, &v12);
    LODWORD(v11) = v14;
    v4 = updated;
    LODWORD(v10) = *(_DWORD *)(*a1 + 64);
    LOWORD(v9) = v12;
    LOWORD(Src) = v13;
    PcpTraceUpdateFlowEvent(v5, updated, 2, *a1, Src, v9, v10, *(_QWORD *)(*a1 + 72), v11);
  }
  else
  {
    v4 = -1073741789;
  }
  return PcpNormalizeNtStatus(v4);
}

```

## disassembly

```asm
0x14000c460  mov     rax, rsp
0x14000c463  push    rbx
0x14000c464  push    rsi
0x14000c465  push    rdi
0x14000c466  sub     rsp, 50h
0x14000c46a  xor     edx, edx; int
0x14000c46c  mov     rsi, rcx
0x14000c46f  mov     rcx, [rcx]
0x14000c472  mov     [rax+18h], edx
0x14000c475  mov     [rax+10h], dx
0x14000c479  mov     [rax+8], dx
0x14000c47d  mov     r8d, [rcx+40h]
0x14000c481  add     r8d, 50h ; 'P'; int
0x14000c485  cmp     r8d, 50h ; 'P'
0x14000c489  jb      loc_14000C529
0x14000c48f  mov     eax, r8d
0x14000c492  cmp     [rsi+8], rax
0x14000c496  jnb     short loc_14000C4A2
0x14000c498  mov     edi, 0C0000023h
0x14000c49d  jmp     loc_14000C52E
0x14000c4a2  mov     rbx, [rsi+10h]
0x14000c4a6  lea     rax, [rsp+68h+arg_0]
0x14000c4ab  mov     [rsp+68h+var_20], rax; __int64
0x14000c4b0  mov     r9d, 2; int
0x14000c4b6  lea     rax, [rsp+68h+arg_8]
0x14000c4bb  mov     [rsp+68h+var_28], rax; __int64
0x14000c4c0  lea     rax, [rsp+68h+arg_10]
0x14000c4c8  mov     [rsp+68h+var_30], rax; __int64
0x14000c4cd  mov     dword ptr [rsp+68h+var_38], edx; int
0x14000c4d1  mov     [rsp+68h+var_40], dl; char
0x14000c4d5  mov     [rsp+68h+Src], rcx; Src
0x14000c4da  mov     rcx, rbx; int
0x14000c4dd  call    PcpUpdateFlow
0x14000c4e2  mov     r9, [rsi]
0x14000c4e5  mov     r8d, 2
0x14000c4eb  mov     edx, dword ptr [rsp+68h+arg_10]
0x14000c4f2  mov     rcx, rbx
0x14000c4f5  mov     dword ptr [rsp+68h+var_28], edx
0x14000c4f9  mov     edi, eax
0x14000c4fb  mov     rdx, [r9+48h]
0x14000c4ff  mov     [rsp+68h+var_30], rdx
0x14000c504  mov     edx, [r9+40h]
0x14000c508  mov     dword ptr [rsp+68h+var_38], edx
0x14000c50c  movzx   edx, word ptr [rsp+68h+arg_0]
0x14000c511  mov     word ptr [rsp+68h+var_40], dx
0x14000c516  movzx   edx, word ptr [rsp+68h+arg_8]
0x14000c51b  mov     word ptr [rsp+68h+Src], dx
0x14000c520  mov     edx, eax
0x14000c522  call    PcpTraceUpdateFlowEvent
0x14000c527  jmp     short loc_14000C52E
0x14000c529  mov     edi, 0C0000095h
0x14000c52e  mov     ecx, edi
0x14000c530  call    PcpNormalizeNtStatus
0x14000c535  add     rsp, 50h
0x14000c539  pop     rdi
0x14000c53a  pop     rsi
0x14000c53b  pop     rbx
0x14000c53c  retn
```
