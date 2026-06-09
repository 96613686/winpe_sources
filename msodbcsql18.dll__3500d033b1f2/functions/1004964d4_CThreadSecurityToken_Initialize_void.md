# CThreadSecurityToken::Initialize(void)

- ea: `0x1004964d4`
- end: `0x1004966c6`
- name: `?Initialize@CThreadSecurityToken@@QEAAJXZ`
- size: `498`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004966d0`
- `0x1004e5b60`

## callees

- `0x1004964d4`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1004965aa`
- `KERNEL32!GetCurrentProcess` at `0x1004965aa`
- `KERNEL32!GetCurrentThread` at `0x1004964dd`
- `KERNEL32!GetCurrentThread` at `0x10049650e`
- `KERNEL32!GetCurrentThread` at `0x1004964dd`
- `KERNEL32!GetCurrentThread` at `0x10049650e`
- `KERNEL32!GetLastError` at `0x100496500`
- `KERNEL32!GetLastError` at `0x100496568`
- `KERNEL32!GetLastError` at `0x1004965c5`
- `KERNEL32!GetLastError` at `0x100496500`
- `KERNEL32!GetLastError` at `0x100496568`
- `KERNEL32!GetLastError` at `0x1004965c5`
- `ADVAPI32!OpenThreadToken` at `0x1004964f2`
- `ADVAPI32!OpenThreadToken` at `0x100496521`
- `ADVAPI32!OpenThreadToken` at `0x1004964f2`
- `ADVAPI32!OpenThreadToken` at `0x100496521`
- `ADVAPI32!OpenProcessToken` at `0x1004965bb`
- `ADVAPI32!OpenProcessToken` at `0x1004965bb`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::Initialize(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v4; // r9
  HANDLE v5; // rax
  wchar_t *v6; // r9
  __int64 v7; // r8
  HANDLE CurrentProcess; // rax
  DWORD v9; // eax
  wchar_t *v10; // r8
  __int64 v11; // rdx

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) )
  {
    if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`66'::_bidPtrSA_030_4595[0] || bidID == -1 )
      return 0;
    v6 = `CThreadSecurityToken::Initialize'::`66'::_bidPtrSA_030_4595[0];
    v7 = 4705280;
    goto LABEL_31;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 5 )
  {
LABEL_9:
    if ( (_DWORD)v4 == 1008 )
    {
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`31'::_bidPtrSA_030_4569[0] )
        bidTraceW(0, 4678656, `CThreadSecurityToken::Initialize'::`31'::_bidPtrSA_030_4569[0], 1008);
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xEu, TokenHandle) )
      {
        if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`48'::_bidPtrSA_030_4583[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
            bidID,
            0,
            4692992,
            `CThreadSecurityToken::Initialize'::`48'::_bidPtrSA_030_4583[0],
            0);
        *((_BYTE *)TokenHandle + 8) = 1;
        return 0;
      }
      v9 = GetLastError();
      if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`41'::_bidPtrSA_030_4578[0] )
        return 2147500037LL;
      v10 = `CThreadSecurityToken::Initialize'::`41'::_bidPtrSA_030_4578[0];
      v4 = v9;
      v11 = 4687872;
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`57'::_bidPtrSA_030_4588[0] )
        return 2147500037LL;
      v10 = `CThreadSecurityToken::Initialize'::`57'::_bidPtrSA_030_4588[0];
      v11 = 4698112;
    }
    bidTraceW(0, v11, v10, v4);
    return 2147500037LL;
  }
  v5 = GetCurrentThread();
  if ( !OpenThreadToken(v5, 0xEu, 0, TokenHandle) )
  {
    v4 = GetLastError();
    goto LABEL_9;
  }
  if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`16'::_bidPtrSA_030_4557[0] || bidID == -1 )
    return 0;
  v6 = `CThreadSecurityToken::Initialize'::`16'::_bidPtrSA_030_4557[0];
  v7 = 4666368;
LABEL_31:
  ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(bidID, 0, v7, v6, 0);
  return 0;
}

