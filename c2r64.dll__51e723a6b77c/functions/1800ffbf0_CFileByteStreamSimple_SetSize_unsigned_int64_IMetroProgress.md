# CFileByteStreamSimple::SetSize(unsigned __int64,IMetroProgress *)

- ea: `0x1800ffbf0`
- end: `0x1800ffd67`
- name: `?SetSize@CFileByteStreamSimple@@UEAAJ_KPEAUIMetroProgress@@@Z`
- size: `375`
- prototype: `int(CFileByteStreamSimple *__hidden this, unsigned __int64, struct IMetroProgress *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callees

- `0x180011618`
- `0x1800264b4`
- `0x18003bec8`
- `0x180053f1c`
- `0x1800ff354`
- `0x1800ffbf0`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ffcde`
- `KERNEL32!GetLastError` at `0x1800ffd05`
- `KERNEL32!GetLastError` at `0x1800ffcde`
- `KERNEL32!GetLastError` at `0x1800ffd05`
- `KERNEL32!GetCurrentThreadId` at `0x1800ffc61`
- `KERNEL32!GetCurrentThreadId` at `0x1800ffc61`
- `KERNEL32!SetFilePointerEx` at `0x1800ffcd4`
- `KERNEL32!SetFilePointerEx` at `0x1800ffcd4`
- `KERNEL32!SetEndOfFile` at `0x1800ffcfb`
- `KERNEL32!SetEndOfFile` at `0x1800ffcfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileByteStreamSimple::SetSize(
        CFileByteStreamSimple *this,
        LARGE_INTEGER a2,
        struct IMetroProgress *a3)
{
  signed int v5; // ebx
  int v6; // ebx
  std::_Mutex_base *v7; // rax
  signed int LastError; // eax
  signed int v9; // eax
  struct _Mtx_internal_imp_t *v10; // rax

  if ( *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 312LL) )
  {
    return (unsigned int)-2134044667;
  }
  else if ( (*(unsigned int (__fastcall **)(CFileByteStreamSimple *))(*(_QWORD *)this + 40LL))(this) )
  {
    if ( !*((_DWORD *)this + 60) || (v6 = *((_DWORD *)this + 60), v6 == GetCurrentThreadId()) )
    {
      if ( *((_BYTE *)this + 144) )
      {
        v7 = (std::_Mutex_base *)std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*((char *)this + 64);
        std::_Mutex_base::lock(v7);
      }
      if ( (*(unsigned __int8 (__fastcall **)(CFileByteStreamSimple *))(*(_QWORD *)this + 88LL))(this) )
      {
        v5 = -2147467259;
      }
      else
      {
        v5 = 0;
        if ( a2.QuadPart != CFileByteStreamSimple::InternalGetSize(this) )
        {
          if ( !SetFilePointerEx(*((HANDLE *)this + 5), a2, 0, 0) )
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
          }
          if ( v5 >= 0 )
          {
            if ( SetEndOfFile(*((HANDLE *)this + 5)) )
              goto LABEL_21;
            v9 = GetLastError();
            v5 = v9;
            if ( v9 > 0 )
              v5 = (unsigned __int16)v9 | 0x80070000;
            if ( !v5 )
            {
LABEL_21:
              *((LARGE_INTEGER *)this + 19) = a2;
              if ( *((_QWORD *)this + 21) < a2.QuadPart )
                a2 = *(LARGE_INTEGER *)((char *)this + 168);
              *((LARGE_INTEGER *)this + 21) = a2;
            }
          }
        }
      }
      if ( *((_BYTE *)this + 144) )
      {
        v10 = (struct _Mtx_internal_imp_t *)std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*((char *)this + 64);
        Mtx_unlock(v10);
      }
    }
    else
    {
      MsoShipAssertTagProc(7118849);
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    return (unsigned int)-2134044671;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ffbf0  mov     [rsp+arg_0], rbx
0x1800ffbf5  mov     [rsp+arg_8], rbp
0x1800ffbfa  mov     [rsp+arg_10], rsi
0x1800ffbff  push    rdi
0x1800ffc00  sub     rsp, 20h
0x1800ffc04  mov     rbp, rdx
0x1800ffc07  mov     rsi, rcx
0x1800ffc0a  mov     r8d, cs:_tls_index
0x1800ffc11  mov     rax, gs:58h
0x1800ffc1a  mov     ecx, 138h
0x1800ffc1f  mov     r8, [rax+r8*8]
0x1800ffc23  cmp     dword ptr [rcx+r8], 0
0x1800ffc28  jbe     short loc_1800FFC34
0x1800ffc2a  mov     ebx, 80CD1005h
0x1800ffc2f  jmp     loc_1800FFD50
0x1800ffc34  mov     rax, [rsi]
0x1800ffc37  mov     rcx, rsi
0x1800ffc3a  mov     rax, [rax+28h]
0x1800ffc3e  call    cs:__guard_dispatch_icall_fptr
0x1800ffc44  test    eax, eax
0x1800ffc46  jnz     short loc_1800FFC52
0x1800ffc48  mov     ebx, 80CD1001h
0x1800ffc4d  jmp     loc_1800FFD50
0x1800ffc52  cmp     dword ptr [rsi+0F0h], 0
0x1800ffc59  jz      short loc_1800FFC7F
0x1800ffc5b  mov     ebx, [rsi+0F0h]
0x1800ffc61  call    cs:__imp_GetCurrentThreadId
0x1800ffc67  cmp     ebx, eax
0x1800ffc69  jz      short loc_1800FFC7F
0x1800ffc6b  mov     ecx, 6CA001h
0x1800ffc70  call    MsoShipAssertTagProc
0x1800ffc75  mov     ebx, 80004005h
0x1800ffc7a  jmp     loc_1800FFD50
0x1800ffc7f  lea     rdi, [rsi+40h]
0x1800ffc83  cmp     byte ptr [rdi+50h], 0
0x1800ffc87  jz      short loc_1800FFC9A
0x1800ffc89  mov     rcx, rdi
0x1800ffc8c  call    ??D?$_Optional_construct_base@U?$DataField@_N@Telemetry@Mso@@@std@@QEGBAAEBU?$DataField@_N@Telemetry@Mso@@XZ; std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*(void)
0x1800ffc91  mov     rcx, rax; this
0x1800ffc94  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800ffc99  nop
0x1800ffc9a  mov     rax, [rsi]
0x1800ffc9d  mov     rcx, rsi
0x1800ffca0  mov     rax, [rax+58h]
0x1800ffca4  call    cs:__guard_dispatch_icall_fptr
0x1800ffcaa  test    al, al
0x1800ffcac  jz      short loc_1800FFCB8
0x1800ffcae  mov     ebx, 80004005h
0x1800ffcb3  jmp     loc_1800FFD3A
0x1800ffcb8  xor     ebx, ebx
0x1800ffcba  mov     rcx, rsi
0x1800ffcbd  call    ?InternalGetSize@CFileByteStreamSimple@@IEBA_KAEBV?$scoped_lock@U?$optional_mutex@Vrecursive_mutex@std@@@Mso@@@std@@@Z; CFileByteStreamSimple::InternalGetSize(std::scoped_lock<Mso::optional_mutex<std::recursive_mutex>> const &)
0x1800ffcc2  cmp     rbp, rax
0x1800ffcc5  jz      short loc_1800FFD3A
0x1800ffcc7  xor     r9d, r9d; dwMoveMethod
0x1800ffcca  xor     r8d, r8d; lpNewFilePointer
0x1800ffccd  mov     rdx, rbp; liDistanceToMove
0x1800ffcd0  mov     rcx, [rsi+28h]; hFile
0x1800ffcd4  call    cs:__imp_SetFilePointerEx
0x1800ffcda  test    eax, eax
0x1800ffcdc  jnz     short loc_1800FFCF3
0x1800ffcde  call    cs:__imp_GetLastError
0x1800ffce4  mov     ebx, eax
0x1800ffce6  test    eax, eax
0x1800ffce8  jle     short loc_1800FFCF3
0x1800ffcea  movzx   ebx, ax
0x1800ffced  or      ebx, 80070000h
0x1800ffcf3  test    ebx, ebx
0x1800ffcf5  js      short loc_1800FFD3A
0x1800ffcf7  mov     rcx, [rsi+28h]; hFile
0x1800ffcfb  call    cs:__imp_SetEndOfFile
0x1800ffd01  test    eax, eax
0x1800ffd03  jnz     short loc_1800FFD1E
0x1800ffd05  call    cs:__imp_GetLastError
0x1800ffd0b  mov     ebx, eax
0x1800ffd0d  test    eax, eax
0x1800ffd0f  jle     short loc_1800FFD1A
0x1800ffd11  movzx   ebx, ax
0x1800ffd14  or      ebx, 80070000h
0x1800ffd1a  test    ebx, ebx
0x1800ffd1c  jnz     short loc_1800FFD3A
0x1800ffd1e  mov     [rsi+98h], rbp
0x1800ffd25  mov     rax, [rsi+0A8h]
0x1800ffd2c  cmp     rax, rbp
0x1800ffd2f  cmovb   rbp, rax
0x1800ffd33  mov     [rsi+0A8h], rbp
0x1800ffd3a  cmp     byte ptr [rdi+50h], 0
0x1800ffd3e  jz      short loc_1800FFD50
0x1800ffd40  mov     rcx, rdi
0x1800ffd43  call    ??D?$_Optional_construct_base@U?$DataField@_N@Telemetry@Mso@@@std@@QEGBAAEBU?$DataField@_N@Telemetry@Mso@@XZ; std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*(void)
0x1800ffd48  mov     rcx, rax; _Mtx_t
0x1800ffd4b  call    _Mtx_unlock
0x1800ffd50  mov     eax, ebx
0x1800ffd52  mov     rbx, [rsp+28h+arg_0]
0x1800ffd57  mov     rbp, [rsp+28h+arg_8]
0x1800ffd5c  mov     rsi, [rsp+28h+arg_10]
0x1800ffd61  add     rsp, 20h
0x1800ffd65  pop     rdi
0x1800ffd66  retn
```
