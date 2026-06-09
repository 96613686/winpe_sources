# FrameBufferClientChannel::GetLogonSid(uchar * *,ulong *)

- ea: `0x1800fa32c`
- end: `0x1800fa784`
- name: `?GetLogonSid@FrameBufferClientChannel@@AEAAJPEAPEAEPEAK@Z`
- size: `1112`
- prototype: `__int64 __fastcall(FrameBufferClientChannel *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1802bee10`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800fa32c`
- `0x18012962c`
- `0x18012966c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800fa765`
- `KERNEL32!CloseHandle` at `0x1800fa765`
- `KERNEL32!GetLastError` at `0x1800fa379`
- `KERNEL32!GetLastError` at `0x1800fa461`
- `KERNEL32!GetLastError` at `0x1800fa587`
- `KERNEL32!GetLastError` at `0x1800fa5c0`
- `KERNEL32!GetLastError` at `0x1800fa681`
- `KERNEL32!GetLastError` at `0x1800fa379`
- `KERNEL32!GetLastError` at `0x1800fa461`
- `KERNEL32!GetLastError` at `0x1800fa587`
- `KERNEL32!GetLastError` at `0x1800fa5c0`
- `KERNEL32!GetLastError` at `0x1800fa681`
- `KERNEL32!GetCurrentProcess` at `0x1800fa35c`
- `KERNEL32!GetCurrentProcess` at `0x1800fa35c`
- `ADVAPI32!CopySid` at `0x1800fa677`
- `ADVAPI32!CopySid` at `0x1800fa677`
- `ADVAPI32!GetLengthSid` at `0x1800fa603`
- `ADVAPI32!GetLengthSid` at `0x1800fa603`
- `ADVAPI32!OpenProcessToken` at `0x1800fa36f`
- `ADVAPI32!OpenProcessToken` at `0x1800fa36f`
- `ADVAPI32!GetTokenInformation` at `0x1800fa404`
- `ADVAPI32!GetTokenInformation` at `0x1800fa559`
- `ADVAPI32!GetTokenInformation` at `0x1800fa404`
- `ADVAPI32!GetTokenInformation` at `0x1800fa559`

## pseudocode

```c
__int64 __fastcall FrameBufferClientChannel::GetLogonSid(
        FrameBufferClientChannel *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  unsigned int v7; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // edi
  unsigned int v10; // eax
  unsigned int *v11; // r14
  unsigned int v12; // eax
  unsigned __int8 *v13; // rbp
  signed int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  signed int v17; // eax
  unsigned int i; // ecx
  __int64 v19; // rbx
  unsigned int LengthSid; // esi
  unsigned __int8 *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  int v27; // [rsp+64h] [rbp+Ch]
  void *TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  v27 = HIDWORD(this);
  TokenHandle = 0;
  TokenInformationLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, TokenInformationLength, &TokenInformationLength) )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
          CurrentThreadActivityIdPrefix,
          -2147418113);
      }
      LastError = -2147418113;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        v11 = (unsigned int *)operator new(TokenInformationLength);
        if ( v11 )
        {
          v13 = 0;
          if ( GetTokenInformation(TokenHandle, TokenGroups, v11, TokenInformationLength, &TokenInformationLength) )
          {
            for ( i = 0; i < *v11; ++i )
            {
              v19 = 2LL * i;
              if ( (v11[4 * i + 4] & 0xC0000000) == 0xC0000000 )
              {
                LengthSid = GetLengthSid(*(PSID *)&v11[4 * i + 2]);
                v21 = (unsigned __int8 *)operator new(LengthSid);
                v13 = v21;
                if ( v21 )
                {
                  if ( CopySid(LengthSid, v21, *(PSID *)&v11[2 * v19 + 2]) )
                  {
                    *a2 = v13;
                    v13 = 0;
                    LastError = 0;
                    *a3 = LengthSid;
                  }
                  else
                  {
                    LastError = GetLastError();
                    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        57,
                        WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
                        v23,
                        LastError);
                    }
                    if ( LastError > 0 )
                      LastError = (unsigned __int16)LastError | 0x80070000;
                    if ( LastError >= 0 )
                      LastError = -2147467259;
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      56,
                      WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
                      v22,
                      -2147024882);
                  }
                  LastError = -2147024882;
                }
                goto LABEL_68;
              }
            }
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                58,
                WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
                v24,
                -2147418113);
            }
            LastError = -2147418113;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = GetLastError();
              v15 = v14;
              if ( v14 > 0 )
                v15 = (unsigned __int16)v14 | 0x80070000;
              v16 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                55,
                WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
                v16,
                v15);
            }
            v17 = GetLastError();
            LastError = v17;
            if ( v17 > 0 )
              LastError = (unsigned __int16)v17 | 0x80070000;
          }
