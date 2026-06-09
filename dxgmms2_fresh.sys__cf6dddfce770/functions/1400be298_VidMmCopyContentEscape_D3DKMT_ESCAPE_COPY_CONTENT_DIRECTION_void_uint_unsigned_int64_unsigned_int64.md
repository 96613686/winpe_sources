# VidMmCopyContentEscape(_D3DKMT_ESCAPE_COPY_CONTENT_DIRECTION,void *,uint,unsigned __int64,unsigned __int64)

- ea: `0x1400be298`
- end: `0x1400be6ff`
- name: `?VidMmCopyContentEscape@@YAJW4_D3DKMT_ESCAPE_COPY_CONTENT_DIRECTION@@PEAXI_K2@Z`
- size: `1127`
- prototype: `__int64 __fastcall(int, char *, unsigned int, size_t, size_t Size)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1400b7da4`

## callees

- `0x140004268`
- `0x140012588`
- `0x14002bddc`
- `0x14002c5d0`
- `0x14002d810`
- `0x14002da90`
- `0x14003a734`
- `0x140059030`
- `0x140059080`
- `0x1400be298`
- `0x140110ae0`
- `0x14011ac38`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400be555`
- `watchdog!WdLogSingleEntry3` at `0x1400be5e7`
- `watchdog!WdLogSingleEntry3` at `0x1400be555`
- `watchdog!WdLogSingleEntry3` at `0x1400be5e7`
- `watchdog!WdLogSingleEntry2` at `0x1400be33b`
- `watchdog!WdLogSingleEntry2` at `0x1400be6b9`
- `watchdog!WdLogSingleEntry2` at `0x1400be33b`
- `watchdog!WdLogSingleEntry2` at `0x1400be6b9`
- `watchdog!WdLogSingleEntry0` at `0x1400be3c2`
- `watchdog!WdLogSingleEntry0` at `0x1400be3c2`
- `watchdog!WdLogSingleEntry1` at `0x1400be2ed`
- `watchdog!WdLogSingleEntry1` at `0x1400be406`
- `watchdog!WdLogSingleEntry1` at `0x1400be43c`
- `watchdog!WdLogSingleEntry1` at `0x1400be4b6`
- `watchdog!WdLogSingleEntry1` at `0x1400be4e9`
- `watchdog!WdLogSingleEntry1` at `0x1400be515`
- `watchdog!WdLogSingleEntry1` at `0x1400be693`
- `watchdog!WdLogSingleEntry1` at `0x1400be2ed`
- `watchdog!WdLogSingleEntry1` at `0x1400be406`
- `watchdog!WdLogSingleEntry1` at `0x1400be43c`
- `watchdog!WdLogSingleEntry1` at `0x1400be4b6`
- `watchdog!WdLogSingleEntry1` at `0x1400be4e9`
- `watchdog!WdLogSingleEntry1` at `0x1400be515`
- `watchdog!WdLogSingleEntry1` at `0x1400be693`

## string_xrefs

- `0x1400be615`: `Failed to copy memory to or from backing store. pSrc=0x%.16I64x, pDst=0x%.16I64x, Direction=%u`

## pseudocode

```c
__int64 __fastcall VidMmCopyContentEscape(int a1, char *a2, unsigned int a3, size_t a4, size_t Size)
{
  __int64 v6; // rsi
  __int64 v8; // r14
  struct DXGPROCESS *Current; // r12
  int v11; // r8d
  __int64 v12; // r12
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // r12
  __int64 **v16; // r12
  __int64 v17; // rsi
  unsigned int v18; // ebx
  char *v19; // rax
  char *v21; // rdx
  void *v22[2]; // [rsp+58h] [rbp-70h] BYREF
  char *v23; // [rsp+68h] [rbp-60h]
  __int64 v24; // [rsp+70h] [rbp-58h]
  _BYTE v25[16]; // [rsp+78h] [rbp-50h] BYREF
  _BYTE v26[24]; // [rsp+88h] [rbp-40h] BYREF

  v6 = a3;
  v8 = a1;
  Current = DXGPROCESS::GetCurrent();
  DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v26, Current);
  v22[0] = 0;
  if ( (int)v8 <= 1 )
  {
    if ( (a4 & 0xFFF) != 0 || (Size & 0xFFF) != 0 )
    {
      WdLogSingleEntry2(3, a4, Size);
      WdLogGlobalForLineNumber = 33513;
      goto LABEL_44;
    }
    if ( a4 + Size < a4 )
    {
      WdLogSingleEntry2(3, a4, Size);
      WdLogGlobalForLineNumber = 33519;
      goto LABEL_44;
    }
    if ( !((((unsigned int)v6 >> 6) & 0xFFFFFF) < *((_DWORD *)Current + 74)
        && (v11 = *(_DWORD *)(*((_QWORD *)Current + 35) + 16LL * (((unsigned int)v6 >> 6) & 0xFFFFFF) + 8),
            (((unsigned int)v6 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)Current + 35)
                                                           + 16LL * (((unsigned int)v6 >> 6) & 0xFFFFFF)
                                                           + 8)
                                                & 0x60))
        && (v11 & 0x2000) == 0
        && (v11 & 0x1F) != 0) )
    {
LABEL_15:
      WdLogSingleEntry1(3, v6);
      WdLogGlobalForLineNumber = 33527;
      goto LABEL_44;
    }
    v12 = *((_QWORD *)Current + 35);
    if ( (*(_BYTE *)(v12 + 16LL * (((unsigned int)v6 >> 6) & 0xFFFFFF) + 8) & 0x1F) != 5 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 318;
      DxgkLogInternalTriageEvent(v13, 0x40000, v14, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0);
      goto LABEL_15;
    }
    v15 = *(_QWORD *)(v12 + 16LL * (((unsigned int)v6 >> 6) & 0xFFFFFF));
    if ( !v15 )
      goto LABEL_15;
    v16 = *(__int64 ***)(v15 + 24);
    if ( !v16 )
    {
      WdLogSingleEntry1(3, v6);
      WdLogGlobalForLineNumber = 33535;
      goto LABEL_44;
    }
    v17 = **v16;
    v24 = v17;
    v23 = *(char **)v17;
    DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)v25, (struct DXGFASTMUTEX *const)(v17 + 136), 0);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v25);
    if ( (*((_DWORD *)v16 + 7) & 4) != 0 || ((_DWORD)v16[4] & 1) != 0 )
    {
      WdLogSingleEntry1(3, v16);
      WdLogGlobalForLineNumber = 33550;
      goto LABEL_24;
    }
    if ( (_DWORD)v8 == 1 && !*(_BYTE *)(v17 + 42) )
    {
      WdLogSingleEntry1(3, v17);
      WdLogGlobalForLineNumber = 33560;
LABEL_24:
      DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v25);
      goto LABEL_44;
    }
    if ( !*(_QWORD *)(v17 + 48) )
    {
      WdLogSingleEntry1(3, v17);
      WdLogGlobalForLineNumber = 33570;
      goto LABEL_24;
    }
    if ( (*((_DWORD *)v23 + 16) & 1) != 0 )
    {
      WdLogSingleEntry1(3, v17);
      WdLogGlobalForLineNumber = 33580;
      v18 = -1073741811;
LABEL_31:
      DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v25);
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v26);
      return v18;
    }
    v19 = (char *)VidMmMapViewOfAllocation((struct VIDMM_GLOBAL_ALLOC *)v17, 0, 0, v22);
    if ( !v19 )
    {
      WdLogSingleEntry3(3, v17, a4, Size);
      WdLogGlobalForLineNumber = 33587;
      v18 = -1073741823;
      goto LABEL_31;
    }
    if ( (_DWORD)v8 )
    {
      if ( (_DWORD)v8 != 1 )
      {
        v18 = -1073741811;
LABEL_40:
        if ( v22[0] )
        {
          VidMmUnmapViewOfAllocation((struct VIDMM_GLOBAL_ALLOC *)v17, v22[0]);
          v22[0] = 0;
        }
        goto LABEL_31;
      }
      v21 = &v19[a4];
    }
    else
    {
      v21 = a2;
      a2 = &v19[a4];
    }
    v22[1] = a2;
    v23 = v21;
    memmove(a2, v21, Size);
    if ( !(_DWORD)v8 )
    {
      *(_BYTE *)(v17 + 42) = 1;
      *(_DWORD *)(v17 + 24) &= ~0x10000u;
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v17 + 232) + 96LL))(
        *(_QWORD *)(v17 + 232),
        *(_QWORD *)(v17 + 240));
    }
    v18 = 0;
    goto LABEL_40;
  }
  WdLogSingleEntry1(3, v8);
  WdLogGlobalForLineNumber = 33506;
