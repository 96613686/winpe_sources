# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x1800010f8`
- end: `0x18000117f`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0x180004cbc`
- `0x1800052d0`
- `0x180006d18`
- `0x18000a140`
- `0x18000acb0`
- `0x18000ae80`
- `0x18000bdbc`
- `0x18000f670`
- `0x18000f7cc`
- `0x18001054c`
- `0x1800108a8`
- `0x180010a30`
- `0x180012238`
- `0x1800129e4`
- `0x180013e58`
- `0x1800148c8`
- `0x180015210`
- `0x1800154f0`
- `0x1800157dc`
- `0x180017230`
- `0x180017350`
- `0x180017b80`
- `0x180018658`
- `0x1800195d0`
- `0x180021f80`
- `0x180022420`
- `0x1800242a0`
- `0x180024d20`
- `0x180025f34`
- `0x180026cd0`
- `0x180028298`
- `0x180028514`
- `0x180029688`
- `0x180029f60`
- `0x18002a888`
- `0x18002ab18`

## callees

- `0x1800010f8`
- `0x180001ef8`
- `0x18002b960`

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
    v5 = &word_18002F722;
    v7 = 1;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180044008, a2, 0, 0, 3, v9);
}

```

## disassembly

```asm
0x1800010f8  sub     rsp, 78h
0x1800010fc  mov     rax, cs:__security_cookie
0x180001103  xor     rax, rsp
0x180001106  mov     [rsp+78h+var_18], rax
0x18000110b  mov     rax, [rsp+78h+arg_20]
0x180001113  mov     rcx, [rax]
0x180001116  test    rcx, rcx
0x180001119  jz      short loc_18000112C
0x18000111b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000111f  inc     rax
0x180001122  cmp     byte ptr [rcx+rax], 0
0x180001126  jnz     short loc_18000111F
0x180001128  inc     eax
0x18000112a  jmp     short loc_180001138
0x18000112c  lea     rcx, word_18002F722
0x180001133  mov     eax, 1
0x180001138  mov     [rsp+78h+var_20], eax
0x18000113c  xor     r9d, r9d
0x18000113f  lea     rax, [rsp+78h+var_48]
0x180001144  mov     [rsp+78h+var_28], rcx
0x180001149  mov     [rsp+78h+var_50], rax
0x18000114e  lea     rcx, dword_180044008
0x180001155  xor     r8d, r8d
0x180001158  mov     [rsp+78h+var_58], 3
0x180001160  mov     [rsp+78h+var_1C], 0
0x180001168  call    _tlgWriteTransfer_EventWriteTransfer
0x18000116d  mov     rcx, [rsp+78h+var_18]
0x180001172  xor     rcx, rsp; StackCookie
0x180001175  call    __security_check_cookie
0x18000117a  add     rsp, 78h
0x18000117e  retn
```
