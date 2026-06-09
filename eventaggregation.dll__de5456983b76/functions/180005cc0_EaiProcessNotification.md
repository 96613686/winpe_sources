# EaiProcessNotification

- ea: `0x180005cc0`
- end: `0x1800062cf`
- name: `EaiProcessNotification`
- size: `1551`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8, char, __int64, unsigned int, int, _DWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800038c0`
- `0x1800054c0`

## callees

- `0x1800018a0`
- `0x180001970`
- `0x180003ca0`
- `0x180003d90`
- `0x180004180`
- `0x1800041c0`
- `0x180004330`
- `0x180005cc0`
- `0x1800069d0`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006141`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006141`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005dc8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005dc8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005dbe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000629f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005dbe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000629f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005dce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005dce`

## pseudocode

```c
__int64 __fastcall EaiProcessNotification(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        char a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        _DWORD *a8)
{
  char v10; // r12
  int v11; // r15d
  unsigned int v12; // r13d
  int v13; // esi
  __int64 *v14; // rdx
  __int64 v15; // rcx
  char v16; // al
  bool v17; // zf
  __int64 v18; // rcx
  char v19; // cl
  char v20; // al
  __int64 v21; // rdx
  int v22; // eax
  char v23; // al
  char v24; // r12
  __int64 *v25; // rax
  __int64 v26; // rdx
  char v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v29; // [rsp+41h] [rbp-BFh]
  unsigned int v30; // [rsp+44h] [rbp-BCh] BYREF
  char v31; // [rsp+48h] [rbp-B8h]
  int v32; // [rsp+4Ch] [rbp-B4h] BYREF
  BOOL v33; // [rsp+50h] [rbp-B0h] BYREF
  BOOL v34; // [rsp+54h] [rbp-ACh] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR v38; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v43)(); // [rsp+B0h] [rbp-50h]
  __int64 v44; // [rsp+B8h] [rbp-48h]
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+C0h] [rbp-40h] BYREF
  __int16 *v46; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+D8h] [rbp-28h]
  int v48; // [rsp+DCh] [rbp-24h]
  __int64 *v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+F8h] [rbp-8h]
  char *v53; // [rsp+100h] [rbp+0h]
  __int64 v54; // [rsp+108h] [rbp+8h]
  unsigned int *v55; // [rsp+110h] [rbp+10h]
  __int64 v56; // [rsp+118h] [rbp+18h]
  int *v57; // [rsp+120h] [rbp+20h]
  __int64 v58; // [rsp+128h] [rbp+28h]
  BOOL *v59; // [rsp+130h] [rbp+30h]
  __int64 v60; // [rsp+138h] [rbp+38h]
  BOOL *v61; // [rsp+140h] [rbp+40h]
  __int64 v62; // [rsp+148h] [rbp+48h]
  int *v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+158h] [rbp+58h]

  v28 = a4;
  v10 = a4;
  v29 = a3;
  v31 = *(_BYTE *)(a1 + 64);
  v11 = 0;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    EventDescriptor.Keyword = 0;
    v43 = (__int64 (__fastcall *)())&v36;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v36 = a1;
    v44 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v41 = &word_18000F55E;
    UserData.Reserved = 2;
    v42 = 0x10000002BLL;
    v30 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  RtlAcquireSRWLockExclusive(a1 + 80);
  *(_DWORD *)(a1 + 88) = GetCurrentThreadId();
  EaLibClearAndReleaseTimer(a1);
  v12 = *(_DWORD *)(a1 + 108);
  v30 = v12;
  if ( !v12 )
  {
    v13 = 0;
    goto LABEL_58;
  }
  v14 = *(__int64 **)(a1 + 56);
  v15 = *v14;
  if ( *v14 && *(_DWORD *)a2 == *(_DWORD *)(v15 + 8) && *(_DWORD *)(a2 + 4) == *(_DWORD *)(v15 + 12) )
  {
    v16 = EaiEvaluateConditions(a1);
    if ( v29 )
    {
      if ( v16 )
      {
LABEL_10:
        *(_BYTE *)(a1 + 64) = 1;
LABEL_11:
        EaiSignalCallback(0, a1, a2, a5, a6, a7, (__int64)a8);
        *(_BYTE *)(a1 + 65) = 1;
        EaLibCreateAndSetLimitTimer(a1);
        v13 = 1;
        goto LABEL_58;
      }
      if ( (*(_BYTE *)(a1 + 140) & 4) == 0 )
      {
        if ( a8 )
          *a8 = 2;
        v17 = (*(_BYTE *)(a1 + 140) & 0x10) == 0;
        *(_BYTE *)(a1 + 64) = 1;
        if ( !v17 && *(_QWORD *)(a1 + 40) )
          goto LABEL_17;
        v18 = a1;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    if ( v10 )
    {
      v19 = *(_BYTE *)(a1 + 64);
      if ( !v19 )
      {
        if ( v16 )
          goto LABEL_10;
        if ( (*(_BYTE *)(a1 + 140) & 4) == 0 )
        {
          *(_BYTE *)(a1 + 64) = 1;
          if ( !(unsigned __int8)EaiOnLatchCallbackAvailable(a1) )
          {
LABEL_19:
            v11 = EaiResetTriggerPayload(v18, a5, a6);
            v13 = 1;
            goto LABEL_58;
          }
LABEL_17:
          EaiSignalCallback(2, a1, a2, a5, a6, a7, (__int64)a8);
          v13 = 1;
          goto LABEL_58;
        }
        goto LABEL_20;
      }
      if ( v19 == 1 )
      {
        if ( v16 )
          goto LABEL_11;
        if ( (*(_BYTE *)(a1 + 140) & 4) == 0 )
        {
          *(_BYTE *)(a1 + 64) = 1;
          if ( !(unsigned __int8)EaiOnLatchCallbackAvailable(a1) )
            goto LABEL_19;
          goto LABEL_17;
        }
LABEL_20:
        if ( a8 )
          *a8 = 0;
      }
LABEL_22:
      v13 = 1;
      goto LABEL_58;
    }
    v20 = *(_BYTE *)(a1 + 64);
    if ( v20 )
    {
      if ( v20 != 1 )
        goto LABEL_22;
      if ( (*(_BYTE *)(a1 + 140) & 1) == 0 || *(_BYTE *)(a1 + 65) )
      {
        EaiSignalCallback(1, a1, a2, a5, a6, a7, (__int64)a8);
      }
      else
      {
        EaiSignalCallback(0, a1, a2, *(_QWORD *)(a1 + 96), *(_DWORD *)(a1 + 104), a7, (__int64)a8);
        EaLibCreateAndSetLimitTimer(a1);
      }
      *(_WORD *)(a1 + 64) = 0;
      EaiFreeTriggerPayload(a1);
      v13 = 1;
    }
    else
    {
      EaiSignalCallback(1, a1, a2, 0, 0, a7, (__int64)a8);
      v13 = 1;
    }
  }
  else
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    *(_QWORD *)&EventDescriptor.Level = *(_QWORD *)a2;
    *(_QWORD *)&EventDescriptor.Id = v10 != 0;
    v21 = v14[1];
    UserData.Ptr = (ULONGLONG)&EventDescriptor;
    v13 = 0;
    v41 = 0;
    *(_QWORD *)&UserData.Size = EaiAggregationConditionNextChild;
    v43 = EaiSetAggregationConditionVisitNode;
    v42 = 0;
    v22 = EapTreeTraverse(&UserData, v21);
    if ( v22 < 0 )
      v11 = v22;
    if ( v11 >= 0 )
    {
      v23 = EaiEvaluateConditions(a1);
      v24 = v23;
      if ( *(_BYTE *)(a1 + 64) == 1 )
      {
        if ( v23 && !*(_BYTE *)(a1 + 65) )
        {
          EaiSignalCallback(0, a1, a2, *(_QWORD *)(a1 + 96), *(_DWORD *)(a1 + 104), a7, (__int64)a8);
          *(_BYTE *)(a1 + 65) = 1;
          EaLibCreateAndSetLimitTimer(a1);
          EaiFreeTriggerPayload(a1);
        }
        if ( *(_BYTE *)(a1 + 64) == 1 && !v24 && *(_BYTE *)(a1 + 65) )
        {
          EaiSignalCallback(1, a1, a2, 0, 0, a7, (__int64)a8);
          v25 = *(__int64 **)(a1 + 56);
          *(_BYTE *)(a1 + 65) = 0;
          v26 = *v25;
          if ( *v25 && (*(_DWORD *)(v26 + 8) || *(_DWORD *)(v26 + 12)) )
            *(_BYTE *)(a1 + 64) = 0;
          EaiFreeTriggerPayload(a1);
        }
      }
      LOBYTE(v12) = v30;
      v10 = v28;
    }
  }
LABEL_58:
  *(_DWORD *)(a1 + 88) = 0;
  RtlReleaseSRWLockExclusive(a1 + 80);
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v37 = a1;
    v49 = &v37;
    *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)a2;
    p_EventDescriptor = &EventDescriptor;
    v53 = &v28;
    v55 = &v30;
    v32 = v29;
    v57 = &v32;
    v38.Keyword = 0;
    v33 = v31 != 0;
    v50 = 8;
    v59 = &v33;
    v52 = 8;
    v34 = v10 != 0;
    v28 = v12;
    v61 = &v34;
    v54 = 1;
    v63 = &v35;
    *(_DWORD *)&v38.Level = 516;
    v45.Ptr = (ULONGLONG)off_180012008;
    v30 = v13;
    v56 = 4;
    v58 = 4;
    v60 = 4;
    v62 = 4;
    v35 = v11;
    v64 = 4;
    *(_DWORD *)&v38.Id = 184549376;
    v45.Size = *(unsigned __int16 *)off_180012008;
    v46 = &word_18000F336;
    v45.Reserved = 2;
    v47 = 127;
    v48 = 1;
    LODWORD(v36) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v38, 0, 0, 0xAu, &v45);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005cc0  mov     [rsp-8+arg_10], rbx
0x180005cc5  push    rbp
0x180005cc6  push    rsi
0x180005cc7  push    rdi
0x180005cc8  push    r12
0x180005cca  push    r13
0x180005ccc  push    r14
0x180005cce  push    r15
0x180005cd0  lea     rbp, [rsp-70h]
0x180005cd5  sub     rsp, 170h
0x180005cdc  mov     rax, cs:__security_cookie
0x180005ce3  xor     rax, rsp
0x180005ce6  mov     [rbp+0A0h+var_40], rax
0x180005cea  mov     rsi, [rbp+0A0h+arg_20]
0x180005cf1  mov     rbx, rcx
0x180005cf4  mov     rdi, [rbp+0A0h+arg_38]
0x180005cfb  xor     ecx, ecx
0x180005cfd  mov     r14, rdx
0x180005d00  mov     [rsp+1A0h+var_160], r9b
0x180005d05  movzx   r12d, r9b
0x180005d09  mov     [rsp+1A0h+var_15F], r8b
0x180005d0e  movzx   eax, byte ptr [rbx+40h]
0x180005d12  lea     rdx, _TraceLoggingMetadata
0x180005d19  mov     [rsp+1A0h+var_158], al
0x180005d1d  mov     r15d, ecx
0x180005d20  mov     eax, cs:dword_180012000
0x180005d26  cmp     eax, 4
0x180005d29  jbe     loc_180005DC4
0x180005d2f  mov     [rbp+0A0h+EventDescriptor.Keyword], rcx
0x180005d33  lea     rax, [rsp+1A0h+var_140]
0x180005d38  mov     [rbp+0A0h+var_F0], rax
0x180005d3c  xor     r9d, r9d; RelatedActivityId
0x180005d3f  movzx   eax, cs:word_18000F554
0x180005d46  xor     r8d, r8d; ActivityId
0x180005d49  mov     dword ptr [rbp+0A0h+EventDescriptor.Level], eax
0x180005d4c  mov     rax, cs:off_180012008
0x180005d53  mov     [rbp+0A0h+var_110.Ptr], rax
0x180005d57  mov     [rsp+1A0h+var_140], rbx
0x180005d5c  mov     [rbp+0A0h+var_E8], 8
0x180005d64  mov     dword ptr [rbp+0A0h+EventDescriptor.Id], 0B000000h
0x180005d6b  movzx   eax, word ptr [rax]
0x180005d6e  mov     [rbp+0A0h+var_110.Size], eax
0x180005d71  lea     rax, word_18000F55E
0x180005d78  mov     [rbp+0A0h+var_100], rax
0x180005d7c  lea     rax, _TraceLoggingMetadataEnd
0x180005d83  sub     eax, edx
0x180005d85  mov     dword ptr [rbp+0A0h+var_110.0Ch], 2
0x180005d8c  mov     dword ptr [rbp+0A0h+var_F8], 2Bh ; '+'
0x180005d93  lea     rdx, [rbp+0A0h+EventDescriptor]; EventDescriptor
0x180005d97  mov     dword ptr [rbp+0A0h+var_F8+4], 1
0x180005d9e  mov     [rsp+1A0h+var_15C], eax
0x180005da2  mov     eax, [rsp+1A0h+var_15C]
0x180005da6  mov     rcx, cs:RegHandle; RegHandle
0x180005dad  lea     rax, [rbp+0A0h+var_110]
0x180005db1  mov     [rsp+1A0h+UserData], rax; UserData
0x180005db6  mov     [rsp+1A0h+UserDataCount], 3; UserDataCount
0x180005dbe  call    cs:__imp_EventWriteTransfer
0x180005dc4  lea     rcx, [rbx+50h]
0x180005dc8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180005dce  call    cs:__imp_GetCurrentThreadId
0x180005dd4  mov     rcx, rbx
0x180005dd7  mov     [rbx+58h], eax
0x180005dda  call    EaLibClearAndReleaseTimer
0x180005ddf  mov     r13d, [rbx+6Ch]
0x180005de3  mov     [rsp+1A0h+var_15C], r13d
0x180005de8  test    r13d, r13d
0x180005deb  jnz     short loc_180005DF4
0x180005ded  xor     esi, esi
0x180005def  jmp     loc_180006136
0x180005df4  mov     rdx, [rbx+38h]
0x180005df8  mov     rcx, [rdx]
0x180005dfb  test    rcx, rcx
0x180005dfe  jz      loc_18000601E
0x180005e04  mov     eax, [rcx+8]
0x180005e07  cmp     [r14], eax
0x180005e0a  jnz     loc_18000601E
0x180005e10  mov     eax, [rcx+0Ch]
0x180005e13  cmp     [r14+4], eax
0x180005e17  jnz     loc_18000601E
0x180005e1d  mov     rcx, rbx
0x180005e20  call    EaiEvaluateConditions
0x180005e25  cmp     [rsp+1A0h+var_15F], r15b
0x180005e2a  jz      loc_180005F0D
0x180005e30  test    al, al
0x180005e32  jz      short loc_180005E77
0x180005e34  mov     byte ptr [rbx+40h], 1
0x180005e38  mov     eax, [rbp+0A0h+arg_30]
0x180005e3e  mov     r9, rsi
0x180005e41  mov     [rsp+1A0h+var_170], rdi
0x180005e46  mov     r8, r14
0x180005e49  mov     dword ptr [rsp+1A0h+UserData], eax
0x180005e4d  mov     rdx, rbx
0x180005e50  mov     eax, [rbp+0A0h+arg_28]
0x180005e56  xor     ecx, ecx
0x180005e58  mov     [rsp+1A0h+UserDataCount], eax
0x180005e5c  call    EaiSignalCallback
0x180005e61  mov     rcx, rbx
0x180005e64  mov     byte ptr [rbx+41h], 1
0x180005e68  call    EaLibCreateAndSetLimitTimer
0x180005e6d  mov     esi, 1
0x180005e72  jmp     loc_180006136
0x180005e77  test    byte ptr [rbx+8Ch], 4
0x180005e7e  jnz     short loc_180005EFB
0x180005e80  test    rdi, rdi
0x180005e83  jz      short loc_180005E8B
0x180005e85  mov     dword ptr [rdi], 2
0x180005e8b  test    byte ptr [rbx+8Ch], 10h
0x180005e92  mov     byte ptr [rbx+40h], 1
0x180005e96  jz      short loc_180005ED4
0x180005e98  cmp     [rbx+28h], r15
0x180005e9c  jz      short loc_180005ED4
0x180005e9e  mov     eax, [rbp+0A0h+arg_30]
0x180005ea4  mov     r9, rsi
0x180005ea7  mov     [rsp+1A0h+var_170], rdi
0x180005eac  mov     r8, r14
0x180005eaf  mov     dword ptr [rsp+1A0h+UserData], eax
0x180005eb3  mov     rdx, rbx
0x180005eb6  mov     eax, [rbp+0A0h+arg_28]
0x180005ebc  mov     ecx, 2
0x180005ec1  mov     [rsp+1A0h+UserDataCount], eax
0x180005ec5  call    EaiSignalCallback
0x180005eca  mov     esi, 1
0x180005ecf  jmp     loc_180006136
0x180005ed4  mov     rcx, rbx
0x180005ed7  mov     r8d, [rbp+0A0h+arg_28]
0x180005ede  mov     rdx, rsi
0x180005ee1  call    EaiResetTriggerPayload
0x180005ee6  mov     r15d, eax
0x180005ee9  mov     esi, 1
0x180005eee  test    eax, eax
0x180005ef0  js      loc_180006136
0x180005ef6  jmp     loc_180006136
0x180005efb  test    rdi, rdi
0x180005efe  jz      short loc_180005F03
0x180005f00  mov     [rdi], r15d
0x180005f03  mov     esi, 1
0x180005f08  jmp     loc_180006136
0x180005f0d  test    r12b, r12b
0x180005f10  jz      short loc_180005F6F
0x180005f12  movzx   ecx, byte ptr [rbx+40h]
0x180005f16  test    cl, cl
0x180005f18  jnz     short loc_180005F41
0x180005f1a  test    al, al
0x180005f1c  jnz     loc_180005E34
0x180005f22  test    byte ptr [rbx+8Ch], 4
0x180005f29  jnz     short loc_180005EFB
0x180005f2b  mov     rcx, rbx
0x180005f2e  mov     byte ptr [rbx+40h], 1
0x180005f32  call    EaiOnLatchCallbackAvailable
0x180005f37  test    al, al
0x180005f39  jnz     loc_180005E9E
0x180005f3f  jmp     short loc_180005ED7
0x180005f41  cmp     cl, 1
0x180005f44  jnz     short loc_180005F03
0x180005f46  test    al, al
0x180005f48  jnz     loc_180005E38
0x180005f4e  test    byte ptr [rbx+8Ch], 4
0x180005f55  jnz     short loc_180005EFB
0x180005f57  mov     [rbx+40h], cl
0x180005f5a  mov     rcx, rbx
0x180005f5d  call    EaiOnLatchCallbackAvailable
0x180005f62  test    al, al
0x180005f64  jnz     loc_180005E9E
0x180005f6a  jmp     loc_180005ED7
0x180005f6f  movzx   eax, byte ptr [rbx+40h]
0x180005f73  test    al, al
0x180005f75  jnz     short loc_180005FA8
0x180005f77  mov     eax, [rbp+0A0h+arg_30]
0x180005f7d  xor     r9d, r9d
0x180005f80  mov     [rsp+1A0h+var_170], rdi
0x180005f85  mov     r8, r14
0x180005f88  mov     dword ptr [rsp+1A0h+UserData], eax
0x180005f8c  mov     rdx, rbx
0x180005f8f  mov     ecx, 1
0x180005f94  mov     [rsp+1A0h+UserDataCount], r15d
0x180005f99  call    EaiSignalCallback
0x180005f9e  mov     esi, 1
0x180005fa3  jmp     loc_180006136
0x180005fa8  cmp     al, 1
0x180005faa  jnz     loc_180005F03
0x180005fb0  test    byte ptr [rbx+8Ch], 1
0x180005fb7  mov     r8, r14
0x180005fba  mov     eax, [rbp+0A0h+arg_30]
0x180005fc0  mov     rdx, rbx
0x180005fc3  mov     [rsp+1A0h+var_170], rdi
0x180005fc8  mov     dword ptr [rsp+1A0h+UserData], eax
0x180005fcc  jz      short loc_180005FF0
0x180005fce  cmp     [rbx+41h], r15b
0x180005fd2  jnz     short loc_180005FF0
0x180005fd4  mov     eax, [rbx+68h]
0x180005fd7  xor     ecx, ecx
0x180005fd9  mov     r9, [rbx+60h]
0x180005fdd  mov     [rsp+1A0h+UserDataCount], eax
0x180005fe1  call    EaiSignalCallback
0x180005fe6  mov     rcx, rbx
0x180005fe9  call    EaLibCreateAndSetLimitTimer
0x180005fee  jmp     short loc_180006007
0x180005ff0  mov     eax, [rbp+0A0h+arg_28]
0x180005ff6  mov     r9, rsi
0x180005ff9  mov     ecx, 1
0x180005ffe  mov     [rsp+1A0h+UserDataCount], eax
0x180006002  call    EaiSignalCallback
0x180006007  mov     rcx, rbx
0x18000600a  mov     [rbx+40h], r15w
0x18000600f  call    EaiFreeTriggerPayload
0x180006014  mov     esi, 1
0x180006019  jmp     loc_180006136
0x18000601e  xor     eax, eax
0x180006020  lea     rcx, [rbp+0A0h+var_110]
0x180006024  mov     qword ptr [rbp+0A0h+EventDescriptor.Id], rax
0x180006028  test    r12b, r12b
0x18000602b  mov     rax, [r14]
0x18000602e  mov     qword ptr [rbp+0A0h+EventDescriptor.Level], rax
0x180006032  setnz   byte ptr [rbp+0A0h+EventDescriptor.Id]
0x180006036  mov     rdx, [rdx+8]
0x18000603a  lea     rax, [rbp+0A0h+EventDescriptor]
0x18000603e  mov     [rbp+0A0h+var_110.Ptr], rax
0x180006042  xor     esi, esi
0x180006044  lea     rax, EaiAggregationConditionNextChild
0x18000604b  mov     [rbp+0A0h+var_100], rsi
0x18000604f  mov     qword ptr [rbp+0A0h+var_110.Size], rax
0x180006053  lea     rax, EaiSetAggregationConditionVisitNode
0x18000605a  mov     [rbp+0A0h+var_F0], rax
0x18000605e  mov     [rbp+0A0h+var_F8], rsi
0x180006062  call    EapTreeTraverse
0x180006067  test    eax, eax
0x180006069  cmovs   r15d, eax
0x18000606d  test    r15d, r15d
0x180006070  js      loc_180006136
0x180006076  mov     rcx, rbx
0x180006079  call    EaiEvaluateConditions
0x18000607e  cmp     byte ptr [rbx+40h], 1
0x180006082  movzx   r12d, al
0x180006086  mov     r13d, [rbp+0A0h+arg_30]
0x18000608d  jnz     loc_18000612B
0x180006093  test    al, al
0x180006095  jz      short loc_1800060D3
0x180006097  cmp     [rbx+41h], sil
0x18000609b  jnz     short loc_1800060D3
0x18000609d  mov     ecx, [rbx+68h]
0x1800060a0  mov     r8, r14
0x1800060a3  mov     r9, [rbx+60h]
0x1800060a7  mov     rdx, rbx
0x1800060aa  mov     [rsp+1A0h+var_170], rdi
0x1800060af  mov     dword ptr [rsp+1A0h+UserData], r13d
0x1800060b4  mov     [rsp+1A0h+UserDataCount], ecx
0x1800060b8  xor     ecx, ecx
0x1800060ba  call    EaiSignalCallback
0x1800060bf  mov     rcx, rbx
0x1800060c2  mov     byte ptr [rbx+41h], 1
0x1800060c6  call    EaLibCreateAndSetLimitTimer
0x1800060cb  mov     rcx, rbx
0x1800060ce  call    EaiFreeTriggerPayload
0x1800060d3  cmp     byte ptr [rbx+40h], 1
0x1800060d7  jnz     short loc_18000612B
0x1800060d9  test    r12b, r12b
0x1800060dc  jnz     short loc_18000612B
0x1800060de  cmp     [rbx+41h], sil
0x1800060e2  jz      short loc_18000612B
0x1800060e4  mov     [rsp+1A0h+var_170], rdi
0x1800060e9  xor     r9d, r9d
0x1800060ec  mov     dword ptr [rsp+1A0h+UserData], r13d
0x1800060f1  mov     r8, r14
0x1800060f4  mov     rdx, rbx
0x1800060f7  mov     [rsp+1A0h+UserDataCount], esi
0x1800060fb  mov     ecx, 1
0x180006100  call    EaiSignalCallback
0x180006105  mov     rax, [rbx+38h]
0x180006109  mov     [rbx+41h], sil
0x18000610d  mov     rdx, [rax]
0x180006110  test    rdx, rdx
0x180006113  jz      short loc_180006123
0x180006115  cmp     [rdx+8], esi
0x180006118  jnz     short loc_18000611F
0x18000611a  cmp     [rdx+0Ch], esi
0x18000611d  jz      short loc_180006123
0x18000611f  mov     [rbx+40h], sil
0x180006123  mov     rcx, rbx
0x180006126  call    EaiFreeTriggerPayload
0x18000612b  mov     r13d, [rsp+1A0h+var_15C]
0x180006130  movzx   r12d, [rsp+1A0h+var_160]
0x180006136  lea     rcx, [rbx+50h]
0x18000613a  mov     dword ptr [rbx+58h], 0
0x180006141  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180006147  mov     eax, cs:dword_180012000
0x18000614d  cmp     eax, 4
0x180006150  jbe     loc_1800062A5
0x180006156  xor     ecx, ecx
0x180006158  mov     [rsp+1A0h+var_138], rbx
0x18000615d  cmp     [rsp+1A0h+var_158], cl
0x180006161  lea     rax, [rsp+1A0h+var_138]
0x180006166  mov     [rbp+0A0h+var_C0], rax
0x18000616a  lea     rdx, [rsp+1A0h+var_130]; EventDescriptor
0x18000616f  mov     rax, [r14]
0x180006172  mov     qword ptr [rbp+0A0h+EventDescriptor.Id], rax
0x180006176  lea     rax, [rbp+0A0h+EventDescriptor]
0x18000617a  mov     [rbp+0A0h+var_B0], rax
0x18000617e  lea     rax, [rsp+1A0h+var_160]
0x180006183  mov     [rbp+0A0h+var_A0], rax
0x180006187  lea     rax, [rsp+1A0h+var_15C]
  ... truncated ...
```
