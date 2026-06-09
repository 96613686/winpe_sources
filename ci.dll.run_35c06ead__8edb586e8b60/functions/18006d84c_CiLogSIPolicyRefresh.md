# CiLogSIPolicyRefresh

- ea: `0x18006d84c`
- end: `0x18006da96`
- name: `CiLogSIPolicyRefresh`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180058048`
- `0x18006dbf4`
- `0x1800e5228`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18006d84c`
- `0x18006eccc`
- `0x18006ed34`
- `0x18007d7cc`
- `0x180091448`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006da53`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006da64`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006da53`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006da64`
- `ntoskrnl!EtwEventEnabled` at `0x18006d8c9`
- `ntoskrnl!EtwEventEnabled` at `0x18006d8c9`
- `ntoskrnl!EtwWrite` at `0x18006da26`
- `ntoskrnl!EtwWrite` at `0x18006da26`

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
0x18006d84c  mov     [rsp-8+arg_8], rbx
0x18006d851  push    rbp
0x18006d852  push    rsi
0x18006d853  push    rdi
0x18006d854  push    r14
0x18006d856  push    r15
0x18006d858  lea     rbp, [rsp-60h]
0x18006d85d  sub     rsp, 160h
0x18006d864  mov     rax, cs:__security_cookie
0x18006d86b  xor     rax, rsp
0x18006d86e  mov     [rbp+80h+var_30], rax
0x18006d872  xor     r15d, r15d
0x18006d875  mov     r14, r8
0x18006d878  mov     rdi, rcx
0x18006d87b  mov     [rsp+180h+var_138], r15d
0x18006d880  xor     edx, edx; Val
0x18006d882  lea     rcx, [rbp+80h+var_70]; void *
0x18006d886  lea     ebx, [r15+40h]
0x18006d88a  mov     r8d, ebx; Size
0x18006d88d  call    memset
0x18006d892  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d899  xorps   xmm0, xmm0
0x18006d89c  xorps   xmm1, xmm1
0x18006d89f  mov     [rsp+180h+var_148], ebx
0x18006d8a3  mov     rdx, r14; EventDescriptor
0x18006d8a6  mov     [rsp+180h+var_14C], r15w
0x18006d8ac  movups  xmmword ptr [rsp+180h+UnicodeString.Length], xmm0
0x18006d8b1  mov     [rsp+180h+var_150], r15w
0x18006d8b7  mov     ebx, r15d
0x18006d8ba  movups  xmmword ptr [rsp+180h+var_120.Length], xmm1
0x18006d8bf  mov     [rsp+180h+var_144], r15d
0x18006d8c4  mov     [rsp+180h+var_140], r15d
0x18006d8c9  call    cs:__imp_EtwEventEnabled
0x18006d8d0  nop     dword ptr [rax+rax+00h]
0x18006d8d5  test    al, al
0x18006d8d7  jz      loc_18006DA4E
0x18006d8dd  cmp     dword ptr [rdi+28h], 6
0x18006d8e1  lea     r9, [rsp+180h+var_148]
0x18006d8e6  lea     r8, [rbp+80h+var_70]
0x18006d8ea  mov     rcx, rdi
0x18006d8ed  sbb     rsi, rsi
0x18006d8f0  and     rsi, 0FFFFFFFFFFFFFD50h
0x18006d8f7  add     rsi, 2C0h
0x18006d8fe  call    CipGetPolicyHash
0x18006d903  mov     ebx, eax
0x18006d905  test    eax, eax
0x18006d907  js      loc_18006DA4E
0x18006d90d  lea     r8, [rsp+180h+UnicodeString]
0x18006d912  mov     rcx, rdi
0x18006d915  lea     rdx, [rsp+180h+var_120]
0x18006d91a  call    CiLogSIPolicyGetPolicyIDs
0x18006d91f  mov     ebx, eax
0x18006d921  test    eax, eax
0x18006d923  js      loc_18006DA4E
0x18006d929  mov     eax, [rdi+2Ch]
0x18006d92c  mov     rcx, rdi
0x18006d92f  mov     [rsp+180h+var_144], eax
0x18006d933  call    SIPolicyGetPolicyOptionsV2
0x18006d938  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d93f  lea     r9d, [r15+0Ah]; UserDataCount
0x18006d943  mov     [rsp+180h+var_140], eax
0x18006d947  xor     r8d, r8d; ActivityId
0x18006d94a  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18006d94f  mov     rdx, r14; EventDescriptor
0x18006d952  shr     ax, 1
0x18006d955  mov     [rsp+180h+var_150], ax
0x18006d95a  lea     rax, [rsp+180h+var_150]
0x18006d95f  mov     [rsp+180h+var_110.Ptr], rax
0x18006d964  mov     rax, [rsp+180h+UnicodeString.Buffer]
0x18006d969  mov     [rbp+80h+var_100], rax
0x18006d96d  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18006d972  mov     [rbp+80h+var_F8], eax
0x18006d975  movzx   eax, [rsp+180h+var_120.Length]
0x18006d97a  shr     ax, 1
0x18006d97d  mov     [rsp+180h+var_14C], ax
0x18006d982  lea     rax, [rsp+180h+var_14C]
0x18006d987  mov     [rbp+80h+var_F0], rax
0x18006d98b  mov     rax, [rsp+180h+var_120.Buffer]
0x18006d990  mov     [rbp+80h+var_E0], rax
0x18006d994  movzx   eax, [rsp+180h+var_120.Length]
0x18006d999  mov     [rbp+80h+var_D8], eax
0x18006d99c  lea     rax, [rsi+rdi]
0x18006d9a0  mov     [rbp+80h+var_D0], rax
0x18006d9a4  lea     rax, [rsp+180h+var_138]
0x18006d9a9  mov     [rbp+80h+var_C0], rax
0x18006d9ad  lea     rax, [rsp+180h+var_144]
0x18006d9b2  mov     [rbp+80h+var_B0], rax
0x18006d9b6  lea     rax, [rsp+180h+var_148]
0x18006d9bb  mov     [rbp+80h+var_A0], rax
0x18006d9bf  lea     rax, [rbp+80h+var_70]
0x18006d9c3  mov     [rbp+80h+var_90], rax
0x18006d9c7  mov     eax, [rsp+180h+var_148]
0x18006d9cb  mov     [rbp+80h+var_88], eax
0x18006d9ce  lea     rax, [rsp+180h+var_140]
0x18006d9d3  mov     [rbp+80h+var_80], rax
0x18006d9d7  lea     rax, [rsp+180h+var_110]
0x18006d9dc  mov     [rsp+180h+UserData], rax; UserData
0x18006d9e1  mov     qword ptr [rsp+180h+var_110.Size], 2
0x18006d9ea  mov     [rbp+80h+var_F4], r15d
0x18006d9ee  mov     [rbp+80h+var_E8], 2
0x18006d9f6  mov     [rbp+80h+var_D4], r15d
0x18006d9fa  mov     [rbp+80h+var_C8], 10h
0x18006da02  mov     [rbp+80h+var_B8], 4
0x18006da0a  mov     [rbp+80h+var_A8], 4
0x18006da12  mov     [rbp+80h+var_98], 4
0x18006da1a  mov     [rbp+80h+var_84], r15d
0x18006da1e  mov     [rbp+80h+var_78], 4
0x18006da26  call    cs:__imp_EtwWrite
0x18006da2d  nop     dword ptr [rax+rax+00h]
0x18006da32  mov     ebx, eax
0x18006da34  test    eax, eax
0x18006da36  js      short loc_18006DA4E
0x18006da38  lea     rax, CiPolicyRefreshActivatePolicySucceded
0x18006da3f  cmp     r14, rax
0x18006da42  jnz     short loc_18006DA4E
0x18006da44  mov     rcx, rdi
0x18006da47  call    CipLogSIPolicySigner
0x18006da4c  mov     ebx, eax
0x18006da4e  lea     rcx, [rsp+180h+UnicodeString]; UnicodeString
0x18006da53  call    cs:__imp_RtlFreeUnicodeString
0x18006da5a  nop     dword ptr [rax+rax+00h]
0x18006da5f  lea     rcx, [rsp+180h+var_120]; UnicodeString
0x18006da64  call    cs:__imp_RtlFreeUnicodeString
0x18006da6b  nop     dword ptr [rax+rax+00h]
0x18006da70  mov     eax, ebx
0x18006da72  mov     rcx, [rbp+80h+var_30]
0x18006da76  xor     rcx, rsp; StackCookie
0x18006da79  call    __security_check_cookie
0x18006da7e  mov     rbx, [rsp+180h+arg_8]
0x18006da86  add     rsp, 160h
0x18006da8d  pop     r15
0x18006da8f  pop     r14
0x18006da91  pop     rdi
0x18006da92  pop     rsi
0x18006da93  pop     rbp
0x18006da94  retn
```
