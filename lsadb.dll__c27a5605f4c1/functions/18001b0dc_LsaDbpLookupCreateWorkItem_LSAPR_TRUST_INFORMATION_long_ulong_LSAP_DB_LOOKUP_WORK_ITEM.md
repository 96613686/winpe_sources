# LsaDbpLookupCreateWorkItem(_LSAPR_TRUST_INFORMATION *,long,ulong,_LSAP_DB_LOOKUP_WORK_ITEM * *)

- ea: `0x18001b0dc`
- end: `0x18001b20e`
- name: `?LsaDbpLookupCreateWorkItem@@YAJPEAU_LSAPR_TRUST_INFORMATION@@JKPEAPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, int, __int64, struct _LSAP_DB_LOOKUP_WORK_ITEM **)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b2d4`
- `0x18001b94c`
- `0x18001bbd4`
- `0x18001be28`

## callees

- `0x180001fb8`
- `0x18001b0dc`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b0ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b144`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b18c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b1ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b0ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b144`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b18c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b1ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b1c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b1d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b1df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b1c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b1d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b1df`
- `ntdll!RtlCopyUnicodeString` at `0x18001b1a2`
- `ntdll!RtlCopyUnicodeString` at `0x18001b1a2`
- `ntdll!RtlLengthSid` at `0x18001b139`
- `ntdll!RtlLengthSid` at `0x18001b15e`
- `ntdll!RtlLengthSid` at `0x18001b139`
- `ntdll!RtlLengthSid` at `0x18001b15e`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupCreateWorkItem(
        PCUNICODE_STRING SourceString,
        int a2,
        __int64 a3,
        struct _LSAP_DB_LOOKUP_WORK_ITEM **a4)
{
  char *v7; // rax
  char *v8; // rbx
  unsigned int v9; // edi
  void *v10; // rcx
  ULONG v11; // eax
  HLOCAL v12; // rax
  ULONG v13; // eax
  HLOCAL v14; // rax
  HLOCAL v15; // rax
  void *v16; // rcx
  void *v17; // rcx

  v7 = (char *)LocalAlloc(0x40u, 0x48u);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -1073741801;
    goto LABEL_18;
  }
  memset_0(v7, 0, 0x48u);
  *((_DWORD *)v8 + 4) = 5;
  if ( !SourceString )
    goto LABEL_10;
  v10 = *(void **)&SourceString[1].Length;
  if ( !v10 )
  {
LABEL_8:
    *((_WORD *)v8 + 13) = SourceString->Length + 2;
    v14 = LocalAlloc(0x40u, SourceString->Length + 2LL);
    *((_QWORD *)v8 + 4) = v14;
    if ( !v14 )
      goto LABEL_6;
    RtlCopyUnicodeString((PUNICODE_STRING)(v8 + 24), SourceString);
LABEL_10:
    v15 = LocalAlloc(0x40u, 0x40u);
    if ( v15 )
    {
      v9 = 0;
      *((_DWORD *)v8 + 14) = 16;
      *((_DWORD *)v8 + 13) = 0;
      *((_QWORD *)v8 + 8) = v15;
      *((_DWORD *)v8 + 12) = a2;
      goto LABEL_18;
    }
    v9 = -1073741801;
    goto LABEL_12;
  }
  v11 = RtlLengthSid(v10);
  v12 = LocalAlloc(0x40u, v11);
  *((_QWORD *)v8 + 5) = v12;
  if ( v12 )
  {
    v13 = RtlLengthSid(*(PSID *)&SourceString[1].Length);
    memcpy_0(*((void **)v8 + 5), *(const void **)&SourceString[1].Length, v13);
    goto LABEL_8;
  }
LABEL_6:
  v9 = -1073741670;
LABEL_12:
  v16 = (void *)*((_QWORD *)v8 + 5);
  if ( v16 )
    LocalFree(v16);
  v17 = (void *)*((_QWORD *)v8 + 4);
  if ( v17 )
    LocalFree(v17);
  LocalFree(v8);
  v8 = 0;
LABEL_18:
  *a4 = (struct _LSAP_DB_LOOKUP_WORK_ITEM *)v8;
  return v9;
}

```

## disassembly