LABEL_68:
          operator delete(v11);
          if ( v13 )
            operator delete(v13);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
              v12,
              -2147024882);
          }
          LastError = -2147024882;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          else
            v9 = LastError;
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids, v10, v9);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids, v7, LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800fa32c  mov     rax, rsp
0x1800fa32f  mov     [rax+10h], rbx
0x1800fa333  mov     [rax+18h], rbp
0x1800fa337  mov     [rax+8], rcx
0x1800fa33b  push    rsi
0x1800fa33c  push    rdi
0x1800fa33d  push    r12
0x1800fa33f  push    r14
0x1800fa341  push    r15
0x1800fa343  sub     rsp, 30h
0x1800fa347  mov     r15, r8
0x1800fa34a  mov     qword ptr [rax+20h], 0
0x1800fa352  mov     r12, rdx
0x1800fa355  mov     dword ptr [rax+8], 0
0x1800fa35c  call    cs:__imp_GetCurrentProcess
0x1800fa362  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800fa367  mov     edx, 8; DesiredAccess
0x1800fa36c  mov     rcx, rax; ProcessHandle
0x1800fa36f  call    cs:__imp_OpenProcessToken
0x1800fa375  test    eax, eax
0x1800fa377  jnz     short loc_1800FA3E7
0x1800fa379  call    cs:__imp_GetLastError
0x1800fa37f  mov     ebx, eax
0x1800fa381  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa388  lea     rax, WPP_GLOBAL_Control
0x1800fa38f  cmp     rcx, rax
0x1800fa392  jz      short loc_1800FA3CB
0x1800fa394  test    byte ptr [rcx+1Ch], 8
0x1800fa398  jz      short loc_1800FA3CB
0x1800fa39a  mov     edi, 2
0x1800fa39f  cmp     [rcx+19h], dil
0x1800fa3a3  jb      short loc_1800FA3CB
0x1800fa3a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa3b1  lea     edx, [rdi+31h]
0x1800fa3b4  mov     r9d, eax
0x1800fa3b7  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x1800fa3bb  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa3c2  mov     rcx, [rcx+10h]
0x1800fa3c6  call    WPP_SF_Dd
0x1800fa3cb  test    ebx, ebx
0x1800fa3cd  jle     short loc_1800FA3D8
0x1800fa3cf  movzx   ebx, bx
0x1800fa3d2  or      ebx, 80070000h
0x1800fa3d8  test    ebx, ebx
0x1800fa3da  mov     eax, 80004005h
0x1800fa3df  cmovns  ebx, eax
0x1800fa3e2  jmp     loc_1800FA75B
0x1800fa3e7  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800fa3ec  lea     rax, [rsp+58h+TokenInformationLength]
0x1800fa3f1  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800fa3f6  xor     r8d, r8d; TokenInformation
0x1800fa3f9  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800fa3fe  lea     edi, [r8+2]
0x1800fa402  mov     edx, edi; TokenInformationClass
0x1800fa404  call    cs:__imp_GetTokenInformation
0x1800fa40a  test    eax, eax
0x1800fa40c  jz      short loc_1800FA461
0x1800fa40e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa415  lea     rax, WPP_GLOBAL_Control
0x1800fa41c  cmp     rcx, rax
0x1800fa41f  jz      short loc_1800FA457
0x1800fa421  test    byte ptr [rcx+1Ch], 8
0x1800fa425  jz      short loc_1800FA457
0x1800fa427  cmp     [rcx+19h], dil
0x1800fa42b  jb      short loc_1800FA457
0x1800fa42d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa432  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa439  lea     edx, [rdi+32h]
0x1800fa43c  mov     r9d, eax
0x1800fa43f  mov     dword ptr [rsp+58h+ReturnLength], 8000FFFFh
0x1800fa447  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa44e  mov     rcx, [rcx+10h]
0x1800fa452  call    WPP_SF_Dd
0x1800fa457  mov     ebx, 8000FFFFh
0x1800fa45c  jmp     loc_1800FA75B
0x1800fa461  call    cs:__imp_GetLastError
0x1800fa467  mov     ebx, eax
0x1800fa469  cmp     eax, 7Ah ; 'z'
0x1800fa46c  jz      short loc_1800FA4D9
0x1800fa46e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa475  lea     rax, WPP_GLOBAL_Control
0x1800fa47c  mov     esi, 80070000h
0x1800fa481  cmp     rcx, rax
0x1800fa484  jz      short loc_1800FA4C7
0x1800fa486  test    byte ptr [rcx+1Ch], 8
0x1800fa48a  jz      short loc_1800FA4C7
0x1800fa48c  cmp     [rcx+19h], dil
0x1800fa490  jb      short loc_1800FA4C7
0x1800fa492  test    ebx, ebx
0x1800fa494  jg      short loc_1800FA49A
0x1800fa496  mov     edi, ebx
0x1800fa498  jmp     short loc_1800FA49F
0x1800fa49a  movzx   edi, bx
0x1800fa49d  or      edi, esi
0x1800fa49f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa4ab  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa4b2  mov     edx, 35h ; '5'
0x1800fa4b7  mov     dword ptr [rsp+58h+ReturnLength], edi
0x1800fa4bb  mov     r9d, eax
0x1800fa4be  mov     rcx, [rcx+10h]
0x1800fa4c2  call    WPP_SF_Dd
0x1800fa4c7  test    ebx, ebx
0x1800fa4c9  jle     loc_1800FA75B
0x1800fa4cf  movzx   ebx, bx
0x1800fa4d2  or      ebx, esi
0x1800fa4d4  jmp     loc_1800FA75B
0x1800fa4d9  mov     ecx, [rsp+58h+TokenInformationLength]; Size
0x1800fa4dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fa4e2  mov     r14, rax
0x1800fa4e5  test    rax, rax
0x1800fa4e8  jnz     short loc_1800FA53E
0x1800fa4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa4f1  lea     rax, WPP_GLOBAL_Control
0x1800fa4f8  cmp     rcx, rax
0x1800fa4fb  jz      short loc_1800FA534
0x1800fa4fd  test    byte ptr [rcx+1Ch], 8
0x1800fa501  jz      short loc_1800FA534
0x1800fa503  cmp     [rcx+19h], dil
0x1800fa507  jb      short loc_1800FA534
0x1800fa509  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa50e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa515  lea     edx, [r14+36h]
0x1800fa519  mov     r9d, eax
0x1800fa51c  mov     dword ptr [rsp+58h+ReturnLength], 8007000Eh
0x1800fa524  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa52b  mov     rcx, [rcx+10h]
0x1800fa52f  call    WPP_SF_Dd
0x1800fa534  mov     ebx, 8007000Eh
0x1800fa539  jmp     loc_1800FA75B
0x1800fa53e  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800fa543  lea     rax, [rsp+58h+TokenInformationLength]
0x1800fa548  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800fa54d  mov     r8, r14; TokenInformation
0x1800fa550  mov     edx, edi; TokenInformationClass
0x1800fa552  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800fa557  xor     ebp, ebp
0x1800fa559  call    cs:__imp_GetTokenInformation
0x1800fa55f  test    eax, eax
0x1800fa561  jnz     short loc_1800FA5DA
0x1800fa563  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa56a  lea     rax, WPP_GLOBAL_Control
0x1800fa571  mov     esi, 80070000h
0x1800fa576  cmp     rcx, rax
0x1800fa579  jz      short loc_1800FA5C0
0x1800fa57b  test    byte ptr [rcx+1Ch], 8
0x1800fa57f  jz      short loc_1800FA5C0
0x1800fa581  cmp     [rcx+19h], dil
0x1800fa585  jb      short loc_1800FA5C0
0x1800fa587  call    cs:__imp_GetLastError
0x1800fa58d  mov     ebx, eax
0x1800fa58f  test    eax, eax
0x1800fa591  jle     short loc_1800FA598
0x1800fa593  movzx   ebx, ax
0x1800fa596  or      ebx, esi
0x1800fa598  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa59d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa5a4  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa5ab  mov     edx, 37h ; '7'
0x1800fa5b0  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x1800fa5b4  mov     r9d, eax
0x1800fa5b7  mov     rcx, [rcx+10h]
0x1800fa5bb  call    WPP_SF_Dd
0x1800fa5c0  call    cs:__imp_GetLastError
0x1800fa5c6  mov     ebx, eax
0x1800fa5c8  test    eax, eax
0x1800fa5ca  jle     loc_1800FA746
0x1800fa5d0  movzx   ebx, ax
0x1800fa5d3  or      ebx, esi
0x1800fa5d5  jmp     loc_1800FA746
0x1800fa5da  xor     ecx, ecx
0x1800fa5dc  mov     edx, 0C0000000h
0x1800fa5e1  cmp     ecx, [r14]
0x1800fa5e4  jnb     loc_1800FA6F6
0x1800fa5ea  mov     ebx, ecx
0x1800fa5ec  add     rbx, rbx
0x1800fa5ef  mov     eax, [r14+rbx*8+10h]
0x1800fa5f4  and     eax, edx
0x1800fa5f6  cmp     eax, edx
0x1800fa5f8  jz      short loc_1800FA5FE
0x1800fa5fa  inc     ecx
0x1800fa5fc  jmp     short loc_1800FA5E1
0x1800fa5fe  mov     rcx, [r14+rbx*8+8]; pSid
0x1800fa603  call    cs:__imp_GetLengthSid
0x1800fa609  mov     ecx, eax; Size
0x1800fa60b  mov     esi, eax
0x1800fa60d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fa612  mov     rbp, rax
0x1800fa615  test    rax, rax
0x1800fa618  jnz     short loc_1800FA66D
0x1800fa61a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa621  lea     rax, WPP_GLOBAL_Control
0x1800fa628  cmp     rcx, rax
0x1800fa62b  jz      short loc_1800FA663
0x1800fa62d  test    byte ptr [rcx+1Ch], 8
0x1800fa631  jz      short loc_1800FA663
0x1800fa633  cmp     [rcx+19h], dil
0x1800fa637  jb      short loc_1800FA663
0x1800fa639  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa63e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa645  lea     edx, [rbp+38h]
0x1800fa648  mov     r9d, eax
0x1800fa64b  mov     dword ptr [rsp+58h+ReturnLength], 8007000Eh
0x1800fa653  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa65a  mov     rcx, [rcx+10h]
0x1800fa65e  call    WPP_SF_Dd
0x1800fa663  mov     ebx, 8007000Eh
0x1800fa668  jmp     loc_1800FA746
0x1800fa66d  mov     r8, [r14+rbx*8+8]; pSourceSid
0x1800fa672  mov     rdx, rbp; pDestinationSid
0x1800fa675  mov     ecx, esi; nDestinationSidLength
0x1800fa677  call    cs:__imp_CopySid
0x1800fa67d  test    eax, eax
0x1800fa67f  jnz     short loc_1800FA6E9
0x1800fa681  call    cs:__imp_GetLastError
0x1800fa687  mov     ebx, eax
0x1800fa689  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa690  lea     rax, WPP_GLOBAL_Control
0x1800fa697  cmp     rcx, rax
0x1800fa69a  jz      short loc_1800FA6D0
0x1800fa69c  test    byte ptr [rcx+1Ch], 8
0x1800fa6a0  jz      short loc_1800FA6D0
0x1800fa6a2  cmp     [rcx+19h], dil
0x1800fa6a6  jb      short loc_1800FA6D0
0x1800fa6a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa6ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa6b4  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa6bb  mov     edx, 39h ; '9'
0x1800fa6c0  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x1800fa6c4  mov     r9d, eax
0x1800fa6c7  mov     rcx, [rcx+10h]
0x1800fa6cb  call    WPP_SF_Dd
0x1800fa6d0  test    ebx, ebx
0x1800fa6d2  jle     short loc_1800FA6DD
0x1800fa6d4  movzx   ebx, bx
0x1800fa6d7  or      ebx, 80070000h
0x1800fa6dd  test    ebx, ebx
0x1800fa6df  mov     eax, 80004005h
0x1800fa6e4  cmovns  ebx, eax
0x1800fa6e7  jmp     short loc_1800FA746
0x1800fa6e9  mov     [r12], rbp
0x1800fa6ed  xor     ebp, ebp
0x1800fa6ef  xor     ebx, ebx
0x1800fa6f1  mov     [r15], esi
0x1800fa6f4  jmp     short loc_1800FA746
0x1800fa6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa6fd  lea     rax, WPP_GLOBAL_Control
0x1800fa704  cmp     rcx, rax
0x1800fa707  jz      short loc_1800FA741
0x1800fa709  test    byte ptr [rcx+1Ch], 8
0x1800fa70d  jz      short loc_1800FA741
0x1800fa70f  cmp     [rcx+19h], dil
0x1800fa713  jb      short loc_1800FA741
0x1800fa715  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa71a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa721  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1800fa728  mov     edx, 3Ah ; ':'
0x1800fa72d  mov     dword ptr [rsp+58h+ReturnLength], 8000FFFFh
0x1800fa735  mov     r9d, eax
0x1800fa738  mov     rcx, [rcx+10h]
0x1800fa73c  call    WPP_SF_Dd
0x1800fa741  mov     ebx, 8000FFFFh
0x1800fa746  mov     rcx, r14; Block
0x1800fa749  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800fa74e  test    rbp, rbp
0x1800fa751  jz      short loc_1800FA75B
0x1800fa753  mov     rcx, rbp; Block
0x1800fa756  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800fa75b  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800fa760  test    rcx, rcx
0x1800fa763  jz      short loc_1800FA76B
0x1800fa765  call    cs:__imp_CloseHandle
0x1800fa76b  mov     rbp, [rsp+58h+arg_10]
0x1800fa770  mov     eax, ebx
0x1800fa772  mov     rbx, [rsp+58h+arg_8]
0x1800fa777  add     rsp, 30h
0x1800fa77b  pop     r15
0x1800fa77d  pop     r14
0x1800fa77f  pop     r12
0x1800fa781  pop     rdi
0x1800fa782  pop     rsi
0x1800fa783  retn
```
