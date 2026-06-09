# DdmDevice::AcceptReauthentication(RasObjPtr<DdmConnection> &)

- ea: `0x18002fb40`
- end: `0x180030148`
- name: `?AcceptReauthentication@DdmDevice@@UEAAHAEAV?$RasObjPtr@VDdmConnection@@@@@Z`
- size: `1544`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007c50`
- `0x18002ce44`
- `0x18002fb40`
- `0x18003197c`
- `0x180031b88`
- `0x180031d54`
- `0x180031ef0`
- `0x180032a88`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18002fca9`
- `msvcrt!_itow_s` at `0x18002fda0`
- `msvcrt!_itow_s` at `0x18002ff9d`
- `msvcrt!_itow_s` at `0x180030024`
- `msvcrt!_itow_s` at `0x180030083`
- `msvcrt!_itow_s` at `0x18002fca9`
- `msvcrt!_itow_s` at `0x18002fda0`
- `msvcrt!_itow_s` at `0x18002ff9d`
- `msvcrt!_itow_s` at `0x180030024`
- `msvcrt!_itow_s` at `0x180030083`
- `msvcrt!_wcsicmp` at `0x18002ff0d`
- `msvcrt!_wcsicmp` at `0x18002ff0d`
- `KERNEL32!LeaveCriticalSection` at `0x180030116`
- `KERNEL32!LeaveCriticalSection` at `0x180030116`
- `KERNEL32!EnterCriticalSection` at `0x18002fc40`
- `KERNEL32!EnterCriticalSection` at `0x18002fc40`

## string_xrefs

- `0x18002fccd`: `AcceptReauthentication: Skipping version 1 Admin Dll callback for IKEv2 connection`
- `0x18002fda6`: `AcceptReauthenticationEx failed for Admin Dll with index %d`
- `0x180030089`: `AcceptReauthentication: failed for Admin Dll with index %d`

## pseudocode

