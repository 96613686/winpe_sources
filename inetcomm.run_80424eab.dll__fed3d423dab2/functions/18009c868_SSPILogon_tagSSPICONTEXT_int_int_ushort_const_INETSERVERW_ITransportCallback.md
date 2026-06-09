# SSPILogon(tagSSPICONTEXT *,int,int,ushort const *,INETSERVERW *,ITransportCallback *)

- ea: `0x18009c868`
- end: `0x18009cccc`
- name: `?SSPILogon@@YAJPEAUtagSSPICONTEXT@@HHPEBGPEAUINETSERVERW@@PEAUITransportCallback@@@Z`
- size: `1124`
- prototype: `__int64 __usercall@<rax>(struct tagSSPICONTEXT *@<rcx>, int@<edx>, int@<r8d>, const unsigned __int16 *@<r9>, struct INETSERVERW *, struct ITransportCallback *)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009ccd4`
- `0x1800ad6bc`
- `0x1800b327c`
- `0x1800b70cc`
- `0x1800b8f0c`

## callees

- `0x1800055bc`
- `0x18009bf74`
- `0x18009bff0`
- `0x18009c7d0`
- `0x18009c868`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszDupW` at `0x18009c98d`
- `MSOERT2!PszDupW` at `0x18009c9ad`
- `MSOERT2!PszDupW` at `0x18009ca12`
- `MSOERT2!PszDupW` at `0x18009ca40`
- `MSOERT2!PszDupW` at `0x18009c98d`
- `MSOERT2!PszDupW` at `0x18009c9ad`
- `MSOERT2!PszDupW` at `0x18009ca12`
- `MSOERT2!PszDupW` at `0x18009ca40`
- `MSOERT2!PszAllocW` at `0x18009c9ea`
- `MSOERT2!PszAllocW` at `0x18009c9ea`
- `MSOERT2!FIsEmptyW` at `0x18009ca2f`
- `MSOERT2!FIsEmptyW` at `0x18009ca2f`
- `SHLWAPI!StrChrW` at `0x18009c9ce`
- `SHLWAPI!StrChrW` at `0x18009c9ce`
- `KERNEL32!lstrcmpiW` at `0x18009cb11`
- `KERNEL32!lstrcmpiW` at `0x18009cb11`
- `KERNEL32!CompareStringW` at `0x18009c94e`
- `KERNEL32!CompareStringW` at `0x18009c978`
- `KERNEL32!CompareStringW` at `0x18009cc35`
- `KERNEL32!CompareStringW` at `0x18009c94e`
- `KERNEL32!CompareStringW` at `0x18009c978`
- `KERNEL32!CompareStringW` at `0x18009cc35`
- `KERNEL32!LeaveCriticalSection` at `0x18009cb32`
- `KERNEL32!LeaveCriticalSection` at `0x18009cb32`
- `KERNEL32!EnterCriticalSection` at `0x18009caf8`
- `KERNEL32!EnterCriticalSection` at `0x18009caf8`

## pseudocode

```c
__int64 __fastcall SSPILogon(
        struct tagSSPICONTEXT *a1,
        int a2,
        int a3,
        const unsigned __int16 *a4,
        const WCHAR *a5,
        struct ITransportCallback *a6)
{
  __int64 result; // rax
  int v11; // eax
  const wchar_t *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // esi
  PWSTR v16; // rax
  unsigned __int16 *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  LPCWSTR i; // rdi
  int v22; // eax
  __int64 v23; // rdx
  int (__fastcall *v24)(_QWORD, __int64, __int64, _QWORD, _SEC_WINNT_AUTH_IDENTITY_W *, _QWORD, _QWORD, __int128 *, __int64 *); // rax
  __int64 v25; // [rsp+50h] [rbp-49h] BYREF
  __int64 v26; // [rsp+58h] [rbp-41h] BYREF
  _SEC_WINNT_AUTH_IDENTITY_W v27; // [rsp+60h] [rbp-39h] BYREF
  __int128 v28; // [rsp+90h] [rbp-9h] BYREF

