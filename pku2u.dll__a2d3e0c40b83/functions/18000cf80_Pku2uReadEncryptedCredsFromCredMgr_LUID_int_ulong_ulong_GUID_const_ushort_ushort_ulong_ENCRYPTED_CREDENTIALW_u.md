# Pku2uReadEncryptedCredsFromCredMgr(_LUID *,int,ulong *,ulong,_GUID const &,ushort *,ushort *,ulong *,_ENCRYPTED_CREDENTIALW * * *,ulong *,uchar * *)

- ea: `0x18000cf80`
- end: `0x18000d159`
- name: `?Pku2uReadEncryptedCredsFromCredMgr@@YAJPEAU_LUID@@HPEAKKAEBU_GUID@@PEAG31PEAPEAPEAU_ENCRYPTED_CREDENTIALW@@1PEAPEAE@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct _LUID *, int, unsigned int *, unsigned int, const struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned int *, struct _ENCRYPTED_CREDENTIALW ***, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b000`

## callees

- `0x18000cf80`
- `0x180023ce0`
- `0x18002b04c`
- `0x180046010`

## import_xrefs

- `SspiCli!CredMarshalTargetInfo` at `0x18000d0d2`
- `SspiCli!CredMarshalTargetInfo` at `0x18000d0d2`

## pseudocode

