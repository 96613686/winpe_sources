# EnumerateRasEntries(_RAS_CONNECTION_INFO * *,ulong *)

- ea: `0x180001a80`
- end: `0x180001e3f`
- name: `?EnumerateRasEntries@@YAKPEAPEAU_RAS_CONNECTION_INFO@@PEAK@Z`
- size: `959`
- prototype: `unsigned int __fastcall(struct _RAS_CONNECTION_INFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800019a0`

## callees

- `0x180001a80`
- `0x1800056d4`
- `0x180007288`
- `0x18000b100`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180001bbb`
- `KERNEL32!LocalAlloc` at `0x180001bbb`
- `KERNEL32!GetLastError` at `0x180001bc9`
- `KERNEL32!GetLastError` at `0x180001bc9`
- `KERNEL32!LocalFree` at `0x180001dff`
- `KERNEL32!LocalFree` at `0x180001dff`
- `RASAPI32!ReadPhonebookFile` at `0x180001b5b`
- `RASAPI32!ReadPhonebookFile` at `0x180001b5b`
- `RASAPI32!ClosePhonebookFile` at `0x180001ded`
- `RASAPI32!ClosePhonebookFile` at `0x180001ded`
- `RASAPI32!DwGetCustomAuthData` at `0x180001c63`
- `RASAPI32!DwGetCustomAuthData` at `0x180001c63`
- `RASAPI32!GetPublicPhonebookPath` at `0x180001b0d`
- `RASAPI32!GetPublicPhonebookPath` at `0x180001b0d`
- `rtutils!TracePrintfExA` at `0x180001af5`
- `rtutils!TracePrintfExA` at `0x180001b3c`
- `rtutils!TracePrintfExA` at `0x180001ba1`
- `rtutils!TracePrintfExA` at `0x180001cc6`
- `rtutils!TracePrintfExA` at `0x180001cf3`
- `rtutils!TracePrintfExA` at `0x180001d34`
- `rtutils!TracePrintfExA` at `0x180001de2`
- `rtutils!TracePrintfExA` at `0x180001af5`
- `rtutils!TracePrintfExA` at `0x180001b3c`
- `rtutils!TracePrintfExA` at `0x180001ba1`
- `rtutils!TracePrintfExA` at `0x180001cc6`
- `rtutils!TracePrintfExA` at `0x180001cf3`
- `rtutils!TracePrintfExA` at `0x180001d34`
- `rtutils!TracePrintfExA` at `0x180001de2`

## string_xrefs

- `0x180001b35`: `EnumerateRasEntries: Pbk path: %S`
- `0x180001b95`: `EnumerateRasEntries: ReadPhonebookFile returned %d entries`
- `0x180001ce7`: `EnumerateRasEntries: Excluding entry [%S] as it is configured to use machine certs.`

## pseudocode

```c
__int64 __fastcall EnumerateRasEntries(HLOCAL *a1, unsigned int *a2)
{
  DWORD LastError; // ebx
  __int64 v5; // rax
  int v6; // r9d
  struct _RAS_CONNECTION_INFO *v7; // rax
  __int64 v8; // r13
  __int64 v9; // r15
  char v10; // di
  int v11; // eax
  const char *v12; // rax
  __int64 v13; // rcx
  wchar_t *v14; // rdi
  int v16; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h]
  __int64 v19; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v20[7]; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t v21[264]; // [rsp+98h] [rbp-70h] BYREF

  memset(v20, 0, sizeof(v20));
  if ( !a1 || !a2 )
    return 87;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasEntries");
  *a2 = 0;
  *a1 = 0;
  if ( !(unsigned int)GetPublicPhonebookPath(v21, 261) )
  {
    LastError = 621;
    goto LABEL_42;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasEntries: Pbk path: %S", v21);
  LODWORD(v18) = ReadPhonebookFile(v21, 0, 0, 1024, v20);
  LastError = v18;
  if ( !(_DWORD)v18 )
  {
    v5 = v20[2];
    if ( v20[2] )
    {
      v6 = *(_DWORD *)(v20[2] + 16LL);
      if ( v6 )
      {
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasEntries: ReadPhonebookFile returned %d entries", v6);
          v5 = v20[2];
        }
        v7 = (struct _RAS_CONNECTION_INFO *)LocalAlloc(0x40u, 536LL * *(unsigned int *)(v5 + 16));
        *a1 = v7;
        if ( !v7 )
        {
          LastError = GetLastError();
          goto LABEL_42;
        }
        v8 = *(_QWORD *)v20[2];
        if ( *a2 < *(_DWORD *)(v20[2] + 16LL) )
        {
          while ( 1 )
          {
            if ( !v8 )
            {
LABEL_41:
              LastError = v18;
              break;
            }
            v9 = *(_QWORD *)(v8 + 16);
            v16 = 0;
            if ( v9 && *(_QWORD *)(v9 + 8) )
            {
              v10 = 0;
              if ( *(_DWORD *)(v9 + 752) )
                goto LABEL_31;
              v11 = *(_DWORD *)(v9 + 164);
              if ( (v11 & 0x80u) == 0 )
              {
                if ( (v11 & 0x800) == 0 )
                {
                  v16 = 2;
LABEL_30:
                  v10 = 1;
LABEL_31:
                  if ( g_dwTraceId != -1 )
                  {
                    v12 = "Add";
                    if ( !v10 )
                      v12 = "Ignore";
                    TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasEntries: Entry [%S]: %s", *(_QWORD *)(v9 + 8), v12);
                  }
                  if ( v10 )
                  {
                    v13 = **(_QWORD **)(v9 + 32);
                    if ( v13 )
                    {
                      if ( *(_QWORD *)(v13 + 16) )
                      {
                        v14 = (wchar_t *)((char *)*a1 + 536 * *a2);
                        StringCchCopyW(v14, 0x101u, *(STRSAFE_LPCWSTR *)(v9 + 8));
                        *((_DWORD *)v14 + 129) = *(_DWORD *)(v9 + 24);
                        *((_DWORD *)v14 + 133) = v16;
                        *((_DWORD *)v14 + 132) = *(_DWORD *)(v9 + 192);
                        if ( !*(_DWORD *)(v9 + 548) )
                          ++*a2;
                      }
                    }
                  }
                  goto LABEL_40;
                }
                if ( g_dwTraceId != -1 )
                {
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "EnumerateRasEntries: Excluding entry [%S] as it is configured to use machine certs.",
                    *(const wchar_t **)(v9 + 8));
                  goto LABEL_31;
                }
              }
              else
              {
                v19 = 0;
                v17 = 0;
                if ( (unsigned int)DwGetCustomAuthData(v9, &v17, &v19) )
                  goto LABEL_31;
                GetEapCredentialsInputType(*(unsigned int *)(v9 + 192), v19, v17, &v16, 0, 0, 0);
                if ( v16 )
                  goto LABEL_30;
                if ( g_dwTraceId != -1 )
                {
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "EnumerateRasEntries: Excluding entry [%S] as it is not of supported authentication type[%d].",
                    *(const wchar_t **)(v9 + 8),
                    0);
                  goto LABEL_31;
                }
              }
            }
LABEL_40:
            v8 = *(_QWORD *)(v8 + 8);
            if ( *a2 >= *(_DWORD *)(v20[2] + 16LL) )
              goto LABEL_41;
          }
        }
      }
    }
  }
