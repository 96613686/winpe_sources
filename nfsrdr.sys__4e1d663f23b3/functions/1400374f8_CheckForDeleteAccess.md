# CheckForDeleteAccess

- ea: `0x1400374f8`
- end: `0x1400378f4`
- name: `CheckForDeleteAccess`
- size: `1020`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14001b1c4`
- `0x1400316d0`

## callees

- `0x140008140`
- `0x14000e4ec`
- `0x1400159fc`
- `0x14002a9e0`
- `0x1400374f8`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400375fa`
- `ntoskrnl!KeReleaseMutex` at `0x140037768`
- `ntoskrnl!KeReleaseMutex` at `0x1400377bf`
- `ntoskrnl!KeReleaseMutex` at `0x1400378aa`
- `ntoskrnl!KeReleaseMutex` at `0x1400375fa`
- `ntoskrnl!KeReleaseMutex` at `0x140037768`
- `ntoskrnl!KeReleaseMutex` at `0x1400377bf`
- `ntoskrnl!KeReleaseMutex` at `0x1400378aa`

## pseudocode

```c
__int64 __fastcall CheckForDeleteAccess(__int64 a1, __int64 a2, __int64 *a3, int a4)
{
  _DWORD *v7; // r15
  __int64 v8; // r13
  __int64 v9; // r14
  unsigned int v10; // edi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 i; // rcx
  unsigned int v14; // eax
  unsigned __int64 v15; // rdx
  struct _KMUTANT *v16; // rcx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  int v19; // ebx
  int v21; // [rsp+30h] [rbp-98h] BYREF
  _DWORD *v22; // [rsp+38h] [rbp-90h]
  _QWORD v23[8]; // [rsp+40h] [rbp-88h] BYREF

  if ( !a1 )
    return (unsigned int)-1073741823;
  if ( !a2 )
    return (unsigned int)-1073741823;
  v7 = *(_DWORD **)(a2 + 40);
  v22 = v7;
  if ( !v7 || !a3 )
    return (unsigned int)-1073741823;
  v8 = a3[1];
  v9 = *a3;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 32LL) + 32LL) + 88LL) != 2 )
  {
    v21 = 0;
    v10 = NfsAccess(a2, a1, v9, a4, (__int64)&v21);
    if ( (v10 & 0x80000000) == 0 )
    {
      HacAcquireLock(v8);
      v19 = *(_DWORD *)(v8 + 128);
      v10 = v19 != 5 ? 0xC0000022 : 0;
      KeReleaseMutex(*(PRKMUTEX *)(v8 + 40), 0);
      if ( v19 != 5 && (v21 & 0x10) != 0 )
        return 0;
      return v10;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      return v10;
    v18 = 46;
    goto LABEL_44;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 1420LL) & 1) == 0 )
  {
    memset(v23, 0, sizeof(v23));
    LODWORD(v23[5]) = 2;
    HIDWORD(v23[6]) = 2;
    HacAcquireLock(v8);
    v16 = *(struct _KMUTANT **)(v8 + 40);
    *(_QWORD *)((char *)&v23[5] + 4) = *(_QWORD *)(v8 + 192);
    v23[7] = *(_QWORD *)(v8 + 200);
    KeReleaseMutex(v16, 0);
    v10 = NfsSetAttributes(a2, a1, a3, v23);
    if ( v10 == -1073741734 )
      return 0;
    if ( (v10 & 0x80000000) == 0 )
      return v10;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      return v10;
    v18 = 45;
LABEL_44:
    WPP_SF_d(v17->AttachedDevice, v18, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    return v10;
  }
  v21 = v7[9];
  v10 = v21 != 0 ? 0xC0000022 : 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  if ( v21 )
  {
    HacAcquireLock(v8);
    v10 = *(_DWORD *)(v8 + 128) != 5 ? 0xC0000022 : 0;
    KeReleaseMutex(*(PRKMUTEX *)(v8 + 40), 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    v7 = v22;
  }
  if ( (v10 & 0x80000000) != 0 )
  {
    HacAcquireLock(v9);
    if ( *(_DWORD *)(v9 + 140) == v7[9] )
    {
      v10 = (*(_DWORD *)(v9 + 132) & 0x80u) == 0 ? 0xC0000022 : 0;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_37;
      v12 = 41;
    }
    else
    {
      if ( *(_DWORD *)(v9 + 144) != v7[10] )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v14 = v7[11];
          v15 = v14;
          if ( v14 >= 0x10 )
            v15 = 16;
          if ( (unsigned int)i >= v15 )
            break;
          if ( *(_DWORD *)(v9 + 144) == v7[i + 12] )
          {
            v10 = (*(_DWORD *)(v9 + 132) & 0x80u) == 0 ? 0xC0000022 : 0;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              v12 = 43;
              goto LABEL_36;
            }
            goto LABEL_37;
          }
        }
        v10 = (*(_DWORD *)(v9 + 132) & 0x80u) == 0 ? 0xC0000022 : 0;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v12 = 44;
          goto LABEL_36;
        }
        goto LABEL_37;
      }
      v10 = (*(_DWORD *)(v9 + 132) & 0x80u) == 0 ? 0xC0000022 : 0;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      {
LABEL_37:
        KeReleaseMutex(*(PRKMUTEX *)(v9 + 40), 0);
        return v10;
      }
      v12 = 42;
    }
LABEL_36:
    WPP_SF_d(v11->AttachedDevice, v12, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    goto LABEL_37;
  }
  return v10;
}

```

