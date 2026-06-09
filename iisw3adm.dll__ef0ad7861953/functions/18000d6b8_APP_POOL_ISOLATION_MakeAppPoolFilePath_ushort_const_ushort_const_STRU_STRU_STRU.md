# APP_POOL_ISOLATION::MakeAppPoolFilePath(ushort const *,ushort const *,STRU *,STRU *,STRU *)

- ea: `0x18000d6b8`
- end: `0x18000d785`
- name: `?MakeAppPoolFilePath@APP_POOL_ISOLATION@@SAJPEBG0PEAVSTRU@@11@Z`
- size: `205`
- prototype: `int __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct STRU *, struct STRU *, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x18000cc40`
- `0x18000e1f0`

## callees

- `0x18000d6b8`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d6fa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d6fa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d70a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d72e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d73e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d752`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d776`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d70a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d72e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d73e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d752`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d776`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18000d71a`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18000d762`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18000d71a`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18000d762`

## string_xrefs

- `0x18000d748`: `.config`

## pseudocode

```c
int __fastcall APP_POOL_ISOLATION::MakeAppPoolFilePath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct STRU *a3,
        struct STRU *a4,
        struct STRU *a5)
{
  int result; // eax

  **((_WORD **)a3 + 4) = 0;
  *((_DWORD *)a3 + 12) = 0;
  **((_WORD **)a4 + 4) = 0;
  *((_DWORD *)a4 + 12) = 0;
  **((_WORD **)a5 + 4) = 0;
  *((_DWORD *)a5 + 12) = 0;
  result = STRU::Copy(a3, a1);
  if ( result >= 0 )
  {
    result = STRU::Append(a3, a2);
    if ( result >= 0 )
    {
      result = STRU::Copy(a4, a3);
      if ( result >= 0 )
      {
        result = STRU::Append(a4, L"\\");
        if ( result >= 0 )
        {
          result = STRU::Append(a4, a2);
          if ( result >= 0 )
          {
            result = STRU::Append(a4, L".config");
            if ( result >= 0 )
            {
              result = STRU::Copy(a5, a4);
              if ( result >= 0 )
                return STRU::Append(a5, L".tmp");
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d6b8  push    rbx
0x18000d6ba  push    rbp
0x18000d6bb  push    rsi
0x18000d6bc  push    rdi
0x18000d6bd  sub     rsp, 28h
0x18000d6c1  mov     r10, [r8+20h]
0x18000d6c5  xor     eax, eax
0x18000d6c7  mov     rsi, [rsp+48h+arg_20]
0x18000d6cc  mov     rbx, r9
0x18000d6cf  mov     rbp, rdx
0x18000d6d2  mov     rdi, r8
0x18000d6d5  mov     rdx, rcx
0x18000d6d8  mov     rcx, r8
0x18000d6db  mov     [r10], ax
0x18000d6df  mov     [r8+30h], eax
0x18000d6e3  mov     r10, [r9+20h]
0x18000d6e7  mov     [r10], ax
0x18000d6eb  mov     [r9+30h], eax
0x18000d6ef  mov     r9, [rsi+20h]
0x18000d6f3  mov     [r9], ax
0x18000d6f7  mov     [rsi+30h], eax
0x18000d6fa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d700  test    eax, eax
0x18000d702  js      short loc_18000D77C
0x18000d704  mov     rdx, rbp
0x18000d707  mov     rcx, rdi
0x18000d70a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d710  test    eax, eax
0x18000d712  js      short loc_18000D77C
0x18000d714  mov     rdx, rdi
0x18000d717  mov     rcx, rbx
0x18000d71a  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x18000d720  test    eax, eax
0x18000d722  js      short loc_18000D77C
0x18000d724  lea     rdx, asc_180065770; "\\"
0x18000d72b  mov     rcx, rbx
0x18000d72e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d734  test    eax, eax
0x18000d736  js      short loc_18000D77C
0x18000d738  mov     rdx, rbp
0x18000d73b  mov     rcx, rbx
0x18000d73e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d744  test    eax, eax
0x18000d746  js      short loc_18000D77C
0x18000d748  lea     rdx, aConfig; ".config"
0x18000d74f  mov     rcx, rbx
0x18000d752  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d758  test    eax, eax
0x18000d75a  js      short loc_18000D77C
0x18000d75c  mov     rdx, rbx
0x18000d75f  mov     rcx, rsi
0x18000d762  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x18000d768  test    eax, eax
0x18000d76a  js      short loc_18000D77C
0x18000d76c  lea     rdx, aTmp; ".tmp"
0x18000d773  mov     rcx, rsi
0x18000d776  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d77c  add     rsp, 28h
0x18000d780  pop     rdi
0x18000d781  pop     rsi
0x18000d782  pop     rbp
0x18000d783  pop     rbx
0x18000d784  retn
```
