# QuicLibrarySetGlobalParam

- ea: `0x14003f350`
- end: `0x14003f9ac`
- name: `QuicLibrarySetGlobalParam`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400018a0`

## callees

- `0x140005f0c`
- `0x14002430c`
- `0x14002443c`
- `0x14002854c`
- `0x140028ce4`
- `0x140028ee0`
- `0x14002bfd8`
- `0x14002caf0`
- `0x14002cb4c`
- `0x14002d09c`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ead8`
- `0x14003ed00`
- `0x14003f350`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003f3f7`
- `ntoskrnl!_snprintf_s` at `0x14003f494`
- `ntoskrnl!_snprintf_s` at `0x14003f519`
- `ntoskrnl!_snprintf_s` at `0x14003f594`
- `ntoskrnl!_snprintf_s` at `0x14003f5fb`
- `ntoskrnl!_snprintf_s` at `0x14003f65a`
- `ntoskrnl!_snprintf_s` at `0x14003f835`
- `ntoskrnl!_snprintf_s` at `0x14003f3f7`
- `ntoskrnl!_snprintf_s` at `0x14003f494`
- `ntoskrnl!_snprintf_s` at `0x14003f519`
- `ntoskrnl!_snprintf_s` at `0x14003f594`
- `ntoskrnl!_snprintf_s` at `0x14003f5fb`
- `ntoskrnl!_snprintf_s` at `0x14003f65a`
- `ntoskrnl!_snprintf_s` at `0x14003f835`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f733`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f733`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f74b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f74b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f767`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f7fc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f767`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f7fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f6c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f7d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f6c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f7d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f773`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f808`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f773`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f808`
- `ntoskrnl!ExAllocatePool2` at `0x14003f792`
- `ntoskrnl!ExAllocatePool2` at `0x14003f792`

## string_xrefs

- `0x14003f647`: `[ lib] Updated retry memory limit = %hu`
- `0x14003f5e3`: `[ lib] Updated load balancing mode = %hu`
- `0x14003f7b2`: `Execution config`
- `0x14003f821`: `[ lib] Setting execution config`

## pseudocode

```c
__int64 __fastcall QuicLibrarySetGlobalParam(unsigned int a1, unsigned int a2, unsigned __int16 *a3)
{
  size_t v4; // r15
  __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int updated; // ebx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int16 v21; // ax
  __int64 v22; // rcx
  int v23; // eax
  const char *v24; // r9
  __int64 v25; // rcx
  int v26; // ecx
  __int64 v27; // rcx
  __int64 v29; // rcx
  unsigned int v30; // r8d
  unsigned __int16 *v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  void *Pool2; // rsi
  unsigned __int8 v35; // cl
  unsigned __int16 i; // r15
  char v37[144]; // [rsp+30h] [rbp-D0h] BYREF
  char DstBuf[128]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = a2;
  memset(v37, 0, sizeof(v37));
  if ( a1 > 0x1000009 )
  {
    switch ( a1 )
    {
      case 0x100000Bu:
        if ( (MsQuicLib & 2) != 0 )
        {
          if ( (_DWORD)v4 == 32 )
          {
            updated = 0;
            for ( i = 0; i < (unsigned __int16)word_14005C55C; ++i )
            {
              updated = QuicPartitionUpdateStatelessResetKey((char *)Val + 2496 * i, v6, a3);
              if ( (updated & 0x80000000) != 0 )
                break;
            }
            return updated;
          }
          return (unsigned int)-1073741811;
        }
        return (unsigned int)-1073741436;
      case 0x100000Du:
        if ( a3 && (unsigned int)v4 >= 0x18 )
          return (unsigned int)QuicLibrarySetRetryKeyConfig(a3);
        return (unsigned int)-1073741811;
      case 0x81000003:
        if ( !a3 || !(_DWORD)v4 )
          return (unsigned int)-1073741811;
        qword_14005C4B0 |= 0x80000000uLL;
        byte_14005C53B = byte_14005C53B & 0xBF | ((*(_BYTE *)a3 & 1) << 6);
        return 0;
    }
    if ( a1 != -2130706425 || (_DWORD)v4 != 1 || !a3 )
      return (unsigned int)-1073741811;
    if ( (MsQuicLib & 2) != 0 )
      return (unsigned int)-1073741436;
    v35 = MsQuicLib & 0xEF | (16 * (*(_BYTE *)a3 & 1));
    MsQuicLib = v35;
    if ( (byte_14005C48E & 0x40) != 0 )
    {
      v24 = "[ lib] Setting Dscp on recv = %u";
      v23 = (v35 >> 4) & 1;
      goto LABEL_36;
    }
    return 0;
  }
  if ( a1 != 16777225 )
  {
    v7 = a1 - 0x1000000;
    if ( !v7 )
    {
      if ( (_DWORD)v4 != 2 )
        return (unsigned int)-1073741811;
      v26 = *a3;
      qword_14005C4B0 |= 0x200000uLL;
      word_14005C52C = v26;
      if ( (byte_14005C48E & 0x40) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Updated retry memory limit = %hu", v26);
        McTemplateU0s_EtwWriteTransfer(v27, QuicLogInfo, DstBuf);
      }
      qword_14005C570 = CxPlatTotalMemory * (unsigned __int64)(unsigned __int16)word_14005C52C / 0xFFFF;
      QuicLibraryEvaluateSendRetryState();
      return 0;
    }
    v8 = v7 - 2;
    if ( v8 )
    {
      v9 = v8 - 3;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 || !a3 )
            return (unsigned int)-1073741811;
          if ( (byte_14005C48E & 0x40) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Setting new settings");
            McTemplateU0s_EtwWriteTransfer(v11, QuicLogInfo, DstBuf);
          }
          updated = QuicSettingsVersionSettingsToInternal((unsigned int)v4, a3, v37);
          if ( (updated & 0x80000000) != 0 )
            return updated;
          LOBYTE(v14) = 1;
          LOBYTE(v12) = 1;
          if ( !(unsigned __int8)QuicSettingApply(&qword_14005C4B0, v12, v14, v37) )
          {
            QuicSettingsCleanup(v37);
            return (unsigned int)-1073741811;
          }
          QuicSettingsCleanup(v37);
          goto LABEL_15;
        }
        if ( !a3 )
          return (unsigned int)-1073741811;
        if ( (byte_14005C48E & 0x40) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Setting new settings");
          McTemplateU0s_EtwWriteTransfer(v16, QuicLogInfo, DstBuf);
        }
        v17 = QuicSettingsGlobalSettingsToInternal((unsigned int)v4, a3, v37);
      }
      else
      {
        if ( !a3 )
          return (unsigned int)-1073741811;
        if ( (byte_14005C48E & 0x40) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Setting new settings");
          McTemplateU0s_EtwWriteTransfer(v20, QuicLogInfo, DstBuf);
        }
        v17 = QuicSettingsSettingsToInternal((unsigned int)v4, a3, v37);
      }
      updated = v17;
      if ( v17 < 0 )
        return updated;
      LOBYTE(v19) = 1;
      LOBYTE(v18) = 1;
      if ( !(unsigned __int8)QuicSettingApply(&qword_14005C4B0, v18, v19, v37) )
        return (unsigned int)-1073741811;
