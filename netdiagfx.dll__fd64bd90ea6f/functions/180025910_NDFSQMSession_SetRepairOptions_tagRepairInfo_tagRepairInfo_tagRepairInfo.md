# NDFSQMSession::SetRepairOptions(tagRepairInfo *,tagRepairInfo *,tagRepairInfo *)

- ea: `0x180025910`
- end: `0x180025a7d`
- name: `?SetRepairOptions@NDFSQMSession@@UEAAJPEAUtagRepairInfo@@00@Z`
- size: `365`
- prototype: `__int64 __fastcall(NDFSQMSession *__hidden this, struct tagRepairInfo *, struct tagRepairInfo *, struct tagRepairInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x180025910`
- `0x180025fe4`
- `0x1800263e0`
- `0x18002c840`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180025a3d`
- `ntdll!WinSqmAddToStream` at `0x180025a3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NDFSQMSession::SetRepairOptions(
        NDFSQMSession *this,
        struct tagRepairInfo *a2,
        struct tagRepairInfo *a3,
        struct tagRepairInfo *a4)
{
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // rdi
  unsigned __int16 *v11; // rbx
  unsigned __int16 *v12[2]; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int16 *v13[2]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int16 *v14[2]; // [rsp+40h] [rbp-29h] BYREF
  GUID guid; // [rsp+50h] [rbp-19h] BYREF
  int v16; // [rsp+60h] [rbp-9h] BYREF
  __int128 v17; // [rsp+68h] [rbp-1h] BYREF
  __int128 v18; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  if ( !a2 )
    return 2147942487LL;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v14);
  *(GUID *)v13 = a2->guid;
  AttributeConverter::GuidToString((unsigned int *)v13, (__int64)v14);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v12);
  if ( a3 )
  {
    *(GUID *)v13 = a3->guid;
    AttributeConverter::GuidToString((unsigned int *)v13, (__int64)v12);
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString((char **)v12, L"{00000000-0000-0000-0000-000000000000}", 38);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v13);
  if ( a4 )
  {
    guid = a4->guid;
    AttributeConverter::GuidToString(&guid.Data1, (__int64)v13);
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString((char **)v13, L"{00000000-0000-0000-0000-000000000000}", 38);
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v9 = v14[0];
  WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)&v16, v14[0]);
  v10 = v12[0];
  WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)((char *)&v17 + 8), v12[0]);
  v11 = v13[0];
  WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)((char *)&v18 + 8), v13[0]);
  WinSqmAddToStream(*((_QWORD *)this + 1), 1057, 3, &v16);
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  return 0;
}

```

## disassembly

```asm
0x180025910  push    rbp
0x180025912  push    rbx
0x180025913  push    rsi
0x180025914  push    rdi
0x180025915  push    r14
0x180025917  lea     rbp, [rsp-37h]
0x18002591c  sub     rsp, 0A0h
0x180025923  mov     rax, cs:__security_cookie
0x18002592a  xor     rax, rsp
0x18002592d  mov     [rbp+57h+var_30], rax
0x180025931  mov     rbx, r9
0x180025934  mov     rdi, r8
0x180025937  mov     rsi, rdx
0x18002593a  mov     r14, rcx
0x18002593d  test    rdx, rdx
0x180025940  jnz     short loc_18002594C
0x180025942  mov     eax, 80070057h
0x180025947  jmp     loc_180025A63
0x18002594c  lea     rcx, [rbp+57h+var_80]
0x180025950  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180025955  nop
0x180025956  movups  xmm0, xmmword ptr [rsi]
0x180025959  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18002595e  lea     rdx, [rbp+57h+var_80]
0x180025962  lea     rcx, [rbp+57h+var_90]
0x180025966  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002596b  lea     rcx, [rbp+57h+var_A0]
0x18002596f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180025974  nop
0x180025975  mov     esi, 26h ; '&'
0x18002597a  test    rdi, rdi
0x18002597d  jz      short loc_180025996
0x18002597f  movups  xmm0, xmmword ptr [rdi]
0x180025982  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180025987  lea     rdx, [rbp+57h+var_A0]
0x18002598b  lea     rcx, [rbp+57h+var_90]
0x18002598f  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180025994  jmp     short loc_1800259A9
0x180025996  mov     r8d, esi
0x180025999  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800259a0  lea     rcx, [rbp+57h+var_A0]
0x1800259a4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800259a9  lea     rcx, [rbp+57h+var_90]
0x1800259ad  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800259b2  nop
0x1800259b3  test    rbx, rbx
0x1800259b6  jz      short loc_1800259CF
0x1800259b8  movups  xmm0, xmmword ptr [rbx]
0x1800259bb  movdqu  [rbp+57h+var_70], xmm0
0x1800259c0  lea     rdx, [rbp+57h+var_90]
0x1800259c4  lea     rcx, [rbp+57h+var_70]
0x1800259c8  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800259cd  jmp     short loc_1800259E2
0x1800259cf  mov     r8d, esi
0x1800259d2  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800259d9  lea     rcx, [rbp+57h+var_90]
0x1800259dd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800259e2  mov     [rbp+57h+var_60], 0
0x1800259e9  xorps   xmm0, xmm0
0x1800259ec  xor     eax, eax
0x1800259ee  movups  [rbp+57h+var_58], xmm0
0x1800259f2  movups  [rbp+57h+var_48], xmm0
0x1800259f6  mov     [rbp+57h+var_38], rax
0x1800259fa  mov     rsi, [rbp+57h+var_80]
0x1800259fe  mov     rdx, rsi; unsigned __int16 *
0x180025a01  lea     rcx, [rbp+57h+var_60]; struct _SQM_STREAM_ENTRY *
0x180025a05  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180025a0a  mov     rdi, [rbp+57h+var_A0]
0x180025a0e  mov     rdx, rdi; unsigned __int16 *
0x180025a11  lea     rcx, [rbp+57h+var_58+8]; struct _SQM_STREAM_ENTRY *
0x180025a15  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180025a1a  mov     rbx, [rbp+57h+var_90]
0x180025a1e  mov     rdx, rbx; unsigned __int16 *
0x180025a21  lea     rcx, [rbp+57h+var_48+8]; struct _SQM_STREAM_ENTRY *
0x180025a25  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180025a2a  lea     r9, [rbp+57h+var_60]
0x180025a2e  mov     edx, 421h
0x180025a33  mov     r8d, 3
0x180025a39  mov     rcx, [r14+8]
0x180025a3d  call    cs:__imp_WinSqmAddToStream
0x180025a43  nop
0x180025a44  lea     rcx, [rbx-18h]; this
0x180025a48  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025a4d  nop
0x180025a4e  lea     rcx, [rdi-18h]; this
0x180025a52  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025a57  nop
0x180025a58  lea     rcx, [rsi-18h]; this
0x180025a5c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025a61  xor     eax, eax
0x180025a63  mov     rcx, [rbp+57h+var_30]
0x180025a67  xor     rcx, rsp; StackCookie
0x180025a6a  call    __security_check_cookie
0x180025a6f  add     rsp, 0A0h
0x180025a76  pop     r14
0x180025a78  pop     rdi
0x180025a79  pop     rsi
0x180025a7a  pop     rbx
0x180025a7b  pop     rbp
0x180025a7c  retn
```
