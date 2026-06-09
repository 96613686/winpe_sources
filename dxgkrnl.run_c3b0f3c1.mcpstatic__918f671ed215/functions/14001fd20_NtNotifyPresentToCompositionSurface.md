# NtNotifyPresentToCompositionSurface

- ea: `0x14001fd20`
- end: `0x140020319`
- name: `NtNotifyPresentToCompositionSurface`
- size: `1529`
- prototype: `__int64 __fastcall(HANDLE Handle, char *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1403bef70`

## callees

- `0x14001b9c0`
- `0x14001fd20`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140329ff0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140020058`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140020058`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ff0d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020046`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ff0d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020046`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ffdf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020167`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ffdf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020167`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400201cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400201cd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002015b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002015b`
- `ntoskrnl!ObfDereferenceObject` at `0x140020177`
- `ntoskrnl!ObfDereferenceObject` at `0x1400201b8`
- `ntoskrnl!ObfDereferenceObject` at `0x140020276`
- `ntoskrnl!ObfDereferenceObject` at `0x140020177`
- `ntoskrnl!ObfDereferenceObject` at `0x1400201b8`
- `ntoskrnl!ObfDereferenceObject` at `0x140020276`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ff91`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ff91`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020064`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020143`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020064`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140020143`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14001fd89`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14001fd89`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x140020030`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x140020030`
- `watchdog!WdLogSingleEntry0` at `0x1400202ab`
- `watchdog!WdLogSingleEntry0` at `0x1400202ab`

## pseudocode

```c
__int64 __fastcall NtNotifyPresentToCompositionSurface(HANDLE Handle, char *Src)
{
  NTSTATUS v4; // edi
  PVOID v5; // r12
  _OWORD *v6; // rax
  _OWORD *v7; // rcx
  __int64 v8; // rdx
  _OWORD *v9; // rax
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  void (__fastcall ***v12)(_QWORD); // rsi
  _QWORD *v13; // r15
  struct DXGSESSIONDATA *SessionData; // rax
  void (__fastcall ***v15)(_QWORD); // r14
  _QWORD *v16; // r14
  _QWORD *v18; // r13
  _QWORD *i; // rcx
  _BYTE *v20; // r14
  int v21; // edi
  __int64 v22; // rax
  _QWORD *v23; // r14
  __int64 v24; // r12
  HANDLE CurrentThreadId; // rax
  _QWORD *v26; // rcx
  _OWORD *v27; // rax
  _OWORD *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // [rsp+50h] [rbp-CC8h] BYREF
  PVOID Object; // [rsp+58h] [rbp-CC0h] BYREF
  NTSTATUS v32; // [rsp+60h] [rbp-CB8h]
  PVOID v33; // [rsp+68h] [rbp-CB0h]
  HANDLE v34; // [rsp+70h] [rbp-CA8h]
  _BYTE v35[1064]; // [rsp+78h] [rbp-CA0h] BYREF
  _BYTE v36[1056]; // [rsp+4A0h] [rbp-878h] BYREF
  _QWORD v37[132]; // [rsp+8C0h] [rbp-458h] BYREF

  v34 = Handle;
  v4 = 0;
  memset(v37, 0, sizeof(v37));
  v5 = 0;
  v33 = 0;
  if ( Src )
  {
    if ( (unsigned __int8)PsGetCurrentThreadPreviousMode() == 1 )
    {
      LODWORD(v30) = 0;
      RtlCopyFromUser(&v30, Src, 4u);
      if ( (_DWORD)v30 != 2 )
        v4 = -1073741811;
      v32 = v4;
      memset(v35, 0, 0x420u);
      RtlCopyFromUser(v35, Src + 16, 0x420u);
      v6 = v36;
      v7 = v35;
      v8 = 8;
      do
      {
        *v6 = *v7;
        v6[1] = v7[1];
        v6[2] = v7[2];
        v6[3] = v7[3];
        v6[4] = v7[4];
        v6[5] = v7[5];
        v6[6] = v7[6];
        v6[7] = v7[7];
        v6 += 8;
        v7 += 8;
        --v8;
      }
      while ( v8 );
      *v6 = *v7;
      v6[1] = v7[1];
      v9 = v37;
      v10 = v36;
      v11 = 8;
      do
      {
        *v9 = *v10;
        v9[1] = v10[1];
        v9[2] = v10[2];
        v9[3] = v10[3];
        v9[4] = v10[4];
        v9[5] = v10[5];
        v9[6] = v10[6];
        v9[7] = v10[7];
        v9 += 8;
        v10 += 8;
        --v11;
      }
      while ( v11 );
      *v9 = *v10;
      v9[1] = v10[1];
      Object = 0;
      RtlCopyFromUser(&Object, Src + 8, 8u);
      v5 = Object;
      v33 = Object;
    }
    else
    {
      v27 = Src + 16;
      v28 = v37;
      v29 = 8;
      do
      {
        *v28 = *v27;
        v28[1] = v27[1];
        v28[2] = v27[2];
        v28[3] = v27[3];
        v28[4] = v27[4];
        v28[5] = v27[5];
        v28[6] = v27[6];
        v28[7] = v27[7];
        v28 += 8;
        v27 += 8;
        --v29;
      }
      while ( v29 );
      *v28 = *v27;
      v28[1] = v27[1];
      v5 = (PVOID)*((_QWORD *)Src + 1);
      v4 = -1073741811;
      if ( *(_DWORD *)Src == 2 )
        v4 = 0;
    }
  }
  v12 = 0;
  v13 = 0;
  KeEnterCriticalRegion();
  if ( v4 >= 0 )
  {
    v4 = -1073741823;
    if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2650;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
    }
    SessionData = DXGGLOBAL::GetSessionData(*(DXGGLOBAL **)&DXGGLOBAL::m_pGlobal);
    if ( SessionData )
    {
      v15 = (void (__fastcall ***)(_QWORD))*((_QWORD *)SessionData + 2344);
      if ( v15 )
      {
        (**v15)(v15);
        v12 = v15;
        v4 = 0;
      }
    }
    if ( v4 >= 0 )
    {
      v16 = 0;
      Object = 0;
      v4 = ObReferenceObjectByHandle(Handle, 2u, g_pDxgkCompositionObjectType, 1, &Object, 0);
      if ( v4 < 0
        || (v16 = Object, (***((unsigned int (__fastcall ****)(_QWORD))Object + 2))(*((_QWORD *)Object + 2)) == 1) )
      {
        if ( v4 < 0 )
          goto LABEL_22;
        v13 = v16;
      }
      else
      {
        ObfDereferenceObject(v16);
        v4 = -1073741788;
      }
      if ( v4 >= 0 )
      {
        v18 = 0;
        v4 = ObReferenceObjectByPointer(v13, 3u, g_pDxgkCompositionObjectType, 0);
        if ( v4 >= 0 )
        {
          v18 = v13 + 5;
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v13 + 6, 0);
          v13[7] = PsGetCurrentThreadId();
          v4 = 0;
        }
        if ( v4 < 0 )
        {
          v24 = 0;
        }
        else
        {
          if ( *((_DWORD *)v18 + 30) )
          {
            for ( i = (_QWORD *)v18[13]; i != v18 + 13; i = (_QWORD *)*i )
            {
              v20 = i - 3;
              if ( (PVOID)*(i - 1) == v5 )
              {
                v21 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)v20 + 8LL))(i - 3);
                v22 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v20 + 32LL))(v20);
                v30 = v22;
                if ( v21 == 2 && v20[40] )
                {
                  v23 = 0;
                  if ( *((_DWORD *)v18 + 30) && *(_BYTE *)(v18[13] - 24LL + 40) )
                    v23 = (_QWORD *)(v18[13] - 24LL);
                  if ( v23 && (PVOID)v23[2] == v5 && (*(unsigned int (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23) == 2 )
                  {
                    v4 = 0;
                    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 64LL))(v23, v37);
                  }
                  else
                  {
                    v4 = -1073741811;
                  }
                  v24 = v30;
                }
                else
                {
                  v24 = v22;
                  v4 = -1073741811;
                }
                goto LABEL_42;
              }
            }
          }
          v24 = 0;
          v4 = -1073741811;
