# CFileByteStreamAdvanced::HrCancel(void)

- ea: `0x1801029d0`
- end: `0x180102b21`
- name: `?HrCancel@CFileByteStreamAdvanced@@UEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(CFileByteStreamAdvanced *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800115c0`
- `0x180012bf8`
- `0x1800264b4`
- `0x1801023b4`
- `0x18010259c`
- `0x1801029d0`
- `0x180103970`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180102ac9`
- `KERNEL32!GetLastError` at `0x180102ad6`
- `KERNEL32!GetLastError` at `0x180102ac9`
- `KERNEL32!GetLastError` at `0x180102ad6`
- `KERNEL32!GetCurrentThreadId` at `0x180102a10`
- `KERNEL32!GetCurrentThreadId` at `0x180102a10`
- `KERNEL32!CancelIoEx` at `0x180102abc`
- `KERNEL32!CancelIoEx` at `0x180102abc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileByteStreamAdvanced::HrCancel(CFileByteStreamAdvanced *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rax
  signed int LastError; // eax
  _BYTE v7[12]; // [rsp+20h] [rbp-18h] BYREF
  _BYTE v8[12]; // [rsp+2Ch] [rbp-Ch] BYREF

  if ( *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 312LL) )
  {
    return (unsigned int)-2134044667;
  }
  else if ( !*((_DWORD *)this - 4) || *((_DWORD *)this - 4) == GetCurrentThreadId() )
  {
    Mso::TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(
      v7,
      (char *)this + 16);
    if ( Mso::ZeroOrOneThreaded::IsThreadOk((Mso::ZeroOrOneThreaded *)v8)
      && ((*((_DWORD *)this + 2) - 2) & 0xFFFFFFFD) == 0
      && *((_QWORD *)this + 13) )
    {
      v3 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 104);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v3 + 104LL))(v3) )
      {
        v4 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 104);
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, 0) )
        {
          v2 = 0;
          *((_DWORD *)this + 2) = 1;
          *((_DWORD *)CFileByteStreamAdvanced::UseTpCallback(*((struct ITpWorkObject **)this + 13)) + 10) = -2147467260;
        }
        else
        {
          v2 = 0;
          if ( !CancelIoEx(*((HANDLE *)this - 27), 0) )
          {
            v2 = 1;
            if ( GetLastError() != 1168 )
            {
              LastError = GetLastError();
              v2 = LastError;
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
      else
      {
        v2 = 1;
      }
    }
    else
    {
      v2 = -2147467259;
    }
    Mso::TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v7);
  }
  else
  {
    MsoShipAssertTagProc(7118932);
    return (unsigned int)-2147467259;
  }
  return v2;
}

