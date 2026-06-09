# WcsTranslateColors

- ea: `0x18003e2d0`
- end: `0x18003e499`
- name: `WcsTranslateColors`
- size: `457`
- prototype: `BOOL __stdcall(HTRANSFORM hColorTransform, DWORD nColors, DWORD nInputChannels, COLORDATATYPE cdtInput, DWORD cbInput, PVOID pInputData, DWORD nOutputChannels, COLORDATATYPE cdtOutput, DWORD cbOutput, PVOID pOutputData)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000ef40`
- `0x18000efa0`
- `0x18002e5f0`
- `0x18003e2d0`
- `0x180052410`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003e3b0`
- `ntdll!EtwEventWrite` at `0x18003e430`
- `ntdll!EtwEventWrite` at `0x18003e46d`
- `ntdll!EtwEventWrite` at `0x18003e3b0`
- `ntdll!EtwEventWrite` at `0x18003e430`
- `ntdll!EtwEventWrite` at `0x18003e46d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e438`

## pseudocode

```c
BOOL __stdcall WcsTranslateColors(
        HTRANSFORM hColorTransform,
        DWORD nColors,
        DWORD nInputChannels,
        COLORDATATYPE cdtInput,
        DWORD cbInput,
        PVOID pInputData,
        DWORD nOutputChannels,
        COLORDATATYPE cdtOutput,
        DWORD cbOutput,
        PVOID pOutputData)
{
  PVOID v10; // rbx
  PVOID v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 FPU; // rdi
  int v15; // ebx
  COLORDATATYPE v17; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v18; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v19; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwErrCode; // [rsp+68h] [rbp-98h] BYREF
  HTRANSFORM v21; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v23[16]; // [rsp+90h] [rbp-70h] BYREF

  v10 = pInputData;
  v11 = pOutputData;
  v23[0] = &v21;
  v23[2] = &v19;
  v23[4] = &v18;
  v23[6] = &v17;
  v23[8] = &cbInput;
  v23[10] = &nOutputChannels;
  v23[12] = &cdtOutput;
  v18 = nInputChannels;
  v21 = hColorTransform;
  v19 = nColors;
  v17 = cdtInput;
  v23[14] = &cbOutput;
  v23[1] = 8;
  v23[3] = 4;
  v23[5] = 4;
  v23[7] = 4;
  v23[9] = 4;
  v23[11] = 4;
  v23[13] = 4;
  v23[15] = 4;
  EtwEventWrite(g_etwHandle, WCS_TRANSLATING_COLORS, 8, v23);
  FPU = CreateFPU(v13, v12);
  if ( FPU )
    v15 = CITEWcsTranslateColors(
            v21,
            v19,
            v18,
            (unsigned int)v17,
            cbInput,
            v10,
            nOutputChannels,
            cdtOutput,
            cbOutput,
            v11);
  else
    v15 = 0;
  DeleteFPU(FPU);
  if ( v15 )
  {
    EtwEventWrite(g_etwHandle, TRANSLATED_COLORS, 0, 0);
  }
  else
  {
    dwErrCode = GetLastError();
    v22[1] = 4;
    v22[0] = &dwErrCode;
    EtwEventWrite(g_etwHandle, COLOR_TRANSLATION_FAILED, 1, v22);
    SetLastError(dwErrCode);
  }
  return v15;
}

