# COmaDmPrcLogger::LogOmaDmPrcSessionComplete(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,long,long)

- ea: `0x14000c1a4`
- end: `0x14000c320`
- name: `?LogOmaDmPrcSessionComplete@COmaDmPrcLogger@@QEAAXPEBG000KKKJJ@Z`
- size: `380`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013ae0`

## callees

- `0x140001134`
- `0x14000c1a4`
- `0x14000d4e8`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcSessionComplete(
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
      (unsigned __int8 *)&dword_14001E11C,
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
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionComplete,
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
0x14000c1a4  push    rbp
0x14000c1a6  push    rbx
0x14000c1a7  push    rsi
0x14000c1a8  push    rdi
0x14000c1a9  push    r12
0x14000c1ab  push    r13
0x14000c1ad  push    r14
0x14000c1af  push    r15
0x14000c1b1  lea     rbp, [rsp-7]
0x14000c1b6  sub     rsp, 0D8h
0x14000c1bd  mov     eax, cs:dword_140023000
0x14000c1c3  mov     rbx, r9
0x14000c1c6  mov     r14d, [rbp+3Fh+arg_48]
0x14000c1cd  mov     rdi, r8
0x14000c1d0  mov     r15d, [rbp+3Fh+arg_40]
0x14000c1d7  mov     rsi, rdx
0x14000c1da  mov     r12d, [rbp+3Fh+arg_38]
0x14000c1e1  mov     r13d, [rbp+3Fh+arg_30]
0x14000c1e5  cmp     eax, 5
0x14000c1e8  jbe     loc_14000C2C7
0x14000c1ee  mov     r8, cs:qword_140023018
0x14000c1f5  mov     rdx, 400000000000h
0x14000c1ff  mov     rax, cs:qword_140023010
0x14000c206  test    rdx, rax
0x14000c209  jz      loc_14000C2C7
0x14000c20f  mov     rax, r8
0x14000c212  and     rax, rdx
0x14000c215  cmp     rax, r8
0x14000c218  jnz     loc_14000C2C7
0x14000c21e  lea     rax, [rcx+10h]
0x14000c222  mov     [rbp+3Fh+var_90], r14d
0x14000c226  mov     [rbp+3Fh+var_78], rax
0x14000c22a  lea     rdx, dword_14001E11C
0x14000c231  mov     eax, [rbp+3Fh+arg_28]
0x14000c234  mov     [rbp+3Fh+var_80], eax
0x14000c237  mov     rax, [rbp+3Fh+arg_20]
0x14000c23b  mov     [rbp+3Fh+var_70], rax
0x14000c23f  lea     rax, [rbp+3Fh+var_78]
0x14000c243  mov     [rsp+110h+var_A0], rax
0x14000c248  lea     rax, [rbp+3Fh+var_90]
0x14000c24c  mov     [rsp+110h+var_A8], rax
0x14000c251  lea     rax, [rbp+3Fh+var_8C]
0x14000c255  mov     [rsp+110h+var_B0], rax
0x14000c25a  lea     rax, [rbp+3Fh+var_88]
0x14000c25e  mov     [rsp+110h+var_B8], rax
0x14000c263  lea     rax, [rbp+3Fh+var_84]
0x14000c267  mov     [rsp+110h+var_C0], rax
0x14000c26c  lea     rax, [rbp+3Fh+var_80]
0x14000c270  mov     [rsp+110h+var_C8], rax
0x14000c275  lea     rax, [rbp+3Fh+var_70]
0x14000c279  mov     [rsp+110h+var_D0], rax
0x14000c27e  lea     rax, [rbp+3Fh+var_68]
0x14000c282  mov     [rsp+110h+var_D8], rax
0x14000c287  lea     rax, [rbp+3Fh+var_60]
0x14000c28b  mov     [rsp+110h+var_E0], rax
0x14000c290  lea     rax, [rbp+3Fh+var_58]
0x14000c294  mov     [rsp+110h+var_E8], rax
0x14000c299  lea     rax, [rbp+3Fh+var_50]
0x14000c29d  mov     [rsp+110h+var_F0], rax
0x14000c2a2  mov     [rbp+3Fh+var_8C], r15d
0x14000c2a6  mov     [rbp+3Fh+var_88], r12d
0x14000c2aa  mov     [rbp+3Fh+var_84], r13d
0x14000c2ae  mov     [rbp+3Fh+var_68], rbx
0x14000c2b2  mov     [rbp+3Fh+var_60], rdi
0x14000c2b6  mov     [rbp+3Fh+var_58], rsi
0x14000c2ba  mov     [rbp+3Fh+var_50], 2000000h
0x14000c2c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$03@@5555AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000c2c7  test    cs:byte_1400242C1, 4
0x14000c2ce  jz      short loc_14000C30B
0x14000c2d0  mov     eax, [rbp+3Fh+arg_28]
0x14000c2d3  lea     rdx, EnterpriseDiagnosticsOmaDmSessionComplete
0x14000c2da  mov     dword ptr [rsp+110h+var_C0], r14d
0x14000c2df  mov     r9, rdi
0x14000c2e2  mov     dword ptr [rsp+110h+var_C8], r15d
0x14000c2e7  mov     r8, rsi
0x14000c2ea  mov     dword ptr [rsp+110h+var_D0], r12d
0x14000c2ef  mov     dword ptr [rsp+110h+var_D8], r13d
0x14000c2f4  mov     dword ptr [rsp+110h+var_E0], eax
0x14000c2f8  mov     rax, [rbp+3Fh+arg_20]
0x14000c2fc  mov     [rsp+110h+var_E8], rax
0x14000c301  mov     [rsp+110h+var_F0], rbx
0x14000c306  call    McTemplateU0zzzzqqqdd_EventWriteTransfer
0x14000c30b  add     rsp, 0D8h
0x14000c312  pop     r15
0x14000c314  pop     r14
0x14000c316  pop     r13
0x14000c318  pop     r12
0x14000c31a  pop     rdi
0x14000c31b  pop     rsi
0x14000c31c  pop     rbx
0x14000c31d  pop     rbp
0x14000c31e  retn
```
