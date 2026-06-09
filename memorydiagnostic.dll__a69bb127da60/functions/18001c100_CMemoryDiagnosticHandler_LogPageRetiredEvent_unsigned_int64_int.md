# CMemoryDiagnosticHandler::LogPageRetiredEvent(unsigned __int64,int)

- ea: `0x18001c100`
- end: `0x18001c308`
- name: `?LogPageRetiredEvent@CMemoryDiagnosticHandler@@AEAAJ_KH@Z`
- size: `520`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c310`

## callees

- `0x180002e50`
- `0x18001c100`
- `0x18001e21c`
- `0x18001e24c`
- `0x18001e454`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18001c186`
- `KERNEL32!GetSystemInfo` at `0x18001c186`
- `ADVAPI32!EventUnregister` at `0x18001c2c0`
- `ADVAPI32!EventUnregister` at `0x18001c2c0`
- `ADVAPI32!EventRegister` at `0x18001c1e0`
- `ADVAPI32!EventRegister` at `0x18001c1e0`
- `ADVAPI32!EventWrite` at `0x18001c24c`
- `ADVAPI32!EventWrite` at `0x18001c24c`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::LogPageRetiredEvent(
        CMemoryDiagnosticHandler *this,
        unsigned __int64 a2,
        int a3)
{
  const EVENT_DESCRIPTOR *v4; // rdi
  __int64 v5; // r8
  signed int v6; // eax
  unsigned int v7; // ebx
  CMemoryDiagnosticHandler *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  ULONGLONG RegHandle; // [rsp+38h] [rbp-21h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp+17h] BYREF

  UserData.Ptr = 0;
  *(_QWORD *)&UserData.Size = 0;
  RegHandle = 0;
  v12 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( a3 )
  {
    v4 = &MEMORY_DIAGNOSTIC_LIMIT_EVENT;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43);
    }
  }
  else
  {
    v4 = (const EVENT_DESCRIPTOR *)MEMORY_DIAGNOSTIC_RETIRE_EVENT;
  }
  GetSystemInfo(&SystemInfo);
  v12 = 0;
  if ( is_mul_ok(a2, SystemInfo.dwPageSize) )
  {
    v12 = a2 * SystemInfo.dwPageSize;
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
LABEL_16:
        WPP_SF_(*((_QWORD *)v8 + 2), v9);
LABEL_17:
        v8 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      UserData.Ptr = (ULONGLONG)&v12;
      *(_QWORD *)&UserData.Size = 8;
      v10 = EventWrite(RegHandle, v4, 1u, &UserData);
      v7 = 0;
      if ( !v10 )
        goto LABEL_17;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      else
        v7 = v10;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 47;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v12 = -1;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
      v8 = WPP_GLOBAL_Control;
    }
    v7 = -2147024362;
  }
  if ( RegHandle )
  {
    EventUnregister(RegHandle);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v7 & 0x80000000) != 0 && v8 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v8 + 2), 10, v5, v7);
  return v7;
}

