# COmaDmLogger::LogOmaDmApiInitiateSession(ushort const *,ulong,ushort const *,ulong,ulong,int,ulong,ushort const *,ushort const *,int,int,ushort const *,int,long)

- ea: `0x180021a20`
- end: `0x180021c18`
- name: `?LogOmaDmApiInitiateSession@COmaDmLogger@@QEAAXPEBGK0KKHK00HH0HJ@Z`
- size: `504`
- prototype: `void __fastcall(COmaDmLogger *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int, int, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019684`

## callees

- `0x1800014a0`
- `0x180021a20`
- `0x180021cb8`

## pseudocode

```c
void __fastcall COmaDmLogger::LogOmaDmApiInitiateSession(
        COmaDmLogger *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        int a11,
        int a12,
        const unsigned __int16 *a13,
        int a14,
        int a15)
{
  COmaDmLogger *v17; // rdx
  bool v18; // [rsp+A8h] [rbp-80h] BYREF
  bool v19; // [rsp+A9h] [rbp-7Fh] BYREF
  bool v20[2]; // [rsp+AAh] [rbp-7Eh] BYREF
  unsigned int v21; // [rsp+ACh] [rbp-7Ch] BYREF
  int v22; // [rsp+B0h] [rbp-78h] BYREF
  unsigned int v23; // [rsp+B4h] [rbp-74h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp-70h] BYREF
  int v25; // [rsp+BCh] [rbp-6Ch] BYREF
  int v26; // [rsp+C0h] [rbp-68h] BYREF
  const unsigned __int16 *v27; // [rsp+C8h] [rbp-60h] BYREF
  __int64 *v28; // [rsp+D0h] [rbp-58h] BYREF
  __int64 *v29; // [rsp+D8h] [rbp-50h] BYREF
  __int64 *v30; // [rsp+E0h] [rbp-48h] BYREF
  __int64 *v31; // [rsp+E8h] [rbp-40h] BYREF
  __int64 *v32; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v33[10]; // [rsp+F8h] [rbp-30h] BYREF

  v17 = this;
  if ( (unsigned int)dword_1800320D0 > 5 )
  {
    this = (COmaDmLogger *)qword_1800320E8;
    if ( (qword_1800320E0 & 0x400000000000LL) != 0 && (qword_1800320E8 & 0x400000000000LL) == qword_1800320E8 )
    {
      v28 = (__int64 *)a13;
      v27 = (const unsigned __int16 *)((char *)v17 + 16);
      v29 = (__int64 *)a10;
      v18 = a14 > 0;
      v30 = (__int64 *)a9;
      v21 = a8;
      v19 = a12 > 0;
      v22 = a7;
      v20[0] = a11 > 0;
      v23 = a6;
      v24 = a5;
      v31 = (__int64 *)a4;
      v25 = a3;
      v32 = (__int64 *)a2;
      v26 = a15;
      v33[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(
        qword_1800320E8,
        (unsigned __int8 *)word_18002B372,
        a3,
        0x400000000000LL,
        (__int64)v33,
        (__int64)&v26,
        &v32,
        (__int64)&v25,
        &v31,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        &v30,
        &v29,
        (__int64)v20,
        (__int64)&v19,
        &v28,
        (__int64)&v18,
        &v27);
    }
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
    McTemplateU0dzzqqtqzzttzt_EventWriteTransfer(
      (__int64)this,
      (__int64)v17,
      a15,
      a2,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9,
      a10,
      a11,
      a12,
      a13,
      a14);
}

```

## disassembly

