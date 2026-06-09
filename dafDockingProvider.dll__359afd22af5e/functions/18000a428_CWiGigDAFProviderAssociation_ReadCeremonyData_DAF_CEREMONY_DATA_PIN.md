# CWiGigDAFProviderAssociation::ReadCeremonyData(DAF_CEREMONY_DATA_PIN *)

- ea: `0x18000a428`
- end: `0x18000a784`
- name: `?ReadCeremonyData@CWiGigDAFProviderAssociation@@QEAAJPEAUDAF_CEREMONY_DATA_PIN@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CWiGigDAFProviderAssociation *__hidden this, struct DAF_CEREMONY_DATA_PIN *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000bee0`

## callees

- `0x1800073d8`
- `0x180009040`
- `0x18000a428`
- `0x18000c308`
- `0x18000c348`
- `0x180017f94`
- `0x18001ca3e`
- `0x18001ca70`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18000a638`
- `bcrypt!BCryptGenRandom` at `0x18000a638`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::ReadCeremonyData(
        CWiGigDAFProviderAssociation *this,
        struct DAF_CEREMONY_DATA_PIN *a2)
{
  _BYTE *v4; // rcx
  __int64 v5; // rdx
  int v7; // eax
  unsigned int v8; // edi
  _BYTE *v9; // rcx
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  NTSTATUS v12; // edi
  UCHAR pbBuffer[16]; // [rsp+70h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  memset_0((char *)a2 + 16, 0, 0x208u);
  if ( *((_BYTE *)this + 3288) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return CWiGigDAFProviderAssociation::CancelCleanup(this);
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 4u || (v4[28] & 1) == 0 )
      return CWiGigDAFProviderAssociation::CancelCleanup(this);
    v5 = 93;
LABEL_14:
    WPP_SF_q(*((_QWORD *)v4 + 2), v5, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
    return CWiGigDAFProviderAssociation::CancelCleanup(this);
  }
  v7 = ManualResetEvent::Wait((CWiGigDAFProviderAssociation *)((char *)this + 64), 0xEA60u);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v7);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 4u || (v9[28] & 1) == 0 )
      return v8;
    v10 = 95;
    goto LABEL_50;
  }
  if ( *((_BYTE *)this + 3288) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return CWiGigDAFProviderAssociation::CancelCleanup(this);
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 4u || (v4[28] & 1) == 0 )
      return CWiGigDAFProviderAssociation::CancelCleanup(this);
    v5 = 97;
    goto LABEL_14;
  }
  if ( *(_OWORD *)((char *)this + 76) != DAF_Ceremony_PinDisplay )
  {
    v9 = WPP_GLOBAL_Control;
    v8 = -2147019873;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return v8;
    }
    v10 = 98;
LABEL_50:
    WPP_SF_qD(*((_QWORD *)v9 + 2), v10, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v8);
    return v8;
  }
  *(_OWORD *)a2 = DAF_Ceremony_PinDisplay;
  v11 = BCryptGenRandom(*((BCRYPT_ALG_HANDLE *)this + 335), pbBuffer, 0xAu, 2u);
  v12 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_c2da2149000737c368804296c411cd66_Traceguids,
        this,
        v11 | 0x10000000);
    }
    return v12 | 0x10000000u;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  return StringCchPrintfW(
           (unsigned __int16 *)a2 + 8,
           0x104u,
           L"%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x%0.x",
           pbBuffer[0],
           pbBuffer[1],
           pbBuffer[2],
           pbBuffer[3],
           pbBuffer[4],
           pbBuffer[5],
           pbBuffer[6],
           pbBuffer[7],
           pbBuffer[8],
           pbBuffer[9]);
}

```

## disassembly

