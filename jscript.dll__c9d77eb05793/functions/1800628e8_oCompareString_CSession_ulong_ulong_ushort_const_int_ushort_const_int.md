# oCompareString(CSession *,ulong,ulong,ushort const *,int,ushort const *,int)

- ea: `0x1800628e8`
- end: `0x180062a67`
- name: `?oCompareString@@YAHPEAVCSession@@KKPEBGH1H@Z`
- size: `383`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, LCID Locale@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, int cchCount1, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180070c00`

## callees

- `0x18000bf44`
- `0x1800628e8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180062a4e`
- `KERNEL32!SetLastError` at `0x180062a4e`
- `KERNEL32!CompareStringW` at `0x180062934`
- `KERNEL32!CompareStringW` at `0x180062934`
- `KERNEL32!CompareStringA` at `0x180062a3a`
- `KERNEL32!CompareStringA` at `0x180062a3a`
- `KERNEL32!WideCharToMultiByte` at `0x1800629e5`
- `KERNEL32!WideCharToMultiByte` at `0x180062a18`
- `KERNEL32!WideCharToMultiByte` at `0x1800629e5`
- `KERNEL32!WideCharToMultiByte` at `0x180062a18`

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
0x1800628e8  push    rbx
0x1800628ea  push    rbp
0x1800628eb  push    rsi
0x1800628ec  push    rdi
0x1800628ed  push    r12
0x1800628ef  push    r13
0x1800628f1  push    r14
0x1800628f3  push    r15
0x1800628f5  sub     rsp, 58h
0x1800628f9  xor     esi, esi
0x1800628fb  mov     r12d, edx
0x1800628fe  cmp     cs:?g_fAnsiOs@@3HA, esi; int g_fAnsiOs
0x180062904  mov     rbp, r9
0x180062907  mov     rdx, rcx; struct CSession *
0x18006290a  jnz     short loc_18006293F
0x18006290c  mov     eax, [rsp+98h+cchWideChar]
0x180062913  mov     r8, rbp; lpString1
0x180062916  mov     r9d, [rsp+98h+cchCount1]; cchCount1
0x18006291e  xor     edx, edx; dwCmpFlags
0x180062920  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180062924  mov     ecx, r12d; Locale
0x180062927  mov     rax, [rsp+98h+lpWideCharStr]
0x18006292f  mov     [rsp+98h+lpString2], rax; lpString2
0x180062934  call    cs:__imp_CompareStringW
0x18006293a  jmp     loc_180062A56
0x18006293f  mov     ebx, [rsp+98h+cchCount1]
0x180062946  test    ebx, ebx
0x180062948  jz      loc_180062A49
0x18006294e  mov     edi, [rsp+98h+cchWideChar]
0x180062955  test    edi, edi
0x180062957  jz      loc_180062A49
0x18006295d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180062961  cmp     ebx, eax
0x180062963  jnz     short loc_180062974
0x180062965  mov     rbx, rax
0x180062968  inc     rbx
0x18006296b  cmp     [r9+rbx*2], si
0x180062970  jnz     short loc_180062968
0x180062972  inc     ebx
0x180062974  mov     r15, [rsp+98h+lpWideCharStr]
0x18006297c  cmp     edi, eax
0x18006297e  jnz     short loc_18006298D
0x180062980  inc     rax
0x180062983  cmp     [r15+rax*2], si
0x180062988  jnz     short loc_180062980
0x18006298a  lea     edi, [rax+1]
0x18006298d  lea     r14d, [rbx+rbx]
0x180062991  lea     r13d, [rdi+rdi]
0x180062995  lea     ecx, [r14+r13]; len
0x180062999  call    ?PvarAllocBstrByteLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrByteLen(long,CSession *)
0x18006299e  test    rax, rax
0x1800629a1  jz      loc_180062A42
0x1800629a7  mov     rsi, [rax+8]
0x1800629ab  test    rsi, rsi
0x1800629ae  jz      loc_180062A42
0x1800629b4  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800629bd  mov     r9d, ebx; cchWideChar
0x1800629c0  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x1800629c9  mov     r8, rbp; lpWideCharStr
0x1800629cc  movsxd  rax, r14d
0x1800629cf  xor     edx, edx; dwFlags
0x1800629d1  add     rax, rsi
0x1800629d4  mov     [rsp+98h+cchCount2], r14d; cbMultiByte
0x1800629d9  xor     ecx, ecx; CodePage
0x1800629db  mov     [rsp+98h+lpMultiByteStr], rax
0x1800629e0  mov     [rsp+98h+lpString2], rsi; lpMultiByteStr
0x1800629e5  call    cs:__imp_WideCharToMultiByte
0x1800629eb  mov     rbx, [rsp+98h+lpMultiByteStr]
0x1800629f0  mov     r9d, edi; cchWideChar
0x1800629f3  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800629fc  mov     r8, r15; lpWideCharStr
0x1800629ff  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180062a08  xor     edx, edx; dwFlags
0x180062a0a  mov     [rsp+98h+cchCount2], r13d; cbMultiByte
0x180062a0f  xor     ecx, ecx; CodePage
0x180062a11  mov     [rsp+98h+lpString2], rbx; lpMultiByteStr
0x180062a16  mov     ebp, eax
0x180062a18  call    cs:__imp_WideCharToMultiByte
0x180062a1e  test    ebp, ebp
0x180062a20  jz      short loc_180062A54
0x180062a22  test    eax, eax
0x180062a24  jz      short loc_180062A54
0x180062a26  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180062a2a  mov     r9d, ebp; cchCount1
0x180062a2d  mov     r8, rsi; lpString1
0x180062a30  mov     [rsp+98h+lpString2], rbx; lpString2
0x180062a35  xor     edx, edx; dwCmpFlags
0x180062a37  mov     ecx, r12d; Locale
0x180062a3a  call    cs:__imp_CompareStringA
0x180062a40  jmp     short loc_180062A56
0x180062a42  mov     ecx, 0Eh
0x180062a47  jmp     short loc_180062A4E
0x180062a49  mov     ecx, 57h ; 'W'; dwErrCode
0x180062a4e  call    cs:__imp_SetLastError
0x180062a54  xor     eax, eax
0x180062a56  add     rsp, 58h
0x180062a5a  pop     r15
0x180062a5c  pop     r14
0x180062a5e  pop     r13
0x180062a60  pop     r12
0x180062a62  pop     rdi
0x180062a63  pop     rsi
0x180062a64  pop     rbp
0x180062a65  pop     rbx
0x180062a66  retn
```
