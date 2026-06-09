# GetLocalSystemQueueName(wchar_t const *,bool)

- ea: `0x1800c7984`
- end: `0x1800c7b3b`
- name: `?GetLocalSystemQueueName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEB_W_N@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c8008`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18000f7e4`
- `0x180012ad4`
- `0x180078d08`
- `0x1800b04b8`
- `0x1800c5fb8`
- `0x1800c6860`
- `0x1800c78a8`
- `0x1800c7984`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x1800c79f3`
- `msvcrt!free` at `0x1800c7b03`
- `msvcrt!free` at `0x1800c79f3`
- `msvcrt!free` at `0x1800c7b03`
- `KERNEL32!GetLastError` at `0x1800c7a24`
- `KERNEL32!GetLastError` at `0x1800c7a24`
- `KERNEL32!GetComputerNameW` at `0x1800c7a1a`
- `KERNEL32!GetComputerNameW` at `0x1800c7a1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetLocalSystemQueueName(__int64 a1, __int64 a2, char a3)
{
  void *v6; // rsi
  void *v7; // rbx
  DWORD LastError; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  void *Block; // [rsp+20h] [rbp-E0h] BYREF
  DWORD nSize; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[232]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[16]; // [rsp+150h] [rbp+50h] BYREF

  v6 = 0;
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>(v20);
  Block = 0;
  if ( !a3 )
  {
    nSize = 16;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 15, WPP_e54437e9c8b438399f706fc9b765c57c_Traceguids, LastError);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, LastError);
      throw (bad_win32_error *)pExceptionObject;
    }
    v7 = Buffer;
    goto LABEL_11;
  }
  if ( (unsigned int)GetLocalMachineDnsName((WCHAR **)&Block) )
  {
    v7 = Block;
    v6 = Block;
LABEL_11:
    v9 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v21, L"HTTP://");
    v10 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v9, v7);
    v11 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v10, L"/");
    v12 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v11, L"MSMQ");
    v13 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v12, L"/");
    v14 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v13, L"PRIVATE$");
    v15 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v14, L"/");
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v15, a2);
    std::basic_stringbuf<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::str(v22, a1);
    free(v6);
    goto LABEL_12;
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    a1,
    &ServiceName);
  free(Block);
LABEL_12:
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::`vbase destructor'(v20);
  return a1;
}

