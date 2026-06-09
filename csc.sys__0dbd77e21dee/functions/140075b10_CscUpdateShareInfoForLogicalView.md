# CscUpdateShareInfoForLogicalView

- ea: `0x140075b10`
- end: `0x140075f5e`
- name: `CscUpdateShareInfoForLogicalView`
- size: `1102`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PCUNICODE_STRING String2, __int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140062b70`
- `0x14008caec`

## callees

- `0x14000a634`
- `0x14000dfc0`
- `0x1400119d0`
- `0x140012c48`
- `0x1400190ec`
- `0x14001a624`
- `0x14001a69c`
- `0x14001b710`
- `0x14001d504`
- `0x140075b10`
- `0x140075f70`
- `0x1400761e0`
- `0x140076458`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140075eea`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140075eea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140075cc4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140075d17`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140075cc4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140075d17`
- `ntoskrnl!ExReleaseFastMutex` at `0x140075d63`
- `ntoskrnl!ExReleaseFastMutex` at `0x140075d74`
- `ntoskrnl!ExReleaseFastMutex` at `0x140075d63`
- `ntoskrnl!ExReleaseFastMutex` at `0x140075d74`

## pseudocode

```c
__int64 __fastcall CscUpdateShareInfoForLogicalView(
        _QWORD *a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        PCUNICODE_STRING String2,
        _DWORD *a7,
        __int64 a8)
{
  __int64 v9; // r15
  __int64 v11; // rdi
  __int64 v12; // r13
  bool v13; // r14
  __int64 v14; // rdx
  signed __int64 v15; // rbp
  _DWORD *v16; // rsi
  int Entry; // ebp
  int v18; // esi
  __int64 v20; // rax
  struct _FAST_MUTEX *v21; // rcx
  char v22; // r14
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  struct _FAST_MUTEX *v27; // rcx
  char v28; // al
  int v29; // ecx
  char v30; // r8
  char v31; // al
  signed __int64 v32; // rbp
  int v33; // [rsp+40h] [rbp-58h] BYREF
  signed __int64 v34; // [rsp+48h] [rbp-50h] BYREF
  __int64 v35; // [rsp+50h] [rbp-48h]
  char v36; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v37; // [rsp+B0h] [rbp+18h]

  v37 = a3;
  v9 = a1[7];
  v11 = *(_QWORD *)(v9 + 128);
  v35 = *(_QWORD *)(a1[9] + 40LL);
  v12 = *(_QWORD *)(v11 + 48);
  v13 = a1[10] != (_QWORD)CscDeviceObject;
  v33 = 0;
  v14 = *(_QWORD *)(v11 + 48);
  v36 = 0;
  v15 = _InterlockedCompareExchange64((volatile signed __int64 *)(v14 + 40), 0, 0);
  v34 = v15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v30 = 78;
    v31 = 89;
    if ( v15 )
      v30 = 89;
    if ( !v13 )
      v31 = 78;
    WPP_SF_ZDcc(
      WPP_GLOBAL_Control->AttachedDevice,
      79,
      (unsigned int)WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      *(_QWORD *)(v11 + 56),
      a2,
      v30,
      v31);
  }
  v16 = a7;
  if ( a7 )
    *a7 = 0;
  if ( !v13 )
  {
    Entry = 0;
    v18 = 3162;
    goto LABEL_12;
  }
  if ( !v15 )
  {
    if ( (a2 & 4) != 0 )
      a2 = 12;
    else
      a2 |= 0x10u;
    Entry = CscStoreFindOrCreateEntry((unsigned int)&v34, (unsigned int)&v33, 0, *(_QWORD *)(v11 + 56), a2, 0, 0, a8);
    if ( Entry < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_ZD(
          WPP_GLOBAL_Control->AttachedDevice,
          80,
          (unsigned int)WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
          *(_QWORD *)(v11 + 56),
          Entry);
      v18 = 3205;
      goto LABEL_12;
    }
    v22 = 1;
    v32 = v34;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v34, v9, 0);
    if ( !v16 )
      goto LABEL_32;
    v28 = v33;
    v29 = v33 & 2;
    if ( (v33 & 2) != 0 )
      *v16 |= 2u;
    if ( String2 )
    {
      if ( (v28 & 1) != 0 )
      {
        *v16 |= 2 - (RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v11 + 56), String2, 1u) != 0);
LABEL_32:
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(v11 + 48) + 40LL), v32, 0) )
        {
          CscStoreDereferenceEntry(&v34);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_qqq(
              WPP_GLOBAL_Control->AttachedDevice,
              82,
              WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
              v32,
              v9,
              0);
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            83,
            WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
            *(_QWORD *)(v11 + 56));
        }
        goto LABEL_21;
      }
    }
    else if ( (v28 & 1) != 0 )
    {
LABEL_40:
      *v16 |= 2u;
      goto LABEL_32;
    }
    if ( !v29 )
      goto LABEL_32;
    goto LABEL_40;
  }
  CscAcquireLViewLock(v11);
  v20 = *(_QWORD *)(v11 + 48);
  v21 = (struct _FAST_MUTEX *)(v20 + 56);
  v22 = (*(_DWORD *)(v20 + 4) & 0x800) != 0;
  *(_QWORD *)(v20 + 112) = 0;
  if ( *(_BYTE *)(v20 + 120) )
    ExReleaseFastMutexUnsafe(v21);
  else
    ExReleaseFastMutex(v21);
LABEL_21:
  v18 = 0;
  CscAcquireLViewLock(v11);
  Entry = CscStoreEntryIsTransparentlyCached(*(_QWORD *)(v12 + 40), &v36);
  v23 = *(_QWORD *)(v11 + 48);
  v24 = *(_DWORD *)(v23 + 4);
  if ( v36 )
    v25 = v24 | 0x2000;
  else
    v25 = v24 & 0xFFFFDFFF;
  *(_DWORD *)(v23 + 4) = v25;
  v26 = *(_QWORD *)(v11 + 48);
  v27 = (struct _FAST_MUTEX *)(v26 + 56);
  *(_QWORD *)(v26 + 112) = 0;
  if ( *(_BYTE *)(v26 + 120) )
    ExReleaseFastMutexUnsafe(v27);
  else
    ExReleaseFastMutex(v27);
  if ( (a2 & 4) == 0 )
    Entry = CscLViewUpdateInfoWorker(v11, v35, v37, a4, a5, v22);
LABEL_12:
  CscLoadLViewWasPreviouslyOffline(v11);
  CscFlushLViewWasPreviouslyOffline(v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      84,
      WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      (unsigned int)Entry,
      v18);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x140075b10  mov     r11, rsp
0x140075b13  mov     [r11+10h], rbx
0x140075b17  mov     [r11+18h], r8
0x140075b1b  push    rbp
0x140075b1c  push    rsi
0x140075b1d  push    rdi
0x140075b1e  push    r12
0x140075b20  push    r13
0x140075b22  push    r14
0x140075b24  push    r15
0x140075b26  sub     rsp, 60h
0x140075b2a  mov     rax, [rcx+48h]
0x140075b2e  mov     ebx, edx
0x140075b30  mov     r15, [rcx+38h]
0x140075b34  mov     r12d, r9d
0x140075b37  mov     rax, [rax+28h]
0x140075b3b  mov     rdi, [r15+80h]
0x140075b42  mov     [rsp+98h+var_48], rax
0x140075b47  mov     rax, cs:CscDeviceObject
0x140075b4e  cmp     [rcx+50h], rax
0x140075b52  mov     r13, [rdi+30h]
0x140075b56  setnz   r14b
0x140075b5a  xor     r8d, r8d
0x140075b5d  mov     [r11-58h], r8d
0x140075b61  mov     ecx, r8d
0x140075b64  mov     rdx, [rdi+30h]
0x140075b68  xor     eax, eax
0x140075b6a  mov     [r11+8], r8b
0x140075b6e  lock cmpxchg [rdx+28h], rcx
0x140075b74  mov     rbp, rax
0x140075b77  mov     [r11-50h], rax
0x140075b7b  mov     r10, cs:WPP_GLOBAL_Control
0x140075b82  lea     rax, WPP_GLOBAL_Control
0x140075b89  cmp     r10, rax
0x140075b8c  jz      short loc_140075B9B
0x140075b8e  mov     ecx, [r10+2Ch]
0x140075b92  test    cl, 40h
0x140075b95  jnz     loc_140075E33
0x140075b9b  mov     rsi, [rsp+98h+arg_30]
0x140075ba3  test    rsi, rsi
0x140075ba6  jz      short loc_140075BAB
0x140075ba8  mov     [rsi], r8d
0x140075bab  test    r14b, r14b
0x140075bae  jz      loc_140075C8C
0x140075bb4  test    rbp, rbp
0x140075bb7  jnz     loc_140075C96
0x140075bbd  test    bl, 4
0x140075bc0  jnz     loc_140075E7B
0x140075bc6  or      ebx, 10h
0x140075bc9  mov     rax, [rsp+98h+arg_38]
0x140075bd1  lea     rdx, [rsp+98h+var_58]
0x140075bd6  mov     r9, [rdi+38h]
0x140075bda  lea     rcx, [rsp+98h+var_50]
0x140075bdf  mov     [rsp+98h+var_60], rax
0x140075be4  mov     [rsp+98h+var_68], r8
0x140075be9  mov     [rsp+98h+var_70], r8
0x140075bee  xor     r8d, r8d
0x140075bf1  mov     dword ptr [rsp+98h+var_78], ebx
0x140075bf5  call    CscStoreFindOrCreateEntry
0x140075bfa  mov     ebp, eax
0x140075bfc  test    eax, eax
0x140075bfe  jns     loc_140075E85
0x140075c04  mov     rcx, cs:WPP_GLOBAL_Control
0x140075c0b  lea     rax, WPP_GLOBAL_Control
0x140075c12  cmp     rcx, rax
0x140075c15  jnz     short loc_140075C65
0x140075c17  mov     esi, 0C85h
0x140075c1c  mov     rcx, rdi
0x140075c1f  call    CscLoadLViewWasPreviouslyOffline
0x140075c24  mov     rcx, rdi
0x140075c27  call    CscFlushLViewWasPreviouslyOffline
0x140075c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140075c33  lea     rax, WPP_GLOBAL_Control
0x140075c3a  cmp     rcx, rax
0x140075c3d  jz      short loc_140075C4A
0x140075c3f  mov     eax, [rcx+2Ch]
0x140075c42  test    al, 20h
0x140075c44  jnz     loc_140075F3D
0x140075c4a  mov     rbx, [rsp+98h+arg_8]
0x140075c52  mov     eax, ebp
0x140075c54  add     rsp, 60h
0x140075c58  pop     r15
0x140075c5a  pop     r14
0x140075c5c  pop     r13
0x140075c5e  pop     r12
0x140075c60  pop     rdi
0x140075c61  pop     rsi
0x140075c62  pop     rbp
0x140075c63  retn
0x140075c65  mov     edx, [rcx+2Ch]
0x140075c68  test    dl, 40h
0x140075c6b  jz      short loc_140075C17
0x140075c6d  mov     r9, [rdi+38h]
0x140075c71  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075c78  mov     rcx, [rcx+18h]
0x140075c7c  mov     edx, 50h ; 'P'
0x140075c81  mov     dword ptr [rsp+98h+var_78], ebp
0x140075c85  call    WPP_SF_ZD
0x140075c8a  jmp     short loc_140075C17
0x140075c8c  mov     ebp, r8d
0x140075c8f  mov     esi, 0C5Ah
0x140075c94  jmp     short loc_140075C1C
0x140075c96  mov     rcx, rdi
0x140075c99  call    CscAcquireLViewLock
0x140075c9e  mov     rax, [rdi+30h]
0x140075ca2  mov     r14d, [rax+4]
0x140075ca6  lea     rcx, [rax+38h]; FastMutex
0x140075caa  shr     r14d, 0Bh
0x140075cae  and     r14b, 1
0x140075cb2  mov     qword ptr [rax+70h], 0
0x140075cba  cmp     byte ptr [rax+78h], 0
0x140075cbe  jz      loc_140075D63
0x140075cc4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140075ccb  nop     dword ptr [rax+rax+00h]
0x140075cd0  mov     rcx, rdi
0x140075cd3  xor     esi, esi
0x140075cd5  call    CscAcquireLViewLock
0x140075cda  mov     rcx, [r13+28h]
0x140075cde  lea     rdx, [rsp+98h+arg_0]
0x140075ce6  call    CscStoreEntryIsTransparentlyCached
0x140075ceb  mov     ebp, eax
0x140075ced  mov     rcx, [rdi+30h]
0x140075cf1  mov     eax, [rcx+4]
0x140075cf4  cmp     [rsp+98h+arg_0], sil
0x140075cfc  jz      short loc_140075D5D
0x140075cfe  bts     eax, 0Dh
0x140075d02  mov     [rcx+4], eax
0x140075d05  mov     rax, [rdi+30h]
0x140075d09  lea     rcx, [rax+38h]; FastMutex
0x140075d0d  mov     [rax+70h], rsi
0x140075d11  cmp     [rax+78h], sil
0x140075d15  jz      short loc_140075D74
0x140075d17  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140075d1e  nop     dword ptr [rax+rax+00h]
0x140075d23  test    bl, 4
0x140075d26  jnz     loc_140075C1C
0x140075d2c  mov     rax, [rsp+98h+arg_20]
0x140075d34  mov     r9d, r12d
0x140075d37  mov     r8, [rsp+98h+arg_10]
0x140075d3f  mov     rcx, rdi
0x140075d42  mov     rdx, [rsp+98h+var_48]
0x140075d47  mov     byte ptr [rsp+98h+var_70], r14b
0x140075d4c  mov     [rsp+98h+var_78], rax
0x140075d51  call    CscLViewUpdateInfoWorker
0x140075d56  mov     ebp, eax
0x140075d58  jmp     loc_140075C1C
0x140075d5d  btr     eax, 0Dh
0x140075d61  jmp     short loc_140075D02
0x140075d63  call    cs:__imp_ExReleaseFastMutex
0x140075d6a  nop     dword ptr [rax+rax+00h]
0x140075d6f  jmp     loc_140075CD0
0x140075d74  call    cs:__imp_ExReleaseFastMutex
0x140075d7b  nop     dword ptr [rax+rax+00h]
0x140075d80  jmp     short loc_140075D23
0x140075d82  test    r14b, al
0x140075d85  jnz     loc_140075EE2
0x140075d8b  test    ecx, ecx
0x140075d8d  jnz     loc_140075E2B
0x140075d93  lea     rdx, WPP_GLOBAL_Control
0x140075d9a  mov     rcx, [rdi+30h]
0x140075d9e  xor     eax, eax
0x140075da0  lock cmpxchg [rcx+28h], rbp
0x140075da6  jz      loc_140075F04
0x140075dac  lea     rcx, [rsp+98h+var_50]
0x140075db1  call    CscStoreDereferenceEntry
0x140075db6  mov     rcx, cs:WPP_GLOBAL_Control
0x140075dbd  lea     rax, WPP_GLOBAL_Control
0x140075dc4  cmp     rcx, rax
0x140075dc7  jz      loc_140075CD0
0x140075dcd  mov     eax, [rcx+2Ch]
0x140075dd0  test    al, 40h
0x140075dd2  jz      loc_140075CD0
0x140075dd8  mov     rcx, [rcx+18h]
0x140075ddc  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075de3  mov     edx, 52h ; 'R'
0x140075de8  mov     [rsp+98h+var_70], 0
0x140075df1  mov     r9, rbp
0x140075df4  mov     [rsp+98h+var_78], r15
0x140075df9  call    WPP_SF_qqq
0x140075dfe  jmp     loc_140075CD0
0x140075e03  mov     eax, [rsp+98h+var_58]
0x140075e07  mov     ecx, eax
0x140075e09  and     ecx, 2
0x140075e0c  jz      short loc_140075E11
0x140075e0e  or      dword ptr [rsi], 2
0x140075e11  mov     rdx, [rsp+98h+String2]; String2
0x140075e19  test    rdx, rdx
0x140075e1c  jnz     loc_140075D82
0x140075e22  test    r14b, al
0x140075e25  jz      loc_140075D8B
0x140075e2b  or      dword ptr [rsi], 2
0x140075e2e  jmp     loc_140075D93
0x140075e33  mov     r9, [rdi+38h]
0x140075e37  mov     ecx, 4Eh ; 'N'
0x140075e3c  mov     r8d, ecx
0x140075e3f  mov     eax, 59h ; 'Y'
0x140075e44  test    rbp, rbp
0x140075e47  mov     edx, 4Fh ; 'O'
0x140075e4c  cmovnz  r8d, eax
0x140075e50  test    r14b, r14b
0x140075e53  cmovz   eax, ecx
0x140075e56  mov     rcx, [r10+18h]
0x140075e5a  mov     byte ptr [rsp+98h+var_68], al
0x140075e5e  mov     byte ptr [rsp+98h+var_70], r8b
0x140075e63  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075e6a  mov     dword ptr [rsp+98h+var_78], ebx
0x140075e6e  call    WPP_SF_ZDcc
0x140075e73  xor     r8d, r8d
0x140075e76  jmp     loc_140075B9B
0x140075e7b  mov     ebx, 0Ch
0x140075e80  jmp     loc_140075BC9
0x140075e85  mov     r14b, 1
0x140075e88  mov     rcx, cs:WPP_GLOBAL_Control
0x140075e8f  lea     rdx, WPP_GLOBAL_Control
0x140075e96  mov     rbp, [rsp+98h+var_50]
0x140075e9b  cmp     rcx, rdx
0x140075e9e  jz      short loc_140075ED4
0x140075ea0  mov     eax, [rcx+2Ch]
0x140075ea3  test    al, 40h
0x140075ea5  jz      short loc_140075ED4
0x140075ea7  mov     rcx, [rcx+18h]
0x140075eab  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075eb2  mov     edx, 51h ; 'Q'
0x140075eb7  mov     [rsp+98h+var_70], 0
0x140075ec0  mov     r9, rbp
0x140075ec3  mov     [rsp+98h+var_78], r15
0x140075ec8  call    WPP_SF_qqq
0x140075ecd  lea     rdx, WPP_GLOBAL_Control
0x140075ed4  test    rsi, rsi
0x140075ed7  jz      loc_140075D9A
0x140075edd  jmp     loc_140075E03
0x140075ee2  mov     rcx, [rdi+38h]; String1
0x140075ee6  movzx   r8d, r14b; CaseInSensitive
0x140075eea  call    cs:__imp_RtlEqualUnicodeString
0x140075ef1  nop     dword ptr [rax+rax+00h]
0x140075ef6  neg     al
0x140075ef8  sbb     ecx, ecx
0x140075efa  add     ecx, 2
0x140075efd  or      [rsi], ecx
0x140075eff  jmp     loc_140075D93
0x140075f04  mov     rcx, cs:WPP_GLOBAL_Control
0x140075f0b  cmp     rcx, rdx
0x140075f0e  jz      loc_140075CD0
0x140075f14  mov     eax, [rcx+2Ch]
0x140075f17  test    al, 40h
0x140075f19  jz      loc_140075CD0
0x140075f1f  mov     r9, [rdi+38h]
0x140075f23  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075f2a  mov     rcx, [rcx+18h]
0x140075f2e  mov     edx, 53h ; 'S'
0x140075f33  call    WPP_SF_Z
0x140075f38  jmp     loc_140075CD0
0x140075f3d  mov     rcx, [rcx+18h]
0x140075f41  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075f48  mov     edx, 54h ; 'T'
0x140075f4d  mov     dword ptr [rsp+98h+var_78], esi
0x140075f51  mov     r9d, ebp
0x140075f54  call    WPP_SF_Dd
0x140075f59  jmp     loc_140075C4A
```
