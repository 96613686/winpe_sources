# ALLOW_LIST_ENTRY::Set(ushort const *,ushort const *)

- ea: `0x180002dd0`
- end: `0x180002ef4`
- name: `?Set@ALLOW_LIST_ENTRY@@QEAAJPEBG0@Z`
- size: `292`
- prototype: `__int64 __fastcall(ALLOW_LIST_ENTRY *this, unsigned __int16 *, wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002604`

## callees

- `0x180001948`
- `0x180001af4`
- `0x180002dd0`
- `0x180002efc`
- `0x18000679a`
- `0x1800067c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ed2`

## pseudocode

```c
__int64 __fastcall ALLOW_LIST_ENTRY::Set(ALLOW_LIST_ENTRY *this, unsigned __int16 *a2, wchar_t *a3)
{
  int v6; // ebx
  void **v8; // [rsp+20h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-31h]
  unsigned int v10; // [rsp+30h] [rbp-29h]
  char v11; // [rsp+3Ch] [rbp-1Dh] BYREF

  STBUFF::STBUFF((STBUFF *)&v8, (int)a2);
  if ( !a3 || !*a3 || !wcscmp_0(a3, L"255.255.255.255") || !wcscmp_0(a3, L"ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff") )
    *((_DWORD *)this + 2) = 1;
  v6 = STBUFF::UnicodeToAnsi((STBUFF *)&v8, a2);
  if ( v6 >= 0 )
  {
    *((_BYTE *)hMem + v10) = 0;
    *((_BYTE *)hMem + v10 + 1) = 0;
    v6 = IpToSockAddr((char *)hMem, (ALLOW_LIST_ENTRY *)((char *)this + 16));
    if ( v6 >= 0 && !*((_DWORD *)this + 2) )
    {
      v6 = STBUFF::UnicodeToAnsi((STBUFF *)&v8, a3);
      if ( v6 >= 0 )
      {
        *((_BYTE *)hMem + v10) = 0;
        *((_BYTE *)hMem + v10 + 1) = 0;
        v6 = IpToSockAddr((char *)hMem, (ALLOW_LIST_ENTRY *)((char *)this + 112));
      }
    }
  }
  v8 = &STBUFF::`vftable';
  if ( hMem != &v11 )
    LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002dd0  push    rbp
0x180002dd2  push    rbx
0x180002dd3  push    rsi
0x180002dd4  push    rdi
0x180002dd5  push    r14
0x180002dd7  lea     rbp, [rsp-37h]
0x180002ddc  sub     rsp, 90h
0x180002de3  mov     rax, cs:__security_cookie
0x180002dea  xor     rax, rsp
0x180002ded  mov     [rbp+57h+var_30], rax
0x180002df1  mov     rsi, rcx
0x180002df4  mov     rdi, r8
0x180002df7  lea     rcx, [rbp+57h+var_90]; this
0x180002dfb  mov     rbx, rdx
0x180002dfe  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180002e03  xor     r14d, r14d
0x180002e06  test    rdi, rdi
0x180002e09  jz      short loc_180002E37
0x180002e0b  cmp     [rdi], r14w
0x180002e0f  jz      short loc_180002E37
0x180002e11  lea     rdx, a255255255255; "255.255.255.255"
0x180002e18  mov     rcx, rdi; String1
0x180002e1b  call    wcscmp_0
0x180002e20  test    eax, eax
0x180002e22  jz      short loc_180002E37
0x180002e24  lea     rdx, aFfffFfffFfffFf; "ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff"
0x180002e2b  mov     rcx, rdi; String1
0x180002e2e  call    wcscmp_0
0x180002e33  test    eax, eax
0x180002e35  jnz     short loc_180002E3E
0x180002e37  mov     dword ptr [rsi+8], 1
0x180002e3e  mov     rdx, rbx; unsigned __int16 *
0x180002e41  lea     rcx, [rbp+57h+var_90]; this
0x180002e45  call    ?UnicodeToAnsi@STBUFF@@QEAAJPEAG@Z; STBUFF::UnicodeToAnsi(ushort *)
0x180002e4a  mov     ebx, eax
0x180002e4c  test    eax, eax
0x180002e4e  js      short loc_180002EBA
0x180002e50  mov     ecx, [rbp+57h+var_80]
0x180002e53  lea     rdx, [rsi+10h]; this
0x180002e57  mov     rax, [rbp+57h+hMem]
0x180002e5b  mov     [rcx+rax], r14b
0x180002e5f  mov     ecx, [rbp+57h+var_80]
0x180002e62  mov     rax, [rbp+57h+hMem]
0x180002e66  inc     ecx
0x180002e68  mov     [rcx+rax], r14b
0x180002e6c  mov     rcx, [rbp+57h+hMem]; char *
0x180002e70  call    ?IpToSockAddr@@YAJPEADPEAVSTBUFF@@@Z; IpToSockAddr(char *,STBUFF *)
0x180002e75  mov     ebx, eax
0x180002e77  test    eax, eax
0x180002e79  js      short loc_180002EBA
0x180002e7b  cmp     [rsi+8], r14d
0x180002e7f  jnz     short loc_180002EBA
0x180002e81  mov     rdx, rdi; unsigned __int16 *
0x180002e84  lea     rcx, [rbp+57h+var_90]; this
0x180002e88  call    ?UnicodeToAnsi@STBUFF@@QEAAJPEAG@Z; STBUFF::UnicodeToAnsi(ushort *)
0x180002e8d  mov     ebx, eax
0x180002e8f  test    eax, eax
0x180002e91  js      short loc_180002EBA
0x180002e93  mov     ecx, [rbp+57h+var_80]
0x180002e96  lea     rdx, [rsi+70h]; this
0x180002e9a  mov     rax, [rbp+57h+hMem]
0x180002e9e  mov     [rcx+rax], r14b
0x180002ea2  mov     ecx, [rbp+57h+var_80]
0x180002ea5  mov     rax, [rbp+57h+hMem]
0x180002ea9  inc     ecx
0x180002eab  mov     [rcx+rax], r14b
0x180002eaf  mov     rcx, [rbp+57h+hMem]; char *
0x180002eb3  call    ?IpToSockAddr@@YAJPEADPEAVSTBUFF@@@Z; IpToSockAddr(char *,STBUFF *)
0x180002eb8  mov     ebx, eax
0x180002eba  mov     rcx, [rbp+57h+hMem]; hMem
0x180002ebe  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180002ec5  mov     [rbp+57h+var_90], rax
0x180002ec9  lea     rax, [rbp+57h+var_74]
0x180002ecd  cmp     rcx, rax
0x180002ed0  jz      short loc_180002ED8
0x180002ed2  call    cs:__imp_LocalFree
0x180002ed8  mov     eax, ebx
0x180002eda  mov     rcx, [rbp+57h+var_30]
0x180002ede  xor     rcx, rsp; StackCookie
0x180002ee1  call    __security_check_cookie
0x180002ee6  add     rsp, 90h
0x180002eed  pop     r14
0x180002eef  pop     rdi
0x180002ef0  pop     rsi
0x180002ef1  pop     rbx
0x180002ef2  pop     rbp
0x180002ef3  retn
```
