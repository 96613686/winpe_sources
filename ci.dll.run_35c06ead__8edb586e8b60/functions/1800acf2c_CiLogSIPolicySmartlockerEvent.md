# CiLogSIPolicySmartlockerEvent

- ea: `0x1800acf2c`
- end: `0x1800ad221`
- name: `CiLogSIPolicySmartlockerEvent`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e7db8`

## callees

- `0x18002c0d0`
- `0x1800acf2c`
- `0x1800ad2f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800ad1d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800ad1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800ad1d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800ad1eb`
- `ntoskrnl!EtwEventEnabled` at `0x1800ad07d`
- `ntoskrnl!EtwEventEnabled` at `0x1800ad07d`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800ad190`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800ad190`
- `ntoskrnl!EtwWrite` at `0x1800ad1b9`
- `ntoskrnl!EtwWrite` at `0x1800ad1b9`

## pseudocode

```c
__int64 __fastcall CiLogSIPolicySmartlockerEvent(const wchar_t *a1, unsigned int a2, unsigned int a3, int a4, int a5)
{
  __int64 v6; // rcx
  NTSTATUS PolicyNameAndID; // esi
  PVOID *v8; // r15
  PVOID *v9; // r13
  bool v10; // r14
  bool v11; // zf
  __int64 *v12; // rax
  __int64 *v13; // rbx
  int v14; // ecx
  __int64 v15; // rcx
  unsigned __int16 v16; // ax
  const GUID *ActivityIdThread; // rax
  __int16 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v20; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+3Ch] [rbp-C4h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+8Ch] [rbp-74h]
  int *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  int *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  int *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  int *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  int *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  int *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  int *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  __int16 *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  PVOID v49; // [rsp+110h] [rbp+10h]
  int v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+11Ch] [rbp+1Ch]
  __int16 *v52; // [rsp+120h] [rbp+20h]
  __int64 v53; // [rsp+128h] [rbp+28h]
  PVOID v54; // [rsp+130h] [rbp+30h]
  int v55; // [rsp+138h] [rbp+38h]
  int v56; // [rsp+13Ch] [rbp+3Ch]
  int v57; // [rsp+1A8h] [rbp+A8h] BYREF

  v57 = a4;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v6 = *((_QWORD *)g_SiPolicyHandles + a2);
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v28 = 0;
  v22 = *(_WORD *)(v6 + 46) & 1;
  if ( !a1 || *a1 <= 2u )
    a1 = L"\b\n";
  v23 = (*(_DWORD *)(v6 + 44) >> 27) & 1;
  v25 = (*(_DWORD *)(v6 + 44) >> 4) & 1;
  v24 = a3 & 1;
  v26 = (a3 >> 1) & 1;
  PolicyNameAndID = CiLogSIPolicyGetPolicyNameAndID(v6, P, v28);
  v8 = v28;
  v9 = P;
  if ( PolicyNameAndID < 0 )
  {
    v8 = (PVOID *)L"TV";
    v9 = (PVOID *)L"TV";
  }
  v10 = PolicyNameAndID >= 0;
  v19 = *a1 >> 1;
  if ( a5 < 0 )
  {
    v11 = v22 == 0;
    v13 = SmartlockerOperationalAudit;
    v12 = SmartlockerOperationalFailure;
  }
  else
  {
    v11 = (g_CiTestFlags & 0x200) == 0;
    v12 = (__int64 *)&SmartlockerVerbose;
    v13 = SmartlockerOperationalSuccess;
  }
  if ( v11 )
    v13 = v12;
  if ( EtwEventEnabled(g_EtwEventHandle, (PCEVENT_DESCRIPTOR)v13) )
  {
    v14 = *(unsigned __int16 *)v9;
    UserData.Ptr = (ULONGLONG)&v19;
    v30 = *((_QWORD *)a1 + 1);
    v31 = *a1;
    v33 = &a5;
    v35 = &v23;
    v37 = &v24;
    v39 = &v25;
    v41 = &v26;
    v43 = &v57;
    v45 = &v22;
    v20 = (unsigned __int16)v14 >> 1;
    v47 = &v20;
    v49 = v9[1];
    v50 = v14;
    v15 = *(unsigned __int16 *)v8;
    v16 = *(_WORD *)v8;
    *(_QWORD *)&UserData.Size = 2;
    v21 = v16 >> 1;
    v52 = &v21;
    v54 = v8[1];
    v32 = 0;
    v34 = 4;
    v36 = 4;
    v38 = 4;
    v40 = 4;
    v42 = 4;
    v44 = 4;
    v46 = 4;
    v48 = 2;
    v51 = 0;
    v53 = 2;
    v55 = v15;
    v56 = 0;
    ActivityIdThread = (const GUID *)IoGetActivityIdThread(v15);
    PolicyNameAndID = EtwWrite(g_EtwEventHandle, (PCEVENT_DESCRIPTOR)v13, ActivityIdThread, 0xDu, &UserData);
  }
  if ( v10 )
  {
    ExFreePoolWithTag(P[1], 0x63734943u);
    ExFreePoolWithTag(v28[1], 0x63734943u);
  }
  return (unsigned int)PolicyNameAndID;
}

