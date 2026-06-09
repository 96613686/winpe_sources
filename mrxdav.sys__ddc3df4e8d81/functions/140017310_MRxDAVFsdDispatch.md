# MRxDAVFsdDispatch

- ea: `0x140017310`
- end: `0x140017b72`
- name: `MRxDAVFsdDispatch`
- size: `2146`
- prototype: `__int64 __fastcall(struct _RDBSS_DEVICE_OBJECT *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140002ac4`
- `0x140002ea8`
- `0x140002f34`
- `0x140002fec`
- `0x140017310`
- `0x140018188`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140017404`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017475`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400174fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001754d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400175b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017622`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001768e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400176f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001779b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400177f0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001781a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400178b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001791d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017988`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017a29`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017ab2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017b0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017404`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017475`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400174fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001754d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400175b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017622`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001768e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400176f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001779b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400177f0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001781a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400178b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001791d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017988`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017a29`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017ab2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017b0d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017585`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400175f1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001765d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400176c9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017585`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400175f1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001765d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400176c9`
- `ntoskrnl!IofCompleteRequest` at `0x140017b4f`
- `ntoskrnl!IofCompleteRequest` at `0x140017b4f`
- `rdbss!RxFsdDispatch` at `0x140017a62`
- `rdbss!RxFsdDispatch` at `0x140017a62`

## pseudocode

```c
__int64 __fastcall MRxDAVFsdDispatch(struct _RDBSS_DEVICE_OBJECT *a1, __int64 a2)
{
  IRP *v2; // r14
  __int64 v3; // r8
  unsigned __int8 v4; // dl
  __int64 v5; // rbx
  __int64 v6; // rdi
  KPROCESSOR_MODE RequestorMode; // al
  int v8; // ecx
  int v9; // r14d
  unsigned int v10; // r14d
  IRP *v11; // rcx
  _WORD *v12; // rax
  int v13; // edx
  __int64 v14; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v16; // rbx
  HANDLE v17; // rax
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  unsigned int v21; // eax
  __int64 v22; // rbx
  HANDLE v23; // rax
  __int64 v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rbx
  HANDLE v27; // rax
  __int64 v28; // rbx
  HANDLE v29; // rax
  __int64 v30; // rbx
  HANDLE v31; // rax
  __int64 v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rbx
  HANDLE v36; // rax
  __int64 v37; // rsi
  int v38; // edi
  HANDLE v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdi
  unsigned int v43; // eax
  int v44; // edx
  int v45; // r8d
  unsigned int v46; // ecx
  _WORD *v47; // rdx
  _WORD *v48; // rax
  bool v49; // zf
  int v50; // eax
  __int64 v51; // rbx
  unsigned int v52; // eax
  NTSTATUS v53; // eax
  __int64 v54; // rsi
  HANDLE v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  int v59; // [rsp+40h] [rbp-98h]
  int v60; // [rsp+40h] [rbp-98h]
  __int64 v61; // [rsp+48h] [rbp-90h]
  _WORD *v62; // [rsp+58h] [rbp-80h]
  _WORD *v63; // [rsp+60h] [rbp-78h]
  UNICODE_STRING String1; // [rsp+68h] [rbp-70h] BYREF
  _WORD *v65; // [rsp+78h] [rbp-60h]
  __int64 v66; // [rsp+80h] [rbp-58h]
  __int128 v67; // [rsp+88h] [rbp-50h] BYREF
  unsigned __int8 v70; // [rsp+F0h] [rbp+18h]
  unsigned __int8 v71; // [rsp+F8h] [rbp+20h]

  v2 = (IRP *)a2;
  v3 = *(_QWORD *)(a2 + 184);
  v4 = *(_BYTE *)v3;
  v70 = *(_BYTE *)v3;
  v71 = *(_BYTE *)(v3 + 1);
  v5 = *(_QWORD *)(v3 + 48);
  v61 = v5;
  v6 = 0;
  v63 = 0;
  if ( *(_BYTE *)v3 != 14 || *(_DWORD *)(v3 + 24) != 1311123 )
    goto LABEL_65;
  RequestorMode = v2->RequestorMode;
  v65 = 0;
  v8 = 1;
  String1 = 0;
  v67 = 0;
  v9 = 0;
  if ( RequestorMode )
  {
    v10 = -1073741808;
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  v66 = *(_QWORD *)(v3 + 32);
  v12 = (_WORD *)(*(_QWORD *)(v66 + 32) + 2LL);
  v62 = v12;
  v13 = *(unsigned __int16 *)(v66 + 24) - 2;
  v59 = v13;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_qD(v14, 25, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, CurrentThreadId, v59);
      v12 = v62;
      v8 = 1;
      v13 = v59;
    }
    else
    {
      v12 = (_WORD *)(*(_QWORD *)(v66 + 32) + 2LL);
    }
  }
  if ( !v13 )
  {
    v10 = -1073741634;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v17 = PsGetCurrentThreadId();
      WPP_SF_q(v16, 26, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v17);
    }
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  while ( 1 )
  {
    if ( *v12 == 92 )
    {
      if ( !v8 )
        break;
      v6 = (__int64)v12;
      v65 = v12;
      v8 = 0;
    }
    else if ( v8 )
    {
      goto LABEL_19;
    }
    v9 += 2;
LABEL_19:
    v13 -= 2;
    if ( !v13 )
      break;
    ++v12;
  }
  if ( !v6 || v9 == 2 )
  {
    v10 = -1073741634;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_61;
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v33 = PsGetCurrentThreadId();
      v34 = 28;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_61;
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v33 = PsGetCurrentThreadId();
      v34 = 27;
    }
    WPP_SF_q(v32, v34, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v33);
