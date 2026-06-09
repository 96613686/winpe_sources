# LPA::Lpd::InvalidateClientToken(void)

- ea: `0x1800b12cc`
- end: `0x1800b134f`
- name: `?InvalidateClientToken@Lpd@LPA@@QEAAXXZ`
- size: `131`
- prototype: `void __fastcall(LPA::Lpd *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800a847c`
- `0x1800b8608`
- `0x1800faaf2`
- `0x1800fb16f`
- `0x1800fb2f6`
- `0x1800fb46b`
- `0x1800fb60e`
- `0x1800fb887`

## callees

- `0x1800056e4`
- `0x1800b12cc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1338`

## string_xrefs

- `0x1800b1309`: `LpaServiceLpd`
- `0x1800b12fe`: `LPA::Lpd::InvalidateClientToken`

## pseudocode

```c
void __fastcall LPA::Lpd::InvalidateClientToken(LPA::Lpd *this, __int64 a2, int a3, int a4)
{
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF
  const char *v6; // [rsp+58h] [rbp+10h] BYREF
  const char *v7; // [rsp+60h] [rbp+18h] BYREF

  if ( *((_QWORD *)this + 18) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v5 = *((_QWORD *)this + 18);
      v6 = "LPA::Lpd::InvalidateClientToken";
      v7 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)this,
        (unsigned int)&word_1801301C6,
        a3,
        a4,
        (__int64)&v7,
        (__int64)&v6,
        (__int64)&v5);
    }
    CloseHandle(*((HANDLE *)this + 18));
    *((_QWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x1800b12cc  mov     r11, rsp
0x1800b12cf  push    rbx
0x1800b12d0  sub     rsp, 40h
0x1800b12d4  cmp     qword ptr [rcx+90h], 0
0x1800b12dc  mov     rbx, rcx
0x1800b12df  jz      short loc_1800B1349
0x1800b12e1  mov     eax, cs:CallbackContext
0x1800b12e7  cmp     eax, 4
0x1800b12ea  jbe     short loc_1800B1331
0x1800b12ec  mov     rax, [rcx+90h]
0x1800b12f3  lea     rdx, word_1801301C6
0x1800b12fa  mov     [r11+8], rax
0x1800b12fe  lea     rax, aLpaLpdInvalida; "LPA::Lpd::InvalidateClientToken"
0x1800b1305  mov     [r11+10h], rax
0x1800b1309  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b1310  mov     [r11+18h], rax
0x1800b1314  lea     rax, [r11+8]
0x1800b1318  mov     [r11-18h], rax
0x1800b131c  lea     rax, [r11+10h]
0x1800b1320  mov     [r11-20h], rax
0x1800b1324  lea     rax, [r11+18h]
0x1800b1328  mov     [r11-28h], rax
0x1800b132c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800b1331  mov     rcx, [rbx+90h]; hObject
0x1800b1338  call    cs:__imp_CloseHandle
0x1800b133e  mov     qword ptr [rbx+90h], 0
0x1800b1349  add     rsp, 40h
0x1800b134d  pop     rbx
0x1800b134e  retn
```
