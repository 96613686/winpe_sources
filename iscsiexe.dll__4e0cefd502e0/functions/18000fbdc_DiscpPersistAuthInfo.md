# DiscpPersistAuthInfo

- ea: `0x18000fbdc`
- end: `0x18000fe67`
- name: `DiscpPersistAuthInfo`
- size: `651`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001048c`

## callees

- `0x180001cfe`
- `0x18000ec10`
- `0x18000f1c4`
- `0x18000fbdc`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpGetRegistryValue` at `0x18000fc76`
- `ISCSIUM!DiscpGetRegistryValue` at `0x18000fc76`
- `ISCSIUM!DiscpAllocMemory` at `0x18000fd14`
- `ISCSIUM!DiscpAllocMemory` at `0x18000fd7a`
- `ISCSIUM!DiscpAllocMemory` at `0x18000fd14`
- `ISCSIUM!DiscpAllocMemory` at `0x18000fd7a`
- `ISCSIUM!DiscpSetRegistryValue` at `0x18000fe21`
- `ISCSIUM!DiscpSetRegistryValue` at `0x18000fe21`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000fc3e`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000fc3e`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fcbd`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fe2c`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fe3b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fe4e`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fcbd`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fe2c`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fe3b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fe4e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fca4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe45`

## string_xrefs

- `0x18000fc33`: `Software\Microsoft\Windows NT\CurrentVersion\iSCSI\Discovery\Authentication Cache`

## pseudocode

