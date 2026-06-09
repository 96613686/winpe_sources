# CSyncMLCmdAlert::EndCmdSpecificElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)

- ea: `0x180020150`
- end: `0x180020291`
- name: `?EndCmdSpecificElement@CSyncMLCmdAlert@@EEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z`
- size: `321`
- prototype: `int __high(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, enum SyncMLElemType, const unsigned __int16 *, unsigned int, enum SyncMLElemType *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011d4`
- `0x1800034d0`
- `0x180003960`
- `0x180020150`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020253`
- `DMCmnUtils!CopyString` at `0x18002026c`
- `DMCmnUtils!CopyString` at `0x18002026c`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAlert::EndCmdSpecificElement(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        __int64 a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        _DWORD *a9)
{
  unsigned int v9; // esi
  int Type; // eax
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // r9
  signed int v16; // ebx
  const unsigned __int16 *v18; // rsi
  int v19[14]; // [rsp+30h] [rbp-38h] BYREF

  v9 = a5;
  v19[0] = 73;
  Type = GenericGetType(a4, a5, (const unsigned __int16 **const)&c_rgszSyncMLElem, 73, v19);
  v16 = Type;
  if ( Type == -2147023728 )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_QWORD *)v19 = a4;
      a5 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v13,
        (unsigned int)byte_180036865,
        v14,
        v15,
        (__int64)&a5,
        (__int64)v19);
    }
    goto LABEL_4;
  }
  if ( Type >= 0 )
  {
    if ( v19[0] == 7 )
    {
LABEL_9:
      v16 = -2147467263;
      goto LABEL_10;
    }
    if ( v19[0] != 21 )
    {
      if ( v19[0] == 24 )
        goto LABEL_9;
LABEL_4:
      v16 = -2102788095;
      goto LABEL_10;
    }
    v18 = a7;
    if ( !a7 || !a8 )
      goto LABEL_4;
    LocalFree(*(HLOCAL *)(a1 + 168));
    v16 = CopyString(v18, a8, (unsigned __int16 **)(a1 + 168));
    if ( v16 >= 0 )
      *a9 = 21;
  }
LABEL_10:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    a5 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&dword_1800365F4,
      v14,
      v15,
      (__int64)&a5);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180020150  push    rbx
0x180020152  push    rsi
0x180020153  push    rdi
0x180020154  push    r14
0x180020156  sub     rsp, 48h
0x18002015a  mov     esi, [rsp+68h+arg_20]
0x180020161  lea     rax, [rsp+68h+var_38]
0x180020166  mov     rdi, r9
0x180020169  mov     [rsp+68h+var_48], rax; int *
0x18002016e  mov     r9d, 49h ; 'I'; int
0x180020174  lea     r8, ?c_rgszSyncMLElem@@3PAPEBGA; unsigned __int16 **
0x18002017b  mov     r14, rcx
0x18002017e  mov     [rsp+68h+var_38], r9d
0x180020183  mov     rcx, rdi; unsigned __int16 *
0x180020186  mov     edx, esi; unsigned int
0x180020188  call    ?GenericGetType@@YAJPEBGKQEAPEBGHPEAH@Z; GenericGetType(ushort const *,ulong,ushort const * * const,int,int *)
0x18002018d  mov     ebx, eax
0x18002018f  cmp     eax, 80070490h
0x180020194  jnz     short loc_1800201D7
0x180020196  mov     eax, cs:dword_18003E048
0x18002019c  cmp     eax, 2
0x18002019f  jbe     short loc_1800201D0
0x1800201a1  lea     rax, [rsp+68h+var_38]
0x1800201a6  mov     qword ptr [rsp+68h+var_38], rdi
0x1800201ab  mov     [rsp+68h+var_40], rax
0x1800201b0  lea     rdx, byte_180036865
0x1800201b7  lea     rax, [rsp+68h+arg_20]
0x1800201bf  mov     [rsp+68h+arg_20], esi
0x1800201c6  mov     [rsp+68h+var_48], rax
0x1800201cb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800201d0  mov     ebx, 82AA0001h
0x1800201d5  jmp     short loc_1800201F3
0x1800201d7  test    eax, eax
0x1800201d9  js      short loc_1800201F3
0x1800201db  mov     edi, [rsp+68h+var_38]
0x1800201df  cmp     edi, 7
0x1800201e2  jz      short loc_1800201EE
0x1800201e4  cmp     edi, 15h
0x1800201e7  jz      short loc_180020232
0x1800201e9  cmp     edi, 18h
0x1800201ec  jnz     short loc_1800201D0
0x1800201ee  mov     ebx, 80004001h
0x1800201f3  mov     eax, cs:dword_18003E048
0x1800201f9  cmp     eax, 5
0x1800201fc  jbe     short loc_180020225
0x1800201fe  lea     rax, [rsp+68h+arg_20]
0x180020206  mov     [rsp+68h+arg_20], ebx
0x18002020d  lea     rdx, dword_1800365F4
0x180020214  mov     [rsp+68h+var_48], rax
0x180020219  lea     rcx, dword_18003E048
0x180020220  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020225  mov     eax, ebx
0x180020227  add     rsp, 48h
0x18002022b  pop     r14
0x18002022d  pop     rdi
0x18002022e  pop     rsi
0x18002022f  pop     rbx
0x180020230  retn
0x180020232  mov     rsi, [rsp+68h+arg_30]
0x18002023a  test    rsi, rsi
0x18002023d  jz      short loc_1800201D0
0x18002023f  cmp     [rsp+68h+arg_38], 0
0x180020247  jz      short loc_1800201D0
0x180020249  lea     rbx, [r14+0A8h]
0x180020250  mov     rcx, [rbx]; hMem
0x180020253  call    cs:__imp_LocalFree
0x18002025a  nop     dword ptr [rax+rax+00h]
0x18002025f  mov     edx, [rsp+68h+arg_38]
0x180020266  mov     r8, rbx
0x180020269  mov     rcx, rsi
0x18002026c  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180020273  nop     dword ptr [rax+rax+00h]
0x180020278  mov     ebx, eax
0x18002027a  test    eax, eax
0x18002027c  js      loc_1800201F3
0x180020282  mov     rcx, [rsp+68h+arg_40]
0x18002028a  mov     [rcx], edi
0x18002028c  jmp     loc_1800201F3
```