```

## disassembly

```asm
0x18003e2d0  push    rbp
0x18003e2d2  push    rbx
0x18003e2d3  push    rsi
0x18003e2d4  push    rdi
0x18003e2d5  push    r15
0x18003e2d7  lea     rbp, [rsp-20h]
0x18003e2dc  sub     rsp, 120h
0x18003e2e3  mov     rax, cs:__security_cookie
0x18003e2ea  xor     rax, rsp
0x18003e2ed  mov     [rbp+40h+var_30], rax
0x18003e2f1  mov     rbx, [rbp+40h+pInputData]
0x18003e2f5  lea     rax, [rsp+140h+var_D0]
0x18003e2fa  mov     rsi, [rbp+40h+pOutputData]
0x18003e301  mov     [rbp+40h+var_B0], rax
0x18003e305  lea     rax, [rsp+140h+var_E0]
0x18003e30a  mov     [rbp+40h+var_A0], rax
0x18003e30e  lea     rax, [rsp+140h+var_E8]
0x18003e313  mov     [rbp+40h+var_90], rax
0x18003e317  lea     rax, [rsp+140h+var_F0]
0x18003e31c  mov     [rbp+40h+var_80], rax
0x18003e320  lea     rax, [rbp+40h+cbInput]
0x18003e324  mov     [rbp+40h+var_70], rax
0x18003e328  lea     rax, [rbp+40h+nOutputChannels]
0x18003e32f  mov     [rbp+40h+var_60], rax
0x18003e333  lea     rax, [rbp+40h+cdtOutput]
0x18003e33a  mov     [rbp+40h+var_50], rax
0x18003e33e  lea     rax, [rbp+40h+cbOutput]
0x18003e345  mov     [rsp+140h+var_E8], r8d
0x18003e34a  mov     r8d, 8
0x18003e350  mov     [rsp+140h+var_D0], rcx
0x18003e355  mov     rcx, cs:g_etwHandle
0x18003e35c  mov     [rsp+140h+var_E0], edx
0x18003e360  lea     rdx, WCS_TRANSLATING_COLORS
0x18003e367  mov     [rsp+140h+var_F0], r9d
0x18003e36c  lea     r9, [rbp+40h+var_B0]
0x18003e370  mov     [rbp+40h+var_40], rax
0x18003e374  mov     [rbp+40h+var_A8], r8
0x18003e378  mov     [rbp+40h+var_98], 4
0x18003e380  mov     [rbp+40h+var_88], 4
0x18003e388  mov     [rbp+40h+var_78], 4
0x18003e390  mov     [rbp+40h+var_68], 4
0x18003e398  mov     [rbp+40h+var_58], 4
0x18003e3a0  mov     [rbp+40h+var_48], 4
0x18003e3a8  mov     [rbp+40h+var_38], 4
0x18003e3b0  call    cs:__imp_EtwEventWrite
0x18003e3b6  call    CreateFPU
0x18003e3bb  mov     rdi, rax
0x18003e3be  test    rax, rax
0x18003e3c1  jnz     short loc_18003E3C7
0x18003e3c3  xor     ebx, ebx
0x18003e3c5  jmp     short loc_18003E410
0x18003e3c7  mov     eax, [rbp+40h+cbOutput]
0x18003e3cd  mov     r9d, [rsp+140h+var_F0]
0x18003e3d2  mov     r8d, [rsp+140h+var_E8]
0x18003e3d7  mov     edx, [rsp+140h+var_E0]
0x18003e3db  mov     rcx, [rsp+140h+var_D0]
0x18003e3e0  mov     [rsp+140h+var_F8], rsi
0x18003e3e5  mov     [rsp+140h+var_100], eax
0x18003e3e9  mov     eax, [rbp+40h+cdtOutput]
0x18003e3ef  mov     [rsp+140h+var_108], eax
0x18003e3f3  mov     eax, [rbp+40h+nOutputChannels]
0x18003e3f9  mov     [rsp+140h+var_110], eax
0x18003e3fd  mov     eax, [rbp+40h+cbInput]
0x18003e400  mov     [rsp+140h+var_118], rbx
0x18003e405  mov     [rsp+140h+var_120], eax
0x18003e409  call    CITEWcsTranslateColors
0x18003e40e  mov     ebx, eax
0x18003e410  mov     rcx, rdi
0x18003e413  call    DeleteFPU
0x18003e418  test    ebx, ebx
0x18003e41a  jz      short loc_18003E438
0x18003e41c  mov     rcx, cs:g_etwHandle
0x18003e423  lea     rdx, TRANSLATED_COLORS
0x18003e42a  xor     r9d, r9d
0x18003e42d  xor     r8d, r8d
0x18003e430  call    cs:__imp_EtwEventWrite
0x18003e436  jmp     short loc_18003E47D
0x18003e438  call    cs:__imp_GetLastError
0x18003e43e  mov     rcx, cs:g_etwHandle
0x18003e445  lea     r9, [rsp+140h+var_C8]
0x18003e44a  mov     [rsp+140h+dwErrCode], eax
0x18003e44e  lea     rdx, COLOR_TRANSLATION_FAILED
0x18003e455  lea     rax, [rsp+140h+dwErrCode]
0x18003e45a  mov     [rbp+40h+var_C0], 4
0x18003e462  mov     r8d, 1
0x18003e468  mov     [rsp+140h+var_C8], rax
0x18003e46d  call    cs:__imp_EtwEventWrite
0x18003e473  mov     ecx, [rsp+140h+dwErrCode]; dwErrCode
0x18003e477  call    cs:__imp_SetLastError
0x18003e47d  mov     eax, ebx
0x18003e47f  mov     rcx, [rbp+40h+var_30]
0x18003e483  xor     rcx, rsp; StackCookie
0x18003e486  call    __security_check_cookie
0x18003e48b  add     rsp, 120h
0x18003e492  pop     r15
0x18003e494  pop     rdi
0x18003e495  pop     rsi
0x18003e496  pop     rbx
0x18003e497  pop     rbp
0x18003e498  retn
```
