# SignalInjector

- ea: `0x180006b70`
- end: `0x180006e0f`
- name: `SignalInjector`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800063bc`

## callees

- `0x180006b70`
- `0x180006f28`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180006cbd`
- `msvcrt!wcscat_s` at `0x180006ccf`
- `msvcrt!wcscat_s` at `0x180006cde`
- `msvcrt!wcscat_s` at `0x180006cbd`
- `msvcrt!wcscat_s` at `0x180006ccf`
- `msvcrt!wcscat_s` at `0x180006cde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006c62`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006d2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006dc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006d2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006dc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180006d74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180006ddc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180006d74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180006ddc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006de5`

## pseudocode

```c
int SignalInjector()
{
  unsigned __int64 CurrentProcessId; // r9
  wchar_t *v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r8
  int result; // eax
  HANDLE v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // [rsp+20h] [rbp-E0h]
  __int64 v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+20h] [rbp-E0h]
  HANDLE hSemaphore[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+54h] [rbp-ACh]
  HANDLE hHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v18; // [rsp+70h] [rbp-90h]
  _BYTE v19[124]; // [rsp+72h] [rbp-8Eh] BYREF
  __int16 v20; // [rsp+EEh] [rbp-12h] BYREF
  wchar_t v21[18]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v22[220]; // [rsp+114h] [rbp+14h] BYREF
  wchar_t v23[17]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v24[222]; // [rsp+212h] [rbp+112h] BYREF
  wchar_t Destination[16]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v26[224]; // [rsp+310h] [rbp+210h] BYREF

  wcscpy(Destination, L"NitsInjectorIn_");
  memset_0(v26, 0, sizeof(v26));
  wcscpy(v23, L"NitsInjectorOut_");
  memset_0(v24, 0, sizeof(v24));
  wcscpy(v21, L"NitsInjectorLock_");
  memset_0(v22, 0, sizeof(v22));
  hSemaphore[0] = 0;
  hHandle[0] = 0;
  v18 = 0;
  memset_0(v19, 0, 0x7Eu);
  CurrentProcessId = GetCurrentProcessId();
  v1 = (wchar_t *)&v20;
  v20 = 0;
  do
  {
    *--v1 = CurrentProcessId % 0xA + 48;
    CurrentProcessId /= 0xAu;
  }
  while ( CurrentProcessId );
  wcscat_s(Destination, 0x80u, v1);
  wcscat_s(v23, 0x80u, v1);
  wcscat_s(v21, 0x80u, v1);
  v15 = 0;
  v14 = 0;
  v16 = -3;
  result = NamedSem_Open_Injected(hHandle, v2, v3, v21, v10, &v14);
  if ( !result )
  {
    v5 = hHandle[0];
    if ( !WaitForSingleObject(hHandle[0], 0x1F4u) )
    {
      v15 = 0;
      v16 = -3;
      v14 = 0;
      if ( !(unsigned int)NamedSem_Open_Injected(hSemaphore, v6, v7, Destination, v11, &v14) )
      {
        ReleaseSemaphore(hSemaphore[0], 1, 0);
        CloseHandle(hSemaphore[0]);
        v15 = 0;
        v14 = 0;
        v16 = -3;
        if ( !(unsigned int)NamedSem_Open_Injected(hSemaphore, v8, v9, v23, v12, &v14) )
        {
          WaitForSingleObject(hSemaphore[0], 0x64u);
          CloseHandle(hSemaphore[0]);
        }
      }
      ReleaseSemaphore(v5, 1, 0);
    }
    return CloseHandle(v5);
  }
  return result;
}

