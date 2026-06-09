# TMetabase_XMLtable::TMetabase_XMLtable(void)

- ea: `0x1800054d8`
- end: `0x180005777`
- name: `??0TMetabase_XMLtable@@QEAA@XZ`
- size: `671`
- prototype: `TMetabase_XMLtable *__fastcall(TMetabase_XMLtable *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002970`

## callees

- `0x180001d04`
- `0x180001ef0`
- `0x180005798`
- `0x180010e7c`
- `0x18002e0ca`

## string_xrefs

- `0x18000552e`: `ComCatMeta_v6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
TMetabase_XMLtable *__fastcall TMetabase_XMLtable::TMetabase_XMLtable(TMetabase_XMLtable *this)
{
  int v2; // r8d

  *(_QWORD *)this = &TMetabase_XMLtable::`vftable'{for `ISimpleTableWrite2'};
  *((_QWORD *)this + 1) = &TMetabase_XMLtable::`vftable'{for `ISimpleTableController'};
  *((_QWORD *)this + 2) = &TMetabase_XMLtable::`vftable'{for `ISimpleTableInterceptor'};
  *((_QWORD *)this + 3) = &TMetabase_XMLtable::`vftable'{for `TXmlParsedFileNodeFactory'};
  *((_QWORD *)this + 4) = &TMetabase_XMLtable::`vftable'{for `TMSXMLBase'};
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = L"ComCatMeta_v6";
  `eh vector constructor iterator'(
    (char *)this + 592,
    8u,
    9u,
    (void (*)(void *))ATL::CComBSTR::CComBSTR,
    (void (*)(void *))ATL::CComBSTR::~CComBSTR);
  `vector constructor iterator'(
    (char *)this + 1316,
    8u,
    9u,
    (void *(*)(void *))TMetabase_XMLtable::TTagMetaIndex::TTagMetaIndex);
  `eh vector constructor iterator'(
    (char *)this + 1392,
    0x10u,
    9u,
    (void (*)(void *))TGrowableBuffer::TGrowableBuffer,
    (void (*)(void *))TGrowableBuffer::~TGrowableBuffer);
  TPublicRowName::TPublicRowName((TMetabase_XMLtable *)((char *)this + 1536));
  *((_QWORD *)this + 198) = 0;
  *((_QWORD *)this + 199) = 0;
  *((_DWORD *)this + 400) = 256;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_WORD *)this + 812) = 257;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 205) = 32;
  *((_DWORD *)this + 412) = 0;
  *((_QWORD *)this + 207) = 0;
  *((_DWORD *)this + 416) = -1;
  *((_DWORD *)this + 417) = -1;
  *((_DWORD *)this + 418) = -1;
  *((_DWORD *)this + 420) = 0;
  *((_QWORD *)this + 211) = 0;
  *((_QWORD *)this + 212) = 0;
  *((_DWORD *)this + 426) = -1;
  *((_QWORD *)this + 214) = 0;
  *((_QWORD *)this + 215) = 0;
  *((_QWORD *)this + 216) = 0;
  *((_QWORD *)this + 217) = 0;
  *((_QWORD *)this + 218) = 0;
  *((_QWORD *)this + 219) = 0;
  *((_QWORD *)this + 220) = 0;
  *((_QWORD *)this + 221) = 0;
  *((_QWORD *)this + 222) = 0;
  *((_QWORD *)this + 223) = 0;
  *((_QWORD *)this + 224) = 0;
  *((_QWORD *)this + 225) = 0;
  *((_QWORD *)this + 226) = 0;
  *((_QWORD *)this + 244) = 0;
  TXmlParsedFile_NoCache::TXmlParsedFile_NoCache((TMetabase_XMLtable *)((char *)this + 1960));
  *((_QWORD *)this + 255) = 0;
  *((_QWORD *)this + 283) = 0;
  *((_QWORD *)this + 284) = 0;
  *((_DWORD *)this + 570) = v2;
  *((_WORD *)this + 20) = 0;
  memset_0((char *)this + 664, 0, 0x6Cu);
  *(_OWORD *)((char *)this + 772) = 0;
  *(_OWORD *)((char *)this + 788) = 0;
  *((_DWORD *)this + 201) = 0;
  *(_OWORD *)((char *)this + 1096) = 0;
  *(_OWORD *)((char *)this + 1112) = 0;
  *((_DWORD *)this + 282) = 0;
  *((_OWORD *)this + 80) = 0;
  *((_OWORD *)this + 81) = 0;
  *((_DWORD *)this + 328) = 0;
  memset_0((char *)this + 1136, 0, 0x48u);
  *(_OWORD *)((char *)this + 1208) = 0;
  *(_OWORD *)((char *)this + 1224) = 0;
  *((_DWORD *)this + 310) = 0;
  *((_DWORD *)this + 512) = 0;
  *(_QWORD *)((char *)this + 2052) = 2;
  *((_DWORD *)this + 515) = 13;
  *((_DWORD *)this + 552) = 0;
  *((_DWORD *)this + 553) = 2;
  return this;
}

```

