# DsRolepCloneDC

- ea: `0x180003a80`
- end: `0x180003cb1`
- name: `DsRolepCloneDC`
- size: `561`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x180003ff0`

## callees

- `0x180003994`
- `0x180003a80`
- `0x180004ef8`
- `0x18000b914`
- `0x18000eb40`
- `0x18000f71c`
- `0x18000ffa8`
- `0x1800161a8`
- `0x180020dbc`
- `0x18002c012`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ac5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b2c`
- `CRYPT32!CryptProtectMemory` at `0x180003b22`
- `CRYPT32!CryptProtectMemory` at `0x180003b22`

## string_xrefs

- `0x180003b48`: `Validate supplied paths\n`
- `0x180003b83`: `Start the worker task\n`

## pseudocode

```c
__int64 __fastcall DsRolepCloneDC(__int64 a1, const void *a2, unsigned int a3)
{
  __int64 v3; // rbp
  unsigned __int16 v6; // r14
  _WORD *v7; // rax
  _WORD *v8; // rsi
  DWORD LastError; // ebx
  __int64 v10; // rdx
  __int128 v12; // [rsp+B0h] [rbp-38h] BYREF
  __int64 v13; // [rsp+108h] [rbp+20h] BYREF

  v3 = a3;
  v13 = 0;
  v12 = 0;
  v6 = (2 * a3 + 17) & 0xFFF0;
  v7 = LocalAlloc(0x40u, (2 * a3 + 17) & 0xFFFFFFF0);
  v8 = v7;
  if ( v7 )
  {
    memcpy_0(v7, a2, 2 * v3);
    v8[v3] = 0;
    *((_QWORD *)&v12 + 1) = v8;
    LOWORD(v12) = 2 * v3;
    WORD1(v12) = v6;
    if ( !v6 || CryptProtectMemory(v8, v6, 0) )
    {
      gdwCloningProgress = 16;
      DsRolepUpdateCloningProgressMessage();
      DsRolepLogPrintRoutine(4, "Validate supplied paths\n");
      LastError = DsRolepCheckFilePaths(
                    *(STRSAFE_PCNZWCH *)(a1 + 24),
                    *(STRSAFE_PCNZWCH *)(a1 + 32),
                    *(STRSAFE_PCNZWCH *)(a1 + 48));
      if ( !LastError )
      {
        gdwCloningProgress = 17;
        DsRolepUpdateCloningProgressMessage();
        DsRolepLogPrintRoutine(4, "Start the worker task\n");
        LastError = DsRolepBuildPromoteArgumentBlock(
                      *(STRSAFE_LPCWSTR *)a1,
                      0,
                      *(STRSAFE_LPCWSTR *)(a1 + 16),
                      *(STRSAFE_LPCWSTR *)(a1 + 24),
                      *(STRSAFE_LPCWSTR *)(a1 + 32),
                      0,
                      *(STRSAFE_LPCWSTR *)(a1 + 48),
                      0,
                      0,
                      *(STRSAFE_LPCWSTR *)(a1 + 8),
                      *(STRSAFE_LPCWSTR *)(a1 + 64),
                      (__int64)&v12,
                      0,
                      0,
                      *(_DWORD *)(a1 + 88),
                      0,
                      0,
                      0,
                      0,
                      0,
                      (__int64)&v13);
        DsRolepFreePasswords(&v12, 1);
        if ( !LastError )
        {
          gdwCloningProgress = 20;
          DsRolepUpdateCloningProgressMessage();
          LastError = DsRolepSpinWorkerThread(1, v13);
          if ( !LastError )
            goto LABEL_11;
          LOBYTE(v10) = 1;
          DsRolepFreeArgumentBlock(&v13, v10);
        }
        DsRolepResetOperationHandle(0);
      }
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 8;
  }
LABEL_11:
  DsRolepLogPrintRoutine(4, "Request for promotion returning %lu\n", LastError);
  return LastError;
}

```

