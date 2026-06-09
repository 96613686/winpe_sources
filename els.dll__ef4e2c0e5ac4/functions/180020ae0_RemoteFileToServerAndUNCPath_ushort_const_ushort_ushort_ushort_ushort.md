# RemoteFileToServerAndUNCPath(ushort const *,ushort *,ushort,ushort *,ushort)

- ea: `0x180020ae0`
- end: `0x180020c01`
- name: `?RemoteFileToServerAndUNCPath@@YAJPEBGPEAGG1G@Z`
- size: `289`
- prototype: `__int64 __usercall@<rax>(wchar_t *Source@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, unsigned __int16 *@<r9>, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007724`
- `0x180016cd4`

## callees

- `0x1800200d0`
- `0x180020ae0`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180020b66`
- `msvcrt!wcsncpy_s` at `0x180020b66`
- `KERNEL32!GetDriveTypeW` at `0x180020b95`
- `KERNEL32!GetDriveTypeW` at `0x180020b95`
- `MPR!WNetGetUniversalNameW` at `0x180020bb8`
- `MPR!WNetGetUniversalNameW` at `0x180020bb8`

## pseudocode

```c
__int64 __fastcall RemoteFileToServerAndUNCPath(
        wchar_t *Source,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned __int16 *a4,
        unsigned __int16 a5)
{
  wchar_t *v5; // rsi
  WCHAR v6; // cx
  unsigned int v7; // ebp
  unsigned __int16 v9; // r14
  unsigned __int16 *v10; // rbx
  DWORD BufferSize; // [rsp+20h] [rbp-278h] BYREF
  WCHAR RootPathName; // [rsp+28h] [rbp-270h] BYREF
  int v14; // [rsp+2Ah] [rbp-26Eh]
  wchar_t v15; // [rsp+2Eh] [rbp-26Ah]
  wchar_t *Buffer; // [rsp+30h] [rbp-268h] BYREF

  v5 = Source;
  v6 = *Source;
  v7 = 0;
  v14 = *(_DWORD *)L":\\";
  v9 = a3;
  v10 = a2;
  v15 = aC[3];
  RootPathName = v6;
  if ( v6 == 92 )
  {
    if ( v5[1] == 92 )
      goto LABEL_3;
    return 1;
  }
  if ( (unsigned __int16)(v6 - 65) > 0x19u && (unsigned __int16)(v6 - 97) > 0x19u
    || v5[1] != 58
    || GetDriveTypeW(&RootPathName) != 4 )
  {
    return 1;
  }
  BufferSize = 531;
  if ( WNetGetUniversalNameW(v5, 1u, &Buffer, &BufferSize) )
    return (unsigned int)-2147467259;
  v5 = Buffer;
  a3 = v9;
  a2 = v10;
LABEL_3:
  GetUncServer(v5, a2, a3);
  if ( a4 )
  {
    wcsncpy_s(a4, a5, v5, a5 - 1LL);
    a4[a5 - 1] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180020ae0  push    rbx
0x180020ae2  push    rbp
0x180020ae3  push    rsi
0x180020ae4  push    rdi
0x180020ae5  push    r14
0x180020ae7  push    r15
0x180020ae9  sub     rsp, 268h
0x180020af0  mov     rax, cs:__security_cookie
0x180020af7  xor     rax, rsp
0x180020afa  mov     [rsp+298h+var_48], rax
0x180020b02  mov     eax, dword ptr cs:aC+2; ":\\"
0x180020b08  mov     rsi, rcx
0x180020b0b  movzx   ecx, word ptr [rcx]
0x180020b0e  xor     ebp, ebp
0x180020b10  movzx   r15d, [rsp+298h+arg_20]
0x180020b19  mov     rdi, r9
0x180020b1c  mov     [rsp+298h+var_26E], eax
0x180020b20  movzx   r14d, r8w
0x180020b24  movzx   eax, word ptr cs:aC+6; ""
0x180020b2b  mov     rbx, rdx
0x180020b2e  mov     [rsp+298h+var_26A], ax
0x180020b33  mov     [rsp+298h+RootPathName], cx
0x180020b38  cmp     cx, 5Ch ; '\'
0x180020b3c  jnz     short loc_180020B76
0x180020b3e  cmp     [rsi+2], cx
0x180020b42  jnz     loc_180020BDA
0x180020b48  mov     rcx, rsi; Source
0x180020b4b  call    ?GetUncServer@@YAXPEBGPEAGG@Z; GetUncServer(ushort const *,ushort *,ushort)
0x180020b50  test    rdi, rdi
0x180020b53  jz      loc_180020BDF
0x180020b59  lea     r9, [r15-1]; MaxCount
0x180020b5d  mov     r8, rsi; Source
0x180020b60  mov     rdx, r15; SizeInWords
0x180020b63  mov     rcx, rdi; Destination
0x180020b66  call    cs:__imp_wcsncpy_s
0x180020b6c  xor     eax, eax
0x180020b6e  mov     [rdi+r15*2-2], ax
0x180020b74  jmp     short loc_180020BDF
0x180020b76  lea     eax, [rcx-41h]
0x180020b79  cmp     ax, 19h
0x180020b7d  jbe     short loc_180020B89
0x180020b7f  sub     cx, 61h ; 'a'
0x180020b83  cmp     cx, 19h
0x180020b87  ja      short loc_180020BDA
0x180020b89  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180020b8e  jnz     short loc_180020BDA
0x180020b90  lea     rcx, [rsp+298h+RootPathName]; lpRootPathName
0x180020b95  call    cs:__imp_GetDriveTypeW
0x180020b9b  cmp     eax, 4
0x180020b9e  jnz     short loc_180020BDA
0x180020ba0  lea     r9, [rsp+298h+BufferSize]; lpBufferSize
0x180020ba5  mov     [rsp+298h+BufferSize], 213h
0x180020bad  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x180020bb2  mov     rcx, rsi; lpLocalPath
0x180020bb5  lea     edx, [rax-3]; dwInfoLevel
0x180020bb8  call    cs:__imp_WNetGetUniversalNameW
0x180020bbe  test    eax, eax
0x180020bc0  jnz     short loc_180020BD3
0x180020bc2  mov     rsi, [rsp+298h+Buffer]
0x180020bc7  movzx   r8d, r14w
0x180020bcb  mov     rdx, rbx
0x180020bce  jmp     loc_180020B48
0x180020bd3  mov     ebp, 80004005h
0x180020bd8  jmp     short loc_180020BDF
0x180020bda  mov     ebp, 1
0x180020bdf  mov     eax, ebp
0x180020be1  mov     rcx, [rsp+298h+var_48]
0x180020be9  xor     rcx, rsp; StackCookie
0x180020bec  call    __security_check_cookie
0x180020bf1  add     rsp, 268h
0x180020bf8  pop     r15
0x180020bfa  pop     r14
0x180020bfc  pop     rdi
0x180020bfd  pop     rsi
0x180020bfe  pop     rbp
0x180020bff  pop     rbx
0x180020c00  retn
```
