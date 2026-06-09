# HsmpUpdateLastAccessTime

- ea: `0x14004b934`
- end: `0x14004bbe2`
- name: `HsmpUpdateLastAccessTime`
- size: `686`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140001e40`
- `0x1400021e0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000bad4`
- `0x14001e140`
- `0x14004b934`
- `0x14004c5e0`
- `0x140058cbc`
- `0x14005e64c`
- `0x140067838`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004bac1`
- `ntoskrnl!ObfDereferenceObject` at `0x14004bac1`
- `FLTMGR!FltSetInformationFile` at `0x14004ba59`
- `FLTMGR!FltSetInformationFile` at `0x14004ba59`
- `FLTMGR!FltClose` at `0x14004bad0`
- `FLTMGR!FltClose` at `0x14004bad0`
- `FLTMGR!FltReferenceContext` at `0x14004b9fc`
- `FLTMGR!FltReferenceContext` at `0x14004b9fc`
- `FLTMGR!FltReleaseContext` at `0x14004baad`
- `FLTMGR!FltReleaseContext` at `0x14004baad`

## pseudocode

```c
__int64 __fastcall HsmpUpdateLastAccessTime(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        void *a3,
        struct _FILE_OBJECT *a4)
{
  _QWORD *v4; // rsi
  int v5; // eax
  void *v7; // r14
  PFLT_CONTEXT StreamHandleContext; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 result; // rax
  __int64 v14; // r12
  struct _FLT_INSTANCE *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 StreamSize; // rax
  __int64 v20; // r15
  int v21; // r14d
  __int64 FileInformationClass; // [rsp+20h] [rbp-69h]
  void *v23; // [rsp+50h] [rbp-39h] BYREF
  PFILE_OBJECT v24; // [rsp+58h] [rbp-31h] BYREF
  __int64 v25; // [rsp+60h] [rbp-29h]
  PFLT_INSTANCE Instance; // [rsp+68h] [rbp-21h]
  __int128 FileInformation; // [rsp+70h] [rbp-19h] BYREF
  __int128 v28; // [rsp+80h] [rbp-9h]
  __int64 v29; // [rsp+90h] [rbp+7h]

  v4 = *(_QWORD **)(a2 + 16);
  v29 = 0;
  v5 = *(_DWORD *)(a2 + 36);
  FileInformation = 0;
  v7 = 0;
  v28 = 0;
  *(_DWORD *)(a2 + 36) = v5 + 1;
  v23 = 0;
  StreamHandleContext = a3;
  v24 = a4;
  v11 = MEMORY[0xFFFFF78000000014];
  v12 = v4[5];
  if ( v12 && v12 + *((_QWORD *)&_Config + 1) >= MEMORY[0xFFFFF78000000014] )
    goto LABEL_3;
  v14 = v4[2];
  v25 = v4[4];
  v15 = *(struct _FLT_INSTANCE **)(v14 + 32);
  Instance = v15;
  if ( a3 )
  {
    FltReferenceContext(a3);
  }
  else
  {
    StreamHandleContext = HsmpGetStreamHandleContext(CallbackData, v15, a4);
    if ( !StreamHandleContext )
    {
      v20 = v25;
      v21 = HsmpOpenFileByIdEx(
              (const UNICODE_STRING *)v14,
              *(struct _FLT_INSTANCE **)(v14 + 32),
              v25,
              0x100100u,
              FileInformationClass,
              0x200000,
              0,
              &v23,
              &v24);
      HsmDbgBreakOnStatus((unsigned int)v21);
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            52,
            WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
            v14,
            v4,
            v20,
            v21);
        }
        v7 = v23;
        a4 = v24;
        goto LABEL_16;
      }
      v7 = v23;
      a4 = v24;
    }
  }
  *(_QWORD *)&FileInformation = 0;
  v29 = 0;
  *((_QWORD *)&FileInformation + 1) = v11;
  v28 = 0;
  LODWORD(v23) = FltSetInformationFile(Instance, a4, &FileInformation, 0x28u, FileBasicInformation);
  HsmDbgBreakOnStatus((unsigned int)v23);
  if ( (int)v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        53,
        WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
        v14,
        v4,
        v25,
        (_DWORD)v23);
    }
LABEL_16:
    v4[5] = 0;
    goto LABEL_9;
  }
  v4[5] = v11;
  HsmpGetLastHydrationTime(a2, v16, v17);
  StreamSize = HsmpGetStreamSize(v18);
  TlmWriteLastAccessedTimeChangedEvent(v11, StreamSize, v11);
LABEL_9:
  if ( v7 )
  {
    ObfDereferenceObject(a4);
    FltClose(v7);
  }
  if ( StreamHandleContext )
    FltReleaseContext(StreamHandleContext);
LABEL_3:
  result = (unsigned int)(*(_DWORD *)(a2 + 36) - 1);
  *(_DWORD *)(a2 + 36) = result;
  return result;
}

```

