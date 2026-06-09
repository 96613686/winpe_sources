# CscUmFindOpenPattern

- ea: `0x180007b40`
- end: `0x180007daa`
- name: `CscUmFindOpenPattern`
- size: `618`
- prototype: `__int64 __fastcall(void ***, struct _UNICODE_STRING *, const UNICODE_STRING *, void *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008310`
- `0x180028a88`
- `0x18006ba50`

## callees

- `0x1800068b0`
- `0x180007280`
- `0x180007b40`
- `0x180007db0`
- `0x180039610`
- `0x180039fb4`
- `0x180087608`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180007d84`
- `ntdll!RtlValidSid` at `0x180007d84`
- `ntdll!RtlLengthSid` at `0x180007d58`
- `ntdll!RtlLengthSid` at `0x180007d58`
- `ntdll!RtlDuplicateUnicodeString` at `0x180007cc4`
- `ntdll!RtlDuplicateUnicodeString` at `0x180007cc4`
- `KERNEL32!LocalAlloc` at `0x180007bd9`
- `KERNEL32!LocalAlloc` at `0x180007d65`
- `KERNEL32!LocalAlloc` at `0x180007bd9`
- `KERNEL32!LocalAlloc` at `0x180007d65`

## pseudocode

```c
__int64 __fastcall CscUmFindOpenPattern(
        void ***a1,
        struct _UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        void *a4,
        int a5)
{
  bool v5; // zf
  void **v9; // rbx
  struct _UNICODE_STRING *v10; // rbp
  void *v11; // r14
  struct _UNICODE_STRING *v12; // rax
  int v13; // edi
  __int64 result; // rax
  void *v15; // rcx
  __int64 v16; // rdx
  ULONG v17; // r13d
  HLOCAL v18; // rax
  int v19; // [rsp+40h] [rbp-148h] BYREF
  _DWORD v20[2]; // [rsp+48h] [rbp-140h] BYREF
  _QWORD v21[10]; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v22[144]; // [rsp+A0h] [rbp-E8h] BYREF

  v21[0] = 393220;
  v5 = CscUmpLibraryState == 0;
  v21[1] = L"\\\\";
  *a1 = 0;
  if ( !v5 )
  {
    v9 = 0;
    if ( (a5 & 0xFFFFFFFE) != 0 )
    {
      v13 = -1073741811;
      goto LABEL_10;
    }
    v10 = (struct _UNICODE_STRING *)v21;
    if ( a2 )
      v10 = a2;
    v11 = 0;
    if ( a4 )
    {
      v17 = RtlLengthSid(a4);
      v18 = LocalAlloc(0, v17);
      v11 = v18;
      if ( !v18 )
        goto LABEL_23;
      memcpy_0(v18, a4, v17);
      if ( !RtlValidSid(v11) )
      {
        v13 = -1073741811;
        goto LABEL_10;
      }
    }
    v12 = (struct _UNICODE_STRING *)LocalAlloc(0, 0x30u);
    v9 = (void **)v12;
    if ( v12 )
    {
      *v12 = 0;
      v12[1] = 0;
      v12[2] = 0;
      *(_DWORD *)&v12->Length = 1130718291;
      LOBYTE(v12[2].Length) = 1;
      v12[2].Buffer = (PWSTR)v11;
      if ( !a3 || !a3->Length || (v13 = RtlDuplicateUnicodeString(0, a3, v12 + 1), v13 >= 0) )
      {
        v13 = CscDriverOpenItemWithDispositionEx(v9 + 1, 0, v10, ((a5 & 1) << 11) | 6u, 1048577, 7u, 1u, 1);
        if ( v13 >= 0 )
        {
          v19 = 0;
          memset_0(v22, 0, 0x88u);
          v15 = v9[1];
          v20[0] = 8;
          v20[1] = 2;
          v13 = CscDriverpFsControlEx(v15, v16, &v19, v20, 8u, v22, 0x88u);
          if ( v13 >= 0 )
          {
            if ( (v22[48] & 0x10) != 0 )
              goto LABEL_10;
            v13 = -1073741565;
          }
        }
      }
      CscUmFindClose(v9);
      v9 = 0;
LABEL_10:
      result = (unsigned int)v13;
      *a1 = v9;
      return result;
    }
LABEL_23:
    v13 = -1073741670;
    goto LABEL_10;
  }
  return 3221225860LL;
}

