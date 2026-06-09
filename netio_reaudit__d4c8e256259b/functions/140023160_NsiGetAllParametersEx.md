# NsiGetAllParametersEx

- ea: `0x140023160`
- end: `0x140023609`
- name: `NsiGetAllParametersEx`
- size: `1193`
- prototype: ``
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020eb0`
- `0x140022d10`
- `0x140023090`
- `0x1400267b0`
- `0x140028380`
- `0x14003d740`

## callees

- `0x140023160`
- `0x140023610`
- `0x140023a40`
- `0x140023c30`
- `0x14002764c`
- `0x140042828`
- `0x14004f3bc`
- `0x140050ea4`
- `0x1400512d8`
- `0x14005d2b0`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b29e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b29e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002323d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002323d`

## pseudocode

```c
__int64 __fastcall NsiGetAllParametersEx(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // r9
  unsigned int v5; // ecx
  __int64 NmpContext; // rdi
  int v7; // eax
  int BootFirmwareTableData; // esi
  __int64 v9; // r14
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // rdx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // r14d
  int v22; // r15d
  __int128 *v23; // rdi
  __int64 v24; // rax
  unsigned int v25; // r15d
  unsigned int v26; // r12d
  __int64 v27; // r14
  __int64 v28; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v30; // rax
  __int128 *v31; // rdx
  char CurrentProcessId; // si
  int v33; // [rsp+68h] [rbp-59h] BYREF
  int v34; // [rsp+70h] [rbp-51h] BYREF
  __int128 v35; // [rsp+78h] [rbp-49h] BYREF
  __int128 v36; // [rsp+88h] [rbp-39h]
  _OWORD v37[4]; // [rsp+98h] [rbp-29h] BYREF
  __int128 v38; // [rsp+D8h] [rbp+17h] BYREF

  v35 = 0;
  v34 = 0;
  v36 = 0;
  v33 = 0;
  memset(v37, 0, 56);
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v20 = *(_QWORD *)(a1 + 16);
    v21 = *(_DWORD *)(a1 + 32);
    v22 = *(_DWORD *)(a1 + 24);
    v38 = 0;
    v23 = (__int128 *)(v20 + 8);
    if ( !v20 )
      v23 = &v38;
    CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
    NdisGetCurrentThreadCompartmentScope((__int64)&v34, (__int64)&v33);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v34,
        a3,
        (unsigned int)"NsiGetAllParametersEx",
        (__int64)v23,
        v22,
        v21,
        CurrentProcessId,
        0,
        v33,
        v34);
    }
  }
  v4 = *(unsigned int *)(a1 + 32);
  if ( (unsigned int)v4 > 4 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_35;
    }
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v28 = 35;
LABEL_78:
    WPP_SF_d(AttachedDevice, v28, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v4);
    goto LABEL_35;
  }
  v5 = *(_DWORD *)(a1 + 36);
  if ( v5 > 2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_35;
    }
    v4 = v5;
    v28 = 36;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    goto LABEL_78;
  }
  if ( (_DWORD)v4 == 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
    }
    goto LABEL_35;
  }
  if ( !*(_QWORD *)a1 )
  {
    NmpContext = 0;
    if ( (v4 & 0xFFFFFFFB) != 0 )
      NmpContext = NsipGetNmpContext(a1 + 8);
    v7 = *(_DWORD *)(a1 + 32);
    if ( v7 )
    {
      if ( v7 == 4 )
      {
        BootFirmwareTableData = NsipReadBootFirmwareTableData(a1 + 40, *(_QWORD *)(a1 + 56), (unsigned int *)(a1 + 64));
        goto LABEL_16;
      }
      if ( v7 != 3 )
      {
        if ( !NmpContext )
        {
          BootFirmwareTableData = -1073741637;
          goto LABEL_18;
        }
LABEL_12:
        if ( KeGetCurrentIrql() < 2u )
        {
          BootFirmwareTableData = NsipAccessCheck((unsigned int *)(a1 + 8), 1, 0);
          if ( BootFirmwareTableData < 0 )
            goto LABEL_16;
        }
        v9 = *(_QWORD *)(NmpContext + 48);
        BootFirmwareTableData = NsipValidateGetAllParametersRequest(v9, a1);
        if ( BootFirmwareTableData < 0 )
          goto LABEL_16;
        v10 = *(_OWORD *)(a1 + 40);
        v11 = *(_OWORD *)(a1 + 56);
        LODWORD(v37[0]) = *(_DWORD *)(a1 + 36);
        v36 = v10;
        v12 = *(_OWORD *)(a1 + 72);
        *(_OWORD *)((char *)v37 + 8) = v11;
        v13 = *(_OWORD *)(a1 + 88);
        *(_OWORD *)((char *)&v37[1] + 8) = v12;
        *(_OWORD *)((char *)&v37[2] + 8) = v13;
        *(_QWORD *)&v35 = *(_QWORD *)(NmpContext + 40);
        v14 = 104LL * *(unsigned int *)(a1 + 24);
        *((_QWORD *)&v35 + 1) = *(_QWORD *)(*(_QWORD *)(v9 + 8) + v14 + 24);
        BootFirmwareTableData = (*(__int64 (__fastcall **)(__int128 *))(*(_QWORD *)(v9 + 8) + v14 + 48))(&v35);
        if ( BootFirmwareTableData >= 0 )
        {
LABEL_16:
          if ( !NmpContext )
            goto LABEL_18;
          goto LABEL_17;
        }
        if ( BootFirmwareTableData == -1073741275 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            goto LABEL_16;
          }
          v17 = 40;
        }
        else
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            goto LABEL_16;
          }
          v17 = 39;
        }
        WPP_SF_d(
          v16->AttachedDevice,
          v17,
          WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids,
          (unsigned int)BootFirmwareTableData);
        goto LABEL_16;
      }
      if ( NmpContext )
        goto LABEL_12;
    }
    if ( *(_QWORD *)(a1 + 16) )
    {
LABEL_26:
      BootFirmwareTableData = NsipReadPersistentData(
                                (int)a1 + 8,
                                *(_DWORD *)(a1 + 36),
                                (int)a1 + 40,
                                *(_QWORD *)(a1 + 56),
                                0,
                                a1 + 64,
                                0);
      if ( !NmpContext )
        goto LABEL_18;
      *(_QWORD *)(a1 + 16) = 0;
LABEL_17:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)NmpContext, 0xFFFFFFFF) == 1 )
      {
        v38 = 0;
        if ( *(_QWORD *)(NmpContext + 72) )
        {
          v25 = 0;
          v26 = *(_DWORD *)(*(_QWORD *)(NmpContext + 48) + 4LL);
          if ( v26 )
          {
            v27 = 0;
            do
            {
              v18 = *(_QWORD *)(NmpContext + 72) + 24 * v27;
              if ( *(_QWORD *)v18 != v18 || *(_DWORD *)(v18 + 16) )
              {
                v19 = *(_QWORD *)(NmpContext + 48);
                *(_QWORD *)&v38 = *(_QWORD *)(NmpContext + 40);
                *((_QWORD *)&v38 + 1) = *(_QWORD *)(104 * v27 + *(_QWORD *)(v19 + 8) + 24);
                (*(void (__fastcall **)(__int128 *))(104 * v27 + *(_QWORD *)(v19 + 8) + 80))(&v38);
              }
              ++v25;
              ++v27;
            }
            while ( v25 < v26 );
          }
        }
        NmrClientDetachProviderComplete(*(HANDLE *)(NmpContext + 56));
      }
      goto LABEL_18;
    }
    if ( v7 )
    {
      BootFirmwareTableData = -1073741811;
      goto LABEL_16;
    }
    v24 = NsipGetNmpContext(a1 + 8);
    NmpContext = v24;
    if ( v24 )
    {
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(v24 + 24);
      goto LABEL_26;
    }
LABEL_35:
    BootFirmwareTableData = -1073741811;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
  }
  BootFirmwareTableData = -1073741822;
LABEL_18:
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v30 = *(_QWORD *)(a1 + 16);
    v38 = 0;
    v31 = (__int128 *)(v30 + 8);
    if ( !v30 )
      v31 = &v38;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_s_guid_dddqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v31,
        a3,
        (unsigned int)"NsiGetAllParametersEx",
        (__int64)v31,
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        0,
        0,
        0,
        0,
        BootFirmwareTableData);
  }
  return (unsigned int)BootFirmwareTableData;
}

```

