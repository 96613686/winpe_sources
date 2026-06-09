# ThreadPool_CreateIo

- ea: `0x1800245a0`
- end: `0x18002466c`
- name: `ThreadPool_CreateIo`
- size: `204`
- prototype: `__int64 __usercall@<rax>(HANDLE fl@<rcx>, PTP_WIN32_IO_CALLBACK pfnio@<rdx>, PVOID pv@<r8>, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800241a4`
- `0x180039328`
- `0x180068b34`

## callees

- `0x1800245a0`
- `0x1800dfa80`
- `0x1800e1ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002461e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002461e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800245f8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800245f8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800245db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800245db`

## pseudocode

```c
__int64 __fastcall ThreadPool_CreateIo(HANDLE fl, PTP_WIN32_IO_CALLBACK pfnio, PVOID pv, int a4, struct _TP_IO **a5)
{
  struct _TP_IO *ThreadpoolIo; // rax
  struct _TP_IO *v10; // rdi
  DWORD LastError; // ebx

  *a5 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qql((_DWORD)fl, 16, (unsigned int)WPP_0ee542721a7b375122a881c30985be4a_Traceguids, (_DWORD)fl, (__int64)pv);
  ThreadpoolIo = CreateThreadpoolIo(fl, pfnio, pv, 0);
  v10 = ThreadpoolIo;
  if ( ThreadpoolIo )
  {
    LastError = 0;
    if ( a4 )
      StartThreadpoolIo(ThreadpoolIo);
    *a5 = v10;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 17, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, *a5, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800245a0  push    rbx
0x1800245a2  push    rbp
0x1800245a3  push    rsi
0x1800245a4  push    rdi
0x1800245a5  push    r14
0x1800245a7  sub     rsp, 30h
0x1800245ab  mov     rsi, [rsp+58h+arg_20]
0x1800245b3  mov     ebp, r9d
0x1800245b6  mov     rbx, r8
0x1800245b9  mov     r14, rdx
0x1800245bc  mov     rdi, rcx
0x1800245bf  mov     qword ptr [rsi], 0
0x1800245c6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800245cd  jnz     short loc_18002462E
0x1800245cf  xor     r9d, r9d; pcbe
0x1800245d2  mov     r8, rbx; pv
0x1800245d5  mov     rdx, r14; pfnio
0x1800245d8  mov     rcx, rdi; fl
0x1800245db  call    cs:__imp_CreateThreadpoolIo
0x1800245e2  nop     dword ptr [rax+rax+00h]
0x1800245e7  mov     rdi, rax
0x1800245ea  test    rax, rax
0x1800245ed  jz      short loc_18002461E
0x1800245ef  xor     ebx, ebx
0x1800245f1  test    ebp, ebp
0x1800245f3  jz      short loc_180024604
0x1800245f5  mov     rcx, rax; pio
0x1800245f8  call    cs:__imp_StartThreadpoolIo
0x1800245ff  nop     dword ptr [rax+rax+00h]
0x180024604  mov     [rsi], rdi
0x180024607  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18002460e  jnz     short loc_18002464D
0x180024610  mov     eax, ebx
0x180024612  add     rsp, 30h
0x180024616  pop     r14
0x180024618  pop     rdi
0x180024619  pop     rsi
0x18002461a  pop     rbp
0x18002461b  pop     rbx
0x18002461c  retn
0x18002461e  call    cs:__imp_GetLastError
0x180024625  nop     dword ptr [rax+rax+00h]
0x18002462a  mov     ebx, eax
0x18002462c  jmp     short loc_180024607
0x18002462e  mov     edx, 10h
0x180024633  mov     [rsp+58h+var_30], ebp
0x180024637  mov     r9, rdi
0x18002463a  mov     [rsp+58h+var_38], rbx
0x18002463f  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180024646  call    WPP_SF_qql
0x18002464b  jmp     short loc_1800245CF
0x18002464d  mov     r9, [rsi]
0x180024650  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180024657  mov     edx, 11h
0x18002465c  mov     dword ptr [rsp+58h+var_38], ebx
0x180024660  mov     ecx, 40Bh
0x180024665  call    WPP_SF_qD
0x18002466a  jmp     short loc_180024610
```
