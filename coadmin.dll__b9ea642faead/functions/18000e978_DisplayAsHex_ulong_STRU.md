# DisplayAsHex(ulong,STRU *)

- ea: `0x18000e978`
- end: `0x18000ea3d`
- name: `?DisplayAsHex@@YAJKPEAVSTRU@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(unsigned int, struct STRU *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000238c`
- `0x18000eeb8`

## callees

- `0x18000e978`
- `0x18000eb50`
- `0x18000fb50`

## import_xrefs

- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000ea1a`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000ea1a`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000e99b`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000e99b`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e9f2`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e9f2`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000ea06`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000ea06`

## pseudocode

```c
__int64 __fastcall DisplayAsHex(unsigned int a1, struct STRU *a2)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r9
  __int16 v8; // cx
  _BYTE v10[32]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  unsigned int v12; // [rsp+50h] [rbp-18h]

  STRU::STRU((STRU *)v10);
  v4 = DisplayDwordRadix(a1, (struct STRU *)v10, 16);
  if ( v4 >= 0 )
  {
    v5 = v12;
    v6 = 0;
    v7 = v11;
    if ( v12 )
    {
      do
      {
        v8 = *(_WORD *)(v7 + 2 * v6);
        if ( (unsigned __int16)(v8 - 97) <= 5u )
          *(_WORD *)(v7 + 2 * v6) = v8 - 32;
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < (unsigned int)v5 );
    }
    v4 = STRU::Copy(a2, L"0x", v5, v7);
    if ( v4 >= 0 )
    {
      v4 = STRU::Append(a2, (const struct STRU *)v10);
      if ( v4 >= 0 )
        v4 = 0;
    }
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e978  mov     [rsp+arg_10], rbx
0x18000e97d  push    rdi
0x18000e97e  sub     rsp, 60h
0x18000e982  mov     rax, cs:__security_cookie
0x18000e989  xor     rax, rsp
0x18000e98c  mov     [rsp+68h+var_10], rax
0x18000e991  mov     ebx, ecx
0x18000e993  mov     rdi, rdx
0x18000e996  lea     rcx, [rsp+68h+var_48]
0x18000e99b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000e9a1  mov     r8d, 10h; int
0x18000e9a7  lea     rdx, [rsp+68h+var_48]; struct STRU *
0x18000e9ac  mov     ecx, ebx; unsigned int
0x18000e9ae  call    ?DisplayDwordRadix@@YAJKPEAVSTRU@@H@Z; DisplayDwordRadix(ulong,STRU *,int)
0x18000e9b3  mov     ebx, eax
0x18000e9b5  test    eax, eax
0x18000e9b7  js      short loc_18000EA15
0x18000e9b9  mov     r8d, [rsp+68h+var_18]
0x18000e9be  xor     edx, edx
0x18000e9c0  mov     r9, [rsp+68h+var_28]
0x18000e9c5  test    r8d, r8d
0x18000e9c8  jz      short loc_18000E9E8
0x18000e9ca  movzx   ecx, word ptr [r9+rdx*2]
0x18000e9cf  lea     eax, [rcx-61h]
0x18000e9d2  cmp     ax, 5
0x18000e9d6  ja      short loc_18000E9E1
0x18000e9d8  sub     cx, 20h ; ' '
0x18000e9dc  mov     [r9+rdx*2], cx
0x18000e9e1  inc     edx
0x18000e9e3  cmp     edx, r8d
0x18000e9e6  jb      short loc_18000E9CA
0x18000e9e8  lea     rdx, a0x; "0x"
0x18000e9ef  mov     rcx, rdi
0x18000e9f2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000e9f8  mov     ebx, eax
0x18000e9fa  test    eax, eax
0x18000e9fc  js      short loc_18000EA15
0x18000e9fe  lea     rdx, [rsp+68h+var_48]
0x18000ea03  mov     rcx, rdi
0x18000ea06  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000ea0c  mov     ebx, eax
0x18000ea0e  xor     eax, eax
0x18000ea10  test    ebx, ebx
0x18000ea12  cmovns  ebx, eax
0x18000ea15  lea     rcx, [rsp+68h+var_48]
0x18000ea1a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ea20  mov     eax, ebx
0x18000ea22  mov     rcx, [rsp+68h+var_10]
0x18000ea27  xor     rcx, rsp; StackCookie
0x18000ea2a  call    __security_check_cookie
0x18000ea2f  mov     rbx, [rsp+68h+arg_10]
0x18000ea37  add     rsp, 60h
0x18000ea3b  pop     rdi
0x18000ea3c  retn
```
