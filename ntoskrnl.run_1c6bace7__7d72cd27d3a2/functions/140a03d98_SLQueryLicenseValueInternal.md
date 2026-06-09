# SLQueryLicenseValueInternal

- ea: `0x140a03d98`
- end: `0x140a0454f`
- name: `SLQueryLicenseValueInternal`
- size: `1975`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140a03980`
- `0x140a03d30`

## callees

- `0x140212ec0`
- `0x140213760`
- `0x140214360`
- `0x140214b10`
- `0x140250630`
- `0x1402acde0`
- `0x1402ad1e0`
- `0x14034a0c0`
- `0x14036f270`
- `0x1404cfb80`
- `0x140544600`
- `0x1406dc8c0`
- `0x1406eb0e0`
- `0x1406f6f80`
- `0x1406f7250`
- `0x1407e7b18`
- `0x1407e83e4`
- `0x140873c20`
- `0x140a03d98`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140a041e2`: `Security-SPP-Action-StateData`
- `0x140a041d3`: `Security-SPP-GenuineLocalStatus`
- `0x140a04200`: `Security-SPP-LastWindowsActivationTime`
- `0x140a041f1`: `Security-SPP-LastWindowsActivationHResult`
- `0x140a0422d`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`

## pseudocode

```c
__int64 __fastcall SLQueryLicenseValueInternal(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        int a5,
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
    v38 = sub_1407E7B18(a1);
    v44 = 0;
    v7 = 0;
    v8 = 1;
    v40 = 1;
    for ( i = 0; i < 0xE; ++i )
    {
      v10 = *((unsigned __int16 *)&off_140B7AB40 + 20 * i + 4);
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
        if ( !memcmp(Buf1, *(&off_140B7AB40 + 5 * i), v10) )
        {
          v7 = *((_BYTE *)&off_140B7AB40 + 40 * i + 32);
          v14 = (__int64)*(&off_140B7AB40 + 5 * i + 2);
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
      guard_dispatch_icall_no_overrides(v6, v42, v41);
      if ( v7 )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 46840), 0, 17) != 17 )
          ExfReleasePushLockShared(v6 + 46840);
        KeAbPostRelease(v6 + 46840);
        KeLeaveCriticalRegion();
      }
    }
    v17 = v38;
    if ( v38 >= 0 )
    {
      v18 = 1;
      v40 = 0;
      v17 = sub_1404CFB80(v6, (unsigned int)&qword_140B7B588, 0, (unsigned int)&v40, 4, (__int64)&v38);
      if ( !qword_140FDA368 || !v40 || RtlEqualUnicodeString(String1, &stru_140B7B578, 0) )
        goto LABEL_47;
      v19 = p_Length;
      v38 = *p_Length + 2;
      Pool2 = (wchar_t *)ExAllocatePool2(256, (unsigned int)v38, 0x20534C53u);
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
        v25 = guard_dispatch_icall_no_overrides(P, 0, 0);
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
        v17 = sub_1404CFB80(v6, (unsigned int)&v51, v42, v41, a5, v24);
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
          KeAbPostRelease(v6 + 46840);
          KeLeaveCriticalRegion();
        }
      }
      v29 = 0;
      v30 = 1;
      for ( k = 0; k < 0xE; ++k )
      {
        v32 = 5LL * k;
        p_Length = (unsigned __int16 *)v32;
        v33 = *((unsigned __int16 *)&off_140B7AB40 + 20 * k + 4);
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
          if ( !memcmp(Buf1, *(&off_140B7AB40 + v32), v33) )
          {
            v29 = (__int64)*(&off_140B7AB40 + (_QWORD)p_Length + 3);
            break;
          }
        }
        else
        {
          v30 += v33;
        }
      }
      if ( v29 && (v17 >= 0 || v17 == -1073741772 || v17 == -1073741275) )
        guard_dispatch_icall_no_overrides(v6, v42, v41);
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
0x140a03d98  push    rbx
0x140a03d9a  push    rsi
0x140a03d9b  push    rdi
0x140a03d9c  push    r12
0x140a03d9e  push    r13
0x140a03da0  push    r14
0x140a03da2  push    r15
0x140a03da4  sub     rsp, 1A0h
0x140a03dab  mov     rax, cs:__security_cookie
0x140a03db2  xor     rax, rsp
0x140a03db5  mov     [rsp+1D8h+var_48], rax
0x140a03dbd  mov     [rsp+1D8h+var_158], r9
0x140a03dc5  mov     [rsp+1D8h+var_150], r8
0x140a03dcd  mov     [rsp+1D8h+var_148], rdx
0x140a03dd5  mov     r13, rcx
0x140a03dd8  mov     [rsp+1D8h+var_108], rcx
0x140a03de0  mov     [rsp+1D8h+var_E0], rdx
0x140a03de8  mov     [rsp+1D8h+var_D8], rcx
0x140a03df0  mov     [rsp+1D8h+String1], rdx
0x140a03df8  mov     [rsp+1D8h+var_D0], r8
0x140a03e00  mov     [rsp+1D8h+var_100], r9
0x140a03e08  mov     rcx, [rsp+1D8h+arg_28]
0x140a03e10  mov     [rsp+1D8h+var_168], rcx
0x140a03e15  xor     edi, edi
0x140a03e17  mov     [rsp+1D8h+var_174], edi
0x140a03e1b  xorps   xmm0, xmm0
0x140a03e1e  movups  [rsp+1D8h+var_F8], xmm0
0x140a03e26  mov     [rsp+1D8h+var_178], dil
0x140a03e2b  mov     [rsp+1D8h+var_138], rdi
0x140a03e33  mov     [rsp+1D8h+P], rdi
0x140a03e3b  test    rdx, rdx
0x140a03e3e  jz      loc_140A044F2
0x140a03e44  test    rcx, rcx
0x140a03e47  jz      loc_140A044F2
0x140a03e4d  mov     ebx, edi
0x140a03e4f  mov     [rsp+1D8h+var_130], ebx
0x140a03e56  mov     [rsp+1D8h+var_174], ebx
0x140a03e5a  lea     rcx, [rdx+8]
0x140a03e5e  mov     [rsp+1D8h+var_118], rcx
0x140a03e66  cmp     [rcx], rdi
0x140a03e69  jz      loc_140A044F2
0x140a03e6f  lea     ecx, [rdi+2]
0x140a03e72  cmp     [rdx], cx
0x140a03e75  jb      loc_140A044F2
0x140a03e7b  lea     r14d, [rdi+1]
0x140a03e7f  mov     byte ptr [rsp+1D8h+var_F8], r14b
0x140a03e87  mov     qword ptr [rsp+1D8h+var_F8+8], rdx
0x140a03e8f  mov     rcx, r13
0x140a03e92  call    sub_1407E7B18
0x140a03e97  mov     [rsp+1D8h+var_16C], eax
0x140a03e9b  mov     [rsp+1D8h+var_140], rdi
0x140a03ea3  mov     r15b, dil
0x140a03ea6  mov     [rsp+1D8h+var_170], dil
0x140a03eab  mov     r9d, r14d
0x140a03eae  mov     [rsp+1D8h+var_160], r14d
0x140a03eb3  mov     esi, edi
0x140a03eb5  lea     rcx, off_140B7AB40
0x140a03ebc  cmp     esi, 0Eh
0x140a03ebf  jnb     loc_140A03F8A
0x140a03ec5  mov     eax, esi
0x140a03ec7  lea     r12, [rax+rax*4]
0x140a03ecb  movzx   r8d, word ptr [rcx+r12*8+8]; Size
0x140a03ed1  mov     rcx, qword ptr [rsp+1D8h+var_F8+8]
0x140a03ed9  movzx   eax, word ptr [rcx]
0x140a03edc  cmp     ax, r8w
0x140a03ee0  jnz     short loc_140A03F5A
0x140a03ee2  mov     r10d, eax
0x140a03ee5  shr     r10d, 1
0x140a03ee8  jz      short loc_140A03F37
0x140a03eea  mov     r11d, edi
0x140a03eed  mov     rax, [rcx+8]
0x140a03ef1  mov     rbx, rax
0x140a03ef4  mov     edx, r11d
0x140a03ef7  movzx   ecx, r9w
0x140a03efb  shl     cx, 8
0x140a03eff  lea     eax, [r14+r9]
0x140a03f03  or      cx, ax
0x140a03f06  or      cx, 5555h
0x140a03f0b  xor     cx, [rbx+rdx*2]
0x140a03f0f  mov     word ptr [rsp+rdx*2+1D8h+Buf1], cx
0x140a03f17  add     r9d, 2
0x140a03f1b  add     r11d, r14d
0x140a03f1e  cmp     r11d, r10d
0x140a03f21  jb      short loc_140A03EF4
0x140a03f23  mov     [rsp+1D8h+var_160], r9d
0x140a03f28  mov     ebx, [rsp+1D8h+var_130]
0x140a03f2f  mov     r13, [rsp+1D8h+var_108]
0x140a03f37  lea     rdx, off_140B7AB40
0x140a03f3e  mov     rdx, [rdx+r12*8]; Buf2
0x140a03f42  lea     rcx, [rsp+1D8h+Buf1]; Buf1
0x140a03f4a  call    memcmp
0x140a03f4f  test    eax, eax
0x140a03f51  jz      short loc_140A03F6A
0x140a03f53  mov     r9d, [rsp+1D8h+var_160]
0x140a03f58  jmp     short loc_140A03F62
0x140a03f5a  add     r9d, r8d
0x140a03f5d  mov     [rsp+1D8h+var_160], r9d
0x140a03f62  add     esi, r14d
0x140a03f65  jmp     loc_140A03EB5
0x140a03f6a  lea     rcx, off_140B7AB40
0x140a03f71  mov     r15b, [rcx+r12*8+20h]
0x140a03f76  mov     [rsp+1D8h+var_170], r15b
0x140a03f7b  mov     rax, [rcx+r12*8+10h]
0x140a03f80  mov     [rsp+1D8h+var_140], rax
0x140a03f88  jmp     short loc_140A03F8D
0x140a03f8a  mov     rax, rdi
0x140a03f8d  test    rax, rax
0x140a03f90  jz      loc_140A040C5
0x140a03f96  test    r15b, r15b
0x140a03f99  jz      short loc_140A03FF4
0x140a03f9b  call    KeEnterCriticalRegion
0x140a03fa0  lea     rsi, [r13+0B6F8h]
0x140a03fa7  xor     r8d, r8d
0x140a03faa  xor     edx, edx
0x140a03fac  mov     rcx, rsi
0x140a03faf  call    KeAbPreAcquire
0x140a03fb4  mov     rbx, rax
0x140a03fb7  xor     eax, eax
0x140a03fb9  lea     r12d, [rax+11h]
0x140a03fbd  lock cmpxchg [rsi], r12
0x140a03fc2  jz      short loc_140A03FD4
0x140a03fc4  mov     r9, rsi
0x140a03fc7  mov     r8, rbx
0x140a03fca  xor     edx, edx
0x140a03fcc  mov     rcx, rsi
0x140a03fcf  call    ExfAcquirePushLockSharedEx
0x140a03fd4  test    rbx, rbx
0x140a03fd7  jz      short loc_140A03FFC
0x140a03fd9  mov     eax, cs:?KiAbpGlobalState@@3UKI_AB_GLOBAL_STATE@@A; KI_AB_GLOBAL_STATE KiAbpGlobalState
0x140a03fdf  test    r14b, al
0x140a03fe2  jz      short loc_140A03FEE
0x140a03fe4  mov     rcx, rbx; this
0x140a03fe7  call    ?KiAbpPostAcquire@AutoBoost@@YAXPEAX@Z; AutoBoost::KiAbpPostAcquire(void *)
0x140a03fec  jmp     short loc_140A03FFC
0x140a03fee  mov     [rbx+0Ah], r14b
0x140a03ff2  jmp     short loc_140A03FFC
0x140a03ff4  mov     r12d, 11h
0x140a03ffa  jmp     short loc_140A04004
0x140a03ffc  mov     rax, [rsp+1D8h+var_140]
0x140a04004  lea     rcx, [rsp+1D8h+var_178]
0x140a04009  mov     [rsp+1D8h+var_1B0], rcx
0x140a0400e  mov     rcx, [rsp+1D8h+var_168]
0x140a04013  mov     [rsp+1D8h+var_1B8], rcx
0x140a04018  mov     r9d, [rsp+1D8h+arg_20]
0x140a04020  mov     r8, [rsp+1D8h+var_158]
0x140a04028  mov     rdx, [rsp+1D8h+var_150]
0x140a04030  mov     rcx, r13
0x140a04033  call    _guard_dispatch_icall_no_overrides
0x140a04038  mov     ebx, eax
0x140a0403a  mov     [rsp+1D8h+var_174], eax
0x140a0403e  jmp     short loc_140A0409A
0x140a04040  mov     ebx, eax
0x140a04042  mov     [rsp+1D8h+var_174], eax
0x140a04046  mov     [rsp+1D8h+var_178], 1
0x140a0404b  xor     edi, edi
0x140a0404d  lea     r14d, [rdi+1]
0x140a04051  lea     r12d, [rdi+11h]
0x140a04055  mov     [rsp+1D8h+var_138], rdi
0x140a0405d  mov     r15b, [rsp+1D8h+var_170]
0x140a04062  mov     rax, [rsp+1D8h+var_E0]
0x140a0406a  mov     [rsp+1D8h+var_148], rax
0x140a04072  mov     r13, [rsp+1D8h+var_D8]
0x140a0407a  mov     rax, [rsp+1D8h+var_D0]
0x140a04082  mov     [rsp+1D8h+var_150], rax
0x140a0408a  mov     rax, [rsp+1D8h+var_100]
0x140a04092  mov     [rsp+1D8h+var_158], rax
0x140a0409a  test    r15b, r15b
0x140a0409d  jz      short loc_140A040C5
0x140a0409f  lea     rsi, [r13+0B6F8h]
0x140a040a6  mov     rax, r12
0x140a040a9  lock cmpxchg [rsi], rdi
0x140a040ae  jz      short loc_140A040B8
0x140a040b0  mov     rcx, rsi
0x140a040b3  call    ExfReleasePushLockShared
0x140a040b8  mov     rcx, rsi; BugCheckParameter2
0x140a040bb  call    KeAbPostRelease
0x140a040c0  call    KeLeaveCriticalRegion
0x140a040c5  cmp     [rsp+1D8h+var_178], dil
0x140a040ca  jz      short loc_140A04101
0x140a040cc  test    ebx, ebx
0x140a040ce  js      short loc_140A040EA
0x140a040d0  mov     ecx, 0C0000023h
0x140a040d5  mov     eax, [rsp+1D8h+arg_20]
0x140a040dc  mov     rdx, [rsp+1D8h+var_168]
0x140a040e1  cmp     [rdx], eax
0x140a040e3  cmova   ebx, ecx
0x140a040e6  mov     [rsp+1D8h+var_174], ebx
0x140a040ea  jmp     short loc_140A040FC
0x140a040ec  mov     ebx, eax
0x140a040ee  mov     [rsp+1D8h+var_174], eax
0x140a040f2  xor     edi, edi
0x140a040f4  mov     [rsp+1D8h+var_138], rdi
0x140a040fc  jmp     loc_140A044FB
0x140a04101  mov     ebx, [rsp+1D8h+var_16C]
0x140a04105  test    ebx, ebx
0x140a04107  js      loc_140A044F7
0x140a0410d  mov     r12b, r14b
0x140a04110  mov     [rsp+1D8h+var_174], edi
0x140a04114  mov     [rsp+1D8h+var_160], edi
0x140a04118  lea     rax, [rsp+1D8h+var_16C]
0x140a0411d  mov     [rsp+1D8h+var_1B0], rax
0x140a04122  mov     dword ptr [rsp+1D8h+var_1B8], 4
0x140a0412a  lea     r9, [rsp+1D8h+var_160]
0x140a0412f  xor     r8d, r8d
0x140a04132  lea     rdx, qword_140B7B588
0x140a04139  mov     rcx, r13
0x140a0413c  call    sub_1404CFB80
0x140a04141  mov     ebx, eax
0x140a04143  mov     [rsp+1D8h+var_174], eax
0x140a04147  cmp     cs:qword_140FDA368, 0
0x140a0414f  jz      loc_140A04302
0x140a04155  cmp     [rsp+1D8h+var_160], edi
0x140a04159  jz      loc_140A04302
0x140a0415f  xor     r8d, r8d; CaseInSensitive
0x140a04162  lea     rdx, stru_140B7B578; String2
0x140a04169  mov     rcx, [rsp+1D8h+String1]; String1
0x140a04171  call    RtlEqualUnicodeString
0x140a04176  test    al, al
0x140a04178  jnz     loc_140A04302
0x140a0417e  mov     rsi, [rsp+1D8h+var_148]
0x140a04186  movzx   eax, word ptr [rsi]
0x140a04189  add     eax, 2
0x140a0418c  mov     [rsp+1D8h+var_16C], eax
0x140a04190  mov     edx, eax
0x140a04192  mov     ecx, 100h
0x140a04197  mov     r8d, 20534C53h
0x140a0419d  call    ExAllocatePool2
0x140a041a2  mov     r15, rax
0x140a041a5  mov     [rsp+1D8h+var_138], rax
0x140a041ad  test    rax, rax
0x140a041b0  jnz     short loc_140A041BC
0x140a041b2  mov     ebx, 0C0000017h
0x140a041b7  jmp     loc_140A044F7
0x140a041bc  movzx   r8d, word ptr [rsi]; Size
0x140a041c0  mov     rdx, [rsp+1D8h+var_118]
0x140a041c8  mov     rdx, [rdx]; Src
0x140a041cb  mov     rcx, r15; void *
0x140a041ce  call    memmove
0x140a041d3  lea     rax, aSecuritySppGen_0; "Security-SPP-GenuineLocalStatus"
0x140a041da  mov     [rsp+1D8h+Buf1], rax
0x140a041e2  lea     rax, aSecuritySppAct; "Security-SPP-Action-StateData"
0x140a041e9  mov     [rsp+1D8h+var_B0], rax
0x140a041f1  lea     rax, aSecuritySppLas_0; "Security-SPP-LastWindowsActivationHResu"...
0x140a041f8  mov     [rsp+1D8h+var_A8], rax
0x140a04200  lea     rax, aSecuritySppLas; "Security-SPP-LastWindowsActivationTime"
0x140a04207  mov     [rsp+1D8h+var_A0], rax
0x140a0420f  lea     rax, aKernelExpirati_0; "Kernel-ExpirationDate"
0x140a04216  mov     [rsp+1D8h+var_98], rax
0x140a0421e  lea     rax, aSmrHostmanaged; "SMR-HostManaged-Enabled"
0x140a04225  mov     [rsp+1D8h+var_90], rax
0x140a0422d  lea     rax, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x140a04234  mov     [rsp+1D8h+var_88], rax
0x140a0423c  mov     esi, edi
0x140a0423e  mov     eax, edi
0x140a04240  cmp     esi, 7
0x140a04243  jnb     short loc_140A04263
0x140a04245  mov     edx, esi
0x140a04247  mov     rdx, [rsp+rdx*8+1D8h+Buf1]; Str2
0x140a0424f  mov     rcx, r15; Str1
0x140a04252  call    _wcsicmp
0x140a04257  test    eax, eax
0x140a04259  jz      short loc_140A04260
0x140a0425b  add     esi, r14d
0x140a0425e  jmp     short loc_140A0423E
0x140a04260  mov     eax, r14d
0x140a04263  test    eax, eax
0x140a04265  jnz     loc_140A04302
0x140a0426b  lea     rdx, [rsp+1D8h+P]
0x140a04273  mov     rcx, r13
0x140a04276  call    SLGetSubscriptionPfn
0x140a0427b  mov     rax, cs:qword_140FDA368
0x140a04282  mov     [rsp+1D8h+var_188], rdi
0x140a04287  mov     rcx, [rsp+1D8h+var_150]
0x140a0428f  mov     [rsp+1D8h+var_190], rcx
0x140a04294  mov     rsi, [rsp+1D8h+var_168]
0x140a04299  mov     [rsp+1D8h+var_198], rsi
0x140a0429e  mov     ecx, [rsp+1D8h+arg_20]
0x140a042a5  mov     [rsp+1D8h+var_1A0], ecx
0x140a042a9  mov     rcx, [rsp+1D8h+var_158]
0x140a042b1  mov     [rsp+1D8h+var_1A8], rcx
0x140a042b6  mov     ecx, [rsp+1D8h+var_16C]
0x140a042ba  mov     dword ptr [rsp+1D8h+var_1B0], ecx
0x140a042be  mov     [rsp+1D8h+var_1B8], r15
0x140a042c3  xor     r9d, r9d
0x140a042c6  xor     r8d, r8d
0x140a042c9  xor     edx, edx
0x140a042cb  mov     rcx, [rsp+1D8h+P]
0x140a042d3  call    _guard_dispatch_icall_no_overrides
0x140a042d8  mov     edx, 80000000h
0x140a042dd  lea     ecx, [rax+rdx]
0x140a042e0  test    edx, ecx
0x140a042e2  mov     ecx, 0C0000023h
0x140a042e7  jnz     short loc_140A042ED
0x140a042e9  cmp     eax, ecx
0x140a042eb  jnz     short loc_140A04307
0x140a042ed  mov     ebx, eax
0x140a042ef  cmp     [rsp+1D8h+arg_20], edi
0x140a042f6  cmovz   ebx, ecx
0x140a042f9  mov     [rsp+1D8h+var_174], ebx
0x140a042fd  mov     r12b, dil
  ... truncated ...
```
