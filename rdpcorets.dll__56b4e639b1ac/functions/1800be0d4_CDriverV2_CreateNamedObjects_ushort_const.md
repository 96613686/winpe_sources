# CDriverV2::CreateNamedObjects(ushort const *)

- ea: `0x1800be0d4`
- end: `0x1800be53e`
- name: `?CreateNamedObjects@CDriverV2@@IEAAJPEBG@Z`
- size: `1130`
- prototype: `__int64 __fastcall(CDriverV2 *this, const unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002b620`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800bdcf4`
- `0x1800be0d4`
- `0x1800be544`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800be285`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800be285`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800be2ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800be355`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800be2ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800be355`

## string_xrefs

- `0x1800be107`: `CreateNamedObjects`
- `0x1800be1ce`: `CreateNamedObjects`
- `0x1800be3d1`: `CreateNamedObjects`
- `0x1800be4c9`: `CreateNamedObjects`
- `0x1800be18b`: `RdpUpdatesFlushedEvent`
- `0x1800be2a7`: `RdpProtocolStartedEvent`
- `0x1800be2d0`: `Failed to allocate protocol started event`
- `0x1800be376`: `RdpUpdateBufferEmptyEvent`
- `0x1800be4b0`: `Failed to create and map update buffer`

## pseudocode

```c
__int64 __fastcall CDriverV2::CreateNamedObjects(CDriverV2 *this, const unsigned __int16 *a2, __int64 a3, int a4)
{
  CDriverV2 *v5; // rdi
  int NamedEvent; // ebx
  int *v7; // rdx
  const char **v8; // rax
  __int16 *v9; // rdx
  const char **v10; // rax
  const char *v11; // rax
  __int64 v12; // rax
  _OWORD *v13; // rcx
  __int128 v14; // xmm1
  const char **v16; // [rsp+30h] [rbp-40h]
  const char **v17; // [rsp+40h] [rbp-30h]
  const char *v18; // [rsp+50h] [rbp-20h] BYREF
  const char *v19; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-10h] BYREF
  int v21; // [rsp+A0h] [rbp+30h] BYREF
  int v22; // [rsp+B0h] [rbp+40h] BYREF
  const char *v23; // [rsp+B8h] [rbp+48h] BYREF

  v5 = this;
  if ( *((_DWORD *)this + 14) == -1 )
  {
    NamedEvent = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v21 = 224;
      v23 = "CreateNamedObjects";
      v7 = (int *)&unk_1801A7670;
      v18 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
      v19 = "******Session ID -1 still****";
      v8 = &v18;
LABEL_4:
      v22 = NamedEvent;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (_DWORD)v7,
        a3,
        a4,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)v8,
        (__int64)&v21,
        (__int64)&v23);
      return (unsigned int)NamedEvent;
    }
    return (unsigned int)NamedEvent;
  }
  NamedEvent = CDriverV2::AllocateNamedEvent(
                 this,
                 L"RdpUpdatesFlushedEvent",
                 0,
                 0,
                 (unsigned __int16 *)this + 364,
                 (void **)this + 79);
  if ( NamedEvent < 0 )
  {
    LODWORD(this) = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)NamedEvent;
    v21 = 236;
    v23 = "Failed to allocate flush event";
    v9 = word_1801A7582;
    v19 = "CreateNamedObjects";
    v18 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
    v20[0] = "Error HResult failed";
    v17 = &v19;
    v16 = &v18;
    v10 = (const char **)v20;
