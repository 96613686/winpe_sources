# SLQueryLicenseValueInternal

- ea: `0x1409fa9a8`
- end: `0x1409fb15f`
- name: `SLQueryLicenseValueInternal`
- size: `1975`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1409fa590`
- `0x1409fa940`

## callees

- `0x1402232f0`
- `0x140223ba0`
- `0x1402247c0`
- `0x140224f70`
- `0x14029a100`
- `0x14029e8c0`
- `0x14029ecc0`
- `0x1402f3cb0`
- `0x1402f8270`
- `0x1404bfcb0`
- `0x14053cf40`
- `0x1406d9d70`
- `0x1406e8590`
- `0x1406f4480`
- `0x1406f4750`
- `0x1407e4e58`
- `0x1407e5724`
- `0x140964870`
- `0x1409fa9a8`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x1409fae3d`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`
- `0x1409fae01`: `Security-SPP-LastWindowsActivationHResult`
- `0x1409fae10`: `Security-SPP-LastWindowsActivationTime`
- `0x1409fade3`: `Security-SPP-GenuineLocalStatus`
- `0x1409fadf2`: `Security-SPP-Action-StateData`

## pseudocode

```c
__int64 __fastcall SLQueryLicenseValueInternal(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // r13
  char v7; // r15
  int v8; // r9d
  unsigned int i; // esi
  size_t v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // r11d
  __int64 v13; // rbx
  __int64 v14; // rax
  void *v15; // rdx
  AutoBoost *v16; // rbx
  int v17; // ebx
  char v18; // r12
  unsigned __int16 *v19; // rsi
  wchar_t *Pool2; // rax
  const wchar_t *v21; // r15
  unsigned int j; // esi
  int v23; // eax
  __int64 v24; // rsi
  int v25; // eax
  __int64 v26; // rax
  void *v27; // rdx
  AutoBoost *v28; // r15
  __int64 v29; // r12
  int v30; // r15d
  unsigned int k; // esi
  __int64 v32; // r9
  size_t v33; // r8
  unsigned int v34; // eax
  unsigned int v35; // r10d
  __int64 v36; // r9
  int v38; // [rsp+6Ch] [rbp-16Ch] BYREF
  __int64 v39; // [rsp+70h] [rbp-168h]
  int v40; // [rsp+78h] [rbp-160h] BYREF
  __int64 v41; // [rsp+80h] [rbp-158h]
  __int64 v42; // [rsp+88h] [rbp-150h]
  unsigned __int16 *p_Length; // [rsp+90h] [rbp-148h]
  __int64 v44; // [rsp+98h] [rbp-140h]
  PVOID v45; // [rsp+A0h] [rbp-138h]
  int v46; // [rsp+A8h] [rbp-130h]
  PVOID P; // [rsp+B8h] [rbp-120h] BYREF
  const void **p_Buffer; // [rsp+C0h] [rbp-118h]
  __int64 v49; // [rsp+D0h] [rbp-108h]
  __int64 v50; // [rsp+D8h] [rbp-100h]
  __int128 v51; // [rsp+E0h] [rbp-F8h] BYREF
  const UNICODE_STRING *v52; // [rsp+F8h] [rbp-E0h]
  __int64 v53; // [rsp+100h] [rbp-D8h]
  __int64 v54; // [rsp+108h] [rbp-D0h]
  PCUNICODE_STRING String1; // [rsp+118h] [rbp-C0h]
  _QWORD Buf1[14]; // [rsp+120h] [rbp-B8h] BYREF

  v41 = a4;
  v42 = a3;
  p_Length = &a2->Length;
  v6 = a1;
  v49 = a1;
  v52 = a2;
  v53 = a1;
  String1 = a2;
  v54 = a3;
  v50 = a4;
  v39 = a6;
  v51 = 0;
  v45 = 0;
  P = 0;
  if ( a2 && a6 && (v46 = 0, p_Buffer = (const void **)&a2->Buffer, a2->Buffer) && a2->Length >= 2u )
  {
    LOBYTE(v51) = 1;
    *((_QWORD *)&v51 + 1) = a2;
    v38 = sub_1407E4E58(a1);
    v44 = 0;
    v7 = 0;
    v8 = 1;
    v40 = 1;
    for ( i = 0; i < 0xE; ++i )
    {
      v10 = *((unsigned __int16 *)&off_140B78720 + 20 * i + 4);
      v11 = (unsigned __int16)**((_WORD **)&v51 + 1);
      if ( (_WORD)v11 == (_WORD)v10 )
      {
        if ( v11 >> 1 )
        {
          v12 = 0;
          v13 = *(_QWORD *)(*((_QWORD *)&v51 + 1) + 8LL);
          do
          {
            *((_WORD *)Buf1 + v12) = *(_WORD *)(v13 + 2LL * v12) ^ ((v8 + 1) | ((_WORD)v8 << 8) | 0x5555);
            v8 += 2;
            ++v12;
          }
          while ( v12 < v11 >> 1 );
          v40 = v8;
          v6 = v49;
        }
        if ( !memcmp(Buf1, *(&off_140B78720 + 5 * i), v10) )
        {
          v7 = *((_BYTE *)&off_140B78720 + 40 * i + 32);
          v14 = (__int64)*(&off_140B78720 + 5 * i + 2);
          v44 = v14;
          goto LABEL_18;
        }
        v8 = v40;
      }
      else
      {
        v8 += v10;
        v40 = v8;
      }
    }
    v14 = 0;
LABEL_18:
    if ( v14 )
    {
      if ( v7 )
      {
        KeEnterCriticalRegion();
        v16 = (AutoBoost *)KeAbPreAcquire((struct _KTHREAD *)(v6 + 46840), 0);
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 46840), 17, 0) )
          ExfAcquirePushLockSharedEx(v6 + 46840, 0, v16, v6 + 46840);
        if ( v16 )
        {
          if ( (KiAbpGlobalState & 1) != 0 )
            AutoBoost::KiAbpPostAcquire(v16, v15);
          else
            *((_BYTE *)v16 + 10) = 1;
        }
      }
      guard_dispatch_icall_no_overrides(v6, v42, v41, a5);
      if ( v7 )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 46840), 0, 17) != 17 )
          ExfReleasePushLockShared(v6 + 46840);
        KeAbPostRelease((struct _KTHREAD *)(v6 + 46840));
        KeLeaveCriticalRegion();
      }
    }
    v17 = v38;
    if ( v38 >= 0 )
    {
      v18 = 1;
      v40 = 0;
      v17 = sub_1404BFCB0(v6, (unsigned int)&qword_140B79138, 0, (unsigned int)&v40, 4, (__int64)&v38);
      if ( !ExpPlatformBinaryLock.SchedulerApc.Reserved[2] || !v40 || RtlEqualUnicodeString(String1, &stru_140B79148, 0) )
        goto LABEL_47;
      v19 = p_Length;
      v38 = *p_Length + 2;
      Pool2 = (wchar_t *)ExAllocatePool2(256, (unsigned int)v38, 542329939);
      v21 = Pool2;
      v45 = Pool2;
      if ( !Pool2 )
      {
        v17 = -1073741801;
        goto LABEL_77;
      }
      memmove(Pool2, *p_Buffer, *v19);
      Buf1[0] = L"Security-SPP-GenuineLocalStatus";
      Buf1[1] = L"Security-SPP-Action-StateData";
      Buf1[2] = L"Security-SPP-LastWindowsActivationHResult";
      Buf1[3] = L"Security-SPP-LastWindowsActivationTime";
      Buf1[4] = L"Kernel-ExpirationDate";
      Buf1[5] = L"SMR-HostManaged-Enabled";
      Buf1[6] = L"TerminalServices-RemoteConnectionManager-AllowAppServerMode";
      for ( j = 0; ; ++j )
      {
        v23 = 0;
        if ( j >= 7 )
          break;
        if ( !wcsicmp(v21, (const wchar_t *)Buf1[j]) )
        {
          v23 = 1;
          break;
        }
      }
      if ( v23 )
      {
LABEL_47:
        v24 = v39;
      }
      else
      {
        SLGetSubscriptionPfn(v6, &P);
        v24 = v39;
        v25 = guard_dispatch_icall_no_overrides(P, 0, 0, 0);
        if ( (int)(v25 + 0x80000000) < 0 || v25 == -1073741789 )
        {
          v17 = v25;
          if ( !a5 )
            v17 = -1073741789;
          v18 = 0;
        }
      }
      if ( v18 )
      {
        v17 = sub_1404BFCB0(v6, (unsigned int)&v51, v42, v41, a5, v24);
        if ( v17 == -1073741762 )
        {
          KeEnterCriticalRegion();
          v26 = KeAbPreAcquire((struct _KTHREAD *)(v6 + 46840), 0);
          v28 = (AutoBoost *)v26;
          if ( _interlockedbittestandset64((volatile signed __int32 *)(v6 + 46840), 0) )
            ExfAcquirePushLockExclusiveEx(v6 + 46840, v26, v6 + 46840);
          if ( v28 )
          {
            if ( (KiAbpGlobalState & 1) != 0 )
              AutoBoost::KiAbpPostAcquire(v28, v27);
            else
              *((_BYTE *)v28 + 10) = 1;
          }
          *(_BYTE *)(v6 + 46992) = 1;
          if ( (_InterlockedExchangeAdd64((volatile signed __int64 *)(v6 + 46840), 0xFFFFFFFFFFFFFFFFuLL) & 6) == 2 )
            ExfTryToWakePushLock(v6 + 46840);
          KeAbPostRelease((struct _KTHREAD *)(v6 + 46840));
          KeLeaveCriticalRegion();
        }
      }
      v29 = 0;
      v30 = 1;
      for ( k = 0; k < 0xE; ++k )
      {
        v32 = 5LL * k;
        p_Length = (unsigned __int16 *)v32;
        v33 = *((unsigned __int16 *)&off_140B78720 + 20 * k + 4);
        v34 = (unsigned __int16)**((_WORD **)&v51 + 1);
        if ( (_WORD)v34 == (_WORD)v33 )
        {
          if ( v34 >> 1 )
          {
            v35 = 0;
            v36 = *(_QWORD *)(*((_QWORD *)&v51 + 1) + 8LL);
            do
            {
              *((_WORD *)Buf1 + v35) = *(_WORD *)(v36 + 2LL * v35) ^ ((v30 + 1) | ((_WORD)v30 << 8) | 0x5555);
              v30 += 2;
              ++v35;
            }
            while ( v35 < v34 >> 1 );
            v29 = 0;
            v32 = (__int64)p_Length;
          }
          if ( !memcmp(Buf1, *(&off_140B78720 + v32), v33) )
          {
            v29 = (__int64)*(&off_140B78720 + (_QWORD)p_Length + 3);
            break;
          }
        }
        else
        {
          v30 += v33;
        }
      }
      if ( v29 && (v17 >= 0 || v17 == -1073741772 || v17 == -1073741275) )
        guard_dispatch_icall_no_overrides(v6, v42, v41, a5);
    }
  }
  else
  {
    v17 = -1073741811;
  }
