# CJob::CreateTrigger(ushort *,ITaskTrigger * *)

- ea: `0x18000d870`
- end: `0x18000d997`
- name: `?CreateTrigger@CJob@@UEAAJPEAGPEAPEAUITaskTrigger@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 *, struct ITaskTrigger **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009448`
- `0x180009ef8`
- `0x18000d780`
- `0x18000d870`
- `0x18000e4a4`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d8ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d8ab`

## pseudocode

```c
__int64 __fastcall CJob::CreateTrigger(CJob *this, unsigned __int16 *a2, struct ITaskTrigger **a3)
{
  unsigned __int16 v6; // r14
  CTrigger *v7; // rax
  struct ITaskTrigger *v8; // rdi
  unsigned int v9; // edx
  int v10; // ebx
  _WORD v12[5]; // [rsp+20h] [rbp-50h] BYREF
  int v13; // [rsp+2Ah] [rbp-46h]
  __int16 v14; // [rsp+2Eh] [rbp-42h]
  WORD wHour; // [rsp+30h] [rbp-40h]
  WORD wMinute; // [rsp+32h] [rbp-3Eh]
  __int64 v17; // [rsp+34h] [rbp-3Ch]
  int v18; // [rsp+3Ch] [rbp-34h]
  int v19; // [rsp+40h] [rbp-30h]
  __int16 v20; // [rsp+44h] [rbp-2Ch]
  __int64 v21; // [rsp+46h] [rbp-2Ah]
  __int16 v22; // [rsp+4Eh] [rbp-22h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  *a3 = 0;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v6 = *((_WORD *)this + 16);
  v12[0] = 48;
  v12[2] = SystemTime.wYear;
  v12[3] = SystemTime.wMonth;
  v12[4] = SystemTime.wDay;
  v13 = 0;
  v14 = 0;
  wHour = SystemTime.wHour;
  wMinute = SystemTime.wMinute;
  v19 = 1;
  v20 = 1;
  v12[1] = v6;
  v17 = 0;
  v18 = 0x10000;
  v21 = 0;
  v22 = 0;
  v7 = (CTrigger *)operator new(0x18u);
  if ( !v7 )
    return 2147942414LL;
  v8 = (struct ITaskTrigger *)CTrigger::CTrigger(v7, v6, this);
  if ( !v8 )
    return 2147942414LL;
  v10 = CDynamicArray<_TASK_TRIGGER>::Add((char *)this + 24, v12);
  if ( v10 >= 0 )
  {
    *((_DWORD *)this + 22) = *((_DWORD *)this + 22) & 0xFFFFFFF | 0xD0000000;
    *a2 = v6;
    *a3 = v8;
  }
  else
  {
    CTrigger::`scalar deleting destructor'((CTrigger *)v8, v9);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d870  push    rbp
0x18000d872  push    rbx
0x18000d873  push    rsi
0x18000d874  push    rdi
0x18000d875  push    r12
0x18000d877  push    r14
0x18000d879  push    r15
0x18000d87b  mov     rbp, rsp
0x18000d87e  sub     rsp, 70h
0x18000d882  mov     rax, cs:__security_cookie
0x18000d889  xor     rax, rsp
0x18000d88c  mov     [rbp+var_10], rax
0x18000d890  mov     rsi, rcx
0x18000d893  mov     qword ptr [r8], 0
0x18000d89a  xorps   xmm0, xmm0
0x18000d89d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000d8a1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000d8a5  mov     r15, r8
0x18000d8a8  mov     r12, rdx
0x18000d8ab  call    cs:__imp_GetLocalTime
0x18000d8b1  movzx   r14d, word ptr [rsi+20h]
0x18000d8b6  mov     eax, 30h ; '0'
0x18000d8bb  mov     [rbp+var_50], ax
0x18000d8bf  movzx   eax, [rbp+SystemTime.wYear]
0x18000d8c3  mov     [rbp+var_4C], ax
0x18000d8c7  movzx   eax, [rbp+SystemTime.wMonth]
0x18000d8cb  mov     [rbp+var_4A], ax
0x18000d8cf  movzx   eax, [rbp+SystemTime.wDay]
0x18000d8d3  mov     [rbp+var_48], ax
0x18000d8d7  xor     eax, eax
0x18000d8d9  mov     [rbp+var_46], eax
0x18000d8dc  mov     [rbp+var_42], ax
0x18000d8e0  movzx   eax, [rbp+SystemTime.wHour]
0x18000d8e4  mov     [rbp+var_40], ax
0x18000d8e8  movzx   eax, [rbp+SystemTime.wMinute]
0x18000d8ec  mov     [rbp+var_3E], ax
0x18000d8f0  mov     eax, 1
0x18000d8f5  mov     [rbp+var_30], eax
0x18000d8f8  mov     [rbp+var_2C], ax
0x18000d8fc  xor     eax, eax
0x18000d8fe  mov     [rbp+var_4E], r14w
0x18000d903  mov     [rbp+var_3C], 0
0x18000d90b  mov     [rbp+var_34], 10000h
0x18000d912  lea     ecx, [rax+18h]; Size
0x18000d915  mov     [rbp+var_2A], rax
0x18000d919  mov     [rbp+var_22], ax
0x18000d91d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d922  test    rax, rax
0x18000d925  jz      short loc_18000D977
0x18000d927  mov     r8, rsi; struct CJob *
0x18000d92a  movzx   edx, r14w; unsigned __int16
0x18000d92e  mov     rcx, rax; this
0x18000d931  call    ??0CTrigger@@QEAA@GPEAVCJob@@@Z; CTrigger::CTrigger(ushort,CJob *)
0x18000d936  mov     rdi, rax
0x18000d939  test    rax, rax
0x18000d93c  jz      short loc_18000D977
0x18000d93e  lea     rdx, [rbp+var_50]
0x18000d942  lea     rcx, [rsi+18h]
0x18000d946  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x18000d94b  mov     ebx, eax
0x18000d94d  test    eax, eax
0x18000d94f  jns     short loc_18000D95D
0x18000d951  mov     rcx, rdi; this
0x18000d954  call    ??_GCTrigger@@QEAAPEAXI@Z; CTrigger::`scalar deleting destructor'(uint)
0x18000d959  mov     eax, ebx
0x18000d95b  jmp     short loc_18000D97C
0x18000d95d  mov     eax, [rsi+58h]
0x18000d960  and     eax, 0FFFFFFFh
0x18000d965  or      eax, 0D0000000h
0x18000d96a  mov     [rsi+58h], eax
0x18000d96d  mov     [r12], r14w
0x18000d972  mov     [r15], rdi
0x18000d975  jmp     short loc_18000D959
0x18000d977  mov     eax, 8007000Eh
0x18000d97c  mov     rcx, [rbp+var_10]
0x18000d980  xor     rcx, rsp; StackCookie
0x18000d983  call    __security_check_cookie
0x18000d988  add     rsp, 70h
0x18000d98c  pop     r15
0x18000d98e  pop     r14
0x18000d990  pop     r12
0x18000d992  pop     rdi
0x18000d993  pop     rsi
0x18000d994  pop     rbx
0x18000d995  pop     rbp
0x18000d996  retn
```
