# CiRevalidateImage

- ea: `0x1800a8a90`
- end: `0x1800a8d8c`
- name: `CiRevalidateImage`
- size: `764`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PFILE_OBJECT FileObject)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000eae4`
- `0x1800100a4`
- `0x18002c0d0`
- `0x18006c1c4`
- `0x1800715b4`
- `0x18008fa34`
- `0x1800a8a90`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1800a8b6f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800a8b6f`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800a8b7e`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800a8b7e`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a8bc4`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a8bc4`
- `ntoskrnl!MmIsKernelAddress` at `0x1800a8b15`
- `ntoskrnl!MmIsKernelAddress` at `0x1800a8b15`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800a8c04`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800a8c04`

## pseudocode

```c
__int64 __fastcall CiRevalidateImage(
        unsigned int a1,
        char a2,
        char a3,
        int a4,
        __int64 a5,
        __int64 a6,
        PFILE_OBJECT FileObject)
{
  bool v9; // r14
  __int64 CurrentProcess; // rax
  int v12; // edx
  int FileCache; // eax
  char v14; // [rsp+90h] [rbp-51h] BYREF
  int v15; // [rsp+94h] [rbp-4Dh] BYREF
  __int64 v16; // [rsp+98h] [rbp-49h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v18[2]; // [rsp+A8h] [rbp-39h] BYREF
  __int128 v19; // [rsp+B8h] [rbp-29h]
  __int64 v20; // [rsp+C8h] [rbp-19h]

  v15 = 0;
  v14 = 0;
  v16 = 0;
  v20 = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  if ( (a1 & 5) == 0 )
  {
    if ( (a1 & 0xA) == 0 && a2 != 5 )
    {
      v9 = 0;
      if ( !a5 || (unsigned __int8)MmIsKernelAddress(a5) )
      {
LABEL_6:
        if ( (a1 & 0x10) != 0
          || (CurrentProcess = PsGetCurrentProcess(), !(unsigned int)PsIsProtectedProcessLight(CurrentProcess))
          || a4 == 7 && !v9 )
        {
          if ( !(unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline()
            || (a1 & 0x10) == 0
            || (RtlQueryPackageClaims(a6, 0, 0, 0, 0, 0, &v17, 0), (v17 & 0x200000) == 0) )
          {
            if ( (g_CiPolicyState & 2) == 0
              || (g_CiPolicyState & 0x40) == 0 && !(unsigned __int8)CipShouldRevalidateForPolicyChange(a5) )
            {
              if ( (g_CiPolicyState & 0x4000) == 0 || (a1 & 0x10) == 0 )
                return 0;
              if ( !a6 || !(unsigned int)CipSmartlockerHasDangerousOrInstallerExtension(a6) )
              {
                if ( !FileObject )
                  return 0;
                FileCache = CipGetFileCache(
                              FileObject,
                              0,
                              a1,
                              &v15,
                              (int *)&v16 + 1,
                              &v14,
                              0,
                              0,
                              0,
                              0,
                              0,
                              a6,
                              0,
                              0,
                              0,
                              &v16,
                              (__int64)v18);
                if ( FileCache != -1073741275 )
                {
                  if ( FileCache >= 0 && (int)v16 < 0 )
                    CiInstrumentSmartAppControlNoReEvaluation(FileObject, (unsigned int)v16, &v18[1], HIDWORD(v18[0]));
                  return 0;
                }
                if ( v15 != 15 && v15 > 4 )
                  return 0;
              }
            }
          }
        }
        return 1;
      }
      if ( (a5 & 0x800000000000000LL) == 0 )
      {
        v9 = (a5 & 0x400000000000000LL) == 0;
        goto LABEL_6;
      }
      if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
        goto LABEL_6;
    }
    return 1;
  }
  if ( !a4 || a4 != 1 && (a4 == 2 || a4 != 3 && (unsigned int)(a4 - 4) > 1) )
    return 1;
  v12 = 1 << (a3 & 0xF);
  if ( (v12 & (_DWORD)g_CipWhichLevelComparisons[2]) == 0
    || (g_CiPolicyState & 1) != 0 && (v12 & (_DWORD)g_CipWhichLevelComparisons[3]) == 0 )
  {
    return 1;
  }
  return (unsigned __int8)CipShouldRevalidateForPolicyChange(a5);
}

```

