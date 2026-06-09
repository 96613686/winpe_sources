# CThread::Execute(void)

- ea: `0x140007af8`
- end: `0x140007c72`
- name: `?Execute@CThread@@AEAAXXZ`
- size: `378`
- prototype: `void __fastcall(CThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007d20`

## callees

- `0x140004538`
- `0x140007554`
- `0x140007af8`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140007b69`
- `KERNEL32!GetLastError` at `0x140007bc5`
- `KERNEL32!GetLastError` at `0x140007b69`
- `KERNEL32!GetLastError` at `0x140007bc5`
- `KERNEL32!SetEvent` at `0x140007ba9`
- `KERNEL32!SetEvent` at `0x140007ba9`
- `msvcrt!_endthreadex` at `0x140007c5c`
- `msvcrt!_endthreadex` at `0x140007c5c`
- `ole32!CoUninitialize` at `0x140007c21`
- `ole32!CoUninitialize` at `0x140007c21`
- `ole32!CoInitializeEx` at `0x140007b45`
- `ole32!CoInitializeEx` at `0x140007b45`

## pseudocode

```c
void __fastcall CThread::Execute(CThread *this)
{
  CReference *v1; // rbx
  char v2; // si
  __int64 v3; // r8
  CThread *v4; // rbx
  CThread *v5; // rbx
  const _com_error *v6; // [rsp+30h] [rbp-18h] BYREF

  v1 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  if ( CoInitializeEx(0, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      GetLastError();
      ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
    }
    return;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v2 = (*(__int64 (__fastcall **)(CReference *))(*(_QWORD *)v1 + 8LL))(v1);
    if ( SetEvent(*((HANDLE *)v1 + 10)) )
    {
      if ( v2 == 1 )
        (*(void (__fastcall **)(CReference *))(*(_QWORD *)v1 + 16LL))(v1);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
    }
    (*(void (__fastcall **)(CReference *))(*(_QWORD *)v1 + 24LL))(v1);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v6) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v4 = this;
      }
      else
      {
        v4 = this;
        WPP_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((unsigned int *)v6 + 2),
          v3,
          *((unsigned int *)this + 6),
          *((_DWORD *)v6 + 2));
      }
      SetEvent(*((HANDLE *)v4 + 10));
      v1 = this;
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_140007C13);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v5 = this;
      }
      else
      {
        v5 = this;
        ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
      }
      SetEvent(*((HANDLE *)v5 + 10));
      v1 = this;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140007C15);
    }
  }
LABEL_15:
  CoUninitialize();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  CReference::Release(v1);
  _endthreadex(0);
}

```

## disassembly

```asm
0x140007af8  mov     [rsp+arg_8], rbx
0x140007afd  mov     [rsp+arg_10], rsi
0x140007b02  mov     [rsp+arg_0], rcx
0x140007b07  push    rdi
0x140007b08  sub     rsp, 40h
0x140007b0c  mov     rbx, rcx
0x140007b0f  lea     rdi, WPP_GLOBAL_Control
0x140007b16  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b1d  cmp     rcx, rdi
0x140007b20  jz      short loc_140007B41
0x140007b22  test    byte ptr [rcx+1Ch], 4
0x140007b26  jz      short loc_140007B41
0x140007b28  mov     edx, 0Fh
0x140007b2d  mov     r9d, [rbx+18h]
0x140007b31  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007b38  mov     rcx, [rcx+10h]
0x140007b3c  call    WPP_SF_d
0x140007b41  xor     edx, edx; dwCoInit
0x140007b43  xor     ecx, ecx; pvReserved
0x140007b45  call    cs:__imp_CoInitializeEx
0x140007b4b  test    eax, eax
0x140007b4d  jns     short loc_140007B93
0x140007b4f  mov     rax, cs:WPP_GLOBAL_Control
0x140007b56  cmp     rax, rdi
0x140007b59  jz      loc_140007C62
0x140007b5f  test    byte ptr [rax+1Ch], 4
0x140007b63  jz      loc_140007C62
0x140007b69  call    cs:__imp_GetLastError
0x140007b6f  mov     edx, 10h
0x140007b74  mov     r9d, eax
0x140007b77  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b85  mov     rcx, [rcx+10h]
0x140007b89  call    WPP_SF_d
0x140007b8e  jmp     loc_140007C62
0x140007b93  mov     rax, [rbx]
0x140007b96  mov     rcx, rbx
0x140007b99  mov     rax, [rax+8]
0x140007b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ba2  mov     sil, al
0x140007ba5  mov     rcx, [rbx+50h]; hEvent
0x140007ba9  call    cs:__imp_SetEvent
0x140007baf  test    eax, eax
0x140007bb1  jnz     short loc_140007BEC
0x140007bb3  mov     rax, cs:WPP_GLOBAL_Control
0x140007bba  cmp     rax, rdi
0x140007bbd  jz      short loc_140007C01
0x140007bbf  test    byte ptr [rax+1Ch], 1
0x140007bc3  jz      short loc_140007C01
0x140007bc5  call    cs:__imp_GetLastError
0x140007bcb  mov     edx, 11h
0x140007bd0  mov     r9d, eax
0x140007bd3  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007bda  mov     rcx, cs:WPP_GLOBAL_Control
0x140007be1  mov     rcx, [rcx+10h]
0x140007be5  call    WPP_SF_d
0x140007bea  jmp     short loc_140007C01
0x140007bec  cmp     sil, 1
0x140007bf0  jnz     short loc_140007C01
0x140007bf2  mov     rax, [rbx]
0x140007bf5  mov     rcx, rbx
0x140007bf8  mov     rax, [rax+10h]
0x140007bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c01  mov     rax, [rbx]
0x140007c04  mov     rcx, rbx
0x140007c07  mov     rax, [rax+18h]
0x140007c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c10  nop
0x140007c11  jmp     short loc_140007C21
0x140007c13  jmp     short $+2
0x140007c15  mov     rbx, [rsp+48h+arg_0]
0x140007c1a  lea     rdi, WPP_GLOBAL_Control
0x140007c21  call    cs:__imp_CoUninitialize
0x140007c27  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c2e  cmp     rcx, rdi
0x140007c31  jz      short loc_140007C52
0x140007c33  test    byte ptr [rcx+1Ch], 4
0x140007c37  jz      short loc_140007C52
0x140007c39  mov     edx, 14h
0x140007c3e  mov     r9d, [rbx+18h]
0x140007c42  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007c49  mov     rcx, [rcx+10h]
0x140007c4d  call    WPP_SF_d
0x140007c52  mov     rcx, rbx; this
0x140007c55  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x140007c5a  xor     ecx, ecx; ReturnCode
0x140007c5c  call    cs:__imp__endthreadex
0x140007c62  mov     rbx, [rsp+48h+arg_8]
0x140007c67  mov     rsi, [rsp+48h+arg_10]
0x140007c6c  add     rsp, 40h
0x140007c70  pop     rdi
0x140007c71  retn
```
