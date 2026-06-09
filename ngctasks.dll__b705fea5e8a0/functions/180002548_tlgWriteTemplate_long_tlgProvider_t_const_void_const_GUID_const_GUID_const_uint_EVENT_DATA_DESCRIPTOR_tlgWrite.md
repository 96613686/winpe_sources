# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002548`
- end: `0x1800029ff`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U1@U1@U1@U1@U1@U1@U1@U1@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@43333333344444444444344AEBU?$_tlgWrapperByVal@$07@@53344@Z`
- size: `1207`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013310`

## callees

- `0x1800024a8`
- `0x180002548`
- `0x180006330`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
        _QWORD *a32,
        _QWORD *a33)
{
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax

  v33 = -1;
  if ( *a33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(*a33 + 2 * v34) );
  }
  if ( *a32 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *(_WORD *)(*a32 + 2 * v35) );
  }
  if ( *a27 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *(_WORD *)(*a27 + 2 * v36) );
  }
  if ( *a15 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)(*a15 + 2 * v37) );
  }
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *(_WORD *)(*a14 + 2 * v38) );
  }
  if ( *a13 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)(*a13 + 2 * v39) );
  }
  if ( *a12 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)(*a12 + 2 * v40) );
  }
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)(*a11 + 2 * v41) );
  }
  if ( *a10 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *(_WORD *)(*a10 + 2 * v42) );
  }
  if ( *a9 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)(*a9 + 2 * v43) );
  }
  if ( *a8 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *(_WORD *)(*a8 + 2 * v44) );
  }
  if ( *a5 )
  {
    do
      ++v33;
    while ( *(_WORD *)(*a5 + 2 * v33) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180031038, a2);
}

