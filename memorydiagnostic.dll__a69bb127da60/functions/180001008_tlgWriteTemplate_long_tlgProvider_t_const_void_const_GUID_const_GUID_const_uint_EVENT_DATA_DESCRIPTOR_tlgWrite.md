# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x180001091`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x180008bf0`
- `0x1800094d4`
- `0x180009fc0`
- `0x18000a6d4`
- `0x18000aed0`
- `0x18000b238`
- `0x18000dcdc`
- `0x180010ac4`
- `0x1800115f8`
- `0x180011760`
- `0x1800132f0`
- `0x1800139d0`
- `0x180014030`
- `0x1800149b8`
- `0x18001d4f4`
- `0x18001de90`
- `0x18001e080`

## callees

- `0x180001008`
- `0x180001a7c`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-48h] BYREF
  int *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]

  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_180025214;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           3,
           v10);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 78h
0x18000100c  mov     rax, cs:__security_cookie
0x180001013  xor     rax, rsp
0x180001016  mov     [rsp+78h+var_18], rax
0x18000101b  mov     rax, [rsp+78h+arg_20]
0x180001023  mov     r10, rcx
0x180001026  xor     r8d, r8d
0x180001029  mov     rcx, [rax]
0x18000102c  test    rcx, rcx
0x18000102f  jz      short loc_180001048
0x180001031  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001035  inc     rax
0x180001038  cmp     [rcx+rax*2], r8w
0x18000103d  jnz     short loc_180001035
0x18000103f  lea     eax, ds:2[rax*2]
0x180001046  jmp     short loc_180001054
0x180001048  lea     rcx, dword_180025214
0x18000104f  mov     eax, 2
0x180001054  mov     [rsp+78h+var_20], eax
0x180001058  xor     r9d, r9d
0x18000105b  lea     rax, [rsp+78h+var_48]
0x180001060  mov     [rsp+78h+var_28], rcx
0x180001065  mov     [rsp+78h+var_50], rax
0x18000106a  mov     rcx, r10
0x18000106d  mov     [rsp+78h+var_58], 3
0x180001075  mov     [rsp+78h+var_1C], r8d
0x18000107a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000107f  mov     rcx, [rsp+78h+var_18]
0x180001084  xor     rcx, rsp; StackCookie
0x180001087  call    __security_check_cookie
0x18000108c  add     rsp, 78h
0x180001090  retn
```