```

## disassembly

```asm
0x180006b70  mov     [rsp-8+arg_0], rbx
0x180006b75  mov     [rsp-8+arg_8], rdi
0x180006b7a  push    rbp
0x180006b7b  lea     rbp, [rsp-300h]
0x180006b83  sub     rsp, 400h
0x180006b8a  mov     rax, cs:__security_cookie
0x180006b91  xor     rax, rsp
0x180006b94  mov     [rbp+300h+var_10], rax
0x180006b9b  movups  xmm0, xmmword ptr cs:aNitsinjectorin; "NitsInjectorIn_"
0x180006ba2  xor     edx, edx; Val
0x180006ba4  mov     r8d, 0E0h; Size
0x180006baa  movups  xmm1, xmmword ptr cs:aNitsinjectorin+10h; "ctorIn_"
0x180006bb1  lea     rcx, [rbp+300h+var_F0]; void *
0x180006bb8  movaps  xmmword ptr [rbp+300h+Destination], xmm0
0x180006bbf  movaps  [rbp+300h+var_100], xmm1
0x180006bc6  call    memset_0
0x180006bcb  movups  xmm0, xmmword ptr cs:aNitsinjectorou; "NitsInjectorOut_"
0x180006bd2  movzx   eax, word ptr cs:aNitsinjectorou+20h; ""
0x180006bd9  xor     edx, edx; Val
0x180006bdb  movups  xmm1, xmmword ptr cs:aNitsinjectorou+10h; "ctorOut_"
0x180006be2  mov     r8d, 0DEh; Size
0x180006be8  lea     rcx, [rbp+300h+var_1EE]; void *
0x180006bef  movaps  xmmword ptr [rbp+300h+var_210], xmm0
0x180006bf6  movaps  [rbp+300h+var_200], xmm1
0x180006bfd  mov     [rbp+300h+var_1F0], ax
0x180006c04  call    memset_0
0x180006c09  movups  xmm0, xmmword ptr cs:aNitsinjectorlo; "NitsInjectorLock_"
0x180006c10  mov     eax, dword ptr cs:aNitsinjectorlo+20h; "_"
0x180006c16  xor     edx, edx; Val
0x180006c18  movups  xmm1, xmmword ptr cs:aNitsinjectorlo+10h; "ctorLock_"
0x180006c1f  mov     r8d, 0DCh; Size
0x180006c25  lea     rcx, [rbp+300h+var_2EC]; void *
0x180006c29  movaps  xmmword ptr [rbp+300h+var_310], xmm0
0x180006c2d  movaps  [rbp+300h+var_300], xmm1
0x180006c31  mov     [rbp+300h+var_2F0], eax
0x180006c34  call    memset_0
0x180006c39  xor     eax, eax
0x180006c3b  mov     [rsp+400h+hSemaphore], 0
0x180006c44  xor     edx, edx; Val
0x180006c46  mov     [rsp+400h+hHandle], 0
0x180006c4f  lea     rcx, [rsp+400h+var_38E]; void *
0x180006c54  mov     [rsp+400h+var_390], ax
0x180006c59  lea     r8d, [rax+7Eh]; Size
0x180006c5d  call    memset_0
0x180006c62  call    cs:__imp_GetCurrentProcessId
0x180006c68  mov     r9d, eax
0x180006c6b  lea     rbx, [rbp+300h+var_312]
0x180006c6f  xor     eax, eax
0x180006c71  mov     [rbp+300h+var_312], ax
0x180006c75  sub     rbx, 2
0x180006c79  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006c83  mul     r9
0x180006c86  shr     rdx, 3
0x180006c8a  movzx   eax, dx
0x180006c8d  shl     ax, 2
0x180006c91  lea     ecx, [rax+rdx]
0x180006c94  add     cx, cx
0x180006c97  sub     r9w, cx
0x180006c9b  add     r9w, 30h ; '0'
0x180006ca0  mov     [rbx], r9w
0x180006ca4  mov     r9, rdx
0x180006ca7  test    rdx, rdx
0x180006caa  jnz     short loc_180006C75
0x180006cac  mov     edi, 80h
0x180006cb1  lea     rcx, [rbp+300h+Destination]; Destination
0x180006cb8  mov     edx, edi; SizeInWords
0x180006cba  mov     r8, rbx; Source
0x180006cbd  call    cs:__imp_wcscat_s
0x180006cc3  mov     r8, rbx; Source
0x180006cc6  lea     rcx, [rbp+300h+var_210]; Destination
0x180006ccd  mov     edx, edi; SizeInWords
0x180006ccf  call    cs:__imp_wcscat_s
0x180006cd5  mov     r8, rbx; Source
0x180006cd8  lea     rcx, [rbp+300h+var_310]; Destination
0x180006cdc  mov     edx, edi; SizeInWords
0x180006cde  call    cs:__imp_wcscat_s
0x180006ce4  xorps   xmm0, xmm0
0x180006ce7  mov     [rsp+400h+var_3B0], 0
0x180006cef  lea     rax, [rsp+400h+var_3C0]
0x180006cf4  movdqa  [rsp+400h+var_3C0], xmm0
0x180006cfa  mov     edi, 0FFFFFFFDh
0x180006cff  mov     [rsp+400h+var_3D8], rax
0x180006d04  lea     r9, [rbp+300h+var_310]
0x180006d08  mov     [rsp+400h+var_3AC], edi
0x180006d0c  lea     rcx, [rsp+400h+hHandle]
0x180006d11  call    NamedSem_Open_Injected
0x180006d16  test    eax, eax
0x180006d18  jnz     loc_180006DEB
0x180006d1e  mov     rbx, [rsp+400h+hHandle]
0x180006d23  mov     edx, 1F4h; dwMilliseconds
0x180006d28  mov     rcx, rbx; hHandle
0x180006d2b  call    cs:__imp_WaitForSingleObject
0x180006d31  test    eax, eax
0x180006d33  jnz     loc_180006DE2
0x180006d39  mov     [rsp+400h+var_3B0], eax
0x180006d3d  lea     r9, [rbp+300h+Destination]
0x180006d44  lea     rax, [rsp+400h+var_3C0]
0x180006d49  mov     [rsp+400h+var_3AC], edi
0x180006d4d  xorps   xmm0, xmm0
0x180006d50  mov     [rsp+400h+var_3D8], rax
0x180006d55  lea     rcx, [rsp+400h+hSemaphore]
0x180006d5a  movdqa  [rsp+400h+var_3C0], xmm0
0x180006d60  call    NamedSem_Open_Injected
0x180006d65  test    eax, eax
0x180006d67  jnz     short loc_180006DD2
0x180006d69  mov     rcx, [rsp+400h+hSemaphore]; hSemaphore
0x180006d6e  lea     edx, [rdi+4]; lReleaseCount
0x180006d71  xor     r8d, r8d; lpPreviousCount
0x180006d74  call    cs:__imp_ReleaseSemaphore
0x180006d7a  mov     rcx, [rsp+400h+hSemaphore]; hObject
0x180006d7f  call    cs:__imp_CloseHandle
0x180006d85  xorps   xmm0, xmm0
0x180006d88  mov     [rsp+400h+var_3B0], 0
0x180006d90  lea     rax, [rsp+400h+var_3C0]
0x180006d95  movdqa  [rsp+400h+var_3C0], xmm0
0x180006d9b  lea     r9, [rbp+300h+var_210]
0x180006da2  mov     [rsp+400h+var_3D8], rax
0x180006da7  lea     rcx, [rsp+400h+hSemaphore]
0x180006dac  mov     [rsp+400h+var_3AC], edi
0x180006db0  call    NamedSem_Open_Injected
0x180006db5  test    eax, eax
0x180006db7  jnz     short loc_180006DD2
0x180006db9  mov     rcx, [rsp+400h+hSemaphore]; hHandle
0x180006dbe  lea     edx, [rdi+67h]; dwMilliseconds
0x180006dc1  call    cs:__imp_WaitForSingleObject
0x180006dc7  mov     rcx, [rsp+400h+hSemaphore]; hObject
0x180006dcc  call    cs:__imp_CloseHandle
0x180006dd2  xor     r8d, r8d; lpPreviousCount
0x180006dd5  mov     rcx, rbx; hSemaphore
0x180006dd8  lea     edx, [r8+1]; lReleaseCount
0x180006ddc  call    cs:__imp_ReleaseSemaphore
0x180006de2  mov     rcx, rbx; hObject
0x180006de5  call    cs:__imp_CloseHandle
0x180006deb  mov     rcx, [rbp+300h+var_10]
0x180006df2  xor     rcx, rsp; StackCookie
0x180006df5  call    __security_check_cookie
0x180006dfa  lea     r11, [rsp+400h+var_s0]
0x180006e02  mov     rbx, [r11+10h]
0x180006e06  mov     rdi, [r11+18h]
0x180006e0a  mov     rsp, r11
0x180006e0d  pop     rbp
0x180006e0e  retn
```
