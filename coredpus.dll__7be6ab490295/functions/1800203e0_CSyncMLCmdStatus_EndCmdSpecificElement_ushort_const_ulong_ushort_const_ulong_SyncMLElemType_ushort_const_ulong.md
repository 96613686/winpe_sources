# CSyncMLCmdStatus::EndCmdSpecificElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)

- ea: `0x1800203e0`
- end: `0x180020790`
- name: `?EndCmdSpecificElement@CSyncMLCmdStatus@@EEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z`
- size: `944`
- prototype: `int __high(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, enum SyncMLElemType, const unsigned __int16 *, unsigned int, enum SyncMLElemType *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001190`
- `0x1800011d4`
- `0x1800034d0`
- `0x180003960`
- `0x180010e04`
- `0x1800203e0`
- `0x180021ae0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002060b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002060b`
- `DMCmnUtils!CopyString` at `0x18002061f`
- `DMCmnUtils!CopyString` at `0x18002061f`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdStatus::EndCmdSpecificElement(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        unsigned __int16 *a7,
        unsigned int a8,
        int *a9)
{
  int v9; // eax
  int *v12; // rbp
  int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // ebp
  int Type; // eax
  int v18; // ecx
  int v19; // r14d
  unsigned __int16 *v20; // rsi
  unsigned __int16 **v21; // rbx
  unsigned int v22; // edx
  unsigned int v23; // ebp
  int *v24; // rdi
  int v25; // eax
  const unsigned __int16 *v27; // [rsp+50h] [rbp-48h] BYREF
  int v28; // [rsp+A0h] [rbp+8h] BYREF

  v9 = *(_DWORD *)(a1 + 168);
  v28 = 73;
  if ( (v9 & 4) == 0 )
  {
    v16 = a5;
    Type = GenericGetType(a4, a5, (const unsigned __int16 **const)&c_rgszSyncMLElem, 73, &v28);
    v13 = Type;
    if ( Type == -2147023728 )
    {
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        v27 = a4;
        v28 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v18,
          (unsigned int)word_1800367B2,
          v14,
          v15,
          (__int64)&v28,
          (__int64)&v27);
      }
      goto LABEL_17;
    }
    if ( Type < 0 )
      goto LABEL_50;
    v19 = v28;
    switch ( v28 )
    {
      case 3:
        *(_DWORD *)(a1 + 168) &= ~1u;
        *(_DWORD *)(a1 + 168) |= 2u;
        goto LABEL_49;
      case 4:
        if ( !a7 || !a8 )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              word_1800372C2,
              0,
              0);
          goto LABEL_17;
        }
        v24 = (int *)(a1 + 212);
        v25 = GenericGetType(a7, a8, (const unsigned __int16 **const)&c_rgszSyncMLElem, 73, v24);
        v13 = v25;
        if ( v25 == -2147023728 )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              byte_180036DE5,
              0,
              0);
          goto LABEL_17;
        }
        if ( v25 < 0 )
          goto LABEL_50;
        if ( *v24 != 1 && !(unsigned int)CSyncMLCmd::IsCmdType((unsigned int)*v24) )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              byte_180036503,
              0,
              0);
          goto LABEL_17;
        }
        goto LABEL_49;
      case 6:
        v20 = a7;
        if ( !a7 || (v23 = a8) == 0 )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              &dword_180036B74,
              0,
              0);
          goto LABEL_17;
        }
        v21 = (unsigned __int16 **)(a1 + 192);
        break;
      case 12:
        v20 = a7;
        if ( !a7 || (v23 = a8) == 0 )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              byte_1800368A3,
              0,
              0);
          goto LABEL_17;
        }
        v21 = (unsigned __int16 **)(a1 + 200);
        break;
      case 16:
      case 18:
        goto LABEL_49;
      case 21:
        v20 = a7;
        if ( !a7 || !a8 )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              &dword_1800368FC,
              0,
              0);
          goto LABEL_17;
        }
        v21 = (unsigned __int16 **)(a1 + 184);
        LocalFree(*(HLOCAL *)(a1 + 184));
        v22 = -1;
