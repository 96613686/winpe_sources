# AicpGetCurrentDesktop(ushort const *,ushort * *)

- ea: `0x1800b0adc`
- end: `0x1800b0ce2`
- name: `?AicpGetCurrentDesktop@@YAKPEBGPEAPEAG@Z`
- size: `518`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800b137c`

## callees

- `0x18000cfc8`
- `0x1800b0adc`
- `0x1800b0ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0c38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0b8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0b8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0caf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0caf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0b34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0bf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0c8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0b34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0bf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0c8e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800b0b9a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800b0b9a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0bbf`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0be1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0c28`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0c74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0bbf`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0be1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0c28`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800b0c74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x1800b0b7d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x1800b0b7d`

## pseudocode

```c
__int64 __fastcall AicpGetCurrentDesktop(unsigned __int16 *a1, unsigned __int16 **a2)
{
  DWORD LastError; // edi
  unsigned __int16 *v5; // rax
  char *v6; // rbx
  HWINSTA ProcessWindowStation; // r15
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // r12
  DWORD nLengthNeeded; // [rsp+80h] [rbp+30h] BYREF
  DWORD nLength; // [rsp+88h] [rbp+38h] BYREF

  LastError = 0;
  *a2 = a1;
  nLengthNeeded = 0;
  nLength = 0;
  if ( !AicpImpersonatingCrossSession() )
  {
    if ( !a1 || !*a1 )
    {
      if ( (unsigned __int8)IsGetProcessWindowStationPresent() )
      {
        ProcessWindowStation = GetProcessWindowStation();
        CurrentThreadId = GetCurrentThreadId();
        ThreadDesktop = GetThreadDesktop(CurrentThreadId);
        GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded);
        GetUserObjectInformationW(ThreadDesktop, 2, 0, 0, &nLength);
        v6 = (char *)LocalAlloc(0x40u, nLength + nLengthNeeded);
        if ( !v6 )
          goto LABEL_3;
        if ( !GetUserObjectInformationW(ProcessWindowStation, 2, v6, nLengthNeeded, &nLengthNeeded)
          || (*(_WORD *)&v6[2 * ((unsigned __int64)nLengthNeeded >> 1) - 2] = 92,
              !GetUserObjectInformationW(
                 ThreadDesktop,
                 2,
                 &v6[2 * ((unsigned __int64)nLengthNeeded >> 1)],
                 nLength,
                 &nLength)) )
        {
          LastError = GetLastError();
          goto LABEL_16;
        }
      }
      else
      {
        v6 = (char *)LocalAlloc(0x40u, 2u);
        if ( !v6 )
          goto LABEL_3;
      }
      *a2 = (unsigned __int16 *)v6;
    }
LABEL_15:
    v6 = 0;
    goto LABEL_16;
  }
  v5 = (unsigned __int16 *)LocalAlloc(0x40u, 0x20u);
  v6 = (char *)v5;
  if ( v5 )
  {
    *(_OWORD *)v5 = *(_OWORD *)L"Winsta0\\Default";
    *((_OWORD *)v5 + 1) = *(_OWORD *)L"Default";
    *a2 = v5;
    goto LABEL_15;
  }
LABEL_3:
  LastError = 8;
LABEL_16:
  LocalFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x1800b0adc  mov     rax, rsp
