# _FlushThread(ulong *)

- ea: `0x180007b40`
- end: `0x180007d73`
- name: `?_FlushThread@@YAKPEAK@Z`
- size: `563`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000651c`
- `0x18000699c`
- `0x1800073b4`
- `0x180007b40`
- `0x18001266c`
- `0x180012830`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180007c1b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180007c1b`
- `msvcrt!_endthread` at `0x180007d08`
- `msvcrt!_endthread` at `0x180007d08`

## pseudocode

```c
__int64 __fastcall _FlushThread(char *Parameter)
{
  int v2; // edi
  int v3; // r15d
  DWORD v4; // r14d
  DWORD v5; // eax
  unsigned __int64 v6; // rax
  int pExceptionObject; // [rsp+20h] [rbp-438h] BYREF
  int v9; // [rsp+24h] [rbp-434h] BYREF
  ulong v10; // [rsp+28h] [rbp-430h] BYREF
  unsigned int v11; // [rsp+2Ch] [rbp-42Ch] BYREF
  int v12; // [rsp+30h] [rbp-428h] BYREF
  int v13; // [rsp+34h] [rbp-424h] BYREF

  if ( !Parameter )
  {
    pExceptionObject = -2147418113;
    throw (long *)&pExceptionObject;
  }
  try
  {
    v2 = 0;
    v3 = 1;
    *((_DWORD *)Parameter + 144) = 0;
    if ( !*((_QWORD *)Parameter + 68) )
    {
      v9 = -2147418113;
      throw (long *)&v9;
    }
    while ( 1 )
    {
      if ( !v3 || *((_DWORD *)Parameter + 4) && *((_DWORD *)Parameter + 3) )
        return 0;
      v4 = *((_DWORD *)Parameter + 124);
      *((_DWORD *)Parameter + 162) = 0;
      (**((void (__fastcall ***)(char *))Parameter + 51))(Parameter + 408);
      if ( v2 )
      {
        if ( ++*((_DWORD *)Parameter + 144) <= 0x3E8u )
          goto LABEL_11;
        *((_DWORD *)Parameter + 162) = 1;
        v4 = -1;
      }
      *((_DWORD *)Parameter + 144) = 0;
LABEL_11:
      (*(void (__fastcall **)(char *))(*((_QWORD *)Parameter + 51) + 8LL))(Parameter + 408);
      v5 = WaitForMultipleObjects(4u, (const HANDLE *)Parameter + 64, 0, v4);
      v2 = 0;
      *((_DWORD *)Parameter + 162) = 0;
      if ( *((_DWORD *)Parameter + 145) || v5 == 2 )
      {
        CLogMgr::_Flush((CLogMgr *)Parameter, 0, 0, 1);
        _endthread();
      }
      else if ( *((_DWORD *)Parameter + 97) || v5 == 1 )
      {
        CLogMgr::PeriodicCheckpoint((CLogMgr *)Parameter);
      }
      else if ( *((int *)Parameter + 96) < 3 && v5 )
      {
        if ( v5 == 258 )
        {
          v6 = CLogMgr::Get64BitTickCount();
          if ( *((_DWORD *)Parameter + 97) || v6 >= *((_QWORD *)Parameter + 75) )
          {
            CLogMgr::PeriodicCheckpoint((CLogMgr *)Parameter);
          }
          else if ( *((int *)Parameter + 96) >= 3 || v6 >= *((_QWORD *)Parameter + 76) )
          {
            _InterlockedExchange((volatile __int32 *)Parameter + 96, 0);
            CLogMgr::_Flush((CLogMgr *)Parameter, 0, 0, 0);
          }
          v2 = 1;
        }
        else if ( v5 != 3 )
        {
          v3 = 0;
        }
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)Parameter + 96, 0);
        CLogMgr::_Flush((CLogMgr *)Parameter, 0, 0, 0);
        CLogMgr::Get64BitTickCount();
      }
    }
  }
  catch ( long v11 )
  {
    v12 = 0;
    memset_0(&v13, 0, 0x3FCu);
    TracedStringCchPrintfW(
      (unsigned __int16 *)&v12,
      0x200u,
      L"The FlushThread hit the exception (%d). The process will be terminated",
      v11);
    DtcInternalErrorW((const unsigned __int16 *)&v12);
  }
  catch ( ulong v10 )
  {
    TracedStringCchPrintfW(
      (unsigned __int16 *)&v12,
      0x200u,
      L"The FlushThread hit the exception (%d). The process will be terminated",
      v10);
    DtcInternalErrorW((const unsigned __int16 *)&v12);
  }
  v2 = 0;
}

```