```c
__int64 __fastcall DdmDevice::AcceptReauthentication(__int64 a1, DdmConnection **a2)
{
  unsigned int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  unsigned int v6; // r12d
  int v7; // r13d
  char *v8; // r15
  __int64 v9; // r14
  int v10; // ecx
  DdmConnection *v11; // rax
  int v12; // ecx
  unsigned int i; // esi
  __int64 v14; // rcx
  void (__fastcall *v15)(_DWORD *); // rax
  DdmConnection *v16; // rax
  DdmConnection *v17; // rax
  DdmConnection *v18; // rax
  DdmConnection *v19; // rax
  unsigned int (__fastcall *v20)(_BYTE *, _BYTE *, _BYTE *, _BYTE *); // rax
  char v21; // dl
  int v22; // ecx
  const wchar_t *v23; // r8
  char v24; // dl
  int v25; // ecx
  int v26; // ecx
  void (__fastcall *v27)(_BYTE *, _BYTE *, _BYTE *, _BYTE *); // rax
  void (__fastcall *v28)(_BYTE *, _BYTE *, _BYTE *); // rax
  void (__fastcall *v29)(_BYTE *, _BYTE *); // rax
  DdmConnection *v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+38h] [rbp-C8h]
  int v33; // [rsp+3Ch] [rbp-C4h]
  __int128 v34; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[304]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[542]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t String1[297]; // [rsp+39Eh] [rbp+29Eh] BYREF
  _BYTE v38[800]; // [rsp+5F0h] [rbp+4F0h] BYREF
  _BYTE v39[848]; // [rsp+910h] [rbp+810h] BYREF
  _DWORD v40[420]; // [rsp+C60h] [rbp+B60h] BYREF
  wchar_t Buffer[2]; // [rsp+12F0h] [rbp+11F0h] BYREF
  __int128 v42; // [rsp+12F4h] [rbp+11F4h]
  __int128 v43; // [rsp+1304h] [rbp+1204h]
  int v44; // [rsp+1314h] [rbp+1214h]
  int v45; // [rsp+1320h] [rbp+1220h] BYREF
  _BYTE v46[2044]; // [rsp+1324h] [rbp+1224h] BYREF

  v33 = *(unsigned __int16 *)(a1 + 136);
  v4 = 1;
  v32 = 1;
  memset_0(v36, 0, 0x468u);
  memset_0(v35, 0, 0x128u);
  memset_0(v39, 0, sizeof(v39));
  memset_0(v38, 0, 0x318u);
  LOBYTE(v40[0]) = 0;
  memset_0((char *)v40 + 1, 0, 0x687u);
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)*a2 + 16);
  *(_DWORD *)Buffer = 0;
  v42 = 0;
  v44 = 0;
  v43 = 0;
  v34 = 0;
  EnterCriticalSection(v5);
  v6 = 0;
  v7 = 1;
  if ( !dword_1800C8568 )
    goto LABEL_67;
  while ( 1 )
  {
    v8 = (char *)qword_1800C8560;
    v9 = 168LL * v6;
    if ( v33 == 15 && *((_BYTE *)qword_1800C8560 + v9 + 8) == 1 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v10 = *(_DWORD *)(a1 + 96);
        Buffer[0] = 0;
        if ( v10 != -1 )
          _itow_s(v10, Buffer, 0x14u, 10);
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)L"AcceptReauthentication: Skipping version 1 Admin Dll callback for IKEv2 connection",
            (unsigned int)&v34,
            0,
            (__int64)Buffer);
      }
      goto LABEL_42;
    }
    if ( *(_QWORD *)((char *)qword_1800C8560 + v9 + 144) )
    {
      if ( v32 )
      {
        v11 = *a2;
        v32 = 0;
        v40[0] = 109576449;
        v31 = v11;
        if ( v11 )
          _InterlockedAdd((volatile signed __int32 *)v11 + 2, 1u);
        if ( (unsigned int)DdmDevice::GetConnectionData(a1, &v31, v40) )
        {
          DdmConnection::Disconnect(*a2, 0);
          v21 = byte_1800C8404;
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v22 = *(_DWORD *)(a1 + 96);
            Buffer[0] = 0;
            if ( v22 != -1 )
            {
              _itow_s(v22, Buffer, 0x14u, 10);
              v21 = byte_1800C8404;
            }
            if ( (v21 & 8) != 0 )
            {
              v23 = L"AcceptReauthenticationEx: Not able to get connection data";
LABEL_49:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (_DWORD)v23,
                (unsigned int)&v34,
                0,
                (__int64)Buffer);
              goto LABEL_67;
            }
          }
          goto LABEL_67;
        }
      }
      if ( !(*(unsigned int (__fastcall **)(_DWORD *))&v8[v9 + 144])(v40) )
      {
        DdmConnection::Disconnect(*a2, 0);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v12 = *(_DWORD *)(a1 + 96);
          LOWORD(v45) = 0;
          Buffer[0] = 0;
          if ( v12 != -1 )
            _itow_s(v12, Buffer, 0x14u, 10);
          FormatRRASErrorString(&v45, L"AcceptReauthenticationEx failed for Admin Dll with index %d", v6);
          goto LABEL_19;
        }
        goto LABEL_21;
      }
      goto LABEL_42;
    }
    if ( !*(_QWORD *)((char *)qword_1800C8560 + v9 + 120) )
      goto LABEL_42;
    if ( v7 )
      break;
LABEL_40:
    v20 = *(unsigned int (__fastcall **)(_BYTE *, _BYTE *, _BYTE *, _BYTE *))&v8[v9 + 120];
    if ( v20 && !v20(v36, v35, v39, v38) )
    {
      DdmConnection::Disconnect(*a2, 0);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v26 = *(_DWORD *)(a1 + 96);
        LOWORD(v45) = 0;
        Buffer[0] = 0;
        if ( v26 != -1 )
          _itow_s(v26, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v45, L"AcceptReauthentication: failed for Admin Dll with index %d", v6);
LABEL_19:
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v45,
            (unsigned int)&v34,
            0,
            (__int64)Buffer);
      }
LABEL_21:
      for ( i = 0; i < dword_1800C8568; ++i )
      {
        v14 = 168LL * i;
        v15 = *(void (__fastcall **)(_DWORD *))((char *)qword_1800C8560 + v14 + 152);
        if ( v15 )
        {
          v15(v40);
        }
        else
        {
          v27 = *(void (__fastcall **)(_BYTE *, _BYTE *, _BYTE *, _BYTE *))((char *)qword_1800C8560 + v14 + 96);
          if ( v27 )
          {
            v27(v36, v35, v39, v38);
          }
          else
          {
            v28 = *(void (__fastcall **)(_BYTE *, _BYTE *, _BYTE *))((char *)qword_1800C8560 + v14 + 88);
            if ( v28 )
            {
              v28(v36, v35, v39);
            }
            else
            {
              v29 = *(void (__fastcall **)(_BYTE *, _BYTE *))((char *)qword_1800C8560 + v14 + 80);
              if ( v29 )
                v29(v36, v35);
            }
          }
        }
      }
      v4 = 0;
      goto LABEL_67;
    }
LABEL_42:
    if ( ++v6 >= dword_1800C8568 )
      goto LABEL_67;
  }
  v16 = *a2;
  v31 = v16;
  if ( v16 )
    _InterlockedAdd((volatile signed __int32 *)v16 + 2, 1u);
  if ( !(unsigned int)DdmDevice::GetConnectionData(0, &v31, v36) )
  {
    v17 = *a2;
    v31 = v17;
    if ( v17 )
      _InterlockedAdd((volatile signed __int32 *)v17 + 2, 1u);
    if ( !(unsigned int)DdmDevice::GetConnectionData(a1, &v31, v35) )
    {
      v18 = *a2;
      v31 = v18;
      if ( v18 )
        _InterlockedAdd((volatile signed __int32 *)v18 + 2, 1u);
      if ( !(unsigned int)DdmDevice::GetConnectionData(a1, &v31, v39) )
      {
        v19 = *a2;
        v31 = v19;
        if ( v19 )
          _InterlockedAdd((volatile signed __int32 *)v19 + 2, 1u);
        if ( !(unsigned int)DdmDevice::GetConnectionData(a1, &v31, v38) )
        {
          v7 = 0;
          if ( !_wcsicmp(String1, gblpszUnknown) )
            String1[0] = 0;
          goto LABEL_40;
        }
      }
    }
  }
  DdmConnection::Disconnect(*a2, 0);
  v24 = byte_1800C8404;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    v25 = *(_DWORD *)(a1 + 96);
    Buffer[0] = 0;
    if ( v25 != -1 )
    {
      _itow_s(v25, Buffer, 0x14u, 10);
      v24 = byte_1800C8404;
    }
    if ( (v24 & 8) != 0 )
    {
      v23 = L"AcceptReauthentication: Not able to get connection data";
      goto LABEL_49;
    }
  }
LABEL_67:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)*a2 + 16));
  return v4;
}

```

