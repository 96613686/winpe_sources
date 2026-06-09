# WheaReportHwError

- ea: `0x140264f20`
- end: `0x14026537c`
- name: `WheaReportHwError`
- size: `1116`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140422e3c`
- `0x1404b4e5c`
- `0x14058c3e0`
- `0x14068f2d0`

## callees

- `0x140264f20`
- `0x140265384`
- `0x1402653d4`
- `0x14026547c`
- `0x140265518`
- `0x140265720`
- `0x140265958`
- `0x140265990`
- `0x1402659e0`
- `0x140265a08`
- `0x140265bd0`
- `0x140541bf0`
- `0x14068ec00`
- `0x14068ecf0`
- `0x14068edd8`
- `0x14068ee80`
- `0x1406dc8c0`

## import_xrefs

- `PSHED!PshedWriteErrorRecord` at `0x1402652e2`
- `PSHED!PshedWriteErrorRecord` at `0x140708661`
- `PSHED!PshedWriteErrorRecord` at `0x1402652e2`
- `PSHED!PshedWriteErrorRecord` at `0x140708661`
- `PSHED!PshedBugCheckSystem` at `0x1407086a4`
- `PSHED!PshedBugCheckSystem` at `0x1407086a4`
- `PSHED!PshedFinalizeErrorRecord` at `0x1402650ab`
- `PSHED!PshedFinalizeErrorRecord` at `0x140265314`
- `PSHED!PshedFinalizeErrorRecord` at `0x140708638`
- `PSHED!PshedFinalizeErrorRecord` at `0x1402650ab`
- `PSHED!PshedFinalizeErrorRecord` at `0x140265314`
- `PSHED!PshedFinalizeErrorRecord` at `0x140708638`

## pseudocode

```c
__int64 __fastcall WheaReportHwError(__int64 a1)
{
  int v1; // r11d
  int v2; // eax
  char v4; // r15
  unsigned __int64 v5; // r13
  char v6; // r12
  _QWORD *WheaInfo; // rax
  __int64 v8; // rcx
  __int64 ErrorSource; // rax
  ULONG_PTR v10; // rdx
  unsigned int v11; // r11d
  __int64 v12; // r14
  __int64 v13; // rax
  char *v14; // rsi
  __int64 v15; // r8
  int v16; // ecx
  unsigned int v17; // r12d
  int v18; // edx
  __int128 *p_Src; // rcx
  __int64 v21; // r13
  char v22; // [rsp+30h] [rbp-49h]
  int v23; // [rsp+34h] [rbp-45h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-41h]
  __int128 Src; // [rsp+40h] [rbp-39h] BYREF
  __int128 v26; // [rsp+50h] [rbp-29h]
  __int64 v27; // [rsp+60h] [rbp-19h]
  __int128 v28; // [rsp+68h] [rbp-11h] BYREF
  __int128 v29; // [rsp+78h] [rbp-1h]

  v1 = *(_DWORD *)(a1 + 20);
  v27 = 0;
  v2 = v1 & 0x40000000;
  v23 = 0;
  Src = 0;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  if ( v1 >= 0 )
  {
    v4 = 0;
    if ( v2 )
    {
      v1 &= ~0x40000000u;
      v21 = *(unsigned int *)(a1 + 8) + 7LL;
      *(_DWORD *)(a1 + 20) = v1;
      v22 = 1;
      v5 = (a1 + v21) & 0xFFFFFFFFFFFFFFF8uLL;
      v6 = 1;
      goto LABEL_5;
    }
  }
  else
  {
    if ( v2 )
      return 3221225485LL;
    v1 &= ~0x80000000;
    v4 = 1;
    *(_DWORD *)(a1 + 20) = v1;
  }
  v5 = 0;
  v22 = 0;
  v6 = 0;
LABEL_5:
  if ( v1 == 3 && !v4 )
    return 0;
  WheaInfo = KeGetPcr()->Prcb.WheaInfo;
  v24 = WheaInfo;
  if ( !WheaInfo || (v8 = WheaInfo[1]) == 0 || !*(_DWORD *)(v8 + 4) )
  {
    if ( (unsigned int)v1 <= 1 && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
      KeBugCheckEx(0x124u, *(int *)(a1 + 28), 0, 0, 0);
    *(_QWORD *)&v28 = 0x1674C6857LL;
    p_Src = &v28;
    *((_QWORD *)&v28 + 1) = 0x100000020LL;
    *(_QWORD *)&v29 = 0x800000364C4E524BuLL;
    *((_QWORD *)&v29 + 1) = 2;
    goto LABEL_24;
  }
  ErrorSource = WheapGetErrorSource(v8, *(unsigned int *)(a1 + 24));
  v12 = ErrorSource;
  if ( ErrorSource )
  {
    _InterlockedAdd((volatile signed __int32 *)(ErrorSource + 24), 1u);
    if ( *(_DWORD *)(a1 + 20) == 2 && (unsigned __int8)WheapApplyThresholdChecks(ErrorSource) )
    {
      p_Src = &Src;
      LODWORD(v27) = *(_DWORD *)(a1 + 28);
      HIDWORD(v27) = *(_DWORD *)(a1 + 24);
      *(_QWORD *)&Src = 0x1674C6857LL;
      *((_QWORD *)&Src + 1) = 0x100000028LL;
      *(_QWORD *)&v26 = 0x800000044C4E524BuLL;
      *((_QWORD *)&v26 + 1) = 0x800000002LL;
LABEL_24:
      WheaLogInternalEvent(p_Src);
      return 0;
    }
    v13 = WheapAllocErrorRecord(v12, &v23);
    v14 = (char *)v13;
    if ( v13 )
    {
      v15 = (unsigned int)(v23 - 40);
      v16 = *(_DWORD *)(v13 + 24)
          ^ ((unsigned __int8)*(_DWORD *)(v13 + 24)
           ^ (unsigned __int8)(*(_DWORD *)(a1 + 12) >> 2))
          & 4;
      *(_DWORD *)(v13 + 24) = v16;
      *(_DWORD *)(v13 + 24) = v16 ^ ((unsigned __int8)v16 ^ (unsigned __int8)(*(_DWORD *)(a1 + 12) >> 2)) & 8;
      v23 = WheapCallErrorSourceCreateRecord(v12, a1, v15, v13 + 40);
      if ( v23 >= 0 )
      {
        if ( v4 || v6 )
          *((_DWORD *)v14 + 36) |= 8u;
        v17 = 0;
        if ( (v14[144] & 2) != 0 )
        {
          if ( (*((_DWORD *)v14 + 6) & 1) == 0 || (unsigned __int8)WheaIsCriticalState() )
            goto LABEL_20;
          if ( WheapEventingInitialized != 1 )
          {
LABEL_64:
            WheapFreeErrorRecord(v14);
            return v17;
          }
        }
        else
        {
          if ( !*(_BYTE *)off_140E0CBE8 && !v4 )
          {
            WheapCompressErrorRecord(0, v14 + 40);
            if ( (int)PshedWriteErrorRecord(1, *((unsigned int *)v14 + 15), v14 + 40) < 0 )
              *(_BYTE *)off_140E0CBE8 = 1;
          }
          v18 = *(_DWORD *)(a1 + 20);
          if ( v18 == 1 )
          {
            if ( !v4 )
            {
              PshedFinalizeErrorRecord(v14 + 40, v12 + 96);
              WheapPersistPageForMemoryError(v14 + 40);
              WheapCompressErrorRecord(3, v14 + 40);
              PshedWriteErrorRecord(0, *((unsigned int *)v14 + 15), v14 + 40);
              WheapAddToDumpFile(v14 + 40, *((unsigned int *)v14 + 15));
              if ( v22 )
                KeBugCheckEx(
                  0x124u,
                  *(int *)(v12 + 104),
                  (ULONG_PTR)(v14 + 40),
                  *(_QWORD *)(v5 + 72),
                  *(_QWORD *)(v5 + 80));
              PshedBugCheckSystem(v12 + 96, v14 + 40);
              return v17;
            }
            goto LABEL_19;
          }
          if ( (unsigned int)(v18 - 2) <= 1 )
          {
LABEL_19:
            PshedFinalizeErrorRecord(v14 + 40, v12 + 96);
            goto LABEL_20;
          }
          if ( v18 )
          {
            WheapFreeErrorRecord(v14);
            return (unsigned int)-1073741811;
          }
          PshedFinalizeErrorRecord(v14 + 40, v12 + 96);
          WheapAttemptErrorRecovery(v14 + 40);
          if ( *((_DWORD *)v14 + 13) == 2 )
          {
            *((_DWORD *)v14 + 36) |= 1u;
          }
          else if ( !v4 )
          {
            WheaRecoveryBugCheck(v14 + 40, v12 + 96, a1);
            return v17;
          }
          if ( (*((_DWORD *)v14 + 6) & 1) == 0
            || WheapEventingInitialized != 1
            || (unsigned __int8)WheaIsCriticalState()
            || v14[144] < 0 )
          {
LABEL_20:
            WheapWorkQueueAddItem(v24[2], v14);
            return v17;
          }
        }
        WheapGenerateETWEvents(v14 + 40);
        goto LABEL_64;
      }
      if ( *(_DWORD *)(a1 + 20) <= 1u && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
        KeBugCheckEx(0x122u, 0xBu, *(int *)(a1 + 28), *(unsigned int *)(a1 + 24), 0);
      WheapFreeErrorRecord(v14);
      return (unsigned int)v23;
    }
    else
    {
      ++*(_DWORD *)(v12 + 16);
      if ( *(_DWORD *)(a1 + 20) <= 1u && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
        KeBugCheckEx(0x122u, 0xAu, *(int *)(a1 + 28), *(unsigned int *)(a1 + 24), 0);
      return 3221225626LL;
    }
  }
  else
  {
    if ( v11 <= 1 && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
      KeBugCheckEx(0x122u, 9u, *(int *)(a1 + 28), v10, 0);
    return 3221225664LL;
  }
}

```

## disassembly

```asm
0x140264f20  push    rbp
0x140264f22  push    rbx
0x140264f23  push    rsi
0x140264f24  push    rdi
0x140264f25  push    r12
0x140264f27  push    r13
0x140264f29  push    r14
0x140264f2b  push    r15
0x140264f2d  lea     rbp, [rsp-1Fh]
0x140264f32  sub     rsp, 98h
0x140264f39  mov     rax, cs:__security_cookie
0x140264f40  xor     rax, rsp
0x140264f43  mov     [rbp+57h+var_48], rax
0x140264f47  mov     r11d, [rcx+14h]
0x140264f4b  xor     eax, eax
0x140264f4d  xorps   xmm0, xmm0
0x140264f50  mov     [rbp+57h+var_70], rax
0x140264f54  xor     edi, edi
0x140264f56  mov     eax, r11d
0x140264f59  and     eax, 40000000h
0x140264f5e  mov     [rbp+57h+var_9C], edi
0x140264f61  mov     rbx, rcx
0x140264f64  movups  [rbp+57h+Src], xmm0
0x140264f68  lea     esi, [rdi+1]
0x140264f6b  movups  [rbp+57h+var_80], xmm0
0x140264f6f  movups  [rbp+57h+var_68], xmm0
0x140264f73  movups  [rbp+57h+var_58], xmm0
0x140264f77  test    r11d, r11d
0x140264f7a  jns     loc_1402651E2
0x140264f80  test    eax, eax
0x140264f82  jnz     loc_140265188
0x140264f88  btr     r11d, 1Fh
0x140264f8d  mov     r15b, sil
0x140264f90  mov     [rcx+14h], r11d
0x140264f94  mov     r13, rdi
0x140264f97  mov     [rbp+57h+var_A0], dil
0x140264f9b  mov     r12b, dil
0x140264f9e  cmp     r11d, 3
0x140264fa2  jz      loc_140265211
0x140264fa8  mov     rax, gs:18h
0x140264fb1  mov     rax, [rax+6160h]
0x140264fb8  mov     [rbp+57h+var_98], rax
0x140264fbc  test    rax, rax
0x140264fbf  jz      loc_140265192
0x140264fc5  mov     rcx, [rax+8]
0x140264fc9  test    rcx, rcx
0x140264fcc  jz      loc_140265192
0x140264fd2  cmp     [rcx+4], edi
0x140264fd5  jz      loc_140265192
0x140264fdb  mov     edx, [rbx+18h]
0x140264fde  call    WheapGetErrorSource
0x140264fe3  mov     r14, rax
0x140264fe6  test    rax, rax
0x140264fe9  jz      loc_14026521F
0x140264fef  lock add [rax+18h], esi
0x140264ff3  cmp     dword ptr [rbx+14h], 2
0x140264ff7  jz      loc_1402650EB
0x140264ffd  lea     rdx, [rbp+57h+var_9C]
0x140265001  mov     rcx, r14
0x140265004  call    WheapAllocErrorRecord
0x140265009  mov     rsi, rax
0x14026500c  test    rax, rax
0x14026500f  jz      loc_1402651CE
0x140265015  mov     eax, [rax+18h]
0x140265018  lea     rdi, [rsi+28h]
0x14026501c  mov     ecx, [rbx+0Ch]
0x14026501f  mov     r9, rdi
0x140265022  mov     r8d, [rbp+57h+var_9C]
0x140265026  mov     rdx, rbx
0x140265029  shr     ecx, 2
0x14026502c  add     r8d, 0FFFFFFD8h
0x140265030  xor     ecx, eax
0x140265032  and     ecx, 4
0x140265035  xor     ecx, eax
0x140265037  mov     [rsi+18h], ecx
0x14026503a  mov     eax, [rbx+0Ch]
0x14026503d  shr     eax, 2
0x140265040  xor     eax, ecx
0x140265042  and     eax, 8
0x140265045  xor     eax, ecx
0x140265047  mov     rcx, r14
0x14026504a  mov     [rsi+18h], eax
0x14026504d  call    WheapCallErrorSourceCreateRecord
0x140265052  mov     [rbp+57h+var_9C], eax
0x140265055  test    eax, eax
0x140265057  js      loc_14026516E
0x14026505d  test    r15b, r15b
0x140265060  jnz     loc_1402652BB
0x140265066  test    r12b, r12b
0x140265069  jnz     loc_1402652BB
0x14026506f  xor     r12d, r12d
0x140265072  test    byte ptr [rdi+68h], 2
0x140265076  jnz     loc_140265144
0x14026507c  mov     rax, cs:off_140E0CBE8
0x140265083  cmp     [rax], r12b
0x140265086  jz      loc_1402652C4
0x14026508c  mov     edx, [rbx+14h]
0x14026508f  cmp     edx, 1
0x140265092  jz      loc_140708628
0x140265098  lea     eax, [rdx-2]
0x14026509b  cmp     eax, 1
0x14026509e  ja      loc_140265305
0x1402650a4  lea     rdx, [r14+60h]
0x1402650a8  mov     rcx, rdi
0x1402650ab  call    cs:__imp_PshedFinalizeErrorRecord
0x1402650b2  nop     dword ptr [rax+rax+00h]
0x1402650b7  mov     rcx, [rbp+57h+var_98]
0x1402650bb  mov     rdx, rsi
0x1402650be  mov     rcx, [rcx+10h]
0x1402650c2  call    WheapWorkQueueAddItem
0x1402650c7  mov     eax, r12d
0x1402650ca  mov     rcx, [rbp+57h+var_48]
0x1402650ce  xor     rcx, rsp; StackCookie
0x1402650d1  call    __security_check_cookie
0x1402650d6  add     rsp, 98h
0x1402650dd  pop     r15
0x1402650df  pop     r14
0x1402650e1  pop     r13
0x1402650e3  pop     r12
0x1402650e5  pop     rdi
0x1402650e6  pop     rsi
0x1402650e7  pop     rbx
0x1402650e8  pop     rbp
0x1402650e9  retn
0x1402650eb  mov     rcx, r14
0x1402650ee  call    WheapApplyThresholdChecks
0x1402650f3  test    al, al
0x1402650f5  jz      loc_140264FFD
0x1402650fb  mov     eax, [rbx+1Ch]
0x1402650fe  lea     rcx, [rbp+57h+Src]; Src
0x140265102  mov     dword ptr [rbp+57h+var_70], eax
0x140265105  mov     eax, [rbx+18h]
0x140265108  mov     dword ptr [rbp+57h+var_70+4], eax
0x14026510b  mov     dword ptr [rbp+57h+Src], 674C6857h
0x140265112  mov     dword ptr [rbp+57h+Src+4], esi
0x140265115  mov     dword ptr [rbp+57h+Src+8], 28h ; '('
0x14026511c  mov     dword ptr [rbp+57h+Src+0Ch], esi
0x14026511f  mov     dword ptr [rbp+57h+var_80+4], 80000004h
0x140265126  mov     dword ptr [rbp+57h+var_80], 4C4E524Bh
0x14026512d  mov     dword ptr [rbp+57h+var_80+8], 2
0x140265134  mov     dword ptr [rbp+57h+var_80+0Ch], 8
0x14026513b  call    WheaLogInternalEvent
0x140265140  xor     eax, eax
0x140265142  jmp     short loc_1402650CA
0x140265144  mov     eax, [rsi+18h]
0x140265147  test    al, 1
0x140265149  jz      loc_1402650B7
0x14026514f  call    WheaIsCriticalState
0x140265154  test    al, al
0x140265156  jnz     loc_1402650B7
0x14026515c  cmp     cs:WheapEventingInitialized, 1
0x140265163  jz      loc_140708612
0x140265169  jmp     loc_14070861A
0x14026516e  cmp     dword ptr [rbx+14h], 1
0x140265172  jbe     loc_140265287
0x140265178  mov     rcx, rsi
0x14026517b  call    WheapFreeErrorRecord
0x140265180  mov     eax, [rbp+57h+var_9C]
0x140265183  jmp     loc_1402650CA
0x140265188  mov     eax, 0C000000Dh
0x14026518d  jmp     loc_1402650CA
0x140265192  cmp     r11d, esi
0x140265195  jbe     loc_14026534F
0x14026519b  mov     dword ptr [rbp+57h+var_68], 674C6857h
0x1402651a2  lea     rcx, [rbp+57h+var_68]
0x1402651a6  mov     dword ptr [rbp+57h+var_68+4], esi
0x1402651a9  mov     dword ptr [rbp+57h+var_68+8], 20h ; ' '
0x1402651b0  mov     dword ptr [rbp+57h+var_68+0Ch], esi
0x1402651b3  mov     dword ptr [rbp+57h+var_58+4], 80000036h
0x1402651ba  mov     dword ptr [rbp+57h+var_58], 4C4E524Bh
0x1402651c1  mov     qword ptr [rbp+57h+var_58+8], 2
0x1402651c9  jmp     loc_14026513B
0x1402651ce  inc     dword ptr [r14+10h]
0x1402651d2  cmp     dword ptr [rbx+14h], 1
0x1402651d6  jbe     short loc_140265257
0x1402651d8  mov     eax, 0C000009Ah
0x1402651dd  jmp     loc_1402650CA
0x1402651e2  mov     r15b, dil
0x1402651e5  test    eax, eax
0x1402651e7  jz      loc_140264F94
0x1402651ed  mov     r13d, [rcx+8]
0x1402651f1  btr     r11d, 1Eh
0x1402651f6  add     r13, 7
0x1402651fa  mov     [rcx+14h], r11d
0x1402651fe  add     r13, rbx
0x140265201  mov     [rbp+57h+var_A0], sil
0x140265205  and     r13, 0FFFFFFFFFFFFFFF8h
0x140265209  mov     r12b, sil
0x14026520c  jmp     loc_140264F9E
0x140265211  test    r15b, r15b
0x140265214  jz      loc_140265140
0x14026521a  jmp     loc_140264FA8
0x14026521f  cmp     r11d, esi
0x140265222  ja      loc_140708608
0x140265228  test    [rbx+0Ch], sil
0x14026522c  jnz     loc_140708608
0x140265232  test    r15b, r15b
0x140265235  jnz     loc_140708608
0x14026523b  movsxd  r8, dword ptr [rbx+1Ch]; BugCheckParameter2
0x14026523f  mov     r9, rdx; BugCheckParameter3
0x140265242  mov     edx, 9; BugCheckParameter1
0x140265247  mov     [rsp+0D0h+BugCheckParameter4], rdi; BugCheckParameter4
0x14026524c  mov     ecx, 122h; BugCheckCode
0x140265251  call    KeBugCheckEx
0x140265257  test    byte ptr [rbx+0Ch], 1
0x14026525b  jnz     loc_1402651D8
0x140265261  test    r15b, r15b
0x140265264  jnz     loc_1402651D8
0x14026526a  mov     r9d, [rbx+18h]; BugCheckParameter3
0x14026526e  mov     edx, 0Ah; BugCheckParameter1
0x140265273  movsxd  r8, dword ptr [rbx+1Ch]; BugCheckParameter2
0x140265277  mov     ecx, 122h; BugCheckCode
0x14026527c  mov     [rsp+0D0h+BugCheckParameter4], rdi; BugCheckParameter4
0x140265281  call    KeBugCheckEx
0x140265287  test    byte ptr [rbx+0Ch], 1
0x14026528b  jnz     loc_140265178
0x140265291  test    r15b, r15b
0x140265294  jnz     loc_140265178
0x14026529a  mov     r9d, [rbx+18h]; BugCheckParameter3
0x14026529e  mov     edx, 0Bh; BugCheckParameter1
0x1402652a3  movsxd  r8, dword ptr [rbx+1Ch]; BugCheckParameter2
0x1402652a7  mov     ecx, 122h; BugCheckCode
0x1402652ac  mov     [rsp+0D0h+BugCheckParameter4], 0; BugCheckParameter4
0x1402652b5  call    KeBugCheckEx
0x1402652bb  or      dword ptr [rdi+68h], 8
0x1402652bf  jmp     loc_14026506F
0x1402652c4  test    r15b, r15b
0x1402652c7  jnz     loc_14026508C
0x1402652cd  mov     rdx, rdi
0x1402652d0  xor     ecx, ecx
0x1402652d2  call    WheapCompressErrorRecord
0x1402652d7  mov     edx, [rdi+14h]
0x1402652da  mov     r8, rdi
0x1402652dd  mov     ecx, 1
0x1402652e2  call    cs:__imp_PshedWriteErrorRecord
0x1402652e9  nop     dword ptr [rax+rax+00h]
0x1402652ee  test    eax, eax
0x1402652f0  jns     loc_14026508C
0x1402652f6  mov     rax, cs:off_140E0CBE8
0x1402652fd  mov     byte ptr [rax], 1
0x140265300  jmp     loc_14026508C
0x140265305  test    edx, edx
0x140265307  jnz     loc_1407086EF
0x14026530d  lea     rdx, [r14+60h]
0x140265311  mov     rcx, rdi
0x140265314  call    cs:__imp_PshedFinalizeErrorRecord
0x14026531b  nop     dword ptr [rax+rax+00h]
0x140265320  mov     rcx, rdi
0x140265323  call    WheapAttemptErrorRecovery
0x140265328  cmp     dword ptr [rdi+0Ch], 2
0x14026532c  jz      loc_1407086B6
0x140265332  test    r15b, r15b
0x140265335  jnz     loc_1407086BA
0x14026533b  mov     r8, rbx
0x14026533e  lea     rdx, [r14+60h]
0x140265342  mov     rcx, rdi
0x140265345  call    WheaRecoveryBugCheck
0x14026534a  jmp     loc_1402650C7
0x14026534f  test    [rbx+0Ch], sil
0x140265353  jnz     loc_14026519B
0x140265359  test    r15b, r15b
0x14026535c  jnz     loc_14026519B
0x140265362  movsxd  rdx, dword ptr [rbx+1Ch]; BugCheckParameter1
0x140265366  xor     r9d, r9d; BugCheckParameter3
0x140265369  xor     r8d, r8d; BugCheckParameter2
0x14026536c  mov     [rsp+0D0h+BugCheckParameter4], rdi; BugCheckParameter4
0x140265371  mov     ecx, 124h; BugCheckCode
0x140265376  call    KeBugCheckEx
0x140708608  mov     eax, 0C00000C0h
0x14070860d  jmp     loc_1402650CA
0x140708612  mov     rcx, rdi
0x140708615  call    WheapGenerateETWEvents
0x14070861a  mov     rcx, rsi
0x14070861d  call    WheapFreeErrorRecord
0x140708622  nop
0x140708623  jmp     loc_1402650C7
0x140708628  test    r15b, r15b
0x14070862b  jnz     loc_1402650A4
0x140708631  lea     rdx, [r14+60h]
0x140708635  mov     rcx, rdi
0x140708638  call    cs:__imp_PshedFinalizeErrorRecord
0x14070863f  nop     dword ptr [rax+rax+00h]
0x140708644  mov     rcx, rdi
0x140708647  call    WheapPersistPageForMemoryError
0x14070864c  mov     rdx, rdi
0x14070864f  mov     ecx, 3
0x140708654  call    WheapCompressErrorRecord
0x140708659  mov     edx, [rdi+14h]
0x14070865c  mov     r8, rdi
0x14070865f  xor     ecx, ecx
0x140708661  call    cs:__imp_PshedWriteErrorRecord
0x140708668  nop     dword ptr [rax+rax+00h]
0x14070866d  mov     edx, [rdi+14h]
0x140708670  mov     rcx, rdi
0x140708673  call    WheapAddToDumpFile
0x140708678  cmp     [rbp+57h+var_A0], r12b
0x14070867c  jz      short loc_14070869D
0x14070867e  mov     rax, [r13+50h]
0x140708682  mov     r8, rdi; BugCheckParameter2
0x140708685  movsxd  rdx, dword ptr [r14+68h]; BugCheckParameter1
  ... truncated ...
```
