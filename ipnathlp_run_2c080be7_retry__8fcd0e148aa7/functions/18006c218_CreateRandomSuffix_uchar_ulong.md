# CreateRandomSuffix(uchar *,ulong)

- ea: `0x18006c218`
- end: `0x18006c3da`
- name: `?CreateRandomSuffix@@YAKPEAEK@Z`
- size: `450`
- prototype: `unsigned int __fastcall(BYTE *pbBuffer, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006c6a8`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180051f30`
- `0x18006c218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c338`
- `RPCRT4!UuidCreate` at `0x18006c281`
- `RPCRT4!UuidCreate` at `0x18006c281`
- `CRYPTSP!CryptGenRandom` at `0x18006c328`
- `CRYPTSP!CryptGenRandom` at `0x18006c328`
- `CRYPTSP!CryptAcquireContextW` at `0x18006c2de`
- `CRYPTSP!CryptAcquireContextW` at `0x18006c2de`
- `CRYPTSP!CryptReleaseContext` at `0x18006c388`
- `CRYPTSP!CryptReleaseContext` at `0x18006c388`

## pseudocode

```c
__int64 __fastcall CreateRandomSuffix(BYTE *pbBuffer)
{
  unsigned int v2; // eax
  DWORD LastError; // eax
  DWORD v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  HCRYPTPROV phProv; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
  phProv = 0;
  Uuid = 0;
  v2 = UuidCreate(&Uuid);
  if ( v2
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v2);
  }
  *(UUID *)pbBuffer = Uuid;
  if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000040) )
  {
    v4 = 0;
    if ( CryptGenRandom(phProv, 0x10u, pbBuffer) )
    {
LABEL_21:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 33;
      goto LABEL_20;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 32;
LABEL_20:
      WPP_SF_d(v5[2], v6, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, LastError);
      goto LABEL_21;
    }
  }
