# CiLogSIPolicySmartlockerEvent

- ea: `0x1800a2818`
- end: `0x1800a2b0d`
- name: `CiLogSIPolicySmartlockerEvent`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e7584`

## callees

- `0x18002bf20`
- `0x1800a1880`
- `0x1800a2818`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2ad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2ad7`
- `ntoskrnl!EtwEventEnabled` at `0x1800a2969`
- `ntoskrnl!EtwEventEnabled` at `0x1800a2969`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a2a7c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a2a7c`
- `ntoskrnl!EtwWrite` at `0x1800a2aa5`
- `ntoskrnl!EtwWrite` at `0x1800a2aa5`

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
0x1800a2818  mov     [rsp-8+arg_0], rbx
0x1800a281d  mov     [rsp-8+arg_18], r9d
0x1800a2822  push    rbp
0x1800a2823  push    rsi
0x1800a2824  push    rdi
0x1800a2825  push    r12
0x1800a2827  push    r13
0x1800a2829  push    r14
0x1800a282b  push    r15
0x1800a282d  lea     rbp, [rsp-50h]
0x1800a2832  sub     rsp, 150h
0x1800a2839  mov     rax, cs:__security_cookie
0x1800a2840  xor     rax, rsp
0x1800a2843  mov     [rbp+80h+var_40], rax
0x1800a2847  mov     rax, cs:g_SiPolicyHandles
0x1800a284e  xor     r12d, r12d
0x1800a2851  mov     rdi, rcx
0x1800a2854  mov     [rsp+180h+var_144], r12d
0x1800a2859  mov     ecx, edx
0x1800a285b  xorps   xmm0, xmm0
0x1800a285e  xorps   xmm1, xmm1
0x1800a2861  mov     [rsp+180h+var_150], r12w
0x1800a2867  lea     ebx, [r12+1]
0x1800a286c  mov     [rsp+180h+var_14C], r12w
0x1800a2872  mov     [rsp+180h+var_148], r12w
0x1800a2878  mov     rcx, [rax+rcx*8]
0x1800a287c  mov     [rsp+180h+var_140], r12d
0x1800a2881  mov     [rsp+180h+var_13C], r12d
0x1800a2886  mov     [rsp+180h+var_138], r12d
0x1800a288b  mov     [rsp+180h+var_134], r12d
0x1800a2890  movups  xmmword ptr [rsp+180h+P], xmm0
0x1800a2895  movups  xmmword ptr [rsp+180h+var_120], xmm1
0x1800a289a  movzx   eax, word ptr [rcx+2Eh]
0x1800a289e  and     eax, ebx
0x1800a28a0  mov     [rsp+180h+var_144], eax
0x1800a28a4  lea     eax, [rbx+1]
0x1800a28a7  test    rdi, rdi
0x1800a28aa  jz      short loc_1800A28B1
0x1800a28ac  cmp     [rdi], ax
0x1800a28af  ja      short loc_1800A28B8
0x1800a28b1  lea     rdi, asc_18002EF88; "\b\n"
0x1800a28b8  mov     eax, [rcx+2Ch]
0x1800a28bb  lea     rdx, [rsp+180h+P]
0x1800a28c0  shr     eax, 1Bh
0x1800a28c3  and     eax, ebx
0x1800a28c5  mov     [rsp+180h+var_140], eax
0x1800a28c9  mov     eax, [rcx+2Ch]
0x1800a28cc  shr     eax, 4
0x1800a28cf  and     eax, ebx
0x1800a28d1  mov     [rsp+180h+var_138], eax
0x1800a28d5  mov     eax, r8d
0x1800a28d8  shr     r8d, 1
0x1800a28db  and     eax, ebx
0x1800a28dd  and     r8d, ebx
0x1800a28e0  mov     [rsp+180h+var_13C], eax
0x1800a28e4  mov     [rsp+180h+var_134], r8d
0x1800a28e9  lea     r8, [rsp+180h+var_120]
0x1800a28ee  call    CiLogSIPolicyGetPolicyNameAndID
0x1800a28f3  mov     esi, eax
0x1800a28f5  lea     r15, [rsp+180h+var_120]
0x1800a28fa  test    esi, esi
0x1800a28fc  lea     rax, aTv; "TV"
0x1800a2903  lea     r13, [rsp+180h+P]
0x1800a2908  mov     r14d, esi
0x1800a290b  cmovs   r15, rax
0x1800a290f  cmovs   r13, rax
0x1800a2913  movzx   eax, word ptr [rdi]
0x1800a2916  shr     r14d, 1Fh
0x1800a291a  shr     ax, 1
0x1800a291d  xor     r14b, bl
0x1800a2920  mov     [rsp+180h+var_150], ax
0x1800a2925  cmp     [rbp+80h+arg_20], r12d
0x1800a292c  jl      short loc_1800A2948
0x1800a292e  test    cs:g_CiTestFlags, 200h
0x1800a2938  lea     rax, SmartlockerVerbose
0x1800a293f  lea     rbx, SmartlockerOperationalSuccess
0x1800a2946  jmp     short loc_1800A295B
0x1800a2948  cmp     [rsp+180h+var_144], r12d
0x1800a294d  lea     rbx, SmartlockerOperationalAudit
0x1800a2954  lea     rax, SmartlockerOperationalFailure
0x1800a295b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a2962  cmovz   rbx, rax
0x1800a2966  mov     rdx, rbx; EventDescriptor
0x1800a2969  call    cs:__imp_EtwEventEnabled
0x1800a2970  nop     dword ptr [rax+rax+00h]
0x1800a2975  test    al, al
0x1800a2977  jz      loc_1800A2AB3
0x1800a297d  movzx   ecx, word ptr [r13+0]
0x1800a2982  lea     rax, [rsp+180h+var_150]
0x1800a2987  mov     [rsp+180h+var_110.Ptr], rax
0x1800a298c  mov     rax, [rdi+8]
0x1800a2990  mov     [rbp+80h+var_100], rax
0x1800a2994  movzx   eax, word ptr [rdi]
0x1800a2997  mov     [rbp+80h+var_F8], eax
0x1800a299a  lea     rax, [rbp+80h+arg_20]
0x1800a29a1  mov     [rbp+80h+var_F0], rax
0x1800a29a5  lea     rax, [rsp+180h+var_140]
0x1800a29aa  mov     [rbp+80h+var_E0], rax
0x1800a29ae  lea     rax, [rsp+180h+var_13C]
0x1800a29b3  mov     [rbp+80h+var_D0], rax
0x1800a29b7  lea     rax, [rsp+180h+var_138]
0x1800a29bc  mov     [rbp+80h+var_C0], rax
0x1800a29c0  lea     rax, [rsp+180h+var_134]
0x1800a29c5  mov     [rbp+80h+var_B0], rax
0x1800a29c9  lea     rax, [rbp+80h+arg_18]
0x1800a29d0  mov     [rbp+80h+var_A0], rax
0x1800a29d4  lea     rax, [rsp+180h+var_144]
0x1800a29d9  mov     [rbp+80h+var_90], rax
0x1800a29dd  movzx   eax, cx
0x1800a29e0  shr     ax, 1
0x1800a29e3  mov     [rsp+180h+var_14C], ax
0x1800a29e8  lea     rax, [rsp+180h+var_14C]
0x1800a29ed  mov     [rbp+80h+var_80], rax
0x1800a29f1  mov     rax, [r13+8]
0x1800a29f5  mov     [rbp+80h+var_70], rax
0x1800a29f9  mov     [rbp+80h+var_68], ecx
0x1800a29fc  movzx   ecx, word ptr [r15]
0x1800a2a00  movzx   eax, cx
0x1800a2a03  mov     qword ptr [rsp+180h+var_110.Size], 2
0x1800a2a0c  shr     ax, 1
0x1800a2a0f  mov     [rsp+180h+var_148], ax
0x1800a2a14  lea     rax, [rsp+180h+var_148]
0x1800a2a19  mov     [rbp+80h+var_60], rax
0x1800a2a1d  mov     rax, [r15+8]
0x1800a2a21  mov     [rbp+80h+var_50], rax
0x1800a2a25  mov     [rbp+80h+var_F4], r12d
0x1800a2a29  mov     [rbp+80h+var_E8], 4
0x1800a2a31  mov     [rbp+80h+var_D8], 4
0x1800a2a39  mov     [rbp+80h+var_C8], 4
0x1800a2a41  mov     [rbp+80h+var_B8], 4
0x1800a2a49  mov     [rbp+80h+var_A8], 4
0x1800a2a51  mov     [rbp+80h+var_98], 4
0x1800a2a59  mov     [rbp+80h+var_88], 4
0x1800a2a61  mov     [rbp+80h+var_78], 2
0x1800a2a69  mov     [rbp+80h+var_64], r12d
0x1800a2a6d  mov     [rbp+80h+var_58], 2
0x1800a2a75  mov     [rbp+80h+var_48], ecx
0x1800a2a78  mov     [rbp+80h+var_44], r12d
0x1800a2a7c  call    cs:__imp_IoGetActivityIdThread
0x1800a2a83  nop     dword ptr [rax+rax+00h]
0x1800a2a88  lea     rcx, [rsp+180h+var_110]
0x1800a2a8d  mov     r9d, 0Dh; UserDataCount
0x1800a2a93  mov     [rsp+180h+UserData], rcx; UserData
0x1800a2a98  mov     r8, rax; ActivityId
0x1800a2a9b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a2aa2  mov     rdx, rbx; EventDescriptor
0x1800a2aa5  call    cs:__imp_EtwWrite
0x1800a2aac  nop     dword ptr [rax+rax+00h]
0x1800a2ab1  mov     esi, eax
0x1800a2ab3  test    r14b, r14b
0x1800a2ab6  jz      short loc_1800A2AE3
0x1800a2ab8  mov     rcx, [rsp+180h+P+8]; P
0x1800a2abd  mov     ebx, 63734943h
0x1800a2ac2  mov     edx, ebx; Tag
0x1800a2ac4  call    cs:__imp_ExFreePoolWithTag
0x1800a2acb  nop     dword ptr [rax+rax+00h]
0x1800a2ad0  mov     rcx, [rsp+180h+var_120+8]; P
0x1800a2ad5  mov     edx, ebx; Tag
0x1800a2ad7  call    cs:__imp_ExFreePoolWithTag
0x1800a2ade  nop     dword ptr [rax+rax+00h]
0x1800a2ae3  mov     eax, esi
0x1800a2ae5  mov     rcx, [rbp+80h+var_40]
0x1800a2ae9  xor     rcx, rsp; StackCookie
0x1800a2aec  call    __security_check_cookie
0x1800a2af1  mov     rbx, [rsp+180h+arg_0]
0x1800a2af9  add     rsp, 150h
0x1800a2b00  pop     r15
0x1800a2b02  pop     r14
0x1800a2b04  pop     r13
0x1800a2b06  pop     r12
0x1800a2b08  pop     rdi
0x1800a2b09  pop     rsi
0x1800a2b0a  pop     rbp
0x1800a2b0b  retn
```
