# CiHvciSetFileVersionInformation

- ea: `0x180075ae0`
- end: `0x180075d31`
- name: `CiHvciSetFileVersionInformation`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x18000eda0`
- `0x18002bfd0`
- `0x180059680`
- `0x180074e64`
- `0x180075ae0`
- `0x1800999f0`

## import_xrefs

- `ntoskrnl!LdrResFindResource` at `0x180075c88`
- `ntoskrnl!LdrResFindResource` at `0x180075c88`

## pseudocode

```c
__int64 __fastcall CiHvciSetFileVersionInformation(__int64 a1, __int64 a2, char *a3, unsigned int a4)
{
  int FileOffsetForRva; // ecx
  int Resource; // eax
  unsigned int v10; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-64h] BYREF
  __int64 v12; // [rsp+58h] [rbp-60h] BYREF
  DWORD v13; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v14; // [rsp+64h] [rbp-54h] BYREF
  unsigned int v15; // [rsp+68h] [rbp-50h] BYREF
  int v16; // [rsp+6Ch] [rbp-4Ch]
  __int64 v17; // [rsp+70h] [rbp-48h] BYREF
  __int64 v18; // [rsp+78h] [rbp-40h]
  _QWORD v19[7]; // [rsp+80h] [rbp-38h] BYREF

  v12 = 0;
  v17 = 0;
  v13 = 0;
  v18 = 0;
  v19[0] = 0;
  v11 = 0;
  v15 = 0;
  v10 = 0;
  v14 = 0;
  FileOffsetForRva = CipSetFileVersionInformation();
  if ( FileOffsetForRva >= 0 )
  {
    FileOffsetForRva = CiValidateImageHeaderMapping(a3, a4, &v17, &v13);
    if ( FileOffsetForRva >= 0 )
    {
      if ( (g_CiPolicyState & 0x400000) == 0
        || (int)CiGetHotpatchSequenceNumberAndRegionsFromImage(
                  v17,
                  v13,
                  (_DWORD)a3,
                  a4,
                  0,
                  (__int64)&v10,
                  (__int64)&v14,
                  (__int64)&v11,
                  (__int64)&v15) < 0 )
      {
        goto LABEL_10;
      }
      FileOffsetForRva = CiGetFileOffsetForRva(v17, v10, &v12);
      if ( FileOffsetForRva >= 0 )
        FileOffsetForRva = ((__int64 (__fastcall *)(_QWORD, __int64, char *, _QWORD, __int64))xmmword_1800495E0)(
                             *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
                             1,
                             &a3[v10],
                             v14,
                             v12);
      if ( FileOffsetForRva >= 0 )
      {
        FileOffsetForRva = CiGetFileOffsetForRva(v17, v11, &v12);
        if ( FileOffsetForRva >= 0 )
        {
          FileOffsetForRva = ((__int64 (__fastcall *)(_QWORD, __int64, char *, _QWORD, __int64))xmmword_1800495E0)(
                               *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
                               2,
                               &a3[v11],
                               v15,
                               v12);
          if ( FileOffsetForRva >= 0 )
          {
LABEL_10:
            Resource = LdrResFindResource(a3, 16, 1);
            FileOffsetForRva = Resource;
            v16 = Resource;
            if ( Resource >= 0 )
            {
              if ( (unsigned __int64)(v18 - (_QWORD)a3) > 0xFFFFFFFF )
              {
                return (unsigned int)-1073741675;
              }
              else
              {
                FileOffsetForRva = CiGetFileOffsetForRva(v17, v18 - (_QWORD)a3, &v12);
                if ( FileOffsetForRva >= 0 )
                  return (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _QWORD *, _QWORD, _QWORD, _DWORD))xmmword_1800495E0)(
                                         *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
                                         0,
                                         v18,
                                         v19[0],
                                         v12,
                                         v19,
                                         0,
                                         0,
                                         0);
              }
            }
            else if ( (unsigned int)(Resource + 1073741687) <= 2 || Resource == -1073741308 )
            {
              FileOffsetForRva = 0;
              v16 = 0;
            }
          }
        }
      }
    }
  }
  return (unsigned int)FileOffsetForRva;
}

