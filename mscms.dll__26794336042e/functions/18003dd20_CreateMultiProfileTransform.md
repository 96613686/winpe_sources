# CreateMultiProfileTransform

- ea: `0x18003dd20`
- end: `0x18003e06c`
- name: `CreateMultiProfileTransform`
- size: `844`
- prototype: `HTRANSFORM __stdcall(PHPROFILE pahProfiles, DWORD nProfiles, PDWORD padwIntent, DWORD nIntents, DWORD dwFlags, DWORD indexPreferredCMM)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180063010`

## callees

- `0x18000be44`
- `0x18000bf9c`
- `0x18000c310`
- `0x18000c38c`
- `0x18000ef40`
- `0x18000efa0`
- `0x18000fe30`
- `0x1800181d0`
- `0x180021aec`
- `0x18002e5f0`
- `0x18003dd20`
- `0x18005082c`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003dda6`
- `ntdll!EtwEventWrite` at `0x18003e004`
- `ntdll!EtwEventWrite` at `0x18003e03d`
- `ntdll!EtwEventWrite` at `0x18003dda6`
- `ntdll!EtwEventWrite` at `0x18003e004`
- `ntdll!EtwEventWrite` at `0x18003e03d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003df14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003df71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dfc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e046`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003df14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003df71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dfc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e00c`

## pseudocode

```c
HTRANSFORM __stdcall CreateMultiProfileTransform(
        PHPROFILE pahProfiles,
        DWORD nProfiles,
        PDWORD padwIntent,
        DWORD nIntents,
        DWORD dwFlags,
        DWORD indexPreferredCMM)
{
  __int64 FPU; // r15
  unsigned int v9; // edi
  __int64 i; // r8
  DWORD v11; // r9d
  HPROFILE v12; // rcx
  __int64 v13; // rbx
  unsigned __int32 v14; // r10d
  __int64 v15; // r11
  __int64 v16; // r11
  DWORD v17; // ecx
  __int64 PreferredCMM; // rbx
  __int64 HeapObject; // rax
  __int64 v20; // rdi
  unsigned __int64 v21; // rax
  _DWORD *v22; // rcx
  DWORD v24; // [rsp+30h] [rbp-59h] BYREF
  DWORD v25; // [rsp+38h] [rbp-51h] BYREF
  DWORD v26; // [rsp+40h] [rbp-49h] BYREF
  __int64 v27; // [rsp+48h] [rbp-41h] BYREF
  DWORD dwErrCode; // [rsp+50h] [rbp-39h] BYREF
  DWORD *p_dwErrCode; // [rsp+58h] [rbp-31h] BYREF
  __int64 v30; // [rsp+60h] [rbp-29h]
  _QWORD v31[6]; // [rsp+68h] [rbp-21h] BYREF

  v26 = dwFlags;
  v31[0] = &v25;
  v25 = nProfiles;
  v31[2] = &v24;
  v24 = nIntents;
  v31[4] = &v26;
  v27 = 0;
  v31[1] = 4;
  v31[3] = 4;
  v31[5] = 4;
  EtwEventWrite(g_etwHandle, CREATING_MULTI_PROFILE_TRANSFORM, 3, v31);
  if ( v25 && indexPreferredCMM <= v25 && pahProfiles && padwIntent && (v24 == v25 || v24 == v25 - 1 || v24 == 1) )
  {
    FPU = CreateFPU();
    if ( !FPU )
      goto LABEL_41;
    v9 = v25;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v11 = v26;
      if ( (unsigned int)i >= v9 )
        break;
      v12 = pahProfiles[i];
      if ( v12 && (unsigned int)ValidHandle(v12, 1129860428) )
        goto LABEL_37;
    }
    if ( (v26 & 0x200000) != 0 )
    {
LABEL_37:
      v27 = CITECreateMultiProfileTransform((_DWORD)pahProfiles, v9, (_DWORD)padwIntent, v24, v11);
      goto LABEL_41;
    }
    if ( v24 == v9 || v24 == 1 )
    {
      v13 = 0;
      v14 = 1466527264;
      while ( (unsigned int)v13 < v9 )
      {
        if ( !pahProfiles[v13] || !(unsigned int)ValidHandle(pahProfiles[v13], 1347569228) )
          goto LABEL_39;
        if ( !ValidProfile(v15 ^ 0x49434D20) )
        {
          v17 = 2011;
          goto LABEL_40;
        }
        v13 = (unsigned int)(v13 + 1);
        if ( (_DWORD)v13 == indexPreferredCMM )
          v14 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v16 + 56) + 4LL));
      }
      if ( !indexPreferredCMM )
      {
        PreferredCMM = GetPreferredCMM();
        if ( PreferredCMM )
        {
LABEL_31:
          HeapObject = AllocateHeapObject(1481003597);
          v27 = HeapObject;
          if ( HeapObject )
          {
            v20 = HeapObject ^ 0x49434D20;
            *(_QWORD *)(v20 + 8) = PreferredCMM;
            *(_DWORD *)(v20 + 4) = 1;
            v21 = (*(__int64 (__fastcall **)(PHPROFILE, _QWORD, PDWORD, _QWORD, DWORD))(PreferredCMM + 72))(
                    pahProfiles,
                    v25,
                    padwIntent,
                    v24,
                    v26);
            *(_QWORD *)(v20 + 16) = v21;
            if ( v21 <= 0xFF )
            {
              if ( !GetLastError() )
                SetLastError(0x7DBu);
              ReleaseColorMatchingModule(*(_QWORD *)(v20 + 8));
              --*(_DWORD *)(v20 + 4);
              v22 = (_DWORD *)(v27 ^ 0x49434D20);
              *v22 = 0;
              MemFree(v22);
              v27 = 0;
            }
          }
          else
          {
            SetLastError(8u);
            ReleaseColorMatchingModule(PreferredCMM);
          }
          goto LABEL_41;
        }
        v14 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(((unsigned __int64)pahProfiles[v25 - 1] ^ 0x49434D20) + 0x38) + 4LL));
      }
      PreferredCMM = GetColorMatchingModule(v14);
      if ( !PreferredCMM )
      {
        PreferredCMM = GetColorMatchingModule(1466527264);
        if ( !PreferredCMM )
        {
          v17 = 2010;
          goto LABEL_40;
        }
      }
      goto LABEL_31;
    }
  }
  else
  {
    FPU = 0;
  }
LABEL_39:
  v17 = 87;
LABEL_40:
  SetLastError(v17);
LABEL_41:
  DeleteFPU(FPU);
  if ( v27 )
  {
    p_dwErrCode = (DWORD *)&v27;
    v30 = 8;
    EtwEventWrite(g_etwHandle, CREATED_COLOR_TRANSFORM, 1, &p_dwErrCode);
  }
  else
  {
    dwErrCode = GetLastError();
    v30 = 4;
    p_dwErrCode = &dwErrCode;
    EtwEventWrite(g_etwHandle, COLOR_TRANSFORM_CREATION_FAILED, 1, &p_dwErrCode);
    SetLastError(dwErrCode);
  }
  return (HTRANSFORM)v27;
}

```

