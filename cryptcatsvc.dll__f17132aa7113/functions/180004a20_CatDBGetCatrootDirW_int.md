# _CatDBGetCatrootDirW(int)

- ea: `0x180004a20`
- end: `0x180004b90`
- name: `?_CatDBGetCatrootDirW@@YAPEAGH@Z`
- size: `368`
- prototype: `unsigned __int16 *__fastcall(int)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180001264`
- `0x180004824`
- `0x18000ad54`
- `0x18001344c`
- `0x18001d184`
- `0x18001d62c`

## callees

- `0x180003538`
- `0x180004170`
- `0x1800041ec`
- `0x180004a20`
- `0x18000a59c`
- `0x18000a918`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ae9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180004a7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180004a7d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180004a57`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180004a57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall _CatDBGetCatrootDirW(int a1)
{
  WCHAR *v1; // rsi
  __int64 v2; // rdi
  unsigned int v5; // edx
  unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // edx
  unsigned __int64 v9; // r14
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  const unsigned __int16 *v14; // r8
  int v15; // [rsp+28h] [rbp-260h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  v1 = (WCHAR *)qword_180032A90;
  v2 = -1;
  if ( qword_180032A90 )
  {
    v8 = dword_180032A88 + 3;
  }
  else
  {
    if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
      return _CatDBGetPersistedCatrootDirW(a1);
    Buffer[0] = 0;
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      ErrLog_LogError(v6, v5, 0xDEu, 0, 0, v15);
      return 0;
    }
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    v8 = v7 + 3;
    v1 = Buffer;
  }
  v9 = v8 + (unsigned int)(a1 != 0) + 7;
  v10 = (unsigned __int16 *)_CatDBAlloc(2 * v9);
  v11 = v10;
  if ( v10 )
  {
    StringCchCopyW(v10, v9, v1);
    if ( *v11 )
    {
      do
        ++v2;
      while ( v11[v2] );
      if ( v11[v2 - 1] != 92 )
        StringCchCatW(v11, v9, L"\\");
    }
    v14 = L"CatRoot2";
    if ( !a1 )
      v14 = L"CatRoot";
    StringCchCatW(v11, v9, v14);
    StringCchCatW(v11, v9, L"\\");
  }
  else
  {
    SetLastError(8u);
    ErrLog_LogError(v13, v12, 0xF9u, 0, 0, v15);
  }
  return v11;
}

```

## disassembly

```asm
0x180004a20  push    rbx
0x180004a22  push    rbp
0x180004a23  push    rsi
0x180004a24  push    rdi
0x180004a25  push    r14
0x180004a27  push    r15
0x180004a29  sub     rsp, 258h
0x180004a30  mov     rax, cs:__security_cookie
0x180004a37  xor     rax, rsp
0x180004a3a  mov     [rsp+288h+var_48], rax
0x180004a42  mov     rsi, cs:qword_180032A90
0x180004a49  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004a4d  xor     r15d, r15d
0x180004a50  mov     ebp, ecx
0x180004a52  test    rsi, rsi
0x180004a55  jnz     short loc_180004ABD
0x180004a57  call    cs:__imp_RtlIsStateSeparationEnabled
0x180004a5d  test    al, al
0x180004a5f  jz      short loc_180004A6D
0x180004a61  mov     ecx, ebp; int
0x180004a63  call    ?_CatDBGetPersistedCatrootDirW@@YAPEAGH@Z; _CatDBGetPersistedCatrootDirW(int)
0x180004a68  jmp     loc_180004B70
0x180004a6d  mov     edx, 104h; uSize
0x180004a72  mov     [rsp+288h+Buffer], r15w
0x180004a78  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x180004a7d  call    cs:__imp_GetSystemDirectoryW
0x180004a83  test    eax, eax
0x180004a85  jnz     short loc_180004AA1
0x180004a87  xor     r9d, r9d; unsigned int
0x180004a8a  mov     [rsp+288h+var_268], r15d; int
0x180004a8f  mov     r8d, 0DEh; unsigned int
0x180004a95  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180004a9a  xor     eax, eax
0x180004a9c  jmp     loc_180004B70
0x180004aa1  lea     rcx, [rsp+288h+Buffer]
0x180004aa6  mov     rax, rdi
0x180004aa9  inc     rax
0x180004aac  cmp     [rcx+rax*2], r15w
0x180004ab1  jnz     short loc_180004AA9
0x180004ab3  lea     edx, [rax+3]
0x180004ab6  lea     rsi, [rsp+288h+Buffer]
0x180004abb  jmp     short loc_180004AC6
0x180004abd  mov     edx, cs:dword_180032A88
0x180004ac3  add     edx, 3
0x180004ac6  mov     eax, ebp
0x180004ac8  neg     eax
0x180004aca  sbb     ecx, ecx
0x180004acc  neg     ecx
0x180004ace  add     ecx, 7
0x180004ad1  add     ecx, edx
0x180004ad3  mov     r14d, ecx
0x180004ad6  add     rcx, rcx; uBytes
0x180004ad9  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x180004ade  mov     rbx, rax
0x180004ae1  test    rax, rax
0x180004ae4  jnz     short loc_180004B04
0x180004ae6  lea     ecx, [rax+8]; dwErrCode
0x180004ae9  call    cs:__imp_SetLastError
0x180004aef  xor     r9d, r9d; unsigned int
0x180004af2  mov     [rsp+288h+var_268], r15d; int
0x180004af7  mov     r8d, 0F9h; unsigned int
0x180004afd  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180004b02  jmp     short loc_180004B6D
0x180004b04  mov     r8, rsi; unsigned __int16 *
0x180004b07  mov     rdx, r14; unsigned __int64
0x180004b0a  mov     rcx, rbx; unsigned __int16 *
0x180004b0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b12  cmp     [rbx], r15w
0x180004b16  jz      short loc_180004B3C
0x180004b18  inc     rdi
0x180004b1b  cmp     [rbx+rdi*2], r15w
0x180004b20  jnz     short loc_180004B18
0x180004b22  cmp     word ptr [rbx+rdi*2-2], 5Ch ; '\'
0x180004b28  jz      short loc_180004B3C
0x180004b2a  lea     r8, asc_18002564C; "\\"
0x180004b31  mov     rdx, r14; unsigned __int64
0x180004b34  mov     rcx, rbx; unsigned __int16 *
0x180004b37  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b3c  lea     rax, aCatroot; "CatRoot"
0x180004b43  test    ebp, ebp
0x180004b45  lea     r8, aCatroot2; "CatRoot2"
0x180004b4c  mov     rdx, r14; unsigned __int64
0x180004b4f  cmovz   r8, rax; unsigned __int16 *
0x180004b53  mov     rcx, rbx; unsigned __int16 *
0x180004b56  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b5b  lea     r8, asc_18002564C; "\\"
0x180004b62  mov     rdx, r14; unsigned __int64
0x180004b65  mov     rcx, rbx; unsigned __int16 *
0x180004b68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b6d  mov     rax, rbx
0x180004b70  mov     rcx, [rsp+288h+var_48]
0x180004b78  xor     rcx, rsp; StackCookie
0x180004b7b  call    __security_check_cookie
0x180004b80  add     rsp, 258h
0x180004b87  pop     r15
0x180004b89  pop     r14
0x180004b8b  pop     rdi
0x180004b8c  pop     rsi
0x180004b8d  pop     rbp
0x180004b8e  pop     rbx
0x180004b8f  retn
```