LABEL_29:
    v22 = NamedEvent;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (_DWORD)v9,
      a3,
      a4,
      (__int64)v10,
      (__int64)&v22,
      (__int64)v16,
      (__int64)&v21,
      (__int64)v17,
      (__int64)&v23);
    return (unsigned int)NamedEvent;
  }
  NamedEvent = CDriverV2::AllocateNamedEvent(
                 v5,
                 L"RdpWaitAbortEvent",
                 1,
                 0,
                 (unsigned __int16 *)v5 + 624,
                 (void **)v5 + 80);
  if ( NamedEvent < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)NamedEvent;
    v11 = "Failed to allocate abort event";
    v21 = 245;
    v9 = (__int16 *)&dword_1801A75D4;
    goto LABEL_28;
  }
  ResetEvent(*((HANDLE *)v5 + 80));
  NamedEvent = CDriverV2::AllocateNamedEvent(
                 v5,
                 L"RdpProtocolStartedEvent",
                 1,
                 1,
                 (unsigned __int16 *)v5 + 1144,
                 (void **)v5 + 81);
  if ( NamedEvent < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)NamedEvent;
    v11 = "Failed to allocate protocol started event";
    v21 = 263;
    v9 = &word_1801A74DE;
    goto LABEL_28;
  }
  SetEvent(*((HANDLE *)v5 + 81));
  NamedEvent = CDriverV2::AllocateNamedEvent(
                 v5,
                 L"RdpPipeLockevent",
                 0,
                 1,
                 (unsigned __int16 *)v5 + 1944,
                 (void **)v5 + 83);
  if ( NamedEvent < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)NamedEvent;
    v11 = "Failed to allocate buffer empty event";
    v21 = 277;
    v9 = (__int16 *)&unk_1801A7530;
    goto LABEL_28;
  }
  SetEvent(*((HANDLE *)v5 + 83));
  NamedEvent = CDriverV2::AllocateNamedEvent(
                 v5,
                 L"RdpUpdateBufferEmptyEvent",
                 0,
                 0,
                 (unsigned __int16 *)v5 + 884,
                 (void **)v5 + 82);
  if ( NamedEvent < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)NamedEvent;
    v11 = "Failed to allocate buffer empty event";
    v21 = 289;
    v9 = word_1801A7442;
    goto LABEL_28;
  }
  if ( !*a2 )
  {
    NamedEvent = -2147418113;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)NamedEvent;
    v21 = 301;
    v23 = "CreateNamedObjects";
    v7 = &dword_1801A7494;
    v20[0] = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
    v19 = "Unexpected event name";
    v8 = (const char **)v20;
    goto LABEL_4;
  }
  v12 = 4;
  v13 = (_OWORD *)((char *)v5 + 2808);
  do
  {
    *v13 = *(_OWORD *)a2;
    v13[1] = *((_OWORD *)a2 + 1);
    v13[2] = *((_OWORD *)a2 + 2);
    v13[3] = *((_OWORD *)a2 + 3);
    v13[4] = *((_OWORD *)a2 + 4);
    v13[5] = *((_OWORD *)a2 + 5);
    v13[6] = *((_OWORD *)a2 + 6);
    v14 = *((_OWORD *)a2 + 7);
    a2 += 64;
    v13[7] = v14;
    v13 += 8;
    --v12;
  }
  while ( v12 );
  *(_QWORD *)v13 = *(_QWORD *)a2;
  NamedEvent = CDriverV2::CreateSharedBuffer(
                 v5,
                 (unsigned __int16 *)0x80,
                 a3,
                 (unsigned __int16 *)v5 + 1664,
                 (unsigned __int8 **)v5 + 8,
                 (void **)v5 + 10);
  if ( NamedEvent < 0 && (unsigned int)dword_1801B76C8 > 2 )
  {
    v11 = "Failed to create and map update buffer";
    v21 = 322;
    v9 = &word_1801A739E;
LABEL_28:
    v23 = v11;
    v20[0] = "CreateNamedObjects";
    v19 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
    v18 = "Error HResult failed";
    v17 = (const char **)v20;
    v16 = &v19;
    v10 = &v18;
    goto LABEL_29;
  }
  return (unsigned int)NamedEvent;
}

