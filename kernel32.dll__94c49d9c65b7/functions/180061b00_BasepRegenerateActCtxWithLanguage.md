# BasepRegenerateActCtxWithLanguage

- ea: `0x180061b00`
- end: `0x180061d03`
- name: `BasepRegenerateActCtxWithLanguage`
- size: `515`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180061b00`

## import_xrefs

- `ntdll!RtlQueryInformationActivationContext` at `0x180061b8a`
- `ntdll!RtlQueryInformationActivationContext` at `0x180061bf3`
- `ntdll!RtlQueryInformationActivationContext` at `0x180061c75`
- `ntdll!RtlQueryInformationActivationContext` at `0x180061b8a`
- `ntdll!RtlQueryInformationActivationContext` at `0x180061bf3`
- `ntdll!RtlQueryInformationActivationContext` at `0x180061c75`
- `ntdll!wcsrchr` at `0x180061c2d`
- `ntdll!wcsrchr` at `0x180061c2d`
- `ntdll!RtlFreeHeap` at `0x180061cdd`
- `ntdll!RtlFreeHeap` at `0x180061cdd`
- `ntdll!RtlAllocateHeap` at `0x180061bbb`
- `ntdll!RtlAllocateHeap` at `0x180061bbb`
- `ntdll!_wcsicmp` at `0x180061c42`
- `ntdll!_wcsicmp` at `0x180061c42`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180061ca9`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180061ca9`

## string_xrefs

- `0x180061c38`: `.Manifest`

## pseudocode

```c
__int64 __fastcall BasepRegenerateActCtxWithLanguage(PVOID Context, LANGID a2, _QWORD *a3)
{
  int LastStatusValue; // ebx
  LPCWSTR *pvBuffer; // rsi
  DWORD dwFlags; // ecx
  wchar_t *v9; // rax
  HANDLE v10; // rax
  __int64 pvSubInstance; // [rsp+40h] [rbp-40h] BYREF
  ACTCTXW pActCtx; // [rsp+48h] [rbp-38h] BYREF
  int v14; // [rsp+C0h] [rbp+40h] BYREF
  SIZE_T Size; // [rsp+C8h] [rbp+48h] BYREF

  pActCtx.cbSize = 56;
  Size = 0;
  v14 = 0;
  memset(&pActCtx.dwFlags, 0, 52);
  if ( !a3 )
    return (unsigned int)-1073741811;
  *a3 = 0;
  if ( Context == (PVOID)-1LL )
    return (unsigned int)-1073741811;
  pvSubInstance = 1;
  LastStatusValue = RtlQueryInformationActivationContext(0, Context, &pvSubInstance, 3u, 0, 0, &Size);
  if ( LastStatusValue == -1073741789 )
  {
    if ( Size )
    {
      pvBuffer = (LPCWSTR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
      if ( pvBuffer )
      {
        LastStatusValue = RtlQueryInformationActivationContext(0, Context, &pvSubInstance, 3u, pvBuffer, Size, &Size);
        if ( LastStatusValue >= 0 )
        {
          if ( Context == (PVOID)-4LL )
          {
            dwFlags = pActCtx.dwFlags | 0x40;
            pActCtx.dwFlags |= 0x40u;
            pActCtx.lpSource = pvBuffer[8];
            goto LABEL_15;
          }
          pActCtx.lpSource = pvBuffer[9];
          v9 = wcsrchr(pvBuffer[9], 0x2Eu);
          if ( v9 && !_wcsicmp(v9, L".Manifest") )
            goto LABEL_14;
          LastStatusValue = RtlQueryInformationActivationContext(0, Context, 0, 7u, &v14, 4u, &Size);
          if ( LastStatusValue >= 0 )
          {
            if ( v14 )
            {
              dwFlags = pActCtx.dwFlags | 8;
              pActCtx.lpResourceName = (LPCWSTR)(unsigned __int16)v14;
              goto LABEL_15;
            }
LABEL_14:
            dwFlags = pActCtx.dwFlags;
LABEL_15:
            pActCtx.wLangId = a2;
            pActCtx.dwFlags = dwFlags | 2;
            v10 = CreateActCtxW(&pActCtx);
            if ( v10 == (HANDLE)-1LL )
            {
              LastStatusValue = NtCurrentTeb()->LastStatusValue;
            }
            else
            {
              *a3 = v10;
              LastStatusValue = 0;
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pvBuffer);
      }
    }
  }
  return (unsigned int)LastStatusValue;
}

```

## disassembly

```asm
0x180061b00  mov     [rsp-28h+arg_0], rbx
0x180061b05  push    rbp
0x180061b06  push    rsi
0x180061b07  push    rdi
0x180061b08  push    r14
0x180061b0a  push    r15
0x180061b0c  mov     rbp, rsp
0x180061b0f  sub     rsp, 80h
0x180061b16  xor     eax, eax
0x180061b18  mov     [rbp+pActCtx.cbSize], 38h ; '8'
0x180061b1f  mov     dword ptr [rbp+pActCtx.hModule+4], eax
0x180061b22  xorps   xmm0, xmm0
0x180061b25  mov     [rbp+Size], rax
0x180061b29  mov     r14, r8
0x180061b2c  mov     [rbp+arg_10], eax
0x180061b2f  movzx   r15d, dx
0x180061b33  mov     rdi, rcx
0x180061b36  movups  xmmword ptr [rbp+pActCtx.dwFlags], xmm0
0x180061b3a  movups  xmmword ptr [rbp+pActCtx+14h], xmm0
0x180061b3e  movups  xmmword ptr [rbp+pActCtx.lpResourceName+4], xmm0
0x180061b42  test    r8, r8
0x180061b45  jz      loc_180061CE5
0x180061b4b  mov     [r8], rax
0x180061b4e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180061b52  jz      loc_180061CE5
0x180061b58  lea     rax, [rbp+Size]
0x180061b5c  mov     [rbp+pvSubInstance], 1
0x180061b64  mov     [rsp+80h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x180061b69  lea     r8, [rbp+pvSubInstance]; pvSubInstance
0x180061b6d  mov     rdx, rcx; Context
0x180061b70  mov     [rsp+80h+cbBuffer], 0; cbBuffer
0x180061b79  mov     r9d, 3; ulInfoClass
0x180061b7f  mov     [rsp+80h+pvBuffer], 0; pvBuffer
0x180061b88  xor     ecx, ecx; dwFlags
0x180061b8a  call    cs:__imp_RtlQueryInformationActivationContext
0x180061b90  mov     ebx, eax
0x180061b92  cmp     eax, 0C0000023h
0x180061b97  jnz     loc_180061CEA
0x180061b9d  cmp     [rbp+Size], 0
0x180061ba2  jz      loc_180061CEA
0x180061ba8  mov     rcx, gs:60h
0x180061bb1  xor     edx, edx; Flags
0x180061bb3  mov     r8, [rbp+Size]; Size
0x180061bb7  mov     rcx, [rcx+30h]; HeapHandle
0x180061bbb  call    cs:__imp_RtlAllocateHeap
0x180061bc1  mov     rsi, rax
0x180061bc4  test    rax, rax
0x180061bc7  jz      loc_180061CEA
0x180061bcd  mov     rcx, [rbp+Size]
0x180061bd1  lea     rax, [rbp+Size]
0x180061bd5  mov     [rsp+80h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x180061bda  lea     r8, [rbp+pvSubInstance]; pvSubInstance
0x180061bde  mov     [rsp+80h+cbBuffer], rcx; cbBuffer
0x180061be3  mov     r9d, 3; ulInfoClass
0x180061be9  xor     ecx, ecx; dwFlags
0x180061beb  mov     [rsp+80h+pvBuffer], rsi; pvBuffer
0x180061bf0  mov     rdx, rdi; Context
0x180061bf3  call    cs:__imp_RtlQueryInformationActivationContext
0x180061bf9  mov     ebx, eax
0x180061bfb  test    eax, eax
0x180061bfd  js      loc_180061CCB
0x180061c03  cmp     rdi, 0FFFFFFFFFFFFFFFCh
0x180061c07  jnz     short loc_180061C1C
0x180061c09  mov     ecx, [rbp+pActCtx.dwFlags]
0x180061c0c  or      ecx, 40h
0x180061c0f  mov     [rbp+pActCtx.dwFlags], ecx
0x180061c12  mov     rax, [rsi+40h]
0x180061c16  mov     [rbp+pActCtx.lpSource], rax
0x180061c1a  jmp     short loc_180061C9A
0x180061c1c  mov     rax, [rsi+48h]
0x180061c20  mov     edx, 2Eh ; '.'; Ch
0x180061c25  mov     [rbp+pActCtx.lpSource], rax
0x180061c29  mov     rcx, [rsi+48h]; Str
0x180061c2d  call    cs:__imp_wcsrchr
0x180061c33  test    rax, rax
0x180061c36  jz      short loc_180061C4C
0x180061c38  lea     rdx, aManifest; ".Manifest"
0x180061c3f  mov     rcx, rax; String1
0x180061c42  call    cs:__imp__wcsicmp
0x180061c48  test    eax, eax
0x180061c4a  jz      short loc_180061C97
0x180061c4c  lea     rax, [rbp+Size]
0x180061c50  mov     r9d, 7; ulInfoClass
0x180061c56  mov     [rsp+80h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x180061c5b  xor     r8d, r8d; pvSubInstance
0x180061c5e  lea     rax, [rbp+arg_10]
0x180061c62  mov     [rsp+80h+cbBuffer], 4; cbBuffer
0x180061c6b  mov     rdx, rdi; Context
0x180061c6e  mov     [rsp+80h+pvBuffer], rax; pvBuffer
0x180061c73  xor     ecx, ecx; dwFlags
0x180061c75  call    cs:__imp_RtlQueryInformationActivationContext
0x180061c7b  mov     ebx, eax
0x180061c7d  test    eax, eax
0x180061c7f  js      short loc_180061CCB
0x180061c81  mov     eax, [rbp+arg_10]
0x180061c84  test    eax, eax
0x180061c86  jz      short loc_180061C97
0x180061c88  mov     ecx, [rbp+pActCtx.dwFlags]
0x180061c8b  movzx   eax, ax
0x180061c8e  or      ecx, 8
0x180061c91  mov     [rbp+pActCtx.lpResourceName], rax
0x180061c95  jmp     short loc_180061C9A
0x180061c97  mov     ecx, [rbp+pActCtx.dwFlags]
0x180061c9a  or      ecx, 2
0x180061c9d  mov     [rbp+pActCtx.wLangId], r15w
0x180061ca2  mov     [rbp+pActCtx.dwFlags], ecx
0x180061ca5  lea     rcx, [rbp+pActCtx]; pActCtx
0x180061ca9  call    cs:__imp_CreateActCtxW
0x180061caf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061cb3  jnz     short loc_180061CC6
0x180061cb5  mov     rax, gs:30h
0x180061cbe  mov     ebx, [rax+1250h]
0x180061cc4  jmp     short loc_180061CCB
0x180061cc6  mov     [r14], rax
0x180061cc9  xor     ebx, ebx
0x180061ccb  mov     rcx, gs:60h
0x180061cd4  mov     r8, rsi; P
0x180061cd7  xor     edx, edx; Flags
0x180061cd9  mov     rcx, [rcx+30h]; HeapHandle
0x180061cdd  call    cs:__imp_RtlFreeHeap
0x180061ce3  jmp     short loc_180061CEA
0x180061ce5  mov     ebx, 0C000000Dh
0x180061cea  mov     eax, ebx
0x180061cec  mov     rbx, [rsp+80h+arg_0]
0x180061cf4  add     rsp, 80h
0x180061cfb  pop     r15
0x180061cfd  pop     r14
0x180061cff  pop     rdi
0x180061d00  pop     rsi
0x180061d01  pop     rbp
0x180061d02  retn
```
