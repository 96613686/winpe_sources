# UnregisterServer

- ea: `0x18000cca0`
- end: `0x18000cd75`
- name: `UnregisterServer`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007da0`

## callees

- `0x1800015d0`
- `0x18000c7c0`
- `0x18000c810`
- `0x18000ca38`
- `0x18000cca0`

## string_xrefs

- `0x18000ccdb`: `CLSID\`

## pseudocode

```c
HRESULT __fastcall UnregisterServer(const struct _GUID *a1, __int64 a2, const CHAR *a3, const CHAR *a4)
{
  HRESULT result; // eax
  const char *v7; // rdx
  __int64 v8; // r8
  char *v9; // rcx
  __int64 v10; // rax
  char *v11; // rax
  char v12[48]; // [rsp+20h] [rbp-158h] BYREF
  char v13[256]; // [rsp+50h] [rbp-128h] BYREF

  result = CLSIDToStr(a1, v12);
  if ( result >= 0 )
  {
    v7 = "CLSID\\";
    v8 = 256;
    v9 = v13;
    v10 = 2147483646;
    do
    {
      if ( !v10 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v10;
      --v8;
    }
    while ( v8 );
    v11 = v9 - 1;
    if ( v8 )
      v11 = v9;
    *v11 = 0;
    StringCchCatA(v13, 0x100u, v12);
    RegRemoveSubtree(HKEY_CLASSES_ROOT, v13);
    RegRemoveSubtree(HKEY_CLASSES_ROOT, a3);
    RegRemoveSubtree(HKEY_CLASSES_ROOT, a4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000cca0  push    rbx
0x18000cca2  push    rsi
0x18000cca3  push    rdi
0x18000cca4  sub     rsp, 160h
0x18000ccab  mov     rax, cs:__security_cookie
0x18000ccb2  xor     rax, rsp
0x18000ccb5  mov     [rsp+178h+var_28], rax
0x18000ccbd  lea     rdx, [rsp+178h+var_158]; char *
0x18000ccc2  mov     rdi, r9
0x18000ccc5  mov     rbx, r8
0x18000ccc8  call    ?CLSIDToStr@@YAJAEBU_GUID@@PEADH@Z; CLSIDToStr(_GUID const &,char *,int)
0x18000cccd  test    eax, eax
0x18000cccf  js      loc_18000CD5A
0x18000ccd5  mov     r10d, 100h
0x18000ccdb  lea     rdx, aClsid; "CLSID\\"
0x18000cce2  mov     r8d, r10d
0x18000cce5  lea     rcx, [rsp+178h+var_128]
0x18000ccea  mov     eax, 7FFFFFFEh
0x18000ccef  test    rax, rax
0x18000ccf2  jz      short loc_18000CD0E
0x18000ccf4  mov     r9b, [rdx]
0x18000ccf7  test    r9b, r9b
0x18000ccfa  jz      short loc_18000CD0E
0x18000ccfc  mov     [rcx], r9b
0x18000ccff  inc     rdx
0x18000cd02  inc     rcx
0x18000cd05  dec     rax
0x18000cd08  sub     r8, 1
0x18000cd0c  jnz     short loc_18000CCEF
0x18000cd0e  test    r8, r8
0x18000cd11  lea     rax, [rcx-1]
0x18000cd15  lea     r8, [rsp+178h+var_158]; char *
0x18000cd1a  mov     rdx, r10; unsigned __int64
0x18000cd1d  cmovnz  rax, rcx
0x18000cd21  lea     rcx, [rsp+178h+var_128]; char *
0x18000cd26  mov     byte ptr [rax], 0
0x18000cd29  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000cd2e  mov     rsi, 0FFFFFFFF80000000h
0x18000cd35  lea     rdx, [rsp+178h+var_128]
0x18000cd3a  mov     rcx, rsi
0x18000cd3d  call    RegRemoveSubtree
0x18000cd42  mov     rdx, rbx
0x18000cd45  mov     rcx, rsi
0x18000cd48  call    RegRemoveSubtree
0x18000cd4d  mov     rdx, rdi
0x18000cd50  mov     rcx, rsi
0x18000cd53  call    RegRemoveSubtree
0x18000cd58  xor     eax, eax
0x18000cd5a  mov     rcx, [rsp+178h+var_28]
0x18000cd62  xor     rcx, rsp; StackCookie
0x18000cd65  call    __security_check_cookie
0x18000cd6a  add     rsp, 160h
0x18000cd71  pop     rdi
0x18000cd72  pop     rsi
0x18000cd73  pop     rbx
0x18000cd74  retn
```
