# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180016888`
- end: `0x180016b20`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@4333333333333333@Z`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003da28`

## callees

- `0x180016888`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016b00`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016b00`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        const WCHAR **a7,
        const WCHAR **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23)
{
  __int64 v26; // rcx
  const WCHAR *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  const WCHAR *v30; // rdx
  int v31; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+68h] [rbp-98h]
  int v37; // [rsp+6Ch] [rbp-94h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  __int64 v40; // [rsp+80h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-78h]
  const WCHAR *v42; // [rsp+90h] [rbp-70h]
  int v43; // [rsp+98h] [rbp-68h]
  int v44; // [rsp+9Ch] [rbp-64h]
  const WCHAR *v45; // [rsp+A0h] [rbp-60h]
  int v46; // [rsp+A8h] [rbp-58h]
  int v47; // [rsp+ACh] [rbp-54h]
  __int64 v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  __int64 v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  __int64 v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  __int64 v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+108h] [rbp+8h]
  __int64 v60; // [rsp+110h] [rbp+10h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  __int64 v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  __int64 v64; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  __int64 v66; // [rsp+140h] [rbp+40h]
  __int64 v67; // [rsp+148h] [rbp+48h]
  __int64 v68; // [rsp+150h] [rbp+50h]
  __int64 v69; // [rsp+158h] [rbp+58h]
  __int64 v70; // [rsp+160h] [rbp+60h]
  __int64 v71; // [rsp+168h] [rbp+68h]
  __int64 v72; // [rsp+170h] [rbp+70h]
  __int64 v73; // [rsp+178h] [rbp+78h]
  __int64 v74; // [rsp+180h] [rbp+80h]
  __int64 v75; // [rsp+188h] [rbp+88h]
  __int64 v76; // [rsp+190h] [rbp+90h]
  __int64 v77; // [rsp+198h] [rbp+98h]

  v76 = a23;
  v74 = a22;
  v26 = -1;
  v72 = a21;
  v70 = a20;
  v68 = a19;
  v66 = a18;
  v64 = a17;
  v62 = a16;
  v60 = a15;
  v58 = a14;
  v56 = a13;
  v54 = a12;
  v52 = a11;
  v50 = a10;
  v48 = a9;
  v77 = 4;
  v75 = 4;
  v73 = 4;
  v27 = *a8;
  v71 = 4;
  v69 = 4;
  v67 = 4;
  v65 = 4;
  v63 = 4;
  v61 = 4;
  v59 = 4;
  v57 = 4;
  v55 = 4;
  v53 = 4;
  v51 = 4;
  v49 = 4;
  if ( v27 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &LocaleName;
    v29 = 2;
  }
  v46 = v29;
  v45 = v27;
  v47 = 0;
  v30 = *a7;
  if ( *a7 )
  {
    do
      ++v26;
    while ( v30[v26] );
    v31 = 2 * v26 + 2;
  }
  else
  {
    v30 = &LocaleName;
    v31 = 2;
  }
  v40 = a6;
  v38 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v43 = v31;
  v42 = v30;
  v44 = 0;
  v41 = 4;
  v39 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v36 = *(unsigned __int16 *)(a2 + 11);
  v35 = a2 + 11;
  UserData.Reserved = 2;
  v37 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 0x15u, &UserData);
}

