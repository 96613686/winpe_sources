# TimerQRemove

- ea: `0x180020260`
- end: `0x1800203d1`
- name: `TimerQRemove`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a130`
- `0x18001fe70`
- `0x18002b500`
- `0x18002c440`
- `0x18002d0f0`
- `0x18002ddd0`
- `0x18002e1e0`
- `0x18002e3e0`
- `0x18002e940`
- `0x18003f2e0`
- `0x180046b10`
- `0x18004c360`

## callees

- `0x180007c0c`
- `0x180020260`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180020321`
- `KERNEL32!LeaveCriticalSection` at `0x180020389`
- `KERNEL32!LeaveCriticalSection` at `0x180020321`
- `KERNEL32!LeaveCriticalSection` at `0x180020389`
- `KERNEL32!EnterCriticalSection` at `0x1800202e6`
- `KERNEL32!EnterCriticalSection` at `0x1800202e6`
- `KERNEL32!HeapFree` at `0x1800203a1`
- `KERNEL32!HeapFree` at `0x1800203a1`

## string_xrefs

- `0x180020294`: `TimerQRemove called`

## pseudocode

```c
void __fastcall TimerQRemove(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-28h]
  int v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+4Ch] [rbp-1Ch]

  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( aTimerqremoveCa[v5] );
    v9 = L"TimerQRemove called";
    v10 = 2 * v5 + 2;
    v11 = 0;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      a3,
      2u,
      &v8);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800D07D0 + 1));
  v6 = xmmword_1800D07D0;
  if ( xmmword_1800D07D0 )
  {
    do
    {
      if ( v6[2] == a2 && v6[3] == a1 )
        break;
      v6 = (_QWORD *)*v6;
    }
    while ( v6 );
  }
  if ( v6 )
  {
    if ( v6 == xmmword_1800D07D0 )
    {
      v7 = (_QWORD *)*v6;
      xmmword_1800D07D0 = v7;
      if ( v7 )
      {
        v7[1] = 0;
        *((_DWORD *)xmmword_1800D07D0 + 8) += *((_DWORD *)v6 + 8);
      }
    }
    else if ( *v6 )
    {
      *(_DWORD *)(*v6 + 32LL) += *((_DWORD *)v6 + 8);
      *(_QWORD *)v6[1] = *v6;
      *(_QWORD *)(*v6 + 8LL) = v6[1];
    }
    else
    {
      *(_QWORD *)v6[1] = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800D07D0 + 1));
    HeapFree(hHeap, 0, v6);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800D07D0 + 1));
  }
}

```

## disassembly

```asm
0x180020260  mov     [rsp+arg_0], rbx
0x180020265  mov     [rsp+arg_8], rbp
0x18002026a  mov     [rsp+arg_10], rsi
0x18002026f  push    rdi
0x180020270  sub     rsp, 60h
0x180020274  mov     rax, cs:__security_cookie
0x18002027b  xor     rax, rsp
0x18002027e  mov     [rsp+68h+var_18], rax
0x180020283  xor     ebp, ebp
0x180020285  mov     rdi, rdx
0x180020288  test    cs:byte_1800CF404, 10h
0x18002028f  mov     rsi, rcx
0x180020292  jz      short loc_1800202DF
0x180020294  lea     rcx, aTimerqremoveCa; "TimerQRemove called"
0x18002029b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002029f  inc     rax
0x1800202a2  cmp     [rcx+rax*2], bp
0x1800202a6  jnz     short loc_18002029F
0x1800202a8  lea     eax, ds:2[rax*2]
0x1800202af  mov     [rsp+68h+var_28], rcx
0x1800202b4  mov     [rsp+68h+var_20], eax
0x1800202b8  lea     rdx, RasDdmTraceInfo
0x1800202bf  lea     rax, [rsp+68h+var_38]
0x1800202c4  mov     [rsp+68h+var_1C], ebp
0x1800202c8  mov     r9d, 2
0x1800202ce  mov     [rsp+68h+var_48], rax
0x1800202d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800202da  call    McGenEventWrite_EventWriteTransfer
0x1800202df  lea     rcx, xmmword_1800D07D0+8; lpCriticalSection
0x1800202e6  call    cs:__imp_EnterCriticalSection
0x1800202ed  nop     dword ptr [rax+rax+00h]
0x1800202f2  mov     rax, qword ptr cs:xmmword_1800D07D0
0x1800202f9  mov     rbx, rax
0x1800202fc  test    rax, rax
0x1800202ff  jz      short loc_180020315
0x180020301  cmp     [rbx+10h], rdi
0x180020305  jnz     short loc_18002030D
0x180020307  cmp     [rbx+18h], rsi
0x18002030b  jz      short loc_180020315
0x18002030d  mov     rbx, [rbx]
0x180020310  test    rbx, rbx
0x180020313  jnz     short loc_180020301
0x180020315  test    rbx, rbx
0x180020318  jnz     short loc_18002032F
0x18002031a  lea     rcx, xmmword_1800D07D0+8; lpCriticalSection
0x180020321  call    cs:__imp_LeaveCriticalSection
0x180020328  nop     dword ptr [rax+rax+00h]
0x18002032d  jmp     short loc_1800203AD
0x18002032f  cmp     rbx, rax
0x180020332  jnz     short loc_180020356
0x180020334  mov     rax, [rbx]
0x180020337  mov     qword ptr cs:xmmword_1800D07D0, rax
0x18002033e  test    rax, rax
0x180020341  jz      short loc_180020382
0x180020343  mov     [rax+8], rbp
0x180020347  mov     rcx, qword ptr cs:xmmword_1800D07D0
0x18002034e  mov     eax, [rbx+20h]
0x180020351  add     [rcx+20h], eax
0x180020354  jmp     short loc_180020382
0x180020356  mov     rcx, [rbx]
0x180020359  test    rcx, rcx
0x18002035c  jnz     short loc_180020367
0x18002035e  mov     rax, [rbx+8]
0x180020362  mov     [rax], rbp
0x180020365  jmp     short loc_180020382
0x180020367  mov     eax, [rbx+20h]
0x18002036a  add     [rcx+20h], eax
0x18002036d  mov     rcx, [rbx+8]
0x180020371  mov     rax, [rbx]
0x180020374  mov     [rcx], rax
0x180020377  mov     rcx, [rbx]
0x18002037a  mov     rax, [rbx+8]
0x18002037e  mov     [rcx+8], rax
0x180020382  lea     rcx, xmmword_1800D07D0+8; lpCriticalSection
0x180020389  call    cs:__imp_LeaveCriticalSection
0x180020390  nop     dword ptr [rax+rax+00h]
0x180020395  mov     rcx, cs:hHeap; hHeap
0x18002039c  mov     r8, rbx; lpMem
0x18002039f  xor     edx, edx; dwFlags
0x1800203a1  call    cs:__imp_HeapFree
0x1800203a8  nop     dword ptr [rax+rax+00h]
0x1800203ad  mov     rcx, [rsp+68h+var_18]
0x1800203b2  xor     rcx, rsp; StackCookie
0x1800203b5  call    __security_check_cookie
0x1800203ba  lea     r11, [rsp+68h+var_8]
0x1800203bf  mov     rbx, [r11+10h]
0x1800203c3  mov     rbp, [r11+18h]
0x1800203c7  mov     rsi, [r11+20h]
0x1800203cb  mov     rsp, r11
0x1800203ce  pop     rdi
0x1800203cf  retn
```
