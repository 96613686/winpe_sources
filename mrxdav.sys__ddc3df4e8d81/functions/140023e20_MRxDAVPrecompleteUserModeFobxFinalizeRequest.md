# MRxDAVPrecompleteUserModeFobxFinalizeRequest

- ea: `0x140023e20`
- end: `0x140023f8f`
- name: `MRxDAVPrecompleteUserModeFobxFinalizeRequest`
- size: `367`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001b64`
- `0x140023e20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140023e58`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023e90`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023edc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023f27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023f5f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023e58`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023e90`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023edc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023f27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023f5f`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeFobxFinalizeRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v7, 22, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_qqq(v9, 23, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v10, a1, a2);
    }
  }
  if ( a5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qqq(v11, 24, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v12, a1, a2);
  }
  if ( *(_DWORD *)(a1 + 128) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 1;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v14 = PsGetCurrentThreadId();
      WPP_SF_q(v13, 25, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v14);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v16 = PsGetCurrentThreadId();
    WPP_SF_q(v15, 26, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v16);
  }
  return 1;
}

```

## disassembly

```asm
0x140023e20  push    rbx
0x140023e22  push    rbp
0x140023e23  push    rsi
0x140023e24  push    rdi
0x140023e25  push    r14
0x140023e27  sub     rsp, 30h
0x140023e2b  mov     rsi, rdx
0x140023e2e  mov     rdi, rcx
0x140023e31  mov     rbx, cs:WPP_GLOBAL_Control
0x140023e38  lea     rbp, WPP_GLOBAL_Control
0x140023e3f  lea     r14, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023e46  cmp     rbx, rbp
0x140023e49  jz      short loc_140023EB9
0x140023e4b  test    dword ptr [rbx+2Ch], 4000h
0x140023e52  jz      short loc_140023E77
0x140023e54  mov     rbx, [rbx+18h]
0x140023e58  call    cs:__imp_PsGetCurrentThreadId
0x140023e5f  nop     dword ptr [rax+rax+00h]
0x140023e64  mov     edx, 16h
0x140023e69  mov     r8, r14
0x140023e6c  mov     r9, rax
0x140023e6f  mov     rcx, rbx
0x140023e72  call    WPP_SF_q
0x140023e77  mov     rbx, cs:WPP_GLOBAL_Control
0x140023e7e  cmp     rbx, rbp
0x140023e81  jz      short loc_140023EB9
0x140023e83  test    dword ptr [rbx+2Ch], 2000h
0x140023e8a  jz      short loc_140023EB9
0x140023e8c  mov     rbx, [rbx+18h]
0x140023e90  call    cs:__imp_PsGetCurrentThreadId
0x140023e97  nop     dword ptr [rax+rax+00h]
0x140023e9c  mov     edx, 17h
0x140023ea1  mov     [rsp+58h+var_30], rsi
0x140023ea6  mov     r9, rax
0x140023ea9  mov     [rsp+58h+var_38], rdi
0x140023eae  mov     r8, r14
0x140023eb1  mov     rcx, rbx
0x140023eb4  call    WPP_SF_qqq
0x140023eb9  cmp     [rsp+58h+arg_20], 0
0x140023ec1  jz      short loc_140023F05
0x140023ec3  mov     rbx, cs:WPP_GLOBAL_Control
0x140023eca  cmp     rbx, rbp
0x140023ecd  jz      short loc_140023F05
0x140023ecf  test    dword ptr [rbx+2Ch], 2000h
0x140023ed6  jz      short loc_140023F05
0x140023ed8  mov     rbx, [rbx+18h]
0x140023edc  call    cs:__imp_PsGetCurrentThreadId
0x140023ee3  nop     dword ptr [rax+rax+00h]
0x140023ee8  mov     edx, 18h
0x140023eed  mov     [rsp+58h+var_30], rsi
0x140023ef2  mov     r9, rax
0x140023ef5  mov     [rsp+58h+var_38], rdi
0x140023efa  mov     r8, r14
0x140023efd  mov     rcx, rbx
0x140023f00  call    WPP_SF_qqq
0x140023f05  cmp     dword ptr [rdi+80h], 0
0x140023f0c  jz      short loc_140023F46
0x140023f0e  mov     rbx, cs:WPP_GLOBAL_Control
0x140023f15  cmp     rbx, rbp
0x140023f18  jz      short loc_140023F7E
0x140023f1a  test    dword ptr [rbx+2Ch], 2000h
0x140023f21  jz      short loc_140023F46
0x140023f23  mov     rbx, [rbx+18h]
0x140023f27  call    cs:__imp_PsGetCurrentThreadId
0x140023f2e  nop     dword ptr [rax+rax+00h]
0x140023f33  mov     edx, 19h
0x140023f38  mov     r8, r14
0x140023f3b  mov     r9, rax
0x140023f3e  mov     rcx, rbx
0x140023f41  call    WPP_SF_q
0x140023f46  mov     rbx, cs:WPP_GLOBAL_Control
0x140023f4d  cmp     rbx, rbp
0x140023f50  jz      short loc_140023F7E
0x140023f52  test    dword ptr [rbx+2Ch], 4000h
0x140023f59  jz      short loc_140023F7E
0x140023f5b  mov     rbx, [rbx+18h]
0x140023f5f  call    cs:__imp_PsGetCurrentThreadId
0x140023f66  nop     dword ptr [rax+rax+00h]
0x140023f6b  mov     edx, 1Ah
0x140023f70  mov     r8, r14
0x140023f73  mov     r9, rax
0x140023f76  mov     rcx, rbx
0x140023f79  call    WPP_SF_q
0x140023f7e  mov     eax, 1
0x140023f83  add     rsp, 30h
0x140023f87  pop     r14
0x140023f89  pop     rdi
0x140023f8a  pop     rsi
0x140023f8b  pop     rbp
0x140023f8c  pop     rbx
0x140023f8d  retn
```
