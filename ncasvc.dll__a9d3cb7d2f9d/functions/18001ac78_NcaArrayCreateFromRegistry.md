# NcaArrayCreateFromRegistry

- ea: `0x18001ac78`
- end: `0x18001ae69`
- name: `NcaArrayCreateFromRegistry`
- size: `497`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64, __int64 (__fastcall *)(_QWORD, HKEY, LPVOID, LPVOID, char *), __int64, DWORD cValues, _OWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800052c8`
- `0x180005770`

## callees

- `0x180002d50`
- `0x1800033bc`
- `0x180003770`
- `0x1800037b0`
- `0x1800199b4`
- `0x180019ad0`
- `0x18001a0fc`
- `0x18001a890`
- `0x18001abd4`
- `0x18001ac78`
- `0x18001ae70`
- `0x18001e010`

## string_xrefs

- `0x18001ace7`: `NcaArrayCreateFromRegistry`
- `0x18001ad58`: `NcaArrayCreateFromRegistry`
- `0x18001ae47`: `NcaArrayCreateFromRegistry`

## pseudocode

```c
__int64 __fastcall NcaArrayCreateFromRegistry(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 (__fastcall *a4)(_QWORD, HKEY, LPVOID, LPVOID, char *),
        __int64 a5,
        DWORD cValues,
        _OWORD *a7)
{
  DWORD v7; // r15d
  DWORD v9; // esi
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  DWORD v13; // eax
  char *v14; // r14
  int *v16; // [rsp+28h] [rbp-49h]
  int v17; // [rsp+40h] [rbp-31h] BYREF
  int v18; // [rsp+44h] [rbp-2Dh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-29h]
  LPVOID lpMem; // [rsp+50h] [rbp-21h]
  LPVOID v21; // [rsp+58h] [rbp-19h]
  SIZE_T v22; // [rsp+60h] [rbp-11h] BYREF
  __int128 v23; // [rsp+68h] [rbp-9h] BYREF

  v7 = 0;
  hKey = 0;
  v17 = 0;
  v9 = 0;
  *a7 = 0;
  cValues = 0;
  v22 = 0;
  v23 = 0u;
  lpMem = 0;
  v21 = 0;
  v18 = 0;
  v10 = NcaRegOpenKey(a1, a2, 1u, (__int64)&v17);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( v17 )
    {
      v10 = NcaRegQueryNumValues(hKey, &cValues);
      v11 = v10;
      if ( v10 < 0 )
        goto LABEL_2;
      v13 = cValues;
    }
    else
    {
      v13 = 0;
      cValues = 0;
    }
    if ( v13 )
    {
      v10 = NcaSizeTMultiply(v13, a3, &v22);
      v11 = v10;
      if ( v10 < 0 )
        goto LABEL_2;
      *((_QWORD *)&v23 + 1) = NcaAlloc(v22);
      v14 = (char *)*((_QWORD *)&v23 + 1);
      if ( !*((_QWORD *)&v23 + 1) )
      {
        v11 = NcaReportErrorAsWinError("NcaArrayCreateFromRegistry", "NcaAlloc", 8);
        goto LABEL_22;
      }
      while ( v9 < cValues )
      {
        v10 = NcaRegEnumValueNameAndValueData(hKey, v7, (__int64)&v17, (DWORD)v16);
        v11 = v10;
        if ( v10 < 0 )
          goto LABEL_2;
        if ( !v17 )
          break;
        v16 = &v18;
        v11 = a4(0, hKey, lpMem, v21, &v14[a3 * v9]);
        NcaFree(lpMem);
        NcaFree(v21);
        if ( v11 < 0 )
        {
          v12 = (unsigned int)v11;
          goto LABEL_3;
        }
        ++v7;
        if ( v18 )
          LODWORD(v23) = ++v9;
      }
      if ( !v9 )
      {
        NcaFree(v14);
        *((_QWORD *)&v23 + 1) = 0;
      }
    }
    *a7 = v23;
LABEL_22:
    if ( v11 >= 0 )
      goto LABEL_24;
    goto LABEL_23;
  }
LABEL_2:
  v12 = (unsigned int)v10;
LABEL_3:
  NcaReportReturnError("NcaArrayCreateFromRegistry", v12);
