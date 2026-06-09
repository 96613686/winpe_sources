# SQLGetPrivateProfileStringCover

- ea: `0x1800017c0`
- end: `0x180001bee`
- name: `SQLGetPrivateProfileStringCover`
- size: `1070`
- prototype: `unsigned __int64 __fastcall(const WCHAR *, const WCHAR *, void *, WCHAR *, int, wchar_t *String1)`
- caller_count: `17`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180001ca0`
- `0x180004e80`
- `0x180005530`
- `0x180005c00`
- `0x180006184`
- `0x180006afc`
- `0x180007200`
- `0x180007628`
- `0x180008dc0`
- `0x1800099a0`
- `0x180009e8c`
- `0x18000a66c`
- `0x18000aaf0`
- `0x18000c440`
- `0x18000d208`
- `0x18000dc70`
- `0x18000ef70`

## callees

- `0x180001010`
- `0x1800017c0`
- `0x180002e14`
- `0x180004bac`
- `0x1800074c4`
- `0x180014aa2`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_ltow_s` at `0x180001907`
- `msvcrt!_ltow_s` at `0x180001907`
- `msvcrt!_wcsicmp` at `0x180001888`
- `msvcrt!_wcsicmp` at `0x180001a8b`
- `msvcrt!_wcsicmp` at `0x180001888`
- `msvcrt!_wcsicmp` at `0x180001a8b`
- `msvcrt!calloc` at `0x1800019d9`
- `msvcrt!calloc` at `0x1800019d9`
- `msvcrt!free` at `0x180001a4c`
- `msvcrt!free` at `0x180001b29`
- `msvcrt!free` at `0x180001a4c`
- `msvcrt!free` at `0x180001b29`
- `KERNEL32!LeaveCriticalSection` at `0x180001869`
- `KERNEL32!LeaveCriticalSection` at `0x180001b5c`
- `KERNEL32!LeaveCriticalSection` at `0x180001869`
- `KERNEL32!LeaveCriticalSection` at `0x180001b5c`
- `KERNEL32!EnterCriticalSection` at `0x180001854`
- `KERNEL32!EnterCriticalSection` at `0x180001b45`
- `KERNEL32!EnterCriticalSection` at `0x180001854`
- `KERNEL32!EnterCriticalSection` at `0x180001b45`

## pseudocode

