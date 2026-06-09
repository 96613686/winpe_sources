# UnregisterServer

- ea: `0x180015630`
- end: `0x180015705`
- name: `UnregisterServer`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d680`

## callees

- `0x1800016d0`
- `0x180015150`
- `0x1800151a0`
- `0x1800153c8`
- `0x180015630`

## string_xrefs

- `0x18001566b`: `CLSID\`

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
0x180015630  push    rbx
0x180015632  push    rsi
0x180015633  push    rdi
0x180015634  sub     rsp, 160h
0x18001563b  mov     rax, cs:__security_cookie
0x180015642  xor     rax, rsp
0x180015645  mov     [rsp+178h+var_28], rax
0x18001564d  lea     rdx, [rsp+178h+var_158]; char *
0x180015652  mov     rdi, r9
0x180015655  mov     rbx, r8
0x180015658  call    ?CLSIDToStr@@YAJAEBU_GUID@@PEADH@Z; CLSIDToStr(_GUID const &,char *,int)
0x18001565d  test    eax, eax
0x18001565f  js      loc_1800156EA
0x180015665  mov     r10d, 100h
0x18001566b  lea     rdx, aClsid; "CLSID\\"
0x180015672  mov     r8d, r10d
0x180015675  lea     rcx, [rsp+178h+var_128]
0x18001567a  mov     eax, 7FFFFFFEh
0x18001567f  test    rax, rax
0x180015682  jz      short loc_18001569E
0x180015684  mov     r9b, [rdx]
0x180015687  test    r9b, r9b
0x18001568a  jz      short loc_18001569E
0x18001568c  mov     [rcx], r9b
0x18001568f  inc     rdx
0x180015692  inc     rcx
0x180015695  dec     rax
0x180015698  sub     r8, 1
0x18001569c  jnz     short loc_18001567F
0x18001569e  test    r8, r8
0x1800156a1  lea     rax, [rcx-1]
0x1800156a5  lea     r8, [rsp+178h+var_158]; char *
0x1800156aa  mov     rdx, r10; unsigned __int64
0x1800156ad  cmovnz  rax, rcx
0x1800156b1  lea     rcx, [rsp+178h+var_128]; char *
0x1800156b6  mov     byte ptr [rax], 0
0x1800156b9  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800156be  mov     rsi, 0FFFFFFFF80000000h
0x1800156c5  lea     rdx, [rsp+178h+var_128]
0x1800156ca  mov     rcx, rsi
0x1800156cd  call    RegRemoveSubtree
0x1800156d2  mov     rdx, rbx
0x1800156d5  mov     rcx, rsi
0x1800156d8  call    RegRemoveSubtree
0x1800156dd  mov     rdx, rdi
0x1800156e0  mov     rcx, rsi
0x1800156e3  call    RegRemoveSubtree
0x1800156e8  xor     eax, eax
0x1800156ea  mov     rcx, [rsp+178h+var_28]
0x1800156f2  xor     rcx, rsp; StackCookie
0x1800156f5  call    __security_check_cookie
0x1800156fa  add     rsp, 160h
0x180015701  pop     rdi
0x180015702  pop     rsi
0x180015703  pop     rbx
0x180015704  retn
```