```

## disassembly

```asm
0x1801029d0  mov     [rsp+arg_0], rbx
0x1801029d5  mov     [rsp+arg_8], rsi
0x1801029da  push    rdi
0x1801029db  sub     rsp, 30h
0x1801029df  mov     rdi, rcx
0x1801029e2  mov     edx, cs:_tls_index
0x1801029e8  mov     rax, gs:58h
0x1801029f1  mov     ecx, 138h
0x1801029f6  mov     rdx, [rax+rdx*8]
0x1801029fa  cmp     dword ptr [rcx+rdx], 0
0x1801029fe  jbe     short loc_180102A0A
0x180102a00  mov     ebx, 80CD1005h
0x180102a05  jmp     loc_180102B0F
0x180102a0a  cmp     dword ptr [rdi-10h], 0
0x180102a0e  jz      short loc_180102A2F
0x180102a10  call    cs:__imp_GetCurrentThreadId
0x180102a16  cmp     [rdi-10h], eax
0x180102a19  jz      short loc_180102A2F
0x180102a1b  mov     ecx, 6CA054h
0x180102a20  call    MsoShipAssertTagProc
0x180102a25  mov     ebx, 80004005h
0x180102a2a  jmp     loc_180102B0F
0x180102a2f  lea     rdx, [rdi+10h]
0x180102a33  lea     rcx, [rsp+38h+var_18]
0x180102a38  call    ??0?$TLocker@V?$Lockable@V?$LazyInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@AEAV?$Lockable@V?$LazyInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@1@@Z; Mso::TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> &)
0x180102a3d  lea     rcx, [rsp+38h+var_C]; this
0x180102a42  call    ?IsThreadOk@ZeroOrOneThreaded@Mso@@QEBA_NXZ; Mso::ZeroOrOneThreaded::IsThreadOk(void)
0x180102a47  test    al, al
0x180102a49  jnz     short loc_180102A55
0x180102a4b  mov     ebx, 80004005h
0x180102a50  jmp     loc_180102B05
0x180102a55  mov     eax, [rdi+8]
0x180102a58  add     eax, 0FFFFFFFEh
0x180102a5b  test    eax, 0FFFFFFFDh
0x180102a60  jnz     short loc_180102A4B
0x180102a62  lea     rsi, [rdi+68h]
0x180102a66  cmp     qword ptr [rsi], 0
0x180102a6a  jz      short loc_180102A4B
0x180102a6c  mov     rcx, rsi
0x180102a6f  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180102a74  mov     rdx, rax
0x180102a77  mov     rcx, [rax]
0x180102a7a  mov     rax, [rcx+68h]
0x180102a7e  mov     rcx, rdx
0x180102a81  call    cs:__guard_dispatch_icall_fptr
0x180102a87  test    eax, eax
0x180102a89  jnz     short loc_180102A90
0x180102a8b  lea     ebx, [rax+1]
0x180102a8e  jmp     short loc_180102B05
0x180102a90  mov     rcx, rsi
0x180102a93  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180102a98  mov     r8, rax
0x180102a9b  mov     rcx, [rax]
0x180102a9e  mov     rax, [rcx+18h]
0x180102aa2  xor     edx, edx
0x180102aa4  mov     rcx, r8
0x180102aa7  call    cs:__guard_dispatch_icall_fptr
0x180102aad  test    eax, eax
0x180102aaf  jnz     short loc_180102AED
0x180102ab1  xor     ebx, ebx
0x180102ab3  xor     edx, edx; lpOverlapped
0x180102ab5  mov     rcx, [rdi-0D8h]; hFile
0x180102abc  call    cs:__imp_CancelIoEx
0x180102ac2  test    eax, eax
0x180102ac4  jnz     short loc_180102AEB
0x180102ac6  lea     ebx, [rax+1]
0x180102ac9  call    cs:__imp_GetLastError
0x180102acf  cmp     eax, 490h
0x180102ad4  jz      short loc_180102AEB
0x180102ad6  call    cs:__imp_GetLastError
0x180102adc  mov     ebx, eax
0x180102ade  test    eax, eax
0x180102ae0  jle     short loc_180102AEB
0x180102ae2  movzx   ebx, ax
0x180102ae5  or      ebx, 80070000h
0x180102aeb  jmp     short loc_180102B05
0x180102aed  xor     ebx, ebx
0x180102aef  mov     dword ptr [rdi+8], 1
0x180102af6  mov     rcx, [rsi]; struct ITpWorkObject *
0x180102af9  call    ?UseTpCallback@CFileByteStreamAdvanced@@CAPEAVCBgFlushCallback@@PEAUITpWorkObject@@@Z; CFileByteStreamAdvanced::UseTpCallback(ITpWorkObject *)
0x180102afe  mov     dword ptr [rax+28h], 80004004h
0x180102b05  lea     rcx, [rsp+38h+var_18]
0x180102b0a  call    ??1?$TLocker@V?$Lockable@V?$LazyInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::LazyInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x180102b0f  mov     eax, ebx
0x180102b11  mov     rbx, [rsp+38h+arg_0]
0x180102b16  mov     rsi, [rsp+38h+arg_8]
0x180102b1b  add     rsp, 30h
0x180102b1f  pop     rdi
0x180102b20  retn
```
