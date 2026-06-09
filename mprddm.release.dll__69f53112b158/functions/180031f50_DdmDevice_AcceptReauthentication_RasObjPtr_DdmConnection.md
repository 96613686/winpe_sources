# DdmDevice::AcceptReauthentication(RasObjPtr<DdmConnection> &)

- ea: `0x180031f50`
- end: `0x1800324e3`
- name: `?AcceptReauthentication@DdmDevice@@UEAAHAEAV?$RasObjPtr@VDdmConnection@@@@@Z`
- size: `1427`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007d00`
- `0x18002f010`
- `0x180031f50`
- `0x180033c18`
- `0x180033d4c`
- `0x180033f0c`
- `0x180034068`
- `0x180034b2c`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180032269`
- `msvcrt!_wcsicmp` at `0x180032269`
- `KERNEL32!LeaveCriticalSection` at `0x1800322cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800322cc`
- `KERNEL32!EnterCriticalSection` at `0x18003204f`
- `KERNEL32!EnterCriticalSection` at `0x18003204f`

## string_xrefs

- `0x1800320ca`: `AcceptReauthentication: Skipping version 1 Admin Dll callback for IKEv2 connection`
- `0x18003218a`: `AcceptReauthenticationEx failed for Admin Dll with index %d`
- `0x1800323e2`: `AcceptReauthentication: failed for Admin Dll with index %d`

## pseudocode

