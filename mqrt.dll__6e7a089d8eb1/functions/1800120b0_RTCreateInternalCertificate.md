# RTCreateInternalCertificate

- ea: `0x1800120b0`
- end: `0x1800126ed`
- name: `RTCreateInternalCertificate`
- size: `1597`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800114c0`

## callees

- `0x180006fdc`
- `0x180010a58`
- `0x180010f00`
- `0x18001138c`
- `0x180011c14`
- `0x1800120b0`
- `0x180013c74`
- `0x180014458`
- `0x180021010`
- `0x180023ca0`
- `0x180026010`

## import_xrefs

- `msvcrt!free` at `0x18001222b`
- `msvcrt!free` at `0x180012237`
- `msvcrt!free` at `0x180012282`
- `msvcrt!free` at `0x18001228e`
- `msvcrt!free` at `0x180012301`
- `msvcrt!free` at `0x18001230d`
- `msvcrt!free` at `0x180012319`
- `msvcrt!free` at `0x180012366`
- `msvcrt!free` at `0x180012372`
- `msvcrt!free` at `0x18001237e`
- `msvcrt!free` at `0x1800123bc`
- `msvcrt!free` at `0x1800123c8`
- `msvcrt!free` at `0x1800123d4`
- `msvcrt!free` at `0x18001241a`
- `msvcrt!free` at `0x180012426`
- `msvcrt!free` at `0x180012432`
- `msvcrt!free` at `0x1800124a7`
- `msvcrt!free` at `0x1800124b1`
- `msvcrt!free` at `0x1800124bb`
- `msvcrt!free` at `0x180012529`
- `msvcrt!free` at `0x180012533`
- `msvcrt!free` at `0x18001253d`
- `msvcrt!free` at `0x180012598`
- `msvcrt!free` at `0x1800125a2`
- `msvcrt!free` at `0x1800125ac`
- `msvcrt!free` at `0x1800125fd`
- `msvcrt!free` at `0x180012607`
- `msvcrt!free` at `0x180012611`
- `msvcrt!free` at `0x18001265b`
- `msvcrt!free` at `0x180012665`
- `msvcrt!free` at `0x18001266f`
- `msvcrt!free` at `0x1800126a0`
- `msvcrt!free` at `0x1800126aa`
- `msvcrt!free` at `0x1800126b4`
- `msvcrt!free` at `0x18001222b`
- `msvcrt!free` at `0x180012237`
- `msvcrt!free` at `0x180012282`
- `msvcrt!free` at `0x18001228e`
- `msvcrt!free` at `0x180012301`
- `msvcrt!free` at `0x18001230d`
- `msvcrt!free` at `0x180012319`
- `msvcrt!free` at `0x180012366`
- `msvcrt!free` at `0x180012372`
- `msvcrt!free` at `0x18001237e`
- `msvcrt!free` at `0x1800123bc`
- `msvcrt!free` at `0x1800123c8`
- `msvcrt!free` at `0x1800123d4`
- `msvcrt!free` at `0x18001241a`
- `msvcrt!free` at `0x180012426`
- `msvcrt!free` at `0x180012432`
- `msvcrt!free` at `0x1800124a7`
- `msvcrt!free` at `0x1800124b1`
- `msvcrt!free` at `0x1800124bb`
- `msvcrt!free` at `0x180012529`
- `msvcrt!free` at `0x180012533`
- `msvcrt!free` at `0x18001253d`
- `msvcrt!free` at `0x180012598`
- `msvcrt!free` at `0x1800125a2`
- `msvcrt!free` at `0x1800125ac`
- `msvcrt!free` at `0x1800125fd`
- `msvcrt!free` at `0x180012607`
- `msvcrt!free` at `0x180012611`
- `msvcrt!free` at `0x18001265b`
- `msvcrt!free` at `0x180012665`
- `msvcrt!free` at `0x18001266f`
- `msvcrt!free` at `0x1800126a0`
- `msvcrt!free` at `0x1800126aa`
- `msvcrt!free` at `0x1800126b4`
- `KERNEL32!GetComputerNameExW` at `0x180012259`
- `KERNEL32!GetComputerNameExW` at `0x180012259`
- `USER32!CharLowerW` at `0x1800122a0`
- `USER32!CharLowerW` at `0x1800122a0`
- `mqsec!MQSigCreateCertificate` at `0x180012337`
- `mqsec!MQSigCreateCertificate` at `0x180012337`
- `mqsec!MQSec_GetUserType` at `0x180012145`
- `mqsec!MQSec_GetUserType` at `0x180012145`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RTCreateInternalCertificate(_QWORD *a1)
{
  int UserType; // ebx
  unsigned __int16 v3; // r8
  int v4; // eax
  unsigned __int16 v5; // r8
  int v6; // ecx
  __int64 v7; // r12
  int v8; // ecx
  int UserAccountNameAndDomain; // eax
  int v10; // edi
  wchar_t *v11; // rbx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  void *v15; // rsi
  void *v16; // rdi
  int v17; // eax
  int v18; // r15d
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-B8h] BYREF
  void *v27; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+64h] [rbp-9Ch] BYREF
  int v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+6Ch] [rbp-94h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  UserType = RtpOneTimeThreadInit();
  if ( UserType >= 0 )
  {
    if ( IsWorkGroupMode() )
    {
      v3 = 75;
      UserType = -1072824214;
      goto LABEL_3;
    }
    v30 = 0;
    v26 = 0;
    v31 = 0;
    if ( a1 )
      *a1 = 0;
    UserType = MQSec_GetUserType(0, &v30, (int *)&v26, &v31);
    if ( UserType < 0 )
    {
      v3 = 80;
      goto LABEL_3;
    }
    if ( v30 )
    {
      v3 = 90;
      UserType = -1072824303;
      goto LABEL_3;
    }
    LODWORD(v27) = 0;
    v33[0] = 0;
    v4 = RTOpenInternalCertStore((unsigned int)v33, (unsigned int)&v27, 1, v26, 0);
    UserType = v4;
    if ( v4 >= 0 )
    {
      if ( !(_DWORD)v27 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v33[0] + 8LL))(v33[0]);
        v27 = 0;
        Block = 0;
        if ( v26 || (v8 = 0, v31) )
          v8 = 1;
        UserAccountNameAndDomain = GetUserAccountNameAndDomain(v8, (wchar_t **)&v27, (wchar_t **)&Block);
        UserType = UserAccountNameAndDomain;
        if ( UserAccountNameAndDomain < 0 )
        {
          LogMsgHR(UserAccountNameAndDomain, (wchar_t *)L"rt/rtintcrt", 0xB4u);
          free(Block);
          free(v27);
          goto LABEL_47;
        }
        nSize = 256;
        if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
        {
          CharLowerW(Buffer);
          v11 = (wchar_t *)MmAllocate(saturated_mul(nSize + 2, 2u));
          v33[1] = v11;
          v12 = StringCchCopyW(v11, nSize + 2, Buffer);
          v10 = v12;
          if ( v12 >= 0 )
          {
            v25 = 0;
            v13 = MQSigCreateCertificate(&v25, 0, 0, 0);
            v10 = v13;
            if ( v13 >= 0 )
            {
              if ( v25 )
              {
                v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 72LL))(v25, 8);
                v10 = v14;
                if ( v14 >= 0 )
                {
                  v15 = v27;
                  v16 = Block;
                  v17 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, const wchar_t *, const wchar_t *, void *, void *, wchar_t *))(*(_QWORD *)v25 + 56LL))(
                          v25,
                          L"MSMQ",
                          L"-",
                          L"-",
                          Block,
                          v27,
                          v11);
                  v18 = v17;
                  if ( v17 >= 0 )
                  {
                    v19 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, const wchar_t *, const wchar_t *, void *, void *, wchar_t *))(*(_QWORD *)v25 + 64LL))(
                            v25,
                            L"MSMQ",
                            L"-",
                            L"-",
                            v16,
                            v15,
                            v11);
                    v18 = v19;
                    if ( v19 >= 0 )
                    {
                      v32 = 0;
                      v20 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v25 + 80LL))(
                              v25,
                              1,
                              v26,
                              &v32);
                      v18 = v20;
                      if ( v20 >= 0 )
                      {
                        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v25 + 8LL))(
                                v25,
                                v26,
                                0,
                                0);
                        v18 = v21;
                        if ( v21 >= 0 )
                        {
                          v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 40LL))(v25, v7);
                          v18 = v22;
                          if ( v22 >= 0 )
                          {
                            if ( a1 )
                            {
                              v23 = v25;
                              v25 = 0;
                              *a1 = v23;
                            }
                            ((void (*)(void))SafeRelease<CMQSigCertificate>)();
                            free(v11);
                            free(v16);
                            free(v15);
                            UserType = 0;
                            goto LABEL_47;
                          }
                          LogMsgHR(v22, (wchar_t *)L"rt/rtintcrt", 0x10Eu);
                          SafeRelease<CMQSigCertificate>(v25);
                          free(v11);
                          free(v16);
                          free(v15);
                        }
                        else
                        {
                          LogMsgHR(v21, (wchar_t *)L"rt/rtintcrt", 0x104u);
                          SafeRelease<CMQSigCertificate>(v25);
                          free(v11);
                          free(v16);
                          free(v15);
                        }
                      }
                      else
                      {
                        LogMsgHR(v20, (wchar_t *)L"rt/rtintcrt", 0xFAu);
                        SafeRelease<CMQSigCertificate>(v25);
                        free(v11);
                        free(v16);
                        free(v15);
                      }
                    }
                    else
                    {
                      LogMsgHR(v19, (wchar_t *)L"rt/rtintcrt", 0xF0u);
                      SafeRelease<CMQSigCertificate>(v25);
                      free(v11);
                      free(v16);
                      free(v15);
                    }
                  }
                  else
                  {
                    LogMsgHR(v17, (wchar_t *)L"rt/rtintcrt", 0xE6u);
                    SafeRelease<CMQSigCertificate>(v25);
                    free(v11);
                    free(v16);
                    free(v15);
                  }
                  UserType = v18;
LABEL_47:
                  SafeRelease<CMQSigCertificate>(v33[0]);
                  return (unsigned int)UserType;
                }
                LogMsgHR(v14, (wchar_t *)L"rt/rtintcrt", 0xDCu);
                SafeRelease<CMQSigCertificate>(v25);
                free(v11);
                free(Block);
                free(v27);
              }
              else
              {
                v10 = -1072824319;
                LogMsgHR(-1072824319, (wchar_t *)L"rt/rtintcrt", 0xD2u);
                SafeRelease<CMQSigCertificate>(v25);
                free(v11);
                free(Block);
                free(v27);
              }
            }
            else
            {
              LogMsgHR(v13, (wchar_t *)L"rt/rtintcrt", 0xC8u);
              SafeRelease<CMQSigCertificate>(v25);
              free(v11);
              free(Block);
              free(v27);
            }
          }
          else
          {
            LogMsgHR(v12, (wchar_t *)L"rt/rtintcrt", 0xC0u);
            free(v11);
            free(Block);
            free(v27);
          }
        }
        else
        {
          v10 = -1072824319;
          LogMsgHR(-1072824319, (wchar_t *)L"rt/rtintcrt", 0xBEu);
          free(Block);
          free(v27);
        }
        UserType = v10;
        goto LABEL_47;
      }
      v5 = 110;
      UserType = -1072824274;
      v6 = -1072824274;
    }
    else
    {
      v5 = 100;
      v6 = v4;
    }
    LogMsgHR(v6, (wchar_t *)L"rt/rtintcrt", v5);
    goto LABEL_47;
  }
  v3 = 1102;
LABEL_3:
  LogMsgHR(UserType, (wchar_t *)L"rt/rtintcrt", v3);
  return (unsigned int)UserType;
}

```