LABEL_61:
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v19 = PsGetCurrentThreadId();
    WPP_SF_qD(v18, 29, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v19, v9);
  }
  String1.Buffer = (PWSTR)__PAIR64__(HIDWORD(v65), v6);
  String1.Length = v9;
  String1.MaximumLength = v9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qZ(v20, 30, (unsigned int)WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v21, (__int64)&String1);
  }
  if ( RtlEqualUnicodeString(&String1, &str_PipeShareName, 1u) )
  {
    v10 = -1073741634;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v23 = PsGetCurrentThreadId();
      WPP_SF_q(v22, 31, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v23);
    }
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  if ( RtlEqualUnicodeString(&String1, &str_MailSlotShareName, 1u) )
  {
    v10 = -1073741634;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v25 = PsGetCurrentThreadId();
      WPP_SF_q(v24, 32, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v25);
    }
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  if ( RtlEqualUnicodeString(&String1, &str_IpcShareName, 1u) )
  {
    v10 = -1073741634;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v27 = PsGetCurrentThreadId();
      WPP_SF_q(v26, 33, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v27);
    }
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  if ( RtlEqualUnicodeString(&String1, &str_DavWWWRootShareName, 1u) )
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v28 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v29 = PsGetCurrentThreadId();
      WPP_SF_q(v28, 34, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v29);
    }
    v11 = (IRP *)a2;
    **(_DWORD **)(a2 + 112) = v6 - *(_DWORD *)(v66 + 32) + 22;
    goto LABEL_102;
  }
  *((_QWORD *)&v67 + 1) = *(_QWORD *)(v66 + 32);
  WORD1(v67) = *(_WORD *)(v66 + 24);
  LOWORD(v67) = WORD1(v67);
  if ( !(unsigned int)MRxDAVSkipIrps(v66, &v67, 1) )
  {
    v10 = -1073741634;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v31 = PsGetCurrentThreadId();
      WPP_SF_q(v30, 35, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v31);
    }
    v11 = (IRP *)a2;
    goto LABEL_102;
  }
  v2 = (IRP *)a2;
  v5 = v61;
  v6 = 0;
  v4 = 14;
LABEL_65:
  if ( !v4 )
  {
    if ( !(unsigned int)MRxDAVSkipIrps(a1, v5 + 88, 0) )
    {
      v10 = -1073741634;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v35 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v36 = PsGetCurrentThreadId();
        WPP_SF_q(v35, 36, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v36);
      }
      v11 = (IRP *)a2;
      goto LABEL_102;
    }
    v4 = v70;
  }
  if ( v5 )
  {
    v6 = *(_QWORD *)(v5 + 96);
    v63 = (_WORD *)v6;
  }
  v60 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v37 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v38 = v4;
    v39 = PsGetCurrentThreadId();
    WPP_SF_qddq(v37, v40, v41, v39, v38, v71, v61);
    v5 = v61;
    v6 = (__int64)v63;
  }
  if ( v6 && !v70 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v42 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v43 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qZq(v42, v44, v45, v43, v5 + 88, v61);
      v5 = v61;
    }
    v46 = *(unsigned __int16 *)(v5 + 88) >> 1;
    v6 = (__int64)v63;
    if ( v46 >= 2 && *v63 == 92 && v63[1] == 92 )
    {
      v60 = 1;
      v47 = v63 + 2;
      while ( v46 != 2 )
      {
        v48 = v47 + 1;
        v49 = *v47++ == 92;
        if ( v49 && *v48 )
        {
          v50 = 0;
          goto LABEL_91;
        }
        --v46;
      }
    }
  }
  v50 = v60;
