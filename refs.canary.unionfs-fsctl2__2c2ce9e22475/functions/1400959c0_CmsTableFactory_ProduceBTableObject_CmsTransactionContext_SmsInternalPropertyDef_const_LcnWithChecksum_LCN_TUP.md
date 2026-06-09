# CmsTableFactory::ProduceBTableObject(CmsTransactionContext *,SmsInternalPropertyDef const &,LcnWithChecksum *,_LCN_TUPLE const *,ulong,uchar,CmsBPlusTable * *)

- ea: `0x1400959c0`
- end: `0x1400960d2`
- name: `?ProduceBTableObject@CmsTableFactory@@SAJPEAVCmsTransactionContext@@AEBUSmsInternalPropertyDef@@PEAULcnWithChecksum@@PEBT_LCN_TUPLE@@KEPEAPEAVCmsBPlusTable@@@Z`
- size: `1810`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, const struct SmsInternalPropertyDef *, struct LcnWithChecksum *, const union _LCN_TUPLE *, unsigned int, char, struct CmsBPlusTable **)`
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001e410`
- `0x14009bdb4`
- `0x1400bd724`
- `0x14012d594`
- `0x14013a9f8`
- `0x14013ab64`
- `0x14015c80c`

## callees

- `0x1400959c0`
- `0x1400960d8`
- `0x1400c8574`
- `0x1400c9080`
- `0x1401e9dc0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140095e86`
- `ntoskrnl!KeSetEvent` at `0x140095e86`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009608f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009608f`
- `ntoskrnl!ExAllocatePool2` at `0x140095a1d`
- `ntoskrnl!ExAllocatePool2` at `0x140095a1d`
- `ntoskrnl!ExInitializeFastResource` at `0x140095e9b`
- `ntoskrnl!ExInitializeFastResource` at `0x140095e9b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400959e0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400959e0`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x140095b9b`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x140095b9b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9baa`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9baa`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400960ac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400960ac`
- `ntoskrnl!KeInitializeEvent` at `0x140095e6e`
- `ntoskrnl!KeInitializeEvent` at `0x140095e6e`

## string_xrefs

- `0x140095a34`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsTableFactory::ProduceBTableObject(
        struct CmsTransactionContext *a1,
        const struct SmsInternalPropertyDef *a2,
        struct LcnWithChecksum *a3,
        const union _LCN_TUPLE *a4,
        unsigned int a5,
        char a6,
        struct CmsBPlusTable **a7)
{
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 Pool2; // rax
  char *v13; // rdi
  int v14; // ecx
  struct CmsBPlusTable *v15; // rbx
  unsigned int v16; // ebp
  char *v17; // r14
  __int64 v18; // r13
  unsigned int v19; // r8d
  struct CmsBPlusTable **v20; // r15
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  char v22; // al
  __int64 v23; // rax
  struct _NPAGED_LOOKASIDE_LIST *v25; // rcx
  char *v26; // rax
  int v27; // [rsp+24h] [rbp-34h]

  v10 = qword_140262478 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v10 < 0x5E8u )
  {
    v10 = 0;
    v11 = 1528;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v10 + 8) )
  {
    v25 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
    if ( *(_BYTE *)(v10 + 9) )
      v26 = (char *)ExAllocateFromNPagedLookasideList(v25);
    else
      v26 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v25);
LABEL_10:
    v13 = v26;
    if ( v26 )
      goto LABEL_11;
    goto LABEL_9;
  }
  if ( (int)*(_QWORD *)(v10 + 88) > (int)HIDWORD(*(_QWORD *)(v10 + 88)) )
  {
    v14 = _InterlockedDecrement((volatile signed __int32 *)(v10 + 88));
    if ( v14 >= *(_DWORD *)(v10 + 92) && v14 >= 0 )
    {
      v26 = (char *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v10 + 64));
      goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
  }
LABEL_9:
  v11 = *(unsigned int *)(v10 + 4);
LABEL_3:
  Pool2 = ExAllocatePool2(66, v11, 1766871885);
  v13 = (char *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !Pool2 )
    goto LABEL_29;
LABEL_11:
  *(_QWORD *)v13 = v10;
  v15 = (struct CmsBPlusTable *)(v13 + 16);
  if ( v13 == (char *)-16LL )
  {
LABEL_29:
    v16 = -1073741670;
    v15 = 0;
    goto LABEL_23;
  }
  v16 = 0;
  v17 = v13 + 232;
  if ( v13 == (char *)-232LL )
  {
    v17 = 0;
  }
  else
  {
    v18 = *((_QWORD *)a1 + 1);
    *(_QWORD *)v17 = &CmsCompositeBase::`vftable';
    *((_DWORD *)v13 + 60) = 0x1000000;
    v13[244] = 0;
    *((_QWORD *)v13 + 31) = v18;
    v13[256] = 0;
    *((_DWORD *)v13 + 65) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
    *(_QWORD *)v17 = &CmsCowRootComposite::`vftable';
    *((_QWORD *)v13 + 42) = 0;
    *((_QWORD *)v13 + 43) = 0;
    *((_QWORD *)v13 + 44) = 0;
    *((_QWORD *)v13 + 45) = 0;
    *((_QWORD *)v13 + 46) = 0;
    *((_DWORD *)v13 + 100) = a5;
    *((_QWORD *)v13 + 47) = 0;
    *((_OWORD *)v13 + 24) = 0;
    memset(v13 + 264, 0, 0x48u);
    if ( a3 )
    {
      *(_OWORD *)(v13 + 264) = *(_OWORD *)a3;
      *(_OWORD *)(v13 + 280) = *((_OWORD *)a3 + 1);
      SmsChecksumBlob::CopyFrom((SmsChecksumBlob *)(v13 + 296), (struct LcnWithChecksum *)((char *)a3 + 32), v19);
    }
    else
    {
      *(_OWORD *)(v13 + 264) = *(_OWORD *)a4;
      *(_OWORD *)(v13 + 280) = *((_OWORD *)a4 + 1);
      CmsChecksum::InitChecksumBlob(
        *(CmsChecksum **)(v18 + 3608),
        a5 << *(_DWORD *)(v18 + 64),
        (struct SmsChecksumBlob *)(v13 + 296));
    }
  }
  v17[12] |= 2u;
  ExInitializeAutoExpandPushLock(v13 + 408, 1);
  *((_QWORD *)v13 + 58) = 0;
  v20 = (struct CmsBPlusTable **)(v13 + 552);
  *((_QWORD *)v13 + 54) = 0;
  *((_QWORD *)v13 + 56) = 0;
  *((_DWORD *)v13 + 115) = 0;
  *((_QWORD *)v13 + 63) = v13 + 496;
  *((_QWORD *)v13 + 62) = v13 + 496;
  *((_QWORD *)v13 + 65) = v13 + 512;
  *((_QWORD *)v13 + 64) = v13 + 512;
  *((_QWORD *)v13 + 66) = 0;
  *((_QWORD *)v13 + 67) = 0;
  *((_QWORD *)v13 + 68) = 0;
  *((_QWORD *)v13 + 60) = 0;
  *((_QWORD *)v13 + 59) = 0;
  *((_QWORD *)v13 + 53) = 0;
  *((_QWORD *)v13 + 55) = 0;
  *((_DWORD *)v13 + 114) = 0;
  *((_QWORD *)v13 + 83) = 0;
  *((_OWORD *)v13 + 49) = 0;
  *((_OWORD *)v13 + 50) = 0;
  v13[836] = 0;
  *((_DWORD *)v13 + 208) = 0;
  *((_QWORD *)v13 + 102) = 0;
  v13[838] = 0;
  *((_QWORD *)v13 + 103) = 0;
  *((_OWORD *)v13 + 53) = 0;
  *((_OWORD *)v13 + 54) = 0;
  v13[900] = 0;
  *((_DWORD *)v13 + 224) = 0;
  *((_QWORD *)v13 + 110) = 0;
  v13[902] = 0;
  *((_QWORD *)v13 + 111) = 0;
  *((_DWORD *)v13 + 229) = 0;
  *((_QWORD *)v13 + 123) = v13 + 552;
  *((_QWORD *)v13 + 137) = 0;
  *((_QWORD *)v13 + 138) = 0;
  *((_QWORD *)v13 + 139) = 0;
  *((_QWORD *)v13 + 127) = 0;
  *((_QWORD *)v13 + 125) = 0;
  v13[1024] = 0;
  *((_QWORD *)v13 + 131) = 0;
  *((_QWORD *)v13 + 129) = 0;
  v13[1056] = 1;
  *((_QWORD *)v13 + 133) = 0;
  *((_QWORD *)v13 + 134) = 1;
  *((_QWORD *)v13 + 135) = 0;
  *((_QWORD *)v13 + 136) = 0;
  *((_QWORD *)v13 + 141) = ML_LSN_NULL;
  *((_DWORD *)v13 + 290) = 0;
  *((_QWORD *)v13 + 144) = v13 + 1144;
  *((_QWORD *)v13 + 143) = v13 + 1144;
  *((_QWORD *)v13 + 147) = v13 + 1168;
  *((_QWORD *)v13 + 146) = v13 + 1168;
  *((_DWORD *)v13 + 300) = 0;
  *((_DWORD *)v13 + 306) = 3;
  *((_QWORD *)v13 + 155) = 0;
  *((_DWORD *)v13 + 304) = 0;
  *((_DWORD *)v13 + 312) = 0;
  *((_QWORD *)v13 + 157) = 0;
  *(_OWORD *)(v13 + 1272) = 0;
  *(_OWORD *)(v13 + 1288) = 0;
  v13[1324] = 0;
  *((_DWORD *)v13 + 330) = 0;
  *((_QWORD *)v13 + 163) = 0;
  v13[1326] = 0;
  *((_QWORD *)v13 + 164) = 0;
  *(_OWORD *)(v13 + 1336) = 0;
  *(_OWORD *)(v13 + 1352) = 0;
  v13[1388] = 0;
  *((_DWORD *)v13 + 346) = 0;
  *((_QWORD *)v13 + 171) = 0;
  v13[1390] = 0;
  *((_QWORD *)v13 + 172) = 0;
  *((_QWORD *)v13 + 179) = v13 + 1448;
  *((_DWORD *)v13 + 355) = v27;
  *((_DWORD *)v13 + 361) = 32;
  *(_OWORD *)(v13 + 1400) = 0;
  *((_DWORD *)v13 + 354) = 0;
  *((_QWORD *)v13 + 178) = 0;
  v13[1440] = 0;
  *((_DWORD *)v13 + 370) = 0;
  *((_QWORD *)v13 + 186) = 0;
  *((_QWORD *)v13 + 88) = 0;
  *((_QWORD *)v13 + 89) = 0;
  *((_QWORD *)v13 + 87) = 0;
  *((_QWORD *)v13 + 86) = v13 + 552;
  *((_QWORD *)v13 + 95) = 0;
  *((_QWORD *)v13 + 96) = 0;
  *((_DWORD *)v13 + 194) = 0;
  *((_QWORD *)v13 + 105) = 0;
  *((_QWORD *)v13 + 166) = 0;
  *((_DWORD *)v13 + 228) = 0;
  *((_QWORD *)v13 + 115) = 0;
  *((_OWORD *)v13 + 58) = 0;
  *((_DWORD *)v13 + 284) = 0;
  *((_QWORD *)v13 + 113) = 0;
  *((_QWORD *)v13 + 174) = 0;
  *((_QWORD *)v13 + 85) = v13 + 672;
  *((_QWORD *)v13 + 84) = v13 + 672;
  *((_QWORD *)v13 + 94) = v13 + 744;
  *((_QWORD *)v13 + 93) = v13 + 744;
  *((_DWORD *)v13 + 290) |= 1u;
  KeInitializeEvent((PRKEVENT)v13 + 30, NotificationEvent, 0);
  KeSetEvent((PRKEVENT)v13 + 30, 0, 0);
  ExInitializeFastResource(v13 + 560, 9);
  *((_QWORD *)v13 + 83) = 0;
  *((_QWORD *)v13 + 120) = 0;
  *((_QWORD *)v13 + 190) = 0;
  *((_QWORD *)v13 + 157) = 0;
  *((_DWORD *)v13 + 312) = 0;
  *((_DWORD *)v13 + 316) = 0;
  *((_QWORD *)v13 + 187) = 0;
  *((_QWORD *)v13 + 186) = 0;
  *((_DWORD *)v13 + 370) = 0;
  *((_QWORD *)v13 + 121) = 0;
  *((_QWORD *)v13 + 3) = 1;
  v13[32] = 0;
  *((_QWORD *)v13 + 5) = a2;
  *(_QWORD *)v15 = &CmsBPlusTable::`vftable';
  *((_QWORD *)v13 + 8) = 0;
  *((_QWORD *)v13 + 9) = 0;
  *((_QWORD *)v13 + 11) = 0;
  *((_QWORD *)v13 + 13) = 0;
  *((_QWORD *)v13 + 14) = 0;
  *((_QWORD *)v13 + 15) = 0;
  *((_QWORD *)v13 + 16) = 0;
  *((_QWORD *)v13 + 17) = 0;
  *((_DWORD *)v13 + 36) = 0;
  *((_QWORD *)v13 + 19) = 4;
  *((_QWORD *)v13 + 20) = 4;
  *((_QWORD *)v13 + 21) = 4;
  *((_QWORD *)v13 + 22) = 4;
  *((_QWORD *)v13 + 23) = 4;
  *((_QWORD *)v13 + 24) = 4;
  *((_DWORD *)v13 + 50) = 4;
  *((_QWORD *)v13 + 26) = 0;
  *((_QWORD *)v13 + 27) = 0;
  *((_WORD *)v13 + 112) = *(unsigned __int8 *)(*((_QWORD *)v17 + 2) + 88LL);
  *((_WORD *)v13 + 113) = -1;
  v13[228] = 0;
  *((_DWORD *)v13 + 51) = 0;
  *((_QWORD *)v13 + 7) = v13 + 408;
  *((_QWORD *)v13 + 10) = v13 + 16;
  *((_QWORD *)v13 + 6) = v13 + 16;
  if ( v13 != (char *)-552LL )
  {
    *((_QWORD *)v13 + 11) = v20;
    *v20 = v15;
    *((_QWORD *)v13 + 87) = v13 + 16;
  }
  v13[32] = v13[32] & 0xFB | (*(_DWORD *)(*((_QWORD *)v13 + 5) + 44LL) >> 6) & 4;
  v21 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v13 + 16);
  *((_QWORD *)v13 + 16) = v17;
  if ( v21 )
    (**v21)(v21, 1);
  v22 = v13[29];
  *((_QWORD *)v13 + 12) = 0;
  v13[29] = v22 & 0xFE | (a6 != 0);
  v13[28] |= 9u;
  v23 = *((_QWORD *)v13 + 5);
  if ( v23 && (*(_DWORD *)(v23 + 44) & 0x200) != 0 )
    v13[32] |= 2u;