## disassembly

```asm
0x1400374f8  push    rbx
0x1400374fa  push    rsi
0x1400374fb  push    rdi
0x1400374fc  push    r12
0x1400374fe  push    r13
0x140037500  push    r14
0x140037502  push    r15
0x140037504  sub     rsp, 90h
0x14003750b  mov     rax, cs:__security_cookie
0x140037512  xor     rax, rsp
0x140037515  mov     [rsp+0C8h+var_48], rax
0x14003751d  mov     rdi, r8
0x140037520  mov     rbx, rdx
0x140037523  mov     rsi, rcx
0x140037526  test    rcx, rcx
0x140037529  jz      loc_1400378C9
0x14003752f  test    rdx, rdx
0x140037532  jz      loc_1400378C9
0x140037538  mov     r15, [rdx+28h]
0x14003753c  mov     [rsp+0C8h+var_90], r15
0x140037541  test    r15, r15
0x140037544  jz      loc_1400378C9
0x14003754a  test    r8, r8
0x14003754d  jz      loc_1400378C9
0x140037553  mov     rax, [rdx+20h]
0x140037557  mov     r13, [r8+8]
0x14003755b  mov     r14, [r8]
0x14003755e  mov     rcx, [rax+20h]
0x140037562  mov     rax, [rcx+20h]
0x140037566  cmp     dword ptr [rax+58h], 2
0x14003756a  jnz     loc_140037837
0x140037570  mov     rax, [rsi+50h]
0x140037574  mov     ecx, [rax+58Ch]
0x14003757a  test    cl, 1
0x14003757d  jz      loc_140037779
0x140037583  mov     ecx, [r15+24h]
0x140037587  mov     [rsp+0C8h+var_98], ecx
0x14003758b  xor     eax, eax
0x14003758d  lea     rsi, WPP_GLOBAL_Control
0x140037594  sub     eax, ecx
0x140037596  mov     r12d, 0C0000022h
0x14003759c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400375a3  neg     eax
0x1400375a5  mov     bl, 4
0x1400375a7  sbb     edi, edi
0x1400375a9  and     edi, r12d
0x1400375ac  cmp     rcx, rsi
0x1400375af  jz      short loc_1400375D0
0x1400375b1  mov     eax, [rcx+2Ch]
0x1400375b4  test    bl, al
0x1400375b6  jz      short loc_1400375D0
0x1400375b8  mov     rcx, [rcx+18h]
0x1400375bc  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x1400375c3  mov     edx, 27h ; '''
0x1400375c8  mov     r9d, edi
0x1400375cb  call    WPP_SF_d
0x1400375d0  cmp     [rsp+0C8h+var_98], 0
0x1400375d5  jz      short loc_140037636
0x1400375d7  mov     rcx, r13
0x1400375da  call    HacAcquireLock
0x1400375df  mov     rcx, [r13+28h]; Mutex
0x1400375e3  mov     r15d, 5
0x1400375e9  sub     r15d, [r13+80h]
0x1400375f0  neg     r15d
0x1400375f3  sbb     edi, edi
0x1400375f5  xor     edx, edx; Wait
0x1400375f7  and     edi, r12d
0x1400375fa  call    cs:__imp_KeReleaseMutex
0x140037601  nop     dword ptr [rax+rax+00h]
0x140037606  mov     rcx, cs:WPP_GLOBAL_Control
0x14003760d  cmp     rcx, rsi
0x140037610  jz      short loc_140037631
0x140037612  mov     eax, [rcx+2Ch]
0x140037615  test    bl, al
0x140037617  jz      short loc_140037631
0x140037619  mov     rcx, [rcx+18h]
0x14003761d  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140037624  mov     edx, 28h ; '('
0x140037629  mov     r9d, edi
0x14003762c  call    WPP_SF_d
0x140037631  mov     r15, [rsp+0C8h+var_90]
0x140037636  test    edi, edi
0x140037638  jns     loc_1400378CE
0x14003763e  mov     rcx, r14
0x140037641  call    HacAcquireLock
0x140037646  mov     eax, [r15+24h]
0x14003764a  cmp     [r14+8Ch], eax
0x140037651  jnz     short loc_14003768A
0x140037653  mov     eax, [r14+84h]
0x14003765a  and     al, 80h
0x14003765c  neg     al
0x14003765e  sbb     edi, edi
0x140037660  not     edi
0x140037662  and     edi, r12d
0x140037665  mov     rcx, cs:WPP_GLOBAL_Control
0x14003766c  cmp     rcx, rsi
0x14003766f  jz      loc_140037762
0x140037675  mov     eax, [rcx+2Ch]
0x140037678  test    bl, al
0x14003767a  jz      loc_140037762
0x140037680  mov     edx, 29h ; ')'
0x140037685  jmp     loc_14003774F
0x14003768a  mov     eax, [r15+28h]
0x14003768e  cmp     [r14+90h], eax
0x140037695  jnz     short loc_1400376CE
0x140037697  mov     eax, [r14+84h]
0x14003769e  and     al, 80h
0x1400376a0  neg     al
0x1400376a2  sbb     edi, edi
0x1400376a4  not     edi
0x1400376a6  and     edi, r12d
0x1400376a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400376b0  cmp     rcx, rsi
0x1400376b3  jz      loc_140037762
0x1400376b9  mov     eax, [rcx+2Ch]
0x1400376bc  test    bl, al
0x1400376be  jz      loc_140037762
0x1400376c4  mov     edx, 2Ah ; '*'
0x1400376c9  jmp     loc_14003774F
0x1400376ce  xor     ecx, ecx
0x1400376d0  mov     eax, [r15+2Ch]
0x1400376d4  mov     edx, eax
0x1400376d6  cmp     eax, 10h
0x1400376d9  jb      short loc_1400376E0
0x1400376db  mov     edx, 10h
0x1400376e0  mov     eax, ecx
0x1400376e2  cmp     rax, rdx
0x1400376e5  jnb     short loc_140037725
0x1400376e7  mov     eax, [r15+rcx*4+30h]
0x1400376ec  cmp     [r14+90h], eax
0x1400376f3  jz      short loc_1400376F9
0x1400376f5  inc     ecx
0x1400376f7  jmp     short loc_1400376D0
0x1400376f9  mov     eax, [r14+84h]
0x140037700  and     al, 80h
0x140037702  neg     al
0x140037704  sbb     edi, edi
0x140037706  not     edi
0x140037708  and     edi, r12d
0x14003770b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037712  cmp     rcx, rsi
0x140037715  jz      short loc_140037762
0x140037717  mov     eax, [rcx+2Ch]
0x14003771a  test    bl, al
0x14003771c  jz      short loc_140037762
0x14003771e  mov     edx, 2Bh ; '+'
0x140037723  jmp     short loc_14003774F
0x140037725  mov     eax, [r14+84h]
0x14003772c  and     al, 80h
0x14003772e  neg     al
0x140037730  sbb     edi, edi
0x140037732  not     edi
0x140037734  and     edi, r12d
0x140037737  mov     rcx, cs:WPP_GLOBAL_Control
0x14003773e  cmp     rcx, rsi
0x140037741  jz      short loc_140037762
0x140037743  mov     eax, [rcx+2Ch]
0x140037746  test    bl, al
0x140037748  jz      short loc_140037762
0x14003774a  mov     edx, 2Ch ; ','
0x14003774f  mov     rcx, [rcx+18h]
0x140037753  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14003775a  mov     r9d, edi
0x14003775d  call    WPP_SF_d
0x140037762  mov     rcx, [r14+28h]; Mutex
0x140037766  xor     edx, edx; Wait
0x140037768  call    cs:__imp_KeReleaseMutex
0x14003776f  nop     dword ptr [rax+rax+00h]
0x140037774  jmp     loc_1400378CE
0x140037779  xor     edx, edx; Val
0x14003777b  lea     rcx, [rsp+0C8h+var_88]; void *
0x140037780  lea     r8d, [rdx+40h]; Size
0x140037784  call    memset
0x140037789  mov     rcx, r13
0x14003778c  mov     [rsp+0C8h+var_60], 2
0x140037794  mov     [rsp+0C8h+var_54], 2
0x14003779c  call    HacAcquireLock
0x1400377a1  mov     rax, [r13+0C0h]
0x1400377a8  xor     edx, edx; Wait
0x1400377aa  mov     rcx, [r13+28h]; Mutex
0x1400377ae  mov     [rsp+0C8h+var_5C], rax
0x1400377b3  mov     rax, [r13+0C8h]
0x1400377ba  mov     [rsp+0C8h+var_50], rax
0x1400377bf  call    cs:__imp_KeReleaseMutex
0x1400377c6  nop     dword ptr [rax+rax+00h]
0x1400377cb  lea     r9, [rsp+0C8h+var_88]
0x1400377d0  mov     r8, rdi
0x1400377d3  mov     rdx, rsi
0x1400377d6  mov     rcx, rbx
0x1400377d9  call    NfsSetAttributes
0x1400377de  mov     edi, eax
0x1400377e0  cmp     eax, 0C000005Ah
0x1400377e5  jnz     short loc_1400377EE
0x1400377e7  xor     edi, edi
0x1400377e9  jmp     loc_1400378CE
0x1400377ee  test    edi, edi
0x1400377f0  jns     loc_1400378CE
0x1400377f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400377fd  lea     rsi, WPP_GLOBAL_Control
0x140037804  cmp     rcx, rsi
0x140037807  jz      loc_1400378CE
0x14003780d  mov     eax, [rcx+2Ch]
0x140037810  mov     bl, 4
0x140037812  test    bl, al
0x140037814  jz      loc_1400378CE
0x14003781a  mov     edx, 2Dh ; '-'
0x14003781f  mov     rcx, [rcx+18h]
0x140037823  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14003782a  mov     r9d, edi
0x14003782d  call    WPP_SF_d
0x140037832  jmp     loc_1400378CE
0x140037837  lea     rax, [rsp+0C8h+var_98]
0x14003783c  mov     [rsp+0C8h+var_98], 0
0x140037844  mov     r8, r14
0x140037847  mov     [rsp+0C8h+var_A8], rax
0x14003784c  mov     rdx, rsi
0x14003784f  mov     rcx, rbx
0x140037852  call    NfsAccess
0x140037857  mov     edi, eax
0x140037859  test    eax, eax
0x14003785b  jns     short loc_140037880
0x14003785d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037864  lea     rsi, WPP_GLOBAL_Control
0x14003786b  cmp     rcx, rsi
0x14003786e  jz      short loc_1400378CE
0x140037870  mov     eax, [rcx+2Ch]
0x140037873  mov     bl, 4
0x140037875  test    bl, al
0x140037877  jz      short loc_1400378CE
0x140037879  mov     edx, 2Eh ; '.'
0x14003787e  jmp     short loc_14003781F
0x140037880  mov     rcx, r13
0x140037883  call    HacAcquireLock
0x140037888  mov     ebx, [r13+80h]
0x14003788f  mov     r15d, 5
0x140037895  mov     rcx, [r13+28h]; Mutex
0x140037899  mov     eax, r15d
0x14003789c  sub     eax, ebx
0x14003789e  neg     eax
0x1400378a0  sbb     edi, edi
0x1400378a2  xor     edx, edx; Wait
0x1400378a4  and     edi, 0C0000022h
0x1400378aa  call    cs:__imp_KeReleaseMutex
0x1400378b1  nop     dword ptr [rax+rax+00h]
0x1400378b6  cmp     ebx, r15d
0x1400378b9  jz      short loc_1400378CE
0x1400378bb  test    byte ptr [rsp+0C8h+var_98], 10h
0x1400378c0  lea     eax, [r15-5]
0x1400378c4  cmovnz  edi, eax
0x1400378c7  jmp     short loc_1400378CE
0x1400378c9  mov     edi, 0C0000001h
0x1400378ce  mov     eax, edi
0x1400378d0  mov     rcx, [rsp+0C8h+var_48]
0x1400378d8  xor     rcx, rsp; StackCookie
0x1400378db  call    __security_check_cookie
0x1400378e0  add     rsp, 90h
0x1400378e7  pop     r15
0x1400378e9  pop     r14
0x1400378eb  pop     r13
0x1400378ed  pop     r12
0x1400378ef  pop     rdi
0x1400378f0  pop     rsi
0x1400378f1  pop     rbx
0x1400378f2  retn
```
