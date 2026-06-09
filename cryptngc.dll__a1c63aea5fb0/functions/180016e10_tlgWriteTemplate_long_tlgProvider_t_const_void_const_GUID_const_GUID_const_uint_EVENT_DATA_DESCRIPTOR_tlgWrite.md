# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x180016e10`
- end: `0x180017025`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U1@U1@U1@U?$_tlgWrapperByVal@$00@@U3@U3@U3@U3@U1@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4333AEBU?$_tlgWrapperByVal@$00@@5555355@Z`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035cc8`

## callees

- `0x180016e10`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017002`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017002`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const WCHAR **a6,
        const WCHAR **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18)
{
  __int64 v19; // rcx
  const WCHAR *v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  const WCHAR *v23; // rdx
  int v24; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+6Ch] [rbp-94h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  const WCHAR *v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  const WCHAR *v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+9Ch] [rbp-64h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+B8h] [rbp-48h]
  __int64 v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int64 v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+E8h] [rbp-18h]
  __int64 v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  __int64 v51; // [rsp+100h] [rbp+0h]
  __int64 v52; // [rsp+108h] [rbp+8h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  __int64 v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int64 v59; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+148h] [rbp+48h]

  v59 = a18;
  v57 = a17;
  v19 = -1;
  v55 = a16;
  v53 = a15;
  v51 = a14;
  v49 = a13;
  v47 = a12;
  v45 = a11;
  v43 = a10;
  v41 = a9;
  v39 = a8;
  v60 = 1;
  v58 = 1;
  v56 = 4;
  v20 = *a7;
  v54 = 1;
  v52 = 1;
  v50 = 1;
  v48 = 1;
  v46 = 1;
  v44 = 4;
  v42 = 4;
  v40 = 4;
  if ( v20 )
  {
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    v22 = 2 * v21 + 2;
  }
  else
  {
    v20 = &LocaleName;
    v22 = 2;
  }
  v37 = v22;
  v36 = v20;
  v38 = 0;
  v23 = *a6;
  if ( *a6 )
  {
    do
      ++v19;
    while ( v23[v19] );
    v24 = 2 * v19 + 2;
  }
  else
  {
    v23 = &LocaleName;
    v24 = 2;
  }
  v31 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18006E008;
  v34 = v24;
  v33 = v23;
  v35 = 0;
  v32 = 4;
  UserData.Size = *(unsigned __int16 *)off_18006E008;
  v29 = *(unsigned __int16 *)(a2 + 11);
  v28 = a2 + 11;
  UserData.Reserved = 2;
  v30 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0x10u, &UserData);
}

