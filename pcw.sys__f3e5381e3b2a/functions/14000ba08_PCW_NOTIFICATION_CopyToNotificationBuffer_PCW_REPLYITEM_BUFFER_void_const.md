# PCW_NOTIFICATION::CopyToNotificationBuffer(PCW_REPLYITEM_BUFFER *,void const *)

- ea: `0x14000ba08`
- end: `0x14000bba8`
- name: `?CopyToNotificationBuffer@PCW_NOTIFICATION@@AEAAJPEAUPCW_REPLYITEM_BUFFER@@PEBX@Z`
- size: `416`
- prototype: `__int64 __fastcall(PCW_NOTIFICATION *this, struct PCW_REPLYITEM_BUFFER *, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b76c`

## callees

- `0x140001370`
- `0x140008008`
- `0x14000ba08`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14000bb3b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000bb3b`
- `ntoskrnl!MmCopyVirtualMemory` at `0x14000bb68`
- `ntoskrnl!MmCopyVirtualMemory` at `0x14000bb68`
- `ntoskrnl!KeStackAttachProcess` at `0x14000bac0`
- `ntoskrnl!KeStackAttachProcess` at `0x14000bac0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000bb12`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000bb12`

## pseudocode

```c
__int64 __fastcall PCW_NOTIFICATION::CopyToNotificationBuffer(
        PCW_NOTIFICATION *this,
        struct PCW_REPLYITEM_BUFFER *a2,
        const void *a3)
{
  unsigned int *v6; // r12
  unsigned int v7; // eax
  unsigned int v8; // ecx
  unsigned int *v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // r14d
  __int64 v12; // r12
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 CurrentProcess; // rax
  __int64 result; // rax
  __int64 v17; // [rsp+70h] [rbp-78h] BYREF
  _KAPC_STATE ApcState; // [rsp+78h] [rbp-70h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  v17 = 0;
  v6 = (unsigned int *)((char *)a2 + 4);
  v7 = *((_DWORD *)a2 + 1);
  if ( v7 > 0xFFFFFFF8 )
    return 3221225621LL;
  v8 = ((v7 + 7) & 0xFFFFFFF8) + 16;
  if ( v8 < 0x10 )
    return 3221225621LL;
  *(_DWORD *)a2 = v8;
  v9 = (unsigned int *)((char *)this + 64);
  v10 = *((_DWORD *)this + 16);
  v11 = v10 + v8;
  if ( v10 + v8 < v10 )
    return 3221225621LL;
  if ( v11 > *((_DWORD *)this + 15) )
    goto LABEL_7;
  KeStackAttachProcess(*((PRKPROCESS *)this + 4), &ApcState);
  RtlCopyToUser((void *)(*((_QWORD *)this + 6) + *v9), a2, 0x10u);
  KeUnstackDetachProcess(&ApcState);
  v12 = *v6;
  if ( !(_DWORD)v12
    || (v13 = *v9 + *((_QWORD *)this + 6),
        v14 = *((_QWORD *)this + 4),
        CurrentProcess = PsGetCurrentProcess(),
        result = MmCopyVirtualMemory(CurrentProcess, a3, v14, v13 + 16, v12, 0, &v17),
        (int)result >= 0) )
  {
LABEL_7:
    *v9 = v11;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000ba08  mov     r11, rsp
0x14000ba0b  push    rbx
0x14000ba0c  push    rsi
0x14000ba0d  push    rdi
0x14000ba0e  push    r12
0x14000ba10  push    r13
0x14000ba12  push    r14
0x14000ba14  push    r15
0x14000ba16  sub     rsp, 0B0h
0x14000ba1d  mov     rax, cs:__security_cookie
0x14000ba24  xor     rax, rsp
0x14000ba27  mov     [rsp+0E8h+var_40], rax
0x14000ba2f  mov     r13, r8
0x14000ba32  mov     rbx, rdx
0x14000ba35  mov     rdi, rcx
0x14000ba38  mov     [rsp+0E8h+var_A0], rcx
0x14000ba3d  mov     [rsp+0E8h+var_98], r8
0x14000ba42  xorps   xmm0, xmm0
0x14000ba45  movups  xmmword ptr [rsp+0E8h+ApcState.ApcListHead.Flink], xmm0
0x14000ba4a  movups  xmmword ptr [r11-60h], xmm0
0x14000ba4f  movups  xmmword ptr [r11-50h], xmm0
0x14000ba54  mov     qword ptr [r11-78h], 0
0x14000ba5c  lea     r12, [rdx+4]
0x14000ba60  mov     [rsp+0E8h+var_90], r12
0x14000ba65  mov     eax, [r12]
0x14000ba69  mov     ecx, 0FFFFFFF8h
0x14000ba6e  cmp     eax, ecx
0x14000ba70  ja      loc_14000BB7F
0x14000ba76  add     eax, 7
0x14000ba79  and     ecx, eax
0x14000ba7b  add     ecx, 10h
0x14000ba7e  cmp     ecx, 10h
0x14000ba81  jb      loc_14000BB7F
0x14000ba87  mov     [rdx], ecx
0x14000ba89  lea     rsi, [rdi+40h]
0x14000ba8d  mov     [rsp+0E8h+var_88], rsi
0x14000ba92  mov     eax, [rsi]
0x14000ba94  lea     r14d, [rax+rcx]
0x14000ba98  mov     [rsp+0E8h+var_A4], r14d
0x14000ba9d  cmp     r14d, eax
0x14000baa0  jb      loc_14000BB7F
0x14000baa6  cmp     r14d, [rdi+3Ch]
0x14000baaa  ja      loc_14000BB78
0x14000bab0  lea     r15, [rdi+20h]
0x14000bab4  mov     [rsp+0E8h+var_80], r15
0x14000bab9  lea     rdx, [r11-70h]; ApcState
0x14000babd  mov     rcx, [r15]; PROCESS
0x14000bac0  call    cs:__imp_KeStackAttachProcess
0x14000bac7  nop     dword ptr [rax+rax+00h]
0x14000bacc  nop
0x14000bacd  mov     ecx, [rsi]
0x14000bacf  add     rcx, [rdi+30h]; void *
0x14000bad3  mov     r8d, 10h; Size
0x14000bad9  mov     rdx, rbx; Src
0x14000badc  call    RtlCopyToUser
0x14000bae1  xor     ebx, ebx
0x14000bae3  mov     [rsp+0E8h+var_A8], ebx
0x14000bae7  jmp     short loc_14000BB0D
0x14000bae9  mov     ebx, eax
0x14000baeb  mov     [rsp+0E8h+var_A8], eax
0x14000baef  mov     rdi, [rsp+0E8h+var_A0]
0x14000baf4  mov     r13, [rsp+0E8h+var_98]
0x14000baf9  mov     r12, [rsp+0E8h+var_90]
0x14000bafe  mov     rsi, [rsp+0E8h+var_88]
0x14000bb03  mov     r15, [rsp+0E8h+var_80]
0x14000bb08  mov     r14d, [rsp+0E8h+var_A4]
0x14000bb0d  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x14000bb12  call    cs:__imp_KeUnstackDetachProcess
0x14000bb19  nop     dword ptr [rax+rax+00h]
0x14000bb1e  test    ebx, ebx
0x14000bb20  jns     short loc_14000BB26
0x14000bb22  mov     eax, ebx
0x14000bb24  jmp     short loc_14000BB84
0x14000bb26  mov     r12d, [r12]
0x14000bb2a  test    r12d, r12d
0x14000bb2d  jz      short loc_14000BB78
0x14000bb2f  mov     ecx, [rsi]
0x14000bb31  mov     rbx, [rdi+30h]
0x14000bb35  add     rbx, rcx
0x14000bb38  mov     rdi, [r15]
0x14000bb3b  call    cs:__imp_PsGetCurrentProcess
0x14000bb42  nop     dword ptr [rax+rax+00h]
0x14000bb47  lea     rdx, [rsp+0E8h+var_78]
0x14000bb4c  mov     [rsp+0E8h+var_B8], rdx
0x14000bb51  mov     [rsp+0E8h+var_C0], 0
0x14000bb56  mov     [rsp+0E8h+var_C8], r12
0x14000bb5b  lea     r9, [rbx+10h]
0x14000bb5f  mov     r8, rdi
0x14000bb62  mov     rdx, r13
0x14000bb65  mov     rcx, rax
0x14000bb68  call    cs:__imp_MmCopyVirtualMemory
0x14000bb6f  nop     dword ptr [rax+rax+00h]
0x14000bb74  test    eax, eax
0x14000bb76  js      short loc_14000BB84
0x14000bb78  mov     [rsi], r14d
0x14000bb7b  xor     eax, eax
0x14000bb7d  jmp     short loc_14000BB84
0x14000bb7f  mov     eax, 0C0000095h
0x14000bb84  mov     rcx, [rsp+0E8h+var_40]
0x14000bb8c  xor     rcx, rsp; StackCookie
0x14000bb8f  call    __security_check_cookie
0x14000bb94  add     rsp, 0B0h
0x14000bb9b  pop     r15
0x14000bb9d  pop     r14
0x14000bb9f  pop     r13
0x14000bba1  pop     r12
0x14000bba3  pop     rdi
0x14000bba4  pop     rsi
0x14000bba5  pop     rbx
0x14000bba6  retn
```
