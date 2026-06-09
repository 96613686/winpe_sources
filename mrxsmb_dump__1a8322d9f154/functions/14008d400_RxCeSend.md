# RxCeSend

- ea: `0x14008d400`
- end: `0x14008da19`
- name: `RxCeSend`
- size: `1561`
- prototype: `NTSTATUS __stdcall(PRXCE_VC pVc, ULONG SendOptions, PMDL pMdl, ULONG SendLength, PVOID pCompletionContext)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14008d220`
- `0x14008d380`

## callees

- `0x14000e530`
- `0x14000f1a0`
- `0x14001a2a0`
- `0x14001a354`
- `0x140026a5c`
- `0x140036d90`
- `0x140038068`
- `0x14003838c`
- `0x140059dc0`
- `0x14008c298`
- `0x14008d400`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d77d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d7a9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d77d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d7a9`
- `ntoskrnl!KeBugCheckEx` at `0x14008d976`
- `ntoskrnl!KeBugCheckEx` at `0x14008d9e6`
- `ntoskrnl!KeBugCheckEx` at `0x14008d976`
- `ntoskrnl!KeBugCheckEx` at `0x14008d9e6`
- `ntoskrnl!IoGetActivityIdThread` at `0x14008d58b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14008d58b`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d52a`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d572`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d52a`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d572`

## pseudocode

```c
NTSTATUS __stdcall RxCeSend(PRXCE_VC pVc, ULONG SendOptions, PMDL pMdl, ULONG SendLength, PVOID pCompletionContext)
{
  __int64 v9; // rcx
  NTSTATUS v10; // edi
  ULONG Signature; // edx
  NTSTATUS v12; // eax
  _DWORD *v13; // rax
  ULONG v14; // r8d
  ULONG v15; // edx
  PMDL Next; // rcx
  unsigned int v17; // r10d
  char *MappedSystemVa; // r9
  char v19; // r11
  unsigned int v20; // ecx
  __int64 v21; // rdx
  ULONG v22; // edx
  ULONG v23; // edx
  __int64 v24; // r8
  int v25; // eax
  ULONG ByteCount; // ecx
  int Priority; // [rsp+28h] [rbp-100h]
  char *v29; // [rsp+30h] [rbp-F8h]
  unsigned int v30; // [rsp+38h] [rbp-F0h]
  char *v31; // [rsp+40h] [rbp-E8h]
  char v32; // [rsp+50h] [rbp-D8h]
  USHORT Type; // [rsp+52h] [rbp-D6h]
  ULONG v34; // [rsp+54h] [rbp-D4h]
  ULONG v35; // [rsp+58h] [rbp-D0h]
  unsigned int v36; // [rsp+5Ch] [rbp-CCh]
  _DWORD *v37; // [rsp+60h] [rbp-C8h]
  char *v38; // [rsp+60h] [rbp-C8h]
  char v39; // [rsp+74h] [rbp-B4h]
  unsigned int v40; // [rsp+78h] [rbp-B0h]
  __int128 *ActivityIdThread; // [rsp+80h] [rbp-A8h]
  unsigned int v42; // [rsp+88h] [rbp-A0h]
  PMDL v43; // [rsp+98h] [rbp-90h]
  __int128 v44; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v45[40]; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v46; // [rsp+158h] [rbp+30h]
  __int64 v47; // [rsp+160h] [rbp+38h]

  v9 = v46;
  v10 = -1073741300;
  if ( !HIDWORD(pVc->pConnection) )
  {
    v43 = pMdl;
    Type = pVc[5].Type;
    v44 = 0;
    if ( (byte_1400712A4 & 0x20) != 0 )
    {
      if ( EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x100000000uLL) )
      {
        v13 = (pMdl->MdlFlags & 5) != 0
            ? pMdl->MappedSystemVa
            : MmMapLockedPagesSpecifyCache(pMdl, 0, MmCached, 0, 0, 0x40000000u);
        v37 = v13;
        if ( v13 )
        {
          v32 = 1;
          if ( EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x800000000000uLL) )
          {
            v35 = SendLength;
          }
          else
          {
            ByteCount = pMdl->ByteCount;
            if ( ByteCount >= 0x40 && *v37 == 1112364030 )
              ByteCount = v37[5] + 576;
            if ( ByteCount > SendLength )
              ByteCount = SendLength;
            v35 = ByteCount;
          }
          ActivityIdThread = (__int128 *)IoGetActivityIdThread();
          if ( !ActivityIdThread )
          {
            v44 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
            ActivityIdThread = &v44;
          }
          v14 = v35;
          v15 = v35;
          v34 = v35;
          Next = pMdl;
          while ( v15 && Next )
          {
            v17 = Next->ByteCount;
            if ( v17 > v15 )
              v17 = v15;
            v40 = v17;
            if ( (Next->MdlFlags & 5) != 0 )
            {
              MappedSystemVa = (char *)Next->MappedSystemVa;
              v38 = MappedSystemVa;
            }
            else
            {
              MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u);
              v38 = MappedSystemVa;
              v15 = v34;
              v14 = v35;
              v17 = v40;
            }
            if ( !MappedSystemVa )
              break;
            if ( v15 == v17 )
            {
              v39 = 1;
              v19 = 1;
            }
            else
            {
              v39 = 0;
              v19 = 0;
            }
            v20 = v17;
            v36 = v17;
            v21 = 0;
            if ( v32 )
            {
              if ( !v19 || v17 >= 0xF000 )
              {
                memset(v45, 0, sizeof(v45));
                *(_OWORD *)&v45[8] = *(_OWORD *)((char *)&pVc[6].ConnectionId + 4);
                *(_OWORD *)&v45[20] = *(_OWORD *)&pVc[6].pCleanUpEvent;
                *(_DWORD *)v45 = Type;
                *(_DWORD *)&v45[36] = v14;
                *(_DWORD *)&v45[4] = 28;
                v21 = (unsigned int)Template_qqbjqb_ex(
                                      REMOTEFS_SMB_Context,
                                      0,
                                      0x140000000uLL,
                                      ActivityIdThread,
                                      40,
                                      v45);
                v20 = v36;
                MappedSystemVa = v38;
                goto LABEL_46;
              }
              v31 = MappedSystemVa;
              v30 = v17;
              v29 = (char *)&pVc[6].ConnectionId + 4;
              LODWORD(v21) = Template_qqbqb_ex(REMOTEFS_SMB_Context, 0, 0x100000000LL, ActivityIdThread, Type);
            }
            else
            {
LABEL_46:
              while ( v20 )
              {
                if ( (int)v21 < 0 )
                  goto LABEL_21;
                v24 = 0x100000000LL;
                v25 = 61440;
                if ( v20 < 0xF000 )
                  v25 = v20;
                v42 = v25;
                if ( v39 && v20 == v25 )
                  v24 = 0x180000000LL;
                LODWORD(v21) = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v21, v24, ActivityIdThread, v25, MappedSystemVa);
                v20 = v36 - v42;
                v36 -= v42;
                MappedSystemVa = &v38[v42];
                v38 = MappedSystemVa;
              }
            }
            if ( (int)v21 < 0 )
              break;
            v32 = 0;
            v15 = v34 - v40;
            v34 -= v40;
            Next = v43->Next;
            v43 = v43->Next;
            v14 = v35;
          }
        }
      }
