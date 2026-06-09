# DumpChainOpenHash(unsigned __int64 *,unsigned __int64 *)

- ea: `0x18001a008`
- end: `0x18001a0d2`
- name: `?DumpChainOpenHash@@YAJPEA_K0@Z`
- size: `202`
- prototype: `__int64 __fastcall(unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b07c`

## callees

- `0x180008400`
- `0x180012450`
- `0x18001a008`

## import_xrefs

- `CRYPTSP!CryptAcquireContextW` at `0x18001a03d`
- `CRYPTSP!CryptAcquireContextW` at `0x18001a03d`
- `CRYPTSP!CryptReleaseContext` at `0x18001a09f`
- `CRYPTSP!CryptReleaseContext` at `0x18001a09f`
- `CRYPTSP!CryptCreateHash` at `0x18001a06d`
- `CRYPTSP!CryptCreateHash` at `0x18001a06d`

## pseudocode

```c
__int64 __fastcall DumpChainOpenHash(unsigned __int64 *a1, unsigned __int64 *a2)
{
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // ebx

  *a1 = 0;
  *a2 = 0;
  if ( CryptAcquireContextW(a1, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    if ( CryptCreateHash(*a1, 0x8004u, 0, 0, a2) )
      return 0;
    *a2 = 0;
    v4 = myHLastError();
    v5 = 305004963;
  }
  else
  {
    *a1 = 0;
    v4 = myHLastError();
    v5 = 304546211;
  }
  v6 = v4;
  CSPrintErrorLineFile(v5, v4);
  if ( v6 && *a1 )
  {
    if ( !CryptReleaseContext(*a1, 0) )
    {
      myHLastError();
      CSPrintErrorLineFile(0x123901A3u, v6);
    }
    *a1 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18001a008  mov     [rsp+arg_0], rbx
0x18001a00d  push    rdi
0x18001a00e  sub     rsp, 30h
0x18001a012  mov     qword ptr [rcx], 0
0x18001a019  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18001a020  mov     qword ptr [rdx], 0
0x18001a027  mov     rbx, rdx
0x18001a02a  xor     edx, edx; szContainer
0x18001a02c  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x18001a034  mov     r9d, 1; dwProvType
0x18001a03a  mov     rdi, rcx
0x18001a03d  call    cs:__imp_CryptAcquireContextW
0x18001a043  test    eax, eax
0x18001a045  jnz     short loc_18001A05A
0x18001a047  mov     qword ptr [rdi], 0
0x18001a04e  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a053  mov     ecx, 122701A3h
0x18001a058  jmp     short loc_18001A088
0x18001a05a  mov     rcx, [rdi]; hProv
0x18001a05d  xor     r9d, r9d; dwFlags
0x18001a060  xor     r8d, r8d; hKey
0x18001a063  mov     qword ptr [rsp+38h+dwFlags], rbx; phHash
0x18001a068  mov     edx, 8004h; Algid
0x18001a06d  call    cs:__imp_CryptCreateHash
0x18001a073  test    eax, eax
0x18001a075  jnz     short loc_18001A0C3
0x18001a077  mov     qword ptr [rbx], 0
0x18001a07e  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a083  mov     ecx, 122E01A3h; unsigned int
0x18001a088  mov     edx, eax; int
0x18001a08a  mov     ebx, eax
0x18001a08c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a091  test    ebx, ebx
0x18001a093  jz      short loc_18001A0C5
0x18001a095  mov     rcx, [rdi]; hProv
0x18001a098  test    rcx, rcx
0x18001a09b  jz      short loc_18001A0C5
0x18001a09d  xor     edx, edx; dwFlags
0x18001a09f  call    cs:__imp_CryptReleaseContext
0x18001a0a5  test    eax, eax
0x18001a0a7  jnz     short loc_18001A0BA
0x18001a0a9  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a0ae  mov     edx, ebx; int
0x18001a0b0  mov     ecx, 123901A3h; unsigned int
0x18001a0b5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a0ba  mov     qword ptr [rdi], 0
0x18001a0c1  jmp     short loc_18001A0C5
0x18001a0c3  xor     ebx, ebx
0x18001a0c5  mov     eax, ebx
0x18001a0c7  mov     rbx, [rsp+38h+arg_0]
0x18001a0cc  add     rsp, 30h
0x18001a0d0  pop     rdi
0x18001a0d1  retn
```
