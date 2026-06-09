# wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18000f2cc`
- end: `0x18000f537`
- name: `?ReportStopActivity@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `619`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000dc48`
- `0x180010418`

## callees

- `0x1800016f0`
- `0x1800017ec`
- `0x18000895c`
- `0x18000f2cc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f4bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f4bc`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
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
      v7 = ContainerProvider::Provider();
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
            (unsigned int)byte_18003B7CB,
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
      v11 = ContainerProvider::Provider();
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
            (unsigned int)&byte_18003C7D7,
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
0x18000f2cc  push    rbp
0x18000f2ce  push    rbx
0x18000f2cf  push    rsi
0x18000f2d0  push    rdi
0x18000f2d1  lea     rbp, [rsp-3Fh]
0x18000f2d6  sub     rsp, 0F8h
0x18000f2dd  mov     esi, edx
0x18000f2df  mov     rbx, rcx
0x18000f2e2  test    edx, edx
0x18000f2e4  jns     loc_18000F51D
0x18000f2ea  mov     rdi, [rcx+110h]
0x18000f2f1  mov     eax, [rdi+48h]
0x18000f2f4  test    eax, eax
0x18000f2f6  jns     loc_18000F46C
0x18000f2fc  add     rdi, 50h ; 'P'
0x18000f300  cmp     eax, [rdi+8]
0x18000f303  jnz     loc_18000F46C
0x18000f309  test    rdi, rdi
0x18000f30c  jz      loc_18000F46C
0x18000f312  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000f317  mov     r9, rax
0x18000f31a  mov     ecx, [rax]
0x18000f31c  cmp     ecx, 2
0x18000f31f  jbe     loc_18000F51D
0x18000f325  mov     rax, [rax+18h]
0x18000f329  mov     rdx, 200000000000h
0x18000f333  mov     rcx, [r9+10h]
0x18000f337  test    rdx, rcx
0x18000f33a  jz      loc_18000F51D
0x18000f340  mov     rcx, rax
0x18000f343  and     rcx, rdx
0x18000f346  cmp     rcx, rax
0x18000f349  jnz     loc_18000F51D
0x18000f34f  mov     rax, [rdi+78h]
0x18000f353  lea     rdx, byte_18003B7CB
0x18000f35a  mov     r8, [rbx+110h]
0x18000f361  mov     rcx, r9
0x18000f364  mov     [rbp+57h+var_60], rax
0x18000f368  add     r8, 8
0x18000f36c  mov     rax, [rdi+70h]
0x18000f370  mov     [rbp+57h+var_58], rax
0x18000f374  mov     eax, [rdi+68h]
0x18000f377  mov     [rbp+57h+arg_8], eax
0x18000f37a  mov     rax, [rdi+60h]
0x18000f37e  mov     [rbp+57h+var_50], rax
0x18000f382  mov     rax, [rdi+58h]
0x18000f386  mov     [rbp+57h+var_48], rax
0x18000f38a  mov     eax, [rdi+50h]
0x18000f38d  mov     [rbp+57h+arg_0], eax
0x18000f390  mov     rax, [rdi+48h]
0x18000f394  mov     [rbp+57h+var_40], rax
0x18000f398  mov     eax, [rdi+20h]
0x18000f39b  mov     dword ptr [rbp+57h+arg_10], eax
0x18000f39e  mov     rax, [rdi+18h]
0x18000f3a2  mov     [rbp+57h+var_38], rax
0x18000f3a6  mov     eax, [rdi]
0x18000f3a8  mov     dword ptr [rbp+57h+arg_18], eax
0x18000f3ab  mov     rax, [rdi+80h]
0x18000f3b2  mov     [rbp+57h+var_30], rax
0x18000f3b6  mov     eax, [rdi+40h]
0x18000f3b9  mov     [rbp+57h+var_70], eax
0x18000f3bc  mov     rax, [rdi+38h]
0x18000f3c0  mov     [rbp+57h+var_28], rax
0x18000f3c4  mov     eax, [rdi+8]
0x18000f3c7  mov     [rbp+57h+var_6C], eax
0x18000f3ca  lea     rax, [rbp+57h+var_60]
0x18000f3ce  mov     [rsp+110h+var_80], rax
0x18000f3d6  lea     rax, [rbp+57h+var_58]
0x18000f3da  mov     [rsp+110h+var_88], rax
0x18000f3e2  lea     rax, [rbp+57h+arg_8]
0x18000f3e6  mov     [rsp+110h+var_90], rax
0x18000f3ee  lea     rax, [rbp+57h+var_50]
0x18000f3f2  mov     [rsp+110h+var_98], rax
0x18000f3f7  lea     rax, [rbp+57h+var_48]
0x18000f3fb  mov     [rsp+110h+var_A0], rax
0x18000f400  lea     rax, [rbp+57h+arg_0]
0x18000f404  mov     [rsp+110h+var_A8], rax
0x18000f409  lea     rax, [rbp+57h+var_40]
0x18000f40d  mov     [rsp+110h+var_B0], rax
0x18000f412  lea     rax, [rbp+57h+arg_10]
0x18000f416  mov     [rsp+110h+var_B8], rax
0x18000f41b  lea     rax, [rbp+57h+var_38]
0x18000f41f  mov     [rsp+110h+var_C0], rax
0x18000f424  lea     rax, [rbp+57h+arg_18]
0x18000f428  mov     [rsp+110h+var_C8], rax
0x18000f42d  lea     rax, [rbp+57h+var_30]
0x18000f431  mov     [rsp+110h+var_D0], rax
0x18000f436  lea     rax, [rbp+57h+var_70]
0x18000f43a  mov     [rsp+110h+var_D8], rax
0x18000f43f  lea     rax, [rbp+57h+var_28]
0x18000f443  mov     [rsp+110h+var_E0], rax
0x18000f448  lea     rax, [rbp+57h+var_6C]
0x18000f44c  mov     [rsp+110h+var_E8], rax
0x18000f451  lea     rax, [rbp+57h+var_68]
0x18000f455  mov     [rsp+110h+var_F0], rax
0x18000f45a  mov     [rbp+57h+var_68], 1000000h
0x18000f462  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f467  jmp     loc_18000F51D
0x18000f46c  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000f471  mov     rdi, rax
0x18000f474  mov     ecx, [rax]
0x18000f476  cmp     ecx, 2
0x18000f479  jbe     loc_18000F51D
0x18000f47f  mov     rax, [rax+18h]
0x18000f483  mov     rdx, 200000000000h
0x18000f48d  mov     rcx, [rdi+10h]
0x18000f491  test    rdx, rcx
0x18000f494  jz      loc_18000F51D
0x18000f49a  mov     rcx, rax
0x18000f49d  and     rcx, rdx
0x18000f4a0  cmp     rcx, rax
0x18000f4a3  jnz     short loc_18000F51D
0x18000f4a5  mov     rcx, [rbx+110h]
0x18000f4ac  mov     rax, [rcx+38h]
0x18000f4b0  mov     [rbp+57h+arg_10], rax
0x18000f4b4  mov     rax, [rcx+30h]
0x18000f4b8  mov     [rbp+57h+arg_18], rax
0x18000f4bc  call    cs:__imp_GetCurrentThreadId
0x18000f4c3  nop     dword ptr [rax+rax+00h]
0x18000f4c8  mov     r8, [rbx+110h]
0x18000f4cf  lea     rdx, byte_18003C7D7
0x18000f4d6  mov     [rbp+57h+arg_8], eax
0x18000f4d9  add     r8, 8
0x18000f4dd  lea     rax, [rbp+57h+arg_10]
0x18000f4e1  mov     [rbp+57h+arg_0], esi
0x18000f4e4  mov     [rsp+110h+var_D0], rax
0x18000f4e9  mov     rcx, rdi
0x18000f4ec  lea     rax, [rbp+57h+arg_18]
0x18000f4f0  mov     [rbp+57h+var_68], 1000000h
0x18000f4f8  mov     [rsp+110h+var_D8], rax
0x18000f4fd  lea     rax, [rbp+57h+arg_8]
0x18000f501  mov     [rsp+110h+var_E0], rax
0x18000f506  lea     rax, [rbp+57h+arg_0]
0x18000f50a  mov     [rsp+110h+var_E8], rax
0x18000f50f  lea     rax, [rbp+57h+var_68]
0x18000f513  mov     [rsp+110h+var_F0], rax
0x18000f518  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f51d  mov     rax, [rbx]
0x18000f520  mov     rcx, rbx
0x18000f523  mov     rax, [rax+8]
0x18000f527  add     rsp, 0F8h
0x18000f52e  pop     rdi
0x18000f52f  pop     rsi
0x18000f530  pop     rbx
0x18000f531  pop     rbp
0x18000f532  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
