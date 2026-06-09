# HsmpUpdateLastAccessTime

- ea: `0x14004ba24`
- end: `0x14004bcd2`
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
- `0x14001e1c0`
- `0x14004ba24`
- `0x14004c6d0`
- `0x140058ddc`
- `0x14005e76c`
- `0x140067958`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004bbb1`
- `ntoskrnl!ObfDereferenceObject` at `0x14004bbb1`
- `FLTMGR!FltSetInformationFile` at `0x14004bb49`
- `FLTMGR!FltSetInformationFile` at `0x14004bb49`
- `FLTMGR!FltClose` at `0x14004bbc0`
- `FLTMGR!FltClose` at `0x14004bbc0`
- `FLTMGR!FltReferenceContext` at `0x14004baec`
- `FLTMGR!FltReferenceContext` at `0x14004baec`
- `FLTMGR!FltReleaseContext` at `0x14004bb9d`
- `FLTMGR!FltReleaseContext` at `0x14004bb9d`

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
      HsmDbgBreakOnStatus(v21);
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
  HsmDbgBreakOnStatus((int)v23);
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
0x14004ba24  push    rbp
0x14004ba26  push    rbx
0x14004ba27  push    rsi
0x14004ba28  push    rdi
0x14004ba29  push    r12
0x14004ba2b  push    r13
0x14004ba2d  push    r14
0x14004ba2f  push    r15
0x14004ba31  lea     rbp, [rsp-1Fh]
0x14004ba36  sub     rsp, 0A8h
0x14004ba3d  mov     rax, cs:__security_cookie
0x14004ba44  xor     rax, rsp
0x14004ba47  mov     [rbp+57h+var_48], rax
0x14004ba4b  mov     rsi, [rdx+10h]
0x14004ba4f  xor     eax, eax
0x14004ba51  mov     [rbp+57h+var_50], rax
0x14004ba55  xorps   xmm0, xmm0
0x14004ba58  mov     eax, [rdx+24h]
0x14004ba5b  mov     r15, r9
0x14004ba5e  movups  [rbp+57h+FileInformation], xmm0
0x14004ba62  inc     eax
0x14004ba64  xor     r14d, r14d
0x14004ba67  movups  [rbp+57h+var_60], xmm0
0x14004ba6b  mov     [rdx+24h], eax
0x14004ba6e  mov     rbx, 0FFFFF78000000014h
0x14004ba78  mov     r9, rcx
0x14004ba7b  mov     [rbp+57h+var_90], r14
0x14004ba7f  mov     rdi, r8
0x14004ba82  mov     [rbp+57h+var_88], r15
0x14004ba86  mov     r13, rdx
0x14004ba89  mov     rbx, [rbx]
0x14004ba8c  mov     rcx, [rsi+28h]
0x14004ba90  test    rcx, rcx
0x14004ba93  jz      short loc_14004BACF
0x14004ba95  mov     rdx, qword ptr cs:__Config+8
0x14004ba9c  add     rdx, rcx
0x14004ba9f  cmp     rdx, rbx
0x14004baa2  jl      short loc_14004BACF
0x14004baa4  mov     eax, [r13+24h]
0x14004baa8  dec     eax
0x14004baaa  mov     [r13+24h], eax
0x14004baae  mov     rcx, [rbp+57h+var_48]
0x14004bab2  xor     rcx, rsp; StackCookie
0x14004bab5  call    __security_check_cookie
0x14004baba  add     rsp, 0A8h
0x14004bac1  pop     r15
0x14004bac3  pop     r14
0x14004bac5  pop     r13
0x14004bac7  pop     r12
0x14004bac9  pop     rdi
0x14004baca  pop     rsi
0x14004bacb  pop     rbx
0x14004bacc  pop     rbp
0x14004bacd  retn
0x14004bacf  mov     r12, [rsi+10h]
0x14004bad3  mov     rax, [rsi+20h]
0x14004bad7  mov     [rbp+57h+var_80], rax
0x14004badb  mov     rcx, [r12+20h]
0x14004bae0  mov     [rbp+57h+Instance], rcx
0x14004bae4  test    r8, r8
0x14004bae7  jz      short loc_14004BAFA
0x14004bae9  mov     rcx, r8; Context
0x14004baec  call    cs:__imp_FltReferenceContext
0x14004baf3  nop     dword ptr [rax+rax+00h]
0x14004baf8  jmp     short loc_14004BB14
0x14004bafa  mov     rdx, rcx; Instance
0x14004bafd  mov     r8, r15; FileObject
0x14004bb00  mov     rcx, r9; CallbackData
0x14004bb03  call    HsmpGetStreamHandleContext
0x14004bb08  mov     rdi, rax
0x14004bb0b  test    rax, rax
0x14004bb0e  jz      loc_14004BBCE
0x14004bb14  mov     rcx, [rbp+57h+Instance]; Instance
0x14004bb18  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14004bb1c  xorps   xmm0, xmm0
0x14004bb1f  mov     qword ptr [rbp+57h+FileInformation], 0
0x14004bb27  mov     r9d, 28h ; '('; Length
0x14004bb2d  mov     [rbp+57h+var_50], 0
0x14004bb35  mov     rdx, r15; FileObject
0x14004bb38  mov     qword ptr [rbp+57h+FileInformation+8], rbx
0x14004bb3c  movdqu  [rbp+57h+var_60], xmm0
0x14004bb41  mov     [rsp+0E0h+FileInformationClass], 4; FileInformationClass
0x14004bb49  call    cs:__imp_FltSetInformationFile
0x14004bb50  nop     dword ptr [rax+rax+00h]
0x14004bb55  mov     ecx, eax
0x14004bb57  mov     dword ptr [rbp+57h+var_90], eax
0x14004bb5a  call    HsmDbgBreakOnStatus
0x14004bb5f  mov     eax, dword ptr [rbp+57h+var_90]
0x14004bb62  test    eax, eax
0x14004bb64  js      loc_14004BC82
0x14004bb6a  mov     rcx, r13
0x14004bb6d  mov     [rsi+28h], rbx
0x14004bb71  call    HsmpGetLastHydrationTime
0x14004bb76  mov     r9, rax
0x14004bb79  call    HsmpGetStreamSize
0x14004bb7e  mov     rdx, rax
0x14004bb81  mov     r8, rbx
0x14004bb84  mov     rcx, rbx
0x14004bb87  call    TlmWriteLastAccessedTimeChangedEvent
0x14004bb8c  test    r14, r14
0x14004bb8f  jnz     short loc_14004BBAE
0x14004bb91  test    rdi, rdi
0x14004bb94  jz      loc_14004BAA4
0x14004bb9a  mov     rcx, rdi; Context
0x14004bb9d  call    cs:__imp_FltReleaseContext
0x14004bba4  nop     dword ptr [rax+rax+00h]
0x14004bba9  jmp     loc_14004BAA4
0x14004bbae  mov     rcx, r15; Object
0x14004bbb1  call    cs:__imp_ObfDereferenceObject
0x14004bbb8  nop     dword ptr [rax+rax+00h]
0x14004bbbd  mov     rcx, r14; FileHandle
0x14004bbc0  call    cs:__imp_FltClose
0x14004bbc7  nop     dword ptr [rax+rax+00h]
0x14004bbcc  jmp     short loc_14004BB91
0x14004bbce  mov     r15, [rbp+57h+var_80]
0x14004bbd2  lea     rax, [rbp+57h+var_88]
0x14004bbd6  mov     rdx, [r12+20h]
0x14004bbdb  mov     r9d, 100100h
0x14004bbe1  mov     [rsp+0E0h+var_A0], rax
0x14004bbe6  mov     r8, r15
0x14004bbe9  lea     rax, [rbp+57h+var_90]
0x14004bbed  mov     rcx, r12
0x14004bbf0  mov     [rsp+0E0h+var_A8], rax
0x14004bbf5  mov     byte ptr [rsp+0E0h+var_B0], r14b
0x14004bbfa  mov     dword ptr [rsp+0E0h+var_B8], 200000h
0x14004bc02  call    HsmpOpenFileByIdEx
0x14004bc07  mov     ecx, eax
0x14004bc09  mov     r14d, eax
0x14004bc0c  call    HsmDbgBreakOnStatus
0x14004bc11  test    r14d, r14d
0x14004bc14  jns     short loc_14004BC75
0x14004bc16  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc1d  lea     rdx, WPP_GLOBAL_Control
0x14004bc24  cmp     rcx, rdx
0x14004bc27  jnz     short loc_14004BC3E
0x14004bc29  mov     r14, [rbp+57h+var_90]
0x14004bc2d  mov     r15, [rbp+57h+var_88]
0x14004bc31  mov     qword ptr [rsi+28h], 0
0x14004bc39  jmp     loc_14004BB8C
0x14004bc3e  mov     edx, [rcx+2Ch]
0x14004bc41  test    dl, 1
0x14004bc44  jz      short loc_14004BC29
0x14004bc46  cmp     byte ptr [rcx+29h], 3
0x14004bc4a  jb      short loc_14004BC29
0x14004bc4c  mov     rcx, [rcx+18h]
0x14004bc50  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14004bc57  mov     [rsp+0E0h+var_B0], r14d
0x14004bc5c  mov     edx, 34h ; '4'
0x14004bc61  mov     [rsp+0E0h+var_B8], r15
0x14004bc66  mov     r9, r12
0x14004bc69  mov     qword ptr [rsp+0E0h+FileInformationClass], rsi
0x14004bc6e  call    WPP_SF_qqqd
0x14004bc73  jmp     short loc_14004BC29
0x14004bc75  mov     r14, [rbp+57h+var_90]
0x14004bc79  mov     r15, [rbp+57h+var_88]
0x14004bc7d  jmp     loc_14004BB14
0x14004bc82  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc89  lea     rdx, WPP_GLOBAL_Control
0x14004bc90  cmp     rcx, rdx
0x14004bc93  jz      short loc_14004BC31
0x14004bc95  mov     edx, [rcx+2Ch]
0x14004bc98  test    dl, 1
0x14004bc9b  jz      short loc_14004BC31
0x14004bc9d  cmp     byte ptr [rcx+29h], 3
0x14004bca1  jb      short loc_14004BC31
0x14004bca3  mov     rcx, [rcx+18h]
0x14004bca7  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14004bcae  mov     [rsp+0E0h+var_B0], eax
0x14004bcb2  mov     edx, 35h ; '5'
0x14004bcb7  mov     rax, [rbp+57h+var_80]
0x14004bcbb  mov     r9, r12
0x14004bcbe  mov     [rsp+0E0h+var_B8], rax
0x14004bcc3  mov     qword ptr [rsp+0E0h+FileInformationClass], rsi
0x14004bcc8  call    WPP_SF_qqqd
0x14004bccd  jmp     loc_14004BC31
```