LABEL_15:
      LOBYTE(v15) = 1;
      MsQuicLibraryOnSettingsChanged(v15);
      return updated;
    }
    if ( (_DWORD)v4 != 2 )
      return (unsigned int)-1073741811;
    v21 = *a3;
    if ( *a3 > 1u )
      return (unsigned int)-1073741811;
    if ( byte_14005C491 && word_14005C52E != v21 )
    {
      if ( (byte_14005C48E & 0x10) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "[ lib] Tried to change load balancing mode after library in use!");
        McTemplateU0s_EtwWriteTransfer(v22, QuicLogError, DstBuf);
      }
      return (unsigned int)-1073741436;
    }
    qword_14005C4B0 |= 0x400000uLL;
    word_14005C52E = v21;
    QuicLibApplyLoadBalancingSetting();
    if ( (byte_14005C48E & 0x40) != 0 )
    {
      v23 = (unsigned __int16)word_14005C52E;
      v24 = "[ lib] Updated load balancing mode = %hu";
LABEL_36:
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v24, v23);
LABEL_37:
      McTemplateU0s_EtwWriteTransfer(v25, QuicLogInfo, DstBuf);
      return 0;
    }
    return 0;
  }
  if ( (_DWORD)v4 )
  {
    if ( a3 )
    {
      if ( (unsigned int)v4 >= 0xC )
      {
        v29 = *((unsigned int *)a3 + 2);
        if ( v4 >= 2 * v29 + 12 )
        {
          v30 = 0;
          if ( !(_DWORD)v29 )
          {
LABEL_54:
            KeEnterCriticalRegion();
            ExAcquirePushLockExclusiveEx(&PushLock, 0);
            if ( (MsQuicLib & 2) != 0 )
            {
              updated = 0;
            }
            else
            {
              Pool2 = (void *)ExAllocatePool2(66, v4, 1127506769);
              if ( Pool2 )
              {
                if ( P )
                  ExFreePoolWithTag(P, 0x43346351u);
                memmove(Pool2, a3, v4);
                P = Pool2;
                ExReleasePushLockExclusiveEx(&PushLock, 0);
                KeLeaveCriticalRegion();
                if ( (byte_14005C48E & 0x40) == 0 )
                  return 0;
                _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Setting execution config");
                goto LABEL_37;
              }
              if ( (Microsoft_QuicEnableBits & 2) != 0 )
                McTemplateU0sx_EtwWriteTransfer(v33, v32, "Execution config", v4);
              updated = -1073741801;
            }
            ExReleasePushLockExclusiveEx(&PushLock, 0);
            KeLeaveCriticalRegion();
            return updated;
          }
          v31 = a3 + 6;
          while ( *v31 < (unsigned int)CxPlatProcessorCount )
          {
            ++v30;
            ++v31;
            if ( v30 >= (unsigned int)v29 )
              goto LABEL_54;
          }
        }
      }
    }
    return 3221225485LL;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0x43346351u);
    P = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14003f350  mov     [rsp-8+arg_0], rbx
