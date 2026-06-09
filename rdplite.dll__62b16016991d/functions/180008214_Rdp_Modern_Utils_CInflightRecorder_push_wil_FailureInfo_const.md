# Rdp::Modern::Utils::CInflightRecorder::push(wil::FailureInfo const &)

- ea: `0x180008214`
- end: `0x1800082fd`
- name: `?push@CInflightRecorder@Utils@Modern@Rdp@@QEAAXAEBUFailureInfo@wil@@@Z`
- size: `233`
- prototype: `void(Rdp::Modern::Utils::CInflightRecorder *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007f80`

## callees

- `0x180008214`
- `0x180008304`
- `0x1800086b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000828e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000828e`

## pseudocode

```c
void __fastcall Rdp::Modern::Utils::CInflightRecorder::push(
        Rdp::Modern::Utils::CInflightRecorder *this,
        const struct wil::FailureInfo *a2)
{
  bool v3; // r15
  int v4; // ebp
  int v5; // esi
  __int64 v6; // r14
  __int64 v7; // rdi
  int v8; // ebx
  char CurrentThreadId; // al
  const wchar_t *v10; // rcx
  int v11; // [rsp+20h] [rbp-98h]
  int v12; // [rsp+28h] [rbp-90h]
  int v13; // [rsp+30h] [rbp-88h]
  __int64 v14; // [rsp+38h] [rbp-80h]

  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = *((_DWORD *)a2 + 16);
    v5 = *((_DWORD *)a2 + 1) & 8;
    v6 = *((_QWORD *)a2 + 7);
    v7 = *((_QWORD *)a2 + 3);
    v8 = *(_DWORD *)((char *)a2 + (v5 != 0 ? 4 : 0) + 8);
    CurrentThreadId = GetCurrentThreadId();
    v10 = L"status";
    if ( !v5 )
      v10 = (const wchar_t *)L"hr";
    WPP_RECORDER_AND_TRACE_SF_DSSDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v12,
      v13,
      v14,
      CurrentThreadId,
      v7,
      (__int64)v10,
      v8,
      v6,
      v4);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushInternal(this, a2);
}

```

## disassembly

```asm
0x180008214  mov     [rsp+arg_0], rcx
0x180008219  push    rbx
0x18000821a  push    rbp
0x18000821b  push    rsi
0x18000821c  push    rdi
0x18000821d  push    r12
0x18000821f  push    r13
0x180008221  push    r14
0x180008223  push    r15
0x180008225  sub     rsp, 78h
0x180008229  mov     r13, rdx
0x18000822c  mov     rax, cs:WPP_GLOBAL_Control
0x180008233  lea     rcx, WPP_GLOBAL_Control
0x18000823a  cmp     rax, rcx
0x18000823d  jz      short loc_180008250
0x18000823f  test    byte ptr [rax+1Ch], 4
0x180008243  jz      short loc_180008250
0x180008245  cmp     byte ptr [rax+19h], 4
0x180008249  jb      short loc_180008250
0x18000824b  mov     r15b, 1
0x18000824e  jmp     short loc_180008253
0x180008250  xor     r15b, r15b
0x180008253  lea     rax, WPP_RECORDER_INITIALIZED
0x18000825a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180008261  setnz   r12b
0x180008265  test    r15b, r15b
0x180008268  jnz     short loc_18000826F
0x18000826a  test    r12b, r12b
0x18000826d  jz      short loc_1800082DD
0x18000826f  mov     esi, [rdx+4]
0x180008272  mov     ebp, [rdx+40h]
0x180008275  and     esi, 8
0x180008278  mov     r14, [rdx+38h]
0x18000827c  mov     eax, esi
0x18000827e  mov     rdi, [rdx+18h]
0x180008282  neg     eax
0x180008284  sbb     rcx, rcx
0x180008287  and     ecx, 4
0x18000828a  mov     ebx, [rcx+rdx+8]
0x18000828e  call    cs:__imp_GetCurrentThreadId
0x180008294  mov     dword ptr [rsp+0B8h+var_50], ebp; char
0x180008298  lea     rdx, aHr; "hr"
0x18000829f  mov     [rsp+0B8h+var_58], r14; __int64
0x1800082a4  lea     rcx, aStatus; "status"
0x1800082ab  mov     dword ptr [rsp+0B8h+var_60], ebx; char
0x1800082af  test    esi, esi
0x1800082b1  mov     r8b, r12b
0x1800082b4  cmovz   rcx, rdx
0x1800082b8  mov     dl, r15b
0x1800082bb  mov     [rsp+0B8h+var_68], rcx; __int64
0x1800082c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082c7  mov     [rsp+0B8h+var_70], rdi; __int64
0x1800082cc  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x1800082d0  mov     r9, [rcx+28h]
0x1800082d4  mov     rcx, [rcx+10h]; LoggerHandle
0x1800082d8  call    WPP_RECORDER_AND_TRACE_SF_DSSDsd
0x1800082dd  mov     rcx, [rsp+0B8h+arg_0]; this
0x1800082e5  mov     rdx, r13; struct wil::FailureInfo *
0x1800082e8  add     rsp, 78h
0x1800082ec  pop     r15
0x1800082ee  pop     r14
0x1800082f0  pop     r13
0x1800082f2  pop     r12
0x1800082f4  pop     rdi
0x1800082f5  pop     rsi
0x1800082f6  pop     rbp
0x1800082f7  pop     rbx
0x1800082f8  jmp     ?pushInternal@CInflightRecorder@Utils@Modern@Rdp@@AEAAXAEBUFailureInfo@wil@@@Z; Rdp::Modern::Utils::CInflightRecorder::pushInternal(wil::FailureInfo const &)
```
