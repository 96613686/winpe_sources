# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180030d88`
- end: `0x180030ffa`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U2@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444444AEBU?$_tlgWrapSz@G@@4544443@Z`
- size: `626`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180080ed4`

## callees

- `0x180030d88`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180030fbe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180030fbe`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  __int64 v22; // rcx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  int v27; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+6Ch] [rbp-94h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  __int64 v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  __int64 v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  __int64 v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v52; // [rsp+100h] [rbp+0h]
  int v53; // [rsp+108h] [rbp+8h]
  int v54; // [rsp+10Ch] [rbp+Ch]
  __int64 v55; // [rsp+110h] [rbp+10h]
  __int64 v56; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v57; // [rsp+120h] [rbp+20h]
  int v58; // [rsp+128h] [rbp+28h]
  int v59; // [rsp+12Ch] [rbp+2Ch]
  __int64 v60; // [rsp+130h] [rbp+30h]
  __int64 v61; // [rsp+138h] [rbp+38h]
  __int64 v62; // [rsp+140h] [rbp+40h]
  __int64 v63; // [rsp+148h] [rbp+48h]
  __int64 v64; // [rsp+150h] [rbp+50h]
  __int64 v65; // [rsp+158h] [rbp+58h]
  __int64 v66; // [rsp+160h] [rbp+60h]
  __int64 v67; // [rsp+168h] [rbp+68h]
  __int64 v68; // [rsp+170h] [rbp+70h]
  __int64 v69; // [rsp+178h] [rbp+78h]

  v68 = a21;
  v22 = -1;
  v66 = a20;
  v64 = a19;
  v62 = a18;
  v60 = a17;
  v69 = 8;
  v67 = 4;
  v65 = 4;
  v23 = *a16;
  v63 = 4;
  v61 = 4;
  if ( v23 )
  {
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    v25 = 2 * v24 + 2;
  }
  else
  {
    v23 = &qword_18009CA18;
    v25 = 2;
  }
  v58 = v25;
  v55 = a15;
  v57 = v23;
  v59 = 0;
  v56 = 4;
  v26 = *a14;
  if ( *a14 )
  {
    do
      ++v22;
    while ( v26[v22] );
    v27 = 2 * v22 + 2;
  }
  else
  {
    v26 = &qword_18009CA18;
    v27 = 2;
  }
  v50 = a13;
  v48 = a12;
  v46 = a11;
  v44 = a10;
  v42 = a9;
  v40 = a8;
  v38 = a7;
  v36 = a6;
  v34 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1800C62A8;
  v53 = v27;
  v52 = v26;
  v54 = 0;
  v51 = 4;
  v49 = 4;
  v47 = 4;
  v45 = 4;
  v43 = 4;
  v41 = 4;
  v39 = 4;
  v37 = 4;
  v35 = 8;
  UserData.Size = *(unsigned __int16 *)off_1800C62A8;
  v32 = *(unsigned __int16 *)(a2 + 11);
  v31 = a2 + 11;
  UserData.Reserved = 2;
  v33 = 1;
  return EventWriteTransfer(qword_1800C62C0, &EventDescriptor, 0, 0, 0x13u, &UserData);
}

```

## disassembly