LABEL_23:
  NcaArrayDestroy(a3, a5, &v23);
LABEL_24:
  NcaRegCloseKey(hKey);
  if ( v11 < 0 )
    return (unsigned int)NcaReportReturnError("NcaArrayCreateFromRegistry", (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001ac78  mov     [rsp-8+arg_18], r9
0x18001ac7d  push    rbp
0x18001ac7e  push    rbx
0x18001ac7f  push    rsi
0x18001ac80  push    r13
0x18001ac82  push    r14
0x18001ac84  push    r15
0x18001ac86  lea     rbp, [rsp-17h]
0x18001ac8b  sub     rsp, 88h
0x18001ac92  mov     rax, [rbp+3Fh+arg_30]
0x18001ac96  lea     r9, [rbp+3Fh+hKey]
0x18001ac9a  xor     r15d, r15d
0x18001ac9d  xorps   xmm0, xmm0
0x18001aca0  mov     r13, r8
0x18001aca3  mov     [rbp+3Fh+hKey], r15
0x18001aca7  mov     dword ptr [rbp+3Fh+var_70], r15d
0x18001acab  mov     esi, r15d
0x18001acae  movups  xmmword ptr [rax], xmm0
0x18001acb1  lea     rax, [rbp+3Fh+var_70]
0x18001acb5  mov     [rbp+3Fh+cValues], r15d
0x18001acb9  lea     r8d, [r15+1]; samDesired
0x18001acbd  mov     [rsp+0B0h+var_90], rax; __int64
0x18001acc2  mov     [rbp+3Fh+var_50], r15
0x18001acc6  mov     qword ptr [rbp+3Fh+var_48], r15
0x18001acca  mov     qword ptr [rbp+3Fh+var_48+8], r15
0x18001acce  mov     [rbp+3Fh+lpMem], r15
0x18001acd2  mov     [rbp+3Fh+var_58], r15
0x18001acd6  mov     dword ptr [rbp+3Fh+var_70+4], r15d
0x18001acda  call    NcaRegOpenKey
0x18001acdf  mov     ebx, eax
0x18001ace1  test    eax, eax
0x18001ace3  jns     short loc_18001ACF8
0x18001ace5  mov     edx, eax
0x18001ace7  lea     rcx, aNcaarraycreate; "NcaArrayCreateFromRegistry"
0x18001acee  call    NcaReportReturnError
0x18001acf3  jmp     loc_18001AE28
0x18001acf8  cmp     dword ptr [rbp+3Fh+var_70], r15d
0x18001acfc  jz      short loc_18001AD16
0x18001acfe  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18001ad02  lea     rdx, [rbp+3Fh+cValues]; lpcValues
0x18001ad06  call    NcaRegQueryNumValues
0x18001ad0b  mov     ebx, eax
0x18001ad0d  test    eax, eax
0x18001ad0f  js      short loc_18001ACE5
0x18001ad11  mov     eax, [rbp+3Fh+cValues]
0x18001ad14  jmp     short loc_18001AD1C
0x18001ad16  mov     eax, r15d
0x18001ad19  mov     [rbp+3Fh+cValues], eax
0x18001ad1c  test    eax, eax
0x18001ad1e  jz      loc_18001AE18
0x18001ad24  mov     ecx, eax
0x18001ad26  lea     r8, [rbp+3Fh+var_50]
0x18001ad2a  mov     rdx, r13
0x18001ad2d  call    NcaSizeTMultiply
0x18001ad32  mov     ebx, eax
0x18001ad34  test    eax, eax
0x18001ad36  js      short loc_18001ACE5
0x18001ad38  mov     rcx, [rbp+3Fh+var_50]
0x18001ad3c  call    NcaAlloc
0x18001ad41  mov     qword ptr [rbp+3Fh+var_48+8], rax
0x18001ad45  mov     r14, rax
0x18001ad48  test    rax, rax
0x18001ad4b  jnz     short loc_18001AD6B
0x18001ad4d  lea     r8d, [rax+8]
0x18001ad51  lea     rdx, aNcaalloc; "NcaAlloc"
0x18001ad58  lea     rcx, aNcaarraycreate; "NcaArrayCreateFromRegistry"
0x18001ad5f  call    NcaReportErrorAsWinError
0x18001ad64  mov     ebx, eax
0x18001ad66  jmp     loc_18001AE24
0x18001ad6b  cmp     esi, [rbp+3Fh+cValues]
0x18001ad6e  jnb     loc_18001AE05
0x18001ad74  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18001ad78  lea     rax, [rbp+3Fh+var_70]
0x18001ad7c  lea     r9, [rbp+3Fh+var_58]
0x18001ad80  mov     [rsp+0B0h+var_90], rax; __int64
0x18001ad85  lea     r8, [rbp+3Fh+lpMem]
0x18001ad89  mov     edx, r15d; dwIndex
0x18001ad8c  call    NcaRegEnumValueNameAndValueData
0x18001ad91  mov     ebx, eax
0x18001ad93  test    eax, eax
0x18001ad95  js      loc_18001ACE5
0x18001ad9b  cmp     dword ptr [rbp+3Fh+var_70], 0
0x18001ad9f  jz      short loc_18001AE05
0x18001ada1  mov     r9, [rbp+3Fh+var_58]
0x18001ada5  lea     rcx, [rbp+3Fh+var_70+4]
0x18001ada9  mov     r8, [rbp+3Fh+lpMem]
0x18001adad  mov     rdx, [rbp+3Fh+hKey]
0x18001adb1  mov     [rsp+0B0h+var_88], rcx
0x18001adb6  xor     ecx, ecx
0x18001adb8  mov     eax, esi
0x18001adba  imul    rax, r13
0x18001adbe  add     rax, r14
0x18001adc1  mov     [rsp+0B0h+var_90], rax
0x18001adc6  mov     rax, [rbp+3Fh+arg_18]
0x18001adca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adcf  mov     rcx, [rbp+3Fh+lpMem]; lpMem
0x18001add3  mov     ebx, eax
0x18001add5  call    NcaFree
0x18001adda  mov     rcx, [rbp+3Fh+var_58]; lpMem
0x18001adde  call    NcaFree
0x18001ade3  test    ebx, ebx
0x18001ade5  js      short loc_18001ADFE
0x18001ade7  inc     r15d
0x18001adea  cmp     dword ptr [rbp+3Fh+var_70+4], 0
0x18001adee  jz      loc_18001AD6B
0x18001adf4  inc     esi
0x18001adf6  mov     dword ptr [rbp+3Fh+var_48], esi
0x18001adf9  jmp     loc_18001AD6B
0x18001adfe  mov     edx, ebx
0x18001ae00  jmp     loc_18001ACE7
0x18001ae05  xor     r15d, r15d
0x18001ae08  test    esi, esi
0x18001ae0a  jnz     short loc_18001AE18
0x18001ae0c  mov     rcx, r14; lpMem
0x18001ae0f  call    NcaFree
0x18001ae14  mov     qword ptr [rbp+3Fh+var_48+8], r15
0x18001ae18  mov     rax, [rbp+3Fh+arg_30]
0x18001ae1c  movups  xmm0, [rbp+3Fh+var_48]
0x18001ae20  movdqu  xmmword ptr [rax], xmm0
0x18001ae24  test    ebx, ebx
0x18001ae26  jns     short loc_18001AE38
0x18001ae28  mov     rdx, [rbp+3Fh+arg_20]
0x18001ae2c  lea     r8, [rbp+3Fh+var_48]
0x18001ae30  mov     rcx, r13
0x18001ae33  call    NcaArrayDestroy
0x18001ae38  mov     rcx, [rbp+3Fh+hKey]
0x18001ae3c  call    NcaRegCloseKey
0x18001ae41  test    ebx, ebx
0x18001ae43  jns     short loc_18001AE55
0x18001ae45  mov     edx, ebx
0x18001ae47  lea     rcx, aNcaarraycreate; "NcaArrayCreateFromRegistry"
0x18001ae4e  call    NcaReportReturnError
0x18001ae53  mov     ebx, eax
0x18001ae55  mov     eax, ebx
0x18001ae57  add     rsp, 88h
0x18001ae5e  pop     r15
0x18001ae60  pop     r14
0x18001ae62  pop     r13
0x18001ae64  pop     rsi
0x18001ae65  pop     rbx
0x18001ae66  pop     rbp
0x18001ae67  retn
```