## disassembly

```asm
0x140023160  mov     r11, rsp
0x140023163  push    rbp
0x140023164  push    rbx
0x140023165  push    rsi
0x140023166  push    r12
0x140023168  push    r13
0x14002316a  lea     rbp, [r11-5Fh]
0x14002316e  sub     rsp, 0F0h
0x140023175  mov     rax, cs:__security_cookie
0x14002317c  xor     rax, rsp
0x14002317f  mov     [rbp+57h+var_30], rax
0x140023183  xorps   xmm0, xmm0
0x140023186  mov     [r11+10h], rdi
0x14002318a  xor     eax, eax
0x14002318c  mov     [r11+18h], r14
0x140023190  xor     r13d, r13d
0x140023193  mov     [rbp+57h+var_50], rax
0x140023197  mov     rax, cs:WPP_GLOBAL_Control
0x14002319e  lea     r12, WPP_GLOBAL_Control
0x1400231a5  movups  [rbp+57h+var_A0], xmm0
0x1400231a9  mov     [rbp+57h+var_A8], r13d
0x1400231ad  mov     rbx, rcx
0x1400231b0  movups  [rbp+57h+var_90], xmm0
0x1400231b4  mov     [rbp+57h+var_B0], r13d
0x1400231b8  movups  [rbp+57h+var_80], xmm0
0x1400231bc  mov     [r11+20h], r15
0x1400231c0  movups  [rbp+57h+var_70], xmm0
0x1400231c4  movups  [rbp+57h+var_60], xmm0
0x1400231c8  cmp     byte ptr [rax+29h], 5
0x1400231cc  jnb     loc_14002343B
0x1400231d2  mov     r9d, [rbx+20h]
0x1400231d6  cmp     r9d, 4
0x1400231da  ja      loc_1400233D8
0x1400231e0  mov     ecx, [rbx+24h]
0x1400231e3  cmp     ecx, 2
0x1400231e6  ja      loc_140023582
0x1400231ec  cmp     r9d, 2
0x1400231f0  jz      loc_14002346C
0x1400231f6  cmp     [rbx], r13
0x1400231f9  jnz     loc_1400234AB
0x1400231ff  mov     rdi, r13
0x140023202  test    r9d, 0FFFFFFFBh
0x140023209  jz      short loc_140023217
0x14002320b  lea     rcx, [rbx+8]
0x14002320f  call    NsipGetNmpContext
0x140023214  mov     rdi, rax
0x140023217  mov     eax, [rbx+20h]
0x14002321a  test    eax, eax
0x14002321c  jz      loc_140023359
0x140023222  cmp     eax, 4
0x140023225  jz      loc_1400234F5
0x14002322b  cmp     eax, 3
0x14002322e  jz      loc_1400233CD
0x140023234  test    rdi, rdi
0x140023237  jz      loc_1400234EB
0x14002323d  call    cs:__imp_KeGetCurrentIrql
0x140023244  nop     dword ptr [rax+rax+00h]
0x140023249  cmp     al, 2
0x14002324b  jnb     short loc_140023261
0x14002324d  lea     rcx, [rbx+8]
0x140023251  xor     r8d, r8d
0x140023254  mov     dl, 1
0x140023256  call    NsipAccessCheck
0x14002325b  mov     esi, eax
0x14002325d  test    eax, eax
0x14002325f  js      short loc_1400232D0
0x140023261  mov     r14, [rdi+30h]
0x140023265  mov     rdx, rbx
0x140023268  mov     rcx, r14
0x14002326b  call    NsipValidateGetAllParametersRequest
0x140023270  mov     esi, eax
0x140023272  test    eax, eax
0x140023274  js      short loc_1400232D0
0x140023276  movups  xmm0, xmmword ptr [rbx+28h]
0x14002327a  mov     eax, [rbx+24h]
0x14002327d  movups  xmm1, xmmword ptr [rbx+38h]
0x140023281  mov     dword ptr [rbp+57h+var_80], eax
0x140023284  movaps  [rbp+57h+var_90], xmm0
0x140023288  movups  xmm0, xmmword ptr [rbx+48h]
0x14002328c  movups  [rbp+57h+var_80+8], xmm1
0x140023290  movups  xmm1, xmmword ptr [rbx+58h]
0x140023294  movups  [rbp+57h+var_70+8], xmm0
0x140023298  movups  [rbp+57h+var_60+8], xmm1
0x14002329c  mov     rax, [rdi+28h]
0x1400232a0  mov     qword ptr [rbp+57h+var_A0], rax
0x1400232a4  mov     eax, [rbx+18h]
0x1400232a7  imul    rdx, rax, 68h ; 'h'
0x1400232ab  mov     rax, [r14+8]
0x1400232af  mov     rcx, [rax+rdx+18h]
0x1400232b4  mov     qword ptr [rbp+57h+var_A0+8], rcx
0x1400232b8  lea     rcx, [rbp+57h+var_A0]
0x1400232bc  mov     rax, [r14+8]
0x1400232c0  mov     rax, [rax+rdx+30h]
0x1400232c5  call    _guard_dispatch_icall
0x1400232ca  mov     esi, eax
0x1400232cc  test    eax, eax
0x1400232ce  js      short loc_14002332E
0x1400232d0  test    rdi, rdi
0x1400232d3  jz      short loc_1400232E7
0x1400232d5  mov     eax, 0FFFFFFFFh
0x1400232da  lock xadd [rdi], eax
0x1400232de  cmp     eax, 1
0x1400232e1  jz      loc_140023537
0x1400232e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232ee  mov     r15, [rsp+110h+arg_18]
0x1400232f6  mov     r14, [rsp+110h+arg_10]
0x1400232fe  mov     rdi, [rsp+110h+arg_8]
0x140023306  cmp     byte ptr [rcx+29h], 5
0x14002330a  jnb     loc_1400235DD
0x140023310  mov     eax, esi
0x140023312  mov     rcx, [rbp+57h+var_30]
0x140023316  xor     rcx, rsp; StackCookie
0x140023319  call    __security_check_cookie
0x14002331e  add     rsp, 0F0h
0x140023325  pop     r13
0x140023327  pop     r12
0x140023329  pop     rsi
0x14002332a  pop     rbx
0x14002332b  pop     rbp
0x14002332c  retn
0x14002332e  cmp     esi, 0C0000225h
0x140023334  jnz     short loc_14002339E
0x140023336  mov     rcx, cs:WPP_GLOBAL_Control
0x14002333d  cmp     rcx, r12
0x140023340  jz      short loc_1400232D0
0x140023342  cmp     byte ptr [rcx+29h], 4
0x140023346  jb      short loc_1400232D0
0x140023348  mov     eax, [rcx+2Ch]
0x14002334b  test    al, 10h
0x14002334d  jz      short loc_1400232D0
0x14002334f  mov     edx, 28h ; '('
0x140023354  jmp     loc_14007B332
0x140023359  cmp     [rbx+10h], r13
0x14002335d  jz      loc_14002350D
0x140023363  mov     r9, [rbx+38h]
0x140023367  lea     rax, [rbx+40h]
0x14002336b  mov     edx, [rbx+24h]
0x14002336e  lea     r8, [rbx+28h]
0x140023372  mov     [rsp+110h+var_E0], r13d
0x140023377  lea     rcx, [rbx+8]
0x14002337b  mov     qword ptr [rsp+110h+var_E8], rax
0x140023380  mov     [rsp+110h+var_F0], r13
0x140023385  call    NsipReadPersistentData
0x14002338a  mov     esi, eax
0x14002338c  test    rdi, rdi
0x14002338f  jz      loc_1400232E7
0x140023395  mov     [rbx+10h], r13
0x140023399  jmp     loc_1400232D5
0x14002339e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233a5  cmp     rcx, r12
0x1400233a8  jz      loc_1400232D0
0x1400233ae  cmp     byte ptr [rcx+29h], 2
0x1400233b2  jb      loc_1400232D0
0x1400233b8  mov     eax, [rcx+2Ch]
0x1400233bb  test    al, 10h
0x1400233bd  jz      loc_1400232D0
0x1400233c3  mov     edx, 27h ; '''
0x1400233c8  jmp     loc_14007B332
0x1400233cd  test    rdi, rdi
0x1400233d0  jnz     loc_14002323D
0x1400233d6  jmp     short loc_140023359
0x1400233d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233df  cmp     rcx, r12
0x1400233e2  jnz     loc_1400235BA
0x1400233e8  mov     esi, 0C000000Dh
0x1400233ed  jmp     loc_1400232E7
0x1400233f2  mov     rax, [rdi+48h]
0x1400233f6  lea     rcx, [r14+r14*2]
0x1400233fa  lea     rdx, [rax+rcx*8]
0x1400233fe  cmp     [rdx], rdx
0x140023401  jz      loc_140023564
0x140023407  mov     rdx, [rdi+30h]
0x14002340b  mov     rax, [rdi+28h]
0x14002340f  mov     qword ptr [rbp+57h+var_40], rax
0x140023413  imul    r8, r14, 68h ; 'h'
0x140023417  mov     rax, [rdx+8]
0x14002341b  mov     rcx, [r8+rax+18h]
0x140023420  mov     qword ptr [rbp+57h+var_40+8], rcx
0x140023424  lea     rcx, [rbp+57h+var_40]
0x140023428  mov     rax, [rdx+8]
0x14002342c  mov     rax, [r8+rax+50h]
0x140023431  call    _guard_dispatch_icall
0x140023436  jmp     loc_14002356E
0x14002343b  mov     eax, [rax+2Ch]
0x14002343e  test    al, 10h
0x140023440  jz      loc_1400231D2
0x140023446  mov     rax, [rcx+10h]
0x14002344a  mov     r14d, [rcx+20h]
0x14002344e  mov     r15d, [rcx+18h]
0x140023452  movups  [rbp+57h+var_40], xmm0
0x140023456  lea     rdi, [rax+8]
0x14002345a  test    rax, rax
0x14002345d  jnz     loc_14007B29E
0x140023463  lea     rdi, [rbp+57h+var_40]
0x140023467  jmp     loc_14007B29E
0x14002346c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023473  cmp     rcx, r12
0x140023476  jz      loc_1400233E8
0x14002347c  cmp     byte ptr [rcx+29h], 2
0x140023480  jb      loc_1400233E8
0x140023486  mov     eax, [rcx+2Ch]
0x140023489  test    al, 10h
0x14002348b  jz      loc_1400233E8
0x140023491  mov     rcx, [rcx+18h]
0x140023495  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x14002349c  mov     edx, 25h ; '%'
0x1400234a1  call    WPP_SF_
0x1400234a6  jmp     loc_1400233E8
0x1400234ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234b2  cmp     rcx, r12
0x1400234b5  jz      loc_14007B328
0x1400234bb  cmp     byte ptr [rcx+29h], 2
0x1400234bf  jb      loc_14007B328
0x1400234c5  mov     eax, [rcx+2Ch]
0x1400234c8  test    al, 10h
0x1400234ca  jz      loc_14007B328
0x1400234d0  mov     rcx, [rcx+18h]
0x1400234d4  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x1400234db  mov     edx, 26h ; '&'
0x1400234e0  call    WPP_SF_
0x1400234e5  nop
0x1400234e6  jmp     loc_14007B328
0x1400234eb  mov     esi, 0C00000BBh
0x1400234f0  jmp     loc_1400232E7
0x1400234f5  mov     rdx, [rbx+38h]
0x1400234f9  lea     r8, [rbx+40h]
0x1400234fd  lea     rcx, [rbx+28h]
0x140023501  call    NsipReadBootFirmwareTableData
0x140023506  mov     esi, eax
0x140023508  jmp     loc_1400232D0
0x14002350d  test    eax, eax
0x14002350f  jnz     loc_14007B34B
0x140023515  lea     rcx, [rbx+8]
0x140023519  call    NsipGetNmpContext
0x14002351e  mov     rdi, rax
0x140023521  test    rax, rax
0x140023524  jz      loc_1400233E8
0x14002352a  mov     rax, [rax+18h]
0x14002352e  mov     [rbx+10h], rax
0x140023532  jmp     loc_140023363
0x140023537  xorps   xmm0, xmm0
0x14002353a  movups  [rbp+57h+var_40], xmm0
0x14002353e  cmp     [rdi+48h], r13
0x140023542  jz      loc_14007B35C
0x140023548  mov     rax, [rdi+30h]
0x14002354c  mov     r15d, r13d
0x14002354f  mov     r12d, [rax+4]
0x140023553  test    r12d, r12d
0x140023556  jz      loc_14007B355
0x14002355c  mov     r14, r13
0x14002355f  jmp     loc_1400233F2
0x140023564  cmp     [rdx+10h], r13d
0x140023568  jnz     loc_140023407
0x14002356e  inc     r15d
0x140023571  inc     r14
0x140023574  cmp     r15d, r12d
0x140023577  jb      loc_1400233F2
0x14002357d  jmp     loc_14007B355
0x140023582  mov     r10, cs:WPP_GLOBAL_Control
0x140023589  cmp     r10, r12
0x14002358c  jz      loc_1400233E8
0x140023592  cmp     byte ptr [r10+29h], 2
0x140023597  jb      loc_1400233E8
0x14002359d  mov     eax, [r10+2Ch]
0x1400235a1  test    al, 10h
0x1400235a3  jz      loc_1400233E8
0x1400235a9  mov     r9d, ecx
0x1400235ac  mov     edx, 24h ; '$'
0x1400235b1  mov     rcx, [r10+18h]
0x1400235b5  jmp     loc_14007B36B
0x1400235ba  cmp     byte ptr [rcx+29h], 2
0x1400235be  jb      loc_1400233E8
0x1400235c4  mov     eax, [rcx+2Ch]
0x1400235c7  test    al, 10h
0x1400235c9  jz      loc_1400233E8
0x1400235cf  mov     rcx, [rcx+18h]
0x1400235d3  mov     edx, 23h ; '#'
0x1400235d8  jmp     loc_14007B36B
0x1400235dd  mov     eax, [rcx+2Ch]
0x1400235e0  test    al, 10h
0x1400235e2  jz      loc_140023310
0x1400235e8  mov     rax, [rbx+10h]
0x1400235ec  xorps   xmm0, xmm0
0x1400235ef  movups  [rbp+57h+var_40], xmm0
0x1400235f3  lea     rdx, [rax+8]
0x1400235f7  test    rax, rax
0x1400235fa  jnz     loc_14007B37D
0x140023600  lea     rdx, [rbp+57h+var_40]
0x140023604  jmp     loc_14007B37D
0x14007b29e  call    cs:__imp_PsGetCurrentProcessId
0x14007b2a5  nop     dword ptr [rax+rax+00h]
0x14007b2aa  mov     edx, [rbp+57h+var_A8]
0x14007b2ad  mov     rsi, rax
0x14007b2b0  test    edx, edx
0x14007b2b2  jnz     short loc_14007B2CA
0x14007b2b4  cmp     [rbp+57h+var_B0], r13d
0x14007b2b8  jnz     short loc_14007B2CA
0x14007b2ba  lea     rdx, [rbp+57h+var_B0]
0x14007b2be  lea     rcx, [rbp+57h+var_A8]
0x14007b2c2  call    NdisGetCurrentThreadCompartmentScope
  ... truncated ...
```
