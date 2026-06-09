# SaferValidate(ushort const *)

- ea: `0x18002ba80`
- end: `0x18002bc35`
- name: `?SaferValidate@@YAKPEBG@Z`
- size: `437`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002f250`

## callees

- `0x18002a7c8`
- `0x18002ba80`
- `0x180041ac0`
- `0x180045020`
- `0x180045030`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002bad4`
- `KERNEL32!GetProcAddress` at `0x18002bae7`
- `KERNEL32!GetProcAddress` at `0x18002bafa`
- `KERNEL32!GetProcAddress` at `0x18002bb0d`
- `KERNEL32!GetProcAddress` at `0x18002bad4`
- `KERNEL32!GetProcAddress` at `0x18002bae7`
- `KERNEL32!GetProcAddress` at `0x18002bafa`
- `KERNEL32!GetProcAddress` at `0x18002bb0d`
- `KERNEL32!SetLastError` at `0x18002bbd9`
- `KERNEL32!SetLastError` at `0x18002bbd9`
- `KERNEL32!LoadLibraryW` at `0x18002baad`
- `KERNEL32!LoadLibraryW` at `0x18002baad`

## string_xrefs

- `0x18002baa6`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall SaferValidate(const unsigned __int16 *a1)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // r15
  FARPROC v6; // r14
  FARPROC v7; // rdi
  FARPROC v8; // rax
  void (__fastcall *v9)(_QWORD, _QWORD, _QWORD); // rbx
  unsigned int v10; // ebx
  int v11; // [rsp+30h] [rbp-99h] BYREF
  __int64 v12; // [rsp+38h] [rbp-91h] BYREF
  int v13; // [rsp+40h] [rbp-89h]
  _DWORD v14[2]; // [rsp+50h] [rbp-79h] BYREF
  const unsigned __int16 *v15; // [rsp+58h] [rbp-71h]
  _BYTE v16[128]; // [rsp+60h] [rbp-69h] BYREF

  LibraryW = LoadLibraryW(L"advapi32.dll");
  v3 = LibraryW;
  if ( !LibraryW )
    return (unsigned int)HRESULT_FROM_GetLastError() | 0xC0000000;
  ProcAddress = GetProcAddress(LibraryW, "SaferIdentifyLevel");
  v6 = GetProcAddress(v3, "SaferGetLevelInformation");
  v7 = GetProcAddress(v3, "SaferCloseLevel");
  v8 = GetProcAddress(v3, "SaferRecordEventLogEntry");
  v9 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))v8;
  if ( !ProcAddress || !v6 || !v7 || !v8 )
    return 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  memset_thunk_772440563353939046(v16, 0, 0x78u);
  v14[0] = 136;
  v14[1] = 5;
  v15 = a1;
  if ( ((unsigned int (__fastcall *)(__int64, _DWORD *, __int64 *))ProcAddress)(1, v14, &v12) )
  {
    if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))v6)(v12, 1, &v11) )
    {
      if ( v11 )
      {
        v10 = 0;
      }
      else
      {
        v9(v12, a1, 0);
        SetLastError(0x4ECu);
        v10 = -1073740958;
      }
    }
    else
    {
      v10 = HRESULT_FROM_GetLastError() | 0xC0000000;
    }
    ((void (__fastcall *)(__int64))v7)(v12);
  }
  else
  {
    return (unsigned int)HRESULT_FROM_GetLastError() | 0xC0000000;
  }
  return v10;
}

