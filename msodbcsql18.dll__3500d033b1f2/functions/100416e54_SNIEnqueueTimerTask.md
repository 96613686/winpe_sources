# SNIEnqueueTimerTask

- ea: `0x100416e54`
- end: `0x100416f8d`
- name: `SNIEnqueueTimerTask`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100434d74`

## callees

- `0x100416e54`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x100416f03`
- `KERNEL32!CreateTimerQueueTimer` at `0x100416f03`
- `KERNEL32!GetLastError` at `0x100416f2b`
- `KERNEL32!GetLastError` at `0x100416f2b`

## pseudocode

```c
__int64 __fastcall SNIEnqueueTimerTask(__int64 *a1, __int64 a2, __int64 a3, DWORD a4)
{
  __int64 v8; // rax
  __int64 v9; // rbx
  DWORD LastError; // ebx
  _QWORD v12[3]; // [rsp+40h] [rbp-18h] BYREF

  v12[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7808[0] )
    bidScopeEnterW(v12, off_1005E7808[0], a2);
  v8 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 32);
  v9 = v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = a3;
    *(_QWORD *)(v8 + 8) = a2;
    *(_DWORD *)(v8 + 24) = a4;
    if ( CreateTimerQueueTimer((PHANDLE)(v8 + 16), 0, SNITimerCallback, (PVOID)v8, a4, a4, 0) )
    {
      *a1 = v9;
      LastError = 0;
    }
    else
    {
      ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v9);
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 14;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E47B0[0] )
    bidTraceW(0, 2844672, off_1005E47B0[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v12);
  return LastError;
}

```

## disassembly

```asm
0x100416e54  mov     r11, rsp
0x100416e57  mov     [r11+8], rbx
0x100416e5b  mov     [r11+10h], rbp
0x100416e5f  mov     [r11+18h], rsi
0x100416e63  mov     [r11+20h], rdi
0x100416e67  push    r14
0x100416e69  sub     rsp, 50h
0x100416e6d  mov     eax, cs:_bidGblFlags
0x100416e73  mov     r14, rcx
0x100416e76  or      qword ptr [r11-18h], 0FFFFFFFFFFFFFFFFh
0x100416e7b  mov     ecx, 20004h
0x100416e80  and     eax, ecx
0x100416e82  mov     edi, r9d
0x100416e85  mov     rsi, r8
0x100416e88  mov     rbp, rdx
0x100416e8b  cmp     eax, ecx
0x100416e8d  jnz     short loc_100416EB6
0x100416e8f  mov     rax, cs:off_1005E7808; "<SNIEnqueueTimerTask|API|SNI> pfnAsyncW"...
0x100416e96  test    rax, rax
0x100416e99  jz      short loc_100416EB6
0x100416e9b  mov     [rsp+58h+DueTime], r9d
0x100416ea0  lea     rcx, [r11-18h]
0x100416ea4  mov     r9, r8
0x100416ea7  mov     r8, rdx
0x100416eaa  mov     rdx, cs:off_1005E7808; "<SNIEnqueueTimerTask|API|SNI> pfnAsyncW"...
0x100416eb1  call    _bidScopeEnterW
0x100416eb6  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x100416ebd  mov     edx, 20h ; ' '
0x100416ec2  mov     rax, [rcx]
0x100416ec5  mov     rax, [rax+58h]
0x100416ec9  call    cs:__guard_dispatch_icall_fptr
0x100416ecf  mov     rbx, rax
0x100416ed2  test    rax, rax
0x100416ed5  jnz     short loc_100416EDC
0x100416ed7  lea     ebx, [rax+0Eh]
0x100416eda  jmp     short loc_100416F33
0x100416edc  and     [rsp+58h+var_28], 0
0x100416ee1  lea     rcx, [rax+10h]; phNewTimer
0x100416ee5  mov     [rsp+58h+Period], edi; Period
0x100416ee9  lea     r8, SNITimerCallback; Callback
0x100416ef0  mov     r9, rbx; Parameter
0x100416ef3  mov     [rsp+58h+DueTime], edi; DueTime
0x100416ef7  xor     edx, edx; TimerQueue
0x100416ef9  mov     [rax], rsi
0x100416efc  mov     [rax+8], rbp
0x100416f00  mov     [rax+18h], edi
0x100416f03  call    cs:__imp_CreateTimerQueueTimer
0x100416f09  test    eax, eax
0x100416f0b  jz      short loc_100416F14
0x100416f0d  mov     [r14], rbx
0x100416f10  xor     ebx, ebx
0x100416f12  jmp     short loc_100416F33
0x100416f14  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100416f1b  mov     rdx, rbx
0x100416f1e  mov     rax, [rcx]
0x100416f21  mov     rax, [rax+68h]
0x100416f25  call    cs:__guard_dispatch_icall_fptr
0x100416f2b  call    cs:__imp_GetLastError
0x100416f31  mov     ebx, eax
0x100416f33  mov     ecx, cs:_bidGblFlags
0x100416f39  mov     eax, 20002h
0x100416f3e  and     ecx, eax
0x100416f40  cmp     ecx, eax
0x100416f42  jnz     short loc_100416F66
0x100416f44  mov     rcx, cs:off_1005E47B0; "<SNIEnqueueTimerTask|RET|SNI> %d{WINERR"...
0x100416f4b  test    rcx, rcx
0x100416f4e  jz      short loc_100416F66
0x100416f50  mov     r8, cs:off_1005E47B0; "<SNIEnqueueTimerTask|RET|SNI> %d{WINERR"...
0x100416f57  mov     r9d, ebx
0x100416f5a  mov     edx, 2B6800h
0x100416f5f  xor     ecx, ecx
0x100416f61  call    _bidTraceW
0x100416f66  lea     rcx, [rsp+58h+var_18]; this
0x100416f6b  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100416f70  mov     rbp, [rsp+58h+arg_8]
0x100416f75  mov     eax, ebx
0x100416f77  mov     rbx, [rsp+58h+arg_0]
0x100416f7c  mov     rsi, [rsp+58h+arg_10]
0x100416f81  mov     rdi, [rsp+58h+arg_18]
0x100416f86  add     rsp, 50h
0x100416f8a  pop     r14
0x100416f8c  retn
```