```

## disassembly

```asm
0x1004964d4  push    rbx
0x1004964d6  sub     rsp, 30h
0x1004964da  mov     rbx, rcx
0x1004964dd  call    cs:__imp_GetCurrentThread
0x1004964e3  mov     edx, 0Eh; DesiredAccess
0x1004964e8  mov     r9, rbx; TokenHandle
0x1004964eb  mov     rcx, rax; ThreadHandle
0x1004964ee  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1004964f2  call    cs:__imp_OpenThreadToken
0x1004964f8  test    eax, eax
0x1004964fa  jnz     loc_100496676
0x100496500  call    cs:__imp_GetLastError
0x100496506  mov     r9d, eax
0x100496509  cmp     eax, 5
0x10049650c  jnz     short loc_100496571
0x10049650e  call    cs:__imp_GetCurrentThread
0x100496514  xor     r8d, r8d; OpenAsSelf
0x100496517  mov     r9, rbx; TokenHandle
0x10049651a  mov     rcx, rax; ThreadHandle
0x10049651d  lea     edx, [r8+0Eh]; DesiredAccess
0x100496521  call    cs:__imp_OpenThreadToken
0x100496527  test    eax, eax
0x100496529  jz      short loc_100496568
0x10049652b  test    byte ptr cs:_bidGblFlags, 2
0x100496532  jz      loc_1004966BE
0x100496538  mov     rax, cs:?_bidPtrSA_030_4557@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidPtrSA_030_4557
0x10049653f  test    rax, rax
0x100496542  jz      loc_1004966BE
0x100496548  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100496550  jz      loc_1004966BE
0x100496556  mov     r9, cs:?_bidPtrSA_030_4557@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidPtrSA_030_4557
0x10049655d  mov     r8d, 473400h
0x100496563  jmp     loc_1004966A2
0x100496568  call    cs:__imp_GetLastError
0x10049656e  mov     r9d, eax
0x100496571  mov     ecx, 3F0h
0x100496576  cmp     r9d, ecx
0x100496579  jnz     loc_100496647
0x10049657f  test    byte ptr cs:_bidGblFlags, 2
0x100496586  jz      short loc_1004965AA
0x100496588  mov     rax, cs:?_bidPtrSA_030_4569@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidPtrSA_030_4569
0x10049658f  test    rax, rax
0x100496592  jz      short loc_1004965AA
0x100496594  mov     r8, cs:?_bidPtrSA_030_4569@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidPtrSA_030_4569
0x10049659b  mov     r9d, ecx
0x10049659e  xor     ecx, ecx
0x1004965a0  mov     edx, 476400h
0x1004965a5  call    _bidTraceW
0x1004965aa  call    cs:__imp_GetCurrentProcess
0x1004965b0  mov     r8, rbx; TokenHandle
0x1004965b3  mov     edx, 0Eh; DesiredAccess
0x1004965b8  mov     rcx, rax; ProcessHandle
0x1004965bb  call    cs:__imp_OpenProcessToken
0x1004965c1  test    eax, eax
0x1004965c3  jnz     short loc_1004965F9
0x1004965c5  call    cs:__imp_GetLastError
0x1004965cb  test    byte ptr cs:_bidGblFlags, 2
0x1004965d2  jz      loc_10049666F
0x1004965d8  mov     rcx, cs:?_bidPtrSA_030_4578@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidPtrSA_030_4578
0x1004965df  test    rcx, rcx
0x1004965e2  jz      loc_10049666F
0x1004965e8  mov     r8, cs:?_bidPtrSA_030_4578@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidPtrSA_030_4578
0x1004965ef  mov     r9d, eax
0x1004965f2  mov     edx, 478800h
0x1004965f7  jmp     short loc_100496668
0x1004965f9  test    byte ptr cs:_bidGblFlags, 2
0x100496600  jz      short loc_100496641
0x100496602  mov     rax, cs:?_bidPtrSA_030_4583@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidPtrSA_030_4583
0x100496609  test    rax, rax
0x10049660c  jz      short loc_100496641
0x10049660e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100496616  jz      short loc_100496641
0x100496618  mov     r9, cs:?_bidPtrSA_030_4583@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidPtrSA_030_4583
0x10049661f  xor     edx, edx
0x100496621  mov     rcx, cs:_bidID
0x100496628  mov     r8d, 479C00h
0x10049662e  mov     rax, cs:off_1005D39E0
0x100496635  and     [rsp+38h+var_18], 0
0x10049663b  call    cs:__guard_dispatch_icall_fptr
0x100496641  mov     byte ptr [rbx+8], 1
0x100496645  jmp     short loc_1004966BE
0x100496647  test    byte ptr cs:_bidGblFlags, 2
0x10049664e  jz      short loc_10049666F
0x100496650  mov     rax, cs:?_bidPtrSA_030_4588@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidPtrSA_030_4588
0x100496657  test    rax, rax
0x10049665a  jz      short loc_10049666F
0x10049665c  mov     r8, cs:?_bidPtrSA_030_4588@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidPtrSA_030_4588
0x100496663  mov     edx, 47B000h
0x100496668  xor     ecx, ecx
0x10049666a  call    _bidTraceW
0x10049666f  mov     eax, 80004005h
0x100496674  jmp     short loc_1004966C0
0x100496676  test    byte ptr cs:_bidGblFlags, 2
0x10049667d  jz      short loc_1004966BE
0x10049667f  mov     rax, cs:?_bidPtrSA_030_4595@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidPtrSA_030_4595
0x100496686  test    rax, rax
0x100496689  jz      short loc_1004966BE
0x10049668b  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100496693  jz      short loc_1004966BE
0x100496695  mov     r9, cs:?_bidPtrSA_030_4595@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidPtrSA_030_4595
0x10049669c  mov     r8d, 47CC00h
0x1004966a2  and     [rsp+38h+var_18], 0
0x1004966a8  xor     edx, edx
0x1004966aa  mov     rcx, cs:_bidID
0x1004966b1  mov     rax, cs:off_1005D39E0
0x1004966b8  call    cs:__guard_dispatch_icall_fptr
0x1004966be  xor     eax, eax
0x1004966c0  add     rsp, 30h
0x1004966c4  pop     rbx
0x1004966c5  retn
```