  v26 = 0;
  memset(&v27, 0, sizeof(v27));
  if ( !a1 || !a4 || !a6 )
    return 2147942487LL;
  if ( !qword_1800F3440 || !qword_1800F3448 )
    return 2147549183LL;
  if ( !*((_BYTE *)a1 + 32) || (result = 0, *(_DWORD *)a1) )
  {
    if ( (unsigned int)SSPIIsInstalled() == 1 )
      return 2148322304LL;
    *((_BYTE *)a1 + 16) = 0;
    if ( *((_QWORD *)a1 + 17) )
    {
LABEL_26:
      if ( *((_BYTE *)a1 + 32) )
      {
        (*(void (__fastcall **)(char *))(qword_1800F3448 + 32))((char *)a1 + 40);
        *((_BYTE *)a1 + 32) = 0;
      }
      if ( !lpString2 )
      {
        if ( *(_DWORD *)a1 )
          goto LABEL_40;
        *(_DWORD *)a1 = 1;
      }
      if ( !*(_DWORD *)a1 )
      {
        if ( a2 )
        {
          v22 = *((_DWORD *)a1 + 2);
          ++*((_DWORD *)a1 + 3);
          *(_DWORD *)a1 = v22;
        }
        else
        {
          *((_DWORD *)a1 + 3) = 0;
          EnterCriticalSection(&g_csDllMain);
          for ( i = lpString2; i; i = (LPCWSTR)*((_QWORD *)i + 257) )
          {
            if ( !lstrcmpiW(*((LPCWSTR *)a1 + 11), i) )
            {
              *((_DWORD *)i + 512) = 0;
              break;
            }
          }
          LeaveCriticalSection(&g_csDllMain);
        }
        goto LABEL_46;
      }
LABEL_40:
      if ( *(_DWORD *)a1 == 1 )
      {
        *(_DWORD *)a1 = 3;
        v27.User = (unsigned __int16 *)c_szEmptyW;
        v27.Domain = (unsigned __int16 *)c_szEmptyW;
        v27.Password = (unsigned __int16 *)c_szEmptyW;
        v27.Flags = 2;
        v23 = *((_QWORD *)a1 + 12);
        v27.UserLength = 0;
        v27.DomainLength = 0;
        v27.PasswordLength = 0;
        v24 = *(int (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _SEC_WINNT_AUTH_IDENTITY_W *, _QWORD, _QWORD, __int128 *, __int64 *))(qword_1800F3448 + 24);
        v28 = 0;
        if ( v24(0, v23, 2, 0, &v27, 0, 0, &v28, &v26) >= 0 )
          (*(void (__fastcall **)(__int128 *))(qword_1800F3448 + 32))(&v28);
      }
      else
      {
        if ( *(_DWORD *)a1 != 3 )
          goto LABEL_46;
        *(_DWORD *)a1 = 0;
        result = SSPIFindCredential(a1, a6);
        if ( (int)result < 0 )
          return result;
      }
      SSPIFillAuth(
        *((const unsigned __int16 **)a1 + 13),
        *((const unsigned __int16 **)a1 + 14),
        *((const unsigned __int16 **)a1 + 15),
        &v27);
      CompareStringW(0x7Fu, 1u, a4, -1, L"NTLM", -1);
LABEL_46:
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(qword_1800F3448 + 24))(0, *((_QWORD *)a1 + 12), 2);
      if ( (int)result >= 0 )
        *((_BYTE *)a1 + 32) = 1;
      return result;
    }
    v25 = 0;
    *((_DWORD *)a1 + 20) = a3;
    if ( CompareStringW(0x7Fu, 1u, a4, -1, L"digest", -1) == 2
      || (v11 = CompareStringW(0x7Fu, 1u, a4, -1, L"digest-md5", -1), v12 = a4, v11 == 2) )
    {
      v12 = L"wdigest";
    }
    v13 = PszDupW(v12);
    *((_QWORD *)a1 + 12) = v13;
    if ( v13 )
    {
      v14 = PszDupW(a5 + 768);
      *((_QWORD *)a1 + 11) = v14;
      if ( v14 )
      {
        v15 = 0;
        v16 = StrChrW(a5 + 256, 0x5Cu);
        if ( v16 )
        {
          v15 = (((char *)v16 - (char *)a5 - 512) >> 1) + 1;
          v17 = (unsigned __int16 *)PszAllocW(v15);
          *((_QWORD *)a1 + 15) = v17;
          if ( !v17 )
            return 2147942414LL;
          StringCchCopyW(v17, v15, a5 + 256);
        }
        v18 = PszDupW(&a5[v15 + 256]);
        *((_QWORD *)a1 + 13) = v18;
        if ( v18 )
        {
          if ( (unsigned int)FIsEmptyW(a5 + 512) || (v19 = PszDupW(a5 + 512), (*((_QWORD *)a1 + 14) = v19) != 0) )
          {
            *((_QWORD *)a1 + 17) = a6;
            (*(void (__fastcall **)(struct ITransportCallback *))(*(_QWORD *)a6 + 8LL))(a6);
            if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))a1 + 17))(
                   *((_QWORD *)a1 + 17),
                   &IID_ITransportCallbackService,
                   &v25) < 0 )
            {
              *((_DWORD *)a1 + 32) = 0;
            }
            else
            {
              v20 = v25;
              *((_DWORD *)a1 + 32) = 1;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
            goto LABEL_26;
          }
        }
      }
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18009c868  mov     [rsp-8+arg_8], rbx
0x18009c86d  push    rbp
0x18009c86e  push    rsi
0x18009c86f  push    rdi
0x18009c870  push    r12
0x18009c872  push    r13
0x18009c874  push    r14
0x18009c876  push    r15
0x18009c878  lea     rbp, [rsp-17h]
0x18009c87d  sub     rsp, 0B0h
0x18009c884  mov     rax, cs:__security_cookie
0x18009c88b  xor     rax, rsp
0x18009c88e  mov     [rbp+47h+var_40], rax
0x18009c892  mov     rdi, [rbp+47h+arg_20]
0x18009c896  xorps   xmm0, xmm0
0x18009c899  mov     r12, [rbp+47h+arg_28]
0x18009c89d  xor     r14d, r14d
0x18009c8a0  mov     [rbp+47h+var_88], r14
0x18009c8a4  mov     r15, r9
0x18009c8a7  mov     esi, r8d
0x18009c8aa  mov     r13d, edx
0x18009c8ad  mov     rbx, rcx
0x18009c8b0  movups  xmmword ptr [rbp+47h+var_80.User], xmm0
0x18009c8b4  movups  xmmword ptr [rbp+47h+var_80.Domain], xmm0
0x18009c8b8  movups  xmmword ptr [rbp+47h+var_80.Password], xmm0
0x18009c8bc  test    rcx, rcx
0x18009c8bf  jz      loc_18009CCA0
0x18009c8c5  test    r9, r9
0x18009c8c8  jz      loc_18009CCA0
0x18009c8ce  test    r12, r12
0x18009c8d1  jz      loc_18009CCA0
0x18009c8d7  cmp     cs:qword_1800F3440, r14
0x18009c8de  jz      loc_18009CC99
0x18009c8e4  cmp     cs:qword_1800F3448, r14
0x18009c8eb  jz      loc_18009CC99
0x18009c8f1  cmp     [rcx+20h], r14b
0x18009c8f5  jz      short loc_18009C903
0x18009c8f7  mov     eax, r14d
0x18009c8fa  cmp     [rcx], r14d
0x18009c8fd  jz      loc_18009CCA5
0x18009c903  call    ?SSPIIsInstalled@@YAJXZ; SSPIIsInstalled(void)
0x18009c908  cmp     eax, 1
0x18009c90b  jnz     short loc_18009C917
0x18009c90d  mov     eax, 800CCC00h
0x18009c912  jmp     loc_18009CCA5
0x18009c917  or      ecx, 0FFFFFFFFh
0x18009c91a  mov     [rbx+10h], r14b
0x18009c91e  cmp     [rbx+88h], r14
0x18009c925  jnz     loc_18009CAAE
0x18009c92b  mov     [rsp+0E0h+cchCount2], ecx; cchCount2
0x18009c92f  lea     edx, [rcx+2]; dwCmpFlags
0x18009c932  lea     rax, aDigest; "digest"
0x18009c939  mov     [rbp+47h+var_90], r14
0x18009c93d  mov     r9d, ecx; cchCount1
0x18009c940  mov     [rbx+50h], esi
0x18009c943  lea     ecx, [rdx+7Eh]; Locale
0x18009c946  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18009c94b  mov     r8, r15; lpString1
0x18009c94e  call    cs:__imp_CompareStringW
0x18009c954  cmp     eax, 2
0x18009c957  jz      short loc_18009C986
0x18009c959  or      r9d, 0FFFFFFFFh; cchCount1
0x18009c95d  lea     rax, aDigestMd5; "digest-md5"
0x18009c964  mov     [rsp+0E0h+cchCount2], r9d; cchCount2
0x18009c969  mov     r8, r15; lpString1
0x18009c96c  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18009c971  lea     edx, [r9+2]; dwCmpFlags
0x18009c975  lea     ecx, [rdx+7Eh]; Locale
0x18009c978  call    cs:__imp_CompareStringW
0x18009c97e  mov     rcx, r15
0x18009c981  cmp     eax, 2
0x18009c984  jnz     short loc_18009C98D
0x18009c986  lea     rcx, aWdigest; "wdigest"
0x18009c98d  call    cs:__imp_PszDupW
0x18009c993  mov     [rbx+60h], rax
0x18009c997  test    rax, rax
0x18009c99a  jnz     short loc_18009C9A6
0x18009c99c  mov     eax, 8007000Eh
0x18009c9a1  jmp     loc_18009CCA5
0x18009c9a6  lea     rcx, [rdi+600h]
0x18009c9ad  call    cs:__imp_PszDupW
0x18009c9b3  mov     [rbx+58h], rax
0x18009c9b7  test    rax, rax
0x18009c9ba  jz      short loc_18009C99C
0x18009c9bc  mov     esi, r14d
0x18009c9bf  mov     edx, 5Ch ; '\'; wMatch
0x18009c9c4  lea     r14, [rdi+200h]
0x18009c9cb  mov     rcx, r14; pszStart
0x18009c9ce  call    cs:__imp_StrChrW
0x18009c9d4  test    rax, rax
0x18009c9d7  jz      short loc_18009CA06
0x18009c9d9  sub     rax, rdi
0x18009c9dc  lea     rsi, [rax-200h]
0x18009c9e3  sar     rsi, 1
0x18009c9e6  inc     esi
0x18009c9e8  mov     ecx, esi
0x18009c9ea  call    cs:__imp_PszAllocW
0x18009c9f0  mov     [rbx+78h], rax
0x18009c9f4  test    rax, rax
0x18009c9f7  jz      short loc_18009C99C
0x18009c9f9  mov     edx, esi; unsigned __int64
0x18009c9fb  mov     r8, r14; unsigned __int16 *
0x18009c9fe  mov     rcx, rax; unsigned __int16 *
0x18009ca01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009ca06  mov     eax, esi
0x18009ca08  add     rax, 100h
0x18009ca0e  lea     rcx, [rdi+rax*2]
0x18009ca12  call    cs:__imp_PszDupW
0x18009ca18  xor     r14d, r14d
0x18009ca1b  mov     [rbx+68h], rax
0x18009ca1f  test    rax, rax
0x18009ca22  jz      loc_18009C99C
0x18009ca28  lea     rcx, [rdi+400h]
0x18009ca2f  call    cs:__imp_FIsEmptyW
0x18009ca35  test    eax, eax
0x18009ca37  jnz     short loc_18009CA53
0x18009ca39  lea     rcx, [rdi+400h]
0x18009ca40  call    cs:__imp_PszDupW
0x18009ca46  mov     [rbx+70h], rax
0x18009ca4a  test    rax, rax
0x18009ca4d  jz      loc_18009C99C
0x18009ca53  mov     [rbx+88h], r12
0x18009ca5a  mov     rcx, r12
0x18009ca5d  mov     rax, [r12]
0x18009ca61  mov     rax, [rax+8]
0x18009ca65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca6a  mov     rcx, [rbx+88h]
0x18009ca71  lea     r8, [rbp+47h+var_90]
0x18009ca75  lea     rdx, IID_ITransportCallbackService
0x18009ca7c  mov     rax, [rcx]
0x18009ca7f  mov     rax, [rax]
0x18009ca82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca87  test    eax, eax
0x18009ca89  js      short loc_18009CAA7
0x18009ca8b  mov     rcx, [rbp+47h+var_90]
0x18009ca8f  mov     dword ptr [rbx+80h], 1
0x18009ca99  mov     rax, [rcx]
0x18009ca9c  mov     rax, [rax+10h]
0x18009caa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009caa5  jmp     short loc_18009CAAE
0x18009caa7  mov     [rbx+80h], r14d
0x18009caae  mov     rsi, r14
0x18009cab1  cmp     [rbx+20h], r14b
0x18009cab5  jz      short loc_18009CACF
0x18009cab7  mov     rax, cs:qword_1800F3448
0x18009cabe  lea     rcx, [rbx+28h]
0x18009cac2  mov     rax, [rax+20h]
0x18009cac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cacb  mov     [rbx+20h], r14b
0x18009cacf  cmp     cs:lpString2, r14
0x18009cad6  jnz     short loc_18009CAE3
0x18009cad8  cmp     [rbx], r14d
0x18009cadb  jnz     short loc_18009CB4A
0x18009cadd  mov     dword ptr [rbx], 1
0x18009cae3  cmp     [rbx], r14d
0x18009cae6  jnz     short loc_18009CB4A
0x18009cae8  test    r13d, r13d
0x18009caeb  jnz     short loc_18009CB3D
0x18009caed  lea     rcx, ?g_csDllMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009caf4  mov     [rbx+0Ch], r14d
0x18009caf8  call    cs:__imp_EnterCriticalSection
0x18009cafe  mov     rdi, cs:lpString2
0x18009cb05  test    rdi, rdi
0x18009cb08  jz      short loc_18009CB2B
0x18009cb0a  mov     rcx, [rbx+58h]; lpString1
0x18009cb0e  mov     rdx, rdi; lpString2
0x18009cb11  call    cs:__imp_lstrcmpiW
0x18009cb17  test    eax, eax
0x18009cb19  jz      short loc_18009CB24
0x18009cb1b  mov     rdi, [rdi+808h]
0x18009cb22  jmp     short loc_18009CB05
0x18009cb24  mov     [rdi+800h], r14d
0x18009cb2b  lea     rcx, ?g_csDllMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009cb32  call    cs:__imp_LeaveCriticalSection
0x18009cb38  jmp     loc_18009CC51
0x18009cb3d  mov     eax, [rbx+8]
0x18009cb40  inc     dword ptr [rbx+0Ch]
0x18009cb43  mov     [rbx], eax
0x18009cb45  jmp     loc_18009CC51
0x18009cb4a  cmp     dword ptr [rbx], 1
0x18009cb4d  jnz     loc_18009CBE2
0x18009cb53  lea     rax, c_szEmptyW
0x18009cb5a  mov     dword ptr [rbx], 3
0x18009cb60  mov     [rbp+47h+var_80.User], rax
0x18009cb64  lea     rcx, [rbp+47h+var_88]
0x18009cb68  mov     [rsp+0E0h+var_A0], rcx
0x18009cb6d  mov     edx, 2
0x18009cb72  mov     [rbp+47h+var_80.Domain], rax
0x18009cb76  lea     rcx, [rbp+47h+var_50]
0x18009cb7a  mov     [rsp+0E0h+var_A8], rcx
0x18009cb7f  xorps   xmm0, xmm0
0x18009cb82  mov     [rbp+47h+var_80.Password], rax
0x18009cb86  lea     rcx, [rbp+47h+var_80]
0x18009cb8a  mov     rax, cs:qword_1800F3448
0x18009cb91  mov     r8d, edx
0x18009cb94  mov     [rbp+47h+var_80.Flags], edx
0x18009cb97  xor     r9d, r9d
0x18009cb9a  mov     rdx, [rbx+60h]
0x18009cb9e  mov     [rsp+0E0h+var_B0], r14
0x18009cba3  mov     [rbp+47h+var_80.UserLength], r14d
0x18009cba7  mov     [rbp+47h+var_80.DomainLength], r14d
0x18009cbab  mov     [rbp+47h+var_80.PasswordLength], r14d
0x18009cbaf  mov     rax, [rax+18h]
0x18009cbb3  mov     qword ptr [rsp+0E0h+cchCount2], r14
0x18009cbb8  mov     [rsp+0E0h+lpString2], rcx
0x18009cbbd  xor     ecx, ecx
0x18009cbbf  movups  [rbp+47h+var_50], xmm0
0x18009cbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbc8  test    eax, eax
0x18009cbca  js      short loc_18009CBFD
0x18009cbcc  mov     rax, cs:qword_1800F3448
0x18009cbd3  lea     rcx, [rbp+47h+var_50]
0x18009cbd7  mov     rax, [rax+20h]
0x18009cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbe0  jmp     short loc_18009CBFD
0x18009cbe2  cmp     dword ptr [rbx], 3
0x18009cbe5  jnz     short loc_18009CC51
0x18009cbe7  mov     rdx, r12; struct ITransportCallback *
0x18009cbea  mov     [rbx], r14d
0x18009cbed  mov     rcx, rbx; struct tagSSPICONTEXT *
0x18009cbf0  call    ?SSPIFindCredential@@YAJPEAUtagSSPICONTEXT@@PEAUITransportCallback@@@Z; SSPIFindCredential(tagSSPICONTEXT *,ITransportCallback *)
0x18009cbf5  test    eax, eax
0x18009cbf7  js      loc_18009CCA5
0x18009cbfd  mov     r8, [rbx+78h]; unsigned __int16 *
0x18009cc01  lea     r9, [rbp+47h+var_80]; struct _SEC_WINNT_AUTH_IDENTITY_W *
0x18009cc05  mov     rdx, [rbx+70h]; unsigned __int16 *
0x18009cc09  mov     rcx, [rbx+68h]; unsigned __int16 *
0x18009cc0d  call    ?SSPIFillAuth@@YAJPEBG00PEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z; SSPIFillAuth(ushort const *,ushort const *,ushort const *,_SEC_WINNT_AUTH_IDENTITY_W *)
0x18009cc12  or      ecx, 0FFFFFFFFh
0x18009cc15  lea     rax, aNtlm; "NTLM"
0x18009cc1c  mov     [rsp+0E0h+cchCount2], ecx; cchCount2
0x18009cc20  lea     rsi, [rbp+47h+var_80]
0x18009cc24  mov     r9d, ecx; cchCount1
0x18009cc27  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18009cc2c  mov     r8, r15; lpString1
0x18009cc2f  lea     edx, [rcx+2]; dwCmpFlags
0x18009cc32  lea     ecx, [rdx+7Eh]; Locale
0x18009cc35  call    cs:__imp_CompareStringW
0x18009cc3b  cmp     eax, 2
0x18009cc3e  jnz     short loc_18009CC51
0x18009cc40  cmp     [rbp+47h+var_80.UserLength], r14d
0x18009cc44  jnz     short loc_18009CC51
0x18009cc46  mov     eax, [rbp+47h+var_80.PasswordLength]
0x18009cc49  neg     eax
0x18009cc4b  sbb     rcx, rcx
0x18009cc4e  and     rsi, rcx
0x18009cc51  mov     rax, cs:qword_1800F3448
0x18009cc58  lea     rdx, [rbp+47h+var_88]
0x18009cc5c  mov     [rsp+0E0h+var_A0], rdx
0x18009cc61  lea     rcx, [rbx+28h]
0x18009cc65  mov     rdx, [rbx+60h]
0x18009cc69  xor     r9d, r9d
0x18009cc6c  mov     [rsp+0E0h+var_A8], rcx
0x18009cc71  xor     ecx, ecx
0x18009cc73  mov     rax, [rax+18h]
0x18009cc77  mov     [rsp+0E0h+var_B0], r14
0x18009cc7c  mov     qword ptr [rsp+0E0h+cchCount2], r14
0x18009cc81  lea     r8d, [r9+2]
0x18009cc85  mov     [rsp+0E0h+lpString2], rsi
0x18009cc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc8f  test    eax, eax
0x18009cc91  js      short loc_18009CCA5
0x18009cc93  mov     byte ptr [rbx+20h], 1
0x18009cc97  jmp     short loc_18009CCA5
0x18009cc99  mov     eax, 8000FFFFh
0x18009cc9e  jmp     short loc_18009CCA5
0x18009cca0  mov     eax, 80070057h
0x18009cca5  mov     rcx, [rbp+47h+var_40]
0x18009cca9  xor     rcx, rsp; StackCookie
0x18009ccac  call    __security_check_cookie
0x18009ccb1  mov     rbx, [rsp+0E0h+arg_8]
0x18009ccb9  add     rsp, 0B0h
0x18009ccc0  pop     r15
0x18009ccc2  pop     r14
0x18009ccc4  pop     r13
0x18009ccc6  pop     r12
0x18009ccc8  pop     rdi
0x18009ccc9  pop     rsi
0x18009ccca  pop     rbp
0x18009cccb  retn
```
