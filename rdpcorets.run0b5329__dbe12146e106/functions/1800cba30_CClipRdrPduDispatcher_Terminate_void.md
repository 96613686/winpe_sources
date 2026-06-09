# CClipRdrPduDispatcher::Terminate(void)

- ea: `0x1800cba30`
- end: `0x1800cc046`
- name: `?Terminate@CClipRdrPduDispatcher@@MEAAJXZ`
- size: `1558`
- prototype: `__int64 __fastcall(CClipRdrPduDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180071460`

## callees

- `0x1800071c0`
- `0x18002e600`
- `0x1800cba30`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cba94`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbb0d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbb88`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbc03`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbc7e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbcf9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbd7b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbdf3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbe6b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbee6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbf68`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbfea`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cba94`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbb0d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbb88`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbc03`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbc7e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbcf9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbd7b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbdf3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbe6b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbee6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbf68`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cbfea`

## string_xrefs

- `0x1800cba9a`: `Failed to remove FORMAT_LIST event source!`
- `0x1800cbb8e`: `Failed to remove FORMAT_DATA_REQUEST event source!`
- `0x1800cbb13`: `Failed to remove FORMAT_LIST_RESPONSE event source!`
- `0x1800cbc84`: `Failed to remove CLIP_EVENT_FILE_CONTENTS_REQUEST event source!`
- `0x1800cbc09`: `Failed to remove FORMAT_DATA_RESPONSE event source!`
- `0x1800cbd41`: `Failed to remove CLIP_CAPS event source!`
- `0x1800cbcff`: `Failed to remove CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!`
- `0x1800cbf6e`: `Failed to remove DATA_CHANNEL_RESPONSE event source!`
- `0x1800cbeec`: `Failed to remove DATA_CHANNEL_REQUEST event source!`
- `0x1800cbff0`: `Failed to remove UNKNOWN_PDU event source!`

## pseudocode

