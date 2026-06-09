# Win32LiveSystemProvider::QueryProcessVmCounters(void *,_MINIDUMP_PROCESS_VM_COUNTERS_2 *,ulong)

- ea: `0x1800153b0`
- end: `0x18001550e`
- name: `?QueryProcessVmCounters@Win32LiveSystemProvider@@UEAAJPEAXPEAU_MINIDUMP_PROCESS_VM_COUNTERS_2@@K@Z`
- size: `350`
- prototype: `int(Win32LiveSystemProvider *__hidden this, void *, struct _MINIDUMP_PROCESS_VM_COUNTERS_2 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180025b00`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180014950`
- `0x1800153b0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015480`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::QueryProcessVmCounters(
        Win32LiveSystemProvider *this,
        void *a2,
        struct _MINIDUMP_PROCESS_VM_COUNTERS_2 *a3,
        int a4)
{
  int result; // eax
  unsigned int (__fastcall *v8)(void *, _DWORD *, __int64); // rax
  unsigned int (__fastcall *v9)(void *, _DWORD *); // rax
  bool v10; // zf
  _DWORD v11[2]; // [rsp+20h] [rbp-60h] BYREF
  ULONG64 v12; // [rsp+28h] [rbp-58h]
  ULONG64 v13; // [rsp+30h] [rbp-50h]
  ULONG64 v14; // [rsp+38h] [rbp-48h]
  ULONG64 v15; // [rsp+40h] [rbp-40h]
  ULONG64 v16; // [rsp+48h] [rbp-38h]
  ULONG64 v17; // [rsp+50h] [rbp-30h]
  ULONG64 v18; // [rsp+58h] [rbp-28h]
  ULONG64 v19; // [rsp+60h] [rbp-20h]
  ULONG64 v20; // [rsp+68h] [rbp-18h]

  if ( a4 != 152 )
    return -2147024872;
  result = Win32LiveSystemProvider::LoadPsApi(this);
  if ( !result )
  {
    if ( *((_QWORD *)this + 65) )
    {
      memset_0(v11, 0, 0x50u);
      memset_0(a3, 0, sizeof(struct _MINIDUMP_PROCESS_VM_COUNTERS_2));
      a3->Flags = 5;
      v8 = (unsigned int (__fastcall *)(void *, _DWORD *, __int64))*((_QWORD *)this + 65);
      v11[0] = 80;
      if ( v8(a2, v11, 80)
        || (a3->Flags &= ~4u,
            v9 = (unsigned int (__fastcall *)(void *, _DWORD *))*((_QWORD *)this + 65),
            v11[0] = 72,
            v9(a2, v11)) )
      {
        v10 = (a3->Flags & 4) == 0;
        a3->PageFaultCount = v11[1];
        a3->PeakWorkingSetSize = v12;
        a3->WorkingSetSize = v13;
        a3->QuotaPeakPagedPoolUsage = v14;
        a3->QuotaPagedPoolUsage = v15;
        a3->QuotaPeakNonPagedPoolUsage = v16;
        a3->QuotaNonPagedPoolUsage = v17;
        a3->PagefileUsage = v18;
        a3->PeakPagefileUsage = v19;
        a3->Revision = 2;
        if ( !v10 )
          a3->PrivateUsage = v20;
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
    else
    {
      return -2147024846;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800153b0  mov     [rsp-18h+arg_18], rbx
0x1800153b5  push    rbp
0x1800153b6  push    rsi
0x1800153b7  push    rdi
0x1800153b8  mov     rbp, rsp
0x1800153bb  sub     rsp, 80h
0x1800153c2  mov     rax, cs:__security_cookie
0x1800153c9  xor     rax, rsp
0x1800153cc  mov     [rbp+var_10], rax
0x1800153d0  mov     rbx, r8
0x1800153d3  mov     rsi, rdx
0x1800153d6  mov     rdi, rcx
0x1800153d9  cmp     r9d, 98h
0x1800153e0  jz      short loc_1800153EC
0x1800153e2  mov     eax, 80070018h
0x1800153e7  jmp     loc_1800154EF
0x1800153ec  call    ?LoadPsApi@Win32LiveSystemProvider@@IEAAJXZ; Win32LiveSystemProvider::LoadPsApi(void)
0x1800153f1  test    eax, eax
0x1800153f3  jnz     loc_1800154EF
0x1800153f9  cmp     qword ptr [rdi+208h], 0
0x180015401  jnz     short loc_18001540D
0x180015403  mov     eax, 80070032h
0x180015408  jmp     loc_1800154EF
0x18001540d  xor     edx, edx; Val
0x18001540f  lea     rcx, [rbp+var_60]; void *
0x180015413  lea     r8d, [rdx+50h]; Size
0x180015417  call    memset_0
0x18001541c  xor     edx, edx; Val
0x18001541e  mov     r8d, 98h; Size
0x180015424  mov     rcx, rbx; void *
0x180015427  call    memset_0
0x18001542c  mov     word ptr [rbx+2], 5
0x180015432  lea     rdx, [rbp+var_60]
0x180015436  mov     rax, [rdi+208h]
0x18001543d  mov     r8d, 50h ; 'P'
0x180015443  mov     rcx, rsi
0x180015446  mov     [rbp+var_60], 50h ; 'P'
0x18001544d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015452  test    eax, eax
0x180015454  jnz     short loc_180015494
0x180015456  mov     eax, 0FFFBh
0x18001545b  lea     rdx, [rbp+var_60]
0x18001545f  and     [rbx+2], ax
0x180015463  mov     r8d, 48h ; 'H'
0x180015469  mov     rax, [rdi+208h]
0x180015470  mov     rcx, rsi
0x180015473  mov     [rbp+var_60], r8d
0x180015477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001547c  test    eax, eax
0x18001547e  jnz     short loc_180015494
0x180015480  call    cs:__imp_GetLastError
0x180015486  test    eax, eax
0x180015488  jle     short loc_1800154EF
0x18001548a  movzx   eax, ax
0x18001548d  or      eax, 80070000h
0x180015492  jmp     short loc_1800154EF
0x180015494  test    byte ptr [rbx+2], 4
0x180015498  mov     eax, [rbp+var_5C]
0x18001549b  mov     [rbx+4], eax
0x18001549e  mov     rax, [rbp+var_58]
0x1800154a2  mov     [rbx+8], rax
0x1800154a6  mov     rax, [rbp+var_50]
0x1800154aa  mov     [rbx+10h], rax
0x1800154ae  mov     rax, [rbp+var_48]
0x1800154b2  mov     [rbx+18h], rax
0x1800154b6  mov     rax, [rbp+var_40]
0x1800154ba  mov     [rbx+20h], rax
0x1800154be  mov     rax, [rbp+var_38]
0x1800154c2  mov     [rbx+28h], rax
0x1800154c6  mov     rax, [rbp+var_30]
0x1800154ca  mov     [rbx+30h], rax
0x1800154ce  mov     rax, [rbp+var_28]
0x1800154d2  mov     [rbx+38h], rax
0x1800154d6  mov     rax, [rbp+var_20]
0x1800154da  mov     [rbx+40h], rax
0x1800154de  mov     word ptr [rbx], 2
0x1800154e3  jz      short loc_1800154ED
0x1800154e5  mov     rax, [rbp+var_18]
0x1800154e9  mov     [rbx+58h], rax
0x1800154ed  xor     eax, eax
0x1800154ef  mov     rcx, [rbp+var_10]
0x1800154f3  xor     rcx, rsp; StackCookie
0x1800154f6  call    __security_check_cookie
0x1800154fb  mov     rbx, [rsp+80h+arg_18]
0x180015503  add     rsp, 80h
0x18001550a  pop     rdi
0x18001550b  pop     rsi
0x18001550c  pop     rbp
0x18001550d  retn
```