LABEL_91:
  if ( v50 )
  {
    v10 = -1073741634;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v51 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v52 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v51, 40, (unsigned int)WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v52, v6);
    }
    v11 = (IRP *)a2;
LABEL_102:
    v11->IoStatus.Status = v10;
    v11->IoStatus.Information = 0;
    IofCompleteRequest(v11, 0);
  }
  else
  {
    v53 = RxFsdDispatch(a1, v2);
    v10 = v53;
    if ( v53
      && v53 != 259
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v54 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v55 = PsGetCurrentThreadId();
      WPP_SF_qLqdd(v54, v56, v57, v55, v10, v61, v70, v71);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140017310  mov     r11, rsp
0x140017313  mov     [r11+10h], rdx
0x140017317  mov     [r11+8], rcx
0x14001731b  push    rbx
0x14001731c  push    rsi
0x14001731d  push    rdi
0x14001731e  push    r12
0x140017320  push    r13
0x140017322  push    r14
0x140017324  push    r15
0x140017326  sub     rsp, 0A0h
0x14001732d  mov     r14, rdx
0x140017330  mov     r8, [rdx+0B8h]
0x140017337  mov     dl, [r8]
0x14001733a  mov     [rsp+0D8h+arg_10], dl
0x140017341  mov     al, [r8+1]
0x140017345  mov     [rsp+0D8h+arg_18], al
0x14001734c  mov     rbx, [r8+30h]
0x140017350  mov     [rsp+0D8h+var_90], rbx
0x140017355  xor     r15d, r15d
0x140017358  mov     edi, r15d
0x14001735b  mov     [rsp+0D8h+var_78], r15
0x140017360  cmp     dl, 0Eh
0x140017363  jnz     loc_140017854
0x140017369  cmp     dword ptr [r8+18h], 140193h
0x140017371  jnz     loc_140017854
0x140017377  mov     al, [r14+40h]
0x14001737b  mov     [rsp+0D8h+var_60], r15
0x140017380  lea     ecx, [r15+1]
0x140017384  mov     [rsp+0D8h+var_88], ecx
0x140017388  xorps   xmm0, xmm0
0x14001738b  movups  xmmword ptr [rsp+0D8h+String1.Length], xmm0
0x140017390  xorps   xmm1, xmm1
0x140017393  movups  xmmword ptr [r11-50h], xmm1
0x140017398  mov     r14d, r15d
0x14001739b  mov     [rsp+0D8h+var_98], r15d
0x1400173a0  test    al, al
0x1400173a2  jz      short loc_1400173B8
0x1400173a4  mov     r14d, 0C0000010h
0x1400173aa  mov     [rsp+0D8h+var_94], r14d
0x1400173af  mov     rcx, [r11+10h]
0x1400173b3  jmp     loc_140017B45
0x1400173b8  mov     rdx, [r8+20h]
0x1400173bc  mov     [rsp+0D8h+var_58], rdx
0x1400173c4  mov     rax, [rdx+20h]
0x1400173c8  mov     [rsp+0D8h+var_80], rax
0x1400173cd  add     rax, 2
0x1400173d1  mov     [rsp+0D8h+var_80], rax
0x1400173d6  movzx   edx, word ptr [rdx+18h]
0x1400173da  sub     edx, 2
0x1400173dd  mov     [rsp+0D8h+var_98], edx
0x1400173e1  lea     r12, WPP_GLOBAL_Control
0x1400173e8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400173ef  mov     r13d, 4000h
0x1400173f5  cmp     rbx, r12
0x1400173f8  jz      short loc_140017446
0x1400173fa  test    [rbx+2Ch], r13d
0x1400173fe  jz      short loc_140017441
0x140017400  mov     rbx, [rbx+18h]
0x140017404  call    cs:__imp_PsGetCurrentThreadId
0x14001740b  nop     dword ptr [rax+rax+00h]
0x140017410  mov     r9, rax
0x140017413  mov     edx, 19h
0x140017418  mov     eax, [rsp+0D8h+var_98]
0x14001741c  mov     dword ptr [rsp+0D8h+var_B8], eax
0x140017420  lea     rsi, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140017427  mov     r8, rsi
0x14001742a  mov     rcx, rbx
0x14001742d  call    WPP_SF_qD
0x140017432  mov     rax, [rsp+0D8h+var_80]
0x140017437  mov     ecx, [rsp+0D8h+var_88]
0x14001743b  mov     edx, [rsp+0D8h+var_98]
0x14001743f  jmp     short loc_14001744D
0x140017441  mov     rax, [rsp+0D8h+var_80]
0x140017446  lea     rsi, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x14001744d  test    edx, edx
0x14001744f  jnz     short loc_1400174A1
0x140017451  mov     r14d, 0C00000BEh
0x140017457  mov     [rsp+0D8h+var_94], r14d
0x14001745c  mov     rbx, cs:WPP_GLOBAL_Control
0x140017463  cmp     rbx, r12
0x140017466  jz      short loc_140017494
0x140017468  test    dword ptr [rbx+2Ch], 2000h
0x14001746f  jz      short loc_140017494
0x140017471  mov     rbx, [rbx+18h]
0x140017475  call    cs:__imp_PsGetCurrentThreadId
0x14001747c  nop     dword ptr [rax+rax+00h]
0x140017481  mov     r9, rax
0x140017484  mov     edx, 1Ah
0x140017489  mov     r8, rsi
0x14001748c  mov     rcx, rbx
0x14001748f  call    WPP_SF_q
0x140017494  mov     rcx, [rsp+0D8h+Irp]
0x14001749c  jmp     loc_140017B45
0x1400174a1  cmp     word ptr [rax], 5Ch ; '\'
0x1400174a5  jnz     short loc_1400174BC
0x1400174a7  test    ecx, ecx
0x1400174a9  jz      short loc_1400174D2
0x1400174ab  mov     rdi, rax
0x1400174ae  mov     [rsp+0D8h+var_60], rax
0x1400174b3  mov     ecx, r15d
0x1400174b6  mov     [rsp+0D8h+var_88], ecx
0x1400174ba  jmp     short loc_1400174C0
0x1400174bc  test    ecx, ecx
0x1400174be  jnz     short loc_1400174C9
0x1400174c0  add     r14d, 2
0x1400174c4  mov     [rsp+0D8h+var_98], r14d
0x1400174c9  add     edx, 0FFFFFFFEh
0x1400174cc  jnz     loc_140017846
0x1400174d2  test    rdi, rdi
0x1400174d5  jz      loc_1400177C7
0x1400174db  cmp     r14d, 2
0x1400174df  jz      loc_1400177C7
0x1400174e5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400174ec  cmp     rbx, r12
0x1400174ef  jz      short loc_14001751F
0x1400174f1  test    [rbx+2Ch], r13d
0x1400174f5  jz      short loc_14001751F
0x1400174f7  mov     rbx, [rbx+18h]
0x1400174fb  call    cs:__imp_PsGetCurrentThreadId
0x140017502  nop     dword ptr [rax+rax+00h]
0x140017507  mov     r9, rax
0x14001750a  mov     edx, 1Dh
0x14001750f  mov     dword ptr [rsp+0D8h+var_B8], r14d
0x140017514  mov     r8, rsi
0x140017517  mov     rcx, rbx
0x14001751a  call    WPP_SF_qD
0x14001751f  mov     dword ptr [rsp+0D8h+String1.Buffer], edi
0x140017523  mov     eax, dword ptr [rsp+0D8h+var_60+4]
0x140017527  mov     dword ptr [rsp+0D8h+String1.Buffer+4], eax
0x14001752b  mov     [rsp+0D8h+String1.Length], r14w
0x140017531  mov     [rsp+0D8h+String1.MaximumLength], r14w
0x140017537  mov     rbx, cs:WPP_GLOBAL_Control
0x14001753e  cmp     rbx, r12
0x140017541  jz      short loc_140017576
0x140017543  test    [rbx+2Ch], r13d
0x140017547  jz      short loc_140017576
0x140017549  mov     rbx, [rbx+18h]
0x14001754d  call    cs:__imp_PsGetCurrentThreadId
0x140017554  nop     dword ptr [rax+rax+00h]
0x140017559  mov     r9, rax
0x14001755c  mov     edx, 1Eh
0x140017561  lea     rax, [rsp+0D8h+String1]
0x140017566  mov     [rsp+0D8h+var_B8], rax
0x14001756b  mov     r8, rsi
0x14001756e  mov     rcx, rbx
0x140017571  call    WPP_SF_qZ
0x140017576  mov     r8b, 1; CaseInSensitive
0x140017579  lea     rdx, str_PipeShareName; String2
0x140017580  lea     rcx, [rsp+0D8h+String1]; String1
0x140017585  call    cs:__imp_RtlEqualUnicodeString
0x14001758c  nop     dword ptr [rax+rax+00h]
0x140017591  test    al, al
0x140017593  jz      short loc_1400175E2
0x140017595  mov     r14d, 0C00000BEh
0x14001759b  mov     [rsp+0D8h+var_94], r14d
0x1400175a0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400175a7  cmp     rbx, r12
0x1400175aa  jz      short loc_1400175D5
0x1400175ac  test    [rbx+2Ch], r13d
0x1400175b0  jz      short loc_1400175D5
0x1400175b2  mov     rbx, [rbx+18h]
0x1400175b6  call    cs:__imp_PsGetCurrentThreadId
0x1400175bd  nop     dword ptr [rax+rax+00h]
0x1400175c2  mov     r9, rax
0x1400175c5  mov     edx, 1Fh
0x1400175ca  mov     r8, rsi
0x1400175cd  mov     rcx, rbx
0x1400175d0  call    WPP_SF_q
0x1400175d5  mov     rcx, [rsp+0D8h+Irp]
0x1400175dd  jmp     loc_140017B45
0x1400175e2  mov     r8b, 1; CaseInSensitive
0x1400175e5  lea     rdx, str_MailSlotShareName; String2
0x1400175ec  lea     rcx, [rsp+0D8h+String1]; String1
0x1400175f1  call    cs:__imp_RtlEqualUnicodeString
0x1400175f8  nop     dword ptr [rax+rax+00h]
0x1400175fd  test    al, al
0x1400175ff  jz      short loc_14001764E
0x140017601  mov     r14d, 0C00000BEh
0x140017607  mov     [rsp+0D8h+var_94], r14d
0x14001760c  mov     rbx, cs:WPP_GLOBAL_Control
0x140017613  cmp     rbx, r12
0x140017616  jz      short loc_140017641
0x140017618  test    [rbx+2Ch], r13d
0x14001761c  jz      short loc_140017641
0x14001761e  mov     rbx, [rbx+18h]
0x140017622  call    cs:__imp_PsGetCurrentThreadId
0x140017629  nop     dword ptr [rax+rax+00h]
0x14001762e  mov     r9, rax
0x140017631  mov     edx, 20h ; ' '
0x140017636  mov     r8, rsi
0x140017639  mov     rcx, rbx
0x14001763c  call    WPP_SF_q
0x140017641  mov     rcx, [rsp+0D8h+Irp]
0x140017649  jmp     loc_140017B45
0x14001764e  mov     r8b, 1; CaseInSensitive
0x140017651  lea     rdx, str_IpcShareName; String2
0x140017658  lea     rcx, [rsp+0D8h+String1]; String1
0x14001765d  call    cs:__imp_RtlEqualUnicodeString
0x140017664  nop     dword ptr [rax+rax+00h]
0x140017669  test    al, al
0x14001766b  jz      short loc_1400176BA
0x14001766d  mov     r14d, 0C00000BEh
0x140017673  mov     [rsp+0D8h+var_94], r14d
0x140017678  mov     rbx, cs:WPP_GLOBAL_Control
0x14001767f  cmp     rbx, r12
0x140017682  jz      short loc_1400176AD
0x140017684  test    [rbx+2Ch], r13d
0x140017688  jz      short loc_1400176AD
0x14001768a  mov     rbx, [rbx+18h]
0x14001768e  call    cs:__imp_PsGetCurrentThreadId
0x140017695  nop     dword ptr [rax+rax+00h]
0x14001769a  mov     r9, rax
0x14001769d  mov     edx, 21h ; '!'
0x1400176a2  mov     r8, rsi
0x1400176a5  mov     rcx, rbx
0x1400176a8  call    WPP_SF_q
0x1400176ad  mov     rcx, [rsp+0D8h+Irp]
0x1400176b5  jmp     loc_140017B45
0x1400176ba  mov     r8b, 1; CaseInSensitive
0x1400176bd  lea     rdx, str_DavWWWRootShareName; String2
0x1400176c4  lea     rcx, [rsp+0D8h+String1]; String1
0x1400176c9  call    cs:__imp_RtlEqualUnicodeString
0x1400176d0  nop     dword ptr [rax+rax+00h]
0x1400176d5  test    al, al
0x1400176d7  jz      short loc_140017737
0x1400176d9  mov     r14d, r15d
0x1400176dc  mov     [rsp+0D8h+var_94], r15d
0x1400176e1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400176e8  cmp     rbx, r12
0x1400176eb  jz      short loc_140017716
0x1400176ed  test    [rbx+2Ch], r13d
0x1400176f1  jz      short loc_140017716
0x1400176f3  mov     rbx, [rbx+18h]
0x1400176f7  call    cs:__imp_PsGetCurrentThreadId
0x1400176fe  nop     dword ptr [rax+rax+00h]
0x140017703  mov     r9, rax
0x140017706  mov     edx, 22h ; '"'
0x14001770b  mov     r8, rsi
0x14001770e  mov     rcx, rbx
0x140017711  call    WPP_SF_q
0x140017716  mov     rcx, [rsp+0D8h+var_58]
0x14001771e  sub     edi, [rcx+20h]
0x140017721  add     edi, 16h
0x140017724  mov     rcx, [rsp+0D8h+Irp]
0x14001772c  mov     rax, [rcx+70h]
0x140017730  mov     [rax], edi
0x140017732  jmp     loc_140017B45
0x140017737  mov     rcx, [rsp+0D8h+var_58]
0x14001773f  mov     rax, [rcx+20h]
0x140017743  mov     [rsp+0D8h+var_48], rax
0x14001774b  movzx   eax, word ptr [rcx+18h]
0x14001774f  mov     [rsp+0D8h+var_4E], ax
0x140017757  mov     [rsp+0D8h+var_50], ax
0x14001775f  mov     r8d, 1
0x140017765  lea     rdx, [rsp+0D8h+var_50]
0x14001776d  call    MRxDAVSkipIrps
0x140017772  test    eax, eax
0x140017774  jnz     loc_14001786A
0x14001777a  mov     r14d, 0C00000BEh
0x140017780  mov     [rsp+0D8h+var_94], r14d
0x140017785  mov     rbx, cs:WPP_GLOBAL_Control
0x14001778c  cmp     rbx, r12
0x14001778f  jz      short loc_1400177BA
0x140017791  test    [rbx+2Ch], r13d
0x140017795  jz      short loc_1400177BA
0x140017797  mov     rbx, [rbx+18h]
0x14001779b  call    cs:__imp_PsGetCurrentThreadId
0x1400177a2  nop     dword ptr [rax+rax+00h]
0x1400177a7  mov     r9, rax
0x1400177aa  mov     edx, 23h ; '#'
0x1400177af  mov     r8, rsi
0x1400177b2  mov     rcx, rbx
0x1400177b5  call    WPP_SF_q
0x1400177ba  mov     rcx, [rsp+0D8h+Irp]
0x1400177c2  jmp     loc_140017B45
0x1400177c7  mov     r14d, 0C00000BEh
0x1400177cd  mov     [rsp+0D8h+var_94], r14d
0x1400177d2  test    rdi, rdi
0x1400177d5  jnz     short loc_140017801
0x1400177d7  mov     rbx, cs:WPP_GLOBAL_Control
0x1400177de  cmp     rbx, r12
0x1400177e1  jz      short loc_140017839
0x1400177e3  test    dword ptr [rbx+2Ch], 2000h
0x1400177ea  jz      short loc_140017839
0x1400177ec  mov     rbx, [rbx+18h]
0x1400177f0  call    cs:__imp_PsGetCurrentThreadId
0x1400177f7  nop     dword ptr [rax+rax+00h]
0x1400177fc  lea     edx, [rdi+1Bh]
0x1400177ff  jmp     short loc_14001782B
0x140017801  mov     rbx, cs:WPP_GLOBAL_Control
0x140017808  cmp     rbx, r12
0x14001780b  jz      short loc_140017839
0x14001780d  test    dword ptr [rbx+2Ch], 2000h
0x140017814  jz      short loc_140017839
0x140017816  mov     rbx, [rbx+18h]
0x14001781a  call    cs:__imp_PsGetCurrentThreadId
0x140017821  nop     dword ptr [rax+rax+00h]
0x140017826  mov     edx, 1Ch
0x14001782b  mov     r9, rax
  ... truncated ...
```
