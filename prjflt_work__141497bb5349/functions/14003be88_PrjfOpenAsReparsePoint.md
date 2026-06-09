# PrjfOpenAsReparsePoint

- ea: `0x14003be88`
- end: `0x14003c4b0`
- name: `PrjfOpenAsReparsePoint`
- size: `1576`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FLT_INSTANCE *, __int64, __int64, void **, PFILE_OBJECT *, _BYTE *, _BYTE *, _BYTE *, _BYTE *, int *)`
- caller_count: `6`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140007300`
- `0x140022320`
- `0x1400396a4`
- `0x140042658`
- `0x140042cf0`
- `0x140042eac`

## callees

- `0x14000b1d0`
- `0x14000d128`
- `0x14001249c`
- `0x14003be88`
- `0x14003c668`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c434`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c44f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c46a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c485`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c434`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c44f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c46a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003c485`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003bf5d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003c063`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003c137`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003c20c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003bf5d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003c063`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003c137`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003c20c`
- `FLTMGR!FltGetInstanceContext` at `0x14003beeb`
- `FLTMGR!FltGetInstanceContext` at `0x14003beeb`
- `FLTMGR!FltReleaseContext` at `0x14003c419`
- `FLTMGR!FltReleaseContext` at `0x14003c419`

## pseudocode

```c
__int64 __fastcall PrjfOpenAsReparsePoint(
        __int64 a1,
        __int64 a2,
        struct _FLT_INSTANCE *a3,
        __int64 a4,
        __int64 a5,
        void **a6,
        PFILE_OBJECT *a7,
        _BYTE *a8,
        _BYTE *a9,
        _BYTE *a10,
        _BYTE *a11,
        int *a12)
{
  __int64 **v12; // rbx
  __int64 **v13; // r14
  __int64 **v14; // rsi
  int v15; // r15d
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int *v18; // rax
  __int64 v19; // rcx
  char *v20; // rax
  int v21; // edx
  int v22; // r8d
  __int64 **v23; // rdi
  unsigned int v24; // r15d
  unsigned int v25; // r15d
  __int64 ***v26; // rax
  char *v27; // rax
  int v28; // edx
  int v29; // r8d
  __int64 ***v30; // rax
  char *v31; // rax
  int v32; // edx
  int v33; // r8d
  __int64 ***v34; // rax
  char *v35; // rax
  int v36; // edx
  int v37; // r8d
  __int64 ***v38; // rax
  int v39; // eax
  int v40; // edx
  const char *v41; // r8
  const char *v42; // rcx
  ULONG v44; // [rsp+28h] [rbp-81h]
  int v45; // [rsp+30h] [rbp-79h]
  int v46; // [rsp+30h] [rbp-79h]
  int v47; // [rsp+38h] [rbp-71h]
  PHANDLE FileHandle; // [rsp+40h] [rbp-69h]
  PFILE_OBJECT *FileObject; // [rsp+48h] [rbp-61h]
  PFLT_CONTEXT Context; // [rsp+88h] [rbp-21h] BYREF
  __int64 v51[2]; // [rsp+90h] [rbp-19h] BYREF

  *(_OWORD *)v51 = 0;
  Context = 0;
  if ( !a6 || !a7 )
    return 3221225485LL;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = -2147483644;
  if ( FltGetInstanceContext(a3, &Context) < 0 || (v18 = (unsigned int *)Context) == 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
    v18 = (unsigned int *)Context;
  }
  v19 = v18[6];
  if ( (_DWORD)v19 != 2 && (_DWORD)v19 != 28 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, v16);
  if ( a12 )
    v15 = *a12;
  v51[1] = (__int64)v51;
  v51[0] = (__int64)v51;
  if ( !a8 )
  {
    v23 = 0;
    v25 = v15 | 0x80000000;
    goto LABEL_19;
  }
  *a8 = 0;
  v20 = (char *)ExAllocateFromPagedLookasideList(&stru_14001A6C0);
  v23 = (__int64 **)v20;
  if ( v20 )
  {
    *((_QWORD *)v20 + 1) = v20;
    *(_QWORD *)v20 = v20;
    v25 = v15 | 0x80000000;
    *(_OWORD *)(v20 + 24) = 0;
    *((_DWORD *)v20 + 4) = -1879048164;
    *((_DWORD *)v20 + 5) = v25;
    *((_WORD *)v20 + 20) = 48;
    *((_WORD *)v20 + 21) = 0;
    v26 = (__int64 ***)v51[1];
    if ( *(__int64 **)v51[1] != v51 )
      goto LABEL_39;
    v23[1] = (__int64 *)v51[1];
    *v23 = v51;
    *v26 = v23;
    v51[1] = (__int64)v23;
LABEL_19:
    if ( a9 )
    {
      *a9 = 0;
      v27 = (char *)ExAllocateFromPagedLookasideList(&stru_14001A6C0);
      v12 = (__int64 **)v27;
      if ( !v27 )
      {
        v24 = -1073741670;
        if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = BYTE1(xmmword_14001A3D0) & 4;
          LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            522,
            v28,
            v29,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            10,
            51,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            29,
            154);
        }
        goto LABEL_57;
      }
      *((_QWORD *)v27 + 1) = v27;
      *(_QWORD *)v27 = v27;
      *(_OWORD *)(v27 + 24) = 0;
      *((_DWORD *)v27 + 4) = -1610612724;
      *((_DWORD *)v27 + 5) = v25;
      *((_WORD *)v27 + 20) = 48;
      *((_WORD *)v27 + 21) = 0;
      v30 = (__int64 ***)v51[1];
      if ( *(__int64 **)v51[1] != v51 )
        goto LABEL_39;
      v12[1] = (__int64 *)v51[1];
      *v12 = v51;
      *v30 = v12;
      v51[1] = (__int64)v12;
    }
    if ( !a10 )
      goto LABEL_33;
    *a10 = 0;
    v31 = (char *)ExAllocateFromPagedLookasideList(&stru_14001A6C0);
    v13 = (__int64 **)v31;
    if ( !v31 )
    {
      v24 = -1073741670;
      if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v32) = BYTE1(xmmword_14001A3D0) & 4;
        LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          522,
          v32,
          v33,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          10,
          52,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          47,
          154);
      }
      goto LABEL_57;
    }
    *((_QWORD *)v31 + 1) = v31;
    *(_QWORD *)v31 = v31;
    *(_OWORD *)(v31 + 24) = 0;
    *((_DWORD *)v31 + 4) = -1610612733;
    *((_DWORD *)v31 + 5) = v25;
    *((_WORD *)v31 + 20) = 48;
    *((_WORD *)v31 + 21) = 0;
    v34 = (__int64 ***)v51[1];
    if ( *(__int64 **)v51[1] == v51 )
    {
      v13[1] = (__int64 *)v51[1];
      *v13 = v51;
      *v34 = v13;
      v51[1] = (__int64)v13;
LABEL_33:
      if ( a11 )
      {
        *a11 = 0;
        v35 = (char *)ExAllocateFromPagedLookasideList(&stru_14001A6C0);
        v14 = (__int64 **)v35;
        if ( !v35 )
        {
          v24 = -1073741670;
          if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v36) = BYTE1(xmmword_14001A3D0) & 4;
            LOBYTE(v37) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              522,
              v36,
              v37,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              10,
              53,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              65,
              154);
          }
          goto LABEL_57;
        }
        *((_QWORD *)v35 + 1) = v35;
        *(_QWORD *)v35 = v35;
        *(_OWORD *)(v35 + 24) = 0;
        *((_DWORD *)v35 + 4) = -1610612702;
        *((_DWORD *)v35 + 5) = v25;
        *((_WORD *)v35 + 20) = 48;
        *((_WORD *)v35 + 21) = 0;
        v38 = (__int64 ***)v51[1];
        if ( *(__int64 **)v51[1] != v51 )
          goto LABEL_39;
        v14[1] = (__int64 *)v51[1];
        *v14 = v51;
        *v38 = v14;
        v51[1] = (__int64)v14;
      }
      v39 = PrjfOpenReparsePoint(a3, 0x28u, v45, (__int64)v51, a6, a7);
      v24 = v39;
      if ( v39 >= 0 )
      {
        if ( a8 )
          *a8 = *((_BYTE *)v23 + 20) & 1;
        if ( a9 )
          *a9 = *((_BYTE *)v12 + 20) & 1;
        if ( a10 )
          *a10 = *((_BYTE *)v13 + 20) & 1;
        if ( a11 )
          *a11 = *((_BYTE *)v14 + 20) & 1;
      }
      else if ( v39 != -1073741772
             && v39 != -1073741766
             && ((BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        v41 = "Did NOT";
        v42 = "did";
        if ( !a10 )
          v42 = "did NOT";
        LOBYTE(v41) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v40) = BYTE1(xmmword_14001A3D0) & 4;
        WPP_RECORDER_AND_TRACE_SF_sDdZssss(
          (_DWORD)v42,
          v40,
          (_DWORD)v41,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v44,
          v46,
          v47,
          (__int64)FileHandle,
          (__int64)FileObject);
      }
      goto LABEL_57;
    }
