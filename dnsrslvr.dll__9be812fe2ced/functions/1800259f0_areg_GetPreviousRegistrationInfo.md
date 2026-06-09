# areg_GetPreviousRegistrationInfo

- ea: `0x1800259f0`
- end: `0x180025d16`
- name: `areg_GetPreviousRegistrationInfo`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034828`

## callees

- `0x1800158bc`
- `0x1800259f0`
- `0x180026134`
- `0x180026270`
- `0x1800264e4`
- `0x18002759c`
- `0x180046ec0`
- `0x180047818`
- `0x18007c108`
- `0x180085fb8`
- `0x180086c38`
- `0x180086f24`

## import_xrefs

- `DNSAPI!Faz_AreServerListsInSameNameSpace` at `0x180025bfe`
- `DNSAPI!Faz_AreServerListsInSameNameSpace` at `0x180025bfe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180025ac3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180025ac3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025afc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025afc`

## pseudocode

```c
__int64 __fastcall areg_GetPreviousRegistrationInfo(__int64 a1, int a2, _OWORD *a3)
{
  int v3; // esi
  __int64 v7; // r15
  const WCHAR *v8; // r14
  DWORD i; // r13d
  const WCHAR *v10; // rax
  _DWORD *EntryFromRegistry; // rax
  _DWORD *v12; // rbx
  int v13; // eax
  int v14; // esi
  int v15; // r10d
  int v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = *(_DWORD *)(a1 + 232);
  v17 = v3;
  cchName[0] = 260;
  v7 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qdSSd(a1, a2, (_DWORD)a3, a1, a2, *(_QWORD *)(a1 + 24));
  memset_0(a3, 0, 0x40u);
  if ( a2 == 1 )
  {
    v8 = *(const WCHAR **)(a1 + 40);
  }
  else
  {
    if ( a2 != 2 )
      goto LABEL_35;
    v8 = *(const WCHAR **)(a1 + 48);
  }
  if ( v8 )
  {
    for ( i = 0; ; ++i )
    {
      cchName[0] = 260;
      if ( RegEnumKeyExW(g_hAregRegKey, i, Name, cchName, 0, 0, 0, 0) )
        break;
      v10 = *(const WCHAR **)(a1 + 24);
      if ( !v10 || CompareStringW(0x409u, 1u, Name, -1, v10, -1) != 2 )
      {
        EntryFromRegistry = areg_ReadEntryFromRegistry(Name, 1, 1);
        v12 = EntryFromRegistry;
        if ( EntryFromRegistry )
        {
          v13 = EntryFromRegistry[58];
          if ( v13 == v3 )
          {
            if ( (unsigned int)Dns_NameCompare_W(*((PCNZWCH *)v12 + 4), *(PCNZWCH *)(a1 + 32)) )
            {
              v14 = 0;
              if ( !(unsigned int)Dns_NameCompare_W(*((PCNZWCH *)v12 + 6), v8) )
              {
                v14 = Dns_NameCompare_W(*((PCNZWCH *)v12 + 5), v8);
                if ( !v14 )
                  goto LABEL_32;
              }
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_S(1035, 138, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, Name);
              if ( !(unsigned int)Faz_AreServerListsInSameNameSpace(v8, *(_QWORD *)(a1 + 96), *((_QWORD *)v12 + 12)) )
                goto LABEL_32;
              v18 = 0;
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_S(1035, 139, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, Name);
              areg_CreateForwardRecordsForEntry(v12, 2 - (unsigned int)(v14 != 0), &v18);
              if ( v18
                && (v7 = Dns_RecordListAppend(v7), a3)
                && *(_WORD *)a3 == (_WORD)v15
                && *(_DWORD *)(a1 + 300) == v15 )
              {
                v3 = v17;
                if ( *((_WORD *)v12 + 52) == (_WORD)v15 )
                {
                  *a3 = *(_OWORD *)(v12 + 26);
                  a3[1] = *(_OWORD *)(v12 + 30);
                  a3[2] = *(_OWORD *)(v12 + 34);
                  a3[3] = *(_OWORD *)(v12 + 38);
                }
              }
              else
              {
LABEL_32:
                v3 = v17;
              }
            }
          }
          else if ( SBYTE2(xmmword_1800AB5A0) < 0 )
          {
            WPP_SF_Sdd(
              1047,
              137,
              (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids,
              (unsigned int)Name,
              v13,
              v3);
          }
          areg_FreeEntry(v12);
        }
        else if ( SBYTE2(xmmword_1800AB5A0) < 0 )
        {
          WPP_SF_S(1047, 136, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, Name);
        }
      }
    }
  }
LABEL_35:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 140, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800259f0  mov     [rsp-8+arg_8], rbx
0x1800259f5  push    rbp
0x1800259f6  push    rsi
0x1800259f7  push    rdi
0x1800259f8  push    r12
0x1800259fa  push    r13
0x1800259fc  push    r14
0x1800259fe  push    r15
0x180025a00  lea     rbp, [rsp-180h]
0x180025a08  sub     rsp, 280h
0x180025a0f  mov     rax, cs:__security_cookie
0x180025a16  xor     rax, rsp
0x180025a19  mov     [rbp+1B0h+var_40], rax
0x180025a20  mov     esi, [rcx+0E8h]
0x180025a26  mov     r12, r8
0x180025a29  mov     [rsp+2B0h+var_270], esi
0x180025a2d  mov     ebx, edx
0x180025a2f  mov     rdi, rcx
0x180025a32  mov     [rsp+2B0h+cchName], 104h
0x180025a3a  xor     r15d, r15d
0x180025a3d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180025a44  jz      short loc_180025A5F
0x180025a46  mov     rax, [rcx+18h]
0x180025a4a  mov     r9, rcx
0x180025a4d  mov     dword ptr [rsp+2B0h+lpftLastWriteTime], esi
0x180025a51  mov     [rsp+2B0h+lpClass], rax
0x180025a56  mov     dword ptr [rsp+2B0h+lpReserved], edx
0x180025a5a  call    WPP_SF_qdSSd
0x180025a5f  xor     edx, edx; Val
0x180025a61  mov     rcx, r12; void *
0x180025a64  lea     r8d, [rdx+40h]; Size
0x180025a68  call    memset_0
0x180025a6d  cmp     ebx, 1
0x180025a70  jnz     short loc_180025A78
0x180025a72  mov     r14, [rdi+28h]
0x180025a76  jmp     short loc_180025A85
0x180025a78  cmp     ebx, 2
0x180025a7b  jnz     loc_180025CC7
0x180025a81  mov     r14, [rdi+30h]
0x180025a85  xor     ecx, ecx
0x180025a87  test    r14, r14
0x180025a8a  jz      loc_180025CC7
0x180025a90  mov     r13d, ecx
0x180025a93  mov     [rsp+2B0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180025a98  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180025a9d  mov     [rsp+2B0h+lpcchClass], rcx; lpcchClass
0x180025aa2  lea     r8, [rsp+2B0h+Name]; lpName
0x180025aa7  mov     [rsp+2B0h+lpClass], rcx; lpClass
0x180025aac  mov     edx, r13d; dwIndex
0x180025aaf  mov     [rsp+2B0h+lpReserved], rcx; lpReserved
0x180025ab4  mov     rcx, cs:g_hAregRegKey; hKey
0x180025abb  mov     [rsp+2B0h+cchName], 104h
0x180025ac3  call    cs:__imp_RegEnumKeyExW
0x180025ac9  test    eax, eax
0x180025acb  jnz     loc_180025CC7
0x180025ad1  mov     rax, [rdi+18h]
0x180025ad5  inc     r13d
0x180025ad8  test    rax, rax
0x180025adb  jz      short loc_180025B0C
0x180025add  or      r9d, 0FFFFFFFFh; cchCount1
0x180025ae1  mov     dword ptr [rsp+2B0h+lpClass], 0FFFFFFFFh; cchCount2
0x180025ae9  lea     r8, [rsp+2B0h+Name]; lpString1
0x180025aee  mov     [rsp+2B0h+lpReserved], rax; lpString2
0x180025af3  mov     ecx, 409h; Locale
0x180025af8  lea     edx, [r9+2]; dwCmpFlags
0x180025afc  call    cs:__imp_CompareStringW
0x180025b02  mov     ecx, 0
0x180025b07  cmp     eax, 2
0x180025b0a  jz      short loc_180025A93
0x180025b0c  mov     edx, 1
0x180025b11  lea     rcx, [rsp+2B0h+Name]; Src
0x180025b16  mov     r8d, edx
0x180025b19  call    areg_ReadEntryFromRegistry
0x180025b1e  xor     ecx, ecx
0x180025b20  mov     rbx, rax
0x180025b23  test    rax, rax
0x180025b26  jnz     short loc_180025B54
0x180025b28  cmp     byte ptr cs:xmmword_1800AB5A0+2, cl
0x180025b2e  jge     loc_180025A93
0x180025b34  mov     edx, 88h
0x180025b39  lea     r9, [rsp+2B0h+Name]
0x180025b3e  mov     ecx, 417h
0x180025b43  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180025b4a  call    WPP_SF_S
0x180025b4f  jmp     loc_180025CC0
0x180025b54  mov     eax, [rax+0E8h]
0x180025b5a  cmp     eax, esi
0x180025b5c  jz      short loc_180025B92
0x180025b5e  cmp     byte ptr cs:xmmword_1800AB5A0+2, cl
0x180025b64  jge     loc_180025CB8
0x180025b6a  mov     edx, 89h
0x180025b6f  mov     dword ptr [rsp+2B0h+lpClass], esi
0x180025b73  mov     ecx, 417h
0x180025b78  mov     dword ptr [rsp+2B0h+lpReserved], eax
0x180025b7c  lea     r9, [rsp+2B0h+Name]
0x180025b81  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180025b88  call    WPP_SF_Sdd
0x180025b8d  jmp     loc_180025CB8
0x180025b92  mov     rdx, [rdi+20h]; lpString2
0x180025b96  mov     rcx, [rbx+20h]; lpString1
0x180025b9a  call    Dns_NameCompare_W
0x180025b9f  test    eax, eax
0x180025ba1  jz      loc_180025CB8
0x180025ba7  mov     rcx, [rbx+30h]; lpString1
0x180025bab  mov     rdx, r14; lpString2
0x180025bae  xor     esi, esi
0x180025bb0  call    Dns_NameCompare_W
0x180025bb5  test    eax, eax
0x180025bb7  jnz     short loc_180025BCF
0x180025bb9  mov     rcx, [rbx+28h]; lpString1
0x180025bbd  mov     rdx, r14; lpString2
0x180025bc0  call    Dns_NameCompare_W
0x180025bc5  mov     esi, eax
0x180025bc7  test    eax, eax
0x180025bc9  jz      loc_180025CB4
0x180025bcf  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180025bd6  jz      short loc_180025BF3
0x180025bd8  mov     edx, 8Ah
0x180025bdd  lea     r9, [rsp+2B0h+Name]
0x180025be2  mov     ecx, 40Bh
0x180025be7  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180025bee  call    WPP_SF_S
0x180025bf3  mov     r8, [rbx+60h]
0x180025bf7  mov     rcx, r14
0x180025bfa  mov     rdx, [rdi+60h]
0x180025bfe  call    cs:__imp_Faz_AreServerListsInSameNameSpace
0x180025c04  test    eax, eax
0x180025c06  jz      loc_180025CB4
0x180025c0c  mov     [rsp+2B0h+var_268], 0
0x180025c15  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180025c1c  jz      short loc_180025C39
0x180025c1e  mov     edx, 8Bh
0x180025c23  lea     r9, [rsp+2B0h+Name]
0x180025c28  mov     ecx, 40Bh
0x180025c2d  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180025c34  call    WPP_SF_S
0x180025c39  neg     esi
0x180025c3b  lea     r8, [rsp+2B0h+var_268]
0x180025c40  mov     rcx, rbx
0x180025c43  sbb     edx, edx
0x180025c45  add     edx, 2
0x180025c48  call    areg_CreateForwardRecordsForEntry
0x180025c4d  mov     rdx, [rsp+2B0h+var_268]
0x180025c52  xor     r10d, r10d
0x180025c55  test    rdx, rdx
0x180025c58  jz      short loc_180025CB4
0x180025c5a  mov     rcx, r15
0x180025c5d  call    Dns_RecordListAppend
0x180025c62  mov     r15, rax
0x180025c65  test    r12, r12
0x180025c68  jz      short loc_180025CB4
0x180025c6a  cmp     [r12], r10w
0x180025c6f  jnz     short loc_180025CB4
0x180025c71  cmp     [rdi+12Ch], r10d
0x180025c78  jnz     short loc_180025CB4
0x180025c7a  mov     esi, [rsp+2B0h+var_270]
0x180025c7e  cmp     [rbx+68h], r10w
0x180025c83  jnz     short loc_180025CB8
0x180025c85  movups  xmm0, xmmword ptr [rbx+68h]
0x180025c89  movaps  xmmword ptr [r12], xmm0
0x180025c8e  movups  xmm1, xmmword ptr [rbx+78h]
0x180025c92  movaps  xmmword ptr [r12+10h], xmm1
0x180025c98  movups  xmm0, xmmword ptr [rbx+88h]
0x180025c9f  movaps  xmmword ptr [r12+20h], xmm0
0x180025ca5  movups  xmm1, xmmword ptr [rbx+98h]
0x180025cac  movaps  xmmword ptr [r12+30h], xmm1
0x180025cb2  jmp     short loc_180025CB8
0x180025cb4  mov     esi, [rsp+2B0h+var_270]
0x180025cb8  mov     rcx, rbx; void *
0x180025cbb  call    areg_FreeEntry
0x180025cc0  xor     ecx, ecx
0x180025cc2  jmp     loc_180025A93
0x180025cc7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180025cce  jz      short loc_180025CE9
0x180025cd0  mov     edx, 8Ch
0x180025cd5  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180025cdc  mov     ecx, 40Bh
0x180025ce1  mov     r9, r15
0x180025ce4  call    WPP_SF_q
0x180025ce9  mov     rax, r15
0x180025cec  mov     rcx, [rbp+1B0h+var_40]
0x180025cf3  xor     rcx, rsp; StackCookie
0x180025cf6  call    __security_check_cookie
0x180025cfb  mov     rbx, [rsp+2B0h+arg_8]
0x180025d03  add     rsp, 280h
0x180025d0a  pop     r15
0x180025d0c  pop     r14
0x180025d0e  pop     r13
0x180025d10  pop     r12
0x180025d12  pop     rdi
0x180025d13  pop     rsi
0x180025d14  pop     rbp
0x180025d15  retn
```
