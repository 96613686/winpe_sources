# CMethodPart::ValidateBuffer(uchar *,unsigned __int64)

- ea: `0x180018130`
- end: `0x1800183e9`
- name: `?ValidateBuffer@CMethodPart@@SA_KPEAE_K@Z`
- size: `697`
- prototype: `unsigned __int64 __fastcall(unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017eb0`

## callees

- `0x180017f30`
- `0x180018130`
- `0x180019210`
- `0x18001cb00`
- `0x180035b08`
- `0x18006fa4c`
- `0x1800919b0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180018254`
- `wbemcomn!GetMemLogObject` at `0x1800182bb`
- `wbemcomn!GetMemLogObject` at `0x180018322`
- `wbemcomn!GetMemLogObject` at `0x180018389`
- `wbemcomn!GetMemLogObject` at `0x180018254`
- `wbemcomn!GetMemLogObject` at `0x1800182bb`
- `wbemcomn!GetMemLogObject` at `0x180018322`
- `wbemcomn!GetMemLogObject` at `0x180018389`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018262`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800182c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018330`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018397`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018262`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800182c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018330`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018397`

## pseudocode

```c
unsigned __int64 __fastcall CMethodPart::ValidateBuffer(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  unsigned __int8 *v7; // rdx
  int v8; // eax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  char v14; // [rsp+20h] [rbp-49h] BYREF
  int pExceptionObject; // [rsp+28h] [rbp-41h] BYREF
  void **v16; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v17[3]; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 *v18; // [rsp+58h] [rbp-11h]
  unsigned __int8 *v19; // [rsp+60h] [rbp-9h]
  _DWORD v20[4]; // [rsp+68h] [rbp-1h] BYREF
  _QWORD *v21; // [rsp+78h] [rbp+Fh]
  void ***v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]

  if ( a2 < 8 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  v4 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(
                    &pExceptionObject,
                    8,
                    24LL * *((unsigned __int16 *)a1 + 2));
  if ( v4 > a2 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v5 = CFastHeap::ValidateBuffer(&a1[v4], a2 - v4);
  if ( *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&pExceptionObject, v4, v5) > (unsigned __int64)*(unsigned int *)a1 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v17[1] = a1;
  v16 = &DummyMethodPartContainer::`vftable';
  v23 = 0;
  v17[0] = &CMethodPart::`vftable';
  v22 = &v16;
  v17[2] = a1 + 8;
  v6 = *((unsigned __int16 *)a1 + 2) + 2LL * *((unsigned __int16 *)a1 + 2) + 1;
  v21 = v17;
  v7 = &a1[8 * v6];
  if ( *(int *)v7 >= 0 )
  {
    v19 = v7;
    v18 = v7 + 12;
  }
  else
  {
    v18 = v7 + 4;
    v19 = (unsigned __int8 *)v20;
    v8 = *(_DWORD *)v7;
    v20[2] = 0;
    v20[0] = v8 & 0x7FFFFFFF;
    v20[1] = v8 & 0x7FFFFFFF;
  }
  if ( (int)CMethodPart::IsValidMethodPart((CMethodPart *)v17) < 0 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&v14;
  }
  return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x180018130  push    rbp
0x180018132  push    rbx
0x180018133  push    rsi
0x180018134  push    rdi
0x180018135  lea     rbp, [rsp-3Fh]
0x18001813a  sub     rsp, 0A8h
0x180018141  mov     rax, cs:__security_cookie
0x180018148  xor     rax, rsp
0x18001814b  mov     [rbp+57h+var_30], rax
0x18001814f  mov     rsi, rdx
0x180018152  mov     rdi, rcx
0x180018155  mov     edx, 8
0x18001815a  cmp     rsi, rdx
0x18001815d  jb      loc_180018254
0x180018163  movzx   eax, word ptr [rcx+4]
0x180018167  lea     rcx, [rbp+57h+pExceptionObject]
0x18001816b  lea     r8, [rax+rax*2]
0x18001816f  shl     r8, 3
0x180018173  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x180018178  mov     rbx, [rax]
0x18001817b  cmp     rbx, rsi
0x18001817e  ja      loc_1800182BB
0x180018184  sub     rsi, rbx
0x180018187  lea     rcx, [rbx+rdi]; unsigned __int8 *
0x18001818b  mov     rdx, rsi; unsigned __int64
0x18001818e  call    ?ValidateBuffer@CFastHeap@@SA_KPEAE_K@Z; CFastHeap::ValidateBuffer(uchar *,unsigned __int64)
0x180018193  mov     r8, rax
0x180018196  lea     rcx, [rbp+57h+pExceptionObject]
0x18001819a  mov     rdx, rbx
0x18001819d  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x1800181a2  mov     ecx, [rdi]
0x1800181a4  cmp     [rax], rcx
0x1800181a7  ja      loc_180018322
0x1800181ad  lea     rax, ??_7DummyMethodPartContainer@@6B@; const DummyMethodPartContainer::`vftable'
0x1800181b4  mov     [rbp+57h+var_78], rdi
0x1800181b8  mov     [rbp+57h+var_90], rax
0x1800181bc  xor     ebx, ebx
0x1800181be  lea     rax, ??_7CMethodPart@@6B@; const CMethodPart::`vftable'
0x1800181c5  mov     [rbp+57h+var_38], rbx
0x1800181c9  mov     [rbp+57h+var_80], rax
0x1800181cd  lea     rax, [rbp+57h+var_90]
0x1800181d1  mov     [rbp+57h+var_40], rax
0x1800181d5  lea     rax, [rdi+8]
0x1800181d9  mov     [rbp+57h+var_70], rax
0x1800181dd  movzx   eax, word ptr [rdi+4]
0x1800181e1  lea     rdx, ds:1[rax*2]
0x1800181e9  add     rdx, rax
0x1800181ec  lea     rax, [rbp+57h+var_80]
0x1800181f0  mov     [rbp+57h+var_48], rax
0x1800181f4  lea     rdx, [rdi+rdx*8]
0x1800181f8  cmp     [rdx], ebx
0x1800181fa  jge     short loc_180018246
0x1800181fc  lea     rax, [rdx+4]
0x180018200  mov     [rbp+57h+var_68], rax
0x180018204  lea     rax, [rbp+57h+var_58]
0x180018208  mov     [rbp+57h+var_60], rax
0x18001820c  mov     eax, [rdx]
0x18001820e  btr     eax, 1Fh
0x180018212  mov     [rbp+57h+var_50], ebx
0x180018215  mov     [rbp+57h+var_58], eax
0x180018218  mov     [rbp+57h+var_54], eax
0x18001821b  lea     rcx, [rbp+57h+var_80]; this
0x18001821f  call    ?IsValidMethodPart@CMethodPart@@QEAAJXZ; CMethodPart::IsValidMethodPart(void)
0x180018224  test    eax, eax
0x180018226  js      loc_180018389
0x18001822c  mov     eax, [rdi]
0x18001822e  mov     rcx, [rbp+57h+var_30]
0x180018232  xor     rcx, rsp; StackCookie
0x180018235  call    __security_check_cookie
0x18001823a  add     rsp, 0A8h
0x180018241  pop     rdi
0x180018242  pop     rsi
0x180018243  pop     rbx
0x180018244  pop     rbp
0x180018245  retn
0x180018246  lea     rax, [rdx+0Ch]
0x18001824a  mov     [rbp+57h+var_60], rdx
0x18001824e  mov     [rbp+57h+var_68], rax
0x180018252  jmp     short loc_18001821B
0x180018254  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001825a  mov     rcx, rax
0x18001825d  mov     edx, 0FFFFFFFEh
0x180018262  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180018268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001826f  lea     rax, WPP_GLOBAL_Control
0x180018276  cmp     rcx, rax
0x180018279  jz      short loc_1800182A3
0x18001827b  test    byte ptr [rcx+1Ch], 1
0x18001827f  jz      short loc_1800182A3
0x180018281  cmp     byte ptr [rcx+19h], 2
0x180018285  jb      short loc_1800182A3
0x180018287  mov     rcx, [rcx+10h]
0x18001828b  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180018292  mov     edx, 0Eh
0x180018297  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18001829e  call    WPP_SF_s
0x1800182a3  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800182aa  mov     [rbp+57h+pExceptionObject], 57h ; 'W'
0x1800182b1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800182b5  call    _CxxThrowException_0
0x1800182bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800182c1  mov     rcx, rax
0x1800182c4  mov     edx, 0FFFFFFFEh
0x1800182c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800182cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182d6  lea     rax, WPP_GLOBAL_Control
0x1800182dd  cmp     rcx, rax
0x1800182e0  jz      short loc_18001830A
0x1800182e2  test    byte ptr [rcx+1Ch], 1
0x1800182e6  jz      short loc_18001830A
0x1800182e8  cmp     byte ptr [rcx+19h], 2
0x1800182ec  jb      short loc_18001830A
0x1800182ee  mov     rcx, [rcx+10h]
0x1800182f2  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x1800182f9  mov     edx, 0Fh
0x1800182fe  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x180018305  call    WPP_SF_s
0x18001830a  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180018311  mov     [rbp+57h+pExceptionObject], 0Dh
0x180018318  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001831c  call    _CxxThrowException_0
0x180018322  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180018328  mov     rcx, rax
0x18001832b  mov     edx, 0FFFFFFFEh
0x180018330  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180018336  mov     rcx, cs:WPP_GLOBAL_Control
0x18001833d  lea     rax, WPP_GLOBAL_Control
0x180018344  cmp     rcx, rax
0x180018347  jz      short loc_180018371
0x180018349  test    byte ptr [rcx+1Ch], 1
0x18001834d  jz      short loc_180018371
0x18001834f  cmp     byte ptr [rcx+19h], 2
0x180018353  jb      short loc_180018371
0x180018355  mov     rcx, [rcx+10h]
0x180018359  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180018360  mov     edx, 10h
0x180018365  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18001836c  call    WPP_SF_s
0x180018371  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180018378  mov     [rbp+57h+pExceptionObject], 0Dh
0x18001837f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018383  call    _CxxThrowException_0
0x180018389  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001838f  mov     rcx, rax
0x180018392  mov     edx, 0FFFFFFFEh
0x180018397  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001839d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183a4  lea     rax, WPP_GLOBAL_Control
0x1800183ab  cmp     rcx, rax
0x1800183ae  jz      short loc_1800183D8
0x1800183b0  test    byte ptr [rcx+1Ch], 1
0x1800183b4  jz      short loc_1800183D8
0x1800183b6  cmp     byte ptr [rcx+19h], 2
0x1800183ba  jb      short loc_1800183D8
0x1800183bc  mov     rcx, [rcx+10h]
0x1800183c0  lea     r9, aCxException; "CX_Exception()"
0x1800183c7  mov     edx, 11h
0x1800183cc  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x1800183d3  call    WPP_SF_s
0x1800183d8  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x1800183df  lea     rcx, [rbp+57h+var_A0]; pExceptionObject
0x1800183e3  call    _CxxThrowException_0
```