```

## disassembly

```asm
0x180002548  mov     [rsp-8+arg_0], rbx
0x18000254d  push    rbp
0x18000254e  lea     rbp, [rsp-150h]
0x180002556  sub     rsp, 250h
0x18000255d  mov     rax, cs:__security_cookie
0x180002564  xor     rax, rsp
0x180002567  mov     [rbp+150h+var_10], rax
0x18000256e  mov     rax, [rbp+150h+arg_110]
0x180002575  lea     r11, qword_180024840
0x18000257c  mov     [rbp+150h+var_20], rax
0x180002583  xor     r9d, r9d
0x180002586  mov     rax, [rbp+150h+arg_108]
0x18000258d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002591  mov     [rbp+150h+var_30], rax
0x180002598  mov     r10, rdx
0x18000259b  mov     rax, [rbp+150h+arg_100]
0x1800025a2  mov     [rbp+150h+var_18], 4
0x1800025ad  lea     edx, [r9+2]
0x1800025b1  mov     [rbp+150h+var_28], 4
0x1800025bc  mov     r8, [rax]
0x1800025bf  test    r8, r8
0x1800025c2  jz      short loc_1800025DA
0x1800025c4  mov     rax, rcx
0x1800025c7  inc     rax
0x1800025ca  cmp     [r8+rax*2], r9w
0x1800025cf  jnz     short loc_1800025C7
0x1800025d1  lea     eax, ds:2[rax*2]
0x1800025d8  jmp     short loc_1800025DF
0x1800025da  mov     r8, r11
0x1800025dd  mov     eax, edx
0x1800025df  mov     [rbp+150h+var_38], eax
0x1800025e5  mov     rax, [rbp+150h+arg_F8]
0x1800025ec  mov     [rbp+150h+var_40], r8
0x1800025f3  mov     [rbp+150h+var_34], r9d
0x1800025fa  mov     r8, [rax]
0x1800025fd  test    r8, r8
0x180002600  jz      short loc_180002618
0x180002602  mov     rax, rcx
0x180002605  inc     rax
0x180002608  cmp     [r8+rax*2], r9w
0x18000260d  jnz     short loc_180002605
0x18000260f  lea     eax, ds:2[rax*2]
0x180002616  jmp     short loc_18000261D
0x180002618  mov     r8, r11
0x18000261b  mov     eax, edx
0x18000261d  mov     [rbp+150h+var_48], eax
0x180002623  mov     rax, [rbp+150h+arg_F0]
0x18000262a  mov     [rbp+150h+var_60], rax
0x180002631  mov     rax, [rbp+150h+arg_E8]
0x180002638  mov     [rbp+150h+var_70], rax
0x18000263f  mov     rax, [rbp+150h+arg_E0]
0x180002646  mov     [rbp+150h+var_80], rax
0x18000264d  mov     rax, [rbp+150h+arg_D8]
0x180002654  mov     [rbp+150h+var_90], rax
0x18000265b  mov     rax, [rbp+150h+arg_D0]
0x180002662  mov     [rbp+150h+var_50], r8
0x180002669  mov     [rbp+150h+var_44], r9d
0x180002670  mov     [rbp+150h+var_58], 8
0x18000267b  mov     r8, [rax]
0x18000267e  mov     [rbp+150h+var_68], 8
0x180002689  mov     [rbp+150h+var_78], 4
0x180002694  mov     [rbp+150h+var_88], 4
0x18000269f  test    r8, r8
0x1800026a2  jz      short loc_1800026BA
0x1800026a4  mov     rax, rcx
0x1800026a7  inc     rax
0x1800026aa  cmp     [r8+rax*2], r9w
0x1800026af  jnz     short loc_1800026A7
0x1800026b1  lea     eax, ds:2[rax*2]
0x1800026b8  jmp     short loc_1800026BF
0x1800026ba  mov     r8, r11
0x1800026bd  mov     eax, edx
0x1800026bf  mov     [rbp+150h+var_98], eax
0x1800026c5  mov     rax, [rbp+150h+arg_C8]
0x1800026cc  mov     [rbp+150h+var_B0], rax
0x1800026d3  mov     rax, [rbp+150h+arg_C0]
0x1800026da  mov     [rbp+150h+var_C0], rax
0x1800026e1  mov     rax, [rbp+150h+arg_B8]
0x1800026e8  mov     [rbp+150h+var_D0], rax
0x1800026ef  mov     rax, [rbp+150h+arg_B0]
0x1800026f6  mov     [rbp+150h+var_E0], rax
0x1800026fa  mov     rax, [rbp+150h+arg_A8]
0x180002701  mov     [rbp+150h+var_F0], rax
0x180002705  mov     rax, [rbp+150h+arg_A0]
0x18000270c  mov     [rbp+150h+var_100], rax
0x180002710  mov     rax, [rbp+150h+arg_98]
0x180002717  mov     [rbp+150h+var_110], rax
0x18000271b  mov     rax, [rbp+150h+arg_90]
0x180002722  mov     [rbp+150h+var_120], rax
0x180002726  mov     rax, [rbp+150h+arg_88]
0x18000272d  mov     [rbp+150h+var_130], rax
0x180002731  mov     rax, [rbp+150h+arg_80]
0x180002738  mov     [rbp+150h+var_140], rax
0x18000273c  mov     rax, [rbp+150h+arg_78]
0x180002743  mov     [rbp+150h+var_150], rax
0x180002747  mov     rax, [rbp+150h+arg_70]
0x18000274e  mov     [rbp+150h+var_A0], r8
0x180002755  mov     [rbp+150h+var_94], r9d
0x18000275c  mov     [rbp+150h+var_A8], 4
0x180002767  mov     r8, [rax]
0x18000276a  mov     [rbp+150h+var_B8], 4
0x180002775  mov     [rbp+150h+var_C8], 4
0x180002780  mov     [rbp+150h+var_D8], 4
0x180002788  mov     [rbp+150h+var_E8], 4
0x180002790  mov     [rbp+150h+var_F8], 4
0x180002798  mov     [rbp+150h+var_108], 4
0x1800027a0  mov     [rbp+150h+var_118], 4
0x1800027a8  mov     [rbp+150h+var_128], 4
0x1800027b0  mov     [rbp+150h+var_138], 4
0x1800027b8  mov     [rbp+150h+var_148], 4
0x1800027c0  test    r8, r8
0x1800027c3  jz      short loc_1800027DB
0x1800027c5  mov     rax, rcx
0x1800027c8  inc     rax
0x1800027cb  cmp     [r8+rax*2], r9w
0x1800027d0  jnz     short loc_1800027C8
0x1800027d2  lea     eax, ds:2[rax*2]
0x1800027d9  jmp     short loc_1800027E0
0x1800027db  mov     r8, r11
0x1800027de  mov     eax, edx
0x1800027e0  mov     [rbp+150h+var_158], eax
0x1800027e3  mov     rax, [rbp+150h+arg_68]
0x1800027ea  mov     [rbp+150h+var_160], r8
0x1800027ee  mov     [rbp+150h+var_154], r9d
0x1800027f2  mov     r8, [rax]
0x1800027f5  test    r8, r8
0x1800027f8  jz      short loc_180002810
0x1800027fa  mov     rax, rcx
0x1800027fd  inc     rax
0x180002800  cmp     [r8+rax*2], r9w
0x180002805  jnz     short loc_1800027FD
0x180002807  lea     eax, ds:2[rax*2]
0x18000280e  jmp     short loc_180002815
0x180002810  mov     r8, r11
0x180002813  mov     eax, edx
0x180002815  mov     [rbp+150h+var_168], eax
0x180002818  mov     rax, [rbp+150h+arg_60]
0x18000281f  mov     [rbp+150h+var_170], r8
0x180002823  mov     [rbp+150h+var_164], r9d
0x180002827  mov     r8, [rax]
0x18000282a  test    r8, r8
0x18000282d  jz      short loc_180002845
0x18000282f  mov     rax, rcx
0x180002832  inc     rax
0x180002835  cmp     [r8+rax*2], r9w
0x18000283a  jnz     short loc_180002832
0x18000283c  lea     eax, ds:2[rax*2]
0x180002843  jmp     short loc_18000284A
0x180002845  mov     r8, r11
0x180002848  mov     eax, edx
0x18000284a  mov     [rbp+150h+var_178], eax
0x18000284d  mov     rax, [rbp+150h+arg_58]
0x180002854  mov     [rbp+150h+var_180], r8
0x180002858  mov     [rbp+150h+var_174], r9d
0x18000285c  mov     r8, [rax]
0x18000285f  test    r8, r8
0x180002862  jz      short loc_18000287A
0x180002864  mov     rax, rcx
0x180002867  inc     rax
0x18000286a  cmp     [r8+rax*2], r9w
0x18000286f  jnz     short loc_180002867
0x180002871  lea     eax, ds:2[rax*2]
0x180002878  jmp     short loc_18000287F
0x18000287a  mov     r8, r11
0x18000287d  mov     eax, edx
0x18000287f  mov     [rbp+150h+var_188], eax
0x180002882  mov     rax, [rbp+150h+arg_50]
0x180002889  mov     [rbp+150h+var_190], r8
0x18000288d  mov     [rbp+150h+var_184], r9d
0x180002891  mov     r8, [rax]
0x180002894  test    r8, r8
0x180002897  jz      short loc_1800028AF
0x180002899  mov     rax, rcx
0x18000289c  inc     rax
0x18000289f  cmp     [r8+rax*2], r9w
0x1800028a4  jnz     short loc_18000289C
0x1800028a6  lea     eax, ds:2[rax*2]
0x1800028ad  jmp     short loc_1800028B4
0x1800028af  mov     r8, r11
0x1800028b2  mov     eax, edx
0x1800028b4  mov     [rbp+150h+var_198], eax
0x1800028b7  mov     rax, [rbp+150h+arg_48]
0x1800028be  mov     [rbp+150h+var_1A0], r8
0x1800028c2  mov     [rbp+150h+var_194], r9d
0x1800028c6  mov     r8, [rax]
0x1800028c9  test    r8, r8
0x1800028cc  jz      short loc_1800028E4
0x1800028ce  mov     rax, rcx
0x1800028d1  inc     rax
0x1800028d4  cmp     [r8+rax*2], r9w
0x1800028d9  jnz     short loc_1800028D1
0x1800028db  lea     eax, ds:2[rax*2]
0x1800028e2  jmp     short loc_1800028E9
0x1800028e4  mov     r8, r11
0x1800028e7  mov     eax, edx
0x1800028e9  mov     [rbp+150h+var_1A8], eax
0x1800028ec  mov     rax, [rbp+150h+arg_40]
0x1800028f3  mov     [rbp+150h+var_1B0], r8
0x1800028f7  mov     [rbp+150h+var_1A4], r9d
0x1800028fb  mov     r8, [rax]
0x1800028fe  test    r8, r8
0x180002901  jz      short loc_180002919
0x180002903  mov     rax, rcx
0x180002906  inc     rax
0x180002909  cmp     [r8+rax*2], r9w
0x18000290e  jnz     short loc_180002906
0x180002910  lea     eax, ds:2[rax*2]
0x180002917  jmp     short loc_18000291E
0x180002919  mov     r8, r11
0x18000291c  mov     eax, edx
0x18000291e  mov     [rbp+150h+var_1B8], eax
0x180002921  mov     rax, [rbp+150h+arg_38]
0x180002928  mov     [rbp+150h+var_1C0], r8
0x18000292c  mov     [rbp+150h+var_1B4], r9d
0x180002930  mov     r8, [rax]
0x180002933  test    r8, r8
0x180002936  jz      short loc_18000294E
0x180002938  mov     rax, rcx
0x18000293b  inc     rax
0x18000293e  cmp     [r8+rax*2], r9w
0x180002943  jnz     short loc_18000293B
0x180002945  lea     eax, ds:2[rax*2]
0x18000294c  jmp     short loc_180002953
0x18000294e  mov     r8, r11
0x180002951  mov     eax, edx
0x180002953  mov     [rbp+150h+var_1C8], eax
0x180002956  mov     rax, [rbp+150h+arg_30]
0x18000295d  mov     [rsp+250h+var_1E0], rax
0x180002962  mov     rax, [rbp+150h+arg_28]
0x180002969  mov     [rsp+250h+var_1F0], rax
0x18000296e  mov     rax, [rbp+150h+arg_20]
0x180002975  mov     [rbp+150h+var_1D0], r8
0x180002979  mov     [rbp+150h+var_1C4], r9d
0x18000297d  mov     [rsp+250h+var_1D8], 4
0x180002986  mov     r8, [rax]
0x180002989  mov     [rsp+250h+var_1E8], 4
0x180002992  test    r8, r8
0x180002995  jz      short loc_1800029AA
0x180002997  inc     rcx
0x18000299a  cmp     [r8+rcx*2], r9w
0x18000299f  jnz     short loc_180002997
0x1800029a1  lea     edx, ds:2[rcx*2]
0x1800029a8  jmp     short loc_1800029AD
0x1800029aa  mov     r8, r11
0x1800029ad  lea     rax, [rsp+250h+var_220]
0x1800029b2  mov     [rsp+250h+var_200], r8
0x1800029b7  mov     [rsp+250h+var_1F8], edx
0x1800029bb  lea     rcx, dword_180031038
0x1800029c2  mov     [rsp+250h+var_228], rax
0x1800029c7  xor     r8d, r8d
0x1800029ca  mov     rdx, r10
0x1800029cd  mov     [rsp+250h+var_230], 21h ; '!'
0x1800029d5  mov     [rsp+250h+var_1F4], r9d
0x1800029da  call    _tlgWriteTransfer_EventWriteTransfer
0x1800029df  mov     rcx, [rbp+150h+var_10]
0x1800029e6  xor     rcx, rsp; StackCookie
0x1800029e9  call    __security_check_cookie
0x1800029ee  mov     rbx, [rsp+250h+arg_0]
0x1800029f6  add     rsp, 250h
0x1800029fd  pop     rbp
0x1800029fe  retn
```
