# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x140001278`
- end: `0x1400012ff`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x14001fa90`
- `0x140020168`
- `0x1400203ec`
- `0x140020744`
- `0x140023ba0`
- `0x140024700`
- `0x140024870`
- `0x140024900`
- `0x140024c84`
- `0x140024d88`
- `0x14002537c`
- `0x140025910`
- `0x140025e00`
- `0x14002cfb4`
- `0x14002dd08`
- `0x14002ed10`
- `0x14002fb4c`
- `0x140030da8`
- `0x140033e00`
- `0x140034cf8`

## callees

- `0x1400011d8`
- `0x140001278`
- `0x140002f60`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _BYTE v9[32]; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &byte_14005E3A8;
    v7 = 1;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140075078, a2, 0, 0, 3, v9);
}

```

## disassembly

```asm
0x140001278  sub     rsp, 78h
0x14000127c  mov     rax, cs:__security_cookie
0x140001283  xor     rax, rsp
0x140001286  mov     [rsp+78h+var_18], rax
0x14000128b  mov     rax, [rsp+78h+arg_20]
0x140001293  mov     rcx, [rax]
0x140001296  test    rcx, rcx
0x140001299  jz      short loc_1400012AC
0x14000129b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000129f  inc     rax
0x1400012a2  cmp     byte ptr [rcx+rax], 0
0x1400012a6  jnz     short loc_14000129F
0x1400012a8  inc     eax
0x1400012aa  jmp     short loc_1400012B8
0x1400012ac  lea     rcx, byte_14005E3A8
0x1400012b3  mov     eax, 1
0x1400012b8  mov     [rsp+78h+var_20], eax
0x1400012bc  xor     r9d, r9d
0x1400012bf  lea     rax, [rsp+78h+var_48]
0x1400012c4  mov     [rsp+78h+var_28], rcx
0x1400012c9  mov     [rsp+78h+var_50], rax
0x1400012ce  lea     rcx, dword_140075078
0x1400012d5  xor     r8d, r8d
0x1400012d8  mov     [rsp+78h+var_58], 3
0x1400012e0  mov     [rsp+78h+var_1C], 0
0x1400012e8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400012ed  mov     rcx, [rsp+78h+var_18]
0x1400012f2  xor     rcx, rsp; StackCookie
0x1400012f5  call    __security_check_cookie
0x1400012fa  add     rsp, 78h
0x1400012fe  retn
```