## disassembly

```asm
0x1800054d8  mov     r11, rsp
0x1800054db  mov     [r11+10h], rbx
0x1800054df  mov     [r11+18h], rbp
0x1800054e3  mov     [r11+8], rcx
0x1800054e7  push    rsi
0x1800054e8  sub     rsp, 30h
0x1800054ec  mov     rbx, rcx
0x1800054ef  lea     rax, ??_7TMetabase_XMLtable@@6BISimpleTableWrite2@@@; const TMetabase_XMLtable::`vftable'{for `ISimpleTableWrite2'}
0x1800054f6  mov     [rcx], rax
0x1800054f9  lea     rax, ??_7TMetabase_XMLtable@@6BISimpleTableController@@@; const TMetabase_XMLtable::`vftable'{for `ISimpleTableController'}
0x180005500  mov     [rcx+8], rax
0x180005504  lea     rax, ??_7TMetabase_XMLtable@@6BISimpleTableInterceptor@@@; const TMetabase_XMLtable::`vftable'{for `ISimpleTableInterceptor'}
0x18000550b  mov     [rcx+10h], rax
0x18000550f  lea     rax, ??_7TMetabase_XMLtable@@6BTXmlParsedFileNodeFactory@@@; const TMetabase_XMLtable::`vftable'{for `TXmlParsedFileNodeFactory'}
0x180005516  mov     [rcx+18h], rax
0x18000551a  lea     rax, ??_7TMetabase_XMLtable@@6BTMSXMLBase@@@; const TMetabase_XMLtable::`vftable'{for `TMSXMLBase'}
0x180005521  mov     [rcx+20h], rax
0x180005525  xor     ebp, ebp
0x180005527  mov     [rcx+240h], rbp
0x18000552e  lea     rax, aComcatmetaV6; "ComCatMeta_v6"
0x180005535  mov     [rcx+248h], rax
0x18000553c  add     rcx, 250h; void *
0x180005543  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18000554a  mov     [r11-18h], rax
0x18000554e  lea     r9, ??0CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180005555  lea     esi, [rbp+9]
0x180005558  mov     r8d, esi; unsigned __int64
0x18000555b  lea     edx, [rbp+8]; unsigned __int64
0x18000555e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180005563  nop
0x180005564  lea     rcx, [rbx+524h]; void *
0x18000556b  lea     r9, ??0TTagMetaIndex@TMetabase_XMLtable@@QEAA@XZ; void *(*)(void *)
0x180005572  mov     r8d, esi; unsigned __int64
0x180005575  lea     edx, [rbp+8]; unsigned __int64
0x180005578  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000557d  lea     rcx, [rbx+570h]; void *
0x180005584  lea     rax, ??1TGrowableBuffer@@QEAA@XZ; TGrowableBuffer::~TGrowableBuffer(void)
0x18000558b  mov     [rsp+38h+var_18], rax; void (*)(void *)
0x180005590  lea     r9, ??0TGrowableBuffer@@QEAA@XZ; void (*)(void *)
0x180005597  mov     r8d, esi; unsigned __int64
0x18000559a  lea     edx, [rbp+10h]; unsigned __int64
0x18000559d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800055a2  nop
0x1800055a3  lea     rcx, [rbx+600h]; this
0x1800055aa  call    ??0TPublicRowName@@QEAA@XZ; TPublicRowName::TPublicRowName(void)
0x1800055af  nop
0x1800055b0  mov     [rbx+630h], rbp
0x1800055b7  mov     [rbx+638h], rbp
0x1800055be  mov     dword ptr [rbx+640h], 100h
0x1800055c8  mov     [rbx+648h], rbp
0x1800055cf  mov     [rbx+650h], rbp
0x1800055d6  mov     word ptr [rbx+658h], 101h
0x1800055df  mov     [rbx+660h], rbp
0x1800055e6  mov     qword ptr [rbx+668h], 20h ; ' '
0x1800055f1  mov     [rbx+670h], ebp
0x1800055f7  mov     [rbx+678h], rbp
0x1800055fe  or      r8d, 0FFFFFFFFh
0x180005602  mov     [rbx+680h], r8d
0x180005609  mov     [rbx+684h], r8d
0x180005610  mov     [rbx+688h], r8d
0x180005617  mov     [rbx+690h], ebp
0x18000561d  mov     [rbx+698h], rbp
0x180005624  mov     [rbx+6A0h], rbp
0x18000562b  mov     [rbx+6A8h], r8d
0x180005632  mov     [rbx+6B0h], rbp
0x180005639  mov     [rbx+6B8h], rbp
0x180005640  mov     [rbx+6C0h], rbp
0x180005647  mov     [rbx+6C8h], rbp
0x18000564e  mov     [rbx+6D0h], rbp
0x180005655  mov     [rbx+6D8h], rbp
0x18000565c  mov     [rbx+6E0h], rbp
0x180005663  mov     [rbx+6E8h], rbp
0x18000566a  mov     [rbx+6F0h], rbp
0x180005671  mov     [rbx+6F8h], rbp
0x180005678  mov     [rbx+700h], rbp
0x18000567f  mov     [rbx+708h], rbp
0x180005686  mov     [rbx+710h], rbp
0x18000568d  mov     [rbx+7A0h], rbp
0x180005694  lea     rcx, [rbx+7A8h]; this
0x18000569b  call    ??0TXmlParsedFile_NoCache@@QEAA@XZ; TXmlParsedFile_NoCache::TXmlParsedFile_NoCache(void)
0x1800056a0  mov     [rbx+7F8h], rbp
0x1800056a7  mov     [rbx+8D8h], rbp
0x1800056ae  mov     [rbx+8E0h], rbp
0x1800056b5  mov     [rbx+8E8h], r8d
0x1800056bc  mov     [rbx+28h], bp
0x1800056c0  lea     rcx, [rbx+298h]; void *
0x1800056c7  xor     edx, edx; Val
0x1800056c9  lea     r8d, [rbp+6Ch]; Size
0x1800056cd  call    memset_0
0x1800056d2  xorps   xmm0, xmm0
0x1800056d5  xor     eax, eax
0x1800056d7  movups  xmmword ptr [rbx+304h], xmm0
0x1800056de  movups  xmmword ptr [rbx+314h], xmm0
0x1800056e5  mov     [rbx+324h], eax
0x1800056eb  movups  xmmword ptr [rbx+448h], xmm0
0x1800056f2  movups  xmmword ptr [rbx+458h], xmm0
0x1800056f9  mov     [rbx+468h], eax
0x1800056ff  movups  xmmword ptr [rbx+500h], xmm0
0x180005706  movups  xmmword ptr [rbx+510h], xmm0
0x18000570d  mov     [rbx+520h], eax
0x180005713  lea     rcx, [rbx+470h]; void *
0x18000571a  xor     edx, edx; Val
0x18000571c  lea     r8d, [rbp+48h]; Size
0x180005720  call    memset_0
0x180005725  xorps   xmm0, xmm0
0x180005728  xor     eax, eax
0x18000572a  movups  xmmword ptr [rbx+4B8h], xmm0
0x180005731  movups  xmmword ptr [rbx+4C8h], xmm0
0x180005738  mov     [rbx+4D8h], eax
0x18000573e  mov     [rbx+800h], ebp
0x180005744  lea     eax, [rbp+2]
0x180005747  mov     [rbx+804h], rax
0x18000574e  mov     dword ptr [rbx+80Ch], 0Dh
0x180005758  mov     [rbx+8A0h], ebp
0x18000575e  mov     [rbx+8A4h], eax
0x180005764  mov     rax, rbx
0x180005767  mov     rbx, [rsp+38h+arg_8]
0x18000576c  mov     rbp, [rsp+38h+arg_10]
0x180005771  add     rsp, 30h
0x180005775  pop     rsi
0x180005776  retn
```
