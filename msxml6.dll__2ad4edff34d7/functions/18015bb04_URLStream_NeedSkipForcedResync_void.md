# URLStream::NeedSkipForcedResync(void)

- ea: `0x18015bb04`
- end: `0x18015bbd6`
- name: `?NeedSkipForcedResync@URLStream@@IEAAHXZ`
- size: `210`
- prototype: `int __fastcall(URLStream *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18015cfa0`

## callees

- `0x1800644e8`
- `0x18015bb04`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18015bbc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18015bbc1`
- `OLEAUT32!__imp_SysStringLen` at `0x18015bb60`
- `OLEAUT32!__imp_SysStringLen` at `0x18015bb60`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18015bb37`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18015bb37`

## pseudocode

```c
__int64 __fastcall URLStream::NeedSkipForcedResync(URLStream *this)
{
  wchar_t *resolvedURL; // rcx
  unsigned int v2; // edi
  UINT v3; // esi
  char v4; // bl
  int i; // ebx
  const wchar_t *pwszText; // rcx
  wchar_t *strHostName; // [rsp+40h] [rbp+8h] BYREF
  IUri *v9; // [rsp+48h] [rbp+10h] BYREF

  resolvedURL = this->_resolvedURL;
  v2 = 0;
  if ( resolvedURL )
  {
    v3 = 0;
    strHostName = 0;
    v9 = 0;
    v4 = 0;
    if ( CreateUri(resolvedURL, 5u, 0, &v9) >= 0 && !v9->GetHost(v9, &strHostName) )
    {
      v3 = SysStringLen(strHostName);
      v4 = 1;
    }
    if ( v9 )
      v9->Release(v9);
    if ( v4 )
    {
      for ( i = 0; ; ++i )
      {
        pwszText = IgnoreList[i].pwszText;
        if ( !pwszText )
          break;
        if ( v3 == IgnoreList[i].nLength && !fastcmpni(pwszText, strHostName, v3) )
        {
          v2 = 1;
          break;
        }
      }
    }
    SysFreeString(strHostName);
  }
  return v2;
}

```

## disassembly

```asm
0x18015bb04  mov     rax, rsp
0x18015bb07  mov     [rax+18h], rbx
0x18015bb0b  push    rbp
0x18015bb0c  push    rsi
0x18015bb0d  push    rdi
0x18015bb0e  sub     rsp, 20h
0x18015bb12  mov     this, [this+18h]; pwzURI
0x18015bb16  xor     edi, edi
0x18015bb18  test    this, this
0x18015bb1b  jz      loc_18015BBC7
0x18015bb21  xor     esi, esi
0x18015bb23  mov     [rax+8], rdi
0x18015bb27  lea     r9, [rax+10h]; ppURI
0x18015bb2b  mov     [rax+10h], rsi
0x18015bb2f  xor     r8d, r8d; dwReserved
0x18015bb32  lea     edx, [rdi+5]; dwFlags
0x18015bb35  xor     bl, bl
0x18015bb37  call    cs:__imp_CreateUri
0x18015bb3d  test    eax, eax
0x18015bb3f  js      short loc_18015BB6A
0x18015bb41  mov     this, [rsp+38h+arg_8]
0x18015bb46  lea     rdx, [rsp+38h+strHostName]
0x18015bb4b  mov     rax, [this]
0x18015bb4e  mov     rax, [rax+68h]
0x18015bb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bb57  test    eax, eax
0x18015bb59  jnz     short loc_18015BB6A
0x18015bb5b  mov     this, [rsp+38h+strHostName]; pbstr
0x18015bb60  call    cs:__imp_SysStringLen
0x18015bb66  mov     esi, eax
0x18015bb68  mov     bl, 1
0x18015bb6a  mov     this, [rsp+38h+arg_8]
0x18015bb6f  test    this, this
0x18015bb72  jz      short loc_18015BB80
0x18015bb74  mov     rax, [this]
0x18015bb77  mov     rax, [rax+10h]
0x18015bb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bb80  test    bl, bl
0x18015bb82  jz      short loc_18015BBBC
0x18015bb84  xor     ebx, ebx
0x18015bb86  lea     rbp, IgnoreList
0x18015bb8d  mov     eax, ebx
0x18015bb8f  add     rax, rax
0x18015bb92  mov     this, [rbp+rax*8+0]; first
0x18015bb97  test    this, this
0x18015bb9a  jz      short loc_18015BBBC
0x18015bb9c  cmp     esi, [rbp+rax*8+8]
0x18015bba0  jnz     short loc_18015BBB3
0x18015bba2  mov     rdx, [rsp+38h+strHostName]; last
0x18015bba7  mov     r8d, esi; count
0x18015bbaa  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x18015bbaf  test    eax, eax
0x18015bbb1  jz      short loc_18015BBB7
0x18015bbb3  inc     ebx
0x18015bbb5  jmp     short loc_18015BB8D
0x18015bbb7  mov     edi, 1
0x18015bbbc  mov     this, [rsp+38h+strHostName]; bstrString
0x18015bbc1  call    cs:__imp_SysFreeString
0x18015bbc7  mov     rbx, [rsp+38h+arg_10]
0x18015bbcc  mov     eax, edi
0x18015bbce  add     rsp, 20h
0x18015bbd2  pop     rdi
0x18015bbd3  pop     rsi
0x18015bbd4  pop     rbp
0x18015bbd5  retn
```