LABEL_77:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v45 )
    ExFreePoolWithTag(v45, 0);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1409fa9a8  push    rbx
0x1409fa9aa  push    rsi
0x1409fa9ab  push    rdi
0x1409fa9ac  push    r12
0x1409fa9ae  push    r13
0x1409fa9b0  push    r14
0x1409fa9b2  push    r15
0x1409fa9b4  sub     rsp, 1A0h
0x1409fa9bb  mov     rax, cs:__security_cookie
0x1409fa9c2  xor     rax, rsp
0x1409fa9c5  mov     [rsp+1D8h+var_48], rax
0x1409fa9cd  mov     [rsp+1D8h+var_158], r9
0x1409fa9d5  mov     [rsp+1D8h+var_150], r8
0x1409fa9dd  mov     [rsp+1D8h+var_148], rdx
0x1409fa9e5  mov     r13, rcx
0x1409fa9e8  mov     [rsp+1D8h+var_108], rcx
0x1409fa9f0  mov     [rsp+1D8h+var_E0], rdx
0x1409fa9f8  mov     [rsp+1D8h+var_D8], rcx
0x1409faa00  mov     [rsp+1D8h+String1], rdx
0x1409faa08  mov     [rsp+1D8h+var_D0], r8
0x1409faa10  mov     [rsp+1D8h+var_100], r9
0x1409faa18  mov     rcx, [rsp+1D8h+arg_28]
0x1409faa20  mov     [rsp+1D8h+var_168], rcx
0x1409faa25  xor     edi, edi
0x1409faa27  mov     [rsp+1D8h+var_174], edi
0x1409faa2b  xorps   xmm0, xmm0
0x1409faa2e  movups  [rsp+1D8h+var_F8], xmm0
0x1409faa36  mov     [rsp+1D8h+var_178], dil
0x1409faa3b  mov     [rsp+1D8h+var_138], rdi
0x1409faa43  mov     [rsp+1D8h+P], rdi
0x1409faa4b  test    rdx, rdx
0x1409faa4e  jz      loc_1409FB102
0x1409faa54  test    rcx, rcx
0x1409faa57  jz      loc_1409FB102
0x1409faa5d  mov     ebx, edi
0x1409faa5f  mov     [rsp+1D8h+var_130], ebx
0x1409faa66  mov     [rsp+1D8h+var_174], ebx
0x1409faa6a  lea     rcx, [rdx+8]
0x1409faa6e  mov     [rsp+1D8h+var_118], rcx
0x1409faa76  cmp     [rcx], rdi
0x1409faa79  jz      loc_1409FB102
0x1409faa7f  lea     ecx, [rdi+2]
0x1409faa82  cmp     [rdx], cx
0x1409faa85  jb      loc_1409FB102
0x1409faa8b  lea     r14d, [rdi+1]
0x1409faa8f  mov     byte ptr [rsp+1D8h+var_F8], r14b
0x1409faa97  mov     qword ptr [rsp+1D8h+var_F8+8], rdx
0x1409faa9f  mov     rcx, r13
0x1409faaa2  call    sub_1407E4E58
0x1409faaa7  mov     [rsp+1D8h+var_16C], eax
0x1409faaab  mov     [rsp+1D8h+var_140], rdi
0x1409faab3  mov     r15b, dil
0x1409faab6  mov     [rsp+1D8h+var_170], dil
0x1409faabb  mov     r9d, r14d
0x1409faabe  mov     [rsp+1D8h+var_160], r14d
0x1409faac3  mov     esi, edi
0x1409faac5  lea     rcx, off_140B78720
0x1409faacc  cmp     esi, 0Eh
0x1409faacf  jnb     loc_1409FAB9A
0x1409faad5  mov     eax, esi
0x1409faad7  lea     r12, [rax+rax*4]
0x1409faadb  movzx   r8d, word ptr [rcx+r12*8+8]; Size
0x1409faae1  mov     rcx, qword ptr [rsp+1D8h+var_F8+8]
0x1409faae9  movzx   eax, word ptr [rcx]
0x1409faaec  cmp     ax, r8w
0x1409faaf0  jnz     short loc_1409FAB6A
0x1409faaf2  mov     r10d, eax
0x1409faaf5  shr     r10d, 1
0x1409faaf8  jz      short loc_1409FAB47
0x1409faafa  mov     r11d, edi
0x1409faafd  mov     rax, [rcx+8]
0x1409fab01  mov     rbx, rax
0x1409fab04  mov     edx, r11d
0x1409fab07  movzx   ecx, r9w
0x1409fab0b  shl     cx, 8
0x1409fab0f  lea     eax, [r14+r9]
0x1409fab13  or      cx, ax
0x1409fab16  or      cx, 5555h
0x1409fab1b  xor     cx, [rbx+rdx*2]
0x1409fab1f  mov     word ptr [rsp+rdx*2+1D8h+Buf1], cx
0x1409fab27  add     r9d, 2
0x1409fab2b  add     r11d, r14d
0x1409fab2e  cmp     r11d, r10d
0x1409fab31  jb      short loc_1409FAB04
0x1409fab33  mov     [rsp+1D8h+var_160], r9d
0x1409fab38  mov     ebx, [rsp+1D8h+var_130]
0x1409fab3f  mov     r13, [rsp+1D8h+var_108]
0x1409fab47  lea     rdx, off_140B78720
0x1409fab4e  mov     rdx, [rdx+r12*8]; Buf2
0x1409fab52  lea     rcx, [rsp+1D8h+Buf1]; Buf1
0x1409fab5a  call    memcmp
0x1409fab5f  test    eax, eax
0x1409fab61  jz      short loc_1409FAB7A
0x1409fab63  mov     r9d, [rsp+1D8h+var_160]
0x1409fab68  jmp     short loc_1409FAB72
0x1409fab6a  add     r9d, r8d
0x1409fab6d  mov     [rsp+1D8h+var_160], r9d
0x1409fab72  add     esi, r14d
0x1409fab75  jmp     loc_1409FAAC5
0x1409fab7a  lea     rcx, off_140B78720
0x1409fab81  mov     r15b, [rcx+r12*8+20h]
0x1409fab86  mov     [rsp+1D8h+var_170], r15b
0x1409fab8b  mov     rax, [rcx+r12*8+10h]
0x1409fab90  mov     [rsp+1D8h+var_140], rax
0x1409fab98  jmp     short loc_1409FAB9D
0x1409fab9a  mov     rax, rdi
0x1409fab9d  test    rax, rax
0x1409faba0  jz      loc_1409FACD5
0x1409faba6  test    r15b, r15b
0x1409faba9  jz      short loc_1409FAC04
0x1409fabab  call    KeEnterCriticalRegion
0x1409fabb0  lea     rsi, [r13+0B6F8h]
0x1409fabb7  xor     r8d, r8d
0x1409fabba  xor     edx, edx
0x1409fabbc  mov     rcx, rsi
0x1409fabbf  call    KeAbPreAcquire
0x1409fabc4  mov     rbx, rax
0x1409fabc7  xor     eax, eax
0x1409fabc9  lea     r12d, [rax+11h]
0x1409fabcd  lock cmpxchg [rsi], r12
0x1409fabd2  jz      short loc_1409FABE4
0x1409fabd4  mov     r9, rsi
0x1409fabd7  mov     r8, rbx
0x1409fabda  xor     edx, edx
0x1409fabdc  mov     rcx, rsi
0x1409fabdf  call    ExfAcquirePushLockSharedEx
0x1409fabe4  test    rbx, rbx
0x1409fabe7  jz      short loc_1409FAC0C
0x1409fabe9  mov     eax, cs:?KiAbpGlobalState@@3UKI_AB_GLOBAL_STATE@@A; KI_AB_GLOBAL_STATE KiAbpGlobalState
0x1409fabef  test    r14b, al
0x1409fabf2  jz      short loc_1409FABFE
0x1409fabf4  mov     rcx, rbx; this
0x1409fabf7  call    ?KiAbpPostAcquire@AutoBoost@@YAXPEAX@Z; AutoBoost::KiAbpPostAcquire(void *)
0x1409fabfc  jmp     short loc_1409FAC0C
0x1409fabfe  mov     [rbx+0Ah], r14b
0x1409fac02  jmp     short loc_1409FAC0C
0x1409fac04  mov     r12d, 11h
0x1409fac0a  jmp     short loc_1409FAC14
0x1409fac0c  mov     rax, [rsp+1D8h+var_140]
0x1409fac14  lea     rcx, [rsp+1D8h+var_178]
0x1409fac19  mov     [rsp+1D8h+var_1B0], rcx
0x1409fac1e  mov     rcx, [rsp+1D8h+var_168]
0x1409fac23  mov     [rsp+1D8h+var_1B8], rcx
0x1409fac28  mov     r9d, [rsp+1D8h+arg_20]
0x1409fac30  mov     r8, [rsp+1D8h+var_158]
0x1409fac38  mov     rdx, [rsp+1D8h+var_150]
0x1409fac40  mov     rcx, r13
0x1409fac43  call    _guard_dispatch_icall_no_overrides
0x1409fac48  mov     ebx, eax
0x1409fac4a  mov     [rsp+1D8h+var_174], eax
0x1409fac4e  jmp     short loc_1409FACAA
0x1409fac50  mov     ebx, eax
0x1409fac52  mov     [rsp+1D8h+var_174], eax
0x1409fac56  mov     [rsp+1D8h+var_178], 1
0x1409fac5b  xor     edi, edi
0x1409fac5d  lea     r14d, [rdi+1]
0x1409fac61  lea     r12d, [rdi+11h]
0x1409fac65  mov     [rsp+1D8h+var_138], rdi
0x1409fac6d  mov     r15b, [rsp+1D8h+var_170]
0x1409fac72  mov     rax, [rsp+1D8h+var_E0]
0x1409fac7a  mov     [rsp+1D8h+var_148], rax
0x1409fac82  mov     r13, [rsp+1D8h+var_D8]
0x1409fac8a  mov     rax, [rsp+1D8h+var_D0]
0x1409fac92  mov     [rsp+1D8h+var_150], rax
0x1409fac9a  mov     rax, [rsp+1D8h+var_100]
0x1409faca2  mov     [rsp+1D8h+var_158], rax
0x1409facaa  test    r15b, r15b
0x1409facad  jz      short loc_1409FACD5
0x1409facaf  lea     rsi, [r13+0B6F8h]
0x1409facb6  mov     rax, r12
0x1409facb9  lock cmpxchg [rsi], rdi
0x1409facbe  jz      short loc_1409FACC8
0x1409facc0  mov     rcx, rsi
0x1409facc3  call    ExfReleasePushLockShared
0x1409facc8  mov     rcx, rsi; struct _KTHREAD *
0x1409faccb  call    KeAbPostRelease
0x1409facd0  call    KeLeaveCriticalRegion
0x1409facd5  cmp     [rsp+1D8h+var_178], dil
0x1409facda  jz      short loc_1409FAD11
0x1409facdc  test    ebx, ebx
0x1409facde  js      short loc_1409FACFA
0x1409face0  mov     ecx, 0C0000023h
0x1409face5  mov     eax, [rsp+1D8h+arg_20]
0x1409facec  mov     rdx, [rsp+1D8h+var_168]
0x1409facf1  cmp     [rdx], eax
0x1409facf3  cmova   ebx, ecx
0x1409facf6  mov     [rsp+1D8h+var_174], ebx
0x1409facfa  jmp     short loc_1409FAD0C
0x1409facfc  mov     ebx, eax
0x1409facfe  mov     [rsp+1D8h+var_174], eax
0x1409fad02  xor     edi, edi
0x1409fad04  mov     [rsp+1D8h+var_138], rdi
0x1409fad0c  jmp     loc_1409FB10B
0x1409fad11  mov     ebx, [rsp+1D8h+var_16C]
0x1409fad15  test    ebx, ebx
0x1409fad17  js      loc_1409FB107
0x1409fad1d  mov     r12b, r14b
0x1409fad20  mov     [rsp+1D8h+var_174], edi
0x1409fad24  mov     [rsp+1D8h+var_160], edi
0x1409fad28  lea     rax, [rsp+1D8h+var_16C]
0x1409fad2d  mov     [rsp+1D8h+var_1B0], rax
0x1409fad32  mov     dword ptr [rsp+1D8h+var_1B8], 4
0x1409fad3a  lea     r9, [rsp+1D8h+var_160]
0x1409fad3f  xor     r8d, r8d
0x1409fad42  lea     rdx, qword_140B79138
0x1409fad49  mov     rcx, r13
0x1409fad4c  call    sub_1404BFCB0
0x1409fad51  mov     ebx, eax
0x1409fad53  mov     [rsp+1D8h+var_174], eax
0x1409fad57  cmp     qword ptr cs:ExpPlatformBinaryLock.___u58+30h, 0
0x1409fad5f  jz      loc_1409FAF12
0x1409fad65  cmp     [rsp+1D8h+var_160], edi
0x1409fad69  jz      loc_1409FAF12
0x1409fad6f  xor     r8d, r8d; CaseInSensitive
0x1409fad72  lea     rdx, stru_140B79148; String2
0x1409fad79  mov     rcx, [rsp+1D8h+String1]; String1
0x1409fad81  call    RtlEqualUnicodeString
0x1409fad86  test    al, al
0x1409fad88  jnz     loc_1409FAF12
0x1409fad8e  mov     rsi, [rsp+1D8h+var_148]
0x1409fad96  movzx   eax, word ptr [rsi]
0x1409fad99  add     eax, 2
0x1409fad9c  mov     [rsp+1D8h+var_16C], eax
0x1409fada0  mov     edx, eax
0x1409fada2  mov     ecx, 100h
0x1409fada7  mov     r8d, 20534C53h
0x1409fadad  call    ExAllocatePool2
0x1409fadb2  mov     r15, rax
0x1409fadb5  mov     [rsp+1D8h+var_138], rax
0x1409fadbd  test    rax, rax
0x1409fadc0  jnz     short loc_1409FADCC
0x1409fadc2  mov     ebx, 0C0000017h
0x1409fadc7  jmp     loc_1409FB107
0x1409fadcc  movzx   r8d, word ptr [rsi]; Size
0x1409fadd0  mov     rdx, [rsp+1D8h+var_118]
0x1409fadd8  mov     rdx, [rdx]; Src
0x1409faddb  mov     rcx, r15; void *
0x1409fadde  call    memmove
0x1409fade3  lea     rax, aSecuritySppGen_0; "Security-SPP-GenuineLocalStatus"
0x1409fadea  mov     [rsp+1D8h+Buf1], rax
0x1409fadf2  lea     rax, aSecuritySppAct; "Security-SPP-Action-StateData"
0x1409fadf9  mov     [rsp+1D8h+var_B0], rax
0x1409fae01  lea     rax, aSecuritySppLas_0; "Security-SPP-LastWindowsActivationHResu"...
0x1409fae08  mov     [rsp+1D8h+var_A8], rax
0x1409fae10  lea     rax, aSecuritySppLas; "Security-SPP-LastWindowsActivationTime"
0x1409fae17  mov     [rsp+1D8h+var_A0], rax
0x1409fae1f  lea     rax, aKernelExpirati_0; "Kernel-ExpirationDate"
0x1409fae26  mov     [rsp+1D8h+var_98], rax
0x1409fae2e  lea     rax, aSmrHostmanaged; "SMR-HostManaged-Enabled"
0x1409fae35  mov     [rsp+1D8h+var_90], rax
0x1409fae3d  lea     rax, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x1409fae44  mov     [rsp+1D8h+var_88], rax
0x1409fae4c  mov     esi, edi
0x1409fae4e  mov     eax, edi
0x1409fae50  cmp     esi, 7
0x1409fae53  jnb     short loc_1409FAE73
0x1409fae55  mov     edx, esi
0x1409fae57  mov     rdx, [rsp+rdx*8+1D8h+Buf1]; Str2
0x1409fae5f  mov     rcx, r15; Str1
0x1409fae62  call    _wcsicmp
0x1409fae67  test    eax, eax
0x1409fae69  jz      short loc_1409FAE70
0x1409fae6b  add     esi, r14d
0x1409fae6e  jmp     short loc_1409FAE4E
0x1409fae70  mov     eax, r14d
0x1409fae73  test    eax, eax
0x1409fae75  jnz     loc_1409FAF12
0x1409fae7b  lea     rdx, [rsp+1D8h+P]
0x1409fae83  mov     rcx, r13
0x1409fae86  call    SLGetSubscriptionPfn
0x1409fae8b  mov     rax, qword ptr cs:ExpPlatformBinaryLock.___u58+30h
0x1409fae92  mov     [rsp+1D8h+var_188], rdi
0x1409fae97  mov     rcx, [rsp+1D8h+var_150]
0x1409fae9f  mov     [rsp+1D8h+var_190], rcx
0x1409faea4  mov     rsi, [rsp+1D8h+var_168]
0x1409faea9  mov     [rsp+1D8h+var_198], rsi
0x1409faeae  mov     ecx, [rsp+1D8h+arg_20]
0x1409faeb5  mov     [rsp+1D8h+var_1A0], ecx
0x1409faeb9  mov     rcx, [rsp+1D8h+var_158]
0x1409faec1  mov     [rsp+1D8h+var_1A8], rcx
0x1409faec6  mov     ecx, [rsp+1D8h+var_16C]
0x1409faeca  mov     dword ptr [rsp+1D8h+var_1B0], ecx
0x1409faece  mov     [rsp+1D8h+var_1B8], r15
0x1409faed3  xor     r9d, r9d
0x1409faed6  xor     r8d, r8d
0x1409faed9  xor     edx, edx
0x1409faedb  mov     rcx, [rsp+1D8h+P]
0x1409faee3  call    _guard_dispatch_icall_no_overrides
0x1409faee8  mov     edx, 80000000h
0x1409faeed  lea     ecx, [rax+rdx]
0x1409faef0  test    edx, ecx
0x1409faef2  mov     ecx, 0C0000023h
0x1409faef7  jnz     short loc_1409FAEFD
0x1409faef9  cmp     eax, ecx
0x1409faefb  jnz     short loc_1409FAF17
0x1409faefd  mov     ebx, eax
0x1409faeff  cmp     [rsp+1D8h+arg_20], edi
0x1409faf06  cmovz   ebx, ecx
0x1409faf09  mov     [rsp+1D8h+var_174], ebx
0x1409faf0d  mov     r12b, dil
  ... truncated ...
```
