# NtfsCreateNonresidentWithValue

- ea: `0x1401578a0`
- end: `0x1401580cf`
- name: `NtfsCreateNonresidentWithValue`
- size: `2095`
- prototype: `LARGE_INTEGER __fastcall(__int64, LARGE_INTEGER *, unsigned int, __int128 *, void *, int, __int16, LARGE_INTEGER *, char, char, __int64)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140156080`
- `0x1401580e0`
- `0x140278ed8`

## callees

- `0x140007ea0`
- `0x14000ea70`
- `0x14001e810`
- `0x1400285c0`
- `0x140040ec4`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x14013c2d0`
- `0x14013f374`
- `0x140150bc0`
- `0x1401578a0`
- `0x140159768`
- `0x1401606a0`
- `0x140163f78`
- `0x14019a718`
- `0x1401e0e3c`
- `0x140223a60`

## import_xrefs

- `ntoskrnl!CcSetFileSizesEx` at `0x140157b09`
- `ntoskrnl!CcSetFileSizesEx` at `0x140157b09`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a8537`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a8537`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140157f3e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140157f3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a85a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a85a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140157c27`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140157c27`
- `ntoskrnl!CcUnpinData` at `0x140157ec2`
- `ntoskrnl!CcUnpinData` at `0x140157ef0`
- `ntoskrnl!CcUnpinData` at `0x1402a856b`
- `ntoskrnl!CcUnpinData` at `0x140157ec2`
- `ntoskrnl!CcUnpinData` at `0x140157ef0`
- `ntoskrnl!CcUnpinData` at `0x1402a856b`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140157de6`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140157de6`
- `ntoskrnl!ExRaiseStatus` at `0x14015808a`
- `ntoskrnl!ExRaiseStatus` at `0x14015808a`

## pseudocode

```c
LARGE_INTEGER __fastcall NtfsCreateNonresidentWithValue(
        __int64 a1,
        LARGE_INTEGER *a2,
        unsigned int a3,
        __int128 *a4,
        void *a5,
        int a6,
        __int16 a7,
        LARGE_INTEGER *a8,
        char a9,
        char a10,
        __int64 a11)
{
  LARGE_INTEGER v14; // r15
  __int64 v15; // rcx
  __int16 v16; // si
  LARGE_INTEGER *Scb; // rbx
  char v18; // r12
  __int64 v19; // rsi
  int v20; // r8d
  bool v21; // dl
  size_t v22; // r14
  struct _FILE_OBJECT *v23; // r9
  struct _CC_FILE_SIZES *v24; // rdx
  NTSTATUS v25; // eax
  LARGE_INTEGER result; // rax
  unsigned int v27; // r8d
  unsigned int v28; // esi
  void *v29; // r14
  signed __int64 QuadPart; // r8
  void *v31; // rcx
  size_t v32; // rax
  unsigned int v33; // r14d
  _WORD *v34; // rax
  int v35; // ecx
  __int128 v36; // xmm1
  LARGE_INTEGER v37; // rdx
  LARGE_INTEGER v38; // rdx
  signed __int64 v39; // r8
  LARGE_INTEGER v40; // r9
  signed __int64 v41; // r10
  unsigned __int64 v42; // rax
  __int16 Buffer; // [rsp+20h] [rbp-118h]
  int v44; // [rsp+28h] [rbp-110h]
  char v45; // [rsp+70h] [rbp-C8h] BYREF
  bool v46; // [rsp+71h] [rbp-C7h]
  int Length[3]; // [rsp+74h] [rbp-C4h] BYREF
  void *v48; // [rsp+80h] [rbp-B8h] BYREF
  void *Src; // [rsp+88h] [rbp-B0h]
  size_t Size; // [rsp+90h] [rbp-A8h]
  _WORD *v51; // [rsp+98h] [rbp-A0h]
  int v52[2]; // [rsp+A0h] [rbp-98h]
  unsigned int v53; // [rsp+A8h] [rbp-90h]
  __int64 v54; // [rsp+B0h] [rbp-88h]
  void *v55; // [rsp+B8h] [rbp-80h]
  __int128 v56; // [rsp+C0h] [rbp-78h] BYREF
  void *v57; // [rsp+D0h] [rbp-68h]
  size_t v58; // [rsp+D8h] [rbp-60h]
  struct _CC_FILE_SIZES v59; // [rsp+E0h] [rbp-58h] BYREF

  LODWORD(v48) = a3;
  *(_QWORD *)v52 = a1;
  Src = a5;
  v55 = a5;
  Length[0] = a6;
  v54 = a11;
  v45 = 0;
  v56 = 0;
  v14 = a2[12];
  *(_QWORD *)&Length[1] = 0;
  v51 = 0;
  v15 = *(unsigned int *)(160LL * ((a3 >> 4) - 1) + *(_QWORD *)(v14.QuadPart + 4704) + 140);
  v46 = (v15 & 0x80u) != 0LL || a2[1].LowPart == 4;
  v16 = *(_WORD *)(v14.QuadPart + 776) & a7;
  if ( a4 )
    v56 = *a4;
  if ( a2 == *(LARGE_INTEGER **)(*(_QWORD *)(v14.QuadPart + 48) + 184LL)
    && a3 == 32
    && (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
  {
    McTemplateU0pdd_EtwWriteTransfer(v15, (const EVENT_DESCRIPTOR *)attrsup_c3873, a1, Length[0], v16);
  }
  if ( a8 )
  {
    Scb = a8;
    v45 = 1;
  }
  else
  {
    v51 = ExAllocateFromLookasideListEx(&NtfsRollbackStructLookasideList);
    NtfsAddPreallocatedStructToRollbackList(a1, 0, 0, v51);
    Scb = (LARGE_INTEGER *)NtfsCreateScb(a1, (_DWORD)a2, a3, (unsigned int)&v56, 0, 0, (__int64)&v45);
    ClearFlagInterlocked((unsigned int *)&Scb[25], 552);
    if ( !v45 )
    {
      v34 = v51;
      *v51 = 1830;
      *((_QWORD *)v34 + 3) = Scb;
      v35 = *((_DWORD *)v34 + 1) | 4;
      *((_DWORD *)v34 + 15) |= 0x40u;
      *((_DWORD *)v34 + 14) |= 0x40u;
      *((_DWORD *)v34 + 1) = v35 | 8;
      Scb[64].LowPart |= 0x2000000u;
    }
  }
  v18 = a10 | v46;
  Size = (unsigned int)Length[0];
  Buffer = v16;
  v19 = *(_QWORD *)v52;
  NtfsAllocateAttribute(v52[0], Buffer, 1, a9, (unsigned int)Length[0], v54);
  NtfsUpdateScbFromAttribute(v19, Scb, 0);
  if ( !v45 && Scb[32].LowPart != 128 )
    SetFlagInterlocked((unsigned int *)(Scb[62].QuadPart + 88), 8u);
  if ( (Scb[25].LowPart & 1) == 0 )
    _InterlockedOr((volatile signed __int32 *)&Scb[25], 1u);
  v21 = v46;
  if ( v46 )
  {
    LOBYTE(v20) = 1;
    NtfsCreateInternalAttributeStream(v19, (_DWORD)Scb, v20, 0, (__int64)L"8:", 0);
    v21 = v46;
  }
  v22 = Size;
  if ( (Scb[25].LowPart & 0x20000) != 0 && Scb[4].QuadPart < (signed __int64)Size )
  {
    QuadPart = Size;
    if ( (signed __int64)Size >= Scb[58].QuadPart )
      QuadPart = Scb[58].QuadPart;
    if ( QuadPart > Scb[5].QuadPart )
    {
      if ( (Scb[25].LowPart & 0x20000) != 0 )
      {
        v40 = Scb[58];
        if ( v40.QuadPart < QuadPart )
        {
LABEL_89:
          Scb[58].QuadPart = QuadPart;
          goto LABEL_90;
        }
        if ( Scb[5].QuadPart > QuadPart )
        {
          if ( *(_QWORD *)(Scb[36].QuadPart + 16) && QuadPart != 0x7FFFFFFFFFFFFFFFLL )
          {
            v41 = (QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v41 < v40.QuadPart )
              Scb[58].QuadPart = v41;
            goto LABEL_90;
          }
          goto LABEL_89;
        }
      }
LABEL_90:
      Scb[5].QuadPart = QuadPart;
    }
  }
  Scb[4].QuadPart = v22;
  if ( Src )
  {
    v27 = Length[0];
    if ( Length[0] )
    {
      if ( v21 )
      {
        v31 = 0;
        v48 = 0;
        v32 = 0;
        Size = 0;
        while ( v27 )
        {
          v33 = 4096;
          if ( v27 < 0x1000 )
            v33 = v27;
          if ( v31 )
          {
            CcUnpinData(v31);
            v48 = 0;
            v32 = Size;
          }
          NtfsPinStream(v19, Scb, v32, v33, &v48, &Length[1]);
          if ( a8 )
            MmSetAddressRangeModified(*(PVOID *)&Length[1], v33);
          else
            memmove(*(void **)&Length[1], Src, v33);
          NtfsWriteLog(v19, (__int64)Scb, v48, 8, *(__int64 **)&Length[1], v33, 0, 0, 0, Size, 0, 0, v33);
          v27 = Length[0] - v33;
          Length[0] = v27;
          v53 = v27;
          Src = (char *)Src + v33;
          v57 = Src;
          v32 = v33 + Size;
          Size = v32;
          v58 = v32;
          v31 = v48;
        }
        if ( v31 )
        {
          CcUnpinData(v31);
          v48 = 0;
        }
      }
      else
      {
        v28 = -*(_DWORD *)(v14.QuadPart + 356) & (*(_DWORD *)(v14.QuadPart + 356) + Length[0] - 1);
        if ( v28 == Length[0] )
        {
          v29 = Src;
          *(_QWORD *)&Length[1] = Src;
        }
        else
        {
          *(_QWORD *)&Length[1] = ExAllocatePoolWithTag((POOL_TYPE)528, v28, 0x4146744Eu);
          memmove(*(void **)&Length[1], Src, v22);
          if ( v28 > Length[0] )
            memset((void *)(v22 + *(_QWORD *)&Length[1]), 0, v28 - Length[0]);
          v29 = Src;
        }
        v44 = v28;
        v19 = *(_QWORD *)v52;
        NtfsWriteBytes(v52[0], v14.LowPart, (int)Scb, 0, *(PVOID *)&Length[1], v44, 0);
        if ( *(void **)&Length[1] != v29 )
          ExFreePoolWithTag(*(PVOID *)&Length[1], 0);
        v18 = 1;
      }
      if ( (Scb[25].LowPart & 0x20000) == 0 )
        goto LABEL_46;
      v38 = Scb[4];
      v39 = Scb[58].QuadPart;
      if ( v39 < v38.QuadPart )
        goto LABEL_96;
      if ( Scb[5].QuadPart > v38.QuadPart )
      {
        if ( !*(_QWORD *)(Scb[36].QuadPart + 16) || v38.QuadPart == 0x7FFFFFFFFFFFFFFFLL )
        {
LABEL_96:
          v42 = Scb[4].QuadPart;
          goto LABEL_97;
        }
        if ( (__int64)((v38.QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL) < v39 )
        {
          v42 = (Scb[4].QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
LABEL_97:
          Scb[58].QuadPart = v42;
        }
      }
LABEL_46:
      Scb[5] = Scb[4];
    }
  }
  NtfsWriteFileSizes(v19, (__int64)Scb, 0, v18, a9, 0);
  v23 = (struct _FILE_OBJECT *)Scb[35].QuadPart;
  if ( v23 )
  {
    if ( v23->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(Scb[36].QuadPart + 16) && v19 )
    {
      NtfsCreateInternalAttributeStream(v19, (_DWORD)Scb, 0, 0, 0, 0);
      v23 = (struct _FILE_OBJECT *)Scb[35].QuadPart;
    }
    if ( *(_QWORD *)(Scb[36].QuadPart + 24) )
    {
      v24 = (struct _CC_FILE_SIZES *)&Scb[3];
      if ( (Scb[64].LowPart & 1) != 0 )
      {
        v36 = *(_OWORD *)&v24->AllocationSize.LowPart;
        *(_OWORD *)&v59.AllocationSize.LowPart = v36;
        v59.ValidDataLength = Scb[5];
        v37 = Scb[24];
        v59.AllocationSize.QuadPart = v36 - *(_QWORD *)(v37.QuadPart + 1952);
        v59.FileSize.QuadPart = *((_QWORD *)&v36 + 1) - *(_QWORD *)(v37.QuadPart + 1952);
        NtfsSetCcFileSizes(v23, (__int64)Scb, &v59);
      }
      else
      {
        v25 = CcSetFileSizesEx(v23, v24);
        if ( v25 < 0 && Scb[27].HighPart )
          ExRaiseStatus(v25);
        if ( NtfsStatusDebugFlags
          && v25
          && v25 != 294
          && (unsigned int)(v25 - 298) > 1
          && (unsigned int)v25 < 0xFFFFFFED
          && v25 != -1073741608
          && v25 != -1073741802
          && v25 != -1073741807
          && (unsigned int)(v25 + 2147483643) > 1
          && v25 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(0, v25, 0x516ADu);
        }
      }
    }
  }
  result.QuadPart = Scb[25].LowPart;
  if ( (result.LowPart & 0x10) != 0 )
  {
    a2[20] = Scb[59];
    result = Scb[4];
    a2[21] = result;
    a2[23].LowPart |= 0x40000008u;
  }
  return result;
}

```

## disassembly

```asm
0x1401578a0  push    rbx
0x1401578a2  push    rsi
0x1401578a3  push    rdi
0x1401578a4  push    r12
0x1401578a6  push    r13
0x1401578a8  push    r14
0x1401578aa  push    r15
0x1401578ac  sub     rsp, 100h
0x1401578b3  mov     rax, cs:__security_cookie
0x1401578ba  xor     rax, rsp
0x1401578bd  mov     [rsp+138h+var_40], rax
0x1401578c5  mov     r14, r9
0x1401578c8  mov     ebx, r8d
0x1401578cb  mov     dword ptr [rsp+138h+var_B8], ebx
0x1401578d2  mov     rdi, rdx
0x1401578d5  mov     r12, rcx
0x1401578d8  mov     qword ptr [rsp+138h+var_98], rcx
0x1401578e0  mov     rax, [rsp+138h+arg_20]
0x1401578e8  mov     [rsp+138h+Src], rax
0x1401578f0  mov     [rsp+138h+var_80], rax
0x1401578f8  mov     eax, [rsp+138h+arg_28]
0x1401578ff  mov     dword ptr [rsp+138h+Length], eax
0x140157903  mov     r13, [rsp+138h+arg_38]
0x14015790b  mov     rax, [rsp+138h+arg_50]
0x140157913  mov     [rsp+138h+var_88], rax
0x14015791b  mov     [rsp+138h+var_C8], 0
0x140157920  xorps   xmm0, xmm0
0x140157923  movups  [rsp+138h+var_78], xmm0
0x14015792b  mov     r15, [rdx+60h]
0x14015792f  xor     eax, eax
0x140157931  mov     qword ptr [rsp+138h+Length+4], rax
0x140157936  mov     [rsp+138h+var_A0], rax
0x14015793e  mov     eax, r8d
0x140157941  shr     eax, 4
0x140157944  dec     eax
0x140157946  lea     rcx, [rax+rax*4]
0x14015794a  shl     rcx, 5
0x14015794e  mov     rax, [r15+1260h]
0x140157955  mov     ecx, [rcx+rax+8Ch]
0x14015795c  test    cl, cl
0x14015795e  js      loc_140157BE0
0x140157964  cmp     dword ptr [rdx+8], 4
0x140157968  jz      loc_140157BE0
0x14015796e  mov     [rsp+138h+var_C7], 0
0x140157973  movzx   esi, [rsp+138h+arg_30]
0x14015797b  and     si, [r15+308h]
0x140157983  test    r14, r14
0x140157986  jz      short loc_140157994
0x140157988  movups  xmm0, xmmword ptr [r9]
0x14015798c  movups  [rsp+138h+var_78], xmm0
0x140157994  mov     rax, [r15+30h]
0x140157998  cmp     rdi, [rax+0B8h]
0x14015799f  jz      loc_140157CEB
0x1401579a5  test    r13, r13
0x1401579a8  jz      loc_140157F37
0x1401579ae  mov     rbx, r13
0x1401579b1  mov     [rsp+138h+var_C8], 1
0x1401579b6  movzx   r12d, [rsp+138h+var_C7]
0x1401579bc  or      r12b, [rsp+138h+arg_48]
0x1401579c4  mov     eax, dword ptr [rsp+138h+Length]
0x1401579c8  mov     [rsp+138h+Size], rax
0x1401579d0  mov     rcx, [rsp+138h+var_88]
0x1401579d8  mov     [rsp+138h+var_F8], rcx
0x1401579dd  mov     [rsp+138h+var_100], rax
0x1401579e2  movzx   eax, [rsp+138h+arg_40]
0x1401579ea  mov     byte ptr [rsp+138h+var_108], al
0x1401579ee  mov     byte ptr [rsp+138h+var_110], 1
0x1401579f3  mov     word ptr [rsp+138h+Buffer], si
0x1401579f8  mov     r9, r14
0x1401579fb  mov     r8d, dword ptr [rsp+138h+var_B8]
0x140157a03  mov     rdx, rbx
0x140157a06  mov     rsi, qword ptr [rsp+138h+var_98]
0x140157a0e  mov     rcx, rsi
0x140157a11  call    NtfsAllocateAttribute
0x140157a16  xor     r8d, r8d
0x140157a19  mov     rdx, rbx
0x140157a1c  mov     rcx, rsi
0x140157a1f  call    NtfsUpdateScbFromAttribute
0x140157a24  cmp     [rsp+138h+var_C8], 0
0x140157a29  jz      loc_140157F0D
0x140157a2f  mov     eax, [rbx+0C8h]
0x140157a35  test    al, 1
0x140157a37  jnz     short loc_140157A41
0x140157a39  lock or dword ptr [rbx+0C8h], 1
0x140157a41  movzx   edx, [rsp+138h+var_C7]
0x140157a46  test    dl, dl
0x140157a48  jz      short loc_140157A75
0x140157a4a  mov     qword ptr [rsp+138h+var_110], 0
0x140157a53  lea     rax, a8_0; "8:"
0x140157a5a  mov     [rsp+138h+Buffer], rax
0x140157a5f  xor     r9d, r9d
0x140157a62  mov     r8b, 1
0x140157a65  mov     rdx, rbx
0x140157a68  mov     rcx, rsi
0x140157a6b  call    NtfsCreateInternalAttributeStream
0x140157a70  movzx   edx, [rsp+138h+var_C7]
0x140157a75  mov     ecx, [rbx+0C8h]
0x140157a7b  mov     r14, [rsp+138h+Size]
0x140157a83  bt      ecx, 11h
0x140157a87  jb      loc_140157D2A
0x140157a8d  mov     [rbx+20h], r14
0x140157a91  cmp     [rsp+138h+Src], 0
0x140157a9a  jnz     loc_140157BEA
0x140157aa0  mov     byte ptr [rsp+138h+var_110], 0
0x140157aa5  movzx   eax, [rsp+138h+arg_40]
0x140157aad  mov     byte ptr [rsp+138h+Buffer], al
0x140157ab1  movzx   r9d, r12b
0x140157ab5  xor     r8d, r8d
0x140157ab8  mov     rdx, rbx
0x140157abb  mov     rcx, rsi
0x140157abe  call    NtfsWriteFileSizes
0x140157ac3  mov     r9, [rbx+118h]
0x140157aca  test    r9, r9
0x140157acd  jz      short loc_140157B2A
0x140157acf  mov     rax, [rbx+120h]
0x140157ad6  add     rax, 10h
0x140157ada  cmp     [r9+28h], rax
0x140157ade  jnz     loc_14015803C
0x140157ae4  mov     rax, [rbx+120h]
0x140157aeb  mov     rcx, [rax+18h]
0x140157aef  test    rcx, rcx
0x140157af2  jz      short loc_140157B2A
0x140157af4  lea     rdx, [rbx+18h]; FileSizes
0x140157af8  mov     eax, [rbx+200h]
0x140157afe  mov     rcx, r9; FileObject
0x140157b01  test    al, 1
0x140157b03  jnz     loc_140157FE4
0x140157b09  call    cs:__imp_CcSetFileSizesEx
0x140157b10  nop     dword ptr [rax+rax+00h]
0x140157b15  mov     edx, eax
0x140157b17  test    eax, eax
0x140157b19  js      loc_140158074
0x140157b1f  movzx   eax, cs:NtfsStatusDebugFlags
0x140157b26  test    al, al
0x140157b28  jnz     short loc_140157B7B
0x140157b2a  mov     eax, [rbx+0C8h]
0x140157b30  test    al, 10h
0x140157b32  jz      short loc_140157B57
0x140157b34  mov     rax, [rbx+1D8h]
0x140157b3b  mov     [rdi+0A0h], rax
0x140157b42  mov     rax, [rbx+20h]
0x140157b46  mov     [rdi+0A8h], rax
0x140157b4d  or      dword ptr [rdi+0B8h], 40000008h
0x140157b57  mov     rcx, [rsp+138h+var_40]
0x140157b5f  xor     rcx, rsp; StackCookie
0x140157b62  call    __security_check_cookie
0x140157b67  add     rsp, 100h
0x140157b6e  pop     r15
0x140157b70  pop     r14
0x140157b72  pop     r13
0x140157b74  pop     r12
0x140157b76  pop     rdi
0x140157b77  pop     rsi
0x140157b78  pop     rbx
0x140157b79  retn
0x140157b7b  test    edx, edx
0x140157b7d  jz      short loc_140157B2A
0x140157b7f  cmp     edx, 126h
0x140157b85  jz      short loc_140157B2A
0x140157b87  lea     eax, [rdx-12Ah]
0x140157b8d  cmp     eax, 1
0x140157b90  jbe     short loc_140157B2A
0x140157b92  cmp     edx, 0FFFFFFEDh
0x140157b95  jnb     short loc_140157B2A
0x140157b97  cmp     edx, 0C00000D8h
0x140157b9d  jz      short loc_140157B2A
0x140157b9f  cmp     edx, 0C0000016h
0x140157ba5  jz      short loc_140157B2A
0x140157ba7  cmp     edx, 0C0000011h
0x140157bad  jz      loc_140157B2A
0x140157bb3  lea     eax, [rdx+7FFFFFFBh]
0x140157bb9  cmp     eax, 1
0x140157bbc  jbe     loc_140157B2A
0x140157bc2  cmp     edx, 103h
0x140157bc8  jz      loc_140157B2A
0x140157bce  xor     ecx, ecx
0x140157bd0  mov     r8d, 516ADh
0x140157bd6  call    NtfsStatusTraceAndDebugInternal
0x140157bdb  jmp     loc_140157B2A
0x140157be0  mov     [rsp+138h+var_C7], 1
0x140157be5  jmp     loc_140157973
0x140157bea  mov     r8d, dword ptr [rsp+138h+Length]
0x140157bef  test    r8d, r8d
0x140157bf2  jz      loc_140157AA0
0x140157bf8  test    dl, dl
0x140157bfa  jnz     loc_140157D77
0x140157c00  mov     eax, [r15+164h]
0x140157c07  lea     esi, [r8-1]
0x140157c0b  add     esi, eax
0x140157c0d  neg     eax
0x140157c0f  and     esi, eax
0x140157c11  cmp     esi, r8d
0x140157c14  jz      loc_140157D65
0x140157c1a  mov     edx, esi; NumberOfBytes
0x140157c1c  mov     ecx, 210h; PoolType
0x140157c21  mov     r8d, 4146744Eh; Tag
0x140157c27  call    cs:__imp_ExAllocatePoolWithTag
0x140157c2e  nop     dword ptr [rax+rax+00h]
0x140157c33  mov     qword ptr [rsp+138h+Length+4], rax
0x140157c38  mov     r8, r14; Size
0x140157c3b  mov     rdx, [rsp+138h+Src]; Src
0x140157c43  mov     rcx, rax; void *
0x140157c46  call    memmove
0x140157c4b  mov     ecx, dword ptr [rsp+138h+Length]
0x140157c4f  cmp     esi, ecx
0x140157c51  jbe     short loc_140157C68
0x140157c53  mov     r8d, esi
0x140157c56  sub     r8d, ecx; Size
0x140157c59  mov     rcx, qword ptr [rsp+138h+Length+4]
0x140157c5e  add     rcx, r14; void *
0x140157c61  xor     edx, edx; Val
0x140157c63  call    memset
0x140157c68  mov     r14, [rsp+138h+Src]
0x140157c70  mov     [rsp+138h+var_108], 0; int
0x140157c78  mov     [rsp+138h+var_110], esi; int
0x140157c7c  mov     rax, qword ptr [rsp+138h+Length+4]
0x140157c81  mov     [rsp+138h+Buffer], rax; Buffer
0x140157c86  xor     r9d, r9d; int
0x140157c89  mov     r8, rbx; int
0x140157c8c  mov     rdx, r15; int
0x140157c8f  mov     rsi, qword ptr [rsp+138h+var_98]
0x140157c97  mov     rcx, rsi; int
0x140157c9a  call    NtfsWriteBytes
0x140157c9f  nop
0x140157ca0  mov     rcx, qword ptr [rsp+138h+Length+4]; P
0x140157ca5  cmp     rcx, r14
0x140157ca8  jz      short loc_140157CB8
0x140157caa  xor     edx, edx; Tag
0x140157cac  call    cs:__imp_ExFreePoolWithTag
0x140157cb3  nop     dword ptr [rax+rax+00h]
0x140157cb8  mov     r12b, 1
0x140157cbb  test    dword ptr [rbx+0C8h], 200h
0x140157cc5  jz      short loc_140157CCE
0x140157cc7  movzx   eax, cs:NtfsStatusDebugFlags
0x140157cce  mov     ecx, [rbx+0C8h]
0x140157cd4  bt      ecx, 11h
0x140157cd8  jb      loc_1401580AC
0x140157cde  mov     rax, [rbx+20h]
0x140157ce2  mov     [rbx+28h], rax
0x140157ce6  jmp     loc_140157AA0
0x140157ceb  cmp     ebx, 20h ; ' '
0x140157cee  jnz     loc_1401579A5
0x140157cf4  test    r12, r12
0x140157cf7  jnz     loc_140158097
0x140157cfd  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 2
0x140157d04  jz      loc_1401579A5
0x140157d0a  movzx   eax, si
0x140157d0d  mov     dword ptr [rsp+138h+Buffer], eax
0x140157d11  mov     r9d, dword ptr [rsp+138h+Length]
0x140157d16  mov     r8, r12
0x140157d19  lea     rdx, attrsup_c3873
0x140157d20  call    McTemplateU0pdd_EtwWriteTransfer
0x140157d25  jmp     loc_1401579A5
0x140157d2a  cmp     [rbx+20h], r14
0x140157d2e  jge     loc_140157A8D
0x140157d34  mov     rax, [rbx+1D0h]
0x140157d3b  mov     r8, r14
0x140157d3e  cmp     r14, rax
0x140157d41  cmovge  r8, rax
0x140157d45  cmp     r8, [rbx+28h]
0x140157d49  jle     loc_140157A8D
0x140157d4f  bt      ecx, 9
0x140157d53  jnb     loc_1402C9298
0x140157d59  movzx   eax, cs:NtfsStatusDebugFlags
0x140157d60  jmp     loc_1402C9298
0x140157d65  mov     r14, [rsp+138h+Src]
0x140157d6d  mov     qword ptr [rsp+138h+Length+4], r14
0x140157d72  jmp     loc_140157C70
0x140157d77  xor     ecx, ecx; Bcb
0x140157d79  mov     [rsp+138h+var_B8], rcx
0x140157d81  xor     eax, eax
0x140157d83  mov     [rsp+138h+Size], rax
0x140157d8b  test    r8d, r8d
0x140157d8e  jz      loc_140157EE7
0x140157d94  mov     r14d, 1000h
0x140157d9a  cmp     r8d, r14d
0x140157d9d  cmovb   r14d, r8d
0x140157da1  test    rcx, rcx
0x140157da4  jnz     loc_140157EC2
0x140157daa  lea     rcx, [rsp+138h+Length+4]
0x140157daf  mov     qword ptr [rsp+138h+var_110], rcx
0x140157db4  lea     rcx, [rsp+138h+var_B8]
0x140157dbc  mov     [rsp+138h+Buffer], rcx
0x140157dc1  mov     r9d, r14d
0x140157dc4  mov     r8, rax
0x140157dc7  mov     rdx, rbx
0x140157dca  mov     rcx, rsi
0x140157dcd  call    NtfsPinStream
0x140157dd2  mov     r15d, r14d
0x140157dd5  mov     rcx, qword ptr [rsp+138h+Length+4]; void *
0x140157dda  test    r13, r13
0x140157ddd  jz      loc_140157EAD
0x140157de3  mov     edx, r15d; Length
0x140157de6  call    cs:__imp_MmSetAddressRangeModified
0x140157ded  nop     dword ptr [rax+rax+00h]
0x140157df2  mov     [rsp+138h+var_D8], r14d
0x140157df7  mov     [rsp+138h+var_E0], 0
0x140157dff  mov     [rsp+138h+var_E8], 0
0x140157e07  mov     rax, [rsp+138h+Size]
0x140157e0f  mov     [rsp+138h+var_F0], rax
  ... truncated ...
```
