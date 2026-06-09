# GetDomainNameFromTextualSid(ushort *,ushort *,ulong)

- ea: `0x18003f378`
- end: `0x18003f5ff`
- name: `?GetDomainNameFromTextualSid@@YAJPEAG0K@Z`
- size: `647`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f608`

## callees

- `0x180008fbc`
- `0x180012f50`
- `0x18003f378`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3cf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003f5a0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003f5a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003f3c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003f3c2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003f4fd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003f4fd`

## pseudocode

```c
__int64 __fastcall GetDomainNameFromTextualSid(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rdi
  unsigned __int16 *v4; // rbx
  DWORD *p_cchName; // rsi
  signed int LastError; // eax
  signed int v7; // ebx
  void *v8; // rsp
  DWORD *v9; // rax
  void *v10; // rsp
  unsigned __int16 *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  __int64 v16; // [rsp-20h] [rbp-840h] BYREF
  int v17; // [rsp+10h] [rbp-810h]
  _BYTE v18[2008]; // [rsp+18h] [rbp-808h] BYREF
  int v19; // [rsp+7F0h] [rbp-30h] BYREF
  DWORD cchReferencedDomainName; // [rsp+820h] [rbp+0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+824h] [rbp+4h] BYREF
  DWORD cchName; // [rsp+828h] [rbp+8h] BYREF
  PSID Sid; // [rsp+830h] [rbp+10h] BYREF

  peUse = 0;
  cchName = 1024;
  v3 = 0;
  cchReferencedDomainName = 1024;
  Sid = 0;
  v4 = a1;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x800
      || (unsigned __int64)(g_ulAdditionalProbeSize + 2056) < 0x800
      || !(unsigned int)VerifyStackAvailable()
      || (v8 = alloca(2064), &v19 == (int *)-48LL)
      || (cchReferencedDomainName = 1801679955, (p_cchName = &cchName) == 0) )
    {
      v9 = (DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(2056);
      p_cchName = v9;
      if ( v9 )
      {
        *v9 = 1885431112;
        p_cchName = v9 + 2;
      }
    }
    if ( !p_cchName )
      goto LABEL_12;
    if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x800
      || (unsigned __int64)(g_ulAdditionalProbeSize + 2056) < 0x800
      || !(unsigned int)VerifyStackAvailable()
      || (v10 = alloca(2064), &v16 == (__int64 *)-48LL)
      || (v17 = 1801679955, (v3 = (unsigned __int16 *)v18) == 0) )
    {
      v11 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(2056);
      v3 = v11;
      if ( v11 )
      {
        *(_DWORD *)v11 = 1885431112;
        v3 = v11 + 4;
      }
    }
    if ( v3 )
    {
      if ( LookupAccountSidLocalW(Sid, (LPWSTR)p_cchName, &cchName, v3, &cchReferencedDomainName, &peUse) )
      {
        *a2 = 0;
        if ( !cchReferencedDomainName
          || (v7 = StringCbCatW(a2, 0x400u, v3), v7 >= 0) && (v7 = StringCbCatW(a2, 0x400u, L"\\"), v7 >= 0) )
        {
          v7 = StringCbCatW(a2, 0x400u, (const unsigned __int16 *)p_cchName);
        }
      }
      else
      {
        v12 = 2147483646;
        v13 = 512;
        do
        {
          if ( !v12 )
            break;
          if ( !*v4 )
            break;
          *a2++ = *v4++;
          --v12;
          --v13;
        }
        while ( v13 );
        v14 = a2 - 1;
        if ( v13 )
          v14 = a2;
        v7 = v13 == 0 ? 0x8007007A : 0;
        *v14 = 0;
      }
    }
    else
    {
LABEL_12:
      v7 = -2147024882;
    }
  }
  else
  {
    p_cchName = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Sid )
    FreeSid(Sid);
  if ( v3 && *((_DWORD *)v3 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( p_cchName && *(p_cchName - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003f378  push    rbp
0x18003f37a  push    rbx
0x18003f37b  push    rsi
0x18003f37c  push    rdi
0x18003f37d  push    r12
0x18003f37f  push    r13
0x18003f381  push    r14
0x18003f383  push    r15
0x18003f385  sub     rsp, 58h
0x18003f389  lea     rbp, [rsp+30h]
0x18003f38e  mov     rax, cs:__security_cookie
0x18003f395  xor     rax, rbp
0x18003f398  mov     [rbp+60h+var_48], rax
0x18003f39c  xor     r15d, r15d
0x18003f39f  mov     r14, rdx
0x18003f3a2  mov     r13d, 400h
0x18003f3a8  mov     [rbp+60h+var_5C], r15d
0x18003f3ac  lea     rdx, [rbp+60h+Sid]; Sid
0x18003f3b0  mov     [rbp+60h+cchName], r13d
0x18003f3b4  mov     edi, r15d
0x18003f3b7  mov     [rbp+60h+var_60], r13d
0x18003f3bb  mov     [rbp+60h+Sid], r15
0x18003f3bf  mov     rbx, rcx
0x18003f3c2  call    cs:__imp_ConvertStringSidToSidW
0x18003f3c8  test    eax, eax
0x18003f3ca  jnz     short loc_18003F3ED
0x18003f3cc  mov     esi, r15d
0x18003f3cf  call    cs:__imp_GetLastError
0x18003f3d5  mov     ebx, eax
0x18003f3d7  test    eax, eax
0x18003f3d9  jle     loc_18003F597
0x18003f3df  movzx   ebx, ax
0x18003f3e2  or      ebx, 80070000h
0x18003f3e8  jmp     loc_18003F597
0x18003f3ed  mov     r12d, 800h
0x18003f3f3  cmp     cs:g_ulMaxStackAllocSize, r12
0x18003f3fa  jb      short loc_18003F43B
0x18003f3fc  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003f403  add     rcx, 808h
0x18003f40a  cmp     rcx, r12
0x18003f40d  jb      short loc_18003F43B
0x18003f40f  call    VerifyStackAvailable
0x18003f414  test    eax, eax
0x18003f416  jz      short loc_18003F43B
0x18003f418  mov     eax, [rsp+90h+var_90]
0x18003f41b  lea     eax, [r12+10h]
0x18003f420  sub     rsp, rax
0x18003f423  lea     rsi, [rsp+90h+var_60]
0x18003f428  mov     eax, [rsi]
0x18003f42a  test    rsi, rsi
0x18003f42d  jz      short loc_18003F43B
0x18003f42f  mov     dword ptr [rsi], 6B637453h
0x18003f435  add     rsi, 8
0x18003f439  jnz     short loc_18003F45E
0x18003f43b  mov     rax, cs:g_pfnAllocate
0x18003f442  mov     ecx, 808h
0x18003f447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f44c  mov     rsi, rax
0x18003f44f  test    rax, rax
0x18003f452  jz      short loc_18003F45E
0x18003f454  mov     dword ptr [rax], 70616548h
0x18003f45a  add     rsi, 8
0x18003f45e  test    rsi, rsi
0x18003f461  jnz     short loc_18003F46D
0x18003f463  mov     ebx, 8007000Eh
0x18003f468  jmp     loc_18003F597
0x18003f46d  cmp     cs:g_ulMaxStackAllocSize, r12
0x18003f474  jb      short loc_18003F4B5
0x18003f476  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003f47d  add     rcx, 808h
0x18003f484  cmp     rcx, r12
0x18003f487  jb      short loc_18003F4B5
0x18003f489  call    VerifyStackAvailable
0x18003f48e  test    eax, eax
0x18003f490  jz      short loc_18003F4B5
0x18003f492  mov     eax, [rsp+90h+var_90]
0x18003f495  mov     eax, 810h
0x18003f49a  sub     rsp, rax
0x18003f49d  lea     rdi, [rsp+8A0h+var_870]
0x18003f4a2  mov     eax, [rdi]
0x18003f4a4  test    rdi, rdi
0x18003f4a7  jz      short loc_18003F4B5
0x18003f4a9  mov     dword ptr [rdi], 6B637453h
0x18003f4af  add     rdi, 8
0x18003f4b3  jnz     short loc_18003F4D8
0x18003f4b5  mov     rax, cs:g_pfnAllocate
0x18003f4bc  mov     ecx, 808h
0x18003f4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4c6  mov     rdi, rax
0x18003f4c9  test    rax, rax
0x18003f4cc  jz      short loc_18003F4D8
0x18003f4ce  mov     dword ptr [rax], 70616548h
0x18003f4d4  add     rdi, 8
0x18003f4d8  test    rdi, rdi
0x18003f4db  jz      short loc_18003F463
0x18003f4dd  mov     rcx, [rbp+60h+Sid]; Sid
0x18003f4e1  lea     rax, [rbp+60h+var_5C]
0x18003f4e5  mov     [rsp+8A0h+peUse], rax; peUse
0x18003f4ea  lea     r8, [rbp+60h+cchName]; cchName
0x18003f4ee  lea     rax, [rbp+60h+var_60]
0x18003f4f2  mov     r9, rdi; ReferencedDomainName
0x18003f4f5  mov     rdx, rsi; Name
0x18003f4f8  mov     [rsp+8A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003f4fd  call    cs:__imp_LookupAccountSidLocalW
0x18003f503  test    eax, eax
0x18003f505  jnz     short loc_18003F551
0x18003f507  mov     eax, 7FFFFFFEh
0x18003f50c  mov     edx, 200h
0x18003f511  test    rax, rax
0x18003f514  jz      short loc_18003F533
0x18003f516  movzx   ecx, word ptr [rbx]
0x18003f519  test    cx, cx
0x18003f51c  jz      short loc_18003F533
0x18003f51e  mov     [r14], cx
0x18003f522  add     rbx, 2
0x18003f526  add     r14, 2
0x18003f52a  dec     rax
0x18003f52d  sub     rdx, 1
0x18003f531  jnz     short loc_18003F511
0x18003f533  test    rdx, rdx
0x18003f536  lea     rcx, [r14-2]
0x18003f53a  cmovnz  rcx, r14
0x18003f53e  neg     rdx
0x18003f541  sbb     ebx, ebx
0x18003f543  not     ebx
0x18003f545  and     ebx, 8007007Ah
0x18003f54b  mov     [rcx], r15w
0x18003f54f  jmp     short loc_18003F597
0x18003f551  mov     [r14], r15w
0x18003f555  cmp     [rbp+60h+var_60], r15d
0x18003f559  jbe     short loc_18003F587
0x18003f55b  mov     r8, rdi; unsigned __int16 *
0x18003f55e  mov     rdx, r13; unsigned __int64
0x18003f561  mov     rcx, r14; unsigned __int16 *
0x18003f564  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18003f569  mov     ebx, eax
0x18003f56b  test    eax, eax
0x18003f56d  js      short loc_18003F597
0x18003f56f  lea     r8, asc_180054FD0; "\\"
0x18003f576  mov     rdx, r13; unsigned __int64
0x18003f579  mov     rcx, r14; unsigned __int16 *
0x18003f57c  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18003f581  mov     ebx, eax
0x18003f583  test    eax, eax
0x18003f585  js      short loc_18003F597
0x18003f587  mov     r8, rsi; unsigned __int16 *
0x18003f58a  mov     rdx, r13; unsigned __int64
0x18003f58d  mov     rcx, r14; unsigned __int16 *
0x18003f590  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18003f595  mov     ebx, eax
0x18003f597  mov     rcx, [rbp+60h+Sid]; pSid
0x18003f59b  test    rcx, rcx
0x18003f59e  jz      short loc_18003F5A6
0x18003f5a0  call    cs:__imp_FreeSid
0x18003f5a6  test    rdi, rdi
0x18003f5a9  jz      short loc_18003F5C3
0x18003f5ab  lea     rcx, [rdi-8]
0x18003f5af  cmp     dword ptr [rcx], 70616548h
0x18003f5b5  jnz     short loc_18003F5C3
0x18003f5b7  mov     rax, cs:g_pfnFree
0x18003f5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5c3  test    rsi, rsi
0x18003f5c6  jz      short loc_18003F5E0
0x18003f5c8  lea     rcx, [rsi-8]
0x18003f5cc  cmp     dword ptr [rcx], 70616548h
0x18003f5d2  jnz     short loc_18003F5E0
0x18003f5d4  mov     rax, cs:g_pfnFree
0x18003f5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5e0  mov     eax, ebx
0x18003f5e2  mov     rcx, [rbp+60h+var_48]
0x18003f5e6  xor     rcx, rbp; StackCookie
0x18003f5e9  call    __security_check_cookie
0x18003f5ee  lea     rsp, [rbp+28h]
0x18003f5f2  pop     r15
0x18003f5f4  pop     r14
0x18003f5f6  pop     r13
0x18003f5f8  pop     r12
0x18003f5fa  pop     rdi
0x18003f5fb  pop     rsi
0x18003f5fc  pop     rbx
0x18003f5fd  pop     rbp
0x18003f5fe  retn
```
