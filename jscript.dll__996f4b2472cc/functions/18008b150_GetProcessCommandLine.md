# GetProcessCommandLine

- ea: `0x18008b150`
- end: `0x18008b502`
- name: `GetProcessCommandLine`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hProcess, char *Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18008b5c0`

## callees

- `0x180058610`
- `0x18005925c`
- `0x18008b150`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!_mbstok_s` at `0x18008b3ce`
- `msvcrt!_mbstok_s` at `0x18008b45d`
- `msvcrt!_mbstok_s` at `0x18008b3ce`
- `msvcrt!_mbstok_s` at `0x18008b45d`
- `msvcrt!strcat_s` at `0x18008b40f`
- `msvcrt!strcat_s` at `0x18008b428`
- `msvcrt!strcat_s` at `0x18008b443`
- `msvcrt!strcat_s` at `0x18008b47e`
- `msvcrt!strcat_s` at `0x18008b40f`
- `msvcrt!strcat_s` at `0x18008b428`
- `msvcrt!strcat_s` at `0x18008b443`
- `msvcrt!strcat_s` at `0x18008b47e`
- `msvcrt!strcpy_s` at `0x18008b3ab`
- `msvcrt!strcpy_s` at `0x18008b49a`
- `msvcrt!strcpy_s` at `0x18008b3ab`
- `msvcrt!strcpy_s` at `0x18008b49a`
- `msvcrt!_mbsrchr` at `0x18008b3ee`
- `msvcrt!_mbsrchr` at `0x18008b3ee`
- `KERNEL32!ReadProcessMemory` at `0x18008b220`
- `KERNEL32!ReadProcessMemory` at `0x18008b26d`
- `KERNEL32!ReadProcessMemory` at `0x18008b2ee`
- `KERNEL32!ReadProcessMemory` at `0x18008b220`
- `KERNEL32!ReadProcessMemory` at `0x18008b26d`
- `KERNEL32!ReadProcessMemory` at `0x18008b2ee`
- `KERNEL32!GetModuleHandleA` at `0x18008b197`
- `KERNEL32!GetModuleHandleA` at `0x18008b197`
- `KERNEL32!GetProcAddress` at `0x18008b1b6`
- `KERNEL32!GetProcAddress` at `0x18008b1b6`
- `KERNEL32!WideCharToMultiByte` at `0x18008b32f`
- `KERNEL32!WideCharToMultiByte` at `0x18008b32f`

## string_xrefs

- `0x18008b408`: `<path>`
- `0x18008b181`: `ntdll.dll`

## pseudocode

