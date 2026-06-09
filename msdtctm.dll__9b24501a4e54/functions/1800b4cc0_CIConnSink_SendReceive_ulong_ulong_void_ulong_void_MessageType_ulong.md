# CIConnSink::SendReceive(ulong,ulong,void *,ulong *,void * *,_MessageType,ulong *)

- ea: `0x1800b4cc0`
- end: `0x1800b509f`
- name: `?SendReceive@CIConnSink@@UEAAJKKPEAXPEAKPEAPEAXW4_MessageType@@1@Z`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x1800b4cc0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4e23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4fde`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4e23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4e34`

## string_xrefs

- `0x1800b4d0b`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4d6b`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4e56`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4e9f`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4f4a`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b5001`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`

## pseudocode

```c
__int64 __fastcall CIConnSink::SendReceive(
        _DWORD *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6,
        int a7,
        _DWORD *a8)
{
  int v12; // eax
  signed int LastError; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // [rsp+38h] [rbp-60h]
  __int64 v18; // [rsp+38h] [rbp-60h]

  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
    544,
    L"CIConnSink::SendReceive",
    0,
    L"Entering SendReceive, this=%p",
    a1);
  if ( !a5 || !a6 )
    return 2147942487LL;
  *a6 = 0;
  *a5 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a3 && !a4 )
    return 2147942487LL;
  if ( (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 48LL))(a1) )
  {
    TraceStringInline(
      1,
      5,
      L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
      600,
      L"CIConnSink::SendReceive",
      0,
      L"Blocking on m_hConnectionStatus=0x%x",
      *((_QWORD *)a1 + 14));
    LastError = WaitForSingleObject(*((HANDLE *)a1 + 14), 0xFFFFFFFF);
    v15 = LastError;
    if ( LastError )
    {
      if ( LastError != -1 )
        goto LABEL_19;
    }
    else
    {
      TraceStringInline(
        1,
        5,
        L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
        618,
        L"CIConnSink::SendReceive",
        0,
        L"Woke up, received m_hConnectionStatus=0x%x",
        *((_QWORD *)a1 + 14));
      a1[11] = a7;
      v16 = *((_QWORD *)a1 + 1);
      *((_QWORD *)a1 + 4) = a4;
      a1[6] = 0;
      a1[10] = a3;
      a1[13] = 0;
      if ( !v16 )
      {
        v15 = -2147168228;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
          632,
          L"CIConnSink::SendReceive",
          -2147168228,
          L"Connection went down while in SendReceive");
        goto LABEL_34;
      }
      TraceStringInline(
        1,
        5,
        L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
        636,
        L"CIConnSink::SendReceive",
        0,
        L"Requesting buffer on m_pIConnection=%p",
        v16);
      v15 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD))a1 + 1))(*((_QWORD *)a1 + 1), a3, a2, 0);
      if ( v15 )
      {
        LODWORD(v18) = a3;
        v15 = -2147168228;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
          643,
          L"CIConnSink::SendReceive",
          -2147168228,
          L"Errored out from m_pIConnection->RequestBuffer, dwsize=%d MsgTag=0x%x ",
          v18,
          a2);
        goto LABEL_34;
      }
      TraceStringInline(
        1,
        5,
        L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
        647,
        L"CIConnSink::SendReceive",
        0,
        L"Blocking on m_hSendReceiveEvent=0x%x",
        *((_QWORD *)a1 + 13));
      LastError = WaitForSingleObject(*((HANDLE *)a1 + 13), 0xFFFFFFFF);
      if ( !LastError )
      {
        TraceStringInline(
          1,
          5,
          L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
          665,
          L"CIConnSink::SendReceive",
          0,
          L"Woke up, received m_hSendReceiveEvent=0x%x",
          *((_QWORD *)a1 + 13));
        (**((void (__fastcall ***)(__int64))a1 + 15))((__int64)(a1 + 30));
        *a5 = a1[13];
        if ( a1[16] )
          *a6 = *((_QWORD *)a1 + 7);
        if ( a8 )
          *a8 = a1[16];
        (*(void (__fastcall **)(_DWORD *))(*((_QWORD *)a1 + 15) + 8LL))(a1 + 30);
        goto LABEL_34;
      }
      if ( LastError != -1 )
      {
        if ( LastError <= 0 )
        {
          v15 = LastError;
          goto LABEL_34;
        }
        goto LABEL_20;
      }
    }
    LastError = GetLastError();
    v15 = LastError;
LABEL_19:
    if ( LastError <= 0 )
    {
LABEL_34:
      (*(void (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v15);
      return v15;
    }
LABEL_20:
    v15 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_34;
  }
  LODWORD(v17) = a1[12];
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
    571,
    L"CIConnSink::SendReceive",
    0,
    L"Something went wrong with IntendToSendReceive, m_MessageTagIn=0x%x",
    v17);
  v12 = a1[12];
  if ( v12 )
  {
    if ( v12 == 3 )
      return 2147799296LL;
    if ( v12 == 6 )
      return 2147799069LL;
    if ( v12 != 9 )
      return 2147500037LL;
  }
  return 2147799068LL;
}

```

