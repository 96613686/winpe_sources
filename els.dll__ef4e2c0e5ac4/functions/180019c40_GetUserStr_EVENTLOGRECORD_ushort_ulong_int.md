# GetUserStr(_EVENTLOGRECORD *,ushort *,ulong,int)

- ea: `0x180019c40`
- end: `0x180019f66`
- name: `?GetUserStr@@YAPEAGPEAU_EVENTLOGRECORD@@PEAGKH@Z`
- size: `806`
- prototype: `unsigned __int16 *__fastcall(struct _EVENTLOGRECORD *, unsigned __int16 *, unsigned int, int)`
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000aac0`
- `0x18000b6b8`
- `0x1800150a0`
- `0x180015860`
- `0x18001766c`
- `0x18001a3d0`

## callees

- `0x1800036a6`
- `0x180005274`
- `0x180017e00`
- `0x180019c40`
- `0x180019f6c`
- `0x18001b3f8`
- `0x180020430`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180019d96`
- `msvcrt!wcsrchr` at `0x180019d96`
- `msvcrt!wcscat_s` at `0x180019eea`
- `msvcrt!wcscat_s` at `0x180019eff`
- `msvcrt!wcscat_s` at `0x180019eea`
- `msvcrt!wcscat_s` at `0x180019eff`
- `msvcrt!wcsncpy_s` at `0x180019db5`
- `msvcrt!wcsncpy_s` at `0x180019f41`
- `msvcrt!wcsncpy_s` at `0x180019db5`
- `msvcrt!wcsncpy_s` at `0x180019f41`
- `msvcrt!free` at `0x180019d18`
- `msvcrt!free` at `0x180019dc7`
- `msvcrt!free` at `0x180019f4f`
- `msvcrt!free` at `0x180019d18`
- `msvcrt!free` at `0x180019dc7`
- `msvcrt!free` at `0x180019f4f`
- `msvcrt!malloc` at `0x180019cc8`
- `msvcrt!malloc` at `0x180019cc8`
- `msvcrt!wcscpy_s` at `0x180019ed3`
- `msvcrt!wcscpy_s` at `0x180019f11`
- `msvcrt!wcscpy_s` at `0x180019ed3`
- `msvcrt!wcscpy_s` at `0x180019f11`
- `ntdll!RtlLengthSid` at `0x180019ca4`
- `ntdll!RtlLengthSid` at `0x180019ca4`
- `ADVAPI32!IsValidSid` at `0x180019d03`
- `ADVAPI32!IsValidSid` at `0x180019d03`
- `ADVAPI32!LookupAccountSidW` at `0x180019e3a`
- `ADVAPI32!LookupAccountSidW` at `0x180019e83`
- `ADVAPI32!LookupAccountSidW` at `0x180019e3a`
- `ADVAPI32!LookupAccountSidW` at `0x180019e83`
- `USER32!SetCursor` at `0x180019f5b`
- `USER32!SetCursor` at `0x180019f5b`

## pseudocode

