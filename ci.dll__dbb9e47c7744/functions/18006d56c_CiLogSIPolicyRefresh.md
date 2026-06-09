# CiLogSIPolicyRefresh

- ea: `0x18006d56c`
- end: `0x18006d7b6`
- name: `CiLogSIPolicyRefresh`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180058120`
- `0x18006d914`
- `0x1800e4ca8`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18006d56c`
- `0x18006e9ec`
- `0x18006ea54`
- `0x18007d04c`
- `0x1800a09a0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d773`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d784`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d773`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d784`
- `ntoskrnl!EtwEventEnabled` at `0x18006d5e9`
- `ntoskrnl!EtwEventEnabled` at `0x18006d5e9`
- `ntoskrnl!EtwWrite` at `0x18006d746`
- `ntoskrnl!EtwWrite` at `0x18006d746`

## pseudocode

```c
__int64 __fastcall CiLogSIPolicyRefresh(__int64 a1, __int64 a2, const EVENT_DESCRIPTOR *a3)
{
  NTSTATUS PolicyHash; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // rsi
  __int16 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v10; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+3Ch] [rbp-C4h] BYREF
  int PolicyOptionsV2; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v16; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  PWSTR Buffer; // [rsp+80h] [rbp-80h]
  int Length; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+8Ch] [rbp-74h]
  __int16 *v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  PWSTR v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+ACh] [rbp-54h]
  __int64 v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  int *v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  int *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  int *v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  _BYTE *v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F8h] [rbp-8h]
  int v36; // [rsp+FCh] [rbp-4h]
  int *p_PolicyOptionsV2; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  _BYTE v39[64]; // [rsp+110h] [rbp+10h] BYREF

  v14 = 0;
  memset(v39, 0, sizeof(v39));
  v11 = 64;
  v10 = 0;
  UnicodeString = 0;
  v9 = 0;
  PolicyHash = 0;
  v16 = 0;
  v12 = 0;
  PolicyOptionsV2 = 0;
  if ( EtwEventEnabled(g_EtwEventHandle, a3) )
  {
    v7 = (-(__int64)(*(_DWORD *)(a1 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL) + 704;
    PolicyHash = CipGetPolicyHash(a1, v6, v39, &v11);
    if ( PolicyHash >= 0 )
    {
      PolicyHash = CiLogSIPolicyGetPolicyIDs(a1, &v16, &UnicodeString);
      if ( PolicyHash >= 0 )
      {
        v12 = *(_DWORD *)(a1 + 44);
        PolicyOptionsV2 = SIPolicyGetPolicyOptionsV2(a1);
        v9 = UnicodeString.Length >> 1;
        UserData.Ptr = (ULONGLONG)&v9;
        Buffer = UnicodeString.Buffer;
        Length = UnicodeString.Length;
        v10 = v16.Length >> 1;
        v21 = &v10;
        v23 = v16.Buffer;
        v24 = v16.Length;
        v26 = v7 + a1;
        v28 = &v14;
        v30 = &v12;
        v32 = &v11;
        v34 = v39;
        v35 = v11;
        p_PolicyOptionsV2 = &PolicyOptionsV2;
        *(_QWORD *)&UserData.Size = 2;
        v20 = 0;
        v22 = 2;
        v25 = 0;
        v27 = 16;
        v29 = 4;
        v31 = 4;
        v33 = 4;
        v36 = 0;
        v38 = 4;
        PolicyHash = EtwWrite(g_EtwEventHandle, a3, 0, 0xAu, &UserData);
        if ( PolicyHash >= 0 && a3 == (const EVENT_DESCRIPTOR *)CiPolicyRefreshActivatePolicySucceded )
          PolicyHash = CipLogSIPolicySigner(a1);
      }
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v16);
  return (unsigned int)PolicyHash;
}

```

## disassembly

```asm
0x18006d56c  mov     [rsp-8+arg_8], rbx
0x18006d571  push    rbp
0x18006d572  push    rsi
0x18006d573  push    rdi
0x18006d574  push    r14
0x18006d576  push    r15
0x18006d578  lea     rbp, [rsp-60h]
0x18006d57d  sub     rsp, 160h
0x18006d584  mov     rax, cs:__security_cookie
0x18006d58b  xor     rax, rsp
0x18006d58e  mov     [rbp+80h+var_30], rax
0x18006d592  xor     r15d, r15d
0x18006d595  mov     r14, r8
0x18006d598  mov     rdi, rcx
0x18006d59b  mov     [rsp+180h+var_138], r15d
0x18006d5a0  xor     edx, edx; Val
0x18006d5a2  lea     rcx, [rbp+80h+var_70]; void *
0x18006d5a6  lea     ebx, [r15+40h]
0x18006d5aa  mov     r8d, ebx; Size
0x18006d5ad  call    memset
0x18006d5b2  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d5b9  xorps   xmm0, xmm0
0x18006d5bc  xorps   xmm1, xmm1
0x18006d5bf  mov     [rsp+180h+var_148], ebx
0x18006d5c3  mov     rdx, r14; EventDescriptor
0x18006d5c6  mov     [rsp+180h+var_14C], r15w
0x18006d5cc  movups  xmmword ptr [rsp+180h+UnicodeString.Length], xmm0
0x18006d5d1  mov     [rsp+180h+var_150], r15w
0x18006d5d7  mov     ebx, r15d
0x18006d5da  movups  xmmword ptr [rsp+180h+var_120.Length], xmm1
0x18006d5df  mov     [rsp+180h+var_144], r15d
0x18006d5e4  mov     [rsp+180h+var_140], r15d
0x18006d5e9  call    cs:__imp_EtwEventEnabled
0x18006d5f0  nop     dword ptr [rax+rax+00h]
0x18006d5f5  test    al, al
0x18006d5f7  jz      loc_18006D76E
0x18006d5fd  cmp     dword ptr [rdi+28h], 6
0x18006d601  lea     r9, [rsp+180h+var_148]
0x18006d606  lea     r8, [rbp+80h+var_70]
0x18006d60a  mov     rcx, rdi
0x18006d60d  sbb     rsi, rsi
0x18006d610  and     rsi, 0FFFFFFFFFFFFFD50h
0x18006d617  add     rsi, 2C0h
0x18006d61e  call    CipGetPolicyHash
0x18006d623  mov     ebx, eax
0x18006d625  test    eax, eax
0x18006d627  js      loc_18006D76E
0x18006d62d  lea     r8, [rsp+180h+UnicodeString]
0x18006d632  mov     rcx, rdi
0x18006d635  lea     rdx, [rsp+180h+var_120]
0x18006d63a  call    CiLogSIPolicyGetPolicyIDs
0x18006d63f  mov     ebx, eax
0x18006d641  test    eax, eax
0x18006d643  js      loc_18006D76E
0x18006d649  mov     eax, [rdi+2Ch]
0x18006d64c  mov     rcx, rdi
0x18006d64f  mov     [rsp+180h+var_144], eax
0x18006d653  call    SIPolicyGetPolicyOptionsV2
0x18006d658  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d65f  lea     r9d, [r15+0Ah]; UserDataCount
0x18006d663  mov     [rsp+180h+var_140], eax
0x18006d667  xor     r8d, r8d; ActivityId
0x18006d66a  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18006d66f  mov     rdx, r14; EventDescriptor
0x18006d672  shr     ax, 1
0x18006d675  mov     [rsp+180h+var_150], ax
0x18006d67a  lea     rax, [rsp+180h+var_150]
0x18006d67f  mov     [rsp+180h+var_110.Ptr], rax
0x18006d684  mov     rax, [rsp+180h+UnicodeString.Buffer]
0x18006d689  mov     [rbp+80h+var_100], rax
0x18006d68d  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18006d692  mov     [rbp+80h+var_F8], eax
0x18006d695  movzx   eax, [rsp+180h+var_120.Length]
0x18006d69a  shr     ax, 1
0x18006d69d  mov     [rsp+180h+var_14C], ax
0x18006d6a2  lea     rax, [rsp+180h+var_14C]
0x18006d6a7  mov     [rbp+80h+var_F0], rax
0x18006d6ab  mov     rax, [rsp+180h+var_120.Buffer]
0x18006d6b0  mov     [rbp+80h+var_E0], rax
0x18006d6b4  movzx   eax, [rsp+180h+var_120.Length]
0x18006d6b9  mov     [rbp+80h+var_D8], eax
0x18006d6bc  lea     rax, [rsi+rdi]
0x18006d6c0  mov     [rbp+80h+var_D0], rax
0x18006d6c4  lea     rax, [rsp+180h+var_138]
0x18006d6c9  mov     [rbp+80h+var_C0], rax
0x18006d6cd  lea     rax, [rsp+180h+var_144]
0x18006d6d2  mov     [rbp+80h+var_B0], rax
0x18006d6d6  lea     rax, [rsp+180h+var_148]
0x18006d6db  mov     [rbp+80h+var_A0], rax
0x18006d6df  lea     rax, [rbp+80h+var_70]
0x18006d6e3  mov     [rbp+80h+var_90], rax
0x18006d6e7  mov     eax, [rsp+180h+var_148]
0x18006d6eb  mov     [rbp+80h+var_88], eax
0x18006d6ee  lea     rax, [rsp+180h+var_140]
0x18006d6f3  mov     [rbp+80h+var_80], rax
0x18006d6f7  lea     rax, [rsp+180h+var_110]
0x18006d6fc  mov     [rsp+180h+UserData], rax; UserData
0x18006d701  mov     qword ptr [rsp+180h+var_110.Size], 2
0x18006d70a  mov     [rbp+80h+var_F4], r15d
0x18006d70e  mov     [rbp+80h+var_E8], 2
0x18006d716  mov     [rbp+80h+var_D4], r15d
0x18006d71a  mov     [rbp+80h+var_C8], 10h
0x18006d722  mov     [rbp+80h+var_B8], 4
0x18006d72a  mov     [rbp+80h+var_A8], 4
0x18006d732  mov     [rbp+80h+var_98], 4
0x18006d73a  mov     [rbp+80h+var_84], r15d
0x18006d73e  mov     [rbp+80h+var_78], 4
0x18006d746  call    cs:__imp_EtwWrite
0x18006d74d  nop     dword ptr [rax+rax+00h]
0x18006d752  mov     ebx, eax
0x18006d754  test    eax, eax
0x18006d756  js      short loc_18006D76E
0x18006d758  lea     rax, CiPolicyRefreshActivatePolicySucceded
0x18006d75f  cmp     r14, rax
0x18006d762  jnz     short loc_18006D76E
0x18006d764  mov     rcx, rdi
0x18006d767  call    CipLogSIPolicySigner
0x18006d76c  mov     ebx, eax
0x18006d76e  lea     rcx, [rsp+180h+UnicodeString]; UnicodeString
0x18006d773  call    cs:__imp_RtlFreeUnicodeString
0x18006d77a  nop     dword ptr [rax+rax+00h]
0x18006d77f  lea     rcx, [rsp+180h+var_120]; UnicodeString
0x18006d784  call    cs:__imp_RtlFreeUnicodeString
0x18006d78b  nop     dword ptr [rax+rax+00h]
0x18006d790  mov     eax, ebx
0x18006d792  mov     rcx, [rbp+80h+var_30]
0x18006d796  xor     rcx, rsp; StackCookie
0x18006d799  call    __security_check_cookie
0x18006d79e  mov     rbx, [rsp+180h+arg_8]
0x18006d7a6  add     rsp, 160h
0x18006d7ad  pop     r15
0x18006d7af  pop     r14
0x18006d7b1  pop     rdi
0x18006d7b2  pop     rsi
0x18006d7b3  pop     rbp
0x18006d7b4  retn
```
