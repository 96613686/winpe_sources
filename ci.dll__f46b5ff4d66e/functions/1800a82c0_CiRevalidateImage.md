# CiRevalidateImage

- ea: `0x1800a82c0`
- end: `0x1800a85bc`
- name: `CiRevalidateImage`
- size: `764`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PFILE_OBJECT FileObject)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ead4`
- `0x180010128`
- `0x18002bef0`
- `0x18006add4`
- `0x180070024`
- `0x18009d178`
- `0x1800a82c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1800a839f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800a839f`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800a83ae`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800a83ae`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a83f4`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a83f4`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800a8434`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800a8434`
- `ntoskrnl!MmIsKernelAddress` at `0x1800a8345`
- `ntoskrnl!MmIsKernelAddress` at `0x1800a8345`

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
0x1800a82c0  push    rbp
0x1800a82c2  push    rbx
0x1800a82c3  push    rsi
0x1800a82c4  push    rdi
0x1800a82c5  push    r12
0x1800a82c7  push    r13
0x1800a82c9  push    r14
0x1800a82cb  push    r15
0x1800a82cd  lea     rbp, [rsp-7]
0x1800a82d2  sub     rsp, 0E8h
0x1800a82d9  mov     rax, cs:__security_cookie
0x1800a82e0  xor     rax, rsp
0x1800a82e3  mov     [rbp+3Fh+var_50], rax
0x1800a82e7  mov     rdi, [rbp+3Fh+arg_20]
0x1800a82eb  xor     esi, esi
0x1800a82ed  mov     r15, [rbp+3Fh+arg_28]
0x1800a82f1  xor     eax, eax
0x1800a82f3  mov     r12, [rbp+3Fh+FileObject]
0x1800a82f7  xorps   xmm0, xmm0
0x1800a82fa  mov     dword ptr [rbp+3Fh+var_90+4], esi
0x1800a82fd  mov     ebx, r9d
0x1800a8300  mov     dword ptr [rbp+3Fh+var_88+4], esi
0x1800a8303  mov     r13d, ecx
0x1800a8306  mov     byte ptr [rbp+3Fh+var_90], sil
0x1800a830a  mov     dword ptr [rbp+3Fh+var_88], esi
0x1800a830d  mov     [rbp+3Fh+var_58], rax
0x1800a8311  mov     [rbp+3Fh+var_80], rsi
0x1800a8315  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x1800a8319  movups  [rbp+3Fh+var_68], xmm0
0x1800a831d  test    cl, 5
0x1800a8320  jnz     loc_1800A84B0
0x1800a8326  test    r13b, 0Ah
0x1800a832a  jnz     loc_1800A83C7
0x1800a8330  cmp     dl, 5
0x1800a8333  jz      loc_1800A83C7
0x1800a8339  movzx   r14d, sil
0x1800a833d  test    rdi, rdi
0x1800a8340  jz      short loc_1800A8359
0x1800a8342  mov     rcx, rdi
0x1800a8345  call    cs:__imp_MmIsKernelAddress
0x1800a834c  nop     dword ptr [rax+rax+00h]
0x1800a8351  test    al, al
0x1800a8353  jz      loc_1800A83ED
0x1800a8359  mov     esi, r13d
0x1800a835c  and     esi, 10h
0x1800a835f  jz      short loc_1800A839F
0x1800a8361  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800a8366  xor     r14d, r14d
0x1800a8369  test    eax, eax
0x1800a836b  jnz     loc_1800A8409
0x1800a8371  mov     eax, cs:g_CiPolicyState
0x1800a8377  test    al, 2
0x1800a8379  jz      short loc_1800A838B
0x1800a837b  test    al, 40h
0x1800a837d  jnz     short loc_1800A83C7
0x1800a837f  mov     rcx, rdi
0x1800a8382  call    CipShouldRevalidateForPolicyChange
0x1800a8387  test    al, al
0x1800a8389  jnz     short loc_1800A83C7
0x1800a838b  test    cs:g_CiPolicyState, 4000h
0x1800a8395  jnz     loc_1800A84E9
0x1800a839b  xor     eax, eax
0x1800a839d  jmp     short loc_1800A83CC
0x1800a839f  call    cs:__imp_PsGetCurrentProcess
0x1800a83a6  nop     dword ptr [rax+rax+00h]
0x1800a83ab  mov     rcx, rax
0x1800a83ae  call    cs:__imp_PsIsProtectedProcessLight
0x1800a83b5  nop     dword ptr [rax+rax+00h]
0x1800a83ba  test    eax, eax
0x1800a83bc  jz      short loc_1800A8361
0x1800a83be  cmp     ebx, 7
0x1800a83c1  jz      loc_1800A84DB
0x1800a83c7  mov     eax, 1
0x1800a83cc  mov     rcx, [rbp+3Fh+var_50]
0x1800a83d0  xor     rcx, rsp; StackCookie
0x1800a83d3  call    __security_check_cookie
0x1800a83d8  add     rsp, 0E8h
0x1800a83df  pop     r15
0x1800a83e1  pop     r14
0x1800a83e3  pop     r13
0x1800a83e5  pop     r12
0x1800a83e7  pop     rdi
0x1800a83e8  pop     rsi
0x1800a83e9  pop     rbx
0x1800a83ea  pop     rbp
0x1800a83eb  retn
0x1800a83ed  bt      rdi, 3Bh ; ';'
0x1800a83f2  jnb     short loc_1800A8452
0x1800a83f4  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800a83fb  nop     dword ptr [rax+rax+00h]
0x1800a8400  test    al, al
0x1800a8402  jz      short loc_1800A83C7
0x1800a8404  jmp     loc_1800A8359
0x1800a8409  test    esi, esi
0x1800a840b  jz      loc_1800A8371
0x1800a8411  mov     [rsp+120h+var_E8], r14
0x1800a8416  lea     rax, [rbp+3Fh+var_80]
0x1800a841a  mov     [rsp+120h+var_F0], rax
0x1800a841f  xor     r9d, r9d
0x1800a8422  mov     [rsp+120h+var_F8], r14
0x1800a8427  xor     r8d, r8d
0x1800a842a  xor     edx, edx
0x1800a842c  mov     [rsp+120h+var_100], r14
0x1800a8431  mov     rcx, r15
0x1800a8434  call    cs:__imp_RtlQueryPackageClaims
0x1800a843b  nop     dword ptr [rax+rax+00h]
0x1800a8440  test    dword ptr [rbp+3Fh+var_80], 200000h
0x1800a8447  jnz     loc_1800A83C7
0x1800a844d  jmp     loc_1800A8371
0x1800a8452  bt      rdi, 3Ah ; ':'
0x1800a8457  mov     r8d, 1
0x1800a845d  cmovnb  r14d, r8d
0x1800a8461  jmp     loc_1800A8359
0x1800a8466  movzx   ecx, r8b
0x1800a846a  mov     edx, 1
0x1800a846f  and     ecx, 0Fh
0x1800a8472  shl     edx, cl
0x1800a8474  mov     rcx, cs:g_CipWhichLevelComparisons
0x1800a847b  test    [rcx+20h], edx
0x1800a847e  jz      loc_1800A83C7
0x1800a8484  mov     eax, cs:g_CiPolicyState
0x1800a848a  mov     r8d, 1
0x1800a8490  test    r8b, al
0x1800a8493  jnz     short loc_1800A84A5
0x1800a8495  mov     rcx, rdi
0x1800a8498  call    CipShouldRevalidateForPolicyChange
0x1800a849d  movzx   eax, al
0x1800a84a0  jmp     loc_1800A83CC
0x1800a84a5  test    [rcx+30h], edx
0x1800a84a8  jz      loc_1800A83C7
0x1800a84ae  jmp     short loc_1800A8495
0x1800a84b0  test    ebx, ebx
0x1800a84b2  jz      loc_1800A83C7
0x1800a84b8  sub     ebx, 1
0x1800a84bb  jz      short loc_1800A8466
0x1800a84bd  sub     ebx, 1
0x1800a84c0  jz      loc_1800A83C7
0x1800a84c6  sub     ebx, 1
0x1800a84c9  jz      short loc_1800A8466
0x1800a84cb  sub     ebx, 1
0x1800a84ce  jz      short loc_1800A8466
0x1800a84d0  sub     ebx, 1
0x1800a84d3  jnz     loc_1800A83C7
0x1800a84d9  jmp     short loc_1800A8466
0x1800a84db  test    r14b, r14b
0x1800a84de  jnz     loc_1800A83C7
0x1800a84e4  jmp     loc_1800A8361
0x1800a84e9  test    esi, esi
0x1800a84eb  jz      loc_1800A839B
0x1800a84f1  test    r15, r15
0x1800a84f4  jz      short loc_1800A8506
0x1800a84f6  mov     rcx, r15
0x1800a84f9  call    CipSmartlockerHasDangerousOrInstallerExtension
0x1800a84fe  test    eax, eax
0x1800a8500  jnz     loc_1800A83C7
0x1800a8506  test    r12, r12
0x1800a8509  jz      loc_1800A839B
0x1800a850f  lea     rax, [rbp+3Fh+var_78]
0x1800a8513  mov     r8d, r13d
0x1800a8516  mov     [rsp+120h+var_A0], rax; __int64
0x1800a851e  lea     r9, [rbp+3Fh+var_90+4]
0x1800a8522  lea     rax, [rbp+3Fh+var_88]
0x1800a8526  xor     edx, edx
0x1800a8528  mov     [rsp+120h+var_A8], rax; __int64
0x1800a852d  mov     rcx, r12; FileObject
0x1800a8530  mov     [rsp+120h+var_B0], r14; __int64
0x1800a8535  lea     rax, [rbp+3Fh+var_90]
0x1800a8539  mov     [rsp+120h+var_B8], r14; __int64
0x1800a853e  mov     [rsp+120h+var_C0], r14; __int64
0x1800a8543  mov     [rsp+120h+var_C8], r15; __int64
0x1800a8548  mov     [rsp+120h+var_D0], r14; __int64
0x1800a854d  mov     [rsp+120h+var_D8], r14; __int64
0x1800a8552  mov     [rsp+120h+var_E0], r14; __int64
0x1800a8557  mov     [rsp+120h+var_E8], r14; __int64
0x1800a855c  mov     [rsp+120h+var_F0], r14; __int64
0x1800a8561  mov     [rsp+120h+var_F8], rax; __int64
0x1800a8566  lea     rax, [rbp+3Fh+var_88+4]
0x1800a856a  mov     [rsp+120h+var_100], rax; __int64
0x1800a856f  call    CipGetFileCache
0x1800a8574  cmp     eax, 0C0000225h
0x1800a8579  jnz     short loc_1800A8594
0x1800a857b  cmp     dword ptr [rbp+3Fh+var_90+4], 0Fh
0x1800a857f  jz      loc_1800A83C7
0x1800a8585  cmp     dword ptr [rbp+3Fh+var_90+4], 4
0x1800a8589  jle     loc_1800A83C7
0x1800a858f  jmp     loc_1800A839B
0x1800a8594  test    eax, eax
0x1800a8596  js      loc_1800A839B
0x1800a859c  mov     edx, dword ptr [rbp+3Fh+var_88]
0x1800a859f  test    edx, edx
0x1800a85a1  jns     loc_1800A839B
0x1800a85a7  mov     r9d, dword ptr [rbp+3Fh+var_78+4]
0x1800a85ab  lea     r8, [rbp+3Fh+var_78+8]
0x1800a85af  mov     rcx, r12
0x1800a85b2  call    CiInstrumentSmartAppControlNoReEvaluation
0x1800a85b7  jmp     loc_1800A839B
```
