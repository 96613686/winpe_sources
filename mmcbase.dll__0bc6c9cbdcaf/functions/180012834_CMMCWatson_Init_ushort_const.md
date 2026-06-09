# CMMCWatson::Init(ushort const *)

- ea: `0x180012834`
- end: `0x180012bec`
- name: `?Init@CMMCWatson@@QEAA_NPEBG@Z`
- size: `952`
- prototype: `char __fastcall(CMMCWatson *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007ca8`

## callees

- `0x180005ef0`
- `0x1800064b4`
- `0x180006628`
- `0x18000bd34`
- `0x180012364`
- `0x180012668`
- `0x180012834`
- `0x180012fbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180012b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180012b97`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001290a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001290a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180012b60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180012b60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800128cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800128d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800128de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800128cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800128d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800128de`

## string_xrefs

- `0x180012aa4`: `watson.microsoft.com`
- `0x180012b25`: `mmcbase.dll`

## pseudocode

```c
char __fastcall CMMCWatson::Init(CMMCWatson *this, const unsigned __int16 *a2)
{
  CMMCWatson *v2; // rsi
  char v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rdx
  HANDLE CurrentProcess; // rdi
  HANDLE v8; // rbx
  HANDLE v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // rax
  LONG (__stdcall *v12)(struct _EXCEPTION_POINTERS *); // rax
  HANDLE TargetHandle; // [rsp+D0h] [rbp+8h] BYREF

  TargetHandle = this;
  v2 = g_pMMCWatson;
  v4 = 0;
  if ( *((_QWORD *)g_pMMCWatson + 71) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      v6 = 54;
LABEL_5:
      WPP_SF_(*(_QWORD *)(v5 + 16), v6, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
    }
  }
  else
  {
    TargetHandle = 0;
    if ( !CMMCWatson::CreateSharedMemory(g_pMMCWatson) )
      return v4;
    if ( !CMMCWatson::CreateSyncObjects(v2)
      || (CurrentProcess = GetCurrentProcess(),
          v8 = GetCurrentProcess(),
          v9 = GetCurrentProcess(),
          !DuplicateHandle(v9, v8, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0)) )
    {
      CMMCWatson::CleanUp(v2);
      return v4;
    }
    **((_DWORD **)v2 + 71) = 7276;
    *(_QWORD *)(*((_QWORD *)v2 + 71) + 60LL) = TargetHandle;
    *(_DWORD *)(*((_QWORD *)v2 + 71) + 4LL) = GetCurrentProcessId();
    *(_QWORD *)(*((_QWORD *)v2 + 71) + 44LL) = *((_QWORD *)v2 + 1);
    *(_QWORD *)(*((_QWORD *)v2 + 71) + 28LL) = *(_QWORD *)v2;
    *(_QWORD *)(*((_QWORD *)v2 + 71) + 52LL) = *((_QWORD *)v2 + 2);
    *(_QWORD *)(*((_QWORD *)v2 + 71) + 36LL) = *((_QWORD *)v2 + 3);
    *(_DWORD *)(*((_QWORD *)v2 + 71) + 80LL) = 1;
    *(_DWORD *)(*((_QWORD *)v2 + 71) + 88LL) = 1;
    *(_DWORD *)(*((_QWORD *)v2 + 71) + 68LL) = 256;
    if ( (int)StringCchCopyA((char *)(*((_QWORD *)v2 + 71) + 4452LL), 0xC8u, "Microsoft\\PCHealth\\ErrorReporting\\DW") >= 0 )
    {
      if ( !a2 )
        goto LABEL_22;
      v10 = -1;
      do
        ++v10;
      while ( a2[v10] );
      if ( v10 < 0x38 )
      {
        if ( (int)StringCchCopyW((unsigned __int16 *)(*((_QWORD *)v2 + 71) + 100LL), 0x38u, a2) < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v6 = 57;
            goto LABEL_5;
          }
          return v4;
        }
      }
      else
      {
LABEL_22:
        if ( (int)StringCchCopyW((unsigned __int16 *)(*((_QWORD *)v2 + 71) + 100LL), 0x38u, L"MMC.EXE") < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v6 = 58;
            goto LABEL_5;
          }
          return v4;
        }
      }
      if ( (int)StringCchCopyA((char *)(*((_QWORD *)v2 + 71) + 3668LL), 0x104u, "watson.microsoft.com") >= 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
        v11 = *((_QWORD *)v2 + 71);
        *(_OWORD *)(v11 + 4652) = *(_OWORD *)L"mmcbase.dll";
        *(_OWORD *)(v11 + 4668) = *(_OWORD *)L"dll";
        *(_QWORD *)(v11 + 4684) = 0x720067006D0064LL;
        GetModuleFileNameW(0, (LPWSTR)(*((_QWORD *)v2 + 71) + 212LL), 0x104u);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 63, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
        v12 = SetUnhandledExceptionFilter(CMMCWatsonAPI::GlobalExceptionFilter);
        if ( v12
          && v12 != CMMCWatsonAPI::GlobalExceptionFilter
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
        }
        CMMCWatson::GetWatsonExe(v2);
        return 1;
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v6 = 61;
          goto LABEL_5;
        }
      }
      return v4;
    }
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v6 = 55;
      goto LABEL_5;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180012834  mov     [rsp+TargetHandle], rcx
