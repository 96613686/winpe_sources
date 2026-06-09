# CSessionObject::MaintainIt(void)

- ea: `0x18000290c`
- end: `0x18000307f`
- name: `?MaintainIt@CSessionObject@@QEAAXXZ`
- size: `1907`
- prototype: `void __fastcall(CSessionObject *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067140`

## callees

- `0x180001ca4`
- `0x18000290c`
- `0x180003150`
- `0x180003cf0`
- `0x18000cd08`
- `0x18000cddc`
- `0x18000f6c0`
- `0x18001234c`
- `0x1800123a8`
- `0x18006720c`
- `0x1800676b8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e0c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e0c`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x1800029e6`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x1800029e6`

## string_xrefs

- `0x180002999`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002a5a`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002a9b`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002b4f`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002bb4`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002c38`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002c8d`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002cd1`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002d58`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002da1`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002e24`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002e6f`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002ee0`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002f4d`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002ff8`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180002f6e`: `Status Attempt To Bind Succeeded.`
- `0x180002948`: `CAUTION: Inside MaintainSession with Maintain Session FALSE`
- `0x180002987`: `CAUTION: Inside MaintainSession with Maintain Session FALSE.`
- `0x180002d8c`: `STATUS: Attempt To Bind Failed.\n`
- `0x180002ed4`: `STATUS: Attempt To Bind Failed.\n`
- `0x180002d46`: `STATUS: Attempt To Bind Succeeded.\n`

## pseudocode

```c
void __fastcall CSessionObject::MaintainIt(CSessionObject *this, __int64 a2, __int64 a3, void *a4)
{
  int v5; // ebp
  int v6; // esi
  unsigned int v7; // r15d
  int v8; // ebx
  char *v9; // r14
  void (__fastcall **v10)(char *); // rax
  __int64 v11; // rdx
  int v12; // eax
  const wchar_t *v13; // rax
  __int64 v14; // r9
  void *v15; // rcx
  int i; // ebx
  int v17; // eax
  char *v18; // [rsp+A0h] [rbp+8h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( *((_DWORD *)this + 2) == 1 )
  {
    v8 = 1;
  }
  else
  {
    v18 = "CAUTION: Inside MaintainSession with Maintain Session FALSE";
    DtcWriteToEventLoggerExA(1u, 3u, 0x4000103Cu, a4, 1u, 0, (const char **)&v18, 0, 0);
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
      1555,
      L"CSessionObject::MaintainIt",
      0,
      L"CAUTION: Inside MaintainSession with Maintain Session FALSE.");
    v8 = 0;
  }
  v9 = (char *)this + 1040;
  (**((void (__fastcall ***)(char *))this + 130))((char *)this + 1040);
  *((_DWORD *)this + 25) = 2;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 130) + 8LL))((char *)this + 1040);
  RpcMgmtSetCancelTimeout(-1);
  if ( v8 == 1 )
  {
    while ( 1 )
    {
LABEL_5:
      while ( *((_DWORD *)this + 26) != 1 )
      {
        switch ( *((_DWORD *)this + 26) )
        {
          case 2:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1609,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State AGGRESSIVE\n");
            for ( i = 0; !i; i = 1 )
            {
              v17 = CSessionObject::AttemptToBind(this);
              *((_DWORD *)this + 342) = v17;
              v6 = v17;
              switch ( v17 )
              {
                case 0:
                  TraceStringInline(
                    1,
                    240,
                    L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                    1620,
                    L"CSessionObject::MaintainIt",
                    0,
                    L"Status Attempt To Bind Succeeded.");
                  goto LABEL_5;
                case -2147483344:
                  TraceStringInline(
                    1,
                    240,
                    L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                    1627,
                    L"CSessionObject::MaintainIt",
                    0,
                    L"STATUS: Poke caused no response.");
                  break;
                case -2147483278:
                  *((_DWORD *)this + 2) = 0;
                  TraceStringInline(
                    1,
                    240,
                    L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                    1632,
                    L"CSessionObject::MaintainIt",
                    0,
                    L"STATUS: Session Bind failed as version numbers do not mactch");
                  goto LABEL_63;
                default:
                  TraceStringInline(
                    1,
                    240,
                    L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                    1637,
                    L"CSessionObject::MaintainIt",
                    0,
                    L"STATUS: Attempt To Bind Failed.\n");
                  break;
              }
              if ( !*((_DWORD *)this + 2) )
              {
                CSessionObject::SetStatus(this, 1);
                CSessionObject::SetState(this, 4);
                goto LABEL_63;
              }
            }
            if ( !v6 )
              continue;
LABEL_63:
            (**(void (__fastcall ***)(char *))v9)((char *)this + 1040);
            if ( !*((_DWORD *)this + 25) )
              *((_DWORD *)this + 25) = 1;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))((char *)this + 1040);
            (**(void (__fastcall ***)(char *))v9)((char *)this + 1040);
            *((_DWORD *)this + 26) = 4;
LABEL_66:
            (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))((char *)this + 1040);
            break;
          case 3:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1657,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State SLUGGISH");
            CSessionObject::SetStatus(this, 2);
            if ( !*((_DWORD *)this + 2) )
            {
              CSessionObject::SetStatus(this, 1);
              v11 = 4;
              goto LABEL_73;
            }
            if ( *((_DWORD *)this + 3) || *((_DWORD *)this + 4) )
            {
              CSessionObject::SetState(this, 2);
              *((_DWORD *)this + 3) = 0;
            }
            else
            {
              ++v7;
              v12 = CSessionObject::AttemptToBind(this);
              *((_DWORD *)this + 342) = v12;
              v6 = v12;
              *((_DWORD *)this + 4) = 0;
              if ( !v12 )
              {
                TraceStringInline(
                  1,
                  240,
                  L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                  1691,
                  L"CSessionObject::MaintainIt",
                  0,
                  L"STATUS: Attempt To Bind Succeeded.\n");
                goto LABEL_48;
              }
              if ( v12 == -2147483278 )
              {
                *((_DWORD *)this + 2) = 0;
              }
              else
              {
                v13 = L"STATUS: Poke caused no response.";
                if ( v6 != -2147483344 )
                  v13 = L"STATUS: Attempt To Bind Failed.\n";
                v14 = 1704;
                if ( v6 != -2147483344 )
                  v14 = 1708;
                TraceStringInline(
                  1,
                  240,
                  L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                  v14,
                  L"CSessionObject::MaintainIt",
                  0,
                  v13);
                if ( v7 > 1
                  && !(*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 102) + 88LL))((char *)this + 816) )
                {
                  *((_DWORD *)this + 2) = 0;
                }
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  v15 = (void *)*((_QWORD *)this + 16);
                  *((_DWORD *)this + 164) = 0;
                  WaitForSingleObject(v15, 0xFFFFFFFF);
                }