LABEL_42:
          CurrentThreadId = PsGetCurrentThreadId();
          v26 = v18 + 1;
          if ( CurrentThreadId == (HANDLE)v18[2] )
          {
            v18[2] = 0;
            ExReleasePushLockExclusiveEx(v26, 0);
          }
          else
          {
            ExReleasePushLockSharedEx(v26, 0);
          }
          KeLeaveCriticalRegion();
          ObfDereferenceObject(v18 - 5);
        }
        if ( v4 >= 0 )
        {
          if ( ((unsigned int (__fastcall *)(_QWORD))(*v12)[19])(v12) )
          {
            v4 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD *))(*v12)[14])(v12, v13);
          }
          else
          {
            v4 = -1071775730;
            if ( v24 )
              v4 = -1071775733;
          }
        }
        ObfDereferenceObject(v13);
      }
    }
  }
LABEL_22:
  if ( v12 )
    (*v12)[1](v12);
  KeLeaveCriticalRegion();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001fd20  mov     [rsp+arg_10], rbx
0x14001fd25  mov     [rsp+arg_18], rsi
0x14001fd2a  push    rdi
0x14001fd2b  push    r12
0x14001fd2d  push    r13
0x14001fd2f  push    r14
0x14001fd31  push    r15
0x14001fd33  sub     rsp, 0CF0h
0x14001fd3a  mov     rax, cs:__security_cookie
0x14001fd41  xor     rax, rsp
0x14001fd44  mov     [rsp+0D18h+var_38], rax
0x14001fd4c  mov     rsi, rdx
0x14001fd4f  mov     r13, rcx
0x14001fd52  mov     [rsp+0D18h+var_CA8], rcx
0x14001fd57  xor     ebx, ebx
0x14001fd59  mov     edi, ebx
0x14001fd5b  xor     edx, edx; Val
0x14001fd5d  mov     r8d, 418h; Size
0x14001fd63  lea     rcx, [rsp+0D18h+var_450]; void *
0x14001fd6b  call    memset
0x14001fd70  mov     [rsp+0D18h+var_458], rbx
0x14001fd78  mov     r12d, ebx
0x14001fd7b  mov     [rsp+0D18h+var_CB0], rbx
0x14001fd80  test    rsi, rsi
0x14001fd83  jz      loc_14001FF07
0x14001fd89  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14001fd90  nop     dword ptr [rax+rax+00h]
0x14001fd95  cmp     al, 1
0x14001fd97  jnz     loc_1400201E3
0x14001fd9d  mov     dword ptr [rsp+0D18h+var_CC8], ebx
0x14001fda1  mov     r8d, 4; Size
0x14001fda7  mov     rdx, rsi; Src
0x14001fdaa  lea     rcx, [rsp+0D18h+var_CC8]; void *
0x14001fdaf  call    RtlCopyFromUser
0x14001fdb4  mov     r14d, 0C000000Dh
0x14001fdba  cmp     dword ptr [rsp+0D18h+var_CC8], 2
0x14001fdbf  cmovnz  edi, r14d
0x14001fdc3  mov     [rsp+0D18h+var_CB8], edi
0x14001fdc7  xor     edx, edx; Val
0x14001fdc9  mov     r8d, 420h; Size
0x14001fdcf  lea     rcx, [rsp+0D18h+var_CA0]; void *
0x14001fdd4  call    memset
0x14001fdd9  lea     rdx, [rsi+10h]; Src
0x14001fddd  mov     r8d, 420h; Size
0x14001fde3  lea     rcx, [rsp+0D18h+var_CA0]; void *
0x14001fde8  call    RtlCopyFromUser
0x14001fded  lea     rax, [rsp+0D18h+var_878]
0x14001fdf5  lea     rcx, [rsp+0D18h+var_CA0]
0x14001fdfa  mov     r8d, 8; Size
0x14001fe00  mov     edx, r8d
0x14001fe03  movups  xmm0, xmmword ptr [rcx]
0x14001fe06  movups  xmmword ptr [rax], xmm0
0x14001fe09  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fe0d  movups  xmmword ptr [rax+10h], xmm1
0x14001fe11  movups  xmm0, xmmword ptr [rcx+20h]
0x14001fe15  movups  xmmword ptr [rax+20h], xmm0
0x14001fe19  movups  xmm1, xmmword ptr [rcx+30h]
0x14001fe1d  movups  xmmword ptr [rax+30h], xmm1
0x14001fe21  movups  xmm0, xmmword ptr [rcx+40h]
0x14001fe25  movups  xmmword ptr [rax+40h], xmm0
0x14001fe29  movups  xmm1, xmmword ptr [rcx+50h]
0x14001fe2d  movups  xmmword ptr [rax+50h], xmm1
0x14001fe31  movups  xmm0, xmmword ptr [rcx+60h]
0x14001fe35  movups  xmmword ptr [rax+60h], xmm0
0x14001fe39  movups  xmm1, xmmword ptr [rcx+70h]
0x14001fe3d  movups  xmmword ptr [rax+70h], xmm1
0x14001fe41  lea     rax, [rax+80h]
0x14001fe48  lea     rcx, [rcx+80h]
0x14001fe4f  sub     rdx, 1
0x14001fe53  jnz     short loc_14001FE03
0x14001fe55  movups  xmm0, xmmword ptr [rcx]
0x14001fe58  movups  xmmword ptr [rax], xmm0
0x14001fe5b  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fe5f  movups  xmmword ptr [rax+10h], xmm1
0x14001fe63  lea     rax, [rsp+0D18h+var_458]
0x14001fe6b  lea     rcx, [rsp+0D18h+var_878]
0x14001fe73  mov     rdx, r8
0x14001fe76  movups  xmm0, xmmword ptr [rcx]
0x14001fe79  movups  xmmword ptr [rax], xmm0
0x14001fe7c  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fe80  movups  xmmword ptr [rax+10h], xmm1
0x14001fe84  movups  xmm0, xmmword ptr [rcx+20h]
0x14001fe88  movups  xmmword ptr [rax+20h], xmm0
0x14001fe8c  movups  xmm1, xmmword ptr [rcx+30h]
0x14001fe90  movups  xmmword ptr [rax+30h], xmm1
0x14001fe94  movups  xmm0, xmmword ptr [rcx+40h]
0x14001fe98  movups  xmmword ptr [rax+40h], xmm0
0x14001fe9c  movups  xmm1, xmmword ptr [rcx+50h]
0x14001fea0  movups  xmmword ptr [rax+50h], xmm1
0x14001fea4  movups  xmm0, xmmword ptr [rcx+60h]
0x14001fea8  movups  xmmword ptr [rax+60h], xmm0
0x14001feac  movups  xmm1, xmmword ptr [rcx+70h]
0x14001feb0  movups  xmmword ptr [rax+70h], xmm1
0x14001feb4  lea     rax, [rax+80h]
0x14001febb  lea     rcx, [rcx+80h]
0x14001fec2  sub     rdx, 1
0x14001fec6  jnz     short loc_14001FE76
0x14001fec8  movups  xmm0, xmmword ptr [rcx]
0x14001fecb  movups  xmmword ptr [rax], xmm0
0x14001fece  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fed2  movups  xmmword ptr [rax+10h], xmm1
0x14001fed6  mov     [rsp+0D18h+var_CC0], rbx
0x14001fedb  lea     rdx, [rsi+8]; Src
0x14001fedf  lea     rcx, [rsp+0D18h+var_CC0]; void *
0x14001fee4  call    RtlCopyFromUser
0x14001fee9  mov     r12, [rsp+0D18h+var_CC0]
0x14001feee  mov     [rsp+0D18h+var_CB0], r12
0x14001fef3  jmp     short loc_14001FF07
0x14001fef5  mov     edi, eax
0x14001fef7  mov     [rsp+0D18h+var_CB8], eax
0x14001fefb  xor     ebx, ebx
0x14001fefd  mov     r12, [rsp+0D18h+var_CB0]
0x14001ff02  mov     r13, [rsp+0D18h+var_CA8]
0x14001ff07  mov     rsi, rbx
0x14001ff0a  mov     r15, rbx
0x14001ff0d  call    cs:__imp_KeEnterCriticalRegion
0x14001ff14  nop     dword ptr [rax+rax+00h]
0x14001ff19  test    edi, edi
0x14001ff1b  js      loc_14001FFCB
0x14001ff21  mov     edi, 0C0000001h
0x14001ff26  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14001ff2e  jz      loc_1400202A6
0x14001ff34  mov     rcx, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; this
0x14001ff3b  call    ?GetSessionData@DXGGLOBAL@@QEAAPEAVDXGSESSIONDATA@@XZ; DXGGLOBAL::GetSessionData(void)
0x14001ff40  test    rax, rax
0x14001ff43  jz      short loc_14001FF64
0x14001ff45  mov     r14, [rax+4940h]
0x14001ff4c  test    r14, r14
0x14001ff4f  jz      short loc_14001FF64
0x14001ff51  mov     rax, [r14]
0x14001ff54  mov     rax, [rax]
0x14001ff57  mov     rcx, r14
0x14001ff5a  call    _guard_dispatch_icall
0x14001ff5f  mov     rsi, r14
0x14001ff62  mov     edi, ebx
0x14001ff64  test    edi, edi
0x14001ff66  js      short loc_14001FFCB
0x14001ff68  mov     r14, rbx
0x14001ff6b  mov     r8, cs:g_pDxgkCompositionObjectType; ObjectType
0x14001ff72  mov     [rsp+0D18h+var_CC0], rbx
0x14001ff77  mov     [rsp+0D18h+HandleInformation], rbx; HandleInformation
0x14001ff7c  lea     rax, [rsp+0D18h+var_CC0]
0x14001ff81  mov     [rsp+0D18h+Object], rax; Object
0x14001ff86  mov     r9b, 1; AccessMode
0x14001ff89  mov     edx, 2; DesiredAccess
0x14001ff8e  mov     rcx, r13; Handle
0x14001ff91  call    cs:__imp_ObReferenceObjectByHandle
0x14001ff98  nop     dword ptr [rax+rax+00h]
0x14001ff9d  mov     edi, eax
0x14001ff9f  test    eax, eax
0x14001ffa1  js      short loc_14001FFC0
0x14001ffa3  mov     r14, [rsp+0D18h+var_CC0]
0x14001ffa8  mov     rcx, [r14+10h]
0x14001ffac  mov     rax, [rcx]
0x14001ffaf  mov     rax, [rax]
0x14001ffb2  call    _guard_dispatch_icall
0x14001ffb7  cmp     eax, 1
0x14001ffba  jnz     loc_140020273
0x14001ffc0  test    edi, edi
0x14001ffc2  js      short loc_14001FFCB
0x14001ffc4  mov     r15, r14
0x14001ffc7  test    edi, edi
0x14001ffc9  jns     short loc_14002001B
0x14001ffcb  test    rsi, rsi
0x14001ffce  jz      short loc_14001FFDF
0x14001ffd0  mov     rax, [rsi]
0x14001ffd3  mov     rax, [rax+8]
0x14001ffd7  mov     rcx, rsi
0x14001ffda  call    _guard_dispatch_icall
0x14001ffdf  call    cs:__imp_KeLeaveCriticalRegion
0x14001ffe6  nop     dword ptr [rax+rax+00h]
0x14001ffeb  mov     eax, edi
0x14001ffed  mov     rcx, [rsp+0D18h+var_38]
0x14001fff5  xor     rcx, rsp; StackCookie
0x14001fff8  call    __security_check_cookie
0x14001fffd  lea     r11, [rsp+0D18h+var_28]
0x140020005  mov     rbx, [r11+40h]
0x140020009  mov     rsi, [r11+48h]
0x14002000d  mov     rsp, r11
0x140020010  pop     r15
0x140020012  pop     r14
0x140020014  pop     r13
0x140020016  pop     r12
0x140020018  pop     rdi
0x140020019  retn
0x14002001b  mov     r13, rbx
0x14002001e  xor     r9d, r9d; AccessMode
0x140020021  mov     r8, cs:g_pDxgkCompositionObjectType; ObjectType
0x140020028  mov     edx, 3; DesiredAccess
0x14002002d  mov     rcx, r15; Object
0x140020030  call    cs:__imp_ObReferenceObjectByPointer
0x140020037  nop     dword ptr [rax+rax+00h]
0x14002003c  mov     edi, eax
0x14002003e  test    eax, eax
0x140020040  js      short loc_140020076
0x140020042  lea     r13, [r15+28h]
0x140020046  call    cs:__imp_KeEnterCriticalRegion
0x14002004d  nop     dword ptr [rax+rax+00h]
0x140020052  xor     edx, edx
0x140020054  lea     rcx, [r13+8]
0x140020058  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002005f  nop     dword ptr [rax+rax+00h]
0x140020064  call    cs:__imp_PsGetCurrentThreadId
0x14002006b  nop     dword ptr [rax+rax+00h]
0x140020070  mov     [r13+10h], rax
0x140020074  mov     edi, ebx
0x140020076  test    edi, edi
0x140020078  js      loc_1400202FC
0x14002007e  cmp     dword ptr [r13+78h], 0
0x140020083  jbe     loc_140020299
0x140020089  lea     rax, [r13+68h]
0x14002008d  mov     rcx, [rax]
0x140020090  cmp     rcx, rax
0x140020093  jz      loc_140020299
0x140020099  lea     r14, [rcx-18h]
0x14002009d  cmp     [r14+10h], r12
0x1400200a1  jnz     loc_1400201DB
0x1400200a7  mov     rax, [r14]
0x1400200aa  mov     rax, [rax+8]
0x1400200ae  mov     rcx, r14
0x1400200b1  call    _guard_dispatch_icall
0x1400200b6  mov     edi, eax
0x1400200b8  mov     rcx, [r14]
0x1400200bb  mov     rax, [rcx+20h]
0x1400200bf  mov     rcx, r14
0x1400200c2  call    _guard_dispatch_icall
0x1400200c7  mov     [rsp+0D18h+var_CC8], rax
0x1400200cc  cmp     edi, 2
0x1400200cf  jnz     loc_14002028C
0x1400200d5  cmp     byte ptr [r14+28h], 0
0x1400200da  jz      loc_14002028C
0x1400200e0  mov     r14, rbx
0x1400200e3  cmp     dword ptr [r13+78h], 0
0x1400200e8  jbe     short loc_1400200FA
0x1400200ea  mov     rcx, [r13+68h]
0x1400200ee  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1400200f2  cmp     byte ptr [rcx+28h], 0
0x1400200f6  cmovnz  r14, rcx
0x1400200fa  test    r14, r14
0x1400200fd  jz      loc_140020269
0x140020103  cmp     [r14+10h], r12
0x140020107  jnz     loc_140020269
0x14002010d  mov     rax, [r14]
0x140020110  mov     rax, [rax+8]
0x140020114  mov     rcx, r14
0x140020117  call    _guard_dispatch_icall
0x14002011c  cmp     eax, 2
0x14002011f  jnz     loc_140020269
0x140020125  mov     edi, ebx
0x140020127  mov     rax, [r14]
0x14002012a  mov     rax, [rax+40h]
0x14002012e  lea     rdx, [rsp+0D18h+var_458]
0x140020136  mov     rcx, r14
0x140020139  call    _guard_dispatch_icall
0x14002013e  mov     r12, [rsp+0D18h+var_CC8]
0x140020143  call    cs:__imp_PsGetCurrentThreadId
0x14002014a  nop     dword ptr [rax+rax+00h]
0x14002014f  xor     edx, edx
0x140020151  lea     rcx, [r13+8]
0x140020155  cmp     rax, [r13+10h]
0x140020159  jz      short loc_1400201C9
0x14002015b  call    cs:__imp_ExReleasePushLockSharedEx
0x140020162  nop     dword ptr [rax+rax+00h]
0x140020167  call    cs:__imp_KeLeaveCriticalRegion
0x14002016e  nop     dword ptr [rax+rax+00h]
0x140020173  lea     rcx, [r13-28h]; Object
0x140020177  call    cs:__imp_ObfDereferenceObject
0x14002017e  nop     dword ptr [rax+rax+00h]
0x140020183  test    edi, edi
0x140020185  js      short loc_1400201B5
0x140020187  mov     rax, [rsi]
0x14002018a  mov     rax, [rax+98h]
0x140020191  mov     rcx, rsi
0x140020194  call    _guard_dispatch_icall
0x140020199  test    eax, eax
0x14002019b  jz      loc_140020304
0x1400201a1  mov     rax, [rsi]
0x1400201a4  mov     rax, [rax+70h]
0x1400201a8  mov     rdx, r15
0x1400201ab  mov     rcx, rsi
0x1400201ae  call    _guard_dispatch_icall
0x1400201b3  mov     edi, eax
0x1400201b5  mov     rcx, r15; Object
0x1400201b8  call    cs:__imp_ObfDereferenceObject
0x1400201bf  nop     dword ptr [rax+rax+00h]
0x1400201c4  jmp     loc_14001FFCB
0x1400201c9  mov     [r13+10h], rbx
0x1400201cd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400201d4  nop     dword ptr [rax+rax+00h]
0x1400201d9  jmp     short loc_140020167
0x1400201db  mov     rcx, [rcx]
0x1400201de  jmp     loc_140020090
0x1400201e3  lea     rax, [rsi+10h]
0x1400201e7  lea     rcx, [rsp+0D18h+var_458]
0x1400201ef  mov     r8d, 8
0x1400201f5  movups  xmm0, xmmword ptr [rax]
0x1400201f8  movups  xmmword ptr [rcx], xmm0
0x1400201fb  movups  xmm1, xmmword ptr [rax+10h]
0x1400201ff  movups  xmmword ptr [rcx+10h], xmm1
0x140020203  movups  xmm0, xmmword ptr [rax+20h]
  ... truncated ...
```