```asm
0x18001b0dc  push    rbx
0x18001b0de  push    rbp
0x18001b0df  push    rsi
0x18001b0e0  push    rdi
0x18001b0e1  push    r14
0x18001b0e3  push    r15
0x18001b0e5  sub     rsp, 28h
0x18001b0e9  mov     esi, 48h ; 'H'
0x18001b0ee  mov     ebp, edx
0x18001b0f0  mov     rdi, rcx
0x18001b0f3  mov     edx, esi; uBytes
0x18001b0f5  mov     r14, r9
0x18001b0f8  lea     r15d, [rsi-8]
0x18001b0fc  mov     ecx, r15d; uFlags
0x18001b0ff  call    cs:__imp_LocalAlloc
0x18001b105  mov     rbx, rax
0x18001b108  test    rax, rax
0x18001b10b  jnz     short loc_18001B117
0x18001b10d  mov     edi, 0C0000017h
0x18001b112  jmp     loc_18001B1FC
0x18001b117  mov     r8, rsi; Size
0x18001b11a  xor     edx, edx; Val
0x18001b11c  mov     rcx, rbx; void *
0x18001b11f  call    memset_0
0x18001b124  mov     dword ptr [rbx+10h], 5
0x18001b12b  test    rdi, rdi
0x18001b12e  jz      short loc_18001B1A8
0x18001b130  mov     rcx, [rdi+10h]; Sid
0x18001b134  test    rcx, rcx
0x18001b137  jz      short loc_18001B174
0x18001b139  call    cs:__imp_RtlLengthSid
0x18001b13f  mov     edx, eax; uBytes
0x18001b141  mov     ecx, r15d; uFlags
0x18001b144  call    cs:__imp_LocalAlloc
0x18001b14a  mov     [rbx+28h], rax
0x18001b14e  test    rax, rax
0x18001b151  jnz     short loc_18001B15A
0x18001b153  mov     edi, 0C000009Ah
0x18001b158  jmp     short loc_18001B1BE
0x18001b15a  mov     rcx, [rdi+10h]; Sid
0x18001b15e  call    cs:__imp_RtlLengthSid
0x18001b164  mov     rdx, [rdi+10h]; Src
0x18001b168  mov     rcx, [rbx+28h]; void *
0x18001b16c  mov     r8d, eax; Size
0x18001b16f  call    memcpy_0
0x18001b174  movzx   eax, word ptr [rdi]
0x18001b177  mov     ecx, 2
0x18001b17c  add     ax, cx
0x18001b17f  mov     [rbx+1Ah], ax
0x18001b183  movzx   edx, word ptr [rdi]
0x18001b186  add     rdx, rcx; uBytes
0x18001b189  mov     ecx, r15d; uFlags
0x18001b18c  call    cs:__imp_LocalAlloc
0x18001b192  mov     [rbx+20h], rax
0x18001b196  test    rax, rax
0x18001b199  jz      short loc_18001B153
0x18001b19b  mov     rdx, rdi; SourceString
0x18001b19e  lea     rcx, [rbx+18h]; DestinationString
0x18001b1a2  call    cs:__imp_RtlCopyUnicodeString
0x18001b1a8  mov     rdx, r15; uBytes
0x18001b1ab  mov     ecx, r15d; uFlags
0x18001b1ae  call    cs:__imp_LocalAlloc
0x18001b1b4  test    rax, rax
0x18001b1b7  jnz     short loc_18001B1E9
0x18001b1b9  mov     edi, 0C0000017h
0x18001b1be  mov     rcx, [rbx+28h]; hMem
0x18001b1c2  test    rcx, rcx
0x18001b1c5  jz      short loc_18001B1CD
0x18001b1c7  call    cs:__imp_LocalFree
0x18001b1cd  mov     rcx, [rbx+20h]; hMem
0x18001b1d1  test    rcx, rcx
0x18001b1d4  jz      short loc_18001B1DC
0x18001b1d6  call    cs:__imp_LocalFree
0x18001b1dc  mov     rcx, rbx; hMem
0x18001b1df  call    cs:__imp_LocalFree
0x18001b1e5  xor     ebx, ebx
0x18001b1e7  jmp     short loc_18001B1FC
0x18001b1e9  xor     edi, edi
0x18001b1eb  mov     dword ptr [rbx+38h], 10h
0x18001b1f2  mov     [rbx+34h], edi
0x18001b1f5  mov     [rbx+40h], rax
0x18001b1f9  mov     [rbx+30h], ebp
0x18001b1fc  mov     [r14], rbx
0x18001b1ff  mov     eax, edi
0x18001b201  add     rsp, 28h
0x18001b205  pop     r15
0x18001b207  pop     r14
0x18001b209  pop     rdi
0x18001b20a  pop     rsi
0x18001b20b  pop     rbp
0x18001b20c  pop     rbx
0x18001b20d  retn
```