LABEL_48:
                TraceStringInline(
                  1,
                  240,
                  L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                  1728,
                  L"CSessionObject::MaintainIt",
                  0,
                  L"STATUS : Leaving State SLUGGISH\n");
              }
            }
            break;
          case 4:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1732,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State DECLARE_DOWN\n");
            *((_DWORD *)this + 3) = 0;
            CSessionObject::SendDOWNMessageToHotConnections(this);
            goto LABEL_30;
          case 5:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1744,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State DECLARE_UP\n");
            v10 = *(void (__fastcall ***)(char *))v9;
            *((_DWORD *)this + 3) = 0;
            *((_DWORD *)this + 164) = 0;
            (*v10)((char *)this + 1040);
            *((_DWORD *)this + 26) = 7;
            goto LABEL_66;
          case 6:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1759,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State DOWN\n");
            CSessionObject::SetStatus(this, 1);
            CRWLock::AcquireWriterLock((CSessionObject *)((char *)this + 1152));
            CRWLock::ReleaseWriterLock((CSessionObject *)((char *)this + 1152));
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 88LL))(*((_QWORD *)this + 21));
            if ( !v5 )
            {
              CSessionObject::SendDOWNMessageToAllConnections(this);
              v5 = 1;
            }
            CSessionObject::SetState(this, 1);
            break;
          case 7:
            v5 = 0;
            CSessionObject::MaintainItInUpState(this);
            break;
          case 8:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1799,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State TEARDOWN\n");
            if ( g_fShutDownAll == 1 )
              return;
            v6 = 0;
            if ( *((_DWORD *)this + 25) == 1 )
            {
              v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 80) + 24LL))(
                     *((_QWORD *)this + 80),
                     *((unsigned int *)this + 24),
                     2);
              goto LABEL_21;
            }
            if ( *((_DWORD *)this + 25) == 3 )
            {
              v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 80) + 24LL))(
                     *((_QWORD *)this + 80),
                     *((unsigned int *)this + 24),
                     0);
              CRWLock::AcquireWriterLock((CSessionObject *)((char *)this + 1152));
              CRWLock::ReleaseWriterLock((CSessionObject *)((char *)this + 1152));
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 88LL))(*((_QWORD *)this + 21));
              if ( !v5 )
              {
                CSessionObject::SendDOWNMessageToAllConnections(this);
                v5 = 1;
              }
