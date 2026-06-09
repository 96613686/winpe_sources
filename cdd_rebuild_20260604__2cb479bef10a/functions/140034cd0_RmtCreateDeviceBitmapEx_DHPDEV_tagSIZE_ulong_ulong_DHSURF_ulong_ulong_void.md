# RmtCreateDeviceBitmapEx(DHPDEV__ *,tagSIZE,ulong,ulong,DHSURF__ *,ulong,ulong,void * *)

- ea: `0x140034cd0`
- end: `0x140034e46`
- name: `?RmtCreateDeviceBitmapEx@@YAPEAUHBITMAP__@@PEAUDHPDEV__@@UtagSIZE@@KKPEAUDHSURF__@@KKPEAPEAX@Z`
- size: `374`
- prototype: `HBITMAP __fastcall(struct DHPDEV__ *, struct tagSIZE, unsigned int, unsigned int, struct DHSURF__ *, unsigned int, unsigned int, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14003461c`
- `0x140034cd0`
- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140034ced`
- `WIN32K!W32GetSessionState` at `0x140034d17`
- `WIN32K!W32GetSessionState` at `0x140034d8e`
- `WIN32K!W32GetSessionState` at `0x140034dcd`
- `WIN32K!W32GetSessionState` at `0x140034de6`
- `WIN32K!W32GetSessionState` at `0x140034ced`
- `WIN32K!W32GetSessionState` at `0x140034d17`
- `WIN32K!W32GetSessionState` at `0x140034d8e`
- `WIN32K!W32GetSessionState` at `0x140034dcd`
- `WIN32K!W32GetSessionState` at `0x140034de6`

## pseudocode

```c
HBITMAP __fastcall RmtCreateDeviceBitmapEx(
        struct DHPDEV__ *a1,
        struct tagSIZE a2,
        unsigned int a3,
        unsigned int a4,
        struct DHSURF__ *a5,
        unsigned int a6,
        unsigned int a7,
        void **a8)
{
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 SessionState; // rax
  HBITMAP result; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 (__fastcall *v18)(_QWORD, struct tagSIZE, _QWORD, _QWORD, struct DHSURF__ *, unsigned int, unsigned int, void **); // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(_QWORD, struct tagSIZE, _QWORD, _QWORD, struct DHSURF__ *, unsigned int, unsigned int, void **); // rax

  v12 = *(_QWORD *)(((__int64 (__fastcall *)(_QWORD, _QWORD))W32GetSessionState)(a1, a2) + 72);
  if ( *(_BYTE *)(v12 + 3336) )
  {
    v20 = *(_QWORD *)(W32GetSessionState(v13, v12) + 72);
    if ( *(_QWORD *)(v20 + 1592) )
    {
      v21 = *(__int64 (__fastcall **)(_QWORD, struct tagSIZE, _QWORD, _QWORD, struct DHSURF__ *, unsigned int, unsigned int, void **))(*(_QWORD *)(W32GetSessionState(v20, v19) + 72) + 1592LL);
      return (HBITMAP)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))v21)(
                        *(_QWORD *)a1,
                        a2,
                        a3,
                        a4,
                        a5,
                        a6,
                        a7,
                        a8);
    }
    return 0;
  }
  if ( !*((_QWORD *)a1 + 1) )
    return 0;
  SessionState = W32GetSessionState(v13, v12);
  result = (HBITMAP)(*(__int64 (__fastcall **)(_QWORD, struct tagSIZE, _QWORD, _QWORD, struct DHSURF__ *, unsigned int, unsigned int, void **))(*(_QWORD *)(SessionState + 72) + 760LL))(
                      *((_QWORD *)a1 + 1),
                      a2,
                      a3,
                      a4,
                      a5,
                      a6,
                      a7,
                      a8);
  if ( result )
    return result;
  if ( (int)CddTryTDRRecovery(*((struct DHPDEV__ **)a1 + 1)) < 0 )
    return 0;
  v18 = *(__int64 (__fastcall **)(_QWORD, struct tagSIZE, _QWORD, _QWORD, struct DHSURF__ *, unsigned int, unsigned int, void **))(*(_QWORD *)(W32GetSessionState(v17, v16) + 72) + 760LL);
  return (HBITMAP)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))v18)(
                    *((_QWORD *)a1 + 1),
                    a2,
                    a3,
                    a4,
                    a5,
                    a6,
                    a7,
                    a8);
}

