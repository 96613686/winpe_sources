# CSystemScanner::SystemScanCompleteWork(_TP_CALLBACK_INSTANCE *)

- ea: `0x180016d24`
- end: `0x180016f96`
- name: `?SystemScanCompleteWork@CSystemScanner@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `626`
- prototype: `void(CSystemScanner *__hidden this, struct _TP_CALLBACK_INSTANCE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016fa0`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x1800137d4`
- `0x180016d24`
- `0x18001ac20`
- `0x18001ae24`
- `0x180039010`

## import_xrefs

- `KERNEL32!SetEventWhenCallbackReturns` at `0x180016d50`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x180016f67`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x180016d50`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x180016f67`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180016e29`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180016e29`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016d84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016dba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016dda`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016e13`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016ee0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016d84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016dba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016dda`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016e13`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016ee0`
- `KERNEL32!WaitForSingleObject` at `0x180016d70`
- `KERNEL32!WaitForSingleObject` at `0x180016d70`

## string_xrefs

- `0x180016e4f`: `CSystemScanner::SystemScanCompleteWork`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSystemScanner::SystemScanCompleteWork(RTL_SRWLOCK *this, struct _TP_CALLBACK_INSTANCE *a2)
{
  __int64 v4; // r8
  RTL_SRWLOCK *v5; // rbx
  DWORD v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  const char *v9; // [rsp+40h] [rbp-10h] BYREF
  int v10; // [rsp+48h] [rbp-8h]
  RTL_SRWLOCK *v11; // [rsp+70h] [rbp+20h] BYREF
  RTL_SRWLOCK *v12; // [rsp+80h] [rbp+30h] BYREF

  if ( *((_DWORD *)this[2].Ptr + 2) )
  {
    v5 = this + 32;
    v6 = WaitForSingleObject(this[4].Ptr, 0);
    v11 = v5;
    if ( v6 == 258 )
    {
      AcquireSRWLockExclusive(v5);
      if ( LODWORD(this[33].Ptr) )
      {
        CDiskPnpMonitor::Shutdown((CDiskPnpMonitor *)&this[34]);
        LODWORD(this[33].Ptr) = 0;
      }
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v11);
      v11 = this + 6;
      AcquireSRWLockExclusive(this + 6);
      if ( SHIDWORD(this[7].Ptr) > SLODWORD(this[8].Ptr) )
      {
LABEL_7:
        CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v11);
        return;
      }
    }
    else
    {
      AcquireSRWLockExclusive(v5);
      if ( LODWORD(this[33].Ptr) )
      {
        CDiskPnpMonitor::Shutdown((CDiskPnpMonitor *)&this[34]);
        LODWORD(this[33].Ptr) = 0;
      }
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v11);
      v11 = this + 6;
      AcquireSRWLockExclusive(this + 6);
      if ( SHIDWORD(this[7].Ptr) > SLODWORD(this[8].Ptr) )
      {
        ReleaseSRWLockExclusive(this + 6);
        v11 = 0;
        v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
        *(_QWORD *)(v7 + 16) = "CSystemScanner::SystemScanCompleteWork";
        v9 = "CSystemScanner::SystemScanCompleteWork";
        v10 = 0;
        ++*(_WORD *)(v7 + 8);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CSystemScanner::SystemScanCompleteWork");
        }
        v12 = v5;
        AcquireSRWLockExclusive(v5);
        LODWORD(this[33].Ptr) = 1;
        v8 = CDiskPnpMonitor::Start((CDiskPnpMonitor *)&this[34]);
        v10 = v8;
        if ( v8 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              59,
              &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
              (unsigned int)v8);
          }
          LODWORD(this[33].Ptr) = 0;
        }
        CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v12);
        CHResultImp::~CHResultImp((CHResultImp *)&v9);
        goto LABEL_7;
      }
    }
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v11);
    SetEventWhenCallbackReturns(a2, this[5].Ptr);
    v4 = 0;
    goto LABEL_23;
  }
  SetEventWhenCallbackReturns(a2, this[5].Ptr);
  LOBYTE(v4) = SHIDWORD(this[8].Ptr) > 0;
