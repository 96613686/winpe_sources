# CClipRdrPduDispatcher::Terminate(void)

- ea: `0x14002fd00`
- end: `0x14003030a`
- name: `?Terminate@CClipRdrPduDispatcher@@MEAAJXZ`
- size: `1546`
- prototype: `__int64 __fastcall(CClipRdrPduDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x14003f990`

## callees

- `0x140005750`
- `0x1400081d0`
- `0x1400256b4`
- `0x14002fd00`
- `0x14006b010`

## string_xrefs

- `0x14002fd69`: `Failed to remove FORMAT_LIST event source!`
- `0x14002fde1`: `Failed to remove FORMAT_LIST_RESPONSE event source!`
- `0x14002fe5b`: `Failed to remove FORMAT_DATA_REQUEST event source!`
- `0x14002fed5`: `Failed to remove FORMAT_DATA_RESPONSE event source!`
- `0x14002ff4f`: `Failed to remove CLIP_EVENT_FILE_CONTENTS_REQUEST event source!`
- `0x14002ffc9`: `Failed to remove CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!`
- `0x14003000b`: `Failed to remove CLIP_CAPS event source!`
- `0x1400301b2`: `Failed to remove DATA_CHANNEL_REQUEST event source!`
- `0x140030233`: `Failed to remove DATA_CHANNEL_RESPONSE event source!`
- `0x1400302b4`: `Failed to remove UNKNOWN_PDU event source!`

## pseudocode

```c
__int64 __fastcall CClipRdrPduDispatcher::Terminate(CClipRdrPduDispatcher *this)
{
  _QWORD *v2; // rdi
  int v3; // esi
  int ActivityIdPrefix; // eax
  _QWORD *v5; // rdi
  int v6; // esi
  int v7; // eax
  _QWORD *v8; // rdi
  int v9; // esi
  int v10; // eax
  _QWORD *v11; // rdi
  int v12; // esi
  int v13; // eax
  _QWORD *v14; // rdi
  int v15; // esi
  int v16; // eax
  _QWORD *v17; // rdi
  int v18; // esi
  int v19; // eax
  _QWORD *v20; // rdi
  int v21; // esi
  int v22; // eax
  _QWORD *v23; // rdi
  int v24; // esi
  int v25; // eax
  _QWORD *v26; // rdi
  int v27; // esi
  int v28; // eax
  _QWORD *v29; // rdi
  int v30; // esi
  int v31; // eax
  _QWORD *v32; // rdi
  int v33; // esi
  int v34; // eax
  _QWORD *v35; // rdi
  int v36; // esi
  int v37; // eax
  __int64 v39; // [rsp+28h] [rbp-50h]
  int v40; // [rsp+28h] [rbp-50h]

  v2 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v3 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v40 = v3;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        ActivityIdPrefix,
        (__int64)"Failed to remove FORMAT_LIST event source!",
        v40);
    }
    if ( *v2 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(v2);
      *v2 = 0;
    }
  }
  v5 = (_QWORD *)((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v6 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v6;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v7,
        (__int64)"Failed to remove FORMAT_LIST_RESPONSE event source!",
        v39);
    }
    if ( *v5 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 64);
      *v5 = 0;
    }
  }
  v8 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v9;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v10,
        (__int64)"Failed to remove FORMAT_DATA_REQUEST event source!",
        v39);
    }
    if ( *v8 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 72);
      *v8 = 0;
    }
  }
  v11 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v12 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v12;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v13,
        (__int64)"Failed to remove FORMAT_DATA_RESPONSE event source!",
        v39);
    }
    if ( *v11 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 80);
      *v11 = 0;
    }
  }
  v14 = (_QWORD *)((char *)this + 88);
  if ( *((_QWORD *)this + 11) )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v15 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v15;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v16,
        (__int64)"Failed to remove CLIP_EVENT_FILE_CONTENTS_REQUEST event source!",
        v39);
    }
    if ( *v14 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 88);
      *v14 = 0;
    }
  }
  v17 = (_QWORD *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v18 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v18;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v19,
        (__int64)"Failed to remove CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!",
        v39);
    }
    if ( *v17 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 96);
      *v17 = 0;
    }
  }
  v20 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 13) )
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v21 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v21;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v22,
        (__int64)"Failed to remove CLIP_CAPS event source!",
        v39);
    }
    if ( *v20 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 104);
      *v20 = 0;
    }
  }
  v23 = (_QWORD *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v24 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v24;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v25,
        (__int64)"Failed to remove CLIP_CAPS event source!",
        v39);
    }
    if ( *v23 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 112);
      *v23 = 0;
    }
  }
  v26 = (_QWORD *)((char *)this + 120);
  if ( *((_QWORD *)this + 15) )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v27 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v28 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v27;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v28,
        (__int64)"Failed to remove CLIP_CAPS event source!",
        v39);
    }
    if ( *v26 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 120);
      *v26 = 0;
    }
  }
  v29 = (_QWORD *)((char *)this + 136);
  if ( *((_QWORD *)this + 17) )
  {
    v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v30 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v30;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v31,
        (__int64)"Failed to remove DATA_CHANNEL_REQUEST event source!",
        v39);
    }
    if ( *v29 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 136);
      *v29 = 0;
    }
  }
  v32 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    v33 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v33 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v34 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v33;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v34,
        (__int64)"Failed to remove DATA_CHANNEL_RESPONSE event source!",
        v39);
    }
    if ( *v32 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 144);
      *v32 = 0;
    }
  }
  v35 = (_QWORD *)((char *)this + 128);
  if ( *((_QWORD *)this + 16) )
  {
    v36 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v36 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v39) = v36;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v37,
        (__int64)"Failed to remove UNKNOWN_PDU event source!",
        v39);
    }
    if ( *v35 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 128);
      *v35 = 0;
    }
  }
  *((_DWORD *)this + 5) |= 4u;
  return 0;
}

```