0x1800b0adf  mov     [rax+18h], rbx
0x1800b0ae3  mov     [rax+20h], rdi
0x1800b0ae7  push    rbp
0x1800b0ae8  push    r12
0x1800b0aea  push    r13
0x1800b0aec  push    r14
0x1800b0aee  push    r15
0x1800b0af0  mov     rbp, rsp
0x1800b0af3  sub     rsp, 50h
0x1800b0af7  movaps  xmmword ptr [rax-38h], xmm6
0x1800b0afb  xor     r13d, r13d
0x1800b0afe  movups  xmm6, xmmword ptr cs:aWinsta0Default; "Winsta0\\Default"
0x1800b0b05  mov     r14, rdx
0x1800b0b08  mov     rbx, rcx
0x1800b0b0b  movaps  xmmword ptr [rax-48h], xmm7
0x1800b0b0f  mov     edi, r13d
0x1800b0b12  movups  xmm7, xmmword ptr cs:aWinsta0Default+10h; "Default"
0x1800b0b19  mov     [rdx], rcx
0x1800b0b1c  mov     [rbp+nLengthNeeded], r13d
0x1800b0b20  mov     [rbp+nLength], r13d
0x1800b0b24  call    ?AicpImpersonatingCrossSession@@YAHXZ; AicpImpersonatingCrossSession(void)
0x1800b0b29  test    eax, eax
0x1800b0b2b  jz      short loc_1800B0B61
0x1800b0b2d  lea     edx, [r13+20h]; uBytes
0x1800b0b31  lea     ecx, [rdx+20h]; uFlags
0x1800b0b34  call    cs:__imp_LocalAlloc
0x1800b0b3b  nop     dword ptr [rax+rax+00h]
0x1800b0b40  mov     rbx, rax
0x1800b0b43  test    rax, rax
0x1800b0b46  jnz     short loc_1800B0B52
0x1800b0b48  mov     edi, 8
0x1800b0b4d  jmp     loc_1800B0CAC
0x1800b0b52  movups  xmmword ptr [rax], xmm6
0x1800b0b55  movups  xmmword ptr [rax+10h], xmm7
0x1800b0b59  mov     [r14], rax
0x1800b0b5c  jmp     loc_1800B0CA9
0x1800b0b61  test    rbx, rbx
0x1800b0b64  jz      short loc_1800B0B70
0x1800b0b66  cmp     [rbx], r13w
0x1800b0b6a  jnz     loc_1800B0CA9
0x1800b0b70  call    IsGetProcessWindowStationPresent
0x1800b0b75  test    al, al
0x1800b0b77  jz      loc_1800B0C86
0x1800b0b7d  call    cs:__imp_GetProcessWindowStation
0x1800b0b84  nop     dword ptr [rax+rax+00h]
0x1800b0b89  mov     r15, rax
0x1800b0b8c  call    cs:__imp_GetCurrentThreadId
0x1800b0b93  nop     dword ptr [rax+rax+00h]
0x1800b0b98  mov     ecx, eax; dwThreadId
0x1800b0b9a  call    cs:__imp_GetThreadDesktop
0x1800b0ba1  nop     dword ptr [rax+rax+00h]
0x1800b0ba6  xor     r9d, r9d; nLength
0x1800b0ba9  xor     r8d, r8d; pvInfo
0x1800b0bac  mov     r12, rax
0x1800b0baf  mov     rcx, r15; hObj
0x1800b0bb2  lea     rax, [rbp+nLengthNeeded]
0x1800b0bb6  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800b0bbb  lea     edx, [r9+2]; nIndex
0x1800b0bbf  call    cs:__imp_GetUserObjectInformationW
0x1800b0bc6  nop     dword ptr [rax+rax+00h]
0x1800b0bcb  xor     r9d, r9d; nLength
0x1800b0bce  lea     rax, [rbp+nLength]
0x1800b0bd2  xor     r8d, r8d; pvInfo
0x1800b0bd5  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800b0bda  mov     rcx, r12; hObj
0x1800b0bdd  lea     edx, [r9+2]; nIndex
0x1800b0be1  call    cs:__imp_GetUserObjectInformationW
0x1800b0be8  nop     dword ptr [rax+rax+00h]
0x1800b0bed  mov     edx, [rbp+nLengthNeeded]
0x1800b0bf0  mov     ecx, 40h ; '@'; uFlags
0x1800b0bf5  add     edx, [rbp+nLength]; uBytes
0x1800b0bf8  call    cs:__imp_LocalAlloc
0x1800b0bff  nop     dword ptr [rax+rax+00h]
0x1800b0c04  mov     rbx, rax
0x1800b0c07  test    rax, rax
0x1800b0c0a  jz      loc_1800B0B48
0x1800b0c10  mov     r9d, [rbp+nLengthNeeded]; nLength
0x1800b0c14  lea     rax, [rbp+nLengthNeeded]
0x1800b0c18  mov     r8, rbx; pvInfo
0x1800b0c1b  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800b0c20  mov     edx, 2; nIndex
0x1800b0c25  mov     rcx, r15; hObj
0x1800b0c28  call    cs:__imp_GetUserObjectInformationW
0x1800b0c2f  nop     dword ptr [rax+rax+00h]
0x1800b0c34  test    eax, eax
0x1800b0c36  jnz     short loc_1800B0C48
0x1800b0c38  call    cs:__imp_GetLastError
0x1800b0c3f  nop     dword ptr [rax+rax+00h]
0x1800b0c44  mov     edi, eax
0x1800b0c46  jmp     short loc_1800B0CAC
0x1800b0c48  mov     eax, [rbp+nLengthNeeded]
0x1800b0c4b  mov     edx, 2; nIndex
0x1800b0c50  shr     rax, 1
0x1800b0c53  mov     rcx, r12; hObj
0x1800b0c56  mov     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800b0c5d  mov     eax, [rbp+nLengthNeeded]
0x1800b0c60  mov     r9d, [rbp+nLength]; nLength
0x1800b0c64  shr     rax, 1
0x1800b0c67  lea     r8, [rbx+rax*2]; pvInfo
0x1800b0c6b  lea     rax, [rbp+nLength]
0x1800b0c6f  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800b0c74  call    cs:__imp_GetUserObjectInformationW
0x1800b0c7b  nop     dword ptr [rax+rax+00h]
0x1800b0c80  test    eax, eax
0x1800b0c82  jnz     short loc_1800B0CA6
0x1800b0c84  jmp     short loc_1800B0C38
0x1800b0c86  mov     edx, 2; uBytes
0x1800b0c8b  lea     ecx, [rdx+3Eh]; uFlags
0x1800b0c8e  call    cs:__imp_LocalAlloc
0x1800b0c95  nop     dword ptr [rax+rax+00h]
0x1800b0c9a  mov     rbx, rax
0x1800b0c9d  test    rax, rax
0x1800b0ca0  jz      loc_1800B0B48
0x1800b0ca6  mov     [r14], rbx
0x1800b0ca9  mov     rbx, r13
0x1800b0cac  mov     rcx, rbx; hMem
0x1800b0caf  call    cs:__imp_LocalFree
0x1800b0cb6  nop     dword ptr [rax+rax+00h]
0x1800b0cbb  movaps  xmm6, [rsp+50h+var_10]
0x1800b0cc0  lea     r11, [rsp+50h+var_s0]
0x1800b0cc5  mov     rbx, [r11+40h]
0x1800b0cc9  mov     eax, edi
0x1800b0ccb  mov     rdi, [r11+48h]
0x1800b0ccf  movaps  xmm7, [rsp+50h+var_20]
0x1800b0cd4  mov     rsp, r11
0x1800b0cd7  pop     r15
0x1800b0cd9  pop     r14
0x1800b0cdb  pop     r13
0x1800b0cdd  pop     r12
0x1800b0cdf  pop     rbp
0x1800b0ce0  retn
```