```

## disassembly

```asm
0x18002ba80  push    rbp
0x18002ba82  push    rbx
0x18002ba83  push    rsi
0x18002ba84  push    rdi
0x18002ba85  push    r14
0x18002ba87  push    r15
0x18002ba89  lea     rbp, [rsp-2Fh]
0x18002ba8e  sub     rsp, 0F8h
0x18002ba95  mov     rax, cs:__security_cookie
0x18002ba9c  xor     rax, rsp
0x18002ba9f  mov     [rbp+57h+var_40], rax
0x18002baa3  mov     rsi, rcx
0x18002baa6  lea     rcx, LibFileName; "advapi32.dll"
0x18002baad  call    cs:__imp_LoadLibraryW
0x18002bab3  mov     rbx, rax
0x18002bab6  test    rax, rax
0x18002bab9  jnz     short loc_18002BACA
0x18002babb  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002bac0  or      eax, 0C0000000h
0x18002bac5  jmp     loc_18002BC19
0x18002baca  lea     rdx, aSaferidentifyl; "SaferIdentifyLevel"
0x18002bad1  mov     rcx, rbx; hModule
0x18002bad4  call    cs:__imp_GetProcAddress
0x18002bada  lea     rdx, aSafergetleveli; "SaferGetLevelInformation"
0x18002bae1  mov     rcx, rbx; hModule
0x18002bae4  mov     r15, rax
0x18002bae7  call    cs:__imp_GetProcAddress
0x18002baed  lea     rdx, aSafercloseleve; "SaferCloseLevel"
0x18002baf4  mov     rcx, rbx; hModule
0x18002baf7  mov     r14, rax
0x18002bafa  call    cs:__imp_GetProcAddress
0x18002bb00  lea     rdx, aSaferrecordeve; "SaferRecordEventLogEntry"
0x18002bb07  mov     rcx, rbx; hModule
0x18002bb0a  mov     rdi, rax
0x18002bb0d  call    cs:__imp_GetProcAddress
0x18002bb13  mov     rbx, rax
0x18002bb16  test    r15, r15
0x18002bb19  jz      loc_18002BC17
0x18002bb1f  test    r14, r14
0x18002bb22  jz      loc_18002BC17
0x18002bb28  test    rdi, rdi
0x18002bb2b  jz      loc_18002BC17
0x18002bb31  test    rax, rax
0x18002bb34  jz      loc_18002BC17
0x18002bb3a  xor     edx, edx; Val
0x18002bb3c  mov     [rsp+120h+var_E8], 0
0x18002bb45  lea     rcx, [rbp+57h+var_C0]; void *
0x18002bb49  mov     [rsp+120h+var_F0], 0
0x18002bb51  mov     [rsp+120h+var_E0], 0
0x18002bb59  lea     r8d, [rdx+78h]; Size
0x18002bb5d  call    memset$thunk$772440563353939046
0x18002bb62  xor     r9d, r9d
0x18002bb65  mov     [rbp+57h+var_D0], 88h
0x18002bb6c  lea     r8, [rsp+120h+var_E8]
0x18002bb71  mov     [rbp+57h+var_CC], 5
0x18002bb78  lea     rdx, [rbp+57h+var_D0]
0x18002bb7c  mov     [rbp+57h+var_C8], rsi
0x18002bb80  mov     rax, r15
0x18002bb83  lea     ecx, [r9+1]
0x18002bb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb8c  test    eax, eax
0x18002bb8e  jz      short loc_18002BC06
0x18002bb90  mov     rcx, [rsp+120h+var_E8]
0x18002bb95  lea     rax, [rsp+120h+var_E0]
0x18002bb9a  mov     r9d, 4
0x18002bba0  mov     [rsp+120h+var_100], rax
0x18002bba5  lea     r8, [rsp+120h+var_F0]
0x18002bbaa  mov     rax, r14
0x18002bbad  lea     edx, [r9-3]
0x18002bbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbb6  test    eax, eax
0x18002bbb8  jz      short loc_18002BBEA
0x18002bbba  cmp     [rsp+120h+var_F0], 0
0x18002bbbf  jnz     short loc_18002BBE6
0x18002bbc1  mov     rcx, [rsp+120h+var_E8]
0x18002bbc6  xor     r8d, r8d
0x18002bbc9  mov     rdx, rsi
0x18002bbcc  mov     rax, rbx
0x18002bbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbd4  mov     ecx, 4ECh; dwErrCode
0x18002bbd9  call    cs:__imp_SetLastError
0x18002bbdf  mov     ebx, 0C0000362h
0x18002bbe4  jmp     short loc_18002BBF7
0x18002bbe6  xor     ebx, ebx
0x18002bbe8  jmp     short loc_18002BBF7
0x18002bbea  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002bbef  mov     ebx, eax
0x18002bbf1  or      ebx, 0C0000000h
0x18002bbf7  mov     rcx, [rsp+120h+var_E8]
0x18002bbfc  mov     rax, rdi
0x18002bbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc04  jmp     short loc_18002BC13
0x18002bc06  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002bc0b  mov     ebx, eax
0x18002bc0d  or      ebx, 0C0000000h
0x18002bc13  mov     eax, ebx
0x18002bc15  jmp     short loc_18002BC19
0x18002bc17  xor     eax, eax
0x18002bc19  mov     rcx, [rbp+57h+var_40]
0x18002bc1d  xor     rcx, rsp; StackCookie
0x18002bc20  call    __security_check_cookie
0x18002bc25  add     rsp, 0F8h
0x18002bc2c  pop     r15
0x18002bc2e  pop     r14
0x18002bc30  pop     rdi
0x18002bc31  pop     rsi
0x18002bc32  pop     rbx
0x18002bc33  pop     rbp
0x18002bc34  retn
```