## disassembly

```asm
0x1800120b0  push    rbp
0x1800120b2  push    rbx
0x1800120b3  push    rsi
0x1800120b4  push    rdi
0x1800120b5  push    r12
0x1800120b7  push    r13
0x1800120b9  push    r14
0x1800120bb  push    r15
0x1800120bd  lea     rbp, [rsp-198h]
0x1800120c5  sub     rsp, 298h
0x1800120cc  mov     rax, cs:__security_cookie
0x1800120d3  xor     rax, rsp
0x1800120d6  mov     [rbp+1D0h+var_50], rax
0x1800120dd  mov     r14, rcx
0x1800120e0  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x1800120e5  mov     ebx, eax
0x1800120e7  xor     r13d, r13d
0x1800120ea  test    eax, eax
0x1800120ec  jns     short loc_180012107
0x1800120ee  mov     r8d, 44Eh; unsigned __int16
0x1800120f4  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x1800120fb  mov     ecx, ebx; int
0x1800120fd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012102  jmp     loc_1800126C8
0x180012107  call    ?IsWorkGroupMode@@YA_NXZ; IsWorkGroupMode(void)
0x18001210c  test    al, al
0x18001210e  jz      short loc_18001211D
0x180012110  mov     r8d, 4Bh ; 'K'
0x180012116  mov     ebx, 0C00E006Ah
0x18001211b  jmp     short loc_1800120F4
0x18001211d  mov     [rsp+2D0h+var_26C], r13d
0x180012122  mov     [rsp+2D0h+var_288], r13d
0x180012127  mov     [rsp+2D0h+var_268], r13d
0x18001212c  test    r14, r14
0x18001212f  jz      short loc_180012134
0x180012131  mov     [r14], r13
0x180012134  lea     r9, [rsp+2D0h+var_268]
0x180012139  lea     r8, [rsp+2D0h+var_288]
0x18001213e  lea     rdx, [rsp+2D0h+var_26C]
0x180012143  xor     ecx, ecx
0x180012145  call    cs:__imp_?MQSec_GetUserType@@YAJPEAXPEAH11@Z; MQSec_GetUserType(void *,int *,int *,int *)
0x18001214b  mov     ebx, eax
0x18001214d  test    eax, eax
0x18001214f  jns     short loc_180012159
0x180012151  mov     r8d, 50h ; 'P'
0x180012157  jmp     short loc_1800120F4
0x180012159  cmp     [rsp+2D0h+var_26C], r13d
0x18001215e  jz      short loc_18001216D
0x180012160  mov     r8d, 5Ah ; 'Z'
0x180012166  mov     ebx, 0C00E0011h
0x18001216b  jmp     short loc_1800120F4
0x18001216d  mov     dword ptr [rsp+2D0h+var_280], r13d
0x180012172  mov     [rsp+2D0h+var_260], r13
0x180012177  mov     [rsp+2D0h+var_2B0], r13
0x18001217c  mov     r9d, [rsp+2D0h+var_288]
0x180012181  mov     edi, 1
0x180012186  mov     r8d, edi
0x180012189  lea     rdx, [rsp+2D0h+var_280]
0x18001218e  lea     rcx, [rsp+2D0h+var_260]
0x180012193  call    RTOpenInternalCertStore
0x180012198  mov     ebx, eax
0x18001219a  test    eax, eax
0x18001219c  jns     short loc_1800121A6
0x18001219e  lea     r8d, [rdi+63h]
0x1800121a2  mov     ecx, eax
0x1800121a4  jmp     short loc_1800121BA
0x1800121a6  cmp     dword ptr [rsp+2D0h+var_280], r13d
0x1800121ab  jz      short loc_1800121CB
0x1800121ad  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x1800121b3  mov     ebx, 0C00E002Eh
0x1800121b8  mov     ecx, ebx; int
0x1800121ba  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x1800121c1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800121c6  jmp     loc_1800126BE
0x1800121cb  mov     rcx, [rsp+2D0h+var_260]
0x1800121d0  mov     rax, [rcx]
0x1800121d3  mov     rax, [rax+8]
0x1800121d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121dc  mov     r12, rax
0x1800121df  mov     [rsp+2D0h+var_280], r13
0x1800121e4  mov     [rsp+2D0h+Block], r13
0x1800121e9  cmp     [rsp+2D0h+var_288], r13d
0x1800121ee  jnz     short loc_1800121FA
0x1800121f0  cmp     [rsp+2D0h+var_268], r13d
0x1800121f5  mov     ecx, r13d
0x1800121f8  jz      short loc_1800121FC
0x1800121fa  mov     ecx, edi
0x1800121fc  lea     r8, [rsp+2D0h+Block]
0x180012201  lea     rdx, [rsp+2D0h+var_280]
0x180012206  call    _GetUserAccountNameAndDomain
0x18001220b  mov     ebx, eax
0x18001220d  test    eax, eax
0x18001220f  jns     short loc_180012243
0x180012211  mov     r8d, 0B4h; unsigned __int16
0x180012217  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x18001221e  mov     ecx, eax; int
0x180012220  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012225  nop
0x180012226  mov     rcx, [rsp+2D0h+Block]; Block
0x18001222b  call    cs:__imp_free
0x180012231  nop
0x180012232  mov     rcx, [rsp+2D0h+var_280]; Block
0x180012237  call    cs:__imp_free
0x18001223d  nop
0x18001223e  jmp     loc_1800126BE
0x180012243  mov     [rsp+2D0h+nSize], 100h
0x18001224b  lea     r8, [rsp+2D0h+nSize]; nSize
0x180012250  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x180012254  mov     ecx, 4; NameType
0x180012259  call    cs:__imp_GetComputerNameExW
0x18001225f  test    eax, eax
0x180012261  jnz     short loc_18001229C
0x180012263  mov     r8d, 0BEh; unsigned __int16
0x180012269  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012270  mov     edi, 0C00E0001h
0x180012275  mov     ecx, edi; int
0x180012277  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001227c  nop
0x18001227d  mov     rcx, [rsp+2D0h+Block]; Block
0x180012282  call    cs:__imp_free
0x180012288  nop
0x180012289  mov     rcx, [rsp+2D0h+var_280]; Block
0x18001228e  call    cs:__imp_free
0x180012294  nop
0x180012295  mov     ebx, edi
0x180012297  jmp     loc_1800126BE
0x18001229c  lea     rcx, [rbp+1D0h+Buffer]; lpsz
0x1800122a0  call    cs:__imp_CharLowerW
0x1800122a6  mov     ecx, [rsp+2D0h+nSize]
0x1800122aa  add     ecx, 2
0x1800122ad  mov     eax, 2
0x1800122b2  mul     rcx
0x1800122b5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800122bc  cmovb   rax, rcx
0x1800122c0  mov     rcx, rax; unsigned __int64
0x1800122c3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800122c8  mov     rbx, rax
0x1800122cb  mov     [rsp+2D0h+var_258], rax
0x1800122d0  mov     edx, [rsp+2D0h+nSize]
0x1800122d4  add     edx, 2; unsigned __int64
0x1800122d7  lea     r8, [rbp+1D0h+Buffer]; wchar_t *
0x1800122db  mov     rcx, rax; wchar_t *
0x1800122de  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800122e3  mov     edi, eax
0x1800122e5  test    eax, eax
0x1800122e7  jns     short loc_180012325
0x1800122e9  mov     r8d, 0C0h; unsigned __int16
0x1800122ef  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x1800122f6  mov     ecx, eax; int
0x1800122f8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800122fd  nop
0x1800122fe  mov     rcx, rbx; Block
0x180012301  call    cs:__imp_free
0x180012307  nop
0x180012308  mov     rcx, [rsp+2D0h+Block]; Block
0x18001230d  call    cs:__imp_free
0x180012313  nop
0x180012314  mov     rcx, [rsp+2D0h+var_280]; Block
0x180012319  call    cs:__imp_free
0x18001231f  nop
0x180012320  jmp     loc_180012295
0x180012325  mov     [rsp+2D0h+var_290], r13
0x18001232a  xor     r9d, r9d
0x18001232d  xor     r8d, r8d
0x180012330  xor     edx, edx
0x180012332  lea     rcx, [rsp+2D0h+var_290]
0x180012337  call    cs:__imp_MQSigCreateCertificate
0x18001233d  mov     edi, eax
0x18001233f  test    eax, eax
0x180012341  jns     short loc_18001238A
0x180012343  mov     r8d, 0C8h; unsigned __int16
0x180012349  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012350  mov     ecx, eax; int
0x180012352  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012357  nop
0x180012358  mov     rcx, [rsp+2D0h+var_290]
0x18001235d  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180012362  nop
0x180012363  mov     rcx, rbx; Block
0x180012366  call    cs:__imp_free
0x18001236c  nop
0x18001236d  mov     rcx, [rsp+2D0h+Block]; Block
0x180012372  call    cs:__imp_free
0x180012378  nop
0x180012379  mov     rcx, [rsp+2D0h+var_280]; Block
0x18001237e  call    cs:__imp_free
0x180012384  nop
0x180012385  jmp     loc_180012295
0x18001238a  mov     rcx, [rsp+2D0h+var_290]
0x18001238f  test    rcx, rcx
0x180012392  jnz     short loc_1800123E0
0x180012394  mov     r8d, 0D2h; unsigned __int16
0x18001239a  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x1800123a1  mov     edi, 0C00E0001h
0x1800123a6  mov     ecx, edi; int
0x1800123a8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800123ad  nop
0x1800123ae  mov     rcx, [rsp+2D0h+var_290]
0x1800123b3  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x1800123b8  nop
0x1800123b9  mov     rcx, rbx; Block
0x1800123bc  call    cs:__imp_free
0x1800123c2  nop
0x1800123c3  mov     rcx, [rsp+2D0h+Block]; Block
0x1800123c8  call    cs:__imp_free
0x1800123ce  nop
0x1800123cf  mov     rcx, [rsp+2D0h+var_280]; Block
0x1800123d4  call    cs:__imp_free
0x1800123da  nop
0x1800123db  jmp     loc_180012295
0x1800123e0  mov     rax, [rcx]
0x1800123e3  mov     edx, 8
0x1800123e8  mov     rax, [rax+48h]
0x1800123ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123f1  mov     edi, eax
0x1800123f3  test    eax, eax
0x1800123f5  jns     short loc_18001243E
0x1800123f7  mov     r8d, 0DCh; unsigned __int16
0x1800123fd  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012404  mov     ecx, eax; int
0x180012406  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001240b  nop
0x18001240c  mov     rcx, [rsp+2D0h+var_290]
0x180012411  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180012416  nop
0x180012417  mov     rcx, rbx; Block
0x18001241a  call    cs:__imp_free
0x180012420  nop
0x180012421  mov     rcx, [rsp+2D0h+Block]; Block
0x180012426  call    cs:__imp_free
0x18001242c  nop
0x18001242d  mov     rcx, [rsp+2D0h+var_280]; Block
0x180012432  call    cs:__imp_free
0x180012438  nop
0x180012439  jmp     loc_180012295
0x18001243e  mov     rcx, [rsp+2D0h+var_290]
0x180012443  mov     rax, [rcx]
0x180012446  mov     [rsp+2D0h+var_2A0], rbx
0x18001244b  mov     rsi, [rsp+2D0h+var_280]
0x180012450  mov     [rsp+2D0h+var_2A8], rsi
0x180012455  mov     rdi, [rsp+2D0h+Block]
0x18001245a  mov     [rsp+2D0h+var_2B0], rdi
0x18001245f  lea     r9, asc_180031F30; "-"
0x180012466  lea     r8, asc_180031F30; "-"
0x18001246d  lea     rdx, szContainer; "MSMQ"
0x180012474  mov     rax, [rax+38h]
0x180012478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001247d  mov     r15d, eax
0x180012480  test    eax, eax
0x180012482  jns     short loc_1800124CA
0x180012484  mov     r8d, 0E6h; unsigned __int16
0x18001248a  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012491  mov     ecx, eax; int
0x180012493  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012498  nop
0x180012499  mov     rcx, [rsp+2D0h+var_290]
0x18001249e  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x1800124a3  nop
0x1800124a4  mov     rcx, rbx; Block
0x1800124a7  call    cs:__imp_free
0x1800124ad  nop
0x1800124ae  mov     rcx, rdi; Block
0x1800124b1  call    cs:__imp_free
0x1800124b7  nop
0x1800124b8  mov     rcx, rsi; Block
0x1800124bb  call    cs:__imp_free
0x1800124c1  nop
0x1800124c2  mov     ebx, r15d
0x1800124c5  jmp     loc_1800126BE
0x1800124ca  mov     rcx, [rsp+2D0h+var_290]
0x1800124cf  mov     rax, [rcx]
0x1800124d2  mov     [rsp+2D0h+var_2A0], rbx
0x1800124d7  mov     [rsp+2D0h+var_2A8], rsi
0x1800124dc  mov     [rsp+2D0h+var_2B0], rdi
0x1800124e1  lea     r9, asc_180031F30; "-"
0x1800124e8  lea     r8, asc_180031F30; "-"
0x1800124ef  lea     rdx, szContainer; "MSMQ"
0x1800124f6  mov     rax, [rax+40h]
0x1800124fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ff  mov     r15d, eax
0x180012502  test    eax, eax
0x180012504  jns     short loc_180012549
0x180012506  mov     r8d, 0F0h; unsigned __int16
0x18001250c  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012513  mov     ecx, eax; int
0x180012515  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001251a  nop
0x18001251b  mov     rcx, [rsp+2D0h+var_290]
0x180012520  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180012525  nop
0x180012526  mov     rcx, rbx; Block
0x180012529  call    cs:__imp_free
0x18001252f  nop
0x180012530  mov     rcx, rdi; Block
0x180012533  call    cs:__imp_free
0x180012539  nop
0x18001253a  mov     rcx, rsi; Block
0x18001253d  call    cs:__imp_free
0x180012543  nop
0x180012544  jmp     loc_1800124C2
  ... truncated ...
```