LABEL_21:
      v9 = v46;
    }
    Signature = pVc[5].Signature;
    if ( Signature == 1 )
    {
      v12 = SmbWskSend((_DWORD)pVc, SendOptions, (_DWORD)pMdl, SendLength, (__int64)pCompletionContext, v9, v47);
    }
    else if ( Signature )
    {
      v22 = Signature - 2;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          if ( v23 != 1 )
            goto LABEL_6;
          v12 = SmbQuicSend(
                  (_DWORD)pVc,
                  SendOptions,
                  (_DWORD)pMdl,
                  SendLength,
                  (__int64)pCompletionContext,
                  Priority,
                  v47);
        }
        else
        {
          if ( pCompletionContext )
            KeBugCheckEx(0x27u, 0x747858D7u, (ULONG_PTR)pVc, (ULONG_PTR)pCompletionContext, 0);
          v12 = RxVmbusSend((_DWORD)pVc, SendOptions, (_DWORD)pMdl, SendLength, v9, v47);
        }
      }
      else
      {
        v12 = RxSmbdSend((_DWORD)pVc, SendOptions, (_DWORD)pMdl, SendLength, (__int64)pCompletionContext, v9, v47);
      }
    }
    else
    {
      if ( pCompletionContext || v9 )
        KeBugCheckEx(0x27u, 0x747858D3u, (ULONG_PTR)pVc, (ULONG_PTR)pCompletionContext, 0);
      v12 = RxTdiSend(*(_QWORD *)&pVc->State, pVc, SendOptions, pMdl, SendLength, v47, v29, v30, v31);
    }
    v10 = v12;
  }
