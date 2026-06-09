# CDRollback_GetFTContextInformation(_DOT11_SSID const *,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong)

- ea: `0x140040680`
- end: `0x140040ef5`
- name: `?CDRollback_GetFTContextInformation@@YAPEAUNWF_FT_CONTEXT@@PEBU_DOT11_SSID@@HPEBEK1K1K@Z`
- size: `2165`
- prototype: `struct NWF_FT_CONTEXT *__fastcall(const struct _DOT11_SSID *, int, const unsigned __int8 *, unsigned int, struct DOT11_INFO_ELEMENT *Src, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140042a1c`
- `0x140046610`
- `0x140047794`
- `0x140047e48`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x140030244`
- `0x1400314ec`
- `0x140040680`
- `0x140048cc8`
- `0x14004cfe8`
- `0x140057a60`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040712`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040beb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040712`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040beb`
- `ntoskrnl!ExAllocatePool2` at `0x140040730`
- `ntoskrnl!ExAllocatePool2` at `0x140040730`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040afa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040c37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040afa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040c37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040e8c`

## pseudocode

```c
struct NWF_FT_CONTEXT *__fastcall CDRollback_GetFTContextInformation(
        const struct _DOT11_SSID *a1,
        int a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct DOT11_INFO_ELEMENT *Src,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8)
{
  char *v8; // rdi
  size_t v9; // rsi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v16; // r12
  unsigned __int8 v17; // bl
  struct DOT11_INFO_ELEMENT *v18; // rcx
  struct DOT11_INFO_ELEMENT *v19; // rcx
  unsigned int v20; // r9d
  unsigned __int64 v21; // r10
  char *v22; // r8
  __int64 v23; // rdx
  char v24; // al
  __int64 v25; // rax
  __int64 v26; // r9
  const unsigned __int8 *v27; // r15
  struct DOT11_INFO_ELEMENT *v28; // r14
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // r9
  __int64 v31; // rdx
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  unsigned int v34; // r13d
  unsigned __int8 v35; // r15
  unsigned int v36; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  char *v38; // rax
  _BYTE *v39; // rsi
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int8 v42; // al
  unsigned __int8 v43; // cl
  unsigned __int8 v44; // r9
  unsigned __int8 v45; // al
  __int64 v46; // rax
  _OWORD *v47; // rax
  unsigned int v49; // [rsp+20h] [rbp-69h]
  struct DOT11_INFO_ELEMENT *v50[2]; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v51[32]; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v53; // [rsp+E8h] [rbp+5Fh] BYREF

  v8 = 0;
  v9 = a4;
  v53 = 0;
  memset(v51, 0, 0x48u);
  v13 = v9 + 400;
  v50[0] = 0;
  if ( (unsigned int)(v9 + 400) < 0x10 )
  {
LABEL_115:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 428, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, 384, v9);
    goto LABEL_117;
  }
  if ( v13 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v13 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v13 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v13 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 2053731191);