LABEL_42:
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasEntries: Done");
  ClosePhonebookFile(v20);
  if ( LastError )
  {
    if ( *a1 )
    {
      LocalFree(*a1);
      *a1 = 0;
    }
    *a2 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180001a80  mov     r11, rsp
0x180001a83  push    rbp
0x180001a84  push    rsi
0x180001a85  push    r14
0x180001a87  lea     rbp, [r11-1E8h]
0x180001a8e  sub     rsp, 2D0h
0x180001a95  mov     rax, cs:__security_cookie
0x180001a9c  xor     rax, rsp
0x180001a9f  mov     [rbp+1E0h+var_40], rax
0x180001aa6  xorps   xmm0, xmm0
0x180001aa9  xor     eax, eax
0x180001aab  mov     [rbp+1E0h+var_258], rax
0x180001aaf  mov     rsi, rdx
0x180001ab2  mov     r14, rcx
0x180001ab5  movups  [rsp+2E0h+var_290+8], xmm0
0x180001aba  movups  [rsp+2E0h+var_280+8], xmm0
0x180001abf  movups  xmmword ptr [rsp+2E0h+var_270+8], xmm0
0x180001ac4  test    rcx, rcx
0x180001ac7  jz      loc_180001E1F
0x180001acd  test    rdx, rdx
0x180001ad0  jz      loc_180001E1F
0x180001ad6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001adc  mov     [r11+18h], rbx
0x180001ae0  mov     [r11-28h], r12
0x180001ae4  cmp     ecx, 0FFFFFFFFh
0x180001ae7  jz      short loc_180001AFB
0x180001ae9  lea     r8, aEnumeraterasen_1; "EnumerateRasEntries"
0x180001af0  mov     edx, 0Ch; dwFlags
0x180001af5  call    cs:__imp_TracePrintfExA
0x180001afb  xor     r12d, r12d
0x180001afe  lea     rcx, [rbp+1E0h+var_250]
0x180001b02  mov     [rsi], r12d
0x180001b05  mov     edx, 105h
0x180001b0a  mov     [r14], r12
0x180001b0d  call    cs:__imp_GetPublicPhonebookPath
0x180001b13  test    eax, eax
0x180001b15  jnz     short loc_180001B21
0x180001b17  mov     ebx, 26Dh
0x180001b1c  jmp     loc_180001DCB
0x180001b21  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001b27  cmp     ecx, 0FFFFFFFFh
0x180001b2a  jz      short loc_180001B42
0x180001b2c  lea     r9, [rbp+1E0h+var_250]
0x180001b30  mov     edx, 0Ch; dwFlags
0x180001b35  lea     r8, aEnumeraterasen_3; "EnumerateRasEntries: Pbk path: %S"
0x180001b3c  call    cs:__imp_TracePrintfExA
0x180001b42  lea     rax, [rsp+2E0h+var_290+8]
0x180001b47  mov     r9d, 400h
0x180001b4d  xor     r8d, r8d
0x180001b50  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180001b55  xor     edx, edx
0x180001b57  lea     rcx, [rbp+1E0h+var_250]
0x180001b5b  call    cs:__imp_ReadPhonebookFile
0x180001b61  mov     dword ptr [rsp+2E0h+var_298], eax
0x180001b65  mov     ebx, eax
0x180001b67  test    eax, eax
0x180001b69  jnz     loc_180001DCB
0x180001b6f  mov     rax, qword ptr [rsp+2E0h+var_280+8]
0x180001b74  test    rax, rax
0x180001b77  jz      loc_180001DCB
0x180001b7d  mov     r9d, [rax+10h]
0x180001b81  test    r9d, r9d
0x180001b84  jz      loc_180001DCB
0x180001b8a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001b90  cmp     ecx, 0FFFFFFFFh
0x180001b93  jz      short loc_180001BAC
0x180001b95  lea     r8, aEnumeraterasen_5; "EnumerateRasEntries: ReadPhonebookFile "...
0x180001b9c  mov     edx, 0Ch; dwFlags
0x180001ba1  call    cs:__imp_TracePrintfExA
0x180001ba7  mov     rax, qword ptr [rsp+2E0h+var_280+8]
0x180001bac  mov     eax, [rax+10h]
0x180001baf  mov     ecx, 40h ; '@'; uFlags
0x180001bb4  imul    rdx, rax, 218h; uBytes
0x180001bbb  call    cs:__imp_LocalAlloc
0x180001bc1  mov     [r14], rax
0x180001bc4  test    rax, rax
0x180001bc7  jnz     short loc_180001BD6
0x180001bc9  call    cs:__imp_GetLastError
0x180001bcf  mov     ebx, eax
0x180001bd1  jmp     loc_180001DCB
0x180001bd6  mov     rax, qword ptr [rsp+2E0h+var_280+8]
0x180001bdb  mov     [rsp+2E0h+var_28], r13
0x180001be3  mov     r13, [rax]
0x180001be6  mov     eax, [rax+10h]
0x180001be9  cmp     [rsi], eax
0x180001beb  jnb     loc_180001DC3
0x180001bf1  mov     [rsp+2C8h], rdi
0x180001bf9  lea     rbx, aIgnore; "Ignore"
0x180001c00  mov     [rsp+2E0h+var_30], r15
0x180001c08  test    r13, r13
0x180001c0b  jz      loc_180001DAF
0x180001c11  mov     r15, [r13+10h]
0x180001c15  mov     [rsp+2E0h+var_2A0], r12d
0x180001c1a  test    r15, r15
0x180001c1d  jz      loc_180001D9B
0x180001c23  cmp     [r15+8], r12
0x180001c27  jz      loc_180001D9B
0x180001c2d  xor     dil, dil
0x180001c30  cmp     [r15+2F0h], r12d
0x180001c37  jnz     loc_180001D06
0x180001c3d  mov     eax, [r15+0A4h]
0x180001c44  test    al, al
0x180001c46  jns     loc_180001CCE
0x180001c4c  lea     r8, [rsp+2E0h+var_290]
0x180001c51  mov     qword ptr [rsp+2E0h+var_290], r12
0x180001c56  lea     rdx, [rsp+2E0h+var_29C]
0x180001c5b  mov     [rsp+2E0h+var_29C], r12d
0x180001c60  mov     rcx, r15
0x180001c63  call    cs:__imp_DwGetCustomAuthData
0x180001c69  test    eax, eax
0x180001c6b  jnz     loc_180001D06
0x180001c71  mov     r8d, [rsp+2E0h+var_29C]
0x180001c76  lea     r9, [rsp+2E0h+var_2A0]
0x180001c7b  mov     rdx, qword ptr [rsp+2E0h+var_290]
0x180001c80  mov     ecx, [r15+0C0h]
0x180001c87  mov     [rsp+30h], r12
0x180001c8c  mov     dword ptr [rsp+2E0h+var_2B8], r12d
0x180001c91  mov     qword ptr [rsp+2E0h+var_2C0], r12
0x180001c96  call    GetEapCredentialsInputType
0x180001c9b  cmp     [rsp+2E0h+var_2A0], r12d
0x180001ca0  jnz     short loc_180001D03
0x180001ca2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001ca8  cmp     ecx, 0FFFFFFFFh
0x180001cab  jz      loc_180001D9B
0x180001cb1  mov     r9, [r15+8]
0x180001cb5  lea     r8, aEnumeraterasen_0; "EnumerateRasEntries: Excluding entry [%"...
0x180001cbc  mov     edx, 0Ch; dwFlags
0x180001cc1  mov     [rsp+2E0h+var_2C0], r12d
0x180001cc6  call    cs:__imp_TracePrintfExA
0x180001ccc  jmp     short loc_180001D06
0x180001cce  bt      eax, 0Bh
0x180001cd2  jnb     short loc_180001CFB
0x180001cd4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001cda  cmp     ecx, 0FFFFFFFFh
0x180001cdd  jz      loc_180001D9B
0x180001ce3  mov     r9, [r15+8]
0x180001ce7  lea     r8, aEnumeraterasen; "EnumerateRasEntries: Excluding entry [%"...
0x180001cee  mov     edx, 0Ch; dwFlags
0x180001cf3  call    cs:__imp_TracePrintfExA
0x180001cf9  jmp     short loc_180001D06
0x180001cfb  mov     [rsp+2E0h+var_2A0], 2
0x180001d03  mov     dil, 1
0x180001d06  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001d0c  cmp     ecx, 0FFFFFFFFh
0x180001d0f  jz      short loc_180001D3A
0x180001d11  mov     r9, [r15+8]
0x180001d15  lea     rax, aAdd; "Add"
0x180001d1c  test    dil, dil
0x180001d1f  lea     r8, aEnumeraterasen_2; "EnumerateRasEntries: Entry [%S]: %s"
0x180001d26  mov     edx, 0Ch; dwFlags
0x180001d2b  cmovz   rax, rbx
0x180001d2f  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180001d34  call    cs:__imp_TracePrintfExA
0x180001d3a  test    dil, dil
0x180001d3d  jz      short loc_180001D9B
0x180001d3f  mov     rax, [r15+20h]
0x180001d43  mov     rcx, [rax]
0x180001d46  test    rcx, rcx
0x180001d49  jz      short loc_180001D9B
0x180001d4b  cmp     [rcx+10h], r12
0x180001d4f  jz      short loc_180001D9B
0x180001d51  mov     eax, [rsi]
0x180001d53  mov     edx, 101h; cchDest
0x180001d58  mov     r8, [r15+8]; pszSrc
0x180001d5c  imul    rdi, rax, 218h
0x180001d63  add     rdi, [r14]
0x180001d66  mov     rcx, rdi; pszDest
0x180001d69  call    StringCchCopyW
0x180001d6e  mov     r11d, [r15+18h]
0x180001d72  mov     [rdi+204h], r11d
0x180001d79  mov     eax, [rsp+2E0h+var_2A0]
0x180001d7d  mov     [rdi+214h], eax
0x180001d83  mov     eax, [r15+0C0h]
0x180001d8a  mov     [rdi+210h], eax
0x180001d90  cmp     [r15+224h], r12d
0x180001d97  jnz     short loc_180001D9B
0x180001d99  inc     dword ptr [rsi]
0x180001d9b  mov     rax, qword ptr [rsp+2E0h+var_280+8]
0x180001da0  mov     r13, [r13+8]
0x180001da4  mov     ecx, [rax+10h]
0x180001da7  cmp     [rsi], ecx
0x180001da9  jb      loc_180001C08
0x180001daf  mov     ebx, dword ptr [rsp+2E0h+var_298]
0x180001db3  mov     r15, [rsp+2E0h+var_30]
0x180001dbb  mov     rdi, [rsp+2C8h]
0x180001dc3  mov     r13, [rsp+2E0h+var_28]
0x180001dcb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001dd1  cmp     ecx, 0FFFFFFFFh
0x180001dd4  jz      short loc_180001DE8
0x180001dd6  lea     r8, aEnumeraterasen_4; "EnumerateRasEntries: Done"
0x180001ddd  mov     edx, 0Ch; dwFlags
0x180001de2  call    cs:__imp_TracePrintfExA
0x180001de8  lea     rcx, [rsp+2E0h+var_290+8]
0x180001ded  call    cs:__imp_ClosePhonebookFile
0x180001df3  test    ebx, ebx
0x180001df5  jz      short loc_180001E0B
0x180001df7  mov     rcx, [r14]; hMem
0x180001dfa  test    rcx, rcx
0x180001dfd  jz      short loc_180001E08
0x180001dff  call    cs:__imp_LocalFree
0x180001e05  mov     [r14], r12
0x180001e08  mov     [rsi], r12d
0x180001e0b  mov     r12, [rsp+2E0h+var_20]
0x180001e13  mov     eax, ebx
0x180001e15  mov     rbx, [rsp+2E0h+arg_10]
0x180001e1d  jmp     short loc_180001E24
0x180001e1f  mov     eax, 57h ; 'W'
0x180001e24  mov     rcx, [rbp+1E0h+var_40]
0x180001e2b  xor     rcx, rsp; StackCookie
0x180001e2e  call    __security_check_cookie
0x180001e33  add     rsp, 2D0h
0x180001e3a  pop     r14
0x180001e3c  pop     rsi
0x180001e3d  pop     rbp
0x180001e3e  retn
```
