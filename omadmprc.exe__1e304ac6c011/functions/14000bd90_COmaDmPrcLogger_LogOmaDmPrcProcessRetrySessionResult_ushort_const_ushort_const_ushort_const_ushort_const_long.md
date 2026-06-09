# COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)

- ea: `0x14000bd90`
- end: `0x14000beb1`
- name: `?LogOmaDmPrcProcessRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z`
- size: `289`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000efe4`
- `0x14000fff0`

## callees

- `0x140001314`
- `0x14000bd90`
- `0x14000d238`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(
        COmaDmPrcLogger *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int a6)
{
  int v6; // ebx
  int v7; // edi
  const unsigned __int16 *v8; // r14
  int v9; // esi
  __int64 *v10; // rdx
  __int64 *v11; // [rsp+68h] [rbp-19h] BYREF
  const unsigned __int16 *v12; // [rsp+70h] [rbp-11h] BYREF
  __int64 *v13; // [rsp+78h] [rbp-9h] BYREF
  __int64 *v14; // [rsp+80h] [rbp-1h] BYREF
  __int64 v15[8]; // [rsp+88h] [rbp+7h] BYREF
  const unsigned __int16 *v16; // [rsp+F0h] [rbp+6Fh] BYREF

  v16 = a4;
  v6 = a6;
  v7 = (int)a3;
  v8 = a5;
  v9 = (int)a2;
  if ( (unsigned int)dword_140023000 > 5
    && (qword_140023010 & 0x400000000000LL) != 0
    && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
  {
    v16 = (const unsigned __int16 *)((char *)this + 16);
    v11 = (__int64 *)a5;
    v12 = L"HandleMessage";
    v13 = (__int64 *)a3;
    v14 = (__int64 *)a2;
    v15[0] = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)this,
      (unsigned __int8 *)byte_14001E093,
      0x400000000000LL,
      (__int64)a4,
      (__int64)v15,
      &v14,
      &v13,
      (__int64 **)&v12,
      &v11,
      (__int64)&a6,
      &v16);
  }
  if ( v6 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) == 0 )
      return;
    v10 = EnterpriseDiagnosticsOmaDmProcessRetrySessionSuccess;
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x20) == 0 )
      return;
    v10 = EnterpriseDiagnosticsOmaDmProcessRetrySessionFailure;
  }
  McTemplateU0zzzzd_EventWriteTransfer((_DWORD)this, (_DWORD)v10, v9, v7, (__int64)L"HandleMessage", (__int64)v8, v6);
}

```

## disassembly

```asm
0x14000bd90  mov     r11, rsp
0x14000bd93  mov     [r11+20h], r9
0x14000bd97  push    rbp
0x14000bd98  push    rbx
0x14000bd99  push    rsi
0x14000bd9a  push    rdi
0x14000bd9b  push    r14
0x14000bd9d  push    r15
0x14000bd9f  lea     rbp, [r11-4Fh]
0x14000bda3  sub     rsp, 98h
0x14000bdaa  mov     eax, cs:dword_140023000
0x14000bdb0  lea     r15, aHandlemessage; "HandleMessage"
0x14000bdb7  mov     ebx, [rbp+47h+arg_28]
0x14000bdba  mov     rdi, r8
0x14000bdbd  mov     r14, [rbp+47h+arg_20]
0x14000bdc1  mov     rsi, rdx
0x14000bdc4  cmp     eax, 5
0x14000bdc7  jbe     loc_14000BE61
0x14000bdcd  mov     rdx, cs:qword_140023018
0x14000bdd4  mov     r8, 400000000000h
0x14000bdde  mov     rax, cs:qword_140023010
0x14000bde5  test    r8, rax
0x14000bde8  jz      short loc_14000BE61
0x14000bdea  mov     rax, rdx
0x14000bded  and     rax, r8
0x14000bdf0  cmp     rax, rdx
0x14000bdf3  jnz     short loc_14000BE61
0x14000bdf5  lea     rax, [rcx+10h]
0x14000bdf9  mov     [rbp+47h+arg_28], ebx
0x14000bdfc  mov     [rbp+47h+arg_18], rax
0x14000be00  lea     rdx, byte_14001E093
0x14000be07  lea     rax, [rbp+47h+arg_18]
0x14000be0b  mov     [rbp+47h+var_60], r14
0x14000be0f  mov     [r11-78h], rax
0x14000be13  lea     rax, [rbp+47h+arg_28]
0x14000be17  mov     [r11-80h], rax
0x14000be1b  lea     rax, [rbp+47h+var_60]
0x14000be1f  mov     [rsp+40h], rax
0x14000be24  lea     rax, [rbp+47h+var_58]
0x14000be28  mov     [rsp+0C0h+var_88], rax
0x14000be2d  lea     rax, [rbp+47h+var_50]
0x14000be31  mov     [rsp+0C0h+var_90], rax
0x14000be36  lea     rax, [rbp+47h+var_48]
0x14000be3a  mov     [rsp+0C0h+var_98], rax
0x14000be3f  lea     rax, [rbp+47h+var_40]
0x14000be43  mov     [rsp+0C0h+var_A0], rax
0x14000be48  mov     [rbp+47h+var_58], r15
0x14000be4c  mov     [rbp+47h+var_50], rdi
0x14000be50  mov     [rbp+47h+var_48], rsi
0x14000be54  mov     [rbp+47h+var_40], 2000000h
0x14000be5c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000be61  test    ebx, ebx
0x14000be63  jns     short loc_14000BE77
0x14000be65  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 20h
0x14000be6c  jz      short loc_14000BEA0
0x14000be6e  lea     rdx, EnterpriseDiagnosticsOmaDmProcessRetrySessionFailure
0x14000be75  jmp     short loc_14000BE87
0x14000be77  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000be7e  jz      short loc_14000BEA0
0x14000be80  lea     rdx, EnterpriseDiagnosticsOmaDmProcessRetrySessionSuccess
0x14000be87  mov     dword ptr [rsp+0C0h+var_90], ebx
0x14000be8b  mov     r9, rdi
0x14000be8e  mov     [rsp+0C0h+var_98], r14
0x14000be93  mov     r8, rsi
0x14000be96  mov     [rsp+0C0h+var_A0], r15
0x14000be9b  call    McTemplateU0zzzzd_EventWriteTransfer
0x14000bea0  add     rsp, 98h
0x14000bea7  pop     r15
0x14000bea9  pop     r14
0x14000beab  pop     rdi
0x14000beac  pop     rsi
0x14000bead  pop     rbx
0x14000beae  pop     rbp
0x14000beaf  retn
```
