# sub_1800ECDE0

- ea: `0x1800ecde0`
- end: `0x1800ed2f5`
- name: `sub_1800ECDE0`
- size: `1301`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800018b0`
- `0x180005d20`
- `0x18000ae10`
- `0x18003f940`
- `0x18004038c`
- `0x180051e44`
- `0x180083a48`
- `0x1800ecde0`
- `0x180146950`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ed2b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ed2b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ed05a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ed05a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ece71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecf1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecfc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed08a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed174`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed217`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ece71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecf1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecfc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed08a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed174`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed217`

## pseudocode

```c
__int64 __fastcall sub_1800ECDE0(PROPVARIANT *a1, __int64 a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 (__fastcall ***v6)(); // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 (__fastcall ***v11)(); // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 (__fastcall ***v16)(); // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  char *v19; // rax
  __int64 (__fastcall ***v20)(); // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 (__fastcall ***v24)(); // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 (__fastcall ***v27)(); // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  char v31[4]; // [rsp+30h] [rbp-98h] BYREF
  int v32[3]; // [rsp+34h] [rbp-94h] BYREF
  _QWORD v33[10]; // [rsp+40h] [rbp-88h] BYREF

  memset(v33, 0, sizeof(v33));
  v32[0] = 0;
  sub_18000AE10(v31, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 640);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a2 + 96LL))(a2, v33, 1);
  if ( v5 < 0 )
  {
    v6 = (__int64 (__fastcall ***)())qword_180171350;
    if ( !qword_180171350 )
    {
      v7 = MFGetCallStackTracingWeakReference(0, v4);
      qword_180171350 = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v6 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = sub_1800018B0(v6);
      if ( *(_DWORD *)(v8 + 1996) != v5 )
        sub_180083A48(v8, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 640, (unsigned int)v5);
    }
    if ( !byte_1801712C8 )
      goto LABEL_69;
    v9 = 60;
    goto LABEL_12;
  }
  v10 = v33[2];
  if ( v33[2] >= 0xFFFFFFFF )
  {
    v11 = (__int64 (__fastcall ***)())qword_180171350;
    v5 = -2147418113;
    if ( !qword_180171350 )
    {
      v12 = MFGetCallStackTracingWeakReference(0, v4);
      qword_180171350 = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v11 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = sub_1800018B0(v11);
      if ( *(_DWORD *)(v13 + 1996) != -2147418113 )
        sub_180083A48(v13, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 649, 2147549183LL);
    }
    if ( !byte_1801712C8 )
      goto LABEL_69;
    v14 = 61;
    goto LABEL_68;
  }
  v15 = LODWORD(v33[2]) + 47;
  if ( LODWORD(v33[2]) >= 0xFFFFFFD1 )
  {
    v16 = (__int64 (__fastcall ***)())qword_180171350;
    v5 = -2147024362;
    if ( !qword_180171350 )
    {
      v17 = MFGetCallStackTracingWeakReference(0, v4);
      qword_180171350 = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v16 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = sub_1800018B0(v16);
      if ( *(_DWORD *)(v18 + 1996) != -2147024362 )
        sub_180083A48(v18, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 654, 2147942934LL);
    }
    if ( !byte_1801712C8 )
      goto LABEL_69;
    v9 = 62;
    goto LABEL_12;
  }
  a1[5].vt = 65;
  a1[5].lVal = v15;
  v19 = (char *)CoTaskMemAlloc(v15);
  a1[5].bstrblobVal.pData = (BYTE *)v19;
  if ( !v19 )
  {
    v20 = (__int64 (__fastcall ***)())qword_180171350;
    v5 = -2147024882;
    if ( !qword_180171350 )
    {
      v21 = MFGetCallStackTracingWeakReference(0, 0);
      qword_180171350 = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v20 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = sub_1800018B0(v20);
      if ( *(_DWORD *)(v22 + 1996) != -2147024882 )
        sub_180083A48(v22, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 664, 2147942414LL);
    }
    if ( !byte_1801712C8 )
      goto LABEL_69;
    v9 = 63;
    goto LABEL_12;
  }
  *v19 = 3;
  *(_DWORD *)(v19 + 1) = v10;
  *(_OWORD *)(v19 + 5) = xmmword_180162040;
  *(_QWORD *)(v19 + 19) = 0x6700650070LL;
  *(_OWORD *)(v19 + 27) = xmmword_180162088;
  *(_DWORD *)(v19 + 43) = 108;
  v5 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, int *))(*(_QWORD *)a2 + 24LL))(a2, v19 + 47, v10, v32);
  if ( v5 < 0 )
  {
    v24 = (__int64 (__fastcall ***)())qword_180171350;
    if ( !qword_180171350 )
    {
      v25 = MFGetCallStackTracingWeakReference(0, v23);
      qword_180171350 = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v24 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = sub_1800018B0(v24);
      if ( *(_DWORD *)(v26 + 1996) != v5 )
        sub_180083A48(v26, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 685, (unsigned int)v5);
    }
    if ( !byte_1801712C8 )
      goto LABEL_69;
    v9 = 64;
LABEL_12:
    sub_180051E44(*((_QWORD *)RequestContext + 2), v9, qword_180162120, a1, v5);
LABEL_69:
    PropVariantClear(a1 + 5);
    goto LABEL_70;
  }
  if ( v32[0] != v10 )
  {
    v27 = (__int64 (__fastcall ***)())qword_180171350;
    v5 = -2147418113;
    if ( !qword_180171350 )
    {
      v28 = MFGetCallStackTracingWeakReference(0, v23);
      qword_180171350 = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v27 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = sub_1800018B0(v27);
      if ( *(_DWORD *)(v29 + 1996) != -2147418113 )
        sub_180083A48(v29, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 689, 2147549183LL);
    }
    if ( !byte_1801712C8 )
      goto LABEL_69;
    v14 = 65;
LABEL_68:
    sub_180051E44(*((_QWORD *)RequestContext + 2), v14, qword_180162120, a1, -2147418113);
    goto LABEL_69;
  }
