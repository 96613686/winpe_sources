# CiRevalidateImage

- ea: `0x1800a9740`
- end: `0x1800a9a3c`
- name: `CiRevalidateImage`
- size: `764`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PFILE_OBJECT FileObject)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ead4`
- `0x180010094`
- `0x18002bf20`
- `0x18006c054`
- `0x1800712d4`
- `0x18009e7a8`
- `0x1800a9740`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1800a981f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800a981f`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800a982e`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800a982e`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a9874`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a9874`
- `ntoskrnl!MmIsKernelAddress` at `0x1800a97c5`
- `ntoskrnl!MmIsKernelAddress` at `0x1800a97c5`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800a98b4`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800a98b4`

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
0x1800a9740  push    rbp
0x1800a9742  push    rbx
0x1800a9743  push    rsi
0x1800a9744  push    rdi
0x1800a9745  push    r12
0x1800a9747  push    r13
0x1800a9749  push    r14
0x1800a974b  push    r15
0x1800a974d  lea     rbp, [rsp-7]
0x1800a9752  sub     rsp, 0E8h
0x1800a9759  mov     rax, cs:__security_cookie
0x1800a9760  xor     rax, rsp
0x1800a9763  mov     [rbp+3Fh+var_50], rax
0x1800a9767  mov     rdi, [rbp+3Fh+arg_20]
0x1800a976b  xor     esi, esi
0x1800a976d  mov     r15, [rbp+3Fh+arg_28]
0x1800a9771  xor     eax, eax
0x1800a9773  mov     r12, [rbp+3Fh+FileObject]
0x1800a9777  xorps   xmm0, xmm0
0x1800a977a  mov     dword ptr [rbp+3Fh+var_90+4], esi
0x1800a977d  mov     ebx, r9d
0x1800a9780  mov     dword ptr [rbp+3Fh+var_88+4], esi
0x1800a9783  mov     r13d, ecx
0x1800a9786  mov     byte ptr [rbp+3Fh+var_90], sil
0x1800a978a  mov     dword ptr [rbp+3Fh+var_88], esi
0x1800a978d  mov     [rbp+3Fh+var_58], rax
0x1800a9791  mov     [rbp+3Fh+var_80], rsi
0x1800a9795  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x1800a9799  movups  [rbp+3Fh+var_68], xmm0
0x1800a979d  test    cl, 5
0x1800a97a0  jnz     loc_1800A9930
0x1800a97a6  test    r13b, 0Ah
0x1800a97aa  jnz     loc_1800A9847
0x1800a97b0  cmp     dl, 5
0x1800a97b3  jz      loc_1800A9847
0x1800a97b9  movzx   r14d, sil
0x1800a97bd  test    rdi, rdi
0x1800a97c0  jz      short loc_1800A97D9
0x1800a97c2  mov     rcx, rdi
0x1800a97c5  call    cs:__imp_MmIsKernelAddress
0x1800a97cc  nop     dword ptr [rax+rax+00h]
0x1800a97d1  test    al, al
0x1800a97d3  jz      loc_1800A986D
0x1800a97d9  mov     esi, r13d
0x1800a97dc  and     esi, 10h
0x1800a97df  jz      short loc_1800A981F
0x1800a97e1  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800a97e6  xor     r14d, r14d
0x1800a97e9  test    eax, eax
0x1800a97eb  jnz     loc_1800A9889
0x1800a97f1  mov     eax, cs:g_CiPolicyState
0x1800a97f7  test    al, 2
0x1800a97f9  jz      short loc_1800A980B
0x1800a97fb  test    al, 40h
0x1800a97fd  jnz     short loc_1800A9847
0x1800a97ff  mov     rcx, rdi
0x1800a9802  call    CipShouldRevalidateForPolicyChange
0x1800a9807  test    al, al
0x1800a9809  jnz     short loc_1800A9847
0x1800a980b  test    cs:g_CiPolicyState, 4000h
0x1800a9815  jnz     loc_1800A9969
0x1800a981b  xor     eax, eax
0x1800a981d  jmp     short loc_1800A984C
0x1800a981f  call    cs:__imp_PsGetCurrentProcess
0x1800a9826  nop     dword ptr [rax+rax+00h]
0x1800a982b  mov     rcx, rax
0x1800a982e  call    cs:__imp_PsIsProtectedProcessLight
0x1800a9835  nop     dword ptr [rax+rax+00h]
0x1800a983a  test    eax, eax
0x1800a983c  jz      short loc_1800A97E1
0x1800a983e  cmp     ebx, 7
0x1800a9841  jz      loc_1800A995B
0x1800a9847  mov     eax, 1
0x1800a984c  mov     rcx, [rbp+3Fh+var_50]
0x1800a9850  xor     rcx, rsp; StackCookie
0x1800a9853  call    __security_check_cookie
0x1800a9858  add     rsp, 0E8h
0x1800a985f  pop     r15
0x1800a9861  pop     r14
0x1800a9863  pop     r13
0x1800a9865  pop     r12
0x1800a9867  pop     rdi
0x1800a9868  pop     rsi
0x1800a9869  pop     rbx
0x1800a986a  pop     rbp
0x1800a986b  retn
0x1800a986d  bt      rdi, 3Bh ; ';'
0x1800a9872  jnb     short loc_1800A98D2
0x1800a9874  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800a987b  nop     dword ptr [rax+rax+00h]
0x1800a9880  test    al, al
0x1800a9882  jz      short loc_1800A9847
0x1800a9884  jmp     loc_1800A97D9
0x1800a9889  test    esi, esi
0x1800a988b  jz      loc_1800A97F1
0x1800a9891  mov     [rsp+120h+var_E8], r14
0x1800a9896  lea     rax, [rbp+3Fh+var_80]
0x1800a989a  mov     [rsp+120h+var_F0], rax
0x1800a989f  xor     r9d, r9d
0x1800a98a2  mov     [rsp+120h+var_F8], r14
0x1800a98a7  xor     r8d, r8d
0x1800a98aa  xor     edx, edx
0x1800a98ac  mov     [rsp+120h+var_100], r14
0x1800a98b1  mov     rcx, r15
0x1800a98b4  call    cs:__imp_RtlQueryPackageClaims
0x1800a98bb  nop     dword ptr [rax+rax+00h]
0x1800a98c0  test    dword ptr [rbp+3Fh+var_80], 200000h
0x1800a98c7  jnz     loc_1800A9847
0x1800a98cd  jmp     loc_1800A97F1
0x1800a98d2  bt      rdi, 3Ah ; ':'
0x1800a98d7  mov     r8d, 1
0x1800a98dd  cmovnb  r14d, r8d
0x1800a98e1  jmp     loc_1800A97D9
0x1800a98e6  movzx   ecx, r8b
0x1800a98ea  mov     edx, 1
0x1800a98ef  and     ecx, 0Fh
0x1800a98f2  shl     edx, cl
0x1800a98f4  mov     rcx, cs:g_CipWhichLevelComparisons
0x1800a98fb  test    [rcx+20h], edx
0x1800a98fe  jz      loc_1800A9847
0x1800a9904  mov     eax, cs:g_CiPolicyState
0x1800a990a  mov     r8d, 1
0x1800a9910  test    r8b, al
0x1800a9913  jnz     short loc_1800A9925
0x1800a9915  mov     rcx, rdi
0x1800a9918  call    CipShouldRevalidateForPolicyChange
0x1800a991d  movzx   eax, al
0x1800a9920  jmp     loc_1800A984C
0x1800a9925  test    [rcx+30h], edx
0x1800a9928  jz      loc_1800A9847
0x1800a992e  jmp     short loc_1800A9915
0x1800a9930  test    ebx, ebx
0x1800a9932  jz      loc_1800A9847
0x1800a9938  sub     ebx, 1
0x1800a993b  jz      short loc_1800A98E6
0x1800a993d  sub     ebx, 1
0x1800a9940  jz      loc_1800A9847
0x1800a9946  sub     ebx, 1
0x1800a9949  jz      short loc_1800A98E6
0x1800a994b  sub     ebx, 1
0x1800a994e  jz      short loc_1800A98E6
0x1800a9950  sub     ebx, 1
0x1800a9953  jnz     loc_1800A9847
0x1800a9959  jmp     short loc_1800A98E6
0x1800a995b  test    r14b, r14b
0x1800a995e  jnz     loc_1800A9847
0x1800a9964  jmp     loc_1800A97E1
0x1800a9969  test    esi, esi
0x1800a996b  jz      loc_1800A981B
0x1800a9971  test    r15, r15
0x1800a9974  jz      short loc_1800A9986
0x1800a9976  mov     rcx, r15
0x1800a9979  call    CipSmartlockerHasDangerousOrInstallerExtension
0x1800a997e  test    eax, eax
0x1800a9980  jnz     loc_1800A9847
0x1800a9986  test    r12, r12
0x1800a9989  jz      loc_1800A981B
0x1800a998f  lea     rax, [rbp+3Fh+var_78]
0x1800a9993  mov     r8d, r13d
0x1800a9996  mov     [rsp+120h+var_A0], rax; __int64
0x1800a999e  lea     r9, [rbp+3Fh+var_90+4]
0x1800a99a2  lea     rax, [rbp+3Fh+var_88]
0x1800a99a6  xor     edx, edx
0x1800a99a8  mov     [rsp+120h+var_A8], rax; __int64
0x1800a99ad  mov     rcx, r12; FileObject
0x1800a99b0  mov     [rsp+120h+var_B0], r14; __int64
0x1800a99b5  lea     rax, [rbp+3Fh+var_90]
0x1800a99b9  mov     [rsp+120h+var_B8], r14; __int64
0x1800a99be  mov     [rsp+120h+var_C0], r14; __int64
0x1800a99c3  mov     [rsp+120h+var_C8], r15; __int64
0x1800a99c8  mov     [rsp+120h+var_D0], r14; __int64
0x1800a99cd  mov     [rsp+120h+var_D8], r14; __int64
0x1800a99d2  mov     [rsp+120h+var_E0], r14; __int64
0x1800a99d7  mov     [rsp+120h+var_E8], r14; __int64
0x1800a99dc  mov     [rsp+120h+var_F0], r14; __int64
0x1800a99e1  mov     [rsp+120h+var_F8], rax; __int64
0x1800a99e6  lea     rax, [rbp+3Fh+var_88+4]
0x1800a99ea  mov     [rsp+120h+var_100], rax; __int64
0x1800a99ef  call    CipGetFileCache
0x1800a99f4  cmp     eax, 0C0000225h
0x1800a99f9  jnz     short loc_1800A9A14
0x1800a99fb  cmp     dword ptr [rbp+3Fh+var_90+4], 0Fh
0x1800a99ff  jz      loc_1800A9847
0x1800a9a05  cmp     dword ptr [rbp+3Fh+var_90+4], 4
0x1800a9a09  jle     loc_1800A9847
0x1800a9a0f  jmp     loc_1800A981B
0x1800a9a14  test    eax, eax
0x1800a9a16  js      loc_1800A981B
0x1800a9a1c  mov     edx, dword ptr [rbp+3Fh+var_88]
0x1800a9a1f  test    edx, edx
0x1800a9a21  jns     loc_1800A981B
0x1800a9a27  mov     r9d, dword ptr [rbp+3Fh+var_78+4]
0x1800a9a2b  lea     r8, [rbp+3Fh+var_78+8]
0x1800a9a2f  mov     rcx, r12
0x1800a9a32  call    CiInstrumentSmartAppControlNoReEvaluation
0x1800a9a37  jmp     loc_1800A981B
```