```c
__int64 __fastcall DdmDevice::AcceptReauthentication(__int64 a1, DdmConnection **a2)
{
  int v4; // r12d
  int v5; // r13d
  unsigned int v6; // ebx
  DdmConnection *v7; // rcx
  __int64 v8; // rcx
  unsigned int i; // r15d
  char *v10; // rsi
  __int64 v11; // rdx
  DdmConnection *v12; // rax
  __int64 v13; // rdx
  DdmConnection *v14; // rax
  DdmConnection *v15; // rax
  DdmConnection *v16; // rax
  DdmConnection *v17; // rax
  unsigned int (__fastcall *v18)(_BYTE *, _BYTE *, _BYTE *, _BYTE *); // rax
  __int64 v20; // rdx
  const wchar_t *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned int j; // esi
  _QWORD *v25; // rcx
  void (__fastcall *v26)(_DWORD *); // rax
  void (__fastcall *v27)(_BYTE *, _BYTE *, _BYTE *, _BYTE *); // rax
  void (__fastcall *v28)(_BYTE *, _BYTE *, _BYTE *); // rax
  void (__fastcall *v29)(_BYTE *, _BYTE *); // rax
  int v30; // [rsp+30h] [rbp-D0h]
  DdmConnection *v31; // [rsp+38h] [rbp-C8h] BYREF
  DdmConnection *v32; // [rsp+40h] [rbp-C0h] BYREF
  DdmConnection *v33; // [rsp+48h] [rbp-B8h] BYREF
  DdmConnection *v34; // [rsp+50h] [rbp-B0h] BYREF
  DdmConnection *v35; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[304]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[542]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t String1[297]; // [rsp+3BEh] [rbp+2BEh] BYREF
  _BYTE v40[800]; // [rsp+610h] [rbp+510h] BYREF
  _BYTE v41[848]; // [rsp+930h] [rbp+830h] BYREF
  _DWORD v42[420]; // [rsp+C80h] [rbp+B80h] BYREF
  int v43; // [rsp+1310h] [rbp+1210h] BYREF
  __int128 v44; // [rsp+1314h] [rbp+1214h]
  __int128 v45; // [rsp+1324h] [rbp+1224h]
  int v46; // [rsp+1334h] [rbp+1234h]
  int v47; // [rsp+1340h] [rbp+1240h] BYREF
  char v48[2044]; // [rsp+1344h] [rbp+1244h] BYREF

  v30 = *(unsigned __int16 *)(a1 + 136);
  v4 = 1;
  v5 = 1;
  memset_0(v38, 0, 0x468u);
  memset_0(v37, 0, 0x128u);
  memset_0(v41, 0, sizeof(v41));
  memset_0(v40, 0, 0x318u);
  v6 = 0;
  LOBYTE(v42[0]) = 0;
  memset_0((char *)v42 + 1, 0, 0x687u);
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  v7 = *a2;
  v43 = 0;
  v46 = 0;
  v44 = 0;
  v45 = 0;
  v36 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 16));
  for ( i = 0; i < dword_1800CF568; ++i )
  {
    v10 = (char *)qword_1800CF560 + 168 * i;
    if ( v30 == 15 && v10[8] == 1 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v11 = *(unsigned int *)(a1 + 96);
        LOWORD(v43) = 0;
        ConvertPortNoToString(&v43, v11);
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)L"AcceptReauthentication: Skipping version 1 Admin Dll callback for IKEv2 connection",
            (unsigned int)&v36,
            0,
            (__int64)&v43);
      }
    }
    else if ( *((_QWORD *)v10 + 18) )
    {
      if ( v5 )
      {
        v12 = *a2;
        v5 = 0;
        v42[0] = 109576449;
        v31 = v12;
        if ( v12 )
          _InterlockedIncrement((volatile signed __int32 *)v12 + 2);
        if ( (unsigned int)DdmDevice::GetConnectionData(a1, &v31, v42) )
        {
          DdmConnection::Disconnect(*a2, 0);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v20 = *(unsigned int *)(a1 + 96);
            LOWORD(v43) = 0;
            ConvertPortNoToString(&v43, v20);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              v21 = L"AcceptReauthenticationEx: Not able to get connection data";
LABEL_39:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (_DWORD)v21,
                (unsigned int)&v36,
                0,
                (__int64)&v43);
              break;
            }
          }
          break;
        }
      }
      if ( !(*((unsigned int (__fastcall **)(_DWORD *))v10 + 18))(v42) )
      {
        DdmConnection::Disconnect(*a2, 0);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v13 = *(unsigned int *)(a1 + 96);
          LOWORD(v47) = 0;
          LOWORD(v43) = 0;
          ConvertPortNoToString(&v43, v13);
          FormatRRASErrorString(&v47, L"AcceptReauthenticationEx failed for Admin Dll with index %d", i);
LABEL_45:
          if ( (byte_1800CF404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v47,
              (unsigned int)&v36,
              0,
              (__int64)&v43);
        }
        goto LABEL_47;
      }
    }
    else if ( *((_QWORD *)v10 + 15) )
    {
      if ( v4 )
      {
        v14 = *a2;
        v4 = 0;
        v32 = v14;
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)v14 + 2);
        if ( (unsigned int)DdmDevice::GetConnectionData(v8, &v32, v38) )
          goto LABEL_40;
        v15 = *a2;
        v33 = v15;
        if ( v15 )
          _InterlockedIncrement((volatile signed __int32 *)v15 + 2);
        if ( (unsigned int)DdmDevice::GetConnectionData(a1, &v33, v37) )
          goto LABEL_40;
        v16 = *a2;
        v34 = v16;
        if ( v16 )
          _InterlockedIncrement((volatile signed __int32 *)v16 + 2);
        if ( (unsigned int)DdmDevice::GetConnectionData(a1, &v34, v41) )
          goto LABEL_40;
        v17 = *a2;
        v35 = v17;
        if ( v17 )
          _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
        if ( (unsigned int)DdmDevice::GetConnectionData(a1, &v35, v40) )
        {
LABEL_40:
          DdmConnection::Disconnect(*a2, 0);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v22 = *(unsigned int *)(a1 + 96);
            LOWORD(v43) = 0;
            ConvertPortNoToString(&v43, v22);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              v21 = L"AcceptReauthentication: Not able to get connection data";
              goto LABEL_39;
            }
          }
          break;
        }
        if ( !_wcsicmp(String1, gblpszUnknown) )
          String1[0] = 0;
      }
      v18 = (unsigned int (__fastcall *)(_BYTE *, _BYTE *, _BYTE *, _BYTE *))*((_QWORD *)v10 + 15);
      if ( v18 )
      {
        if ( !v18(v38, v37, v41, v40) )
        {
          DdmConnection::Disconnect(*a2, 0);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v23 = *(unsigned int *)(a1 + 96);
            LOWORD(v47) = 0;
            LOWORD(v43) = 0;
            ConvertPortNoToString(&v43, v23);
            FormatRRASErrorString(&v47, L"AcceptReauthentication: failed for Admin Dll with index %d", i);
            goto LABEL_45;
          }
LABEL_47:
          for ( j = 0; j < dword_1800CF568; ++j )
          {
            v25 = (char *)qword_1800CF560 + 168 * j;
            v26 = (void (__fastcall *)(_DWORD *))v25[19];
            if ( v26 )
            {
              v26(v42);
            }
            else
            {
              v27 = (void (__fastcall *)(_BYTE *, _BYTE *, _BYTE *, _BYTE *))v25[12];
              if ( v27 )
              {
                v27(v38, v37, v41, v40);
              }
              else
              {
                v28 = (void (__fastcall *)(_BYTE *, _BYTE *, _BYTE *))v25[11];
                if ( v28 )
                {
                  v28(v38, v37, v41);
                }
                else
                {
                  v29 = (void (__fastcall *)(_BYTE *, _BYTE *))v25[10];
                  if ( v29 )
                    v29(v38, v37);
                }
              }
            }
          }
          goto LABEL_35;
        }
      }
    }
  }
  v6 = 1;
LABEL_35:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)*a2 + 16));
  return v6;
}

```

