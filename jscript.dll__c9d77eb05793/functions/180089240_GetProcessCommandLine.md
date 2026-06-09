# GetProcessCommandLine

- ea: `0x180089240`
- end: `0x1800895a1`
- name: `GetProcessCommandLine`
- size: `865`
- prototype: `__int64 __fastcall(HANDLE hProcess, char *Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180089640`

## callees

- `0x1800576e0`
- `0x18005830c`
- `0x180089240`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!_mbstok_s` at `0x180089494`
- `msvcrt!_mbstok_s` at `0x18008950f`
- `msvcrt!_mbstok_s` at `0x180089494`
- `msvcrt!_mbstok_s` at `0x18008950f`
- `msvcrt!strcat_s` at `0x1800894d3`
- `msvcrt!strcat_s` at `0x1800894e6`
- `msvcrt!strcat_s` at `0x1800894fb`
- `msvcrt!strcat_s` at `0x18008952a`
- `msvcrt!strcat_s` at `0x1800894d3`
- `msvcrt!strcat_s` at `0x1800894e6`
- `msvcrt!strcat_s` at `0x1800894fb`
- `msvcrt!strcat_s` at `0x18008952a`
- `msvcrt!strcpy_s` at `0x180089477`
- `msvcrt!strcpy_s` at `0x180089540`
- `msvcrt!strcpy_s` at `0x180089477`
- `msvcrt!strcpy_s` at `0x180089540`
- `msvcrt!_mbsrchr` at `0x1800894b8`
- `msvcrt!_mbsrchr` at `0x1800894b8`
- `KERNEL32!ReadProcessMemory` at `0x180089304`
- `KERNEL32!ReadProcessMemory` at `0x18008934b`
- `KERNEL32!ReadProcessMemory` at `0x1800893c6`
- `KERNEL32!ReadProcessMemory` at `0x180089304`
- `KERNEL32!ReadProcessMemory` at `0x18008934b`
- `KERNEL32!ReadProcessMemory` at `0x1800893c6`
- `KERNEL32!GetModuleHandleA` at `0x180089287`
- `KERNEL32!GetModuleHandleA` at `0x180089287`
- `KERNEL32!GetProcAddress` at `0x1800892a0`
- `KERNEL32!GetProcAddress` at `0x1800892a0`
- `KERNEL32!WideCharToMultiByte` at `0x180089401`
- `KERNEL32!WideCharToMultiByte` at `0x180089401`

## string_xrefs

- `0x180089271`: `ntdll.dll`
- `0x1800894cc`: `<path>`

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
0x180089240  push    rbp
0x180089242  push    rdi
0x180089243  push    r14
0x180089245  lea     rbp, [rsp-300h]
0x18008924d  sub     rsp, 400h
0x180089254  mov     rax, cs:__security_cookie
0x18008925b  xor     rax, rsp
0x18008925e  mov     [rbp+310h+var_40], rax
0x180089265  xorps   xmm0, xmm0
0x180089268  mov     byte ptr [rdx], 0
0x18008926b  mov     rdi, rcx
0x18008926e  mov     r14, rdx
0x180089271  lea     rcx, aNtdllDll; "ntdll.dll"
0x180089278  movups  xmmword ptr [rsp+410h+lpBaseAddress], xmm0
0x18008927d  movups  [rsp+410h+var_3B0], xmm0
0x180089282  movups  [rsp+410h+var_3A0], xmm0
0x180089287  call    cs:__imp_GetModuleHandleA
0x18008928d  test    rax, rax
0x180089290  jz      loc_180089586
0x180089296  lea     rdx, aNtqueryinforma; "NtQueryInformationProcess"
0x18008929d  mov     rcx, rax; hModule
0x1800892a0  call    cs:__imp_GetProcAddress
0x1800892a6  test    rax, rax
0x1800892a9  jz      loc_180089586
0x1800892af  mov     [rsp+410h+var_30], r15
0x1800892b7  lea     r8, [rsp+410h+lpBaseAddress]
0x1800892bc  xor     r15d, r15d
0x1800892bf  mov     r9d, 30h ; '0'
0x1800892c5  xor     edx, edx
0x1800892c7  mov     [rsp+410h+lpNumberOfBytesRead], r15
0x1800892cc  mov     rcx, rdi
0x1800892cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892d4  test    eax, eax
0x1800892d6  js      loc_18008957E
0x1800892dc  xor     edx, edx; Val
0x1800892de  lea     rcx, [rbp+310h+Buffer]; void *
0x1800892e2  mov     r8d, 2C8h; Size
0x1800892e8  call    memset_0
0x1800892ed  mov     rdx, [rsp+410h+lpBaseAddress+8]; lpBaseAddress
0x1800892f2  lea     r8, [rbp+310h+Buffer]; lpBuffer
0x1800892f6  mov     r9d, 2C8h; nSize
0x1800892fc  mov     [rsp+410h+lpNumberOfBytesRead], r15; lpNumberOfBytesRead
0x180089301  mov     rcx, rdi; hProcess
0x180089304  call    cs:__imp_ReadProcessMemory
0x18008930a  test    eax, eax
0x18008930c  jz      loc_18008957E
0x180089312  mov     rdx, [rbp+310h+var_2F0]; lpBaseAddress
0x180089316  lea     r8, [rbp+310h+var_390]; lpBuffer
0x18008931a  xorps   xmm0, xmm0
0x18008931d  mov     [rsp+410h+lpNumberOfBytesRead], r15; lpNumberOfBytesRead
0x180089322  mov     r9d, 80h; nSize
0x180089328  mov     rcx, rdi; hProcess
0x18008932b  movups  [rbp+310h+var_390], xmm0
0x18008932f  movups  [rbp+310h+var_380], xmm0
0x180089333  movups  [rbp+310h+var_370], xmm0
0x180089337  movups  [rbp+310h+var_360], xmm0
0x18008933b  movups  [rbp+310h+var_350], xmm0
0x18008933f  movups  [rbp+310h+var_340], xmm0
0x180089343  movups  [rbp+310h+var_330], xmm0
0x180089347  movups  xmmword ptr [rbp+310h+var_320], xmm0
0x18008934b  call    cs:__imp_ReadProcessMemory
0x180089351  test    eax, eax
0x180089353  jz      loc_18008957E
0x180089359  movzx   ecx, word ptr [rbp+310h+var_320]
0x18008935d  mov     edx, 0FFEh
0x180089362  lea     eax, [rcx-1]
0x180089365  cmp     ax, dx
0x180089368  ja      loc_18008957E
0x18008936e  shr     rcx, 1
0x180089371  mov     eax, 2
0x180089376  inc     rcx
0x180089379  mov     [rsp+410h+arg_10], rbx
0x180089381  mul     rcx
0x180089384  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18008938b  mov     [rsp+410h+var_20], r12
0x180089393  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008939a  cmovb   rax, rbx
0x18008939e  mov     rcx, rax; unsigned __int64
0x1800893a1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800893a6  mov     r12, rax
0x1800893a9  test    rax, rax
0x1800893ac  jz      loc_18008956E
0x1800893b2  movzx   r9d, word ptr [rbp+310h+var_320]; nSize
0x1800893b7  mov     r8, rax; lpBuffer
0x1800893ba  mov     rdx, [rbp+310h+var_320+8]; lpBaseAddress
0x1800893be  mov     rcx, rdi; hProcess
0x1800893c1  mov     [rsp+410h+lpNumberOfBytesRead], r15; lpNumberOfBytesRead
0x1800893c6  call    cs:__imp_ReadProcessMemory
0x1800893cc  test    eax, eax
0x1800893ce  jz      loc_180089566
0x1800893d4  movzx   ecx, word ptr [rbp+310h+var_320]
0x1800893d8  mov     r9d, ebx; cchWideChar
0x1800893db  shr     rcx, 1
0x1800893de  mov     r8, r12; lpWideCharStr
0x1800893e1  mov     [rsp+410h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800893e6  xor     edx, edx; dwFlags
0x1800893e8  mov     [rsp+410h+lpDefaultChar], r15; lpDefaultChar
0x1800893ed  mov     [rsp+410h+cbMultiByte], 200h; cbMultiByte
0x1800893f5  mov     [r12+rcx*2], r15w
0x1800893fa  xor     ecx, ecx; CodePage
0x1800893fc  mov     [rsp+410h+lpNumberOfBytesRead], r14; lpMultiByteStr
0x180089401  call    cs:__imp_WideCharToMultiByte
0x180089407  cmp     [r14], r15b
0x18008940a  jz      loc_180089566
0x180089410  mov     [rsp+410h+var_18], rsi
0x180089418  mov     [rsp+410h+var_28], r13
0x180089420  cmp     [r14+rbx+1], r15b
0x180089425  lea     rbx, [rbx+1]
0x180089429  jnz     short loc_180089420
0x18008942b  lea     rdi, [rbx+1]
0x18008942f  mov     rcx, rdi; unsigned __int64
0x180089432  mov     [rsp+410h+SizeInBytes], rdi
0x180089437  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008943e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180089443  lea     rsi, [rbx+rbx]
0x180089447  mov     r13, rax
0x18008944a  mov     rcx, rsi; unsigned __int64
0x18008944d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180089454  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180089459  mov     rbx, rax
0x18008945c  test    r13, r13
0x18008945f  jz      loc_180089546
0x180089465  test    rax, rax
0x180089468  jz      loc_180089546
0x18008946e  mov     r8, r14; Source
0x180089471  mov     rdx, rdi; SizeInBytes
0x180089474  mov     rcx, r13; Destination
0x180089477  call    cs:__imp_strcpy_s
0x18008947d  mov     [rbx], r15b
0x180089480  lea     r8, [rsp+410h+Context]; Context
0x180089485  lea     rdx, Delim; " \t"
0x18008948c  mov     [rsp+410h+Context], r15
0x180089491  mov     rcx, r13; Str
0x180089494  call    cs:__imp__mbstok_s
0x18008949a  mov     rdi, rax
0x18008949d  test    rax, rax
0x1800894a0  jz      loc_180089535
0x1800894a6  nop     word ptr [rax+rax+00000000h]
0x1800894b0  mov     edx, 5Ch ; '\'; C
0x1800894b5  mov     rcx, rdi; String
0x1800894b8  call    cs:__imp__mbsrchr
0x1800894be  mov     rdx, rsi; SizeInBytes
0x1800894c1  mov     rcx, rbx; Destination
0x1800894c4  mov     r15, rax
0x1800894c7  test    rax, rax
0x1800894ca  jz      short loc_1800894F8
0x1800894cc  lea     r8, aPath; "<path>"
0x1800894d3  call    cs:__imp_strcat_s
0x1800894d9  lea     r8, asc_1800A8228; "\\"
0x1800894e0  mov     rdx, rsi; SizeInBytes
0x1800894e3  mov     rcx, rbx; Destination
0x1800894e6  call    cs:__imp_strcat_s
0x1800894ec  lea     r8, [r15+1]
0x1800894f0  mov     rdx, rsi
0x1800894f3  mov     rcx, rbx
0x1800894f6  jmp     short loc_1800894FB
0x1800894f8  mov     r8, rdi; Source
0x1800894fb  call    cs:__imp_strcat_s
0x180089501  lea     r8, [rsp+410h+Context]; Context
0x180089506  xor     ecx, ecx; Str
0x180089508  lea     rdx, Delim; " \t"
0x18008950f  call    cs:__imp__mbstok_s
0x180089515  mov     rdi, rax
0x180089518  test    rax, rax
0x18008951b  jz      short loc_180089535
0x18008951d  lea     r8, asc_1800A8224; " "
0x180089524  mov     rdx, rsi; SizeInBytes
0x180089527  mov     rcx, rbx; Destination
0x18008952a  call    cs:__imp_strcat_s
0x180089530  jmp     loc_1800894B0
0x180089535  mov     rdx, [rsp+410h+SizeInBytes]; SizeInBytes
0x18008953a  mov     r8, rbx; Source
0x18008953d  mov     rcx, r14; Destination
0x180089540  call    cs:__imp_strcpy_s
0x180089546  mov     rcx, r13; Block
0x180089549  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18008954e  mov     rcx, rbx; Block
0x180089551  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180089556  mov     r13, [rsp+410h+var_28]
0x18008955e  mov     rsi, [rsp+410h+var_18]
0x180089566  mov     rcx, r12; Block
0x180089569  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18008956e  mov     r12, [rsp+410h+var_20]
0x180089576  mov     rbx, [rsp+410h+arg_10]
0x18008957e  mov     r15, [rsp+410h+var_30]
0x180089586  mov     rcx, [rbp+310h+var_40]
0x18008958d  xor     rcx, rsp; StackCookie
0x180089590  call    __security_check_cookie
0x180089595  add     rsp, 400h
0x18008959c  pop     r14
0x18008959e  pop     rdi
0x18008959f  pop     rbp
0x1800895a0  retn
```
