# BCryptDecapsulate

- ea: `0x180061e40`
- end: `0x180062075`
- name: `BCryptDecapsulate`
- size: `565`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18001155c`
- `0x18002eb64`
- `0x18003f910`
- `0x18004f2e0`
- `0x180061e40`
- `0x1800656bc`
- `0x18006a044`
- `0x1800a4260`
- `0x1800a4300`

## string_xrefs

- `0x180061ed8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180061f2a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptDecapsulate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6, int a7)
{
  unsigned int v8; // esi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdi
  unsigned int v14; // ebx
  __int64 v15; // rax
  bool v16; // zf
  __int64 v17; // r9
  __int64 v18; // rcx
  int v19; // eax
  char TrustedEnvironment; // al
  __int64 v21; // r10
  int v22; // r9d
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  char v28[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int64 *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  unsigned int *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  __int64 *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  char v37[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v38[16]; // [rsp+E0h] [rbp-20h] BYREF

  v8 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqDqDqD(*((_QWORD *)WPP_GLOBAL_Control + 3), a2, a3, a1, a2, a3, a4, a5, a6, a7);
  v11 = ValidateBaseKeyHandle(a1);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 0;
    v14 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7900);
    goto LABEL_13;
  }
  v15 = *(_QWORD *)(v11 + 8);
  v16 = *(_DWORD *)(v15 + 36) == 8;
  v24 = v15 + 444;
  if ( v16 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, __int64, int))(v15 + 112))(
            *(_QWORD *)(v12 + 16),
            a2,
            v8,
            a4,
            a5,
            a6,
            a7);
    v14 = v19;
    if ( v19 >= 0 )
    {
      v14 = 0;
      goto LABEL_12;
    }
    v17 = 7925;
    v18 = (unsigned int)v19;
  }
  else
  {
    v14 = -1073741637;
    v17 = 7910;
    v18 = 3221225659LL;
  }
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v17);
LABEL_12:
  v13 = v24;
LABEL_13:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && (unsigned int)dword_1800D15C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800D15C0, 0x400000000000LL) )
  {
    v26 = v21;
    v29 = &v26;
    v30 = (unsigned int)(v21 + 7);
    v31 = &v27;
    v27 = 0x1000000;
    v33 = &v25;
    v32 = v30;
    v35 = &v24;
    v25 = v14;
    v34 = 4;
    LODWORD(v24) = v21;
    v36 = 4;
    tlgCreate1Sz_wchar_t(v37, g_processImageName);
    tlgCreate1Sz_wchar_t(v38, v13);
    tlgWriteAgg((unsigned int)&dword_1800D15C0, (unsigned int)byte_1800C90F3, 0, v22, (__int64)v28);
  }
  return v14;
}

