# QuicMtuDiscoveryMoveToSearchComplete

- ea: `0x140030940`
- end: `0x1400309f1`
- name: `QuicMtuDiscoveryMoveToSearchComplete`
- size: `177`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400309f8`
- `0x140030ad0`
- `0x140030cd4`

## callees

- `0x140010820`
- `0x140030940`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400309af`
- `ntoskrnl!_snprintf_s` at `0x1400309af`
- `HAL!KeQueryPerformanceCounter` at `0x14003096b`
- `HAL!KeQueryPerformanceCounter` at `0x14003096b`

## string_xrefs

- `0x140030993`: `Path[%hhu] Mtu Discovery Entering Search Complete at MTU %hu`

## pseudocode

```c
__int64 __fastcall QuicMtuDiscoveryMoveToSearchComplete(__int64 a1, __int64 a2)
{
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 result; // rax
  __int64 v6; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  *(_BYTE *)(a1 + 13) |= 1u;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  result = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
  *(_QWORD *)a1 = result;
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "Path[%hhu] Mtu Discovery Entering Search Complete at MTU %hu",
      *(unsigned __int8 *)(a1 - 24),
      *(unsigned __int16 *)(a1 - 8));
    return McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogInfo, a2, DstBuf);
  }
  return result;
}

```

## disassembly

```asm
0x140030940  mov     [rsp+arg_10], rbx
0x140030945  push    rdi
0x140030946  sub     rsp, 0C0h
0x14003094d  mov     rax, cs:__security_cookie
0x140030954  xor     rax, rsp
0x140030957  mov     [rsp+0C8h+var_18], rax
0x14003095f  or      byte ptr [rcx+0Dh], 1
0x140030963  mov     rbx, rcx
0x140030966  xor     ecx, ecx; PerformanceFrequency
0x140030968  mov     rdi, rdx
0x14003096b  call    cs:__imp_KeQueryPerformanceCounter
0x140030972  nop     dword ptr [rax+rax+00h]
0x140030977  mov     rcx, rax
0x14003097a  call    QuicTimePlatToUs64
0x14003097f  mov     edx, 80h; SizeInBytes
0x140030984  mov     [rbx], rax
0x140030987  test    cs:byte_14005C48B, dl
0x14003098d  jz      short loc_1400309CF
0x14003098f  movzx   ecx, byte ptr [rbx-18h]
0x140030993  lea     r9, aPathHhuMtuDisc_1; "Path[%hhu] Mtu Discovery Entering Searc"...
0x14003099a  movzx   eax, word ptr [rbx-8]
0x14003099e  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400309a2  mov     [rsp+0C8h+var_A0], eax
0x1400309a6  mov     [rsp+0C8h+var_A8], ecx
0x1400309aa  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x1400309af  call    cs:__imp__snprintf_s
0x1400309b6  nop     dword ptr [rax+rax+00h]
0x1400309bb  lea     r9, [rsp+0C8h+DstBuf]
0x1400309c0  mov     r8, rdi
0x1400309c3  lea     rdx, QuicConnLogInfo
0x1400309ca  call    McTemplateU0ps_EtwWriteTransfer
0x1400309cf  mov     rcx, [rsp+0C8h+var_18]
0x1400309d7  xor     rcx, rsp; StackCookie
0x1400309da  call    __security_check_cookie
0x1400309df  mov     rbx, [rsp+0C8h+arg_10]
0x1400309e7  add     rsp, 0C0h
0x1400309ee  pop     rdi
0x1400309ef  retn
```
