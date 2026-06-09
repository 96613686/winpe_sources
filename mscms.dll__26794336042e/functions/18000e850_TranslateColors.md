# TranslateColors

- ea: `0x18000e850`
- end: `0x18000ea14`
- name: `TranslateColors`
- size: `452`
- prototype: `BOOL __stdcall(HTRANSFORM hColorTransform, PCOLOR paInputColors, DWORD nColors, COLORTYPE ctInput, PCOLOR paOutputColors, COLORTYPE ctOutput)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000e6a0`
- `0x180062d80`

## callees

- `0x18000e850`
- `0x18000ef40`
- `0x18000efa0`
- `0x18002e5f0`
- `0x180051f50`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000e8d3`
- `ntdll!EtwEventWrite` at `0x18000e9b4`
- `ntdll!EtwEventWrite` at `0x18000e9e9`
- `ntdll!EtwEventWrite` at `0x18000e8d3`
- `ntdll!EtwEventWrite` at `0x18000e9b4`
- `ntdll!EtwEventWrite` at `0x18000e9e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e98c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e9f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e98c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e9f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9bc`

## pseudocode

```c
BOOL __stdcall TranslateColors(
        HTRANSFORM hColorTransform,
        PCOLOR paInputColors,
        DWORD nColors,
        COLORTYPE ctInput,
        PCOLOR paOutputColors,
        COLORTYPE ctOutput)
{
  __int64 FPU; // rdi
  __int64 v8; // rdx
  __int64 v9; // rcx
  _DWORD *v10; // rcx
  int v11; // eax
  BOOL v12; // ebx
  COLORTYPE v14; // [rsp+40h] [rbp-59h] BYREF
  DWORD v15; // [rsp+48h] [rbp-51h] BYREF
  DWORD dwErrCode; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v19[8]; // [rsp+70h] [rbp-29h] BYREF

  v19[0] = &v17;
  v17 = (unsigned __int64)hColorTransform;
  v19[2] = &v15;
  FPU = 0;
  v15 = nColors;
  v19[4] = &v14;
  v14 = ctInput;
  v19[6] = &ctOutput;
  v19[1] = 8;
  v19[3] = 4;
  v19[5] = 4;
  v19[7] = 4;
  EtwEventWrite(g_etwHandle, TRANSLATING_COLORS, 4, v19);
  if ( (unsigned int)(v14 - 1) > 0xB || (unsigned int)(ctOutput - 1) > 0xB )
  {
LABEL_14:
    SetLastError(0x57u);
    goto LABEL_15;
  }
  FPU = CreateFPU(v9, v8);
  if ( FPU )
  {
    if ( v17 )
    {
      v10 = (_DWORD *)(v17 ^ 0x49434D20);
      if ( v17 != 0x49434D20 )
      {
        if ( *v10 == 1129599565 )
        {
          v11 = CITETranslateColors(v17, paInputColors, v15, (unsigned int)v14, paOutputColors, ctOutput);
LABEL_13:
          v12 = v11;
          goto LABEL_16;
        }
        if ( *v10 == 1481003597 && v15 && paInputColors && paOutputColors )
        {
          v11 = (*(__int64 (__fastcall **)(_QWORD, PCOLOR, _QWORD, _QWORD, PCOLOR, COLORTYPE))(*(_QWORD *)((v17 ^ 0x49434D20) + 8)
                                                                                             + 80LL))(
                  *(_QWORD *)((v17 ^ 0x49434D20) + 0x10),
                  paInputColors,
                  v15,
                  (unsigned int)v14,
                  paOutputColors,
                  ctOutput);
          goto LABEL_13;
        }
      }
    }
    goto LABEL_14;
  }
LABEL_15:
  v12 = 0;
LABEL_16:
  DeleteFPU(FPU);
  if ( v12 )
  {
    EtwEventWrite(g_etwHandle, TRANSLATED_COLORS, 0, 0);
  }
  else
  {
    dwErrCode = GetLastError();
    v18[1] = 4;
    v18[0] = &dwErrCode;
    EtwEventWrite(g_etwHandle, COLOR_TRANSLATION_FAILED, 1, v18);
    SetLastError(dwErrCode);
  }
  return v12;
}

