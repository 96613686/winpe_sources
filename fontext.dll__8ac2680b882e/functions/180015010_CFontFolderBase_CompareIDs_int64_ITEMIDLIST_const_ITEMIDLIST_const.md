# CFontFolderBase::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x180015010`
- end: `0x180015178`
- name: `?CompareIDs@CFontFolderBase@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `360`
- prototype: `int(CFontFolderBase *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180008348`
- `0x180015010`
- `0x180015180`
- `0x180022810`
- `0x180022cb8`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800150fa`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800150fa`

## pseudocode

```c
int __fastcall CFontFolderBase::CompareIDs(
        unsigned __int64 this,
        __int64 a2,
        const struct _ITEMIDLIST *a3,
        const struct _ITEMIDLIST *a4)
{
  int result; // eax
  int Error; // ebx
  int v10; // eax
  unsigned int ActivationStatus; // eax
  int v12; // r9d
  WCHAR String2[384]; // [rsp+50h] [rbp-638h] BYREF
  WCHAR String1[384]; // [rsp+350h] [rbp-338h] BYREF

  result = -2147024809;
  if ( a3 && a4 )
  {
    memset_0(String1, 0, sizeof(String1));
    Error = FID_ParsingName(a3, String1, 0x180u);
    if ( Error >= 0 )
    {
      memset_0(String2, 0, sizeof(String2));
      Error = FID_ParsingName(a4, String2, 0x180u);
      if ( Error >= 0 )
      {
        Error = 1;
        v10 = CompareStringEx(&psz, 1u, String1, -1, String2, -1, 0, 0, 0);
        if ( v10 == 1 )
        {
          Error = 0xFFFF;
        }
        else if ( v10 == 2 )
        {
          FID_GetActivationStatus(a4);
          ActivationStatus = FID_GetActivationStatus(a3);
          Error = (unsigned __int16)-(v12 != ActivationStatus);
        }
        else if ( v10 != 3 )
        {
          Error = ResultFromKnownLastError();
        }
      }
    }
    return CompareIDsImpl2(
             Error,
             (struct IShellFolder2 *)(this & ((unsigned __int128)-(__int128)(this - 40) >> 64)),
             a2,
             a3,
             a4);
  }
  return result;
}

```

## disassembly

```asm
0x180015010  push    rbx
0x180015012  push    rbp
0x180015013  push    rsi
0x180015014  push    rdi
0x180015015  push    r14
0x180015017  sub     rsp, 660h
0x18001501e  mov     rax, cs:__security_cookie
0x180015025  xor     rax, rsp
0x180015028  mov     [rsp+688h+var_38], rax
0x180015030  mov     rdi, r9
0x180015033  mov     rsi, r8
0x180015036  mov     r14, rdx
0x180015039  mov     rbp, rcx
0x18001503c  mov     eax, 80070057h
0x180015041  test    r8, r8
0x180015044  jz      loc_18001515A
0x18001504a  test    r9, r9
0x18001504d  jz      loc_18001515A
0x180015053  xor     edx, edx; Val
0x180015055  lea     rcx, [rsp+688h+String1]; void *
0x18001505d  mov     r8d, 300h; Size
0x180015063  call    memset_0
0x180015068  mov     r8d, 180h; unsigned int
0x18001506e  lea     rdx, [rsp+688h+String1]; unsigned __int16 *
0x180015076  mov     rcx, rsi; struct _ITEMIDLIST *
0x180015079  call    ?FID_ParsingName@@YAJPEFBU_ITEMIDLIST@@PEAGI@Z; FID_ParsingName(_ITEMIDLIST const *,ushort *,uint)
0x18001507e  mov     ebx, eax
0x180015080  test    eax, eax
0x180015082  js      loc_18001513B
0x180015088  xor     edx, edx; Val
0x18001508a  lea     rcx, [rsp+688h+String2]; void *
0x18001508f  mov     r8d, 300h; Size
0x180015095  call    memset_0
0x18001509a  mov     r8d, 180h; unsigned int
0x1800150a0  lea     rdx, [rsp+688h+String2]; unsigned __int16 *
0x1800150a5  mov     rcx, rdi; struct _ITEMIDLIST *
0x1800150a8  call    ?FID_ParsingName@@YAJPEFBU_ITEMIDLIST@@PEAGI@Z; FID_ParsingName(_ITEMIDLIST const *,ushort *,uint)
0x1800150ad  mov     ebx, eax
0x1800150af  test    eax, eax
0x1800150b1  js      loc_18001513B
0x1800150b7  mov     [rsp+688h+lParam], 0; lParam
0x1800150c0  lea     rax, [rsp+688h+String2]
0x1800150c5  or      r9d, 0FFFFFFFFh; cchCount1
0x1800150c9  mov     [rsp+688h+lpReserved], 0; lpReserved
0x1800150d2  mov     [rsp+688h+lpVersionInformation], 0; lpVersionInformation
0x1800150db  lea     r8, [rsp+688h+String1]; lpString1
0x1800150e3  mov     [rsp+688h+cchCount2], r9d; cchCount2
0x1800150e8  lea     rcx, psz; lpLocaleName
0x1800150ef  mov     [rsp+688h+lpString2], rax; lpString2
0x1800150f4  lea     ebx, [r9+2]
0x1800150f8  mov     edx, ebx; dwCmpFlags
0x1800150fa  call    cs:__imp_CompareStringEx
0x180015100  mov     ecx, eax
0x180015102  sub     ecx, ebx
0x180015104  jz      short loc_180015136
0x180015106  sub     ecx, ebx
0x180015108  jz      short loc_180015117
0x18001510a  cmp     ecx, ebx
0x18001510c  jz      short loc_18001513B
0x18001510e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015113  mov     ebx, eax
0x180015115  jmp     short loc_18001513B
0x180015117  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001511a  call    ?FID_GetActivationStatus@@YAKPEFBU_ITEMIDLIST@@@Z; FID_GetActivationStatus(_ITEMIDLIST const *)
0x18001511f  mov     rcx, rsi; struct _ITEMIDLIST *
0x180015122  mov     r9d, eax
0x180015125  call    ?FID_GetActivationStatus@@YAKPEFBU_ITEMIDLIST@@@Z; FID_GetActivationStatus(_ITEMIDLIST const *)
0x18001512a  sub     eax, r9d
0x18001512d  neg     eax
0x18001512f  sbb     ebx, ebx
0x180015131  movzx   ebx, bx
0x180015134  jmp     short loc_18001513B
0x180015136  mov     ebx, 0FFFFh
0x18001513b  lea     rax, [rbp-28h]
0x18001513f  mov     [rsp+688h+lpString2], rdi; struct _ITEMIDLIST *
0x180015144  neg     rax
0x180015147  mov     r9, rsi; struct _ITEMIDLIST *
0x18001514a  mov     r8, r14; __int64
0x18001514d  mov     ecx, ebx; int
0x18001514f  sbb     rdx, rdx
0x180015152  and     rdx, rbp; struct IShellFolder2 *
0x180015155  call    ?CompareIDsImpl2@@YAJJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST@@2@Z; CompareIDsImpl2(long,IShellFolder2 *,__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18001515a  mov     rcx, [rsp+688h+var_38]
0x180015162  xor     rcx, rsp; StackCookie
0x180015165  call    __security_check_cookie
0x18001516a  add     rsp, 660h
0x180015171  pop     r14
0x180015173  pop     rdi
0x180015174  pop     rsi
0x180015175  pop     rbp
0x180015176  pop     rbx
0x180015177  retn
```