```

## disassembly

```asm
0x18001c100  push    rbp
0x18001c102  push    rbx
0x18001c103  push    rdi
0x18001c104  push    r14
0x18001c106  lea     rbp, [rsp-3Fh]
0x18001c10b  sub     rsp, 98h
0x18001c112  mov     rax, cs:__security_cookie
0x18001c119  xor     rax, rsp
0x18001c11c  mov     [rbp+57h+var_30], rax
0x18001c120  xor     eax, eax
0x18001c122  mov     [rbp+57h+UserData.Ptr], 0
0x18001c12a  mov     qword ptr [rbp+57h+UserData.Size], rax
0x18001c12e  xorps   xmm0, xmm0
0x18001c131  mov     [rbp+57h+RegHandle], rax
0x18001c135  mov     rbx, rdx
0x18001c138  mov     [rbp+57h+var_80], rax
0x18001c13c  lea     r14, WPP_GLOBAL_Control
0x18001c143  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18001c147  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18001c14b  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x18001c14f  test    r8d, r8d
0x18001c152  jz      short loc_18001C17B
0x18001c154  lea     rdi, MEMORY_DIAGNOSTIC_LIMIT_EVENT
0x18001c15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c162  cmp     rcx, r14
0x18001c165  jz      short loc_18001C182
0x18001c167  test    byte ptr [rcx+1Ch], 4
0x18001c16b  jz      short loc_18001C182
0x18001c16d  mov     rcx, [rcx+10h]
0x18001c171  lea     edx, [rax+2Bh]
0x18001c174  call    WPP_SF_
0x18001c179  jmp     short loc_18001C182
0x18001c17b  lea     rdi, MEMORY_DIAGNOSTIC_RETIRE_EVENT
0x18001c182  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18001c186  call    cs:__imp_GetSystemInfo
0x18001c18c  mov     r9d, [rbp+57h+SystemInfo.dwPageSize]
0x18001c190  mov     eax, r9d
0x18001c193  mov     [rbp+57h+var_80], 0
0x18001c19b  mul     rbx
0x18001c19e  test    rdx, rdx
0x18001c1a1  jnz     loc_18001C280
0x18001c1a7  mov     [rbp+57h+var_80], rax
0x18001c1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1b2  cmp     rcx, r14
0x18001c1b5  jz      short loc_18001C1D0
0x18001c1b7  test    byte ptr [rcx+1Ch], 4
0x18001c1bb  jz      short loc_18001C1D0
0x18001c1bd  mov     rcx, [rcx+10h]
0x18001c1c1  mov     [rsp+0B0h+var_88], rax
0x18001c1c6  mov     [rsp+0B0h+var_90], rbx
0x18001c1cb  call    WPP_SF_dII
0x18001c1d0  lea     r9, [rbp+57h+RegHandle]; RegHandle
0x18001c1d4  xor     r8d, r8d; CallbackContext
0x18001c1d7  xor     edx, edx; EnableCallback
0x18001c1d9  lea     rcx, MEMORY_DIAGNOSTIC; ProviderId
0x18001c1e0  call    cs:__imp_EventRegister
0x18001c1e6  mov     ebx, eax
0x18001c1e8  test    eax, eax
0x18001c1ea  jz      short loc_18001C22B
0x18001c1ec  jle     short loc_18001C1F7
0x18001c1ee  movzx   ebx, ax
0x18001c1f1  or      ebx, 80070000h
0x18001c1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1fe  cmp     rcx, r14
0x18001c201  jz      loc_18001C2B4
0x18001c207  test    byte ptr [rcx+1Ch], 1
0x18001c20b  jz      loc_18001C2B4
0x18001c211  mov     edx, 2Eh ; '.'
0x18001c216  mov     rcx, [rcx+10h]
0x18001c21a  call    WPP_SF_
0x18001c21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c226  jmp     loc_18001C2B4
0x18001c22b  mov     rcx, [rbp+57h+RegHandle]; RegHandle
0x18001c22f  lea     rax, [rbp+57h+var_80]
0x18001c233  lea     r9, [rbp+57h+UserData]; UserData
0x18001c237  mov     [rbp+57h+UserData.Ptr], rax
0x18001c23b  mov     r8d, 1; UserDataCount
0x18001c241  mov     qword ptr [rbp+57h+UserData.Size], 8
0x18001c249  mov     rdx, rdi; EventDescriptor
0x18001c24c  call    cs:__imp_EventWrite
0x18001c252  xor     ebx, ebx
0x18001c254  test    eax, eax
0x18001c256  jz      short loc_18001C21F
0x18001c258  jg      short loc_18001C25E
0x18001c25a  mov     ebx, eax
0x18001c25c  jmp     short loc_18001C267
0x18001c25e  movzx   ebx, ax
0x18001c261  or      ebx, 80070000h
0x18001c267  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c26e  cmp     rcx, r14
0x18001c271  jz      short loc_18001C2B4
0x18001c273  test    byte ptr [rcx+1Ch], 1
0x18001c277  jz      short loc_18001C2B4
0x18001c279  mov     edx, 2Fh ; '/'
0x18001c27e  jmp     short loc_18001C216
0x18001c280  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x18001c288  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c28f  cmp     rcx, r14
0x18001c292  jz      short loc_18001C2AF
0x18001c294  test    byte ptr [rcx+1Ch], 1
0x18001c298  jz      short loc_18001C2AF
0x18001c29a  mov     rcx, [rcx+10h]
0x18001c29e  mov     edx, 2Ch ; ','
0x18001c2a3  call    WPP_SF_
0x18001c2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2af  mov     ebx, 80070216h
0x18001c2b4  mov     rax, [rbp+57h+RegHandle]
0x18001c2b8  test    rax, rax
0x18001c2bb  jz      short loc_18001C2CD
0x18001c2bd  mov     rcx, rax; RegHandle
0x18001c2c0  call    cs:__imp_EventUnregister
0x18001c2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2cd  test    ebx, ebx
0x18001c2cf  jns     short loc_18001C2ED
0x18001c2d1  cmp     rcx, r14
0x18001c2d4  jz      short loc_18001C2ED
0x18001c2d6  test    byte ptr [rcx+1Ch], 1
0x18001c2da  jz      short loc_18001C2ED
0x18001c2dc  mov     rcx, [rcx+10h]
0x18001c2e0  mov     edx, 0Ah
0x18001c2e5  mov     r9d, ebx
0x18001c2e8  call    WPP_SF_d
0x18001c2ed  mov     eax, ebx
0x18001c2ef  mov     rcx, [rbp+57h+var_30]
0x18001c2f3  xor     rcx, rsp; StackCookie
0x18001c2f6  call    __security_check_cookie
0x18001c2fb  add     rsp, 98h
0x18001c302  pop     r14
0x18001c304  pop     rdi
0x18001c305  pop     rbx
0x18001c306  pop     rbp
0x18001c307  retn
```
