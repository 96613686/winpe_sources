# TranslateBitmapBits

- ea: `0x18000ea20`
- end: `0x18000eda7`
- name: `TranslateBitmapBits`
- size: `903`
- prototype: `BOOL __stdcall(HTRANSFORM hColorTransform, PVOID pSrcBits, BMFORMAT bmInput, DWORD dwWidth, DWORD dwHeight, DWORD dwInputStride, PVOID pDestBits, BMFORMAT bmOutput, DWORD dwOutputStride, PBMCALLBACKFN pfnCallBack, LPARAM ulCallbackData)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000ea20`
- `0x18000edb0`
- `0x18000ef40`
- `0x18000fe30`
- `0x18002e5f0`
- `0x180051aa0`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000eaf6`
- `ntdll!EtwEventWrite` at `0x18000eb6b`
- `ntdll!EtwEventWrite` at `0x18000ecc9`
- `ntdll!EtwEventWrite` at `0x18000eaf6`
- `ntdll!EtwEventWrite` at `0x18000eb6b`
- `ntdll!EtwEventWrite` at `0x18000ecc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb38`

## pseudocode

```c
BOOL __stdcall TranslateBitmapBits(
        HTRANSFORM hColorTransform,
        PVOID pSrcBits,
        BMFORMAT bmInput,
        DWORD dwWidth,
        DWORD dwHeight,
        DWORD dwInputStride,
        PVOID pDestBits,
        BMFORMAT bmOutput,
        DWORD dwOutputStride,
        PBMCALLBACKFN pfnCallBack,
        LPARAM ulCallbackData)
{
  PVOID v11; // r15
  PBMCALLBACKFN v12; // r12
  BOOL v14; // ebx
  DWORD v15; // r8d
  DWORD BitmapBytes; // r9d
  DWORD v17; // r8d
  void (__fastcall ***FPU)(_QWORD, __int64); // rdi
  int v20; // eax
  DWORD v21; // ecx
  __int64 v22; // r10
  DWORD v23; // r9d
  DWORD v24; // r11d
  DWORD v25; // r8d
  unsigned int v26; // ebx
  unsigned int v27; // eax
  BMFORMAT v28; // esi
  unsigned int v29; // eax
  unsigned int v30; // [rsp+60h] [rbp-A0h] BYREF
  enum BMFORMAT v31; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwErrCode; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v34[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v35[14]; // [rsp+90h] [rbp-70h] BYREF

  v11 = pDestBits;
  v12 = pfnCallBack;
  v35[0] = &v33;
  v33 = (unsigned __int64)hColorTransform;
  v14 = 0;
  v35[2] = &v31;
  v35[4] = &v30;
  v35[6] = &dwHeight;
  v35[8] = &dwInputStride;
  v35[10] = &bmOutput;
  v31 = bmInput;
  v30 = dwWidth;
  v35[12] = &dwOutputStride;
  v35[1] = 8;
  v35[3] = 4;
  v35[5] = 4;
  v35[7] = 4;
  v35[9] = 4;
  v35[11] = 4;
  v35[13] = 4;
  EtwEventWrite(g_etwHandle, TRANSLATING_BITMAP_BITS, 7, v35);
  v15 = dwHeight;
  if ( dwInputStride )
    BitmapBytes = dwInputStride * dwHeight;
  else
    BitmapBytes = GetBitmapBytes(v31, v30, dwHeight);
  if ( dwOutputStride )
    v17 = dwOutputStride * v15;
  else
    v17 = GetBitmapBytes(bmOutput, v30, v15);
  if ( !v17 || !BitmapBytes || !pSrcBits || !v11 )
  {
    SetLastError(0x57u);
    goto LABEL_7;
  }
  FPU = (void (__fastcall ***)(_QWORD, __int64))CreateFPU();
  if ( !FPU )
    goto LABEL_7;
  if ( v33 && v33 != 0x49434D20 && *(_DWORD *)(v33 ^ 0x49434D20) == 1481003597 )
  {
    if ( (unsigned int)(v31 - 1537) > 1 && (unsigned int)(bmOutput - 1537) > 1 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, PVOID, _QWORD, _QWORD, DWORD, DWORD, PVOID, BMFORMAT, DWORD, PBMCALLBACKFN, LPARAM))(*(_QWORD *)((v33 ^ 0x49434D20) + 8) + 56LL))(
              *(_QWORD *)((v33 ^ 0x49434D20) + 0x10),
              pSrcBits,
              (unsigned int)v31,
              v30,
              dwHeight,
              dwInputStride,
              v11,
              bmOutput,
              dwOutputStride,
              v12,
              ulCallbackData);
LABEL_21:
      v14 = v20;
      goto LABEL_22;
    }
    v21 = 50;
    goto LABEL_35;
  }
  if ( !(unsigned int)ValidHandle(v33, 1129599565) )
  {
    v21 = 87;
LABEL_35:
    SetLastError(v21);
    goto LABEL_22;
  }
  v23 = dwInputStride;
  v24 = dwOutputStride;
  v25 = dwHeight;
  v26 = v30;
  if ( !dwInputStride )
  {
    v27 = GetBitmapBytes(v31, v30, dwHeight);
    v23 = v27 / v25;
  }
  v28 = bmOutput;
  if ( !v24 )
  {
    v29 = GetBitmapBytes(bmOutput, v26, v25);
    v24 = v29 / v25;
  }
  if ( v23 && v24 )
  {
    v20 = CITETranslateBitmapBits(v22, pSrcBits, (unsigned int)v31, v26, v25, v23, v11, v28, v24, v12, ulCallbackData);
    goto LABEL_21;
  }
  SetLastError(0x57u);
  v14 = 0;
