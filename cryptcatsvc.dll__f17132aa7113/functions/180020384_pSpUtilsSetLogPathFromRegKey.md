# pSpUtilsSetLogPathFromRegKey

- ea: `0x180020384`
- end: `0x180020508`
- name: `pSpUtilsSetLogPathFromRegKey`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001fd5c`

## callees

- `0x180007188`
- `0x18000be40`
- `0x18000c280`
- `0x180020148`
- `0x180020228`
- `0x180020384`
- `0x180020a14`
- `0x180020df4`
- `0x180021124`
- `0x180021288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020449`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180020413`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180020413`

## pseudocode

```c
_BOOL8 pSpUtilsSetLogPathFromRegKey()
{
  DWORD OverrideValue; // ebx
  __int64 v1; // r8
  __int64 v2; // r9
  DWORD v3; // eax
  __int64 v5; // rdi
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v7; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Dst[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src[264]; // [rsp+260h] [rbp+160h] BYREF

  LODWORD(v8) = 520;
  KeyHandle = 0;
  v7 = 0;
  OverrideValue = pSpUtilsOpenSetupKey(&KeyHandle, &v7);
  if ( OverrideValue )
    goto LABEL_9;
  OverrideValue = pSpUtilsQueryOverrideValue(KeyHandle, v7, v1, v2, (__int64)Src, (int *)&v8);
  if ( !OverrideValue )
  {
    v3 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
    if ( v3 )
    {
      if ( v3 > 0x104 )
      {
        OverrideValue = 122;
        goto LABEL_5;
      }
      v5 = -1;
      do
        ++v5;
      while ( Dst[v5] );
      if ( (unsigned int)pSetupConcatenatePaths(Dst, L"setupapi.dev.log", 260) )
      {
        OverrideValue = pSetupMakeSurePathExists(Dst);
        if ( OverrideValue )
          goto LABEL_5;
        if ( 2 * (unsigned __int64)(unsigned int)v5 >= 0x208 )
          _report_rangecheckfailure();
        Dst[(unsigned int)v5] = 0;
        if ( (unsigned int)pSpUtilsSetTextLogPath(Dst) )
        {
          if ( (unsigned int)pSpUtilsLogSetPath(Dst) )
            goto LABEL_5;
        }
      }
    }
    OverrideValue = GetLastError();
  }
LABEL_5:
  if ( KeyHandle )
    pSetupCloseKey(KeyHandle);
  if ( v7 )
    pSetupCloseKey(v7);
LABEL_9:
  SetLastError(OverrideValue);
  return OverrideValue == 0;
}

```

## disassembly

```asm
0x180020384  push    rbp
0x180020386  push    rbx
0x180020387  push    rdi
0x180020388  push    r15
0x18002038a  lea     rbp, [rsp-388h]
0x180020392  sub     rsp, 488h
0x180020399  mov     rax, cs:__security_cookie
0x1800203a0  xor     rax, rsp
0x1800203a3  mov     [rbp+3A0h+var_30], rax
0x1800203aa  xor     r15d, r15d
0x1800203ad  mov     dword ptr [rsp+4A0h+var_460], 208h
0x1800203b5  lea     rdx, [rsp+4A0h+var_468]
0x1800203ba  mov     [rsp+4A0h+KeyHandle], r15
0x1800203bf  lea     rcx, [rsp+4A0h+KeyHandle]
0x1800203c4  mov     [rsp+4A0h+var_468], r15
0x1800203c9  call    pSpUtilsOpenSetupKey
0x1800203ce  mov     ebx, eax
0x1800203d0  test    eax, eax
0x1800203d2  jnz     short loc_180020447
0x1800203d4  mov     rdx, [rsp+4A0h+var_468]; HANDLE
0x1800203d9  lea     rax, [rsp+4A0h+var_460]
0x1800203de  mov     rcx, [rsp+4A0h+KeyHandle]; KeyHandle
0x1800203e3  mov     [rsp+4A0h+var_478], rax; __int64
0x1800203e8  lea     rax, [rbp+3A0h+Src]
0x1800203ef  mov     [rsp+4A0h+var_480], rax; __int64
0x1800203f4  call    pSpUtilsQueryOverrideValue
0x1800203f9  mov     ebx, eax
0x1800203fb  test    eax, eax
0x1800203fd  jnz     short loc_180020425
0x1800203ff  mov     ebx, 104h
0x180020404  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x180020409  mov     r8d, ebx; nSize
0x18002040c  lea     rcx, [rbp+3A0h+Src]; lpSrc
0x180020413  call    cs:__imp_ExpandEnvironmentStringsW
0x180020419  test    eax, eax
0x18002041b  jnz     short loc_180020473
0x18002041d  call    cs:__imp_GetLastError
0x180020423  mov     ebx, eax
0x180020425  cmp     [rsp+4A0h+KeyHandle], r15
0x18002042a  jz      short loc_180020436
0x18002042c  mov     rcx, [rsp+4A0h+KeyHandle]
0x180020431  call    pSetupCloseKey
0x180020436  cmp     [rsp+4A0h+var_468], r15
0x18002043b  jz      short loc_180020447
0x18002043d  mov     rcx, [rsp+4A0h+var_468]
0x180020442  call    pSetupCloseKey
0x180020447  mov     ecx, ebx; dwErrCode
0x180020449  call    cs:__imp_SetLastError
0x18002044f  test    ebx, ebx
0x180020451  mov     eax, r15d
0x180020454  setz    al
0x180020457  mov     rcx, [rbp+3A0h+var_30]
0x18002045e  xor     rcx, rsp; StackCookie
0x180020461  call    __security_check_cookie
0x180020466  add     rsp, 488h
0x18002046d  pop     r15
0x18002046f  pop     rdi
0x180020470  pop     rbx
0x180020471  pop     rbp
0x180020472  retn
0x180020473  cmp     eax, ebx
0x180020475  jbe     short loc_18002047E
0x180020477  mov     ebx, 7Ah ; 'z'
0x18002047c  jmp     short loc_180020425
0x18002047e  lea     rax, [rsp+4A0h+Dst]
0x180020483  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020487  inc     rdi
0x18002048a  cmp     [rax+rdi*2], r15w
0x18002048f  jnz     short loc_180020487
0x180020491  mov     r8d, ebx
0x180020494  lea     rdx, aSetupapiDevLog; "setupapi.dev.log"
0x18002049b  lea     rcx, [rsp+4A0h+Dst]
0x1800204a0  call    pSetupConcatenatePaths
0x1800204a5  test    eax, eax
0x1800204a7  jz      loc_18002041D
0x1800204ad  lea     rcx, [rsp+4A0h+Dst]
0x1800204b2  call    pSetupMakeSurePathExists
0x1800204b7  mov     ebx, eax
0x1800204b9  test    eax, eax
0x1800204bb  jnz     loc_180020425
0x1800204c1  mov     eax, edi
0x1800204c3  lea     rcx, [rax+rax]
0x1800204c7  cmp     rcx, 208h
0x1800204ce  jnb     short loc_180020502
0x1800204d0  mov     [rsp+rcx+4A0h+Dst], r15w
0x1800204d6  lea     edx, [rbx+1]
0x1800204d9  lea     rcx, [rsp+4A0h+Dst]; pszSrc
0x1800204de  call    _pSpUtilsSetTextLogPath
0x1800204e3  test    eax, eax
0x1800204e5  jz      loc_18002041D
0x1800204eb  lea     rcx, [rsp+4A0h+Dst]; pszSrc
0x1800204f0  call    _pSpUtilsLogSetPath
0x1800204f5  test    eax, eax
0x1800204f7  jnz     loc_180020425
0x1800204fd  jmp     loc_18002041D
0x180020502  call    __report_rangecheckfailure
```