LABEL_39:
    __fastfail(3u);
  }
  v24 = -1073741670;
  if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v21) = BYTE1(xmmword_14001A3D0) & 4;
    LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      522,
      v21,
      v22,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      10,
      50,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      11,
      154);
  }
LABEL_57:
  if ( Context )
    FltReleaseContext(Context);
  if ( v23 )
    ExFreeToPagedLookasideList(&stru_14001A6C0, v23);
  if ( v12 )
    ExFreeToPagedLookasideList(&stru_14001A6C0, v12);
  if ( v13 )
    ExFreeToPagedLookasideList(&stru_14001A6C0, v13);
  if ( v14 )
    ExFreeToPagedLookasideList(&stru_14001A6C0, v14);
  return v24;
}

```

## disassembly

```asm
0x14003be88  mov     rax, rsp
0x14003be8b  mov     [rax+20h], r9d
0x14003be8f  mov     [rax+18h], r8
0x14003be93  mov     [rax+10h], rdx
0x14003be97  mov     [rax+8], rcx
0x14003be9b  push    rbp
0x14003be9c  push    rbx
0x14003be9d  push    rsi
0x14003be9e  push    rdi
0x14003be9f  push    r12
0x14003bea1  push    r13
0x14003bea3  push    r14
0x14003bea5  push    r15
0x14003bea7  lea     rbp, [rax-47h]
0x14003beab  sub     rsp, 0A8h
0x14003beb2  cmp     [rbp+3Fh+arg_28], 0
0x14003beb7  xorps   xmm0, xmm0
0x14003beba  movups  xmmword ptr [rbp+3Fh+var_58], xmm0
0x14003bebe  mov     [rbp+3Fh+Context], 0
0x14003bec6  jz      loc_14003C496
0x14003becc  cmp     [rbp+3Fh+arg_30], 0
0x14003bed1  jz      loc_14003C496
0x14003bed7  lea     rdx, [rbp+3Fh+Context]; Context
0x14003bedb  mov     rcx, r8; Instance
0x14003bede  xor     ebx, ebx
0x14003bee0  xor     r14d, r14d
0x14003bee3  xor     esi, esi
0x14003bee5  mov     r15d, 80000004h
0x14003beeb  call    cs:__imp_FltGetInstanceContext
0x14003bef2  nop     dword ptr [rax+rax+00h]
0x14003bef7  test    eax, eax
0x14003bef9  js      short loc_14003BF04
0x14003befb  mov     rax, [rbp+3Fh+Context]
0x14003beff  test    rax, rax
0x14003bf02  jnz     short loc_14003BF0D
0x14003bf04  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003bf09  mov     rax, [rbp+3Fh+Context]
0x14003bf0d  mov     ecx, [rax+18h]
0x14003bf10  cmp     ecx, 2
0x14003bf13  jz      short loc_14003BF1F
0x14003bf15  cmp     ecx, 1Ch
0x14003bf18  jz      short loc_14003BF1F
0x14003bf1a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003bf1f  mov     rax, [rbp+3Fh+arg_58]
0x14003bf26  test    rax, rax
0x14003bf29  jz      short loc_14003BF2E
0x14003bf2b  mov     r15d, [rax]
0x14003bf2e  lea     rax, [rbp+3Fh+var_58]
0x14003bf32  mov     r12d, 30h ; '0'
0x14003bf38  mov     [rbp+3Fh+var_58+8], rax
0x14003bf3c  lea     rax, [rbp+3Fh+var_58]
0x14003bf40  mov     [rbp+3Fh+var_58], rax
0x14003bf44  mov     rax, [rbp+3Fh+arg_38]
0x14003bf4b  test    rax, rax
0x14003bf4e  jz      loc_14003C043
0x14003bf54  lea     rcx, stru_14001A6C0; Lookaside
0x14003bf5b  mov     [rax], bl
0x14003bf5d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003bf64  nop     dword ptr [rax+rax+00h]
0x14003bf69  mov     rdi, rax
0x14003bf6c  test    rax, rax
0x14003bf6f  jnz     loc_14003BFF5
0x14003bf75  mov     eax, 0C000009Ah
0x14003bf7a  mov     r15d, eax
0x14003bf7d  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003bf83  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003bf8a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003bf91  setnz   r8b
0x14003bf95  and     dl, 4
0x14003bf98  jnz     short loc_14003BFA3
0x14003bf9a  test    r8b, r8b
0x14003bf9d  jz      loc_14003C410
0x14003bfa3  mov     dword ptr [rsp+0E0h+var_90], eax
0x14003bfa7  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003bfae  mov     [rsp+0E0h+var_98], 80Bh
0x14003bfb6  mov     [rsp+0E0h+FileObject], rax
0x14003bfbb  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003bfc2  mov     [rsp+0E0h+FileHandle], rax
0x14003bfc7  mov     word ptr [rsp+0E0h+var_B0], 32h ; '2'
0x14003bfce  mov     r9, cs:WPP_GLOBAL_Control
0x14003bfd5  mov     ecx, 20Ah
0x14003bfda  mov     dword ptr [rsp+0E0h+var_B8], 0Ah
0x14003bfe2  mov     byte ptr [rsp+0E0h+var_C0], 2
0x14003bfe7  mov     r9, [r9+40h]
0x14003bfeb  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003bff0  jmp     loc_14003C410
0x14003bff5  mov     [rax+8], rdi
0x14003bff9  lea     rcx, [rbp+3Fh+var_58]
0x14003bffd  mov     [rax], rdi
0x14003c000  bts     r15d, 1Fh
0x14003c005  xorps   xmm0, xmm0
0x14003c008  movups  xmmword ptr [rax+18h], xmm0
0x14003c00c  mov     dword ptr [rax+10h], 9000001Ch
0x14003c013  mov     [rax+14h], r15d
0x14003c017  mov     [rax+28h], r12w
0x14003c01c  xor     eax, eax
0x14003c01e  mov     [rdi+2Ah], ax
0x14003c022  mov     rax, [rbp+3Fh+var_58+8]
0x14003c026  cmp     [rax], rcx
0x14003c029  jnz     loc_14003C2B0
0x14003c02f  mov     [rdi+8], rax
0x14003c033  lea     rcx, [rbp+3Fh+var_58]
0x14003c037  mov     [rdi], rcx
0x14003c03a  mov     [rax], rdi
0x14003c03d  mov     [rbp+3Fh+var_58+8], rdi
0x14003c041  jmp     short loc_14003C04A
0x14003c043  xor     edi, edi
0x14003c045  bts     r15d, 1Fh
0x14003c04a  mov     rax, [rbp+3Fh+arg_40]
0x14003c051  test    rax, rax
0x14003c054  jz      loc_14003C11C
0x14003c05a  lea     rcx, stru_14001A6C0; Lookaside
0x14003c061  mov     [rax], bl
0x14003c063  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003c06a  nop     dword ptr [rax+rax+00h]
0x14003c06f  mov     rbx, rax
0x14003c072  test    rax, rax
0x14003c075  jnz     short loc_14003C0D5
0x14003c077  mov     eax, 0C000009Ah
0x14003c07c  mov     r15d, eax
0x14003c07f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003c085  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c08c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c093  setnz   r8b
0x14003c097  and     dl, 4
0x14003c09a  jnz     short loc_14003C0A5
0x14003c09c  test    r8b, r8b
0x14003c09f  jz      loc_14003C410
0x14003c0a5  mov     dword ptr [rsp+0E0h+var_90], eax
0x14003c0a9  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c0b0  mov     [rsp+0E0h+var_98], 81Dh
0x14003c0b8  mov     [rsp+0E0h+FileObject], rax
0x14003c0bd  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c0c4  mov     [rsp+0E0h+FileHandle], rax
0x14003c0c9  mov     word ptr [rsp+0E0h+var_B0], 33h ; '3'
0x14003c0d0  jmp     loc_14003BFCE
0x14003c0d5  mov     [rax+8], rbx
0x14003c0d9  lea     rcx, [rbp+3Fh+var_58]
0x14003c0dd  mov     [rax], rbx
0x14003c0e0  xorps   xmm0, xmm0
0x14003c0e3  movups  xmmword ptr [rax+18h], xmm0
0x14003c0e7  mov     dword ptr [rax+10h], 0A000000Ch
0x14003c0ee  mov     [rax+14h], r15d
0x14003c0f2  mov     [rax+28h], r12w
0x14003c0f7  xor     eax, eax
0x14003c0f9  mov     [rbx+2Ah], ax
0x14003c0fd  mov     rax, [rbp+3Fh+var_58+8]
0x14003c101  cmp     [rax], rcx
0x14003c104  jnz     loc_14003C2B0
0x14003c10a  mov     [rbx+8], rax
0x14003c10e  lea     rcx, [rbp+3Fh+var_58]
0x14003c112  mov     [rbx], rcx
0x14003c115  mov     [rax], rbx
0x14003c118  mov     [rbp+3Fh+var_58+8], rbx
0x14003c11c  mov     r13, [rbp+3Fh+arg_48]
0x14003c123  test    r13, r13
0x14003c126  jz      loc_14003C1F1
0x14003c12c  lea     rcx, stru_14001A6C0; Lookaside
0x14003c133  mov     [r13+0], sil
0x14003c137  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003c13e  nop     dword ptr [rax+rax+00h]
0x14003c143  mov     r14, rax
0x14003c146  test    rax, rax
0x14003c149  jnz     short loc_14003C1A9
0x14003c14b  mov     eax, 0C000009Ah
0x14003c150  mov     r15d, eax
0x14003c153  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003c159  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c160  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c167  setnz   r8b
0x14003c16b  and     dl, 4
0x14003c16e  jnz     short loc_14003C179
0x14003c170  test    r8b, r8b
0x14003c173  jz      loc_14003C410
0x14003c179  mov     dword ptr [rsp+0E0h+var_90], eax
0x14003c17d  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c184  mov     [rsp+0E0h+var_98], 82Fh
0x14003c18c  mov     [rsp+0E0h+FileObject], rax
0x14003c191  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c198  mov     [rsp+0E0h+FileHandle], rax
0x14003c19d  mov     word ptr [rsp+0E0h+var_B0], 34h ; '4'
0x14003c1a4  jmp     loc_14003BFCE
0x14003c1a9  mov     [rax+8], r14
0x14003c1ad  lea     rcx, [rbp+3Fh+var_58]
0x14003c1b1  mov     [rax], r14
0x14003c1b4  xorps   xmm0, xmm0
0x14003c1b7  movups  xmmword ptr [rax+18h], xmm0
0x14003c1bb  mov     dword ptr [rax+10h], 0A0000003h
0x14003c1c2  mov     [rax+14h], r15d
0x14003c1c6  mov     [rax+28h], r12w
0x14003c1cb  xor     eax, eax
0x14003c1cd  mov     [r14+2Ah], ax
0x14003c1d2  mov     rax, [rbp+3Fh+var_58+8]
0x14003c1d6  cmp     [rax], rcx
0x14003c1d9  jnz     loc_14003C2B0
0x14003c1df  mov     [r14+8], rax
0x14003c1e3  lea     rcx, [rbp+3Fh+var_58]
0x14003c1e7  mov     [r14], rcx
0x14003c1ea  mov     [rax], r14
0x14003c1ed  mov     [rbp+3Fh+var_58+8], r14
0x14003c1f1  mov     r12, [rbp+3Fh+arg_50]
0x14003c1f8  test    r12, r12
0x14003c1fb  jz      loc_14003C2C9
0x14003c201  lea     rcx, stru_14001A6C0; Lookaside
0x14003c208  mov     [r12], sil
0x14003c20c  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003c213  nop     dword ptr [rax+rax+00h]
0x14003c218  mov     rsi, rax
0x14003c21b  test    rax, rax
0x14003c21e  jnz     short loc_14003C27E
0x14003c220  mov     eax, 0C000009Ah
0x14003c225  mov     r15d, eax
0x14003c228  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003c22e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c235  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c23c  setnz   r8b
0x14003c240  and     dl, 4
0x14003c243  jnz     short loc_14003C24E
0x14003c245  test    r8b, r8b
0x14003c248  jz      loc_14003C410
0x14003c24e  mov     dword ptr [rsp+0E0h+var_90], eax
0x14003c252  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c259  mov     [rsp+0E0h+var_98], 841h
0x14003c261  mov     [rsp+0E0h+FileObject], rax
0x14003c266  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c26d  mov     [rsp+0E0h+FileHandle], rax
0x14003c272  mov     word ptr [rsp+0E0h+var_B0], 35h ; '5'
0x14003c279  jmp     loc_14003BFCE
0x14003c27e  mov     [rax+8], rsi
0x14003c282  lea     rcx, [rbp+3Fh+var_58]
0x14003c286  mov     [rax], rsi
0x14003c289  xorps   xmm0, xmm0
0x14003c28c  movups  xmmword ptr [rax+18h], xmm0
0x14003c290  mov     dword ptr [rax+10h], 0A0000022h
0x14003c297  mov     [rax+14h], r15d
0x14003c29b  mov     word ptr [rax+28h], 30h ; '0'
0x14003c2a1  xor     eax, eax
0x14003c2a3  mov     [rsi+2Ah], ax
0x14003c2a7  mov     rax, [rbp+3Fh+var_58+8]
0x14003c2ab  cmp     [rax], rcx
0x14003c2ae  jz      short loc_14003C2B7
0x14003c2b0  mov     ecx, 3
0x14003c2b5  int     29h; Win8: RtlFailFast(ecx)
0x14003c2b7  mov     [rsi+8], rax
0x14003c2bb  lea     rcx, [rbp+3Fh+var_58]
0x14003c2bf  mov     [rsi], rcx
0x14003c2c2  mov     [rax], rsi
0x14003c2c5  mov     [rbp+3Fh+var_58+8], rsi
0x14003c2c9  mov     rax, [rbp+3Fh+arg_30]
0x14003c2cd  mov     r9d, [rbp+3Fh+arg_18]
0x14003c2d1  mov     r8, [rbp+3Fh+arg_8]
0x14003c2d5  mov     rdx, [rbp+3Fh+arg_0]
0x14003c2d9  mov     rcx, [rbp+3Fh+Instance]; Instance
0x14003c2dd  mov     [rsp+0E0h+FileObject], rax; FileObject
0x14003c2e2  mov     rax, [rbp+3Fh+arg_28]
0x14003c2e6  mov     [rsp+0E0h+FileHandle], rax; FileHandle
0x14003c2eb  lea     rax, [rbp+3Fh+var_58]
0x14003c2ef  mov     [rsp+0E0h+var_B0], rax; __int64
0x14003c2f4  mov     [rsp+0E0h+var_C0], 28h ; '('; ULONG
0x14003c2fc  call    PrjfOpenReparsePoint
0x14003c301  mov     r15d, eax
0x14003c304  test    eax, eax
0x14003c306  jns     loc_14003C3C9
0x14003c30c  cmp     eax, 0C0000034h
0x14003c311  jz      loc_14003C410
0x14003c317  cmp     eax, 0C000003Ah
0x14003c31c  jz      loc_14003C410
0x14003c322  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003c328  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c32f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c336  setnz   al
0x14003c339  mov     [rbp+3Fh+arg_20], al
0x14003c33c  and     dl, 4
0x14003c33f  jnz     short loc_14003C349
0x14003c341  test    al, al
0x14003c343  jz      loc_14003C410
0x14003c349  test    r12, r12
0x14003c34c  lea     rax, aDidNot; "did NOT"
0x14003c353  lea     r10, aDid; "did"
0x14003c35a  mov     r9, r10
0x14003c35d  lea     r8, aDidNot_0; "Did NOT"
0x14003c364  cmovz   r9, rax
0x14003c368  mov     rcx, r10
0x14003c36b  mov     [rsp+78h], r9
0x14003c370  test    r13, r13
0x14003c373  mov     r9, cs:WPP_GLOBAL_Control
0x14003c37a  cmovz   rcx, rax
0x14003c37e  cmp     [rbp+3Fh+arg_40], 0
0x14003c386  mov     [rsp+0E0h+var_70], rcx
0x14003c38b  cmovz   r10, rax
0x14003c38f  lea     rax, aDid_0; "Did"
0x14003c396  cmp     [rbp+3Fh+arg_38], 0
0x14003c39e  mov     r9, [r9+40h]
0x14003c3a2  cmovz   rax, r8
0x14003c3a6  mov     [rsp+0E0h+var_78], r10
0x14003c3ab  mov     r8b, [rbp+3Fh+arg_20]
0x14003c3af  mov     [rsp+0E0h+var_80], rax
0x14003c3b4  mov     rax, [rbp+3Fh+arg_0]
0x14003c3b8  mov     [rsp+0E0h+var_88], rax
0x14003c3bd  mov     dword ptr [rsp+0E0h+var_90], r15d
  ... truncated ...
```
