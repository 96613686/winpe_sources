# CDDPDEV::DestroyAllocation(uint)

- ea: `0x140001cb4`
- end: `0x140001dc6`
- name: `?DestroyAllocation@CDDPDEV@@QEAAJI@Z`
- size: `274`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1400015e0`
- `0x140001a5c`
- `0x140001b14`
- `0x1400212b0`
- `0x140029254`
- `0x14002d4b4`
- `0x14002e61c`
- `0x140032000`

## callees

- `0x140001cb4`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140001d0f`
- `ntoskrnl!KeStackAttachProcess` at `0x140001d0f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140001d98`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140001d98`
- `ntoskrnl!PsGetCurrentProcess` at `0x140001cec`
- `ntoskrnl!PsGetCurrentProcess` at `0x140001cec`
- `watchdog!WdLogSingleEntry2` at `0x140001d46`
- `watchdog!WdLogSingleEntry2` at `0x140001d46`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140001d5d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140001d5d`

## pseudocode

```c
__int64 __fastcall CDDPDEV::DestroyAllocation(CDDPDEV *this, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rsi
  struct _KPROCESS *v5; // rbx
  int v6; // eax
  _QWORD *v7; // rax
  struct _KAPC_STATE ApcState; // [rsp+20h] [rbp-48h] BYREF
  char v10; // [rsp+50h] [rbp-18h]

  v2 = 0;
  v3 = a2;
  if ( *((_DWORD *)this + 630) )
  {
    v5 = (struct _KPROCESS *)*((_QWORD *)this + 94);
    v10 = 0;
    if ( (struct _KPROCESS *)PsGetCurrentProcess() != v5 && v5 )
    {
      KeStackAttachProcess(v5, &ApcState);
      v10 = 1;
    }
    v6 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))this + 27))(*((unsigned int *)this + 630), (unsigned int)v3);
    v2 = v6;
    if ( v6 < 0 )
    {
      WdLogSingleEntry2(4, v6, v3);
      WdLogGlobalForLineNumber = 1458;
      v7 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v7[3] = gCddImageInfo;
      v7[4] = (unsigned int)dword_14003E570;
      v7[5] = 215857758;
      WdLogGlobalForLineNumber = 1458;
    }
    if ( v10 )
      KeUnstackDetachProcess(&ApcState);
  }
  return v2;
}

```

## disassembly

```asm
0x140001cb4  mov     [rsp+arg_10], rbx
0x140001cb9  mov     [rsp+arg_18], rsi
0x140001cbe  push    rdi
0x140001cbf  sub     rsp, 60h
0x140001cc3  mov     rax, cs:__security_cookie
0x140001cca  xor     rax, rsp
0x140001ccd  mov     [rsp+68h+var_10], rax
0x140001cd2  xor     ebx, ebx
0x140001cd4  mov     esi, edx
0x140001cd6  mov     rdi, rcx
0x140001cd9  cmp     [rcx+9D8h], ebx
0x140001cdf  jz      loc_140001DA4
0x140001ce5  mov     rbx, [rcx+2F0h]
0x140001cec  call    cs:__imp_PsGetCurrentProcess
0x140001cf3  nop     dword ptr [rax+rax+00h]
0x140001cf8  mov     [rsp+68h+var_18], 0
0x140001cfd  cmp     rax, rbx
0x140001d00  jz      short loc_140001D20
0x140001d02  test    rbx, rbx
0x140001d05  jz      short loc_140001D20
0x140001d07  lea     rdx, [rsp+68h+ApcState]; ApcState
0x140001d0c  mov     rcx, rbx; PROCESS
0x140001d0f  call    cs:__imp_KeStackAttachProcess
0x140001d16  nop     dword ptr [rax+rax+00h]
0x140001d1b  mov     [rsp+68h+var_18], 1
0x140001d20  mov     rax, [rdi+0D8h]
0x140001d27  mov     edx, esi
0x140001d29  mov     ecx, [rdi+9D8h]
0x140001d2f  call    _guard_dispatch_icall
0x140001d34  movsxd  rbx, eax
0x140001d37  test    eax, eax
0x140001d39  jns     short loc_140001D8C
0x140001d3b  mov     r8, rsi
0x140001d3e  mov     rdx, rbx
0x140001d41  mov     ecx, 4
0x140001d46  call    cs:__imp_WdLogSingleEntry2
0x140001d4d  nop     dword ptr [rax+rax+00h]
0x140001d52  mov     edi, 5B2h
0x140001d57  mov     cs:WdLogGlobalForLineNumber, edi
0x140001d5d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140001d64  nop     dword ptr [rax+rax+00h]
0x140001d69  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140001d70  mov     [rax+18h], rcx
0x140001d74  mov     ecx, cs:dword_14003E570
0x140001d7a  mov     [rax+20h], rcx
0x140001d7e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140001d86  mov     cs:WdLogGlobalForLineNumber, edi
0x140001d8c  cmp     [rsp+68h+var_18], 0
0x140001d91  jz      short loc_140001DA4
0x140001d93  lea     rcx, [rsp+68h+ApcState]; ApcState
0x140001d98  call    cs:__imp_KeUnstackDetachProcess
0x140001d9f  nop     dword ptr [rax+rax+00h]
0x140001da4  mov     eax, ebx
0x140001da6  mov     rcx, [rsp+68h+var_10]
0x140001dab  xor     rcx, rsp; StackCookie
0x140001dae  call    __security_check_cookie
0x140001db3  lea     r11, [rsp+68h+var_8]
0x140001db8  mov     rbx, [r11+20h]
0x140001dbc  mov     rsi, [r11+28h]
0x140001dc0  mov     rsp, r11
0x140001dc3  pop     rdi
0x140001dc4  retn
```