```asm
0x180021a20  mov     r11, rsp
0x180021a23  push    rbp
0x180021a24  push    rbx
0x180021a25  push    rsi
0x180021a26  push    rdi
0x180021a27  push    r12
0x180021a29  push    r13
0x180021a2b  push    r14
0x180021a2d  push    r15
0x180021a2f  lea     rbp, [r11-28h]
0x180021a33  sub     rsp, 108h
0x180021a3a  mov     eax, cs:dword_1800320D0
0x180021a40  mov     rdi, rdx
0x180021a43  mov     esi, [rbp+20h+arg_70]
0x180021a49  mov     rbx, r9
0x180021a4c  mov     r14d, [rbp+20h+arg_68]
0x180021a53  mov     rdx, rcx
0x180021a56  mov     r15, [rbp+20h+arg_60]
0x180021a5d  mov     r12d, [rbp+20h+arg_58]
0x180021a64  mov     r13d, [rbp+20h+arg_50]
0x180021a6b  cmp     eax, 5
0x180021a6e  jbe     loc_180021BA8
0x180021a74  mov     rcx, cs:qword_1800320E8
0x180021a7b  mov     r9, 400000000000h
0x180021a85  mov     rax, cs:qword_1800320E0
0x180021a8c  test    r9, rax
0x180021a8f  jz      loc_180021BA8
0x180021a95  mov     rax, rcx
0x180021a98  and     rax, r9
0x180021a9b  cmp     rax, rcx
0x180021a9e  jnz     loc_180021BA8
0x180021aa4  lea     rax, [rdx+10h]
0x180021aa8  mov     [rbp+20h+var_78], r15
0x180021aac  mov     [rbp+20h+var_80], rax
0x180021ab0  lea     rdx, word_18002B372
0x180021ab7  mov     rax, [rbp+20h+arg_48]
0x180021abb  test    r14d, r14d
0x180021abe  mov     [rbp+20h+var_70], rax
0x180021ac2  mov     rax, [rbp+20h+arg_40]
0x180021ac6  setnle  [rbp+20h+var_A0]
0x180021aca  mov     [rbp+20h+var_68], rax
0x180021ace  test    r12d, r12d
0x180021ad1  mov     eax, [rbp+20h+arg_38]
0x180021ad4  mov     [rbp+20h+var_9C], eax
0x180021ad7  setnle  [rbp+20h+var_9F]
0x180021adb  mov     eax, [rbp+20h+arg_30]
0x180021ade  test    r13d, r13d
0x180021ae1  mov     [rbp+20h+var_98], eax
0x180021ae4  mov     eax, [rbp+20h+arg_28]
0x180021ae7  setnle  [rbp+20h+var_9E]
0x180021aeb  mov     [rbp+20h+var_94], eax
0x180021aee  mov     eax, [rbp+20h+arg_20]
0x180021af1  mov     [rbp+20h+var_90], eax
0x180021af4  lea     rax, [rbp+20h+var_80]
0x180021af8  mov     [r11-0B0h], rax
0x180021aff  lea     rax, [rbp+20h+var_A0]
0x180021b03  mov     [r11-0B8h], rax
0x180021b0a  lea     rax, [rbp+20h+var_78]
0x180021b0e  mov     [r11-0C0h], rax
0x180021b15  lea     rax, [rbp+20h+var_9F]
0x180021b19  mov     [r11-0C8h], rax
0x180021b20  lea     rax, [rbp+20h+var_9E]
0x180021b24  mov     [rsp+78h], rax
0x180021b29  lea     rax, [rbp+20h+var_70]
0x180021b2d  mov     [rsp+140h+var_D0], rax
0x180021b32  lea     rax, [rbp+20h+var_68]
0x180021b36  mov     [rsp+140h+var_D8], rax
0x180021b3b  lea     rax, [rbp+20h+var_9C]
0x180021b3f  mov     [rsp+140h+var_E0], rax
0x180021b44  lea     rax, [rbp+20h+var_98]
0x180021b48  mov     [rsp+140h+var_E8], rax
0x180021b4d  lea     rax, [rbp+20h+var_94]
0x180021b51  mov     [rsp+140h+var_F0], rax
0x180021b56  lea     rax, [rbp+20h+var_90]
0x180021b5a  mov     [rsp+140h+var_F8], rax
0x180021b5f  lea     rax, [rbp+20h+var_60]
0x180021b63  mov     [rsp+140h+var_100], rax
0x180021b68  lea     rax, [rbp+20h+var_8C]
0x180021b6c  mov     [rsp+140h+var_108], rax
0x180021b71  lea     rax, [rbp+20h+var_58]
0x180021b75  mov     [rsp+140h+var_110], rax
0x180021b7a  lea     rax, [rbp+20h+var_88]
0x180021b7e  mov     [rsp+140h+var_118], rax
0x180021b83  lea     rax, [rbp+20h+var_50]
0x180021b87  mov     [rsp+140h+var_120], rax
0x180021b8c  mov     [rbp+20h+var_60], rbx
0x180021b90  mov     [rbp+20h+var_8C], r8d
0x180021b94  mov     [rbp+20h+var_58], rdi
0x180021b98  mov     [rbp+20h+var_88], esi
0x180021b9b  mov     [rbp+20h+var_50], 2000000h
0x180021ba3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U3@U2@U2@U2@U2@U3@U3@U?$_tlgWrapperByVal@$00@@U4@U3@U4@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@45444455AEBU?$_tlgWrapperByVal@$00@@656AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &)
0x180021ba8  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x180021baf  jz      short loc_180021C03
0x180021bb1  mov     rax, [rbp+20h+arg_48]
0x180021bb5  mov     r9, rdi
0x180021bb8  mov     dword ptr [rsp+140h+var_D0], r14d
0x180021bbd  mov     r8d, esi
0x180021bc0  mov     [rsp+140h+var_D8], r15
0x180021bc5  mov     dword ptr [rsp+140h+var_E0], r12d
0x180021bca  mov     dword ptr [rsp+140h+var_E8], r13d
0x180021bcf  mov     [rsp+140h+var_F0], rax
0x180021bd4  mov     rax, [rbp+20h+arg_40]
0x180021bd8  mov     [rsp+140h+var_F8], rax
0x180021bdd  mov     eax, [rbp+20h+arg_38]
0x180021be0  mov     dword ptr [rsp+140h+var_100], eax
0x180021be4  mov     eax, [rbp+20h+arg_30]
0x180021be7  mov     dword ptr [rsp+140h+var_108], eax
0x180021beb  mov     eax, [rbp+20h+arg_28]
0x180021bee  mov     dword ptr [rsp+140h+var_110], eax
0x180021bf2  mov     eax, [rbp+20h+arg_20]
0x180021bf5  mov     dword ptr [rsp+140h+var_118], eax
0x180021bf9  mov     [rsp+140h+var_120], rbx
0x180021bfe  call    McTemplateU0dzzqqtqzzttzt_EventWriteTransfer
0x180021c03  add     rsp, 108h
0x180021c0a  pop     r15
0x180021c0c  pop     r14
0x180021c0e  pop     r13
0x180021c10  pop     r12
0x180021c12  pop     rdi
0x180021c13  pop     rsi
0x180021c14  pop     rbx
0x180021c15  pop     rbp
0x180021c16  retn
```