## disassembly

```asm
0x1800b4cc0  mov     r11, rsp
0x1800b4cc3  push    rbx
0x1800b4cc4  push    rbp
0x1800b4cc5  push    rsi
0x1800b4cc6  push    rdi
0x1800b4cc7  push    r12
0x1800b4cc9  push    r13
0x1800b4ccb  push    r14
0x1800b4ccd  push    r15
0x1800b4ccf  sub     rsp, 58h
0x1800b4cd3  mov     [r11-60h], rcx
0x1800b4cd7  lea     rax, aEnteringSendre; "Entering SendReceive, this=%p"
0x1800b4cde  mov     [r11-68h], rax
0x1800b4ce2  xor     ebx, ebx
0x1800b4ce4  mov     r14, r9
0x1800b4ce7  mov     [r11-70h], rbx
0x1800b4ceb  mov     ebp, r8d
0x1800b4cee  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4cf5  mov     r13d, edx
0x1800b4cf8  mov     [r11-78h], rax
0x1800b4cfc  mov     rdi, rcx
0x1800b4cff  lea     edx, [rbx+5]
0x1800b4d02  lea     ecx, [rbx+1]
0x1800b4d05  mov     r9d, 220h
0x1800b4d0b  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4d12  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4d17  mov     r12, [rsp+98h+arg_20]
0x1800b4d1f  test    r12, r12
0x1800b4d22  jz      loc_1800B5089
0x1800b4d28  mov     r15, [rsp+98h+arg_28]
0x1800b4d30  test    r15, r15
0x1800b4d33  jz      loc_1800B5089
0x1800b4d39  mov     rsi, [rsp+98h+arg_38]
0x1800b4d41  mov     [r15], rbx
0x1800b4d44  mov     [r12], ebx
0x1800b4d48  test    rsi, rsi
0x1800b4d4b  jz      short loc_1800B4D4F
0x1800b4d4d  mov     [rsi], ebx
0x1800b4d4f  test    ebp, ebp
0x1800b4d51  jz      short loc_1800B4D5C
0x1800b4d53  test    r14, r14
0x1800b4d56  jz      loc_1800B5089
0x1800b4d5c  mov     rax, [rdi]
0x1800b4d5f  mov     rcx, rdi
0x1800b4d62  mov     rax, [rax+30h]
0x1800b4d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d6b  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4d72  mov     edx, 5
0x1800b4d77  lea     ecx, [rdx-4]
0x1800b4d7a  test    eax, eax
0x1800b4d7c  jnz     short loc_1800B4DEB
0x1800b4d7e  mov     eax, [rdi+30h]
0x1800b4d81  mov     r9d, 23Bh
0x1800b4d87  mov     dword ptr [rsp+98h+var_60], eax
0x1800b4d8b  lea     rax, aSomethingWentW; "Something went wrong with IntendToSendR"...
0x1800b4d92  mov     [rsp+98h+var_68], rax
0x1800b4d97  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4d9e  mov     [rsp+98h+var_70], rbx
0x1800b4da3  mov     [rsp+98h+var_78], rax
0x1800b4da8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4dad  mov     eax, [rdi+30h]
0x1800b4db0  test    eax, eax
0x1800b4db2  jz      short loc_1800B4DE1
0x1800b4db4  cmp     eax, 3
0x1800b4db7  jz      short loc_1800B4DD7
0x1800b4db9  cmp     eax, 6
0x1800b4dbc  jz      short loc_1800B4DCD
0x1800b4dbe  cmp     eax, 9
0x1800b4dc1  jz      short loc_1800B4DE1
0x1800b4dc3  mov     eax, 80004005h
0x1800b4dc8  jmp     loc_1800B508E
0x1800b4dcd  mov     eax, 8004D01Dh
0x1800b4dd2  jmp     loc_1800B508E
0x1800b4dd7  mov     eax, 8004D100h
0x1800b4ddc  jmp     loc_1800B508E
0x1800b4de1  mov     eax, 8004D01Ch
0x1800b4de6  jmp     loc_1800B508E
0x1800b4deb  mov     rax, [rdi+70h]
0x1800b4def  mov     r9d, 258h
0x1800b4df5  mov     [rsp+98h+var_60], rax
0x1800b4dfa  lea     rax, aBlockingOnMHco; "Blocking on m_hConnectionStatus=0x%x"
0x1800b4e01  mov     [rsp+98h+var_68], rax
0x1800b4e06  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4e0d  mov     [rsp+98h+var_70], rbx
0x1800b4e12  mov     [rsp+98h+var_78], rax
0x1800b4e17  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4e1c  mov     rcx, [rdi+70h]; hHandle
0x1800b4e20  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b4e23  call    cs:__imp_WaitForSingleObject
0x1800b4e29  mov     ebx, eax
0x1800b4e2b  test    eax, eax
0x1800b4e2d  jz      short loc_1800B4E52
0x1800b4e2f  cmp     eax, 0FFFFFFFFh
0x1800b4e32  jnz     short loc_1800B4E3C
0x1800b4e34  call    cs:__imp_GetLastError
0x1800b4e3a  mov     ebx, eax
0x1800b4e3c  test    eax, eax
0x1800b4e3e  jle     loc_1800B5074
0x1800b4e44  movzx   ebx, ax
0x1800b4e47  or      ebx, 80070000h
0x1800b4e4d  jmp     loc_1800B5074
0x1800b4e52  mov     rax, [rdi+70h]
0x1800b4e56  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4e5d  mov     [rsp+98h+var_60], rax
0x1800b4e62  mov     edx, 5
0x1800b4e67  lea     rax, aWokeUpReceived; "Woke up, received m_hConnectionStatus=0"...
0x1800b4e6e  mov     r9d, 26Ah
0x1800b4e74  mov     [rsp+98h+var_68], rax
0x1800b4e79  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4e80  mov     [rsp+98h+var_70], 0
0x1800b4e89  lea     ebx, [rdx-4]
0x1800b4e8c  mov     [rsp+98h+var_78], rax
0x1800b4e91  mov     ecx, ebx
0x1800b4e93  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4e98  mov     eax, [rsp+98h+arg_30]
0x1800b4e9f  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4ea6  mov     [rdi+2Ch], eax
0x1800b4ea9  mov     rax, [rdi+8]
0x1800b4ead  mov     [rdi+20h], r14
0x1800b4eb1  xor     r14d, r14d
0x1800b4eb4  mov     [rdi+18h], r14d
0x1800b4eb8  mov     [rdi+28h], ebp
0x1800b4ebb  mov     [rdi+34h], r14d
0x1800b4ebf  test    rax, rax
0x1800b4ec2  jnz     short loc_1800B4EFF
0x1800b4ec4  lea     rcx, aConnectionWent; "Connection went down while in SendRecei"...
0x1800b4ecb  mov     eax, 8004D01Ch
0x1800b4ed0  mov     [rsp+98h+var_68], rcx
0x1800b4ed5  mov     ebx, eax
0x1800b4ed7  mov     dword ptr [rsp+98h+var_70], eax
0x1800b4edb  mov     r9d, 278h
0x1800b4ee1  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4ee8  mov     [rsp+98h+var_78], rax
0x1800b4eed  lea     eax, [r14+1]
0x1800b4ef1  mov     edx, eax
0x1800b4ef3  mov     ecx, eax
0x1800b4ef5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4efa  jmp     loc_1800B5074
0x1800b4eff  mov     [rsp+98h+var_60], rax
0x1800b4f04  mov     r9d, 27Ch
0x1800b4f0a  lea     rax, aRequestingBuff; "Requesting buffer on m_pIConnection=%p"
0x1800b4f11  mov     edx, 5
0x1800b4f16  mov     [rsp+98h+var_68], rax
0x1800b4f1b  mov     ecx, ebx
0x1800b4f1d  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4f24  mov     [rsp+98h+var_70], r14
0x1800b4f29  mov     [rsp+98h+var_78], rax
0x1800b4f2e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4f33  mov     rcx, [rdi+8]
0x1800b4f37  xor     r9d, r9d
0x1800b4f3a  mov     r8d, r13d
0x1800b4f3d  mov     edx, ebp
0x1800b4f3f  mov     rax, [rcx]
0x1800b4f42  mov     rax, [rax]
0x1800b4f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4f4a  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4f51  mov     ebx, eax
0x1800b4f53  test    eax, eax
0x1800b4f55  jz      short loc_1800B4F9C
0x1800b4f57  mov     [rsp+98h+var_58], r13d
0x1800b4f5c  lea     rcx, aErroredOutFrom; "Errored out from m_pIConnection->Reques"...
0x1800b4f63  mov     dword ptr [rsp+98h+var_60], ebp
0x1800b4f67  mov     eax, 8004D01Ch
0x1800b4f6c  mov     [rsp+98h+var_68], rcx
0x1800b4f71  mov     ebx, eax
0x1800b4f73  mov     dword ptr [rsp+98h+var_70], eax
0x1800b4f77  mov     r9d, 283h
0x1800b4f7d  lea     rax, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4f84  mov     [rsp+98h+var_78], rax
0x1800b4f89  mov     eax, 1
0x1800b4f8e  mov     edx, eax
0x1800b4f90  mov     ecx, eax
0x1800b4f92  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4f97  jmp     loc_1800B5074
0x1800b4f9c  mov     rax, [rdi+68h]
0x1800b4fa0  lea     r13, aCiconnsinkSend_0; "CIConnSink::SendReceive"
0x1800b4fa7  mov     [rsp+98h+var_60], rax
0x1800b4fac  mov     edx, 5
0x1800b4fb1  lea     rax, aBlockingOnMHse; "Blocking on m_hSendReceiveEvent=0x%x"
0x1800b4fb8  mov     r9d, 287h
0x1800b4fbe  mov     [rsp+98h+var_68], rax
0x1800b4fc3  mov     [rsp+98h+var_70], r14
0x1800b4fc8  lea     ebp, [rdx-4]
0x1800b4fcb  mov     [rsp+98h+var_78], r13
0x1800b4fd0  mov     ecx, ebp
0x1800b4fd2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4fd7  mov     rcx, [rdi+68h]; hHandle
0x1800b4fdb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b4fde  call    cs:__imp_WaitForSingleObject
0x1800b4fe4  test    eax, eax
0x1800b4fe6  jz      short loc_1800B4FFD
0x1800b4fe8  cmp     eax, 0FFFFFFFFh
0x1800b4feb  jz      loc_1800B4E34
0x1800b4ff1  test    eax, eax
0x1800b4ff3  jg      loc_1800B4E44
0x1800b4ff9  mov     ebx, eax
0x1800b4ffb  jmp     short loc_1800B5074
0x1800b4ffd  mov     rax, [rdi+68h]
0x1800b5001  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b5008  mov     [rsp+98h+var_60], rax
0x1800b500d  mov     r9d, 299h
0x1800b5013  lea     rax, aWokeUpReceived_0; "Woke up, received m_hSendReceiveEvent=0"...
0x1800b501a  mov     edx, 5
0x1800b501f  mov     [rsp+98h+var_68], rax
0x1800b5024  mov     ecx, ebp
0x1800b5026  mov     [rsp+98h+var_70], r14
0x1800b502b  mov     [rsp+98h+var_78], r13
0x1800b5030  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b5035  lea     r14, [rdi+78h]
0x1800b5039  mov     rax, [r14]
0x1800b503c  mov     rcx, r14
0x1800b503f  mov     rax, [rax]
0x1800b5042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5047  mov     eax, [rdi+34h]
0x1800b504a  mov     [r12], eax
0x1800b504e  cmp     dword ptr [rdi+40h], 0
0x1800b5052  jbe     short loc_1800B505B
0x1800b5054  mov     rax, [rdi+38h]
0x1800b5058  mov     [r15], rax
0x1800b505b  test    rsi, rsi
0x1800b505e  jz      short loc_1800B5065
0x1800b5060  mov     eax, [rdi+40h]
0x1800b5063  mov     [rsi], eax
0x1800b5065  mov     rax, [r14]
0x1800b5068  mov     rcx, r14
0x1800b506b  mov     rax, [rax+8]
0x1800b506f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5074  mov     rax, [rdi]
0x1800b5077  mov     edx, ebx
0x1800b5079  mov     rcx, rdi
0x1800b507c  mov     rax, [rax+48h]
0x1800b5080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5085  mov     eax, ebx
0x1800b5087  jmp     short loc_1800B508E
0x1800b5089  mov     eax, 80070057h
0x1800b508e  add     rsp, 58h
0x1800b5092  pop     r15
0x1800b5094  pop     r14
0x1800b5096  pop     r13
0x1800b5098  pop     r12
0x1800b509a  pop     rdi
0x1800b509b  pop     rsi
0x1800b509c  pop     rbp
0x1800b509d  pop     rbx
0x1800b509e  retn
```