LABEL_23:
  (**(void (__fastcall ***)(PVOID, _QWORD, __int64))this[3].Ptr)(this[3].Ptr, 0, v4);
}

```

## disassembly

```asm
0x180016d24  mov     [rsp-18h+arg_8], rbx
0x180016d29  mov     [rsp-18h+arg_18], rsi
0x180016d2e  push    rbp
0x180016d2f  push    rdi
0x180016d30  push    r14
0x180016d32  mov     rbp, rsp
0x180016d35  sub     rsp, 50h
0x180016d39  mov     r14, rdx
0x180016d3c  mov     rsi, rcx
0x180016d3f  mov     rax, [rcx+10h]
0x180016d43  cmp     dword ptr [rax+8], 0
0x180016d47  jnz     short loc_180016D63
0x180016d49  mov     rdx, [rcx+28h]; evt
0x180016d4d  mov     rcx, r14; pci
0x180016d50  call    cs:__imp_SetEventWhenCallbackReturns
0x180016d56  cmp     dword ptr [rsi+44h], 0
0x180016d5a  setnle  r8b
0x180016d5e  jmp     loc_180016F70
0x180016d63  lea     rbx, [rcx+100h]
0x180016d6a  xor     edx, edx; dwMilliseconds
0x180016d6c  mov     rcx, [rcx+20h]; hHandle
0x180016d70  call    cs:__imp_WaitForSingleObject
0x180016d76  mov     [rbp+arg_0], rbx
0x180016d7a  mov     rcx, rbx; SRWLock
0x180016d7d  cmp     eax, 102h
0x180016d82  jnz     short loc_180016DDA
0x180016d84  call    cs:__imp_AcquireSRWLockExclusive
0x180016d8a  cmp     dword ptr [rsi+108h], 0
0x180016d91  jz      short loc_180016DA9
0x180016d93  lea     rcx, [rsi+110h]; this
0x180016d9a  call    ?Shutdown@CDiskPnpMonitor@@QEAAXXZ; CDiskPnpMonitor::Shutdown(void)
0x180016d9f  mov     dword ptr [rsi+108h], 0
0x180016da9  lea     rcx, [rbp+arg_0]; this
0x180016dad  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180016db2  lea     rcx, [rsi+30h]; SRWLock
0x180016db6  mov     [rbp+arg_0], rcx
0x180016dba  call    cs:__imp_AcquireSRWLockExclusive
0x180016dc0  mov     eax, [rsi+40h]
0x180016dc3  lea     rcx, [rbp+arg_0]; this
0x180016dc7  cmp     [rsi+3Ch], eax
0x180016dca  jle     loc_180016F5B
0x180016dd0  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180016dd5  jmp     loc_180016F81
0x180016dda  call    cs:__imp_AcquireSRWLockExclusive
0x180016de0  cmp     dword ptr [rsi+108h], 0
0x180016de7  jz      short loc_180016DFF
0x180016de9  lea     rcx, [rsi+110h]; this
0x180016df0  call    ?Shutdown@CDiskPnpMonitor@@QEAAXXZ; CDiskPnpMonitor::Shutdown(void)
0x180016df5  mov     dword ptr [rsi+108h], 0
0x180016dff  lea     rcx, [rbp+arg_0]; this
0x180016e03  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180016e08  lea     rdi, [rsi+30h]
0x180016e0c  mov     [rbp+arg_0], rdi
0x180016e10  mov     rcx, rdi; SRWLock
0x180016e13  call    cs:__imp_AcquireSRWLockExclusive
0x180016e19  nop
0x180016e1a  mov     eax, [rsi+40h]
0x180016e1d  cmp     [rsi+3Ch], eax
0x180016e20  jle     loc_180016F57
0x180016e26  mov     rcx, rdi; SRWLock
0x180016e29  call    cs:__imp_ReleaseSRWLockExclusive
0x180016e2f  mov     [rbp+arg_0], 0
0x180016e37  mov     ecx, cs:_tls_index
0x180016e3d  mov     rax, gs:58h
0x180016e46  mov     rdx, [rax+rcx*8]
0x180016e4a  mov     eax, 10h
0x180016e4f  lea     r8, aCsystemscanner_2; "CSystemScanner::SystemScanCompleteWork"
0x180016e56  mov     [rax+rdx], r8
0x180016e5a  mov     [rbp+var_10], r8
0x180016e5e  mov     [rbp+var_8], 0
0x180016e65  mov     eax, 8
0x180016e6a  mov     edi, 1
0x180016e6f  add     [rax+rdx], di
0x180016e73  movzx   edx, word ptr [rax+rdx]
0x180016e77  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180016e7e  movzx   eax, cx
0x180016e81  cmp     dx, cx
0x180016e84  cmovb   ax, dx
0x180016e88  mov     [rbp+var_20], ax
0x180016e8c  cmovb   cx, dx
0x180016e90  mov     [rbp+var_1E], cx
0x180016e94  xor     eax, eax
0x180016e96  mov     [rbp+var_1C], eax
0x180016e99  mov     rax, cs:off_180047060; "                                       "...
0x180016ea0  mov     [rbp+var_18], rax
0x180016ea4  lea     r14, WPP_GLOBAL_Control
0x180016eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eb2  cmp     rcx, r14
0x180016eb5  jz      short loc_180016ED9
0x180016eb7  test    [rcx+1Ch], dil
0x180016ebb  jz      short loc_180016ED9
0x180016ebd  cmp     byte ptr [rcx+19h], 5
0x180016ec1  jb      short loc_180016ED9
0x180016ec3  lea     edx, [rdi+0Ch]
0x180016ec6  mov     [rsp+50h+var_30], r8; __int64
0x180016ecb  lea     r9, [rbp+var_20]
0x180016ecf  mov     rcx, [rcx+10h]; LoggerHandle
0x180016ed3  call    WPP_SF_aZs
0x180016ed8  nop
0x180016ed9  mov     [rbp+arg_10], rbx
0x180016edd  mov     rcx, rbx; SRWLock
0x180016ee0  call    cs:__imp_AcquireSRWLockExclusive
0x180016ee6  nop
0x180016ee7  mov     [rsi+108h], edi
0x180016eed  lea     rcx, [rsi+110h]; this
0x180016ef4  call    ?Start@CDiskPnpMonitor@@QEAAJXZ; CDiskPnpMonitor::Start(void)
0x180016ef9  mov     [rbp+var_8], eax
0x180016efc  test    eax, eax
0x180016efe  jns     short loc_180016F3A
0x180016f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f07  cmp     rcx, r14
0x180016f0a  jz      short loc_180016F30
0x180016f0c  test    [rcx+1Ch], dil
0x180016f10  jz      short loc_180016F30
0x180016f12  cmp     byte ptr [rcx+19h], 2
0x180016f16  jb      short loc_180016F30
0x180016f18  mov     edx, 3Bh ; ';'
0x180016f1d  mov     r9d, eax
0x180016f20  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180016f27  mov     rcx, [rcx+10h]
0x180016f2b  call    WPP_SF_d
0x180016f30  mov     dword ptr [rsi+108h], 0
0x180016f3a  lea     rcx, [rbp+arg_10]; this
0x180016f3e  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180016f43  nop
0x180016f44  lea     rcx, [rbp+var_10]; this
0x180016f48  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180016f4d  nop
0x180016f4e  lea     rcx, [rbp+arg_0]
0x180016f52  jmp     loc_180016DD0
0x180016f57  lea     rcx, [rbp+arg_0]; this
0x180016f5b  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180016f60  mov     rdx, [rsi+28h]; evt
0x180016f64  mov     rcx, r14; pci
0x180016f67  call    cs:__imp_SetEventWhenCallbackReturns
0x180016f6d  xor     r8d, r8d
0x180016f70  mov     rcx, [rsi+18h]
0x180016f74  mov     rax, [rcx]
0x180016f77  xor     edx, edx
0x180016f79  mov     rax, [rax]
0x180016f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f81  lea     r11, [rsp+50h+var_s0]
0x180016f86  mov     rbx, [r11+28h]
0x180016f8a  mov     rsi, [r11+38h]
0x180016f8e  mov     rsp, r11
0x180016f91  pop     r14
0x180016f93  pop     rdi
0x180016f94  pop     rbp
0x180016f95  retn
```