```

## disassembly

```asm
0x180016888  push    rbp
0x18001688a  push    rbx
0x18001688b  push    rdi
0x18001688c  lea     rbp, [rsp-0B0h]
0x180016894  sub     rsp, 1B0h
0x18001689b  mov     rax, cs:__security_cookie
0x1800168a2  xor     rax, rsp
0x1800168a5  mov     [rbp+0C0h+var_20], rax
0x1800168ac  mov     rax, [rbp+0C0h+arg_B0]
0x1800168b3  mov     r11, r8
0x1800168b6  mov     [rbp+0C0h+var_30], rax
0x1800168bd  mov     r8, rdx
0x1800168c0  mov     rax, [rbp+0C0h+arg_A8]
0x1800168c7  mov     r10, rcx
0x1800168ca  mov     [rbp+0C0h+var_40], rax
0x1800168d1  xor     ebx, ebx
0x1800168d3  mov     rax, [rbp+0C0h+arg_A0]
0x1800168da  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800168de  mov     [rbp+0C0h+var_50], rax
0x1800168e2  mov     rax, [rbp+0C0h+arg_98]
0x1800168e9  mov     [rbp+0C0h+var_60], rax
0x1800168ed  mov     rax, [rbp+0C0h+arg_90]
0x1800168f4  mov     [rbp+0C0h+var_70], rax
0x1800168f8  mov     rax, [rbp+0C0h+arg_88]
0x1800168ff  mov     [rbp+0C0h+var_80], rax
0x180016903  mov     rax, [rbp+0C0h+arg_80]
0x18001690a  mov     [rbp+0C0h+var_90], rax
0x18001690e  mov     rax, [rbp+0C0h+arg_78]
0x180016915  mov     [rbp+0C0h+var_A0], rax
0x180016919  mov     rax, [rbp+0C0h+arg_70]
0x180016920  mov     [rbp+0C0h+var_B0], rax
0x180016924  mov     rax, [rbp+0C0h+arg_68]
0x18001692b  mov     [rbp+0C0h+var_C0], rax
0x18001692f  mov     rax, [rbp+0C0h+arg_60]
0x180016936  mov     [rbp+0C0h+var_D0], rax
0x18001693a  mov     rax, [rbp+0C0h+arg_58]
0x180016941  mov     [rbp+0C0h+var_E0], rax
0x180016945  mov     rax, [rbp+0C0h+arg_50]
0x18001694c  mov     [rbp+0C0h+var_F0], rax
0x180016950  mov     rax, [rbp+0C0h+arg_48]
0x180016957  mov     [rbp+0C0h+var_100], rax
0x18001695b  mov     rax, [rbp+0C0h+arg_40]
0x180016962  mov     [rbp+0C0h+var_110], rax
0x180016966  mov     rax, [rbp+0C0h+arg_38]
0x18001696d  mov     [rbp+0C0h+var_28], 4
0x180016978  mov     [rbp+0C0h+var_38], 4
0x180016983  mov     [rbp+0C0h+var_48], 4
0x18001698b  mov     rdx, [rax]
0x18001698e  mov     [rbp+0C0h+var_58], 4
0x180016996  mov     [rbp+0C0h+var_68], 4
0x18001699e  mov     [rbp+0C0h+var_78], 4
0x1800169a6  mov     [rbp+0C0h+var_88], 4
0x1800169ae  mov     [rbp+0C0h+var_98], 4
0x1800169b6  mov     [rbp+0C0h+var_A8], 4
0x1800169be  mov     [rbp+0C0h+var_B8], 4
0x1800169c6  mov     [rbp+0C0h+var_C8], 4
0x1800169ce  mov     [rbp+0C0h+var_D8], 4
0x1800169d6  mov     [rbp+0C0h+var_E8], 4
0x1800169de  mov     [rbp+0C0h+var_F8], 4
0x1800169e6  mov     [rbp+0C0h+var_108], 4
0x1800169ee  test    rdx, rdx
0x1800169f1  jz      short loc_180016A08
0x1800169f3  mov     rax, rcx
0x1800169f6  inc     rax
0x1800169f9  cmp     [rdx+rax*2], bx
0x1800169fd  jnz     short loc_1800169F6
0x1800169ff  lea     eax, ds:2[rax*2]
0x180016a06  jmp     short loc_180016A14
0x180016a08  lea     rdx, LocaleName
0x180016a0f  mov     eax, 2
0x180016a14  mov     [rbp+0C0h+var_118], eax
0x180016a17  mov     rax, [rbp+0C0h+arg_30]
0x180016a1e  mov     [rbp+0C0h+var_120], rdx
0x180016a22  mov     [rbp+0C0h+var_114], ebx
0x180016a25  mov     rdx, [rax]
0x180016a28  test    rdx, rdx
0x180016a2b  jz      short loc_180016A3F
0x180016a2d  inc     rcx
0x180016a30  cmp     [rdx+rcx*2], bx
0x180016a34  jnz     short loc_180016A2D
0x180016a36  lea     ecx, ds:2[rcx*2]
0x180016a3d  jmp     short loc_180016A4B
0x180016a3f  lea     rdx, LocaleName
0x180016a46  mov     ecx, 2
0x180016a4b  mov     rax, [rbp+0C0h+arg_28]
0x180016a52  mov     [rbp+0C0h+var_140], rax
0x180016a56  mov     rax, [rbp+0C0h+arg_20]
0x180016a5d  mov     [rsp+1C0h+var_150], rax
0x180016a62  movzx   eax, byte ptr [r8]
0x180016a66  shl     eax, 18h
0x180016a69  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], eax
0x180016a6d  movzx   eax, word ptr [r8+1]
0x180016a72  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x180016a76  mov     rax, [r8+3]
0x180016a7a  mov     [rsp+1C0h+EventDescriptor.Keyword], rax
0x180016a7f  mov     rax, [r10+8]
0x180016a83  mov     [rsp+1C0h+var_170.Ptr], rax
0x180016a88  mov     [rbp+0C0h+var_128], ecx
0x180016a8b  lea     rcx, [r8+0Bh]
0x180016a8f  mov     [rbp+0C0h+var_130], rdx
0x180016a93  mov     r8, r11; ActivityId
0x180016a96  mov     [rbp+0C0h+var_124], ebx
0x180016a99  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x180016a9e  mov     [rbp+0C0h+var_138], 4
0x180016aa6  mov     [rsp+1C0h+var_148], 4
0x180016aaf  movzx   eax, word ptr [rax]
0x180016ab2  mov     [rsp+1C0h+var_170.Size], eax
0x180016ab6  movzx   eax, word ptr [rcx]
0x180016ab9  mov     [rsp+1C0h+var_158], eax
0x180016abd  lea     rax, _TraceLoggingMetadataEnd
0x180016ac4  mov     [rsp+1C0h+var_160], rcx
0x180016ac9  lea     rcx, _TraceLoggingMetadata
0x180016ad0  sub     eax, ecx
0x180016ad2  mov     dword ptr [rsp+1C0h+var_170.0Ch], 2
0x180016ada  mov     [rsp+1C0h+var_154], 1
0x180016ae2  mov     [rsp+1C0h+var_190], eax
0x180016ae6  mov     eax, [rsp+1C0h+var_190]
0x180016aea  mov     rcx, [r10+20h]; RegHandle
0x180016aee  lea     rax, [rsp+1C0h+var_170]
0x180016af3  mov     [rsp+1C0h+UserData], rax; UserData
0x180016af8  mov     [rsp+1C0h+UserDataCount], 15h; UserDataCount
0x180016b00  call    cs:__imp_EventWriteTransfer
0x180016b06  mov     rcx, [rbp+0C0h+var_20]
0x180016b0d  xor     rcx, rsp; StackCookie
0x180016b10  call    __security_check_cookie
0x180016b15  add     rsp, 1B0h
0x180016b1c  pop     rdi
0x180016b1d  pop     rbx
0x180016b1e  pop     rbp
0x180016b1f  retn
```
