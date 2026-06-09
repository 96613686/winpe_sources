# oCompareString(CSession *,ulong,ulong,ushort const *,int,ushort const *,int)

- ea: `0x180063b4c`
- end: `0x180063cea`
- name: `?oCompareString@@YAHPEAVCSession@@KKPEBGH1H@Z`
- size: `414`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, LCID Locale@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, int cchCount1, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180072010`

## callees

- `0x1800090b0`
- `0x180063b4c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180063cca`
- `KERNEL32!SetLastError` at `0x180063cca`
- `KERNEL32!CompareStringW` at `0x180063b98`
- `KERNEL32!CompareStringW` at `0x180063b98`
- `KERNEL32!CompareStringA` at `0x180063cb0`
- `KERNEL32!CompareStringA` at `0x180063cb0`
- `KERNEL32!WideCharToMultiByte` at `0x180063c4f`
- `KERNEL32!WideCharToMultiByte` at `0x180063c88`
- `KERNEL32!WideCharToMultiByte` at `0x180063c4f`
- `KERNEL32!WideCharToMultiByte` at `0x180063c88`

## pseudocode

```c
int __fastcall oCompareString(
        struct CSession *a1,
        LCID Locale,
        __int64 a3,
        const unsigned __int16 *a4,
        int cchCount1,
        const unsigned __int16 *lpWideCharStr,
        int cchWideChar)
{
  int v10; // ebx
  int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rbx
  struct VAR *v14; // rax
  CHAR *v15; // rsi
  int v16; // eax
  CHAR *lpString2; // rbx
  int v18; // ebp
  int cchCount2; // eax
  DWORD v20; // ecx

  if ( !g_fAnsiOs )
    return CompareStringW(Locale, 0, a4, cchCount1, lpWideCharStr, cchWideChar);
  v10 = cchCount1;
  if ( !cchCount1 || (v11 = cchWideChar) == 0 )
  {
    v20 = 87;
    goto LABEL_19;
  }
  v12 = -1;
  if ( cchCount1 == -1 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    v10 = v13 + 1;
  }
  if ( cchWideChar == -1 )
  {
    do
      ++v12;
    while ( lpWideCharStr[v12] );
    v11 = v12 + 1;
  }
  v14 = PvarAllocBstrByteLen(2 * v10 + 2 * v11, a1);
  if ( !v14 || (v15 = (CHAR *)*((_QWORD *)v14 + 1)) == 0 )
  {
    v20 = 14;
LABEL_19:
    SetLastError(v20);
    return 0;
  }
  v16 = WideCharToMultiByte(0, 0, a4, v10, v15, 2 * v10, 0, 0);
  lpString2 = &v15[2 * v10];
  v18 = v16;
  cchCount2 = WideCharToMultiByte(0, 0, lpWideCharStr, v11, lpString2, 2 * v11, 0, 0);
  if ( v18 && cchCount2 )
    return CompareStringA(Locale, 0, v15, v18, lpString2, cchCount2);
  return 0;
}

