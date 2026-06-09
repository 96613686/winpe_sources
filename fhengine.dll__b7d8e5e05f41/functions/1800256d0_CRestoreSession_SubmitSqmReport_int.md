# CRestoreSession::SubmitSqmReport(int)

- ea: `0x1800256d0`
- end: `0x180025a2b`
- name: `?SubmitSqmReport@CRestoreSession@@UEAAJH@Z`
- size: `859`
- prototype: `__int64 __fastcall(CRestoreSession *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007818`
- `0x1800256d0`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002585c`
- `KERNEL32!GetLastError` at `0x18002585c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002576f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002576f`
- `ntdll!WinSqmSetString` at `0x18002598d`
- `ntdll!WinSqmSetString` at `0x1800259c9`
- `ntdll!WinSqmSetString` at `0x1800259f4`
- `ntdll!WinSqmSetString` at `0x18002598d`
- `ntdll!WinSqmSetString` at `0x1800259c9`
- `ntdll!WinSqmSetString` at `0x1800259f4`
- `ntdll!WinSqmSetDWORD64` at `0x1800258e8`
- `ntdll!WinSqmSetDWORD64` at `0x180025951`
- `ntdll!WinSqmSetDWORD64` at `0x180025978`
- `ntdll!WinSqmSetDWORD64` at `0x1800259b4`
- `ntdll!WinSqmSetDWORD64` at `0x1800259df`
- `ntdll!WinSqmSetDWORD64` at `0x1800258e8`
- `ntdll!WinSqmSetDWORD64` at `0x180025951`
- `ntdll!WinSqmSetDWORD64` at `0x180025978`
- `ntdll!WinSqmSetDWORD64` at `0x1800259b4`
- `ntdll!WinSqmSetDWORD64` at `0x1800259df`
- `ntdll!WinSqmStartSession` at `0x18002584d`
- `ntdll!WinSqmStartSession` at `0x18002584d`
- `ntdll!WinSqmSetDWORD` at `0x1800258ab`
- `ntdll!WinSqmSetDWORD` at `0x1800258bc`
- `ntdll!WinSqmSetDWORD` at `0x1800258fd`
- `ntdll!WinSqmSetDWORD` at `0x180025912`
- `ntdll!WinSqmSetDWORD` at `0x180025927`
- `ntdll!WinSqmSetDWORD` at `0x18002593c`
- `ntdll!WinSqmSetDWORD` at `0x1800258ab`
- `ntdll!WinSqmSetDWORD` at `0x1800258bc`
- `ntdll!WinSqmSetDWORD` at `0x1800258fd`
- `ntdll!WinSqmSetDWORD` at `0x180025912`
- `ntdll!WinSqmSetDWORD` at `0x180025927`
- `ntdll!WinSqmSetDWORD` at `0x18002593c`
- `ntdll!WinSqmIsOptedIn` at `0x180025714`
- `ntdll!WinSqmIsOptedIn` at `0x180025714`
- `ntdll!WinSqmEndSession` at `0x1800259fd`
- `ntdll!WinSqmEndSession` at `0x1800259fd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800257f6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800257f6`

## pseudocode

```c
__int64 __fastcall CRestoreSession::SubmitSqmReport(CRestoreSession *this, int a2)
{
  unsigned int v5; // r15d
  __int64 v6; // rax
  signed __int64 v7; // r14
  int v8; // edx
  __int64 v9; // rbp
  __int64 v10; // rcx
  unsigned int v11; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 started; // rax
  __int64 v15; // rsi
  signed int LastError; // eax
  __int64 v17; // r8
  __int64 v18; // r8
  int v19; // [rsp+20h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-50h] BYREF
  __int64 v21; // [rsp+30h] [rbp-48h]
  GUID pguid; // [rsp+38h] [rbp-40h] BYREF

  v19 = 0;
  SystemTimeAsFileTime = 0;
  pguid = 0;
  if ( !(unsigned int)WinSqmIsOptedIn() )
    return 1;
  v5 = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 8) + 80LL))(*((_QWORD *)this + 8), &v19) >= 0 )
  {
    if ( v19 )
    {
      if ( v19 == 1 )
      {
        v5 = 4;
      }
      else if ( v19 == 2 )
      {
        v5 = 3;
      }
    }
    else
    {
      v5 = 1;
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = *((_QWORD *)this + 22);
  if ( v6 )
    v7 = SystemTimeAsFileTime.dwLowDateTime + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32) - v6;
  else
    v7 = 0;
  v8 = *((_DWORD *)this + 85);
  if ( v8 != -1 || (v9 = 0, *((_DWORD *)this + 84) != -1) )
  {
    LODWORD(v21) = *((_DWORD *)this + 84);
    HIDWORD(v21) = v8;
    v10 = *(_QWORD *)&SystemTimeAsFileTime - v21;
    if ( *(_QWORD *)&SystemTimeAsFileTime - v21 <= 0 )
      v10 = 0;
    v9 = v10 / 10000000;
  }
  v11 = CoCreateGuid(&pguid);
  if ( (v11 & 0x80000000) != 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v11;
    v13 = 13;
    goto LABEL_22;
  }
  started = WinSqmStartSession(&pguid, 101457928, 0);
  v15 = started;
  if ( started != -1 )
  {
    WinSqmSetDWORD(started, 7601, 2 - (unsigned int)(a2 != 0));
    WinSqmSetDWORD(v15, 7603, v5);
    WinSqmSetDWORD64(v15, 7604, v7 / 10000000 + v7);
    WinSqmSetDWORD(v15, 7606, (unsigned int)(*((_DWORD *)this + 27) + 1));
    WinSqmSetDWORD(v15, 7607, *((unsigned int *)this + 98));
    WinSqmSetDWORD(v15, 7608, *((unsigned int *)this + 92));
    WinSqmSetDWORD(v15, 7609, *((unsigned int *)this + 93));
    WinSqmSetDWORD64(v15, 7610, *((_QWORD *)this + 47));
    v17 = *((_QWORD *)this + 39);
    if ( v17 || *(_DWORD *)(*((_QWORD *)this + 43) - 16LL) )
    {
      WinSqmSetDWORD64(v15, 7612, v17);
      WinSqmSetString(v15, 7613, *((_QWORD *)this + 43));
    }
    v18 = *((_QWORD *)this + 40);
    if ( v18 || *(_DWORD *)(*((_QWORD *)this + 44) - 16LL) )
    {
      WinSqmSetDWORD64(v15, 7614, v18);
      WinSqmSetString(v15, 7615, *((_QWORD *)this + 44));
    }
    if ( v9 > 0 )
    {
      WinSqmSetDWORD64(v15, 10769, v9);
      WinSqmSetString(v15, 10770, *((_QWORD *)this + 45));
    }
    WinSqmEndSession(v15);
    return v11;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 14;
LABEL_22:
    WPP_SF_d(v12[2], v13, WPP_99859d014f2c3b7a1651f9c2c88a152b_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1800256d0  mov     [rsp+arg_8], rbx
0x1800256d5  mov     [rsp+arg_10], rbp
0x1800256da  push    rsi
0x1800256db  push    rdi
0x1800256dc  push    r12
0x1800256de  push    r14
0x1800256e0  push    r15
0x1800256e2  sub     rsp, 50h
0x1800256e6  mov     rax, cs:__security_cookie
0x1800256ed  xor     rax, rsp
0x1800256f0  mov     [rsp+78h+var_30], rax
0x1800256f5  mov     r12d, edx
0x1800256f8  mov     rbx, rcx
0x1800256fb  mov     [rsp+78h+var_58], 0
0x180025703  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002570c  xorps   xmm0, xmm0
0x18002570f  movups  xmmword ptr [rsp+78h+pguid.Data1], xmm0
0x180025714  call    cs:__imp_WinSqmIsOptedIn
0x18002571a  test    eax, eax
0x18002571c  jnz     short loc_180025728
0x18002571e  mov     eax, 1
0x180025723  jmp     loc_180025A05
0x180025728  mov     rcx, [rbx+40h]
0x18002572c  mov     rax, [rcx]
0x18002572f  lea     rdx, [rsp+78h+var_58]
0x180025734  mov     rax, [rax+50h]
0x180025738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002573d  xor     r15d, r15d
0x180025740  test    eax, eax
0x180025742  js      short loc_18002576A
0x180025744  mov     ecx, [rsp+78h+var_58]
0x180025748  test    ecx, ecx
0x18002574a  jz      short loc_180025764
0x18002574c  sub     ecx, 1
0x18002574f  jz      short loc_18002575C
0x180025751  cmp     ecx, 1
0x180025754  jnz     short loc_18002576A
0x180025756  lea     r15d, [rcx+2]
0x18002575a  jmp     short loc_18002576A
0x18002575c  mov     r15d, 4
0x180025762  jmp     short loc_18002576A
0x180025764  mov     r15d, 1
0x18002576a  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002576f  call    cs:__imp_GetSystemTimeAsFileTime
0x180025775  mov     rax, [rbx+0B0h]
0x18002577c  mov     rcx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180025781  test    rax, rax
0x180025784  jz      short loc_180025799
0x180025786  mov     r14d, [rsp+78h+SystemTimeAsFileTime.dwHighDateTime]
0x18002578b  shl     r14, 20h
0x18002578f  sub     r14, rax
0x180025792  mov     eax, ecx
0x180025794  add     r14, rax
0x180025797  jmp     short loc_18002579C
0x180025799  xor     r14d, r14d
0x18002579c  mov     edx, [rbx+154h]
0x1800257a2  mov     r8, 0D6BF94D5E57A42BDh
0x1800257ac  or      eax, 0FFFFFFFFh
0x1800257af  cmp     edx, eax
0x1800257b1  jnz     short loc_1800257BD
0x1800257b3  xor     ebp, ebp
0x1800257b5  cmp     [rbx+150h], eax
0x1800257bb  jz      short loc_1800257F1
0x1800257bd  mov     eax, [rbx+150h]
0x1800257c3  mov     dword ptr [rsp+78h+var_48], eax
0x1800257c7  mov     dword ptr [rsp+78h+var_48+4], edx
0x1800257cb  sub     rcx, [rsp+78h+var_48]
0x1800257d0  xor     eax, eax
0x1800257d2  test    rcx, rcx
0x1800257d5  cmovle  rcx, rax
0x1800257d9  mov     rax, r8
0x1800257dc  imul    rcx
0x1800257df  lea     rbp, [rcx+rdx]
0x1800257e3  sar     rbp, 17h
0x1800257e7  mov     rax, rbp
0x1800257ea  shr     rax, 3Fh
0x1800257ee  add     rbp, rax
0x1800257f1  lea     rcx, [rsp+78h+pguid]; pguid
0x1800257f6  call    cs:__imp_CoCreateGuid
0x1800257fc  mov     edi, eax
0x1800257fe  test    eax, eax
0x180025800  jns     short loc_180025840
0x180025802  lea     rax, WPP_GLOBAL_Control
0x180025809  mov     rcx, cs:WPP_GLOBAL_Control
0x180025810  cmp     rcx, rax
0x180025813  jz      loc_180025A03
0x180025819  test    byte ptr [rcx+1Ch], 1
0x18002581d  jz      loc_180025A03
0x180025823  mov     edx, 0Dh
0x180025828  mov     r9d, edi
0x18002582b  lea     r8, WPP_99859d014f2c3b7a1651f9c2c88a152b_Traceguids
0x180025832  mov     rcx, [rcx+10h]
0x180025836  call    WPP_SF_d
0x18002583b  jmp     loc_180025A03
0x180025840  xor     r8d, r8d
0x180025843  mov     edx, 60C2008h
0x180025848  lea     rcx, [rsp+78h+pguid]
0x18002584d  call    cs:__imp_WinSqmStartSession
0x180025853  mov     rsi, rax
0x180025856  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002585a  jnz     short loc_180025899
0x18002585c  call    cs:__imp_GetLastError
0x180025862  mov     edi, eax
0x180025864  test    eax, eax
0x180025866  jle     short loc_180025871
0x180025868  movzx   edi, ax
0x18002586b  or      edi, 80070000h
0x180025871  lea     rax, WPP_GLOBAL_Control
0x180025878  mov     rcx, cs:WPP_GLOBAL_Control
0x18002587f  cmp     rcx, rax
0x180025882  jz      loc_180025A03
0x180025888  test    byte ptr [rcx+1Ch], 1
0x18002588c  jz      loc_180025A03
0x180025892  mov     edx, 0Eh
0x180025897  jmp     short loc_180025828
0x180025899  neg     r12d
0x18002589c  sbb     r8d, r8d
0x18002589f  add     r8d, 2
0x1800258a3  mov     edx, 1DB1h
0x1800258a8  mov     rcx, rsi
0x1800258ab  call    cs:__imp_WinSqmSetDWORD
0x1800258b1  mov     r8d, r15d
0x1800258b4  mov     edx, 1DB3h
0x1800258b9  mov     rcx, rsi
0x1800258bc  call    cs:__imp_WinSqmSetDWORD
0x1800258c2  mov     rax, 0D6BF94D5E57A42BDh
0x1800258cc  imul    r14
0x1800258cf  add     rdx, r14
0x1800258d2  sar     rdx, 17h
0x1800258d6  mov     r8, rdx
0x1800258d9  shr     r8, 3Fh
0x1800258dd  add     r8, rdx
0x1800258e0  mov     edx, 1DB4h
0x1800258e5  mov     rcx, rsi
0x1800258e8  call    cs:__imp_WinSqmSetDWORD64
0x1800258ee  mov     r8d, [rbx+6Ch]
0x1800258f2  inc     r8d
0x1800258f5  mov     edx, 1DB6h
0x1800258fa  mov     rcx, rsi
0x1800258fd  call    cs:__imp_WinSqmSetDWORD
0x180025903  mov     r8d, [rbx+188h]
0x18002590a  mov     edx, 1DB7h
0x18002590f  mov     rcx, rsi
0x180025912  call    cs:__imp_WinSqmSetDWORD
0x180025918  mov     r8d, [rbx+170h]
0x18002591f  mov     edx, 1DB8h
0x180025924  mov     rcx, rsi
0x180025927  call    cs:__imp_WinSqmSetDWORD
0x18002592d  mov     r8d, [rbx+174h]
0x180025934  mov     edx, 1DB9h
0x180025939  mov     rcx, rsi
0x18002593c  call    cs:__imp_WinSqmSetDWORD
0x180025942  mov     r8, [rbx+178h]
0x180025949  mov     edx, 1DBAh
0x18002594e  mov     rcx, rsi
0x180025951  call    cs:__imp_WinSqmSetDWORD64
0x180025957  mov     r8, [rbx+138h]
0x18002595e  test    r8, r8
0x180025961  jnz     short loc_180025970
0x180025963  mov     rax, [rbx+158h]
0x18002596a  cmp     [rax-10h], r8d
0x18002596e  jz      short loc_180025993
0x180025970  mov     edx, 1DBCh
0x180025975  mov     rcx, rsi
0x180025978  call    cs:__imp_WinSqmSetDWORD64
0x18002597e  mov     r8, [rbx+158h]
0x180025985  mov     edx, 1DBDh
0x18002598a  mov     rcx, rsi
0x18002598d  call    cs:__imp_WinSqmSetString
0x180025993  mov     r8, [rbx+140h]
0x18002599a  test    r8, r8
0x18002599d  jnz     short loc_1800259AC
0x18002599f  mov     rax, [rbx+160h]
0x1800259a6  cmp     [rax-10h], r8d
0x1800259aa  jz      short loc_1800259CF
0x1800259ac  mov     edx, 1DBEh
0x1800259b1  mov     rcx, rsi
0x1800259b4  call    cs:__imp_WinSqmSetDWORD64
0x1800259ba  mov     r8, [rbx+160h]
0x1800259c1  mov     edx, 1DBFh
0x1800259c6  mov     rcx, rsi
0x1800259c9  call    cs:__imp_WinSqmSetString
0x1800259cf  test    rbp, rbp
0x1800259d2  jle     short loc_1800259FA
0x1800259d4  mov     r8, rbp
0x1800259d7  mov     edx, 2A11h
0x1800259dc  mov     rcx, rsi
0x1800259df  call    cs:__imp_WinSqmSetDWORD64
0x1800259e5  mov     r8, [rbx+168h]
0x1800259ec  mov     edx, 2A12h
0x1800259f1  mov     rcx, rsi
0x1800259f4  call    cs:__imp_WinSqmSetString
0x1800259fa  mov     rcx, rsi
0x1800259fd  call    cs:__imp_WinSqmEndSession
0x180025a03  mov     eax, edi
0x180025a05  mov     rcx, [rsp+78h+var_30]
0x180025a0a  xor     rcx, rsp; StackCookie
0x180025a0d  call    __security_check_cookie
0x180025a12  lea     r11, [rsp+78h+var_28]
0x180025a17  mov     rbx, [r11+38h]
0x180025a1b  mov     rbp, [r11+40h]
0x180025a1f  mov     rsp, r11
0x180025a22  pop     r15
0x180025a24  pop     r14
0x180025a26  pop     r12
0x180025a28  pop     rdi
0x180025a29  pop     rsi
0x180025a2a  retn
```
