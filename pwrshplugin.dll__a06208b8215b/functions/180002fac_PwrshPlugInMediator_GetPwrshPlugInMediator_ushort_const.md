# PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)

- ea: `0x180002fac`
- end: `0x180003151`
- name: `?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z`
- size: `421`
- prototype: `struct PwrshPlugInMediator *__fastcall(const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004530`
- `0x180004590`
- `0x1800045f0`
- `0x180004650`
- `0x1800046a0`
- `0x1800046e0`
- `0x180004750`
- `0x180004830`
- `0x180004900`
- `0x180004960`

## callees

- `0x180001098`
- `0x18000185c`
- `0x1800018cc`
- `0x1800019f8`
- `0x180001dfc`
- `0x180002058`
- `0x180002e80`
- `0x180002fac`
- `0x180003a68`
- `0x180007428`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002ff9`
- `KERNEL32!EnterCriticalSection` at `0x180002ff9`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800030cf`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800030cf`
- `KERNEL32!LeaveCriticalSection` at `0x18000301f`
- `KERNEL32!LeaveCriticalSection` at `0x18000301f`

## pseudocode

```c
struct PwrshPlugInMediator *__fastcall PwrshPlugInMediator::GetPwrshPlugInMediator(const unsigned __int16 *a1)
{
  PlugInException *v2; // rbx
  unsigned __int16 **v3; // r8
  PlugInException *v5; // rax
  PlugInException *pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  __int64 v8[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v9; // [rsp+58h] [rbp+10h] BYREF
  PlugInException *v10; // [rsp+60h] [rbp+18h]

  if ( __TSS0__1__GetPwrshPlugInMediator_PwrshPlugInMediator__SAPEAV2_PEBG_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                               + (unsigned int)tls_index)
                                                                                             + 4LL)
    && (Init_thread_header(&__TSS0__1__GetPwrshPlugInMediator_PwrshPlugInMediator__SAPEAV2_PEBG_Z_4HA),
        __TSS0__1__GetPwrshPlugInMediator_PwrshPlugInMediator__SAPEAV2_PEBG_Z_4HA == -1) )
  {
    NativeMsh::PwrshCommon::PwrshCommon((NativeMsh::PwrshCommon *)qword_180014D80);
    v2 = 0;
    byte_180014D28 = 0;
    byte_180014D40 = 0;
    dword_180014D2C = 0;
    xmmword_180014D30 = 0;
    `PwrshPlugInMediator::GetPwrshPlugInMediator'::`2'::singletonInstance = 0;
    qword_180014CE8 = 0;
    qword_180014CF0 = 0;
    qword_180014CF8 = 0;
    qword_180014D00 = 0;
    qword_180014D08 = 0;
    qword_180014D10 = 0;
    qword_180014D18 = 0;
    qword_180014D20 = 0;
    qword_180014D78 = 0;
    byte_180014D70 = InitializeCriticalSectionAndSpinCount(&CriticalSection, 0x80000400);
    atexit(`PwrshPlugInMediator::GetPwrshPlugInMediator'::`2'::`dynamic atexit destructor for 'singletonInstance'');
    Init_thread_footer(&__TSS0__1__GetPwrshPlugInMediator_PwrshPlugInMediator__SAPEAV2_PEBG_Z_4HA);
  }
  else
  {
    v2 = 0;
  }
  if ( !byte_180014D70 )
  {
    v9 = 0;
    GetFormattedErrorMessage(&v9, 0x805403EF);
    v5 = (PlugInException *)operator new(0x10u);
    v10 = v5;
    if ( v5 )
      v2 = PlugInException::PlugInException(v5, 0x805403EF, v9);
    pExceptionObject = v2;
    throw (PlugInException **)&pExceptionObject;
  }
  if ( !byte_180014D28 )
  {
    EnterCriticalSection(&CriticalSection);
    if ( !byte_180014D28 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        PwrshPlugInMediator::ProcessExtraInfo(
          (PwrshPlugInMediator *)&`PwrshPlugInMediator::GetPwrshPlugInMediator'::`2'::singletonInstance,
          a1,
          v3);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &PlugInException * `RTTI Type Descriptor', (PlugInException **)v8) )
        {
          LeaveCriticalSection(&CriticalSection);
          v7 = v8[0];
          throw (PlugInException **)&v7;
        }
      }
    }
    LeaveCriticalSection(&CriticalSection);
  }
  return (struct PwrshPlugInMediator *)&`PwrshPlugInMediator::GetPwrshPlugInMediator'::`2'::singletonInstance;
}

```

## disassembly

```asm
0x180002fac  mov     [rsp+arg_0], rbx
0x180002fb1  push    rdi
0x180002fb2  sub     rsp, 40h
0x180002fb6  mov     rdi, rcx
0x180002fb9  mov     edx, cs:_tls_index
0x180002fbf  mov     rax, gs:58h
0x180002fc8  mov     ecx, 4
0x180002fcd  mov     rax, [rax+rdx*8]
0x180002fd1  mov     eax, [rcx+rax]
0x180002fd4  cmp     cs:?$TSS0@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4HA, eax
0x180002fda  jg      short loc_180003037
0x180002fdc  xor     ebx, ebx
0x180002fde  cmp     cs:byte_180014D70, bl
0x180002fe4  jz      loc_1800030FE
0x180002fea  cmp     cs:byte_180014D28, bl
0x180002ff0  jnz     short loc_180003025
0x180002ff2  lea     rcx, CriticalSection; lpCriticalSection
0x180002ff9  call    cs:__imp_EnterCriticalSection
0x180002fff  nop
0x180003000  cmp     cs:byte_180014D28, bl
0x180003006  jnz     short loc_180003018
0x180003008  mov     rdx, rdi; unsigned __int16 *
0x18000300b  lea     rcx, ?singletonInstance@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4V2@A; this
0x180003012  call    ?ProcessExtraInfo@PwrshPlugInMediator@@QEAAXPEBGPEAPEAG@Z; PwrshPlugInMediator::ProcessExtraInfo(ushort const *,ushort * *)
0x180003017  nop
0x180003018  lea     rcx, CriticalSection; lpCriticalSection
0x18000301f  call    cs:__imp_LeaveCriticalSection
0x180003025  lea     rax, ?singletonInstance@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4V2@A; PwrshPlugInMediator `PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)'::`2'::singletonInstance
0x18000302c  mov     rbx, [rsp+48h+arg_0]
0x180003031  add     rsp, 40h
0x180003035  pop     rdi
0x180003036  retn
0x180003037  lea     rcx, ?$TSS0@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4HA
0x18000303e  call    _Init_thread_header
0x180003043  cmp     cs:?$TSS0@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4HA, 0FFFFFFFFh
0x18000304a  jnz     short loc_180002FDC
0x18000304c  lea     rcx, qword_180014D80; this
0x180003053  call    ??0PwrshCommon@NativeMsh@@QEAA@XZ; NativeMsh::PwrshCommon::PwrshCommon(void)
0x180003058  xor     ebx, ebx
0x18000305a  mov     cs:byte_180014D28, bl
0x180003060  mov     cs:byte_180014D40, bl
0x180003066  mov     cs:dword_180014D2C, ebx
0x18000306c  xorps   xmm0, xmm0
0x18000306f  movdqa  cs:xmmword_180014D30, xmm0
0x180003077  mov     cs:?singletonInstance@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4V2@A, rbx; PwrshPlugInMediator `PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)'::`2'::singletonInstance
0x18000307e  mov     cs:qword_180014CE8, rbx
0x180003085  mov     cs:qword_180014CF0, rbx
0x18000308c  mov     cs:qword_180014CF8, rbx
0x180003093  mov     cs:qword_180014D00, rbx
0x18000309a  mov     cs:qword_180014D08, rbx
0x1800030a1  mov     cs:qword_180014D10, rbx
0x1800030a8  mov     cs:qword_180014D18, rbx
0x1800030af  mov     cs:qword_180014D20, rbx
0x1800030b6  mov     cs:byte_180014D70, bl
0x1800030bc  mov     cs:qword_180014D78, rbx
0x1800030c3  mov     edx, 80000400h; dwSpinCount
0x1800030c8  lea     rcx, CriticalSection; lpCriticalSection
0x1800030cf  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800030d5  test    eax, eax
0x1800030d7  jz      short loc_1800030E0
0x1800030d9  mov     cs:byte_180014D70, 1
0x1800030e0  lea     rcx, ??__FsingletonInstance@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z@YAXXZ; void (__cdecl *)()
0x1800030e7  call    atexit
0x1800030ec  nop
0x1800030ed  lea     rcx, ?$TSS0@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4HA
0x1800030f4  call    _Init_thread_footer
0x1800030f9  jmp     loc_180002FDE
0x1800030fe  mov     [rsp+48h+arg_8], rbx
0x180003103  mov     edi, 805403EFh
0x180003108  mov     edx, edi; unsigned int
0x18000310a  lea     rcx, [rsp+48h+arg_8]; unsigned __int16 **
0x18000310f  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180003114  mov     ecx, 10h; Size
0x180003119  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000311e  mov     [rsp+48h+arg_10], rax
0x180003123  test    rax, rax
0x180003126  jz      short loc_18000313A
0x180003128  mov     r8, [rsp+48h+arg_8]; unsigned __int16 *
0x18000312d  mov     edx, edi; unsigned int
0x18000312f  mov     rcx, rax; this
0x180003132  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x180003137  mov     rbx, rax
0x18000313a  mov     [rsp+48h+pExceptionObject], rbx
0x18000313f  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x180003146  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000314b  call    _CxxThrowException_0
```
