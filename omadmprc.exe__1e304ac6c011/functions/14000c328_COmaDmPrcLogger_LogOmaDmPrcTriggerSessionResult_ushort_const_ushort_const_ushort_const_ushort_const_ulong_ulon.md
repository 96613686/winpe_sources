# COmaDmPrcLogger::LogOmaDmPrcTriggerSessionResult(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,long,long)

- ea: `0x14000c328`
- end: `0x14000c4a4`
- name: `?LogOmaDmPrcTriggerSessionResult@COmaDmPrcLogger@@QEAAXPEBG000KKKJJ@Z`
- size: `380`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400128d4`

## callees

- `0x140001134`
- `0x14000c328`
- `0x14000d4e8`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcTriggerSessionResult(
        COmaDmPrcLogger *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9,
        int a10)
{
  int v13; // [rsp+80h] [rbp-51h] BYREF
  int v14; // [rsp+84h] [rbp-4Dh] BYREF
  unsigned int v15; // [rsp+88h] [rbp-49h] BYREF
  unsigned int v16; // [rsp+8Ch] [rbp-45h] BYREF
  unsigned int v17; // [rsp+90h] [rbp-41h] BYREF
  const unsigned __int16 *v18; // [rsp+98h] [rbp-39h] BYREF
  __int64 *v19; // [rsp+A0h] [rbp-31h] BYREF
  __int64 *v20; // [rsp+A8h] [rbp-29h] BYREF
  __int64 *v21; // [rsp+B0h] [rbp-21h] BYREF
  __int64 *v22; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v23[10]; // [rsp+C0h] [rbp-11h] BYREF

  if ( (unsigned int)dword_140023000 > 5
    && (qword_140023010 & 0x400000000000LL) != 0
    && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
  {
    v13 = a10;
    v18 = (const unsigned __int16 *)((char *)this + 16);
    v17 = a6;
    v19 = (__int64 *)a5;
    v14 = a9;
    v15 = a8;
    v16 = a7;
    v20 = (__int64 *)a4;
    v21 = (__int64 *)a3;
    v22 = (__int64 *)a2;
    v23[0] = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)this,
      (unsigned __int8 *)byte_14001DE55,
      qword_140023018,
      (__int64)a4,
      (__int64)v23,
      &v22,
      &v21,
      &v20,
      &v19,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      &v18);
  }
  if ( (byte_1400242C1 & 4) != 0 )
    McTemplateU0zzzzqqqdd_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionTriggered,
      a2,
      a3,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9,
      a10);
}

```

## disassembly