```

## disassembly

```asm
0x180007b40  mov     r11, rsp
0x180007b43  push    rdi
0x180007b44  push    r12
0x180007b46  push    r13
0x180007b48  push    r15
0x180007b4a  sub     rsp, 168h
0x180007b51  mov     rax, cs:__security_cookie
0x180007b58  xor     rax, rsp
0x180007b5b  mov     [rsp+188h+var_58], rax
0x180007b63  xor     r13d, r13d
0x180007b66  mov     [rsp+188h+var_138], 60004h
0x180007b6f  cmp     cs:CscUmpLibraryState, r13d
0x180007b76  lea     rax, asc_18008FC74; "\\\\"
0x180007b7d  mov     r12, r9
0x180007b80  mov     [rsp+188h+var_130], rax
0x180007b85  mov     rdi, r8
0x180007b88  mov     [rcx], r13
0x180007b8b  mov     r15, rcx
0x180007b8e  jz      loc_180007CA3
0x180007b94  mov     [r11-28h], rbx
0x180007b98  mov     ebx, r13d
0x180007b9b  mov     [r11-38h], rsi
0x180007b9f  mov     esi, [rsp+188h+arg_20]
0x180007ba6  test    esi, 0FFFFFFFEh
0x180007bac  jnz     loc_180007CAA
0x180007bb2  mov     [r11-30h], rbp
0x180007bb6  test    rdx, rdx
0x180007bb9  lea     rbp, [rsp+188h+var_138]
0x180007bbe  mov     [r11-40h], r14
0x180007bc2  cmovnz  rbp, rdx
0x180007bc6  mov     r14d, r13d
0x180007bc9  test    r9, r9
0x180007bcc  jnz     loc_180007D55
0x180007bd2  mov     edx, 30h ; '0'; uBytes
0x180007bd7  xor     ecx, ecx; uFlags
0x180007bd9  call    cs:__imp_LocalAlloc
0x180007bdf  mov     rbx, rax
0x180007be2  test    rax, rax
0x180007be5  jz      loc_180007DA0
0x180007beb  xorps   xmm0, xmm0
0x180007bee  movups  xmmword ptr [rax], xmm0
0x180007bf1  movups  xmmword ptr [rax+10h], xmm0
0x180007bf5  movups  xmmword ptr [rax+20h], xmm0
0x180007bf9  mov     dword ptr [rax], 43656453h
0x180007bff  mov     byte ptr [rax+20h], 1
0x180007c03  mov     [rax+28h], r14
0x180007c07  test    rdi, rdi
0x180007c0a  jnz     loc_180007CB1
0x180007c10  mov     [rsp+188h+var_150], 1; int
0x180007c18  lea     rcx, [rbx+8]; FileHandle
0x180007c1c  and     esi, 1
0x180007c1f  mov     [rsp+188h+var_158], 1; ULONG
0x180007c27  shl     esi, 0Bh
0x180007c2a  mov     r8, rbp
0x180007c2d  or      esi, 6
0x180007c30  mov     dword ptr [rsp+188h+var_160], 7; ULONG
0x180007c38  mov     r9d, esi
0x180007c3b  mov     [rsp+188h+var_168], 100001h; int
0x180007c43  xor     edx, edx
0x180007c45  call    CscDriverOpenItemWithDispositionEx
0x180007c4a  mov     edi, eax
0x180007c4c  test    eax, eax
0x180007c4e  jns     loc_180007CD9
0x180007c54  mov     rcx, rbx; hMem
0x180007c57  call    CscUmFindClose
0x180007c5c  mov     rbx, r13
0x180007c5f  mov     rbp, [rsp+188h+var_30]
0x180007c67  mov     r14, [rsp+188h+var_40]
0x180007c6f  mov     rsi, [rsp+188h+var_38]
0x180007c77  mov     eax, edi
0x180007c79  mov     [r15], rbx
0x180007c7c  mov     rbx, [rsp+188h+var_28]
0x180007c84  mov     rcx, [rsp+188h+var_58]
0x180007c8c  xor     rcx, rsp; StackCookie
0x180007c8f  call    __security_check_cookie
0x180007c94  add     rsp, 168h
0x180007c9b  pop     r15
0x180007c9d  pop     r13
0x180007c9f  pop     r12
0x180007ca1  pop     rdi
0x180007ca2  retn
0x180007ca3  mov     eax, 0C0000184h
0x180007ca8  jmp     short loc_180007C84
0x180007caa  mov     edi, 0C000000Dh
0x180007caf  jmp     short loc_180007C6F
0x180007cb1  cmp     word ptr [rdi], 0
0x180007cb5  jz      loc_180007C10
0x180007cbb  lea     r8, [rax+10h]; DestinationString
0x180007cbf  mov     rdx, rdi; SourceString
0x180007cc2  xor     ecx, ecx; Flags
0x180007cc4  call    cs:__imp_RtlDuplicateUnicodeString
0x180007cca  mov     edi, eax
0x180007ccc  test    eax, eax
0x180007cce  jns     loc_180007C10
0x180007cd4  jmp     loc_180007C54
0x180007cd9  xor     edx, edx; Val
0x180007cdb  mov     [rsp+188h+var_148], r13d
0x180007ce0  mov     r8d, 88h; Size
0x180007ce6  lea     rcx, [rsp+188h+var_E8]; void *
0x180007cee  call    memset_0
0x180007cf3  mov     rcx, [rbx+8]; FileHandle
0x180007cf7  lea     rax, [rsp+188h+var_E8]
0x180007cff  mov     [rsp+188h+var_158], 88h; ULONG
0x180007d07  lea     r9, [rsp+188h+var_140]
0x180007d0c  mov     [rsp+188h+var_160], rax; PVOID
0x180007d11  lea     r8, [rsp+188h+var_148]
0x180007d16  mov     [rsp+188h+var_168], 8; ULONG
0x180007d1e  mov     [rsp+188h+var_140], 8
0x180007d26  mov     [rsp+188h+var_13C], 2
0x180007d2e  call    CscDriverpFsControlEx
0x180007d33  mov     edi, eax
0x180007d35  test    eax, eax
0x180007d37  js      loc_180007C54
0x180007d3d  test    [rsp+188h+var_B8], 10h
0x180007d45  jnz     loc_180007C5F
0x180007d4b  mov     edi, 0C0000103h
0x180007d50  jmp     loc_180007C54
0x180007d55  mov     rcx, r12; Sid
0x180007d58  call    cs:__imp_RtlLengthSid
0x180007d5e  mov     edx, eax; uBytes
0x180007d60  xor     ecx, ecx; uFlags
0x180007d62  mov     r13d, eax
0x180007d65  call    cs:__imp_LocalAlloc
0x180007d6b  mov     r14, rax
0x180007d6e  test    rax, rax
0x180007d71  jz      short loc_180007DA0
0x180007d73  mov     r8d, r13d; Size
0x180007d76  mov     rdx, r12; Src
0x180007d79  mov     rcx, rax; void *
0x180007d7c  call    memcpy_0
0x180007d81  mov     rcx, r14; Sid
0x180007d84  call    cs:__imp_RtlValidSid
0x180007d8a  test    al, al
0x180007d8c  jnz     short loc_180007D98
0x180007d8e  mov     edi, 0C000000Dh
0x180007d93  jmp     loc_180007C5F
0x180007d98  xor     r13d, r13d
0x180007d9b  jmp     loc_180007BD2
0x180007da0  mov     edi, 0C000009Ah
0x180007da5  jmp     loc_180007C5F
```