```c
unsigned __int16 *__fastcall GetUserStr(struct _EVENTLOGRECORD *a1, unsigned __int16 *a2, unsigned int a3, int a4)
{
  int v4; // r12d
  rsize_t v5; // rsi
  unsigned __int16 *v6; // rbx
  UINT v8; // ecx
  char *v9; // rdi
  size_t v10; // r13
  char v11; // r15
  char *v12; // rax
  char *v13; // r12
  wchar_t *v14; // r9
  rsize_t v16; // r14
  rsize_t v17; // rsi
  wchar_t *v18; // rax
  wchar_t *v19; // r8
  __int64 v20; // rax
  CSidCache *v21; // rcx
  CSidCache *v22; // rcx
  wchar_t *v23; // r8
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  HCURSOR hCursor[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Source[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Str[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t Destination[520]; // [rsp+680h] [rbp+580h] BYREF

  v4 = a4;
  LODWORD(hCursor[0]) = a4;
  v5 = a3;
  v6 = a2;
  if ( !a1->UserSidLength )
  {
    v8 = 200;
LABEL_13:
    v14 = (wchar_t *)L"---";
    goto LABEL_14;
  }
  v9 = (char *)a1 + a1->UserSidOffset;
  if ( v9 >= (char *)a1 + a1->Length
    || (v10 = RtlLengthSid((char *)a1 + a1->UserSidOffset), &v9[v10] > (char *)a1 + a1->Length) )
  {
LABEL_12:
    v8 = 291;
    a2 = v6;
    goto LABEL_13;
  }
  v11 = 0;
  if ( ((unsigned __int8)v9 & 7) != 0 )
  {
    v12 = (char *)malloc((unsigned int)v10);
    v13 = v12;
    if ( !v12 )
    {
      v14 = L"out of memory";
      a2 = v6;
      v8 = 343;
LABEL_14:
      LoadStr(v8, a2, (unsigned int)v5, v14);
      return v6;
    }
    v11 = 1;
    memcpy_0(v12, v9, v10);
    v9 = v13;
    v4 = (int)hCursor[0];
  }
  if ( !IsValidSid(v9) )
  {
    if ( v11 )
      free(v9);
    goto LABEL_12;
  }
  if ( (unsigned int)CLruCache::Fetch((CLruCache *)&g_SidCache, v9, Str, 0x20Au) )
  {
    peUse = 0;
    cchName = 256;
    cchReferencedDomainName = 260;
    *v6 = 0;
    CWaitCursor::CWaitCursor((CWaitCursor *)hCursor);
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)&a1[1].Length + v20) );
    if ( LookupAccountSidW(
           (LPCWSTR)&a1[1].Length + v20 + 1,
           v9,
           Name,
           &cchName,
           Source,
           &cchReferencedDomainName,
           &peUse)
      || (cchName = 256,
          cchReferencedDomainName = 260,
          LookupAccountSidW(0, v9, Name, &cchName, Source, &cchReferencedDomainName, &peUse))
      && peUse == SidTypeWellKnownGroup )
    {
      if ( Source[0] )
      {
        wcscpy_s(Destination, 0x205u, Source);
        wcscat_s(Destination, 0x205u, L"\\");
        wcscat_s(Destination, 0x205u, Name);
      }
      else
      {
        wcscpy_s(Destination, 0x205u, Name);
      }
      CSidCache::Add(v22, v9, Destination);
      v23 = Destination;
      if ( !v4 )
        v23 = Name;
      wcsncpy_s(v6, v5, v23, (unsigned int)(v5 - 1));
    }
    else
    {
      SidToStr(v9, v6, v5);
      CSidCache::Add(v21, v9, v6);
    }
    if ( v11 )
      free(v9);
    SetCursor(hCursor[0]);
  }
  else
  {
    v16 = v5;
    v17 = (unsigned int)(v5 - 1);
    if ( v4 || (v18 = wcsrchr(Str, 0x5Cu), v19 = v18 + 1, !v18) )
      v19 = Str;
    wcsncpy_s(v6, v16, v19, v17);
    if ( v11 )
      free(v9);
  }
  return v6;
}

```

## disassembly