```

## disassembly

```asm
0x140034cd0  push    rbx
0x140034cd2  push    rbp
0x140034cd3  push    rsi
0x140034cd4  push    rdi
0x140034cd5  push    r12
0x140034cd7  push    r13
0x140034cd9  push    r14
0x140034cdb  push    r15
0x140034cdd  sub     rsp, 58h
0x140034ce1  mov     esi, r9d
0x140034ce4  mov     ebp, r8d
0x140034ce7  mov     rbx, rdx
0x140034cea  mov     rdi, rcx
0x140034ced  call    cs:__imp_W32GetSessionState
0x140034cf4  nop     dword ptr [rax+rax+00h]
0x140034cf9  xor     r14d, r14d
0x140034cfc  mov     rdx, [rax+48h]
0x140034d00  cmp     [rdx+0D08h], r14b
0x140034d07  jnz     loc_140034DCD
0x140034d0d  cmp     [rdi+8], r14
0x140034d11  jz      loc_140034E32
0x140034d17  call    cs:__imp_W32GetSessionState
0x140034d1e  nop     dword ptr [rax+rax+00h]
0x140034d23  mov     r14, [rsp+98h+arg_38]
0x140034d2b  mov     r9d, esi
0x140034d2e  mov     r15d, [rsp+98h+arg_30]
0x140034d36  mov     r8d, ebp
0x140034d39  mov     r12d, [rsp+98h+arg_28]
0x140034d41  mov     rdx, rbx
0x140034d44  mov     rcx, [rax+48h]
0x140034d48  mov     r13, [rsp+98h+arg_20]
0x140034d50  mov     [rsp+98h+var_60], r14
0x140034d55  mov     [rsp+98h+var_68], r15d
0x140034d5a  mov     rax, [rcx+2F8h]
0x140034d61  mov     rcx, [rdi+8]
0x140034d65  mov     [rsp+98h+var_70], r12d
0x140034d6a  mov     [rsp+98h+var_78], r13
0x140034d6f  call    _guard_dispatch_icall
0x140034d74  test    rax, rax
0x140034d77  jnz     loc_140034E34
0x140034d7d  mov     rcx, [rdi+8]; struct DHPDEV__ *
0x140034d81  call    ?CddTryTDRRecovery@@YAJPEAUDHPDEV__@@@Z; CddTryTDRRecovery(DHPDEV__ *)
0x140034d86  test    eax, eax
0x140034d88  js      loc_140034E32
0x140034d8e  call    cs:__imp_W32GetSessionState
0x140034d95  nop     dword ptr [rax+rax+00h]
0x140034d9a  mov     [rsp+98h+var_60], r14
0x140034d9f  mov     [rsp+98h+var_68], r15d
0x140034da4  mov     [rsp+98h+var_70], r12d
0x140034da9  mov     rcx, [rax+48h]
0x140034dad  mov     [rsp+98h+var_78], r13
0x140034db2  mov     rax, [rcx+2F8h]
0x140034db9  mov     rcx, [rdi+8]
0x140034dbd  mov     rdx, rbx
0x140034dc0  mov     r8d, ebp
0x140034dc3  mov     r9d, esi
0x140034dc6  call    _guard_dispatch_icall
0x140034dcb  jmp     short loc_140034E34
0x140034dcd  call    cs:__imp_W32GetSessionState
0x140034dd4  nop     dword ptr [rax+rax+00h]
0x140034dd9  mov     rcx, [rax+48h]
0x140034ddd  cmp     [rcx+638h], r14
0x140034de4  jz      short loc_140034E32
0x140034de6  call    cs:__imp_W32GetSessionState
0x140034ded  nop     dword ptr [rax+rax+00h]
0x140034df2  mov     rcx, [rax+48h]
0x140034df6  mov     rax, [rcx+638h]
0x140034dfd  mov     rcx, [rsp+98h+arg_38]
0x140034e05  mov     [rsp+98h+var_60], rcx
0x140034e0a  mov     ecx, [rsp+98h+arg_30]
0x140034e11  mov     [rsp+98h+var_68], ecx
0x140034e15  mov     ecx, [rsp+98h+arg_28]
0x140034e1c  mov     [rsp+98h+var_70], ecx
0x140034e20  mov     rcx, [rsp+98h+arg_20]
0x140034e28  mov     [rsp+98h+var_78], rcx
0x140034e2d  mov     rcx, [rdi]
0x140034e30  jmp     short loc_140034DBD
0x140034e32  xor     eax, eax
0x140034e34  add     rsp, 58h
0x140034e38  pop     r15
0x140034e3a  pop     r14
0x140034e3c  pop     r13
0x140034e3e  pop     r12
0x140034e40  pop     rdi
0x140034e41  pop     rsi
0x140034e42  pop     rbp
0x140034e43  pop     rbx
0x140034e44  retn
```
