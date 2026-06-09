# CDRMCBase::CreateGuidString(ushort * *)

- ea: `0x18001f2fc`
- end: `0x18001f3a5`
- name: `?CreateGuidString@CDRMCBase@@QEAAJPEAPEAG@Z`
- size: `169`
- prototype: `__int64 __fastcall(CDRMCBase *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009bc4`
- `0x18000b5b4`

## callees

- `0x180001244`
- `0x180001284`
- `0x18001f2fc`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f36f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f36f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001f32c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001f32c`

## pseudocode

```c
__int64 __fastcall CDRMCBase::CreateGuidString(CDRMCBase *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rdi
  HRESULT v4; // ebx
  unsigned __int16 *v5; // rax
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF

  pguid = 0;
  v3 = 0;
  v4 = CoCreateGuid(&pguid);
  if ( v4 >= 0 )
  {
    v5 = (unsigned __int16 *)operator new(0x82u);
    v3 = v5;
    if ( v5 && (memset_0(v5, 0, 0x82u), StringFromGUID2(&pguid, v3, 65)) )
    {
      *a2 = v3;
      v3 = 0;
    }
    else
    {
      v4 = -2147024882;
    }
  }
  operator delete(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f2fc  mov     [rsp+arg_0], rbx
0x18001f301  mov     [rsp+arg_10], rsi
0x18001f306  push    rdi
0x18001f307  sub     rsp, 40h
0x18001f30b  mov     rax, cs:__security_cookie
0x18001f312  xor     rax, rsp
0x18001f315  mov     [rsp+48h+var_18], rax
0x18001f31a  xorps   xmm0, xmm0
0x18001f31d  lea     rcx, [rsp+48h+pguid]; pguid
0x18001f322  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x18001f327  mov     rsi, rdx
0x18001f32a  xor     edi, edi
0x18001f32c  call    cs:__imp_CoCreateGuid
0x18001f332  mov     ebx, eax
0x18001f334  test    eax, eax
0x18001f336  js      short loc_18001F37E
0x18001f338  mov     ecx, 82h; Size
0x18001f33d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f342  mov     rdi, rax
0x18001f345  test    rax, rax
0x18001f348  jnz     short loc_18001F351
0x18001f34a  mov     ebx, 8007000Eh
0x18001f34f  jmp     short loc_18001F37E
0x18001f351  xor     edx, edx; Val
0x18001f353  mov     r8d, 82h; Size
0x18001f359  mov     rcx, rdi; void *
0x18001f35c  call    memset_0
0x18001f361  mov     r8d, 41h ; 'A'; cchMax
0x18001f367  lea     rcx, [rsp+48h+pguid]; rguid
0x18001f36c  mov     rdx, rdi; lpsz
0x18001f36f  call    cs:__imp_StringFromGUID2
0x18001f375  test    eax, eax
0x18001f377  jz      short loc_18001F34A
0x18001f379  mov     [rsi], rdi
0x18001f37c  xor     edi, edi
0x18001f37e  mov     rcx, rdi; Block
0x18001f381  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f386  mov     eax, ebx
0x18001f388  mov     rcx, [rsp+48h+var_18]
0x18001f38d  xor     rcx, rsp; StackCookie
0x18001f390  call    __security_check_cookie
0x18001f395  mov     rbx, [rsp+48h+arg_0]
0x18001f39a  mov     rsi, [rsp+48h+arg_10]
0x18001f39f  add     rsp, 40h
0x18001f3a3  pop     rdi
0x18001f3a4  retn
```