## disassembly

```asm
0x14002fd00  push    rbx
0x14002fd02  push    rbp
0x14002fd03  push    rsi
0x14002fd04  push    rdi
0x14002fd05  push    r12
0x14002fd07  push    r13
0x14002fd09  push    r14
0x14002fd0b  push    r15
0x14002fd0d  sub     rsp, 38h
0x14002fd11  mov     rbx, rcx
0x14002fd14  lea     rdi, [rcx+38h]
0x14002fd18  xor     ebp, ebp
0x14002fd1a  mov     rdx, [rdi]
0x14002fd1d  lea     r15, WPP_GLOBAL_Control
0x14002fd24  lea     r13, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x14002fd2b  mov     r12b, 8
0x14002fd2e  mov     r14b, 2
0x14002fd31  test    rdx, rdx
0x14002fd34  jz      short loc_14002FDA2
0x14002fd36  mov     rcx, [rcx+30h]
0x14002fd3a  mov     rax, [rcx]
0x14002fd3d  mov     rax, [rax+40h]
0x14002fd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fd46  mov     esi, eax
0x14002fd48  test    eax, eax
0x14002fd4a  jns     short loc_14002FD92
0x14002fd4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd53  cmp     rcx, r15
0x14002fd56  jz      short loc_14002FD92
0x14002fd58  test    [rcx+1Ch], r12b
0x14002fd5c  jz      short loc_14002FD92
0x14002fd5e  cmp     [rcx+19h], r14b
0x14002fd62  jb      short loc_14002FD92
0x14002fd64  call    RdpX_GetActivityIdPrefix
0x14002fd69  lea     rcx, aFailedToRemove_0; "Failed to remove FORMAT_LIST event sour"...
0x14002fd70  mov     dword ptr [rsp+78h+var_50], esi
0x14002fd74  mov     [rsp+78h+var_58], rcx
0x14002fd79  lea     edx, [rbp+3Ch]
0x14002fd7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd83  mov     r9d, eax
0x14002fd86  mov     r8, r13
0x14002fd89  mov     rcx, [rcx+10h]
0x14002fd8d  call    WPP_SF_DsD
0x14002fd92  cmp     [rdi], rbp
0x14002fd95  jz      short loc_14002FDA2
0x14002fd97  mov     rcx, rdi
0x14002fd9a  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14002fd9f  mov     [rdi], rbp
0x14002fda2  lea     rdi, [rbx+40h]
0x14002fda6  mov     rdx, [rdi]
0x14002fda9  test    rdx, rdx
0x14002fdac  jz      short loc_14002FE1C
0x14002fdae  mov     rcx, [rbx+30h]
0x14002fdb2  mov     rax, [rcx]
0x14002fdb5  mov     rax, [rax+40h]
0x14002fdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fdbe  mov     esi, eax
0x14002fdc0  test    eax, eax
0x14002fdc2  jns     short loc_14002FE0C
0x14002fdc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdcb  cmp     rcx, r15
0x14002fdce  jz      short loc_14002FE0C
0x14002fdd0  test    [rcx+1Ch], r12b
0x14002fdd4  jz      short loc_14002FE0C
0x14002fdd6  cmp     [rcx+19h], r14b
0x14002fdda  jb      short loc_14002FE0C
0x14002fddc  call    RdpX_GetActivityIdPrefix
0x14002fde1  lea     rcx, aFailedToRemove_21; "Failed to remove FORMAT_LIST_RESPONSE e"...
0x14002fde8  mov     dword ptr [rsp+78h+var_50], esi
0x14002fdec  mov     [rsp+78h+var_58], rcx
0x14002fdf1  mov     edx, 3Dh ; '='
0x14002fdf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdfd  mov     r9d, eax
0x14002fe00  mov     r8, r13
0x14002fe03  mov     rcx, [rcx+10h]
0x14002fe07  call    WPP_SF_DsD
0x14002fe0c  cmp     [rdi], rbp
0x14002fe0f  jz      short loc_14002FE1C
0x14002fe11  mov     rcx, rdi
0x14002fe14  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14002fe19  mov     [rdi], rbp
0x14002fe1c  lea     rdi, [rbx+48h]
0x14002fe20  mov     rdx, [rdi]
0x14002fe23  test    rdx, rdx
0x14002fe26  jz      short loc_14002FE96
0x14002fe28  mov     rcx, [rbx+30h]
0x14002fe2c  mov     rax, [rcx]
0x14002fe2f  mov     rax, [rax+40h]
0x14002fe33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fe38  mov     esi, eax
0x14002fe3a  test    eax, eax
0x14002fe3c  jns     short loc_14002FE86
0x14002fe3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe45  cmp     rcx, r15
0x14002fe48  jz      short loc_14002FE86
0x14002fe4a  test    [rcx+1Ch], r12b
0x14002fe4e  jz      short loc_14002FE86
0x14002fe50  cmp     [rcx+19h], r14b
0x14002fe54  jb      short loc_14002FE86
0x14002fe56  call    RdpX_GetActivityIdPrefix
0x14002fe5b  lea     rcx, aFailedToRemove_15; "Failed to remove FORMAT_DATA_REQUEST ev"...
0x14002fe62  mov     dword ptr [rsp+78h+var_50], esi
0x14002fe66  mov     [rsp+78h+var_58], rcx
0x14002fe6b  mov     edx, 3Eh ; '>'
0x14002fe70  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe77  mov     r9d, eax
0x14002fe7a  mov     r8, r13
0x14002fe7d  mov     rcx, [rcx+10h]
0x14002fe81  call    WPP_SF_DsD
0x14002fe86  cmp     [rdi], rbp
0x14002fe89  jz      short loc_14002FE96
0x14002fe8b  mov     rcx, rdi
0x14002fe8e  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14002fe93  mov     [rdi], rbp
0x14002fe96  lea     rdi, [rbx+50h]
0x14002fe9a  mov     rdx, [rdi]
0x14002fe9d  test    rdx, rdx
0x14002fea0  jz      short loc_14002FF10
0x14002fea2  mov     rcx, [rbx+30h]
0x14002fea6  mov     rax, [rcx]
0x14002fea9  mov     rax, [rax+40h]
0x14002fead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002feb2  mov     esi, eax
0x14002feb4  test    eax, eax
0x14002feb6  jns     short loc_14002FF00
0x14002feb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002febf  cmp     rcx, r15
0x14002fec2  jz      short loc_14002FF00
0x14002fec4  test    [rcx+1Ch], r12b
0x14002fec8  jz      short loc_14002FF00
0x14002feca  cmp     [rcx+19h], r14b
0x14002fece  jb      short loc_14002FF00
0x14002fed0  call    RdpX_GetActivityIdPrefix
0x14002fed5  lea     rcx, aFailedToRemove_23; "Failed to remove FORMAT_DATA_RESPONSE e"...
0x14002fedc  mov     dword ptr [rsp+78h+var_50], esi
0x14002fee0  mov     [rsp+78h+var_58], rcx
0x14002fee5  mov     edx, 3Fh ; '?'
0x14002feea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fef1  mov     r9d, eax
0x14002fef4  mov     r8, r13
0x14002fef7  mov     rcx, [rcx+10h]
0x14002fefb  call    WPP_SF_DsD
0x14002ff00  cmp     [rdi], rbp
0x14002ff03  jz      short loc_14002FF10
0x14002ff05  mov     rcx, rdi
0x14002ff08  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14002ff0d  mov     [rdi], rbp
0x14002ff10  lea     rdi, [rbx+58h]
0x14002ff14  mov     rdx, [rdi]
0x14002ff17  test    rdx, rdx
0x14002ff1a  jz      short loc_14002FF8A
0x14002ff1c  mov     rcx, [rbx+30h]
0x14002ff20  mov     rax, [rcx]
0x14002ff23  mov     rax, [rax+40h]
0x14002ff27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff2c  mov     esi, eax
0x14002ff2e  test    eax, eax
0x14002ff30  jns     short loc_14002FF7A
0x14002ff32  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff39  cmp     rcx, r15
0x14002ff3c  jz      short loc_14002FF7A
0x14002ff3e  test    [rcx+1Ch], r12b
0x14002ff42  jz      short loc_14002FF7A
0x14002ff44  cmp     [rcx+19h], r14b
0x14002ff48  jb      short loc_14002FF7A
0x14002ff4a  call    RdpX_GetActivityIdPrefix
0x14002ff4f  lea     rcx, aFailedToRemove_11; "Failed to remove CLIP_EVENT_FILE_CONTEN"...
0x14002ff56  mov     dword ptr [rsp+78h+var_50], esi
0x14002ff5a  mov     [rsp+78h+var_58], rcx
0x14002ff5f  mov     edx, 40h ; '@'
0x14002ff64  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff6b  mov     r9d, eax
0x14002ff6e  mov     r8, r13
0x14002ff71  mov     rcx, [rcx+10h]
0x14002ff75  call    WPP_SF_DsD
0x14002ff7a  cmp     [rdi], rbp
0x14002ff7d  jz      short loc_14002FF8A
0x14002ff7f  mov     rcx, rdi
0x14002ff82  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14002ff87  mov     [rdi], rbp
0x14002ff8a  lea     rdi, [rbx+60h]
0x14002ff8e  mov     rdx, [rdi]
0x14002ff91  test    rdx, rdx
0x14002ff94  jz      short loc_140030004
0x14002ff96  mov     rcx, [rbx+30h]
0x14002ff9a  mov     rax, [rcx]
0x14002ff9d  mov     rax, [rax+40h]
0x14002ffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ffa6  mov     esi, eax
0x14002ffa8  test    eax, eax
0x14002ffaa  jns     short loc_14002FFF4
0x14002ffac  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ffb3  cmp     rcx, r15
0x14002ffb6  jz      short loc_14002FFF4
0x14002ffb8  test    [rcx+1Ch], r12b
0x14002ffbc  jz      short loc_14002FFF4
0x14002ffbe  cmp     [rcx+19h], r14b
0x14002ffc2  jb      short loc_14002FFF4
0x14002ffc4  call    RdpX_GetActivityIdPrefix
0x14002ffc9  lea     rcx, aFailedToRemove_10; "Failed to remove CLIP_EVENT_FILE_CONTEN"...
0x14002ffd0  mov     dword ptr [rsp+78h+var_50], esi
0x14002ffd4  mov     [rsp+78h+var_58], rcx
0x14002ffd9  mov     edx, 41h ; 'A'
0x14002ffde  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ffe5  mov     r9d, eax
0x14002ffe8  mov     r8, r13
0x14002ffeb  mov     rcx, [rcx+10h]
0x14002ffef  call    WPP_SF_DsD
0x14002fff4  cmp     [rdi], rbp
0x14002fff7  jz      short loc_140030004
0x14002fff9  mov     rcx, rdi
0x14002fffc  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140030001  mov     [rdi], rbp
0x140030004  lea     rdi, [rbx+68h]
0x140030008  mov     rdx, [rdi]
0x14003000b  lea     r13, aFailedToRemove_6; "Failed to remove CLIP_CAPS event source"...
0x140030012  test    rdx, rdx
0x140030015  jz      short loc_140030082
0x140030017  mov     rcx, [rbx+30h]
0x14003001b  mov     rax, [rcx]
0x14003001e  mov     rax, [rax+40h]
0x140030022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030027  mov     esi, eax
0x140030029  test    eax, eax
0x14003002b  jns     short loc_140030072
0x14003002d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030034  cmp     rcx, r15
0x140030037  jz      short loc_140030072
0x140030039  test    [rcx+1Ch], r12b
0x14003003d  jz      short loc_140030072
0x14003003f  cmp     [rcx+19h], r14b
0x140030043  jb      short loc_140030072
0x140030045  call    RdpX_GetActivityIdPrefix
0x14003004a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030051  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x140030058  mov     edx, 42h ; 'B'
0x14003005d  mov     dword ptr [rsp+78h+var_50], esi
0x140030061  mov     r9d, eax
0x140030064  mov     [rsp+78h+var_58], r13
0x140030069  mov     rcx, [rcx+10h]
0x14003006d  call    WPP_SF_DsD
0x140030072  cmp     [rdi], rbp
0x140030075  jz      short loc_140030082
0x140030077  mov     rcx, rdi
0x14003007a  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003007f  mov     [rdi], rbp
0x140030082  lea     rdi, [rbx+70h]
0x140030086  mov     rdx, [rdi]
0x140030089  test    rdx, rdx
0x14003008c  jz      short loc_1400300F9
0x14003008e  mov     rcx, [rbx+30h]
0x140030092  mov     rax, [rcx]
0x140030095  mov     rax, [rax+40h]
0x140030099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003009e  mov     esi, eax
0x1400300a0  test    eax, eax
0x1400300a2  jns     short loc_1400300E9
0x1400300a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300ab  cmp     rcx, r15
0x1400300ae  jz      short loc_1400300E9
0x1400300b0  test    [rcx+1Ch], r12b
0x1400300b4  jz      short loc_1400300E9
0x1400300b6  cmp     [rcx+19h], r14b
0x1400300ba  jb      short loc_1400300E9
0x1400300bc  call    RdpX_GetActivityIdPrefix
0x1400300c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300c8  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x1400300cf  mov     edx, 43h ; 'C'
0x1400300d4  mov     dword ptr [rsp+78h+var_50], esi
0x1400300d8  mov     r9d, eax
0x1400300db  mov     [rsp+78h+var_58], r13
0x1400300e0  mov     rcx, [rcx+10h]
0x1400300e4  call    WPP_SF_DsD
0x1400300e9  cmp     [rdi], rbp
0x1400300ec  jz      short loc_1400300F9
0x1400300ee  mov     rcx, rdi
0x1400300f1  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400300f6  mov     [rdi], rbp
0x1400300f9  lea     rdi, [rbx+78h]
0x1400300fd  mov     rdx, [rdi]
0x140030100  test    rdx, rdx
0x140030103  jz      short loc_140030170
0x140030105  mov     rcx, [rbx+30h]
0x140030109  mov     rax, [rcx]
0x14003010c  mov     rax, [rax+40h]
0x140030110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030115  mov     esi, eax
0x140030117  test    eax, eax
0x140030119  jns     short loc_140030160
0x14003011b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030122  cmp     rcx, r15
0x140030125  jz      short loc_140030160
0x140030127  test    [rcx+1Ch], r12b
0x14003012b  jz      short loc_140030160
0x14003012d  cmp     [rcx+19h], r14b
0x140030131  jb      short loc_140030160
0x140030133  call    RdpX_GetActivityIdPrefix
0x140030138  mov     rcx, cs:WPP_GLOBAL_Control
0x14003013f  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x140030146  mov     edx, 44h ; 'D'
  ... truncated ...
```
