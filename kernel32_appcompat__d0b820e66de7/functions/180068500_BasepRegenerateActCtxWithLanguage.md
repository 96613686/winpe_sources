# BasepRegenerateActCtxWithLanguage

- ea: `0x180068500`
- end: `0x180068737`
- name: `BasepRegenerateActCtxWithLanguage`
- size: `567`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180068500`

## import_xrefs

- `ntdll!RtlQueryInformationActivationContext` at `0x18006858a`
- `ntdll!RtlQueryInformationActivationContext` at `0x1800685ff`
- `ntdll!RtlQueryInformationActivationContext` at `0x180068696`
- `ntdll!RtlQueryInformationActivationContext` at `0x18006858a`
- `ntdll!RtlQueryInformationActivationContext` at `0x1800685ff`
- `ntdll!RtlQueryInformationActivationContext` at `0x180068696`
- `ntdll!wcsrchr` at `0x180068642`
- `ntdll!wcsrchr` at `0x180068642`
- `ntdll!RtlFreeHeap` at `0x18006870a`
- `ntdll!RtlFreeHeap` at `0x18006870a`
- `ntdll!RtlAllocateHeap` at `0x1800685c1`
- `ntdll!RtlAllocateHeap` at `0x1800685c1`
- `ntdll!_wcsicmp` at `0x18006865d`
- `ntdll!_wcsicmp` at `0x18006865d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800686d0`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800686d0`

## string_xrefs