## disassembly

```asm
0x18002fb40  mov     [rsp-8+arg_10], rbx
0x18002fb45  push    rbp
0x18002fb46  push    rsi
0x18002fb47  push    rdi
0x18002fb48  push    r12
0x18002fb4a  push    r13
0x18002fb4c  push    r14
0x18002fb4e  push    r15
0x18002fb50  lea     rbp, [rsp-1A30h]
0x18002fb58  mov     eax, 1B30h
0x18002fb5d  call    _alloca_probe
0x18002fb62  sub     rsp, rax
0x18002fb65  mov     rax, cs:__security_cookie
0x18002fb6c  xor     rax, rsp
0x18002fb6f  mov     [rbp+1A60h+var_40], rax
0x18002fb76  movzx   eax, word ptr [rcx+88h]
0x18002fb7d  mov     rdi, rdx
0x18002fb80  mov     rsi, rcx
0x18002fb83  mov     [rsp+1B60h+var_1B24], eax
0x18002fb87  mov     ebx, 1
0x18002fb8c  lea     rcx, [rbp+1A60h+var_19E0]; void *
0x18002fb93  xor     edx, edx; Val
0x18002fb95  mov     [rsp+1B60h+var_1B28], ebx
0x18002fb99  mov     r8d, 468h; Size
0x18002fb9f  call    memset_0
0x18002fba4  xor     edx, edx; Val
0x18002fba6  lea     rcx, [rsp+1B60h+var_1B10]; void *
0x18002fbab  mov     r8d, 128h; Size
0x18002fbb1  call    memset_0
0x18002fbb6  xor     edx, edx; Val
0x18002fbb8  lea     rcx, [rbp+1A60h+var_1250]; void *
0x18002fbbf  mov     r8d, 350h; Size
0x18002fbc5  call    memset_0
0x18002fbca  xor     edx, edx; Val
0x18002fbcc  lea     rcx, [rbp+1A60h+var_1570]; void *
0x18002fbd3  mov     r8d, 318h; Size
0x18002fbd9  call    memset_0
0x18002fbde  xor     edx, edx; Val
0x18002fbe0  mov     byte ptr [rbp+1A60h+var_F00], 0
0x18002fbe7  mov     r8d, 687h; Size
0x18002fbed  lea     rcx, [rbp+1A60h+var_F00+1]; void *
0x18002fbf4  call    memset_0
0x18002fbf9  xor     eax, eax
0x18002fbfb  lea     rcx, [rbp+1A60h+var_83C]; void *
0x18002fc02  xor     edx, edx; Val
0x18002fc04  mov     [rbp+1A60h+var_840], eax
0x18002fc0a  mov     r8d, 7FCh; Size
0x18002fc10  call    memset_0
0x18002fc15  mov     rcx, [rdi]
0x18002fc18  xorps   xmm0, xmm0
0x18002fc1b  xor     eax, eax
0x18002fc1d  add     rcx, 10h; lpCriticalSection
0x18002fc21  mov     dword ptr [rbp+1A60h+Buffer], eax
0x18002fc27  movups  [rbp+1A60h+var_86C], xmm0
0x18002fc2e  mov     [rbp+1A60h+var_84C], eax
0x18002fc34  movups  [rbp+1A60h+var_85C], xmm0
0x18002fc3b  movups  [rsp+1B60h+var_1B20], xmm0
0x18002fc40  call    cs:__imp_EnterCriticalSection
0x18002fc46  xor     r12d, r12d
0x18002fc49  mov     r13d, ebx
0x18002fc4c  cmp     cs:dword_1800C8568, r12d
0x18002fc53  jbe     loc_18003010F
0x18002fc59  mov     r15, cs:qword_1800C8560
0x18002fc60  mov     eax, r12d
0x18002fc63  imul    r14, rax, 0A8h
0x18002fc6a  cmp     [rsp+1B60h+var_1B24], 0Fh
0x18002fc6f  jnz     loc_18002FCF5
0x18002fc75  cmp     [r14+r15+8], bl
0x18002fc7a  jnz     short loc_18002FCF5
0x18002fc7c  test    cs:byte_1800C8404, 8
0x18002fc83  jz      loc_18002FF4F
0x18002fc89  mov     ecx, [rsi+60h]; Value
0x18002fc8c  xor     eax, eax
0x18002fc8e  mov     [rbp+1A60h+Buffer], ax
0x18002fc95  cmp     ecx, 0FFFFFFFFh
0x18002fc98  jz      short loc_18002FCAF
0x18002fc9a  lea     r9d, [rax+0Ah]; Radix
0x18002fc9e  lea     r8d, [rax+14h]; BufferCount
0x18002fca2  lea     rdx, [rbp+1A60h+Buffer]; Buffer
0x18002fca9  call    cs:__imp__itow_s
0x18002fcaf  test    cs:byte_1800C8404, 8
0x18002fcb6  jz      loc_18002FF4F
0x18002fcbc  lea     rax, [rbp+1A60h+Buffer]
0x18002fcc3  mov     [rsp+1B60h+var_1B38], rax
0x18002fcc8  lea     r9, [rsp+1B60h+var_1B20]
0x18002fccd  lea     r8, aAcceptreauthen_0; "AcceptReauthentication: Skipping versio"...
0x18002fcd4  mov     [rsp+1B60h+var_1B40], 0
0x18002fcdd  lea     rdx, RasDdmParamTraceError
0x18002fce4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002fceb  call    McTemplateU0zjzz_EventWriteTransfer
0x18002fcf0  jmp     loc_18002FF4F
0x18002fcf5  xor     ecx, ecx
0x18002fcf7  cmp     [r14+r15+90h], rcx
0x18002fcff  jz      loc_18002FE39
0x18002fd05  cmp     [rsp+1B60h+var_1B28], ecx
0x18002fd09  jz      short loc_18002FD46
0x18002fd0b  mov     rax, [rdi]
0x18002fd0e  mov     [rsp+1B60h+var_1B28], ecx
0x18002fd12  mov     [rbp+1A60h+var_F00], 6880101h
0x18002fd1c  mov     [rsp+1B60h+var_1B30], rax
0x18002fd21  test    rax, rax
0x18002fd24  jz      short loc_18002FD2A
0x18002fd26  lock add [rax+8], ebx
0x18002fd2a  lea     r8, [rbp+1A60h+var_F00]
0x18002fd31  mov     rcx, rsi
0x18002fd34  lea     rdx, [rsp+1B60h+var_1B30]
0x18002fd39  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_EX@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_EX *)
0x18002fd3e  test    eax, eax
0x18002fd40  jnz     loc_18002FF64
0x18002fd46  mov     rax, [r14+r15+90h]
0x18002fd4e  lea     rcx, [rbp+1A60h+var_F00]
0x18002fd55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd5a  test    eax, eax
0x18002fd5c  jnz     loc_18002FF4F
0x18002fd62  mov     rcx, [rdi]; this
0x18002fd65  xor     edx, edx; void *
0x18002fd67  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18002fd6c  test    cs:byte_1800C8404, 8
0x18002fd73  jz      loc_18002FDF9
0x18002fd79  mov     ecx, [rsi+60h]; Value
0x18002fd7c  xor     eax, eax
0x18002fd7e  mov     word ptr [rbp+1A60h+var_840], ax
0x18002fd85  mov     [rbp+1A60h+Buffer], ax
0x18002fd8c  cmp     ecx, 0FFFFFFFFh
0x18002fd8f  jz      short loc_18002FDA6
0x18002fd91  lea     r9d, [rax+0Ah]; Radix
0x18002fd95  lea     r8d, [rax+14h]; BufferCount
0x18002fd99  lea     rdx, [rbp+1A60h+Buffer]; Buffer
0x18002fda0  call    cs:__imp__itow_s
0x18002fda6  lea     rdx, aAcceptreauthen; "AcceptReauthenticationEx failed for Adm"...
0x18002fdad  mov     r8d, r12d
0x18002fdb0  lea     rcx, [rbp+1A60h+var_840]
0x18002fdb7  call    FormatRRASErrorString
0x18002fdbc  test    cs:byte_1800C8404, 8
0x18002fdc3  jz      short loc_18002FDF9
0x18002fdc5  lea     rax, [rbp+1A60h+Buffer]
0x18002fdcc  mov     [rsp+1B60h+var_1B38], rax
0x18002fdd1  lea     r9, [rsp+1B60h+var_1B20]
0x18002fdd6  lea     r8, [rbp+1A60h+var_840]
0x18002fddd  mov     [rsp+1B60h+var_1B40], 0
0x18002fde6  lea     rdx, RasDdmParamTraceError
0x18002fded  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002fdf4  call    McTemplateU0zjzz_EventWriteTransfer
0x18002fdf9  xor     esi, esi
0x18002fdfb  cmp     cs:dword_1800C8568, esi
0x18002fe01  jbe     loc_18003010D
0x18002fe07  mov     rdx, cs:qword_1800C8560
0x18002fe0e  mov     eax, esi
0x18002fe10  imul    rcx, rax, 0A8h
0x18002fe17  mov     rax, [rcx+rdx+98h]
0x18002fe1f  test    rax, rax
0x18002fe22  jz      loc_180030095
0x18002fe28  lea     rcx, [rbp+1A60h+var_F00]
0x18002fe2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe34  jmp     loc_1800300FF
0x18002fe39  cmp     [r14+r15+78h], rcx
0x18002fe3e  jz      loc_18002FF4F
0x18002fe44  test    r13d, r13d
0x18002fe47  jz      loc_18002FF1E
0x18002fe4d  mov     rax, [rdi]
0x18002fe50  mov     [rsp+1B60h+var_1B30], rax
0x18002fe55  test    rax, rax
0x18002fe58  jz      short loc_18002FE5E
0x18002fe5a  lock add [rax+8], ebx
0x18002fe5e  lea     r8, [rbp+1A60h+var_19E0]
0x18002fe65  lea     rdx, [rsp+1B60h+var_1B30]
0x18002fe6a  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_0@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_0 *)
0x18002fe6f  test    eax, eax
0x18002fe71  jnz     loc_18002FFEB
0x18002fe77  mov     rax, [rdi]
0x18002fe7a  mov     [rsp+1B60h+var_1B30], rax
0x18002fe7f  test    rax, rax
0x18002fe82  jz      short loc_18002FE88
0x18002fe84  lock add [rax+8], ebx
0x18002fe88  lea     r8, [rsp+1B60h+var_1B10]
0x18002fe8d  mov     rcx, rsi
0x18002fe90  lea     rdx, [rsp+1B60h+var_1B30]
0x18002fe95  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_1@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_1 *)
0x18002fe9a  test    eax, eax
0x18002fe9c  jnz     loc_18002FFEB
0x18002fea2  mov     rax, [rdi]
0x18002fea5  mov     [rsp+1B60h+var_1B30], rax
0x18002feaa  test    rax, rax
0x18002fead  jz      short loc_18002FEB3
0x18002feaf  lock add [rax+8], ebx
0x18002feb3  lea     r8, [rbp+1A60h+var_1250]
0x18002feba  mov     rcx, rsi
0x18002febd  lea     rdx, [rsp+1B60h+var_1B30]
0x18002fec2  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_2@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_2 *)
0x18002fec7  test    eax, eax
0x18002fec9  jnz     loc_18002FFEB
0x18002fecf  mov     rax, [rdi]
0x18002fed2  mov     [rsp+1B60h+var_1B30], rax
0x18002fed7  test    rax, rax
0x18002feda  jz      short loc_18002FEE0
0x18002fedc  lock add [rax+8], ebx
0x18002fee0  lea     r8, [rbp+1A60h+var_1570]
0x18002fee7  mov     rcx, rsi
0x18002feea  lea     rdx, [rsp+1B60h+var_1B30]
0x18002feef  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_3@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_3 *)
0x18002fef4  test    eax, eax
0x18002fef6  jnz     loc_18002FFEB
0x18002fefc  mov     rdx, cs:gblpszUnknown; String2
0x18002ff03  lea     rcx, [rbp+1A60h+String1]; String1
0x18002ff0a  xor     r13d, r13d
0x18002ff0d  call    cs:__imp__wcsicmp
0x18002ff13  test    eax, eax
0x18002ff15  jnz     short loc_18002FF1E
0x18002ff17  mov     [rbp+1A60h+String1], ax
0x18002ff1e  mov     rax, [r14+r15+78h]
0x18002ff23  test    rax, rax
0x18002ff26  jz      short loc_18002FF4F
0x18002ff28  lea     r9, [rbp+1A60h+var_1570]
0x18002ff2f  lea     r8, [rbp+1A60h+var_1250]
0x18002ff36  lea     rdx, [rsp+1B60h+var_1B10]
0x18002ff3b  lea     rcx, [rbp+1A60h+var_19E0]
0x18002ff42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff47  test    eax, eax
0x18002ff49  jz      loc_180030045
0x18002ff4f  add     r12d, ebx
0x18002ff52  cmp     r12d, cs:dword_1800C8568
0x18002ff59  jb      loc_18002FC59
0x18002ff5f  jmp     loc_18003010F
0x18002ff64  mov     rcx, [rdi]; this
0x18002ff67  xor     edx, edx; void *
0x18002ff69  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18002ff6e  mov     dl, cs:byte_1800C8404
0x18002ff74  test    dl, 8
0x18002ff77  jz      loc_18003010F
0x18002ff7d  mov     ecx, [rsi+60h]; Value
0x18002ff80  xor     eax, eax
0x18002ff82  mov     [rbp+1A60h+Buffer], ax
0x18002ff89  cmp     ecx, 0FFFFFFFFh
0x18002ff8c  jz      short loc_18002FFA9
0x18002ff8e  lea     r9d, [rax+0Ah]; Radix
0x18002ff92  lea     r8d, [rax+14h]; BufferCount
0x18002ff96  lea     rdx, [rbp+1A60h+Buffer]; Buffer
0x18002ff9d  call    cs:__imp__itow_s
0x18002ffa3  mov     dl, cs:byte_1800C8404
0x18002ffa9  test    dl, 8
0x18002ffac  jz      loc_18003010F
0x18002ffb2  lea     r8, aAcceptreauthen_3; "AcceptReauthenticationEx: Not able to g"...
0x18002ffb9  lea     rax, [rbp+1A60h+Buffer]
0x18002ffc0  mov     [rsp+1B60h+var_1B38], rax
0x18002ffc5  lea     r9, [rsp+1B60h+var_1B20]
0x18002ffca  lea     rdx, RasDdmParamTraceError
0x18002ffd1  mov     [rsp+1B60h+var_1B40], 0
0x18002ffda  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ffe1  call    McTemplateU0zjzz_EventWriteTransfer
0x18002ffe6  jmp     loc_18003010F
0x18002ffeb  mov     rcx, [rdi]; this
0x18002ffee  xor     edx, edx; void *
0x18002fff0  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18002fff5  mov     dl, cs:byte_1800C8404
0x18002fffb  test    dl, 8
0x18002fffe  jz      loc_18003010F
0x180030004  mov     ecx, [rsi+60h]; Value
0x180030007  xor     eax, eax
0x180030009  mov     [rbp+1A60h+Buffer], ax
0x180030010  cmp     ecx, 0FFFFFFFFh
0x180030013  jz      short loc_180030030
0x180030015  lea     r9d, [rax+0Ah]; Radix
0x180030019  lea     r8d, [rax+14h]; BufferCount
0x18003001d  lea     rdx, [rbp+1A60h+Buffer]; Buffer
0x180030024  call    cs:__imp__itow_s
0x18003002a  mov     dl, cs:byte_1800C8404
0x180030030  test    dl, 8
0x180030033  jz      loc_18003010F
0x180030039  lea     r8, aAcceptreauthen_2; "AcceptReauthentication: Not able to get"...
0x180030040  jmp     loc_18002FFB9
0x180030045  mov     rcx, [rdi]; this
0x180030048  xor     edx, edx; void *
0x18003004a  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18003004f  test    cs:byte_1800C8404, 8
0x180030056  jz      loc_18002FDF9
0x18003005c  mov     ecx, [rsi+60h]; Value
0x18003005f  xor     eax, eax
0x180030061  mov     word ptr [rbp+1A60h+var_840], ax
0x180030068  mov     [rbp+1A60h+Buffer], ax
0x18003006f  cmp     ecx, 0FFFFFFFFh
0x180030072  jz      short loc_180030089
0x180030074  lea     r9d, [rax+0Ah]; Radix
0x180030078  lea     r8d, [rax+14h]; BufferCount
0x18003007c  lea     rdx, [rbp+1A60h+Buffer]; Buffer
0x180030083  call    cs:__imp__itow_s
0x180030089  lea     rdx, aAcceptreauthen_1; "AcceptReauthentication: failed for Admi"...
0x180030090  jmp     loc_18002FDAD
0x180030095  mov     rax, [rcx+rdx+60h]
0x18003009a  test    rax, rax
0x18003009d  jz      short loc_1800300C0
0x18003009f  lea     r9, [rbp+1A60h+var_1570]
0x1800300a6  lea     r8, [rbp+1A60h+var_1250]
0x1800300ad  lea     rdx, [rsp+1B60h+var_1B10]
0x1800300b2  lea     rcx, [rbp+1A60h+var_19E0]
0x1800300b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300be  jmp     short loc_1800300FF
0x1800300c0  mov     rax, [rcx+rdx+58h]
0x1800300c5  test    rax, rax
0x1800300c8  jz      short loc_1800300E4
0x1800300ca  lea     r8, [rbp+1A60h+var_1250]
  ... truncated ...
```
