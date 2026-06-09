# SecDetAssert25

- ea: `0x140040a08`
- end: `0x140040f3b`
- name: `SecDetAssert25`
- size: `1331`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14000ac80`

## callees

- `0x14000885c`
- `0x1400101a0`
- `0x140011650`
- `0x1400119c0`
- `0x140011bc0`
- `0x14002d86c`
- `0x14002e1f0`
- `0x14003a878`
- `0x140040a08`
- `0x140041e34`
- `0x140043150`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140040c43`
- `ntoskrnl!SeQueryInformationToken` at `0x140040c43`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140040c26`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140040c26`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140040edf`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140040edf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140040e41`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140040e41`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140040adb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140040adb`
- `ntoskrnl!PsInitialSystemProcess` at `0x140040c1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040e24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040ef9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040e24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040ef9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140040abf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140040e30`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140040abf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140040e30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ecf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ecf`
- `ntoskrnl!RtlLengthSid` at `0x140040bb5`
- `ntoskrnl!RtlLengthSid` at `0x140040bca`
- `ntoskrnl!RtlLengthSid` at `0x140040bb5`
- `ntoskrnl!RtlLengthSid` at `0x140040bca`

## pseudocode

```c
void __fastcall SecDetAssert25(__int64 a1, __int64 a2, char a3)
{
  char v6; // di
  __int64 v7; // r14
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 *v10; // r12
  __int64 v11; // r13
  __int64 v12; // r13
  ULONG v13; // esi
  int v14; // r8d
  char v15; // r10
  int v16; // eax
  __int64 v17; // r15
  int v18; // edx
  __int64 v19; // r9
  int v20; // ebx
  __int64 v21; // rdi
  __int64 v22; // rsi
  __int64 v23; // r14
  void *v24; // rcx
  int v25; // r13d
  PSID *v26; // rax
  __int64 v27; // r12
  const char *v28; // r11
  signed __int64 v29; // r11
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int128 v32; // xmm1
  _QWORD *v33; // r8
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  char v36[8]; // [rsp+F0h] [rbp-80h] BYREF
  _QWORD *v37; // [rsp+F8h] [rbp-78h]
  __int64 v38; // [rsp+100h] [rbp-70h]
  __int64 v39; // [rsp+108h] [rbp-68h]
  int v40; // [rsp+110h] [rbp-60h]
  int v41[2]; // [rsp+118h] [rbp-58h]
  __int64 v42; // [rsp+120h] [rbp-50h]
  PSID Sid; // [rsp+128h] [rbp-48h]
  PACCESS_TOKEN PrimaryToken; // [rsp+130h] [rbp-40h]
  PSID v45; // [rsp+138h] [rbp-38h]
  char v46[8]; // [rsp+140h] [rbp-30h]
  char v47[8]; // [rsp+148h] [rbp-28h]
  char v48[8]; // [rsp+150h] [rbp-20h]
  char v49[8]; // [rsp+158h] [rbp-18h]
  __int64 v50; // [rsp+160h] [rbp-10h]
  int v51[2]; // [rsp+168h] [rbp-8h]
  __int64 v52; // [rsp+170h] [rbp+0h]
  PVOID TokenInformation; // [rsp+178h] [rbp+8h] BYREF
  PACCESS_TOKEN Token[10]; // [rsp+180h] [rbp+10h] BYREF

  v42 = a2;
  memset(Token, 0, 0x48u);
  v6 = 0;
  TokenInformation = 0;
  v36[0] = 0;
  if ( *(_BYTE *)DetectionContext )
  {
    if ( (xmmword_14001B740 & 0x8000000) != 0
      && (*(_DWORD *)(a2 + 612) & 8) == 0
      && (int)SecDetSnapshotTokenIfFrozen(a1, a2, v36) >= 0 )
    {
      _mm_lfence();
      if ( (int)SecGetProcessTokenAssertionContext(a1, Token) >= 0 )
      {
        _mm_lfence();
        KeEnterCriticalRegion();
        v7 = a2 + 560;
        v52 = a2 + 560;
        ExAcquirePushLockSharedEx(a2 + 560, 0);
        v8 = 232;
        v9 = *(_DWORD *)(a2 + 96);
        if ( *(_DWORD *)(a2 + 380) == 1 )
          v8 = 304;
        v10 = (__int64 *)(v8 + a2);
        v11 = v8 + a2;
        v37 = (_QWORD *)(v8 + a2);
        if ( LODWORD(Token[4]) <= v9 || *(_BYTE *)(a2 + 384) || v9 == -1 || *(_DWORD *)(a2 + 280) )
        {
          if ( v36[0] || !*(_DWORD *)(a2 + 380) )
            goto LABEL_41;
          v12 = 432;
          if ( !*(_BYTE *)(a2 + 424) )
            v12 = v8;
          v11 = a2 + v12;
          v37 = (_QWORD *)v11;
          if ( Token[0] != *(PACCESS_TOKEN *)v11 )
          {
            v36[0] = 1;
            SecIncrementTokenMismatchAuditCount();
            v38 = 424;
LABEL_27:
            v39 = a2;
            _mm_lfence();
            PrimaryToken = PsReferencePrimaryToken(PsInitialSystemProcess);
            if ( SeQueryInformationToken(Token[0], TokenSource, &TokenInformation) < 0 )
              TokenInformation = 0;
            if ( Token[8] )
              Sid = *(PSID *)Token[8];
            else
              Sid = 0;
            v14 = *(_DWORD *)(a2 + 380);
            v15 = a3;
            v16 = *(_DWORD *)(a2 + 32);
            v17 = (__int64)v10 + 36;
            v18 = *(_DWORD *)(a2 + 96);
            v19 = *(_QWORD *)(a2 + 48);
            v20 = *((_DWORD *)v10 + 8);
            v21 = v10[3];
            v22 = v10[2];
            v23 = v10[1];
            v24 = **(void ***)(v11 + 64);
            v25 = *(_DWORD *)(v11 + 32);
            v40 = v16;
            v26 = (PSID *)v10[8];
            v27 = *v10;
            v45 = *v26;
            *(_QWORD *)v46 = v37[3];
            *(_QWORD *)v47 = v37[2];
            *(_QWORD *)v48 = v37[1];
            v28 = "        ";
            *(_QWORD *)v49 = *v37;
            if ( TokenInformation )
              v28 = (const char *)TokenInformation;
            v50 = (__int64)v28;
            *(_QWORD *)v51 = *(_QWORD *)(v42 + 40);
            v29 = _InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u);
            *(_QWORD *)v41 = v29 + 1;
            v30 = EventWrite25(
                    (int)v29 + 1,
                    v40,
                    v51[0],
                    (int)Token[0],
                    v50,
                    (char)Token[1],
                    (char)Token[2],
                    (char)Token[3],
                    (char)Token[4],
                    Sid,
                    v49[0],
                    (__int64)v37 + 36,
                    v48[0],
                    v47[0],
                    v46[0],
                    v25,
                    v24,
                    v27,
                    v17,
                    v23,
                    v22,
                    v21,
                    v20,
                    v45,
                    (char)PrimaryToken,
                    v15,
                    v19,
                    v14,
                    v18);
            SecIncrementEtwCounters(v30);
            v7 = v52;
            ExReleasePushLockEx_0(v52, 0);
            KeLeaveCriticalRegion();
            KeEnterCriticalRegion();
            ExAcquirePushLockExclusiveEx(v7, 0);
            if ( *(_BYTE *)(v38 + v39) == 1 )
            {
              _mm_lfence();
              SecReleaseProcessToken(v42 + 432);
            }
            v31 = v42;
            v32 = *(_OWORD *)&Token[2];
            v33 = TokenInformation;
            *(_OWORD *)(v42 + 432) = *(_OWORD *)Token;
            v34 = *(_OWORD *)&Token[4];
            *(_OWORD *)(v31 + 448) = v32;
            v35 = *(_OWORD *)&Token[6];
            *(_OWORD *)(v31 + 464) = v34;
            *(PACCESS_TOKEN *)&v34 = Token[8];
            *(_OWORD *)(v31 + 480) = v35;
            *(_QWORD *)(v31 + 496) = v34;
            if ( v33 )
              *(_QWORD *)(v31 + 468) = *v33;
            *(_BYTE *)(v31 + 424) = 1;
            if ( v33 )
              ExFreePoolWithTag(v33, 0);
            PsDereferencePrimaryToken(PrimaryToken);
            v6 = v36[0];
            goto LABEL_41;
          }
          _mm_lfence();
          if ( Token[1] == *(PACCESS_TOKEN *)(v11 + 8)
            && Token[2] == *(PACCESS_TOKEN *)(v11 + 16)
            && Token[3] == *(PACCESS_TOKEN *)(v11 + 24) )
          {
            _mm_lfence();
            v13 = RtlLengthSid(*(PSID *)Token[8]);
            if ( v13 == RtlLengthSid(**(PSID **)(v11 + 64)) )
            {
              _mm_lfence();
              if ( !memcmp(*(const void **)Token[8], **(const void ***)(v11 + 64), v13)
                && LODWORD(Token[4]) == *(_DWORD *)(v11 + 32) )
              {
LABEL_41:
                ExReleasePushLockEx_0(v7, 0);
                KeLeaveCriticalRegion();
                if ( !v6 )
                  SecReleaseProcessToken(Token);
                return;
              }
            }
          }
          v37 = (_QWORD *)v11;
          v38 = 424;
        }
        else
        {
          *(_BYTE *)(a2 + 384) = 1;
          v38 = 424;
        }
        v36[0] = 1;
        goto LABEL_27;
      }
    }
  }
}