## disassembly

```asm
0x180003a80  mov     rax, rsp
0x180003a83  mov     [rax+8], rbx
0x180003a87  mov     [rax+10h], rbp
0x180003a8b  push    rsi
0x180003a8c  push    rdi
0x180003a8d  push    r12
0x180003a8f  push    r14
0x180003a91  push    r15
0x180003a93  sub     rsp, 0C0h
0x180003a9a  mov     ebp, r8d
0x180003a9d  xor     r12d, r12d
0x180003aa0  mov     [rax+20h], r12
0x180003aa4  xorps   xmm0, xmm0
0x180003aa7  movups  xmmword ptr [rax-38h], xmm0
0x180003aab  mov     r15, rdx
0x180003aae  mov     rdi, rcx
0x180003ab1  lea     eax, ds:11h[rbp*2]
0x180003ab8  and     eax, 0FFFFFFF0h
0x180003abb  lea     ecx, [r12+40h]; uFlags
0x180003ac0  mov     edx, eax; uBytes
0x180003ac2  mov     r14d, eax
0x180003ac5  call    cs:__imp_LocalAlloc
0x180003acb  mov     rsi, rax
0x180003ace  test    rax, rax
0x180003ad1  jnz     short loc_180003ADB
0x180003ad3  lea     ebx, [rax+8]
0x180003ad6  jmp     loc_180003C7F
0x180003adb  lea     rbx, ds:0[rbp*2]
0x180003ae3  mov     rdx, r15; Src
0x180003ae6  mov     r8, rbx; Size
0x180003ae9  mov     rcx, rsi; void *
0x180003aec  call    memcpy_0
0x180003af1  mov     [rbx+rsi], r12w
0x180003af6  add     bp, bp
0x180003af9  mov     [rsp+0E8h+var_30], rsi
0x180003b01  mov     word ptr [rsp+0E8h+var_38], bp
0x180003b09  mov     word ptr [rsp+0E8h+var_38+2], r14w
0x180003b12  test    r14w, r14w
0x180003b16  jz      short loc_180003B39
0x180003b18  movzx   edx, r14w; cbDataIn
0x180003b1c  xor     r8d, r8d; dwFlags
0x180003b1f  mov     rcx, rsi; pDataIn
0x180003b22  call    cs:__imp_CryptProtectMemory
0x180003b28  test    eax, eax
0x180003b2a  jnz     short loc_180003B39
0x180003b2c  call    cs:__imp_GetLastError
0x180003b32  mov     ebx, eax
0x180003b34  jmp     loc_180003C7F
0x180003b39  mov     cs:gdwCloningProgress, 10h
0x180003b43  call    DsRolepUpdateCloningProgressMessage
0x180003b48  lea     rdx, aValidateSuppli; "Validate supplied paths\n"
0x180003b4f  mov     ecx, 4
0x180003b54  call    DsRolepLogPrintRoutine
0x180003b59  mov     r8, [rdi+30h]; STRSAFE_PCNZWCH
0x180003b5d  mov     rdx, [rdi+20h]; STRSAFE_PCNZWCH
0x180003b61  mov     rcx, [rdi+18h]; pszSrc
0x180003b65  call    DsRolepCheckFilePaths
0x180003b6a  mov     ebx, eax
0x180003b6c  test    eax, eax
0x180003b6e  jnz     loc_180003C7F
0x180003b74  mov     cs:gdwCloningProgress, 11h
0x180003b7e  call    DsRolepUpdateCloningProgressMessage
0x180003b83  lea     rdx, aStartTheWorker; "Start the worker task\n"
0x180003b8a  lea     ecx, [rbx+4]
0x180003b8d  call    DsRolepLogPrintRoutine
0x180003b92  mov     r9, [rdi+18h]; STRSAFE_LPCWSTR
0x180003b96  lea     rax, [rsp+0E8h+arg_18]
0x180003b9e  mov     r8, [rdi+10h]; STRSAFE_LPCWSTR
0x180003ba2  xor     edx, edx; STRSAFE_LPCWSTR
0x180003ba4  mov     rcx, [rdi]; pszSrc
0x180003ba7  mov     [rsp+0E8h+var_48], rax; __int64
0x180003baf  mov     eax, [rdi+58h]
0x180003bb2  mov     [rsp+0E8h+var_50], r12d; int
0x180003bba  mov     [rsp+0E8h+var_58], r12d; int
0x180003bc2  mov     [rsp+0E8h+var_60], r12; __int64
0x180003bca  mov     [rsp+0E8h+var_68], r12; __int64
0x180003bd2  mov     [rsp+0E8h+var_70], r12d; int
0x180003bd7  mov     [rsp+0E8h+var_78], eax; int
0x180003bdb  lea     rax, [rsp+0E8h+var_38]
0x180003be3  mov     [rsp+0E8h+var_80], r12; __int64
0x180003be8  mov     [rsp+0E8h+var_88], r12; __int64
0x180003bed  mov     [rsp+0E8h+var_90], rax; __int64
0x180003bf2  mov     rax, [rdi+40h]
0x180003bf6  mov     [rsp+0E8h+var_98], rax; STRSAFE_LPCWSTR
0x180003bfb  mov     rax, [rdi+8]
0x180003bff  mov     [rsp+0E8h+var_A0], rax; STRSAFE_LPCWSTR
0x180003c04  mov     rax, [rdi+30h]
0x180003c08  mov     [rsp+0E8h+var_A8], r12; STRSAFE_LPCWSTR
0x180003c0d  mov     [rsp+0E8h+var_B0], r12; __int64
0x180003c12  mov     [rsp+0E8h+var_B8], rax; STRSAFE_LPCWSTR
0x180003c17  mov     rax, [rdi+20h]
0x180003c1b  mov     [rsp+0E8h+var_C0], r12; __int64
0x180003c20  mov     [rsp+0E8h+var_C8], rax; STRSAFE_LPCWSTR
0x180003c25  call    DsRolepBuildPromoteArgumentBlock
0x180003c2a  mov     edi, 1
0x180003c2f  lea     rcx, [rsp+0E8h+var_38]
0x180003c37  mov     edx, edi
0x180003c39  mov     ebx, eax
0x180003c3b  call    DsRolepFreePasswords
0x180003c40  test    ebx, ebx
0x180003c42  jnz     short loc_180003C78
0x180003c44  mov     cs:gdwCloningProgress, 14h
0x180003c4e  call    DsRolepUpdateCloningProgressMessage
0x180003c53  mov     rdx, [rsp+0E8h+arg_18]
0x180003c5b  mov     ecx, edi
0x180003c5d  call    DsRolepSpinWorkerThread
0x180003c62  mov     ebx, eax
0x180003c64  test    eax, eax
0x180003c66  jz      short loc_180003C7F
0x180003c68  mov     dl, dil
0x180003c6b  lea     rcx, [rsp+0E8h+arg_18]
0x180003c73  call    DsRolepFreeArgumentBlock
0x180003c78  xor     ecx, ecx
0x180003c7a  call    DsRolepResetOperationHandle
0x180003c7f  mov     r8d, ebx
0x180003c82  lea     rdx, aRequestForProm; "Request for promotion returning %lu\n"
0x180003c89  mov     ecx, 4
0x180003c8e  call    DsRolepLogPrintRoutine
0x180003c93  lea     r11, [rsp+0E8h+var_28]
0x180003c9b  mov     eax, ebx
0x180003c9d  mov     rbx, [r11+30h]
0x180003ca1  mov     rbp, [r11+38h]
0x180003ca5  mov     rsp, r11
0x180003ca8  pop     r15
0x180003caa  pop     r14
0x180003cac  pop     r12
0x180003cae  pop     rdi
0x180003caf  pop     rsi
0x180003cb0  retn
```