LABEL_12:
  v16 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    goto LABEL_115;
  v8 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  Pool2[2] = 2053731191;
  memset(Pool2 + 4, 0, v9 + 384);
  *(_OWORD *)v8 = *(_OWORD *)&a1->uSSIDLength;
  *((_OWORD *)v8 + 1) = *(_OWORD *)&a1->ucSSID[12];
  *((_DWORD *)v8 + 8) = *(_DWORD *)&a1->ucSSID[28];
  memmove(v8 + 376, a3, v9);
  *((_DWORD *)v8 + 92) = v9;
  v17 = 0;
  if ( (unsigned int)GetDot11InfoElement((const unsigned __int8 *)v8 + 376, v9, 0x36u, v50)
    || (v18 = v50[0], *((_BYTE *)v50[0] + 1) != 3) )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_67;
    v31 = 429;
    goto LABEL_106;
  }
  *((struct DOT11_INFO_ELEMENT **)v8 + 8) = v50[0];
  *((_DWORD *)v8 + 13) = *((unsigned __int8 *)v18 + 1) + 2;
  *((_WORD *)v8 + 18) = *((_WORD *)v18 + 1);
  if ( (unsigned int)GetDot11InfoElement((const unsigned __int8 *)v8 + 376, v9, 0x37u, v50)
    || (v19 = v50[0], *((_BYTE *)v50[0] + 1) < 0x52u) )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_67;
    v31 = 430;
    goto LABEL_106;
  }
  *((struct DOT11_INFO_ELEMENT **)v8 + 9) = v50[0];
  *((_DWORD *)v8 + 14) = *((unsigned __int8 *)v19 + 1) + 2;
  *((_WORD *)v8 + 70) = *((_WORD *)v19 + 1);
  if ( a2 )
  {
    *((_BYTE *)v19 + 2) = 0;
    *(_BYTE *)(*((_QWORD *)v8 + 9) + 3LL) = 3;
  }
  v20 = 84;
  *((_QWORD *)v8 + 19) = (char *)v19 + 4;
  *((_QWORD *)v8 + 20) = (char *)v19 + 20;
  *((_QWORD *)v8 + 21) = (char *)v19 + 52;
  v21 = *((unsigned int *)v8 + 14);
  v22 = (char *)(*((_QWORD *)v8 + 9) + 84LL);
  if ( v21 >= 0x56 )
  {
    do
    {
      v23 = (unsigned __int8)v22[1];
      if ( v21 < v23 + (unsigned __int64)v20 + 2 )
        break;
      v24 = *v22;
      if ( *v22 == 1 )
      {
        if ( (_BYTE)v23 != 6 )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_67;
          v30 = (unsigned __int8)v22[1];
          v31 = 431;
          goto LABEL_44;
        }
        *((_QWORD *)v8 + 22) = v22;
      }
      else
      {
        switch ( v24 )
        {
          case 2:
            if ( (unsigned __int8)(v23 - 35) > 0x10u )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                goto LABEL_67;
              v30 = (unsigned __int8)v22[1];
              v31 = 432;
              goto LABEL_44;
            }
            *((_QWORD *)v8 + 24) = v22;
            break;
          case 3:
            if ( (unsigned __int8)(v23 - 1) > 0x2Fu )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                goto LABEL_67;
              v30 = (unsigned __int8)v22[1];
              v31 = 433;
              goto LABEL_44;
            }
            *((_QWORD *)v8 + 23) = v22;
            break;
          case 4:
            if ( (unsigned __int8)v23 < 9u )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                goto LABEL_67;
              v30 = (unsigned __int8)v22[1];
              v31 = 434;
              goto LABEL_44;
            }
            *((_QWORD *)v8 + 25) = v22;
            break;
          case 6:
            if ( (unsigned __int8)v23 < 9u )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                goto LABEL_67;
              v30 = (unsigned __int8)v22[1];
              v31 = 435;
              goto LABEL_44;
            }
            *((_QWORD *)v8 + 26) = v22;
            break;
        }
      }
      v25 = (unsigned __int8)v22[1];
      v20 += v25 + 2;
      v22 += v25 + 2;
    }
    while ( v21 >= (unsigned __int64)v20 + 2 );
  }
  v26 = *((_QWORD *)v8 + 23);
  if ( !v26 || !*((_QWORD *)v8 + 22) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        436,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        v26,
        *((_QWORD *)v8 + 22));
    goto LABEL_67;
  }
  v27 = (const unsigned __int8 *)Src;
  if ( Src && a6 )
  {
    v28 = Src;
    goto LABEL_59;
  }
  if ( !a2 )
  {
    if ( !(unsigned int)GetDot11InfoElement((const unsigned __int8 *)v8 + 376, v9, 0x30u, v50) )
      goto LABEL_58;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_67;
    v31 = 438;
LABEL_106:
    v30 = (unsigned int)v9;
LABEL_44:
    WPP_SF_d(v29->AttachedDevice, v31, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v30);
    goto LABEL_67;
  }
  if ( (unsigned int)GetDot11InfoElement(a7, a8, 0x30u, v50) )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_67;
    v30 = a8;
    v31 = 437;
    goto LABEL_44;
  }
LABEL_58:
  v28 = v50[0];
  if ( !v50[0] )
    goto LABEL_102;