```asm
0x18000a428  mov     [rsp+arg_10], rbx
0x18000a42d  mov     [rsp+arg_18], rbp
0x18000a432  push    rsi
0x18000a433  push    rdi
0x18000a434  push    r12
0x18000a436  push    r14
0x18000a438  push    r15
0x18000a43a  sub     rsp, 90h
0x18000a441  mov     rax, cs:__security_cookie
0x18000a448  xor     rax, rsp
0x18000a44b  mov     [rsp+0B8h+var_38], rax
0x18000a453  mov     rsi, rdx
0x18000a456  mov     rbx, rcx
0x18000a459  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a460  lea     r15, WPP_GLOBAL_Control
0x18000a467  lea     r12, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a46e  mov     bpl, 1
0x18000a471  cmp     rcx, r15
0x18000a474  jz      short loc_18000A496
0x18000a476  cmp     byte ptr [rcx+19h], 4
0x18000a47a  jb      short loc_18000A496
0x18000a47c  test    [rcx+1Ch], bpl
0x18000a480  jz      short loc_18000A496
0x18000a482  mov     rcx, [rcx+10h]
0x18000a486  mov     edx, 5Bh ; '['
0x18000a48b  mov     r9, rbx
0x18000a48e  mov     r8, r12
0x18000a491  call    WPP_SF_q
0x18000a496  lea     r14, [rsi+10h]
0x18000a49a  xor     edx, edx; Val
0x18000a49c  mov     rcx, r14; void *
0x18000a49f  mov     r8d, 208h; Size
0x18000a4a5  call    memset_0
0x18000a4aa  cmp     byte ptr [rbx+0CD8h], 0
0x18000a4b1  jz      short loc_18000A518
0x18000a4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4ba  cmp     rcx, r15
0x18000a4bd  jz      short loc_18000A50B
0x18000a4bf  cmp     byte ptr [rcx+19h], 3
0x18000a4c3  jb      short loc_18000A4E6
0x18000a4c5  test    [rcx+1Ch], bpl
0x18000a4c9  jz      short loc_18000A4E6
0x18000a4cb  mov     rcx, [rcx+10h]
0x18000a4cf  mov     edx, 5Ch ; '\'
0x18000a4d4  mov     r9, rbx
0x18000a4d7  mov     r8, r12
0x18000a4da  call    WPP_SF_q
0x18000a4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4e6  cmp     rcx, r15
0x18000a4e9  jz      short loc_18000A50B
0x18000a4eb  cmp     byte ptr [rcx+19h], 4
0x18000a4ef  jb      short loc_18000A50B
0x18000a4f1  test    [rcx+1Ch], bpl
0x18000a4f5  jz      short loc_18000A50B
0x18000a4f7  mov     edx, 5Dh ; ']'
0x18000a4fc  mov     rcx, [rcx+10h]
0x18000a500  mov     r9, rbx
0x18000a503  mov     r8, r12
0x18000a506  call    WPP_SF_q
0x18000a50b  mov     rcx, rbx; this
0x18000a50e  call    ?CancelCleanup@CWiGigDAFProviderAssociation@@AEAAJXZ; CWiGigDAFProviderAssociation::CancelCleanup(void)
0x18000a513  jmp     loc_18000A758
0x18000a518  lea     rcx, [rbx+40h]; this
0x18000a51c  mov     edx, 0EA60h; unsigned int
0x18000a521  call    ?Wait@ManualResetEvent@@QEAAJK@Z; ManualResetEvent::Wait(ulong)
0x18000a526  mov     edi, eax
0x18000a528  test    eax, eax
0x18000a52a  jns     short loc_18000A58E
0x18000a52c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a533  cmp     rcx, r15
0x18000a536  jz      loc_18000A756
0x18000a53c  cmp     [rcx+19h], bpl
0x18000a540  jb      short loc_18000A567
0x18000a542  test    [rcx+1Ch], bpl
0x18000a546  jz      short loc_18000A567
0x18000a548  mov     rcx, [rcx+10h]
0x18000a54c  mov     edx, 5Eh ; '^'
0x18000a551  mov     r9, rbx
0x18000a554  mov     [rsp+0B8h+var_98], eax
0x18000a558  mov     r8, r12
0x18000a55b  call    WPP_SF_qD
0x18000a560  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a567  cmp     rcx, r15
0x18000a56a  jz      loc_18000A756
0x18000a570  cmp     byte ptr [rcx+19h], 4
0x18000a574  jb      loc_18000A756
0x18000a57a  test    [rcx+1Ch], bpl
0x18000a57e  jz      loc_18000A756
0x18000a584  mov     edx, 5Fh ; '_'
0x18000a589  jmp     loc_18000A743
0x18000a58e  cmp     byte ptr [rbx+0CD8h], 0
0x18000a595  jz      short loc_18000A5F5
0x18000a597  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a59e  cmp     rcx, r15
0x18000a5a1  jz      loc_18000A50B
0x18000a5a7  cmp     byte ptr [rcx+19h], 3
0x18000a5ab  jb      short loc_18000A5CE
0x18000a5ad  test    [rcx+1Ch], bpl
0x18000a5b1  jz      short loc_18000A5CE
0x18000a5b3  mov     rcx, [rcx+10h]
0x18000a5b7  mov     edx, 60h ; '`'
0x18000a5bc  mov     r9, rbx
0x18000a5bf  mov     r8, r12
0x18000a5c2  call    WPP_SF_q
0x18000a5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5ce  cmp     rcx, r15
0x18000a5d1  jz      loc_18000A50B
0x18000a5d7  cmp     byte ptr [rcx+19h], 4
0x18000a5db  jb      loc_18000A50B
0x18000a5e1  test    [rcx+1Ch], bpl
0x18000a5e5  jz      loc_18000A50B
0x18000a5eb  mov     edx, 61h ; 'a'
0x18000a5f0  jmp     loc_18000A4FC
0x18000a5f5  mov     rax, [rbx+4Ch]
0x18000a5f9  cmp     rax, qword ptr cs:DAF_Ceremony_PinDisplay
0x18000a600  jnz     loc_18000A721
0x18000a606  mov     rax, [rbx+54h]
0x18000a60a  cmp     rax, qword ptr cs:DAF_Ceremony_PinDisplay+8
0x18000a611  jnz     loc_18000A721
0x18000a617  movups  xmm0, cs:DAF_Ceremony_PinDisplay
0x18000a61e  mov     r9d, 2; dwFlags
0x18000a624  lea     rdx, [rsp+0B8h+pbBuffer]; pbBuffer
0x18000a629  movdqu  xmmword ptr [rsi], xmm0
0x18000a62d  mov     rcx, [rbx+0A78h]; hAlgorithm
0x18000a634  lea     r8d, [r9+8]; cbBuffer
0x18000a638  call    cs:__imp_BCryptGenRandom
0x18000a63e  mov     edi, eax
0x18000a640  test    eax, eax
0x18000a642  jz      short loc_18000A682
0x18000a644  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a64b  mov     esi, 10000000h
0x18000a650  cmp     rcx, r15
0x18000a653  jz      short loc_18000A67B
0x18000a655  cmp     byte ptr [rcx+19h], 4
0x18000a659  jb      short loc_18000A67B
0x18000a65b  test    [rcx+1Ch], bpl
0x18000a65f  jz      short loc_18000A67B
0x18000a661  mov     rcx, [rcx+10h]
0x18000a665  or      eax, esi
0x18000a667  mov     edx, 63h ; 'c'
0x18000a66c  mov     [rsp+0B8h+var_98], eax
0x18000a670  mov     r9, rbx
0x18000a673  mov     r8, r12
0x18000a676  call    WPP_SF_qD
0x18000a67b  or      edi, esi
0x18000a67d  jmp     loc_18000A756
0x18000a682  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a689  cmp     rcx, r15
0x18000a68c  jz      short loc_18000A6AE
0x18000a68e  cmp     byte ptr [rcx+19h], 4
0x18000a692  jb      short loc_18000A6AE
0x18000a694  test    [rcx+1Ch], bpl
0x18000a698  jz      short loc_18000A6AE
0x18000a69a  mov     rcx, [rcx+10h]
0x18000a69e  mov     edx, 64h ; 'd'
0x18000a6a3  mov     r9, rbx
0x18000a6a6  mov     r8, r12
0x18000a6a9  call    WPP_SF_q
0x18000a6ae  movzx   edx, [rsp+0B8h+var_40]
0x18000a6b3  mov     rcx, r14; unsigned __int16 *
0x18000a6b6  movzx   r8d, [rsp+0B8h+var_41]
0x18000a6bc  movzx   eax, [rsp+0B8h+var_3F]
0x18000a6c1  movzx   r10d, [rsp+0B8h+var_42]
0x18000a6c7  movzx   r11d, [rsp+0B8h+var_43]
0x18000a6cd  movzx   ebx, [rsp+0B8h+var_44]
0x18000a6d2  movzx   edi, [rsp+0B8h+var_45]
0x18000a6d7  movzx   esi, [rsp+0B8h+var_46]
0x18000a6dc  movzx   ebp, [rsp+0B8h+var_47]
0x18000a6e1  movzx   r9d, [rsp+0B8h+pbBuffer]
0x18000a6e7  mov     [rsp+0B8h+var_58], eax
0x18000a6eb  mov     [rsp+0B8h+var_60], edx
0x18000a6ef  mov     edx, 104h; unsigned __int64
0x18000a6f4  mov     [rsp+0B8h+var_68], r8d
0x18000a6f9  lea     r8, a02x02x02x02x02; "%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x%0.2"...
0x18000a700  mov     [rsp+0B8h+var_70], r10d
0x18000a705  mov     [rsp+0B8h+var_78], r11d
0x18000a70a  mov     [rsp+0B8h+var_80], ebx
0x18000a70e  mov     [rsp+0B8h+var_88], edi
0x18000a712  mov     [rsp+0B8h+var_90], esi
0x18000a716  mov     [rsp+0B8h+var_98], ebp
0x18000a71a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a71f  jmp     short loc_18000A758
0x18000a721  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a728  mov     edi, 8007139Fh
0x18000a72d  cmp     rcx, r15
0x18000a730  jz      short loc_18000A756
0x18000a732  cmp     byte ptr [rcx+19h], 4
0x18000a736  jb      short loc_18000A756
0x18000a738  test    [rcx+1Ch], bpl
0x18000a73c  jz      short loc_18000A756
0x18000a73e  mov     edx, 62h ; 'b'
0x18000a743  mov     rcx, [rcx+10h]
0x18000a747  mov     r9, rbx
0x18000a74a  mov     r8, r12
0x18000a74d  mov     [rsp+0B8h+var_98], edi
0x18000a751  call    WPP_SF_qD
0x18000a756  mov     eax, edi
0x18000a758  mov     rcx, [rsp+0B8h+var_38]
0x18000a760  xor     rcx, rsp; StackCookie
0x18000a763  call    __security_check_cookie
0x18000a768  lea     r11, [rsp+0B8h+var_28]
0x18000a770  mov     rbx, [r11+40h]
0x18000a774  mov     rbp, [r11+48h]
0x18000a778  mov     rsp, r11
0x18000a77b  pop     r15
0x18000a77d  pop     r14
0x18000a77f  pop     r12
0x18000a781  pop     rdi
0x18000a782  pop     rsi
0x18000a783  retn
```
