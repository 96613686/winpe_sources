# CComponentData::ClearLog(unsigned __int64,ulong,unsigned __int64)

- ea: `0x180005540`
- end: `0x1800056b3`
- name: `?ClearLog@CComponentData@@UEAAJ_KK0@Z`
- size: `371`
- prototype: `__int64 __fastcall(CComponentData *this, struct CLogInfo *, unsigned int, const WCHAR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005540`
- `0x180006cc0`
- `0x1800153ac`
- `0x1800154e8`
- `0x1800172cc`
- `0x18001e214`
- `0x18001f2dc`

## import_xrefs

- `ADVAPI32!ClearEventLogW` at `0x1800055e5`
- `ADVAPI32!ClearEventLogW` at `0x1800055e5`
- `KERNEL32!DeleteFileW` at `0x1800055d7`
- `KERNEL32!DeleteFileW` at `0x1800055d7`
- `KERNEL32!GetLastError` at `0x18000561e`
- `KERNEL32!GetLastError` at `0x18000561e`

## pseudocode

```c
__int64 __fastcall CComponentData::ClearLog(
        CComponentData *this,
        struct CLogInfo *a2,
        unsigned int a3,
        const WCHAR *a4)
{
  __int64 v8; // rax
  __int64 v9; // r9
  signed int v10; // eax
  signed int v11; // edi
  CSynchWindow *v12; // rcx
  struct CLogInfo *v13; // rbx
  __int64 v14; // rcx
  signed int LastError; // eax
  __int16 v16; // ax
  HANDLE hEventLog[7]; // [rsp+20h] [rbp-38h] BYREF

  *(_OWORD *)hEventLog = 0;
  if ( a3 > 1 )
  {
    v8 = *((_QWORD *)this + 5);
    v9 = 8;
    if ( v8 && *(_DWORD *)(v8 + 1600) == 9 )
      v9 = 4;
    v10 = CLogInfo::SaveLogAs(a2, a3, a4, v9);
    v11 = v10;
    if ( v10 < 0 )
    {
      DisplayLogAccessError(v10, *((struct IConsole **)this + 140), a2);
      goto LABEL_25;
    }
  }
  v11 = CEventLog::Open((CEventLog *)hEventLog, a2);
  if ( v11 < 0 )
  {
    if ( v11 == -2147024891 )
    {
      *((_WORD *)a2 + 12) |= 0x600u;
      CSynchWindow::Post(v12, 0x7E9u, (unsigned __int64)this - 32, (__int64)a2);
    }
    DisplayLogAccessError(v11, *((struct IConsole **)this + 140), a2);
    goto LABEL_22;
  }
  if ( a3 != 1 )
    a4 = 0;
  if ( a4 )
    DeleteFileW(a4);
  if ( ClearEventLogW(hEventLog[1], a4) )
  {
    v13 = (struct CLogInfo *)hEventLog[0];
    _InterlockedIncrement((volatile signed __int32 *)hEventLog[0] + 1190);
    CEventLog::Close((CEventLog *)hEventLog);
    v11 = CEventLog::Open((CEventLog *)hEventLog, v13);
    CLogInfo::Release(v13);
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v11 >= 0 )
  {
    v16 = *((_WORD *)a2 + 12);
    if ( (v16 & 0x200) != 0 )
    {
      v14 = 65023;
      *((_WORD *)a2 + 12) = v16 & 0xFDFF;
    }
LABEL_22:
    if ( v11 >= 0 && v11 != 1 )
      CSynchWindow::Post((CSynchWindow *)v14, 0x7E8u, 0, (__int64)a2);
  }
LABEL_25:
  CEventLog::Close((CEventLog *)hEventLog);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005540  push    rbx
0x180005542  push    rbp
0x180005543  push    rsi
0x180005544  push    rdi
0x180005545  push    r14
0x180005547  sub     rsp, 30h
0x18000554b  xorps   xmm0, xmm0
0x18000554e  mov     rbx, r9
0x180005551  mov     r14d, r8d
0x180005554  mov     rsi, rdx
0x180005557  mov     rbp, rcx
0x18000555a  movdqu  xmmword ptr [rsp+58h+hEventLog], xmm0
0x180005560  cmp     r8d, 1
0x180005564  jbe     short loc_1800055AE
0x180005566  mov     rax, [rcx+28h]
0x18000556a  mov     r9d, 8
0x180005570  test    rax, rax
0x180005573  jz      short loc_180005584
0x180005575  cmp     dword ptr [rax+640h], 9
0x18000557c  lea     ecx, [r9-4]
0x180005580  cmovz   r9d, ecx
0x180005584  mov     r8, rbx
0x180005587  mov     edx, r14d
0x18000558a  mov     rcx, rsi
0x18000558d  call    ?SaveLogAs@CLogInfo@@QEAAJW4SAVE_TYPE@@PEBGW4DIRECTION@@@Z; CLogInfo::SaveLogAs(SAVE_TYPE,ushort const *,DIRECTION)
0x180005592  mov     edi, eax
0x180005594  test    eax, eax
0x180005596  jns     short loc_1800055AE
0x180005598  mov     rdx, [rbp+460h]; struct IConsole *
0x18000559f  mov     r8, rsi; this
0x1800055a2  mov     ecx, eax; dwMessageId
0x1800055a4  call    ?DisplayLogAccessError@@YAXJPEAUIConsole@@PEAVCLogInfo@@@Z; DisplayLogAccessError(long,IConsole *,CLogInfo *)
0x1800055a9  jmp     loc_18000569C
0x1800055ae  mov     rdx, rsi; struct CLogInfo *
0x1800055b1  lea     rcx, [rsp+58h+hEventLog]; this
0x1800055b6  call    ?Open@CEventLog@@QEAAJPEAVCLogInfo@@@Z; CEventLog::Open(CLogInfo *)
0x1800055bb  mov     edi, eax
0x1800055bd  test    eax, eax
0x1800055bf  js      loc_180005650
0x1800055c5  xor     eax, eax
0x1800055c7  cmp     r14d, 1
0x1800055cb  cmovnz  rbx, rax
0x1800055cf  test    rbx, rbx
0x1800055d2  jz      short loc_1800055DD
0x1800055d4  mov     rcx, rbx; lpFileName
0x1800055d7  call    cs:__imp_DeleteFileW
0x1800055dd  mov     rcx, [rsp+58h+hEventLog+8]; hEventLog
0x1800055e2  mov     rdx, rbx; lpBackupFileName
0x1800055e5  call    cs:__imp_ClearEventLogW
0x1800055eb  test    eax, eax
0x1800055ed  jz      short loc_18000561E
0x1800055ef  mov     rbx, [rsp+58h+hEventLog]
0x1800055f4  lock inc dword ptr [rbx+1298h]
0x1800055fb  lea     rcx, [rsp+58h+hEventLog]; this
0x180005600  call    ?Close@CEventLog@@QEAAXXZ; CEventLog::Close(void)
0x180005605  mov     rdx, rbx; struct CLogInfo *
0x180005608  lea     rcx, [rsp+58h+hEventLog]; this
0x18000560d  call    ?Open@CEventLog@@QEAAJPEAVCLogInfo@@@Z; CEventLog::Open(CLogInfo *)
0x180005612  mov     rcx, rbx; this
0x180005615  mov     edi, eax
0x180005617  call    ?Release@CLogInfo@@QEAAKXZ; CLogInfo::Release(void)
0x18000561c  jmp     short loc_180005633
0x18000561e  call    cs:__imp_GetLastError
0x180005624  mov     edi, eax
0x180005626  test    eax, eax
0x180005628  jle     short loc_180005633
0x18000562a  movzx   edi, ax
0x18000562d  or      edi, 80070000h
0x180005633  test    edi, edi
0x180005635  js      short loc_18000569C
0x180005637  movzx   eax, word ptr [rsi+18h]
0x18000563b  bt      ax, 9
0x180005640  jnb     short loc_180005683
0x180005642  mov     ecx, 0FDFFh
0x180005647  and     ax, cx
0x18000564a  mov     [rsi+18h], ax
0x18000564e  jmp     short loc_180005683
0x180005650  cmp     edi, 80070005h
0x180005656  jnz     short loc_180005672
0x180005658  mov     eax, 600h
0x18000565d  lea     r8, [rbp-20h]; unsigned __int64
0x180005661  or      [rsi+18h], ax
0x180005665  mov     r9, rsi; __int64
0x180005668  mov     edx, 7E9h; unsigned int
0x18000566d  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x180005672  mov     rdx, [rbp+460h]; struct IConsole *
0x180005679  mov     r8, rsi; this
0x18000567c  mov     ecx, edi; dwMessageId
0x18000567e  call    ?DisplayLogAccessError@@YAXJPEAUIConsole@@PEAVCLogInfo@@@Z; DisplayLogAccessError(long,IConsole *,CLogInfo *)
0x180005683  test    edi, edi
0x180005685  js      short loc_18000569C
0x180005687  cmp     edi, 1
0x18000568a  jz      short loc_18000569C
0x18000568c  mov     r9, rsi; __int64
0x18000568f  xor     r8d, r8d; unsigned __int64
0x180005692  mov     edx, 7E8h; unsigned int
0x180005697  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x18000569c  lea     rcx, [rsp+58h+hEventLog]; this
0x1800056a1  call    ?Close@CEventLog@@QEAAXXZ; CEventLog::Close(void)
0x1800056a6  mov     eax, edi
0x1800056a8  add     rsp, 30h
0x1800056ac  pop     r14
0x1800056ae  pop     rdi
0x1800056af  pop     rsi
0x1800056b0  pop     rbp
0x1800056b1  pop     rbx
0x1800056b2  retn
```