```

## disassembly

```asm
0x140040a08  mov     [rsp-8+arg_18], rbx
0x140040a0d  push    rbp
0x140040a0e  push    rsi
0x140040a0f  push    rdi
0x140040a10  push    r12
0x140040a12  push    r13
0x140040a14  push    r14
0x140040a16  push    r15
0x140040a18  lea     rbp, [rsp-70h]
0x140040a1d  sub     rsp, 1E0h
0x140040a24  mov     rax, cs:__security_cookie
0x140040a2b  xor     rax, rsp
0x140040a2e  mov     [rbp+0A0h+var_40], rax
0x140040a32  mov     rbx, rdx
0x140040a35  mov     [rbp+0A0h+var_F0], rdx
0x140040a39  xor     edx, edx; Val
0x140040a3b  movzx   r15d, r8b
0x140040a3f  mov     rsi, rcx
0x140040a42  lea     rcx, [rbp+0A0h+Token]; void *
0x140040a46  lea     r8d, [rdx+48h]; Size
0x140040a4a  call    memset
0x140040a4f  mov     rax, cs:DetectionContext
0x140040a56  xor     dil, dil
0x140040a59  mov     [rbp+0A0h+TokenInformation], 0
0x140040a61  mov     [rbp+0A0h+var_120], dil
0x140040a65  mov     cl, [rax]
0x140040a67  test    cl, cl
0x140040a69  jz      loc_140040F13
0x140040a6f  test    qword ptr cs:xmmword_14001B740, 8000000h
0x140040a7a  jz      loc_140040F13
0x140040a80  mov     eax, [rbx+264h]
0x140040a86  test    al, 8
0x140040a88  jnz     loc_140040F13
0x140040a8e  lea     r8, [rbp+0A0h+var_120]
0x140040a92  mov     rdx, rbx
0x140040a95  mov     rcx, rsi
0x140040a98  call    SecDetSnapshotTokenIfFrozen
0x140040a9d  test    eax, eax
0x140040a9f  js      loc_140040F13
0x140040aa5  lfence
0x140040aa8  lea     rdx, [rbp+0A0h+Token]
0x140040aac  mov     rcx, rsi
0x140040aaf  call    SecGetProcessTokenAssertionContext
0x140040ab4  test    eax, eax
0x140040ab6  js      loc_140040F13
0x140040abc  lfence
0x140040abf  call    cs:__imp_KeEnterCriticalRegion
0x140040ac6  nop     dword ptr [rax+rax+00h]
0x140040acb  lea     r14, [rbx+230h]
0x140040ad2  xor     edx, edx
0x140040ad4  mov     rcx, r14
0x140040ad7  mov     [rbp+0A0h+var_A0], r14
0x140040adb  call    cs:__imp_ExAcquirePushLockSharedEx
0x140040ae2  nop     dword ptr [rax+rax+00h]
0x140040ae7  mov     eax, [rbx+17Ch]
0x140040aed  mov     ecx, 0E8h
0x140040af2  cmp     eax, 1
0x140040af5  mov     eax, [rbx+60h]
0x140040af8  lea     edx, [rcx+48h]
0x140040afb  cmovz   ecx, edx
0x140040afe  lea     r12, [rcx+rbx]
0x140040b02  mov     r13, r12
0x140040b05  mov     [rbp+0A0h+var_118], r12
0x140040b09  cmp     dword ptr [rbp+0A0h+var_70], eax
0x140040b0c  jbe     short loc_140040B39
0x140040b0e  cmp     [rbx+180h], dil
0x140040b15  jnz     short loc_140040B39
0x140040b17  cmp     eax, 0FFFFFFFFh
0x140040b1a  jz      short loc_140040B39
0x140040b1c  cmp     dword ptr [rbx+118h], 0
0x140040b23  jnz     short loc_140040B39
0x140040b25  mov     byte ptr [rbx+180h], 1
0x140040b2c  mov     [rbp+0A0h+var_110], 1A8h
0x140040b34  jmp     loc_140040C11
0x140040b39  cmp     [rbp+0A0h+var_120], dil
0x140040b3d  jnz     loc_140040EEF
0x140040b43  mov     eax, [rbx+17Ch]
0x140040b49  test    eax, eax
0x140040b4b  jz      loc_140040EEF
0x140040b51  cmp     [rbx+1A8h], dil
0x140040b58  mov     r13d, 1B0h
0x140040b5e  cmovz   r13, rcx
0x140040b62  add     r13, rbx
0x140040b65  mov     [rbp+0A0h+var_118], r13
0x140040b69  mov     rax, [r13+0]
0x140040b6d  cmp     [rbp+0A0h+Token], rax
0x140040b71  jz      short loc_140040B8A
0x140040b73  mov     [rbp+0A0h+var_120], 1
0x140040b77  call    SecIncrementTokenMismatchAuditCount
0x140040b7c  mov     edi, 1A8h
0x140040b81  mov     [rbp+0A0h+var_110], rdi
0x140040b85  jmp     loc_140040C15
0x140040b8a  lfence
0x140040b8d  mov     rax, [rbp+0A0h+Token+8]
0x140040b91  cmp     rax, [r13+8]
0x140040b95  jnz     short loc_140040C04
0x140040b97  mov     rax, qword ptr [rbp+0A0h+var_80]
0x140040b9b  cmp     rax, [r13+10h]
0x140040b9f  jnz     short loc_140040C04
0x140040ba1  mov     rax, qword ptr [rbp+0A0h+var_80+8]
0x140040ba5  cmp     rax, [r13+18h]
0x140040ba9  jnz     short loc_140040C04
0x140040bab  lfence
0x140040bae  mov     rcx, [rbp+0A0h+var_50]
0x140040bb2  mov     rcx, [rcx]; Sid
0x140040bb5  call    cs:__imp_RtlLengthSid
0x140040bbc  nop     dword ptr [rax+rax+00h]
0x140040bc1  mov     rcx, [r13+40h]
0x140040bc5  mov     esi, eax
0x140040bc7  mov     rcx, [rcx]; Sid
0x140040bca  call    cs:__imp_RtlLengthSid
0x140040bd1  nop     dword ptr [rax+rax+00h]
0x140040bd6  cmp     esi, eax
0x140040bd8  jnz     short loc_140040C04
0x140040bda  lfence
0x140040bdd  mov     rdx, [r13+40h]
0x140040be1  mov     r8d, esi; Size
0x140040be4  mov     rcx, [rbp+0A0h+var_50]
0x140040be8  mov     rdx, [rdx]; Buf2
0x140040beb  mov     rcx, [rcx]; Buf1
0x140040bee  call    memcmp
0x140040bf3  test    eax, eax
0x140040bf5  jnz     short loc_140040C04
0x140040bf7  mov     eax, [r13+20h]
0x140040bfb  cmp     dword ptr [rbp+0A0h+var_70], eax
0x140040bfe  jz      loc_140040EEF
0x140040c04  mov     edi, 1A8h
0x140040c09  mov     [rbp+0A0h+var_118], r13
0x140040c0d  mov     [rbp+0A0h+var_110], rdi
0x140040c11  mov     [rbp+0A0h+var_120], 1
0x140040c15  mov     [rbp+0A0h+var_108], rbx
0x140040c19  lfence
0x140040c1c  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140040c23  mov     rcx, [rcx]; Process
0x140040c26  call    cs:__imp_PsReferencePrimaryToken
0x140040c2d  nop     dword ptr [rax+rax+00h]
0x140040c32  mov     rcx, [rbp+0A0h+Token]; Token
0x140040c36  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x140040c3a  mov     edx, 7; TokenInformationClass
0x140040c3f  mov     [rbp+0A0h+PrimaryToken], rax
0x140040c43  call    cs:__imp_SeQueryInformationToken
0x140040c4a  nop     dword ptr [rax+rax+00h]
0x140040c4f  test    eax, eax
0x140040c51  jns     short loc_140040C5B
0x140040c53  mov     [rbp+0A0h+TokenInformation], 0
0x140040c5b  mov     rcx, [rbp+0A0h+var_50]
0x140040c5f  test    rcx, rcx
0x140040c62  jz      short loc_140040C6D
0x140040c64  mov     rax, [rcx]
0x140040c67  mov     [rbp+0A0h+var_E8], rax
0x140040c6b  jmp     short loc_140040C75
0x140040c6d  mov     [rbp+0A0h+var_E8], 0
0x140040c75  mov     r8d, [rbx+17Ch]
0x140040c7c  mov     r10d, r15d
0x140040c7f  mov     eax, [rbx+20h]
0x140040c82  lea     r15, [r12+24h]
0x140040c87  mov     rcx, [r13+40h]
0x140040c8b  mov     edx, [rbx+60h]
0x140040c8e  mov     r9, [rbx+30h]
0x140040c92  mov     ebx, [r12+20h]
0x140040c97  mov     rdi, [r12+18h]
0x140040c9c  mov     rsi, [r12+10h]
0x140040ca1  mov     r14, [r12+8]
0x140040ca6  mov     rcx, [rcx]
0x140040ca9  mov     r13d, [r13+20h]
0x140040cad  mov     [rbp+0A0h+var_100], eax
0x140040cb0  mov     rax, [r12+40h]
0x140040cb5  mov     r12, [r12]
0x140040cb9  mov     r11, [rax]
0x140040cbc  mov     [rbp+0A0h+var_D8], r11
0x140040cc0  mov     r11, [rbp+0A0h+var_118]
0x140040cc4  mov     rax, [r11+18h]
0x140040cc8  mov     qword ptr [rbp+0A0h+var_D0], rax
0x140040ccc  mov     rax, [r11+10h]
0x140040cd0  mov     qword ptr [rbp+0A0h+var_C8], rax
0x140040cd4  mov     rax, [r11+8]
0x140040cd8  mov     qword ptr [rbp+0A0h+var_C0], rax
0x140040cdc  mov     rax, [r11]
0x140040cdf  lea     r11, asc_1400169D8; "        "
0x140040ce6  mov     qword ptr [rbp+0A0h+var_B8], rax
0x140040cea  mov     rax, [rbp+0A0h+TokenInformation]
0x140040cee  test    rax, rax
0x140040cf1  cmovnz  r11, rax
0x140040cf5  mov     rax, [rbp+0A0h+var_F0]
0x140040cf9  mov     [rbp+0A0h+var_B0], r11
0x140040cfd  mov     r11d, 1
0x140040d03  mov     rax, [rax+28h]
0x140040d07  mov     qword ptr [rbp+0A0h+var_A8], rax
0x140040d0b  mov     rax, cs:SecData
0x140040d12  lock xadd [rax+150h], r11
0x140040d1b  mov     rax, [rbp+0A0h+PrimaryToken]
0x140040d1f  mov     dword ptr [rsp+210h+var_130], edx; char
0x140040d26  mov     edx, [rbp+0A0h+var_100]; int
0x140040d29  mov     dword ptr [rsp+210h+var_138], r8d; char
0x140040d31  mov     r8, qword ptr [rbp+0A0h+var_A8]; int
0x140040d35  mov     qword ptr [rsp+210h+var_140], r9; char
0x140040d3d  mov     r9, [rbp+0A0h+Token]; int
0x140040d41  mov     dword ptr [rsp+210h+var_148], r10d; char
0x140040d49  mov     qword ptr [rsp+210h+var_150], rax; char
0x140040d51  mov     rax, qword ptr [rbp+0A0h+var_D0]
0x140040d55  mov     qword ptr [rbp+0A0h+var_F8], r11
0x140040d59  mov     r11, [rbp+0A0h+var_D8]
0x140040d5d  inc     qword ptr [rbp+0A0h+var_F8]
0x140040d61  mov     [rsp+210h+var_158], r11; PSID
0x140040d69  mov     dword ptr [rsp+210h+var_160], ebx; char
0x140040d70  mov     qword ptr [rsp+210h+var_168], rdi; char
0x140040d78  mov     qword ptr [rsp+210h+var_170], rsi; char
0x140040d80  mov     qword ptr [rsp+210h+var_178], r14; char
0x140040d88  mov     [rsp+210h+var_180], r15; __int64
0x140040d90  mov     qword ptr [rsp+210h+var_188], r12; char
0x140040d98  mov     [rsp+210h+var_190], rcx; PSID
0x140040da0  mov     rcx, qword ptr [rbp+0A0h+var_F8]; int
0x140040da4  mov     dword ptr [rsp+210h+var_198], r13d; char
0x140040da9  mov     qword ptr [rsp+210h+var_1A0], rax; char
0x140040dae  mov     rax, qword ptr [rbp+0A0h+var_C8]
0x140040db2  mov     qword ptr [rsp+210h+var_1A8], rax; char
0x140040db7  mov     rax, qword ptr [rbp+0A0h+var_C0]
0x140040dbb  mov     qword ptr [rsp+210h+var_1B0], rax; char
0x140040dc0  mov     rax, [rbp+0A0h+var_118]
0x140040dc4  add     rax, 24h ; '$'
0x140040dc8  mov     [rsp+210h+var_1B8], rax; __int64
0x140040dcd  mov     rax, qword ptr [rbp+0A0h+var_B8]
0x140040dd1  mov     qword ptr [rsp+210h+var_1C0], rax; char
0x140040dd6  mov     rax, [rbp+0A0h+var_E8]
0x140040dda  mov     [rsp+210h+Sid], rax; Sid
0x140040ddf  mov     eax, dword ptr [rbp+0A0h+var_70]
0x140040de2  mov     dword ptr [rsp+210h+var_1D0], eax; char
0x140040de6  mov     rax, qword ptr [rbp+0A0h+var_80+8]
0x140040dea  mov     qword ptr [rsp+210h+var_1D8], rax; char
0x140040def  mov     rax, qword ptr [rbp+0A0h+var_80]
0x140040df3  mov     qword ptr [rsp+210h+var_1E0], rax; char
0x140040df8  mov     rax, [rbp+0A0h+Token+8]
0x140040dfc  mov     qword ptr [rsp+210h+var_1E8], rax; char
0x140040e01  mov     rax, [rbp+0A0h+var_B0]
0x140040e05  mov     [rsp+210h+var_1F0], rax; __int64
0x140040e0a  call    EventWrite25
0x140040e0f  mov     ecx, eax
0x140040e11  call    SecIncrementEtwCounters
0x140040e16  mov     r14, [rbp+0A0h+var_A0]
0x140040e1a  xor     edx, edx
0x140040e1c  mov     rcx, r14
0x140040e1f  call    ExReleasePushLockEx_0
0x140040e24  call    cs:__imp_KeLeaveCriticalRegion
0x140040e2b  nop     dword ptr [rax+rax+00h]
0x140040e30  call    cs:__imp_KeEnterCriticalRegion
0x140040e37  nop     dword ptr [rax+rax+00h]
0x140040e3c  xor     edx, edx
0x140040e3e  mov     rcx, r14
0x140040e41  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140040e48  nop     dword ptr [rax+rax+00h]
0x140040e4d  mov     rax, [rbp+0A0h+var_110]
0x140040e51  mov     rcx, [rbp+0A0h+var_108]
0x140040e55  cmp     byte ptr [rax+rcx], 1
0x140040e59  jnz     short loc_140040E6E
0x140040e5b  lfence
0x140040e5e  mov     rcx, [rbp+0A0h+var_F0]
0x140040e62  add     rcx, 1B0h
0x140040e69  call    SecReleaseProcessToken
0x140040e6e  mov     rcx, [rbp+0A0h+var_F0]
0x140040e72  movaps  xmm0, xmmword ptr [rbp+0A0h+Token]
0x140040e76  movaps  xmm1, xmmword ptr [rbp+0A0h+var_80]
0x140040e7a  mov     r8, [rbp+0A0h+TokenInformation]
0x140040e7e  movups  xmmword ptr [rcx+1B0h], xmm0
0x140040e85  movaps  xmm0, xmmword ptr [rbp+0A0h+var_70]
0x140040e89  movups  xmmword ptr [rcx+1C0h], xmm1
0x140040e90  movaps  xmm1, [rbp+0A0h+var_60]
0x140040e94  movups  xmmword ptr [rcx+1D0h], xmm0
0x140040e9b  movsd   xmm0, [rbp+0A0h+var_50]
0x140040ea0  movups  xmmword ptr [rcx+1E0h], xmm1
0x140040ea7  movsd   qword ptr [rcx+1F0h], xmm0
0x140040eaf  test    r8, r8
0x140040eb2  jz      short loc_140040EBE
0x140040eb4  mov     rax, [r8]
0x140040eb7  mov     [rcx+1D4h], rax
0x140040ebe  mov     byte ptr [rcx+1A8h], 1
0x140040ec5  test    r8, r8
0x140040ec8  jz      short loc_140040EDB
0x140040eca  xor     edx, edx; Tag
0x140040ecc  mov     rcx, r8; P
0x140040ecf  call    cs:__imp_ExFreePoolWithTag
0x140040ed6  nop     dword ptr [rax+rax+00h]
0x140040edb  mov     rcx, [rbp+0A0h+PrimaryToken]; PrimaryToken
0x140040edf  call    cs:__imp_PsDereferencePrimaryToken
0x140040ee6  nop     dword ptr [rax+rax+00h]
0x140040eeb  mov     dil, [rbp+0A0h+var_120]
0x140040eef  xor     edx, edx
0x140040ef1  mov     rcx, r14
0x140040ef4  call    ExReleasePushLockEx_0
0x140040ef9  call    cs:__imp_KeLeaveCriticalRegion
0x140040f00  nop     dword ptr [rax+rax+00h]
0x140040f05  test    dil, dil
0x140040f08  jnz     short loc_140040F13
0x140040f0a  lea     rcx, [rbp+0A0h+Token]
0x140040f0e  call    SecReleaseProcessToken
0x140040f13  mov     rcx, [rbp+0A0h+var_40]
0x140040f17  xor     rcx, rsp; StackCookie
0x140040f1a  call    __security_check_cookie
0x140040f1f  mov     rbx, [rsp+210h+arg_18]
0x140040f27  add     rsp, 1E0h
0x140040f2e  pop     r15
  ... truncated ...
```
