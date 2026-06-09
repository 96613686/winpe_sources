# RxCeSend

- ea: `0x14008d450`
- end: `0x14008da69`
- name: `RxCeSend`
- size: `1561`
- prototype: `NTSTATUS __stdcall(PRXCE_VC pVc, ULONG SendOptions, PMDL pMdl, ULONG SendLength, PVOID pCompletionContext)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14008d270`
- `0x14008d3d0`

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
- `0x14008c2e8`
- `0x14008d450`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d7cd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d7f9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d7cd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008d7f9`
- `ntoskrnl!KeBugCheckEx` at `0x14008d9c6`
- `ntoskrnl!KeBugCheckEx` at `0x14008da36`
- `ntoskrnl!KeBugCheckEx` at `0x14008d9c6`
- `ntoskrnl!KeBugCheckEx` at `0x14008da36`
- `ntoskrnl!IoGetActivityIdThread` at `0x14008d5db`
- `ntoskrnl!IoGetActivityIdThread` at `0x14008d5db`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d57a`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d5c2`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d57a`
- `ntoskrnl!EtwProviderEnabled` at `0x14008d5c2`

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
  _BYTE *Priority; // [rsp+28h] [rbp-100h]
  char v29; // [rsp+50h] [rbp-D8h]
  USHORT Type; // [rsp+52h] [rbp-D6h]
  ULONG v31; // [rsp+54h] [rbp-D4h]
  ULONG v32; // [rsp+58h] [rbp-D0h]
  unsigned int v33; // [rsp+5Ch] [rbp-CCh]
  _DWORD *v34; // [rsp+60h] [rbp-C8h]
  char *v35; // [rsp+60h] [rbp-C8h]
  char v36; // [rsp+74h] [rbp-B4h]
  unsigned int v37; // [rsp+78h] [rbp-B0h]
  __int128 *ActivityIdThread; // [rsp+80h] [rbp-A8h]
  unsigned int v39; // [rsp+88h] [rbp-A0h]
  PMDL v40; // [rsp+98h] [rbp-90h]
  __int128 v41; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v42[40]; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v43; // [rsp+158h] [rbp+30h]
  __int64 v44; // [rsp+160h] [rbp+38h]

  v9 = v43;
  v10 = -1073741300;
  if ( !HIDWORD(pVc->pConnection) )
  {
    v40 = pMdl;
    Type = pVc[5].Type;
    v41 = 0;
    if ( (byte_1400712C4 & 0x20) != 0 )
    {
      if ( EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x100000000uLL) )
      {
        v13 = (pMdl->MdlFlags & 5) != 0
            ? pMdl->MappedSystemVa
            : MmMapLockedPagesSpecifyCache(pMdl, 0, MmCached, 0, 0, 0x40000000u);
        v34 = v13;
        if ( v13 )
        {
          v29 = 1;
          if ( EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x800000000000uLL) )
          {
            v32 = SendLength;
          }
          else
          {
            ByteCount = pMdl->ByteCount;
            if ( ByteCount >= 0x40 && *v34 == 1112364030 )
              ByteCount = v34[5] + 576;
            if ( ByteCount > SendLength )
              ByteCount = SendLength;
            v32 = ByteCount;
          }
          ActivityIdThread = (__int128 *)IoGetActivityIdThread();
          if ( !ActivityIdThread )
          {
            v41 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
            ActivityIdThread = &v41;
          }
          v14 = v32;
          v15 = v32;
          v31 = v32;
          Next = pMdl;
          while ( v15 && Next )
          {
            v17 = Next->ByteCount;
            if ( v17 > v15 )
              v17 = v15;
            v37 = v17;
            if ( (Next->MdlFlags & 5) != 0 )
            {
              MappedSystemVa = (char *)Next->MappedSystemVa;
              v35 = MappedSystemVa;
            }
            else
            {
              MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u);
              v35 = MappedSystemVa;
              v15 = v31;
              v14 = v32;
              v17 = v37;
            }
            if ( !MappedSystemVa )
              break;
            if ( v15 == v17 )
            {
              v36 = 1;
              v19 = 1;
            }
            else
            {
              v36 = 0;
              v19 = 0;
            }
            v20 = v17;
            v33 = v17;
            v21 = 0;
            if ( v29 )
            {
              if ( !v19 || v17 >= 0xF000 )
              {
                memset(v42, 0, sizeof(v42));
                *(_OWORD *)&v42[8] = *(_OWORD *)((char *)&pVc[6].ConnectionId + 4);
                *(_OWORD *)&v42[20] = *(_OWORD *)&pVc[6].pCleanUpEvent;
                *(_DWORD *)v42 = Type;
                *(_DWORD *)&v42[36] = v14;
                *(_DWORD *)&v42[4] = 28;
                Priority = v42;
                v21 = (unsigned int)Template_qqbjqb_ex(REMOTEFS_SMB_Context, 0, 0x140000000uLL, ActivityIdThread, 40);
                v20 = v33;
                LODWORD(MappedSystemVa) = (_DWORD)v35;
                goto LABEL_46;
              }
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
                v39 = v25;
                if ( v36 && v20 == v25 )
                  v24 = 0x180000000LL;
                LODWORD(Priority) = (_DWORD)MappedSystemVa;
                LODWORD(v21) = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v21, v24, ActivityIdThread, v25);
                v20 = v33 - v39;
                v33 -= v39;
                LODWORD(MappedSystemVa) = v39 + (_DWORD)v35;
                v35 += v39;
              }
            }
            if ( (int)v21 < 0 )
              break;
            v29 = 0;
            v15 = v31 - v37;
            v31 -= v37;
            Next = v40->Next;
            v40 = v40->Next;
            v14 = v32;
          }
        }
      }