```asm
0x180019c40  mov     [rsp-8+arg_18], rbx
0x180019c45  push    rbp
0x180019c46  push    rsi
0x180019c47  push    rdi
0x180019c48  push    r12
0x180019c4a  push    r13
0x180019c4c  push    r14
0x180019c4e  push    r15
0x180019c50  lea     rbp, [rsp-9A0h]
0x180019c58  sub     rsp, 0AA0h
0x180019c5f  mov     rax, cs:__security_cookie
0x180019c66  xor     rax, rsp
0x180019c69  mov     [rbp+9D0h+var_40], rax
0x180019c70  mov     r12d, r9d
0x180019c73  mov     dword ptr [rsp+0AD0h+hCursor], r9d
0x180019c78  mov     esi, r8d
0x180019c7b  mov     rbx, rdx
0x180019c7e  mov     r14, rcx
0x180019c81  cmp     dword ptr [rcx+28h], 0
0x180019c85  jnz     short loc_180019C91
0x180019c87  mov     ecx, 0C8h
0x180019c8c  jmp     loc_180019D26
0x180019c91  mov     edi, [rcx+2Ch]
0x180019c94  add     rdi, r14
0x180019c97  mov     eax, [rcx]
0x180019c99  add     rax, r14
0x180019c9c  cmp     rdi, rax
0x180019c9f  jnb     short loc_180019D1E
0x180019ca1  mov     rcx, rdi; Sid
0x180019ca4  call    cs:__imp_RtlLengthSid
0x180019caa  mov     r13d, eax
0x180019cad  mov     ecx, [r14]
0x180019cb0  add     rcx, r14
0x180019cb3  lea     rax, [rdi+r13]
0x180019cb7  cmp     rax, rcx
0x180019cba  ja      short loc_180019D1E
0x180019cbc  xor     r15b, r15b
0x180019cbf  test    dil, 7
0x180019cc3  jz      short loc_180019D00
0x180019cc5  mov     ecx, r13d; Size
0x180019cc8  call    cs:__imp_malloc
0x180019cce  mov     r12, rax
0x180019cd1  test    rax, rax
0x180019cd4  jnz     short loc_180019CE7
0x180019cd6  lea     r9, aOutOfMemory; "out of memory"
0x180019cdd  mov     rdx, rbx
0x180019ce0  mov     ecx, 157h
0x180019ce5  jmp     short loc_180019D2D
0x180019ce7  mov     r15b, 1
0x180019cea  mov     r8, r13; Size
0x180019ced  mov     rdx, rdi; Src
0x180019cf0  mov     rcx, r12; void *
0x180019cf3  call    memcpy_0
0x180019cf8  mov     rdi, r12
0x180019cfb  mov     r12d, dword ptr [rsp+0AD0h+hCursor]
0x180019d00  mov     rcx, rdi; pSid
0x180019d03  call    cs:__imp_IsValidSid
0x180019d09  xor     r13d, r13d
0x180019d0c  test    eax, eax
0x180019d0e  jnz     short loc_180019D62
0x180019d10  test    r15b, r15b
0x180019d13  jz      short loc_180019D1E
0x180019d15  mov     rcx, rdi; Block
0x180019d18  call    cs:__imp_free
0x180019d1e  mov     ecx, 123h; uID
0x180019d23  mov     rdx, rbx; Destination
0x180019d26  lea     r9, asc_180028B38; "---"
0x180019d2d  mov     r8d, esi; SizeInWords
0x180019d30  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x180019d35  mov     rax, rbx
0x180019d38  mov     rcx, [rbp+9D0h+var_40]
0x180019d3f  xor     rcx, rsp; StackCookie
0x180019d42  call    __security_check_cookie
0x180019d47  mov     rbx, [rsp+0AD0h+arg_18]
0x180019d4f  add     rsp, 0AA0h
0x180019d56  pop     r15
0x180019d58  pop     r14
0x180019d5a  pop     r13
0x180019d5c  pop     r12
0x180019d5e  pop     rdi
0x180019d5f  pop     rsi
0x180019d60  pop     rbp
0x180019d61  retn
0x180019d62  mov     r9d, 20Ah; unsigned int
0x180019d68  lea     r8, [rbp+9D0h+Str]; void *
0x180019d6f  mov     rdx, rdi; void *
0x180019d72  lea     rcx, ?g_SidCache@@3VCSidCache@@A; this
0x180019d79  call    ?Fetch@CLruCache@@UEAAJPEAX0K@Z; CLruCache::Fetch(void *,void *,ulong)
0x180019d7e  test    eax, eax
0x180019d80  jnz     short loc_180019DD2
0x180019d82  mov     r14, rsi
0x180019d85  dec     esi
0x180019d87  test    r12d, r12d
0x180019d8a  jnz     short loc_180019DA5
0x180019d8c  lea     edx, [rax+5Ch]; Ch
0x180019d8f  lea     rcx, [rbp+9D0h+Str]; Str
0x180019d96  call    cs:__imp_wcsrchr
0x180019d9c  test    rax, rax
0x180019d9f  lea     r8, [rax+2]
0x180019da3  jnz     short loc_180019DAC
0x180019da5  lea     r8, [rbp+9D0h+Str]; Source
0x180019dac  mov     r9, rsi; MaxCount
0x180019daf  mov     rdx, r14; SizeInWords
0x180019db2  mov     rcx, rbx; Destination
0x180019db5  call    cs:__imp_wcsncpy_s
0x180019dbb  test    r15b, r15b
0x180019dbe  jz      loc_180019D35
0x180019dc4  mov     rcx, rdi; Block
0x180019dc7  call    cs:__imp_free
0x180019dcd  jmp     loc_180019D35
0x180019dd2  mov     [rsp+0AD0h+var_A88], r13d
0x180019dd7  mov     [rsp+0AD0h+cchName], 100h
0x180019ddf  mov     [rsp+0AD0h+var_A90], 104h
0x180019de7  mov     [rbx], r13w
0x180019deb  lea     rcx, [rsp+0AD0h+hCursor]; this
0x180019df0  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x180019df5  nop
0x180019df6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019dfa  inc     rax
0x180019dfd  cmp     [r14+rax*2+38h], r13w
0x180019e03  jnz     short loc_180019DFA
0x180019e05  add     rax, 1Dh
0x180019e09  lea     rcx, [r14+rax*2]; lpSystemName
0x180019e0d  lea     rax, [rsp+0AD0h+var_A88]
0x180019e12  mov     [rsp+0AD0h+peUse], rax; peUse
0x180019e17  lea     rax, [rsp+0AD0h+var_A90]
0x180019e1c  mov     [rsp+0AD0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180019e21  lea     rax, [rbp+9D0h+Source]
0x180019e28  mov     [rsp+0AD0h+ReferencedDomainName], rax; ReferencedDomainName
0x180019e2d  lea     r9, [rsp+0AD0h+cchName]; cchName
0x180019e32  lea     r8, [rsp+0AD0h+Name]; Name
0x180019e37  mov     rdx, rdi; Sid
0x180019e3a  call    cs:__imp_LookupAccountSidW
0x180019e40  test    eax, eax
0x180019e42  jnz     short loc_180019EB2
0x180019e44  mov     [rsp+0AD0h+cchName], 100h
0x180019e4c  mov     [rsp+0AD0h+var_A90], 104h
0x180019e54  lea     rax, [rsp+0AD0h+var_A88]
0x180019e59  mov     [rsp+0AD0h+peUse], rax; peUse
0x180019e5e  lea     rax, [rsp+0AD0h+var_A90]
0x180019e63  mov     [rsp+0AD0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180019e68  lea     rax, [rbp+9D0h+Source]
0x180019e6f  mov     [rsp+0AD0h+ReferencedDomainName], rax; ReferencedDomainName
0x180019e74  lea     r9, [rsp+0AD0h+cchName]; cchName
0x180019e79  lea     r8, [rsp+0AD0h+Name]; Name
0x180019e7e  mov     rdx, rdi; Sid
0x180019e81  xor     ecx, ecx; lpSystemName
0x180019e83  call    cs:__imp_LookupAccountSidW
0x180019e89  test    eax, eax
0x180019e8b  jz      short loc_180019E94
0x180019e8d  cmp     [rsp+0AD0h+var_A88], 5
0x180019e92  jz      short loc_180019EB2
0x180019e94  mov     r8d, esi; unsigned int
0x180019e97  mov     rdx, rbx; unsigned __int16 *
0x180019e9a  mov     rcx, rdi; void *
0x180019e9d  call    ?SidToStr@@YAXPEAXPEAGK@Z; SidToStr(void *,ushort *,ulong)
0x180019ea2  mov     r8, rbx; unsigned __int16 *
0x180019ea5  mov     rdx, rdi; void *
0x180019ea8  call    ?Add@CSidCache@@QEAAJPEAXPEBG@Z; CSidCache::Add(void *,ushort const *)
0x180019ead  jmp     loc_180019F47
0x180019eb2  lea     rcx, [rbp+9D0h+Destination]; Destination
0x180019eb9  cmp     [rbp+9D0h+Source], r13w
0x180019ec1  jz      short loc_180019F07
0x180019ec3  lea     r8, [rbp+9D0h+Source]; Source
0x180019eca  mov     r14d, 205h
0x180019ed0  mov     edx, r14d; SizeInWords
0x180019ed3  call    cs:__imp_wcscpy_s
0x180019ed9  lea     r8, SubBlock; "\\"
0x180019ee0  mov     edx, r14d; SizeInWords
0x180019ee3  lea     rcx, [rbp+9D0h+Destination]; Destination
0x180019eea  call    cs:__imp_wcscat_s
0x180019ef0  lea     r8, [rsp+0AD0h+Name]; Source
0x180019ef5  mov     edx, r14d; SizeInWords
0x180019ef8  lea     rcx, [rbp+9D0h+Destination]; Destination
0x180019eff  call    cs:__imp_wcscat_s
0x180019f05  jmp     short loc_180019F17
0x180019f07  lea     r8, [rsp+0AD0h+Name]; Source
0x180019f0c  mov     edx, 205h; SizeInWords
0x180019f11  call    cs:__imp_wcscpy_s
0x180019f17  lea     r8, [rbp+9D0h+Destination]; unsigned __int16 *
0x180019f1e  mov     rdx, rdi; void *
0x180019f21  call    ?Add@CSidCache@@QEAAJPEAXPEBG@Z; CSidCache::Add(void *,ushort const *)
0x180019f26  lea     r9d, [rsi-1]; MaxCount
0x180019f2a  mov     rdx, rsi; SizeInWords
0x180019f2d  mov     rcx, rbx; Destination
0x180019f30  test    r12d, r12d
0x180019f33  lea     r8, [rbp+9D0h+Destination]
0x180019f3a  jnz     short loc_180019F41
0x180019f3c  lea     r8, [rsp+0AD0h+Name]; Source
0x180019f41  call    cs:__imp_wcsncpy_s
0x180019f47  test    r15b, r15b
0x180019f4a  jz      short loc_180019F56
0x180019f4c  mov     rcx, rdi; Block
0x180019f4f  call    cs:__imp_free
0x180019f55  nop
0x180019f56  mov     rcx, [rsp+0AD0h+hCursor]; hCursor
0x180019f5b  call    cs:__imp_SetCursor
0x180019f61  jmp     loc_180019D35
```
