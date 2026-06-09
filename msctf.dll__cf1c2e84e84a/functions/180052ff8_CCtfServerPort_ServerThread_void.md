# CCtfServerPort::ServerThread(void *)

- ea: `0x180052ff8`
- end: `0x180053223`
- name: `?ServerThread@CCtfServerPort@@AEAAXPEAX@Z`
- size: `555`
- prototype: `void __fastcall(CCtfServerPort *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b5040`

## callees

- `0x18000f900`
- `0x1800139a4`
- `0x180040760`
- `0x180052ff8`
- `0x18005322c`
- `0x180053638`
- `0x180053660`
- `0x180053674`
- `0x1800a18d4`
- `0x180106a60`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800530e5`
- `ntdll!RtlInitUnicodeString` at `0x1800530e5`
- `ntdll!NtAlpcCreatePort` at `0x180053124`
- `ntdll!NtAlpcCreatePort` at `0x180053124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053199`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053199`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005314f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005314f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005317c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005317c`
- `USER32!SetThreadDesktop` at `0x18005304b`
- `USER32!SetThreadDesktop` at `0x18005304b`

## pseudocode

```c
void __fastcall CCtfServerPort::ServerThread(CCtfServerPort *this, unsigned __int64 a2, unsigned int a3)
{
  HDESK v5; // rcx
  int i; // esi
  __int64 v7; // rcx
  __int128 v8; // [rsp+40h] [rbp-2C8h] BYREF
  __int128 v9; // [rsp+50h] [rbp-2B8h]
  __int128 v10; // [rsp+60h] [rbp-2A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-298h] BYREF
  int v12; // [rsp+80h] [rbp-288h] BYREF
  __int64 v13; // [rsp+84h] [rbp-284h]
  int v14; // [rsp+8Ch] [rbp-27Ch]
  __int64 v15; // [rsp+90h] [rbp-278h]
  __int64 v16; // [rsp+98h] [rbp-270h]
  __int64 v17; // [rsp+A0h] [rbp-268h]
  __int64 v18; // [rsp+A8h] [rbp-260h]
  __int64 v19; // [rsp+B0h] [rbp-258h]
  __int64 v20; // [rsp+B8h] [rbp-250h]
  __int64 v21; // [rsp+C0h] [rbp-248h]
  WCHAR SourceString[264]; // [rsp+D0h] [rbp-238h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v5 = (HDESK)*((_QWORD *)this + 19);
  if ( v5 )
    SetThreadDesktop(v5);
  GetDesktopUniqueName(L"\\BaseNamedObjects\\msctf.server", SourceString, a3);
  v14 = 1;
  v21 = 16;
  v12 = 655360;
  v13 = 12;
  v15 = 512;
  v16 = 0;
  v17 = 0x20000;
  v18 = 0x20000;
  v19 = 0x20000;
  v20 = 0x100000;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  LODWORD(v8) = 48;
  *((_QWORD *)&v8 + 1) = 0;
  DWORD2(v9) = 64;
  *(_QWORD *)&v9 = &DestinationString;
  v10 = a2;
  if ( (int)NtAlpcCreatePort(this, &v8, &v12) >= 0 )
  {
    CGCompartList::Init((CCtfServerPort *)((char *)this + 64));
    SetEvent(*((HANDLE *)this + 2));
    CCtfServerPort::ServerLoop(this);
    ResetEvent(*((HANDLE *)this + 2));
    CGCompartList::Uninit((CCtfServerPort *)((char *)this + 64));
    if ( dword_180140688 )
    {
      EnterCriticalSection(&g_cs);
      ClosePort((void **)this);
      CicLeaveCriticalSection((struct CCicCriticalSectionStatic *)&g_cs);
    }
    for ( i = 0; ; ++i )
    {
      v7 = *((_QWORD *)this + 6);
      if ( i >= *((_DWORD *)this + 14) )
        break;
      ClosePort((void **)(*(_QWORD *)(v7 + 8LL * i) + 8LL));
    }
    cicMemFree(v7);
    *((_QWORD *)this + 6) = 0;
    *((_DWORD *)this + 15) = 0;
    *((_DWORD *)this + 14) = 0;
  }
}

