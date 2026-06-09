# SearchProtectPasswordCache

- ea: `0x1800052f0`
- end: `0x18000545c`
- name: `SearchProtectPasswordCache`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004350`

## callees

- `0x1800037f4`
- `0x18000383c`
- `0x180003884`
- `0x180004994`
- `0x1800051ec`
- `0x1800052f0`
- `0x18003e576`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000536d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000536d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000542f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000542f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005422`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005422`

## pseudocode

```c
__int64 __fastcall SearchProtectPasswordCache(unsigned int *a1, _OWORD *a2, int a3)
{
  __int64 result; // rax
  unsigned int v7; // edi
  HLOCAL *i; // rbx
  HLOCAL *v9; // rax
  HLOCAL **v10; // rcx
  __int64 v11; // rcx
  HLOCAL *v12; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+20h] [rbp-78h] BYREF
  HLOCAL v14; // [rsp+28h] [rbp-70h] BYREF
  _BYTE Buf1[64]; // [rsp+30h] [rbp-68h] BYREF

  phHash = 0;
  v14 = 0;
  result = GetEffectiveLogonId(&v14);
  if ( (_DWORD)result )
  {
    v7 = 0;
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, *((_QWORD *)a1 + 1), *a1);
    CngRsa32Compat_SHAFinal(&phHash, Buf1);
    EnterCriticalSection(&g_csProtectPasswordCache);
    for ( i = (HLOCAL *)g_ProtectPasswordCache; i != &g_ProtectPasswordCache; i = (HLOCAL *)*i )
    {
      if ( !memcmp_0(Buf1, i + 4, 0x40u) && v14 == i[2] )
      {
        v7 = 1;
        if ( a3 )
        {
          v9 = (HLOCAL *)*i;
          if ( *((HLOCAL **)*i + 1) != i || (v10 = (HLOCAL **)i[1], *v10 != i) )
            __fastfail(3u);
          *v10 = v9;
          v9[1] = v10;
          v11 = 160;
          v12 = i;
          do
          {
            *(_BYTE *)v12 = 0;
            v12 = (HLOCAL *)((char *)v12 + 1);
            --v11;
          }
          while ( v11 );
          LocalFree(i);
        }
        else
        {
          *a2 = *((_OWORD *)i + 6);
          a2[1] = *((_OWORD *)i + 7);
          a2[2] = *((_OWORD *)i + 8);
          a2[3] = *((_OWORD *)i + 9);
          GetSystemTimeAsFileTime((LPFILETIME)i + 3);
        }
        break;
      }
    }
    LeaveCriticalSection(&g_csProtectPasswordCache);
    PurgeProtectPasswordCache();
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800052f0  mov     r11, rsp
0x1800052f3  mov     [r11+18h], rbx
0x1800052f7  push    rbp
0x1800052f8  push    rsi
0x1800052f9  push    rdi
0x1800052fa  sub     rsp, 80h
0x180005301  mov     rax, cs:__security_cookie
0x180005308  xor     rax, rsp
0x18000530b  mov     [rsp+98h+var_28], rax
0x180005310  mov     rbx, rcx
0x180005313  mov     qword ptr [r11-78h], 0
0x18000531b  lea     rcx, [r11-70h]
0x18000531f  mov     qword ptr [r11-70h], 0
0x180005327  mov     ebp, r8d
0x18000532a  mov     rsi, rdx
0x18000532d  call    GetEffectiveLogonId
0x180005332  test    eax, eax
0x180005334  jz      loc_18000543C
0x18000533a  lea     rcx, [rsp+98h+phHash]; phHash
0x18000533f  xor     edi, edi
0x180005341  call    CngRsa32Compat_SHAInit
0x180005346  mov     r8d, [rbx]
0x180005349  lea     rcx, [rsp+98h+phHash]
0x18000534e  mov     rdx, [rbx+8]
0x180005352  call    CngRsa32Compat_SHAUpdate
0x180005357  lea     rdx, [rsp+98h+Buf1]
0x18000535c  lea     rcx, [rsp+98h+phHash]
0x180005361  call    CngRsa32Compat_SHAFinal
0x180005366  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x18000536d  call    cs:__imp_EnterCriticalSection
0x180005373  mov     rbx, cs:g_ProtectPasswordCache
0x18000537a  lea     rax, g_ProtectPasswordCache
0x180005381  cmp     rbx, rax
0x180005384  jz      loc_180005428
0x18000538a  lea     rdx, [rbx+20h]; Buf2
0x18000538e  mov     r8d, 40h ; '@'; Size
0x180005394  lea     rcx, [rsp+98h+Buf1]; Buf1
0x180005399  call    memcmp_0
0x18000539e  test    eax, eax
0x1800053a0  jnz     short loc_1800053AD
0x1800053a2  mov     rax, [rsp+98h+var_70]
0x1800053a7  cmp     rax, [rbx+10h]
0x1800053ab  jz      short loc_1800053B2
0x1800053ad  mov     rbx, [rbx]
0x1800053b0  jmp     short loc_18000537A
0x1800053b2  mov     edi, 1
0x1800053b7  test    ebp, ebp
0x1800053b9  jz      short loc_1800053F9
0x1800053bb  mov     rax, [rbx]
0x1800053be  cmp     [rax+8], rbx
0x1800053c2  jnz     short loc_1800053F2
0x1800053c4  mov     rcx, [rbx+8]
0x1800053c8  cmp     [rcx], rbx
0x1800053cb  jnz     short loc_1800053F2
0x1800053cd  mov     [rcx], rax
0x1800053d0  mov     [rax+8], rcx
0x1800053d4  mov     ecx, 0A0h
0x1800053d9  mov     rax, rbx
0x1800053dc  mov     byte ptr [rax], 0
0x1800053df  add     rax, rdi
0x1800053e2  sub     rcx, rdi
0x1800053e5  jnz     short loc_1800053DC
0x1800053e7  mov     rcx, rbx; hMem
0x1800053ea  call    cs:__imp_LocalFree
0x1800053f0  jmp     short loc_180005428
0x1800053f2  mov     ecx, 3
0x1800053f7  int     29h; Win8: RtlFailFast(ecx)
0x1800053f9  movups  xmm0, xmmword ptr [rbx+60h]
0x1800053fd  lea     rcx, [rbx+18h]; lpSystemTimeAsFileTime
0x180005401  movups  xmmword ptr [rsi], xmm0
0x180005404  movups  xmm1, xmmword ptr [rbx+70h]
0x180005408  movups  xmmword ptr [rsi+10h], xmm1
0x18000540c  movups  xmm0, xmmword ptr [rbx+80h]
0x180005413  movups  xmmword ptr [rsi+20h], xmm0
0x180005417  movups  xmm1, xmmword ptr [rbx+90h]
0x18000541e  movups  xmmword ptr [rsi+30h], xmm1
0x180005422  call    cs:__imp_GetSystemTimeAsFileTime
0x180005428  lea     rcx, g_csProtectPasswordCache; lpCriticalSection
0x18000542f  call    cs:__imp_LeaveCriticalSection
0x180005435  call    PurgeProtectPasswordCache
0x18000543a  mov     eax, edi
0x18000543c  mov     rcx, [rsp+98h+var_28]
0x180005441  xor     rcx, rsp; StackCookie
0x180005444  call    __security_check_cookie
0x180005449  mov     rbx, [rsp+98h+arg_10]
0x180005451  add     rsp, 80h
0x180005458  pop     rdi
0x180005459  pop     rsi
0x18000545a  pop     rbp
0x18000545b  retn
```