LABEL_59:
  v17 = *((_BYTE *)v28 + 1) + 2;
  if ( *((_BYTE *)v28 + 1) == 0xFE
    || v17 > 0xEBu
    || v17 < *((_BYTE *)v28 + 1)
    || (unsigned int)IEPRSNParseIE(
                       (unsigned __int8 *)v28 + 2,
                       *((unsigned __int8 *)v28 + 1),
                       &v53,
                       (struct DOT11_RSN_IE_INFO *)v51) )
  {
LABEL_102:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 439, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v17, v9, 235);
    goto LABEL_67;
  }
  if ( (v53 & 0x10) == 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v33 = 440;
      v49 = v53;
LABEL_66:
      WPP_SF_Dd(v32->AttachedDevice, v33, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v17, v49);
    }
LABEL_67:
    if ( *v16 )
      ExFreeToNPagedLookasideList(*v16, v16);
    else
      ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
    v8 = 0;
    goto LABEL_117;
  }
  *((_DWORD *)v8 + 10) = v51[4];
  *((_DWORD *)v8 + 11) = v51[1];
  *((_DWORD *)v8 + 12) = v51[17];
  v34 = v53 & 0x40;
  LODWORD(v50[0]) = v34;
  if ( (v53 & 0x40) != 0 )
  {
    *((_WORD *)v8 + 108) = HIWORD(v51[10]);
    v8[218] = LOBYTE(v51[16]) + 2;
  }
  FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v51);
  if ( v28 == (struct DOT11_INFO_ELEMENT *)v27 )
  {
    v35 = v17 + (v34 != 0 ? 16 : 18) + (~(unsigned __int8)(v53 >> 4) & 2) - 16 * v8[216];
  }
  else
  {
    if ( !*((_WORD *)v8 + 108) )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_67;
      v33 = 441;
      v49 = v9;
      goto LABEL_66;
    }
    v35 = v17;
  }
  v36 = v35 + 16;
  if ( v36 > 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    if ( v36 > 0x100 )
      p_WaitListHead = &Lookaside;
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  v38 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
  if ( !v38 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 442, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v35, a6);
    goto LABEL_67;
  }
  *(_QWORD *)v38 = p_WaitListHead;
  v39 = v38 + 16;
  *((_DWORD *)v38 + 2) = 2053731191;
  memset(v38 + 16, 0, v35);
  v40 = *((_QWORD *)v8 + 11);
  if ( v40 )
  {
    v41 = v40 - 16;
    if ( *(_QWORD *)v41 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v41, (PVOID)v41);
    else
      ExFreePoolWithTag((PVOID)v41, *(_DWORD *)(v41 + 8));
  }
  *((_QWORD *)v8 + 11) = v39;
  *((_QWORD *)v8 + 10) = v39;
  if ( v28 == Src )
  {
    if ( !LODWORD(v50[0]) )
      v8[218] = v17 + (~(unsigned __int8)(v53 >> 4) & 2);
    v42 = v17;
    if ( (unsigned __int8)v8[218] < v17 )
      v42 = v8[218];
    memmove(v39, v28, v42);
    *((_DWORD *)v8 + 15) = v35;
    v39[1] = v35 - 2;
    *(_WORD *)&v39[(unsigned __int8)v8[218]] = 1;
    v43 = v8[218];
    v44 = v43 + 2;
    if ( *((_WORD *)v8 + 108) && v17 >= (unsigned __int64)v44 + 16 )
    {
      *(_OWORD *)&v39[v44] = *(_OWORD *)((char *)v28 + v44);
      v43 = *((_BYTE *)v16 + 234);
    }
    v45 = v44 + 16 * v8[216];
    if ( v17 > v45 )
      memmove(&v39[v43 + 18], (char *)v28 + v45, v17 - (unsigned __int64)v45);
    *((_QWORD *)v8 + 12) = &v39[(unsigned __int8)v8[218] + 2];
  }
  else
  {
    memmove(v39, v28, v17);
    *((_DWORD *)v8 + 15) = v17;
    v46 = *((unsigned __int8 *)v16 + 234);
    if ( a2 )
    {
      *(_OWORD *)(v8 + 104) = *(_OWORD *)&v39[v46 + 2];
    }
    else
    {
      v47 = &v39[v46 + 2];
      *(_OWORD *)(v8 + 120) = *v47;
      *((_QWORD *)v8 + 12) = v47;
    }
  }
