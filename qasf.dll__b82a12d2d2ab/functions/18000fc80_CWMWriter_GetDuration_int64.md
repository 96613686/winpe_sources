# CWMWriter::GetDuration(__int64 *)

- ea: `0x18000fc80`
- end: `0x18000fdd8`
- name: `?GetDuration@CWMWriter@@UEAAJPEA_J@Z`
- size: `344`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x18000fc80`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000fca9`
- `KERNEL32!EnterCriticalSection` at `0x18000fca9`
- `KERNEL32!LeaveCriticalSection` at `0x18000fda5`
- `KERNEL32!LeaveCriticalSection` at `0x18000fdb2`
- `KERNEL32!LeaveCriticalSection` at `0x18000fda5`
- `KERNEL32!LeaveCriticalSection` at `0x18000fdb2`

## pseudocode

```c
__int64 __fastcall CWMWriter::GetDuration(struct _RTL_CRITICAL_SECTION *this, __int64 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int DebugInfo; // eax
  __int64 v6; // rax
  int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h] BYREF
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF

  v2 = this + 3;
  EnterCriticalSection(this + 3);
  DebugInfo = (int)this[4].DebugInfo;
  *a2 = 0;
  if ( DebugInfo )
  {
    LeaveCriticalSection(v2);
    return 2147549183LL;
  }
  else
  {
    v6 = *(_QWORD *)&this[7].LockCount;
    v7 = 0;
    if ( v6 )
    {
      do
      {
        v8 = *(_QWORD *)(v6 + 16);
        v9 = *(_QWORD *)(v6 + 8);
        if ( *(_QWORD *)(v8 + 48) )
        {
          v13 = 0;
          if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v8 + 24) + 48LL))(v8 + 24, &v13) )
          {
            v12 = 0;
            v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_IMediaSeeking, &v12);
            if ( v7 >= 0 )
            {
              v14 = 0;
              v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 80LL))(v12, &v14);
              if ( v7 >= 0 )
              {
                v10 = *a2;
                if ( v14 > *a2 )
                  v10 = v14;
                *a2 = v10;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
        if ( v7 < 0 )
          break;
        v6 = v9;
      }
      while ( v9 );
    }
    LeaveCriticalSection(v2);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x18000fc80  mov     [rsp+arg_10], rbx
0x18000fc85  push    rsi
0x18000fc86  push    rdi
0x18000fc87  push    r14
0x18000fc89  sub     rsp, 40h
0x18000fc8d  mov     rax, cs:__security_cookie
0x18000fc94  xor     rax, rsp
0x18000fc97  mov     [rsp+58h+var_20], rax
0x18000fc9c  lea     rbx, [rcx+78h]
0x18000fca0  mov     rsi, rcx
0x18000fca3  mov     rcx, rbx; lpCriticalSection
0x18000fca6  mov     r14, rdx
0x18000fca9  call    cs:__imp_EnterCriticalSection
0x18000fcaf  mov     eax, [rsi+0A0h]
0x18000fcb5  mov     qword ptr [r14], 0
0x18000fcbc  test    eax, eax
0x18000fcbe  jnz     loc_18000FDAF
0x18000fcc4  mov     rax, [rsi+120h]
0x18000fccb  xor     edi, edi
0x18000fccd  test    rax, rax
0x18000fcd0  jz      loc_18000FDA2
0x18000fcd6  mov     rcx, [rax+10h]
0x18000fcda  mov     rsi, [rax+8]
0x18000fcde  cmp     qword ptr [rcx+30h], 0
0x18000fce3  jz      loc_18000FD92
0x18000fce9  add     rcx, 18h
0x18000fced  mov     [rsp+58h+var_30], 0
0x18000fcf6  lea     rdx, [rsp+58h+var_30]
0x18000fcfb  mov     rax, [rcx]
0x18000fcfe  mov     rax, [rax+30h]
0x18000fd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd07  test    eax, eax
0x18000fd09  jnz     loc_18000FD92
0x18000fd0f  mov     rcx, [rsp+58h+var_30]
0x18000fd14  lea     r8, [rsp+58h+var_38]
0x18000fd19  mov     [rsp+58h+var_38], 0
0x18000fd22  lea     rdx, IID_IMediaSeeking
0x18000fd29  mov     rax, [rcx]
0x18000fd2c  mov     rax, [rax]
0x18000fd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd34  mov     edi, eax
0x18000fd36  test    eax, eax
0x18000fd38  js      short loc_18000FD81
0x18000fd3a  mov     rcx, [rsp+58h+var_38]
0x18000fd3f  lea     rdx, [rsp+58h+var_28]
0x18000fd44  mov     [rsp+58h+var_28], 0
0x18000fd4d  mov     rax, [rcx]
0x18000fd50  mov     rax, [rax+50h]
0x18000fd54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd59  mov     edi, eax
0x18000fd5b  test    eax, eax
0x18000fd5d  js      short loc_18000FD70
0x18000fd5f  mov     rax, [r14]
0x18000fd62  cmp     [rsp+58h+var_28], rax
0x18000fd67  cmovg   rax, [rsp+58h+var_28]
0x18000fd6d  mov     [r14], rax
0x18000fd70  mov     rcx, [rsp+58h+var_38]
0x18000fd75  mov     rax, [rcx]
0x18000fd78  mov     rax, [rax+10h]
0x18000fd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd81  mov     rcx, [rsp+58h+var_30]
0x18000fd86  mov     rax, [rcx]
0x18000fd89  mov     rax, [rax+10h]
0x18000fd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd92  test    edi, edi
0x18000fd94  js      short loc_18000FDA2
0x18000fd96  mov     rax, rsi
0x18000fd99  test    rsi, rsi
0x18000fd9c  jnz     loc_18000FCD6
0x18000fda2  mov     rcx, rbx; lpCriticalSection
0x18000fda5  call    cs:__imp_LeaveCriticalSection
0x18000fdab  mov     eax, edi
0x18000fdad  jmp     short loc_18000FDBD
0x18000fdaf  mov     rcx, rbx; lpCriticalSection
0x18000fdb2  call    cs:__imp_LeaveCriticalSection
0x18000fdb8  mov     eax, 8000FFFFh
0x18000fdbd  mov     rcx, [rsp+58h+var_20]
0x18000fdc2  xor     rcx, rsp; StackCookie
0x18000fdc5  call    __security_check_cookie
0x18000fdca  mov     rbx, [rsp+58h+arg_10]
0x18000fdcf  add     rsp, 40h
0x18000fdd3  pop     r14
0x18000fdd5  pop     rdi
0x18000fdd6  pop     rsi
0x18000fdd7  retn
```