LABEL_32:
        v13 = CopyString(v20, v22, v21);
        if ( v13 < 0 )
          goto LABEL_50;
        goto LABEL_49;
      case 25:
LABEL_49:
        *a9 = v19;
        goto LABEL_50;
      default:
LABEL_17:
        v13 = -2102788095;
        goto LABEL_50;
    }
    LocalFree(*v21);
    v22 = v23;
    goto LABEL_32;
  }
  v12 = a9;
  v13 = CSyncMLMeta::EndElement(*(_QWORD *)(a1 + 176), a2, a3, a4, a5, a6, a7, a8, (__int64)a9);
  if ( v13 >= 0 && *v12 == 23 )
    *(_DWORD *)(a1 + 168) &= ~4u;
LABEL_50:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v28 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_180036D03,
      v14,
      v15,
      (__int64)&v28);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800203e0  mov     r11, rsp
0x1800203e3  push    rbx
0x1800203e4  push    rbp
0x1800203e5  push    rsi
0x1800203e6  push    rdi
0x1800203e7  push    r14
0x1800203e9  push    r15
0x1800203eb  sub     rsp, 68h
0x1800203ef  mov     eax, [rcx+0A8h]
0x1800203f5  lea     r15, dword_18003E048
0x1800203fc  mov     dword ptr [r11+8], 49h ; 'I'
0x180020404  mov     rsi, r9
0x180020407  mov     rdi, rcx
0x18002040a  test    al, 4
0x18002040c  jz      short loc_180020473
0x18002040e  mov     eax, [rsp+98h+arg_38]
0x180020415  mov     rbp, [rsp+98h+arg_40]
0x18002041d  mov     rcx, [rcx+0B0h]
0x180020424  mov     [r11-58h], rbp
0x180020428  mov     [rsp+98h+var_60], eax
0x18002042c  mov     rax, [rsp+98h+arg_30]
0x180020434  mov     [r11-68h], rax
0x180020438  mov     eax, [rsp+98h+arg_28]
0x18002043f  mov     dword ptr [rsp+98h+var_70], eax
0x180020443  mov     eax, [rsp+98h+arg_20]
0x18002044a  mov     dword ptr [rsp+98h+var_78], eax
0x18002044e  call    ?EndElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z; CSyncMLMeta::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)
0x180020453  mov     ebx, eax
0x180020455  test    eax, eax
0x180020457  js      loc_180020752
0x18002045d  cmp     dword ptr [rbp+0], 17h
0x180020461  jnz     loc_180020752
0x180020467  and     dword ptr [rdi+0A8h], 0FFFFFFFBh
0x18002046e  jmp     loc_180020752
0x180020473  mov     ebp, [rsp+98h+arg_20]
0x18002047a  lea     rax, [rsp+98h+arg_0]
0x180020482  mov     edx, ebp; unsigned int
0x180020484  mov     [rsp+98h+var_78], rax; int *
0x180020489  mov     r9d, 49h ; 'I'; int
0x18002048f  lea     r8, ?c_rgszSyncMLElem@@3PAPEBGA; unsigned __int16 **
0x180020496  mov     rcx, rsi; unsigned __int16 *
0x180020499  call    ?GenericGetType@@YAJPEBGKQEAPEBGHPEAH@Z; GenericGetType(ushort const *,ulong,ushort const * * const,int,int *)
0x18002049e  mov     ebx, eax
0x1800204a0  cmp     eax, 80070490h
0x1800204a5  jnz     short loc_1800204E7
0x1800204a7  mov     eax, cs:dword_18003E048
0x1800204ad  cmp     eax, 2
0x1800204b0  jbe     loc_18002053E
0x1800204b6  lea     rax, [rsp+98h+var_48]
0x1800204bb  mov     [rsp+98h+var_48], rsi
0x1800204c0  mov     [rsp+98h+var_70], rax
0x1800204c5  lea     rdx, word_1800367B2
0x1800204cc  lea     rax, [rsp+98h+arg_0]
0x1800204d4  mov     [rsp+98h+arg_0], ebp
0x1800204db  mov     [rsp+98h+var_78], rax
0x1800204e0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800204e5  jmp     short loc_18002053E
0x1800204e7  test    eax, eax
0x1800204e9  js      loc_180020752
0x1800204ef  mov     r14d, [rsp+98h+arg_0]
0x1800204f7  mov     ecx, r14d
0x1800204fa  sub     ecx, 3
0x1800204fd  jz      loc_180020739
0x180020503  sub     ecx, 1
0x180020506  jz      loc_180020663
0x18002050c  sub     ecx, 2
0x18002050f  jz      loc_1800205E9
0x180020515  sub     ecx, 6
0x180020518  jz      loc_18002059F
0x18002051e  sub     ecx, 4
0x180020521  jz      loc_180020747
0x180020527  sub     ecx, 2
0x18002052a  jz      loc_180020747
0x180020530  sub     ecx, 3
0x180020533  jz      short loc_180020548
0x180020535  cmp     ecx, 4
0x180020538  jz      loc_180020747
0x18002053e  mov     ebx, 82AA0001h
0x180020543  jmp     loc_180020752
0x180020548  mov     rsi, [rsp+98h+arg_30]
0x180020550  test    rsi, rsi
0x180020553  jz      short loc_18002057D
0x180020555  cmp     [rsp+98h+arg_38], 0
0x18002055d  jz      short loc_18002057D
0x18002055f  lea     rbx, [rdi+0B8h]
0x180020566  mov     rcx, [rbx]; hMem
0x180020569  call    cs:__imp_LocalFree
0x180020570  nop     dword ptr [rax+rax+00h]
0x180020575  or      edx, 0FFFFFFFFh
0x180020578  jmp     loc_180020619
0x18002057d  mov     eax, cs:dword_18003E048
0x180020583  cmp     eax, 2
0x180020586  jbe     short loc_18002053E
0x180020588  xor     r9d, r9d
0x18002058b  lea     rdx, dword_1800368FC
0x180020592  xor     r8d, r8d
0x180020595  mov     rcx, r15
0x180020598  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002059d  jmp     short loc_18002053E
0x18002059f  mov     rsi, [rsp+98h+arg_30]
0x1800205a7  test    rsi, rsi
0x1800205aa  jz      short loc_1800205C0
0x1800205ac  mov     ebp, [rsp+98h+arg_38]
0x1800205b3  test    ebp, ebp
0x1800205b5  jz      short loc_1800205C0
0x1800205b7  lea     rbx, [rdi+0C8h]
0x1800205be  jmp     short loc_180020608
0x1800205c0  mov     eax, cs:dword_18003E048
0x1800205c6  cmp     eax, 2
0x1800205c9  jbe     loc_18002053E
0x1800205cf  xor     r9d, r9d
0x1800205d2  lea     rdx, byte_1800368A3
0x1800205d9  xor     r8d, r8d
0x1800205dc  mov     rcx, r15
0x1800205df  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800205e4  jmp     loc_18002053E
0x1800205e9  mov     rsi, [rsp+98h+arg_30]
0x1800205f1  test    rsi, rsi
0x1800205f4  jz      short loc_18002063A
0x1800205f6  mov     ebp, [rsp+98h+arg_38]
0x1800205fd  test    ebp, ebp
0x1800205ff  jz      short loc_18002063A
0x180020601  lea     rbx, [rdi+0C0h]
0x180020608  mov     rcx, [rbx]; hMem
0x18002060b  call    cs:__imp_LocalFree
0x180020612  nop     dword ptr [rax+rax+00h]
0x180020617  mov     edx, ebp
0x180020619  mov     r8, rbx
0x18002061c  mov     rcx, rsi
0x18002061f  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180020626  nop     dword ptr [rax+rax+00h]
0x18002062b  mov     ebx, eax
0x18002062d  test    eax, eax
0x18002062f  js      loc_180020752
0x180020635  jmp     loc_180020747
0x18002063a  mov     eax, cs:dword_18003E048
0x180020640  cmp     eax, 2
0x180020643  jbe     loc_18002053E
0x180020649  xor     r9d, r9d
0x18002064c  lea     rdx, dword_180036B74
0x180020653  xor     r8d, r8d
0x180020656  mov     rcx, r15
0x180020659  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002065e  jmp     loc_18002053E
0x180020663  mov     rcx, [rsp+98h+arg_30]; unsigned __int16 *
0x18002066b  test    rcx, rcx
0x18002066e  jz      loc_180020710
0x180020674  mov     edx, [rsp+98h+arg_38]; unsigned int
0x18002067b  test    edx, edx
0x18002067d  jz      loc_180020710
0x180020683  add     rdi, 0D4h
0x18002068a  lea     r8, ?c_rgszSyncMLElem@@3PAPEBGA; unsigned __int16 **
0x180020691  mov     r9d, 49h ; 'I'; int
0x180020697  mov     [rsp+98h+var_78], rdi; int *
0x18002069c  call    ?GenericGetType@@YAJPEBGKQEAPEBGHPEAH@Z; GenericGetType(ushort const *,ulong,ushort const * * const,int,int *)
0x1800206a1  mov     ebx, eax
0x1800206a3  cmp     eax, 80070490h
0x1800206a8  jnz     short loc_1800206D3
0x1800206aa  mov     eax, cs:dword_18003E048
0x1800206b0  cmp     eax, 2
0x1800206b3  jbe     loc_18002053E
0x1800206b9  xor     r9d, r9d
0x1800206bc  lea     rdx, byte_180036DE5
0x1800206c3  xor     r8d, r8d
0x1800206c6  mov     rcx, r15
0x1800206c9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800206ce  jmp     loc_18002053E
0x1800206d3  test    eax, eax
0x1800206d5  js      short loc_180020752
0x1800206d7  cmp     dword ptr [rdi], 1
0x1800206da  jz      short loc_180020747
0x1800206dc  mov     ecx, [rdi]
0x1800206de  call    ?IsCmdType@CSyncMLCmd@@SAHW4SyncMLElemType@@@Z; CSyncMLCmd::IsCmdType(SyncMLElemType)
0x1800206e3  test    eax, eax
0x1800206e5  jnz     short loc_180020747
0x1800206e7  mov     eax, cs:dword_18003E048
0x1800206ed  cmp     eax, 2
0x1800206f0  jbe     loc_18002053E
0x1800206f6  xor     r9d, r9d
0x1800206f9  lea     rdx, byte_180036503
0x180020700  xor     r8d, r8d
0x180020703  mov     rcx, r15
0x180020706  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002070b  jmp     loc_18002053E
0x180020710  mov     eax, cs:dword_18003E048
0x180020716  cmp     eax, 2
0x180020719  jbe     loc_18002053E
0x18002071f  xor     r9d, r9d
0x180020722  lea     rdx, word_1800372C2
0x180020729  xor     r8d, r8d
0x18002072c  mov     rcx, r15
0x18002072f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180020734  jmp     loc_18002053E
0x180020739  and     dword ptr [rdi+0A8h], 0FFFFFFFEh
0x180020740  or      dword ptr [rdi+0A8h], 2
0x180020747  mov     rax, [rsp+98h+arg_40]
0x18002074f  mov     [rax], r14d
0x180020752  mov     eax, cs:dword_18003E048
0x180020758  cmp     eax, 5
0x18002075b  jbe     short loc_180020780
0x18002075d  lea     rax, [rsp+98h+arg_0]
0x180020765  mov     [rsp+98h+arg_0], ebx
0x18002076c  lea     rdx, byte_180036D03
0x180020773  mov     [rsp+98h+var_78], rax
0x180020778  mov     rcx, r15
0x18002077b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020780  mov     eax, ebx
0x180020782  add     rsp, 68h
0x180020786  pop     r15
0x180020788  pop     r14
0x18002078a  pop     rdi
0x18002078b  pop     rsi
0x18002078c  pop     rbp
0x18002078d  pop     rbx
0x18002078e  retn
```
