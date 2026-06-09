# RtlpAssemblyStorageMapResolutionDefaultCallback

- ea: `0x1800cf510`
- end: `0x1800cf8ed`
- name: `RtlpAssemblyStorageMapResolutionDefaultCallback`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800cee30`

## callees

- `0x18001a080`
- `0x18005b470`
- `0x18005c8a0`
- `0x1800cf510`
- `0x1800cff18`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e910`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## string_xrefs

- `0x1800cf6a9`: `SXS: Unable to open registry key %wZ Status = 0x%08lx\n`
- `0x1800cf626`: `SXS: Attempt to get storage location from subkey %wZ failed; Status = 0x%08lx\n`

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
    v25[2] = &qword_180170F10;
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
    LODWORD(v7) = DbgPrintEx(51, 0, "SXS: Unable to open registry key %wZ Status = 0x%08lx\n", &qword_180170F10, v11);
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
    *(_OWORD *)&v18[v16] = xmmword_18017C8C8;
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
0x1800cf510  mov     [rsp-8+arg_0], rbx
0x1800cf515  mov     [rsp-8+arg_18], rsi
0x1800cf51a  push    rbp
0x1800cf51b  push    rdi
0x1800cf51c  push    r12
0x1800cf51e  push    r14
0x1800cf520  push    r15
0x1800cf522  lea     rbp, [rsp-1B0h]
0x1800cf52a  sub     rsp, 2B0h
0x1800cf531  mov     rax, cs:__security_cookie
0x1800cf538  xor     rax, rsp
0x1800cf53b  mov     [rbp+1D0h+var_30], rax
0x1800cf542  mov     rbx, r8
0x1800cf545  mov     rsi, rdx
0x1800cf548  sub     ecx, 1
0x1800cf54b  jz      loc_1800CF63C
0x1800cf551  sub     ecx, 1
0x1800cf554  jnz     loc_1800CF78F
0x1800cf55a  xor     edi, edi
0x1800cf55c  cmp     [rdx+8], rdi
0x1800cf560  jz      loc_1800CF6F2
0x1800cf566  cmp     qword ptr [rdx+8], 1
0x1800cf56b  jz      loc_1800CF712
0x1800cf571  mov     eax, 0FFFFFFFFh
0x1800cf576  cmp     [rdx+8], rax
0x1800cf57a  ja      loc_1800CF7CA
0x1800cf580  mov     r14d, 220h
0x1800cf586  lea     rcx, [rbp+1D0h+var_250]; void *
0x1800cf58a  mov     r8d, r14d; Size
0x1800cf58d  xor     edx, edx; Val
0x1800cf58f  call    memset$thunk$772440563353939046
0x1800cf594  mov     r12d, [rsi+8]
0x1800cf598  xorps   xmm0, xmm0
0x1800cf59b  mov     r15, [rsi]
0x1800cf59e  add     r12d, 0FFFFFFFEh
0x1800cf5a2  mov     dword ptr [rsp+2D0h+var_2A0], edi
0x1800cf5a6  movups  [rsp+2D0h+var_298], xmm0
0x1800cf5ab  test    r15, r15
0x1800cf5ae  jz      loc_1800CF7CA
0x1800cf5b4  lea     rax, [rsp+2D0h+var_2A0]
0x1800cf5b9  xor     r8d, r8d
0x1800cf5bc  mov     [rsp+2D0h+var_2A8], rax
0x1800cf5c1  lea     r9, [rbp+1D0h+var_250]
0x1800cf5c5  mov     edx, r12d
0x1800cf5c8  mov     dword ptr [rsp+2D0h+var_2B0], r14d
0x1800cf5cd  mov     rcx, r15
0x1800cf5d0  call    NtEnumerateKey
0x1800cf5d5  mov     r14d, eax
0x1800cf5d8  test    eax, eax
0x1800cf5da  js      loc_1800CF88E
0x1800cf5e0  mov     eax, [rbp+1D0h+var_244]
0x1800cf5e3  cmp     eax, 0FFFEh
0x1800cf5e8  ja      loc_1800CF7D3
0x1800cf5ee  mov     word ptr [rsp+2D0h+var_298], ax
0x1800cf5f3  lea     r8, [rsi+18h]
0x1800cf5f7  mov     word ptr [rsp+2D0h+var_298+2], ax
0x1800cf5fc  lea     rdx, [rsp+2D0h+var_298]
0x1800cf601  lea     rax, [rbp+1D0h+var_240]
0x1800cf605  mov     rcx, r15
0x1800cf608  mov     qword ptr [rsp+2D0h+var_298+8], rax
0x1800cf60d  call    RtlpGetAssemblyStorageMapRootLocation
0x1800cf612  mov     r14d, eax
0x1800cf615  test    eax, eax
0x1800cf617  jns     loc_1800CF6C6
0x1800cf61d  lea     r9, [rsp+2D0h+var_298]
0x1800cf622  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x1800cf626  lea     r8, aSxsAttemptToGe; "SXS: Attempt to get storage location fr"...
0x1800cf62d  xor     edx, edx
0x1800cf62f  lea     ecx, [rdi+33h]
0x1800cf632  call    DbgPrintEx
0x1800cf637  jmp     loc_1800CF8B4
0x1800cf63c  xor     edi, edi
0x1800cf63e  mov     [rsp+2D0h+var_288], 30h ; '0'
0x1800cf647  xorps   xmm0, xmm0
0x1800cf64a  mov     [rsp+2D0h+var_270], 40h ; '@'
0x1800cf653  lea     r15, qword_180170F10
0x1800cf65a  mov     [rsp+2D0h+var_2A0], rdi
0x1800cf65f  lea     r8, [rsp+2D0h+var_288]
0x1800cf664  mov     [rsp+2D0h+var_280], rdi
0x1800cf669  lea     edx, [rdi+8]
0x1800cf66c  mov     [rsp+2D0h+var_278], r15
0x1800cf671  lea     rcx, [rsp+2D0h+var_2A0]
0x1800cf676  movdqu  [rsp+2D0h+var_268], xmm0
0x1800cf67c  call    NtOpenKey
0x1800cf681  mov     r14d, eax
0x1800cf684  test    eax, eax
0x1800cf686  jns     loc_1800CF7B4
0x1800cf68c  cmp     eax, 0C0000034h
0x1800cf691  jz      loc_1800CF7B4
0x1800cf697  cmp     eax, 0C0000189h
0x1800cf69c  jz      loc_1800CF7B4
0x1800cf6a2  mov     r9, r15
0x1800cf6a5  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x1800cf6a9  lea     r8, aSxsUnableToOpe_1; "SXS: Unable to open registry key %wZ St"...
0x1800cf6b0  xor     edx, edx
0x1800cf6b2  lea     ecx, [rdi+33h]
0x1800cf6b5  call    DbgPrintEx
0x1800cf6ba  mov     byte ptr [rsi+38h], 1
0x1800cf6be  test    rbx, rbx
0x1800cf6c1  jz      short loc_1800CF6C6
0x1800cf6c3  mov     [rbx], r14d
0x1800cf6c6  mov     rcx, [rbp+1D0h+var_30]
0x1800cf6cd  xor     rcx, rsp; StackCookie
0x1800cf6d0  call    __security_check_cookie
0x1800cf6d5  lea     r11, [rsp+2D0h+var_20]
0x1800cf6dd  mov     rbx, [r11+30h]
0x1800cf6e1  mov     rsi, [r11+48h]
0x1800cf6e5  mov     rsp, r11
0x1800cf6e8  pop     r15
0x1800cf6ea  pop     r14
0x1800cf6ec  pop     r12
0x1800cf6ee  pop     rdi
0x1800cf6ef  pop     rbp
0x1800cf6f0  retn
0x1800cf6f2  mov     rax, gs:60h
0x1800cf6fb  mov     rcx, [rax+20h]
0x1800cf6ff  test    dword ptr [rcx+8], 8000h
0x1800cf706  jnz     loc_1800CF7EB
0x1800cf70c  mov     [rdx+18h], di
0x1800cf710  jmp     short loc_1800CF6C6
0x1800cf712  call    RtlGetNtSystemRoot
0x1800cf717  mov     r15, rax
0x1800cf71a  test    rax, rax
0x1800cf71d  jz      loc_1800CF8E4
0x1800cf723  mov     rcx, rax; String
0x1800cf726  call    wcslen
0x1800cf72b  mov     r14, rax
0x1800cf72e  mov     eax, 0FFFCh
0x1800cf733  add     r14, r14
0x1800cf736  cmp     r14, 0FFFEh
0x1800cf73d  cmovnb  r14, rax
0x1800cf741  movzx   ecx, word ptr [rsi+1Ah]
0x1800cf745  mov     r12d, 10h
0x1800cf74b  movzx   eax, r14w
0x1800cf74f  add     eax, r12d
0x1800cf752  mov     [rsi+18h], di
0x1800cf756  cmp     eax, ecx
0x1800cf758  ja      loc_1800CF8BD
0x1800cf75e  mov     rcx, [rsi+20h]; void *
0x1800cf762  mov     rdx, r15; Src
0x1800cf765  movzx   ebx, r14w
0x1800cf769  mov     r8d, ebx; Size
0x1800cf76c  call    memmove
0x1800cf771  movups  xmm0, xmmword ptr cs:aWinsxs; "\\WinSxS\\"
0x1800cf778  mov     rax, [rsi+20h]
0x1800cf77c  add     r14w, r12w
0x1800cf780  movdqu  xmmword ptr [rbx+rax], xmm0
0x1800cf785  mov     [rsi+18h], r14w
0x1800cf78a  jmp     loc_1800CF6C6
0x1800cf78f  mov     eax, 2
0x1800cf794  cmp     ecx, eax
0x1800cf796  jnz     loc_1800CF6C6
0x1800cf79c  xor     edi, edi
0x1800cf79e  cmp     [rdx], rdi
0x1800cf7a1  jz      loc_1800CF6C6
0x1800cf7a7  mov     rcx, [rdx]; Handle
0x1800cf7aa  call    NtClose
0x1800cf7af  jmp     loc_1800CF6C6
0x1800cf7b4  mov     rax, [rsp+2D0h+var_2A0]
0x1800cf7b9  mov     [rsi+10h], rax
0x1800cf7bd  mov     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x1800cf7c5  jmp     loc_1800CF6C6
0x1800cf7ca  mov     byte ptr [rsi+11h], 1
0x1800cf7ce  jmp     loc_1800CF6C6
0x1800cf7d3  mov     byte ptr [rsi+10h], 1
0x1800cf7d7  test    rbx, rbx
0x1800cf7da  jz      loc_1800CF6C6
0x1800cf7e0  mov     dword ptr [rbx], 0C0000106h
0x1800cf7e6  jmp     loc_1800CF6C6
0x1800cf7eb  mov     rax, gs:60h
0x1800cf7f4  mov     rcx, [rax+20h]
0x1800cf7f8  movzx   r15d, word ptr [rcx+60h]
0x1800cf7fd  lea     r14, [r15+10h]
0x1800cf801  cmp     r14, 0FFFEh
0x1800cf808  ja      loc_1800CF8D5
0x1800cf80e  movzx   eax, word ptr [rdx+1Ah]
0x1800cf812  cmp     r14, rax
0x1800cf815  ja      loc_1800CF8DE
0x1800cf81b  mov     rax, gs:60h
0x1800cf824  mov     rcx, [rax+20h]
0x1800cf828  mov     rax, gs:60h
0x1800cf831  mov     rdx, [rcx+68h]
0x1800cf835  mov     rcx, [rax+20h]
0x1800cf839  test    byte ptr [rcx+8], 1
0x1800cf83d  jnz     short loc_1800CF84C
0x1800cf83f  mov     rax, gs:60h
0x1800cf848  add     rdx, [rax+20h]; Src
0x1800cf84c  mov     rbx, [rsi+20h]
0x1800cf850  mov     r8, r15; Size
0x1800cf853  mov     rcx, rbx; void *
0x1800cf856  call    memmove
0x1800cf85b  movups  xmm0, cs:xmmword_18017C8C8
0x1800cf862  sub     r14w, 2
0x1800cf867  mov     dl, 1
0x1800cf869  movdqu  xmmword ptr [rbx+r15], xmm0
0x1800cf86f  mov     rcx, [rsi+20h]
0x1800cf873  mov     [rsi+18h], r14w
0x1800cf878  call    RtlDoesFileExists_UEx
0x1800cf87d  test    al, al
0x1800cf87f  jnz     loc_1800CF6C6
0x1800cf885  mov     [rsi+18h], di
0x1800cf889  jmp     loc_1800CF6C6
0x1800cf88e  cmp     r14d, 8000001Ah
0x1800cf895  jz      loc_1800CF7CA
0x1800cf89b  xor     edx, edx
0x1800cf89d  mov     dword ptr [rsp+2D0h+var_2B0], r14d
0x1800cf8a2  mov     r9d, r12d
0x1800cf8a5  lea     r8, aSxsUnableToEnu; "SXS: Unable to enumerate assembly stora"...
0x1800cf8ac  lea     ecx, [rdx+33h]
0x1800cf8af  call    DbgPrintEx
0x1800cf8b4  mov     byte ptr [rsi+10h], 1
0x1800cf8b8  jmp     loc_1800CF6BE
0x1800cf8bd  mov     byte ptr [rsi+10h], 1
0x1800cf8c1  test    rbx, rbx
0x1800cf8c4  jz      loc_1800CF6C6
0x1800cf8ca  mov     dword ptr [rbx], 0C0000023h
0x1800cf8d0  jmp     loc_1800CF6C6
0x1800cf8d5  mov     byte ptr [rdx+10h], 1
0x1800cf8d9  jmp     loc_1800CF7D7
0x1800cf8de  mov     byte ptr [rdx+10h], 1
0x1800cf8e2  jmp     short loc_1800CF8C1
0x1800cf8e4  movzx   r14d, di
0x1800cf8e8  jmp     loc_1800CF741
```
