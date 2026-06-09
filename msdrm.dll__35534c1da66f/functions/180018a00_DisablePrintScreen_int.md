# DisablePrintScreen(int)

- ea: `0x180018a00`
- end: `0x180018b6d`
- name: `?DisablePrintScreen@@YAJH@Z`
- size: `365`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x180002ed8`
- `0x1800046c8`
- `0x180018a00`
- `0x18005bdc0`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180018acd`
- `msvcrt!_itoa_s` at `0x180018acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b14`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180018b2d`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180018b2d`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomA` at `0x180018ad8`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomA` at `0x180018ad8`
- `USER32!UnregisterHotKey` at `0x180018aed`
- `USER32!UnregisterHotKey` at `0x180018aed`
- `USER32!RegisterHotKey` at `0x180018b0a`
- `USER32!RegisterHotKey` at `0x180018b0a`

## string_xrefs

- `0x180018b1c`: `RegisterHotKey for key-stroke combination %d failed with error %d`

## pseudocode

```c
__int64 __fastcall DisablePrintScreen(int a1)
{
  const char *v2; // r9
  __int64 v3; // rax
  CHAR *v4; // r8
  __int64 v5; // rdx
  CHAR *v6; // rax
  unsigned int v7; // edi
  __int64 v8; // rbp
  int i; // ebx
  unsigned __int64 v10; // rsi
  ATOM v11; // ax
  int v12; // ecx
  DWORD LastError; // eax
  CHAR String[32]; // [rsp+20h] [rbp-68h] BYREF

  v2 = "MSSNAP";
  v3 = 2147483646;
  v4 = String;
  v5 = 32;
  do
  {
    if ( !v3 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = v4 - 1;
  v7 = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v6 = v4;
  *v6 = 0;
  if ( v5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( String[v8] );
    for ( i = 0; i <= 15; ++i )
    {
      v10 = 2LL * (unsigned int)i;
      v11 = *(_WORD *)((char *)&g_rgatomSNAP + v10);
      if ( !v11 )
      {
        if ( !a1 )
          continue;
        _itoa_s(i, &String[(int)v8], (unsigned int)(32 - v8), 16);
        v11 = GlobalAddAtomA(String);
        *(_WORD *)((char *)&g_rgatomSNAP + v10) = v11;
        if ( !v11 )
          continue;
      }
      UnregisterHotKey(0, v11);
      v12 = *(unsigned __int16 *)((char *)&g_rgatomSNAP + v10);
      if ( a1 )
      {
        if ( !RegisterHotKey(0, v12, i, 0x2Cu) )
        {
          LastError = GetLastError();
          _RTLTRACE("RegisterHotKey for key-stroke combination %d failed with error %d", i, LastError);
        }
      }
      else
      {
        GlobalDeleteAtom(v12);
        if ( v10 >= 0x20 )
          _report_rangecheckfailure();
        *(_WORD *)((char *)&g_rgatomSNAP + v10) = 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180018a00  push    rbx
0x180018a02  push    rbp
0x180018a03  push    rsi
0x180018a04  push    rdi
0x180018a05  push    r12
0x180018a07  push    r14
0x180018a09  push    r15
0x180018a0b  sub     rsp, 50h
0x180018a0f  mov     rax, cs:__security_cookie
0x180018a16  xor     rax, rsp
0x180018a19  mov     [rsp+88h+var_48], rax
0x180018a1e  mov     r14d, ecx
0x180018a21  lea     r9, aMssnap; "MSSNAP"
0x180018a28  mov     eax, 7FFFFFFEh
0x180018a2d  lea     r8, [rsp+88h+String]
0x180018a32  mov     edx, 20h ; ' '
0x180018a37  xor     r15d, r15d
0x180018a3a  test    rax, rax
0x180018a3d  jz      short loc_180018A58
0x180018a3f  mov     cl, [r9]
0x180018a42  test    cl, cl
0x180018a44  jz      short loc_180018A58
0x180018a46  mov     [r8], cl
0x180018a49  inc     r9
0x180018a4c  inc     r8
0x180018a4f  dec     rax
0x180018a52  sub     rdx, 1
0x180018a56  jnz     short loc_180018A3A
0x180018a58  mov     rax, rdx
0x180018a5b  neg     rax
0x180018a5e  lea     rax, [r8-1]
0x180018a62  sbb     edi, edi
0x180018a64  not     edi
0x180018a66  and     edi, 8007007Ah
0x180018a6c  test    rdx, rdx
0x180018a6f  cmovnz  rax, r8
0x180018a73  mov     [rax], r15b
0x180018a76  jz      loc_180018B49
0x180018a7c  lea     rax, [rsp+88h+String]
0x180018a81  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180018a85  inc     rbp
0x180018a88  cmp     [rax+rbp], r15b
0x180018a8c  jnz     short loc_180018A85
0x180018a8e  mov     ebx, r15d
0x180018a91  mov     eax, ebx
0x180018a93  lea     r12, ?g_rgatomSNAP@@3PAGA; ushort near * g_rgatomSNAP
0x180018a9a  lea     rsi, [rax+rax]
0x180018a9e  movzx   eax, word ptr [rsi+r12]
0x180018aa3  test    ax, ax
0x180018aa6  jnz     short loc_180018AE8
0x180018aa8  test    r14d, r14d
0x180018aab  jz      loc_180018B3E
0x180018ab1  mov     r8d, 20h ; ' '
0x180018ab7  movsxd  rax, ebp
0x180018aba  lea     rdx, [rsp+88h+String]
0x180018abf  sub     r8d, ebp; BufferCount
0x180018ac2  add     rdx, rax; Buffer
0x180018ac5  mov     r9d, 10h; Radix
0x180018acb  mov     ecx, ebx; Value
0x180018acd  call    cs:__imp__itoa_s
0x180018ad3  lea     rcx, [rsp+88h+String]; lpString
0x180018ad8  call    cs:__imp_GlobalAddAtomA
0x180018ade  mov     [rsi+r12], ax
0x180018ae3  test    ax, ax
0x180018ae6  jz      short loc_180018B3E
0x180018ae8  movzx   edx, ax; id
0x180018aeb  xor     ecx, ecx; hWnd
0x180018aed  call    cs:__imp_UnregisterHotKey
0x180018af3  movzx   ecx, word ptr [rsi+r12]; nAtom
0x180018af8  test    r14d, r14d
0x180018afb  jz      short loc_180018B2D
0x180018afd  mov     edx, ecx; id
0x180018aff  mov     r9d, 2Ch ; ','; vk
0x180018b05  xor     ecx, ecx; hWnd
0x180018b07  mov     r8d, ebx; fsModifiers
0x180018b0a  call    cs:__imp_RegisterHotKey
0x180018b10  test    eax, eax
0x180018b12  jnz     short loc_180018B3E
0x180018b14  call    cs:__imp_GetLastError
0x180018b1a  mov     edx, ebx
0x180018b1c  lea     rcx, aRegisterhotkey_0; "RegisterHotKey for key-stroke combinati"...
0x180018b23  mov     r8d, eax
0x180018b26  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180018b2b  jmp     short loc_180018B3E
0x180018b2d  call    cs:__imp_GlobalDeleteAtom
0x180018b33  cmp     rsi, 20h ; ' '
0x180018b37  jnb     short loc_180018B67
0x180018b39  mov     [rsi+r12], r15w
0x180018b3e  inc     ebx
0x180018b40  cmp     ebx, 0Fh
0x180018b43  jle     loc_180018A91
0x180018b49  mov     eax, edi
0x180018b4b  mov     rcx, [rsp+88h+var_48]
0x180018b50  xor     rcx, rsp; StackCookie
0x180018b53  call    __security_check_cookie
0x180018b58  add     rsp, 50h
0x180018b5c  pop     r15
0x180018b5e  pop     r14
0x180018b60  pop     r12
0x180018b62  pop     rdi
0x180018b63  pop     rsi
0x180018b64  pop     rbp
0x180018b65  pop     rbx
0x180018b66  retn
0x180018b67  call    __report_rangecheckfailure
```
