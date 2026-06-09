# ReadWs2Catalog

- ea: `0x180035838`
- end: `0x180035924`
- name: `ReadWs2Catalog`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800328c0`

## callees

- `0x180035838`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800358f8`
- `ntdll!RtlFreeHeap` at `0x1800358f8`
- `WS2_32!WSCEnumProtocolsEx` at `0x18003587a`
- `WS2_32!WSCEnumProtocolsEx` at `0x1800358d0`
- `WS2_32!WSCEnumProtocolsEx` at `0x18003587a`
- `WS2_32!WSCEnumProtocolsEx` at `0x1800358d0`

## pseudocode

```c
__int64 __fastcall ReadWs2Catalog(_QWORD *a1, _DWORD *a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  void *v8; // rbx
  int v9; // ecx
  unsigned int v10; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF

  *a1 = 0;
  *a2 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)WSCEnumProtocolsEx(0, 0, &v11, &v10, a3) != -1 )
    return 31;
  result = v10;
  if ( v10 == 10055 )
  {
    v7 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0, v11);
    v8 = (void *)v7;
    if ( v7 )
    {
      v9 = WSCEnumProtocolsEx(0, v7, &v11, &v10, a3);
      if ( v9 == -1 )
      {
        RtlFreeHeap(SockPrivateHeap, 0, v8);
        return v10;
      }
      else
      {
        result = 0;
        *a1 = v8;
        *a2 = v9;
      }
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035838  mov     rax, rsp
0x18003583b  mov     [rax+18h], rbx
0x18003583f  push    rbp
0x180035840  push    rsi
0x180035841  push    rdi
0x180035842  sub     rsp, 30h
0x180035846  mov     rbp, r8
0x180035849  mov     qword ptr [rcx], 0
0x180035850  mov     rdi, rdx
0x180035853  mov     dword ptr [rdx], 0
0x180035859  mov     rsi, rcx
0x18003585c  mov     [rax-28h], r8
0x180035860  lea     r8, [rax+10h]
0x180035864  mov     dword ptr [rax+8], 0
0x18003586b  xor     edx, edx
0x18003586d  mov     dword ptr [rax+10h], 0
0x180035874  xor     ecx, ecx
0x180035876  lea     r9, [rax+8]
0x18003587a  call    cs:__imp_WSCEnumProtocolsEx
0x180035881  nop     dword ptr [rax+rax+00h]
0x180035886  cmp     eax, 0FFFFFFFFh
0x180035889  jnz     loc_180035911
0x18003588f  mov     eax, [rsp+48h+arg_0]
0x180035893  cmp     eax, 2747h
0x180035898  jnz     short loc_180035916
0x18003589a  mov     r8d, [rsp+48h+arg_8]
0x18003589f  xor     edx, edx
0x1800358a1  mov     rcx, cs:SockPrivateHeap
0x1800358a8  mov     rax, cs:SockAllocateHeapRoutine
0x1800358af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358b4  mov     rbx, rax
0x1800358b7  test    rax, rax
0x1800358ba  jz      short loc_18003590A
0x1800358bc  lea     r9, [rsp+48h+arg_0]
0x1800358c1  mov     [rsp+48h+var_28], rbp
0x1800358c6  lea     r8, [rsp+48h+arg_8]
0x1800358cb  mov     rdx, rax
0x1800358ce  xor     ecx, ecx
0x1800358d0  call    cs:__imp_WSCEnumProtocolsEx
0x1800358d7  nop     dword ptr [rax+rax+00h]
0x1800358dc  mov     ecx, eax
0x1800358de  cmp     eax, 0FFFFFFFFh
0x1800358e1  jz      short loc_1800358EC
0x1800358e3  xor     eax, eax
0x1800358e5  mov     [rsi], rbx
0x1800358e8  mov     [rdi], ecx
0x1800358ea  jmp     short loc_180035916
0x1800358ec  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800358f3  mov     r8, rbx; P
0x1800358f6  xor     edx, edx; Flags
0x1800358f8  call    cs:__imp_RtlFreeHeap
0x1800358ff  nop     dword ptr [rax+rax+00h]
0x180035904  mov     eax, [rsp+48h+arg_0]
0x180035908  jmp     short loc_180035916
0x18003590a  mov     eax, 8
0x18003590f  jmp     short loc_180035916
0x180035911  mov     eax, 1Fh
0x180035916  mov     rbx, [rsp+48h+arg_10]
0x18003591b  add     rsp, 30h
0x18003591f  pop     rdi
0x180035920  pop     rsi
0x180035921  pop     rbp
0x180035922  retn
```
