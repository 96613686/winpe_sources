# FTP_SESSION::GetSanitizedFullVirtualPath(ushort const *,ulong,STRU *)

- ea: `0x180033c70`
- end: `0x180033d34`
- name: `?GetSanitizedFullVirtualPath@FTP_SESSION@@QEAAJPEBGKPEAVSTRU@@@Z`
- size: `196`
- prototype: `int __fastcall(FTP_SESSION *this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800386dc`
- `0x180038f98`
- `0x1800396b0`
- `0x180039b14`
- `0x18003ba60`
- `0x18003bb70`
- `0x18003bd0c`
- `0x18003c024`
- `0x18003c19c`
- `0x18003c51c`
- `0x180042540`
- `0x180043510`

## callees

- `0x18002bf04`
- `0x180033c70`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180033cc6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180033cd9`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180033cc6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180033cd9`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180033cf3`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180033d16`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180033cf3`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180033d16`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180033d2a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180033d2a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180033ca7`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180033ca7`

## pseudocode

```c
int __fastcall FTP_SESSION::GetSanitizedFullVirtualPath(
        FTP_SESSION *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  int result; // eax
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned __int16 *v10; // rax

  if ( *a2 == 47 || *a2 == 92 )
  {
    result = STRU::Copy((STRU *)a4, a2);
  }
  else
  {
    result = STRU::Copy((STRU *)a4, *((const unsigned __int16 **)this + 606), *((_DWORD *)this + 1216));
    if ( result < 0 )
      return result;
    if ( !*a2 )
      return 0;
    result = STRU::Append((STRU *)a4, L"/", 1u);
    if ( result < 0 )
      return result;
    result = STRU::Append((STRU *)a4, a2, a3);
  }
  if ( result >= 0 )
  {
    result = FtpSanitizePath(a4[4]);
    if ( result >= 0 )
    {
      STRU::SyncWithBuffer((STRU *)a4);
      v8 = *((_DWORD *)a4 + 12);
      if ( v8 > 1 )
      {
        v9 = v8 - 1;
        v10 = a4[4];
        if ( v10[v9] == 47 )
        {
          v10[v9] = 0;
          STRU::SyncWithBuffer((STRU *)a4);
        }
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180033c70  push    rbx
0x180033c72  push    rbp
0x180033c73  push    rsi
0x180033c74  push    rdi
0x180033c75  sub     rsp, 28h
0x180033c79  cmp     word ptr [rdx], 2Fh ; '/'
0x180033c7d  mov     rdi, r9
0x180033c80  mov     ebp, r8d
0x180033c83  mov     rsi, rdx
0x180033c86  jz      loc_180033D27
0x180033c8c  cmp     word ptr [rdx], 5Ch ; '\'
0x180033c90  jz      loc_180033D27
0x180033c96  mov     r8d, [rcx+1300h]
0x180033c9d  mov     rdx, [rcx+12F0h]
0x180033ca4  mov     rcx, r9
0x180033ca7  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180033cad  xor     ebx, ebx
0x180033caf  test    eax, eax
0x180033cb1  js      short loc_180033D1E
0x180033cb3  cmp     [rsi], bx
0x180033cb6  jz      short loc_180033D1C
0x180033cb8  lea     r8d, [rbx+1]
0x180033cbc  mov     rcx, rdi
0x180033cbf  lea     rdx, asc_18004BD14; "/"
0x180033cc6  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180033ccc  test    eax, eax
0x180033cce  js      short loc_180033D1E
0x180033cd0  mov     r8d, ebp
0x180033cd3  mov     rdx, rsi
0x180033cd6  mov     rcx, rdi
0x180033cd9  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180033cdf  test    eax, eax
0x180033ce1  js      short loc_180033D1E
0x180033ce3  mov     rcx, [rdi+20h]; unsigned __int16 *
0x180033ce7  call    ?FtpSanitizePath@@YAJPEAG@Z; FtpSanitizePath(ushort *)
0x180033cec  test    eax, eax
0x180033cee  js      short loc_180033D1E
0x180033cf0  mov     rcx, rdi
0x180033cf3  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180033cf9  mov     eax, [rdi+30h]
0x180033cfc  cmp     eax, 1
0x180033cff  jbe     short loc_180033D1C
0x180033d01  lea     ecx, [rax-1]
0x180033d04  mov     rax, [rdi+20h]
0x180033d08  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x180033d0d  jnz     short loc_180033D1C
0x180033d0f  mov     [rax+rcx*2], bx
0x180033d13  mov     rcx, rdi
0x180033d16  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180033d1c  mov     eax, ebx
0x180033d1e  add     rsp, 28h
0x180033d22  pop     rdi
0x180033d23  pop     rsi
0x180033d24  pop     rbp
0x180033d25  pop     rbx
0x180033d26  retn
0x180033d27  mov     rcx, rdi
0x180033d2a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180033d30  xor     ebx, ebx
0x180033d32  jmp     short loc_180033CDF
```