LABEL_21:
              if ( v6 )
                TraceStringInline(
                  1,
                  3,
                  L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                  1856,
                  L"CSessionObject::MaintainIt",
                  0,
                  L"ERROR: TEARDOWN failed.\n");
            }
LABEL_30:
            v11 = 1;
            goto LABEL_73;
          case 9:
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              1869,
              L"CSessionObject::MaintainIt",
              0,
              L"STATUS : In State OBLIVION\n");
            return;
        }
      }
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        1582,
        L"CSessionObject::MaintainIt",
        0,
        L"STATUS : In State WHATTODO\n");
      *((_DWORD *)this + 6) = 0;
      if ( !*((_DWORD *)this + 2) )
        break;
      if ( *((_DWORD *)this + 3) || *((_DWORD *)this + 4) )
      {
        CSessionObject::SetStatus(this, 2);
        v11 = 2;
LABEL_73:
        CSessionObject::SetState(this, v11);
      }
      else
      {
        CSessionObject::SetStatus(this, 2);
        CSessionObject::SetState(this, 3);
        v7 = 0;
      }
    }
    CSessionObject::SetStatus(this, 1);
    v11 = 9;
    goto LABEL_73;
  }
}

```

## disassembly

```asm
0x18000290c  push    rbx
0x18000290e  push    rbp
0x18000290f  push    rsi
0x180002910  push    rdi
0x180002911  push    r12
0x180002913  push    r13
0x180002915  push    r14
0x180002917  push    r15
0x180002919  sub     rsp, 58h
0x18000291d  xor     r12d, r12d
0x180002920  lea     rbx, aCsessionobject_0; "CSessionObject::MaintainIt"
0x180002927  mov     rdi, rcx
0x18000292a  mov     ebp, r12d
0x18000292d  mov     esi, r12d
0x180002930  mov     r15d, r12d
0x180002933  lea     r13d, [r12+1]
0x180002938  cmp     [rcx+8], r13d
0x18000293c  jnz     short loc_180002943
0x18000293e  mov     ebx, r13d
0x180002941  jmp     short loc_1800029B8
0x180002943  mov     [rsp+98h+var_58], r12d; int
0x180002948  lea     rax, aCautionInsideM_0; "CAUTION: Inside MaintainSession with Ma"...
0x18000294f  mov     [rsp+98h+var_60], r12; void *
0x180002954  mov     edx, 3; unsigned __int16
0x180002959  mov     [rsp+98h+arg_0], rax
0x180002961  mov     ecx, r13d; unsigned __int16
0x180002964  lea     rax, [rsp+98h+arg_0]
0x18000296c  mov     r8d, 4000103Ch; unsigned int
0x180002972  mov     [rsp+98h+var_68], rax; char **
0x180002977  mov     [rsp+98h+var_70], r12d; unsigned int
0x18000297c  mov     [rsp+98h+var_78], r13w; unsigned __int16
0x180002982  call    ?DtcWriteToEventLoggerExA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x180002987  lea     rax, aCautionInsideM; "CAUTION: Inside MaintainSession with Ma"...
0x18000298e  mov     r9d, 613h
0x180002994  mov     [rsp+98h+var_68], rax
0x180002999  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x1800029a0  mov     qword ptr [rsp+98h+var_70], r12
0x1800029a5  mov     edx, r13d
0x1800029a8  mov     ecx, r13d
0x1800029ab  mov     qword ptr [rsp+98h+var_78], rbx
0x1800029b0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800029b5  mov     ebx, r12d
0x1800029b8  lea     r14, [rdi+410h]
0x1800029bf  mov     rax, [r14]
0x1800029c2  mov     rcx, r14
0x1800029c5  mov     rax, [rax]
0x1800029c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029cd  mov     dword ptr [rdi+64h], 2
0x1800029d4  mov     rax, [r14]
0x1800029d7  mov     rcx, r14
0x1800029da  mov     rax, [rax+8]
0x1800029de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e3  or      ecx, 0FFFFFFFFh; Timeout
0x1800029e6  call    cs:__imp_RpcMgmtSetCancelTimeout
0x1800029ec  cmp     ebx, r13d
0x1800029ef  jnz     loc_180002A78
0x1800029f5  lea     rbx, aCsessionobject_0; "CSessionObject::MaintainIt"
0x1800029fc  mov     ecx, [rdi+68h]
0x1800029ff  sub     ecx, r13d
0x180002a02  jz      loc_180002FE6
0x180002a08  sub     ecx, r13d
0x180002a0b  jz      loc_180002E5D
0x180002a11  sub     ecx, r13d
0x180002a14  jz      loc_180002CBF
0x180002a1a  sub     ecx, r13d
0x180002a1d  jz      loc_180002C7B
0x180002a23  sub     ecx, r13d
0x180002a26  jz      loc_180002C26
0x180002a2c  sub     ecx, r13d
0x180002a2f  jz      loc_180002BA2
0x180002a35  sub     ecx, r13d
0x180002a38  jz      loc_180002B92
0x180002a3e  sub     ecx, r13d
0x180002a41  jz      short loc_180002A89
0x180002a43  cmp     ecx, r13d
0x180002a46  jnz     short loc_1800029FC
0x180002a48  lea     rax, aStatusInStateO; "STATUS : In State OBLIVION\n"
0x180002a4f  mov     r9d, 74Dh
0x180002a55  mov     [rsp+98h+var_68], rax
0x180002a5a  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002a61  mov     qword ptr [rsp+98h+var_70], r12
0x180002a66  mov     edx, 0F0h
0x180002a6b  mov     ecx, r13d
0x180002a6e  mov     qword ptr [rsp+98h+var_78], rbx
0x180002a73  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002a78  add     rsp, 58h
0x180002a7c  pop     r15
0x180002a7e  pop     r14
0x180002a80  pop     r13
0x180002a82  pop     r12
0x180002a84  pop     rdi
0x180002a85  pop     rsi
0x180002a86  pop     rbp
0x180002a87  pop     rbx
0x180002a88  retn
0x180002a89  lea     rax, aStatusInStateT; "STATUS : In State TEARDOWN\n"
0x180002a90  mov     r9d, 707h
0x180002a96  mov     [rsp+98h+var_68], rax
0x180002a9b  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002aa2  mov     qword ptr [rsp+98h+var_70], r12
0x180002aa7  mov     edx, 0F0h
0x180002aac  mov     ecx, r13d
0x180002aaf  mov     qword ptr [rsp+98h+var_78], rbx
0x180002ab4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002ab9  cmp     cs:?g_fShutDownAll@@3HA, r13d; int g_fShutDownAll
0x180002ac0  jz      short loc_180002A78
0x180002ac2  mov     ecx, [rdi+64h]
0x180002ac5  mov     esi, r12d
0x180002ac8  sub     ecx, r13d
0x180002acb  jz      loc_180002B72
0x180002ad1  cmp     ecx, 2
0x180002ad4  jnz     loc_180002CB7
0x180002ada  mov     rcx, [rdi+280h]
0x180002ae1  xor     r8d, r8d
0x180002ae4  mov     edx, [rdi+60h]
0x180002ae7  mov     rax, [rcx]
0x180002aea  mov     rax, [rax+18h]
0x180002aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af3  lea     rbx, [rdi+480h]
0x180002afa  mov     esi, eax
0x180002afc  mov     rcx, rbx; this
0x180002aff  call    ?AcquireWriterLock@CRWLock@@QEAAJXZ; CRWLock::AcquireWriterLock(void)
0x180002b04  mov     rcx, rbx; this
0x180002b07  call    ?ReleaseWriterLock@CRWLock@@QEAAJXZ; CRWLock::ReleaseWriterLock(void)
0x180002b0c  mov     rcx, [rdi+0A8h]
0x180002b13  mov     rdx, [rcx]
0x180002b16  mov     rax, [rdx+58h]
0x180002b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1f  test    ebp, ebp
0x180002b21  jnz     short loc_180002B2E
0x180002b23  mov     rcx, rdi; this
0x180002b26  call    ?SendDOWNMessageToAllConnections@CSessionObject@@QEAAXXZ; CSessionObject::SendDOWNMessageToAllConnections(void)
0x180002b2b  mov     ebp, r13d
0x180002b2e  lea     rbx, aCsessionobject_0; "CSessionObject::MaintainIt"
0x180002b35  test    esi, esi
0x180002b37  jz      loc_180002CB7
0x180002b3d  lea     rax, aErrorTeardownF; "ERROR: TEARDOWN failed.\n"
0x180002b44  mov     r9d, 740h
0x180002b4a  mov     [rsp+98h+var_68], rax
0x180002b4f  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002b56  mov     qword ptr [rsp+98h+var_70], r12
0x180002b5b  mov     edx, 3
0x180002b60  mov     ecx, r13d
0x180002b63  mov     qword ptr [rsp+98h+var_78], rbx
0x180002b68  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002b6d  jmp     loc_180002CB7
0x180002b72  mov     rcx, [rdi+280h]
0x180002b79  mov     r8d, 2
0x180002b7f  mov     edx, [rdi+60h]
0x180002b82  mov     rax, [rcx]
0x180002b85  mov     rax, [rax+18h]
0x180002b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b8e  mov     esi, eax
0x180002b90  jmp     short loc_180002B35
0x180002b92  mov     rcx, rdi; this
0x180002b95  mov     ebp, r12d
0x180002b98  call    ?MaintainItInUpState@CSessionObject@@AEAAXXZ; CSessionObject::MaintainItInUpState(void)
0x180002b9d  jmp     loc_1800029FC
0x180002ba2  lea     rax, aStatusInStateD_0; "STATUS : In State DOWN\n"
0x180002ba9  mov     r9d, 6DFh
0x180002baf  mov     [rsp+98h+var_68], rax
0x180002bb4  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002bbb  mov     qword ptr [rsp+98h+var_70], r12
0x180002bc0  mov     edx, 0F0h
0x180002bc5  mov     ecx, r13d
0x180002bc8  mov     qword ptr [rsp+98h+var_78], rbx
0x180002bcd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002bd2  mov     edx, r13d
0x180002bd5  mov     rcx, rdi
0x180002bd8  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180002bdd  lea     rbx, [rdi+480h]
0x180002be4  mov     rcx, rbx; this
0x180002be7  call    ?AcquireWriterLock@CRWLock@@QEAAJXZ; CRWLock::AcquireWriterLock(void)
0x180002bec  mov     rcx, rbx; this
0x180002bef  call    ?ReleaseWriterLock@CRWLock@@QEAAJXZ; CRWLock::ReleaseWriterLock(void)
0x180002bf4  mov     rcx, [rdi+0A8h]
0x180002bfb  mov     rax, [rcx]
0x180002bfe  mov     rax, [rax+58h]
0x180002c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c07  test    ebp, ebp
0x180002c09  jnz     short loc_180002C16
0x180002c0b  mov     rcx, rdi; this
0x180002c0e  call    ?SendDOWNMessageToAllConnections@CSessionObject@@QEAAXXZ; CSessionObject::SendDOWNMessageToAllConnections(void)
0x180002c13  mov     ebp, r13d
0x180002c16  mov     edx, r13d
0x180002c19  mov     rcx, rdi
0x180002c1c  call    ?SetState@CSessionObject@@QEAAXW4_SessionState@@@Z; CSessionObject::SetState(_SessionState)
0x180002c21  jmp     loc_1800029F5
0x180002c26  lea     rax, aStatusInStateD; "STATUS : In State DECLARE_UP\n"
0x180002c2d  mov     r9d, 6D0h
0x180002c33  mov     [rsp+98h+var_68], rax
0x180002c38  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002c3f  mov     qword ptr [rsp+98h+var_70], r12
0x180002c44  mov     edx, 0F0h
0x180002c49  mov     ecx, r13d
0x180002c4c  mov     qword ptr [rsp+98h+var_78], rbx
0x180002c51  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002c56  mov     rax, [r14]
0x180002c59  mov     rcx, r14
0x180002c5c  mov     [rdi+0Ch], r12d
0x180002c60  mov     [rdi+290h], r12d
0x180002c67  mov     rax, [rax]
0x180002c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6f  mov     dword ptr [rdi+68h], 7
0x180002c76  jmp     loc_180002FD2
0x180002c7b  lea     rax, aStatusInStateD_1; "STATUS : In State DECLARE_DOWN\n"
0x180002c82  mov     r9d, 6C4h
0x180002c88  mov     [rsp+98h+var_68], rax
0x180002c8d  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002c94  mov     qword ptr [rsp+98h+var_70], r12
0x180002c99  mov     edx, 0F0h
0x180002c9e  mov     ecx, r13d
0x180002ca1  mov     qword ptr [rsp+98h+var_78], rbx
0x180002ca6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002cab  mov     rcx, rdi; this
0x180002cae  mov     [rdi+0Ch], r12d
0x180002cb2  call    ?SendDOWNMessageToHotConnections@CSessionObject@@QEAAXXZ; CSessionObject::SendDOWNMessageToHotConnections(void)
0x180002cb7  mov     edx, r13d
0x180002cba  jmp     loc_180003072
0x180002cbf  lea     rax, aStatusInStateS; "STATUS : In State SLUGGISH"
0x180002cc6  mov     r9d, 679h
0x180002ccc  mov     [rsp+98h+var_68], rax
0x180002cd1  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002cd8  mov     qword ptr [rsp+98h+var_70], r12
0x180002cdd  mov     edx, 0F0h
0x180002ce2  mov     ecx, r13d
0x180002ce5  mov     qword ptr [rsp+98h+var_78], rbx
0x180002cea  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002cef  mov     edx, 2
0x180002cf4  mov     rcx, rdi
0x180002cf7  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180002cfc  cmp     [rdi+8], r12d
0x180002d00  jnz     short loc_180002D17
0x180002d02  mov     edx, r13d
0x180002d05  mov     rcx, rdi
0x180002d08  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180002d0d  mov     edx, 4
0x180002d12  jmp     loc_180003072
0x180002d17  cmp     [rdi+0Ch], r12d
0x180002d1b  jnz     loc_180002E47
0x180002d21  cmp     [rdi+10h], r12d
0x180002d25  jnz     loc_180002E47
0x180002d2b  mov     rcx, rdi; this
0x180002d2e  add     r15d, r13d
0x180002d31  call    ?AttemptToBind@CSessionObject@@AEAAJXZ; CSessionObject::AttemptToBind(void)
0x180002d36  mov     [rdi+558h], eax
0x180002d3c  mov     esi, eax
0x180002d3e  mov     [rdi+10h], r12d
0x180002d42  test    eax, eax
0x180002d44  jnz     short loc_180002D7B
0x180002d46  lea     rax, aStatusAttemptT; "STATUS: Attempt To Bind Succeeded.\n"
0x180002d4d  mov     r9d, 69Bh
0x180002d53  mov     [rsp+98h+var_68], rax
0x180002d58  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002d5f  mov     qword ptr [rsp+98h+var_70], r12
0x180002d64  mov     edx, 0F0h
0x180002d69  mov     ecx, r13d
0x180002d6c  mov     qword ptr [rsp+98h+var_78], rbx
0x180002d71  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002d76  jmp     loc_180002E12
0x180002d7b  cmp     esi, 80000172h
0x180002d81  jnz     short loc_180002D8C
0x180002d83  mov     [rdi+8], r12d
0x180002d87  jmp     loc_1800029FC
0x180002d8c  lea     rcx, aStatusAttemptT_0; "STATUS: Attempt To Bind Failed.\n"
0x180002d93  mov     edx, 80000130h
0x180002d98  cmp     esi, edx
0x180002d9a  lea     rax, aStatusPokeCaus; "STATUS: Poke caused no response."
0x180002da1  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002da8  mov     edx, 0F0h
0x180002dad  cmovnz  rax, rcx
0x180002db1  mov     ecx, 6ACh
0x180002db6  mov     [rsp+98h+var_68], rax
0x180002dbb  mov     qword ptr [rsp+98h+var_70], r12
0x180002dc0  mov     qword ptr [rsp+98h+var_78], rbx
0x180002dc5  lea     r9d, [rcx-4]
0x180002dc9  cmovnz  r9d, ecx
0x180002dcd  mov     ecx, r13d
0x180002dd0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002dd5  cmp     r15d, r13d
0x180002dd8  jbe     short loc_180002DF5
0x180002dda  lea     rcx, [rdi+330h]
0x180002de1  mov     rax, [rcx]
0x180002de4  mov     rax, [rax+58h]
0x180002de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ded  test    eax, eax
0x180002def  jnz     short loc_180002DF5
0x180002df1  mov     [rdi+8], r12d
0x180002df5  cmp     [rdi+8], r13d
0x180002df9  jnz     short loc_180002E12
0x180002dfb  mov     rcx, [rdi+80h]; hHandle
0x180002e02  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002e05  mov     [rdi+290h], r12d
0x180002e0c  call    cs:__imp_WaitForSingleObject
0x180002e12  lea     rax, aStatusLeavingS; "STATUS : Leaving State SLUGGISH\n"
0x180002e19  mov     r9d, 6C0h
0x180002e1f  mov     [rsp+98h+var_68], rax
0x180002e24  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002e2b  mov     qword ptr [rsp+98h+var_70], r12
0x180002e30  mov     edx, 0F0h
  ... truncated ...
```
