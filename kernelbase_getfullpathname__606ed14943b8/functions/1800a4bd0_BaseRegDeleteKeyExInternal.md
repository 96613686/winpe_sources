# BaseRegDeleteKeyExInternal

- ea: `0x1800a4bd0`
- end: `0x1800a4f6b`
- name: `BaseRegDeleteKeyExInternal`
- size: `923`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCUNICODE_STRING Source@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a4a40`

## callees

- `0x18005f8a0`
- `0x18005fa00`
- `0x180060700`
- `0x180060db0`
- `0x1800a4bd0`
- `0x180114974`
- `0x1801369c9`
- `0x180139854`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a4dda`
- `ntdll!RtlNtStatusToDosError` at `0x1800a4dda`
- `ntdll!NtDeleteKey` at `0x1800a4db6`
- `ntdll!NtDeleteKey` at `0x1800a4db6`
- `ntdll!NtClose` at `0x1800a4dc7`
- `ntdll!NtClose` at `0x1800a4f5a`
- `ntdll!NtClose` at `0x1800a4dc7`
- `ntdll!NtClose` at `0x1800a4f5a`
- `ntdll!RtlFreeHeap` at `0x1800a4d75`
- `ntdll!RtlFreeHeap` at `0x1800a4ec9`
- `ntdll!RtlFreeHeap` at `0x1800a4d75`
- `ntdll!RtlFreeHeap` at `0x1800a4ec9`
- `ntdll!NtOpenKeyEx` at `0x1800a4d4f`
- `ntdll!NtOpenKeyEx` at `0x1800a4d4f`
- `ntdll!NtSetInformationKey` at `0x1800a4f3f`
- `ntdll!NtSetInformationKey` at `0x1800a4f3f`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteKey` at `0x1800a4da3`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteKey` at `0x1800a4da3`

## pseudocode