0x14003f355  push    rbp
0x14003f356  push    rsi
0x14003f357  push    rdi
0x14003f358  push    r14
0x14003f35a  push    r15
0x14003f35c  lea     rbp, [rsp-50h]
0x14003f361  sub     rsp, 150h
0x14003f368  mov     rax, cs:__security_cookie
0x14003f36f  xor     rax, rsp
0x14003f372  mov     [rbp+70h+var_30], rax
0x14003f376  mov     r14, r8
0x14003f379  mov     r15d, edx
0x14003f37c  mov     ebx, ecx
0x14003f37e  xor     edx, edx; Val
0x14003f380  mov     r8d, 90h; Size
0x14003f386  lea     rcx, [rsp+170h+var_140]; void *
0x14003f38b  call    memset
0x14003f390  mov     eax, 1000009h
0x14003f395  cmp     ebx, eax
0x14003f397  ja      loc_14003F850
0x14003f39d  jz      loc_14003F6AB
0x14003f3a3  sub     ebx, 1000000h
0x14003f3a9  jz      loc_14003F61C
0x14003f3af  sub     ebx, 2
0x14003f3b2  jz      loc_14003F54A
0x14003f3b8  sub     ebx, 3
0x14003f3bb  jz      loc_14003F4F3
0x14003f3c1  sub     ebx, 1
0x14003f3c4  jz      loc_14003F46E
0x14003f3ca  cmp     ebx, 1
0x14003f3cd  jnz     loc_14003F878
0x14003f3d3  test    r14, r14
0x14003f3d6  jz      loc_14003F878
0x14003f3dc  test    cs:byte_14005C48E, 40h
0x14003f3e3  jz      short loc_14003F413
0x14003f3e5  lea     r9, aLibSettingNewS; "[ lib] Setting new settings"
0x14003f3ec  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f3f0  lea     edx, [rbx+7Fh]; SizeInBytes
0x14003f3f3  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f3f7  call    cs:__imp__snprintf_s
0x14003f3fe  nop     dword ptr [rax+rax+00h]
0x14003f403  lea     r8, [rbp+70h+DstBuf]
0x14003f407  lea     rdx, QuicLogInfo
0x14003f40e  call    McTemplateU0s_EtwWriteTransfer
0x14003f413  lea     r8, [rsp+170h+var_140]
0x14003f418  mov     rdx, r14
0x14003f41b  mov     ecx, r15d
0x14003f41e  call    QuicSettingsVersionSettingsToInternal
0x14003f423  mov     ebx, eax
0x14003f425  test    eax, eax
0x14003f427  js      loc_14003F986
0x14003f42d  mov     esi, 1
0x14003f432  lea     r9, [rsp+170h+var_140]
0x14003f437  mov     r8b, sil
0x14003f43a  lea     rcx, qword_14005C4B0
0x14003f441  mov     dl, sil
0x14003f444  call    QuicSettingApply
0x14003f449  lea     rcx, [rsp+170h+var_140]
0x14003f44e  test    al, al
0x14003f450  jnz     short loc_14003F45C
0x14003f452  call    QuicSettingsCleanup
0x14003f457  jmp     loc_14003F878
0x14003f45c  call    QuicSettingsCleanup
0x14003f461  mov     cl, sil
0x14003f464  call    MsQuicLibraryOnSettingsChanged
0x14003f469  jmp     loc_14003F986
0x14003f46e  test    r14, r14
0x14003f471  jz      loc_14003F878
0x14003f477  test    cs:byte_14005C48E, 40h
0x14003f47e  jz      short loc_14003F4B0
0x14003f480  lea     r9, aLibSettingNewS; "[ lib] Setting new settings"
0x14003f487  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f48b  mov     edx, 80h; SizeInBytes
0x14003f490  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f494  call    cs:__imp__snprintf_s
0x14003f49b  nop     dword ptr [rax+rax+00h]
0x14003f4a0  lea     r8, [rbp+70h+DstBuf]
0x14003f4a4  lea     rdx, QuicLogInfo
0x14003f4ab  call    McTemplateU0s_EtwWriteTransfer
0x14003f4b0  lea     r8, [rsp+170h+var_140]
0x14003f4b5  mov     rdx, r14
0x14003f4b8  mov     ecx, r15d
0x14003f4bb  call    QuicSettingsGlobalSettingsToInternal
0x14003f4c0  mov     ebx, eax
0x14003f4c2  test    eax, eax
0x14003f4c4  js      loc_14003F986
0x14003f4ca  mov     esi, 1
0x14003f4cf  lea     r9, [rsp+170h+var_140]
0x14003f4d4  mov     r8b, sil
0x14003f4d7  lea     rcx, qword_14005C4B0
0x14003f4de  mov     dl, sil
0x14003f4e1  call    QuicSettingApply
0x14003f4e6  test    al, al
0x14003f4e8  jnz     loc_14003F461
0x14003f4ee  jmp     loc_14003F878
0x14003f4f3  test    r14, r14
0x14003f4f6  jz      loc_14003F878
0x14003f4fc  test    cs:byte_14005C48E, 40h
0x14003f503  jz      short loc_14003F535
0x14003f505  lea     r9, aLibSettingNewS; "[ lib] Setting new settings"
0x14003f50c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f510  mov     edx, 80h; SizeInBytes
0x14003f515  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f519  call    cs:__imp__snprintf_s
0x14003f520  nop     dword ptr [rax+rax+00h]
0x14003f525  lea     r8, [rbp+70h+DstBuf]
0x14003f529  lea     rdx, QuicLogInfo
0x14003f530  call    McTemplateU0s_EtwWriteTransfer
0x14003f535  lea     r8, [rsp+170h+var_140]
0x14003f53a  mov     rdx, r14
0x14003f53d  mov     ecx, r15d
0x14003f540  call    QuicSettingsSettingsToInternal
0x14003f545  jmp     loc_14003F4C0
0x14003f54a  cmp     r15d, 2
0x14003f54e  jnz     loc_14003F878
0x14003f554  movzx   eax, word ptr [r14]
0x14003f558  lea     esi, [r15-1]
0x14003f55c  cmp     ax, si
0x14003f55f  ja      loc_14003F878
0x14003f565  xor     edi, edi
0x14003f567  cmp     cs:byte_14005C491, dil
0x14003f56e  jz      short loc_14003F5BA
0x14003f570  cmp     cs:word_14005C52E, ax
0x14003f577  jz      short loc_14003F5BA
0x14003f579  test    cs:byte_14005C48E, 10h
0x14003f580  jz      short loc_14003F5B0
0x14003f582  lea     r9, aLibTriedToChan; "[ lib] Tried to change load balancing m"...
0x14003f589  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f58d  lea     edx, [rsi+7Fh]; SizeInBytes
0x14003f590  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f594  call    cs:__imp__snprintf_s
0x14003f59b  nop     dword ptr [rax+rax+00h]
0x14003f5a0  lea     r8, [rbp+70h+DstBuf]
0x14003f5a4  lea     rdx, QuicLogError
0x14003f5ab  call    McTemplateU0s_EtwWriteTransfer
0x14003f5b0  mov     ebx, 0C0000184h
0x14003f5b5  jmp     loc_14003F986
0x14003f5ba  bts     cs:qword_14005C4B0, 16h
0x14003f5c3  mov     cs:word_14005C52E, ax
0x14003f5ca  call    QuicLibApplyLoadBalancingSetting
0x14003f5cf  test    cs:byte_14005C48E, 40h
0x14003f5d6  jz      loc_14003F6A4
0x14003f5dc  movzx   eax, cs:word_14005C52E
0x14003f5e3  lea     r9, aLibUpdatedLoad; "[ lib] Updated load balancing mode = %h"...
0x14003f5ea  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f5ee  mov     [rsp+170h+var_150], eax
0x14003f5f2  mov     edx, 80h; SizeInBytes
0x14003f5f7  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f5fb  call    cs:__imp__snprintf_s
0x14003f602  nop     dword ptr [rax+rax+00h]
0x14003f607  lea     r8, [rbp+70h+DstBuf]
0x14003f60b  lea     rdx, QuicLogInfo
0x14003f612  call    McTemplateU0s_EtwWriteTransfer
0x14003f617  jmp     loc_14003F6A4
0x14003f61c  cmp     r15d, 2
0x14003f620  jnz     loc_14003F878
0x14003f626  movzx   ecx, word ptr [r14]
0x14003f62a  bts     cs:qword_14005C4B0, 15h
0x14003f633  test    cs:byte_14005C48E, 40h
0x14003f63a  mov     cs:word_14005C52C, cx
0x14003f641  jz      short loc_14003F676
0x14003f643  mov     [rsp+170h+var_150], ecx
0x14003f647  lea     r9, aLibUpdatedRetr; "[ lib] Updated retry memory limit = %hu"
0x14003f64e  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f652  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f656  lea     edx, [r15+7Eh]; SizeInBytes
0x14003f65a  call    cs:__imp__snprintf_s
0x14003f661  nop     dword ptr [rax+rax+00h]
0x14003f666  lea     r8, [rbp+70h+DstBuf]
0x14003f66a  lea     rdx, QuicLogInfo
0x14003f671  call    McTemplateU0s_EtwWriteTransfer
0x14003f676  movzx   ecx, cs:word_14005C52C
0x14003f67d  mov     rax, 8000800080008001h
0x14003f687  imul    rcx, cs:CxPlatTotalMemory
0x14003f68f  mul     rcx
0x14003f692  shr     rdx, 0Fh
0x14003f696  mov     cs:qword_14005C570, rdx
0x14003f69d  call    QuicLibraryEvaluateSendRetryState
0x14003f6a2  xor     edi, edi
0x14003f6a4  mov     ebx, edi
0x14003f6a6  jmp     loc_14003F986
0x14003f6ab  xor     edi, edi
0x14003f6ad  test    r15d, r15d
0x14003f6b0  jnz     short loc_14003F6DD
0x14003f6b2  mov     rcx, cs:P; P
0x14003f6b9  test    rcx, rcx
0x14003f6bc  jz      short loc_14003F6D6
0x14003f6be  mov     edx, 43346351h; Tag
0x14003f6c3  call    cs:__imp_ExFreePoolWithTag
0x14003f6ca  nop     dword ptr [rax+rax+00h]
0x14003f6cf  mov     cs:P, rdi
0x14003f6d6  xor     eax, eax
0x14003f6d8  jmp     loc_14003F988
0x14003f6dd  test    r14, r14
0x14003f6e0  jz      loc_14003F846
0x14003f6e6  cmp     r15d, 0Ch
0x14003f6ea  jb      loc_14003F846
0x14003f6f0  mov     ecx, [r14+8]
0x14003f6f4  mov     rbx, r15
0x14003f6f7  lea     rax, ds:0Ch[rcx*2]
0x14003f6ff  cmp     r15, rax
0x14003f702  jb      loc_14003F846
0x14003f708  mov     r8d, edi
0x14003f70b  test    ecx, ecx
0x14003f70d  jz      short loc_14003F733
0x14003f70f  lea     rdx, [r14+0Ch]
0x14003f713  mov     esi, 1
0x14003f718  movzx   eax, word ptr [rdx]
0x14003f71b  cmp     eax, cs:CxPlatProcessorCount
0x14003f721  jnb     loc_14003F846
0x14003f727  add     r8d, esi
0x14003f72a  add     rdx, 2
0x14003f72e  cmp     r8d, ecx
0x14003f731  jb      short loc_14003F718
0x14003f733  call    cs:__imp_KeEnterCriticalRegion
0x14003f73a  nop     dword ptr [rax+rax+00h]
0x14003f73f  lea     r15, PushLock
0x14003f746  xor     edx, edx
0x14003f748  mov     rcx, r15
0x14003f74b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f752  nop     dword ptr [rax+rax+00h]
0x14003f757  test    cs:MsQuicLib, 2
0x14003f75e  jz      short loc_14003F784
0x14003f760  mov     ebx, edi
0x14003f762  xor     edx, edx
0x14003f764  mov     rcx, r15
0x14003f767  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f76e  nop     dword ptr [rax+rax+00h]
0x14003f773  call    cs:__imp_KeLeaveCriticalRegion
0x14003f77a  nop     dword ptr [rax+rax+00h]
0x14003f77f  jmp     loc_14003F986
0x14003f784  mov     r8d, 43346351h
0x14003f78a  mov     rdx, rbx
0x14003f78d  mov     ecx, 42h ; 'B'
0x14003f792  call    cs:__imp_ExAllocatePool2
0x14003f799  nop     dword ptr [rax+rax+00h]
0x14003f79e  mov     rsi, rax
0x14003f7a1  test    rax, rax
0x14003f7a4  jnz     short loc_14003F7C5
0x14003f7a6  test    cs:Microsoft_QuicEnableBits, 2
0x14003f7ad  jz      short loc_14003F7BE
0x14003f7af  mov     r9, rbx
0x14003f7b2  lea     r8, aExecutionConfi; "Execution config"
0x14003f7b9  call    McTemplateU0sx_EtwWriteTransfer
0x14003f7be  mov     ebx, 0C0000017h
0x14003f7c3  jmp     short loc_14003F762
0x14003f7c5  mov     rcx, cs:P; P
0x14003f7cc  test    rcx, rcx
0x14003f7cf  jz      short loc_14003F7E2
0x14003f7d1  mov     edx, 43346351h; Tag
0x14003f7d6  call    cs:__imp_ExFreePoolWithTag
0x14003f7dd  nop     dword ptr [rax+rax+00h]
0x14003f7e2  mov     r8, rbx; Size
0x14003f7e5  mov     rdx, r14; Src
0x14003f7e8  mov     rcx, rsi; void *
0x14003f7eb  call    memmove
0x14003f7f0  xor     edx, edx
0x14003f7f2  mov     cs:P, rsi
0x14003f7f9  mov     rcx, r15
0x14003f7fc  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f803  nop     dword ptr [rax+rax+00h]
0x14003f808  call    cs:__imp_KeLeaveCriticalRegion
0x14003f80f  nop     dword ptr [rax+rax+00h]
0x14003f814  test    cs:byte_14005C48E, 40h
0x14003f81b  jz      loc_14003F6A4
0x14003f821  lea     r9, aLibSettingExec; "[ lib] Setting execution config"
0x14003f828  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f82c  mov     edx, 80h; SizeInBytes
0x14003f831  lea     rcx, [rbp+70h+DstBuf]; DstBuf
0x14003f835  call    cs:__imp__snprintf_s
0x14003f83c  nop     dword ptr [rax+rax+00h]
0x14003f841  jmp     loc_14003F607
0x14003f846  mov     eax, 0C000000Dh
0x14003f84b  jmp     loc_14003F988
0x14003f850  cmp     ebx, 100000Bh
0x14003f856  jz      loc_14003F92D
0x14003f85c  cmp     ebx, 100000Dh
0x14003f862  jz      loc_14003F90E
0x14003f868  cmp     ebx, 81000003h
0x14003f86e  jz      short loc_14003F8D5
0x14003f870  cmp     ebx, 81000007h
0x14003f876  jz      short loc_14003F882
0x14003f878  mov     ebx, 0C000000Dh
0x14003f87d  jmp     loc_14003F986
0x14003f882  mov     esi, 1
0x14003f887  cmp     r15d, esi
0x14003f88a  jnz     short loc_14003F878
0x14003f88c  xor     edi, edi
0x14003f88e  test    r14, r14
0x14003f891  jz      short loc_14003F878
0x14003f893  mov     al, cs:MsQuicLib
0x14003f899  test    al, 2
0x14003f89b  jnz     loc_14003F5B0
0x14003f8a1  mov     cl, [r14]
0x14003f8a4  and     al, 0EFh
0x14003f8a6  and     cl, sil
0x14003f8a9  shl     cl, 4
0x14003f8ac  or      cl, al
0x14003f8ae  test    cs:byte_14005C48E, 40h
  ... truncated ...
```