```

## disassembly

```asm
0x1800acf2c  mov     [rsp-8+arg_0], rbx
0x1800acf31  mov     [rsp-8+arg_18], r9d
0x1800acf36  push    rbp
0x1800acf37  push    rsi
0x1800acf38  push    rdi
0x1800acf39  push    r12
0x1800acf3b  push    r13
0x1800acf3d  push    r14
0x1800acf3f  push    r15
0x1800acf41  lea     rbp, [rsp-50h]
0x1800acf46  sub     rsp, 150h
0x1800acf4d  mov     rax, cs:__security_cookie
0x1800acf54  xor     rax, rsp
0x1800acf57  mov     [rbp+80h+var_40], rax
0x1800acf5b  mov     rax, cs:g_SiPolicyHandles
0x1800acf62  xor     r12d, r12d
0x1800acf65  mov     rdi, rcx
0x1800acf68  mov     [rsp+180h+var_144], r12d
0x1800acf6d  mov     ecx, edx
0x1800acf6f  xorps   xmm0, xmm0
0x1800acf72  xorps   xmm1, xmm1
0x1800acf75  mov     [rsp+180h+var_150], r12w
0x1800acf7b  lea     ebx, [r12+1]
0x1800acf80  mov     [rsp+180h+var_14C], r12w
0x1800acf86  mov     [rsp+180h+var_148], r12w
0x1800acf8c  mov     rcx, [rax+rcx*8]
0x1800acf90  mov     [rsp+180h+var_140], r12d
0x1800acf95  mov     [rsp+180h+var_13C], r12d
0x1800acf9a  mov     [rsp+180h+var_138], r12d
0x1800acf9f  mov     [rsp+180h+var_134], r12d
0x1800acfa4  movups  xmmword ptr [rsp+180h+P], xmm0
0x1800acfa9  movups  xmmword ptr [rsp+180h+var_120], xmm1
0x1800acfae  movzx   eax, word ptr [rcx+2Eh]
0x1800acfb2  and     eax, ebx
0x1800acfb4  mov     [rsp+180h+var_144], eax
0x1800acfb8  lea     eax, [rbx+1]
0x1800acfbb  test    rdi, rdi
0x1800acfbe  jz      short loc_1800ACFC5
0x1800acfc0  cmp     [rdi], ax
0x1800acfc3  ja      short loc_1800ACFCC
0x1800acfc5  lea     rdi, asc_18002F230; "\b\n"
0x1800acfcc  mov     eax, [rcx+2Ch]
0x1800acfcf  lea     rdx, [rsp+180h+P]
0x1800acfd4  shr     eax, 1Bh
0x1800acfd7  and     eax, ebx
0x1800acfd9  mov     [rsp+180h+var_140], eax
0x1800acfdd  mov     eax, [rcx+2Ch]
0x1800acfe0  shr     eax, 4
0x1800acfe3  and     eax, ebx
0x1800acfe5  mov     [rsp+180h+var_138], eax
0x1800acfe9  mov     eax, r8d
0x1800acfec  shr     r8d, 1
0x1800acfef  and     eax, ebx
0x1800acff1  and     r8d, ebx
0x1800acff4  mov     [rsp+180h+var_13C], eax
0x1800acff8  mov     [rsp+180h+var_134], r8d
0x1800acffd  lea     r8, [rsp+180h+var_120]
0x1800ad002  call    CiLogSIPolicyGetPolicyNameAndID
0x1800ad007  mov     esi, eax
0x1800ad009  lea     r15, [rsp+180h+var_120]
0x1800ad00e  test    esi, esi
0x1800ad010  lea     rax, aTv; "TV"
0x1800ad017  lea     r13, [rsp+180h+P]
0x1800ad01c  mov     r14d, esi
0x1800ad01f  cmovs   r15, rax
0x1800ad023  cmovs   r13, rax
0x1800ad027  movzx   eax, word ptr [rdi]
0x1800ad02a  shr     r14d, 1Fh
0x1800ad02e  shr     ax, 1
0x1800ad031  xor     r14b, bl
0x1800ad034  mov     [rsp+180h+var_150], ax
0x1800ad039  cmp     [rbp+80h+arg_20], r12d
0x1800ad040  jl      short loc_1800AD05C
0x1800ad042  test    cs:g_CiTestFlags, 200h
0x1800ad04c  lea     rax, SmartlockerVerbose
0x1800ad053  lea     rbx, SmartlockerOperationalSuccess
0x1800ad05a  jmp     short loc_1800AD06F
0x1800ad05c  cmp     [rsp+180h+var_144], r12d
0x1800ad061  lea     rbx, SmartlockerOperationalAudit
0x1800ad068  lea     rax, SmartlockerOperationalFailure
0x1800ad06f  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800ad076  cmovz   rbx, rax
0x1800ad07a  mov     rdx, rbx; EventDescriptor
0x1800ad07d  call    cs:__imp_EtwEventEnabled
0x1800ad084  nop     dword ptr [rax+rax+00h]
0x1800ad089  test    al, al
0x1800ad08b  jz      loc_1800AD1C7
0x1800ad091  movzx   ecx, word ptr [r13+0]
0x1800ad096  lea     rax, [rsp+180h+var_150]
0x1800ad09b  mov     [rsp+180h+var_110.Ptr], rax
0x1800ad0a0  mov     rax, [rdi+8]
0x1800ad0a4  mov     [rbp+80h+var_100], rax
0x1800ad0a8  movzx   eax, word ptr [rdi]
0x1800ad0ab  mov     [rbp+80h+var_F8], eax
0x1800ad0ae  lea     rax, [rbp+80h+arg_20]
0x1800ad0b5  mov     [rbp+80h+var_F0], rax
0x1800ad0b9  lea     rax, [rsp+180h+var_140]
0x1800ad0be  mov     [rbp+80h+var_E0], rax
0x1800ad0c2  lea     rax, [rsp+180h+var_13C]
0x1800ad0c7  mov     [rbp+80h+var_D0], rax
0x1800ad0cb  lea     rax, [rsp+180h+var_138]
0x1800ad0d0  mov     [rbp+80h+var_C0], rax
0x1800ad0d4  lea     rax, [rsp+180h+var_134]
0x1800ad0d9  mov     [rbp+80h+var_B0], rax
0x1800ad0dd  lea     rax, [rbp+80h+arg_18]
0x1800ad0e4  mov     [rbp+80h+var_A0], rax
0x1800ad0e8  lea     rax, [rsp+180h+var_144]
0x1800ad0ed  mov     [rbp+80h+var_90], rax
0x1800ad0f1  movzx   eax, cx
0x1800ad0f4  shr     ax, 1
0x1800ad0f7  mov     [rsp+180h+var_14C], ax
0x1800ad0fc  lea     rax, [rsp+180h+var_14C]
0x1800ad101  mov     [rbp+80h+var_80], rax
0x1800ad105  mov     rax, [r13+8]
0x1800ad109  mov     [rbp+80h+var_70], rax
0x1800ad10d  mov     [rbp+80h+var_68], ecx
0x1800ad110  movzx   ecx, word ptr [r15]
0x1800ad114  movzx   eax, cx
0x1800ad117  mov     qword ptr [rsp+180h+var_110.Size], 2
0x1800ad120  shr     ax, 1
0x1800ad123  mov     [rsp+180h+var_148], ax
0x1800ad128  lea     rax, [rsp+180h+var_148]
0x1800ad12d  mov     [rbp+80h+var_60], rax
0x1800ad131  mov     rax, [r15+8]
0x1800ad135  mov     [rbp+80h+var_50], rax
0x1800ad139  mov     [rbp+80h+var_F4], r12d
0x1800ad13d  mov     [rbp+80h+var_E8], 4
0x1800ad145  mov     [rbp+80h+var_D8], 4
0x1800ad14d  mov     [rbp+80h+var_C8], 4
0x1800ad155  mov     [rbp+80h+var_B8], 4
0x1800ad15d  mov     [rbp+80h+var_A8], 4
0x1800ad165  mov     [rbp+80h+var_98], 4
0x1800ad16d  mov     [rbp+80h+var_88], 4
0x1800ad175  mov     [rbp+80h+var_78], 2
0x1800ad17d  mov     [rbp+80h+var_64], r12d
0x1800ad181  mov     [rbp+80h+var_58], 2
0x1800ad189  mov     [rbp+80h+var_48], ecx
0x1800ad18c  mov     [rbp+80h+var_44], r12d
0x1800ad190  call    cs:__imp_IoGetActivityIdThread
0x1800ad197  nop     dword ptr [rax+rax+00h]
0x1800ad19c  lea     rcx, [rsp+180h+var_110]
0x1800ad1a1  mov     r9d, 0Dh; UserDataCount
0x1800ad1a7  mov     [rsp+180h+UserData], rcx; UserData
0x1800ad1ac  mov     r8, rax; ActivityId
0x1800ad1af  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800ad1b6  mov     rdx, rbx; EventDescriptor
0x1800ad1b9  call    cs:__imp_EtwWrite
0x1800ad1c0  nop     dword ptr [rax+rax+00h]
0x1800ad1c5  mov     esi, eax
0x1800ad1c7  test    r14b, r14b
0x1800ad1ca  jz      short loc_1800AD1F7
0x1800ad1cc  mov     rcx, [rsp+180h+P+8]; P
0x1800ad1d1  mov     ebx, 63734943h
0x1800ad1d6  mov     edx, ebx; Tag
0x1800ad1d8  call    cs:__imp_ExFreePoolWithTag
0x1800ad1df  nop     dword ptr [rax+rax+00h]
0x1800ad1e4  mov     rcx, [rsp+180h+var_120+8]; P
0x1800ad1e9  mov     edx, ebx; Tag
0x1800ad1eb  call    cs:__imp_ExFreePoolWithTag
0x1800ad1f2  nop     dword ptr [rax+rax+00h]
0x1800ad1f7  mov     eax, esi
0x1800ad1f9  mov     rcx, [rbp+80h+var_40]
0x1800ad1fd  xor     rcx, rsp; StackCookie
0x1800ad200  call    __security_check_cookie
0x1800ad205  mov     rbx, [rsp+180h+arg_0]
0x1800ad20d  add     rsp, 150h
0x1800ad214  pop     r15
0x1800ad216  pop     r14
0x1800ad218  pop     r13
0x1800ad21a  pop     r12
0x1800ad21c  pop     rdi
0x1800ad21d  pop     rsi
0x1800ad21e  pop     rbp
0x1800ad21f  retn
```
