# TimerQRemove

- ea: `0x18001f5e0`
- end: `0x18001f71d`
- name: `TimerQRemove`
- size: `317`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009f50`
- `0x18001f220`
- `0x180029210`
- `0x18002a200`
- `0x18002af20`
- `0x18002bc70`
- `0x18002c050`
- `0x18002c260`
- `0x18002c7a0`
- `0x18003d960`
- `0x180045a30`
- `0x18004ae50`

## callees

- `0x180007b7c`
- `0x18001f5e0`
- `0x18008c630`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f6d9`
- `KERNEL32!LeaveCriticalSection` at `0x18001f6fa`
- `KERNEL32!LeaveCriticalSection` at `0x18001f6d9`
- `KERNEL32!LeaveCriticalSection` at `0x18001f6fa`
- `KERNEL32!EnterCriticalSection` at `0x18001f649`
- `KERNEL32!EnterCriticalSection` at `0x18001f649`
- `KERNEL32!HeapFree` at `0x18001f6eb`
- `KERNEL32!HeapFree` at `0x18001f6eb`

## string_xrefs

- `0x18001f60e`: `TimerQRemove called`

## pseudocode

```c
void __fastcall TimerQRemove(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-30h] BYREF
  const wchar_t *v8; // [rsp+48h] [rbp-20h]
  __int64 v9; // [rsp+50h] [rbp-18h]

  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v9 = 40;
    v8 = L"TimerQRemove called";
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      a3,
      2u,
      &v7);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800C97D0 + 1));
  v5 = xmmword_1800C97D0;
  if ( !xmmword_1800C97D0 )
    goto LABEL_15;
  do
  {
    if ( v5[2] == a2 && v5[3] == a1 )
      break;
    v5 = (_QWORD *)*v5;
  }
  while ( v5 );
  if ( v5 )
  {
    if ( v5 == xmmword_1800C97D0 )
    {
      v6 = (_QWORD *)*v5;
      xmmword_1800C97D0 = v6;
      if ( v6 )
      {
        v6[1] = 0;
        *((_DWORD *)xmmword_1800C97D0 + 8) += *((_DWORD *)v5 + 8);
      }
    }
    else if ( *v5 )
    {
      *(_DWORD *)(*v5 + 32LL) += *((_DWORD *)v5 + 8);
      *(_QWORD *)v5[1] = *v5;
      *(_QWORD *)(*v5 + 8LL) = v5[1];
    }
    else
    {
      *(_QWORD *)v5[1] = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800C97D0 + 1));
    HeapFree(hHeap, 0, v5);
  }
  else
  {
LABEL_15:
    LeaveCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800C97D0 + 1));
  }
}

```

## disassembly

```asm
0x18001f5e0  mov     r11, rsp
0x18001f5e3  mov     [r11+8], rbx
0x18001f5e7  mov     [r11+10h], rsi
0x18001f5eb  push    rdi
0x18001f5ec  sub     rsp, 60h
0x18001f5f0  mov     rax, cs:__security_cookie
0x18001f5f7  xor     rax, rsp
0x18001f5fa  mov     [rsp+68h+var_10], rax
0x18001f5ff  test    cs:byte_1800C8404, 10h
0x18001f606  mov     rdi, rdx
0x18001f609  mov     rsi, rcx
0x18001f60c  jz      short loc_18001F642
0x18001f60e  lea     rax, aTimerqremoveCa; "TimerQRemove called"
0x18001f615  mov     qword ptr [r11-18h], 28h ; '('
0x18001f61d  mov     [r11-20h], rax
0x18001f621  lea     rdx, RasDdmTraceInfo
0x18001f628  lea     rax, [r11-30h]
0x18001f62c  mov     r9d, 2
0x18001f632  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f639  mov     [r11-48h], rax
0x18001f63d  call    McGenEventWrite_EventWriteTransfer
0x18001f642  lea     rcx, xmmword_1800C97D0+8; lpCriticalSection
0x18001f649  call    cs:__imp_EnterCriticalSection
0x18001f64f  mov     rax, qword ptr cs:xmmword_1800C97D0
0x18001f656  mov     rbx, rax
0x18001f659  test    rax, rax
0x18001f65c  jz      loc_18001F6F3
0x18001f662  cmp     [rbx+10h], rdi
0x18001f666  jnz     short loc_18001F66E
0x18001f668  cmp     [rbx+18h], rsi
0x18001f66c  jz      short loc_18001F676
0x18001f66e  mov     rbx, [rbx]
0x18001f671  test    rbx, rbx
0x18001f674  jnz     short loc_18001F662
0x18001f676  test    rbx, rbx
0x18001f679  jz      short loc_18001F6F3
0x18001f67b  cmp     rbx, rax
0x18001f67e  jnz     short loc_18001F6A6
0x18001f680  mov     rax, [rbx]
0x18001f683  mov     qword ptr cs:xmmword_1800C97D0, rax
0x18001f68a  test    rax, rax
0x18001f68d  jz      short loc_18001F6D2
0x18001f68f  mov     qword ptr [rax+8], 0
0x18001f697  mov     rcx, qword ptr cs:xmmword_1800C97D0
0x18001f69e  mov     eax, [rbx+20h]
0x18001f6a1  add     [rcx+20h], eax
0x18001f6a4  jmp     short loc_18001F6D2
0x18001f6a6  mov     rcx, [rbx]
0x18001f6a9  test    rcx, rcx
0x18001f6ac  jnz     short loc_18001F6B7
0x18001f6ae  mov     rax, [rbx+8]
0x18001f6b2  mov     [rax], rcx
0x18001f6b5  jmp     short loc_18001F6D2
0x18001f6b7  mov     eax, [rbx+20h]
0x18001f6ba  add     [rcx+20h], eax
0x18001f6bd  mov     rdx, [rbx+8]
0x18001f6c1  mov     rax, [rbx]
0x18001f6c4  mov     [rdx], rax
0x18001f6c7  mov     rdx, [rbx]
0x18001f6ca  mov     rax, [rbx+8]
0x18001f6ce  mov     [rdx+8], rax
0x18001f6d2  lea     rcx, xmmword_1800C97D0+8; lpCriticalSection
0x18001f6d9  call    cs:__imp_LeaveCriticalSection
0x18001f6df  mov     rcx, cs:hHeap; hHeap
0x18001f6e6  mov     r8, rbx; lpMem
0x18001f6e9  xor     edx, edx; dwFlags
0x18001f6eb  call    cs:__imp_HeapFree
0x18001f6f1  jmp     short loc_18001F700
0x18001f6f3  lea     rcx, xmmword_1800C97D0+8; lpCriticalSection
0x18001f6fa  call    cs:__imp_LeaveCriticalSection
0x18001f700  mov     rcx, [rsp+68h+var_10]
0x18001f705  xor     rcx, rsp; StackCookie
0x18001f708  call    __security_check_cookie
0x18001f70d  mov     rbx, [rsp+68h+arg_0]
0x18001f712  mov     rsi, [rsp+68h+arg_8]
0x18001f717  add     rsp, 60h
0x18001f71b  pop     rdi
0x18001f71c  retn
```