LABEL_44:
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v26);
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400be298  mov     [rsp+arg_8], rbx
0x1400be29d  mov     [rsp+arg_10], rsi
0x1400be2a2  mov     [rsp+arg_0], ecx
0x1400be2a6  push    rdi
0x1400be2a7  push    r12
0x1400be2a9  push    r13
0x1400be2ab  push    r14
0x1400be2ad  push    r15
0x1400be2af  sub     rsp, 0A0h
0x1400be2b6  mov     rbx, r9
0x1400be2b9  mov     esi, r8d
0x1400be2bc  mov     r13, rdx
0x1400be2bf  movsxd  r14, ecx
0x1400be2c2  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1400be2c7  mov     r12, rax
0x1400be2ca  mov     rdx, rax; struct DXGPROCESS *
0x1400be2cd  lea     rcx, [rsp+0C8h+var_40]; this
0x1400be2d5  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x1400be2da  xor     edi, edi
0x1400be2dc  mov     [rsp+0C8h+var_70], rdi
0x1400be2e1  cmp     r14d, 1
0x1400be2e5  jle     short loc_1400BE308
0x1400be2e7  mov     rdx, r14
0x1400be2ea  lea     ecx, [rdi+3]
0x1400be2ed  call    cs:__imp_WdLogSingleEntry1
0x1400be2f4  nop     dword ptr [rax+rax+00h]
0x1400be2f9  mov     cs:WdLogGlobalForLineNumber, 82E2h
0x1400be303  jmp     loc_1400BE6CF
0x1400be308  mov     eax, 0FFFh
0x1400be30d  mov     r15, [rsp+0C8h+Size]
0x1400be315  test    rax, rbx
0x1400be318  jnz     loc_1400BE6AE
0x1400be31e  test    rax, r15
0x1400be321  jnz     loc_1400BE6AE
0x1400be327  lea     rax, [rbx+r15]
0x1400be32b  cmp     rax, rbx
0x1400be32e  jnb     short loc_1400BE356
0x1400be330  mov     r8, r15
0x1400be333  mov     rdx, rbx
0x1400be336  mov     ecx, 3
0x1400be33b  call    cs:__imp_WdLogSingleEntry2
0x1400be342  nop     dword ptr [rax+rax+00h]
0x1400be347  mov     cs:WdLogGlobalForLineNumber, 82EFh
0x1400be351  jmp     loc_1400BE6CF
0x1400be356  mov     eax, esi
0x1400be358  shr     eax, 6
0x1400be35b  and     eax, 0FFFFFFh
0x1400be360  mov     edx, eax
0x1400be362  add     rdx, rdx
0x1400be365  cmp     eax, [r12+128h]
0x1400be36d  jb      short loc_1400BE374
0x1400be36f  mov     al, dil
0x1400be372  jmp     short loc_1400BE3A5
0x1400be374  mov     rax, [r12+118h]
0x1400be37c  mov     r8d, [rax+rdx*8+8]
0x1400be381  mov     ecx, esi
0x1400be383  shr     ecx, 19h
0x1400be386  and     ecx, 60h
0x1400be389  mov     eax, r8d
0x1400be38c  and     eax, 60h
0x1400be38f  cmp     cl, al
0x1400be391  jnz     short loc_1400BE36F
0x1400be393  bt      r8d, 0Dh
0x1400be398  jb      short loc_1400BE36F
0x1400be39a  test    r8b, 1Fh
0x1400be39e  mov     al, dil
0x1400be3a1  jz      short loc_1400BE3A5
0x1400be3a3  mov     al, 1
0x1400be3a5  test    al, al
0x1400be3a7  jz      short loc_1400BE3FE
0x1400be3a9  mov     r12, [r12+118h]
0x1400be3b1  mov     eax, [r12+rdx*8+8]
0x1400be3b6  and     eax, 1Fh
0x1400be3b9  cmp     al, 5
0x1400be3bb  jz      short loc_1400BE421
0x1400be3bd  mov     ecx, 2
0x1400be3c2  call    cs:__imp_WdLogSingleEntry0
0x1400be3c9  nop     dword ptr [rax+rax+00h]
0x1400be3ce  mov     eax, 13Eh
0x1400be3d3  mov     cs:WdLogGlobalForLineNumber, eax
0x1400be3d9  mov     [rsp+0C8h+var_90], rdi
0x1400be3de  mov     [rsp+0C8h+var_98], rdi
0x1400be3e3  mov     [rsp+0C8h+var_A0], rdi
0x1400be3e8  mov     [rsp+0C8h+var_A8], rax
0x1400be3ed  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1400be3f4  mov     edx, 40000h
0x1400be3f9  call    DxgkLogInternalTriageEvent
0x1400be3fe  mov     rdx, rsi
0x1400be401  mov     ecx, 3
0x1400be406  call    cs:__imp_WdLogSingleEntry1
0x1400be40d  nop     dword ptr [rax+rax+00h]
0x1400be412  mov     cs:WdLogGlobalForLineNumber, 82F7h
0x1400be41c  jmp     loc_1400BE6CF
0x1400be421  mov     r12, [r12+rdx*8]
0x1400be425  test    r12, r12
0x1400be428  jz      short loc_1400BE3FE
0x1400be42a  mov     r12, [r12+18h]
0x1400be42f  test    r12, r12
0x1400be432  jnz     short loc_1400BE457
0x1400be434  mov     rdx, rsi
0x1400be437  lea     ecx, [r12+3]
0x1400be43c  call    cs:__imp_WdLogSingleEntry1
0x1400be443  nop     dword ptr [rax+rax+00h]
0x1400be448  mov     cs:WdLogGlobalForLineNumber, 82FFh
0x1400be452  jmp     loc_1400BE6CF
0x1400be457  mov     rax, [r12]
0x1400be45b  mov     rsi, [rax]
0x1400be45e  mov     [rsp+0C8h+var_58], rsi
0x1400be463  mov     rax, [rsi]
0x1400be466  mov     [rsp+0C8h+var_60], rax
0x1400be46b  lea     rdx, [rsi+88h]; struct DXGFASTMUTEX *
0x1400be472  xor     r8d, r8d; unsigned __int8
0x1400be475  lea     rcx, [rsp+0C8h+var_50]; this
0x1400be47a  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1400be47f  lea     rcx, [rsp+0C8h+var_50]; this
0x1400be484  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400be489  mov     eax, [r12+1Ch]
0x1400be48e  test    al, 4
0x1400be490  jnz     loc_1400BE68B
0x1400be496  mov     eax, [r12+20h]
0x1400be49b  test    al, 1
0x1400be49d  jnz     loc_1400BE68B
0x1400be4a3  cmp     r14d, 1
0x1400be4a7  jnz     short loc_1400BE4DB
0x1400be4a9  cmp     [rsi+2Ah], dil
0x1400be4ad  jnz     short loc_1400BE4DB
0x1400be4af  mov     rdx, rsi
0x1400be4b2  lea     ecx, [r14+2]
0x1400be4b6  call    cs:__imp_WdLogSingleEntry1
0x1400be4bd  nop     dword ptr [rax+rax+00h]
0x1400be4c2  mov     cs:WdLogGlobalForLineNumber, 8318h
0x1400be4cc  lea     rcx, [rsp+0C8h+var_50]; this
0x1400be4d1  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400be4d6  jmp     loc_1400BE6CF
0x1400be4db  cmp     [rsi+30h], rdi
0x1400be4df  jnz     short loc_1400BE501
0x1400be4e1  mov     rdx, rsi
0x1400be4e4  mov     ecx, 3
0x1400be4e9  call    cs:__imp_WdLogSingleEntry1
0x1400be4f0  nop     dword ptr [rax+rax+00h]
0x1400be4f5  mov     cs:WdLogGlobalForLineNumber, 8322h
0x1400be4ff  jmp     short loc_1400BE4CC
0x1400be501  mov     rax, [rsp+0C8h+var_60]
0x1400be506  mov     eax, [rax+40h]
0x1400be509  test    al, 1
0x1400be50b  jz      short loc_1400BE532
0x1400be50d  mov     rdx, rsi
0x1400be510  mov     ecx, 3
0x1400be515  call    cs:__imp_WdLogSingleEntry1
0x1400be51c  nop     dword ptr [rax+rax+00h]
0x1400be521  mov     cs:WdLogGlobalForLineNumber, 832Ch
0x1400be52b  mov     ebx, 0C000000Dh
0x1400be530  jmp     short loc_1400BE570
0x1400be532  lea     r9, [rsp+0C8h+var_70]; void **
0x1400be537  xor     r8d, r8d; unsigned __int64
0x1400be53a  xor     edx, edx; unsigned __int64
0x1400be53c  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400be53f  call    ?VidMmMapViewOfAllocation@@YAPEAXPEAUVIDMM_GLOBAL_ALLOC@@_K1PEAPEAX@Z; VidMmMapViewOfAllocation(VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,void * *)
0x1400be544  test    rax, rax
0x1400be547  jnz     short loc_1400BE58E
0x1400be549  mov     r9, r15
0x1400be54c  mov     r8, rbx
0x1400be54f  mov     rdx, rsi
0x1400be552  lea     ecx, [rax+3]
0x1400be555  call    cs:__imp_WdLogSingleEntry3
0x1400be55c  nop     dword ptr [rax+rax+00h]
0x1400be561  mov     cs:WdLogGlobalForLineNumber, 8333h
0x1400be56b  mov     ebx, 0C0000001h
0x1400be570  lea     rcx, [rsp+0C8h+var_50]; this
0x1400be575  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400be57a  lea     rcx, [rsp+0C8h+var_40]; this
0x1400be582  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400be587  mov     eax, ebx
0x1400be589  jmp     loc_1400BE6E1
0x1400be58e  test    r14d, r14d
0x1400be591  jnz     short loc_1400BE59C
0x1400be593  mov     rdx, r13
0x1400be596  lea     r13, [rax+rbx]
0x1400be59a  jmp     short loc_1400BE5AA
0x1400be59c  cmp     r14d, 1
0x1400be5a0  jnz     loc_1400BE666
0x1400be5a6  lea     rdx, [rax+rbx]; Src
0x1400be5aa  mov     [rsp+0C8h+var_68], r13
0x1400be5af  mov     [rsp+0C8h+var_60], rdx
0x1400be5b4  mov     r8, r15; Size
0x1400be5b7  mov     rcx, r13; void *
0x1400be5ba  call    memmove
0x1400be5bf  mov     ebx, edi
0x1400be5c1  mov     [rsp+0C8h+var_78], ebx
0x1400be5c5  jmp     short loc_1400BE636
0x1400be5c7  movsxd  r14, [rsp+0C8h+arg_0]
0x1400be5cf  mov     r9, r14
0x1400be5d2  mov     rdi, [rsp+0C8h+var_68]
0x1400be5d7  mov     r8, rdi
0x1400be5da  mov     rbx, [rsp+0C8h+var_60]
0x1400be5df  mov     rdx, rbx
0x1400be5e2  mov     ecx, 1
0x1400be5e7  call    cs:__imp_WdLogSingleEntry3
0x1400be5ee  nop     dword ptr [rax+rax+00h]
0x1400be5f3  mov     cs:WdLogGlobalForLineNumber, 8352h
0x1400be5fd  mov     [rsp+0C8h+var_90], 0
0x1400be606  mov     [rsp+0C8h+var_98], r14
0x1400be60b  mov     [rsp+0C8h+var_A0], rdi
0x1400be610  mov     [rsp+0C8h+var_A8], rbx
0x1400be615  lea     r9, aFailedToCopyMe; "Failed to copy memory to or from backin"...
0x1400be61c  mov     edx, 40000h
0x1400be621  call    DxgkLogInternalTriageEvent
0x1400be626  mov     ebx, 0C0000001h
0x1400be62b  mov     [rsp+0C8h+var_78], ebx
0x1400be62f  xor     edi, edi
0x1400be631  mov     rsi, [rsp+0C8h+var_58]
0x1400be636  test    ebx, ebx
0x1400be638  js      short loc_1400BE66B
0x1400be63a  test    r14d, r14d
0x1400be63d  jnz     short loc_1400BE662
0x1400be63f  mov     byte ptr [rsi+2Ah], 1
0x1400be643  btr     dword ptr [rsi+18h], 10h
0x1400be648  mov     rcx, [rsi+0E8h]
0x1400be64f  mov     rax, [rcx]
0x1400be652  mov     rax, [rax+60h]
0x1400be656  mov     rdx, [rsi+0F0h]
0x1400be65d  call    _guard_dispatch_icall
0x1400be662  mov     ebx, edi
0x1400be664  jmp     short loc_1400BE66B
0x1400be666  mov     ebx, 0C000000Dh
0x1400be66b  mov     rdx, [rsp+0C8h+var_70]; void *
0x1400be670  test    rdx, rdx
0x1400be673  jz      loc_1400BE570
0x1400be679  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400be67c  call    ?VidMmUnmapViewOfAllocation@@YAXPEAUVIDMM_GLOBAL_ALLOC@@PEAX@Z; VidMmUnmapViewOfAllocation(VIDMM_GLOBAL_ALLOC *,void *)
0x1400be681  mov     [rsp+0C8h+var_70], rdi
0x1400be686  jmp     loc_1400BE570
0x1400be68b  mov     rdx, r12
0x1400be68e  mov     ecx, 3
0x1400be693  call    cs:__imp_WdLogSingleEntry1
0x1400be69a  nop     dword ptr [rax+rax+00h]
0x1400be69f  mov     cs:WdLogGlobalForLineNumber, 830Eh
0x1400be6a9  jmp     loc_1400BE4CC
0x1400be6ae  mov     r8, r15
0x1400be6b1  mov     rdx, rbx
0x1400be6b4  mov     ecx, 3
0x1400be6b9  call    cs:__imp_WdLogSingleEntry2
0x1400be6c0  nop     dword ptr [rax+rax+00h]
0x1400be6c5  mov     cs:WdLogGlobalForLineNumber, 82E9h
0x1400be6cf  lea     rcx, [rsp+0C8h+var_40]; this
0x1400be6d7  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400be6dc  mov     eax, 0C000000Dh
0x1400be6e1  lea     r11, [rsp+0C8h+var_28]
0x1400be6e9  mov     rbx, [r11+38h]
0x1400be6ed  mov     rsi, [r11+40h]
0x1400be6f1  mov     rsp, r11
0x1400be6f4  pop     r15
0x1400be6f6  pop     r14
0x1400be6f8  pop     r13
0x1400be6fa  pop     r12
0x1400be6fc  pop     rdi
0x1400be6fd  retn
```
