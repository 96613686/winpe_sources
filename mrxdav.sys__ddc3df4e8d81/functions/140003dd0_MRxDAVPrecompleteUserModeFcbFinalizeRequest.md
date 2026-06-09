# MRxDAVPrecompleteUserModeFcbFinalizeRequest

- ea: `0x140003dd0`
- end: `0x140003f3f`
- name: `MRxDAVPrecompleteUserModeFcbFinalizeRequest`
- size: `367`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001b64`
- `0x140003dd0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e08`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e40`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e8c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003ed7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003f0f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e08`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e40`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e8c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003ed7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003f0f`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeFcbFinalizeRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
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
      WPP_SF_q(v7, 31, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_qqq(v9, 32, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v10, a1, a2);
    }
  }
  if ( a5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qqq(v11, 33, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v12, a1, a2);
  }
  if ( *(_DWORD *)(a1 + 128) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 1;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v14 = PsGetCurrentThreadId();
      WPP_SF_q(v13, 34, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v14);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v16 = PsGetCurrentThreadId();
    WPP_SF_q(v15, 35, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v16);
  }
  return 1;
}

```

## disassembly

```asm
0x140003dd0  push    rbx
0x140003dd2  push    rbp
0x140003dd3  push    rsi
0x140003dd4  push    rdi
0x140003dd5  push    r14
0x140003dd7  sub     rsp, 30h
0x140003ddb  mov     rsi, rdx
0x140003dde  mov     rdi, rcx
0x140003de1  mov     rbx, cs:WPP_GLOBAL_Control
0x140003de8  lea     rbp, WPP_GLOBAL_Control
0x140003def  lea     r14, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003df6  cmp     rbx, rbp
0x140003df9  jz      short loc_140003E69
0x140003dfb  test    dword ptr [rbx+2Ch], 4000h
0x140003e02  jz      short loc_140003E27
0x140003e04  mov     rbx, [rbx+18h]
0x140003e08  call    cs:__imp_PsGetCurrentThreadId
0x140003e0f  nop     dword ptr [rax+rax+00h]
0x140003e14  mov     edx, 1Fh
0x140003e19  mov     r8, r14
0x140003e1c  mov     r9, rax
0x140003e1f  mov     rcx, rbx
0x140003e22  call    WPP_SF_q
0x140003e27  mov     rbx, cs:WPP_GLOBAL_Control
0x140003e2e  cmp     rbx, rbp
0x140003e31  jz      short loc_140003E69
0x140003e33  test    dword ptr [rbx+2Ch], 2000h
0x140003e3a  jz      short loc_140003E69
0x140003e3c  mov     rbx, [rbx+18h]
0x140003e40  call    cs:__imp_PsGetCurrentThreadId
0x140003e47  nop     dword ptr [rax+rax+00h]
0x140003e4c  mov     edx, 20h ; ' '
0x140003e51  mov     [rsp+58h+var_30], rsi
0x140003e56  mov     r9, rax
0x140003e59  mov     [rsp+58h+var_38], rdi
0x140003e5e  mov     r8, r14
0x140003e61  mov     rcx, rbx
0x140003e64  call    WPP_SF_qqq
0x140003e69  cmp     [rsp+58h+arg_20], 0
0x140003e71  jz      short loc_140003EB5
0x140003e73  mov     rbx, cs:WPP_GLOBAL_Control
0x140003e7a  cmp     rbx, rbp
0x140003e7d  jz      short loc_140003EB5
0x140003e7f  test    dword ptr [rbx+2Ch], 2000h
0x140003e86  jz      short loc_140003EB5
0x140003e88  mov     rbx, [rbx+18h]
0x140003e8c  call    cs:__imp_PsGetCurrentThreadId
0x140003e93  nop     dword ptr [rax+rax+00h]
0x140003e98  mov     edx, 21h ; '!'
0x140003e9d  mov     [rsp+58h+var_30], rsi
0x140003ea2  mov     r9, rax
0x140003ea5  mov     [rsp+58h+var_38], rdi
0x140003eaa  mov     r8, r14
0x140003ead  mov     rcx, rbx
0x140003eb0  call    WPP_SF_qqq
0x140003eb5  cmp     dword ptr [rdi+80h], 0
0x140003ebc  jz      short loc_140003EF6
0x140003ebe  mov     rbx, cs:WPP_GLOBAL_Control
0x140003ec5  cmp     rbx, rbp
0x140003ec8  jz      short loc_140003F2E
0x140003eca  test    dword ptr [rbx+2Ch], 2000h
0x140003ed1  jz      short loc_140003EF6
0x140003ed3  mov     rbx, [rbx+18h]
0x140003ed7  call    cs:__imp_PsGetCurrentThreadId
0x140003ede  nop     dword ptr [rax+rax+00h]
0x140003ee3  mov     edx, 22h ; '"'
0x140003ee8  mov     r8, r14
0x140003eeb  mov     r9, rax
0x140003eee  mov     rcx, rbx
0x140003ef1  call    WPP_SF_q
0x140003ef6  mov     rbx, cs:WPP_GLOBAL_Control
0x140003efd  cmp     rbx, rbp
0x140003f00  jz      short loc_140003F2E
0x140003f02  test    dword ptr [rbx+2Ch], 4000h
0x140003f09  jz      short loc_140003F2E
0x140003f0b  mov     rbx, [rbx+18h]
0x140003f0f  call    cs:__imp_PsGetCurrentThreadId
0x140003f16  nop     dword ptr [rax+rax+00h]
0x140003f1b  mov     edx, 23h ; '#'
0x140003f20  mov     r8, r14
0x140003f23  mov     r9, rax
0x140003f26  mov     rcx, rbx
0x140003f29  call    WPP_SF_q
0x140003f2e  mov     eax, 1
0x140003f33  add     rsp, 30h
0x140003f37  pop     r14
0x140003f39  pop     rdi
0x140003f3a  pop     rsi
0x140003f3b  pop     rbp
0x140003f3c  pop     rbx
0x140003f3d  retn
```