```c
__int64 __fastcall CClipRdrPduDispatcher::Terminate(CClipRdrPduDispatcher *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  int v4; // esi
  __int64 v5; // r8
  int ActivityIdPrefix; // eax
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // r8
  int v11; // eax
  _QWORD *v12; // rdi
  __int64 v13; // rdx
  int v14; // esi
  __int64 v15; // r8
  int v16; // eax
  _QWORD *v17; // rdi
  __int64 v18; // rdx
  int v19; // esi
  __int64 v20; // r8
  int v21; // eax
  _QWORD *v22; // rdi
  __int64 v23; // rdx
  int v24; // esi
  __int64 v25; // r8
  int v26; // eax
  _QWORD *v27; // rdi
  __int64 v28; // rdx
  int v29; // esi
  __int64 v30; // r8
  int v31; // eax
  _QWORD *v32; // rdi
  __int64 v33; // rdx
  int v34; // esi
  __int64 v35; // r8
  int v36; // eax
  _QWORD *v37; // rdi
  __int64 v38; // rdx
  int v39; // esi
  __int64 v40; // r8
  int v41; // eax
  _QWORD *v42; // rdi
  __int64 v43; // rdx
  int v44; // esi
  __int64 v45; // r8
  int v46; // eax
  _QWORD *v47; // rdi
  __int64 v48; // rdx
  int v49; // esi
  __int64 v50; // r8
  int v51; // eax
  _QWORD *v52; // rdi
  __int64 v53; // rdx
  int v54; // esi
  __int64 v55; // r8
  int v56; // eax
  _QWORD *v57; // rdi
  __int64 v58; // rdx
  int v59; // esi
  __int64 v60; // r8
  int v61; // eax
  __int64 v63; // [rsp+28h] [rbp-50h]
  int v64; // [rsp+28h] [rbp-50h]

  v2 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v4 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v64 = v4;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        ActivityIdPrefix,
        (__int64)"Failed to remove FORMAT_LIST event source!",
        v64);
    }
    if ( *v2 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(v2, v3, v5);
      *v2 = 0;
    }
  }
  v7 = (_QWORD *)((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v9;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v11,
        (__int64)"Failed to remove FORMAT_LIST_RESPONSE event source!",
        v63);
    }
    if ( *v7 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 64, v8, v10);
      *v7 = 0;
    }
  }
  v12 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v14 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v14;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v16,
        (__int64)"Failed to remove FORMAT_DATA_REQUEST event source!",
        v63);
    }
    if ( *v12 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 72, v13, v15);
      *v12 = 0;
    }
  }
  v17 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v19 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v19;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v21,
        (__int64)"Failed to remove FORMAT_DATA_RESPONSE event source!",
        v63);
    }
    if ( *v17 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 80, v18, v20);
      *v17 = 0;
    }
  }
  v22 = (_QWORD *)((char *)this + 88);
  if ( *((_QWORD *)this + 11) )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v24 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v24;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v26,
        (__int64)"Failed to remove CLIP_EVENT_FILE_CONTENTS_REQUEST event source!",
        v63);
    }
    if ( *v22 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 88, v23, v25);
      *v22 = 0;
    }
  }
  v27 = (_QWORD *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) )
  {
    v29 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v29 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v29;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v31,
        (__int64)"Failed to remove CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!",
        v63);
    }
    if ( *v27 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 96, v28, v30);
      *v27 = 0;
    }
  }
  v32 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 13) )
  {
    v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v34 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v36 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v34;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v36,
        (__int64)"Failed to remove CLIP_CAPS event source!",
        v63);
    }
    if ( *v32 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 104, v33, v35);
      *v32 = 0;
    }
  }
  v37 = (_QWORD *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
  {
    v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v39 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v39;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v41,
        (__int64)"Failed to remove CLIP_CAPS event source!",
        v63);
    }
    if ( *v37 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 112, v38, v40);
      *v37 = 0;
    }
  }
  v42 = (_QWORD *)((char *)this + 120);
  if ( *((_QWORD *)this + 15) )
  {
    v44 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v44 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v44;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v46,
        (__int64)"Failed to remove CLIP_CAPS event source!",
        v63);
    }
    if ( *v42 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 120, v43, v45);
      *v42 = 0;
    }
  }
  v47 = (_QWORD *)((char *)this + 136);
  if ( *((_QWORD *)this + 17) )
  {
    v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v49 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v51 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v49;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v51,
        (__int64)"Failed to remove DATA_CHANNEL_REQUEST event source!",
        v63);
    }
    if ( *v47 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 136, v48, v50);
      *v47 = 0;
    }
  }
  v52 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    v54 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v54 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v56 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v54;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v56,
        (__int64)"Failed to remove DATA_CHANNEL_RESPONSE event source!",
        v63);
    }
    if ( *v52 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 144, v53, v55);
      *v52 = 0;
    }
  }
  v57 = (_QWORD *)((char *)this + 128);
  if ( *((_QWORD *)this + 16) )
  {
    v59 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
    if ( v59 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v61 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v63) = v59;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
        v61,
        (__int64)"Failed to remove UNKNOWN_PDU event source!",
        v63);
    }
    if ( *v57 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 128, v58, v60);
      *v57 = 0;
    }
  }
  *((_DWORD *)this + 5) |= 4u;
  return 0;
}

```

## disassembly

