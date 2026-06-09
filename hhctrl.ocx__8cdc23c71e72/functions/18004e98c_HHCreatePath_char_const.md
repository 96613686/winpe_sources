# HHCreatePath(char const *)

- ea: `0x18004e98c`
- end: `0x18004eaf3`
- name: `?HHCreatePath@@YAKPEBD@Z`
- size: `359`
- prototype: `unsigned int __fastcall(const char *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004af3c`
- `0x18004ed04`
- `0x18004ed7c`
- `0x18004f3cc`

## callees

- `0x1800095c8`
- `0x18004e98c`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `KERNEL32!IsDBCSLeadByte` at `0x18004ea44`
- `KERNEL32!IsDBCSLeadByte` at `0x18004ea88`
- `KERNEL32!IsDBCSLeadByte` at `0x18004ea44`
- `KERNEL32!IsDBCSLeadByte` at `0x18004ea88`
- `KERNEL32!CreateDirectoryA` at `0x18004ea6e`
- `KERNEL32!CreateDirectoryA` at `0x18004eaba`
- `KERNEL32!CreateDirectoryA` at `0x18004ea6e`
- `KERNEL32!CreateDirectoryA` at `0x18004eaba`
- `KERNEL32!GetLastError` at `0x18004ea78`
- `KERNEL32!GetLastError` at `0x18004eac4`
- `KERNEL32!GetLastError` at `0x18004ea78`
- `KERNEL32!GetLastError` at `0x18004eac4`

## pseudocode

