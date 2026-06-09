# RefCountedTokenPrivilegesCore(itkpEnum,bool)

- ea: `0x140006d4c`
- end: `0x140006df1`
- name: `?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z`
- size: `165`
- prototype: `bool __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400078f0`

## callees

- `0x140003883`
- `0x140003ce4`
- `0x140006d4c`

## import_xrefs

- `KERNEL32!Sleep` at `0x140006d6c`
- `KERNEL32!Sleep` at `0x140006d6c`

## pseudocode

```c
bool __fastcall RefCountedTokenPrivilegesCore(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  bool v4; // bl
  int v5; // edi
  bool result; // al

  v4 = 1;
  while ( _InterlockedExchange(&dword_140010E68, 1) == 1 )
    Sleep(0xAu);
  if ( !byte_140010DD8 )
  {
    memset_0(&g_pTokenPrivilegesRefCount, 0, 0x70u);
    byte_140010DD8 = 1;
  }
  v5 = (int)g_pTokenPrivilegesRefCount;
  LODWORD(g_pTokenPrivilegesRefCount) = (_DWORD)g_pTokenPrivilegesRefCount + 1;
  if ( (_DWORD)g_pTokenPrivilegesRefCount == 1 )
  {
    v4 = AdjustTokenPrivileges(
           (const unsigned __int16 **)&pszTOKEN_PRIVILEGES_SD_READ,
           1,
           a3,
           a4,
           &stru_140010A64,
           &dword_140010A94);
    if ( !v4 )
      LODWORD(g_pTokenPrivilegesRefCount) = v5;
  }
  result = v4;
  dword_140010E68 = 0;
  return result;
}

```

## disassembly

```asm
0x140006d4c  mov     [rsp+arg_0], rbx
0x140006d51  push    rdi
0x140006d52  sub     rsp, 30h
0x140006d56  mov     ebx, 1
0x140006d5b  mov     eax, ebx
0x140006d5d  xchg    eax, cs:dword_140010E68
0x140006d63  cmp     eax, ebx
0x140006d65  jnz     short loc_140006D74
0x140006d67  mov     ecx, 0Ah; dwMilliseconds
0x140006d6c  call    cs:__imp_Sleep
0x140006d72  jmp     short loc_140006D5B
0x140006d74  cmp     cs:byte_140010DD8, 0
0x140006d7b  jnz     short loc_140006D95
0x140006d7d  xor     edx, edx; Val
0x140006d7f  lea     rcx, ?g_pTokenPrivilegesRefCount@@3PAUtagTokenPrivilegesRefCount@@A; void *
0x140006d86  lea     r8d, [rdx+70h]; Size
0x140006d8a  call    memset_0
0x140006d8f  mov     cs:byte_140010DD8, bl
0x140006d95  mov     edi, cs:?g_pTokenPrivilegesRefCount@@3PAUtagTokenPrivilegesRefCount@@A; tagTokenPrivilegesRefCount near * g_pTokenPrivilegesRefCount
0x140006d9b  lea     eax, [rdi+1]
0x140006d9e  mov     cs:?g_pTokenPrivilegesRefCount@@3PAUtagTokenPrivilegesRefCount@@A, eax; tagTokenPrivilegesRefCount near * g_pTokenPrivilegesRefCount
0x140006da4  cmp     eax, ebx
0x140006da6  jnz     short loc_140006DDA
0x140006da8  lea     rax, dword_140010A94
0x140006daf  mov     edx, ebx; int
0x140006db1  mov     [rsp+38h+var_10], rax; PDWORD
0x140006db6  lea     rcx, ?pszTOKEN_PRIVILEGES_SD_READ@@3PAPEBGA; unsigned __int16 **
0x140006dbd  lea     rax, stru_140010A64
0x140006dc4  mov     [rsp+38h+var_18], rax; PTOKEN_PRIVILEGES
0x140006dc9  call    ?AdjustTokenPrivileges@@YA_NPEAPEBGH_NKPEAU_TOKEN_PRIVILEGES@@PEAK@Z; AdjustTokenPrivileges(ushort const * *,int,bool,ulong,_TOKEN_PRIVILEGES *,ulong *)
0x140006dce  mov     bl, al
0x140006dd0  test    al, al
0x140006dd2  jnz     short loc_140006DDA
0x140006dd4  mov     cs:?g_pTokenPrivilegesRefCount@@3PAUtagTokenPrivilegesRefCount@@A, edi; tagTokenPrivilegesRefCount near * g_pTokenPrivilegesRefCount
0x140006dda  mov     al, bl
0x140006ddc  mov     cs:dword_140010E68, 0
0x140006de6  mov     rbx, [rsp+38h+arg_0]
0x140006deb  add     rsp, 30h
0x140006def  pop     rdi
0x140006df0  retn
```
