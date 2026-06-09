# VidMmCopyContentEscape(_D3DKMT_ESCAPE_COPY_CONTENT_DIRECTION,void *,uint,unsigned __int64,unsigned __int64)

- ea: `0x1400ba7f8`
- end: `0x1400bac5f`
- name: `?VidMmCopyContentEscape@@YAJW4_D3DKMT_ESCAPE_COPY_CONTENT_DIRECTION@@PEAXI_K2@Z`
- size: `1127`
- prototype: `__int64 __fastcall(int, char *, unsigned int, size_t, size_t Size)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1400b4468`

## callees

- `0x1400045ec`
- `0x140012ae8`
- `0x14002ed1c`
- `0x14002f510`
- `0x14002faf0`
- `0x14002fd70`
- `0x14003ba24`
- `0x140058760`
- `0x1400587c0`
- `0x1400ba7f8`
- `0x1400ed9e0`
- `0x140117138`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400baab5`
- `watchdog!WdLogSingleEntry3` at `0x1400bab47`
- `watchdog!WdLogSingleEntry3` at `0x1400baab5`
- `watchdog!WdLogSingleEntry3` at `0x1400bab47`
- `watchdog!WdLogSingleEntry2` at `0x1400ba89b`
- `watchdog!WdLogSingleEntry2` at `0x1400bac19`
- `watchdog!WdLogSingleEntry2` at `0x1400ba89b`
- `watchdog!WdLogSingleEntry2` at `0x1400bac19`
- `watchdog!WdLogSingleEntry0` at `0x1400ba922`
- `watchdog!WdLogSingleEntry0` at `0x1400ba922`
- `watchdog!WdLogSingleEntry1` at `0x1400ba84d`
- `watchdog!WdLogSingleEntry1` at `0x1400ba966`
- `watchdog!WdLogSingleEntry1` at `0x1400ba99c`
- `watchdog!WdLogSingleEntry1` at `0x1400baa16`
- `watchdog!WdLogSingleEntry1` at `0x1400baa49`
- `watchdog!WdLogSingleEntry1` at `0x1400baa75`
- `watchdog!WdLogSingleEntry1` at `0x1400babf3`
- `watchdog!WdLogSingleEntry1` at `0x1400ba84d`
- `watchdog!WdLogSingleEntry1` at `0x1400ba966`
- `watchdog!WdLogSingleEntry1` at `0x1400ba99c`
- `watchdog!WdLogSingleEntry1` at `0x1400baa16`
- `watchdog!WdLogSingleEntry1` at `0x1400baa49`
- `watchdog!WdLogSingleEntry1` at `0x1400baa75`
- `watchdog!WdLogSingleEntry1` at `0x1400babf3`

## string_xrefs

- `0x1400bab75`: `Failed to copy memory to or from backing store. pSrc=0x%.16I64x, pDst=0x%.16I64x, Direction=%u`

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
  char ****v16; // r12
  char **v17; // rsi
  unsigned int v18; // ebx
  char *v19; // rax
  char *v21; // rdx
  void *v22[2]; // [rsp+58h] [rbp-70h] BYREF
  char *v23; // [rsp+68h] [rbp-60h]
  char **v24; // [rsp+70h] [rbp-58h]
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
      WdLogGlobalForLineNumber = 33153;
      goto LABEL_44;
    }
    if ( a4 + Size < a4 )
    {
      WdLogSingleEntry2(3, a4, Size);
      WdLogGlobalForLineNumber = 33159;
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
      WdLogGlobalForLineNumber = 33167;
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
    v16 = *(char *****)(v15 + 24);
    if ( !v16 )
    {
      WdLogSingleEntry1(3, v6);
      WdLogGlobalForLineNumber = 33175;
      goto LABEL_44;
    }
    v17 = **v16;
    v24 = v17;
    v23 = *v17;
    DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)v25, (struct DXGFASTMUTEX *const)(v17 + 17), 0);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v25);
    if ( (*((_DWORD *)v16 + 7) & 4) != 0 || ((_DWORD)v16[4] & 1) != 0 )
    {
      WdLogSingleEntry1(3, v16);
      WdLogGlobalForLineNumber = 33190;
      goto LABEL_24;
    }
    if ( (_DWORD)v8 == 1 && !*((_BYTE *)v17 + 42) )
    {
      WdLogSingleEntry1(3, v17);
      WdLogGlobalForLineNumber = 33200;
LABEL_24:
      DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v25);
      goto LABEL_44;
    }
    if ( !v17[6] )
    {
      WdLogSingleEntry1(3, v17);
      WdLogGlobalForLineNumber = 33210;
      goto LABEL_24;
    }
    if ( (*((_DWORD *)v23 + 16) & 1) != 0 )
    {
      WdLogSingleEntry1(3, v17);
      WdLogGlobalForLineNumber = 33220;
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
      WdLogGlobalForLineNumber = 33227;
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
      *((_BYTE *)v17 + 42) = 1;
      *((_DWORD *)v17 + 6) &= ~0x10000u;
      (*(void (__fastcall **)(char *, char *))(*(_QWORD *)v17[29] + 96LL))(v17[29], v17[30]);
    }
    v18 = 0;
    goto LABEL_40;
  }
  WdLogSingleEntry1(3, v8);
  WdLogGlobalForLineNumber = 33146;
LABEL_44:
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v26);
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400ba7f8  mov     [rsp+arg_8], rbx
0x1400ba7fd  mov     [rsp+arg_10], rsi
0x1400ba802  mov     [rsp+arg_0], ecx
0x1400ba806  push    rdi
0x1400ba807  push    r12
0x1400ba809  push    r13
0x1400ba80b  push    r14
0x1400ba80d  push    r15
0x1400ba80f  sub     rsp, 0A0h
0x1400ba816  mov     rbx, r9
0x1400ba819  mov     esi, r8d
0x1400ba81c  mov     r13, rdx
0x1400ba81f  movsxd  r14, ecx
0x1400ba822  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1400ba827  mov     r12, rax
0x1400ba82a  mov     rdx, rax; struct DXGPROCESS *
0x1400ba82d  lea     rcx, [rsp+0C8h+var_40]; this
0x1400ba835  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x1400ba83a  xor     edi, edi
0x1400ba83c  mov     [rsp+0C8h+var_70], rdi
0x1400ba841  cmp     r14d, 1
0x1400ba845  jle     short loc_1400BA868
0x1400ba847  mov     rdx, r14
0x1400ba84a  lea     ecx, [rdi+3]
0x1400ba84d  call    cs:__imp_WdLogSingleEntry1
0x1400ba854  nop     dword ptr [rax+rax+00h]
0x1400ba859  mov     cs:WdLogGlobalForLineNumber, 817Ah
0x1400ba863  jmp     loc_1400BAC2F
0x1400ba868  mov     eax, 0FFFh
0x1400ba86d  mov     r15, [rsp+0C8h+Size]
0x1400ba875  test    rax, rbx
0x1400ba878  jnz     loc_1400BAC0E
0x1400ba87e  test    rax, r15
0x1400ba881  jnz     loc_1400BAC0E
0x1400ba887  lea     rax, [rbx+r15]
0x1400ba88b  cmp     rax, rbx
0x1400ba88e  jnb     short loc_1400BA8B6
0x1400ba890  mov     r8, r15
0x1400ba893  mov     rdx, rbx
0x1400ba896  mov     ecx, 3
0x1400ba89b  call    cs:__imp_WdLogSingleEntry2
0x1400ba8a2  nop     dword ptr [rax+rax+00h]
0x1400ba8a7  mov     cs:WdLogGlobalForLineNumber, 8187h
0x1400ba8b1  jmp     loc_1400BAC2F
0x1400ba8b6  mov     eax, esi
0x1400ba8b8  shr     eax, 6
0x1400ba8bb  and     eax, 0FFFFFFh
0x1400ba8c0  mov     edx, eax
0x1400ba8c2  add     rdx, rdx
0x1400ba8c5  cmp     eax, [r12+128h]
0x1400ba8cd  jb      short loc_1400BA8D4
0x1400ba8cf  mov     al, dil
0x1400ba8d2  jmp     short loc_1400BA905
0x1400ba8d4  mov     rax, [r12+118h]
0x1400ba8dc  mov     r8d, [rax+rdx*8+8]
0x1400ba8e1  mov     ecx, esi
0x1400ba8e3  shr     ecx, 19h
0x1400ba8e6  and     ecx, 60h
0x1400ba8e9  mov     eax, r8d
0x1400ba8ec  and     eax, 60h
0x1400ba8ef  cmp     cl, al
0x1400ba8f1  jnz     short loc_1400BA8CF
0x1400ba8f3  bt      r8d, 0Dh
0x1400ba8f8  jb      short loc_1400BA8CF
0x1400ba8fa  test    r8b, 1Fh
0x1400ba8fe  mov     al, dil
0x1400ba901  jz      short loc_1400BA905
0x1400ba903  mov     al, 1
0x1400ba905  test    al, al
0x1400ba907  jz      short loc_1400BA95E
0x1400ba909  mov     r12, [r12+118h]
0x1400ba911  mov     eax, [r12+rdx*8+8]
0x1400ba916  and     eax, 1Fh
0x1400ba919  cmp     al, 5
0x1400ba91b  jz      short loc_1400BA981
0x1400ba91d  mov     ecx, 2
0x1400ba922  call    cs:__imp_WdLogSingleEntry0
0x1400ba929  nop     dword ptr [rax+rax+00h]
0x1400ba92e  mov     eax, 13Eh
0x1400ba933  mov     cs:WdLogGlobalForLineNumber, eax
0x1400ba939  mov     [rsp+0C8h+var_90], rdi
0x1400ba93e  mov     [rsp+0C8h+var_98], rdi
0x1400ba943  mov     [rsp+0C8h+var_A0], rdi
0x1400ba948  mov     [rsp+0C8h+var_A8], rax
0x1400ba94d  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1400ba954  mov     edx, 40000h
0x1400ba959  call    DxgkLogInternalTriageEvent
0x1400ba95e  mov     rdx, rsi
0x1400ba961  mov     ecx, 3
0x1400ba966  call    cs:__imp_WdLogSingleEntry1
0x1400ba96d  nop     dword ptr [rax+rax+00h]
0x1400ba972  mov     cs:WdLogGlobalForLineNumber, 818Fh
0x1400ba97c  jmp     loc_1400BAC2F
0x1400ba981  mov     r12, [r12+rdx*8]
0x1400ba985  test    r12, r12
0x1400ba988  jz      short loc_1400BA95E
0x1400ba98a  mov     r12, [r12+18h]
0x1400ba98f  test    r12, r12
0x1400ba992  jnz     short loc_1400BA9B7
0x1400ba994  mov     rdx, rsi
0x1400ba997  lea     ecx, [r12+3]
0x1400ba99c  call    cs:__imp_WdLogSingleEntry1
0x1400ba9a3  nop     dword ptr [rax+rax+00h]
0x1400ba9a8  mov     cs:WdLogGlobalForLineNumber, 8197h
0x1400ba9b2  jmp     loc_1400BAC2F
0x1400ba9b7  mov     rax, [r12]
0x1400ba9bb  mov     rsi, [rax]
0x1400ba9be  mov     [rsp+0C8h+var_58], rsi
0x1400ba9c3  mov     rax, [rsi]
0x1400ba9c6  mov     [rsp+0C8h+var_60], rax
0x1400ba9cb  lea     rdx, [rsi+88h]; struct DXGFASTMUTEX *
0x1400ba9d2  xor     r8d, r8d; unsigned __int8
0x1400ba9d5  lea     rcx, [rsp+0C8h+var_50]; this
0x1400ba9da  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1400ba9df  lea     rcx, [rsp+0C8h+var_50]; this
0x1400ba9e4  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400ba9e9  mov     eax, [r12+1Ch]
0x1400ba9ee  test    al, 4
0x1400ba9f0  jnz     loc_1400BABEB
0x1400ba9f6  mov     eax, [r12+20h]
0x1400ba9fb  test    al, 1
0x1400ba9fd  jnz     loc_1400BABEB
0x1400baa03  cmp     r14d, 1
0x1400baa07  jnz     short loc_1400BAA3B
0x1400baa09  cmp     [rsi+2Ah], dil
0x1400baa0d  jnz     short loc_1400BAA3B
0x1400baa0f  mov     rdx, rsi
0x1400baa12  lea     ecx, [r14+2]
0x1400baa16  call    cs:__imp_WdLogSingleEntry1
0x1400baa1d  nop     dword ptr [rax+rax+00h]
0x1400baa22  mov     cs:WdLogGlobalForLineNumber, 81B0h
0x1400baa2c  lea     rcx, [rsp+0C8h+var_50]; this
0x1400baa31  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400baa36  jmp     loc_1400BAC2F
0x1400baa3b  cmp     [rsi+30h], rdi
0x1400baa3f  jnz     short loc_1400BAA61
0x1400baa41  mov     rdx, rsi
0x1400baa44  mov     ecx, 3
0x1400baa49  call    cs:__imp_WdLogSingleEntry1
0x1400baa50  nop     dword ptr [rax+rax+00h]
0x1400baa55  mov     cs:WdLogGlobalForLineNumber, 81BAh
0x1400baa5f  jmp     short loc_1400BAA2C
0x1400baa61  mov     rax, [rsp+0C8h+var_60]
0x1400baa66  mov     eax, [rax+40h]
0x1400baa69  test    al, 1
0x1400baa6b  jz      short loc_1400BAA92
0x1400baa6d  mov     rdx, rsi
0x1400baa70  mov     ecx, 3
0x1400baa75  call    cs:__imp_WdLogSingleEntry1
0x1400baa7c  nop     dword ptr [rax+rax+00h]
0x1400baa81  mov     cs:WdLogGlobalForLineNumber, 81C4h
0x1400baa8b  mov     ebx, 0C000000Dh
0x1400baa90  jmp     short loc_1400BAAD0
0x1400baa92  lea     r9, [rsp+0C8h+var_70]; void **
0x1400baa97  xor     r8d, r8d; unsigned __int64
0x1400baa9a  xor     edx, edx; unsigned __int64
0x1400baa9c  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400baa9f  call    ?VidMmMapViewOfAllocation@@YAPEAXPEAUVIDMM_GLOBAL_ALLOC@@_K1PEAPEAX@Z; VidMmMapViewOfAllocation(VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,void * *)
0x1400baaa4  test    rax, rax
0x1400baaa7  jnz     short loc_1400BAAEE
0x1400baaa9  mov     r9, r15
0x1400baaac  mov     r8, rbx
0x1400baaaf  mov     rdx, rsi
0x1400baab2  lea     ecx, [rax+3]
0x1400baab5  call    cs:__imp_WdLogSingleEntry3
0x1400baabc  nop     dword ptr [rax+rax+00h]
0x1400baac1  mov     cs:WdLogGlobalForLineNumber, 81CBh
0x1400baacb  mov     ebx, 0C0000001h
0x1400baad0  lea     rcx, [rsp+0C8h+var_50]; this
0x1400baad5  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400baada  lea     rcx, [rsp+0C8h+var_40]; this
0x1400baae2  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400baae7  mov     eax, ebx
0x1400baae9  jmp     loc_1400BAC41
0x1400baaee  test    r14d, r14d
0x1400baaf1  jnz     short loc_1400BAAFC
0x1400baaf3  mov     rdx, r13
0x1400baaf6  lea     r13, [rax+rbx]
0x1400baafa  jmp     short loc_1400BAB0A
0x1400baafc  cmp     r14d, 1
0x1400bab00  jnz     loc_1400BABC6
0x1400bab06  lea     rdx, [rax+rbx]; Src
0x1400bab0a  mov     [rsp+0C8h+var_68], r13
0x1400bab0f  mov     [rsp+0C8h+var_60], rdx
0x1400bab14  mov     r8, r15; Size
0x1400bab17  mov     rcx, r13; void *
0x1400bab1a  call    memmove
0x1400bab1f  mov     ebx, edi
0x1400bab21  mov     [rsp+0C8h+var_78], ebx
0x1400bab25  jmp     short loc_1400BAB96
0x1400bab27  movsxd  r14, [rsp+0C8h+arg_0]
0x1400bab2f  mov     r9, r14
0x1400bab32  mov     rdi, [rsp+0C8h+var_68]
0x1400bab37  mov     r8, rdi
0x1400bab3a  mov     rbx, [rsp+0C8h+var_60]
0x1400bab3f  mov     rdx, rbx
0x1400bab42  mov     ecx, 1
0x1400bab47  call    cs:__imp_WdLogSingleEntry3
0x1400bab4e  nop     dword ptr [rax+rax+00h]
0x1400bab53  mov     cs:WdLogGlobalForLineNumber, 81EAh
0x1400bab5d  mov     [rsp+0C8h+var_90], 0
0x1400bab66  mov     [rsp+0C8h+var_98], r14
0x1400bab6b  mov     [rsp+0C8h+var_A0], rdi
0x1400bab70  mov     [rsp+0C8h+var_A8], rbx
0x1400bab75  lea     r9, aFailedToCopyMe; "Failed to copy memory to or from backin"...
0x1400bab7c  mov     edx, 40000h
0x1400bab81  call    DxgkLogInternalTriageEvent
0x1400bab86  mov     ebx, 0C0000001h
0x1400bab8b  mov     [rsp+0C8h+var_78], ebx
0x1400bab8f  xor     edi, edi
0x1400bab91  mov     rsi, [rsp+0C8h+var_58]
0x1400bab96  test    ebx, ebx
0x1400bab98  js      short loc_1400BABCB
0x1400bab9a  test    r14d, r14d
0x1400bab9d  jnz     short loc_1400BABC2
0x1400bab9f  mov     byte ptr [rsi+2Ah], 1
0x1400baba3  btr     dword ptr [rsi+18h], 10h
0x1400baba8  mov     rcx, [rsi+0E8h]
0x1400babaf  mov     rax, [rcx]
0x1400babb2  mov     rax, [rax+60h]
0x1400babb6  mov     rdx, [rsi+0F0h]
0x1400babbd  call    _guard_dispatch_icall
0x1400babc2  mov     ebx, edi
0x1400babc4  jmp     short loc_1400BABCB
0x1400babc6  mov     ebx, 0C000000Dh
0x1400babcb  mov     rdx, [rsp+0C8h+var_70]; void *
0x1400babd0  test    rdx, rdx
0x1400babd3  jz      loc_1400BAAD0
0x1400babd9  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400babdc  call    ?VidMmUnmapViewOfAllocation@@YAXPEAUVIDMM_GLOBAL_ALLOC@@PEAX@Z; VidMmUnmapViewOfAllocation(VIDMM_GLOBAL_ALLOC *,void *)
0x1400babe1  mov     [rsp+0C8h+var_70], rdi
0x1400babe6  jmp     loc_1400BAAD0
0x1400babeb  mov     rdx, r12
0x1400babee  mov     ecx, 3
0x1400babf3  call    cs:__imp_WdLogSingleEntry1
0x1400babfa  nop     dword ptr [rax+rax+00h]
0x1400babff  mov     cs:WdLogGlobalForLineNumber, 81A6h
0x1400bac09  jmp     loc_1400BAA2C
0x1400bac0e  mov     r8, r15
0x1400bac11  mov     rdx, rbx
0x1400bac14  mov     ecx, 3
0x1400bac19  call    cs:__imp_WdLogSingleEntry2
0x1400bac20  nop     dword ptr [rax+rax+00h]
0x1400bac25  mov     cs:WdLogGlobalForLineNumber, 8181h
0x1400bac2f  lea     rcx, [rsp+0C8h+var_40]; this
0x1400bac37  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400bac3c  mov     eax, 0C000000Dh
0x1400bac41  lea     r11, [rsp+0C8h+var_28]
0x1400bac49  mov     rbx, [r11+38h]
0x1400bac4d  mov     rsi, [r11+40h]
0x1400bac51  mov     rsp, r11
0x1400bac54  pop     r15
0x1400bac56  pop     r14
0x1400bac58  pop     r13
0x1400bac5a  pop     r12
0x1400bac5c  pop     rdi
0x1400bac5d  retn
```