```

## disassembly

```asm
0x180016e10  mov     [rsp-8+arg_0], rbx
0x180016e15  push    rbp
0x180016e16  lea     rbp, [rsp-60h]
0x180016e1b  sub     rsp, 160h
0x180016e22  mov     rax, cs:__security_cookie
0x180016e29  xor     rax, rsp
0x180016e2c  mov     [rbp+60h+var_10], rax
0x180016e30  mov     rax, [rbp+60h+arg_88]
0x180016e37  mov     r10d, 1
0x180016e3d  mov     [rbp+60h+var_20], rax
0x180016e41  mov     r8, rdx
0x180016e44  mov     rax, [rbp+60h+arg_80]
0x180016e4b  xor     r9d, r9d; RelatedActivityId
0x180016e4e  mov     [rbp+60h+var_30], rax
0x180016e52  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016e56  mov     rax, [rbp+60h+arg_78]
0x180016e5d  lea     r11d, [r10+1]
0x180016e61  mov     [rbp+60h+var_40], rax
0x180016e65  mov     rax, [rbp+60h+arg_70]
0x180016e6c  mov     [rbp+60h+var_50], rax
0x180016e70  mov     rax, [rbp+60h+arg_68]
0x180016e77  mov     [rbp+60h+var_60], rax
0x180016e7b  mov     rax, [rbp+60h+arg_60]
0x180016e82  mov     [rbp+60h+var_70], rax
0x180016e86  mov     rax, [rbp+60h+arg_58]
0x180016e8d  mov     [rbp+60h+var_80], rax
0x180016e91  mov     rax, [rbp+60h+arg_50]
0x180016e98  mov     [rbp+60h+var_90], rax
0x180016e9c  mov     rax, [rbp+60h+arg_48]
0x180016ea3  mov     [rbp+60h+var_A0], rax
0x180016ea7  mov     rax, [rbp+60h+arg_40]
0x180016eae  mov     [rbp+60h+var_B0], rax
0x180016eb2  mov     rax, [rbp+60h+arg_38]
0x180016eb9  mov     [rbp+60h+var_C0], rax
0x180016ebd  mov     rax, [rbp+60h+arg_30]
0x180016ec4  mov     [rbp+60h+var_18], r10
0x180016ec8  mov     [rbp+60h+var_28], r10
0x180016ecc  mov     [rbp+60h+var_38], 4
0x180016ed4  mov     rdx, [rax]
0x180016ed7  mov     [rbp+60h+var_48], r10
0x180016edb  mov     [rbp+60h+var_58], r10
0x180016edf  mov     [rbp+60h+var_68], r10
0x180016ee3  mov     [rbp+60h+var_78], r10
0x180016ee7  mov     [rbp+60h+var_88], r10
0x180016eeb  mov     [rbp+60h+var_98], 4
0x180016ef3  mov     [rbp+60h+var_A8], 4
0x180016efb  mov     [rbp+60h+var_B8], 4
0x180016f03  test    rdx, rdx
0x180016f06  jz      short loc_180016F1E
0x180016f08  mov     rax, rcx
0x180016f0b  inc     rax
0x180016f0e  cmp     [rdx+rax*2], r9w
0x180016f13  jnz     short loc_180016F0B
0x180016f15  lea     eax, ds:2[rax*2]
0x180016f1c  jmp     short loc_180016F28
0x180016f1e  lea     rdx, LocaleName
0x180016f25  mov     eax, r11d
0x180016f28  mov     [rbp+60h+var_C8], eax
0x180016f2b  mov     rax, [rbp+60h+arg_28]
0x180016f32  mov     [rbp+60h+var_D0], rdx
0x180016f36  mov     [rbp+60h+var_C4], r9d
0x180016f3a  mov     rdx, [rax]
0x180016f3d  test    rdx, rdx
0x180016f40  jz      short loc_180016F55
0x180016f42  inc     rcx
0x180016f45  cmp     [rdx+rcx*2], r9w
0x180016f4a  jnz     short loc_180016F42
0x180016f4c  lea     ecx, ds:2[rcx*2]
0x180016f53  jmp     short loc_180016F5F
0x180016f55  lea     rdx, LocaleName
0x180016f5c  mov     ecx, r11d
0x180016f5f  mov     rax, [rbp+60h+arg_20]
0x180016f66  mov     [rsp+160h+var_F0], rax
0x180016f6b  movzx   eax, byte ptr [r8]
0x180016f6f  shl     eax, 18h
0x180016f72  mov     dword ptr [rsp+160h+EventDescriptor.Id], eax
0x180016f76  movzx   eax, word ptr [r8+1]
0x180016f7b  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x180016f7f  mov     rax, [r8+3]
0x180016f83  mov     [rsp+160h+EventDescriptor.Keyword], rax
0x180016f88  mov     rax, cs:off_18006E008
0x180016f8f  mov     [rsp+160h+var_110.Ptr], rax
0x180016f94  mov     [rbp+60h+var_D8], ecx
0x180016f97  lea     rcx, [r8+0Bh]
0x180016f9b  mov     [rbp+60h+var_E0], rdx
0x180016f9f  xor     r8d, r8d; ActivityId
0x180016fa2  mov     [rbp+60h+var_D4], r9d
0x180016fa6  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x180016fab  mov     [rsp+160h+var_E8], 4
0x180016fb4  movzx   eax, word ptr [rax]
0x180016fb7  mov     [rsp+160h+var_110.Size], eax
0x180016fbb  movzx   eax, word ptr [rcx]
0x180016fbe  mov     [rsp+160h+var_F8], eax
0x180016fc2  lea     rax, _TraceLoggingMetadataEnd
0x180016fc9  mov     [rsp+160h+var_100], rcx
0x180016fce  lea     rcx, _TraceLoggingMetadata
0x180016fd5  sub     eax, ecx
0x180016fd7  mov     dword ptr [rsp+160h+var_110.0Ch], r11d
0x180016fdc  mov     [rsp+160h+var_F4], r10d
0x180016fe1  mov     [rsp+160h+var_130], eax
0x180016fe5  mov     eax, [rsp+160h+var_130]
0x180016fe9  mov     rcx, cs:RegHandle; RegHandle
0x180016ff0  lea     rax, [rsp+160h+var_110]
0x180016ff5  mov     [rsp+160h+UserData], rax; UserData
0x180016ffa  mov     [rsp+160h+UserDataCount], 10h; UserDataCount
0x180017002  call    cs:__imp_EventWriteTransfer
0x180017008  mov     rcx, [rbp+60h+var_10]
0x18001700c  xor     rcx, rsp; StackCookie
0x18001700f  call    __security_check_cookie
0x180017014  mov     rbx, [rsp+160h+arg_0]
0x18001701c  add     rsp, 160h
0x180017023  pop     rbp
0x180017024  retn
```