```c
__int64 __fastcall Pku2uReadEncryptedCredsFromCredMgr(
        struct _LUID *a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        const struct _GUID *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int *a8,
        struct _ENCRYPTED_CREDENTIALW ***a9,
        unsigned int *a10,
        unsigned __int8 **a11)
{
  int v11; // eax
  int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // edx
  int v16; // r8d
  unsigned int v18; // [rsp+40h] [rbp-59h] BYREF
  struct _ENCRYPTED_CREDENTIALW **v19; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v21; // [rsp+60h] [rbp-39h]
  __int128 v22; // [rsp+70h] [rbp-29h]
  const WCHAR *v23; // [rsp+80h] [rbp-19h]
  int v24; // [rsp+88h] [rbp-11h]
  int v25; // [rsp+8Ch] [rbp-Dh]
  unsigned int *v26; // [rsp+90h] [rbp-9h]

  *a8 = 0;
  *a9 = 0;
  v20[1] = 0;
  v21 = 0;
  v22 = 0;
  v19 = 0;
  v18 = 0;
  if ( a3 )
  {
    v23 = L"pku2u";
    v20[0] = a6;
    v25 = 2;
    v26 = a3;
    v24 = 1;
    if ( a7 )
    {
      v24 = 65;
      *((_QWORD *)&v22 + 1) = a7;
    }
    v11 = ((__int64 (__fastcall *)(struct _LUID *, __int64, _QWORD *, _QWORD, unsigned int *, struct _ENCRYPTED_CREDENTIALW ***))Pku2uGlobalLsaFunctions->DummyFunction2)(
            a1,
            1,
            v20,
            0,
            &v18,
            &v19);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v24 &= ~0x40u;
      *((_QWORD *)&v22 + 1) = 0;
      v12 = CredMarshalTargetInfo(v20, a11, a10);
      if ( v12 >= 0 )
      {
        *a8 = v18;
        *a9 = v19;
        return (unsigned int)v12;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, v12, (__int64)a6);
    }
    else
    {
      if ( v11 == -1073741275 || v11 == -1073741811 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_18;
        v14 = 84;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        v14 = 85;
      }
      WPP_SF_d(v13[2], v14, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, (unsigned int)v11);
    }
LABEL_18:
    if ( v19 )
      ((void (__fastcall *)(_QWORD))Pku2uGlobalLsaFunctions->DummyFunction3)(v18);
    return (unsigned int)v12;
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x18000cf80  push    rbp
0x18000cf82  push    rsi
0x18000cf83  push    rdi
0x18000cf84  push    r12
0x18000cf86  push    r13
0x18000cf88  push    r14
0x18000cf8a  push    r15
0x18000cf8c  lea     rbp, [rsp-7]
0x18000cf91  sub     rsp, 0A0h
0x18000cf98  mov     rsi, [rbp+37h+arg_38]
0x18000cf9c  xor     r13d, r13d
0x18000cf9f  mov     r14, [rbp+37h+arg_40]
0x18000cfa6  xorps   xmm0, xmm0
0x18000cfa9  mov     rdi, [rbp+37h+arg_28]
0x18000cfad  xorps   xmm1, xmm1
0x18000cfb0  mov     rax, [rbp+37h+arg_30]
0x18000cfb4  mov     r15, [rbp+37h+arg_48]
0x18000cfbb  mov     r12, [rbp+37h+arg_50]
0x18000cfc2  mov     [rsi], r13d
0x18000cfc5  mov     [r14], r13
0x18000cfc8  mov     [rbp+37h+var_78], r13
0x18000cfcc  movdqa  [rbp+37h+var_70], xmm0
0x18000cfd1  movdqa  [rbp+37h+var_60], xmm1
0x18000cfd6  mov     [rbp+37h+var_88], r13
0x18000cfda  mov     [rbp+37h+var_90], r13d
0x18000cfde  test    r8, r8
0x18000cfe1  jz      loc_18000D152
0x18000cfe7  mov     [rsp+0D0h+arg_8], rbx
0x18000cfef  lea     rdx, pszPackageName; "pku2u"
0x18000cff6  mov     [rbp+37h+var_50], rdx
0x18000cffa  mov     [rbp+37h+var_80], rdi
0x18000cffe  mov     [rbp+37h+var_44], 2
0x18000d005  mov     [rbp+37h+var_40], r8
0x18000d009  mov     [rbp+37h+var_48], 1
0x18000d010  test    rax, rax
0x18000d013  jz      short loc_18000D020
0x18000d015  mov     [rbp+37h+var_48], 41h ; 'A'
0x18000d01c  mov     qword ptr [rbp+37h+var_60+8], rax
0x18000d020  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18000d027  lea     rdx, [rbp+37h+var_88]
0x18000d02b  mov     [rsp+0D0h+var_A8], rdx
0x18000d030  lea     r8, [rbp+37h+var_80]
0x18000d034  lea     rdx, [rbp+37h+var_90]
0x18000d038  xor     r9d, r9d
0x18000d03b  mov     [rsp+0D0h+var_B0], rdx
0x18000d040  mov     edx, 1
0x18000d045  mov     rax, [rax+150h]
0x18000d04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d051  mov     ebx, eax
0x18000d053  test    eax, eax
0x18000d055  jns     short loc_18000D0C0
0x18000d057  cmp     eax, 0C0000225h
0x18000d05c  jz      short loc_18000D08D
0x18000d05e  cmp     eax, 0C000000Dh
0x18000d063  jz      short loc_18000D08D
0x18000d065  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d06c  lea     rax, WPP_GLOBAL_Control
0x18000d073  cmp     rcx, rax
0x18000d076  jz      loc_18000D108
0x18000d07c  test    byte ptr [rcx+1Ch], 1
0x18000d080  jz      loc_18000D108
0x18000d086  mov     edx, 55h ; 'U'
0x18000d08b  jmp     short loc_18000D0AB
0x18000d08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d094  lea     rax, WPP_GLOBAL_Control
0x18000d09b  cmp     rcx, rax
0x18000d09e  jz      short loc_18000D108
0x18000d0a0  test    byte ptr [rcx+1Ch], 2
0x18000d0a4  jz      short loc_18000D108
0x18000d0a6  mov     edx, 54h ; 'T'
0x18000d0ab  mov     rcx, [rcx+10h]
0x18000d0af  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18000d0b6  mov     r9d, ebx
0x18000d0b9  call    WPP_SF_d
0x18000d0be  jmp     short loc_18000D108
0x18000d0c0  and     [rbp+37h+var_48], 0FFFFFFBFh
0x18000d0c4  lea     rcx, [rbp+37h+var_80]
0x18000d0c8  mov     r8, r15
0x18000d0cb  mov     qword ptr [rbp+37h+var_60+8], r13
0x18000d0cf  mov     rdx, r12
0x18000d0d2  call    cs:__imp_CredMarshalTargetInfo
0x18000d0d8  mov     ebx, eax
0x18000d0da  test    eax, eax
0x18000d0dc  jns     short loc_18000D144
0x18000d0de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0e5  lea     rax, WPP_GLOBAL_Control
0x18000d0ec  cmp     rcx, rax
0x18000d0ef  jz      short loc_18000D108
0x18000d0f1  test    byte ptr [rcx+1Ch], 1
0x18000d0f5  jz      short loc_18000D108
0x18000d0f7  mov     rcx, [rcx+10h]
0x18000d0fb  mov     r9d, ebx
0x18000d0fe  mov     [rsp+0D0h+var_B0], rdi
0x18000d103  call    WPP_SF_DS
0x18000d108  mov     rdx, [rbp+37h+var_88]
0x18000d10c  test    rdx, rdx
0x18000d10f  jz      short loc_18000D127
0x18000d111  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18000d118  mov     ecx, [rbp+37h+var_90]
0x18000d11b  mov     rax, [rax+158h]
0x18000d122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d127  mov     eax, ebx
0x18000d129  mov     rbx, [rsp+0D0h+arg_8]
0x18000d131  add     rsp, 0A0h
0x18000d138  pop     r15
0x18000d13a  pop     r14
0x18000d13c  pop     r13
0x18000d13e  pop     r12
0x18000d140  pop     rdi
0x18000d141  pop     rsi
0x18000d142  pop     rbp
0x18000d143  retn
0x18000d144  mov     eax, [rbp+37h+var_90]
0x18000d147  mov     [rsi], eax
0x18000d149  mov     rax, [rbp+37h+var_88]
0x18000d14d  mov     [r14], rax
0x18000d150  jmp     short loc_18000D127
0x18000d152  mov     eax, 0C00000E5h
0x18000d157  jmp     short loc_18000D131
```
