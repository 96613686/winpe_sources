# QuicTimerWheelRemoveConnection

- ea: `0x140022644`
- end: `0x140022709`
- name: `QuicTimerWheelRemoveConnection`
- size: `197`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000edc0`
- `0x14001d88c`
- `0x1400200d8`

## callees

- `0x14000da60`
- `0x14001d7d0`
- `0x140022644`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140022697`
- `ntoskrnl!_snprintf_s` at `0x140022697`

## pseudocode

```c
__int64 __fastcall QuicTimerWheelRemoveConnection(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // rdx
  __int64 result; // rax
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  if ( a2[6] )
  {
    if ( byte_14005C48E < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[time][%p] Removing Connection %p.", a1, a2);
      McTemplateU0s_EtwWriteTransfer(v4, (const EVENT_DESCRIPTOR *)QuicLogVerbose, DstBuf);
    }
    v5 = (_QWORD *)a2[7];
    v6 = a2[6];
    *v5 = v6;
    *(_QWORD *)(v6 + 8) = v5;
    a2[6] = 0;
    --a1[1];
    if ( a2 == (_QWORD *)a1[2] )
      QuicTimerWheelUpdate(a1);
    return QuicConnRelease(a2, 4);
  }
  return result;
}

```

## disassembly

```asm
0x140022644  mov     [rsp+arg_10], rbx
0x140022649  push    rdi
0x14002264a  sub     rsp, 0C0h
0x140022651  mov     rax, cs:__security_cookie
0x140022658  xor     rax, rsp
0x14002265b  mov     [rsp+0C8h+var_18], rax
0x140022663  cmp     qword ptr [rdx+30h], 0
0x140022668  mov     rbx, rdx
0x14002266b  mov     rdi, rcx
0x14002266e  jz      short loc_1400226E7
0x140022670  mov     edx, 80h; SizeInBytes
0x140022675  test    cs:byte_14005C48E, dl
0x14002267b  jz      short loc_1400226B4
0x14002267d  mov     [rsp+0C8h+var_A0], rbx
0x140022682  lea     r9, aTimePRemovingC; "[time][%p] Removing Connection %p."
0x140022689  mov     [rsp+0C8h+var_A8], rcx
0x14002268e  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140022692  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140022697  call    cs:__imp__snprintf_s
0x14002269e  nop     dword ptr [rax+rax+00h]
0x1400226a3  lea     r8, [rsp+0C8h+DstBuf]
0x1400226a8  lea     rdx, QuicLogVerbose
0x1400226af  call    McTemplateU0s_EtwWriteTransfer
0x1400226b4  mov     rax, [rbx+38h]
0x1400226b8  mov     rdx, [rbx+30h]
0x1400226bc  mov     [rax], rdx
0x1400226bf  mov     [rdx+8], rax
0x1400226c3  and     qword ptr [rbx+30h], 0
0x1400226c8  dec     qword ptr [rdi+8]
0x1400226cc  cmp     rbx, [rdi+10h]
0x1400226d0  jnz     short loc_1400226DA
0x1400226d2  mov     rcx, rdi
0x1400226d5  call    QuicTimerWheelUpdate
0x1400226da  mov     edx, 4
0x1400226df  mov     rcx, rbx
0x1400226e2  call    QuicConnRelease
0x1400226e7  mov     rcx, [rsp+0C8h+var_18]
0x1400226ef  xor     rcx, rsp; StackCookie
0x1400226f2  call    __security_check_cookie
0x1400226f7  mov     rbx, [rsp+0C8h+arg_10]
0x1400226ff  add     rsp, 0C0h
0x140022706  pop     rdi
0x140022707  retn
```