- `0x180068653`: `.Manifest`

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
0x180068500  mov     [rsp-28h+arg_0], rbx
0x180068505  push    rbp
0x180068506  push    rsi
0x180068507  push    rdi
0x180068508  push    r14
0x18006850a  push    r15
0x18006850c  mov     rbp, rsp
0x18006850f  sub     rsp, 80h
0x180068516  xor     eax, eax
0x180068518  mov     [rbp+pActCtx.cbSize], 38h ; '8'
0x18006851f  mov     dword ptr [rbp+pActCtx.hModule+4], eax
0x180068522  xorps   xmm0, xmm0
0x180068525  mov     [rbp+Size], rax
0x180068529  mov     r14, r8
0x18006852c  mov     [rbp+arg_10], eax
0x18006852f  movzx   r15d, dx
0x180068533  mov     rdi, rcx
0x180068536  movups  xmmword ptr [rbp+pActCtx.dwFlags], xmm0
0x18006853a  movups  xmmword ptr [rbp+pActCtx+14h], xmm0
0x18006853e  movups  xmmword ptr [rbp+pActCtx.lpResourceName+4], xmm0
0x180068542  test    r8, r8
0x180068545  jz      loc_180068718
0x18006854b  mov     [r8], rax
0x18006854e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180068552  jz      loc_180068718
0x180068558  lea     rax, [rbp+Size]
0x18006855c  mov     [rbp+pvSubInstance], 1
0x180068564  mov     [rsp+80h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x180068569  lea     r8, [rbp+pvSubInstance]; pvSubInstance
0x18006856d  mov     rdx, rcx; Context
0x180068570  mov     [rsp+80h+cbBuffer], 0; cbBuffer
0x180068579  mov     r9d, 3; ulInfoClass
0x18006857f  mov     [rsp+80h+pvBuffer], 0; pvBuffer
0x180068588  xor     ecx, ecx; dwFlags
0x18006858a  call    cs:__imp_RtlQueryInformationActivationContext
0x180068591  nop     dword ptr [rax+rax+00h]
0x180068596  mov     ebx, eax
0x180068598  cmp     eax, 0C0000023h
0x18006859d  jnz     loc_18006871D
0x1800685a3  cmp     [rbp+Size], 0
0x1800685a8  jz      loc_18006871D
0x1800685ae  mov     rcx, gs:60h
0x1800685b7  xor     edx, edx; Flags
0x1800685b9  mov     r8, [rbp+Size]; Size
0x1800685bd  mov     rcx, [rcx+30h]; HeapHandle
0x1800685c1  call    cs:__imp_RtlAllocateHeap
0x1800685c8  nop     dword ptr [rax+rax+00h]
0x1800685cd  mov     rsi, rax
0x1800685d0  test    rax, rax
0x1800685d3  jz      loc_18006871D
0x1800685d9  mov     rcx, [rbp+Size]
0x1800685dd  lea     rax, [rbp+Size]
0x1800685e1  mov     [rsp+80h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x1800685e6  lea     r8, [rbp+pvSubInstance]; pvSubInstance
0x1800685ea  mov     [rsp+80h+cbBuffer], rcx; cbBuffer
0x1800685ef  mov     r9d, 3; ulInfoClass
0x1800685f5  xor     ecx, ecx; dwFlags
0x1800685f7  mov     [rsp+80h+pvBuffer], rsi; pvBuffer
0x1800685fc  mov     rdx, rdi; Context
0x1800685ff  call    cs:__imp_RtlQueryInformationActivationContext
0x180068606  nop     dword ptr [rax+rax+00h]
0x18006860b  mov     ebx, eax
0x18006860d  test    eax, eax
0x18006860f  js      loc_1800686F8
0x180068615  cmp     rdi, 0FFFFFFFFFFFFFFFCh
0x180068619  jnz     short loc_180068631
0x18006861b  mov     ecx, [rbp+pActCtx.dwFlags]
0x18006861e  or      ecx, 40h
0x180068621  mov     [rbp+pActCtx.dwFlags], ecx
0x180068624  mov     rax, [rsi+40h]
0x180068628  mov     [rbp+pActCtx.lpSource], rax
0x18006862c  jmp     loc_1800686C1
0x180068631  mov     rax, [rsi+48h]
0x180068635  mov     edx, 2Eh ; '.'; Ch
0x18006863a  mov     [rbp+pActCtx.lpSource], rax
0x18006863e  mov     rcx, [rsi+48h]; Str
0x180068642  call    cs:__imp_wcsrchr
0x180068649  nop     dword ptr [rax+rax+00h]
0x18006864e  test    rax, rax
0x180068651  jz      short loc_18006866D
0x180068653  lea     rdx, aManifest; ".Manifest"
0x18006865a  mov     rcx, rax; String1
0x18006865d  call    cs:__imp__wcsicmp
0x180068664  nop     dword ptr [rax+rax+00h]
0x180068669  test    eax, eax
0x18006866b  jz      short loc_1800686BE
0x18006866d  lea     rax, [rbp+Size]
0x180068671  mov     r9d, 7; ulInfoClass
0x180068677  mov     [rsp+80h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x18006867c  xor     r8d, r8d; pvSubInstance
0x18006867f  lea     rax, [rbp+arg_10]
0x180068683  mov     [rsp+80h+cbBuffer], 4; cbBuffer
0x18006868c  mov     rdx, rdi; Context
0x18006868f  mov     [rsp+80h+pvBuffer], rax; pvBuffer
0x180068694  xor     ecx, ecx; dwFlags
0x180068696  call    cs:__imp_RtlQueryInformationActivationContext
0x18006869d  nop     dword ptr [rax+rax+00h]
0x1800686a2  mov     ebx, eax
0x1800686a4  test    eax, eax
0x1800686a6  js      short loc_1800686F8
0x1800686a8  mov     eax, [rbp+arg_10]
0x1800686ab  test    eax, eax
0x1800686ad  jz      short loc_1800686BE
0x1800686af  mov     ecx, [rbp+pActCtx.dwFlags]
0x1800686b2  movzx   eax, ax
0x1800686b5  or      ecx, 8
0x1800686b8  mov     [rbp+pActCtx.lpResourceName], rax
0x1800686bc  jmp     short loc_1800686C1
0x1800686be  mov     ecx, [rbp+pActCtx.dwFlags]
0x1800686c1  or      ecx, 2
0x1800686c4  mov     [rbp+pActCtx.wLangId], r15w
0x1800686c9  mov     [rbp+pActCtx.dwFlags], ecx
0x1800686cc  lea     rcx, [rbp+pActCtx]; pActCtx
0x1800686d0  call    cs:__imp_CreateActCtxW
0x1800686d7  nop     dword ptr [rax+rax+00h]
0x1800686dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800686e0  jnz     short loc_1800686F3
0x1800686e2  mov     rax, gs:30h
0x1800686eb  mov     ebx, [rax+1250h]
0x1800686f1  jmp     short loc_1800686F8
0x1800686f3  mov     [r14], rax
0x1800686f6  xor     ebx, ebx
0x1800686f8  mov     rcx, gs:60h
0x180068701  mov     r8, rsi; P
0x180068704  xor     edx, edx; Flags
0x180068706  mov     rcx, [rcx+30h]; HeapHandle
0x18006870a  call    cs:__imp_RtlFreeHeap
0x180068711  nop     dword ptr [rax+rax+00h]
0x180068716  jmp     short loc_18006871D
0x180068718  mov     ebx, 0C000000Dh
0x18006871d  mov     eax, ebx
0x18006871f  mov     rbx, [rsp+80h+arg_0]
0x180068727  add     rsp, 80h
0x18006872e  pop     r15
0x180068730  pop     r14
0x180068732  pop     rdi
0x180068733  pop     rsi
0x180068734  pop     rbp
0x180068735  retn
```
