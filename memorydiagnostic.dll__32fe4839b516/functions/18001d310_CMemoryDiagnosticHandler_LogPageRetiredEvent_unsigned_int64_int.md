# CMemoryDiagnosticHandler::LogPageRetiredEvent(unsigned __int64,int)

- ea: `0x18001d310`
- end: `0x18001d527`
- name: `?LogPageRetiredEvent@CMemoryDiagnosticHandler@@AEAAJ_KH@Z`
- size: `535`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001d530`

## callees

- `0x1800026b0`
- `0x18001d310`
- `0x18001f560`
- `0x18001f594`
- `0x18001f7b4`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18001d396`
- `KERNEL32!GetSystemInfo` at `0x18001d396`
- `ADVAPI32!EventUnregister` at `0x18001d4cc`
- `ADVAPI32!EventUnregister` at `0x18001d4cc`
- `ADVAPI32!EventRegister` at `0x18001d3f3`
- `ADVAPI32!EventRegister` at `0x18001d3f3`
- `ADVAPI32!EventWrite` at `0x18001d455`
- `ADVAPI32!EventWrite` at `0x18001d455`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::LogPageRetiredEvent(
        CMemoryDiagnosticHandler *this,
        unsigned __int64 a2,
        int a3)
{
  const EVENT_DESCRIPTOR *v3; // rdi
  __int64 v5; // r8
  signed int v6; // eax
  unsigned int v7; // ebx
  CMemoryDiagnosticHandler *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  ULONGLONG RegHandle; // [rsp+38h] [rbp-9h] BYREF
  __int64 v13; // [rsp+40h] [rbp-1h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp+37h] BYREF

  UserData.Ptr = 0;
  v3 = &MEMORY_DIAGNOSTIC_RETIRE_EVENT;
  RegHandle = 0;
  *(_QWORD *)&UserData.Size = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( a3 )
  {
    v3 = (const EVENT_DESCRIPTOR *)&MEMORY_DIAGNOSTIC_LIMIT_EVENT;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43);
    }
  }
  GetSystemInfo(&SystemInfo);
  v13 = 0;
  if ( is_mul_ok(a2, SystemInfo.dwPageSize) )
  {
    v13 = a2 * SystemInfo.dwPageSize;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dII(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    v6 = EventRegister(&MEMORY_DIAGNOSTIC, 0, 0, &RegHandle);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 46;
LABEL_25:
        WPP_SF_(*((_QWORD *)v8 + 2), v9);
        goto LABEL_26;
      }
    }
    else
    {
      UserData.Reserved = 0;
      UserData.Ptr = (ULONGLONG)&v13;
      UserData.Size = 8;
      v10 = EventWrite(RegHandle, v3, 1u, &UserData);
      v7 = 0;
      if ( !v10 )
      {
LABEL_26:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_27;
      }
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      else
        v7 = v10;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 47;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v13 = -1;
    v7 = -2147024362;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 44;
      goto LABEL_25;
    }
  }
LABEL_27:
  if ( RegHandle )
  {
    EventUnregister(RegHandle);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v7 & 0x80000000) != 0 && v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)v8 + 2), 10, v5, v7);
  return v7;
}

