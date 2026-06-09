# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18002d45c`
- end: `0x18002d6bd`
- name: `?ReportStopActivity@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `609`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002c6f0`
- `0x18002e054`

## callees

- `0x18000230c`
- `0x180002408`
- `0x18002d36c`
- `0x18002d45c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d648`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rax
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // r9d
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v23; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v24; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v27; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v28; // [rsp+E0h] [rbp+27h] BYREF
  _QWORD v29[5]; // [rsp+E8h] [rbp+2Fh] BYREF
  int v30; // [rsp+120h] [rbp+67h] BYREF
  DWORD v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  __int64 v33; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = MDMPushProvider::Provider();
      v8 = v7;
      if ( *(_DWORD *)v7 > 2u )
      {
        v9 = *((_QWORD *)v7 + 3);
        if ( (*((_QWORD *)v8 + 2) & 0x200000000000LL) != 0 && (v9 & 0x200000000000LL) == v9 )
        {
          v10 = a1[34];
          v22 = *(_QWORD *)(v6 + 120);
          v23 = *(_QWORD *)(v6 + 112);
          v31 = *(_DWORD *)(v6 + 104);
          v24 = *(_QWORD *)(v6 + 96);
          v25 = *(_QWORD *)(v6 + 88);
          v30 = *(_DWORD *)(v6 + 80);
          v26 = *(_QWORD *)(v6 + 72);
          LODWORD(v32) = *(_DWORD *)(v6 + 32);
          v27 = *(_QWORD *)(v6 + 24);
          LODWORD(v33) = *(_DWORD *)v6;
          v28 = *(_QWORD *)(v6 + 128);
          v19 = *(_DWORD *)(v6 + 64);
          v29[0] = *(_QWORD *)(v6 + 56);
          v20 = *(_DWORD *)(v6 + 8);
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v8,
            (unsigned int)byte_180047B4B,
            v10 + 8,
            (_DWORD)v8,
            (__int64)&v21,
            (__int64)&v20,
            (__int64)v29,
            (__int64)&v19,
            (__int64)&v28,
            (__int64)&v33,
            (__int64)&v27,
            (__int64)&v32,
            (__int64)&v26,
            (__int64)&v30,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v31,
            (__int64)&v23,
            (__int64)&v22);
        }
      }
    }
    else
    {
      v11 = MDMPushProvider::Provider();
      v12 = v11;
      if ( *(_DWORD *)v11 > 2u )
      {
        v13 = *((_QWORD *)v11 + 3);
        if ( (*((_QWORD *)v12 + 2) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
        {
          v14 = a1[34];
          v32 = *(_QWORD *)(v14 + 56);
          v33 = *(_QWORD *)(v14 + 48);
          CurrentThreadId = GetCurrentThreadId();
          v16 = a1[34];
          v31 = CurrentThreadId;
          v30 = a2;
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v12,
            (unsigned int)word_180047C62,
            v16 + 8,
            v17,
            (__int64)&v21,
            (__int64)&v30,
            (__int64)&v31,
            (__int64)&v33,
            (__int64)&v32);
        }
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18002d45c  push    rbp
0x18002d45e  push    rbx
0x18002d45f  push    rsi
0x18002d460  push    rdi
0x18002d461  lea     rbp, [rsp-3Fh]
0x18002d466  sub     rsp, 0F8h
0x18002d46d  mov     esi, edx
0x18002d46f  mov     rbx, rcx
0x18002d472  test    edx, edx
0x18002d474  jns     loc_18002D6A3
0x18002d47a  mov     rdi, [rcx+110h]
0x18002d481  mov     eax, [rdi+48h]
0x18002d484  test    eax, eax
0x18002d486  jns     loc_18002D5FC
0x18002d48c  add     rdi, 50h ; 'P'
0x18002d490  cmp     eax, [rdi+8]
0x18002d493  jnz     loc_18002D5FC
0x18002d499  test    rdi, rdi
0x18002d49c  jz      loc_18002D5FC
0x18002d4a2  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002d4a7  mov     r9, rax
0x18002d4aa  mov     ecx, [rax]
0x18002d4ac  cmp     ecx, 2
0x18002d4af  jbe     loc_18002D6A3
0x18002d4b5  mov     rax, [rax+18h]
0x18002d4b9  mov     rdx, 200000000000h
0x18002d4c3  mov     rcx, [r9+10h]
0x18002d4c7  test    rdx, rcx
0x18002d4ca  jz      loc_18002D6A3
0x18002d4d0  mov     rcx, rax
0x18002d4d3  and     rcx, rdx
0x18002d4d6  cmp     rcx, rax
0x18002d4d9  jnz     loc_18002D6A3
0x18002d4df  mov     rax, [rdi+78h]
0x18002d4e3  lea     rdx, byte_180047B4B
0x18002d4ea  mov     r8, [rbx+110h]
0x18002d4f1  mov     rcx, r9
0x18002d4f4  mov     [rbp+57h+var_60], rax
0x18002d4f8  add     r8, 8
0x18002d4fc  mov     rax, [rdi+70h]
0x18002d500  mov     [rbp+57h+var_58], rax
0x18002d504  mov     eax, [rdi+68h]
0x18002d507  mov     [rbp+57h+arg_8], eax
0x18002d50a  mov     rax, [rdi+60h]
0x18002d50e  mov     [rbp+57h+var_50], rax
0x18002d512  mov     rax, [rdi+58h]
0x18002d516  mov     [rbp+57h+var_48], rax
0x18002d51a  mov     eax, [rdi+50h]
0x18002d51d  mov     [rbp+57h+arg_0], eax
0x18002d520  mov     rax, [rdi+48h]
0x18002d524  mov     [rbp+57h+var_40], rax
0x18002d528  mov     eax, [rdi+20h]
0x18002d52b  mov     dword ptr [rbp+57h+arg_10], eax
0x18002d52e  mov     rax, [rdi+18h]
0x18002d532  mov     [rbp+57h+var_38], rax
0x18002d536  mov     eax, [rdi]
0x18002d538  mov     dword ptr [rbp+57h+arg_18], eax
0x18002d53b  mov     rax, [rdi+80h]
0x18002d542  mov     [rbp+57h+var_30], rax
0x18002d546  mov     eax, [rdi+40h]
0x18002d549  mov     [rbp+57h+var_70], eax
0x18002d54c  mov     rax, [rdi+38h]
0x18002d550  mov     [rbp+57h+var_28], rax
0x18002d554  mov     eax, [rdi+8]
0x18002d557  mov     [rbp+57h+var_6C], eax
0x18002d55a  lea     rax, [rbp+57h+var_60]
0x18002d55e  mov     [rsp+110h+var_80], rax
0x18002d566  lea     rax, [rbp+57h+var_58]
0x18002d56a  mov     [rsp+110h+var_88], rax
0x18002d572  lea     rax, [rbp+57h+arg_8]
0x18002d576  mov     [rsp+110h+var_90], rax
0x18002d57e  lea     rax, [rbp+57h+var_50]
0x18002d582  mov     [rsp+110h+var_98], rax
0x18002d587  lea     rax, [rbp+57h+var_48]
0x18002d58b  mov     [rsp+110h+var_A0], rax
0x18002d590  lea     rax, [rbp+57h+arg_0]
0x18002d594  mov     [rsp+110h+var_A8], rax
0x18002d599  lea     rax, [rbp+57h+var_40]
0x18002d59d  mov     [rsp+110h+var_B0], rax
0x18002d5a2  lea     rax, [rbp+57h+arg_10]
0x18002d5a6  mov     [rsp+110h+var_B8], rax
0x18002d5ab  lea     rax, [rbp+57h+var_38]
0x18002d5af  mov     [rsp+110h+var_C0], rax
0x18002d5b4  lea     rax, [rbp+57h+arg_18]
0x18002d5b8  mov     [rsp+110h+var_C8], rax
0x18002d5bd  lea     rax, [rbp+57h+var_30]
0x18002d5c1  mov     [rsp+110h+var_D0], rax
0x18002d5c6  lea     rax, [rbp+57h+var_70]
0x18002d5ca  mov     [rsp+110h+var_D8], rax
0x18002d5cf  lea     rax, [rbp+57h+var_28]
0x18002d5d3  mov     [rsp+110h+var_E0], rax
0x18002d5d8  lea     rax, [rbp+57h+var_6C]
0x18002d5dc  mov     [rsp+110h+var_E8], rax
0x18002d5e1  lea     rax, [rbp+57h+var_68]
0x18002d5e5  mov     [rsp+110h+var_F0], rax
0x18002d5ea  mov     [rbp+57h+var_68], 1000000h
0x18002d5f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002d5f7  jmp     loc_18002D6A3
0x18002d5fc  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002d601  mov     rdi, rax
0x18002d604  mov     ecx, [rax]
0x18002d606  cmp     ecx, 2
0x18002d609  jbe     loc_18002D6A3
0x18002d60f  mov     rax, [rax+18h]
0x18002d613  mov     rdx, 200000000000h
0x18002d61d  mov     rcx, [rdi+10h]
0x18002d621  test    rdx, rcx
0x18002d624  jz      short loc_18002D6A3
0x18002d626  mov     rcx, rax
0x18002d629  and     rcx, rdx
0x18002d62c  cmp     rcx, rax
0x18002d62f  jnz     short loc_18002D6A3
0x18002d631  mov     rcx, [rbx+110h]
0x18002d638  mov     rax, [rcx+38h]
0x18002d63c  mov     [rbp+57h+arg_10], rax
0x18002d640  mov     rax, [rcx+30h]
0x18002d644  mov     [rbp+57h+arg_18], rax
0x18002d648  call    cs:__imp_GetCurrentThreadId
0x18002d64e  mov     r8, [rbx+110h]
0x18002d655  lea     rdx, word_180047C62
0x18002d65c  mov     [rbp+57h+arg_8], eax
0x18002d65f  add     r8, 8
0x18002d663  lea     rax, [rbp+57h+arg_10]
0x18002d667  mov     [rbp+57h+arg_0], esi
0x18002d66a  mov     [rsp+110h+var_D0], rax
0x18002d66f  mov     rcx, rdi
0x18002d672  lea     rax, [rbp+57h+arg_18]
0x18002d676  mov     [rbp+57h+var_68], 1000000h
0x18002d67e  mov     [rsp+110h+var_D8], rax
0x18002d683  lea     rax, [rbp+57h+arg_8]
0x18002d687  mov     [rsp+110h+var_E0], rax
0x18002d68c  lea     rax, [rbp+57h+arg_0]
0x18002d690  mov     [rsp+110h+var_E8], rax
0x18002d695  lea     rax, [rbp+57h+var_68]
0x18002d699  mov     [rsp+110h+var_F0], rax
0x18002d69e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002d6a3  mov     rax, [rbx]
0x18002d6a6  mov     rcx, rbx
0x18002d6a9  mov     rax, [rax+8]
0x18002d6ad  add     rsp, 0F8h
0x18002d6b4  pop     rdi
0x18002d6b5  pop     rsi
0x18002d6b6  pop     rbx
0x18002d6b7  pop     rbp
0x18002d6b8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