```c
unsigned __int64 __fastcall SQLGetPrivateProfileStringCover(
        const WCHAR *a1,
        const WCHAR *a2,
        void *a3,
        WCHAR *a4,
        int a5,
        wchar_t *String1)
{
  char v10; // r12
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rbx
  bool v14; // zf
  int v16; // r12d
  unsigned __int64 v17; // rbp
  int i; // r14d
  WCHAR *v19; // r15
  const wchar_t *v20; // rsi
  WCHAR *v21; // r13
  const wchar_t *j; // r14
  __int64 v23; // rax
  __int64 v24; // r14
  int v25; // r14d
  int v26; // edx
  __int64 v27; // rax
  unsigned __int64 PrivateProfileString; // r11
  int v29; // [rsp+38h] [rbp-D0h]
  DWORD v30; // [rsp+50h] [rbp-B8h] BYREF
  DWORD v31[3]; // [rsp+54h] [rbp-B4h] BYREF
  wchar_t Buffer[40]; // [rsp+60h] [rbp-A8h] BYREF

  v30 = 0;
  v31[0] = 0;
  if ( !a1 || !*a1 || !String1 || !*String1 || !a4 || a5 <= 0 )
    return 0;
  EnterCriticalSection(&g_csInstaller);
  v10 = g_wSystemDSN;
  LeaveCriticalSection(&g_csInstaller);
  if ( (v10 & 1) != 0 )
  {
    v11 = g_hkeyMachine;
LABEL_12:
    LODWORD(v12) = cpGetPrivateProfileString((HKEY)v11, a1, a2, a3, 0xFFFFu, &v30, a4, 2 * a5, (__int64)String1, 0);
    if ( v30 == 4 && (unsigned __int64)(2LL * a5) >= 4 )
    {
      _ltow_s(*(_DWORD *)a4, Buffer, 0x21u, 10);
      StringCchCopyW(a4, a5, Buffer);
      v13 = -1;
      do
        v14 = a4[++v13] == 0;
      while ( !v14 );
      LODWORD(v12) = 2 * v13;
    }
LABEL_17:
    v12 = (int)v12;
    return v12 >> 1;
  }
  if ( !_wcsicmp(String1, L"ODBCINST.INI") )
  {
    v11 = g_hkeyMachine;
    goto LABEL_12;
  }
  v11 = -2147483647;
  if ( (v10 & 2) != 0 )
    goto LABEL_12;
  v16 = 2 * a5;
  v29 = 2 * a5;
  if ( a2 )
  {
    LODWORD(v12) = cpGetPrivateProfileString(
                     HKEY_CURRENT_USER,
                     a1,
                     a2,
                     (void *)&SubKey,
                     0xFFFFu,
                     &v30,
                     a4,
                     v29,
                     (__int64)String1,
                     v31);
    if ( !v31[0] )
    {
      PrivateProfileString = (int)cpGetPrivateProfileString(
                                    (HKEY)g_hkeyMachine,
                                    a1,
                                    a2,
                                    a3,
                                    0xFFFFu,
                                    &v30,
                                    a4,
                                    2 * a5,
                                    (__int64)String1,
                                    v31);
      if ( !v31[0] )
      {
        if ( a3 )
          StringCchCopyW(a4, a5, (STRSAFE_LPCWSTR)a3);
        else
          *a4 = 0;
      }
      v12 = PrivateProfileString;
      return v12 >> 1;
    }
    goto LABEL_17;
  }
  LODWORD(v12) = cpGetPrivateProfileString(
                   HKEY_CURRENT_USER,
                   a1,
                   0,
                   (void *)&SubKey,
                   0xFFFFu,
                   &v30,
                   a4,
                   v29,
                   (__int64)String1,
                   v31);
  v17 = (int)v12;
  if ( (int)v12 + 2 >= (unsigned __int64)(2LL * a5) )
  {
    v12 = (int)v12;
    return v12 >> 1;
  }
  for ( i = 4096; ; i += 4096 )
  {
    v19 = (WCHAR *)calloc(2LL * i, 1u);
    if ( !v19 )
    {
      MemError();
      EnterCriticalSection(&g_csInstaller);
      PostInstError(21);
      LeaveCriticalSection(&g_csInstaller);
      return (unsigned int)v17;
    }
    if ( (int)((unsigned __int64)(int)cpGetPrivateProfileString(
                                        (HKEY)g_hkeyMachine,
                                        a1,
                                        0,
                                        (void *)&SubKey,
                                        0xFFFFu,
                                        &v30,
                                        v19,
                                        2 * i,
                                        (__int64)String1,
                                        v31) >> 1) < i - 3
      || i >= 61440 )
    {
      break;
    }
    free(v19);
  }
  v20 = v19;
  v21 = &a4[v17 >> 1];
  if ( *v19 )
  {
    while ( 2 )
    {
      for ( j = a4; j < v21; j += v23 + 1 )
      {
        if ( !_wcsicmp(j, v20) )
          goto LABEL_41;
        v23 = -1;
        do
          v14 = j[++v23] == 0;
        while ( !v14 );
      }
      v24 = -1;
      do
        ++v24;
      while ( v20[v24] );
      v25 = 2 * v24;
      if ( v25 >= v16 - (int)v17 - 4 )
        v25 = v16 - v17 - 4;
      if ( v25 <= 0 )
        break;
      memcpy_0((char *)a4 + (unsigned int)v17, v20, v25);
      v26 = v25 + v17;
      LODWORD(v17) = v25 + v17 + 2;
      *(WCHAR *)((char *)a4 + (v26 & 0xFFFFFFFE)) = 0;
LABEL_41:
      v27 = -1;
      do
        v14 = v20[++v27] == 0;
      while ( !v14 );
      v20 += v27 + 1;
      if ( *v20 )
        continue;
      break;
    }
  }
  *(WCHAR *)((char *)a4 + ((unsigned int)v17 & 0xFFFFFFFE)) = 0;
  free(v19);
  return (unsigned int)v17 >> 1;
}

```

## disassembly

