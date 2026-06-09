# CFileByteStreamAdvanced::Flush(void)

- ea: `0x1801028b0`
- end: `0x1801029c7`
- name: `?Flush@CFileByteStreamAdvanced@@UEAAJXZ`
- size: `279`
- prototype: `__int64 __fastcall(CFileByteStreamAdvanced *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180011618`
- `0x1800264b4`
- `0x18003bec8`
- `0x180053f1c`
- `0x1800fff18`
- `0x1801028b0`
- `0x180102f30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180102985`
- `KERNEL32!GetLastError` at `0x180102985`
- `KERNEL32!GetCurrentThreadId` at `0x180102918`
- `KERNEL32!GetCurrentThreadId` at `0x180102918`
- `KERNEL32!FlushFileBuffers` at `0x18010297b`
- `KERNEL32!FlushFileBuffers` at `0x18010297b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileByteStreamAdvanced::Flush(CFileByteStreamAdvanced *this)
{
  char *v2; // rbp
  int started; // ebx
  char *v4; // rdi
  std::_Mutex_base *v5; // rax
  signed int LastError; // eax
  struct _Mtx_internal_imp_t *v7; // rax

  v2 = (char *)this - 256;
  if ( !*((_BYTE *)this - 96)
    || (started = CFileByteStreamSimple::WriteZerosToEndGap((CFileByteStreamAdvanced *)((char *)this - 256)),
        started >= 0) )
  {
    if ( *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 312LL) )
      return (unsigned int)-2134044667;
    started = 0;
    if ( *((_DWORD *)this - 4) && *((_DWORD *)this - 4) != GetCurrentThreadId() )
    {
      MsoShipAssertTagProc(7118923);
      return (unsigned int)-2147467259;
    }
    v4 = (char *)this - 192;
    if ( *((_BYTE *)this - 112) )
    {
      v5 = (std::_Mutex_base *)std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*((char *)this - 192);
      std::_Mutex_base::lock(v5);
    }
    if ( (*((_DWORD *)this + 2) & 0xFFFFFFFB) != 0 )
    {
      started = CFileByteStreamAdvanced::HrStartAsyncFlush((__int64)v2);
      if ( started < 0 )
      {
        if ( !v4[80] )
          return (unsigned int)started;
        _mm_lfence();
LABEL_18:
        v7 = (struct _Mtx_internal_imp_t *)std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*((char *)this - 192);
        Mtx_unlock(v7);
        return (unsigned int)started;
      }
    }
    else if ( !FlushFileBuffers(*((HANDLE *)this - 27)) )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
    }
    if ( !v4[80] )
      return (unsigned int)started;
    goto LABEL_18;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1801028b0  mov     [rsp+arg_0], rbx
0x1801028b5  mov     [rsp+arg_8], rbp
0x1801028ba  mov     [rsp+arg_10], rsi
0x1801028bf  push    rdi
0x1801028c0  sub     rsp, 20h
0x1801028c4  mov     rsi, rcx
0x1801028c7  lea     rbp, [rcx-100h]
0x1801028ce  cmp     byte ptr [rbp+0A0h], 0
0x1801028d5  jz      short loc_1801028E9
0x1801028d7  mov     rcx, rbp; this
0x1801028da  call    ?WriteZerosToEndGap@CFileByteStreamSimple@@IEAAJXZ; CFileByteStreamSimple::WriteZerosToEndGap(void)
0x1801028df  mov     ebx, eax
0x1801028e1  test    eax, eax
0x1801028e3  js      loc_1801029B0
0x1801028e9  mov     edx, cs:_tls_index
0x1801028ef  mov     rax, gs:58h
0x1801028f8  mov     ecx, 138h
0x1801028fd  mov     rax, [rax+rdx*8]
0x180102901  cmp     dword ptr [rcx+rax], 0
0x180102905  jbe     short loc_180102911
0x180102907  mov     ebx, 80CD1005h
0x18010290c  jmp     loc_1801029B0
0x180102911  xor     ebx, ebx
0x180102913  cmp     [rsi-10h], ebx
0x180102916  jz      short loc_180102934
0x180102918  call    cs:__imp_GetCurrentThreadId
0x18010291e  cmp     [rsi-10h], eax
0x180102921  jz      short loc_180102934
0x180102923  mov     ecx, 6CA04Bh
0x180102928  call    MsoShipAssertTagProc
0x18010292d  mov     ebx, 80004005h
0x180102932  jmp     short loc_1801029B0
0x180102934  lea     rdi, [rsi-0C0h]
0x18010293b  cmp     byte ptr [rdi+50h], 0
0x18010293f  jz      short loc_180102952
0x180102941  mov     rcx, rdi
0x180102944  call    ??D?$_Optional_construct_base@U?$DataField@_N@Telemetry@Mso@@@std@@QEGBAAEBU?$DataField@_N@Telemetry@Mso@@XZ; std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*(void)
0x180102949  mov     rcx, rax; this
0x18010294c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180102951  nop
0x180102952  test    dword ptr [rsi+8], 0FFFFFFFBh
0x180102959  jz      short loc_180102974
0x18010295b  mov     rcx, rbp
0x18010295e  call    ?HrStartAsyncFlush@CFileByteStreamAdvanced@@AEAAJAEBV?$scoped_lock@U?$optional_mutex@Vrecursive_mutex@std@@@Mso@@@std@@@Z; CFileByteStreamAdvanced::HrStartAsyncFlush(std::scoped_lock<Mso::optional_mutex<std::recursive_mutex>> const &)
0x180102963  mov     ebx, eax
0x180102965  test    eax, eax
0x180102967  jns     short loc_18010299A
0x180102969  cmp     byte ptr [rdi+50h], 0
0x18010296d  jz      short loc_1801029B0
0x18010296f  lfence
0x180102972  jmp     short loc_1801029A0
0x180102974  mov     rcx, [rsi-0D8h]; hFile
0x18010297b  call    cs:__imp_FlushFileBuffers
0x180102981  test    eax, eax
0x180102983  jnz     short loc_18010299A
0x180102985  call    cs:__imp_GetLastError
0x18010298b  mov     ebx, eax
0x18010298d  test    eax, eax
0x18010298f  jle     short loc_18010299A
0x180102991  movzx   ebx, ax
0x180102994  or      ebx, 80070000h
0x18010299a  cmp     byte ptr [rdi+50h], 0
0x18010299e  jz      short loc_1801029B0
0x1801029a0  mov     rcx, rdi
0x1801029a3  call    ??D?$_Optional_construct_base@U?$DataField@_N@Telemetry@Mso@@@std@@QEGBAAEBU?$DataField@_N@Telemetry@Mso@@XZ; std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*(void)
0x1801029a8  mov     rcx, rax; _Mtx_t
0x1801029ab  call    _Mtx_unlock
0x1801029b0  mov     eax, ebx
0x1801029b2  mov     rbx, [rsp+28h+arg_0]
0x1801029b7  mov     rbp, [rsp+28h+arg_8]
0x1801029bc  mov     rsi, [rsp+28h+arg_10]
0x1801029c1  add     rsp, 20h
0x1801029c5  pop     rdi
0x1801029c6  retn
```
