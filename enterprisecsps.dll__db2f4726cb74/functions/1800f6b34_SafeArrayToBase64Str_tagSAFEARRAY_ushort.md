# SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)

- ea: `0x1800f6b34`
- end: `0x1800f6bf8`
- name: `?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z`
- size: `196`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16 **)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180018358`
- `0x180018544`
- `0x180018730`
- `0x18001891c`
- `0x18006d640`
- `0x18006d930`
- `0x1800731a8`
- `0x180073394`
- `0x180073580`
- `0x18007376c`
- `0x180073958`
- `0x180073b44`
- `0x180073d30`
- `0x180073f1c`
- `0x180074108`
- `0x1800742f4`

## callees

- `0x1800f6b34`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800f6b8e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800f6b8e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f6b6f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f6b6f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f6bd9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f6bd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6bc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6bc2`
- `DMCmnUtils!EncodeBase64W` at `0x1800f6bb2`
- `DMCmnUtils!EncodeBase64W` at `0x1800f6bb2`

## pseudocode

```c
__int64 __fastcall SafeArrayToBase64Str(SAFEARRAY *psa, unsigned __int16 **a2)
{
  HRESULT UBound; // ebx
  LONG plUbound; // [rsp+30h] [rbp+8h] BYREF
  void *ppvData; // [rsp+40h] [rbp+18h] BYREF

  ppvData = 0;
  plUbound = 0;
  if ( psa && a2 )
  {
    UBound = SafeArrayAccessData(psa, &ppvData);
    if ( UBound >= 0 )
    {
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( UBound >= 0 )
        UBound = EncodeBase64W((const unsigned __int8 *)ppvData, ++plUbound, a2);
    }
  }
  else
  {
    UBound = -2147024809;
  }
  LocalFree(0);
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x1800f6b34  mov     rax, rsp
0x1800f6b37  mov     [rax+10h], rbx
0x1800f6b3b  mov     [rax+20h], rsi
0x1800f6b3f  push    rdi
0x1800f6b40  sub     rsp, 20h
0x1800f6b44  mov     qword ptr [rax+18h], 0
0x1800f6b4c  mov     rsi, rdx
0x1800f6b4f  mov     dword ptr [rax+8], 0
0x1800f6b56  mov     rdi, rcx
0x1800f6b59  test    rcx, rcx
0x1800f6b5c  jnz     short loc_1800F6B65
0x1800f6b5e  mov     ebx, 80070057h
0x1800f6b63  jmp     short loc_1800F6BC0
0x1800f6b65  test    rsi, rsi
0x1800f6b68  jz      short loc_1800F6B5E
0x1800f6b6a  lea     rdx, [rsp+28h+ppvData]; ppvData
0x1800f6b6f  call    cs:__imp_SafeArrayAccessData
0x1800f6b76  nop     dword ptr [rax+rax+00h]
0x1800f6b7b  mov     ebx, eax
0x1800f6b7d  test    eax, eax
0x1800f6b7f  js      short loc_1800F6BC0
0x1800f6b81  lea     r8, [rsp+28h+plUbound]; plUbound
0x1800f6b86  mov     edx, 1; nDim
0x1800f6b8b  mov     rcx, rdi; psa
0x1800f6b8e  call    cs:__imp_SafeArrayGetUBound
0x1800f6b95  nop     dword ptr [rax+rax+00h]
0x1800f6b9a  mov     ebx, eax
0x1800f6b9c  test    eax, eax
0x1800f6b9e  js      short loc_1800F6BC0
0x1800f6ba0  mov     edx, [rsp+28h+plUbound]
0x1800f6ba4  mov     r8, rsi
0x1800f6ba7  mov     rcx, [rsp+28h+ppvData]
0x1800f6bac  inc     edx
0x1800f6bae  mov     [rsp+28h+plUbound], edx
0x1800f6bb2  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x1800f6bb9  nop     dword ptr [rax+rax+00h]
0x1800f6bbe  mov     ebx, eax
0x1800f6bc0  xor     ecx, ecx; hMem
0x1800f6bc2  call    cs:__imp_LocalFree
0x1800f6bc9  nop     dword ptr [rax+rax+00h]
0x1800f6bce  cmp     [rsp+28h+ppvData], 0
0x1800f6bd4  jz      short loc_1800F6BE5
0x1800f6bd6  mov     rcx, rdi; psa
0x1800f6bd9  call    cs:__imp_SafeArrayUnaccessData
0x1800f6be0  nop     dword ptr [rax+rax+00h]
0x1800f6be5  mov     rsi, [rsp+28h+arg_18]
0x1800f6bea  mov     eax, ebx
0x1800f6bec  mov     rbx, [rsp+28h+arg_8]
0x1800f6bf1  add     rsp, 20h
0x1800f6bf5  pop     rdi
0x1800f6bf6  retn
```