```

## disassembly

```asm
0x18001d310  mov     rax, rsp
0x18001d313  mov     [rax+8], rbx
0x18001d317  mov     [rax+18h], rdi
0x18001d31b  mov     [rax+20h], r14
0x18001d31f  push    rbp
0x18001d320  lea     rbp, [rax-5Fh]
0x18001d324  sub     rsp, 90h
0x18001d32b  mov     rax, cs:__security_cookie
0x18001d332  xor     rax, rsp
0x18001d335  mov     [rbp+57h+var_10], rax
0x18001d339  and     [rbp+57h+UserData.Ptr], 0
0x18001d33e  lea     rdi, MEMORY_DIAGNOSTIC_RETIRE_EVENT
0x18001d345  xor     eax, eax
0x18001d347  lea     r14, WPP_GLOBAL_Control
0x18001d34e  and     [rbp+57h+RegHandle], rax
0x18001d352  xorps   xmm0, xmm0
0x18001d355  mov     qword ptr [rbp+57h+UserData.Size], rax
0x18001d359  mov     rbx, rdx
0x18001d35c  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18001d360  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18001d364  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x18001d368  test    r8d, r8d
0x18001d36b  jz      short loc_18001D392
0x18001d36d  lea     rdi, MEMORY_DIAGNOSTIC_LIMIT_EVENT
0x18001d374  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d37b  cmp     rcx, r14
0x18001d37e  jz      short loc_18001D392
0x18001d380  test    byte ptr [rcx+1Ch], 4
0x18001d384  jz      short loc_18001D392
0x18001d386  mov     rcx, [rcx+10h]
0x18001d38a  lea     edx, [rax+2Bh]
0x18001d38d  call    WPP_SF_
0x18001d392  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18001d396  call    cs:__imp_GetSystemInfo
0x18001d39d  nop     dword ptr [rax+rax+00h]
0x18001d3a2  mov     r9d, [rbp+57h+SystemInfo.dwPageSize]
0x18001d3a6  and     [rbp+57h+var_58], 0
0x18001d3ab  mov     eax, r9d
0x18001d3ae  mul     rbx
0x18001d3b1  test    rdx, rdx
0x18001d3b4  jnz     loc_18001D48F
0x18001d3ba  mov     [rbp+57h+var_58], rax
0x18001d3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3c5  cmp     rcx, r14
0x18001d3c8  jz      short loc_18001D3E3
0x18001d3ca  test    byte ptr [rcx+1Ch], 4
0x18001d3ce  jz      short loc_18001D3E3
0x18001d3d0  mov     rcx, [rcx+10h]
0x18001d3d4  mov     [rsp+90h+var_68], rax
0x18001d3d9  mov     [rsp+90h+var_70], rbx
0x18001d3de  call    WPP_SF_dII
0x18001d3e3  lea     r9, [rbp+57h+RegHandle]; RegHandle
0x18001d3e7  xor     r8d, r8d; CallbackContext
0x18001d3ea  xor     edx, edx; EnableCallback
0x18001d3ec  lea     rcx, MEMORY_DIAGNOSTIC; ProviderId
0x18001d3f3  call    cs:__imp_EventRegister
0x18001d3fa  nop     dword ptr [rax+rax+00h]
0x18001d3ff  mov     ebx, eax
0x18001d401  test    eax, eax
0x18001d403  jz      short loc_18001D431
0x18001d405  jle     short loc_18001D410
0x18001d407  movzx   ebx, ax
0x18001d40a  or      ebx, 80070000h
0x18001d410  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d417  cmp     rcx, r14
0x18001d41a  jz      loc_18001D4C0
0x18001d420  test    byte ptr [rcx+1Ch], 1
0x18001d424  jz      loc_18001D4C0
0x18001d42a  mov     edx, 2Eh ; '.'
0x18001d42f  jmp     short loc_18001D4B0
0x18001d431  mov     rcx, [rbp+57h+RegHandle]; RegHandle
0x18001d435  lea     rax, [rbp+57h+var_58]
0x18001d439  and     dword ptr [rbp+57h+UserData.0Ch], 0
0x18001d43d  lea     r9, [rbp+57h+UserData]; UserData
0x18001d441  mov     r8d, 1; UserDataCount
0x18001d447  mov     [rbp+57h+UserData.Ptr], rax
0x18001d44b  mov     rdx, rdi; EventDescriptor
0x18001d44e  mov     [rbp+57h+UserData.Size], 8
0x18001d455  call    cs:__imp_EventWrite
0x18001d45c  nop     dword ptr [rax+rax+00h]
0x18001d461  xor     ebx, ebx
0x18001d463  test    eax, eax
0x18001d465  jz      short loc_18001D4B9
0x18001d467  jg      short loc_18001D46D
0x18001d469  mov     ebx, eax
0x18001d46b  jmp     short loc_18001D476
0x18001d46d  movzx   ebx, ax
0x18001d470  or      ebx, 80070000h
0x18001d476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d47d  cmp     rcx, r14
0x18001d480  jz      short loc_18001D4C0
0x18001d482  test    byte ptr [rcx+1Ch], 1
0x18001d486  jz      short loc_18001D4C0
0x18001d488  mov     edx, 2Fh ; '/'
0x18001d48d  jmp     short loc_18001D4B0
0x18001d48f  or      [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x18001d494  mov     ebx, 80070216h
0x18001d499  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4a0  cmp     rcx, r14
0x18001d4a3  jz      short loc_18001D4C0
0x18001d4a5  test    byte ptr [rcx+1Ch], 1
0x18001d4a9  jz      short loc_18001D4C0
0x18001d4ab  mov     edx, 2Ch ; ','
0x18001d4b0  mov     rcx, [rcx+10h]
0x18001d4b4  call    WPP_SF_
0x18001d4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4c0  mov     rax, [rbp+57h+RegHandle]
0x18001d4c4  test    rax, rax
0x18001d4c7  jz      short loc_18001D4DF
0x18001d4c9  mov     rcx, rax; RegHandle
0x18001d4cc  call    cs:__imp_EventUnregister
0x18001d4d3  nop     dword ptr [rax+rax+00h]
0x18001d4d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4df  test    ebx, ebx
0x18001d4e1  jns     short loc_18001D4FF
0x18001d4e3  cmp     rcx, r14
0x18001d4e6  jz      short loc_18001D4FF
0x18001d4e8  test    byte ptr [rcx+1Ch], 1
0x18001d4ec  jz      short loc_18001D4FF
0x18001d4ee  mov     rcx, [rcx+10h]
0x18001d4f2  mov     edx, 0Ah
0x18001d4f7  mov     r9d, ebx
0x18001d4fa  call    WPP_SF_D
0x18001d4ff  mov     eax, ebx
0x18001d501  mov     rcx, [rbp+57h+var_10]
0x18001d505  xor     rcx, rsp; StackCookie
0x18001d508  call    __security_check_cookie
0x18001d50d  lea     r11, [rsp+90h+var_s0]
0x18001d515  mov     rbx, [r11+10h]
0x18001d519  mov     rdi, [r11+20h]
0x18001d51d  mov     r14, [r11+28h]
0x18001d521  mov     rsp, r11
0x18001d524  pop     rbp
0x18001d525  retn
```
