# NtNotifyPresentToCompositionSurface

- ea: `0x14001fb50`
- end: `0x140020149`
- name: `NtNotifyPresentToCompositionSurface`
- size: `1529`
- prototype: `__int64 __fastcall(HANDLE Handle, void *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1403bfc50`

## callees

- `0x14001b890`
- `0x14001fb50`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140323280`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001fe88`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001fe88`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fd3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fe76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fd3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fe76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fe0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ff97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fe0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ff97`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001fffd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001fffd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001ff8b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001ff8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ffa7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ffe8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400200a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ffa7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ffe8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400200a6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001fdc1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001fdc1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fe94`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ff73`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fe94`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ff73`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14001fbb9`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14001fbb9`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14001fe60`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14001fe60`
- `watchdog!WdLogSingleEntry0` at `0x1400200db`
- `watchdog!WdLogSingleEntry0` at `0x1400200db`

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
0x14001fb50  mov     [rsp+arg_10], rbx
0x14001fb55  mov     [rsp+arg_18], rsi
0x14001fb5a  push    rdi
0x14001fb5b  push    r12
0x14001fb5d  push    r13
0x14001fb5f  push    r14
0x14001fb61  push    r15
0x14001fb63  sub     rsp, 0CF0h
0x14001fb6a  mov     rax, cs:__security_cookie
0x14001fb71  xor     rax, rsp
0x14001fb74  mov     [rsp+0D18h+var_38], rax
0x14001fb7c  mov     rsi, rdx
0x14001fb7f  mov     r13, rcx
0x14001fb82  mov     [rsp+0D18h+var_CA8], rcx
0x14001fb87  xor     ebx, ebx
0x14001fb89  mov     edi, ebx
0x14001fb8b  xor     edx, edx; Val
0x14001fb8d  mov     r8d, 418h; Size
0x14001fb93  lea     rcx, [rsp+0D18h+var_450]; void *
0x14001fb9b  call    memset
0x14001fba0  mov     [rsp+0D18h+var_458], rbx
0x14001fba8  mov     r12d, ebx
0x14001fbab  mov     [rsp+0D18h+var_CB0], rbx
0x14001fbb0  test    rsi, rsi
0x14001fbb3  jz      loc_14001FD37
0x14001fbb9  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14001fbc0  nop     dword ptr [rax+rax+00h]
0x14001fbc5  cmp     al, 1
0x14001fbc7  jnz     loc_140020013
0x14001fbcd  mov     dword ptr [rsp+0D18h+var_CC8], ebx
0x14001fbd1  mov     r8d, 4; Size
0x14001fbd7  mov     rdx, rsi; Src
0x14001fbda  lea     rcx, [rsp+0D18h+var_CC8]; void *
0x14001fbdf  call    RtlCopyFromUser
0x14001fbe4  mov     r14d, 0C000000Dh
0x14001fbea  cmp     dword ptr [rsp+0D18h+var_CC8], 2
0x14001fbef  cmovnz  edi, r14d
0x14001fbf3  mov     [rsp+0D18h+var_CB8], edi
0x14001fbf7  xor     edx, edx; Val
0x14001fbf9  mov     r8d, 420h; Size
0x14001fbff  lea     rcx, [rsp+0D18h+var_CA0]; void *
0x14001fc04  call    memset
0x14001fc09  lea     rdx, [rsi+10h]; Src
0x14001fc0d  mov     r8d, 420h; Size
0x14001fc13  lea     rcx, [rsp+0D18h+var_CA0]; void *
0x14001fc18  call    RtlCopyFromUser
0x14001fc1d  lea     rax, [rsp+0D18h+var_878]
0x14001fc25  lea     rcx, [rsp+0D18h+var_CA0]
0x14001fc2a  mov     r8d, 8; Size
0x14001fc30  mov     edx, r8d
0x14001fc33  movups  xmm0, xmmword ptr [rcx]
0x14001fc36  movups  xmmword ptr [rax], xmm0
0x14001fc39  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fc3d  movups  xmmword ptr [rax+10h], xmm1
0x14001fc41  movups  xmm0, xmmword ptr [rcx+20h]
0x14001fc45  movups  xmmword ptr [rax+20h], xmm0
0x14001fc49  movups  xmm1, xmmword ptr [rcx+30h]
0x14001fc4d  movups  xmmword ptr [rax+30h], xmm1
0x14001fc51  movups  xmm0, xmmword ptr [rcx+40h]
0x14001fc55  movups  xmmword ptr [rax+40h], xmm0
0x14001fc59  movups  xmm1, xmmword ptr [rcx+50h]
0x14001fc5d  movups  xmmword ptr [rax+50h], xmm1
0x14001fc61  movups  xmm0, xmmword ptr [rcx+60h]
0x14001fc65  movups  xmmword ptr [rax+60h], xmm0
0x14001fc69  movups  xmm1, xmmword ptr [rcx+70h]
0x14001fc6d  movups  xmmword ptr [rax+70h], xmm1
0x14001fc71  lea     rax, [rax+80h]
0x14001fc78  lea     rcx, [rcx+80h]
0x14001fc7f  sub     rdx, 1
0x14001fc83  jnz     short loc_14001FC33
0x14001fc85  movups  xmm0, xmmword ptr [rcx]
0x14001fc88  movups  xmmword ptr [rax], xmm0
0x14001fc8b  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fc8f  movups  xmmword ptr [rax+10h], xmm1
0x14001fc93  lea     rax, [rsp+0D18h+var_458]
0x14001fc9b  lea     rcx, [rsp+0D18h+var_878]
0x14001fca3  mov     rdx, r8
0x14001fca6  movups  xmm0, xmmword ptr [rcx]
0x14001fca9  movups  xmmword ptr [rax], xmm0
0x14001fcac  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fcb0  movups  xmmword ptr [rax+10h], xmm1
0x14001fcb4  movups  xmm0, xmmword ptr [rcx+20h]
0x14001fcb8  movups  xmmword ptr [rax+20h], xmm0
0x14001fcbc  movups  xmm1, xmmword ptr [rcx+30h]
0x14001fcc0  movups  xmmword ptr [rax+30h], xmm1
0x14001fcc4  movups  xmm0, xmmword ptr [rcx+40h]
0x14001fcc8  movups  xmmword ptr [rax+40h], xmm0
0x14001fccc  movups  xmm1, xmmword ptr [rcx+50h]
0x14001fcd0  movups  xmmword ptr [rax+50h], xmm1
0x14001fcd4  movups  xmm0, xmmword ptr [rcx+60h]
0x14001fcd8  movups  xmmword ptr [rax+60h], xmm0
0x14001fcdc  movups  xmm1, xmmword ptr [rcx+70h]
0x14001fce0  movups  xmmword ptr [rax+70h], xmm1
0x14001fce4  lea     rax, [rax+80h]
0x14001fceb  lea     rcx, [rcx+80h]
0x14001fcf2  sub     rdx, 1
0x14001fcf6  jnz     short loc_14001FCA6
0x14001fcf8  movups  xmm0, xmmword ptr [rcx]
0x14001fcfb  movups  xmmword ptr [rax], xmm0
0x14001fcfe  movups  xmm1, xmmword ptr [rcx+10h]
0x14001fd02  movups  xmmword ptr [rax+10h], xmm1
0x14001fd06  mov     [rsp+0D18h+var_CC0], rbx
0x14001fd0b  lea     rdx, [rsi+8]; Src
0x14001fd0f  lea     rcx, [rsp+0D18h+var_CC0]; void *
0x14001fd14  call    RtlCopyFromUser
0x14001fd19  mov     r12, [rsp+0D18h+var_CC0]
0x14001fd1e  mov     [rsp+0D18h+var_CB0], r12
0x14001fd23  jmp     short loc_14001FD37
0x14001fd25  mov     edi, eax
0x14001fd27  mov     [rsp+0D18h+var_CB8], eax
0x14001fd2b  xor     ebx, ebx
0x14001fd2d  mov     r12, [rsp+0D18h+var_CB0]
0x14001fd32  mov     r13, [rsp+0D18h+var_CA8]
0x14001fd37  mov     rsi, rbx
0x14001fd3a  mov     r15, rbx
0x14001fd3d  call    cs:__imp_KeEnterCriticalRegion
0x14001fd44  nop     dword ptr [rax+rax+00h]
0x14001fd49  test    edi, edi
0x14001fd4b  js      loc_14001FDFB
0x14001fd51  mov     edi, 0C0000001h
0x14001fd56  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14001fd5e  jz      loc_1400200D6
0x14001fd64  mov     rcx, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; this
0x14001fd6b  call    ?GetSessionData@DXGGLOBAL@@QEAAPEAVDXGSESSIONDATA@@XZ; DXGGLOBAL::GetSessionData(void)
0x14001fd70  test    rax, rax
0x14001fd73  jz      short loc_14001FD94
0x14001fd75  mov     r14, [rax+4940h]
0x14001fd7c  test    r14, r14
0x14001fd7f  jz      short loc_14001FD94
0x14001fd81  mov     rax, [r14]
0x14001fd84  mov     rax, [rax]
0x14001fd87  mov     rcx, r14
0x14001fd8a  call    _guard_dispatch_icall
0x14001fd8f  mov     rsi, r14
0x14001fd92  mov     edi, ebx
0x14001fd94  test    edi, edi
0x14001fd96  js      short loc_14001FDFB
0x14001fd98  mov     r14, rbx
0x14001fd9b  mov     r8, cs:g_pDxgkCompositionObjectType; ObjectType
0x14001fda2  mov     [rsp+0D18h+var_CC0], rbx
0x14001fda7  mov     [rsp+0D18h+HandleInformation], rbx; HandleInformation
0x14001fdac  lea     rax, [rsp+0D18h+var_CC0]
0x14001fdb1  mov     [rsp+0D18h+Object], rax; Object
0x14001fdb6  mov     r9b, 1; AccessMode
0x14001fdb9  mov     edx, 2; DesiredAccess
0x14001fdbe  mov     rcx, r13; Handle
0x14001fdc1  call    cs:__imp_ObReferenceObjectByHandle
0x14001fdc8  nop     dword ptr [rax+rax+00h]
0x14001fdcd  mov     edi, eax
0x14001fdcf  test    eax, eax
0x14001fdd1  js      short loc_14001FDF0
0x14001fdd3  mov     r14, [rsp+0D18h+var_CC0]
0x14001fdd8  mov     rcx, [r14+10h]
0x14001fddc  mov     rax, [rcx]
0x14001fddf  mov     rax, [rax]
0x14001fde2  call    _guard_dispatch_icall
0x14001fde7  cmp     eax, 1
0x14001fdea  jnz     loc_1400200A3
0x14001fdf0  test    edi, edi
0x14001fdf2  js      short loc_14001FDFB
0x14001fdf4  mov     r15, r14
0x14001fdf7  test    edi, edi
0x14001fdf9  jns     short loc_14001FE4B
0x14001fdfb  test    rsi, rsi
0x14001fdfe  jz      short loc_14001FE0F
0x14001fe00  mov     rax, [rsi]
0x14001fe03  mov     rax, [rax+8]
0x14001fe07  mov     rcx, rsi
0x14001fe0a  call    _guard_dispatch_icall
0x14001fe0f  call    cs:__imp_KeLeaveCriticalRegion
0x14001fe16  nop     dword ptr [rax+rax+00h]
0x14001fe1b  mov     eax, edi
0x14001fe1d  mov     rcx, [rsp+0D18h+var_38]
0x14001fe25  xor     rcx, rsp; StackCookie
0x14001fe28  call    __security_check_cookie
0x14001fe2d  lea     r11, [rsp+0D18h+var_28]
0x14001fe35  mov     rbx, [r11+40h]
0x14001fe39  mov     rsi, [r11+48h]
0x14001fe3d  mov     rsp, r11
0x14001fe40  pop     r15
0x14001fe42  pop     r14
0x14001fe44  pop     r13
0x14001fe46  pop     r12
0x14001fe48  pop     rdi
0x14001fe49  retn
0x14001fe4b  mov     r13, rbx
0x14001fe4e  xor     r9d, r9d; AccessMode
0x14001fe51  mov     r8, cs:g_pDxgkCompositionObjectType; ObjectType
0x14001fe58  mov     edx, 3; DesiredAccess
0x14001fe5d  mov     rcx, r15; Object
0x14001fe60  call    cs:__imp_ObReferenceObjectByPointer
0x14001fe67  nop     dword ptr [rax+rax+00h]
0x14001fe6c  mov     edi, eax
0x14001fe6e  test    eax, eax
0x14001fe70  js      short loc_14001FEA6
0x14001fe72  lea     r13, [r15+28h]
0x14001fe76  call    cs:__imp_KeEnterCriticalRegion
0x14001fe7d  nop     dword ptr [rax+rax+00h]
0x14001fe82  xor     edx, edx
0x14001fe84  lea     rcx, [r13+8]
0x14001fe88  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001fe8f  nop     dword ptr [rax+rax+00h]
0x14001fe94  call    cs:__imp_PsGetCurrentThreadId
0x14001fe9b  nop     dword ptr [rax+rax+00h]
0x14001fea0  mov     [r13+10h], rax
0x14001fea4  mov     edi, ebx
0x14001fea6  test    edi, edi
0x14001fea8  js      loc_14002012C
0x14001feae  cmp     dword ptr [r13+78h], 0
0x14001feb3  jbe     loc_1400200C9
0x14001feb9  lea     rax, [r13+68h]
0x14001febd  mov     rcx, [rax]
0x14001fec0  cmp     rcx, rax
0x14001fec3  jz      loc_1400200C9
0x14001fec9  lea     r14, [rcx-18h]
0x14001fecd  cmp     [r14+10h], r12
0x14001fed1  jnz     loc_14002000B
0x14001fed7  mov     rax, [r14]
0x14001feda  mov     rax, [rax+8]
0x14001fede  mov     rcx, r14
0x14001fee1  call    _guard_dispatch_icall
0x14001fee6  mov     edi, eax
0x14001fee8  mov     rcx, [r14]
0x14001feeb  mov     rax, [rcx+20h]
0x14001feef  mov     rcx, r14
0x14001fef2  call    _guard_dispatch_icall
0x14001fef7  mov     [rsp+0D18h+var_CC8], rax
0x14001fefc  cmp     edi, 2
0x14001feff  jnz     loc_1400200BC
0x14001ff05  cmp     byte ptr [r14+28h], 0
0x14001ff0a  jz      loc_1400200BC
0x14001ff10  mov     r14, rbx
0x14001ff13  cmp     dword ptr [r13+78h], 0
0x14001ff18  jbe     short loc_14001FF2A
0x14001ff1a  mov     rcx, [r13+68h]
0x14001ff1e  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14001ff22  cmp     byte ptr [rcx+28h], 0
0x14001ff26  cmovnz  r14, rcx
0x14001ff2a  test    r14, r14
0x14001ff2d  jz      loc_140020099
0x14001ff33  cmp     [r14+10h], r12
0x14001ff37  jnz     loc_140020099
0x14001ff3d  mov     rax, [r14]
0x14001ff40  mov     rax, [rax+8]
0x14001ff44  mov     rcx, r14
0x14001ff47  call    _guard_dispatch_icall
0x14001ff4c  cmp     eax, 2
0x14001ff4f  jnz     loc_140020099
0x14001ff55  mov     edi, ebx
0x14001ff57  mov     rax, [r14]
0x14001ff5a  mov     rax, [rax+40h]
0x14001ff5e  lea     rdx, [rsp+0D18h+var_458]
0x14001ff66  mov     rcx, r14
0x14001ff69  call    _guard_dispatch_icall
0x14001ff6e  mov     r12, [rsp+0D18h+var_CC8]
0x14001ff73  call    cs:__imp_PsGetCurrentThreadId
0x14001ff7a  nop     dword ptr [rax+rax+00h]
0x14001ff7f  xor     edx, edx
0x14001ff81  lea     rcx, [r13+8]
0x14001ff85  cmp     rax, [r13+10h]
0x14001ff89  jz      short loc_14001FFF9
0x14001ff8b  call    cs:__imp_ExReleasePushLockSharedEx
0x14001ff92  nop     dword ptr [rax+rax+00h]
0x14001ff97  call    cs:__imp_KeLeaveCriticalRegion
0x14001ff9e  nop     dword ptr [rax+rax+00h]
0x14001ffa3  lea     rcx, [r13-28h]; Object
0x14001ffa7  call    cs:__imp_ObfDereferenceObject
0x14001ffae  nop     dword ptr [rax+rax+00h]
0x14001ffb3  test    edi, edi
0x14001ffb5  js      short loc_14001FFE5
0x14001ffb7  mov     rax, [rsi]
0x14001ffba  mov     rax, [rax+98h]
0x14001ffc1  mov     rcx, rsi
0x14001ffc4  call    _guard_dispatch_icall
0x14001ffc9  test    eax, eax
0x14001ffcb  jz      loc_140020134
0x14001ffd1  mov     rax, [rsi]
0x14001ffd4  mov     rax, [rax+70h]
0x14001ffd8  mov     rdx, r15
0x14001ffdb  mov     rcx, rsi
0x14001ffde  call    _guard_dispatch_icall
0x14001ffe3  mov     edi, eax
0x14001ffe5  mov     rcx, r15; Object
0x14001ffe8  call    cs:__imp_ObfDereferenceObject
0x14001ffef  nop     dword ptr [rax+rax+00h]
0x14001fff4  jmp     loc_14001FDFB
0x14001fff9  mov     [r13+10h], rbx
0x14001fffd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140020004  nop     dword ptr [rax+rax+00h]
0x140020009  jmp     short loc_14001FF97
0x14002000b  mov     rcx, [rcx]
0x14002000e  jmp     loc_14001FEC0
0x140020013  lea     rax, [rsi+10h]
0x140020017  lea     rcx, [rsp+0D18h+var_458]
0x14002001f  mov     r8d, 8
0x140020025  movups  xmm0, xmmword ptr [rax]
0x140020028  movups  xmmword ptr [rcx], xmm0
0x14002002b  movups  xmm1, xmmword ptr [rax+10h]
0x14002002f  movups  xmmword ptr [rcx+10h], xmm1
0x140020033  movups  xmm0, xmmword ptr [rax+20h]
  ... truncated ...
```