## disassembly

```asm
0x180031f50  mov     [rsp-8+arg_10], rbx
0x180031f55  push    rbp
0x180031f56  push    rsi
0x180031f57  push    rdi
0x180031f58  push    r12
0x180031f5a  push    r13
0x180031f5c  push    r14
0x180031f5e  push    r15
0x180031f60  lea     rbp, [rsp-1A50h]
0x180031f68  mov     eax, 1B50h
0x180031f6d  call    _alloca_probe
0x180031f72  sub     rsp, rax
0x180031f75  mov     rax, cs:__security_cookie
0x180031f7c  xor     rax, rsp
0x180031f7f  mov     [rbp+1A80h+var_40], rax
0x180031f86  movzx   eax, word ptr [rcx+88h]
0x180031f8d  mov     rdi, rdx
0x180031f90  mov     r14, rcx
0x180031f93  mov     [rsp+1B80h+var_1B50], eax
0x180031f97  mov     r12d, 1
0x180031f9d  lea     rcx, [rbp+1A80h+var_19E0]; void *
0x180031fa4  xor     edx, edx; Val
0x180031fa6  mov     r8d, 468h; Size
0x180031fac  mov     r13d, r12d
0x180031faf  call    memset_0
0x180031fb4  xor     edx, edx; Val
0x180031fb6  lea     rcx, [rsp+1B80h+var_1B10]; void *
0x180031fbb  mov     r8d, 128h; Size
0x180031fc1  call    memset_0
0x180031fc6  xor     edx, edx; Val
0x180031fc8  lea     rcx, [rbp+1A80h+var_1250]; void *
0x180031fcf  mov     r8d, 350h; Size
0x180031fd5  call    memset_0
0x180031fda  xor     edx, edx; Val
0x180031fdc  lea     rcx, [rbp+1A80h+var_1570]; void *
0x180031fe3  mov     r8d, 318h; Size
0x180031fe9  call    memset_0
0x180031fee  xor     ebx, ebx
0x180031ff0  lea     rcx, [rbp+1A80h+var_F00+1]; void *
0x180031ff7  xor     edx, edx; Val
0x180031ff9  mov     byte ptr [rbp+1A80h+var_F00], bl
0x180031fff  mov     r8d, 687h; Size
0x180032005  call    memset_0
0x18003200a  xor     edx, edx; Val
0x18003200c  mov     [rbp+1A80h+var_840], ebx
0x180032012  mov     r8d, 7FCh; Size
0x180032018  lea     rcx, [rbp+1A80h+var_83C]; void *
0x18003201f  call    memset_0
0x180032024  mov     rcx, [rdi]
0x180032027  xorps   xmm0, xmm0
0x18003202a  xor     eax, eax
0x18003202c  mov     [rbp+1A80h+var_870], ebx
0x180032032  add     rcx, 10h; lpCriticalSection
0x180032036  mov     [rbp+1A80h+var_84C], eax
0x18003203c  movups  [rbp+1A80h+var_86C], xmm0
0x180032043  movups  [rbp+1A80h+var_85C], xmm0
0x18003204a  movups  [rsp+1B80h+var_1B20], xmm0
0x18003204f  call    cs:__imp_EnterCriticalSection
0x180032056  nop     dword ptr [rax+rax+00h]
0x18003205b  cmp     cs:dword_1800CF568, ebx
0x180032061  mov     r15d, ebx
0x180032064  jbe     loc_1800322C0
0x18003206a  mov     eax, r15d
0x18003206d  imul    rsi, rax, 0A8h
0x180032074  add     rsi, cs:qword_1800CF560
0x18003207b  cmp     [rsp+1B80h+var_1B50], 0Fh
0x180032080  jnz     short loc_1800320EE
0x180032082  cmp     byte ptr [rsi+8], 1
0x180032086  jnz     short loc_1800320EE
0x180032088  test    cs:byte_1800CF404, 8
0x18003208f  jz      loc_1800322B0
0x180032095  mov     edx, [r14+60h]
0x180032099  lea     rcx, [rbp+1A80h+var_870]
0x1800320a0  mov     word ptr [rbp+1A80h+var_870], bx
0x1800320a7  call    ConvertPortNoToString
0x1800320ac  test    cs:byte_1800CF404, 8
0x1800320b3  jz      loc_1800322B0
0x1800320b9  lea     rax, [rbp+1A80h+var_870]
0x1800320c0  mov     [rsp+1B80h+var_1B58], rax
0x1800320c5  lea     r9, [rsp+1B80h+var_1B20]
0x1800320ca  lea     r8, aAcceptreauthen_0; "AcceptReauthentication: Skipping versio"...
0x1800320d1  mov     [rsp+1B80h+var_1B60], rbx
0x1800320d6  lea     rdx, RasDdmParamTraceError
0x1800320dd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800320e4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800320e9  jmp     loc_1800322B0
0x1800320ee  cmp     [rsi+90h], rbx
0x1800320f5  jz      loc_180032196
0x1800320fb  test    r13d, r13d
0x1800320fe  jz      short loc_18003213A
0x180032100  mov     rax, [rdi]
0x180032103  mov     r13d, ebx
0x180032106  mov     [rbp+1A80h+var_F00], 6880101h
0x180032110  mov     [rsp+1B80h+var_1B48], rax
0x180032115  test    rax, rax
0x180032118  jz      short loc_18003211E
0x18003211a  lock inc dword ptr [rax+8]
0x18003211e  lea     r8, [rbp+1A80h+var_F00]
0x180032125  mov     rcx, r14
0x180032128  lea     rdx, [rsp+1B80h+var_1B48]
0x18003212d  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_EX@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_EX *)
0x180032132  test    eax, eax
0x180032134  jnz     loc_180032305
0x18003213a  mov     rax, [rsi+90h]
0x180032141  lea     rcx, [rbp+1A80h+var_F00]
0x180032148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003214d  test    eax, eax
0x18003214f  jnz     loc_1800322B0
0x180032155  mov     rcx, [rdi]; this
0x180032158  xor     edx, edx; void *
0x18003215a  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18003215f  test    cs:byte_1800CF404, 8
0x180032166  jz      loc_180032431
0x18003216c  mov     edx, [r14+60h]
0x180032170  lea     rcx, [rbp+1A80h+var_870]
0x180032177  mov     word ptr [rbp+1A80h+var_840], bx
0x18003217e  mov     word ptr [rbp+1A80h+var_870], bx
0x180032185  call    ConvertPortNoToString
0x18003218a  lea     rdx, aAcceptreauthen; "AcceptReauthenticationEx failed for Adm"...
0x180032191  jmp     loc_1800323E9
0x180032196  cmp     [rsi+78h], rbx
0x18003219a  jz      loc_1800322B0
0x1800321a0  test    r12d, r12d
0x1800321a3  jz      loc_180032280
0x1800321a9  mov     rax, [rdi]
0x1800321ac  mov     r12d, ebx
0x1800321af  mov     [rsp+1B80h+var_1B40], rax
0x1800321b4  test    rax, rax
0x1800321b7  jz      short loc_1800321BD
0x1800321b9  lock inc dword ptr [rax+8]
0x1800321bd  lea     r8, [rbp+1A80h+var_19E0]
0x1800321c4  lea     rdx, [rsp+1B80h+var_1B40]
0x1800321c9  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_0@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_0 *)
0x1800321ce  test    eax, eax
0x1800321d0  jnz     loc_18003236D
0x1800321d6  mov     rax, [rdi]
0x1800321d9  mov     [rsp+1B80h+var_1B38], rax
0x1800321de  test    rax, rax
0x1800321e1  jz      short loc_1800321E7
0x1800321e3  lock inc dword ptr [rax+8]
0x1800321e7  lea     r8, [rsp+1B80h+var_1B10]
0x1800321ec  mov     rcx, r14
0x1800321ef  lea     rdx, [rsp+1B80h+var_1B38]
0x1800321f4  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_1@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_1 *)
0x1800321f9  test    eax, eax
0x1800321fb  jnz     loc_18003236D
0x180032201  mov     rax, [rdi]
0x180032204  mov     [rsp+1B80h+var_1B30], rax
0x180032209  test    rax, rax
0x18003220c  jz      short loc_180032212
0x18003220e  lock inc dword ptr [rax+8]
0x180032212  lea     r8, [rbp+1A80h+var_1250]
0x180032219  mov     rcx, r14
0x18003221c  lea     rdx, [rsp+1B80h+var_1B30]
0x180032221  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_2@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_2 *)
0x180032226  test    eax, eax
0x180032228  jnz     loc_18003236D
0x18003222e  mov     rax, [rdi]
0x180032231  mov     [rsp+1B80h+var_1B28], rax
0x180032236  test    rax, rax
0x180032239  jz      short loc_18003223F
0x18003223b  lock inc dword ptr [rax+8]
0x18003223f  lea     r8, [rbp+1A80h+var_1570]
0x180032246  mov     rcx, r14
0x180032249  lea     rdx, [rsp+1B80h+var_1B28]
0x18003224e  call    ?GetConnectionData@DdmDevice@@QEAAKV?$RasObjPtr@VDdmConnection@@@@PEAU_RAS_CONNECTION_3@@@Z; DdmDevice::GetConnectionData(RasObjPtr<DdmConnection>,_RAS_CONNECTION_3 *)
0x180032253  test    eax, eax
0x180032255  jnz     loc_18003236D
0x18003225b  mov     rdx, cs:gblpszUnknown; String2
0x180032262  lea     rcx, [rbp+1A80h+String1]; String1
0x180032269  call    cs:__imp__wcsicmp
0x180032270  nop     dword ptr [rax+rax+00h]
0x180032275  test    eax, eax
0x180032277  jnz     short loc_180032280
0x180032279  mov     [rbp+1A80h+String1], bx
0x180032280  mov     rax, [rsi+78h]
0x180032284  test    rax, rax
0x180032287  jz      short loc_1800322B0
0x180032289  lea     r9, [rbp+1A80h+var_1570]
0x180032290  lea     r8, [rbp+1A80h+var_1250]
0x180032297  lea     rdx, [rsp+1B80h+var_1B10]
0x18003229c  lea     rcx, [rbp+1A80h+var_19E0]
0x1800322a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322a8  test    eax, eax
0x1800322aa  jz      loc_1800323B1
0x1800322b0  inc     r15d
0x1800322b3  cmp     r15d, cs:dword_1800CF568
0x1800322ba  jb      loc_18003206A
0x1800322c0  mov     ebx, 1
0x1800322c5  mov     rcx, [rdi]
0x1800322c8  add     rcx, 10h; lpCriticalSection
0x1800322cc  call    cs:__imp_LeaveCriticalSection
0x1800322d3  nop     dword ptr [rax+rax+00h]
0x1800322d8  mov     eax, ebx
0x1800322da  mov     rcx, [rbp+1A80h+var_40]
0x1800322e1  xor     rcx, rsp; StackCookie
0x1800322e4  call    __security_check_cookie
0x1800322e9  mov     rbx, [rsp+1B80h+arg_10]
0x1800322f1  add     rsp, 1B50h
0x1800322f8  pop     r15
0x1800322fa  pop     r14
0x1800322fc  pop     r13
0x1800322fe  pop     r12
0x180032300  pop     rdi
0x180032301  pop     rsi
0x180032302  pop     rbp
0x180032303  retn
0x180032305  mov     rcx, [rdi]; this
0x180032308  xor     edx, edx; void *
0x18003230a  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x18003230f  test    cs:byte_1800CF404, 8
0x180032316  jz      short loc_1800322C0
0x180032318  mov     edx, [r14+60h]
0x18003231c  lea     rcx, [rbp+1A80h+var_870]
0x180032323  mov     word ptr [rbp+1A80h+var_870], bx
0x18003232a  call    ConvertPortNoToString
0x18003232f  test    cs:byte_1800CF404, 8
0x180032336  jz      short loc_1800322C0
0x180032338  lea     r8, aAcceptreauthen_3; "AcceptReauthenticationEx: Not able to g"...
0x18003233f  lea     rax, [rbp+1A80h+var_870]
0x180032346  mov     [rsp+1B80h+var_1B58], rax
0x18003234b  lea     r9, [rsp+1B80h+var_1B20]
0x180032350  lea     rdx, RasDdmParamTraceError
0x180032357  mov     [rsp+1B80h+var_1B60], rbx
0x18003235c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180032363  call    McTemplateU0zjzz_EventWriteTransfer
0x180032368  jmp     loc_1800322C0
0x18003236d  mov     rcx, [rdi]; this
0x180032370  xor     edx, edx; void *
0x180032372  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x180032377  test    cs:byte_1800CF404, 8
0x18003237e  jz      loc_1800322C0
0x180032384  mov     edx, [r14+60h]
0x180032388  lea     rcx, [rbp+1A80h+var_870]
0x18003238f  mov     word ptr [rbp+1A80h+var_870], bx
0x180032396  call    ConvertPortNoToString
0x18003239b  test    cs:byte_1800CF404, 8
0x1800323a2  jz      loc_1800322C0
0x1800323a8  lea     r8, aAcceptreauthen_2; "AcceptReauthentication: Not able to get"...
0x1800323af  jmp     short loc_18003233F
0x1800323b1  mov     rcx, [rdi]; this
0x1800323b4  xor     edx, edx; void *
0x1800323b6  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x1800323bb  test    cs:byte_1800CF404, 8
0x1800323c2  jz      short loc_180032431
0x1800323c4  mov     edx, [r14+60h]
0x1800323c8  lea     rcx, [rbp+1A80h+var_870]
0x1800323cf  mov     word ptr [rbp+1A80h+var_840], bx
0x1800323d6  mov     word ptr [rbp+1A80h+var_870], bx
0x1800323dd  call    ConvertPortNoToString
0x1800323e2  lea     rdx, aAcceptreauthen_1; "AcceptReauthentication: failed for Admi"...
0x1800323e9  mov     r8d, r15d
0x1800323ec  lea     rcx, [rbp+1A80h+var_840]
0x1800323f3  call    FormatRRASErrorString
0x1800323f8  test    cs:byte_1800CF404, 8
0x1800323ff  jz      short loc_180032431
0x180032401  lea     rax, [rbp+1A80h+var_870]
0x180032408  mov     [rsp+1B80h+var_1B58], rax
0x18003240d  lea     r9, [rsp+1B80h+var_1B20]
0x180032412  lea     r8, [rbp+1A80h+var_840]
0x180032419  mov     [rsp+1B80h+var_1B60], rbx
0x18003241e  lea     rdx, RasDdmParamTraceError
0x180032425  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003242c  call    McTemplateU0zjzz_EventWriteTransfer
0x180032431  cmp     cs:dword_1800CF568, ebx
0x180032437  mov     esi, ebx
0x180032439  jbe     loc_1800322C5
0x18003243f  mov     eax, esi
0x180032441  imul    rcx, rax, 0A8h
0x180032448  add     rcx, cs:qword_1800CF560
0x18003244f  mov     rax, [rcx+98h]
0x180032456  test    rax, rax
0x180032459  jz      short loc_180032469
0x18003245b  lea     rcx, [rbp+1A80h+var_F00]
0x180032462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032467  jmp     short loc_1800324D0
0x180032469  mov     rax, [rcx+60h]
0x18003246d  test    rax, rax
0x180032470  jz      short loc_180032493
0x180032472  lea     r9, [rbp+1A80h+var_1570]
0x180032479  lea     r8, [rbp+1A80h+var_1250]
0x180032480  lea     rdx, [rsp+1B80h+var_1B10]
0x180032485  lea     rcx, [rbp+1A80h+var_19E0]
0x18003248c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032491  jmp     short loc_1800324D0
0x180032493  mov     rax, [rcx+58h]
0x180032497  test    rax, rax
0x18003249a  jz      short loc_1800324B6
0x18003249c  lea     r8, [rbp+1A80h+var_1250]
0x1800324a3  lea     rdx, [rsp+1B80h+var_1B10]
0x1800324a8  lea     rcx, [rbp+1A80h+var_19E0]
0x1800324af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324b4  jmp     short loc_1800324D0
0x1800324b6  mov     rax, [rcx+50h]
0x1800324ba  test    rax, rax
0x1800324bd  jz      short loc_1800324D0
0x1800324bf  lea     rdx, [rsp+1B80h+var_1B10]
0x1800324c4  lea     rcx, [rbp+1A80h+var_19E0]
0x1800324cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324d0  inc     esi
  ... truncated ...
```
