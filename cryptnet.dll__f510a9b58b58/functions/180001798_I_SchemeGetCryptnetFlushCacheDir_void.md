# I_SchemeGetCryptnetFlushCacheDir(void)

- ea: `0x180001798`
- end: `0x1800017d9`
- name: `?I_SchemeGetCryptnetFlushCacheDir@@YAPEAGXZ`
- size: `65`
- prototype: `unsigned __int16 *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800015bc`
- `0x180005b30`

## callees

- `0x180001798`
- `0x180005900`
- `0x180006640`
- `0x180006710`

## string_xrefs

- `0x1800017b1`: `\Microsoft\CryptnetFlushCache\`

## pseudocode

```c
unsigned __int16 *I_SchemeGetCryptnetFlushCacheDir(void)
{
  __int64 LowIntegrityUserPath; // rdi
  void *Token; // rax
  void *v2; // rbx

  LowIntegrityUserPath = 0;
  Token = I_SchemeGetToken();
  v2 = Token;
  if ( Token )
  {
    LowIntegrityUserPath = I_CryptGetLowIntegrityUserPath(Token, L"\\Microsoft\\CryptnetFlushCache\\");
    I_UrlCacheCloseHandle(v2);
  }
  return (unsigned __int16 *)LowIntegrityUserPath;
}

```

## disassembly

```asm
0x180001798  mov     [rsp+arg_0], rbx
0x18000179d  push    rdi
0x18000179e  sub     rsp, 20h
0x1800017a2  xor     edi, edi
0x1800017a4  call    ?I_SchemeGetToken@@YAPEAXXZ; I_SchemeGetToken(void)
0x1800017a9  mov     rbx, rax
0x1800017ac  test    rax, rax
0x1800017af  jz      short loc_1800017CB
0x1800017b1  lea     rdx, aMicrosoftCrypt; "\\Microsoft\\CryptnetFlushCache\\"
0x1800017b8  mov     rcx, rax
0x1800017bb  call    I_CryptGetLowIntegrityUserPath
0x1800017c0  mov     rcx, rbx; hObject
0x1800017c3  mov     rdi, rax
0x1800017c6  call    I_UrlCacheCloseHandle
0x1800017cb  mov     rbx, [rsp+28h+arg_0]
0x1800017d0  mov     rax, rdi
0x1800017d3  add     rsp, 20h
0x1800017d7  pop     rdi
0x1800017d8  retn
```