```asm
0x180030d88  push    rbp
0x180030d8a  lea     rbp, [rsp-90h]
0x180030d92  sub     rsp, 190h
0x180030d99  mov     rax, cs:__security_cookie
0x180030da0  xor     rax, rsp
0x180030da3  mov     [rbp+90h+var_10], rax
0x180030daa  mov     rax, [rbp+90h+arg_A0]
0x180030db1  xor     r9d, r9d; RelatedActivityId
0x180030db4  mov     [rbp+90h+var_20], rax
0x180030db8  mov     r8, rdx
0x180030dbb  mov     rax, [rbp+90h+arg_98]
0x180030dc2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180030dc6  mov     [rbp+90h+var_30], rax
0x180030dca  mov     rax, [rbp+90h+arg_90]
0x180030dd1  lea     r11d, [r9+2]
0x180030dd5  mov     [rbp+90h+var_40], rax
0x180030dd9  mov     rax, [rbp+90h+arg_88]
0x180030de0  mov     [rbp+90h+var_50], rax
0x180030de4  mov     rax, [rbp+90h+arg_80]
0x180030deb  mov     [rbp+90h+var_60], rax
0x180030def  mov     rax, [rbp+90h+arg_78]
0x180030df6  mov     [rbp+90h+var_18], 8
0x180030dfe  mov     [rbp+90h+var_28], 4
0x180030e06  mov     [rbp+90h+var_38], 4
0x180030e0e  mov     rdx, [rax]
0x180030e11  mov     [rbp+90h+var_48], 4
0x180030e19  mov     [rbp+90h+var_58], 4
0x180030e21  test    rdx, rdx
0x180030e24  jz      loc_180030FDC
0x180030e2a  mov     rax, rcx
0x180030e2d  inc     rax
0x180030e30  cmp     [rdx+rax*2], r9w
0x180030e35  jnz     short loc_180030E2D
0x180030e37  lea     eax, ds:2[rax*2]
0x180030e3e  mov     [rbp+90h+var_68], eax
0x180030e41  mov     rax, [rbp+90h+arg_70]
0x180030e48  mov     [rbp+90h+var_80], rax
0x180030e4c  mov     rax, [rbp+90h+arg_68]
0x180030e53  mov     [rbp+90h+var_70], rdx
0x180030e57  mov     [rbp+90h+var_64], r9d
0x180030e5b  mov     [rbp+90h+var_78], 4
0x180030e63  mov     rdx, [rax]
0x180030e66  test    rdx, rdx
0x180030e69  jz      loc_180030FEB
0x180030e6f  inc     rcx
0x180030e72  cmp     [rdx+rcx*2], r9w
0x180030e77  jnz     short loc_180030E6F
0x180030e79  lea     ecx, ds:2[rcx*2]
0x180030e80  mov     rax, [rbp+90h+arg_60]
0x180030e87  mov     [rbp+90h+var_A0], rax
0x180030e8b  mov     rax, [rbp+90h+arg_58]
0x180030e92  mov     [rbp+90h+var_B0], rax
0x180030e96  mov     rax, [rbp+90h+arg_50]
0x180030e9d  mov     [rbp+90h+var_C0], rax
0x180030ea1  mov     rax, [rbp+90h+arg_48]
0x180030ea8  mov     [rbp+90h+var_D0], rax
0x180030eac  mov     rax, [rbp+90h+arg_40]
0x180030eb3  mov     [rbp+90h+var_E0], rax
0x180030eb7  mov     rax, [rbp+90h+arg_38]
0x180030ebe  mov     [rbp+90h+var_F0], rax
0x180030ec2  mov     rax, [rbp+90h+arg_30]
0x180030ec9  mov     [rbp+90h+var_100], rax
0x180030ecd  mov     rax, [rbp+90h+arg_28]
0x180030ed4  mov     [rbp+90h+var_110], rax
0x180030ed8  mov     rax, [rbp+90h+arg_20]
0x180030edf  mov     [rsp+190h+var_120], rax
0x180030ee4  movzx   eax, byte ptr [r8]
0x180030ee8  shl     eax, 18h
0x180030eeb  mov     dword ptr [rsp+190h+EventDescriptor.Id], eax
0x180030eef  movzx   eax, word ptr [r8+1]
0x180030ef4  mov     dword ptr [rsp+190h+EventDescriptor.Level], eax
0x180030ef8  mov     rax, [r8+3]
0x180030efc  mov     [rsp+190h+EventDescriptor.Keyword], rax
0x180030f01  mov     rax, cs:off_1800C62A8
0x180030f08  mov     [rsp+190h+var_140.Ptr], rax
0x180030f0d  mov     [rbp+90h+var_88], ecx
0x180030f10  lea     rcx, [r8+0Bh]
0x180030f14  mov     [rbp+90h+var_90], rdx
0x180030f18  xor     r8d, r8d; ActivityId
0x180030f1b  mov     [rbp+90h+var_84], r9d
0x180030f1f  lea     rdx, [rsp+190h+EventDescriptor]; EventDescriptor
0x180030f24  mov     [rbp+90h+var_98], 4
0x180030f2c  mov     [rbp+90h+var_A8], 4
0x180030f34  mov     [rbp+90h+var_B8], 4
0x180030f3c  mov     [rbp+90h+var_C8], 4
0x180030f44  mov     [rbp+90h+var_D8], 4
0x180030f4c  mov     [rbp+90h+var_E8], 4
0x180030f54  mov     [rbp+90h+var_F8], 4
0x180030f5c  mov     [rbp+90h+var_108], 4
0x180030f64  mov     [rsp+190h+var_118], 8
0x180030f6d  movzx   eax, word ptr [rax]
0x180030f70  mov     [rsp+190h+var_140.Size], eax
0x180030f74  movzx   eax, word ptr [rcx]
0x180030f77  mov     [rsp+190h+var_128], eax
0x180030f7b  lea     rax, _TraceLoggingMetadataEnd
0x180030f82  mov     [rsp+190h+var_130], rcx
0x180030f87  lea     rcx, _TraceLoggingMetadata
0x180030f8e  sub     eax, ecx
0x180030f90  mov     dword ptr [rsp+190h+var_140.0Ch], r11d
0x180030f95  mov     [rsp+190h+var_124], 1
0x180030f9d  mov     [rsp+190h+var_160], eax
0x180030fa1  mov     eax, [rsp+190h+var_160]
0x180030fa5  mov     rcx, cs:qword_1800C62C0; RegHandle
0x180030fac  lea     rax, [rsp+190h+var_140]
0x180030fb1  mov     [rsp+190h+UserData], rax; UserData
0x180030fb6  mov     [rsp+190h+UserDataCount], 13h; UserDataCount
0x180030fbe  call    cs:__imp_EventWriteTransfer
0x180030fc4  mov     rcx, [rbp+90h+var_10]
0x180030fcb  xor     rcx, rsp; StackCookie
0x180030fce  call    __security_check_cookie
0x180030fd3  add     rsp, 190h
0x180030fda  pop     rbp
0x180030fdb  retn
0x180030fdc  lea     rdx, qword_18009CA18
0x180030fe3  mov     eax, r11d
0x180030fe6  jmp     loc_180030E3E
0x180030feb  lea     rdx, qword_18009CA18
0x180030ff2  mov     ecx, r11d
0x180030ff5  jmp     loc_180030E80
```