```

## disassembly

```asm
0x180061e40  push    rbp
0x180061e42  push    rbx
0x180061e43  push    rsi
0x180061e44  push    rdi
0x180061e45  push    r12
0x180061e47  push    r13
0x180061e49  push    r14
0x180061e4b  push    r15
0x180061e4d  lea     rbp, [rsp-8]
0x180061e52  sub     rsp, 108h
0x180061e59  mov     rax, cs:__security_cookie
0x180061e60  xor     rax, rsp
0x180061e63  mov     [rbp+40h+var_50], rax
0x180061e67  mov     r15, [rbp+40h+arg_28]
0x180061e6b  mov     r14, r9
0x180061e6e  mov     esi, r8d
0x180061e71  mov     rdi, rdx
0x180061e74  mov     rbx, rcx
0x180061e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180061e7e  lea     rax, WPP_GLOBAL_Control
0x180061e85  mov     r12d, [rbp+40h+arg_30]
0x180061e8c  mov     r13d, [rbp+40h+arg_20]
0x180061e90  cmp     rcx, rax
0x180061e93  jz      short loc_180061EC6
0x180061e95  mov     eax, [rcx+2Ch]
0x180061e98  test    al, 4
0x180061e9a  jz      short loc_180061EC6
0x180061e9c  mov     rcx, [rcx+18h]
0x180061ea0  mov     [rsp+140h+var_F8], r12d
0x180061ea5  mov     [rsp+140h+var_100], r15
0x180061eaa  mov     [rsp+140h+var_108], r13d
0x180061eaf  mov     [rsp+140h+var_110], r9
0x180061eb4  mov     r9, rbx
0x180061eb7  mov     dword ptr [rsp+140h+var_118], r8d
0x180061ebc  mov     [rsp+140h+var_120], rdx
0x180061ec1  call    WPP_SF_qqDqDqD
0x180061ec6  mov     rcx, rbx
0x180061ec9  call    ValidateBaseKeyHandle
0x180061ece  mov     rcx, rax
0x180061ed1  test    rax, rax
0x180061ed4  jnz     short loc_180061EFD
0x180061ed6  xor     edi, edi
0x180061ed8  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061edf  mov     r9d, 1EDCh
0x180061ee5  lea     rdx, aStatus; "Status"
0x180061eec  mov     ecx, 0C0000008h
0x180061ef1  mov     ebx, 0C0000008h
0x180061ef6  call    DebugTraceError
0x180061efb  jmp     short loc_180061F74
0x180061efd  mov     rax, [rax+8]
0x180061f01  cmp     dword ptr [rax+24h], 8
0x180061f05  lea     rdx, [rax+1BCh]
0x180061f0c  mov     [rsp+140h+var_F0], rdx
0x180061f11  jz      short loc_180061F38
0x180061f13  mov     ebx, 0C00000BBh
0x180061f18  mov     r9d, 1EE6h
0x180061f1e  mov     ecx, 0C00000BBh
0x180061f23  lea     rdx, aStatus; "Status"
0x180061f2a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061f31  call    DebugTraceError
0x180061f36  jmp     short loc_180061F6F
0x180061f38  mov     rax, [rax+70h]
0x180061f3c  mov     r9, r14
0x180061f3f  mov     rcx, [rcx+10h]
0x180061f43  mov     r8d, esi
0x180061f46  mov     dword ptr [rsp+140h+var_110], r12d
0x180061f4b  mov     rdx, rdi
0x180061f4e  mov     [rsp+140h+var_118], r15
0x180061f53  mov     dword ptr [rsp+140h+var_120], r13d
0x180061f58  call    _guard_dispatch_icall
0x180061f5d  mov     ebx, eax
0x180061f5f  test    eax, eax
0x180061f61  jns     short loc_180061F6D
0x180061f63  mov     r9d, 1EF5h
0x180061f69  mov     ecx, eax
0x180061f6b  jmp     short loc_180061F23
0x180061f6d  xor     ebx, ebx
0x180061f6f  mov     rdi, [rsp+140h+var_F0]
0x180061f74  mov     eax, cs:g_TrustedEnvironment
0x180061f7a  test    eax, eax
0x180061f7c  jnz     short loc_180061F83
0x180061f7e  call    GetTrustedEnvironment
0x180061f83  mov     r10d, 1
0x180061f89  test    r10b, al
0x180061f8c  jz      loc_180062052
0x180061f92  mov     eax, cs:dword_1800D15C0
0x180061f98  cmp     eax, 5
0x180061f9b  jbe     loc_180062052
0x180061fa1  mov     rdx, 400000000000h
0x180061fab  lea     rcx, dword_1800D15C0
0x180061fb2  call    _tlgKeywordOn
0x180061fb7  test    al, al
0x180061fb9  jz      loc_180062052
0x180061fbf  lea     rax, [rsp+140h+var_E0]
0x180061fc4  mov     [rsp+140h+var_E0], r10
0x180061fc9  mov     [rbp+40h+var_B0], rax
0x180061fcd  lea     r9d, [r10+7]
0x180061fd1  lea     rax, [rsp+140h+var_D8]
0x180061fd6  mov     [rbp+40h+var_A8], r9
0x180061fda  mov     [rbp+40h+var_A0], rax
0x180061fde  lea     rdx, g_processImageName; "UNKNOWN"
0x180061fe5  lea     rax, [rsp+140h+var_E8]
0x180061fea  mov     [rsp+140h+var_D8], 1000000h
0x180061ff3  mov     [rbp+40h+var_90], rax
0x180061ff7  lea     rcx, [rbp+40h+var_70]
0x180061ffb  lea     rax, [rsp+140h+var_F0]
0x180062000  mov     [rbp+40h+var_98], r9
0x180062004  mov     [rbp+40h+var_80], rax
0x180062008  mov     [rsp+140h+var_E8], ebx
0x18006200c  mov     [rbp+40h+var_88], 4
0x180062014  mov     dword ptr [rsp+140h+var_F0], r10d
0x180062019  mov     [rbp+40h+var_78], 4
0x180062021  call    _tlgCreate1Sz_wchar_t
0x180062026  mov     rdx, rdi
0x180062029  lea     rcx, [rbp+40h+var_60]
0x18006202d  call    _tlgCreate1Sz_wchar_t
0x180062032  lea     r10, [rsp+140h+var_D0]
0x180062037  xor     r8d, r8d
0x18006203a  lea     rdx, byte_1800C90F3
0x180062041  mov     [rsp+140h+var_120], r10
0x180062046  lea     rcx, dword_1800D15C0
0x18006204d  call    _tlgWriteAgg
0x180062052  mov     eax, ebx
0x180062054  mov     rcx, [rbp+40h+var_50]
0x180062058  xor     rcx, rsp; StackCookie
0x18006205b  call    __security_check_cookie
0x180062060  add     rsp, 108h
0x180062067  pop     r15
0x180062069  pop     r14
0x18006206b  pop     r13
0x18006206d  pop     r12
0x18006206f  pop     rdi
0x180062070  pop     rsi
0x180062071  pop     rbx
0x180062072  pop     rbp
0x180062073  retn
```