LABEL_22:
  if ( phProv )
  {
    CryptReleaseContext(phProv, 0);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && *((char *)v5 + 28) < 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 34, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18006c218  push    rbx
0x18006c21a  push    rbp
0x18006c21b  push    rdi
0x18006c21c  push    r14
0x18006c21e  sub     rsp, 58h
0x18006c222  mov     rax, cs:__security_cookie
0x18006c229  xor     rax, rsp
0x18006c22c  mov     [rsp+78h+var_30], rax
0x18006c231  mov     rdi, rcx
0x18006c234  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c23b  lea     rbp, WPP_GLOBAL_Control
0x18006c242  lea     r14, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18006c249  cmp     rcx, rbp
0x18006c24c  jz      short loc_18006C26B
0x18006c24e  test    byte ptr [rcx+1Ch], 80h
0x18006c252  jz      short loc_18006C26B
0x18006c254  cmp     byte ptr [rcx+19h], 6
0x18006c258  jb      short loc_18006C26B
0x18006c25a  mov     rcx, [rcx+10h]
0x18006c25e  mov     edx, 1Eh
0x18006c263  mov     r8, r14
0x18006c266  call    WPP_SF_
0x18006c26b  xorps   xmm0, xmm0
0x18006c26e  mov     [rsp+78h+phProv], 0
0x18006c277  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18006c27c  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18006c281  call    cs:__imp_UuidCreate
0x18006c288  nop     dword ptr [rax+rax+00h]
0x18006c28d  test    eax, eax
0x18006c28f  jz      short loc_18006C2BD
0x18006c291  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c298  cmp     rcx, rbp
0x18006c29b  jz      short loc_18006C2BD
0x18006c29d  test    byte ptr [rcx+1Ch], 80h
0x18006c2a1  jz      short loc_18006C2BD
0x18006c2a3  cmp     byte ptr [rcx+19h], 2
0x18006c2a7  jb      short loc_18006C2BD
0x18006c2a9  mov     rcx, [rcx+10h]
0x18006c2ad  mov     edx, 1Fh
0x18006c2b2  mov     r9d, eax
0x18006c2b5  mov     r8, r14
0x18006c2b8  call    WPP_SF_d
0x18006c2bd  movups  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x18006c2c2  mov     r9d, 1; dwProvType
0x18006c2c8  mov     [rsp+78h+dwFlags], 0F0000040h; dwFlags
0x18006c2d0  xor     r8d, r8d; szProvider
0x18006c2d3  lea     rcx, [rsp+78h+phProv]; phProv
0x18006c2d8  xor     edx, edx; szContainer
0x18006c2da  movdqu  xmmword ptr [rdi], xmm0
0x18006c2de  call    cs:__imp_CryptAcquireContextW
0x18006c2e5  nop     dword ptr [rax+rax+00h]
0x18006c2ea  test    eax, eax
0x18006c2ec  jnz     short loc_18006C31B
0x18006c2ee  call    cs:__imp_GetLastError
0x18006c2f5  nop     dword ptr [rax+rax+00h]
0x18006c2fa  mov     ebx, eax
0x18006c2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c303  cmp     rcx, rbp
0x18006c306  jz      short loc_18006C379
0x18006c308  test    byte ptr [rcx+1Ch], 80h
0x18006c30c  jz      short loc_18006C379
0x18006c30e  cmp     byte ptr [rcx+19h], 2
0x18006c312  jb      short loc_18006C379
0x18006c314  mov     edx, 20h ; ' '
0x18006c319  jmp     short loc_18006C363
0x18006c31b  mov     rcx, [rsp+78h+phProv]; hProv
0x18006c320  xor     ebx, ebx
0x18006c322  mov     r8, rdi; pbBuffer
0x18006c325  lea     edx, [rbx+10h]; dwLen
0x18006c328  call    cs:__imp_CryptGenRandom
0x18006c32f  nop     dword ptr [rax+rax+00h]
0x18006c334  test    eax, eax
0x18006c336  jnz     short loc_18006C372
0x18006c338  call    cs:__imp_GetLastError
0x18006c33f  nop     dword ptr [rax+rax+00h]
0x18006c344  mov     ebx, eax
0x18006c346  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c34d  cmp     rcx, rbp
0x18006c350  jz      short loc_18006C379
0x18006c352  test    byte ptr [rcx+1Ch], 80h
0x18006c356  jz      short loc_18006C379
0x18006c358  cmp     byte ptr [rcx+19h], 2
0x18006c35c  jb      short loc_18006C379
0x18006c35e  mov     edx, 21h ; '!'
0x18006c363  mov     rcx, [rcx+10h]
0x18006c367  mov     r9d, eax
0x18006c36a  mov     r8, r14
0x18006c36d  call    WPP_SF_d
0x18006c372  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c379  mov     rax, [rsp+78h+phProv]
0x18006c37e  test    rax, rax
0x18006c381  jz      short loc_18006C39B
0x18006c383  xor     edx, edx; dwFlags
0x18006c385  mov     rcx, rax; hProv
0x18006c388  call    cs:__imp_CryptReleaseContext
0x18006c38f  nop     dword ptr [rax+rax+00h]
0x18006c394  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c39b  cmp     rcx, rbp
0x18006c39e  jz      short loc_18006C3C0
0x18006c3a0  test    byte ptr [rcx+1Ch], 80h
0x18006c3a4  jz      short loc_18006C3C0
0x18006c3a6  cmp     byte ptr [rcx+19h], 6
0x18006c3aa  jb      short loc_18006C3C0
0x18006c3ac  mov     rcx, [rcx+10h]
0x18006c3b0  mov     edx, 22h ; '"'
0x18006c3b5  mov     r9d, ebx
0x18006c3b8  mov     r8, r14
0x18006c3bb  call    WPP_SF_d
0x18006c3c0  mov     eax, ebx
0x18006c3c2  mov     rcx, [rsp+78h+var_30]
0x18006c3c7  xor     rcx, rsp; StackCookie
0x18006c3ca  call    __security_check_cookie
0x18006c3cf  add     rsp, 58h
0x18006c3d3  pop     r14
0x18006c3d5  pop     rdi
0x18006c3d6  pop     rbp
0x18006c3d7  pop     rbx
0x18006c3d8  retn
```
