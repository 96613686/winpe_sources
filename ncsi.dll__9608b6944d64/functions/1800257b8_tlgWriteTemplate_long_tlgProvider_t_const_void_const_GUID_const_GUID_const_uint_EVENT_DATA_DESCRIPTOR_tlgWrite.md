# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x1800257b8`
- end: `0x1800258a6`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800150f8`
- `0x18004debc`
- `0x180050300`
- `0x180051b7c`
- `0x180059c64`
- `0x18005d170`

## callees

- `0x1800257b8`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002587c`
- `ntdll!EtwEventWriteTransfer` at `0x18002587c`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _DWORD v10[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-40h]
  unsigned __int16 *v12; // [rsp+48h] [rbp-38h] BYREF
  int v13; // [rsp+50h] [rbp-30h]
  int v14; // [rsp+54h] [rbp-2Ch]
  unsigned __int8 *v15; // [rsp+58h] [rbp-28h]
  int v16; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+64h] [rbp-1Ch]
  const unsigned __int16 *v18; // [rsp+68h] [rbp-18h]
  int v19; // [rsp+70h] [rbp-10h]
  int v20; // [rsp+74h] [rbp-Ch]

  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &qword_18007F760;
    v8 = 1;
  }
  v19 = v8;
  v10[0] = *a2 << 24;
  v10[1] = *(unsigned __int16 *)(a2 + 1);
  v11 = *(_QWORD *)(a2 + 3);
  v12 = *(unsigned __int16 **)(a1 + 8);
  v18 = v6;
  v20 = 0;
  v13 = *v12;
  v16 = *(unsigned __int16 *)(a2 + 11);
  v15 = a2 + 11;
  v17 = 1;
  v14 = 2;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v10, 0, 0, 3, &v12);
}

```

## disassembly

```asm
0x1800257b8  push    rbp
0x1800257ba  mov     rbp, rsp
0x1800257bd  sub     rsp, 80h
0x1800257c4  mov     rax, cs:__security_cookie
0x1800257cb  xor     rax, rsp
0x1800257ce  mov     [rbp+var_8], rax
0x1800257d2  mov     rax, [rbp+arg_20]
0x1800257d6  mov     r10, rcx
0x1800257d9  mov     r8d, 1
0x1800257df  mov     rcx, [rax]
0x1800257e2  test    rcx, rcx
0x1800257e5  jz      loc_180025897
0x1800257eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800257ef  inc     rax
0x1800257f2  cmp     byte ptr [rcx+rax], 0
0x1800257f6  jnz     short loc_1800257EF
0x1800257f8  inc     eax
0x1800257fa  mov     [rbp+var_10], eax
0x1800257fd  xor     r9d, r9d
0x180025800  movzx   eax, byte ptr [rdx]
0x180025803  shl     eax, 18h
0x180025806  mov     [rbp+var_48], eax
0x180025809  movzx   eax, word ptr [rdx+1]
0x18002580d  mov     [rbp+var_44], eax
0x180025810  mov     rax, [rdx+3]
0x180025814  mov     [rbp+var_40], rax
0x180025818  mov     rax, [r10+8]
0x18002581c  mov     [rbp+var_38], rax
0x180025820  mov     [rbp+var_18], rcx
0x180025824  lea     rcx, [rdx+0Bh]
0x180025828  mov     [rbp+var_C], 0
0x18002582f  lea     rdx, [rbp+var_48]
0x180025833  movzx   eax, word ptr [rax]
0x180025836  mov     [rbp+var_30], eax
0x180025839  movzx   eax, word ptr [rcx]
0x18002583c  mov     [rbp+var_20], eax
0x18002583f  lea     rax, _TraceLoggingMetadataEnd
0x180025846  mov     [rbp+var_28], rcx
0x18002584a  lea     rcx, _TraceLoggingMetadata
0x180025851  sub     eax, ecx
0x180025853  mov     [rbp+var_1C], r8d
0x180025857  mov     [rbp+var_2C], 2
0x18002585e  xor     r8d, r8d
0x180025861  mov     [rbp+var_50], eax
0x180025864  mov     eax, [rbp+var_50]
0x180025867  mov     rcx, [r10+20h]
0x18002586b  lea     rax, [rbp+var_38]
0x18002586f  mov     [rsp+80h+var_58], rax
0x180025874  mov     [rsp+80h+var_60], 3
0x18002587c  call    cs:__imp_EtwEventWriteTransfer
0x180025882  mov     rcx, [rbp+var_8]
0x180025886  xor     rcx, rsp; StackCookie
0x180025889  call    __security_check_cookie
0x18002588e  add     rsp, 80h
0x180025895  pop     rbp
0x180025896  retn
0x180025897  lea     rcx, qword_18007F760
0x18002589e  mov     eax, r8d
0x1800258a1  jmp     loc_1800257FA
```