```

## disassembly

```asm
0x1800be0d4  mov     [rsp-28h+arg_8], rbx
0x1800be0d9  push    rbp
0x1800be0da  push    rsi
0x1800be0db  push    rdi
0x1800be0dc  push    r14
0x1800be0de  push    r15
0x1800be0e0  mov     rbp, rsp
0x1800be0e3  sub     rsp, 70h
0x1800be0e7  cmp     dword ptr [rcx+38h], 0FFFFFFFFh
0x1800be0eb  mov     rsi, rdx
0x1800be0ee  mov     rdi, rcx
0x1800be0f1  jnz     short loc_1800BE170
0x1800be0f3  mov     eax, cs:dword_1801B76C8
0x1800be0f9  mov     ebx, 80070057h
0x1800be0fe  cmp     eax, 2
0x1800be101  jbe     loc_1800BE528
0x1800be107  lea     rax, aCreatenamedobj; "CreateNamedObjects"
0x1800be10e  mov     [rbp+arg_0], 0E0h
0x1800be115  mov     [rbp+arg_18], rax
0x1800be119  lea     rdx, unk_1801A7670
0x1800be120  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be127  mov     [rbp+var_20], rax
0x1800be12b  lea     rax, aSessionId1Stil; "******Session ID -1 still****"
0x1800be132  mov     [rbp+var_18], rax
0x1800be136  lea     rax, [rbp+arg_18]
0x1800be13a  mov     [rsp+70h+var_30], rax
0x1800be13f  lea     rax, [rbp+arg_0]
0x1800be143  mov     [rsp+70h+var_38], rax
0x1800be148  lea     rax, [rbp+var_20]
0x1800be14c  mov     [rsp+70h+var_40], rax
0x1800be151  lea     rax, [rbp+arg_10]
0x1800be155  mov     [rsp+70h+var_48], rax
0x1800be15a  lea     rax, [rbp+var_18]
0x1800be15e  mov     [rsp+70h+var_50], rax
0x1800be163  mov     [rbp+arg_10], ebx
0x1800be166  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800be16b  jmp     loc_1800BE528
0x1800be170  lea     rax, [rcx+278h]
0x1800be177  xor     r9d, r9d; int
0x1800be17a  add     rcx, 2D8h
0x1800be181  mov     [rsp+70h+var_48], rax; void **
0x1800be186  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800be18b  lea     rdx, aRdpupdatesflus; "RdpUpdatesFlushedEvent"
0x1800be192  mov     rcx, rdi; this
0x1800be195  xor     r8d, r8d; int
0x1800be198  call    ?AllocateNamedEvent@CDriverV2@@IEAAJPEAGHH0PEAPEAX@Z; CDriverV2::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800be19d  xor     r15d, r15d
0x1800be1a0  mov     ebx, eax
0x1800be1a2  test    eax, eax
0x1800be1a4  jns     short loc_1800BE225
0x1800be1a6  mov     ecx, cs:dword_1801B76C8
0x1800be1ac  cmp     ecx, 2
0x1800be1af  jbe     loc_1800BE528
0x1800be1b5  lea     rax, aFailedToAlloca_12; "Failed to allocate flush event"
0x1800be1bc  mov     [rbp+arg_0], 0ECh
0x1800be1c3  mov     [rbp+arg_18], rax
0x1800be1c7  lea     rdx, word_1801A7582
0x1800be1ce  lea     rax, aCreatenamedobj; "CreateNamedObjects"
0x1800be1d5  mov     [rbp+var_18], rax
0x1800be1d9  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be1e0  mov     [rbp+var_20], rax
0x1800be1e4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800be1eb  mov     [rbp+var_10], rax
0x1800be1ef  lea     rax, [rbp+arg_18]
0x1800be1f3  mov     [rsp+70h+var_28], rax
0x1800be1f8  lea     rax, [rbp+var_18]
0x1800be1fc  mov     [rsp+70h+var_30], rax
0x1800be201  lea     rax, [rbp+arg_0]
0x1800be205  mov     [rsp+70h+var_38], rax
0x1800be20a  lea     rax, [rbp+var_20]
0x1800be20e  mov     [rsp+70h+var_40], rax
0x1800be213  lea     rax, [rbp+arg_10]
0x1800be217  mov     [rsp+70h+var_48], rax
0x1800be21c  lea     rax, [rbp+var_10]
0x1800be220  jmp     loc_1800BE51B
0x1800be225  xor     r9d, r9d; int
0x1800be228  lea     rax, [rdi+4E0h]
0x1800be22f  lea     r14, [rdi+280h]
0x1800be236  mov     rcx, rdi; this
0x1800be239  mov     [rsp+70h+var_48], r14; void **
0x1800be23e  lea     rdx, aRdpwaitabortev; "RdpWaitAbortEvent"
0x1800be245  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1800be24a  lea     r8d, [r9+1]; int
0x1800be24e  call    ?AllocateNamedEvent@CDriverV2@@IEAAJPEAGHH0PEAPEAX@Z; CDriverV2::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800be253  mov     ebx, eax
0x1800be255  test    eax, eax
0x1800be257  jns     short loc_1800BE282
0x1800be259  mov     eax, cs:dword_1801B76C8
0x1800be25f  cmp     eax, 2
0x1800be262  jbe     loc_1800BE528
0x1800be268  lea     rax, aFailedToAlloca_3; "Failed to allocate abort event"
0x1800be26f  mov     [rbp+arg_0], 0F5h
0x1800be276  lea     rdx, dword_1801A75D4
0x1800be27d  jmp     loc_1800BE4C5
0x1800be282  mov     rcx, [r14]; hEvent
0x1800be285  call    cs:__imp_ResetEvent
0x1800be28b  mov     r9d, 1; int
0x1800be291  lea     rax, [rdi+8F0h]
0x1800be298  lea     r14, [rdi+288h]
0x1800be29f  mov     r8d, r9d; int
0x1800be2a2  mov     [rsp+70h+var_48], r14; void **
0x1800be2a7  lea     rdx, aRdpprotocolsta; "RdpProtocolStartedEvent"
0x1800be2ae  mov     rcx, rdi; this
0x1800be2b1  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1800be2b6  call    ?AllocateNamedEvent@CDriverV2@@IEAAJPEAGHH0PEAPEAX@Z; CDriverV2::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800be2bb  mov     ebx, eax
0x1800be2bd  test    eax, eax
0x1800be2bf  jns     short loc_1800BE2EA
0x1800be2c1  mov     eax, cs:dword_1801B76C8
0x1800be2c7  cmp     eax, 2
0x1800be2ca  jbe     loc_1800BE528
0x1800be2d0  lea     rax, aFailedToAlloca_1; "Failed to allocate protocol started eve"...
0x1800be2d7  mov     [rbp+arg_0], 107h
0x1800be2de  lea     rdx, word_1801A74DE
0x1800be2e5  jmp     loc_1800BE4C5
0x1800be2ea  mov     rcx, [r14]; hEvent
0x1800be2ed  call    cs:__imp_SetEvent
0x1800be2f3  lea     rax, [rdi+0F30h]
0x1800be2fa  mov     r9d, 1; int
0x1800be300  lea     r14, [rdi+298h]
0x1800be307  xor     r8d, r8d; int
0x1800be30a  mov     [rsp+70h+var_48], r14; void **
0x1800be30f  lea     rdx, aRdppipelockeve; "RdpPipeLockevent"
0x1800be316  mov     rcx, rdi; this
0x1800be319  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1800be31e  call    ?AllocateNamedEvent@CDriverV2@@IEAAJPEAGHH0PEAPEAX@Z; CDriverV2::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800be323  mov     ebx, eax
0x1800be325  test    eax, eax
0x1800be327  jns     short loc_1800BE352
0x1800be329  mov     eax, cs:dword_1801B76C8
0x1800be32f  cmp     eax, 2
0x1800be332  jbe     loc_1800BE528
0x1800be338  lea     rax, aFailedToAlloca_10; "Failed to allocate buffer empty event"
0x1800be33f  mov     [rbp+arg_0], 115h
0x1800be346  lea     rdx, unk_1801A7530
0x1800be34d  jmp     loc_1800BE4C5
0x1800be352  mov     rcx, [r14]; hEvent
0x1800be355  call    cs:__imp_SetEvent
0x1800be35b  lea     rax, [rdi+290h]
0x1800be362  xor     r9d, r9d; int
0x1800be365  lea     rcx, [rdi+6E8h]
0x1800be36c  mov     [rsp+70h+var_48], rax; void **
0x1800be371  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800be376  lea     rdx, aRdpupdatebuffe; "RdpUpdateBufferEmptyEvent"
0x1800be37d  mov     rcx, rdi; this
0x1800be380  xor     r8d, r8d; int
0x1800be383  call    ?AllocateNamedEvent@CDriverV2@@IEAAJPEAGHH0PEAPEAX@Z; CDriverV2::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800be388  mov     ebx, eax
0x1800be38a  test    eax, eax
0x1800be38c  jns     short loc_1800BE3B7
0x1800be38e  mov     eax, cs:dword_1801B76C8
0x1800be394  cmp     eax, 2
0x1800be397  jbe     loc_1800BE528
0x1800be39d  lea     rax, aFailedToAlloca_10; "Failed to allocate buffer empty event"
0x1800be3a4  mov     [rbp+arg_0], 121h
0x1800be3ab  lea     rdx, word_1801A7442
0x1800be3b2  jmp     loc_1800BE4C5
0x1800be3b7  cmp     [rsi], r15w
0x1800be3bb  jnz     short loc_1800BE41B
0x1800be3bd  mov     eax, cs:dword_1801B76C8
0x1800be3c3  mov     ebx, 8000FFFFh
0x1800be3c8  cmp     eax, 2
0x1800be3cb  jbe     loc_1800BE528
0x1800be3d1  lea     rax, aCreatenamedobj; "CreateNamedObjects"
0x1800be3d8  mov     [rbp+arg_0], 12Dh
0x1800be3df  mov     [rbp+arg_18], rax
0x1800be3e3  lea     rdx, dword_1801A7494
0x1800be3ea  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be3f1  mov     [rbp+var_10], rax
0x1800be3f5  lea     rax, aUnexpectedEven; "Unexpected event name"
0x1800be3fc  mov     [rbp+var_18], rax
0x1800be400  lea     rax, [rbp+arg_18]
0x1800be404  mov     [rsp+70h+var_30], rax
0x1800be409  lea     rax, [rbp+arg_0]
0x1800be40d  mov     [rsp+70h+var_38], rax
0x1800be412  lea     rax, [rbp+var_10]
0x1800be416  jmp     loc_1800BE14C
0x1800be41b  mov     eax, 4
0x1800be420  lea     rcx, [rdi+0AF8h]
0x1800be427  lea     edx, [rax+7Ch]; unsigned __int16 *
0x1800be42a  movups  xmm0, xmmword ptr [rsi]
0x1800be42d  movups  xmmword ptr [rcx], xmm0
0x1800be430  movups  xmm1, xmmword ptr [rsi+10h]
0x1800be434  movups  xmmword ptr [rcx+10h], xmm1
0x1800be438  movups  xmm0, xmmword ptr [rsi+20h]
0x1800be43c  movups  xmmword ptr [rcx+20h], xmm0
0x1800be440  movups  xmm1, xmmword ptr [rsi+30h]
0x1800be444  movups  xmmword ptr [rcx+30h], xmm1
0x1800be448  movups  xmm0, xmmword ptr [rsi+40h]
0x1800be44c  movups  xmmword ptr [rcx+40h], xmm0
0x1800be450  movups  xmm1, xmmword ptr [rsi+50h]
0x1800be454  movups  xmmword ptr [rcx+50h], xmm1
0x1800be458  movups  xmm0, xmmword ptr [rsi+60h]
0x1800be45c  movups  xmmword ptr [rcx+60h], xmm0
0x1800be460  movups  xmm1, xmmword ptr [rsi+70h]
0x1800be464  add     rsi, rdx
0x1800be467  movups  xmmword ptr [rcx+70h], xmm1
0x1800be46b  add     rcx, rdx
0x1800be46e  sub     rax, 1
0x1800be472  jnz     short loc_1800BE42A
0x1800be474  mov     rax, [rsi]
0x1800be477  lea     r9, [rdi+0D00h]; unsigned __int16 *
0x1800be47e  mov     [rcx], rax
0x1800be481  lea     rax, [rdi+50h]
0x1800be485  lea     rcx, [rdi+40h]
0x1800be489  mov     [rsp+70h+var_48], rax; void **
0x1800be48e  mov     [rsp+70h+var_50], rcx; unsigned __int8 **
0x1800be493  mov     rcx, rdi; this
0x1800be496  call    ?CreateSharedBuffer@CDriverV2@@IEAAJPEAGK0PEAPEAEPEAPEAX@Z; CDriverV2::CreateSharedBuffer(ushort *,ulong,ushort *,uchar * *,void * *)
0x1800be49b  mov     ebx, eax
0x1800be49d  test    eax, eax
0x1800be49f  jns     loc_1800BE528
0x1800be4a5  mov     eax, cs:dword_1801B76C8
0x1800be4ab  cmp     eax, 2
0x1800be4ae  jbe     short loc_1800BE528
0x1800be4b0  lea     rax, aFailedToCreate_60; "Failed to create and map update buffer"
0x1800be4b7  mov     [rbp+arg_0], 142h
0x1800be4be  lea     rdx, word_1801A739E
0x1800be4c5  mov     [rbp+arg_18], rax
0x1800be4c9  lea     rax, aCreatenamedobj; "CreateNamedObjects"
0x1800be4d0  mov     [rbp+var_10], rax
0x1800be4d4  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800be4db  mov     [rbp+var_18], rax
0x1800be4df  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800be4e6  mov     [rbp+var_20], rax
0x1800be4ea  lea     rax, [rbp+arg_18]
0x1800be4ee  mov     [rsp+70h+var_28], rax
0x1800be4f3  lea     rax, [rbp+var_10]
0x1800be4f7  mov     [rsp+70h+var_30], rax
0x1800be4fc  lea     rax, [rbp+arg_0]
0x1800be500  mov     [rsp+70h+var_38], rax
0x1800be505  lea     rax, [rbp+var_18]
0x1800be509  mov     [rsp+70h+var_40], rax
0x1800be50e  lea     rax, [rbp+arg_10]
0x1800be512  mov     [rsp+70h+var_48], rax
0x1800be517  lea     rax, [rbp+var_20]
0x1800be51b  mov     [rsp+70h+var_50], rax
0x1800be520  mov     [rbp+arg_10], ebx
0x1800be523  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800be528  mov     eax, ebx
0x1800be52a  mov     rbx, [rsp+70h+arg_8]
0x1800be532  add     rsp, 70h
0x1800be536  pop     r15
0x1800be538  pop     r14
0x1800be53a  pop     rdi
0x1800be53b  pop     rsi
0x1800be53c  pop     rbp
0x1800be53d  retn
```