## disassembly

```asm
0x1800a8a90  push    rbp
0x1800a8a92  push    rbx
0x1800a8a93  push    rsi
0x1800a8a94  push    rdi
0x1800a8a95  push    r12
0x1800a8a97  push    r13
0x1800a8a99  push    r14
0x1800a8a9b  push    r15
0x1800a8a9d  lea     rbp, [rsp-7]
0x1800a8aa2  sub     rsp, 0E8h
0x1800a8aa9  mov     rax, cs:__security_cookie
0x1800a8ab0  xor     rax, rsp
0x1800a8ab3  mov     [rbp+3Fh+var_50], rax
0x1800a8ab7  mov     rdi, [rbp+3Fh+arg_20]
0x1800a8abb  xor     esi, esi
0x1800a8abd  mov     r15, [rbp+3Fh+arg_28]
0x1800a8ac1  xor     eax, eax
0x1800a8ac3  mov     r12, [rbp+3Fh+FileObject]
0x1800a8ac7  xorps   xmm0, xmm0
0x1800a8aca  mov     dword ptr [rbp+3Fh+var_90+4], esi
0x1800a8acd  mov     ebx, r9d
0x1800a8ad0  mov     dword ptr [rbp+3Fh+var_88+4], esi
0x1800a8ad3  mov     r13d, ecx
0x1800a8ad6  mov     byte ptr [rbp+3Fh+var_90], sil
0x1800a8ada  mov     dword ptr [rbp+3Fh+var_88], esi
0x1800a8add  mov     [rbp+3Fh+var_58], rax
0x1800a8ae1  mov     [rbp+3Fh+var_80], rsi
0x1800a8ae5  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x1800a8ae9  movups  [rbp+3Fh+var_68], xmm0
0x1800a8aed  test    cl, 5
0x1800a8af0  jnz     loc_1800A8C80
0x1800a8af6  test    r13b, 0Ah
0x1800a8afa  jnz     loc_1800A8B97
0x1800a8b00  cmp     dl, 5
0x1800a8b03  jz      loc_1800A8B97
0x1800a8b09  movzx   r14d, sil
0x1800a8b0d  test    rdi, rdi
0x1800a8b10  jz      short loc_1800A8B29
0x1800a8b12  mov     rcx, rdi
0x1800a8b15  call    cs:__imp_MmIsKernelAddress
0x1800a8b1c  nop     dword ptr [rax+rax+00h]
0x1800a8b21  test    al, al
0x1800a8b23  jz      loc_1800A8BBD
0x1800a8b29  mov     esi, r13d
0x1800a8b2c  and     esi, 10h
0x1800a8b2f  jz      short loc_1800A8B6F
0x1800a8b31  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800a8b36  xor     r14d, r14d
0x1800a8b39  test    eax, eax
0x1800a8b3b  jnz     loc_1800A8BD9
0x1800a8b41  mov     eax, cs:g_CiPolicyState
0x1800a8b47  test    al, 2
0x1800a8b49  jz      short loc_1800A8B5B
0x1800a8b4b  test    al, 40h
0x1800a8b4d  jnz     short loc_1800A8B97
0x1800a8b4f  mov     rcx, rdi
0x1800a8b52  call    CipShouldRevalidateForPolicyChange
0x1800a8b57  test    al, al
0x1800a8b59  jnz     short loc_1800A8B97
0x1800a8b5b  test    cs:g_CiPolicyState, 4000h
0x1800a8b65  jnz     loc_1800A8CB9
0x1800a8b6b  xor     eax, eax
0x1800a8b6d  jmp     short loc_1800A8B9C
0x1800a8b6f  call    cs:__imp_PsGetCurrentProcess
0x1800a8b76  nop     dword ptr [rax+rax+00h]
0x1800a8b7b  mov     rcx, rax
0x1800a8b7e  call    cs:__imp_PsIsProtectedProcessLight
0x1800a8b85  nop     dword ptr [rax+rax+00h]
0x1800a8b8a  test    eax, eax
0x1800a8b8c  jz      short loc_1800A8B31
0x1800a8b8e  cmp     ebx, 7
0x1800a8b91  jz      loc_1800A8CAB
0x1800a8b97  mov     eax, 1
0x1800a8b9c  mov     rcx, [rbp+3Fh+var_50]
0x1800a8ba0  xor     rcx, rsp; StackCookie
0x1800a8ba3  call    __security_check_cookie
0x1800a8ba8  add     rsp, 0E8h
0x1800a8baf  pop     r15
0x1800a8bb1  pop     r14
0x1800a8bb3  pop     r13
0x1800a8bb5  pop     r12
0x1800a8bb7  pop     rdi
0x1800a8bb8  pop     rsi
0x1800a8bb9  pop     rbx
0x1800a8bba  pop     rbp
0x1800a8bbb  retn
0x1800a8bbd  bt      rdi, 3Bh ; ';'
0x1800a8bc2  jnb     short loc_1800A8C22
0x1800a8bc4  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800a8bcb  nop     dword ptr [rax+rax+00h]
0x1800a8bd0  test    al, al
0x1800a8bd2  jz      short loc_1800A8B97
0x1800a8bd4  jmp     loc_1800A8B29
0x1800a8bd9  test    esi, esi
0x1800a8bdb  jz      loc_1800A8B41
0x1800a8be1  mov     [rsp+120h+var_E8], r14
0x1800a8be6  lea     rax, [rbp+3Fh+var_80]
0x1800a8bea  mov     [rsp+120h+var_F0], rax
0x1800a8bef  xor     r9d, r9d
0x1800a8bf2  mov     [rsp+120h+var_F8], r14
0x1800a8bf7  xor     r8d, r8d
0x1800a8bfa  xor     edx, edx
0x1800a8bfc  mov     [rsp+120h+var_100], r14
0x1800a8c01  mov     rcx, r15
0x1800a8c04  call    cs:__imp_RtlQueryPackageClaims
0x1800a8c0b  nop     dword ptr [rax+rax+00h]
0x1800a8c10  test    dword ptr [rbp+3Fh+var_80], 200000h
0x1800a8c17  jnz     loc_1800A8B97
0x1800a8c1d  jmp     loc_1800A8B41
0x1800a8c22  bt      rdi, 3Ah ; ':'
0x1800a8c27  mov     r8d, 1
0x1800a8c2d  cmovnb  r14d, r8d
0x1800a8c31  jmp     loc_1800A8B29
0x1800a8c36  movzx   ecx, r8b
0x1800a8c3a  mov     edx, 1
0x1800a8c3f  and     ecx, 0Fh
0x1800a8c42  shl     edx, cl
0x1800a8c44  mov     rcx, cs:g_CipWhichLevelComparisons
0x1800a8c4b  test    [rcx+20h], edx
0x1800a8c4e  jz      loc_1800A8B97
0x1800a8c54  mov     eax, cs:g_CiPolicyState
0x1800a8c5a  mov     r8d, 1
0x1800a8c60  test    r8b, al
0x1800a8c63  jnz     short loc_1800A8C75
0x1800a8c65  mov     rcx, rdi
0x1800a8c68  call    CipShouldRevalidateForPolicyChange
0x1800a8c6d  movzx   eax, al
0x1800a8c70  jmp     loc_1800A8B9C
0x1800a8c75  test    [rcx+30h], edx
0x1800a8c78  jz      loc_1800A8B97
0x1800a8c7e  jmp     short loc_1800A8C65
0x1800a8c80  test    ebx, ebx
0x1800a8c82  jz      loc_1800A8B97
0x1800a8c88  sub     ebx, 1
0x1800a8c8b  jz      short loc_1800A8C36
0x1800a8c8d  sub     ebx, 1
0x1800a8c90  jz      loc_1800A8B97
0x1800a8c96  sub     ebx, 1
0x1800a8c99  jz      short loc_1800A8C36
0x1800a8c9b  sub     ebx, 1
0x1800a8c9e  jz      short loc_1800A8C36
0x1800a8ca0  sub     ebx, 1
0x1800a8ca3  jnz     loc_1800A8B97
0x1800a8ca9  jmp     short loc_1800A8C36
0x1800a8cab  test    r14b, r14b
0x1800a8cae  jnz     loc_1800A8B97
0x1800a8cb4  jmp     loc_1800A8B31
0x1800a8cb9  test    esi, esi
0x1800a8cbb  jz      loc_1800A8B6B
0x1800a8cc1  test    r15, r15
0x1800a8cc4  jz      short loc_1800A8CD6
0x1800a8cc6  mov     rcx, r15
0x1800a8cc9  call    CipSmartlockerHasDangerousOrInstallerExtension
0x1800a8cce  test    eax, eax
0x1800a8cd0  jnz     loc_1800A8B97
0x1800a8cd6  test    r12, r12
0x1800a8cd9  jz      loc_1800A8B6B
0x1800a8cdf  lea     rax, [rbp+3Fh+var_78]
0x1800a8ce3  mov     r8d, r13d
0x1800a8ce6  mov     [rsp+120h+var_A0], rax; __int64
0x1800a8cee  lea     r9, [rbp+3Fh+var_90+4]
0x1800a8cf2  lea     rax, [rbp+3Fh+var_88]
0x1800a8cf6  xor     edx, edx
0x1800a8cf8  mov     [rsp+120h+var_A8], rax; __int64
0x1800a8cfd  mov     rcx, r12; FileObject
0x1800a8d00  mov     [rsp+120h+var_B0], r14; __int64
0x1800a8d05  lea     rax, [rbp+3Fh+var_90]
0x1800a8d09  mov     [rsp+120h+var_B8], r14; __int64
0x1800a8d0e  mov     [rsp+120h+var_C0], r14; __int64
0x1800a8d13  mov     [rsp+120h+var_C8], r15; __int64
0x1800a8d18  mov     [rsp+120h+var_D0], r14; __int64
0x1800a8d1d  mov     [rsp+120h+var_D8], r14; __int64
0x1800a8d22  mov     [rsp+120h+var_E0], r14; __int64
0x1800a8d27  mov     [rsp+120h+var_E8], r14; __int64
0x1800a8d2c  mov     [rsp+120h+var_F0], r14; __int64
0x1800a8d31  mov     [rsp+120h+var_F8], rax; __int64
0x1800a8d36  lea     rax, [rbp+3Fh+var_88+4]
0x1800a8d3a  mov     [rsp+120h+var_100], rax; __int64
0x1800a8d3f  call    CipGetFileCache
0x1800a8d44  cmp     eax, 0C0000225h
0x1800a8d49  jnz     short loc_1800A8D64
0x1800a8d4b  cmp     dword ptr [rbp+3Fh+var_90+4], 0Fh
0x1800a8d4f  jz      loc_1800A8B97
0x1800a8d55  cmp     dword ptr [rbp+3Fh+var_90+4], 4
0x1800a8d59  jle     loc_1800A8B97
0x1800a8d5f  jmp     loc_1800A8B6B
0x1800a8d64  test    eax, eax
0x1800a8d66  js      loc_1800A8B6B
0x1800a8d6c  mov     edx, dword ptr [rbp+3Fh+var_88]
0x1800a8d6f  test    edx, edx
0x1800a8d71  jns     loc_1800A8B6B
0x1800a8d77  mov     r9d, dword ptr [rbp+3Fh+var_78+4]
0x1800a8d7b  lea     r8, [rbp+3Fh+var_78+8]
0x1800a8d7f  mov     rcx, r12
0x1800a8d82  call    CiInstrumentSmartAppControlNoReEvaluation
0x1800a8d87  jmp     loc_1800A8B6B
```