```c
ULONG __fastcall BaseRegDeleteKeyExInternal(HANDLE KeyHandle, UNICODE_STRING *Source, __int16 a3, int a4, void *a5)
{
  HANDLE v7; // r15
  HANDLE v8; // rdi
  unsigned int Length; // ecx
  PWSTR Buffer; // rdx
  UNICODE_STRING v11; // xmm6
  unsigned int v12; // esi
  __int128 v13; // xmm0
  NTSTATUS KeySemantics; // ebx
  int v15; // esi
  int v17; // eax
  NTSTATUS v18; // eax
  __int64 v19; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE KeySetInformation; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE KeyHandlea; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE KeyHandle_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  _OWORD v23[2]; // [rsp+70h] [rbp-98h]
  PVOID P; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v25[3]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v26[400]; // [rsp+C8h] [rbp-40h] BYREF

  KeyHandlea = KeyHandle;
  HIDWORD(KeyHandle_8[0]) = 0;
  HIDWORD(v23[0]) = 0;
  v7 = KeyHandle;
  KeySetInformation = 0;
  v8 = 0;
  if ( Source )
  {
    Length = Source->Length;
    if ( (unsigned __int16)Length >= 2u )
    {
      Buffer = Source->Buffer;
      if ( Buffer )
      {
        if ( (Length & 1) == 0 && !Buffer[((unsigned __int64)Length >> 1) - 1] && !a4 )
        {
          v11 = *Source;
          Source->Length = Length - 2;
          if ( ((unsigned __int8)v7 & 2) != 0
            || (g_RegKrnGlobalState & 2) != 0 && (v17 = ExtractClassKey(&KeyHandlea, Source, a5), v7 = KeyHandlea, v17) )
          {
            memset_0(v26, 0, 0x182u);
            *(HANDLE *)((char *)KeyHandle_8 + 4) = 0;
            *(_QWORD *)&v23[0] = v26;
            HIDWORD(KeyHandle_8[1]) = 386;
            LODWORD(KeyHandle_8[0]) = 0;
            KeySemantics = BaseRegGetKeySemantics(v7, Source);
            if ( KeySemantics >= 0 )
            {
              KeySemantics = BaseRegOpenClassKeyFromLocation(
                               (__int64)KeyHandle_8,
                               v7,
                               (__int64)Source,
                               a3 & 0x300 | 0x2000000u,
                               3,
                               0,
                               &KeySetInformation,
                               a5);
              if ( ((__int64)KeyHandle_8[0] & 0x20) != 0 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v23[0]);
              v8 = KeySetInformation;
            }
            if ( KeySemantics < 0 )
              goto LABEL_21;
            goto LABEL_17;
          }
          v12 = a3 & 0x300 | 0x10000;
          LODWORD(KeyHandle_8[0]) = 48;
          KeyHandle_8[1] = (HANDLE)__PAIR64__(HIDWORD(KeyHandlea), (unsigned int)v7);
          DWORD2(v23[0]) = 64;
          *(_QWORD *)&v23[0] = Source;
          v23[1] = 0;
          if ( a5 )
          {
            v18 = Wow64NtOpenKey((unsigned int)&KeySetInformation, v12, (unsigned int)KeyHandle_8, 0, (__int64)a5);
            v8 = KeySetInformation;
            KeySemantics = v18;
          }
          else
          {
            v13 = *(_OWORD *)KeyHandle_8;
            KeyHandle_8[0] = 0;
            LOWORD(KeyHandle_8[1]) = 0;
            BYTE2(KeyHandle_8[1]) = 0;
            P = 0;
            v25[0] = v13;
            LODWORD(KeySetInformation) = 0;
            v25[1] = v23[0];
            KeyHandlea = 0;
            v25[2] = 0;
            LOBYTE(v19) = 0;
            KeySemantics = ConstructKernelKeyPath(
                             v12,
                             (unsigned int)v25,
                             (unsigned int)&KeySetInformation,
                             (unsigned int)KeyHandle_8,
                             (__int64)&v19,
                             (__int64)&P);
            if ( KeySemantics >= 0 )
            {
              v15 = NtOpenKeyEx(&KeyHandlea, v12, v25, 0);
              if ( P )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              if ( v15 >= 0 )
              {
                if ( (_BYTE)v19 )
                {
                  if ( (_DWORD)KeySetInformation )
                  {
                    LODWORD(KeySetInformation) = (unsigned __int16)KeySetInformation & 0xF01;
                    KeySemantics = NtSetInformationKey(KeyHandlea, KeySetHandleTagsInformation, &KeySetInformation, 4u);
                    if ( KeySemantics < 0 )
                    {
                      NtClose(KeyHandlea);
                      goto LABEL_17;
                    }
                  }
                }
                v8 = KeyHandlea;
              }
              KeySemantics = v15;
            }
          }
LABEL_17:
          if ( (unsigned __int8)IsTermsrvDeleteKeyPresent() )
            TermsrvDeleteKey(v8);
          if ( KeySemantics >= 0 )
          {
            KeySemantics = NtDeleteKey(v8);
            NtClose(v8);
          }
LABEL_21:
          *Source = v11;
          return RtlNtStatusToDosError(KeySemantics);
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x1800a4bd0  mov     rax, rsp
0x1800a4bd3  mov     [rax+20h], rbx
0x1800a4bd7  push    rbp
0x1800a4bd8  push    rsi
0x1800a4bd9  push    rdi
0x1800a4bda  push    r12
0x1800a4bdc  push    r13
0x1800a4bde  push    r14
0x1800a4be0  push    r15
0x1800a4be2  lea     rbp, [rax-1A8h]
0x1800a4be9  sub     rsp, 270h
0x1800a4bf0  movaps  xmmword ptr [rax-48h], xmm6
0x1800a4bf4  mov     rax, cs:__security_cookie
0x1800a4bfb  xor     rax, rsp
0x1800a4bfe  mov     [rbp+1A0h+var_50], rax
0x1800a4c05  mov     r12, [rbp+1A0h+arg_20]
0x1800a4c0c  xor     r13d, r13d
0x1800a4c0f  mov     [rsp+2A0h+KeyHandle], rcx
0x1800a4c14  mov     esi, r8d
0x1800a4c17  mov     dword ptr [rsp+2A0h+KeyHandle+0Ch], r13d
0x1800a4c1c  mov     r14, rdx
0x1800a4c1f  mov     dword ptr [rsp+2A0h+var_230+4], r13d
0x1800a4c24  mov     r15, rcx
0x1800a4c27  mov     [rsp+2A0h+KeySetInformation], r13
0x1800a4c2c  mov     edi, r13d
0x1800a4c2f  test    rdx, rdx
0x1800a4c32  jz      loc_1800A4EE7
0x1800a4c38  movzx   ecx, word ptr [rdx]
0x1800a4c3b  mov     r8w, 2
0x1800a4c40  cmp     cx, r8w
0x1800a4c44  jb      loc_1800A4EE7
0x1800a4c4a  mov     rdx, [rdx+8]
0x1800a4c4e  test    rdx, rdx
0x1800a4c51  jz      loc_1800A4EE7
0x1800a4c57  test    cl, 1
0x1800a4c5a  jnz     loc_1800A4EE7
0x1800a4c60  mov     eax, ecx
0x1800a4c62  shr     rax, 1
0x1800a4c65  cmp     [rdx+rax*2-2], r13w
0x1800a4c6b  jnz     loc_1800A4EE7
0x1800a4c71  test    r9d, r9d
0x1800a4c74  jnz     loc_1800A4EE7
0x1800a4c7a  movups  xmm6, xmmword ptr [r14]
0x1800a4c7e  sub     cx, r8w
0x1800a4c82  mov     [r14], cx
0x1800a4c86  test    r8b, r15b
0x1800a4c89  jnz     loc_1800A4E33
0x1800a4c8f  test    byte ptr cs:g_RegKrnGlobalState, r8b
0x1800a4c96  jnz     loc_1800A4E16
0x1800a4c9c  mov     eax, dword ptr [rsp+2A0h+KeyHandle+4]
0x1800a4ca0  and     esi, 300h
0x1800a4ca6  bts     esi, 10h
0x1800a4caa  mov     dword ptr [rsp+2A0h+KeyHandle+8], 30h ; '0'
0x1800a4cb2  mov     dword ptr [rsp+2A0h+var_240], r15d
0x1800a4cb7  xorps   xmm2, xmm2
0x1800a4cba  mov     dword ptr [rsp+2A0h+var_240+4], eax
0x1800a4cbe  mov     dword ptr [rsp+2A0h+var_230], 40h ; '@'
0x1800a4cc6  mov     [rsp+2A0h+var_240+8], r14
0x1800a4ccb  movdqu  xmmword ptr [rsp+2A0h+var_230+8], xmm2
0x1800a4cd1  test    r12, r12
0x1800a4cd4  jnz     loc_1800A4EF1
0x1800a4cda  movups  xmm0, xmmword ptr [rsp+2A0h+KeyHandle+8]
0x1800a4cdf  xor     eax, eax
0x1800a4ce1  lea     r9, [rsp+2A0h+KeyHandle+8]
0x1800a4ce6  movups  xmm1, xmmword ptr [rsp+2A0h+var_240+8]
0x1800a4ceb  mov     [rsp+2A0h+KeyHandle+8], rax
0x1800a4cf0  lea     r8, [rsp+2A0h+KeySetInformation]
0x1800a4cf5  mov     word ptr [rsp+2A0h+var_240], ax
0x1800a4cfa  lea     rdx, [rbp+1A0h+var_210]
0x1800a4cfe  mov     byte ptr [rsp+2A0h+var_240+2], al
0x1800a4d02  mov     ecx, esi
0x1800a4d04  lea     rax, [rbp+1A0h+P]
0x1800a4d08  mov     [rbp+1A0h+P], r13
0x1800a4d0c  mov     [rsp+2A0h+var_278], rax
0x1800a4d11  lea     rax, [rsp+2A0h+var_260]
0x1800a4d16  mov     [rsp+2A0h+var_280], rax
0x1800a4d1b  movups  [rbp+1A0h+var_210], xmm0
0x1800a4d1f  mov     dword ptr [rsp+2A0h+KeySetInformation], r13d
0x1800a4d24  movups  [rbp+1A0h+var_200], xmm1
0x1800a4d28  mov     [rsp+2A0h+KeyHandle], r13
0x1800a4d2d  movups  [rbp+1A0h+var_1F0], xmm2
0x1800a4d31  mov     byte ptr [rsp+2A0h+var_260], r13b
0x1800a4d36  call    ConstructKernelKeyPath
0x1800a4d3b  mov     ebx, eax
0x1800a4d3d  test    eax, eax
0x1800a4d3f  js      short loc_1800A4D97
0x1800a4d41  xor     r9d, r9d
0x1800a4d44  lea     r8, [rbp+1A0h+var_210]
0x1800a4d48  mov     edx, esi
0x1800a4d4a  lea     rcx, [rsp+2A0h+KeyHandle]
0x1800a4d4f  call    cs:__imp_NtOpenKeyEx
0x1800a4d56  nop     dword ptr [rax+rax+00h]
0x1800a4d5b  mov     r8, [rbp+1A0h+P]; P
0x1800a4d5f  mov     esi, eax
0x1800a4d61  test    r8, r8
0x1800a4d64  jz      short loc_1800A4D81
0x1800a4d66  mov     rcx, gs:60h
0x1800a4d6f  xor     edx, edx; Flags
0x1800a4d71  mov     rcx, [rcx+30h]; HeapHandle
0x1800a4d75  call    cs:__imp_RtlFreeHeap
0x1800a4d7c  nop     dword ptr [rax+rax+00h]
0x1800a4d81  test    esi, esi
0x1800a4d83  js      short loc_1800A4D95
0x1800a4d85  cmp     byte ptr [rsp+2A0h+var_260], r13b
0x1800a4d8a  jnz     loc_1800A4F16
0x1800a4d90  mov     rdi, [rsp+2A0h+KeyHandle]
0x1800a4d95  mov     ebx, esi
0x1800a4d97  call    IsTermsrvDeleteKeyPresent
0x1800a4d9c  test    al, al
0x1800a4d9e  jz      short loc_1800A4DAF
0x1800a4da0  mov     rcx, rdi
0x1800a4da3  call    cs:__imp_TermsrvDeleteKey
0x1800a4daa  nop     dword ptr [rax+rax+00h]
0x1800a4daf  test    ebx, ebx
0x1800a4db1  js      short loc_1800A4DD3
0x1800a4db3  mov     rcx, rdi; KeyHandle
0x1800a4db6  call    cs:__imp_NtDeleteKey
0x1800a4dbd  nop     dword ptr [rax+rax+00h]
0x1800a4dc2  mov     rcx, rdi; Handle
0x1800a4dc5  mov     ebx, eax
0x1800a4dc7  call    cs:__imp_NtClose
0x1800a4dce  nop     dword ptr [rax+rax+00h]
0x1800a4dd3  mov     ecx, ebx; Status
0x1800a4dd5  movdqu  xmmword ptr [r14], xmm6
0x1800a4dda  call    cs:__imp_RtlNtStatusToDosError
0x1800a4de1  nop     dword ptr [rax+rax+00h]
0x1800a4de6  mov     rcx, [rbp+1A0h+var_50]
0x1800a4ded  xor     rcx, rsp; StackCookie
0x1800a4df0  call    __security_check_cookie
0x1800a4df5  lea     r11, [rsp+2A0h+var_30]
0x1800a4dfd  mov     rbx, [r11+58h]
0x1800a4e01  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a4e06  mov     rsp, r11
0x1800a4e09  pop     r15
0x1800a4e0b  pop     r14
0x1800a4e0d  pop     r13
0x1800a4e0f  pop     r12
0x1800a4e11  pop     rdi
0x1800a4e12  pop     rsi
0x1800a4e13  pop     rbp
0x1800a4e14  retn
0x1800a4e16  mov     r8, r12
0x1800a4e19  lea     rcx, [rsp+2A0h+KeyHandle]
0x1800a4e1e  mov     rdx, r14
0x1800a4e21  call    ExtractClassKey
0x1800a4e26  mov     r15, [rsp+2A0h+KeyHandle]
0x1800a4e2b  test    eax, eax
0x1800a4e2d  jz      loc_1800A4C9C
0x1800a4e33  mov     ebx, 182h
0x1800a4e38  lea     rcx, [rbp+1A0h+var_1E0]; void *
0x1800a4e3c  mov     r8d, ebx; Size
0x1800a4e3f  xor     edx, edx; Val
0x1800a4e41  call    memset_0
0x1800a4e46  lea     rax, [rbp+1A0h+var_1E0]
0x1800a4e4a  mov     [rsp+2A0h+KeyHandle+0Ch], r13
0x1800a4e4f  lea     r8, [rsp+2A0h+KeyHandle+8]
0x1800a4e54  mov     [rsp+2A0h+var_240+8], rax
0x1800a4e59  mov     rdx, r14; Source
0x1800a4e5c  mov     dword ptr [rsp+2A0h+var_240+4], ebx
0x1800a4e60  mov     rcx, r15; KeyHandle
0x1800a4e63  mov     dword ptr [rsp+2A0h+KeyHandle+8], r13d
0x1800a4e68  call    BaseRegGetKeySemantics
0x1800a4e6d  mov     ebx, eax
0x1800a4e6f  test    eax, eax
0x1800a4e71  js      short loc_1800A4EDA
0x1800a4e73  mov     qword ptr [rsp+2A0h+var_268], r12
0x1800a4e78  lea     rax, [rsp+2A0h+KeySetInformation]
0x1800a4e7d  mov     [rsp+2A0h+var_270], rax
0x1800a4e82  lea     rcx, [rsp+2A0h+KeyHandle+8]
0x1800a4e87  and     esi, 300h
0x1800a4e8d  mov     dword ptr [rsp+2A0h+var_278], r13d
0x1800a4e92  bts     esi, 19h
0x1800a4e96  mov     dword ptr [rsp+2A0h+var_280], 3
0x1800a4e9e  mov     r9d, esi
0x1800a4ea1  mov     r8, r14
0x1800a4ea4  mov     rdx, r15
0x1800a4ea7  call    BaseRegOpenClassKeyFromLocation
0x1800a4eac  test    byte ptr [rsp+2A0h+KeyHandle+8], 20h
0x1800a4eb1  mov     ebx, eax
0x1800a4eb3  jz      short loc_1800A4ED5
0x1800a4eb5  mov     rcx, gs:60h
0x1800a4ebe  xor     edx, edx; Flags
0x1800a4ec0  mov     r8, [rsp+2A0h+var_240+8]; P
0x1800a4ec5  mov     rcx, [rcx+30h]; HeapHandle
0x1800a4ec9  call    cs:__imp_RtlFreeHeap
0x1800a4ed0  nop     dword ptr [rax+rax+00h]
0x1800a4ed5  mov     rdi, [rsp+2A0h+KeySetInformation]
0x1800a4eda  test    ebx, ebx
0x1800a4edc  jns     loc_1800A4D97
0x1800a4ee2  jmp     loc_1800A4DD3
0x1800a4ee7  mov     eax, 57h ; 'W'
0x1800a4eec  jmp     loc_1800A4DE6
0x1800a4ef1  xor     r9d, r9d
0x1800a4ef4  mov     [rsp+2A0h+var_280], r12
0x1800a4ef9  lea     r8, [rsp+2A0h+KeyHandle+8]
0x1800a4efe  mov     edx, esi
0x1800a4f00  lea     rcx, [rsp+2A0h+KeySetInformation]
0x1800a4f05  call    Wow64NtOpenKey
0x1800a4f0a  mov     rdi, [rsp+2A0h+KeySetInformation]
0x1800a4f0f  mov     ebx, eax
0x1800a4f11  jmp     loc_1800A4D97
0x1800a4f16  mov     eax, dword ptr [rsp+2A0h+KeySetInformation]
0x1800a4f1a  test    eax, eax
0x1800a4f1c  jz      loc_1800A4D90
0x1800a4f22  mov     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x1800a4f27  lea     r8, [rsp+2A0h+KeySetInformation]; KeySetInformation
0x1800a4f2c  mov     r9d, 4; KeySetInformationLength
0x1800a4f32  and     eax, 0F01h
0x1800a4f37  mov     dword ptr [rsp+2A0h+KeySetInformation], eax
0x1800a4f3b  lea     edx, [r9+1]; KeySetInformationClass
0x1800a4f3f  call    cs:__imp_NtSetInformationKey
0x1800a4f46  nop     dword ptr [rax+rax+00h]
0x1800a4f4b  mov     ebx, eax
0x1800a4f4d  test    eax, eax
0x1800a4f4f  jns     loc_1800A4D90
0x1800a4f55  mov     rcx, [rsp+2A0h+KeyHandle]; Handle
0x1800a4f5a  call    cs:__imp_NtClose
0x1800a4f61  nop     dword ptr [rax+rax+00h]
0x1800a4f66  jmp     loc_1800A4D97
```