## disassembly

```asm
0x14004b934  push    rbp
0x14004b936  push    rbx
0x14004b937  push    rsi
0x14004b938  push    rdi
0x14004b939  push    r12
0x14004b93b  push    r13
0x14004b93d  push    r14
0x14004b93f  push    r15
0x14004b941  lea     rbp, [rsp-1Fh]
0x14004b946  sub     rsp, 0A8h
0x14004b94d  mov     rax, cs:__security_cookie
0x14004b954  xor     rax, rsp
0x14004b957  mov     [rbp+57h+var_48], rax
0x14004b95b  mov     rsi, [rdx+10h]
0x14004b95f  xor     eax, eax
0x14004b961  mov     [rbp+57h+var_50], rax
0x14004b965  xorps   xmm0, xmm0
0x14004b968  mov     eax, [rdx+24h]
0x14004b96b  mov     r15, r9
0x14004b96e  movups  [rbp+57h+FileInformation], xmm0
0x14004b972  inc     eax
0x14004b974  xor     r14d, r14d
0x14004b977  movups  [rbp+57h+var_60], xmm0
0x14004b97b  mov     [rdx+24h], eax
0x14004b97e  mov     rbx, 0FFFFF78000000014h
0x14004b988  mov     r9, rcx
0x14004b98b  mov     [rbp+57h+var_90], r14
0x14004b98f  mov     rdi, r8
0x14004b992  mov     [rbp+57h+var_88], r15
0x14004b996  mov     r13, rdx
0x14004b999  mov     rbx, [rbx]
0x14004b99c  mov     rcx, [rsi+28h]
0x14004b9a0  test    rcx, rcx
0x14004b9a3  jz      short loc_14004B9DF
0x14004b9a5  mov     rdx, qword ptr cs:__Config+8
0x14004b9ac  add     rdx, rcx
0x14004b9af  cmp     rdx, rbx
0x14004b9b2  jl      short loc_14004B9DF
0x14004b9b4  mov     eax, [r13+24h]
0x14004b9b8  dec     eax
0x14004b9ba  mov     [r13+24h], eax
0x14004b9be  mov     rcx, [rbp+57h+var_48]
0x14004b9c2  xor     rcx, rsp; StackCookie
0x14004b9c5  call    __security_check_cookie
0x14004b9ca  add     rsp, 0A8h
0x14004b9d1  pop     r15
0x14004b9d3  pop     r14
0x14004b9d5  pop     r13
0x14004b9d7  pop     r12
0x14004b9d9  pop     rdi
0x14004b9da  pop     rsi
0x14004b9db  pop     rbx
0x14004b9dc  pop     rbp
0x14004b9dd  retn
0x14004b9df  mov     r12, [rsi+10h]
0x14004b9e3  mov     rax, [rsi+20h]
0x14004b9e7  mov     [rbp+57h+var_80], rax
0x14004b9eb  mov     rcx, [r12+20h]
0x14004b9f0  mov     [rbp+57h+Instance], rcx
0x14004b9f4  test    r8, r8
0x14004b9f7  jz      short loc_14004BA0A
0x14004b9f9  mov     rcx, r8; Context
0x14004b9fc  call    cs:__imp_FltReferenceContext
0x14004ba03  nop     dword ptr [rax+rax+00h]
0x14004ba08  jmp     short loc_14004BA24
0x14004ba0a  mov     rdx, rcx; Instance
0x14004ba0d  mov     r8, r15; FileObject
0x14004ba10  mov     rcx, r9; CallbackData
0x14004ba13  call    HsmpGetStreamHandleContext
0x14004ba18  mov     rdi, rax
0x14004ba1b  test    rax, rax
0x14004ba1e  jz      loc_14004BADE
0x14004ba24  mov     rcx, [rbp+57h+Instance]; Instance
0x14004ba28  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14004ba2c  xorps   xmm0, xmm0
0x14004ba2f  mov     qword ptr [rbp+57h+FileInformation], 0
0x14004ba37  mov     r9d, 28h ; '('; Length
0x14004ba3d  mov     [rbp+57h+var_50], 0
0x14004ba45  mov     rdx, r15; FileObject
0x14004ba48  mov     qword ptr [rbp+57h+FileInformation+8], rbx
0x14004ba4c  movdqu  [rbp+57h+var_60], xmm0
0x14004ba51  mov     [rsp+0E0h+FileInformationClass], 4; FileInformationClass
0x14004ba59  call    cs:__imp_FltSetInformationFile
0x14004ba60  nop     dword ptr [rax+rax+00h]
0x14004ba65  mov     ecx, eax
0x14004ba67  mov     dword ptr [rbp+57h+var_90], eax
0x14004ba6a  call    HsmDbgBreakOnStatus
0x14004ba6f  mov     eax, dword ptr [rbp+57h+var_90]
0x14004ba72  test    eax, eax
0x14004ba74  js      loc_14004BB92
0x14004ba7a  mov     rcx, r13
0x14004ba7d  mov     [rsi+28h], rbx
0x14004ba81  call    HsmpGetLastHydrationTime
0x14004ba86  mov     r9, rax
0x14004ba89  call    HsmpGetStreamSize
0x14004ba8e  mov     rdx, rax
0x14004ba91  mov     r8, rbx
0x14004ba94  mov     rcx, rbx
0x14004ba97  call    TlmWriteLastAccessedTimeChangedEvent
0x14004ba9c  test    r14, r14
0x14004ba9f  jnz     short loc_14004BABE
0x14004baa1  test    rdi, rdi
0x14004baa4  jz      loc_14004B9B4
0x14004baaa  mov     rcx, rdi; Context
0x14004baad  call    cs:__imp_FltReleaseContext
0x14004bab4  nop     dword ptr [rax+rax+00h]
0x14004bab9  jmp     loc_14004B9B4
0x14004babe  mov     rcx, r15; Object
0x14004bac1  call    cs:__imp_ObfDereferenceObject
0x14004bac8  nop     dword ptr [rax+rax+00h]
0x14004bacd  mov     rcx, r14; FileHandle
0x14004bad0  call    cs:__imp_FltClose
0x14004bad7  nop     dword ptr [rax+rax+00h]
0x14004badc  jmp     short loc_14004BAA1
0x14004bade  mov     r15, [rbp+57h+var_80]
0x14004bae2  lea     rax, [rbp+57h+var_88]
0x14004bae6  mov     rdx, [r12+20h]
0x14004baeb  mov     r9d, 100100h
0x14004baf1  mov     [rsp+0E0h+var_A0], rax
0x14004baf6  mov     r8, r15
0x14004baf9  lea     rax, [rbp+57h+var_90]
0x14004bafd  mov     rcx, r12
0x14004bb00  mov     [rsp+0E0h+var_A8], rax
0x14004bb05  mov     byte ptr [rsp+0E0h+var_B0], r14b
0x14004bb0a  mov     dword ptr [rsp+0E0h+var_B8], 200000h
0x14004bb12  call    HsmpOpenFileByIdEx
0x14004bb17  mov     ecx, eax
0x14004bb19  mov     r14d, eax
0x14004bb1c  call    HsmDbgBreakOnStatus
0x14004bb21  test    r14d, r14d
0x14004bb24  jns     short loc_14004BB85
0x14004bb26  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bb2d  lea     rdx, WPP_GLOBAL_Control
0x14004bb34  cmp     rcx, rdx
0x14004bb37  jnz     short loc_14004BB4E
0x14004bb39  mov     r14, [rbp+57h+var_90]
0x14004bb3d  mov     r15, [rbp+57h+var_88]
0x14004bb41  mov     qword ptr [rsi+28h], 0
0x14004bb49  jmp     loc_14004BA9C
0x14004bb4e  mov     edx, [rcx+2Ch]
0x14004bb51  test    dl, 1
0x14004bb54  jz      short loc_14004BB39
0x14004bb56  cmp     byte ptr [rcx+29h], 3
0x14004bb5a  jb      short loc_14004BB39
0x14004bb5c  mov     rcx, [rcx+18h]
0x14004bb60  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14004bb67  mov     [rsp+0E0h+var_B0], r14d
0x14004bb6c  mov     edx, 34h ; '4'
0x14004bb71  mov     [rsp+0E0h+var_B8], r15
0x14004bb76  mov     r9, r12
0x14004bb79  mov     qword ptr [rsp+0E0h+FileInformationClass], rsi
0x14004bb7e  call    WPP_SF_qqqd
0x14004bb83  jmp     short loc_14004BB39
0x14004bb85  mov     r14, [rbp+57h+var_90]
0x14004bb89  mov     r15, [rbp+57h+var_88]
0x14004bb8d  jmp     loc_14004BA24
0x14004bb92  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bb99  lea     rdx, WPP_GLOBAL_Control
0x14004bba0  cmp     rcx, rdx
0x14004bba3  jz      short loc_14004BB41
0x14004bba5  mov     edx, [rcx+2Ch]
0x14004bba8  test    dl, 1
0x14004bbab  jz      short loc_14004BB41
0x14004bbad  cmp     byte ptr [rcx+29h], 3
0x14004bbb1  jb      short loc_14004BB41
0x14004bbb3  mov     rcx, [rcx+18h]
0x14004bbb7  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14004bbbe  mov     [rsp+0E0h+var_B0], eax
0x14004bbc2  mov     edx, 35h ; '5'
0x14004bbc7  mov     rax, [rbp+57h+var_80]
0x14004bbcb  mov     r9, r12
0x14004bbce  mov     [rsp+0E0h+var_B8], rax
0x14004bbd3  mov     qword ptr [rsp+0E0h+FileInformationClass], rsi
0x14004bbd8  call    WPP_SF_qqqd
0x14004bbdd  jmp     loc_14004BB41
```