```c
__int64 __fastcall DiscpPersistAuthInfo(__int64 a1, int a2, __int64 a3)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  unsigned int v6; // eax
  const WCHAR *v7; // r13
  unsigned int v8; // ebx
  int StaticAuthInfo; // eax
  int v10; // ecx
  unsigned int v11; // r14d
  unsigned int v12; // esi
  const WCHAR *v13; // rbx
  unsigned int v14; // esi
  void *v15; // rax
  __int64 v16; // r15
  unsigned int v17; // ebx
  __int64 v18; // rbx
  unsigned int v19; // edx
  int v21; // [rsp+30h] [rbp-38h]
  unsigned int v22; // [rsp+40h] [rbp-28h] BYREF
  void *Src; // [rsp+48h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-10h] BYREF
  size_t Size; // [rsp+C8h] [rbp+60h] BYREF

  Src = 0;
  v4 = 0;
  LODWORD(Size) = 0;
  v22 = 0;
  hKey = 0;
  lpValueName = 0;
  v5 = DiscpBuildCacheName(a1, a2, 0, (wchar_t **)&lpValueName);
  if ( !v5 )
  {
    v6 = DiscpOpenRegistryKey(
           &hKey,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Authentication Cache",
           983103);
    v7 = lpValueName;
    v5 = v6;
    if ( v6 )
    {
LABEL_31:
      DiscpFreeMemory(v7);
      return v5;
    }
    if ( !(unsigned int)DiscpGetRegistryValue(hKey, 0, lpValueName, 3, 1, &Src, &Size) )
    {
      v8 = Size;
      StaticAuthInfo = DiscpFindStaticAuthInfo(a3, Src, (unsigned int)Size, &v22);
      if ( StaticAuthInfo != -268500938 )
      {
        if ( StaticAuthInfo != -268500981 )
          v4 = v22;
LABEL_7:
        v10 = *(_DWORD *)(a3 + 32);
        if ( v10 )
          v11 = (v10 + *(_DWORD *)(a3 + 20) + 47) & 0xFFFFFFF8;
        else
          v11 = 0;
        if ( v4 )
        {
          v12 = v11 + v8;
          if ( v11 + v8 >= v8 )
          {
            v13 = (const WCHAR *)((char *)Src + v4);
            lpValueName = v13;
            if ( v12 >= *(_DWORD *)v13 )
            {
              v14 = v12 - *(_DWORD *)v13;
              v15 = (void *)DiscpAllocMemory(v14);
              v16 = (__int64)v15;
              if ( v15 )
              {
                v17 = *(_DWORD *)v13;
                memcpy_0(v15, Src, v4);
                memcpy_0((void *)(v16 + v4), (char *)lpValueName + v17, (_DWORD)Size - v17 - v4);
                if ( v14 < v11 )
                {
                  v5 = 87;
LABEL_27:
                  DiscpFreeMemory(v16);
                  goto LABEL_28;
                }
                v4 = v14 - v11;
LABEL_24:
                if ( *(_DWORD *)(a3 + 32) )
                {
                  v18 = v16 + v4;
                  *(_DWORD *)v18 = v11;
                  *(_DWORD *)(v18 + 4) = *(_DWORD *)a3;
                  *(_QWORD *)(v18 + 8) = *(_QWORD *)(a3 + 8);
                  *(_BYTE *)(v18 + 16) = *(_BYTE *)(a3 + 16);
                  *(_DWORD *)(v18 + 20) = *(_DWORD *)(a3 + 20);
                  *(_DWORD *)(v18 + 24) = 40;
                  memcpy_0((void *)(v18 + 40), *(const void **)(a3 + 24), *(unsigned int *)(a3 + 20));
                  v19 = *(_DWORD *)(v18 + 20) + *(_DWORD *)(v18 + 24);
                  *(_DWORD *)(v18 + 28) = *(_DWORD *)(a3 + 32);
                  *(_DWORD *)(v18 + 32) = v19;
                  memcpy_0((void *)(v18 + v19), *(const void **)(a3 + 40), *(unsigned int *)(a3 + 32));
                }
                LOBYTE(v21) = 1;
                v5 = DiscpSetRegistryValue(hKey, 0, v7, 3, v16, v14, v21);
                goto LABEL_27;
              }
LABEL_22:
              v5 = 8;
              goto LABEL_28;
            }
          }
          v5 = 534;
        }
        else
        {
          v5 = 0;
          if ( v10 )
          {
            v16 = DiscpAllocMemory(v11);
            if ( v16 )
            {
              v14 = v11;
              goto LABEL_24;
            }
            goto LABEL_22;
          }
        }
LABEL_28:
        if ( Src )
          DiscpFreeMemory(Src);
        RegCloseKey(hKey);
        goto LABEL_31;
      }
      RegDeleteValueW(hKey, v7);
      memset_0(Src, 0, (unsigned int)Size);
      DiscpFreeMemory(Src);
    }
    v8 = 0;
    Src = 0;
    LODWORD(Size) = 0;
    goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x18000fbdc  push    rbp
0x18000fbde  push    rbx
0x18000fbdf  push    rsi
0x18000fbe0  push    rdi
0x18000fbe1  push    r12
0x18000fbe3  push    r13
0x18000fbe5  push    r14
0x18000fbe7  push    r15
0x18000fbe9  mov     rbp, rsp
0x18000fbec  sub     rsp, 68h
0x18000fbf0  mov     r12, r8
0x18000fbf3  mov     [rbp+Src], 0
0x18000fbfb  xor     edi, edi
0x18000fbfd  mov     dword ptr [rbp+Size], 0
0x18000fc04  xor     r8d, r8d
0x18000fc07  mov     [rbp+var_28], edi
0x18000fc0a  lea     r9, [rbp+lpValueName]
0x18000fc0e  mov     [rbp+hKey], 0
0x18000fc16  mov     [rbp+lpValueName], 0
0x18000fc1e  call    DiscpBuildCacheName
0x18000fc23  mov     ebx, eax
0x18000fc25  test    eax, eax
0x18000fc27  jnz     loc_18000FE54
0x18000fc2d  mov     r8d, 0F003Fh
0x18000fc33  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000fc3a  lea     rcx, [rbp+hKey]
0x18000fc3e  call    cs:__imp_DiscpOpenRegistryKey
0x18000fc44  mov     r13, [rbp+lpValueName]
0x18000fc48  mov     ebx, eax
0x18000fc4a  test    eax, eax
0x18000fc4c  jnz     loc_18000FE4B
0x18000fc52  mov     rcx, [rbp+hKey]
0x18000fc56  lea     rax, [rbp+Size]
0x18000fc5a  mov     qword ptr [rsp+68h+var_38], rax
0x18000fc5f  lea     r9d, [rdi+3]
0x18000fc63  lea     rax, [rbp+Src]
0x18000fc67  mov     r8, r13
0x18000fc6a  mov     [rsp+68h+var_40], rax
0x18000fc6f  xor     edx, edx
0x18000fc71  mov     byte ptr [rsp+68h+var_48], 1
0x18000fc76  call    cs:__imp_DiscpGetRegistryValue
0x18000fc7c  test    eax, eax
0x18000fc7e  jnz     short loc_18000FCC3
0x18000fc80  mov     ebx, dword ptr [rbp+Size]
0x18000fc83  lea     r9, [rbp+var_28]
0x18000fc87  mov     rdx, [rbp+Src]
0x18000fc8b  mov     r8d, ebx
0x18000fc8e  mov     rcx, r12
0x18000fc91  call    DiscpFindStaticAuthInfo
0x18000fc96  cmp     eax, 0EFFF0036h
0x18000fc9b  jnz     short loc_18000FCE7
0x18000fc9d  mov     rcx, [rbp+hKey]; hKey
0x18000fca1  mov     rdx, r13; lpValueName
0x18000fca4  call    cs:__imp_RegDeleteValueW
0x18000fcaa  mov     r8d, dword ptr [rbp+Size]; Size
0x18000fcae  xor     edx, edx; Val
0x18000fcb0  mov     rcx, [rbp+Src]; void *
0x18000fcb4  call    memset_0
0x18000fcb9  mov     rcx, [rbp+Src]
0x18000fcbd  call    cs:__imp_DiscpFreeMemory
0x18000fcc3  xor     ebx, ebx
0x18000fcc5  mov     [rbp+Src], rbx
0x18000fcc9  mov     dword ptr [rbp+Size], ebx
0x18000fccc  mov     ecx, [r12+20h]
0x18000fcd1  test    ecx, ecx
0x18000fcd3  jz      short loc_18000FCF3
0x18000fcd5  mov     r14d, [r12+14h]
0x18000fcda  add     r14d, 2Fh ; '/'
0x18000fcde  add     r14d, ecx
0x18000fce1  and     r14d, 0FFFFFFF8h
0x18000fce5  jmp     short loc_18000FCF6
0x18000fce7  cmp     eax, 0EFFF000Bh
0x18000fcec  jz      short loc_18000FCCC
0x18000fcee  mov     edi, [rbp+var_28]
0x18000fcf1  jmp     short loc_18000FCCC
0x18000fcf3  xor     r14d, r14d
0x18000fcf6  test    edi, edi
0x18000fcf8  jz      short loc_18000FD6D
0x18000fcfa  lea     esi, [r14+rbx]
0x18000fcfe  cmp     esi, ebx
0x18000fd00  jb      short loc_18000FD63
0x18000fd02  mov     ebx, edi
0x18000fd04  add     rbx, [rbp+Src]
0x18000fd08  mov     [rbp+lpValueName], rbx
0x18000fd0c  cmp     esi, [rbx]
0x18000fd0e  jb      short loc_18000FD63
0x18000fd10  sub     esi, [rbx]
0x18000fd12  mov     ecx, esi
0x18000fd14  call    cs:__imp_DiscpAllocMemory
0x18000fd1a  mov     r15, rax
0x18000fd1d  test    rax, rax
0x18000fd20  jz      short loc_18000FD88
0x18000fd22  mov     rdx, [rbp+Src]; Src
0x18000fd26  mov     rcx, rax; void *
0x18000fd29  mov     ebx, [rbx]
0x18000fd2b  mov     r8d, edi; Size
0x18000fd2e  call    memcpy_0
0x18000fd33  mov     r8d, dword ptr [rbp+Size]
0x18000fd37  mov     edx, ebx
0x18000fd39  add     rdx, [rbp+lpValueName]; Src
0x18000fd3d  sub     r8d, ebx
0x18000fd40  mov     ecx, edi
0x18000fd42  sub     r8d, edi; Size
0x18000fd45  add     rcx, r15; void *
0x18000fd48  call    memcpy_0
0x18000fd4d  cmp     esi, r14d
0x18000fd50  jb      short loc_18000FD59
0x18000fd52  mov     edi, esi
0x18000fd54  sub     edi, r14d
0x18000fd57  jmp     short loc_18000FD95
0x18000fd59  mov     ebx, 57h ; 'W'
0x18000fd5e  jmp     loc_18000FE29
0x18000fd63  mov     ebx, 216h
0x18000fd68  jmp     loc_18000FE32
0x18000fd6d  xor     ebx, ebx
0x18000fd6f  test    ecx, ecx
0x18000fd71  jz      loc_18000FE32
0x18000fd77  mov     ecx, r14d
0x18000fd7a  call    cs:__imp_DiscpAllocMemory
0x18000fd80  mov     r15, rax
0x18000fd83  test    rax, rax
0x18000fd86  jnz     short loc_18000FD92
0x18000fd88  mov     ebx, 8
0x18000fd8d  jmp     loc_18000FE32
0x18000fd92  mov     esi, r14d
0x18000fd95  cmp     dword ptr [r12+20h], 0
0x18000fd9b  jz      short loc_18000FE04
0x18000fd9d  mov     ebx, edi
0x18000fd9f  add     rbx, r15
0x18000fda2  mov     [rbx], r14d
0x18000fda5  lea     rcx, [rbx+28h]; void *
0x18000fda9  mov     eax, [r12]
0x18000fdad  mov     [rbx+4], eax
0x18000fdb0  mov     rax, [r12+8]
0x18000fdb5  mov     [rbx+8], rax
0x18000fdb9  mov     al, [r12+10h]
0x18000fdbe  mov     [rbx+10h], al
0x18000fdc1  mov     eax, [r12+14h]
0x18000fdc6  mov     [rbx+14h], eax
0x18000fdc9  mov     dword ptr [rbx+18h], 28h ; '('
0x18000fdd0  mov     r8d, [r12+14h]; Size
0x18000fdd5  mov     rdx, [r12+18h]; Src
0x18000fdda  call    memcpy_0
0x18000fddf  mov     edx, [rbx+18h]
0x18000fde2  add     edx, [rbx+14h]
0x18000fde5  mov     eax, [r12+20h]
0x18000fdea  mov     ecx, edx
0x18000fdec  mov     [rbx+1Ch], eax
0x18000fdef  add     rcx, rbx; void *
0x18000fdf2  mov     [rbx+20h], edx
0x18000fdf5  mov     r8d, [r12+20h]; Size
0x18000fdfa  mov     rdx, [r12+28h]; Src
0x18000fdff  call    memcpy_0
0x18000fe04  mov     rcx, [rbp+hKey]
0x18000fe08  mov     r9d, 3
0x18000fe0e  mov     byte ptr [rsp+68h+var_38], 1
0x18000fe13  mov     r8, r13
0x18000fe16  mov     dword ptr [rsp+68h+var_40], esi
0x18000fe1a  xor     edx, edx
0x18000fe1c  mov     [rsp+68h+var_48], r15
0x18000fe21  call    cs:__imp_DiscpSetRegistryValue
0x18000fe27  mov     ebx, eax
0x18000fe29  mov     rcx, r15
0x18000fe2c  call    cs:__imp_DiscpFreeMemory
0x18000fe32  mov     rcx, [rbp+Src]
0x18000fe36  test    rcx, rcx
0x18000fe39  jz      short loc_18000FE41
0x18000fe3b  call    cs:__imp_DiscpFreeMemory
0x18000fe41  mov     rcx, [rbp+hKey]; hKey
0x18000fe45  call    cs:__imp_RegCloseKey
0x18000fe4b  mov     rcx, r13
0x18000fe4e  call    cs:__imp_DiscpFreeMemory
0x18000fe54  mov     eax, ebx
0x18000fe56  add     rsp, 68h
0x18000fe5a  pop     r15
0x18000fe5c  pop     r14
0x18000fe5e  pop     r13
0x18000fe60  pop     r12
0x18000fe62  pop     rdi
0x18000fe63  pop     rsi
0x18000fe64  pop     rbx
0x18000fe65  pop     rbp
0x18000fe66  retn
```