```asm
0x1800017c0  push    rbx
0x1800017c2  push    rbp
0x1800017c3  push    rsi
0x1800017c4  push    rdi
0x1800017c5  push    r13
0x1800017c7  push    r14
0x1800017c9  push    r15
0x1800017cb  sub     rsp, 0D0h
0x1800017d2  mov     rax, cs:__security_cookie
0x1800017d9  xor     rax, rsp
0x1800017dc  mov     [rsp+108h+var_58], rax
0x1800017e4  mov     rsi, [rsp+108h+String1]
0x1800017ec  xor     r13d, r13d
0x1800017ef  mov     [rsp+108h+var_B8], r13d
0x1800017f4  mov     rdi, r9
0x1800017f7  mov     [rsp+108h+var_B4], r13d
0x1800017fc  mov     rbp, r8
0x1800017ff  mov     r14, rdx
0x180001802  mov     rbx, rcx
0x180001805  test    rcx, rcx
0x180001808  jz      loc_180001BE7
0x18000180e  cmp     [rcx], r13w
0x180001812  jz      loc_180001BE7
0x180001818  test    rsi, rsi
0x18000181b  jz      loc_180001BE7
0x180001821  cmp     [rsi], r13w
0x180001825  jz      loc_180001BE7
0x18000182b  test    r9, r9
0x18000182e  jz      loc_180001BE7
0x180001834  movsxd  r15, [rsp+108h+arg_20]
0x18000183c  test    r15d, r15d
0x18000183f  jle     loc_180001BE7
0x180001845  lea     rcx, g_csInstaller; lpCriticalSection
0x18000184c  mov     [rsp+108h+var_40], r12
0x180001854  call    cs:__imp_EnterCriticalSection
0x18000185a  movzx   r12d, cs:g_wSystemDSN
0x180001862  lea     rcx, g_csInstaller; lpCriticalSection
0x180001869  call    cs:__imp_LeaveCriticalSection
0x18000186f  test    r12b, 1
0x180001873  jz      short loc_18000187E
0x180001875  mov     rcx, cs:g_hkeyMachine
0x18000187c  jmp     short loc_1800018AC
0x18000187e  lea     rdx, aOdbcinstIni; "ODBCINST.INI"
0x180001885  mov     rcx, rsi; String1
0x180001888  call    cs:__imp__wcsicmp
0x18000188e  test    eax, eax
0x180001890  jnz     short loc_18000189B
0x180001892  mov     rcx, cs:g_hkeyMachine
0x180001899  jmp     short loc_1800018AC
0x18000189b  mov     rcx, 0FFFFFFFF80000001h
0x1800018a2  test    r12b, 2
0x1800018a6  jz      loc_180001962
0x1800018ac  mov     [rsp+108h+var_C0], r13
0x1800018b1  lea     eax, [r15+r15]
0x1800018b5  mov     [rsp+108h+var_C8], rsi
0x1800018ba  mov     r9, rbp
0x1800018bd  mov     [rsp+108h+var_D0], eax
0x1800018c1  mov     r8, r14
0x1800018c4  lea     rax, [rsp+108h+var_B8]
0x1800018c9  mov     [rsp+108h+var_D8], rdi
0x1800018ce  mov     [rsp+108h+var_E0], rax
0x1800018d3  mov     rdx, rbx
0x1800018d6  mov     [rsp+108h+var_E8], 0FFFFh
0x1800018de  call    cpGetPrivateProfileString
0x1800018e3  cmp     [rsp+108h+var_B8], 4
0x1800018e8  jnz     short loc_180001933
0x1800018ea  lea     rcx, [r15+r15]
0x1800018ee  cmp     rcx, 4
0x1800018f2  jb      short loc_180001933
0x1800018f4  mov     ecx, [rdi]; Value
0x1800018f6  lea     rdx, [rsp+108h+Buffer]; Buffer
0x1800018fb  mov     r9d, 0Ah; Radix
0x180001901  mov     r8d, 21h ; '!'; BufferCount
0x180001907  call    cs:__imp__ltow_s
0x18000190d  lea     r8, [rsp+108h+Buffer]; pszSrc
0x180001912  mov     rdx, r15; cchDest
0x180001915  mov     rcx, rdi; pszDest
0x180001918  call    StringCchCopyW
0x18000191d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001924  cmp     [rdi+rbx*2+2], r13w
0x18000192a  lea     rbx, [rbx+1]
0x18000192e  jnz     short loc_180001924
0x180001930  lea     eax, [rbx+rbx]
0x180001933  cdqe
0x180001935  shr     rax, 1
0x180001938  mov     r12, [rsp+108h+var_40]
0x180001940  mov     rcx, [rsp+108h+var_58]
0x180001948  xor     rcx, rsp; StackCookie
0x18000194b  call    __security_check_cookie
0x180001950  add     rsp, 0D0h
0x180001957  pop     r15
0x180001959  pop     r14
0x18000195b  pop     r13
0x18000195d  pop     rdi
0x18000195e  pop     rsi
0x18000195f  pop     rbp
0x180001960  pop     rbx
0x180001961  retn
0x180001962  lea     rax, [rsp+108h+var_B4]
0x180001967  mov     rdx, rbx
0x18000196a  mov     [rsp+108h+var_C0], rax
0x18000196f  lea     r12d, [r15+r15]
0x180001973  mov     [rsp+108h+var_C8], rsi
0x180001978  lea     rax, [rsp+108h+var_B8]
0x18000197d  mov     [rsp+108h+var_D0], r12d
0x180001982  lea     r9, SubKey
0x180001989  mov     [rsp+108h+var_D8], rdi
0x18000198e  mov     [rsp+108h+var_E0], rax
0x180001993  mov     [rsp+108h+var_E8], 0FFFFh
0x18000199b  test    r14, r14
0x18000199e  jnz     loc_180001B69
0x1800019a4  xor     r8d, r8d
0x1800019a7  call    cpGetPrivateProfileString
0x1800019ac  movsxd  rbp, eax
0x1800019af  lea     ecx, [rbp+2]
0x1800019b2  movsxd  rdx, ecx
0x1800019b5  mov     rcx, r15
0x1800019b8  add     rcx, rcx
0x1800019bb  cmp     rdx, rcx
0x1800019be  jb      short loc_1800019C8
0x1800019c0  mov     rax, rbp
0x1800019c3  jmp     loc_180001935
0x1800019c8  mov     r14d, 1000h
0x1800019ce  movsxd  rcx, r14d
0x1800019d1  mov     edx, 1; Size
0x1800019d6  add     rcx, rcx; Count
0x1800019d9  call    cs:__imp_calloc
0x1800019df  mov     r15, rax
0x1800019e2  test    rax, rax
0x1800019e5  jz      loc_180001B39
0x1800019eb  lea     rax, [rsp+108h+var_B4]
0x1800019f0  xor     r8d, r8d
0x1800019f3  mov     [rsp+108h+var_C0], rax
0x1800019f8  lea     ecx, [r14+r14]
0x1800019fc  mov     [rsp+108h+var_C8], rsi
0x180001a01  lea     rax, [rsp+108h+var_B8]
0x180001a06  mov     [rsp+108h+var_D0], ecx
0x180001a0a  lea     r9, SubKey
0x180001a11  mov     rcx, cs:g_hkeyMachine
0x180001a18  mov     rdx, rbx
0x180001a1b  mov     [rsp+108h+var_D8], r15
0x180001a20  mov     [rsp+108h+var_E0], rax
0x180001a25  mov     [rsp+108h+var_E8], 0FFFFh
0x180001a2d  call    cpGetPrivateProfileString
0x180001a32  movsxd  rcx, eax
0x180001a35  lea     eax, [r14-3]
0x180001a39  shr     rcx, 1
0x180001a3c  cmp     ecx, eax
0x180001a3e  jl      short loc_180001A5E
0x180001a40  cmp     r14d, 0F000h
0x180001a47  jge     short loc_180001A5E
0x180001a49  mov     rcx, r15; Block
0x180001a4c  call    cs:__imp_free
0x180001a52  add     r14d, 1000h
0x180001a59  jmp     loc_1800019CE
0x180001a5e  mov     rax, rbp
0x180001a61  mov     rsi, r15
0x180001a64  shr     rax, 1
0x180001a67  cmp     word ptr [r15], 0
0x180001a6c  lea     r13, [rdi+rax*2]
0x180001a70  jz      loc_180001B18
0x180001a76  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001a7d  mov     r14, rdi
0x180001a80  cmp     r14, r13
0x180001a83  jnb     short loc_180001AAF
0x180001a85  mov     rdx, rsi; String2
0x180001a88  mov     rcx, r14; String1
0x180001a8b  call    cs:__imp__wcsicmp
0x180001a91  test    eax, eax
0x180001a93  jz      short loc_180001AF7
0x180001a95  mov     rax, rbx
0x180001a98  cmp     word ptr [r14+rax*2+2], 0
0x180001a9f  lea     rax, [rax+1]
0x180001aa3  jnz     short loc_180001A98
0x180001aa5  lea     r14, [r14+rax*2]
0x180001aa9  add     r14, 2
0x180001aad  jmp     short loc_180001A80
0x180001aaf  mov     eax, r12d
0x180001ab2  mov     r14, rbx
0x180001ab5  sub     eax, ebp
0x180001ab7  add     eax, 0FFFFFFFCh
0x180001aba  inc     r14
0x180001abd  cmp     word ptr [rsi+r14*2], 0
0x180001ac3  jnz     short loc_180001ABA
0x180001ac5  add     r14d, r14d
0x180001ac8  cmp     r14d, eax
0x180001acb  cmovge  r14d, eax
0x180001acf  test    r14d, r14d
0x180001ad2  jle     short loc_180001B18
0x180001ad4  mov     ecx, ebp
0x180001ad6  mov     rdx, rsi; Src
0x180001ad9  add     rcx, rdi; void *
0x180001adc  movsxd  r8, r14d; Size
0x180001adf  call    memcpy_0
0x180001ae4  lea     edx, [r14+rbp]
0x180001ae8  mov     ecx, edx
0x180001aea  lea     ebp, [rdx+2]
0x180001aed  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180001af1  xor     eax, eax
0x180001af3  mov     [rcx+rdi], ax
0x180001af7  mov     rax, rbx
0x180001afa  cmp     word ptr [rsi+rax*2+2], 0
0x180001b00  lea     rax, [rax+1]
0x180001b04  jnz     short loc_180001AFA
0x180001b06  lea     rsi, [rsi+rax*2]
0x180001b0a  add     rsi, 2
0x180001b0e  cmp     word ptr [rsi], 0
0x180001b12  jnz     loc_180001A7D
0x180001b18  xor     ecx, ecx
0x180001b1a  mov     edx, ebp
0x180001b1c  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180001b20  mov     ebx, ebp
0x180001b22  mov     [rdx+rdi], cx
0x180001b26  mov     rcx, r15; Block
0x180001b29  call    cs:__imp_free
0x180001b2f  shr     rbx, 1
0x180001b32  mov     eax, ebx
0x180001b34  jmp     loc_180001938
0x180001b39  call    MemError
0x180001b3e  lea     rcx, g_csInstaller; lpCriticalSection
0x180001b45  call    cs:__imp_EnterCriticalSection
0x180001b4b  mov     ecx, 15h
0x180001b50  call    PostInstError
0x180001b55  lea     rcx, g_csInstaller; lpCriticalSection
0x180001b5c  call    cs:__imp_LeaveCriticalSection
0x180001b62  mov     eax, ebp
0x180001b64  jmp     loc_180001938
0x180001b69  mov     r8, r14
0x180001b6c  call    cpGetPrivateProfileString
0x180001b71  cmp     [rsp+108h+var_B4], r13d
0x180001b76  jnz     loc_180001933
0x180001b7c  mov     rcx, cs:g_hkeyMachine
0x180001b83  lea     rax, [rsp+108h+var_B4]
0x180001b88  mov     [rsp+108h+var_C0], rax
0x180001b8d  mov     r9, rbp
0x180001b90  mov     [rsp+108h+var_C8], rsi
0x180001b95  lea     rax, [rsp+108h+var_B8]
0x180001b9a  mov     [rsp+108h+var_D0], r12d
0x180001b9f  mov     r8, r14
0x180001ba2  mov     [rsp+108h+var_D8], rdi
0x180001ba7  mov     rdx, rbx
0x180001baa  mov     [rsp+108h+var_E0], rax
0x180001baf  mov     [rsp+108h+var_E8], 0FFFFh
0x180001bb7  call    cpGetPrivateProfileString
0x180001bbc  movsxd  r11, eax
0x180001bbf  cmp     [rsp+108h+var_B4], r13d
0x180001bc4  jnz     short loc_180001BDF
0x180001bc6  test    rbp, rbp
0x180001bc9  jz      short loc_180001BDB
0x180001bcb  mov     rdx, r15; cchDest
0x180001bce  mov     r8, rbp; pszSrc
0x180001bd1  mov     rcx, rdi; pszDest
0x180001bd4  call    StringCchCopyW
0x180001bd9  jmp     short loc_180001BDF
0x180001bdb  mov     [rdi], r13w
0x180001bdf  mov     rax, r11
0x180001be2  jmp     loc_180001935
0x180001be7  xor     eax, eax
0x180001be9  jmp     loc_180001940
```