```asm
0x14000c328  push    rbp
0x14000c32a  push    rbx
0x14000c32b  push    rsi
0x14000c32c  push    rdi
0x14000c32d  push    r12
0x14000c32f  push    r13
0x14000c331  push    r14
0x14000c333  push    r15
0x14000c335  lea     rbp, [rsp-7]
0x14000c33a  sub     rsp, 0D8h
0x14000c341  mov     eax, cs:dword_140023000
0x14000c347  mov     rbx, r9
0x14000c34a  mov     r14d, [rbp+3Fh+arg_48]
0x14000c351  mov     rdi, r8
0x14000c354  mov     r15d, [rbp+3Fh+arg_40]
0x14000c35b  mov     rsi, rdx
0x14000c35e  mov     r12d, [rbp+3Fh+arg_38]
0x14000c365  mov     r13d, [rbp+3Fh+arg_30]
0x14000c369  cmp     eax, 5
0x14000c36c  jbe     loc_14000C44B
0x14000c372  mov     r8, cs:qword_140023018
0x14000c379  mov     rdx, 400000000000h
0x14000c383  mov     rax, cs:qword_140023010
0x14000c38a  test    rdx, rax
0x14000c38d  jz      loc_14000C44B
0x14000c393  mov     rax, r8
0x14000c396  and     rax, rdx
0x14000c399  cmp     rax, r8
0x14000c39c  jnz     loc_14000C44B
0x14000c3a2  lea     rax, [rcx+10h]
0x14000c3a6  mov     [rbp+3Fh+var_90], r14d
0x14000c3aa  mov     [rbp+3Fh+var_78], rax
0x14000c3ae  lea     rdx, byte_14001DE55
0x14000c3b5  mov     eax, [rbp+3Fh+arg_28]
0x14000c3b8  mov     [rbp+3Fh+var_80], eax
0x14000c3bb  mov     rax, [rbp+3Fh+arg_20]
0x14000c3bf  mov     [rbp+3Fh+var_70], rax
0x14000c3c3  lea     rax, [rbp+3Fh+var_78]
0x14000c3c7  mov     [rsp+110h+var_A0], rax
0x14000c3cc  lea     rax, [rbp+3Fh+var_90]
0x14000c3d0  mov     [rsp+110h+var_A8], rax
0x14000c3d5  lea     rax, [rbp+3Fh+var_8C]
0x14000c3d9  mov     [rsp+110h+var_B0], rax
0x14000c3de  lea     rax, [rbp+3Fh+var_88]
0x14000c3e2  mov     [rsp+110h+var_B8], rax
0x14000c3e7  lea     rax, [rbp+3Fh+var_84]
0x14000c3eb  mov     [rsp+110h+var_C0], rax
0x14000c3f0  lea     rax, [rbp+3Fh+var_80]
0x14000c3f4  mov     [rsp+110h+var_C8], rax
0x14000c3f9  lea     rax, [rbp+3Fh+var_70]
0x14000c3fd  mov     [rsp+110h+var_D0], rax
0x14000c402  lea     rax, [rbp+3Fh+var_68]
0x14000c406  mov     [rsp+110h+var_D8], rax
0x14000c40b  lea     rax, [rbp+3Fh+var_60]
0x14000c40f  mov     [rsp+110h+var_E0], rax
0x14000c414  lea     rax, [rbp+3Fh+var_58]
0x14000c418  mov     [rsp+110h+var_E8], rax
0x14000c41d  lea     rax, [rbp+3Fh+var_50]
0x14000c421  mov     [rsp+110h+var_F0], rax
0x14000c426  mov     [rbp+3Fh+var_8C], r15d
0x14000c42a  mov     [rbp+3Fh+var_88], r12d
0x14000c42e  mov     [rbp+3Fh+var_84], r13d
0x14000c432  mov     [rbp+3Fh+var_68], rbx
0x14000c436  mov     [rbp+3Fh+var_60], rdi
0x14000c43a  mov     [rbp+3Fh+var_58], rsi
0x14000c43e  mov     [rbp+3Fh+var_50], 2000000h
0x14000c446  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$03@@5555AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000c44b  test    cs:byte_1400242C1, 4
0x14000c452  jz      short loc_14000C48F
0x14000c454  mov     eax, [rbp+3Fh+arg_28]
0x14000c457  lea     rdx, EnterpriseDiagnosticsOmaDmSessionTriggered
0x14000c45e  mov     dword ptr [rsp+110h+var_C0], r14d
0x14000c463  mov     r9, rdi
0x14000c466  mov     dword ptr [rsp+110h+var_C8], r15d
0x14000c46b  mov     r8, rsi
0x14000c46e  mov     dword ptr [rsp+110h+var_D0], r12d
0x14000c473  mov     dword ptr [rsp+110h+var_D8], r13d
0x14000c478  mov     dword ptr [rsp+110h+var_E0], eax
0x14000c47c  mov     rax, [rbp+3Fh+arg_20]
0x14000c480  mov     [rsp+110h+var_E8], rax
0x14000c485  mov     [rsp+110h+var_F0], rbx
0x14000c48a  call    McTemplateU0zzzzqqqdd_EventWriteTransfer
0x14000c48f  add     rsp, 0D8h
0x14000c496  pop     r15
0x14000c498  pop     r14
0x14000c49a  pop     r13
0x14000c49c  pop     r12
0x14000c49e  pop     rdi
0x14000c49f  pop     rsi
0x14000c4a0  pop     rbx
0x14000c4a1  pop     rbp
0x14000c4a2  retn
```
