# RemoveAppCompatPolicy(ushort const * *,uint,ushort const *)

- ea: `0x1800900bc`
- end: `0x180090313`
- name: `?RemoveAppCompatPolicy@@YAXPEAPEBGIPEBG@Z`
- size: `599`
- prototype: `void __fastcall(const unsigned __int16 **, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18008a8fc`

## callees

- `0x18001b22c`
- `0x18001c574`
- `0x18004db5c`
- `0x180075fa0`
- `0x1800900bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009024b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009024b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180090225`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180090287`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180090225`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180090287`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180090144`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180090144`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800902cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800902cf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009017d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180090203`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009017d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180090203`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800902ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800902ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800902c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800902c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180090127`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180090127`

## string_xrefs

- `0x1800900f5`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
void __fastcall RemoveAppCompatPolicy(const unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // rdi
  unsigned __int64 v5; // r12
  wchar_t *v6; // r15
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  wchar_t *v9; // r14
  unsigned int i; // esi
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *Context[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  hkey = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hkey,
          0) )
  {
    if ( GetModuleFileNameW(0, Filename, 0x104u) < 0x104 )
    {
      pcbData = 0;
      if ( !RegGetValueW(hkey, 0, Filename, 2u, 0, 0, &pcbData) )
      {
        if ( pcbData )
        {
          v4 = -1;
          v5 = (unsigned __int64)pcbData >> 1;
          v6 = (wchar_t *)operator new(saturated_mul(v5, 2u));
          v7 = (unsigned __int16 *)operator new(saturated_mul(v5, 2u));
          v8 = v7;
          if ( v6 )
          {
            if ( v7 )
            {
              *v7 = 0;
              if ( !RegGetValueW(hkey, 0, Filename, 2u, 0, v6, &pcbData) )
              {
                Context[0] = 0;
                v9 = wcstok_s(v6, L" ", Context);
                if ( v9 )
                {
                  do
                  {
                    for ( i = 0; i < 3; ++i )
                    {
                      if ( a1[i] && !(unsigned int)_o__wcsicmp(v9) )
                        goto LABEL_15;
                    }
                    StringCchCatW(v8, v5, v9);
                    StringCchCatW(v8, v5, L" ");
LABEL_15:
                    v9 = wcstok_s(0, L" ", Context);
                  }
                  while ( v9 );
                  v4 = -1;
                }
                do
                  ++v4;
                while ( v8[v4] );
                if ( (_DWORD)v4 )
                  RegSetValueExW(hkey, Filename, 0, 1u, (const BYTE *)v8, 2 * v4);
                else
                  RegDeleteValueW(hkey, Filename);
              }
            }
          }
          operator delete(v6);
          operator delete(v8);
        }
      }
    }
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x1800900bc  push    rbp
0x1800900be  push    rbx
0x1800900bf  push    rsi
0x1800900c0  push    rdi
0x1800900c1  push    r12
0x1800900c3  push    r13
0x1800900c5  push    r14
0x1800900c7  push    r15
0x1800900c9  lea     rbp, [rsp-198h]
0x1800900d1  sub     rsp, 298h
0x1800900d8  mov     rax, cs:__security_cookie
0x1800900df  xor     rax, rsp
0x1800900e2  mov     [rbp+1D0h+var_50], rax
0x1800900e9  xor     esi, esi
0x1800900eb  lea     rax, [rsp+2D0h+hkey]
0x1800900f0  mov     [rsp+2D0h+lpdwDisposition], rsi; lpdwDisposition
0x1800900f5  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800900fc  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180090101  mov     r13, rcx
0x180090104  mov     [rsp+2D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180090109  xor     r9d, r9d; lpClass
0x18009010c  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180090114  xor     r8d, r8d; Reserved
0x180090117  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009011e  mov     [rsp+2D0h+dwOptions], esi; dwOptions
0x180090122  mov     [rsp+2D0h+hkey], rsi
0x180090127  call    cs:__imp_RegCreateKeyExW
0x18009012d  test    eax, eax
0x18009012f  jnz     loc_1800902F0
0x180090135  mov     ebx, 104h
0x18009013a  lea     rdx, [rsp+2D0h+Filename]; lpFilename
0x18009013f  mov     r8d, ebx; nSize
0x180090142  xor     ecx, ecx; hModule
0x180090144  call    cs:__imp_GetModuleFileNameW
0x18009014a  cmp     eax, ebx
0x18009014c  jnb     loc_1800902E5
0x180090152  mov     rcx, [rsp+2D0h+hkey]; hkey
0x180090157  lea     rax, [rsp+2D0h+pcbData]
0x18009015c  mov     [rsp+2D0h+lpSecurityAttributes], rax; pcbData
0x180090161  lea     r14d, [rsi+2]
0x180090165  mov     qword ptr [rsp+2D0h+samDesired], rsi; pvData
0x18009016a  lea     r8, [rsp+2D0h+Filename]; lpValue
0x18009016f  mov     r9d, r14d; dwFlags
0x180090172  mov     qword ptr [rsp+2D0h+dwOptions], rsi; pdwType
0x180090177  xor     edx, edx; lpSubKey
0x180090179  mov     [rsp+2D0h+pcbData], esi
0x18009017d  call    cs:__imp_RegGetValueW
0x180090183  test    eax, eax
0x180090185  jnz     loc_1800902E5
0x18009018b  mov     eax, [rsp+2D0h+pcbData]
0x18009018f  test    eax, eax
0x180090191  jz      loc_1800902E5
0x180090197  mov     r12d, eax
0x18009019a  lea     rdi, [rsi-1]
0x18009019e  shr     r12, 1
0x1800901a1  mov     eax, r14d
0x1800901a4  mul     r12
0x1800901a7  cmovb   rax, rdi
0x1800901ab  mov     rcx, rax; dwBytes
0x1800901ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800901b3  mov     r15, rax
0x1800901b6  mov     eax, r14d
0x1800901b9  mul     r12
0x1800901bc  cmovb   rax, rdi
0x1800901c0  mov     rcx, rax; dwBytes
0x1800901c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800901c8  mov     rbx, rax
0x1800901cb  test    r15, r15
0x1800901ce  jz      loc_1800902D5
0x1800901d4  test    rax, rax
0x1800901d7  jz      loc_1800902D5
0x1800901dd  mov     [rax], si
0x1800901e0  lea     r8, [rsp+2D0h+Filename]; lpValue
0x1800901e5  mov     rcx, [rsp+2D0h+hkey]; hkey
0x1800901ea  lea     rax, [rsp+2D0h+pcbData]
0x1800901ef  mov     [rsp+2D0h+lpSecurityAttributes], rax; pcbData
0x1800901f4  mov     r9d, r14d; dwFlags
0x1800901f7  mov     qword ptr [rsp+2D0h+samDesired], r15; pvData
0x1800901fc  xor     edx, edx; lpSubKey
0x1800901fe  mov     qword ptr [rsp+2D0h+dwOptions], rsi; pdwType
0x180090203  call    cs:__imp_RegGetValueW
0x180090209  test    eax, eax
0x18009020b  jnz     loc_1800902D5
0x180090211  lea     r8, [rsp+2D0h+Context]; Context
0x180090216  mov     [rsp+2D0h+Context], rsi
0x18009021b  lea     rdx, Delimiter; " "
0x180090222  mov     rcx, r15; String
0x180090225  call    cs:__imp_wcstok_s
0x18009022b  mov     r14, rax
0x18009022e  test    rax, rax
0x180090231  jz      short loc_18009029B
0x180090233  xor     edi, edi
0x180090235  mov     esi, edi
0x180090237  cmp     esi, 3
0x18009023a  jnb     short loc_180090259
0x18009023c  mov     ecx, esi
0x18009023e  mov     rdx, [r13+rcx*8+0]
0x180090243  test    rdx, rdx
0x180090246  jz      short loc_180090255
0x180090248  mov     rcx, r14
0x18009024b  call    cs:__imp__o__wcsicmp
0x180090251  test    eax, eax
0x180090253  jz      short loc_180090279
0x180090255  inc     esi
0x180090257  jmp     short loc_180090237
0x180090259  mov     r8, r14; unsigned __int16 *
0x18009025c  mov     rdx, r12; unsigned __int64
0x18009025f  mov     rcx, rbx; unsigned __int16 *
0x180090262  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180090267  lea     r8, Delimiter; " "
0x18009026e  mov     rdx, r12; unsigned __int64
0x180090271  mov     rcx, rbx; unsigned __int16 *
0x180090274  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180090279  lea     r8, [rsp+2D0h+Context]; Context
0x18009027e  xor     ecx, ecx; String
0x180090280  lea     rdx, Delimiter; " "
0x180090287  call    cs:__imp_wcstok_s
0x18009028d  mov     r14, rax
0x180090290  test    rax, rax
0x180090293  jnz     short loc_180090235
0x180090295  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180090299  xor     esi, esi
0x18009029b  inc     rdi
0x18009029e  cmp     [rbx+rdi*2], si
0x1800902a2  jnz     short loc_18009029B
0x1800902a4  mov     rcx, [rsp+2D0h+hkey]; hKey
0x1800902a9  lea     rdx, [rsp+2D0h+Filename]; lpValueName
0x1800902ae  test    edi, edi
0x1800902b0  jz      short loc_1800902CF
0x1800902b2  lea     eax, [rdi+rdi]
0x1800902b5  mov     r9d, 1; dwType
0x1800902bb  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800902bf  xor     r8d, r8d; Reserved
0x1800902c2  mov     qword ptr [rsp+2D0h+dwOptions], rbx; lpData
0x1800902c7  call    cs:__imp_RegSetValueExW
0x1800902cd  jmp     short loc_1800902D5
0x1800902cf  call    cs:__imp_RegDeleteValueW
0x1800902d5  mov     rcx, r15; lpMem
0x1800902d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800902dd  mov     rcx, rbx; lpMem
0x1800902e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800902e5  mov     rcx, [rsp+2D0h+hkey]; hKey
0x1800902ea  call    cs:__imp_RegCloseKey
0x1800902f0  mov     rcx, [rbp+1D0h+var_50]
0x1800902f7  xor     rcx, rsp; StackCookie
0x1800902fa  call    __security_check_cookie
0x1800902ff  add     rsp, 298h
0x180090306  pop     r15
0x180090308  pop     r14
0x18009030a  pop     r13
0x18009030c  pop     r12
0x18009030e  pop     rdi
0x18009030f  pop     rsi
0x180090310  pop     rbx
0x180090311  pop     rbp
0x180090312  retn
```
