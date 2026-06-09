# CSyncMLDPU::AppendAlertStatus(ushort const *,ulong)

- ea: `0x180019060`
- end: `0x180019167`
- name: `?AppendAlertStatus@CSyncMLDPU@@QEAAJPEBGK@Z`
- size: `263`
- prototype: `__int64 __fastcall(CSyncMLDPU *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000adf0`

## callees

- `0x1800034d0`
- `0x180017880`
- `0x180019060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001911c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001911c`
- `DMCmnUtils!CopyString` at `0x1800190c6`
- `DMCmnUtils!CopyString` at `0x1800190c6`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::AppendAlertStatus(CSyncMLDPU *this, const unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  int v4; // edi
  int v7; // ebx
  _OWORD *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  HLOCAL hMem[2]; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+58h] [rbp+10h] BYREF

  v4 = a3;
  *(_OWORD *)hMem = 0;
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v13 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&unk_180035C60,
      a3,
      a4,
      (__int64)&v13);
  }
  if ( a2 )
  {
    v7 = CopyString(a2, 0xFFFFFFFF, (unsigned __int16 **)hMem);
    if ( v7 >= 0 )
    {
      try
      {
        LODWORD(hMem[1]) = v4;
        v8 = (_OWORD *)*((_QWORD *)this + 39);
        if ( v8 == *((_OWORD **)this + 40) )
        {
          std::vector<ALERTINFORESULT>::_Emplace_reallocate<ALERTINFORESULT const &>((char *)this + 304, v8, hMem);
        }
        else
        {
          *v8 = *(_OWORD *)hMem;
          *((_QWORD *)this + 39) += 16LL;
        }
        hMem[0] = 0;
      }
      catch ( std::bad_alloc )
      {
        v13 = -2147024882;
        v7 = -2147024882;
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  LocalFree(hMem[0]);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v13 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_180035D31,
      v9,
      v10,
      (__int64)&v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019060  mov     r11, rsp
0x180019063  mov     [r11+8], rbx
0x180019067  mov     [r11+18h], rsi
0x18001906b  push    rdi
0x18001906c  sub     rsp, 40h
0x180019070  mov     edi, r8d
0x180019073  mov     rbx, rdx
0x180019076  mov     rsi, rcx
0x180019079  xorps   xmm0, xmm0
0x18001907c  movups  xmmword ptr [rsp+48h+hMem], xmm0
0x180019081  mov     eax, cs:dword_18003E048
0x180019087  cmp     eax, 5
0x18001908a  jbe     short loc_1800190AF
0x18001908c  mov     [rsp+48h+arg_8], 0
0x180019094  lea     rax, [r11+10h]
0x180019098  mov     [r11-28h], rax
0x18001909c  lea     rdx, unk_180035C60
0x1800190a3  lea     rcx, dword_18003E048
0x1800190aa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800190af  test    rbx, rbx
0x1800190b2  jnz     short loc_1800190BB
0x1800190b4  mov     ebx, 80070057h
0x1800190b9  jmp     short loc_180019117
0x1800190bb  lea     r8, [rsp+48h+hMem]
0x1800190c0  or      edx, 0FFFFFFFFh
0x1800190c3  mov     rcx, rbx
0x1800190c6  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800190cd  nop     dword ptr [rax+rax+00h]
0x1800190d2  mov     ebx, eax
0x1800190d4  test    eax, eax
0x1800190d6  js      short loc_180019117
0x1800190d8  mov     dword ptr [rsp+48h+hMem+8], edi
0x1800190dc  lea     rcx, [rsi+130h]
0x1800190e3  mov     rdx, [rcx+8]
0x1800190e7  cmp     rdx, [rcx+10h]
0x1800190eb  jz      short loc_1800190FD
0x1800190ed  movups  xmm0, xmmword ptr [rsp+48h+hMem]
0x1800190f2  movdqu  xmmword ptr [rdx], xmm0
0x1800190f6  add     qword ptr [rcx+8], 10h
0x1800190fb  jmp     short loc_180019108
0x1800190fd  lea     r8, [rsp+48h+hMem]
0x180019102  call    ??$_Emplace_reallocate@AEBUALERTINFORESULT@@@?$vector@UALERTINFORESULT@@V?$allocator@UALERTINFORESULT@@@std@@@std@@AEAAPEAUALERTINFORESULT@@QEAU2@AEBU2@@Z; std::vector<ALERTINFORESULT>::_Emplace_reallocate<ALERTINFORESULT const &>(ALERTINFORESULT * const,ALERTINFORESULT const &)
0x180019107  nop
0x180019108  mov     [rsp+48h+hMem], 0
0x180019111  jmp     short loc_180019117
0x180019113  mov     ebx, [rsp+48h+arg_8]
0x180019117  mov     rcx, [rsp+48h+hMem]; hMem
0x18001911c  call    cs:__imp_LocalFree
0x180019123  nop     dword ptr [rax+rax+00h]
0x180019128  mov     eax, cs:dword_18003E048
0x18001912e  cmp     eax, 5
0x180019131  jbe     short loc_180019154
0x180019133  mov     [rsp+48h+arg_8], ebx
0x180019137  lea     rax, [rsp+48h+arg_8]
0x18001913c  mov     [rsp+48h+var_28], rax
0x180019141  lea     rdx, byte_180035D31
0x180019148  lea     rcx, dword_18003E048
0x18001914f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180019154  mov     eax, ebx
0x180019156  mov     rbx, [rsp+48h+arg_0]
0x18001915b  mov     rsi, [rsp+48h+arg_10]
0x180019160  add     rsp, 40h
0x180019164  pop     rdi
0x180019165  retn
```