LABEL_117:
  FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v51);
  return (struct NWF_FT_CONTEXT *)v8;
}

```

## disassembly

```asm
0x140040680  mov     [rsp-8+arg_0], rbx
0x140040685  mov     [rsp-8+arg_8], edx
0x140040689  push    rbp
0x14004068a  push    rsi
0x14004068b  push    rdi
0x14004068c  push    r12
0x14004068e  push    r13
0x140040690  push    r14
0x140040692  push    r15
0x140040694  lea     rbp, [rsp-7]
0x140040699  sub     rsp, 90h
0x1400406a0  xor     edi, edi
0x1400406a2  mov     esi, r9d
0x1400406a5  mov     r15, r8
0x1400406a8  mov     [rbp+37h+arg_18], edi
0x1400406ab  mov     r13d, edx
0x1400406ae  mov     r14, rcx
0x1400406b1  xor     edx, edx; Val
0x1400406b3  lea     rcx, [rbp+37h+var_80]; void *
0x1400406b7  lea     r8d, [rdi+48h]; Size
0x1400406bb  call    memset
0x1400406c0  lea     eax, [rsi+190h]
0x1400406c6  mov     [rbp+37h+var_90], rdi
0x1400406ca  cmp     eax, 10h
0x1400406cd  jb      loc_140040E9D
0x1400406d3  cmp     eax, 40h ; '@'
0x1400406d6  ja      short loc_1400406E1
0x1400406d8  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400406df  jmp     short loc_14004070F
0x1400406e1  cmp     eax, 100h
0x1400406e6  ja      short loc_1400406F1
0x1400406e8  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400406ef  jmp     short loc_14004070F
0x1400406f1  cmp     eax, 400h
0x1400406f6  ja      short loc_140040701
0x1400406f8  lea     rbx, Lookaside
0x1400406ff  jmp     short loc_14004070F
0x140040701  cmp     eax, 800h
0x140040706  ja      short loc_140040720
0x140040708  lea     rbx, stru_1400B31C0
0x14004070f  mov     rcx, rbx; Lookaside
0x140040712  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140040719  nop     dword ptr [rax+rax+00h]
0x14004071e  jmp     short loc_14004073C
0x140040720  mov     edx, eax
0x140040722  mov     ecx, 40h ; '@'
0x140040727  mov     r8d, 7A697377h
0x14004072d  mov     rbx, rdi
0x140040730  call    cs:__imp_ExAllocatePool2
0x140040737  nop     dword ptr [rax+rax+00h]
0x14004073c  mov     r12, rax
0x14004073f  test    rax, rax
0x140040742  jz      loc_140040E9D
0x140040748  lea     rdi, [rax+10h]
0x14004074c  mov     [rax], rbx
0x14004074f  mov     rcx, rdi; void *
0x140040752  mov     dword ptr [rax+8], 7A697377h
0x140040759  lea     r8, [rsi+180h]; Size
0x140040760  xor     edx, edx; Val
0x140040762  call    memset
0x140040767  movups  xmm0, xmmword ptr [r14]
0x14004076b  mov     r8, rsi; Size
0x14004076e  mov     rdx, r15; Src
0x140040771  movups  xmmword ptr [rdi], xmm0
0x140040774  movups  xmm1, xmmword ptr [r14+10h]
0x140040779  movups  xmmword ptr [rdi+10h], xmm1
0x14004077d  mov     eax, [r14+20h]
0x140040781  lea     r14, [rdi+178h]
0x140040788  mov     rcx, r14; void *
0x14004078b  mov     [rdi+20h], eax
0x14004078e  call    memmove
0x140040793  lea     r9, [rbp+37h+var_90]; struct DOT11_INFO_ELEMENT **
0x140040797  mov     [rdi+170h], esi
0x14004079d  mov     r8b, 36h ; '6'; unsigned __int8
0x1400407a0  mov     edx, esi; unsigned int
0x1400407a2  mov     rcx, r14; unsigned __int8 *
0x1400407a5  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x1400407aa  xor     ebx, ebx
0x1400407ac  test    eax, eax
0x1400407ae  jnz     loc_140040E63
0x1400407b4  mov     rcx, [rbp+37h+var_90]
0x1400407b8  cmp     byte ptr [rcx+1], 3
0x1400407bc  jnz     loc_140040E63
0x1400407c2  mov     [rdi+40h], rcx
0x1400407c6  lea     r9, [rbp+37h+var_90]; struct DOT11_INFO_ELEMENT **
0x1400407ca  movzx   eax, byte ptr [rcx+1]
0x1400407ce  mov     r8b, 37h ; '7'; unsigned __int8
0x1400407d1  add     eax, 2
0x1400407d4  mov     edx, esi; unsigned int
0x1400407d6  mov     [rdi+34h], eax
0x1400407d9  movzx   eax, word ptr [rcx+2]
0x1400407dd  mov     rcx, r14; unsigned __int8 *
0x1400407e0  mov     [rdi+24h], ax
0x1400407e4  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x1400407e9  test    eax, eax
0x1400407eb  jnz     loc_140040E45
0x1400407f1  mov     rcx, [rbp+37h+var_90]
0x1400407f5  cmp     byte ptr [rcx+1], 52h ; 'R'
0x1400407f9  jb      loc_140040E45
0x1400407ff  mov     [rdi+48h], rcx
0x140040803  movzx   eax, byte ptr [rcx+1]
0x140040807  add     eax, 2
0x14004080a  mov     [rdi+38h], eax
0x14004080d  movzx   eax, word ptr [rcx+2]
0x140040811  mov     [rdi+8Ch], ax
0x140040818  test    r13d, r13d
0x14004081b  jz      short loc_140040828
0x14004081d  mov     [rcx+2], bl
0x140040820  mov     rax, [rdi+48h]
0x140040824  mov     byte ptr [rax+3], 3
0x140040828  lea     rax, [rcx+4]
0x14004082c  mov     r9d, 54h ; 'T'
0x140040832  mov     [rdi+98h], rax
0x140040839  lea     rax, [rcx+14h]
0x14004083d  mov     [rdi+0A0h], rax
0x140040844  lea     rax, [rcx+34h]
0x140040848  mov     [rdi+0A8h], rax
0x14004084f  mov     r8, [rdi+48h]
0x140040853  lea     r11d, [r9-53h]
0x140040857  mov     r10d, [rdi+38h]
0x14004085b  add     r8, r9
0x14004085e  cmp     r10, 56h ; 'V'
0x140040862  jb      loc_140040919
0x140040868  movzx   edx, byte ptr [r8+1]
0x14004086d  mov     ecx, r9d
0x140040870  add     rcx, 2
0x140040874  add     rcx, rdx
0x140040877  cmp     r10, rcx
0x14004087a  jb      loc_140040919
0x140040880  mov     al, [r8]
0x140040883  cmp     al, r11b
0x140040886  jnz     short loc_14004089A
0x140040888  cmp     dl, 6
0x14004088b  jnz     loc_140040954
0x140040891  mov     [rdi+0B0h], r8
0x140040898  jmp     short loc_1400408F6
0x14004089a  cmp     al, 2
0x14004089c  jnz     short loc_1400408B2
0x14004089e  lea     eax, [rdx-23h]
0x1400408a1  cmp     al, 10h
0x1400408a3  ja      loc_140040988
0x1400408a9  mov     [rdi+0C0h], r8
0x1400408b0  jmp     short loc_1400408F6
0x1400408b2  cmp     al, 3
0x1400408b4  jnz     short loc_1400408CC
0x1400408b6  mov     al, dl
0x1400408b8  sub     al, r11b
0x1400408bb  cmp     al, 2Fh ; '/'
0x1400408bd  ja      loc_1400409A9
0x1400408c3  mov     [rdi+0B8h], r8
0x1400408ca  jmp     short loc_1400408F6
0x1400408cc  cmp     al, 4
0x1400408ce  jnz     short loc_1400408E2
0x1400408d0  cmp     dl, 9
0x1400408d3  jb      loc_1400409CA
0x1400408d9  mov     [rdi+0C8h], r8
0x1400408e0  jmp     short loc_1400408F6
0x1400408e2  cmp     al, 6
0x1400408e4  jnz     short loc_1400408F6
0x1400408e6  cmp     dl, 9
0x1400408e9  jb      loc_1400409EB
0x1400408ef  mov     [rdi+0D0h], r8
0x1400408f6  movzx   eax, byte ptr [r8+1]
0x1400408fb  add     r9d, 2
0x1400408ff  add     r9d, eax
0x140040902  add     rax, 2
0x140040906  add     r8, rax
0x140040909  mov     eax, r9d
0x14004090c  add     rax, 2
0x140040910  cmp     r10, rax
0x140040913  jnb     loc_140040868
0x140040919  mov     r9, [rdi+0B8h]
0x140040920  test    r9, r9
0x140040923  jz      loc_140040E08
0x140040929  cmp     [rdi+0B0h], rbx
0x140040930  jz      loc_140040E08
0x140040936  mov     r15, [rbp+37h+Src]
0x14004093a  test    r15, r15
0x14004093d  jz      loc_140040A0F
0x140040943  cmp     [rbp+37h+arg_28], ebx
0x140040946  jz      loc_140040A0F
0x14004094c  mov     r14, r15
0x14004094f  jmp     loc_140040A6F
0x140040954  mov     rcx, cs:WPP_GLOBAL_Control
0x14004095b  lea     rax, WPP_GLOBAL_Control
0x140040962  cmp     rcx, rax
0x140040965  jz      loc_140040AEA
0x14004096b  mov     r9d, edx
0x14004096e  mov     edx, 1AFh
0x140040973  mov     rcx, [rcx+18h]
0x140040977  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004097e  call    WPP_SF_d
0x140040983  jmp     loc_140040AEA
0x140040988  mov     rcx, cs:WPP_GLOBAL_Control
0x14004098f  lea     rax, WPP_GLOBAL_Control
0x140040996  cmp     rcx, rax
0x140040999  jz      loc_140040AEA
0x14004099f  mov     r9d, edx
0x1400409a2  mov     edx, 1B0h
0x1400409a7  jmp     short loc_140040973
0x1400409a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400409b0  lea     rax, WPP_GLOBAL_Control
0x1400409b7  cmp     rcx, rax
0x1400409ba  jz      loc_140040AEA
0x1400409c0  mov     r9d, edx
0x1400409c3  mov     edx, 1B1h
0x1400409c8  jmp     short loc_140040973
0x1400409ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400409d1  lea     rax, WPP_GLOBAL_Control
0x1400409d8  cmp     rcx, rax
0x1400409db  jz      loc_140040AEA
0x1400409e1  mov     r9d, edx
0x1400409e4  mov     edx, 1B2h
0x1400409e9  jmp     short loc_140040973
0x1400409eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400409f2  lea     rax, WPP_GLOBAL_Control
0x1400409f9  cmp     rcx, rax
0x1400409fc  jz      loc_140040AEA
0x140040a02  mov     r9d, edx
0x140040a05  mov     edx, 1B3h
0x140040a0a  jmp     loc_140040973
0x140040a0f  lea     r9, [rbp+37h+var_90]; struct DOT11_INFO_ELEMENT **
0x140040a13  mov     r8b, 30h ; '0'; unsigned __int8
0x140040a16  test    r13d, r13d
0x140040a19  jz      short loc_140040A50
0x140040a1b  mov     edx, [rbp+37h+arg_38]; unsigned int
0x140040a1e  mov     rcx, [rbp+37h+arg_30]; unsigned __int8 *
0x140040a22  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140040a27  test    eax, eax
0x140040a29  jz      short loc_140040A62
0x140040a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a32  lea     rax, WPP_GLOBAL_Control
0x140040a39  cmp     rcx, rax
0x140040a3c  jz      loc_140040AEA
0x140040a42  mov     r9d, [rbp+37h+arg_38]
0x140040a46  mov     edx, 1B5h
0x140040a4b  jmp     loc_140040973
0x140040a50  mov     edx, esi; unsigned int
0x140040a52  mov     rcx, r14; unsigned __int8 *
0x140040a55  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140040a5a  test    eax, eax
0x140040a5c  jnz     loc_140040DE4
0x140040a62  mov     r14, [rbp+37h+var_90]
0x140040a66  test    r14, r14
0x140040a69  jz      loc_140040DA3
0x140040a6f  mov     bl, [r14+1]
0x140040a73  add     bl, 2
0x140040a76  jz      loc_140040DA3
0x140040a7c  cmp     bl, 0EBh
0x140040a7f  ja      loc_140040DA3
0x140040a85  movzx   eax, byte ptr [r14+1]
0x140040a8a  cmp     bl, al
0x140040a8c  jb      loc_140040DA3
0x140040a92  mov     edx, eax; unsigned int
0x140040a94  lea     rcx, [r14+2]; unsigned __int8 *
0x140040a98  lea     r9, [rbp+37h+var_80]; struct DOT11_RSN_IE_INFO *
0x140040a9c  lea     r8, [rbp+37h+arg_18]; unsigned int *
0x140040aa0  call    ?IEPRSNParseIE@@YAJPEAEKPEAKPEAUDOT11_RSN_IE_INFO@@@Z; IEPRSNParseIE(uchar *,ulong,ulong *,DOT11_RSN_IE_INFO *)
0x140040aa5  test    eax, eax
0x140040aa7  jnz     loc_140040DA3
0x140040aad  mov     r8d, [rbp+37h+arg_18]
0x140040ab1  test    r8b, 10h
0x140040ab5  jnz     short loc_140040B0B
0x140040ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140040abe  lea     rax, WPP_GLOBAL_Control
0x140040ac5  cmp     rcx, rax
0x140040ac8  jz      short loc_140040AE8
0x140040aca  mov     edx, 1B8h
0x140040acf  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x140040ad4  movzx   r9d, bl
0x140040ad8  mov     rcx, [rcx+18h]
0x140040adc  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140040ae3  call    WPP_SF_Dd
0x140040ae8  xor     ebx, ebx
0x140040aea  mov     rcx, [r12]; Lookaside
0x140040aee  test    rcx, rcx
0x140040af1  jz      loc_140040E84
0x140040af7  mov     rdx, r12; Entry
0x140040afa  call    cs:__imp_ExFreeToNPagedLookasideList
0x140040b01  nop     dword ptr [rax+rax+00h]
0x140040b06  jmp     loc_140040E98
0x140040b0b  mov     eax, [rbp+37h+var_70]
0x140040b0e  mov     [rdi+28h], eax
0x140040b11  mov     eax, [rbp+37h+var_7C]
0x140040b14  mov     [rdi+2Ch], eax
0x140040b17  mov     eax, [rbp+37h+var_3C]
0x140040b1a  mov     [rdi+30h], eax
0x140040b1d  mov     r13d, [rbp+37h+arg_18]
0x140040b21  and     r13d, 40h
0x140040b25  mov     dword ptr [rbp+37h+var_90], r13d
0x140040b29  jz      short loc_140040B41
0x140040b2b  movzx   eax, [rbp+37h+var_56]
0x140040b2f  mov     [rdi+0D8h], ax
0x140040b36  mov     al, [rbp+37h+var_40]
0x140040b39  add     al, 2
0x140040b3b  mov     [rdi+0DAh], al
0x140040b41  lea     rcx, [rbp+37h+var_80]; struct DOT11_RSN_IE_INFO *
0x140040b45  call    ?FreeRSNIEContent@@YAXPEAUDOT11_RSN_IE_INFO@@@Z; FreeRSNIEContent(DOT11_RSN_IE_INFO *)
0x140040b4a  cmp     r14, r15
0x140040b4d  jz      short loc_140040B84
  ... truncated ...
```