```

## disassembly

```asm
0x18000e850  push    rbp
0x18000e852  push    rbx
0x18000e853  push    rsi
0x18000e854  push    rdi
0x18000e855  push    r15
0x18000e857  lea     rbp, [rsp-27h]
0x18000e85c  sub     rsp, 0C0h
0x18000e863  mov     rax, cs:__security_cookie
0x18000e86a  xor     rax, rsp
0x18000e86d  mov     [rbp+47h+var_30], rax
0x18000e871  mov     rsi, [rbp+47h+paOutputColors]
0x18000e875  lea     rax, [rbp+47h+var_88]
0x18000e879  mov     [rbp+47h+var_70], rax
0x18000e87d  mov     rbx, rdx
0x18000e880  lea     rax, [rbp+47h+var_98]
0x18000e884  mov     [rbp+47h+var_88], rcx
0x18000e888  mov     rcx, cs:g_etwHandle
0x18000e88f  lea     rdx, TRANSLATING_COLORS
0x18000e896  mov     [rbp+47h+var_60], rax
0x18000e89a  xor     edi, edi
0x18000e89c  lea     rax, [rbp+47h+var_A0]
0x18000e8a0  mov     [rbp+47h+var_98], r8d
0x18000e8a4  mov     [rbp+47h+var_50], rax
0x18000e8a8  lea     rax, [rbp+47h+ctOutput]
0x18000e8ac  mov     [rbp+47h+var_A0], r9d
0x18000e8b0  lea     r9, [rbp+47h+var_70]
0x18000e8b4  lea     r15d, [rdi+4]
0x18000e8b8  mov     [rbp+47h+var_40], rax
0x18000e8bc  mov     r8d, r15d
0x18000e8bf  mov     [rbp+47h+var_68], 8
0x18000e8c7  mov     [rbp+47h+var_58], r15
0x18000e8cb  mov     [rbp+47h+var_48], r15
0x18000e8cf  mov     [rbp+47h+var_38], r15
0x18000e8d3  call    cs:__imp_EtwEventWrite
0x18000e8d9  mov     eax, [rbp+47h+var_A0]
0x18000e8dc  dec     eax
0x18000e8de  cmp     eax, 0Bh
0x18000e8e1  ja      loc_18000E987
0x18000e8e7  mov     eax, [rbp+47h+ctOutput]
0x18000e8ea  dec     eax
0x18000e8ec  cmp     eax, 0Bh
0x18000e8ef  ja      loc_18000E987
0x18000e8f5  call    CreateFPU
0x18000e8fa  mov     rdi, rax
0x18000e8fd  test    rax, rax
0x18000e900  jz      loc_18000E992
0x18000e906  mov     r10, [rbp+47h+var_88]
0x18000e90a  test    r10, r10
0x18000e90d  jz      short loc_18000E987
0x18000e90f  mov     rcx, r10
0x18000e912  xor     rcx, 49434D20h
0x18000e919  jz      short loc_18000E987
0x18000e91b  cmp     dword ptr [rcx], 4354524Dh
0x18000e921  jnz     short loc_18000E944
0x18000e923  mov     eax, [rbp+47h+ctOutput]
0x18000e926  mov     rdx, rbx
0x18000e929  mov     r9d, [rbp+47h+var_A0]
0x18000e92d  mov     rcx, r10
0x18000e930  mov     r8d, [rbp+47h+var_98]
0x18000e934  mov     [rsp+0E0h+var_B8], eax
0x18000e938  mov     [rsp+0E0h+var_C0], rsi
0x18000e93d  call    CITETranslateColors
0x18000e942  jmp     short loc_18000E983
0x18000e944  cmp     dword ptr [rcx], 5846524Dh
0x18000e94a  jnz     short loc_18000E987
0x18000e94c  mov     r8d, [rbp+47h+var_98]
0x18000e950  test    r8d, r8d
0x18000e953  jz      short loc_18000E987
0x18000e955  test    rbx, rbx
0x18000e958  jz      short loc_18000E987
0x18000e95a  test    rsi, rsi
0x18000e95d  jz      short loc_18000E987
0x18000e95f  mov     rax, [rcx+8]
0x18000e963  mov     edx, [rbp+47h+ctOutput]
0x18000e966  mov     r9d, [rbp+47h+var_A0]
0x18000e96a  mov     rcx, [rcx+10h]
0x18000e96e  mov     rax, [rax+50h]
0x18000e972  mov     [rsp+0E0h+var_B8], edx
0x18000e976  mov     rdx, rbx
0x18000e979  mov     [rsp+0E0h+var_C0], rsi
0x18000e97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e983  mov     ebx, eax
0x18000e985  jmp     short loc_18000E994
0x18000e987  mov     ecx, 57h ; 'W'; dwErrCode
0x18000e98c  call    cs:__imp_SetLastError
0x18000e992  xor     ebx, ebx
0x18000e994  mov     rcx, rdi
0x18000e997  call    DeleteFPU
0x18000e99c  test    ebx, ebx
0x18000e99e  jz      short loc_18000E9BC
0x18000e9a0  mov     rcx, cs:g_etwHandle
0x18000e9a7  lea     rdx, TRANSLATED_COLORS
0x18000e9ae  xor     r9d, r9d
0x18000e9b1  xor     r8d, r8d
0x18000e9b4  call    cs:__imp_EtwEventWrite
0x18000e9ba  jmp     short loc_18000E9F8
0x18000e9bc  call    cs:__imp_GetLastError
0x18000e9c2  mov     rcx, cs:g_etwHandle
0x18000e9c9  lea     r9, [rbp+47h+var_80]
0x18000e9cd  mov     [rbp+47h+dwErrCode], eax
0x18000e9d0  lea     rdx, COLOR_TRANSLATION_FAILED
0x18000e9d7  lea     rax, [rbp+47h+dwErrCode]
0x18000e9db  mov     [rbp+47h+var_78], r15
0x18000e9df  mov     r8d, 1
0x18000e9e5  mov     [rbp+47h+var_80], rax
0x18000e9e9  call    cs:__imp_EtwEventWrite
0x18000e9ef  mov     ecx, [rbp+47h+dwErrCode]; dwErrCode
0x18000e9f2  call    cs:__imp_SetLastError
0x18000e9f8  mov     eax, ebx
0x18000e9fa  mov     rcx, [rbp+47h+var_30]
0x18000e9fe  xor     rcx, rsp; StackCookie
0x18000ea01  call    __security_check_cookie
0x18000ea06  add     rsp, 0C0h
0x18000ea0d  pop     r15
0x18000ea0f  pop     rdi
0x18000ea10  pop     rsi
0x18000ea11  pop     rbx
0x18000ea12  pop     rbp
0x18000ea13  retn
```