```c
void __fastcall GetProcessCommandLine(HANDLE hProcess, char *Destination)
{
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // rbx
  WCHAR *v9; // rax
  WCHAR *v10; // r12
  rsize_t v12; // rdi
  rsize_t v13; // rsi
  char *v14; // r13
  char *v15; // rax
  char *v16; // rbx
  unsigned __int8 *v17; // rdi
  unsigned __int8 *v18; // rax
  rsize_t v19; // rdx
  char *v20; // rcx
  unsigned __int8 *v21; // r15
  const char *v22; // r8
  unsigned __int8 *Context; // [rsp+40h] [rbp-C0h] BYREF
  rsize_t SizeInBytes; // [rsp+48h] [rbp-B8h]
  LPCVOID lpBaseAddress[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h]
  __int128 v27; // [rsp+70h] [rbp-90h]
  _OWORD v28[7]; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID v29[2]; // [rsp+F0h] [rbp-10h]
  _BYTE Buffer[32]; // [rsp+100h] [rbp+0h] BYREF
  LPCVOID v31; // [rsp+120h] [rbp+20h]

  *Destination = 0;
  *(_OWORD *)lpBaseAddress = 0;
  v26 = 0;
  v27 = 0;
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  if ( ModuleHandleA )
  {
    ProcAddress = GetProcAddress(ModuleHandleA, "NtQueryInformationProcess");
    if ( ProcAddress )
    {
      if ( ((int (__fastcall *)(HANDLE, _QWORD, LPCVOID *, __int64, _QWORD))ProcAddress)(
             hProcess,
             0,
             lpBaseAddress,
             48,
             0) >= 0 )
      {
        memset_0(Buffer, 0, 0x2C8u);
        if ( ReadProcessMemory(hProcess, lpBaseAddress[1], Buffer, 0x2C8u, 0) )
        {
          memset(v28, 0, sizeof(v28));
          *(_OWORD *)v29 = 0;
          if ( ReadProcessMemory(hProcess, v31, v28, 0x80u, 0) )
          {
            if ( (unsigned __int16)(LOWORD(v29[0]) - 1) <= 0xFFEu )
            {
              v6 = ((unsigned __int64)LOWORD(v29[0]) >> 1) + 1;
              v7 = 2 * v6;
              v8 = -1;
              if ( !is_mul_ok(v6, 2u) )
                v7 = -1;
              v9 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
              v10 = v9;
              if ( v9 )
              {
                if ( ReadProcessMemory(hProcess, v29[1], v9, LOWORD(v29[0]), 0) )
                {
                  v10[(unsigned __int64)LOWORD(v29[0]) >> 1] = 0;
                  WideCharToMultiByte(0, 0, v10, -1, Destination, 512, 0, 0);
                  if ( *Destination )
                  {
                    while ( Destination[++v8] != 0 )
                      ;
                    v12 = v8 + 1;
                    SizeInBytes = v8 + 1;
                    v13 = 2 * v8;
                    v14 = (char *)operator new[](v8 + 1, (const struct std::nothrow_t *)std::nothrow);
                    v15 = (char *)operator new[](2 * v8, (const struct std::nothrow_t *)std::nothrow);
                    v16 = v15;
                    if ( v14 && v15 )
                    {
                      strcpy_s(v14, v12, Destination);
                      *v16 = 0;
                      Context = 0;
                      v17 = _mbstok_s((unsigned __int8 *)v14, " \t", &Context);
                      if ( v17 )
                      {
                        while ( 1 )
                        {
                          v18 = _mbsrchr(v17, 0x5Cu);
                          v19 = v13;
                          v20 = v16;
                          v21 = v18;
                          if ( v18 )
                          {
                            strcat_s(v16, v13, "<path>");
                            strcat_s(v16, v13, "\\");
                            v22 = (const char *)(v21 + 1);
                            v19 = v13;
                            v20 = v16;
                          }
                          else
                          {
                            v22 = (const char *)v17;
                          }
                          strcat_s(v20, v19, v22);
                          v17 = _mbstok_s(0, " \t", &Context);
                          if ( !v17 )
                            break;
                          strcat_s(v16, v13, " ");
                        }
                      }
                      strcpy_s(Destination, SizeInBytes, v16);
                    }
                    operator delete[](v14);
                    operator delete[](v16);
                  }
                }
                operator delete[](v10);
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18008b150  push    rbp
0x18008b152  push    rdi
0x18008b153  push    r14
0x18008b155  lea     rbp, [rsp-300h]
0x18008b15d  sub     rsp, 400h
0x18008b164  mov     rax, cs:__security_cookie
0x18008b16b  xor     rax, rsp
0x18008b16e  mov     [rbp+310h+var_40], rax
0x18008b175  xorps   xmm0, xmm0
0x18008b178  mov     byte ptr [rdx], 0
0x18008b17b  mov     rdi, rcx
0x18008b17e  mov     r14, rdx
0x18008b181  lea     rcx, aNtdllDll; "ntdll.dll"
0x18008b188  movups  xmmword ptr [rsp+410h+lpBaseAddress], xmm0
0x18008b18d  movups  [rsp+410h+var_3B0], xmm0
0x18008b192  movups  [rsp+410h+var_3A0], xmm0
0x18008b197  call    cs:__imp_GetModuleHandleA
0x18008b19e  nop     dword ptr [rax+rax+00h]
0x18008b1a3  test    rax, rax
0x18008b1a6  jz      loc_18008B4E6
0x18008b1ac  lea     rdx, aNtqueryinforma; "NtQueryInformationProcess"
0x18008b1b3  mov     rcx, rax; hModule
0x18008b1b6  call    cs:__imp_GetProcAddress
0x18008b1bd  nop     dword ptr [rax+rax+00h]
0x18008b1c2  test    rax, rax
0x18008b1c5  jz      loc_18008B4E6
0x18008b1cb  mov     [rsp+410h+var_30], r15
0x18008b1d3  lea     r8, [rsp+410h+lpBaseAddress]
0x18008b1d8  xor     r15d, r15d
0x18008b1db  mov     r9d, 30h ; '0'
0x18008b1e1  xor     edx, edx
0x18008b1e3  mov     [rsp+410h+lpNumberOfBytesRead], r15
0x18008b1e8  mov     rcx, rdi
0x18008b1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b1f0  test    eax, eax
0x18008b1f2  js      loc_18008B4DE
0x18008b1f8  xor     edx, edx; Val
0x18008b1fa  lea     rcx, [rbp+310h+Buffer]; void *
0x18008b1fe  mov     r8d, 2C8h; Size
0x18008b204  call    memset_0
0x18008b209  mov     rdx, [rsp+410h+lpBaseAddress+8]; lpBaseAddress
0x18008b20e  lea     r8, [rbp+310h+Buffer]; lpBuffer
0x18008b212  mov     r9d, 2C8h; nSize
0x18008b218  mov     [rsp+410h+lpNumberOfBytesRead], r15; lpNumberOfBytesRead
0x18008b21d  mov     rcx, rdi; hProcess
0x18008b220  call    cs:__imp_ReadProcessMemory
0x18008b227  nop     dword ptr [rax+rax+00h]
0x18008b22c  test    eax, eax
0x18008b22e  jz      loc_18008B4DE
0x18008b234  mov     rdx, [rbp+310h+var_2F0]; lpBaseAddress
0x18008b238  lea     r8, [rbp+310h+var_390]; lpBuffer
0x18008b23c  xorps   xmm0, xmm0
0x18008b23f  mov     [rsp+410h+lpNumberOfBytesRead], r15; lpNumberOfBytesRead
0x18008b244  mov     r9d, 80h; nSize
0x18008b24a  mov     rcx, rdi; hProcess
0x18008b24d  movups  [rbp+310h+var_390], xmm0
0x18008b251  movups  [rbp+310h+var_380], xmm0
0x18008b255  movups  [rbp+310h+var_370], xmm0
0x18008b259  movups  [rbp+310h+var_360], xmm0
0x18008b25d  movups  [rbp+310h+var_350], xmm0
0x18008b261  movups  [rbp+310h+var_340], xmm0
0x18008b265  movups  [rbp+310h+var_330], xmm0
0x18008b269  movups  xmmword ptr [rbp+310h+var_320], xmm0
0x18008b26d  call    cs:__imp_ReadProcessMemory
0x18008b274  nop     dword ptr [rax+rax+00h]
0x18008b279  test    eax, eax
0x18008b27b  jz      loc_18008B4DE
0x18008b281  movzx   ecx, word ptr [rbp+310h+var_320]
0x18008b285  mov     edx, 0FFEh
0x18008b28a  lea     eax, [rcx-1]
0x18008b28d  cmp     ax, dx
0x18008b290  ja      loc_18008B4DE
0x18008b296  shr     rcx, 1
0x18008b299  mov     eax, 2
0x18008b29e  inc     rcx
0x18008b2a1  mov     [rsp+410h+arg_10], rbx
0x18008b2a9  mul     rcx
0x18008b2ac  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18008b2b3  mov     [rsp+410h+var_20], r12
0x18008b2bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008b2c2  cmovb   rax, rbx
0x18008b2c6  mov     rcx, rax; unsigned __int64
0x18008b2c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008b2ce  mov     r12, rax
0x18008b2d1  test    rax, rax
0x18008b2d4  jz      loc_18008B4CE
0x18008b2da  movzx   r9d, word ptr [rbp+310h+var_320]; nSize
0x18008b2df  mov     r8, rax; lpBuffer
0x18008b2e2  mov     rdx, [rbp+310h+var_320+8]; lpBaseAddress
0x18008b2e6  mov     rcx, rdi; hProcess
0x18008b2e9  mov     [rsp+410h+lpNumberOfBytesRead], r15; lpNumberOfBytesRead
0x18008b2ee  call    cs:__imp_ReadProcessMemory
0x18008b2f5  nop     dword ptr [rax+rax+00h]
0x18008b2fa  test    eax, eax
0x18008b2fc  jz      loc_18008B4C6
0x18008b302  movzx   ecx, word ptr [rbp+310h+var_320]
0x18008b306  mov     r9d, ebx; cchWideChar
0x18008b309  shr     rcx, 1
0x18008b30c  mov     r8, r12; lpWideCharStr
0x18008b30f  mov     [rsp+410h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18008b314  xor     edx, edx; dwFlags
0x18008b316  mov     [rsp+410h+lpDefaultChar], r15; lpDefaultChar
0x18008b31b  mov     [rsp+410h+cbMultiByte], 200h; cbMultiByte
0x18008b323  mov     [r12+rcx*2], r15w
0x18008b328  xor     ecx, ecx; CodePage
0x18008b32a  mov     [rsp+410h+lpNumberOfBytesRead], r14; lpMultiByteStr
0x18008b32f  call    cs:__imp_WideCharToMultiByte
0x18008b336  nop     dword ptr [rax+rax+00h]
0x18008b33b  cmp     [r14], r15b
0x18008b33e  jz      loc_18008B4C6
0x18008b344  mov     [rsp+410h+var_18], rsi
0x18008b34c  mov     [rsp+410h+var_28], r13
0x18008b354  cmp     [r14+rbx+1], r15b
0x18008b359  lea     rbx, [rbx+1]
0x18008b35d  jnz     short loc_18008B354
0x18008b35f  lea     rdi, [rbx+1]
0x18008b363  mov     rcx, rdi; unsigned __int64
0x18008b366  mov     [rsp+410h+SizeInBytes], rdi
0x18008b36b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008b372  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008b377  lea     rsi, [rbx+rbx]
0x18008b37b  mov     r13, rax
0x18008b37e  mov     rcx, rsi; unsigned __int64
0x18008b381  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008b388  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008b38d  mov     rbx, rax
0x18008b390  test    r13, r13
0x18008b393  jz      loc_18008B4A6
0x18008b399  test    rax, rax
0x18008b39c  jz      loc_18008B4A6
0x18008b3a2  mov     r8, r14; Source
0x18008b3a5  mov     rdx, rdi; SizeInBytes
0x18008b3a8  mov     rcx, r13; Destination
0x18008b3ab  call    cs:__imp_strcpy_s
0x18008b3b2  nop     dword ptr [rax+rax+00h]
0x18008b3b7  mov     [rbx], r15b
0x18008b3ba  lea     r8, [rsp+410h+Context]; Context
0x18008b3bf  lea     rdx, Delim; " \t"
0x18008b3c6  mov     [rsp+410h+Context], r15
0x18008b3cb  mov     rcx, r13; Str
0x18008b3ce  call    cs:__imp__mbstok_s
0x18008b3d5  nop     dword ptr [rax+rax+00h]
0x18008b3da  mov     rdi, rax
0x18008b3dd  test    rax, rax
0x18008b3e0  jz      loc_18008B48F
0x18008b3e6  mov     edx, 5Ch ; '\'; C
0x18008b3eb  mov     rcx, rdi; String
0x18008b3ee  call    cs:__imp__mbsrchr
0x18008b3f5  nop     dword ptr [rax+rax+00h]
0x18008b3fa  mov     rdx, rsi; SizeInBytes
0x18008b3fd  mov     rcx, rbx; Destination
0x18008b400  mov     r15, rax
0x18008b403  test    rax, rax
0x18008b406  jz      short loc_18008B440
0x18008b408  lea     r8, aPath; "<path>"
0x18008b40f  call    cs:__imp_strcat_s
0x18008b416  nop     dword ptr [rax+rax+00h]
0x18008b41b  lea     r8, asc_1800AA244; "\\"
0x18008b422  mov     rdx, rsi; SizeInBytes
0x18008b425  mov     rcx, rbx; Destination
0x18008b428  call    cs:__imp_strcat_s
0x18008b42f  nop     dword ptr [rax+rax+00h]
0x18008b434  lea     r8, [r15+1]
0x18008b438  mov     rdx, rsi
0x18008b43b  mov     rcx, rbx
0x18008b43e  jmp     short loc_18008B443
0x18008b440  mov     r8, rdi; Source
0x18008b443  call    cs:__imp_strcat_s
0x18008b44a  nop     dword ptr [rax+rax+00h]
0x18008b44f  lea     r8, [rsp+410h+Context]; Context
0x18008b454  xor     ecx, ecx; Str
0x18008b456  lea     rdx, Delim; " \t"
0x18008b45d  call    cs:__imp__mbstok_s
0x18008b464  nop     dword ptr [rax+rax+00h]
0x18008b469  mov     rdi, rax
0x18008b46c  test    rax, rax
0x18008b46f  jz      short loc_18008B48F
0x18008b471  lea     r8, asc_1800AA200; " "
0x18008b478  mov     rdx, rsi; SizeInBytes
0x18008b47b  mov     rcx, rbx; Destination
0x18008b47e  call    cs:__imp_strcat_s
0x18008b485  nop     dword ptr [rax+rax+00h]
0x18008b48a  jmp     loc_18008B3E6
0x18008b48f  mov     rdx, [rsp+410h+SizeInBytes]; SizeInBytes
0x18008b494  mov     r8, rbx; Source
0x18008b497  mov     rcx, r14; Destination
0x18008b49a  call    cs:__imp_strcpy_s
0x18008b4a1  nop     dword ptr [rax+rax+00h]
0x18008b4a6  mov     rcx, r13; Block
0x18008b4a9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18008b4ae  mov     rcx, rbx; Block
0x18008b4b1  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18008b4b6  mov     r13, [rsp+410h+var_28]
0x18008b4be  mov     rsi, [rsp+410h+var_18]
0x18008b4c6  mov     rcx, r12; Block
0x18008b4c9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18008b4ce  mov     r12, [rsp+410h+var_20]
0x18008b4d6  mov     rbx, [rsp+410h+arg_10]
0x18008b4de  mov     r15, [rsp+410h+var_30]
0x18008b4e6  mov     rcx, [rbp+310h+var_40]
0x18008b4ed  xor     rcx, rsp; StackCookie
0x18008b4f0  call    __security_check_cookie
0x18008b4f5  add     rsp, 400h
0x18008b4fc  pop     r14
0x18008b4fe  pop     rdi
0x18008b4ff  pop     rbp
0x18008b500  retn
```