```

## disassembly

```asm
0x180075ae0  mov     rax, rsp
0x180075ae3  push    rbx
0x180075ae4  push    rsi
0x180075ae5  push    rdi
0x180075ae6  push    r14
0x180075ae8  sub     rsp, 98h
0x180075aef  mov     edi, r9d
0x180075af2  mov     rbx, r8
0x180075af5  mov     rsi, rcx
0x180075af8  xor     r14d, r14d
0x180075afb  mov     [rax-60h], r14
0x180075aff  mov     [rax-48h], r14
0x180075b03  mov     [rax-58h], r14d
0x180075b07  mov     [rax-40h], r14
0x180075b0b  mov     [rax-38h], r14
0x180075b0f  mov     [rax-64h], r14d
0x180075b13  mov     [rax-50h], r14d
0x180075b17  mov     [rax-68h], r14d
0x180075b1b  mov     [rax-54h], r14d
0x180075b1f  call    CipSetFileVersionInformation
0x180075b24  mov     ecx, eax
0x180075b26  test    eax, eax
0x180075b28  js      loc_180075D21
0x180075b2e  lea     r9, [rsp+0B8h+var_58]
0x180075b33  lea     r8, [rsp+0B8h+var_48]
0x180075b38  mov     edx, edi; Size
0x180075b3a  mov     rcx, rbx; BaseAddress
0x180075b3d  call    CiValidateImageHeaderMapping
0x180075b42  mov     ecx, eax
0x180075b44  test    eax, eax
0x180075b46  js      loc_180075D21
0x180075b4c  test    cs:g_CiPolicyState, 400000h
0x180075b56  jz      loc_180075C54
0x180075b5c  lea     rax, [rsp+0B8h+var_50]
0x180075b61  mov     [rsp+0B8h+var_78], rax
0x180075b66  lea     rax, [rsp+0B8h+var_64]
0x180075b6b  mov     [rsp+0B8h+var_80], rax
0x180075b70  lea     rax, [rsp+0B8h+var_54]
0x180075b75  mov     [rsp+0B8h+var_88], rax
0x180075b7a  lea     rax, [rsp+0B8h+var_68]
0x180075b7f  mov     [rsp+0B8h+var_90], rax
0x180075b84  mov     [rsp+0B8h+var_98], r14
0x180075b89  mov     r9d, edi
0x180075b8c  mov     r8, rbx
0x180075b8f  mov     edx, [rsp+0B8h+var_58]
0x180075b93  mov     rcx, [rsp+0B8h+var_48]
0x180075b98  call    CiGetHotpatchSequenceNumberAndRegionsFromImage
0x180075b9d  test    eax, eax
0x180075b9f  js      loc_180075C54
0x180075ba5  lea     r8, [rsp+0B8h+var_60]
0x180075baa  mov     edx, [rsp+0B8h+var_68]
0x180075bae  mov     rcx, [rsp+0B8h+var_48]
0x180075bb3  call    CiGetFileOffsetForRva
0x180075bb8  mov     ecx, eax
0x180075bba  test    eax, eax
0x180075bbc  js      short loc_180075BF2
0x180075bbe  mov     r9d, [rsp+0B8h+var_54]
0x180075bc3  mov     r8d, [rsp+0B8h+var_68]
0x180075bc8  add     r8, rbx
0x180075bcb  mov     rcx, [rsi+0BF0h]
0x180075bd2  mov     rax, qword ptr cs:xmmword_1800495E0
0x180075bd9  mov     rdx, [rsp+0B8h+var_60]
0x180075bde  mov     [rsp+0B8h+var_98], rdx
0x180075be3  lea     edx, [r14+1]
0x180075be7  mov     rcx, [rcx+10h]
0x180075beb  call    _guard_dispatch_icall
0x180075bf0  mov     ecx, eax
0x180075bf2  test    ecx, ecx
0x180075bf4  js      loc_180075D21
0x180075bfa  lea     r8, [rsp+0B8h+var_60]
0x180075bff  mov     edx, [rsp+0B8h+var_64]
0x180075c03  mov     rcx, [rsp+0B8h+var_48]
0x180075c08  call    CiGetFileOffsetForRva
0x180075c0d  mov     ecx, eax
0x180075c0f  test    eax, eax
0x180075c11  js      loc_180075D21
0x180075c17  mov     r9d, [rsp+0B8h+var_50]
0x180075c1c  mov     r8d, [rsp+0B8h+var_64]
0x180075c21  add     r8, rbx
0x180075c24  mov     rcx, [rsi+0BF0h]
0x180075c2b  mov     rax, qword ptr cs:xmmword_1800495E0
0x180075c32  mov     rdx, [rsp+0B8h+var_60]
0x180075c37  mov     [rsp+0B8h+var_98], rdx
0x180075c3c  mov     edx, 2
0x180075c41  mov     rcx, [rcx+10h]
0x180075c45  call    _guard_dispatch_icall
0x180075c4a  mov     ecx, eax
0x180075c4c  test    eax, eax
0x180075c4e  js      loc_180075D21
0x180075c54  mov     dword ptr [rsp+0B8h+var_78], r14d
0x180075c59  mov     [rsp+0B8h+var_80], r14
0x180075c5e  mov     [rsp+0B8h+var_88], r14
0x180075c63  lea     rax, [rsp+0B8h+var_38]
0x180075c6b  mov     [rsp+0B8h+var_90], rax
0x180075c70  lea     rax, [rsp+0B8h+var_40]
0x180075c75  mov     [rsp+0B8h+var_98], rax
0x180075c7a  xor     r9d, r9d
0x180075c7d  lea     edx, [r9+10h]
0x180075c81  lea     r8d, [r9+1]
0x180075c85  mov     rcx, rbx
0x180075c88  call    cs:__imp_LdrResFindResource
0x180075c8f  nop     dword ptr [rax+rax+00h]
0x180075c94  mov     ecx, eax
0x180075c96  mov     [rsp+0B8h+var_4C], eax
0x180075c9a  test    eax, eax
0x180075c9c  jns     short loc_180075CB9
0x180075c9e  add     eax, 3FFFFF77h
0x180075ca3  cmp     eax, 2
0x180075ca6  jbe     short loc_180075CB0
0x180075ca8  cmp     ecx, 0C0000204h
0x180075cae  jnz     short loc_180075CB7
0x180075cb0  mov     ecx, r14d
0x180075cb3  mov     [rsp+0B8h+var_4C], ecx
0x180075cb7  jmp     short loc_180075D21
0x180075cb9  mov     rdx, [rsp+0B8h+var_40]
0x180075cbe  sub     rdx, rbx
0x180075cc1  mov     eax, 0FFFFFFFFh
0x180075cc6  cmp     rdx, rax
0x180075cc9  ja      short loc_180075D14
0x180075ccb  lea     r8, [rsp+0B8h+var_60]
0x180075cd0  mov     rcx, [rsp+0B8h+var_48]
0x180075cd5  call    CiGetFileOffsetForRva
0x180075cda  mov     ecx, eax
0x180075cdc  test    eax, eax
0x180075cde  js      short loc_180075D21
0x180075ce0  mov     rcx, [rsi+0BF0h]
0x180075ce7  mov     rax, qword ptr cs:xmmword_1800495E0
0x180075cee  mov     rdx, [rsp+0B8h+var_60]
0x180075cf3  mov     [rsp+0B8h+var_98], rdx
0x180075cf8  mov     r9, [rsp+0B8h+var_38]
0x180075d00  mov     r8, [rsp+0B8h+var_40]
0x180075d05  xor     edx, edx
0x180075d07  mov     rcx, [rcx+10h]
0x180075d0b  call    _guard_dispatch_icall
0x180075d10  mov     ecx, eax
0x180075d12  jmp     short loc_180075D21
0x180075d14  mov     ecx, 0C0000095h
0x180075d19  jmp     short loc_180075D21
0x180075d1b  mov     ecx, eax
0x180075d1d  mov     [rsp+0B8h+var_4C], eax
0x180075d21  mov     eax, ecx
0x180075d23  add     rsp, 98h
0x180075d2a  pop     r14
0x180075d2c  pop     rdi
0x180075d2d  pop     rsi
0x180075d2e  pop     rbx
0x180075d2f  retn
```