LABEL_23:
  *a7 = v15;
  return v16;
}

```

## disassembly

```asm
0x1400959c0  mov     [rsp+arg_18], rbx
0x1400959c5  mov     [rsp+arg_8], rdx
0x1400959ca  push    rbp
0x1400959cb  push    rsi
0x1400959cc  push    rdi
0x1400959cd  push    r12
0x1400959cf  push    r13
0x1400959d1  sub     rsp, 30h
0x1400959d5  mov     r13, rcx
0x1400959d8  mov     r12, r9
0x1400959db  xor     ecx, ecx; ProcNumber
0x1400959dd  mov     rsi, r8
0x1400959e0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400959e7  nop     dword ptr [rax+rax+00h]
0x1400959ec  xor     edx, edx
0x1400959ee  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400959f4  lea     rbx, [rdx+rdx*2]
0x1400959f8  shl     rbx, 6
0x1400959fc  add     rbx, cs:qword_140262478
0x140095a03  cmp     dword ptr [rbx], 5E8h
0x140095a09  jnb     short loc_140095A41
0x140095a0b  xor     ebx, ebx
0x140095a0d  mov     edx, 5F8h
0x140095a12  mov     ecx, 42h ; 'B'
0x140095a17  mov     r8d, 6950534Dh
0x140095a1d  call    cs:__imp_ExAllocatePool2
0x140095a24  nop     dword ptr [rax+rax+00h]
0x140095a29  mov     rdi, rax
0x140095a2c  test    al, 0Fh
0x140095a2e  jz      loc_1401F9BBC
0x140095a34  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140095a3b  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140095a41  cmp     byte ptr [rbx+8], 0
0x140095a45  jnz     loc_140096081
0x140095a4b  mov     rcx, [rbx+58h]
0x140095a4f  mov     rax, rcx
0x140095a52  shr     rax, 20h
0x140095a56  cmp     ecx, eax
0x140095a58  jle     short loc_140095A79
0x140095a5a  nop
0x140095a5b  mov     ecx, 0FFFFFFFFh
0x140095a60  lock xadd [rbx+58h], ecx
0x140095a65  nop
0x140095a66  dec     ecx
0x140095a68  mov     eax, [rbx+5Ch]
0x140095a6b  cmp     ecx, eax
0x140095a6d  jge     loc_1400960A0
0x140095a73  nop
0x140095a74  lock inc dword ptr [rbx+58h]
0x140095a78  nop
0x140095a79  mov     edx, [rbx+4]
0x140095a7c  jmp     short loc_140095A12
0x140095a7e  mov     rdi, rax
0x140095a81  test    rax, rax
0x140095a84  jz      short loc_140095A79
0x140095a86  mov     [rdi], rbx
0x140095a89  lea     rbx, [rdi+10h]
0x140095a8d  test    rbx, rbx
0x140095a90  jz      loc_1400960C6
0x140095a96  mov     [rsp+58h+arg_0], r14
0x140095a9b  xor     ebp, ebp
0x140095a9d  lea     r14, [rbx+0D8h]
0x140095aa4  mov     [rsp+58h+arg_10], r15
0x140095aa9  test    r14, r14
0x140095aac  jz      loc_140095B81
0x140095ab2  mov     r13, [r13+8]
0x140095ab6  lea     rax, ??_7CmsCompositeBase@@6B@; const CmsCompositeBase::`vftable'
0x140095abd  mov     [r14], rax
0x140095ac0  xor     eax, eax
0x140095ac2  mov     dword ptr [r14+8], 1000000h
0x140095aca  mov     [r14+0Ch], al
0x140095ace  mov     [r14+10h], r13
0x140095ad2  mov     [r14+18h], al
0x140095ad6  mov     [r14+1Ch], eax
0x140095ada  lock inc dword ptr [r13+8]
0x140095adf  xor     ecx, ecx
0x140095ae1  lea     rax, ??_7CmsCowRootComposite@@6B@; const CmsCowRootComposite::`vftable'
0x140095ae8  mov     [r14], rax
0x140095aeb  xorps   xmm0, xmm0
0x140095aee  mov     eax, [rsp+58h+arg_20]
0x140095af5  xor     edx, edx; Val
0x140095af7  mov     [rdi+150h], rcx
0x140095afe  mov     r8d, 48h ; 'H'; Size
0x140095b04  mov     [rdi+158h], rcx
0x140095b0b  mov     [rdi+160h], rcx
0x140095b12  mov     [rdi+168h], rcx
0x140095b19  mov     [r14+88h], rcx
0x140095b20  lea     rcx, [r14+20h]; void *
0x140095b24  mov     [r14+0A8h], eax
0x140095b2b  xor     eax, eax
0x140095b2d  mov     [r14+90h], rax
0x140095b34  movups  xmmword ptr [r14+98h], xmm0
0x140095b3c  call    memset
0x140095b41  test    rsi, rsi
0x140095b44  jnz     loc_14009605E
0x140095b4a  movups  xmm0, xmmword ptr [r12]
0x140095b4f  mov     edx, [rsp+58h+arg_20]
0x140095b56  lea     r8, [r14+40h]; struct SmsChecksumBlob *
0x140095b5a  movups  xmmword ptr [r14+20h], xmm0
0x140095b5f  movups  xmm1, xmmword ptr [r12+10h]
0x140095b65  movups  xmmword ptr [r14+30h], xmm1
0x140095b6a  mov     ecx, [r13+40h]
0x140095b6e  shl     edx, cl; unsigned int
0x140095b70  mov     rcx, [r13+0E18h]; this
0x140095b77  call    ?InitChecksumBlob@CmsChecksum@@QEBAXKPEAUSmsChecksumBlob@@@Z; CmsChecksum::InitChecksumBlob(ulong,SmsChecksumBlob *)
0x140095b7c  xor     r12d, r12d
0x140095b7f  jmp     short loc_140095B87
0x140095b81  xor     r12d, r12d
0x140095b84  mov     r14d, r12d
0x140095b87  or      byte ptr [r14+0Ch], 2
0x140095b8c  lea     rsi, [rbx+188h]
0x140095b93  mov     rcx, rsi
0x140095b96  mov     edx, 1
0x140095b9b  call    cs:__imp_ExInitializeAutoExpandPushLock
0x140095ba2  nop     dword ptr [rax+rax+00h]
0x140095ba7  mov     [rsi+38h], r12
0x140095bab  lea     r15, [rbx+218h]
0x140095bb2  mov     [rdi+1B0h], r12
0x140095bb9  lea     rcx, [rsi+58h]
0x140095bbd  mov     [rdi+1C0h], r12
0x140095bc4  lea     rax, [rcx+10h]
0x140095bc8  mov     [rsi+34h], r12d
0x140095bcc  xorps   xmm0, xmm0
0x140095bcf  mov     [rcx+8], rcx
0x140095bd3  mov     [rcx], rcx
0x140095bd6  mov     [rax+8], rax
0x140095bda  mov     [rax], rax
0x140095bdd  mov     [rcx+20h], rbp
0x140095be1  mov     [rcx+28h], r12
0x140095be5  mov     [rcx+30h], r12
0x140095be9  lea     rcx, [r15+250h]
0x140095bf0  mov     [rsi+48h], r12
0x140095bf4  mov     [rsi+40h], r12
0x140095bf8  mov     [rsi+10h], r12
0x140095bfc  mov     [rsi+20h], r12
0x140095c00  mov     [rsi+30h], r12d
0x140095c04  mov     [r15+70h], r12
0x140095c08  movups  xmmword ptr [r15+0E8h], xmm0
0x140095c10  mov     rax, cs:ML_LSN_NULL
0x140095c17  movups  xmmword ptr [r15+0F8h], xmm0
0x140095c1f  mov     [r15+11Ch], bpl
0x140095c26  mov     [r15+118h], r12d
0x140095c2d  mov     [r15+108h], r12
0x140095c34  mov     [r15+11Eh], bpl
0x140095c3b  mov     [r15+110h], r12
0x140095c42  movups  xmmword ptr [r15+128h], xmm0
0x140095c4a  movups  xmmword ptr [r15+138h], xmm0
0x140095c52  mov     [r15+15Ch], bpl
0x140095c59  mov     [r15+158h], r12d
0x140095c60  mov     [r15+148h], r12
0x140095c67  mov     [r15+15Eh], bpl
0x140095c6e  mov     [r15+150h], r12
0x140095c75  mov     [r15+16Ch], r12d
0x140095c7c  mov     [r15+1B0h], r15
0x140095c83  mov     [r15+220h], r12
0x140095c8a  mov     [r15+228h], r12
0x140095c91  mov     [r15+230h], rbp
0x140095c98  mov     [r15+1D0h], r12
0x140095c9f  mov     [r15+1C0h], r12
0x140095ca6  mov     [r15+1D8h], bpl
0x140095cad  mov     [r15+1F0h], r12
0x140095cb4  mov     [r15+1E0h], r12
0x140095cbb  mov     byte ptr [r15+1F8h], 1
0x140095cc3  mov     [r15+200h], r12
0x140095cca  mov     qword ptr [r15+208h], 1
0x140095cd5  mov     [r15+210h], r12
0x140095cdc  mov     [r15+218h], r12
0x140095ce3  mov     [r15+240h], rax
0x140095cea  xor     eax, eax
0x140095cec  mov     [rcx+10h], eax
0x140095cef  lea     rax, [rcx+18h]
0x140095cf3  mov     [rcx+8], rcx
0x140095cf7  mov     [rcx], rcx
0x140095cfa  mov     [rax+8], rax
0x140095cfe  mov     [rax], rax
0x140095d01  mov     [rcx+38h], r12d
0x140095d05  mov     dword ptr [rcx+50h], 3
0x140095d0c  mov     [rcx+60h], r12
0x140095d10  mov     [rcx+48h], r12d
0x140095d14  mov     [r15+2B8h], r12d
0x140095d1b  mov     [r15+2C0h], r12
0x140095d22  movups  xmmword ptr [r15+2D0h], xmm0
0x140095d2a  movups  xmmword ptr [r15+2E0h], xmm0
0x140095d32  mov     [r15+304h], bpl
0x140095d39  mov     [r15+300h], r12d
0x140095d40  mov     [r15+2F0h], r12
0x140095d47  mov     [r15+306h], bpl
0x140095d4e  mov     [r15+2F8h], r12
0x140095d55  movups  xmmword ptr [r15+310h], xmm0
0x140095d5d  movups  xmmword ptr [r15+320h], xmm0
0x140095d65  mov     [r15+344h], bpl
0x140095d6c  mov     [r15+340h], r12d
0x140095d73  lea     rax, [r15+380h]
0x140095d7a  mov     [r15+330h], r12
0x140095d81  lea     rcx, [r15+0A8h]; Event
0x140095d88  mov     [r15+346h], bpl
0x140095d8f  xor     r8d, r8d; State
0x140095d92  mov     [r15+338h], r12
0x140095d99  xor     edx, edx; Type
0x140095d9b  mov     [r15+370h], rax
0x140095da2  mov     eax, [rsp+58h+var_34]
0x140095da6  mov     [r15+364h], eax
0x140095dad  lea     rax, [r15+78h]
0x140095db1  mov     dword ptr [r15+37Ch], 20h ; ' '
0x140095dbc  movups  xmmword ptr [r15+350h], xmm0
0x140095dc4  mov     [r15+360h], r12d
0x140095dcb  mov     [r15+368h], r12
0x140095dd2  mov     [r15+378h], bpl
0x140095dd9  mov     [r15+3A0h], r12d
0x140095de0  mov     [r15+3A8h], r12
0x140095de7  mov     [r15+98h], r12
0x140095dee  mov     [r15+0A0h], r12
0x140095df5  mov     [r15+90h], r12
0x140095dfc  mov     [r15+88h], r15
0x140095e03  mov     [r15+0D0h], r12
0x140095e0a  mov     [r15+0D8h], r12
0x140095e11  mov     [r15+0E0h], r12d
0x140095e18  mov     [r15+120h], r12
0x140095e1f  mov     [r15+308h], r12
0x140095e26  mov     [r15+168h], r12d
0x140095e2d  mov     [r15+170h], rbp
0x140095e34  movups  xmmword ptr [r15+178h], xmm0
0x140095e3c  mov     [r15+248h], r12d
0x140095e43  mov     [r15+160h], r12
0x140095e4a  mov     [r15+348h], r12
0x140095e51  mov     [rax+8], rax
0x140095e55  mov     [rax], rax
0x140095e58  lea     rax, [r15+0C0h]
0x140095e5f  mov     [rax+8], rax
0x140095e63  mov     [rax], rax
0x140095e66  or      dword ptr [r15+260h], 1
0x140095e6e  call    cs:__imp_KeInitializeEvent
0x140095e75  nop     dword ptr [rax+rax+00h]
0x140095e7a  xor     r8d, r8d; Wait
0x140095e7d  lea     rcx, [r15+0A8h]; Event
0x140095e84  xor     edx, edx; Increment
0x140095e86  call    cs:__imp_KeSetEvent
0x140095e8d  nop     dword ptr [rax+rax+00h]
0x140095e92  lea     rcx, [r15+8]
0x140095e96  mov     edx, 9
0x140095e9b  call    cs:__imp_ExInitializeFastResource
0x140095ea2  nop     dword ptr [rax+rax+00h]
0x140095ea7  mov     [r15+70h], r12
0x140095eab  xor     eax, eax
0x140095ead  mov     [r15+198h], r12
0x140095eb4  mov     [r15+3C8h], r12
0x140095ebb  mov     [r15+2C0h], r12
0x140095ec2  mov     [r15+2B8h], r12d
0x140095ec9  mov     [r15+2C8h], r12d
0x140095ed0  mov     [r15+3B0h], rbp
0x140095ed7  mov     [r15+3A8h], r12
0x140095ede  mov     [r15+3A0h], r12d
0x140095ee5  mov     [r15+1A0h], r12
0x140095eec  mov     qword ptr [rbx+8], 1
0x140095ef4  mov     [rbx+10h], al
0x140095ef7  mov     rax, [rsp+58h+arg_8]
0x140095efc  mov     [rbx+18h], rax
0x140095f00  lea     rax, ??_7CmsBPlusTable@@6B@; const CmsBPlusTable::`vftable'
0x140095f07  mov     [rbx], rax
0x140095f0a  mov     [rbx+30h], r12
0x140095f0e  mov     [rbx+38h], r12
0x140095f12  mov     [rbx+48h], r12
0x140095f16  mov     [rbx+58h], r12
0x140095f1a  mov     [rbx+60h], r12
0x140095f1e  mov     [rbx+68h], rbp
0x140095f22  mov     [rbx+70h], r12
0x140095f26  mov     [rbx+78h], rbp
0x140095f2a  mov     [rbx+80h], r12d
0x140095f31  mov     qword ptr [rbx+88h], 4
0x140095f3c  mov     qword ptr [rbx+90h], 4
0x140095f47  mov     qword ptr [rbx+98h], 4
0x140095f52  mov     qword ptr [rbx+0A0h], 4
0x140095f5d  mov     qword ptr [rbx+0A8h], 4
0x140095f68  mov     qword ptr [rbx+0B0h], 4
0x140095f73  mov     dword ptr [rbx+0B8h], 4
0x140095f7d  mov     [rbx+0C0h], r12
0x140095f84  mov     [rbx+0C8h], r12
0x140095f8b  mov     rax, [r14+10h]
0x140095f8f  movzx   ecx, byte ptr [rax+58h]
0x140095f93  mov     [rbx+0D0h], cx
0x140095f9a  mov     word ptr [rbx+0D2h], 0FFFFh
0x140095fa3  mov     [rbx+0D4h], bpl
0x140095faa  mov     [rbx+0BCh], r12d
0x140095fb1  mov     [rbx+28h], rsi
0x140095fb5  mov     [rbx+40h], rbx
0x140095fb9  mov     [rbx+20h], rbx
0x140095fbd  test    r15, r15
0x140095fc0  jz      short loc_140095FD0
0x140095fc2  mov     [rbx+48h], r15
0x140095fc6  mov     [r15], rbx
0x140095fc9  mov     [r15+90h], rbx
0x140095fd0  mov     rax, [rbx+18h]
0x140095fd4  mov     r15, [rsp+58h+arg_10]
0x140095fd9  mov     ecx, [rax+2Ch]
0x140095fdc  movzx   eax, byte ptr [rbx+10h]
0x140095fe0  shr     ecx, 6
0x140095fe3  and     al, 0FBh
0x140095fe5  and     cl, 4
0x140095fe8  or      cl, al
0x140095fea  mov     [rbx+10h], cl
  ... truncated ...
```