LABEL_6:
  if ( v10 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f9bc139b4bae35331116152bd0c855e2_Traceguids, (unsigned int)v10);
  }
  return v10;
}

```

## disassembly

```asm
0x14008d400  push    rbx
0x14008d402  push    rsi
0x14008d403  push    rdi
0x14008d404  push    r12
0x14008d406  push    r13
0x14008d408  push    r14
0x14008d40a  push    r15
0x14008d40c  sub     rsp, 0F0h
0x14008d413  mov     rax, cs:__security_cookie
0x14008d41a  xor     rax, rsp
0x14008d41d  mov     [rsp+128h+var_40], rax
0x14008d425  mov     r14d, r9d
0x14008d428  mov     rsi, r8
0x14008d42b  mov     r12d, edx
0x14008d42e  mov     rbx, rcx
0x14008d431  mov     [rsp+128h+var_80], rcx
0x14008d439  mov     r15, [rsp+128h+pCompletionContext]
0x14008d441  mov     rcx, [rsp+128h+arg_28]
0x14008d449  mov     [rsp+128h+var_C0], rcx
0x14008d44e  mov     r13, [rsp+128h+arg_30]
0x14008d456  mov     edi, 0C000020Ch
0x14008d45b  cmp     dword ptr [rbx+0Ch], 0
0x14008d45f  jnz     short loc_14008D4C6
0x14008d461  mov     [rsp+128h+var_90], r8
0x14008d469  movzx   eax, word ptr [rbx+140h]
0x14008d470  mov     [rsp+128h+var_D6], ax
0x14008d475  mov     [rsp+128h+var_D4], 0
0x14008d47d  xorps   xmm0, xmm0
0x14008d480  movups  [rsp+128h+var_78], xmm0
0x14008d488  test    cs:byte_1400712A4, 20h
0x14008d48f  jnz     loc_14008D517
0x14008d495  mov     edx, [rbx+140h]
0x14008d49b  cmp     edx, 1
0x14008d49e  jnz     loc_14008D6FB
0x14008d4a4  mov     [rsp+128h+var_F8], r13
0x14008d4a9  mov     qword ptr [rsp+128h+Priority], rcx
0x14008d4ae  mov     qword ptr [rsp+128h+BugCheckOnFailure], r15
0x14008d4b3  mov     r9d, r14d
0x14008d4b6  mov     r8, rsi
0x14008d4b9  mov     edx, r12d
0x14008d4bc  mov     rcx, rbx
0x14008d4bf  call    SmbWskSend
0x14008d4c4  mov     edi, eax
0x14008d4c6  test    edi, edi
0x14008d4c8  jns     loc_14008D9F3
0x14008d4ce  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14008d4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d4dc  cmp     rcx, rax
0x14008d4df  jz      loc_14008D9F3
0x14008d4e5  mov     eax, [rcx+2Ch]
0x14008d4e8  test    al, 4
0x14008d4ea  jz      loc_14008D9F3
0x14008d4f0  cmp     byte ptr [rcx+29h], 4
0x14008d4f4  jb      loc_14008D9F3
0x14008d4fa  mov     edx, 0Ah
0x14008d4ff  mov     r9d, edi
0x14008d502  lea     r8, WPP_f9bc139b4bae35331116152bd0c855e2_Traceguids
0x14008d509  mov     rcx, [rcx+18h]
0x14008d50d  call    WPP_SF_d
0x14008d512  jmp     loc_14008D9F3
0x14008d517  xor     edx, edx; Level
0x14008d519  mov     r8, 100000000h; Keyword
0x14008d523  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x14008d52a  call    cs:__imp_EtwProviderEnabled
0x14008d531  nop     dword ptr [rax+rax+00h]
0x14008d536  test    al, al
0x14008d538  jz      loc_14008D5EB
0x14008d53e  test    byte ptr [rsi+0Ah], 5
0x14008d542  jz      loc_14008D75F
0x14008d548  mov     rax, [rsi+18h]
0x14008d54c  mov     [rsp+128h+var_C8], rax
0x14008d551  test    rax, rax
0x14008d554  jz      loc_14008D5EB
0x14008d55a  mov     [rsp+128h+var_D8], 1
0x14008d55f  xor     edx, edx; Level
0x14008d561  mov     r8, 800000000000h; Keyword
0x14008d56b  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x14008d572  call    cs:__imp_EtwProviderEnabled
0x14008d579  nop     dword ptr [rax+rax+00h]
0x14008d57e  test    al, al
0x14008d580  jz      loc_14008D91E
0x14008d586  mov     [rsp+128h+var_D0], r14d
0x14008d58b  call    cs:__imp_IoGetActivityIdThread
0x14008d592  nop     dword ptr [rax+rax+00h]
0x14008d597  mov     [rsp+128h+var_A8], rax
0x14008d59f  test    rax, rax
0x14008d5a2  jnz     short loc_14008D5D8
0x14008d5a4  xorps   xmm0, xmm0
0x14008d5a7  movups  [rsp+128h+var_78], xmm0
0x14008d5af  mov     eax, 1
0x14008d5b4  lock xadd cs:Correlation, rax
0x14008d5bd  inc     rax
0x14008d5c0  mov     qword ptr [rsp+128h+var_78], rax
0x14008d5c8  lea     rax, [rsp+128h+var_78]
0x14008d5d0  mov     [rsp+128h+var_A8], rax
0x14008d5d8  mov     r8d, [rsp+128h+var_D0]
0x14008d5dd  mov     edx, r8d
0x14008d5e0  mov     [rsp+128h+var_D4], edx
0x14008d5e4  mov     rcx, rsi; MemoryDescriptorList
0x14008d5e7  test    edx, edx
0x14008d5e9  jnz     short loc_14008D5F5
0x14008d5eb  mov     rcx, [rsp+128h+var_C0]
0x14008d5f0  jmp     loc_14008D495
0x14008d5f5  test    rcx, rcx
0x14008d5f8  jz      short loc_14008D5EB
0x14008d5fa  mov     r10d, [rcx+28h]
0x14008d5fe  cmp     r10d, edx
0x14008d601  cmova   r10d, edx
0x14008d605  mov     [rsp+128h+var_B0], r10d
0x14008d60a  test    byte ptr [rcx+0Ah], 5
0x14008d60e  jz      loc_14008D78E
0x14008d614  mov     r9, [rcx+18h]
0x14008d618  mov     [rsp+128h+var_C8], r9
0x14008d61d  test    r9, r9
0x14008d620  jz      short loc_14008D5EB
0x14008d622  cmp     edx, r10d
0x14008d625  jnz     loc_14008D6EB
0x14008d62b  mov     [rsp+128h+var_B4], 1
0x14008d633  mov     r11b, 1
0x14008d636  mov     [rsp+128h+var_98], 0
0x14008d642  mov     ecx, r10d
0x14008d645  mov     [rsp+128h+var_CC], ecx
0x14008d649  xor     edx, edx
0x14008d64b  mov     [rsp+128h+var_88], r9
0x14008d653  movzx   eax, [rsp+128h+var_D8]
0x14008d658  test    al, al
0x14008d65a  jz      loc_14008D870
0x14008d660  test    r11b, r11b
0x14008d663  jz      loc_14008D7D0
0x14008d669  cmp     r10d, 0F000h
0x14008d670  jnb     loc_14008D7D0
0x14008d676  movzx   eax, [rsp+128h+var_D6]
0x14008d67b  mov     [rsp+128h+var_E8], r9
0x14008d680  mov     [rsp+128h+var_F0], r10d
0x14008d685  lea     rcx, [rbx+1ACh]
0x14008d68c  mov     [rsp+128h+var_F8], rcx
0x14008d691  mov     [rsp+128h+BugCheckOnFailure], eax
0x14008d695  mov     r9, [rsp+128h+var_A8]
0x14008d69d  mov     r8, 100000000h
0x14008d6a7  mov     rcx, cs:REMOTEFS_SMB_Context
0x14008d6ae  call    Template_qqbqb_ex
0x14008d6b3  mov     edx, eax
0x14008d6b5  test    edx, edx
0x14008d6b7  js      loc_14008D5EB
0x14008d6bd  mov     [rsp+128h+var_D8], 0
0x14008d6c2  mov     edx, [rsp+128h+var_D4]
0x14008d6c6  sub     edx, [rsp+128h+var_B0]
0x14008d6ca  mov     [rsp+128h+var_D4], edx
0x14008d6ce  mov     rcx, [rsp+128h+var_90]
0x14008d6d6  mov     rcx, [rcx]
0x14008d6d9  mov     [rsp+128h+var_90], rcx
0x14008d6e1  mov     r8d, [rsp+128h+var_D0]
0x14008d6e6  jmp     loc_14008D5E7
0x14008d6eb  mov     [rsp+128h+var_B4], 0
0x14008d6f3  xor     r11b, r11b
0x14008d6f6  jmp     loc_14008D636
0x14008d6fb  test    edx, edx
0x14008d6fd  jz      loc_14008D9A2
0x14008d703  sub     edx, 2
0x14008d706  jnz     short loc_14008D72D
0x14008d708  mov     [rsp+128h+var_F8], r13
0x14008d70d  mov     qword ptr [rsp+128h+Priority], rcx
0x14008d712  mov     qword ptr [rsp+128h+BugCheckOnFailure], r15
0x14008d717  mov     r9d, r14d
0x14008d71a  mov     r8, rsi
0x14008d71d  mov     edx, r12d
0x14008d720  mov     rcx, rbx
0x14008d723  call    RxSmbdSend
0x14008d728  jmp     loc_14008D4C4
0x14008d72d  sub     edx, 1
0x14008d730  jz      loc_14008D958
0x14008d736  cmp     edx, 1
0x14008d739  jnz     loc_14008D4C6
0x14008d73f  mov     [rsp+128h+var_F8], r13
0x14008d744  mov     qword ptr [rsp+128h+BugCheckOnFailure], r15
0x14008d749  mov     r9d, r14d
0x14008d74c  mov     r8, rsi
0x14008d74f  mov     edx, r12d
0x14008d752  mov     rcx, rbx
0x14008d755  call    SmbQuicSend
0x14008d75a  jmp     loc_14008D4C4
0x14008d75f  mov     [rsp+128h+Priority], 40000000h; Priority
0x14008d767  mov     [rsp+128h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14008d76f  xor     r9d, r9d; RequestedAddress
0x14008d772  xor     edx, edx; AccessMode
0x14008d774  mov     r8d, 1; CacheType
0x14008d77a  mov     rcx, rsi; MemoryDescriptorList
0x14008d77d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008d784  nop     dword ptr [rax+rax+00h]
0x14008d789  jmp     loc_14008D54C
0x14008d78e  mov     [rsp+128h+Priority], 40000000h; Priority
0x14008d796  mov     [rsp+128h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14008d79e  xor     r9d, r9d; RequestedAddress
0x14008d7a1  xor     edx, edx; AccessMode
0x14008d7a3  mov     r8d, 1; CacheType
0x14008d7a9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008d7b0  nop     dword ptr [rax+rax+00h]
0x14008d7b5  mov     r9, rax
0x14008d7b8  mov     [rsp+128h+var_C8], rax
0x14008d7bd  mov     edx, [rsp+128h+var_D4]
0x14008d7c1  mov     r8d, [rsp+128h+var_D0]
0x14008d7c6  mov     r10d, [rsp+128h+var_B0]
0x14008d7cb  jmp     loc_14008D61D
0x14008d7d0  test    al, al
0x14008d7d2  jz      loc_14008D870
0x14008d7d8  xorps   xmm0, xmm0
0x14008d7db  xor     eax, eax
0x14008d7dd  movups  [rsp+128h+var_68], xmm0
0x14008d7e5  movups  [rsp+128h+var_58], xmm0
0x14008d7ed  mov     [rsp+128h+var_48], rax
0x14008d7f5  movups  xmm0, xmmword ptr [rbx+1ACh]
0x14008d7fc  movups  [rsp+128h+var_68+8], xmm0
0x14008d804  movups  xmm1, xmmword ptr [rbx+1B8h]
0x14008d80b  movups  [rsp+128h+var_58+4], xmm1
0x14008d813  movzx   eax, [rsp+128h+var_D6]
0x14008d818  mov     dword ptr [rsp+128h+var_68], eax
0x14008d81f  mov     dword ptr [rsp+128h+var_48+4], r8d
0x14008d827  mov     dword ptr [rsp+128h+var_68+4], 1Ch
0x14008d832  lea     rax, [rsp+128h+var_68]
0x14008d83a  mov     qword ptr [rsp+128h+Priority], rax
0x14008d83f  mov     [rsp+128h+BugCheckOnFailure], 28h ; '('
0x14008d847  mov     r9, [rsp+128h+var_A8]
0x14008d84f  mov     r8, 140000000h
0x14008d859  mov     rcx, cs:REMOTEFS_SMB_Context
0x14008d860  call    Template_qqbjqb_ex
0x14008d865  mov     edx, eax
0x14008d867  mov     ecx, [rsp+128h+var_CC]
0x14008d86b  mov     r9, [rsp+128h+var_C8]
0x14008d870  test    ecx, ecx
0x14008d872  jz      loc_14008D6B5
0x14008d878  test    edx, edx
0x14008d87a  js      loc_14008D5EB
0x14008d880  mov     rax, 100000000h
0x14008d88a  mov     r8, rax
0x14008d88d  mov     [rsp+128h+var_98], rax
0x14008d895  mov     eax, 0F000h
0x14008d89a  cmp     ecx, eax
0x14008d89c  cmovb   eax, ecx
0x14008d89f  mov     [rsp+128h+var_A0], eax
0x14008d8a6  cmp     byte ptr [rsp+128h+var_B4], 0
0x14008d8ab  jnz     short loc_14008D903
0x14008d8ad  mov     qword ptr [rsp+128h+Priority], r9
0x14008d8b2  mov     [rsp+128h+BugCheckOnFailure], eax
0x14008d8b6  mov     r9, [rsp+128h+var_A8]
0x14008d8be  mov     rcx, cs:REMOTEFS_SMB_Context
0x14008d8c5  call    Template_qqbjqb_ex
0x14008d8ca  mov     edx, eax
0x14008d8cc  mov     ecx, [rsp+128h+var_CC]
0x14008d8d0  mov     eax, [rsp+128h+var_A0]
0x14008d8d7  sub     ecx, eax
0x14008d8d9  mov     [rsp+128h+var_CC], ecx
0x14008d8dd  mov     r9, [rsp+128h+var_C8]
0x14008d8e2  add     r9, rax
0x14008d8e5  mov     [rsp+128h+var_C8], r9
0x14008d8ea  mov     [rsp+128h+var_88], r9
0x14008d8f2  mov     [rsp+128h+var_98], 0
0x14008d8fe  jmp     loc_14008D870
0x14008d903  cmp     ecx, eax
0x14008d905  jnz     short loc_14008D8AD
0x14008d907  mov     rcx, 180000000h
0x14008d911  mov     r8, rcx
0x14008d914  mov     [rsp+128h+var_98], rcx
0x14008d91c  jmp     short loc_14008D8AD
0x14008d91e  mov     ecx, [rsi+28h]
0x14008d921  mov     [rsp+128h+var_B8], ecx
0x14008d925  cmp     ecx, 40h ; '@'
0x14008d928  jb      short loc_14008D944
0x14008d92a  mov     rax, [rsp+128h+var_C8]
0x14008d92f  cmp     dword ptr [rax], 424D53FEh
0x14008d935  jnz     short loc_14008D944
0x14008d937  mov     ecx, [rax+14h]
0x14008d93a  add     ecx, 240h
0x14008d940  mov     [rsp+128h+var_B8], ecx
0x14008d944  cmp     ecx, r14d
0x14008d947  cmova   ecx, r14d
0x14008d94b  mov     [rsp+128h+var_D0], ecx
0x14008d94f  mov     [rsp+128h+var_B8], ecx
0x14008d953  jmp     loc_14008D58B
0x14008d958  test    r15, r15
0x14008d95b  jz      short loc_14008D982
0x14008d95d  mov     qword ptr [rsp+128h+BugCheckOnFailure], 0; BugCheckParameter4
0x14008d966  mov     r9, r15; BugCheckParameter3
0x14008d969  mov     r8, rbx; BugCheckParameter2
0x14008d96c  mov     edx, 747858D7h; BugCheckParameter1
0x14008d971  mov     ecx, 27h ; '''; BugCheckCode
0x14008d976  call    cs:__imp_KeBugCheckEx
0x14008d982  mov     qword ptr [rsp+128h+Priority], r13
0x14008d987  mov     qword ptr [rsp+128h+BugCheckOnFailure], rcx
0x14008d98c  mov     r9d, r14d
0x14008d98f  mov     r8, rsi
0x14008d992  mov     edx, r12d
0x14008d995  mov     rcx, rbx
0x14008d998  call    RxVmbusSend
0x14008d99d  jmp     loc_14008D4C4
0x14008d9a2  test    r15, r15
0x14008d9a5  jnz     short loc_14008D9CD
0x14008d9a7  test    rcx, rcx
0x14008d9aa  jnz     short loc_14008D9CD
0x14008d9ac  mov     qword ptr [rsp+128h+Priority], r13
0x14008d9b1  mov     [rsp+128h+BugCheckOnFailure], r14d
  ... truncated ...
```