## disassembly

```asm
0x180007b40  mov     [rsp+arg_8], rbx
0x180007b45  mov     [rsp+arg_10], rsi
0x180007b4a  push    rdi
0x180007b4b  push    r14
0x180007b4d  push    r15
0x180007b4f  sub     rsp, 440h
0x180007b56  mov     rax, cs:__security_cookie
0x180007b5d  xor     rax, rsp
0x180007b60  mov     [rsp+458h+var_28], rax
0x180007b68  mov     rbx, rcx
0x180007b6b  test    rcx, rcx
0x180007b6e  jz      loc_180007D3E
0x180007b74  xor     edi, edi
0x180007b76  lea     r15d, [rdi+1]
0x180007b7a  mov     [rcx+240h], edi
0x180007b80  cmp     [rcx+220h], rdi
0x180007b87  jz      loc_180007D58
0x180007b8d  test    r15d, r15d
0x180007b90  jz      loc_180007D13
0x180007b96  cmp     dword ptr [rbx+10h], 0
0x180007b9a  jz      short loc_180007BA6
0x180007b9c  cmp     dword ptr [rbx+0Ch], 0
0x180007ba0  jnz     loc_180007D13
0x180007ba6  mov     r14d, [rbx+1F0h]
0x180007bad  mov     dword ptr [rbx+288h], 0
0x180007bb7  lea     rsi, [rbx+198h]
0x180007bbe  mov     rax, [rsi]
0x180007bc1  mov     rcx, rsi
0x180007bc4  mov     rax, [rax]
0x180007bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcc  test    edi, edi
0x180007bce  jz      short loc_180007BF0
0x180007bd0  inc     dword ptr [rbx+240h]
0x180007bd6  cmp     dword ptr [rbx+240h], 3E8h
0x180007be0  jbe     short loc_180007BFA
0x180007be2  mov     dword ptr [rbx+288h], 1
0x180007bec  or      r14d, 0FFFFFFFFh
0x180007bf0  mov     dword ptr [rbx+240h], 0
0x180007bfa  mov     rax, [rsi]
0x180007bfd  mov     rcx, rsi
0x180007c00  mov     rax, [rax+8]
0x180007c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c09  nop
0x180007c0a  lea     rdx, [rbx+200h]; lpHandles
0x180007c11  mov     r9d, r14d; dwMilliseconds
0x180007c14  xor     r8d, r8d; bWaitAll
0x180007c17  lea     ecx, [r8+4]; nCount
0x180007c1b  call    cs:__imp_WaitForMultipleObjects
0x180007c21  xor     edi, edi
0x180007c23  mov     [rbx+288h], edi
0x180007c29  cmp     [rbx+244h], edi
0x180007c2f  jnz     loc_180007CF5
0x180007c35  cmp     eax, 2
0x180007c38  jz      loc_180007CF5
0x180007c3e  cmp     [rbx+184h], edi
0x180007c44  jnz     loc_180007CEB
0x180007c4a  cmp     eax, 1
0x180007c4d  jz      loc_180007CEB
0x180007c53  cmp     dword ptr [rbx+180h], 3
0x180007c5a  jge     short loc_180007CCC
0x180007c5c  test    eax, eax
0x180007c5e  jz      short loc_180007CCC
0x180007c60  cmp     eax, 102h
0x180007c65  jnz     short loc_180007CBB
0x180007c67  call    ?Get64BitTickCount@CLogMgr@@SA_KXZ; CLogMgr::Get64BitTickCount(void)
0x180007c6c  cmp     [rbx+184h], edi
0x180007c72  jnz     short loc_180007CA9
0x180007c74  cmp     rax, [rbx+258h]
0x180007c7b  jnb     short loc_180007CA9
0x180007c7d  cmp     dword ptr [rbx+180h], 3
0x180007c84  jge     short loc_180007C8F
0x180007c86  cmp     rax, [rbx+260h]
0x180007c8d  jb      short loc_180007CB1
0x180007c8f  xor     eax, eax
0x180007c91  xchg    eax, [rbx+180h]
0x180007c97  xor     r9d, r9d; int
0x180007c9a  xor     r8d, r8d; unsigned int
0x180007c9d  xor     edx, edx; unsigned int
0x180007c9f  mov     rcx, rbx; this
0x180007ca2  call    ?_Flush@CLogMgr@@QEAAXKKH@Z; CLogMgr::_Flush(ulong,ulong,int)
0x180007ca7  jmp     short loc_180007CB1
0x180007ca9  mov     rcx, rbx; this
0x180007cac  call    ?PeriodicCheckpoint@CLogMgr@@QEAAXXZ; CLogMgr::PeriodicCheckpoint(void)
0x180007cb1  mov     edi, 1
0x180007cb6  jmp     loc_180007B8D
0x180007cbb  cmp     eax, 3
0x180007cbe  jz      loc_180007B8D
0x180007cc4  xor     r15d, r15d
0x180007cc7  jmp     loc_180007B8D
0x180007ccc  xor     eax, eax
0x180007cce  xchg    eax, [rbx+180h]
0x180007cd4  xor     r9d, r9d; int
0x180007cd7  xor     r8d, r8d; unsigned int
0x180007cda  xor     edx, edx; unsigned int
0x180007cdc  mov     rcx, rbx; this
0x180007cdf  call    ?_Flush@CLogMgr@@QEAAXKKH@Z; CLogMgr::_Flush(ulong,ulong,int)
0x180007ce4  call    ?Get64BitTickCount@CLogMgr@@SA_KXZ; CLogMgr::Get64BitTickCount(void)
0x180007ce9  jmp     short loc_180007D0E
0x180007ceb  mov     rcx, rbx; this
0x180007cee  call    ?PeriodicCheckpoint@CLogMgr@@QEAAXXZ; CLogMgr::PeriodicCheckpoint(void)
0x180007cf3  jmp     short loc_180007D0E
0x180007cf5  mov     r9d, 1; int
0x180007cfb  xor     r8d, r8d; unsigned int
0x180007cfe  xor     edx, edx; unsigned int
0x180007d00  mov     rcx, rbx; this
0x180007d03  call    ?_Flush@CLogMgr@@QEAAXKKH@Z; CLogMgr::_Flush(ulong,ulong,int)
0x180007d08  call    cs:__imp__endthread
0x180007d0e  jmp     loc_180007B8D
0x180007d13  xor     eax, eax
0x180007d15  mov     rcx, [rsp+458h+var_28]
0x180007d1d  xor     rcx, rsp; StackCookie
0x180007d20  call    __security_check_cookie
0x180007d25  lea     r11, [rsp+458h+var_18]
0x180007d2d  mov     rbx, [r11+28h]
0x180007d31  mov     rsi, [r11+30h]
0x180007d35  mov     rsp, r11
0x180007d38  pop     r15
0x180007d3a  pop     r14
0x180007d3c  pop     rdi
0x180007d3d  retn
0x180007d3e  mov     [rsp+458h+pExceptionObject], 8000FFFFh
0x180007d46  lea     rdx, _TI1J; pThrowInfo
0x180007d4d  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x180007d52  call    _CxxThrowException_0
0x180007d58  mov     [rsp+458h+var_434], 8000FFFFh
0x180007d60  lea     rdx, _TI1J; pThrowInfo
0x180007d67  lea     rcx, [rsp+458h+var_434]; pExceptionObject
0x180007d6c  call    _CxxThrowException_0
```
