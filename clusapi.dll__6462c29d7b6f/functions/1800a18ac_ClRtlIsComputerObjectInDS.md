# ClRtlIsComputerObjectInDS

- ea: `0x1800a18ac`
- end: `0x1800a1c72`
- name: `ClRtlIsComputerObjectInDS`
- size: `966`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800795d0`
- `0x18007aa80`
- `0x1800a1450`
- `0x1800a16fc`
- `0x1800a2904`

## callees

- `0x180002f50`
- `0x18001236c`
- `0x1800123b0`
- `0x1800a1044`
- `0x1800a18ac`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1c47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1c47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a19f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a1bab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a19f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a1bab`
- `netutils!NetApiBufferFree` at `0x1800a1c2d`
- `netutils!NetApiBufferFree` at `0x1800a1c2d`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x1800a1a65`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x1800a1a65`

## string_xrefs

- `0x1800a1904`: `(&(objectCategory=computer)(samAccountName=`

## pseudocode

```c
__int64 __fastcall ClRtlIsComputerObjectInDS(const WCHAR *a1, __int64 a2, _WORD *a3, _DWORD *a4, wchar_t **a5)
{
  _WORD *v5; // rbx
  DWORD v6; // r15d
  __int64 result; // rax
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // r12
  _BYTE *v12; // rdi
  signed int LastError; // eax
  int v14; // ebx
  SIZE_T v15; // rdx
  unsigned int v16; // esi
  wchar_t *v17; // rax
  signed int v18; // eax
  IID *riid; // [rsp+20h] [rbp-E0h]
  void *ppObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  const wchar_t *v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  _DWORD *v25; // [rsp+68h] [rbp-98h]
  __int128 v26; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  _DWORD v29[20]; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v31; // [rsp+F4h] [rbp-Ch]
  __int128 v32; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v33[5]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v34; // [rsp+160h] [rbp+60h]
  wchar_t v35[64]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v36[528]; // [rsp+1F0h] [rbp+F0h] BYREF

  v32 = *(_OWORD *)L"LDAP://";
  v5 = a3;
  v23 = L"distinguishedName";
  v33[0] = *(_OWORD *)L"(&(objectCategory=computer)(samAccountName=";
  v30 = *(_DWORD *)L"))";
  v33[2] = *(_OWORD *)L"y=computer)(samAccountName=";
  v33[1] = *(_OWORD *)L"tCategory=computer)(samAccountName=";
  v31 = asc_1800FE3DC[2];
  v33[4] = *(_OWORD *)L"ccountName=";
  v33[3] = *(_OWORD *)L"er)(samAccountName=";
  v25 = a4;
  v24 = a2;
  v34 = *(_QWORD *)L"me=";
  v28 = 0;
  ppObject = 0;
  v21 = 0;
  v22 = 0;
  v26 = 0;
  v27 = 0;
  if ( a3 )
  {
    if ( *a3 == 92 && a3[1] == 92 )
      v5 = a3 + 2;
    v6 = 513;
LABEL_10:
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    v10 = (unsigned int)(v9 + 8);
    v11 = (unsigned int)v10;
    if ( (unsigned int)v10 <= 0x108 )
    {
      v12 = v36;
    }
    else
    {
      v12 = LocalAlloc(0, 2 * v10);
      if ( !v12 )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_32:
        if ( ppObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
        if ( v12 != v36 )
        {
          if ( v12 )
            LocalFree(v12);
        }
        return (unsigned int)v14;
      }
    }
    StringCchPrintfW((wchar_t *)v12, v11, L"%ws%ws", &v32, v5);
    v14 = ADsOpenObject((LPCWSTR)v12, 0, 0, v6, &IID_IDirectorySearch, &ppObject);
    if ( v14 >= 0 )
    {
      v29[0] = 2;
      v29[2] = 7;
      v29[12] = 7;
      v29[4] = 1;
      v29[10] = 5;
      v29[14] = 2;
      v14 = (*(__int64 (__fastcall **)(void *, _DWORD *))(*(_QWORD *)ppObject + 24LL))(ppObject, v29);
      if ( v14 >= 0 )
      {
        LODWORD(riid) = 15;
        StringCchPrintfW(v35, 0x3Fu, L"%ws%.*ws$%ws", v33, riid, v24, &v30);
        v14 = (*(__int64 (__fastcall **)(void *, wchar_t *, const wchar_t **, __int64, __int64 *))(*(_QWORD *)ppObject
                                                                                                 + 32LL))(
                ppObject,
                v35,
                &v23,
                1,
                &v21);
        if ( v14 >= 0 )
        {
          v14 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppObject + 48LL))(ppObject, v21);
          *v25 = v14 == 0;
          if ( v14 == 20498 )
          {
            v14 = 0;
          }
          else if ( !v14 )
          {
            if ( a5 )
            {
              v14 = (*(__int64 (__fastcall **)(void *, __int64, const wchar_t *, __int128 *))(*(_QWORD *)ppObject + 80LL))(
                      ppObject,
                      v21,
                      v23,
                      &v26);
              if ( v14 >= 0 )
              {
                do
                  ++v8;
                while ( *(_WORD *)(*(_QWORD *)(v27 + 8) + 2 * v8) );
                v15 = 2LL * (unsigned int)(v8 + 1);
                v16 = v8 + 1;
                v17 = (wchar_t *)LocalAlloc(0, v15);
                *a5 = v17;
                if ( v17 )
                {
                  StringCchCopyW(v17, v16, *(const wchar_t **)(v27 + 8));
                }
                else
                {
                  v18 = GetLastError();
                  v14 = v18;
                  if ( v18 > 0 )
                    v14 = (unsigned __int16)v18 | 0x80070000;
                }
                (*(void (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppObject + 88LL))(ppObject, &v26);
              }
            }
          }
          (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)ppObject + 96LL))(ppObject, v21);
        }
      }
    }
    goto LABEL_32;
  }
  result = ClRtlFindDomainForServer(a1);
  if ( !(_DWORD)result )
  {
    v6 = 1;
    v5 = *(_WORD **)(v22 + 40);
    goto LABEL_10;
  }
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800a18ac  push    rbp
0x1800a18ae  push    rbx
0x1800a18af  push    rsi
0x1800a18b0  push    rdi
0x1800a18b1  push    r12
0x1800a18b3  push    r13
0x1800a18b5  push    r14
0x1800a18b7  push    r15
0x1800a18b9  lea     rbp, [rsp-318h]
0x1800a18c1  sub     rsp, 418h
0x1800a18c8  mov     rax, cs:__security_cookie
0x1800a18cf  xor     rax, rsp
0x1800a18d2  mov     [rbp+350h+var_50], rax
0x1800a18d9  movups  xmm0, xmmword ptr cs:aLdap_0; "LDAP://"
0x1800a18e0  lea     rax, aDistinguishedn; "distinguishedName"
0x1800a18e7  mov     r13, [rbp+350h+arg_20]
0x1800a18ee  movaps  xmm1, xmmword ptr cs:aObjectcategory+10h; "tCategory=computer)(samAccountName="
0x1800a18f5  xor     edi, edi
0x1800a18f7  movdqu  [rbp+350h+var_358], xmm0
0x1800a18fc  mov     rbx, r8
0x1800a18ff  mov     [rsp+450h+var_3F8], rax
0x1800a1904  movaps  xmm0, xmmword ptr cs:aObjectcategory; "(&(objectCategory=computer)(samAccountN"...
0x1800a190b  mov     r14d, edi
0x1800a190e  mov     eax, dword ptr cs:asc_1800FE3DC; "))"
0x1800a1914  movaps  [rbp+350h+var_340], xmm0
0x1800a1918  movaps  xmm0, xmmword ptr cs:aObjectcategory+20h; "y=computer)(samAccountName="
0x1800a191f  mov     [rbp+350h+var_360], eax
0x1800a1922  movzx   eax, word ptr cs:asc_1800FE3DC+4; ""
0x1800a1929  movaps  [rbp+350h+var_320], xmm0
0x1800a192d  movaps  xmm0, xmmword ptr cs:aObjectcategory+40h; "ccountName="
0x1800a1934  movaps  [rbp+350h+var_330], xmm1
0x1800a1938  movaps  xmm1, xmmword ptr cs:aObjectcategory+30h; "er)(samAccountName="
0x1800a193f  mov     [rbp+350h+var_35C], ax
0x1800a1943  xor     eax, eax
0x1800a1945  movaps  [rbp+350h+var_300], xmm0
0x1800a1949  xorps   xmm0, xmm0
0x1800a194c  movaps  [rbp+350h+var_310], xmm1
0x1800a1950  movsd   xmm1, qword ptr cs:aObjectcategory+50h; "me="
0x1800a1958  mov     [rsp+450h+var_3E8], r9
0x1800a195d  mov     [rsp+450h+var_3F0], rdx
0x1800a1962  movsd   [rbp+350h+var_2F0], xmm1
0x1800a1967  mov     [rbp+350h+var_3C0], rax
0x1800a196b  mov     [rsp+450h+var_410], rdi
0x1800a1970  mov     [rsp+450h+var_408], rdi
0x1800a1975  mov     [rsp+450h+var_400], rdi
0x1800a197a  movups  [rsp+450h+var_3E0], xmm0
0x1800a197f  movups  [rbp+350h+var_3D0], xmm0
0x1800a1983  test    r8, r8
0x1800a1986  jz      short loc_1800A19A3
0x1800a1988  cmp     word ptr [r8], 5Ch ; '\'
0x1800a198d  jnz     short loc_1800A199B
0x1800a198f  cmp     word ptr [r8+2], 5Ch ; '\'
0x1800a1995  jnz     short loc_1800A199B
0x1800a1997  add     rbx, 4
0x1800a199b  mov     r15d, 201h
0x1800a19a1  jmp     short loc_1800A19D3
0x1800a19a3  lea     r9, [rsp+450h+var_400]
0x1800a19a8  call    ClRtlFindDomainForServer
0x1800a19ad  test    eax, eax
0x1800a19af  jz      short loc_1800A19C4
0x1800a19b1  jle     loc_1800A1C4F
0x1800a19b7  movzx   eax, ax
0x1800a19ba  or      eax, 80070000h
0x1800a19bf  jmp     loc_1800A1C4F
0x1800a19c4  mov     r14, [rsp+450h+var_400]
0x1800a19c9  mov     r15d, 1
0x1800a19cf  mov     rbx, [r14+28h]
0x1800a19d3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a19d7  mov     rax, rsi
0x1800a19da  inc     rax
0x1800a19dd  cmp     [rbx+rax*2], di
0x1800a19e1  jnz     short loc_1800A19DA
0x1800a19e3  add     eax, 8
0x1800a19e6  mov     r12d, eax
0x1800a19e9  cmp     eax, 108h
0x1800a19ee  jbe     short loc_1800A1A22
0x1800a19f0  lea     rdx, [rax+rax]; uBytes
0x1800a19f4  xor     ecx, ecx; uFlags
0x1800a19f6  call    cs:__imp_LocalAlloc
0x1800a19fc  mov     rdi, rax
0x1800a19ff  test    rax, rax
0x1800a1a02  jnz     short loc_1800A1A29
0x1800a1a04  call    cs:__imp_GetLastError
0x1800a1a0a  mov     ebx, eax
0x1800a1a0c  test    eax, eax
0x1800a1a0e  jle     loc_1800A1C0F
0x1800a1a14  movzx   ebx, ax
0x1800a1a17  or      ebx, 80070000h
0x1800a1a1d  jmp     loc_1800A1C0F
0x1800a1a22  lea     rdi, [rbp+350h+var_260]
0x1800a1a29  lea     r9, [rbp+350h+var_358]
0x1800a1a2d  mov     [rsp+450h+riid], rbx
0x1800a1a32  lea     r8, aWsWs_0; "%ws%ws"
0x1800a1a39  mov     rdx, r12; unsigned __int64
0x1800a1a3c  mov     rcx, rdi; wchar_t *
0x1800a1a3f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a1a44  lea     rax, [rsp+450h+var_410]
0x1800a1a49  mov     r9d, r15d; dwReserved
0x1800a1a4c  mov     [rsp+450h+ppObject], rax; ppObject
0x1800a1a51  xor     r8d, r8d; lpszPassword
0x1800a1a54  lea     rax, IID_IDirectorySearch
0x1800a1a5b  xor     edx, edx; lpszUserName
0x1800a1a5d  mov     rcx, rdi; lpszPathName
0x1800a1a60  mov     [rsp+450h+riid], rax; riid
0x1800a1a65  call    cs:__imp_ADsOpenObject
0x1800a1a6b  xor     r15d, r15d
0x1800a1a6e  mov     ebx, eax
0x1800a1a70  test    eax, eax
0x1800a1a72  js      loc_1800A1C0F
0x1800a1a78  mov     rcx, [rsp+450h+var_410]
0x1800a1a7d  lea     r8d, [r15+2]
0x1800a1a81  lea     eax, [r15+7]
0x1800a1a85  mov     [rbp+350h+var_3B0], r8d
0x1800a1a89  mov     [rbp+350h+var_3A8], eax
0x1800a1a8c  lea     r12d, [r15+1]
0x1800a1a90  mov     [rbp+350h+var_380], eax
0x1800a1a93  lea     rdx, [rbp+350h+var_3B0]
0x1800a1a97  mov     [rbp+350h+var_3A0], r12d
0x1800a1a9b  mov     [rbp+350h+var_388], 5
0x1800a1aa2  mov     [rbp+350h+var_378], r8d
0x1800a1aa6  mov     rax, [rcx]
0x1800a1aa9  mov     rax, [rax+18h]
0x1800a1aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ab2  mov     ebx, eax
0x1800a1ab4  test    eax, eax
0x1800a1ab6  js      loc_1800A1C0F
0x1800a1abc  lea     rax, [rbp+350h+var_360]
0x1800a1ac0  mov     [rsp+450h+var_420], rax
0x1800a1ac5  lea     r9, [rbp+350h+var_340]
0x1800a1ac9  mov     rax, [rsp+450h+var_3F0]
0x1800a1ace  lea     r8, aWsWsWs; "%ws%.*ws$%ws"
0x1800a1ad5  mov     [rsp+450h+ppObject], rax
0x1800a1ada  lea     edx, [r15+3Fh]; unsigned __int64
0x1800a1ade  lea     rcx, [rbp+350h+var_2E0]; wchar_t *
0x1800a1ae2  mov     dword ptr [rsp+450h+riid], 0Fh
0x1800a1aea  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a1aef  mov     rcx, [rsp+450h+var_410]
0x1800a1af4  lea     rdx, [rsp+450h+var_408]
0x1800a1af9  mov     [rsp+450h+riid], rdx
0x1800a1afe  lea     r8, [rsp+450h+var_3F8]
0x1800a1b03  mov     r9d, r12d
0x1800a1b06  lea     rdx, [rbp+350h+var_2E0]
0x1800a1b0a  mov     rax, [rcx]
0x1800a1b0d  mov     rax, [rax+20h]
0x1800a1b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b16  mov     ebx, eax
0x1800a1b18  test    eax, eax
0x1800a1b1a  js      loc_1800A1C0F
0x1800a1b20  mov     rcx, [rsp+450h+var_410]
0x1800a1b25  mov     rdx, [rsp+450h+var_408]
0x1800a1b2a  mov     rax, [rcx]
0x1800a1b2d  mov     rax, [rax+30h]
0x1800a1b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b36  mov     rcx, [rsp+450h+var_3E8]
0x1800a1b3b  mov     ebx, eax
0x1800a1b3d  test    ebx, ebx
0x1800a1b3f  mov     eax, r15d
0x1800a1b42  setz    al
0x1800a1b45  mov     [rcx], eax
0x1800a1b47  cmp     ebx, 5012h
0x1800a1b4d  jnz     short loc_1800A1B57
0x1800a1b4f  mov     ebx, r15d
0x1800a1b52  jmp     loc_1800A1BF9
0x1800a1b57  test    ebx, ebx
0x1800a1b59  jnz     loc_1800A1BF9
0x1800a1b5f  test    r13, r13
0x1800a1b62  jz      loc_1800A1BF9
0x1800a1b68  mov     rcx, [rsp+450h+var_410]
0x1800a1b6d  lea     r9, [rsp+450h+var_3E0]
0x1800a1b72  mov     r8, [rsp+450h+var_3F8]
0x1800a1b77  mov     rdx, [rsp+450h+var_408]
0x1800a1b7c  mov     rax, [rcx]
0x1800a1b7f  mov     rax, [rax+50h]
0x1800a1b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b88  mov     ebx, eax
0x1800a1b8a  test    eax, eax
0x1800a1b8c  js      short loc_1800A1BF9
0x1800a1b8e  mov     rax, qword ptr [rbp+350h+var_3D0]
0x1800a1b92  mov     rcx, [rax+8]
0x1800a1b96  inc     rsi
0x1800a1b99  cmp     [rcx+rsi*2], r15w
0x1800a1b9e  jnz     short loc_1800A1B96
0x1800a1ba0  lea     eax, [rsi+1]
0x1800a1ba3  xor     ecx, ecx; uFlags
0x1800a1ba5  lea     rdx, [rax+rax]; uBytes
0x1800a1ba9  mov     esi, eax
0x1800a1bab  call    cs:__imp_LocalAlloc
0x1800a1bb1  mov     [r13+0], rax
0x1800a1bb5  test    rax, rax
0x1800a1bb8  jz      short loc_1800A1BCE
0x1800a1bba  mov     r8, qword ptr [rbp+350h+var_3D0]
0x1800a1bbe  mov     edx, esi; unsigned __int64
0x1800a1bc0  mov     rcx, rax; wchar_t *
0x1800a1bc3  mov     r8, [r8+8]; wchar_t *
0x1800a1bc7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a1bcc  jmp     short loc_1800A1BE3
0x1800a1bce  call    cs:__imp_GetLastError
0x1800a1bd4  mov     ebx, eax
0x1800a1bd6  test    eax, eax
0x1800a1bd8  jle     short loc_1800A1BE3
0x1800a1bda  movzx   ebx, ax
0x1800a1bdd  or      ebx, 80070000h
0x1800a1be3  mov     rcx, [rsp+450h+var_410]
0x1800a1be8  lea     rdx, [rsp+450h+var_3E0]
0x1800a1bed  mov     rax, [rcx]
0x1800a1bf0  mov     rax, [rax+58h]
0x1800a1bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bf9  mov     rcx, [rsp+450h+var_410]
0x1800a1bfe  mov     rdx, [rsp+450h+var_408]
0x1800a1c03  mov     rax, [rcx]
0x1800a1c06  mov     rax, [rax+60h]
0x1800a1c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c0f  mov     rcx, [rsp+450h+var_410]
0x1800a1c14  test    rcx, rcx
0x1800a1c17  jz      short loc_1800A1C25
0x1800a1c19  mov     rax, [rcx]
0x1800a1c1c  mov     rax, [rax+10h]
0x1800a1c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c25  test    r14, r14
0x1800a1c28  jz      short loc_1800A1C33
0x1800a1c2a  mov     rcx, r14; Buffer
0x1800a1c2d  call    cs:__imp_NetApiBufferFree
0x1800a1c33  lea     rax, [rbp+350h+var_260]
0x1800a1c3a  cmp     rdi, rax
0x1800a1c3d  jz      short loc_1800A1C4D
0x1800a1c3f  test    rdi, rdi
0x1800a1c42  jz      short loc_1800A1C4D
0x1800a1c44  mov     rcx, rdi; hMem
0x1800a1c47  call    cs:__imp_LocalFree
0x1800a1c4d  mov     eax, ebx
0x1800a1c4f  mov     rcx, [rbp+350h+var_50]
0x1800a1c56  xor     rcx, rsp; StackCookie
0x1800a1c59  call    __security_check_cookie
0x1800a1c5e  add     rsp, 418h
0x1800a1c65  pop     r15
0x1800a1c67  pop     r14
0x1800a1c69  pop     r13
0x1800a1c6b  pop     r12
0x1800a1c6d  pop     rdi
0x1800a1c6e  pop     rsi
0x1800a1c6f  pop     rbx
0x1800a1c70  pop     rbp
0x1800a1c71  retn
```
