# IsWindowProtected(HWND__ *,int *)

- ea: `0x18001a09c`
- end: `0x18001a1e3`
- name: `?IsWindowProtected@@YAJPEAUHWND__@@PEAH@Z`
- size: `327`
- prototype: `__int64 __fastcall(HWND hWnd, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180019b70`
- `0x18001c440`

## callees

- `0x1800046c8`
- `0x180017358`
- `0x18001a09c`
- `0x1800385a0`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a12e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a12e`
- `USER32!GetPropW` at `0x18001a140`
- `USER32!GetPropW` at `0x18001a153`
- `USER32!GetPropW` at `0x18001a166`
- `USER32!GetPropW` at `0x18001a140`
- `USER32!GetPropW` at `0x18001a153`
- `USER32!GetPropW` at `0x18001a166`
- `USER32!GetWindowThreadProcessId` at `0x18001a0e6`
- `USER32!GetWindowThreadProcessId` at `0x18001a0e6`

## string_xrefs

- `0x18001a136`: `RM_ProcessId`
- `0x18001a146`: `RM_ThreadId`

## pseudocode

```c
__int64 __fastcall IsWindowProtected(HWND hWnd, int *a2)
{
  HANDLE WindowThreadProcessId; // r15
  DRMOS *v5; // rcx
  int v6; // ebx
  const unsigned __int16 *v7; // r9
  void *v8; // rax
  HANDLE PropW; // r14
  HANDLE v10; // rbp
  HANDLE v11; // rax
  int v12; // ecx
  DWORD dwProcessId[4]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v15[264]; // [rsp+30h] [rbp-248h] BYREF

  _RTLTRACE("[msdrm]:+IsWindowProtected hwnd = %x\n", (_DWORD)hWnd);
  dwProcessId[0] = 0;
  WindowThreadProcessId = (HANDLE)GetWindowThreadProcessId(hWnd, dwProcessId);
  v6 = StringCchPrintfW(v15, 0x104u, L"DRMRegisterContent_%lu", dwProcessId[0]);
  if ( v6 >= 0 )
  {
    v8 = DRMOS::OpenEventA(v5, 0, (int)v15, v7);
    if ( v8 )
    {
      *a2 = 1;
      CloseHandle(v8);
    }
    else
    {
      PropW = GetPropW(hWnd, L"RM_ProcessId");
      v10 = GetPropW(hWnd, L"RM_ThreadId");
      v11 = GetPropW(hWnd, L"RM_EnvHandle");
      if ( PropW || v10 || v11 )
      {
        *a2 = 1;
        if ( v11 && (HANDLE)dwProcessId[0] == PropW )
        {
          v12 = v6;
          if ( WindowThreadProcessId != v10 )
            v12 = -2147168394;
          v6 = v12;
        }
        else
        {
          v6 = -2147168394;
        }
      }
    }
  }
  _RTLTRACE("[msdrm]:-IsWindowProtected hwnd = %x, HR = %x, protected = %d\n", (_DWORD)hWnd, v6, *a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a09c  mov     [rsp+arg_10], rbx
0x18001a0a1  push    rbp
0x18001a0a2  push    rsi
0x18001a0a3  push    rdi
0x18001a0a4  push    r14
0x18001a0a6  push    r15
0x18001a0a8  sub     rsp, 250h
0x18001a0af  mov     rax, cs:__security_cookie
0x18001a0b6  xor     rax, rsp
0x18001a0b9  mov     [rsp+278h+var_38], rax
0x18001a0c1  mov     rdi, rdx
0x18001a0c4  mov     rsi, rcx
0x18001a0c7  mov     rdx, rcx
0x18001a0ca  lea     rcx, aMsdrmIswindowp_0; "[msdrm]:+IsWindowProtected hwnd = %x\n"
0x18001a0d1  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001a0d6  lea     rdx, [rsp+278h+dwProcessId]; lpdwProcessId
0x18001a0db  mov     [rsp+278h+dwProcessId], 0
0x18001a0e3  mov     rcx, rsi; hWnd
0x18001a0e6  call    cs:__imp_GetWindowThreadProcessId
0x18001a0ec  mov     r9d, [rsp+278h+dwProcessId]
0x18001a0f1  lea     r8, ?g_wszDRMRegisterContentEventName@@3QBGB; "DRMRegisterContent_%lu"
0x18001a0f8  mov     edx, 104h; unsigned __int64
0x18001a0fd  mov     r15d, eax
0x18001a100  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x18001a105  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a10a  mov     ebx, eax
0x18001a10c  test    eax, eax
0x18001a10e  js      loc_18001A1A5
0x18001a114  lea     r8, [rsp+278h+var_248]; int
0x18001a119  xor     edx, edx; unsigned int
0x18001a11b  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x18001a120  test    rax, rax
0x18001a123  jz      short loc_18001A136
0x18001a125  mov     rcx, rax; hObject
0x18001a128  mov     dword ptr [rdi], 1
0x18001a12e  call    cs:__imp_CloseHandle
0x18001a134  jmp     short loc_18001A1A5
0x18001a136  lea     rdx, String; "RM_ProcessId"
0x18001a13d  mov     rcx, rsi; hWnd
0x18001a140  call    cs:__imp_GetPropW
0x18001a146  lea     rdx, aRmThreadid; "RM_ThreadId"
0x18001a14d  mov     rcx, rsi; hWnd
0x18001a150  mov     r14, rax
0x18001a153  call    cs:__imp_GetPropW
0x18001a159  lea     rdx, aRmEnvhandle; "RM_EnvHandle"
0x18001a160  mov     rcx, rsi; hWnd
0x18001a163  mov     rbp, rax
0x18001a166  call    cs:__imp_GetPropW
0x18001a16c  test    r14, r14
0x18001a16f  jnz     short loc_18001A17B
0x18001a171  test    rbp, rbp
0x18001a174  jnz     short loc_18001A17B
0x18001a176  test    rax, rax
0x18001a179  jz      short loc_18001A1A5
0x18001a17b  mov     dword ptr [rdi], 1
0x18001a181  test    rax, rax
0x18001a184  jnz     short loc_18001A18D
0x18001a186  mov     ebx, 8004CF76h
0x18001a18b  jmp     short loc_18001A1A5
0x18001a18d  mov     eax, [rsp+278h+dwProcessId]
0x18001a191  cmp     rax, r14
0x18001a194  jnz     short loc_18001A186
0x18001a196  mov     ecx, ebx
0x18001a198  cmp     r15, rbp
0x18001a19b  mov     ebx, 8004CF76h
0x18001a1a0  cmovnz  ecx, ebx
0x18001a1a3  mov     ebx, ecx
0x18001a1a5  mov     r9d, [rdi]
0x18001a1a8  lea     rcx, aMsdrmIswindowp; "[msdrm]:-IsWindowProtected hwnd = %x, H"...
0x18001a1af  mov     r8d, ebx
0x18001a1b2  mov     rdx, rsi
0x18001a1b5  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001a1ba  mov     eax, ebx
0x18001a1bc  mov     rcx, [rsp+278h+var_38]
0x18001a1c4  xor     rcx, rsp; StackCookie
0x18001a1c7  call    __security_check_cookie
0x18001a1cc  mov     rbx, [rsp+278h+arg_10]
0x18001a1d4  add     rsp, 250h
0x18001a1db  pop     r15
0x18001a1dd  pop     r14
0x18001a1df  pop     rdi
0x18001a1e0  pop     rsi
0x18001a1e1  pop     rbp
0x18001a1e2  retn
```