```

## disassembly

```asm
0x180052ff8  mov     [rsp+arg_10], rbx
0x180052ffd  mov     [rsp+arg_18], rsi
0x180053002  push    rdi
0x180053003  push    r14
0x180053005  push    r15
0x180053007  sub     rsp, 2F0h
0x18005300e  mov     rax, cs:__security_cookie
0x180053015  xor     rax, rsp
0x180053018  mov     [rsp+308h+var_28], rax
0x180053020  mov     rsi, rdx
0x180053023  mov     rbx, rcx
0x180053026  mov     [rsp+308h+var_2D0], rcx
0x18005302b  xorps   xmm0, xmm0
0x18005302e  movups  [rsp+308h+var_2C8], xmm0
0x180053033  movups  [rsp+308h+var_2B8], xmm0
0x180053038  movups  [rsp+308h+var_2A8], xmm0
0x18005303d  mov     rcx, [rcx+98h]; hDesktop
0x180053044  xor     edi, edi
0x180053046  test    rcx, rcx
0x180053049  jz      short loc_180053051
0x18005304b  call    cs:__imp_SetThreadDesktop
0x180053051  lea     rdx, [rsp+308h+SourceString]; unsigned __int16 *
0x180053059  lea     rcx, aBasenamedobjec_0; "\\BaseNamedObjects\\msctf.server"
0x180053060  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x180053065  mov     [rsp+308h+var_27C], 1
0x180053070  mov     [rsp+308h+var_248], 10h
0x18005307c  mov     [rsp+308h+var_288], 0A0000h
0x180053087  mov     [rsp+308h+var_284], 0Ch
0x180053093  mov     [rsp+308h+var_278], 200h
0x18005309f  mov     [rsp+308h+var_270], rdi
0x1800530a7  mov     eax, 20000h
0x1800530ac  mov     [rsp+308h+var_268], rax
0x1800530b4  mov     [rsp+308h+var_260], rax
0x1800530bc  mov     [rsp+308h+var_258], rax
0x1800530c4  mov     [rsp+308h+var_250], 100000h
0x1800530d0  xorps   xmm0, xmm0
0x1800530d3  movups  xmmword ptr [rsp+308h+DestinationString.Length], xmm0
0x1800530d8  lea     rdx, [rsp+308h+SourceString]; SourceString
0x1800530e0  lea     rcx, [rsp+308h+DestinationString]; DestinationString
0x1800530e5  call    cs:__imp_RtlInitUnicodeString
0x1800530eb  mov     dword ptr [rsp+308h+var_2C8], 30h ; '0'
0x1800530f3  mov     qword ptr [rsp+308h+var_2C8+8], rdi
0x1800530f8  mov     dword ptr [rsp+308h+var_2B8+8], 40h ; '@'
0x180053100  lea     rax, [rsp+308h+DestinationString]
0x180053105  mov     qword ptr [rsp+308h+var_2B8], rax
0x18005310a  mov     qword ptr [rsp+308h+var_2A8], rsi
0x18005310f  mov     qword ptr [rsp+308h+var_2A8+8], rdi
0x180053114  lea     r8, [rsp+308h+var_288]
0x18005311c  lea     rdx, [rsp+308h+var_2C8]
0x180053121  mov     rcx, rbx
0x180053124  call    cs:__imp_NtAlpcCreatePort
0x18005312a  test    eax, eax
0x18005312c  js      loc_1800531FA
0x180053132  lea     rsi, [rbx+40h]
0x180053136  mov     [rsp+308h+var_2E0], rsi
0x18005313b  mov     rcx, rsi; this
0x18005313e  call    ?Init@CGCompartList@@QEAAXXZ; CGCompartList::Init(void)
0x180053143  lea     r15, [rbx+10h]
0x180053147  mov     [rsp+308h+var_2D8], r15
0x18005314c  mov     rcx, [r15]; hEvent
0x18005314f  call    cs:__imp_SetEvent
0x180053155  nop
0x180053156  mov     rcx, rbx; this
0x180053159  call    ?ServerLoop@CCtfServerPort@@AEAAXXZ; CCtfServerPort::ServerLoop(void)
0x18005315e  jmp     short loc_180053171
0x180053160  xor     edi, edi
0x180053162  mov     rbx, [rsp+308h+var_2D0]
0x180053167  mov     rsi, [rsp+308h+var_2E0]
0x18005316c  mov     r15, [rsp+308h+var_2D8]
0x180053171  mov     r14, rbx
0x180053174  mov     [rsp+308h+var_2D8], rbx
0x180053179  mov     rcx, [r15]; hEvent
0x18005317c  call    cs:__imp_ResetEvent
0x180053182  mov     rcx, rsi; this
0x180053185  call    ?Uninit@CGCompartList@@QEAAXXZ; CGCompartList::Uninit(void)
0x18005318a  cmp     cs:dword_180140688, edi
0x180053190  jz      short loc_1800531C1
0x180053192  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x180053199  call    cs:__imp_EnterCriticalSection
0x18005319f  nop
0x1800531a0  mov     rcx, rbx; void **
0x1800531a3  call    ?ClosePort@@YAXAEAPEAX@Z; ClosePort(void * &)
0x1800531a8  jmp     short loc_1800531B4
0x1800531aa  xor     edi, edi
0x1800531ac  mov     r14, [rsp+308h+var_2D8]
0x1800531b1  mov     rbx, r14
0x1800531b4  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; struct CCicCriticalSectionStatic *
0x1800531bb  call    ?CicLeaveCriticalSection@@YAXAEAVCCicCriticalSectionStatic@@@Z; CicLeaveCriticalSection(CCicCriticalSectionStatic &)
0x1800531c0  nop
0x1800531c1  mov     esi, edi
0x1800531c3  mov     [rsp+308h+var_2E8], edi
0x1800531c7  mov     rcx, [r14+30h]
0x1800531cb  cmp     esi, [rbx+38h]
0x1800531ce  jge     short loc_1800531E8
0x1800531d0  movsxd  rax, esi
0x1800531d3  mov     rcx, [rcx+rax*8]
0x1800531d7  add     rcx, 8; void **
0x1800531db  call    ?ClosePort@@YAXAEAPEAX@Z; ClosePort(void * &)
0x1800531e0  inc     esi
0x1800531e2  mov     [rsp+308h+var_2E8], esi
0x1800531e6  jmp     short loc_1800531C7
0x1800531e8  call    cicMemFree
0x1800531ed  mov     [r14+30h], rdi
0x1800531f1  mov     [r14+3Ch], edi
0x1800531f5  mov     [rbx+38h], edi
0x1800531f8  jmp     short $+2
0x1800531fa  mov     rcx, [rsp+308h+var_28]
0x180053202  xor     rcx, rsp; StackCookie
0x180053205  call    __security_check_cookie
0x18005320a  lea     r11, [rsp+308h+var_18]
0x180053212  mov     rbx, [r11+30h]
0x180053216  mov     rsi, [r11+38h]
0x18005321a  mov     rsp, r11
0x18005321d  pop     r15
0x18005321f  pop     r14
0x180053221  pop     rdi
0x180053222  retn
0x180107a0f  push    rbp
0x180107a11  sub     rsp, 20h
0x180107a15  mov     rbp, rdx
0x180107a18  mov     dl, cs:?g_fEnableFailFast@@3_NA; bool
0x180107a1e  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x180107a23  nop
0x180107a24  add     rsp, 20h
0x180107a28  pop     rbp
0x180107a29  retn
0x180107a2b  push    rbp
0x180107a2d  sub     rsp, 20h
0x180107a31  mov     rbp, rdx
0x180107a34  mov     dl, cs:?g_fEnableFailFast@@3_NA; bool
0x180107a3a  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x180107a3f  nop
0x180107a40  add     rsp, 20h
0x180107a44  pop     rbp
0x180107a45  retn
0x180107a47  push    rbp
0x180107a49  sub     rsp, 20h
0x180107a4d  mov     rbp, rdx
0x180107a50  mov     dl, cs:?g_fEnableFailFast@@3_NA; bool
0x180107a56  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x180107a5b  nop
0x180107a5c  add     rsp, 20h
0x180107a60  pop     rbp
0x180107a61  retn
```