0x180012839  push    rbx
0x18001283a  push    rbp
0x18001283b  push    rsi
0x18001283c  push    rdi
0x18001283d  push    r14
0x18001283f  push    r15
0x180012841  sub     rsp, 98h
0x180012848  mov     rsi, cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA; CMMCWatson * g_pMMCWatson
0x18001284f  xor     r15d, r15d
0x180012852  mov     rbp, rdx
0x180012855  mov     r14b, r15b
0x180012858  cmp     [rsi+238h], r15
0x18001285f  jz      short loc_18001289B
0x180012861  mov     rcx, cs:WPP_GLOBAL_Control
0x180012868  lea     rbx, WPP_GLOBAL_Control
0x18001286f  cmp     rcx, rbx
0x180012872  jz      loc_180012BD9
0x180012878  cmp     byte ptr [rcx+19h], 3
0x18001287c  jb      loc_180012BD9
0x180012882  lea     edx, [r15+36h]
0x180012886  mov     rcx, [rcx+10h]
0x18001288a  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x180012891  call    WPP_SF_
0x180012896  jmp     loc_180012BD9
0x18001289b  mov     rcx, rsi; this
0x18001289e  mov     [rsp+0C8h+TargetHandle], r15
0x1800128a6  call    ?CreateSharedMemory@CMMCWatson@@AEAA_NXZ; CMMCWatson::CreateSharedMemory(void)
0x1800128ab  test    al, al
0x1800128ad  jz      loc_180012BD9
0x1800128b3  mov     rcx, rsi; this
0x1800128b6  call    ?CreateSyncObjects@CMMCWatson@@AEAA_NXZ; CMMCWatson::CreateSyncObjects(void)
0x1800128bb  test    al, al
0x1800128bd  jnz     short loc_1800128CC
0x1800128bf  mov     rcx, rsi; this
0x1800128c2  call    ?CleanUp@CMMCWatson@@AEAAXXZ; CMMCWatson::CleanUp(void)
0x1800128c7  jmp     loc_180012BD9
0x1800128cc  call    cs:__imp_GetCurrentProcess
0x1800128d2  mov     rdi, rax
0x1800128d5  call    cs:__imp_GetCurrentProcess
0x1800128db  mov     rbx, rax
0x1800128de  call    cs:__imp_GetCurrentProcess
0x1800128e4  mov     [rsp+0C8h+dwOptions], r15d; dwOptions
0x1800128e9  lea     r9, [rsp+0C8h+TargetHandle]; lpTargetHandle
0x1800128f1  mov     rcx, rax; hSourceProcessHandle
0x1800128f4  mov     [rsp+0C8h+bInheritHandle], 1; bInheritHandle
0x1800128fc  mov     r8, rdi; hTargetProcessHandle
0x1800128ff  mov     [rsp+0C8h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x180012907  mov     rdx, rbx; hSourceHandle
0x18001290a  call    cs:__imp_DuplicateHandle
0x180012910  test    eax, eax
0x180012912  jz      short loc_1800128BF
0x180012914  mov     rax, [rsi+238h]
0x18001291b  mov     dword ptr [rax], 1C6Ch
0x180012921  mov     rcx, [rsi+238h]
0x180012928  mov     rax, [rsp+0C8h+TargetHandle]
0x180012930  mov     [rcx+3Ch], rax
0x180012934  call    cs:__imp_GetCurrentProcessId
0x18001293a  mov     rcx, [rsi+238h]
0x180012941  lea     r8, aMicrosoftPchea; "Microsoft\\PCHealth\\ErrorReporting\\DW"
0x180012948  mov     edx, 0C8h; unsigned __int64
0x18001294d  mov     [rcx+4], eax
0x180012950  mov     rcx, [rsi+238h]
0x180012957  mov     rax, [rsi+8]
0x18001295b  mov     [rcx+2Ch], rax
0x18001295f  mov     rcx, [rsi+238h]
0x180012966  mov     rax, [rsi]
0x180012969  mov     [rcx+1Ch], rax
0x18001296d  mov     rcx, [rsi+238h]
0x180012974  mov     rax, [rsi+10h]
0x180012978  mov     [rcx+34h], rax
0x18001297c  mov     rcx, [rsi+238h]
0x180012983  mov     rax, [rsi+18h]
0x180012987  mov     [rcx+24h], rax
0x18001298b  mov     rax, [rsi+238h]
0x180012992  mov     dword ptr [rax+50h], 1
0x180012999  mov     rax, [rsi+238h]
0x1800129a0  mov     dword ptr [rax+58h], 1
0x1800129a7  mov     rax, [rsi+238h]
0x1800129ae  mov     dword ptr [rax+44h], 100h
0x1800129b5  mov     rcx, [rsi+238h]
0x1800129bc  add     rcx, 1164h; char *
0x1800129c3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800129c8  test    eax, eax
0x1800129ca  jns     short loc_1800129F7
0x1800129cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129d3  lea     rbx, WPP_GLOBAL_Control
0x1800129da  cmp     rcx, rbx
0x1800129dd  jz      loc_180012BD9
0x1800129e3  cmp     byte ptr [rcx+19h], 2
0x1800129e7  jb      loc_180012BD9
0x1800129ed  mov     edx, 37h ; '7'
0x1800129f2  jmp     loc_180012886
0x1800129f7  mov     edx, 38h ; '8'; unsigned __int64
0x1800129fc  test    rbp, rbp
0x1800129ff  jz      short loc_180012A57
0x180012a01  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012a05  inc     rax
0x180012a08  cmp     [rbp+rax*2+0], r15w
0x180012a0e  jnz     short loc_180012A05
0x180012a10  cmp     rax, rdx
0x180012a13  jnb     short loc_180012A57
0x180012a15  mov     rcx, [rsi+238h]
0x180012a1c  mov     r8, rbp; unsigned __int16 *
0x180012a1f  add     rcx, 64h ; 'd'; unsigned __int16 *
0x180012a23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012a28  test    eax, eax
0x180012a2a  jns     short loc_180012A9D
0x180012a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a33  lea     rbx, WPP_GLOBAL_Control
0x180012a3a  cmp     rcx, rbx
0x180012a3d  jz      loc_180012BD9
0x180012a43  cmp     byte ptr [rcx+19h], 2
0x180012a47  jb      loc_180012BD9
0x180012a4d  mov     edx, 39h ; '9'
0x180012a52  jmp     loc_180012886
0x180012a57  mov     rcx, [rsi+238h]
0x180012a5e  lea     r8, aMmcExe; "MMC.EXE"
0x180012a65  add     rcx, 64h ; 'd'; unsigned __int16 *
0x180012a69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012a6e  test    eax, eax
0x180012a70  jns     short loc_180012A9D
0x180012a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a79  lea     rbx, WPP_GLOBAL_Control
0x180012a80  cmp     rcx, rbx
0x180012a83  jz      loc_180012BD9
0x180012a89  cmp     byte ptr [rcx+19h], 2
0x180012a8d  jb      loc_180012BD9
0x180012a93  mov     edx, 3Ah ; ':'
0x180012a98  jmp     loc_180012886
0x180012a9d  mov     rcx, [rsi+238h]
0x180012aa4  lea     r8, aWatsonMicrosof; "watson.microsoft.com"
0x180012aab  mov     edi, 104h
0x180012ab0  add     rcx, 0E54h; char *
0x180012ab7  mov     edx, edi; unsigned __int64
0x180012ab9  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180012abe  test    eax, eax
0x180012ac0  jns     short loc_180012AED
0x180012ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ac9  lea     rbx, WPP_GLOBAL_Control
0x180012ad0  cmp     rcx, rbx
0x180012ad3  jz      loc_180012BD9
0x180012ad9  cmp     byte ptr [rcx+19h], 2
0x180012add  jb      loc_180012BD9
0x180012ae3  mov     edx, 3Dh ; '='
0x180012ae8  jmp     loc_180012886
0x180012aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180012af4  lea     rbx, WPP_GLOBAL_Control
0x180012afb  cmp     rcx, rbx
0x180012afe  jz      short loc_180012B1B
0x180012b00  cmp     byte ptr [rcx+19h], 4
0x180012b04  jb      short loc_180012B1B
0x180012b06  mov     rcx, [rcx+10h]
0x180012b0a  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x180012b11  mov     edx, 3Eh ; '>'
0x180012b16  call    WPP_SF_
0x180012b1b  mov     rax, [rsi+238h]
0x180012b22  mov     r8d, edi; nSize
0x180012b25  movaps  xmm4, xmmword ptr cs:aMmcbaseDll_0; "mmcbase.dll"
0x180012b2c  xor     ecx, ecx; hModule
0x180012b2e  movaps  xmm3, xmmword ptr cs:aMmcbaseDll_0+10h; "dll"
0x180012b35  movaps  xmm2, cs:xmmword_1800221E0
0x180012b3c  movups  xmmword ptr [rax+122Ch], xmm4
0x180012b43  movups  xmmword ptr [rax+123Ch], xmm3
0x180012b4a  movsd   qword ptr [rax+124Ch], xmm2
0x180012b52  mov     rdx, [rsi+238h]
0x180012b59  add     rdx, 0D4h; lpFilename
0x180012b60  call    cs:__imp_GetModuleFileNameW
0x180012b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b6d  cmp     rcx, rbx
0x180012b70  jz      short loc_180012B8D
0x180012b72  cmp     byte ptr [rcx+19h], 5
0x180012b76  jb      short loc_180012B8D
0x180012b78  mov     rcx, [rcx+10h]
0x180012b7c  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x180012b83  mov     edx, 3Fh ; '?'
0x180012b88  call    WPP_SF_
0x180012b8d  lea     rdi, ?GlobalExceptionFilter@CMMCWatsonAPI@@SAJPEAU_EXCEPTION_POINTERS@@@Z; CMMCWatsonAPI::GlobalExceptionFilter(_EXCEPTION_POINTERS *)
0x180012b94  mov     rcx, rdi; lpTopLevelExceptionFilter
0x180012b97  call    cs:__imp_SetUnhandledExceptionFilter
0x180012b9d  test    rax, rax
0x180012ba0  jz      short loc_180012BCE
0x180012ba2  cmp     rax, rdi
0x180012ba5  jz      short loc_180012BCE
0x180012ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bae  cmp     rcx, rbx
0x180012bb1  jz      short loc_180012BCE
0x180012bb3  cmp     byte ptr [rcx+19h], 5
0x180012bb7  jb      short loc_180012BCE
0x180012bb9  mov     rcx, [rcx+10h]
0x180012bbd  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x180012bc4  mov     edx, 18h
0x180012bc9  call    WPP_SF_
0x180012bce  mov     rcx, rsi; this
0x180012bd1  call    ?GetWatsonExe@CMMCWatson@@AEAA_NXZ; CMMCWatson::GetWatsonExe(void)
0x180012bd6  mov     r14b, 1
0x180012bd9  mov     al, r14b
0x180012bdc  add     rsp, 98h
0x180012be3  pop     r15
0x180012be5  pop     r14
0x180012be7  pop     rdi
0x180012be8  pop     rsi
0x180012be9  pop     rbp
0x180012bea  pop     rbx
0x180012beb  retn
```
