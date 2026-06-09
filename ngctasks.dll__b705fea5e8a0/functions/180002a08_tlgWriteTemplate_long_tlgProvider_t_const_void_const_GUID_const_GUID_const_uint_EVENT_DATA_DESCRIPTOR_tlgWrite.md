# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002a08`
- end: `0x180002e68`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U1@U1@U1@U1@U1@U1@U1@U1@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@43333333344444444444344AEBU?$_tlgWrapperByVal@$07@@534@Z`
- size: `1120`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013310`

## callees

- `0x1800024a8`
- `0x180002a08`
- `0x180006330`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14,
        _QWORD *a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        _QWORD *a27,
        __int64 a28,
        __int64 a29,
        __int64 a30,
        __int64 a31,
        _QWORD *a32)
{
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax

  v32 = -1;
  if ( *a32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)(*a32 + 2 * v33) );
  }
  if ( *a27 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(*a27 + 2 * v34) );
  }
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *(_WORD *)(*a15 + 2 * v35) );
  }
  if ( *a14 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *(_WORD *)(*a14 + 2 * v36) );
  }
  if ( *a13 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)(*a13 + 2 * v37) );
  }
  if ( *a12 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *(_WORD *)(*a12 + 2 * v38) );
  }
  if ( *a11 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)(*a11 + 2 * v39) );
  }
  if ( *a10 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)(*a10 + 2 * v40) );
  }
  if ( *a9 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)(*a9 + 2 * v41) );
  }
  if ( *a8 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *(_WORD *)(*a8 + 2 * v42) );
  }
  if ( *a5 )
  {
    do
      ++v32;
    while ( *(_WORD *)(*a5 + 2 * v32) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180031038, a2);
}

