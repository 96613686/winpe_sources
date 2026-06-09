# EEDBManager::UpdateEnrollment(Enrollment *)

- ea: `0x18003d1b4`
- end: `0x18003d3e3`
- name: `?UpdateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct Enrollment *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003fc30`

## callees

- `0x1800026d0`
- `0x18003cddc`
- `0x18003d1b4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d3b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d3b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d38a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d38a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003d207`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003d207`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EEDBManager::UpdateEnrollment(EEDBManager *this, struct Enrollment *a2)
{
  HKEY v3; // rbx
  __int64 v4; // rcx
  OLECHAR *p_sz; // rax
  signed int v6; // edi
  __int64 v7; // rax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // r8
  wchar_t v11; // r9
  wchar_t *v12; // rcx
  __int64 v13; // rcx
  wchar_t *v14; // rax
  __int64 v15; // rdx
  LSTATUS v16; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t String1[40]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz; // [rsp+A0h] [rbp-60h] BYREF
  char v22; // [rsp+A2h] [rbp-5Eh] BYREF

  *(_DWORD *)Data = 63;
  v3 = 0;
  hKey[0] = 0;
  String1[0] = 0;
  sz = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 28), &sz, 39) != 39 )
    goto LABEL_25;
  v4 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? 0x80070057 : 0;
  if ( !v4 )
    goto LABEL_26;
  if ( (unsigned __int64)(37 - v4) > 0x24 )
    goto LABEL_25;
  v7 = 2147483646;
  v8 = (wchar_t *)&v22;
  v9 = 39;
  v10 = String1;
  do
  {
    if ( !v7 )
      break;
    v11 = *v8;
    if ( !*v8 )
      break;
    ++v8;
    *v10++ = v11;
    --v7;
    --v9;
  }
  while ( v9 );
  v6 = v9 == 0 ? 0x8007007A : 0;
  v12 = v10 - 1;
  if ( v9 )
    v12 = v10;
  *v12 = 0;
  if ( v9 )
  {
    v13 = 39;
    v14 = String1;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    v6 = v13 == 0 ? 0x80070057 : 0;
    v15 = (39 - v13) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64);
    if ( v13 )
    {
      if ( (unsigned __int64)(v15 - 2) <= 0x24 )
      {
        *((_WORD *)&hKey[2] + v15 + 3) = 0;
        v6 = EEDBManager::OpenEnrollmentHKEY(HKEY_LOCAL_MACHINE, String1, 131078, hKey, 0, 0);
        if ( v6 >= 0 )
        {
          v3 = hKey[0];
          hKey[1] = hKey[0];
          v6 = (*(__int64 (__fastcall **)(struct Enrollment *, BYTE *))(*(_QWORD *)a2 + 56LL))(a2, Data);
          if ( v6 >= 0 )
          {
            v16 = RegSetValueExW(v3, L"EnrollmentState", 0, 4u, Data, 4u);
            if ( v16 )
            {
              if ( v16 > 0 )
                v6 = (unsigned __int16)v16 | 0x80070000;
              else
                v6 = v16;
            }
          }
        }
        goto LABEL_26;
      }
LABEL_25:
      v6 = -2147418113;
    }
  }
LABEL_26:
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003d1b4  push    rbp
0x18003d1b6  push    rbx
0x18003d1b7  push    rsi
0x18003d1b8  push    rdi
0x18003d1b9  push    r14
0x18003d1bb  push    r15
0x18003d1bd  lea     rbp, [rsp-8]
0x18003d1c2  sub     rsp, 108h
0x18003d1c9  mov     rax, cs:__security_cookie
0x18003d1d0  xor     rax, rsp
0x18003d1d3  mov     [rbp+30h+var_40], rax
0x18003d1d7  mov     r14, rdx
0x18003d1da  mov     dword ptr [rsp+130h+Data], 3Fh ; '?'
0x18003d1e2  xor     r15d, r15d
0x18003d1e5  mov     ebx, r15d
0x18003d1e8  mov     [rsp+130h+hKey], r15
0x18003d1ed  mov     [rsp+130h+String1], r15w
0x18003d1f3  mov     [rbp+30h+sz], r15w
0x18003d1f8  lea     rcx, [rdx+1Ch]; rguid
0x18003d1fc  lea     esi, [r15+27h]
0x18003d200  mov     r8d, esi; cchMax
0x18003d203  lea     rdx, [rbp+30h+sz]; lpsz
0x18003d207  call    cs:__imp_StringFromGUID2
0x18003d20e  nop     dword ptr [rax+rax+00h]
0x18003d213  cmp     eax, esi
0x18003d215  jnz     loc_18003D3AB
0x18003d21b  mov     ecx, esi
0x18003d21d  lea     rax, [rbp+30h+sz]
0x18003d221  cmp     [rax], r15w
0x18003d225  jz      short loc_18003D231
0x18003d227  add     rax, 2
0x18003d22b  sub     rcx, 1
0x18003d22f  jnz     short loc_18003D221
0x18003d231  mov     rax, rcx
0x18003d234  neg     rax
0x18003d237  sbb     edi, edi
0x18003d239  not     edi
0x18003d23b  mov     r10d, 80070057h
0x18003d241  and     edi, r10d
0x18003d244  test    rcx, rcx
0x18003d247  jz      loc_18003D3B0
0x18003d24d  mov     eax, 25h ; '%'
0x18003d252  sub     rax, rcx
0x18003d255  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18003d25c  test    rcx, rcx
0x18003d25f  cmovz   rax, rdx
0x18003d263  cmp     rax, 24h ; '$'
0x18003d267  ja      loc_18003D3AB
0x18003d26d  mov     eax, 7FFFFFFEh
0x18003d272  lea     rcx, [rbp+30h+var_8E]
0x18003d276  mov     rdx, rsi
0x18003d279  lea     r8, [rsp+130h+String1]
0x18003d27e  test    rax, rax
0x18003d281  jz      short loc_18003D2A2
0x18003d283  movzx   r9d, word ptr [rcx]
0x18003d287  test    r9w, r9w
0x18003d28b  jz      short loc_18003D2A2
0x18003d28d  add     rcx, 2
0x18003d291  mov     [r8], r9w
0x18003d295  add     r8, 2
0x18003d299  dec     rax
0x18003d29c  sub     rdx, 1
0x18003d2a0  jnz     short loc_18003D27E
0x18003d2a2  mov     rax, rdx
0x18003d2a5  neg     rax
0x18003d2a8  sbb     edi, edi
0x18003d2aa  not     edi
0x18003d2ac  and     edi, 8007007Ah
0x18003d2b2  lea     rcx, [r8-2]
0x18003d2b6  test    rdx, rdx
0x18003d2b9  cmovnz  rcx, r8
0x18003d2bd  mov     [rcx], r15w
0x18003d2c1  jz      loc_18003D3B0
0x18003d2c7  mov     rcx, rsi
0x18003d2ca  lea     rax, [rsp+130h+String1]
0x18003d2cf  cmp     [rax], r15w
0x18003d2d3  jz      short loc_18003D2DF
0x18003d2d5  add     rax, 2
0x18003d2d9  sub     rcx, 1
0x18003d2dd  jnz     short loc_18003D2CF
0x18003d2df  mov     rax, rcx
0x18003d2e2  neg     rax
0x18003d2e5  sbb     edi, edi
0x18003d2e7  not     edi
0x18003d2e9  and     edi, r10d
0x18003d2ec  mov     rax, rcx
0x18003d2ef  sub     rsi, rcx
0x18003d2f2  neg     rax
0x18003d2f5  sbb     rdx, rdx
0x18003d2f8  and     rdx, rsi
0x18003d2fb  test    rcx, rcx
0x18003d2fe  jz      loc_18003D3B0
0x18003d304  lea     rax, [rdx-2]
0x18003d308  cmp     rax, 24h ; '$'
0x18003d30c  ja      loc_18003D3AB
0x18003d312  mov     [rsp+rdx*2+130h+var_E2], r15w
0x18003d318  mov     qword ptr [rsp+130h+cbData], r15; unsigned __int64
0x18003d31d  mov     [rsp+130h+lpData], r15; unsigned __int16 *
0x18003d322  lea     r9, [rsp+130h+hKey]; HKEY *
0x18003d327  mov     r8d, 20006h; unsigned int
0x18003d32d  lea     rdx, [rsp+130h+String1]; String1
0x18003d332  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d339  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x18003d33e  mov     edi, eax
0x18003d340  test    eax, eax
0x18003d342  js      short loc_18003D3B0
0x18003d344  mov     rbx, [rsp+130h+hKey]
0x18003d349  mov     [rsp+130h+var_F0], rbx
0x18003d34e  mov     rax, [r14]
0x18003d351  lea     rdx, [rsp+130h+Data]
0x18003d356  mov     rcx, r14
0x18003d359  mov     rax, [rax+38h]
0x18003d35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d362  mov     edi, eax
0x18003d364  test    eax, eax
0x18003d366  js      short loc_18003D3B0
0x18003d368  mov     r9d, 4; dwType
0x18003d36e  mov     [rsp+130h+cbData], r9d; cbData
0x18003d373  lea     rax, [rsp+130h+Data]
0x18003d378  mov     [rsp+130h+lpData], rax; lpData
0x18003d37d  xor     r8d, r8d; Reserved
0x18003d380  lea     rdx, aEnrollmentstat; "EnrollmentState"
0x18003d387  mov     rcx, rbx; hKey
0x18003d38a  call    cs:__imp_RegSetValueExW
0x18003d391  nop     dword ptr [rax+rax+00h]
0x18003d396  test    eax, eax
0x18003d398  jz      short loc_18003D3B0
0x18003d39a  jg      short loc_18003D3A0
0x18003d39c  mov     edi, eax
0x18003d39e  jmp     short loc_18003D3B0
0x18003d3a0  movzx   edi, ax
0x18003d3a3  or      edi, 80070000h
0x18003d3a9  jmp     short loc_18003D3B0
0x18003d3ab  mov     edi, 8000FFFFh
0x18003d3b0  test    rbx, rbx
0x18003d3b3  jz      short loc_18003D3C4
0x18003d3b5  mov     rcx, rbx; hKey
0x18003d3b8  call    cs:__imp_RegCloseKey
0x18003d3bf  nop     dword ptr [rax+rax+00h]
0x18003d3c4  mov     eax, edi
0x18003d3c6  mov     rcx, [rbp+30h+var_40]
0x18003d3ca  xor     rcx, rsp; StackCookie
0x18003d3cd  call    __security_check_cookie
0x18003d3d2  add     rsp, 108h
0x18003d3d9  pop     r15
0x18003d3db  pop     r14
0x18003d3dd  pop     rdi
0x18003d3de  pop     rsi
0x18003d3df  pop     rbx
0x18003d3e0  pop     rbp
0x18003d3e1  retn
```