```asm
0x1800cba30  push    rbx
0x1800cba32  push    rbp
0x1800cba33  push    rsi
0x1800cba34  push    rdi
0x1800cba35  push    r12
0x1800cba37  push    r13
0x1800cba39  push    r14
0x1800cba3b  push    r15
0x1800cba3d  sub     rsp, 38h
0x1800cba41  mov     rbx, rcx
0x1800cba44  lea     rdi, [rcx+38h]
0x1800cba48  xor     ebp, ebp
0x1800cba4a  mov     rdx, [rdi]
0x1800cba4d  lea     r15, WPP_GLOBAL_Control
0x1800cba54  lea     r13, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x1800cba5b  mov     r12b, 8
0x1800cba5e  mov     r14b, 2
0x1800cba61  test    rdx, rdx
0x1800cba64  jz      short loc_1800CBAD3
0x1800cba66  mov     rcx, [rcx+30h]
0x1800cba6a  mov     rax, [rcx]
0x1800cba6d  mov     rax, [rax+40h]
0x1800cba71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cba76  mov     esi, eax
0x1800cba78  test    eax, eax
0x1800cba7a  jns     short loc_1800CBAC3
0x1800cba7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cba83  cmp     rcx, r15
0x1800cba86  jz      short loc_1800CBAC3
0x1800cba88  test    [rcx+1Ch], r12b
0x1800cba8c  jz      short loc_1800CBAC3
0x1800cba8e  cmp     [rcx+19h], r14b
0x1800cba92  jb      short loc_1800CBAC3
0x1800cba94  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cba9a  lea     rcx, aFailedToRemove_1; "Failed to remove FORMAT_LIST event sour"...
0x1800cbaa1  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbaa5  mov     [rsp+78h+var_58], rcx
0x1800cbaaa  lea     edx, [rbp+3Ch]
0x1800cbaad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbab4  mov     r9d, eax
0x1800cbab7  mov     r8, r13
0x1800cbaba  mov     rcx, [rcx+10h]
0x1800cbabe  call    WPP_SF_DsD
0x1800cbac3  cmp     [rdi], rbp
0x1800cbac6  jz      short loc_1800CBAD3
0x1800cbac8  mov     rcx, rdi
0x1800cbacb  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbad0  mov     [rdi], rbp
0x1800cbad3  lea     rdi, [rbx+40h]
0x1800cbad7  mov     rdx, [rdi]
0x1800cbada  test    rdx, rdx
0x1800cbadd  jz      short loc_1800CBB4E
0x1800cbadf  mov     rcx, [rbx+30h]
0x1800cbae3  mov     rax, [rcx]
0x1800cbae6  mov     rax, [rax+40h]
0x1800cbaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbaef  mov     esi, eax
0x1800cbaf1  test    eax, eax
0x1800cbaf3  jns     short loc_1800CBB3E
0x1800cbaf5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbafc  cmp     rcx, r15
0x1800cbaff  jz      short loc_1800CBB3E
0x1800cbb01  test    [rcx+1Ch], r12b
0x1800cbb05  jz      short loc_1800CBB3E
0x1800cbb07  cmp     [rcx+19h], r14b
0x1800cbb0b  jb      short loc_1800CBB3E
0x1800cbb0d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbb13  lea     rcx, aFailedToRemove_21; "Failed to remove FORMAT_LIST_RESPONSE e"...
0x1800cbb1a  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbb1e  mov     [rsp+78h+var_58], rcx
0x1800cbb23  mov     edx, 3Dh ; '='
0x1800cbb28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbb2f  mov     r9d, eax
0x1800cbb32  mov     r8, r13
0x1800cbb35  mov     rcx, [rcx+10h]
0x1800cbb39  call    WPP_SF_DsD
0x1800cbb3e  cmp     [rdi], rbp
0x1800cbb41  jz      short loc_1800CBB4E
0x1800cbb43  mov     rcx, rdi
0x1800cbb46  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbb4b  mov     [rdi], rbp
0x1800cbb4e  lea     rdi, [rbx+48h]
0x1800cbb52  mov     rdx, [rdi]
0x1800cbb55  test    rdx, rdx
0x1800cbb58  jz      short loc_1800CBBC9
0x1800cbb5a  mov     rcx, [rbx+30h]
0x1800cbb5e  mov     rax, [rcx]
0x1800cbb61  mov     rax, [rax+40h]
0x1800cbb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbb6a  mov     esi, eax
0x1800cbb6c  test    eax, eax
0x1800cbb6e  jns     short loc_1800CBBB9
0x1800cbb70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbb77  cmp     rcx, r15
0x1800cbb7a  jz      short loc_1800CBBB9
0x1800cbb7c  test    [rcx+1Ch], r12b
0x1800cbb80  jz      short loc_1800CBBB9
0x1800cbb82  cmp     [rcx+19h], r14b
0x1800cbb86  jb      short loc_1800CBBB9
0x1800cbb88  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbb8e  lea     rcx, aFailedToRemove_15; "Failed to remove FORMAT_DATA_REQUEST ev"...
0x1800cbb95  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbb99  mov     [rsp+78h+var_58], rcx
0x1800cbb9e  mov     edx, 3Eh ; '>'
0x1800cbba3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbbaa  mov     r9d, eax
0x1800cbbad  mov     r8, r13
0x1800cbbb0  mov     rcx, [rcx+10h]
0x1800cbbb4  call    WPP_SF_DsD
0x1800cbbb9  cmp     [rdi], rbp
0x1800cbbbc  jz      short loc_1800CBBC9
0x1800cbbbe  mov     rcx, rdi
0x1800cbbc1  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbbc6  mov     [rdi], rbp
0x1800cbbc9  lea     rdi, [rbx+50h]
0x1800cbbcd  mov     rdx, [rdi]
0x1800cbbd0  test    rdx, rdx
0x1800cbbd3  jz      short loc_1800CBC44
0x1800cbbd5  mov     rcx, [rbx+30h]
0x1800cbbd9  mov     rax, [rcx]
0x1800cbbdc  mov     rax, [rax+40h]
0x1800cbbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbbe5  mov     esi, eax
0x1800cbbe7  test    eax, eax
0x1800cbbe9  jns     short loc_1800CBC34
0x1800cbbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbbf2  cmp     rcx, r15
0x1800cbbf5  jz      short loc_1800CBC34
0x1800cbbf7  test    [rcx+1Ch], r12b
0x1800cbbfb  jz      short loc_1800CBC34
0x1800cbbfd  cmp     [rcx+19h], r14b
0x1800cbc01  jb      short loc_1800CBC34
0x1800cbc03  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbc09  lea     rcx, aFailedToRemove_23; "Failed to remove FORMAT_DATA_RESPONSE e"...
0x1800cbc10  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbc14  mov     [rsp+78h+var_58], rcx
0x1800cbc19  mov     edx, 3Fh ; '?'
0x1800cbc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbc25  mov     r9d, eax
0x1800cbc28  mov     r8, r13
0x1800cbc2b  mov     rcx, [rcx+10h]
0x1800cbc2f  call    WPP_SF_DsD
0x1800cbc34  cmp     [rdi], rbp
0x1800cbc37  jz      short loc_1800CBC44
0x1800cbc39  mov     rcx, rdi
0x1800cbc3c  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbc41  mov     [rdi], rbp
0x1800cbc44  lea     rdi, [rbx+58h]
0x1800cbc48  mov     rdx, [rdi]
0x1800cbc4b  test    rdx, rdx
0x1800cbc4e  jz      short loc_1800CBCBF
0x1800cbc50  mov     rcx, [rbx+30h]
0x1800cbc54  mov     rax, [rcx]
0x1800cbc57  mov     rax, [rax+40h]
0x1800cbc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbc60  mov     esi, eax
0x1800cbc62  test    eax, eax
0x1800cbc64  jns     short loc_1800CBCAF
0x1800cbc66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbc6d  cmp     rcx, r15
0x1800cbc70  jz      short loc_1800CBCAF
0x1800cbc72  test    [rcx+1Ch], r12b
0x1800cbc76  jz      short loc_1800CBCAF
0x1800cbc78  cmp     [rcx+19h], r14b
0x1800cbc7c  jb      short loc_1800CBCAF
0x1800cbc7e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbc84  lea     rcx, aFailedToRemove_11; "Failed to remove CLIP_EVENT_FILE_CONTEN"...
0x1800cbc8b  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbc8f  mov     [rsp+78h+var_58], rcx
0x1800cbc94  mov     edx, 40h ; '@'
0x1800cbc99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbca0  mov     r9d, eax
0x1800cbca3  mov     r8, r13
0x1800cbca6  mov     rcx, [rcx+10h]
0x1800cbcaa  call    WPP_SF_DsD
0x1800cbcaf  cmp     [rdi], rbp
0x1800cbcb2  jz      short loc_1800CBCBF
0x1800cbcb4  mov     rcx, rdi
0x1800cbcb7  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbcbc  mov     [rdi], rbp
0x1800cbcbf  lea     rdi, [rbx+60h]
0x1800cbcc3  mov     rdx, [rdi]
0x1800cbcc6  test    rdx, rdx
0x1800cbcc9  jz      short loc_1800CBD3A
0x1800cbccb  mov     rcx, [rbx+30h]
0x1800cbccf  mov     rax, [rcx]
0x1800cbcd2  mov     rax, [rax+40h]
0x1800cbcd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbcdb  mov     esi, eax
0x1800cbcdd  test    eax, eax
0x1800cbcdf  jns     short loc_1800CBD2A
0x1800cbce1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbce8  cmp     rcx, r15
0x1800cbceb  jz      short loc_1800CBD2A
0x1800cbced  test    [rcx+1Ch], r12b
0x1800cbcf1  jz      short loc_1800CBD2A
0x1800cbcf3  cmp     [rcx+19h], r14b
0x1800cbcf7  jb      short loc_1800CBD2A
0x1800cbcf9  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbcff  lea     rcx, aFailedToRemove_10; "Failed to remove CLIP_EVENT_FILE_CONTEN"...
0x1800cbd06  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbd0a  mov     [rsp+78h+var_58], rcx
0x1800cbd0f  mov     edx, 41h ; 'A'
0x1800cbd14  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbd1b  mov     r9d, eax
0x1800cbd1e  mov     r8, r13
0x1800cbd21  mov     rcx, [rcx+10h]
0x1800cbd25  call    WPP_SF_DsD
0x1800cbd2a  cmp     [rdi], rbp
0x1800cbd2d  jz      short loc_1800CBD3A
0x1800cbd2f  mov     rcx, rdi
0x1800cbd32  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbd37  mov     [rdi], rbp
0x1800cbd3a  lea     rdi, [rbx+68h]
0x1800cbd3e  mov     rdx, [rdi]
0x1800cbd41  lea     r13, aFailedToRemove_7; "Failed to remove CLIP_CAPS event source"...
0x1800cbd48  test    rdx, rdx
0x1800cbd4b  jz      short loc_1800CBDB9
0x1800cbd4d  mov     rcx, [rbx+30h]
0x1800cbd51  mov     rax, [rcx]
0x1800cbd54  mov     rax, [rax+40h]
0x1800cbd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd5d  mov     esi, eax
0x1800cbd5f  test    eax, eax
0x1800cbd61  jns     short loc_1800CBDA9
0x1800cbd63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbd6a  cmp     rcx, r15
0x1800cbd6d  jz      short loc_1800CBDA9
0x1800cbd6f  test    [rcx+1Ch], r12b
0x1800cbd73  jz      short loc_1800CBDA9
0x1800cbd75  cmp     [rcx+19h], r14b
0x1800cbd79  jb      short loc_1800CBDA9
0x1800cbd7b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbd81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbd88  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x1800cbd8f  mov     edx, 42h ; 'B'
0x1800cbd94  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbd98  mov     r9d, eax
0x1800cbd9b  mov     [rsp+78h+var_58], r13
0x1800cbda0  mov     rcx, [rcx+10h]
0x1800cbda4  call    WPP_SF_DsD
0x1800cbda9  cmp     [rdi], rbp
0x1800cbdac  jz      short loc_1800CBDB9
0x1800cbdae  mov     rcx, rdi
0x1800cbdb1  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbdb6  mov     [rdi], rbp
0x1800cbdb9  lea     rdi, [rbx+70h]
0x1800cbdbd  mov     rdx, [rdi]
0x1800cbdc0  test    rdx, rdx
0x1800cbdc3  jz      short loc_1800CBE31
0x1800cbdc5  mov     rcx, [rbx+30h]
0x1800cbdc9  mov     rax, [rcx]
0x1800cbdcc  mov     rax, [rax+40h]
0x1800cbdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbdd5  mov     esi, eax
0x1800cbdd7  test    eax, eax
0x1800cbdd9  jns     short loc_1800CBE21
0x1800cbddb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbde2  cmp     rcx, r15
0x1800cbde5  jz      short loc_1800CBE21
0x1800cbde7  test    [rcx+1Ch], r12b
0x1800cbdeb  jz      short loc_1800CBE21
0x1800cbded  cmp     [rcx+19h], r14b
0x1800cbdf1  jb      short loc_1800CBE21
0x1800cbdf3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbdf9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbe00  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x1800cbe07  mov     edx, 43h ; 'C'
0x1800cbe0c  mov     dword ptr [rsp+78h+var_50], esi
0x1800cbe10  mov     r9d, eax
0x1800cbe13  mov     [rsp+78h+var_58], r13
0x1800cbe18  mov     rcx, [rcx+10h]
0x1800cbe1c  call    WPP_SF_DsD
0x1800cbe21  cmp     [rdi], rbp
0x1800cbe24  jz      short loc_1800CBE31
0x1800cbe26  mov     rcx, rdi
0x1800cbe29  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cbe2e  mov     [rdi], rbp
0x1800cbe31  lea     rdi, [rbx+78h]
0x1800cbe35  mov     rdx, [rdi]
0x1800cbe38  test    rdx, rdx
0x1800cbe3b  jz      short loc_1800CBEA9
0x1800cbe3d  mov     rcx, [rbx+30h]
0x1800cbe41  mov     rax, [rcx]
0x1800cbe44  mov     rax, [rax+40h]
0x1800cbe48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe4d  mov     esi, eax
0x1800cbe4f  test    eax, eax
0x1800cbe51  jns     short loc_1800CBE99
0x1800cbe53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbe5a  cmp     rcx, r15
0x1800cbe5d  jz      short loc_1800CBE99
0x1800cbe5f  test    [rcx+1Ch], r12b
0x1800cbe63  jz      short loc_1800CBE99
0x1800cbe65  cmp     [rcx+19h], r14b
0x1800cbe69  jb      short loc_1800CBE99
0x1800cbe6b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cbe71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbe78  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x1800cbe7f  mov     edx, 44h ; 'D'
  ... truncated ...
```
