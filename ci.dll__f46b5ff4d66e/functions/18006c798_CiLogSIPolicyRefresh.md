# CiLogSIPolicyRefresh

- ea: `0x18006c798`
- end: `0x18006c9e2`
- name: `CiLogSIPolicyRefresh`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180057408`
- `0x18006cb40`
- `0x1800e4cb8`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x18006c798`
- `0x18006dc18`
- `0x18006dc80`
- `0x18007ba9c`
- `0x18009f370`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006c99f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006c9b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006c99f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006c9b0`
- `ntoskrnl!EtwEventEnabled` at `0x18006c815`
- `ntoskrnl!EtwEventEnabled` at `0x18006c815`
- `ntoskrnl!EtwWrite` at `0x18006c972`
- `ntoskrnl!EtwWrite` at `0x18006c972`

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
0x18006c798  mov     [rsp-8+arg_8], rbx
0x18006c79d  push    rbp
0x18006c79e  push    rsi
0x18006c79f  push    rdi
0x18006c7a0  push    r14
0x18006c7a2  push    r15
0x18006c7a4  lea     rbp, [rsp-60h]
0x18006c7a9  sub     rsp, 160h
0x18006c7b0  mov     rax, cs:__security_cookie
0x18006c7b7  xor     rax, rsp
0x18006c7ba  mov     [rbp+80h+var_30], rax
0x18006c7be  xor     r15d, r15d
0x18006c7c1  mov     r14, r8
0x18006c7c4  mov     rdi, rcx
0x18006c7c7  mov     [rsp+180h+var_138], r15d
0x18006c7cc  xor     edx, edx; Val
0x18006c7ce  lea     rcx, [rbp+80h+var_70]; void *
0x18006c7d2  lea     ebx, [r15+40h]
0x18006c7d6  mov     r8d, ebx; Size
0x18006c7d9  call    memset
0x18006c7de  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c7e5  xorps   xmm0, xmm0
0x18006c7e8  xorps   xmm1, xmm1
0x18006c7eb  mov     [rsp+180h+var_148], ebx
0x18006c7ef  mov     rdx, r14; EventDescriptor
0x18006c7f2  mov     [rsp+180h+var_14C], r15w
0x18006c7f8  movups  xmmword ptr [rsp+180h+UnicodeString.Length], xmm0
0x18006c7fd  mov     [rsp+180h+var_150], r15w
0x18006c803  mov     ebx, r15d
0x18006c806  movups  xmmword ptr [rsp+180h+var_120.Length], xmm1
0x18006c80b  mov     [rsp+180h+var_144], r15d
0x18006c810  mov     [rsp+180h+var_140], r15d
0x18006c815  call    cs:__imp_EtwEventEnabled
0x18006c81c  nop     dword ptr [rax+rax+00h]
0x18006c821  test    al, al
0x18006c823  jz      loc_18006C99A
0x18006c829  cmp     dword ptr [rdi+28h], 6
0x18006c82d  lea     r9, [rsp+180h+var_148]
0x18006c832  lea     r8, [rbp+80h+var_70]
0x18006c836  mov     rcx, rdi
0x18006c839  sbb     rsi, rsi
0x18006c83c  and     rsi, 0FFFFFFFFFFFFFD50h
0x18006c843  add     rsi, 2C0h
0x18006c84a  call    CipGetPolicyHash
0x18006c84f  mov     ebx, eax
0x18006c851  test    eax, eax
0x18006c853  js      loc_18006C99A
0x18006c859  lea     r8, [rsp+180h+UnicodeString]
0x18006c85e  mov     rcx, rdi
0x18006c861  lea     rdx, [rsp+180h+var_120]
0x18006c866  call    CiLogSIPolicyGetPolicyIDs
0x18006c86b  mov     ebx, eax
0x18006c86d  test    eax, eax
0x18006c86f  js      loc_18006C99A
0x18006c875  mov     eax, [rdi+2Ch]
0x18006c878  mov     rcx, rdi
0x18006c87b  mov     [rsp+180h+var_144], eax
0x18006c87f  call    SIPolicyGetPolicyOptionsV2
0x18006c884  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c88b  lea     r9d, [r15+0Ah]; UserDataCount
0x18006c88f  mov     [rsp+180h+var_140], eax
0x18006c893  xor     r8d, r8d; ActivityId
0x18006c896  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18006c89b  mov     rdx, r14; EventDescriptor
0x18006c89e  shr     ax, 1
0x18006c8a1  mov     [rsp+180h+var_150], ax
0x18006c8a6  lea     rax, [rsp+180h+var_150]
0x18006c8ab  mov     [rsp+180h+var_110.Ptr], rax
0x18006c8b0  mov     rax, [rsp+180h+UnicodeString.Buffer]
0x18006c8b5  mov     [rbp+80h+var_100], rax
0x18006c8b9  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18006c8be  mov     [rbp+80h+var_F8], eax
0x18006c8c1  movzx   eax, [rsp+180h+var_120.Length]
0x18006c8c6  shr     ax, 1
0x18006c8c9  mov     [rsp+180h+var_14C], ax
0x18006c8ce  lea     rax, [rsp+180h+var_14C]
0x18006c8d3  mov     [rbp+80h+var_F0], rax
0x18006c8d7  mov     rax, [rsp+180h+var_120.Buffer]
0x18006c8dc  mov     [rbp+80h+var_E0], rax
0x18006c8e0  movzx   eax, [rsp+180h+var_120.Length]
0x18006c8e5  mov     [rbp+80h+var_D8], eax
0x18006c8e8  lea     rax, [rsi+rdi]
0x18006c8ec  mov     [rbp+80h+var_D0], rax
0x18006c8f0  lea     rax, [rsp+180h+var_138]
0x18006c8f5  mov     [rbp+80h+var_C0], rax
0x18006c8f9  lea     rax, [rsp+180h+var_144]
0x18006c8fe  mov     [rbp+80h+var_B0], rax
0x18006c902  lea     rax, [rsp+180h+var_148]
0x18006c907  mov     [rbp+80h+var_A0], rax
0x18006c90b  lea     rax, [rbp+80h+var_70]
0x18006c90f  mov     [rbp+80h+var_90], rax
0x18006c913  mov     eax, [rsp+180h+var_148]
0x18006c917  mov     [rbp+80h+var_88], eax
0x18006c91a  lea     rax, [rsp+180h+var_140]
0x18006c91f  mov     [rbp+80h+var_80], rax
0x18006c923  lea     rax, [rsp+180h+var_110]
0x18006c928  mov     [rsp+180h+UserData], rax; UserData
0x18006c92d  mov     qword ptr [rsp+180h+var_110.Size], 2
0x18006c936  mov     [rbp+80h+var_F4], r15d
0x18006c93a  mov     [rbp+80h+var_E8], 2
0x18006c942  mov     [rbp+80h+var_D4], r15d
0x18006c946  mov     [rbp+80h+var_C8], 10h
0x18006c94e  mov     [rbp+80h+var_B8], 4
0x18006c956  mov     [rbp+80h+var_A8], 4
0x18006c95e  mov     [rbp+80h+var_98], 4
0x18006c966  mov     [rbp+80h+var_84], r15d
0x18006c96a  mov     [rbp+80h+var_78], 4
0x18006c972  call    cs:__imp_EtwWrite
0x18006c979  nop     dword ptr [rax+rax+00h]
0x18006c97e  mov     ebx, eax
0x18006c980  test    eax, eax
0x18006c982  js      short loc_18006C99A
0x18006c984  lea     rax, CiPolicyRefreshActivatePolicySucceded
0x18006c98b  cmp     r14, rax
0x18006c98e  jnz     short loc_18006C99A
0x18006c990  mov     rcx, rdi
0x18006c993  call    CipLogSIPolicySigner
0x18006c998  mov     ebx, eax
0x18006c99a  lea     rcx, [rsp+180h+UnicodeString]; UnicodeString
0x18006c99f  call    cs:__imp_RtlFreeUnicodeString
0x18006c9a6  nop     dword ptr [rax+rax+00h]
0x18006c9ab  lea     rcx, [rsp+180h+var_120]; UnicodeString
0x18006c9b0  call    cs:__imp_RtlFreeUnicodeString
0x18006c9b7  nop     dword ptr [rax+rax+00h]
0x18006c9bc  mov     eax, ebx
0x18006c9be  mov     rcx, [rbp+80h+var_30]
0x18006c9c2  xor     rcx, rsp; StackCookie
0x18006c9c5  call    __security_check_cookie
0x18006c9ca  mov     rbx, [rsp+180h+arg_8]
0x18006c9d2  add     rsp, 160h
0x18006c9d9  pop     r15
0x18006c9db  pop     r14
0x18006c9dd  pop     rdi
0x18006c9de  pop     rsi
0x18006c9df  pop     rbp
0x18006c9e0  retn
```