```

## disassembly

```asm
0x180063b4c  push    rbx
0x180063b4e  push    rbp
0x180063b4f  push    rsi
0x180063b50  push    rdi
0x180063b51  push    r12
0x180063b53  push    r13
0x180063b55  push    r14
0x180063b57  push    r15
0x180063b59  sub     rsp, 58h
0x180063b5d  xor     esi, esi
0x180063b5f  mov     r12d, edx
0x180063b62  cmp     cs:?g_fAnsiOs@@3HA, esi; int g_fAnsiOs
0x180063b68  mov     rbp, r9
0x180063b6b  mov     rdx, rcx; struct CSession *
0x180063b6e  jnz     short loc_180063BA9
0x180063b70  mov     eax, [rsp+98h+cchWideChar]
0x180063b77  mov     r8, rbp; lpString1
0x180063b7a  mov     r9d, [rsp+98h+cchCount1]; cchCount1
0x180063b82  xor     edx, edx; dwCmpFlags
0x180063b84  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180063b88  mov     ecx, r12d; Locale
0x180063b8b  mov     rax, [rsp+98h+lpWideCharStr]
0x180063b93  mov     [rsp+98h+lpString2], rax; lpString2
0x180063b98  call    cs:__imp_CompareStringW
0x180063b9f  nop     dword ptr [rax+rax+00h]
0x180063ba4  jmp     loc_180063CD8
0x180063ba9  mov     ebx, [rsp+98h+cchCount1]
0x180063bb0  test    ebx, ebx
0x180063bb2  jz      loc_180063CC5
0x180063bb8  mov     edi, [rsp+98h+cchWideChar]
0x180063bbf  test    edi, edi
0x180063bc1  jz      loc_180063CC5
0x180063bc7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063bcb  cmp     ebx, eax
0x180063bcd  jnz     short loc_180063BDE
0x180063bcf  mov     rbx, rax
0x180063bd2  inc     rbx
0x180063bd5  cmp     [r9+rbx*2], si
0x180063bda  jnz     short loc_180063BD2
0x180063bdc  inc     ebx
0x180063bde  mov     r15, [rsp+98h+lpWideCharStr]
0x180063be6  cmp     edi, eax
0x180063be8  jnz     short loc_180063BF7
0x180063bea  inc     rax
0x180063bed  cmp     [r15+rax*2], si
0x180063bf2  jnz     short loc_180063BEA
0x180063bf4  lea     edi, [rax+1]
0x180063bf7  lea     r14d, [rbx+rbx]
0x180063bfb  lea     r13d, [rdi+rdi]
0x180063bff  lea     ecx, [r14+r13]; len
0x180063c03  call    ?PvarAllocBstrByteLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrByteLen(long,CSession *)
0x180063c08  test    rax, rax
0x180063c0b  jz      loc_180063CBE
0x180063c11  mov     rsi, [rax+8]
0x180063c15  test    rsi, rsi
0x180063c18  jz      loc_180063CBE
0x180063c1e  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180063c27  mov     r9d, ebx; cchWideChar
0x180063c2a  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180063c33  mov     r8, rbp; lpWideCharStr
0x180063c36  movsxd  rax, r14d
0x180063c39  xor     edx, edx; dwFlags
0x180063c3b  add     rax, rsi
0x180063c3e  mov     [rsp+98h+cchCount2], r14d; cbMultiByte
0x180063c43  xor     ecx, ecx; CodePage
0x180063c45  mov     [rsp+98h+lpMultiByteStr], rax
0x180063c4a  mov     [rsp+98h+lpString2], rsi; lpMultiByteStr
0x180063c4f  call    cs:__imp_WideCharToMultiByte
0x180063c56  nop     dword ptr [rax+rax+00h]
0x180063c5b  mov     rbx, [rsp+98h+lpMultiByteStr]
0x180063c60  mov     r9d, edi; cchWideChar
0x180063c63  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180063c6c  mov     r8, r15; lpWideCharStr
0x180063c6f  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180063c78  xor     edx, edx; dwFlags
0x180063c7a  mov     [rsp+98h+cchCount2], r13d; cbMultiByte
0x180063c7f  xor     ecx, ecx; CodePage
0x180063c81  mov     [rsp+98h+lpString2], rbx; lpMultiByteStr
0x180063c86  mov     ebp, eax
0x180063c88  call    cs:__imp_WideCharToMultiByte
0x180063c8f  nop     dword ptr [rax+rax+00h]
0x180063c94  test    ebp, ebp
0x180063c96  jz      short loc_180063CD6
0x180063c98  test    eax, eax
0x180063c9a  jz      short loc_180063CD6
0x180063c9c  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180063ca0  mov     r9d, ebp; cchCount1
0x180063ca3  mov     r8, rsi; lpString1
0x180063ca6  mov     [rsp+98h+lpString2], rbx; lpString2
0x180063cab  xor     edx, edx; dwCmpFlags
0x180063cad  mov     ecx, r12d; Locale
0x180063cb0  call    cs:__imp_CompareStringA
0x180063cb7  nop     dword ptr [rax+rax+00h]
0x180063cbc  jmp     short loc_180063CD8
0x180063cbe  mov     ecx, 0Eh
0x180063cc3  jmp     short loc_180063CCA
0x180063cc5  mov     ecx, 57h ; 'W'; dwErrCode
0x180063cca  call    cs:__imp_SetLastError
0x180063cd1  nop     dword ptr [rax+rax+00h]
0x180063cd6  xor     eax, eax
0x180063cd8  add     rsp, 58h
0x180063cdc  pop     r15
0x180063cde  pop     r14
0x180063ce0  pop     r13
0x180063ce2  pop     r12
0x180063ce4  pop     rdi
0x180063ce5  pop     rsi
0x180063ce6  pop     rbp
0x180063ce7  pop     rbx
0x180063ce8  retn
```