```c
DWORD __fastcall HHCreatePath(const char *a1)
{
  size_t v1; // r10
  DWORD result; // eax
  BYTE *v3; // rbx
  CHAR *v4; // rdi
  BYTE v5; // si
  unsigned __int64 v6; // rax
  BYTE v7; // cl
  BOOL v8; // eax
  BYTE v9; // al
  BOOL v10; // eax
  DWORD LastError; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-E0h] BYREF
  CHAR PathName[272]; // [rsp+40h] [rbp-C0h] BYREF
  char v14[272]; // [rsp+150h] [rbp+50h] BYREF

  if ( StringCchCopyA(v14, 0x104u, a1) < 0 )
    return 3;
  memset_0(PathName, 0, v1);
  v3 = (BYTE *)v14;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  v4 = PathName;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  while ( 1 )
  {
    v5 = *v3;
    if ( !*v3 )
      break;
    if ( v5 == 47 || v5 == 92 )
    {
      if ( PathName[1] != 58 )
        goto LABEL_26;
      v6 = -1;
      do
        ++v6;
      while ( PathName[v6] );
      if ( v6 > 3 )
      {
LABEL_26:
        if ( !CreateDirectoryA(PathName, &SecurityAttributes) )
        {
          result = GetLastError();
          if ( result != 183 )
            return result;
        }
        goto LABEL_17;
      }
      v7 = *v3++;
      v8 = IsDBCSLeadByte(v7);
      *v4++ = v5;
      if ( v8 )
      {
        v9 = *v3;
        if ( *v3 )
        {
          ++v3;
          goto LABEL_14;
        }
      }
    }
    else
    {
LABEL_17:
      v10 = IsDBCSLeadByte(v5);
      ++v3;
      *v4++ = v5;
      if ( v10 )
      {
        v9 = *v3;
        if ( *v3 )
        {
          ++v3;
LABEL_14:
          *v4++ = v9;
        }
      }
    }
  }
  LastError = 0;
  if ( !CreateDirectoryA(PathName, &SecurityAttributes) )
  {
    LastError = GetLastError();
    if ( LastError == 183 )
      return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18004e98c  push    rbp
0x18004e98e  push    rbx
0x18004e98f  push    rsi
0x18004e990  push    rdi
0x18004e991  lea     rbp, [rsp-178h]
0x18004e999  sub     rsp, 278h
0x18004e9a0  mov     rax, cs:__security_cookie
0x18004e9a7  xor     rax, rsp
0x18004e9aa  mov     [rbp+190h+var_30], rax
0x18004e9b1  mov     r8, rcx; char *
0x18004e9b4  mov     r10d, 104h
0x18004e9ba  mov     edx, r10d; unsigned __int64
0x18004e9bd  lea     rcx, [rbp+190h+var_140]; char *
0x18004e9c1  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004e9c6  test    eax, eax
0x18004e9c8  jns     short loc_18004E9D4
0x18004e9ca  mov     eax, 3
0x18004e9cf  jmp     loc_18004EAD8
0x18004e9d4  mov     r8, r10; Size
0x18004e9d7  lea     rcx, [rsp+290h+PathName]; void *
0x18004e9dc  xor     edx, edx; Val
0x18004e9de  call    memset_0
0x18004e9e3  lea     rbx, [rbp+190h+var_140]
0x18004e9e7  mov     qword ptr [rsp+290h+SecurityAttributes.nLength], 18h
0x18004e9f0  lea     rdi, [rsp+290h+PathName]
0x18004e9f5  mov     qword ptr [rsp+290h+SecurityAttributes.bInheritHandle], 0
0x18004e9fe  mov     [rsp+290h+SecurityAttributes.lpSecurityDescriptor], 0
0x18004ea07  mov     sil, [rbx]
0x18004ea0a  test    sil, sil
0x18004ea0d  jz      loc_18004EAAE
0x18004ea13  cmp     sil, 2Fh ; '/'
0x18004ea17  jz      short loc_18004EA1F
0x18004ea19  cmp     sil, 5Ch ; '\'
0x18004ea1d  jnz     short loc_18004EA85
0x18004ea1f  cmp     [rsp+290h+var_24F], 3Ah ; ':'
0x18004ea24  jnz     short loc_18004EA64
0x18004ea26  lea     rcx, [rsp+290h+PathName]
0x18004ea2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ea2f  inc     rax
0x18004ea32  cmp     byte ptr [rcx+rax], 0
0x18004ea36  jnz     short loc_18004EA2F
0x18004ea38  cmp     rax, 3
0x18004ea3c  ja      short loc_18004EA64
0x18004ea3e  mov     cl, sil; TestChar
0x18004ea41  inc     rbx
0x18004ea44  call    cs:__imp_IsDBCSLeadByte
0x18004ea4a  mov     [rdi], sil
0x18004ea4d  inc     rdi
0x18004ea50  test    eax, eax
0x18004ea52  jz      short loc_18004EA07
0x18004ea54  mov     al, [rbx]
0x18004ea56  test    al, al
0x18004ea58  jz      short loc_18004EA07
0x18004ea5a  inc     rbx
0x18004ea5d  mov     [rdi], al
0x18004ea5f  inc     rdi
0x18004ea62  jmp     short loc_18004EA07
0x18004ea64  lea     rdx, [rsp+290h+SecurityAttributes]; lpSecurityAttributes
0x18004ea69  lea     rcx, [rsp+290h+PathName]; lpPathName
0x18004ea6e  call    cs:__imp_CreateDirectoryA
0x18004ea74  test    eax, eax
0x18004ea76  jnz     short loc_18004EA85
0x18004ea78  call    cs:__imp_GetLastError
0x18004ea7e  cmp     eax, 0B7h
0x18004ea83  jnz     short loc_18004EAD8
0x18004ea85  mov     cl, sil; TestChar
0x18004ea88  call    cs:__imp_IsDBCSLeadByte
0x18004ea8e  inc     rbx
0x18004ea91  mov     [rdi], sil
0x18004ea94  inc     rdi
0x18004ea97  test    eax, eax
0x18004ea99  jz      loc_18004EA07
0x18004ea9f  mov     al, [rbx]
0x18004eaa1  test    al, al
0x18004eaa3  jz      loc_18004EA07
0x18004eaa9  inc     rbx
0x18004eaac  jmp     short loc_18004EA5D
0x18004eaae  lea     rdx, [rsp+290h+SecurityAttributes]; lpSecurityAttributes
0x18004eab3  xor     ebx, ebx
0x18004eab5  lea     rcx, [rsp+290h+PathName]; lpPathName
0x18004eaba  call    cs:__imp_CreateDirectoryA
0x18004eac0  test    eax, eax
0x18004eac2  jnz     short loc_18004EAD6
0x18004eac4  call    cs:__imp_GetLastError
0x18004eaca  xor     ecx, ecx
0x18004eacc  mov     ebx, eax
0x18004eace  cmp     eax, 0B7h
0x18004ead3  cmovz   ebx, ecx
0x18004ead6  mov     eax, ebx
0x18004ead8  mov     rcx, [rbp+190h+var_30]
0x18004eadf  xor     rcx, rsp; StackCookie
0x18004eae2  call    __security_check_cookie
0x18004eae7  add     rsp, 278h
0x18004eaee  pop     rdi
0x18004eaef  pop     rsi
0x18004eaf0  pop     rbx
0x18004eaf1  pop     rbp
0x18004eaf2  retn
```