```

## disassembly

```asm
0x180002a08  mov     [rsp-8+arg_0], rbx
0x180002a0d  push    rbp
0x180002a0e  lea     rbp, [rsp-130h]
0x180002a16  sub     rsp, 230h
0x180002a1d  mov     rax, cs:__security_cookie
0x180002a24  xor     rax, rsp
0x180002a27  mov     [rbp+130h+var_10], rax
0x180002a2e  mov     rax, [rbp+130h+arg_100]
0x180002a35  lea     r11, qword_180024840
0x180002a3c  xor     r9d, r9d
0x180002a3f  mov     [rbp+130h+var_20], rax
0x180002a46  mov     rax, [rbp+130h+arg_F8]
0x180002a4d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002a51  mov     r10, rdx
0x180002a54  mov     [rbp+130h+var_18], 4
0x180002a5f  lea     edx, [r9+2]
0x180002a63  mov     r8, [rax]
0x180002a66  test    r8, r8
0x180002a69  jz      short loc_180002A81
0x180002a6b  mov     rax, rcx
0x180002a6e  inc     rax
0x180002a71  cmp     [r8+rax*2], r9w
0x180002a76  jnz     short loc_180002A6E
0x180002a78  lea     eax, ds:2[rax*2]
0x180002a7f  jmp     short loc_180002A86
0x180002a81  mov     r8, r11
0x180002a84  mov     eax, edx
0x180002a86  mov     [rbp+130h+var_28], eax
0x180002a8c  mov     rax, [rbp+130h+arg_F0]
0x180002a93  mov     [rbp+130h+var_40], rax
0x180002a9a  mov     rax, [rbp+130h+arg_E8]
0x180002aa1  mov     [rbp+130h+var_50], rax
0x180002aa8  mov     rax, [rbp+130h+arg_E0]
0x180002aaf  mov     [rbp+130h+var_60], rax
0x180002ab6  mov     rax, [rbp+130h+arg_D8]
0x180002abd  mov     [rbp+130h+var_70], rax
0x180002ac4  mov     rax, [rbp+130h+arg_D0]
0x180002acb  mov     [rbp+130h+var_30], r8
0x180002ad2  mov     [rbp+130h+var_24], r9d
0x180002ad9  mov     [rbp+130h+var_38], 8
0x180002ae4  mov     r8, [rax]
0x180002ae7  mov     [rbp+130h+var_48], 8
0x180002af2  mov     [rbp+130h+var_58], 4
0x180002afd  mov     [rbp+130h+var_68], 4
0x180002b08  test    r8, r8
0x180002b0b  jz      short loc_180002B23
0x180002b0d  mov     rax, rcx
0x180002b10  inc     rax
0x180002b13  cmp     [r8+rax*2], r9w
0x180002b18  jnz     short loc_180002B10
0x180002b1a  lea     eax, ds:2[rax*2]
0x180002b21  jmp     short loc_180002B28
0x180002b23  mov     r8, r11
0x180002b26  mov     eax, edx
0x180002b28  mov     [rbp+130h+var_78], eax
0x180002b2e  mov     rax, [rbp+130h+arg_C8]
0x180002b35  mov     [rbp+130h+var_90], rax
0x180002b3c  mov     rax, [rbp+130h+arg_C0]
0x180002b43  mov     [rbp+130h+var_A0], rax
0x180002b4a  mov     rax, [rbp+130h+arg_B8]
0x180002b51  mov     [rbp+130h+var_B0], rax
0x180002b58  mov     rax, [rbp+130h+arg_B0]
0x180002b5f  mov     [rbp+130h+var_C0], rax
0x180002b63  mov     rax, [rbp+130h+arg_A8]
0x180002b6a  mov     [rbp+130h+var_D0], rax
0x180002b6e  mov     rax, [rbp+130h+arg_A0]
0x180002b75  mov     [rbp+130h+var_E0], rax
0x180002b79  mov     rax, [rbp+130h+arg_98]
0x180002b80  mov     [rbp+130h+var_F0], rax
0x180002b84  mov     rax, [rbp+130h+arg_90]
0x180002b8b  mov     [rbp+130h+var_100], rax
0x180002b8f  mov     rax, [rbp+130h+arg_88]
0x180002b96  mov     [rbp+130h+var_110], rax
0x180002b9a  mov     rax, [rbp+130h+arg_80]
0x180002ba1  mov     [rbp+130h+var_120], rax
0x180002ba5  mov     rax, [rbp+130h+arg_78]
0x180002bac  mov     [rbp+130h+var_130], rax
0x180002bb0  mov     rax, [rbp+130h+arg_70]
0x180002bb7  mov     [rbp+130h+var_80], r8
0x180002bbe  mov     [rbp+130h+var_74], r9d
0x180002bc5  mov     [rbp+130h+var_88], 4
0x180002bd0  mov     r8, [rax]
0x180002bd3  mov     [rbp+130h+var_98], 4
0x180002bde  mov     [rbp+130h+var_A8], 4
0x180002be9  mov     [rbp+130h+var_B8], 4
0x180002bf1  mov     [rbp+130h+var_C8], 4
0x180002bf9  mov     [rbp+130h+var_D8], 4
0x180002c01  mov     [rbp+130h+var_E8], 4
0x180002c09  mov     [rbp+130h+var_F8], 4
0x180002c11  mov     [rbp+130h+var_108], 4
0x180002c19  mov     [rbp+130h+var_118], 4
0x180002c21  mov     [rbp+130h+var_128], 4
0x180002c29  test    r8, r8
0x180002c2c  jz      short loc_180002C44
0x180002c2e  mov     rax, rcx
0x180002c31  inc     rax
0x180002c34  cmp     [r8+rax*2], r9w
0x180002c39  jnz     short loc_180002C31
0x180002c3b  lea     eax, ds:2[rax*2]
0x180002c42  jmp     short loc_180002C49
0x180002c44  mov     r8, r11
0x180002c47  mov     eax, edx
0x180002c49  mov     [rbp+130h+var_138], eax
0x180002c4c  mov     rax, [rbp+130h+arg_68]
0x180002c53  mov     [rbp+130h+var_140], r8
0x180002c57  mov     [rbp+130h+var_134], r9d
0x180002c5b  mov     r8, [rax]
0x180002c5e  test    r8, r8
0x180002c61  jz      short loc_180002C79
0x180002c63  mov     rax, rcx
0x180002c66  inc     rax
0x180002c69  cmp     [r8+rax*2], r9w
0x180002c6e  jnz     short loc_180002C66
0x180002c70  lea     eax, ds:2[rax*2]
0x180002c77  jmp     short loc_180002C7E
0x180002c79  mov     r8, r11
0x180002c7c  mov     eax, edx
0x180002c7e  mov     [rbp+130h+var_148], eax
0x180002c81  mov     rax, [rbp+130h+arg_60]
0x180002c88  mov     [rbp+130h+var_150], r8
0x180002c8c  mov     [rbp+130h+var_144], r9d
0x180002c90  mov     r8, [rax]
0x180002c93  test    r8, r8
0x180002c96  jz      short loc_180002CAE
0x180002c98  mov     rax, rcx
0x180002c9b  inc     rax
0x180002c9e  cmp     [r8+rax*2], r9w
0x180002ca3  jnz     short loc_180002C9B
0x180002ca5  lea     eax, ds:2[rax*2]
0x180002cac  jmp     short loc_180002CB3
0x180002cae  mov     r8, r11
0x180002cb1  mov     eax, edx
0x180002cb3  mov     [rbp+130h+var_158], eax
0x180002cb6  mov     rax, [rbp+130h+arg_58]
0x180002cbd  mov     [rbp+130h+var_160], r8
0x180002cc1  mov     [rbp+130h+var_154], r9d
0x180002cc5  mov     r8, [rax]
0x180002cc8  test    r8, r8
0x180002ccb  jz      short loc_180002CE3
0x180002ccd  mov     rax, rcx
0x180002cd0  inc     rax
0x180002cd3  cmp     [r8+rax*2], r9w
0x180002cd8  jnz     short loc_180002CD0
0x180002cda  lea     eax, ds:2[rax*2]
0x180002ce1  jmp     short loc_180002CE8
0x180002ce3  mov     r8, r11
0x180002ce6  mov     eax, edx
0x180002ce8  mov     [rbp+130h+var_168], eax
0x180002ceb  mov     rax, [rbp+130h+arg_50]
0x180002cf2  mov     [rbp+130h+var_170], r8
0x180002cf6  mov     [rbp+130h+var_164], r9d
0x180002cfa  mov     r8, [rax]
0x180002cfd  test    r8, r8
0x180002d00  jz      short loc_180002D18
0x180002d02  mov     rax, rcx
0x180002d05  inc     rax
0x180002d08  cmp     [r8+rax*2], r9w
0x180002d0d  jnz     short loc_180002D05
0x180002d0f  lea     eax, ds:2[rax*2]
0x180002d16  jmp     short loc_180002D1D
0x180002d18  mov     r8, r11
0x180002d1b  mov     eax, edx
0x180002d1d  mov     [rbp+130h+var_178], eax
0x180002d20  mov     rax, [rbp+130h+arg_48]
0x180002d27  mov     [rbp+130h+var_180], r8
0x180002d2b  mov     [rbp+130h+var_174], r9d
0x180002d2f  mov     r8, [rax]
0x180002d32  test    r8, r8
0x180002d35  jz      short loc_180002D4D
0x180002d37  mov     rax, rcx
0x180002d3a  inc     rax
0x180002d3d  cmp     [r8+rax*2], r9w
0x180002d42  jnz     short loc_180002D3A
0x180002d44  lea     eax, ds:2[rax*2]
0x180002d4b  jmp     short loc_180002D52
0x180002d4d  mov     r8, r11
0x180002d50  mov     eax, edx
0x180002d52  mov     [rbp+130h+var_188], eax
0x180002d55  mov     rax, [rbp+130h+arg_40]
0x180002d5c  mov     [rbp+130h+var_190], r8
0x180002d60  mov     [rbp+130h+var_184], r9d
0x180002d64  mov     r8, [rax]
0x180002d67  test    r8, r8
0x180002d6a  jz      short loc_180002D82
0x180002d6c  mov     rax, rcx
0x180002d6f  inc     rax
0x180002d72  cmp     [r8+rax*2], r9w
0x180002d77  jnz     short loc_180002D6F
0x180002d79  lea     eax, ds:2[rax*2]
0x180002d80  jmp     short loc_180002D87
0x180002d82  mov     r8, r11
0x180002d85  mov     eax, edx
0x180002d87  mov     [rbp+130h+var_198], eax
0x180002d8a  mov     rax, [rbp+130h+arg_38]
0x180002d91  mov     [rbp+130h+var_1A0], r8
0x180002d95  mov     [rbp+130h+var_194], r9d
0x180002d99  mov     r8, [rax]
0x180002d9c  test    r8, r8
0x180002d9f  jz      short loc_180002DB7
0x180002da1  mov     rax, rcx
0x180002da4  inc     rax
0x180002da7  cmp     [r8+rax*2], r9w
0x180002dac  jnz     short loc_180002DA4
0x180002dae  lea     eax, ds:2[rax*2]
0x180002db5  jmp     short loc_180002DBC
0x180002db7  mov     r8, r11
0x180002dba  mov     eax, edx
0x180002dbc  mov     [rbp+130h+var_1A8], eax
0x180002dbf  mov     rax, [rbp+130h+arg_30]
0x180002dc6  mov     [rsp+230h+var_1C0], rax
0x180002dcb  mov     rax, [rbp+130h+arg_28]
0x180002dd2  mov     [rsp+230h+var_1D0], rax
0x180002dd7  mov     rax, [rbp+130h+arg_20]
0x180002dde  mov     [rbp+130h+var_1B0], r8
0x180002de2  mov     [rbp+130h+var_1A4], r9d
0x180002de6  mov     [rsp+230h+var_1B8], 4
0x180002def  mov     r8, [rax]
0x180002df2  mov     [rsp+230h+var_1C8], 4
0x180002dfb  test    r8, r8
0x180002dfe  jz      short loc_180002E13
0x180002e00  inc     rcx
0x180002e03  cmp     [r8+rcx*2], r9w
0x180002e08  jnz     short loc_180002E00
0x180002e0a  lea     edx, ds:2[rcx*2]
0x180002e11  jmp     short loc_180002E16
0x180002e13  mov     r8, r11
0x180002e16  lea     rax, [rsp+230h+var_200]
0x180002e1b  mov     [rsp+230h+var_1E0], r8
0x180002e20  mov     [rsp+230h+var_1D8], edx
0x180002e24  lea     rcx, dword_180031038
0x180002e2b  mov     [rsp+230h+var_208], rax
0x180002e30  xor     r8d, r8d
0x180002e33  mov     rdx, r10
0x180002e36  mov     [rsp+230h+var_210], 1Fh
0x180002e3e  mov     [rsp+230h+var_1D4], r9d
0x180002e43  call    _tlgWriteTransfer_EventWriteTransfer
0x180002e48  mov     rcx, [rbp+130h+var_10]
0x180002e4f  xor     rcx, rsp; StackCookie
0x180002e52  call    __security_check_cookie
0x180002e57  mov     rbx, [rsp+230h+arg_0]
0x180002e5f  add     rsp, 230h
0x180002e66  pop     rbp
0x180002e67  retn
```