## disassembly

```asm
0x18003dd20  push    rbp
0x18003dd22  push    rbx
0x18003dd23  push    rsi
0x18003dd24  push    rdi
0x18003dd25  push    r12
0x18003dd27  push    r15
0x18003dd29  lea     rbp, [rsp-1Fh]
0x18003dd2e  sub     rsp, 0A8h
0x18003dd35  mov     rax, cs:__security_cookie
0x18003dd3c  xor     rax, rsp
0x18003dd3f  mov     [rbp+47h+var_38], rax
0x18003dd43  mov     eax, [rbp+47h+dwFlags]
0x18003dd46  mov     r12, r8
0x18003dd49  mov     [rbp+47h+var_90], eax
0x18003dd4c  mov     rsi, rcx
0x18003dd4f  mov     rcx, cs:g_etwHandle
0x18003dd56  lea     rax, [rbp+47h+var_98]
0x18003dd5a  mov     [rbp+47h+var_68], rax
0x18003dd5e  mov     r8d, 3
0x18003dd64  lea     rax, [rbp+47h+var_A0]
0x18003dd68  mov     [rbp+47h+var_98], edx
0x18003dd6b  mov     [rbp+47h+var_58], rax
0x18003dd6f  lea     rdx, CREATING_MULTI_PROFILE_TRANSFORM
0x18003dd76  lea     rax, [rbp+47h+var_90]
0x18003dd7a  mov     [rbp+47h+var_A0], r9d
0x18003dd7e  lea     r9, [rbp+47h+var_68]
0x18003dd82  mov     [rbp+47h+var_48], rax
0x18003dd86  mov     [rbp+47h+var_88], 0
0x18003dd8e  mov     [rbp+47h+var_60], 4
0x18003dd96  mov     [rbp+47h+var_50], 4
0x18003dd9e  mov     [rbp+47h+var_40], 4
0x18003dda6  call    cs:__imp_EtwEventWrite
0x18003ddac  mov     eax, [rbp+47h+var_98]
0x18003ddaf  cmp     eax, 1
0x18003ddb2  jb      loc_18003DFBF
0x18003ddb8  cmp     [rbp+47h+indexPreferredCMM], eax
0x18003ddbb  ja      loc_18003DFBF
0x18003ddc1  test    rsi, rsi
0x18003ddc4  jz      loc_18003DFBF
0x18003ddca  test    r12, r12
0x18003ddcd  jz      loc_18003DFBF
0x18003ddd3  mov     ecx, [rbp+47h+var_A0]
0x18003ddd6  cmp     ecx, eax
0x18003ddd8  jz      short loc_18003DDE9
0x18003ddda  dec     eax
0x18003dddc  cmp     ecx, eax
0x18003ddde  jz      short loc_18003DDE9
0x18003dde0  cmp     ecx, 1
0x18003dde3  jnz     loc_18003DFBF
0x18003dde9  call    CreateFPU
0x18003ddee  mov     r15, rax
0x18003ddf1  test    rax, rax
0x18003ddf4  jz      loc_18003DFCD
0x18003ddfa  mov     edi, [rbp+47h+var_98]
0x18003ddfd  xor     r8d, r8d
0x18003de00  mov     r9d, [rbp+47h+var_90]
0x18003de04  cmp     r8d, edi
0x18003de07  jnb     short loc_18003DE29
0x18003de09  mov     rcx, [rsi+r8*8]
0x18003de0d  test    rcx, rcx
0x18003de10  jz      short loc_18003DE24
0x18003de12  mov     edx, 43584D4Ch
0x18003de17  call    ValidHandle
0x18003de1c  test    eax, eax
0x18003de1e  jnz     loc_18003DFA3
0x18003de24  inc     r8d
0x18003de27  jmp     short loc_18003DE00
0x18003de29  bt      r9d, 15h
0x18003de2e  jb      loc_18003DFA3
0x18003de34  cmp     [rbp+47h+var_A0], edi
0x18003de37  jz      short loc_18003DE43
0x18003de39  cmp     [rbp+47h+var_A0], 1
0x18003de3d  jnz     loc_18003DFC2
0x18003de43  xor     ebx, ebx
0x18003de45  mov     r10d, 57696E20h
0x18003de4b  cmp     ebx, edi
0x18003de4d  jnb     short loc_18003DEA2
0x18003de4f  mov     r11, [rsi+rbx*8]
0x18003de53  test    r11, r11
0x18003de56  jz      loc_18003DFC2
0x18003de5c  mov     edx, 5052464Ch
0x18003de61  mov     rcx, r11
0x18003de64  call    ValidHandle
0x18003de69  test    eax, eax
0x18003de6b  jz      loc_18003DFC2
0x18003de71  xor     r11, 49434D20h
0x18003de78  mov     rcx, r11
0x18003de7b  call    ValidProfile
0x18003de80  test    eax, eax
0x18003de82  jz      short loc_18003DE98
0x18003de84  inc     ebx
0x18003de86  cmp     ebx, [rbp+47h+indexPreferredCMM]
0x18003de89  jnz     short loc_18003DE4B
0x18003de8b  mov     rax, [r11+38h]
0x18003de8f  mov     r10d, [rax+4]
0x18003de93  bswap   r10d
0x18003de96  jmp     short loc_18003DE4B
0x18003de98  mov     ecx, 7DBh
0x18003de9d  jmp     loc_18003DFC7
0x18003dea2  cmp     [rbp+47h+indexPreferredCMM], 0
0x18003dea6  jnz     short loc_18003DECF
0x18003dea8  call    GetPreferredCMM
0x18003dead  mov     rbx, rax
0x18003deb0  test    rax, rax
0x18003deb3  jnz     short loc_18003DEFB
0x18003deb5  mov     eax, [rbp+47h+var_98]
0x18003deb8  dec     eax
0x18003deba  mov     rax, [rsi+rax*8]
0x18003debe  xor     rax, 49434D20h
0x18003dec4  mov     rax, [rax+38h]
0x18003dec8  mov     r10d, [rax+4]
0x18003decc  bswap   r10d
0x18003decf  mov     ecx, r10d
0x18003ded2  call    GetColorMatchingModule
0x18003ded7  mov     rbx, rax
0x18003deda  test    rax, rax
0x18003dedd  jnz     short loc_18003DEFB
0x18003dedf  mov     ecx, 57696E20h
0x18003dee4  call    GetColorMatchingModule
0x18003dee9  mov     rbx, rax
0x18003deec  test    rax, rax
0x18003deef  jnz     short loc_18003DEFB
0x18003def1  mov     ecx, 7DAh
0x18003def6  jmp     loc_18003DFC7
0x18003defb  mov     ecx, 5846524Dh
0x18003df00  call    AllocateHeapObject
0x18003df05  mov     [rbp+47h+var_88], rax
0x18003df09  mov     rdi, rax
0x18003df0c  test    rax, rax
0x18003df0f  jnz     short loc_18003DF27
0x18003df11  lea     ecx, [rax+8]; dwErrCode
0x18003df14  call    cs:__imp_SetLastError
0x18003df1a  mov     rcx, rbx
0x18003df1d  call    ReleaseColorMatchingModule
0x18003df22  jmp     loc_18003DFCD
0x18003df27  xor     rdi, 49434D20h
0x18003df2e  mov     r8, r12
0x18003df31  mov     rcx, rsi
0x18003df34  mov     [rdi+8], rbx
0x18003df38  mov     dword ptr [rdi+4], 1
0x18003df3f  mov     edx, [rbp+47h+var_90]
0x18003df42  mov     r9d, [rbp+47h+var_A0]
0x18003df46  mov     rax, [rbx+48h]
0x18003df4a  mov     [rsp+0D0h+var_B0], edx
0x18003df4e  mov     edx, [rbp+47h+var_98]
0x18003df51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df56  mov     [rdi+10h], rax
0x18003df5a  cmp     rax, 0FFh
0x18003df60  ja      short loc_18003DFCD
0x18003df62  call    cs:__imp_GetLastError
0x18003df68  test    eax, eax
0x18003df6a  jnz     short loc_18003DF77
0x18003df6c  mov     ecx, 7DBh; dwErrCode
0x18003df71  call    cs:__imp_SetLastError
0x18003df77  mov     rcx, [rdi+8]
0x18003df7b  call    ReleaseColorMatchingModule
0x18003df80  dec     dword ptr [rdi+4]
0x18003df83  mov     rcx, [rbp+47h+var_88]
0x18003df87  xor     rcx, 49434D20h; lpMem
0x18003df8e  mov     dword ptr [rcx], 0
0x18003df94  call    MemFree
0x18003df99  mov     [rbp+47h+var_88], 0
0x18003dfa1  jmp     short loc_18003DFCD
0x18003dfa3  mov     [rsp+0D0h+var_B0], r9d
0x18003dfa8  mov     r8, r12
0x18003dfab  mov     r9d, [rbp+47h+var_A0]
0x18003dfaf  mov     edx, edi
0x18003dfb1  mov     rcx, rsi
0x18003dfb4  call    CITECreateMultiProfileTransform
0x18003dfb9  mov     [rbp+47h+var_88], rax
0x18003dfbd  jmp     short loc_18003DFCD
0x18003dfbf  xor     r15d, r15d
0x18003dfc2  mov     ecx, 57h ; 'W'; dwErrCode
0x18003dfc7  call    cs:__imp_SetLastError
0x18003dfcd  mov     rcx, r15
0x18003dfd0  call    DeleteFPU
0x18003dfd5  cmp     [rbp+47h+var_88], 0
0x18003dfda  jz      short loc_18003E00C
0x18003dfdc  mov     rcx, cs:g_etwHandle
0x18003dfe3  lea     rax, [rbp+47h+var_88]
0x18003dfe7  lea     r9, [rbp+47h+var_78]
0x18003dfeb  mov     [rbp+47h+var_78], rax
0x18003dfef  mov     r8d, 1
0x18003dff5  mov     [rbp+47h+var_70], 8
0x18003dffd  lea     rdx, CREATED_COLOR_TRANSFORM
0x18003e004  call    cs:__imp_EtwEventWrite
0x18003e00a  jmp     short loc_18003E04C
0x18003e00c  call    cs:__imp_GetLastError
0x18003e012  mov     rcx, cs:g_etwHandle
0x18003e019  lea     r9, [rbp+47h+var_78]
0x18003e01d  mov     [rbp+47h+dwErrCode], eax
0x18003e020  lea     rdx, COLOR_TRANSFORM_CREATION_FAILED
0x18003e027  lea     rax, [rbp+47h+dwErrCode]
0x18003e02b  mov     [rbp+47h+var_70], 4
0x18003e033  mov     r8d, 1
0x18003e039  mov     [rbp+47h+var_78], rax
0x18003e03d  call    cs:__imp_EtwEventWrite
0x18003e043  mov     ecx, [rbp+47h+dwErrCode]; dwErrCode
0x18003e046  call    cs:__imp_SetLastError
0x18003e04c  mov     rax, [rbp+47h+var_88]
0x18003e050  mov     rcx, [rbp+47h+var_38]
0x18003e054  xor     rcx, rsp; StackCookie
0x18003e057  call    __security_check_cookie
0x18003e05c  add     rsp, 0A8h
0x18003e063  pop     r15
0x18003e065  pop     r12
0x18003e067  pop     rdi
0x18003e068  pop     rsi
0x18003e069  pop     rbx
0x18003e06a  pop     rbp
0x18003e06b  retn
```
