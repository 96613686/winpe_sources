# COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)

- ea: `0x14000c084`
- end: `0x14000c19e`
- name: `?LogOmaDmPrcScheduleRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z`
- size: `282`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000edf4`
- `0x14000fff0`
- `0x140010bb8`
- `0x140012288`
- `0x14001401c`

## callees

- `0x140001314`
- `0x14000c084`
- `0x14000d238`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(
        COmaDmPrcLogger *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int a6)
{
  int v7; // ebx
  int v8; // esi
  int v9; // r14d
  __int64 *v10; // rdx
  char *v11; // [rsp+60h] [rbp-19h] BYREF
  const unsigned __int16 *v12; // [rsp+68h] [rbp-11h] BYREF
  const unsigned __int16 *v13; // [rsp+70h] [rbp-9h] BYREF
  const unsigned __int16 *v14; // [rsp+78h] [rbp-1h] BYREF
  const unsigned __int16 *v15; // [rsp+80h] [rbp+7h] BYREF
  __int64 v16[7]; // [rsp+88h] [rbp+Fh] BYREF

  v7 = a6;
  v8 = (int)a3;
  v9 = (int)a2;
  if ( (unsigned int)dword_140023000 > 5
    && (qword_140023010 & 0x400000000000LL) != 0
    && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
  {
    v11 = (char *)this + 16;
    v12 = a5;
    v13 = a4;
    v14 = a3;
    v15 = a2;
    v16[0] = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_14001DF91,
      0,
      (_DWORD)a4,
      (__int64)v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&a6,
      (__int64)&v11);
  }
  if ( v7 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) == 0 )
      return;
    v10 = EnterpriseDiagnosticsOmaDmScheduleRetrySessionSuccess;
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x20) == 0 )
      return;
    v10 = EnterpriseDiagnosticsOmaDmScheduleRetrySessionFailure2;
  }
  McTemplateU0zzzzd_EventWriteTransfer((_DWORD)this, (_DWORD)v10, v9, v8, (__int64)a4, (__int64)a5, v7);
}

```

## disassembly

```asm
0x14000c084  push    rbp
0x14000c086  push    rbx
0x14000c087  push    rsi
0x14000c088  push    rdi
0x14000c089  push    r14
0x14000c08b  push    r15
0x14000c08d  lea     rbp, [rsp-1Fh]
0x14000c092  sub     rsp, 98h
0x14000c099  mov     eax, cs:dword_140023000
0x14000c09f  mov     rdi, r9
0x14000c0a2  mov     ebx, [rbp+47h+arg_28]
0x14000c0a5  mov     rsi, r8
0x14000c0a8  mov     r15, [rbp+47h+arg_20]
0x14000c0ac  mov     r14, rdx
0x14000c0af  cmp     eax, 5
0x14000c0b2  jbe     loc_14000C14E
0x14000c0b8  mov     rdx, cs:qword_140023018
0x14000c0bf  mov     r8, 400000000000h
0x14000c0c9  mov     rax, cs:qword_140023010
0x14000c0d0  test    r8, rax
0x14000c0d3  jz      short loc_14000C14E
0x14000c0d5  mov     rax, rdx
0x14000c0d8  and     rax, r8
0x14000c0db  cmp     rax, rdx
0x14000c0de  jnz     short loc_14000C14E
0x14000c0e0  lea     rax, [rcx+10h]
0x14000c0e4  mov     [rbp+47h+arg_28], ebx
0x14000c0e7  mov     [rbp+47h+var_60], rax
0x14000c0eb  lea     rdx, byte_14001DF91
0x14000c0f2  lea     rax, [rbp+47h+var_60]
0x14000c0f6  mov     [rbp+47h+var_58], r15
0x14000c0fa  mov     [rsp+0C0h+var_70], rax
0x14000c0ff  lea     rax, [rbp+47h+arg_28]
0x14000c103  mov     [rsp+0C0h+var_78], rax
0x14000c108  lea     rax, [rbp+47h+var_58]
0x14000c10c  mov     [rsp+0C0h+var_80], rax
0x14000c111  lea     rax, [rbp+47h+var_50]
0x14000c115  mov     [rsp+0C0h+var_88], rax
0x14000c11a  lea     rax, [rbp+47h+var_48]
0x14000c11e  mov     [rsp+0C0h+var_90], rax
0x14000c123  lea     rax, [rbp+47h+var_40]
0x14000c127  mov     [rsp+0C0h+var_98], rax
0x14000c12c  lea     rax, [rbp+47h+var_38]
0x14000c130  mov     [rsp+0C0h+var_A0], rax
0x14000c135  mov     [rbp+47h+var_50], r9
0x14000c139  mov     [rbp+47h+var_48], rsi
0x14000c13d  mov     [rbp+47h+var_40], r14
0x14000c141  mov     [rbp+47h+var_38], 2000000h
0x14000c149  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000c14e  test    ebx, ebx
0x14000c150  jns     short loc_14000C164
0x14000c152  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 20h
0x14000c159  jz      short loc_14000C18D
0x14000c15b  lea     rdx, EnterpriseDiagnosticsOmaDmScheduleRetrySessionFailure2
0x14000c162  jmp     short loc_14000C174
0x14000c164  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000c16b  jz      short loc_14000C18D
0x14000c16d  lea     rdx, EnterpriseDiagnosticsOmaDmScheduleRetrySessionSuccess
0x14000c174  mov     dword ptr [rsp+0C0h+var_90], ebx
0x14000c178  mov     r9, rsi
0x14000c17b  mov     [rsp+0C0h+var_98], r15
0x14000c180  mov     r8, r14
0x14000c183  mov     [rsp+0C0h+var_A0], rdi
0x14000c188  call    McTemplateU0zzzzd_EventWriteTransfer
0x14000c18d  add     rsp, 98h
0x14000c194  pop     r15
0x14000c196  pop     r14
0x14000c198  pop     rdi
0x14000c199  pop     rsi
0x14000c19a  pop     rbx
0x14000c19b  pop     rbp
0x14000c19c  retn
```