```

## disassembly

```asm
0x1800c7984  mov     [rsp-8+arg_10], rbx
0x1800c7989  mov     [rsp-8+arg_18], rsi
0x1800c798e  push    rbp
0x1800c798f  push    rdi
0x1800c7990  push    r14
0x1800c7992  lea     rbp, [rsp-80h]
0x1800c7997  sub     rsp, 180h
0x1800c799e  mov     rax, cs:__security_cookie
0x1800c79a5  xor     rax, rsp
0x1800c79a8  mov     [rbp+90h+var_20], rax
0x1800c79ac  mov     bl, r8b
0x1800c79af  mov     r14, rdx
0x1800c79b2  mov     rdi, rcx
0x1800c79b5  mov     [rsp+190h+Block], rcx
0x1800c79ba  xor     esi, esi
0x1800c79bc  lea     rcx, [rsp+190h+var_140]
0x1800c79c1  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@@std@@QEAA@H@Z; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>(int)
0x1800c79c6  nop
0x1800c79c7  mov     [rsp+190h+Block], rsi
0x1800c79cc  test    bl, bl
0x1800c79ce  jz      short loc_1800C7A09
0x1800c79d0  lea     rcx, [rsp+190h+Block]
0x1800c79d5  call    GetLocalMachineDnsName
0x1800c79da  test    eax, eax
0x1800c79dc  jnz     short loc_1800C79FF
0x1800c79de  lea     rdx, ServiceName
0x1800c79e5  mov     rcx, rdi
0x1800c79e8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x1800c79ed  nop
0x1800c79ee  mov     rcx, [rsp+190h+Block]; Block
0x1800c79f3  call    cs:__imp_free
0x1800c79f9  nop
0x1800c79fa  jmp     loc_1800C7B0A
0x1800c79ff  mov     rbx, [rsp+190h+Block]
0x1800c7a04  mov     rsi, rbx
0x1800c7a07  jmp     short loc_1800C7A85
0x1800c7a09  mov     [rsp+190h+nSize], 10h
0x1800c7a11  lea     rdx, [rsp+190h+nSize]; nSize
0x1800c7a16  lea     rcx, [rbp+90h+Buffer]; lpBuffer
0x1800c7a1a  call    cs:__imp_GetComputerNameW
0x1800c7a20  test    eax, eax
0x1800c7a22  jnz     short loc_1800C7A81
0x1800c7a24  call    cs:__imp_GetLastError
0x1800c7a2a  mov     ebx, eax
0x1800c7a2c  lea     rax, WPP_GLOBAL_Control
0x1800c7a33  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7a3a  cmp     rcx, rax
0x1800c7a3d  jz      short loc_1800C7A63
0x1800c7a3f  test    byte ptr [rcx+94h], 1
0x1800c7a46  jz      short loc_1800C7A63
0x1800c7a48  mov     edx, 0Fh
0x1800c7a4d  mov     r9d, ebx
0x1800c7a50  lea     r8, WPP_e54437e9c8b438399f706fc9b765c57c_Traceguids
0x1800c7a57  mov     rcx, [rcx+88h]
0x1800c7a5e  call    WPP_SF_d
0x1800c7a63  mov     edx, ebx; unsigned int
0x1800c7a65  lea     rcx, [rsp+190h+pExceptionObject]; this
0x1800c7a6a  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800c7a6f  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800c7a76  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1800c7a7b  call    _CxxThrowException_0
0x1800c7a81  lea     rbx, [rbp+90h+Buffer]
0x1800c7a85  lea     rdx, aHttp; "HTTP://"
0x1800c7a8c  lea     rcx, [rsp+190h+var_130]
0x1800c7a91  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7a96  mov     rcx, rax
0x1800c7a99  mov     rdx, rbx
0x1800c7a9c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7aa1  mov     rcx, rax
0x1800c7aa4  lea     rbx, asc_1800F7834; "/"
0x1800c7aab  mov     rdx, rbx
0x1800c7aae  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7ab3  mov     rcx, rax
0x1800c7ab6  lea     rdx, aMsmq_0; "MSMQ"
0x1800c7abd  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7ac2  mov     rcx, rax
0x1800c7ac5  mov     rdx, rbx
0x1800c7ac8  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7acd  mov     rcx, rax
0x1800c7ad0  lea     rdx, aPrivate_2; "PRIVATE$"
0x1800c7ad7  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7adc  mov     rcx, rax
0x1800c7adf  mov     rdx, rbx
0x1800c7ae2  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7ae7  mov     rcx, rax
0x1800c7aea  mov     rdx, r14
0x1800c7aed  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800c7af2  mov     rdx, rdi
0x1800c7af5  lea     rcx, [rsp+190h+var_128]
0x1800c7afa  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@2@XZ; std::basic_stringbuf<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::str(void)
0x1800c7aff  nop
0x1800c7b00  mov     rcx, rsi; Block
0x1800c7b03  call    cs:__imp_free
0x1800c7b09  nop
0x1800c7b0a  lea     rcx, [rsp+190h+var_140]
0x1800c7b0f  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::`vbase destructor'(void)
0x1800c7b14  mov     rax, rdi
0x1800c7b17  mov     rcx, [rbp+90h+var_20]
0x1800c7b1b  xor     rcx, rsp; StackCookie
0x1800c7b1e  call    __security_check_cookie
0x1800c7b23  lea     r11, [rsp+190h+var_10]
0x1800c7b2b  mov     rbx, [r11+30h]
0x1800c7b2f  mov     rsi, [r11+38h]
0x1800c7b33  mov     rsp, r11
0x1800c7b36  pop     r14
0x1800c7b38  pop     rdi
0x1800c7b39  pop     rbp
0x1800c7b3a  retn
```