LABEL_21:
      v9 = v43;
    }
    Signature = pVc[5].Signature;
    if ( Signature == 1 )
    {
      v12 = SmbWskSend((_DWORD)pVc, SendOptions, (_DWORD)pMdl, SendLength, (__int64)pCompletionContext, v9, v44);
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
                  (_DWORD)Priority,
                  v44);
        }
        else
        {
          if ( pCompletionContext )
            KeBugCheckEx(0x27u, 0x747858D7u, (ULONG_PTR)pVc, (ULONG_PTR)pCompletionContext, 0);
          v12 = RxVmbusSend((_DWORD)pVc, SendOptions, (_DWORD)pMdl, SendLength, v9, v44);
        }
      }
      else
      {
        v12 = RxSmbdSend((_DWORD)pVc, SendOptions, (_DWORD)pMdl, SendLength, (__int64)pCompletionContext, v9, v44);
      }
    }
    else
    {
      if ( pCompletionContext || v9 )
        KeBugCheckEx(0x27u, 0x747858D3u, (ULONG_PTR)pVc, (ULONG_PTR)pCompletionContext, 0);
      v12 = RxTdiSend(*(_QWORD *)&pVc->State, pVc, SendOptions, pMdl, SendLength, v44);
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
0x14008d450  push    rbx
0x14008d452  push    rsi
0x14008d453  push    rdi
0x14008d454  push    r12
0x14008d456  push    r13
0x14008d458  push    r14
0x14008d45a  push    r15
0x14008d45c  sub     rsp, 0F0h
0x14008d463  mov     rax, cs:__security_cookie
0x14008d46a  xor     rax, rsp
0x14008d46d  mov     [rsp+128h+var_40], rax
0x14008d475  mov     r14d, r9d
0x14008d478  mov     rsi, r8
0x14008d47b  mov     r12d, edx
0x14008d47e  mov     rbx, rcx
0x14008d481  mov     [rsp+128h+var_80], rcx
0x14008d489  mov     r15, [rsp+128h+pCompletionContext]
0x14008d491  mov     rcx, [rsp+128h+arg_28]
0x14008d499  mov     [rsp+128h+var_C0], rcx
0x14008d49e  mov     r13, [rsp+128h+arg_30]
0x14008d4a6  mov     edi, 0C000020Ch
0x14008d4ab  cmp     dword ptr [rbx+0Ch], 0
0x14008d4af  jnz     short loc_14008D516
0x14008d4b1  mov     [rsp+128h+var_90], r8
0x14008d4b9  movzx   eax, word ptr [rbx+140h]
0x14008d4c0  mov     [rsp+128h+var_D6], ax
0x14008d4c5  mov     [rsp+128h+var_D4], 0
0x14008d4cd  xorps   xmm0, xmm0
0x14008d4d0  movups  [rsp+128h+var_78], xmm0
0x14008d4d8  test    cs:byte_1400712C4, 20h
0x14008d4df  jnz     loc_14008D567
0x14008d4e5  mov     edx, [rbx+140h]
0x14008d4eb  cmp     edx, 1
0x14008d4ee  jnz     loc_14008D74B
0x14008d4f4  mov     [rsp+128h+var_F8], r13
0x14008d4f9  mov     qword ptr [rsp+128h+Priority], rcx
0x14008d4fe  mov     qword ptr [rsp+128h+BugCheckOnFailure], r15
0x14008d503  mov     r9d, r14d
0x14008d506  mov     r8, rsi
0x14008d509  mov     edx, r12d
0x14008d50c  mov     rcx, rbx
0x14008d50f  call    SmbWskSend
0x14008d514  mov     edi, eax
0x14008d516  test    edi, edi
0x14008d518  jns     loc_14008DA43
0x14008d51e  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14008d525  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d52c  cmp     rcx, rax
0x14008d52f  jz      loc_14008DA43
0x14008d535  mov     eax, [rcx+2Ch]
0x14008d538  test    al, 4
0x14008d53a  jz      loc_14008DA43
0x14008d540  cmp     byte ptr [rcx+29h], 4
0x14008d544  jb      loc_14008DA43
0x14008d54a  mov     edx, 0Ah
0x14008d54f  mov     r9d, edi
0x14008d552  lea     r8, WPP_f9bc139b4bae35331116152bd0c855e2_Traceguids
0x14008d559  mov     rcx, [rcx+18h]
0x14008d55d  call    WPP_SF_d
0x14008d562  jmp     loc_14008DA43
0x14008d567  xor     edx, edx; Level
0x14008d569  mov     r8, 100000000h; Keyword
0x14008d573  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x14008d57a  call    cs:__imp_EtwProviderEnabled
0x14008d581  nop     dword ptr [rax+rax+00h]
0x14008d586  test    al, al
0x14008d588  jz      loc_14008D63B
0x14008d58e  test    byte ptr [rsi+0Ah], 5
0x14008d592  jz      loc_14008D7AF
0x14008d598  mov     rax, [rsi+18h]
0x14008d59c  mov     [rsp+128h+var_C8], rax
0x14008d5a1  test    rax, rax
0x14008d5a4  jz      loc_14008D63B
0x14008d5aa  mov     [rsp+128h+var_D8], 1
0x14008d5af  xor     edx, edx; Level
0x14008d5b1  mov     r8, 800000000000h; Keyword
0x14008d5bb  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x14008d5c2  call    cs:__imp_EtwProviderEnabled
0x14008d5c9  nop     dword ptr [rax+rax+00h]
0x14008d5ce  test    al, al
0x14008d5d0  jz      loc_14008D96E
0x14008d5d6  mov     [rsp+128h+var_D0], r14d
0x14008d5db  call    cs:__imp_IoGetActivityIdThread
0x14008d5e2  nop     dword ptr [rax+rax+00h]
0x14008d5e7  mov     [rsp+128h+var_A8], rax
0x14008d5ef  test    rax, rax
0x14008d5f2  jnz     short loc_14008D628
0x14008d5f4  xorps   xmm0, xmm0
0x14008d5f7  movups  [rsp+128h+var_78], xmm0
0x14008d5ff  mov     eax, 1
0x14008d604  lock xadd cs:Correlation, rax
0x14008d60d  inc     rax
0x14008d610  mov     qword ptr [rsp+128h+var_78], rax
0x14008d618  lea     rax, [rsp+128h+var_78]
0x14008d620  mov     [rsp+128h+var_A8], rax
0x14008d628  mov     r8d, [rsp+128h+var_D0]
0x14008d62d  mov     edx, r8d
0x14008d630  mov     [rsp+128h+var_D4], edx
0x14008d634  mov     rcx, rsi; MemoryDescriptorList
0x14008d637  test    edx, edx
0x14008d639  jnz     short loc_14008D645
0x14008d63b  mov     rcx, [rsp+128h+var_C0]
0x14008d640  jmp     loc_14008D4E5
0x14008d645  test    rcx, rcx
0x14008d648  jz      short loc_14008D63B
0x14008d64a  mov     r10d, [rcx+28h]
0x14008d64e  cmp     r10d, edx
0x14008d651  cmova   r10d, edx
0x14008d655  mov     [rsp+128h+var_B0], r10d
0x14008d65a  test    byte ptr [rcx+0Ah], 5
0x14008d65e  jz      loc_14008D7DE
0x14008d664  mov     r9, [rcx+18h]
0x14008d668  mov     [rsp+128h+var_C8], r9
0x14008d66d  test    r9, r9
0x14008d670  jz      short loc_14008D63B
0x14008d672  cmp     edx, r10d
0x14008d675  jnz     loc_14008D73B
0x14008d67b  mov     [rsp+128h+var_B4], 1
0x14008d683  mov     r11b, 1
0x14008d686  mov     [rsp+128h+var_98], 0
0x14008d692  mov     ecx, r10d
0x14008d695  mov     [rsp+128h+var_CC], ecx
0x14008d699  xor     edx, edx
0x14008d69b  mov     [rsp+128h+var_88], r9
0x14008d6a3  movzx   eax, [rsp+128h+var_D8]
0x14008d6a8  test    al, al
0x14008d6aa  jz      loc_14008D8C0
0x14008d6b0  test    r11b, r11b
0x14008d6b3  jz      loc_14008D820
0x14008d6b9  cmp     r10d, 0F000h
0x14008d6c0  jnb     loc_14008D820
0x14008d6c6  movzx   eax, [rsp+128h+var_D6]
0x14008d6cb  mov     [rsp+128h+var_E8], r9
0x14008d6d0  mov     [rsp+128h+var_F0], r10d
0x14008d6d5  lea     rcx, [rbx+1ACh]
0x14008d6dc  mov     [rsp+128h+var_F8], rcx
0x14008d6e1  mov     [rsp+128h+BugCheckOnFailure], eax
0x14008d6e5  mov     r9, [rsp+128h+var_A8]
0x14008d6ed  mov     r8, 100000000h
0x14008d6f7  mov     rcx, cs:REMOTEFS_SMB_Context
0x14008d6fe  call    Template_qqbqb_ex
0x14008d703  mov     edx, eax
0x14008d705  test    edx, edx
0x14008d707  js      loc_14008D63B
0x14008d70d  mov     [rsp+128h+var_D8], 0
0x14008d712  mov     edx, [rsp+128h+var_D4]
0x14008d716  sub     edx, [rsp+128h+var_B0]
0x14008d71a  mov     [rsp+128h+var_D4], edx
0x14008d71e  mov     rcx, [rsp+128h+var_90]
0x14008d726  mov     rcx, [rcx]
0x14008d729  mov     [rsp+128h+var_90], rcx
0x14008d731  mov     r8d, [rsp+128h+var_D0]
0x14008d736  jmp     loc_14008D637
0x14008d73b  mov     [rsp+128h+var_B4], 0
0x14008d743  xor     r11b, r11b
0x14008d746  jmp     loc_14008D686
0x14008d74b  test    edx, edx
0x14008d74d  jz      loc_14008D9F2
0x14008d753  sub     edx, 2
0x14008d756  jnz     short loc_14008D77D
0x14008d758  mov     [rsp+128h+var_F8], r13
0x14008d75d  mov     qword ptr [rsp+128h+Priority], rcx
0x14008d762  mov     qword ptr [rsp+128h+BugCheckOnFailure], r15
0x14008d767  mov     r9d, r14d
0x14008d76a  mov     r8, rsi
0x14008d76d  mov     edx, r12d
0x14008d770  mov     rcx, rbx
0x14008d773  call    RxSmbdSend
0x14008d778  jmp     loc_14008D514
0x14008d77d  sub     edx, 1
0x14008d780  jz      loc_14008D9A8
0x14008d786  cmp     edx, 1
0x14008d789  jnz     loc_14008D516
0x14008d78f  mov     [rsp+128h+var_F8], r13
0x14008d794  mov     qword ptr [rsp+128h+BugCheckOnFailure], r15
0x14008d799  mov     r9d, r14d
0x14008d79c  mov     r8, rsi
0x14008d79f  mov     edx, r12d
0x14008d7a2  mov     rcx, rbx
0x14008d7a5  call    SmbQuicSend
0x14008d7aa  jmp     loc_14008D514
0x14008d7af  mov     [rsp+128h+Priority], 40000000h; Priority
0x14008d7b7  mov     [rsp+128h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14008d7bf  xor     r9d, r9d; RequestedAddress
0x14008d7c2  xor     edx, edx; AccessMode
0x14008d7c4  mov     r8d, 1; CacheType
0x14008d7ca  mov     rcx, rsi; MemoryDescriptorList
0x14008d7cd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008d7d4  nop     dword ptr [rax+rax+00h]
0x14008d7d9  jmp     loc_14008D59C
0x14008d7de  mov     [rsp+128h+Priority], 40000000h; Priority
0x14008d7e6  mov     [rsp+128h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14008d7ee  xor     r9d, r9d; RequestedAddress
0x14008d7f1  xor     edx, edx; AccessMode
0x14008d7f3  mov     r8d, 1; CacheType
0x14008d7f9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008d800  nop     dword ptr [rax+rax+00h]
0x14008d805  mov     r9, rax
0x14008d808  mov     [rsp+128h+var_C8], rax
0x14008d80d  mov     edx, [rsp+128h+var_D4]
0x14008d811  mov     r8d, [rsp+128h+var_D0]
0x14008d816  mov     r10d, [rsp+128h+var_B0]
0x14008d81b  jmp     loc_14008D66D
0x14008d820  test    al, al
0x14008d822  jz      loc_14008D8C0
0x14008d828  xorps   xmm0, xmm0
0x14008d82b  xor     eax, eax
0x14008d82d  movups  [rsp+128h+var_68], xmm0
0x14008d835  movups  [rsp+128h+var_58], xmm0
0x14008d83d  mov     [rsp+128h+var_48], rax
0x14008d845  movups  xmm0, xmmword ptr [rbx+1ACh]
0x14008d84c  movups  [rsp+128h+var_68+8], xmm0
0x14008d854  movups  xmm1, xmmword ptr [rbx+1B8h]
0x14008d85b  movups  [rsp+128h+var_58+4], xmm1
0x14008d863  movzx   eax, [rsp+128h+var_D6]
0x14008d868  mov     dword ptr [rsp+128h+var_68], eax
0x14008d86f  mov     dword ptr [rsp+128h+var_48+4], r8d
0x14008d877  mov     dword ptr [rsp+128h+var_68+4], 1Ch
0x14008d882  lea     rax, [rsp+128h+var_68]
0x14008d88a  mov     qword ptr [rsp+128h+Priority], rax
0x14008d88f  mov     [rsp+128h+BugCheckOnFailure], 28h ; '('
0x14008d897  mov     r9, [rsp+128h+var_A8]
0x14008d89f  mov     r8, 140000000h
0x14008d8a9  mov     rcx, cs:REMOTEFS_SMB_Context
0x14008d8b0  call    Template_qqbjqb_ex
0x14008d8b5  mov     edx, eax
0x14008d8b7  mov     ecx, [rsp+128h+var_CC]
0x14008d8bb  mov     r9, [rsp+128h+var_C8]
0x14008d8c0  test    ecx, ecx
0x14008d8c2  jz      loc_14008D705
0x14008d8c8  test    edx, edx
0x14008d8ca  js      loc_14008D63B
0x14008d8d0  mov     rax, 100000000h
0x14008d8da  mov     r8, rax
0x14008d8dd  mov     [rsp+128h+var_98], rax
0x14008d8e5  mov     eax, 0F000h
0x14008d8ea  cmp     ecx, eax
0x14008d8ec  cmovb   eax, ecx
0x14008d8ef  mov     [rsp+128h+var_A0], eax
0x14008d8f6  cmp     byte ptr [rsp+128h+var_B4], 0
0x14008d8fb  jnz     short loc_14008D953
0x14008d8fd  mov     qword ptr [rsp+128h+Priority], r9
0x14008d902  mov     [rsp+128h+BugCheckOnFailure], eax
0x14008d906  mov     r9, [rsp+128h+var_A8]
0x14008d90e  mov     rcx, cs:REMOTEFS_SMB_Context
0x14008d915  call    Template_qqbjqb_ex
0x14008d91a  mov     edx, eax
0x14008d91c  mov     ecx, [rsp+128h+var_CC]
0x14008d920  mov     eax, [rsp+128h+var_A0]
0x14008d927  sub     ecx, eax
0x14008d929  mov     [rsp+128h+var_CC], ecx
0x14008d92d  mov     r9, [rsp+128h+var_C8]
0x14008d932  add     r9, rax
0x14008d935  mov     [rsp+128h+var_C8], r9
0x14008d93a  mov     [rsp+128h+var_88], r9
0x14008d942  mov     [rsp+128h+var_98], 0
0x14008d94e  jmp     loc_14008D8C0
0x14008d953  cmp     ecx, eax
0x14008d955  jnz     short loc_14008D8FD
0x14008d957  mov     rcx, 180000000h
0x14008d961  mov     r8, rcx
0x14008d964  mov     [rsp+128h+var_98], rcx
0x14008d96c  jmp     short loc_14008D8FD
0x14008d96e  mov     ecx, [rsi+28h]
0x14008d971  mov     [rsp+128h+var_B8], ecx
0x14008d975  cmp     ecx, 40h ; '@'
0x14008d978  jb      short loc_14008D994
0x14008d97a  mov     rax, [rsp+128h+var_C8]
0x14008d97f  cmp     dword ptr [rax], 424D53FEh
0x14008d985  jnz     short loc_14008D994
0x14008d987  mov     ecx, [rax+14h]
0x14008d98a  add     ecx, 240h
0x14008d990  mov     [rsp+128h+var_B8], ecx
0x14008d994  cmp     ecx, r14d
0x14008d997  cmova   ecx, r14d
0x14008d99b  mov     [rsp+128h+var_D0], ecx
0x14008d99f  mov     [rsp+128h+var_B8], ecx
0x14008d9a3  jmp     loc_14008D5DB
0x14008d9a8  test    r15, r15
0x14008d9ab  jz      short loc_14008D9D2
0x14008d9ad  mov     qword ptr [rsp+128h+BugCheckOnFailure], 0; BugCheckParameter4
0x14008d9b6  mov     r9, r15; BugCheckParameter3
0x14008d9b9  mov     r8, rbx; BugCheckParameter2
0x14008d9bc  mov     edx, 747858D7h; BugCheckParameter1
0x14008d9c1  mov     ecx, 27h ; '''; BugCheckCode
0x14008d9c6  call    cs:__imp_KeBugCheckEx
0x14008d9d2  mov     qword ptr [rsp+128h+Priority], r13
0x14008d9d7  mov     qword ptr [rsp+128h+BugCheckOnFailure], rcx
0x14008d9dc  mov     r9d, r14d
0x14008d9df  mov     r8, rsi
0x14008d9e2  mov     edx, r12d
0x14008d9e5  mov     rcx, rbx
0x14008d9e8  call    RxVmbusSend
0x14008d9ed  jmp     loc_14008D514
0x14008d9f2  test    r15, r15
0x14008d9f5  jnz     short loc_14008DA1D
0x14008d9f7  test    rcx, rcx
0x14008d9fa  jnz     short loc_14008DA1D
0x14008d9fc  mov     qword ptr [rsp+128h+Priority], r13
0x14008da01  mov     [rsp+128h+BugCheckOnFailure], r14d
  ... truncated ...
```
