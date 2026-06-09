# DusmNduTracker::NduByteLimitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18003da80`
- end: `0x18003db49`
- name: `?NduByteLimitCallback@DusmNduTracker@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `201`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001db50`
- `0x18002f510`
- `0x18003da80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003db42`

## pseudocode

```c
void __fastcall DusmNduTracker::NduByteLimitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int128 v5; // xmm0
  int v6; // eax
  int v7; // r8d
  __int64 v8; // rdx
  __int64 (__fastcall **v9)(); // [rsp+80h] [rbp-48h] BYREF
  __int128 v10; // [rsp+88h] [rbp-40h]
  int v11; // [rsp+98h] [rbp-30h]
  int v12; // [rsp+9Ch] [rbp-2Ch]
  __int64 (__fastcall ***v13)(); // [rsp+B8h] [rbp-10h]

  v5 = *(_OWORD *)(Context + 24);
  v6 = *((_DWORD *)Context + 28);
  v7 = *((_DWORD *)Context + 29);
  if ( v7 && v6 )
  {
    ++*((_QWORD *)Context + 15);
    v6 = *((_QWORD *)Context + 15) == 5 * (*((_QWORD *)Context + 15) / 5uLL);
  }
  v9 = off_18004CE48;
  v10 = v5;
  v11 = v6;
  v12 = v7;
  v13 = &v9;
  DusmAsync::SubmitOrderedWork((__int64)&v9);
  std::function<long (void)>::~function<long (void)>((__int64)&v9, v8);
  SetThreadpoolWait(Wait, *((HANDLE *)Context + 1), 0);
}

```

## disassembly

```asm
0x18003da80  mov     [rsp+arg_10], r8
0x18003da85  mov     [rsp+arg_8], rdx
0x18003da8a  push    rbx
0x18003da8b  sub     rsp, 0C0h
0x18003da92  mov     rbx, rdx
0x18003da95  movups  xmm0, xmmword ptr [rdx+18h]
0x18003da99  mov     eax, [rdx+70h]
0x18003da9c  mov     r8d, [rdx+74h]
0x18003daa0  test    r8d, r8d
0x18003daa3  jz      short loc_18003DACF
0x18003daa5  test    eax, eax
0x18003daa7  jz      short loc_18003DACF
0x18003daa9  inc     qword ptr [rdx+78h]
0x18003daad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003dab7  mul     qword ptr [rdx+78h]
0x18003dabb  shr     rdx, 2
0x18003dabf  lea     rax, [rdx+rdx*4]
0x18003dac3  cmp     [rbx+78h], rax
0x18003dac7  mov     eax, 0
0x18003dacc  setz    al
0x18003dacf  lea     rcx, off_18004CE48
0x18003dad6  mov     [rsp+0C8h+var_48], rcx
0x18003dade  movdqu  [rsp+0C8h+var_40], xmm0
0x18003dae7  mov     [rsp+0C8h+var_30], eax
0x18003daee  mov     [rsp+0C8h+var_2C], r8d
0x18003daf6  lea     rax, [rsp+0C8h+var_48]
0x18003dafe  mov     [rsp+0C8h+var_10], rax
0x18003db06  lea     rcx, [rsp+0C8h+var_48]
0x18003db0e  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x18003db13  lea     rcx, [rsp+0C8h+var_48]
0x18003db1b  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18003db20  nop
0x18003db21  jmp     short loc_18003DB2B
0x18003db23  mov     rbx, [rsp+0C8h+arg_8]
0x18003db2b  xor     r8d, r8d
0x18003db2e  mov     rdx, [rbx+8]
0x18003db32  mov     rcx, [rsp+0C8h+arg_10]
0x18003db3a  add     rsp, 0C0h
0x18003db41  pop     rbx
0x18003db42  jmp     cs:__imp_SetThreadpoolWait
```