LABEL_70:
  sub_180005D20();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ecde0  mov     [rsp+arg_10], rbx
0x1800ecde5  push    rsi
0x1800ecde6  push    rdi
0x1800ecde7  push    r12
0x1800ecde9  push    r13
0x1800ecdeb  push    r14
0x1800ecded  sub     rsp, 0A0h
0x1800ecdf4  mov     rax, cs:__security_cookie
0x1800ecdfb  xor     rax, rsp
0x1800ecdfe  mov     [rsp+0C8h+var_38], rax
0x1800ece06  mov     r14, rdx
0x1800ece09  mov     rsi, rcx
0x1800ece0c  xor     edx, edx; Val
0x1800ece0e  lea     rcx, [rsp+0C8h+var_88]; void *
0x1800ece13  lea     r8d, [rdx+50h]; Size
0x1800ece17  call    memset
0x1800ece1c  mov     edi, 280h
0x1800ece21  mov     [rsp+0C8h+var_94], 0
0x1800ece29  lea     r12, aCwmthumbnailst_0; "CWMThumbnailStreamProperty::FormatAsNat"...
0x1800ece30  mov     r8d, edi
0x1800ece33  mov     rdx, r12
0x1800ece36  lea     rcx, [rsp+0C8h+var_98]
0x1800ece3b  call    sub_18000AE10
0x1800ece40  mov     rax, [r14]
0x1800ece43  lea     rdx, [rsp+0C8h+var_88]
0x1800ece48  mov     r8d, 1
0x1800ece4e  mov     rcx, r14
0x1800ece51  mov     rax, [rax+60h]
0x1800ece55  call    cs:__guard_dispatch_icall_fptr
0x1800ece5b  mov     ebx, eax
0x1800ece5d  test    eax, eax
0x1800ece5f  jns     loc_1800ECEF8
0x1800ece65  mov     rcx, cs:qword_180171350
0x1800ece6c  test    rcx, rcx
0x1800ece6f  jnz     short loc_1800ECEB9
0x1800ece71  call    cs:MFGetCallStackTracingWeakReference
0x1800ece78  nop     dword ptr [rax+rax+00h]
0x1800ece7d  mov     cs:qword_180171350, rax
0x1800ece84  mov     rcx, rax
0x1800ece87  test    rax, rax
0x1800ece8a  jz      short loc_1800ECEAB
0x1800ece8c  mov     rax, [rax]
0x1800ece8f  mov     edx, 7F0h
0x1800ece94  mov     rax, [rax+8]
0x1800ece98  call    cs:__guard_dispatch_icall_fptr
0x1800ece9e  test    eax, eax
0x1800ecea0  jz      short loc_1800ECEAB
0x1800ecea2  mov     rcx, cs:qword_180171350
0x1800ecea9  jmp     short loc_1800ECEB9
0x1800eceab  lea     rcx, off_1801703B0
0x1800eceb2  mov     cs:qword_180171350, rcx
0x1800eceb9  cmp     byte ptr [rcx+8], 0
0x1800ecebd  jz      short loc_1800ECEDD
0x1800ecebf  call    sub_1800018B0
0x1800ecec4  cmp     [rax+7CCh], ebx
0x1800ececa  jz      short loc_1800ECEDD
0x1800ececc  mov     r9d, ebx
0x1800ececf  mov     r8d, edi
0x1800eced2  mov     rdx, r12
0x1800eced5  mov     rcx, rax
0x1800eced8  call    sub_180083A48
0x1800ecedd  cmp     cs:byte_1801712C8, 1
0x1800ecee4  jb      loc_1800ED2B0
0x1800eceea  mov     edx, 3Ch ; '<'
0x1800eceef  mov     [rsp+0C8h+var_A8], ebx
0x1800ecef3  jmp     loc_1800ED296
0x1800ecef8  mov     rdi, [rsp+0C8h+var_78]
0x1800ecefd  mov     eax, 0FFFFFFFFh
0x1800ecf02  cmp     rdi, rax
0x1800ecf05  jb      loc_1800ECFA4
0x1800ecf0b  mov     rcx, cs:qword_180171350
0x1800ecf12  mov     edi, 8000FFFFh
0x1800ecf17  mov     ebx, edi
0x1800ecf19  test    rcx, rcx
0x1800ecf1c  jnz     short loc_1800ECF66
0x1800ecf1e  call    cs:MFGetCallStackTracingWeakReference
0x1800ecf25  nop     dword ptr [rax+rax+00h]
0x1800ecf2a  mov     cs:qword_180171350, rax
0x1800ecf31  mov     rcx, rax
0x1800ecf34  test    rax, rax
0x1800ecf37  jz      short loc_1800ECF58
0x1800ecf39  mov     rax, [rax]
0x1800ecf3c  mov     edx, 7F0h
0x1800ecf41  mov     rax, [rax+8]
0x1800ecf45  call    cs:__guard_dispatch_icall_fptr
0x1800ecf4b  test    eax, eax
0x1800ecf4d  jz      short loc_1800ECF58
0x1800ecf4f  mov     rcx, cs:qword_180171350
0x1800ecf56  jmp     short loc_1800ECF66
0x1800ecf58  lea     rcx, off_1801703B0
0x1800ecf5f  mov     cs:qword_180171350, rcx
0x1800ecf66  cmp     byte ptr [rcx+8], 0
0x1800ecf6a  jz      short loc_1800ECF8D
0x1800ecf6c  call    sub_1800018B0
0x1800ecf71  cmp     [rax+7CCh], edi
0x1800ecf77  jz      short loc_1800ECF8D
0x1800ecf79  mov     r9d, edi
0x1800ecf7c  mov     r8d, 289h
0x1800ecf82  mov     rdx, r12
0x1800ecf85  mov     rcx, rax
0x1800ecf88  call    sub_180083A48
0x1800ecf8d  cmp     cs:byte_1801712C8, 1
0x1800ecf94  jb      loc_1800ED2B0
0x1800ecf9a  mov     edx, 3Dh ; '='
0x1800ecf9f  jmp     loc_1800ED292
0x1800ecfa4  lea     eax, [rdi+2Fh]
0x1800ecfa7  cmp     eax, 2Fh ; '/'
0x1800ecfaa  jnb     loc_1800ED047
0x1800ecfb0  mov     rcx, cs:qword_180171350
0x1800ecfb7  mov     ebx, 80070216h
0x1800ecfbc  test    rcx, rcx
0x1800ecfbf  jnz     short loc_1800ED009
0x1800ecfc1  call    cs:MFGetCallStackTracingWeakReference
0x1800ecfc8  nop     dword ptr [rax+rax+00h]
0x1800ecfcd  mov     cs:qword_180171350, rax
0x1800ecfd4  mov     rcx, rax
0x1800ecfd7  test    rax, rax
0x1800ecfda  jz      short loc_1800ECFFB
0x1800ecfdc  mov     rax, [rax]
0x1800ecfdf  mov     edx, 7F0h
0x1800ecfe4  mov     rax, [rax+8]
0x1800ecfe8  call    cs:__guard_dispatch_icall_fptr
0x1800ecfee  test    eax, eax
0x1800ecff0  jz      short loc_1800ECFFB
0x1800ecff2  mov     rcx, cs:qword_180171350
0x1800ecff9  jmp     short loc_1800ED009
0x1800ecffb  lea     rcx, off_1801703B0
0x1800ed002  mov     cs:qword_180171350, rcx
0x1800ed009  cmp     byte ptr [rcx+8], 0
0x1800ed00d  jz      short loc_1800ED030
0x1800ed00f  call    sub_1800018B0
0x1800ed014  cmp     [rax+7CCh], ebx
0x1800ed01a  jz      short loc_1800ED030
0x1800ed01c  mov     r9d, ebx
0x1800ed01f  mov     r8d, 28Eh
0x1800ed025  mov     rdx, r12
0x1800ed028  mov     rcx, rax
0x1800ed02b  call    sub_180083A48
0x1800ed030  cmp     cs:byte_1801712C8, 1
0x1800ed037  jb      loc_1800ED2B0
0x1800ed03d  mov     edx, 3Eh ; '>'
0x1800ed042  jmp     loc_1800ECEEF
0x1800ed047  mov     r13d, 41h ; 'A'
0x1800ed04d  mov     ecx, eax; cb
0x1800ed04f  mov     [rsi+78h], r13w
0x1800ed054  mov     [rsi+80h], eax
0x1800ed05a  call    cs:CoTaskMemAlloc
0x1800ed061  nop     dword ptr [rax+rax+00h]
0x1800ed066  mov     [rsi+88h], rax
0x1800ed06d  mov     rdx, rax
0x1800ed070  test    rax, rax
0x1800ed073  jnz     loc_1800ED110
0x1800ed079  mov     rcx, cs:qword_180171350
0x1800ed080  mov     ebx, 8007000Eh
0x1800ed085  test    rcx, rcx
0x1800ed088  jnz     short loc_1800ED0D2
0x1800ed08a  call    cs:MFGetCallStackTracingWeakReference
0x1800ed091  nop     dword ptr [rax+rax+00h]
0x1800ed096  mov     cs:qword_180171350, rax
0x1800ed09d  mov     rcx, rax
0x1800ed0a0  test    rax, rax
0x1800ed0a3  jz      short loc_1800ED0C4
0x1800ed0a5  mov     rax, [rax]
0x1800ed0a8  mov     edx, 7F0h
0x1800ed0ad  mov     rax, [rax+8]
0x1800ed0b1  call    cs:__guard_dispatch_icall_fptr
0x1800ed0b7  test    eax, eax
0x1800ed0b9  jz      short loc_1800ED0C4
0x1800ed0bb  mov     rcx, cs:qword_180171350
0x1800ed0c2  jmp     short loc_1800ED0D2
0x1800ed0c4  lea     rcx, off_1801703B0
0x1800ed0cb  mov     cs:qword_180171350, rcx
0x1800ed0d2  cmp     byte ptr [rcx+8], 0
0x1800ed0d6  jz      short loc_1800ED0F9
0x1800ed0d8  call    sub_1800018B0
0x1800ed0dd  cmp     [rax+7CCh], ebx
0x1800ed0e3  jz      short loc_1800ED0F9
0x1800ed0e5  mov     r9d, ebx
0x1800ed0e8  mov     r8d, 298h
0x1800ed0ee  mov     rdx, r12
0x1800ed0f1  mov     rcx, rax
0x1800ed0f4  call    sub_180083A48
0x1800ed0f9  cmp     cs:byte_1801712C8, 1
0x1800ed100  jb      loc_1800ED2B0
0x1800ed106  mov     edx, 3Fh ; '?'
0x1800ed10b  jmp     loc_1800ECEEF
0x1800ed110  mov     byte ptr [rax], 3
0x1800ed113  lea     r9, [rsp+0C8h+var_94]
0x1800ed118  mov     [rax+1], edi
0x1800ed11b  mov     r8d, edi
0x1800ed11e  movups  xmm0, cs:xmmword_180162040
0x1800ed125  mov     rcx, r14
0x1800ed128  movups  xmmword ptr [rax+5], xmm0
0x1800ed12c  movsd   xmm1, qword ptr cs:xmmword_180162040+0Eh
0x1800ed134  movsd   qword ptr [rax+13h], xmm1
0x1800ed139  movups  xmm0, cs:xmmword_180162088
0x1800ed140  movups  xmmword ptr [rax+1Bh], xmm0
0x1800ed144  mov     eax, cs:dword_180162098
0x1800ed14a  mov     [rdx+2Bh], eax
0x1800ed14d  add     rdx, 2Fh ; '/'
0x1800ed151  mov     rax, [r14]
0x1800ed154  mov     rax, [rax+18h]
0x1800ed158  call    cs:__guard_dispatch_icall_fptr
0x1800ed15e  mov     ebx, eax
0x1800ed160  test    eax, eax
0x1800ed162  jns     loc_1800ED1FA
0x1800ed168  mov     rcx, cs:qword_180171350
0x1800ed16f  test    rcx, rcx
0x1800ed172  jnz     short loc_1800ED1BC
0x1800ed174  call    cs:MFGetCallStackTracingWeakReference
0x1800ed17b  nop     dword ptr [rax+rax+00h]
0x1800ed180  mov     cs:qword_180171350, rax
0x1800ed187  mov     rcx, rax
0x1800ed18a  test    rax, rax
0x1800ed18d  jz      short loc_1800ED1AE
0x1800ed18f  mov     rax, [rax]
0x1800ed192  mov     edx, 7F0h
0x1800ed197  mov     rax, [rax+8]
0x1800ed19b  call    cs:__guard_dispatch_icall_fptr
0x1800ed1a1  test    eax, eax
0x1800ed1a3  jz      short loc_1800ED1AE
0x1800ed1a5  mov     rcx, cs:qword_180171350
0x1800ed1ac  jmp     short loc_1800ED1BC
0x1800ed1ae  lea     rcx, off_1801703B0
0x1800ed1b5  mov     cs:qword_180171350, rcx
0x1800ed1bc  cmp     byte ptr [rcx+8], 0
0x1800ed1c0  jz      short loc_1800ED1E3
0x1800ed1c2  call    sub_1800018B0
0x1800ed1c7  cmp     [rax+7CCh], ebx
0x1800ed1cd  jz      short loc_1800ED1E3
0x1800ed1cf  mov     r9d, ebx
0x1800ed1d2  mov     r8d, 2ADh
0x1800ed1d8  mov     rdx, r12
0x1800ed1db  mov     rcx, rax
0x1800ed1de  call    sub_180083A48
0x1800ed1e3  cmp     cs:byte_1801712C8, 1
0x1800ed1ea  jb      loc_1800ED2B0
0x1800ed1f0  mov     edx, 40h ; '@'
0x1800ed1f5  jmp     loc_1800ECEEF
0x1800ed1fa  cmp     [rsp+0C8h+var_94], edi
0x1800ed1fe  jz      loc_1800ED2C0
0x1800ed204  mov     rcx, cs:qword_180171350
0x1800ed20b  mov     edi, 8000FFFFh
0x1800ed210  mov     ebx, edi
0x1800ed212  test    rcx, rcx
0x1800ed215  jnz     short loc_1800ED25F
0x1800ed217  call    cs:MFGetCallStackTracingWeakReference
0x1800ed21e  nop     dword ptr [rax+rax+00h]
0x1800ed223  mov     cs:qword_180171350, rax
0x1800ed22a  mov     rcx, rax
0x1800ed22d  test    rax, rax
0x1800ed230  jz      short loc_1800ED251
0x1800ed232  mov     rax, [rax]
0x1800ed235  mov     edx, 7F0h
0x1800ed23a  mov     rax, [rax+8]
0x1800ed23e  call    cs:__guard_dispatch_icall_fptr
0x1800ed244  test    eax, eax
0x1800ed246  jz      short loc_1800ED251
0x1800ed248  mov     rcx, cs:qword_180171350
0x1800ed24f  jmp     short loc_1800ED25F
0x1800ed251  lea     rcx, off_1801703B0
0x1800ed258  mov     cs:qword_180171350, rcx
0x1800ed25f  cmp     byte ptr [rcx+8], 0
0x1800ed263  jz      short loc_1800ED286
0x1800ed265  call    sub_1800018B0
0x1800ed26a  cmp     [rax+7CCh], edi
0x1800ed270  jz      short loc_1800ED286
0x1800ed272  mov     r9d, edi
0x1800ed275  mov     r8d, 2B1h
0x1800ed27b  mov     rdx, r12
0x1800ed27e  mov     rcx, rax
0x1800ed281  call    sub_180083A48
0x1800ed286  cmp     cs:byte_1801712C8, 1
0x1800ed28d  jb      short loc_1800ED2B0
0x1800ed28f  mov     edx, r13d
0x1800ed292  mov     [rsp+0C8h+var_A8], edi
0x1800ed296  mov     rcx, cs:RequestContext
0x1800ed29d  lea     r8, qword_180162120
0x1800ed2a4  mov     r9, rsi
0x1800ed2a7  mov     rcx, [rcx+10h]
0x1800ed2ab  call    sub_180051E44
0x1800ed2b0  lea     rcx, [rsi+78h]; pvar
0x1800ed2b4  call    cs:PropVariantClear
0x1800ed2bb  nop     dword ptr [rax+rax+00h]
0x1800ed2c0  lea     rcx, [rsp+0C8h+var_98]
0x1800ed2c5  call    sub_180005D20
0x1800ed2ca  mov     eax, ebx
0x1800ed2cc  mov     rcx, [rsp+0C8h+var_38]
0x1800ed2d4  xor     rcx, rsp; StackCookie
0x1800ed2d7  call    __security_check_cookie
0x1800ed2dc  mov     rbx, [rsp+0C8h+arg_10]
0x1800ed2e4  add     rsp, 0A0h
0x1800ed2eb  pop     r14
0x1800ed2ed  pop     r13
0x1800ed2ef  pop     r12
0x1800ed2f1  pop     rdi
0x1800ed2f2  pop     rsi
0x1800ed2f3  retn
```
