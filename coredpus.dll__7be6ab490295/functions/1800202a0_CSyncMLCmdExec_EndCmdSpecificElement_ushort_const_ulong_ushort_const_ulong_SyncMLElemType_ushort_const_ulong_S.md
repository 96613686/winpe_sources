# CSyncMLCmdExec::EndCmdSpecificElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)

- ea: `0x1800202a0`
- end: `0x1800203cc`
- name: `?EndCmdSpecificElement@CSyncMLCmdExec@@EEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z`
- size: `300`
- prototype: `int __high(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, enum SyncMLElemType, const unsigned __int16 *, unsigned int, enum SyncMLElemType *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011d4`
- `0x1800034d0`
- `0x180003960`
- `0x1800202a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002038f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002038f`
- `DMCmnUtils!CopyString` at `0x1800203a3`
- `DMCmnUtils!CopyString` at `0x1800203a3`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdExec::EndCmdSpecificElement(
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
  const unsigned __int16 *v18; // rdi
  unsigned int v19; // esi
  int v20[14]; // [rsp+30h] [rbp-38h] BYREF

  v9 = a5;
  v20[0] = 73;
  Type = GenericGetType(a4, a5, (const unsigned __int16 **const)&c_rgszSyncMLElem, 73, v20);
  v16 = Type;
  if ( Type == -2147023728 )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_QWORD *)v20 = a4;
      a5 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v13,
        (unsigned int)byte_18003670B,
        v14,
        v15,
        (__int64)&a5,
        (__int64)v20);
    }
    goto LABEL_4;
  }
  if ( Type >= 0 )
  {
    if ( v20[0] != 24 || (v18 = a7) == 0 || (v19 = a8) == 0 )
    {
LABEL_4:
      v16 = -2102788095;
      goto LABEL_5;
    }
    LocalFree(*(HLOCAL *)(a1 + 168));
    v16 = CopyString(v18, v19, (unsigned __int16 **)(a1 + 168));
    if ( v16 >= 0 )
      *a9 = 24;
  }
LABEL_5:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    a5 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_1800366DD,
      v14,
      v15,
      (__int64)&a5);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800202a0  push    rbx
0x1800202a2  push    rbp
0x1800202a3  push    rsi
0x1800202a4  push    rdi
0x1800202a5  sub     rsp, 48h
0x1800202a9  mov     esi, [rsp+68h+arg_20]
0x1800202b0  lea     rax, [rsp+68h+var_38]
0x1800202b5  mov     rdi, r9
0x1800202b8  mov     [rsp+68h+var_48], rax; int *
0x1800202bd  mov     r9d, 49h ; 'I'; int
0x1800202c3  lea     r8, ?c_rgszSyncMLElem@@3PAPEBGA; unsigned __int16 **
0x1800202ca  mov     rbp, rcx
0x1800202cd  mov     [rsp+68h+var_38], r9d
0x1800202d2  mov     rcx, rdi; unsigned __int16 *
0x1800202d5  mov     edx, esi; unsigned int
0x1800202d7  call    ?GenericGetType@@YAJPEBGKQEAPEBGHPEAH@Z; GenericGetType(ushort const *,ulong,ushort const * * const,int,int *)
0x1800202dc  mov     ebx, eax
0x1800202de  cmp     eax, 80070490h
0x1800202e3  jnz     short loc_180020362
0x1800202e5  mov     eax, cs:dword_18003E048
0x1800202eb  cmp     eax, 2
0x1800202ee  jbe     short loc_18002031F
0x1800202f0  lea     rax, [rsp+68h+var_38]
0x1800202f5  mov     qword ptr [rsp+68h+var_38], rdi
0x1800202fa  mov     [rsp+68h+var_40], rax
0x1800202ff  lea     rdx, byte_18003670B
0x180020306  lea     rax, [rsp+68h+arg_20]
0x18002030e  mov     [rsp+68h+arg_20], esi
0x180020315  mov     [rsp+68h+var_48], rax
0x18002031a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002031f  mov     ebx, 82AA0001h
0x180020324  mov     eax, cs:dword_18003E048
0x18002032a  cmp     eax, 5
0x18002032d  jbe     short loc_180020356
0x18002032f  lea     rax, [rsp+68h+arg_20]
0x180020337  mov     [rsp+68h+arg_20], ebx
0x18002033e  lea     rdx, byte_1800366DD
0x180020345  mov     [rsp+68h+var_48], rax
0x18002034a  lea     rcx, dword_18003E048
0x180020351  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020356  mov     eax, ebx
0x180020358  add     rsp, 48h
0x18002035c  pop     rdi
0x18002035d  pop     rsi
0x18002035e  pop     rbp
0x18002035f  pop     rbx
0x180020360  retn
0x180020362  test    eax, eax
0x180020364  js      short loc_180020324
0x180020366  cmp     [rsp+68h+var_38], 18h
0x18002036b  jnz     short loc_18002031F
0x18002036d  mov     rdi, [rsp+68h+arg_30]
0x180020375  test    rdi, rdi
0x180020378  jz      short loc_18002031F
0x18002037a  mov     esi, [rsp+68h+arg_38]
0x180020381  test    esi, esi
0x180020383  jz      short loc_18002031F
0x180020385  lea     rbx, [rbp+0A8h]
0x18002038c  mov     rcx, [rbx]; hMem
0x18002038f  call    cs:__imp_LocalFree
0x180020396  nop     dword ptr [rax+rax+00h]
0x18002039b  mov     r8, rbx
0x18002039e  mov     edx, esi
0x1800203a0  mov     rcx, rdi
0x1800203a3  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800203aa  nop     dword ptr [rax+rax+00h]
0x1800203af  mov     ebx, eax
0x1800203b1  test    eax, eax
0x1800203b3  js      loc_180020324
0x1800203b9  mov     rax, [rsp+68h+arg_40]
0x1800203c1  mov     dword ptr [rax], 18h
0x1800203c7  jmp     loc_180020324
```
