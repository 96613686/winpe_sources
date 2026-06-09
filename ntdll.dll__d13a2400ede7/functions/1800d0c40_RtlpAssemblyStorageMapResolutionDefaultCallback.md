# RtlpAssemblyStorageMapResolutionDefaultCallback

- ea: `0x1800d0c40`
- end: `0x1800d101d`
- name: `RtlpAssemblyStorageMapResolutionDefaultCallback`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800d0560`

## callees

- `0x18001a080`
- `0x180077e50`
- `0x180079280`
- `0x1800d0c40`
- `0x1800d1648`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015f120`
- `0x180162810`
- `0x180164280`
- `0x18016f030`

## string_xrefs

- `0x1800d0dd9`: `SXS: Unable to open registry key %wZ Status = 0x%08lx\n`
- `0x1800d0d56`: `SXS: Attempt to get storage location from subkey %wZ failed; Status = 0x%08lx\n`

## pseudocode

```c
int __fastcall RtlpAssemblyStorageMapResolutionDefaultCallback(int a1, __int64 a2, _DWORD *a3)
{
  int v5; // ecx
  __int64 v6; // rcx
  unsigned __int64 v7; // rax
  HANDLE v8; // r15
  unsigned int v9; // r12d
  int v10; // r14d
  int v11; // eax
  const wchar_t *NtSystemRoot; // rax
  const wchar_t *v13; // r15
  size_t v14; // r14
  unsigned int v15; // ecx
  size_t v16; // r15
  wchar_t *Buffer; // rdx
  char *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v22; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h]
  _BYTE v27[12]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v28; // [rsp+8Ch] [rbp-74h]
  char v29; // [rsp+90h] [rbp-70h] BYREF

  v5 = a1 - 1;
  if ( !v5 )
  {
    v25[0] = 48;
    v25[3] = 64;
    v23 = 0;
    v25[1] = 0;
    v25[2] = &qword_180170E90;
    v26 = 0;
    v11 = NtOpenKey(&v23, 8, v25);
    v10 = v11;
    if ( v11 >= 0 || v11 == -1073741772 || v11 == -1073741431 )
    {
      LODWORD(v7) = v23;
      *(_QWORD *)(a2 + 16) = v23;
      *(_QWORD *)(a2 + 48) = -1;
      return v7;
    }
    LODWORD(v7) = DbgPrintEx(51, 0, "SXS: Unable to open registry key %wZ Status = 0x%08lx\n", &qword_180170E90, v11);
    *(_BYTE *)(a2 + 56) = 1;
    goto LABEL_15;
  }
  v6 = (unsigned int)(v5 - 1);
  if ( (_DWORD)v6 )
  {
    LODWORD(v7) = 2;
    if ( (_DWORD)v6 == 2 && *(_QWORD *)a2 )
      LODWORD(v7) = NtClose(*(HANDLE *)a2);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 8) )
    {
      if ( *(_QWORD *)(a2 + 8) != 1 )
      {
        LODWORD(v7) = -1;
        if ( *(_QWORD *)(a2 + 8) <= 0xFFFFFFFF )
        {
          LODWORD(v7) = (unsigned int)memset_thunk_772440563353939046(v27, 0, 0x220u);
          v8 = *(HANDLE *)a2;
          v9 = *(_DWORD *)(a2 + 8) - 2;
          LODWORD(v23) = 0;
          v24 = 0;
          if ( v8 )
          {
            LODWORD(v7) = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD, _BYTE *, int, __int64 *))NtEnumerateKey)(
                            v8,
                            v9,
                            0,
                            v27,
                            544,
                            &v23);
            v10 = v7;
            if ( (v7 & 0x80000000) == 0LL )
            {
              LODWORD(v7) = v28;
              if ( v28 <= 0xFFFE )
              {
                LOWORD(v24) = v28;
                WORD1(v24) = v28;
                *((_QWORD *)&v24 + 1) = &v29;
                LODWORD(v7) = RtlpGetAssemblyStorageMapRootLocation(v8, &v24, a2 + 24);
                v10 = v7;
                if ( (v7 & 0x80000000) == 0LL )
                  return v7;
                LODWORD(v22) = v7;
                LODWORD(v7) = DbgPrintEx(
                                51,
                                0,
                                "SXS: Attempt to get storage location from subkey %wZ failed; Status = 0x%08lx\n",
                                &v24,
                                v22);
                goto LABEL_41;
              }
              *(_BYTE *)(a2 + 16) = 1;
              goto LABEL_31;
            }
            if ( (_DWORD)v7 != -2147483622 )
            {
              LODWORD(v7) = DbgPrintEx(
                              51,
                              0,
                              "SXS: Unable to enumerate assembly storage subkey #%lu Status = 0x%08lx\n",
                              v9,
                              v7);
LABEL_41:
              *(_BYTE *)(a2 + 16) = 1;
LABEL_15:
              if ( a3 )
                *a3 = v10;
              return v7;
            }
          }
        }
        *(_BYTE *)(a2 + 17) = 1;
        return v7;
      }
      NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot(v6, a2, a3);
      v13 = NtSystemRoot;
      if ( NtSystemRoot )
      {
        v14 = 2 * wcslen(NtSystemRoot);
        if ( v14 >= 0xFFFE )
          LOWORD(v14) = -4;
      }
      else
      {
        LOWORD(v14) = 0;
      }
      v15 = *(unsigned __int16 *)(a2 + 26);
      LODWORD(v7) = (unsigned __int16)v14 + 16;
      *(_WORD *)(a2 + 24) = 0;
      if ( (unsigned int)v7 <= v15 )
      {
        memmove(*(void **)(a2 + 32), v13, (unsigned __int16)v14);
        v7 = *(_QWORD *)(a2 + 32);
        *(_OWORD *)((unsigned __int16)v14 + v7) = *(_OWORD *)L"\\WinSxS\\";
        *(_WORD *)(a2 + 24) = v14 + 16;
        return v7;
      }
      *(_BYTE *)(a2 + 16) = 1;
      goto LABEL_43;
    }
    v7 = (unsigned __int64)NtCurrentPeb();
    if ( (*(_DWORD *)(*(_QWORD *)(v7 + 32) + 8LL) & 0x8000) == 0 )
    {
      *(_WORD *)(a2 + 24) = 0;
      return v7;
    }
    v7 = (unsigned __int64)NtCurrentPeb();
    v16 = *(unsigned __int16 *)(*(_QWORD *)(v7 + 32) + 96LL);
    if ( v16 + 16 > 0xFFFE )
    {
      *(_BYTE *)(a2 + 16) = 1;
LABEL_31:
      if ( a3 )
        *a3 = -1073741562;
      return v7;
    }
    v7 = *(unsigned __int16 *)(a2 + 26);
    if ( v16 + 16 > v7 )
    {
      *(_BYTE *)(a2 + 16) = 1;
LABEL_43:
      if ( a3 )
        *a3 = -1073741789;
      return v7;
    }
    Buffer = NtCurrentPeb()->ProcessParameters->ImagePathName.Buffer;
    if ( (NtCurrentPeb()->ProcessParameters->Flags & 1) == 0 )
      Buffer = (wchar_t *)((char *)Buffer + (unsigned __int64)NtCurrentPeb()->ProcessParameters);
    v18 = *(char **)(a2 + 32);
    memmove(v18, Buffer, v16);
    LOBYTE(v19) = 1;
    *(_OWORD *)&v18[v16] = xmmword_18017CAA8;
    v20 = *(_QWORD *)(a2 + 32);
    *(_WORD *)(a2 + 24) = v16 + 14;
    LODWORD(v7) = RtlDoesFileExists_UEx(v20, v19);
    if ( !(_BYTE)v7 )
      *(_WORD *)(a2 + 24) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800d0c40  mov     [rsp-8+arg_0], rbx
0x1800d0c45  mov     [rsp-8+arg_18], rsi
0x1800d0c4a  push    rbp
0x1800d0c4b  push    rdi
0x1800d0c4c  push    r12
0x1800d0c4e  push    r14
0x1800d0c50  push    r15
0x1800d0c52  lea     rbp, [rsp-1B0h]
0x1800d0c5a  sub     rsp, 2B0h
0x1800d0c61  mov     rax, cs:__security_cookie
0x1800d0c68  xor     rax, rsp
0x1800d0c6b  mov     [rbp+1D0h+var_30], rax
0x1800d0c72  mov     rbx, r8
0x1800d0c75  mov     rsi, rdx
0x1800d0c78  sub     ecx, 1
0x1800d0c7b  jz      loc_1800D0D6C
0x1800d0c81  sub     ecx, 1
0x1800d0c84  jnz     loc_1800D0EBF
0x1800d0c8a  xor     edi, edi
0x1800d0c8c  cmp     [rdx+8], rdi
0x1800d0c90  jz      loc_1800D0E22
0x1800d0c96  cmp     qword ptr [rdx+8], 1
0x1800d0c9b  jz      loc_1800D0E42
0x1800d0ca1  mov     eax, 0FFFFFFFFh
0x1800d0ca6  cmp     [rdx+8], rax
0x1800d0caa  ja      loc_1800D0EFA
0x1800d0cb0  mov     r14d, 220h
0x1800d0cb6  lea     rcx, [rbp+1D0h+var_250]; void *
0x1800d0cba  mov     r8d, r14d; Size
0x1800d0cbd  xor     edx, edx; Val
0x1800d0cbf  call    memset$thunk$772440563353939046
0x1800d0cc4  mov     r12d, [rsi+8]
0x1800d0cc8  xorps   xmm0, xmm0
0x1800d0ccb  mov     r15, [rsi]
0x1800d0cce  add     r12d, 0FFFFFFFEh
0x1800d0cd2  mov     dword ptr [rsp+2D0h+var_2A0], edi
0x1800d0cd6  movups  [rsp+2D0h+var_298], xmm0
0x1800d0cdb  test    r15, r15
0x1800d0cde  jz      loc_1800D0EFA
0x1800d0ce4  lea     rax, [rsp+2D0h+var_2A0]
0x1800d0ce9  xor     r8d, r8d
0x1800d0cec  mov     [rsp+2D0h+var_2A8], rax
0x1800d0cf1  lea     r9, [rbp+1D0h+var_250]
0x1800d0cf5  mov     edx, r12d
0x1800d0cf8  mov     dword ptr [rsp+2D0h+var_2B0], r14d
0x1800d0cfd  mov     rcx, r15
0x1800d0d00  call    NtEnumerateKey
0x1800d0d05  mov     r14d, eax
0x1800d0d08  test    eax, eax
0x1800d0d0a  js      loc_1800D0FBE
0x1800d0d10  mov     eax, [rbp+1D0h+var_244]
0x1800d0d13  cmp     eax, 0FFFEh
0x1800d0d18  ja      loc_1800D0F03
0x1800d0d1e  mov     word ptr [rsp+2D0h+var_298], ax
0x1800d0d23  lea     r8, [rsi+18h]
0x1800d0d27  mov     word ptr [rsp+2D0h+var_298+2], ax
0x1800d0d2c  lea     rdx, [rsp+2D0h+var_298]
0x1800d0d31  lea     rax, [rbp+1D0h+var_240]
0x1800d0d35  mov     rcx, r15
0x1800d0d38  mov     qword ptr [rsp+2D0h+var_298+8], rax
0x1800d0d3d  call    RtlpGetAssemblyStorageMapRootLocation
0x1800d0d42  mov     r14d, eax
0x1800d0d45  test    eax, eax
0x1800d0d47  jns     loc_1800D0DF6
0x1800d0d4d  lea     r9, [rsp+2D0h+var_298]
0x1800d0d52  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x1800d0d56  lea     r8, aSxsAttemptToGe; "SXS: Attempt to get storage location fr"...
0x1800d0d5d  xor     edx, edx
0x1800d0d5f  lea     ecx, [rdi+33h]
0x1800d0d62  call    DbgPrintEx
0x1800d0d67  jmp     loc_1800D0FE4
0x1800d0d6c  xor     edi, edi
0x1800d0d6e  mov     [rsp+2D0h+var_288], 30h ; '0'
0x1800d0d77  xorps   xmm0, xmm0
0x1800d0d7a  mov     [rsp+2D0h+var_270], 40h ; '@'
0x1800d0d83  lea     r15, qword_180170E90
0x1800d0d8a  mov     [rsp+2D0h+var_2A0], rdi
0x1800d0d8f  lea     r8, [rsp+2D0h+var_288]
0x1800d0d94  mov     [rsp+2D0h+var_280], rdi
0x1800d0d99  lea     edx, [rdi+8]
0x1800d0d9c  mov     [rsp+2D0h+var_278], r15
0x1800d0da1  lea     rcx, [rsp+2D0h+var_2A0]
0x1800d0da6  movdqu  [rsp+2D0h+var_268], xmm0
0x1800d0dac  call    NtOpenKey
0x1800d0db1  mov     r14d, eax
0x1800d0db4  test    eax, eax
0x1800d0db6  jns     loc_1800D0EE4
0x1800d0dbc  cmp     eax, 0C0000034h
0x1800d0dc1  jz      loc_1800D0EE4
0x1800d0dc7  cmp     eax, 0C0000189h
0x1800d0dcc  jz      loc_1800D0EE4
0x1800d0dd2  mov     r9, r15
0x1800d0dd5  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x1800d0dd9  lea     r8, aSxsUnableToOpe_1; "SXS: Unable to open registry key %wZ St"...
0x1800d0de0  xor     edx, edx
0x1800d0de2  lea     ecx, [rdi+33h]
0x1800d0de5  call    DbgPrintEx
0x1800d0dea  mov     byte ptr [rsi+38h], 1
0x1800d0dee  test    rbx, rbx
0x1800d0df1  jz      short loc_1800D0DF6
0x1800d0df3  mov     [rbx], r14d
0x1800d0df6  mov     rcx, [rbp+1D0h+var_30]
0x1800d0dfd  xor     rcx, rsp; StackCookie
0x1800d0e00  call    __security_check_cookie
0x1800d0e05  lea     r11, [rsp+2D0h+var_20]
0x1800d0e0d  mov     rbx, [r11+30h]
0x1800d0e11  mov     rsi, [r11+48h]
0x1800d0e15  mov     rsp, r11
0x1800d0e18  pop     r15
0x1800d0e1a  pop     r14
0x1800d0e1c  pop     r12
0x1800d0e1e  pop     rdi
0x1800d0e1f  pop     rbp
0x1800d0e20  retn
0x1800d0e22  mov     rax, gs:60h
0x1800d0e2b  mov     rcx, [rax+20h]
0x1800d0e2f  test    dword ptr [rcx+8], 8000h
0x1800d0e36  jnz     loc_1800D0F1B
0x1800d0e3c  mov     [rdx+18h], di
0x1800d0e40  jmp     short loc_1800D0DF6
0x1800d0e42  call    RtlGetNtSystemRoot
0x1800d0e47  mov     r15, rax
0x1800d0e4a  test    rax, rax
0x1800d0e4d  jz      loc_1800D1014
0x1800d0e53  mov     rcx, rax; String
0x1800d0e56  call    wcslen
0x1800d0e5b  mov     r14, rax
0x1800d0e5e  mov     eax, 0FFFCh
0x1800d0e63  add     r14, r14
0x1800d0e66  cmp     r14, 0FFFEh
0x1800d0e6d  cmovnb  r14, rax
0x1800d0e71  movzx   ecx, word ptr [rsi+1Ah]
0x1800d0e75  mov     r12d, 10h
0x1800d0e7b  movzx   eax, r14w
0x1800d0e7f  add     eax, r12d
0x1800d0e82  mov     [rsi+18h], di
0x1800d0e86  cmp     eax, ecx
0x1800d0e88  ja      loc_1800D0FED
0x1800d0e8e  mov     rcx, [rsi+20h]; void *
0x1800d0e92  mov     rdx, r15; Src
0x1800d0e95  movzx   ebx, r14w
0x1800d0e99  mov     r8d, ebx; Size
0x1800d0e9c  call    memmove
0x1800d0ea1  movups  xmm0, xmmword ptr cs:aWinsxs; "\\WinSxS\\"
0x1800d0ea8  mov     rax, [rsi+20h]
0x1800d0eac  add     r14w, r12w
0x1800d0eb0  movdqu  xmmword ptr [rbx+rax], xmm0
0x1800d0eb5  mov     [rsi+18h], r14w
0x1800d0eba  jmp     loc_1800D0DF6
0x1800d0ebf  mov     eax, 2
0x1800d0ec4  cmp     ecx, eax
0x1800d0ec6  jnz     loc_1800D0DF6
0x1800d0ecc  xor     edi, edi
0x1800d0ece  cmp     [rdx], rdi
0x1800d0ed1  jz      loc_1800D0DF6
0x1800d0ed7  mov     rcx, [rdx]; Handle
0x1800d0eda  call    NtClose
0x1800d0edf  jmp     loc_1800D0DF6
0x1800d0ee4  mov     rax, [rsp+2D0h+var_2A0]
0x1800d0ee9  mov     [rsi+10h], rax
0x1800d0eed  mov     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x1800d0ef5  jmp     loc_1800D0DF6
0x1800d0efa  mov     byte ptr [rsi+11h], 1
0x1800d0efe  jmp     loc_1800D0DF6
0x1800d0f03  mov     byte ptr [rsi+10h], 1
0x1800d0f07  test    rbx, rbx
0x1800d0f0a  jz      loc_1800D0DF6
0x1800d0f10  mov     dword ptr [rbx], 0C0000106h
0x1800d0f16  jmp     loc_1800D0DF6
0x1800d0f1b  mov     rax, gs:60h
0x1800d0f24  mov     rcx, [rax+20h]
0x1800d0f28  movzx   r15d, word ptr [rcx+60h]
0x1800d0f2d  lea     r14, [r15+10h]
0x1800d0f31  cmp     r14, 0FFFEh
0x1800d0f38  ja      loc_1800D1005
0x1800d0f3e  movzx   eax, word ptr [rdx+1Ah]
0x1800d0f42  cmp     r14, rax
0x1800d0f45  ja      loc_1800D100E
0x1800d0f4b  mov     rax, gs:60h
0x1800d0f54  mov     rcx, [rax+20h]
0x1800d0f58  mov     rax, gs:60h
0x1800d0f61  mov     rdx, [rcx+68h]
0x1800d0f65  mov     rcx, [rax+20h]
0x1800d0f69  test    byte ptr [rcx+8], 1
0x1800d0f6d  jnz     short loc_1800D0F7C
0x1800d0f6f  mov     rax, gs:60h
0x1800d0f78  add     rdx, [rax+20h]; Src
0x1800d0f7c  mov     rbx, [rsi+20h]
0x1800d0f80  mov     r8, r15; Size
0x1800d0f83  mov     rcx, rbx; void *
0x1800d0f86  call    memmove
0x1800d0f8b  movups  xmm0, cs:xmmword_18017CAA8
0x1800d0f92  sub     r14w, 2
0x1800d0f97  mov     dl, 1
0x1800d0f99  movdqu  xmmword ptr [rbx+r15], xmm0
0x1800d0f9f  mov     rcx, [rsi+20h]
0x1800d0fa3  mov     [rsi+18h], r14w
0x1800d0fa8  call    RtlDoesFileExists_UEx
0x1800d0fad  test    al, al
0x1800d0faf  jnz     loc_1800D0DF6
0x1800d0fb5  mov     [rsi+18h], di
0x1800d0fb9  jmp     loc_1800D0DF6
0x1800d0fbe  cmp     r14d, 8000001Ah
0x1800d0fc5  jz      loc_1800D0EFA
0x1800d0fcb  xor     edx, edx
0x1800d0fcd  mov     dword ptr [rsp+2D0h+var_2B0], r14d
0x1800d0fd2  mov     r9d, r12d
0x1800d0fd5  lea     r8, aSxsUnableToEnu; "SXS: Unable to enumerate assembly stora"...
0x1800d0fdc  lea     ecx, [rdx+33h]
0x1800d0fdf  call    DbgPrintEx
0x1800d0fe4  mov     byte ptr [rsi+10h], 1
0x1800d0fe8  jmp     loc_1800D0DEE
0x1800d0fed  mov     byte ptr [rsi+10h], 1
0x1800d0ff1  test    rbx, rbx
0x1800d0ff4  jz      loc_1800D0DF6
0x1800d0ffa  mov     dword ptr [rbx], 0C0000023h
0x1800d1000  jmp     loc_1800D0DF6
0x1800d1005  mov     byte ptr [rdx+10h], 1
0x1800d1009  jmp     loc_1800D0F07
0x1800d100e  mov     byte ptr [rdx+10h], 1
0x1800d1012  jmp     short loc_1800D0FF1
0x1800d1014  movzx   r14d, di
0x1800d1018  jmp     loc_1800D0E71
```