LABEL_22:
  (**FPU)(FPU, 1);
  if ( v14 )
  {
    EtwEventWrite(g_etwHandle, TRANSLATED_COLORS, 0, 0);
    return v14;
  }
LABEL_7:
  dwErrCode = GetLastError();
  v34[1] = 4;
  v34[0] = &dwErrCode;
  EtwEventWrite(g_etwHandle, COLOR_TRANSLATION_FAILED, 1, v34);
  SetLastError(dwErrCode);
  return v14;
}

```

## disassembly

```asm
0x18000ea20  push    rbp
0x18000ea22  push    rbx
0x18000ea23  push    rsi
0x18000ea24  push    rdi
0x18000ea25  push    r12
0x18000ea27  push    r14
0x18000ea29  push    r15
0x18000ea2b  lea     rbp, [rsp-10h]
0x18000ea30  sub     rsp, 110h
0x18000ea37  mov     rax, cs:__security_cookie
0x18000ea3e  xor     rax, rsp
0x18000ea41  mov     [rbp+40h+var_40], rax
0x18000ea45  mov     r15, [rbp+40h+pDestBits]
0x18000ea4c  lea     rax, [rsp+140h+var_C8]
0x18000ea51  mov     r12, [rbp+40h+pfnCallBack]
0x18000ea58  mov     r14, rdx
0x18000ea5b  mov     [rbp+40h+var_B0], rax
0x18000ea5f  lea     rdx, TRANSLATING_BITMAP_BITS
0x18000ea66  lea     rax, [rsp+140h+var_D8]
0x18000ea6b  mov     [rsp+140h+var_C8], rcx
0x18000ea70  mov     rcx, cs:g_etwHandle
0x18000ea77  xor     ebx, ebx
0x18000ea79  mov     [rbp+40h+var_A0], rax
0x18000ea7d  lea     rax, [rsp+140h+var_E0]
0x18000ea82  mov     [rbp+40h+var_90], rax
0x18000ea86  lea     rax, [rbp+40h+dwHeight]
0x18000ea8a  mov     [rbp+40h+var_80], rax
0x18000ea8e  lea     rax, [rbp+40h+dwInputStride]
0x18000ea92  mov     [rbp+40h+var_70], rax
0x18000ea96  lea     rax, [rbp+40h+bmOutput]
0x18000ea9d  mov     [rbp+40h+var_60], rax
0x18000eaa1  lea     rax, [rbp+40h+dwOutputStride]
0x18000eaa8  mov     [rsp+140h+var_D8], r8d
0x18000eaad  lea     r8d, [rbx+7]
0x18000eab1  mov     [rsp+140h+var_E0], r9d
0x18000eab6  lea     r9, [rbp+40h+var_B0]
0x18000eaba  mov     [rbp+40h+var_50], rax
0x18000eabe  mov     [rbp+40h+var_A8], 8
0x18000eac6  mov     [rbp+40h+var_98], 4
0x18000eace  mov     [rbp+40h+var_88], 4
0x18000ead6  mov     [rbp+40h+var_78], 4
0x18000eade  mov     [rbp+40h+var_68], 4
0x18000eae6  mov     [rbp+40h+var_58], 4
0x18000eaee  mov     [rbp+40h+var_48], 4
0x18000eaf6  call    cs:__imp_EtwEventWrite
0x18000eafc  mov     eax, [rbp+40h+dwInputStride]
0x18000eaff  mov     r8d, [rbp+40h+dwHeight]; unsigned int
0x18000eb03  test    eax, eax
0x18000eb05  jz      loc_18000EB9B
0x18000eb0b  mov     r9d, r8d
0x18000eb0e  imul    r9d, eax
0x18000eb12  mov     eax, [rbp+40h+dwOutputStride]
0x18000eb18  test    eax, eax
0x18000eb1a  jz      loc_18000EBB0
0x18000eb20  imul    r8d, eax
0x18000eb24  test    r8d, r8d
0x18000eb27  jnz     loc_18000EBC7
0x18000eb2d  mov     ecx, 57h ; 'W'; dwErrCode
0x18000eb32  call    cs:__imp_SetLastError
0x18000eb38  call    cs:__imp_GetLastError
0x18000eb3e  mov     rcx, cs:g_etwHandle
0x18000eb45  lea     r9, [rbp+40h+var_C0]
0x18000eb49  mov     [rsp+140h+dwErrCode], eax
0x18000eb4d  lea     rdx, COLOR_TRANSLATION_FAILED
0x18000eb54  lea     rax, [rsp+140h+dwErrCode]
0x18000eb59  mov     [rbp+40h+var_B8], 4
0x18000eb61  mov     r8d, 1
0x18000eb67  mov     [rbp+40h+var_C0], rax
0x18000eb6b  call    cs:__imp_EtwEventWrite
0x18000eb71  mov     ecx, [rsp+140h+dwErrCode]; dwErrCode
0x18000eb75  call    cs:__imp_SetLastError
0x18000eb7b  mov     eax, ebx
0x18000eb7d  mov     rcx, [rbp+40h+var_40]
0x18000eb81  xor     rcx, rsp; StackCookie
0x18000eb84  call    __security_check_cookie
0x18000eb89  add     rsp, 110h
0x18000eb90  pop     r15
0x18000eb92  pop     r14
0x18000eb94  pop     r12
0x18000eb96  pop     rdi
0x18000eb97  pop     rsi
0x18000eb98  pop     rbx
0x18000eb99  pop     rbp
0x18000eb9a  retn
0x18000eb9b  mov     edx, [rsp+140h+var_E0]; unsigned int
0x18000eb9f  mov     ecx, [rsp+140h+var_D8]; enum BMFORMAT
0x18000eba3  call    ?GetBitmapBytes@@YAKW4BMFORMAT@@KK@Z; GetBitmapBytes(BMFORMAT,ulong,ulong)
0x18000eba8  mov     r9d, eax
0x18000ebab  jmp     loc_18000EB12
0x18000ebb0  mov     edx, [rsp+140h+var_E0]; unsigned int
0x18000ebb4  mov     ecx, [rbp+40h+bmOutput]; enum BMFORMAT
0x18000ebba  call    ?GetBitmapBytes@@YAKW4BMFORMAT@@KK@Z; GetBitmapBytes(BMFORMAT,ulong,ulong)
0x18000ebbf  mov     r8d, eax
0x18000ebc2  jmp     loc_18000EB24
0x18000ebc7  test    r9d, r9d
0x18000ebca  jz      loc_18000EB2D
0x18000ebd0  test    r14, r14
0x18000ebd3  jz      loc_18000EB2D
0x18000ebd9  test    r15, r15
0x18000ebdc  jz      loc_18000EB2D
0x18000ebe2  call    CreateFPU
0x18000ebe7  mov     rdi, rax
0x18000ebea  test    rax, rax
0x18000ebed  jz      loc_18000EB38
0x18000ebf3  mov     r10, [rsp+140h+var_C8]
0x18000ebf8  test    r10, r10
0x18000ebfb  jz      loc_18000ECDE
0x18000ec01  mov     rcx, r10
0x18000ec04  xor     rcx, 49434D20h
0x18000ec0b  jz      loc_18000ECDE
0x18000ec11  cmp     dword ptr [rcx], 5846524Dh
0x18000ec17  jnz     loc_18000ECDE
0x18000ec1d  mov     r8d, [rsp+140h+var_D8]
0x18000ec22  lea     eax, [r8-601h]
0x18000ec29  cmp     eax, 1
0x18000ec2c  jbe     loc_18000ECD4
0x18000ec32  mov     r9d, [rbp+40h+bmOutput]
0x18000ec39  lea     eax, [r9-601h]
0x18000ec40  cmp     eax, 1
0x18000ec43  jbe     loc_18000ECD4
0x18000ec49  mov     rax, [rcx+8]
0x18000ec4d  mov     rdx, r14
0x18000ec50  mov     rcx, [rcx+10h]
0x18000ec54  mov     r10, [rax+38h]
0x18000ec58  mov     rax, [rbp+40h+ulCallbackData]
0x18000ec5f  mov     [rsp+140h+var_F0], rax
0x18000ec64  mov     eax, [rbp+40h+dwOutputStride]
0x18000ec6a  mov     [rsp+140h+var_F8], r12
0x18000ec6f  mov     [rsp+140h+var_100], eax
0x18000ec73  mov     eax, [rbp+40h+dwInputStride]
0x18000ec76  mov     [rsp+140h+var_108], r9d
0x18000ec7b  mov     r9d, [rsp+140h+var_E0]
0x18000ec80  mov     [rsp+140h+var_110], r15
0x18000ec85  mov     [rsp+140h+var_118], eax
0x18000ec89  mov     eax, [rbp+40h+dwHeight]
0x18000ec8c  mov     [rsp+140h+var_120], eax
0x18000ec90  mov     rax, r10
0x18000ec93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec98  mov     ebx, eax
0x18000ec9a  mov     rax, [rdi]
0x18000ec9d  mov     edx, 1
0x18000eca2  mov     rcx, rdi
0x18000eca5  mov     rax, [rax]
0x18000eca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecad  test    ebx, ebx
0x18000ecaf  jz      loc_18000EB38
0x18000ecb5  mov     rcx, cs:g_etwHandle
0x18000ecbc  lea     rdx, TRANSLATED_COLORS
0x18000ecc3  xor     r9d, r9d
0x18000ecc6  xor     r8d, r8d
0x18000ecc9  call    cs:__imp_EtwEventWrite
0x18000eccf  jmp     loc_18000EB7B
0x18000ecd4  mov     ecx, 32h ; '2'
0x18000ecd9  jmp     loc_18000ED9C
0x18000ecde  mov     edx, 4354524Dh
0x18000ece3  mov     rcx, r10
0x18000ece6  call    ValidHandle
0x18000eceb  test    eax, eax
0x18000eced  jz      loc_18000ED97
0x18000ecf3  mov     r9d, [rbp+40h+dwInputStride]
0x18000ecf7  mov     r11d, [rbp+40h+dwOutputStride]
0x18000ecfe  mov     r8d, [rbp+40h+dwHeight]; unsigned int
0x18000ed02  mov     ebx, [rsp+140h+var_E0]
0x18000ed06  test    r9d, r9d
0x18000ed09  jnz     short loc_18000ED1E
0x18000ed0b  mov     ecx, [rsp+140h+var_D8]; enum BMFORMAT
0x18000ed0f  mov     edx, ebx; unsigned int
0x18000ed11  call    ?GetBitmapBytes@@YAKW4BMFORMAT@@KK@Z; GetBitmapBytes(BMFORMAT,ulong,ulong)
0x18000ed16  xor     edx, edx
0x18000ed18  div     r8d
0x18000ed1b  mov     r9d, eax
0x18000ed1e  mov     esi, [rbp+40h+bmOutput]
0x18000ed24  test    r11d, r11d
0x18000ed27  jnz     short loc_18000ED3A
0x18000ed29  mov     edx, ebx; unsigned int
0x18000ed2b  mov     ecx, esi; enum BMFORMAT
0x18000ed2d  call    ?GetBitmapBytes@@YAKW4BMFORMAT@@KK@Z; GetBitmapBytes(BMFORMAT,ulong,ulong)
0x18000ed32  xor     edx, edx
0x18000ed34  div     r8d
0x18000ed37  mov     r11d, eax
0x18000ed3a  test    r9d, r9d
0x18000ed3d  jz      short loc_18000ED85
0x18000ed3f  test    r11d, r11d
0x18000ed42  jz      short loc_18000ED85
0x18000ed44  mov     rax, [rbp+40h+ulCallbackData]
0x18000ed4b  mov     rdx, r14
0x18000ed4e  mov     [rsp+140h+var_F0], rax
0x18000ed53  mov     rcx, r10
0x18000ed56  mov     [rsp+140h+var_F8], r12
0x18000ed5b  mov     [rsp+140h+var_100], r11d
0x18000ed60  mov     [rsp+140h+var_108], esi
0x18000ed64  mov     [rsp+140h+var_110], r15
0x18000ed69  mov     [rsp+140h+var_118], r9d
0x18000ed6e  mov     r9d, ebx
0x18000ed71  mov     [rsp+140h+var_120], r8d
0x18000ed76  mov     r8d, [rsp+140h+var_D8]
0x18000ed7b  call    CITETranslateBitmapBits
0x18000ed80  jmp     loc_18000EC98
0x18000ed85  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ed8a  call    cs:__imp_SetLastError
0x18000ed90  xor     ebx, ebx
0x18000ed92  jmp     loc_18000EC9A
0x18000ed97  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ed9c  call    cs:__imp_SetLastError
0x18000eda2  jmp     loc_18000EC9A
```
