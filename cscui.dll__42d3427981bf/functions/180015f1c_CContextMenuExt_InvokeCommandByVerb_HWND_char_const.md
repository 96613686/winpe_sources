# CContextMenuExt::_InvokeCommandByVerb(HWND__ *,char const *)

- ea: `0x180015f1c`
- end: `0x1800160a1`
- name: `?_InvokeCommandByVerb@CContextMenuExt@@AEAAJPEAUHWND__@@PEBD@Z`
- size: `389`
- prototype: `__int64 __fastcall(CContextMenuExt *__hidden this, HWND, PCNZCH lpString1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014a30`

## callees

- `0x180010ff4`
- `0x180015b8c`
- `0x180015f1c`
- `0x1800174d8`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180015f51`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180015fb0`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18001600c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180015f51`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180015fb0`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18001600c`

## pseudocode

```c
int __fastcall CContextMenuExt::_InvokeCommandByVerb(CContextMenuExt *this, HWND a2, PCNZCH lpString1)
{
  unsigned __int64 v6; // rbx

  v6 = 1;
  if ( CompareStringA(0x7Fu, 1u, lpString1, -1, "pin", -1) == 2 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
    }
    v6 = 0;
    return CContextMenuExt::_InvokeCommandByID(this, a2, v6);
  }
  if ( CompareStringA(0x7Fu, 1u, lpString1, -1, "unpin", -1) == 2 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
    }
    return CContextMenuExt::_InvokeCommandByID(this, a2, v6);
  }
  if ( CompareStringA(0x7Fu, 1u, lpString1, -1, "synchronize", -1) == 2 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
    }
    v6 = 3;
    return CContextMenuExt::_InvokeCommandByID(this, a2, v6);
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids, lpString1);
  }
  return -2147467259;
}

```

## disassembly

```asm
0x180015f1c  push    rbx
0x180015f1e  push    rbp
0x180015f1f  push    rsi
0x180015f20  push    rdi
0x180015f21  push    r14
0x180015f23  sub     rsp, 30h
0x180015f27  or      r14d, 0FFFFFFFFh
0x180015f2b  lea     rax, String2; "pin"
0x180015f32  mov     rsi, rdx
0x180015f35  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180015f3a  mov     rbp, rcx
0x180015f3d  mov     [rsp+58h+lpString2], rax; lpString2
0x180015f42  mov     r9d, r14d; cchCount1
0x180015f45  mov     rdi, r8
0x180015f48  lea     ebx, [r14+2]
0x180015f4c  mov     edx, ebx; dwCmpFlags
0x180015f4e  lea     ecx, [rbx+7Eh]; Locale
0x180015f51  call    cs:__imp_CompareStringA
0x180015f57  cmp     eax, 2
0x180015f5a  jnz     short loc_180015F92
0x180015f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f63  lea     rax, WPP_GLOBAL_Control
0x180015f6a  cmp     rcx, rax
0x180015f6d  jz      short loc_180015F8B
0x180015f6f  test    dword ptr [rcx+1Ch], 40000h
0x180015f76  jz      short loc_180015F8B
0x180015f78  mov     rcx, [rcx+10h]
0x180015f7c  lea     edx, [rbx+2Fh]
0x180015f7f  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180015f86  call    WPP_SF_
0x180015f8b  xor     ebx, ebx
0x180015f8d  jmp     loc_18001604D
0x180015f92  lea     rax, aUnpin; "unpin"
0x180015f99  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180015f9e  mov     r9d, r14d; cchCount1
0x180015fa1  mov     [rsp+58h+lpString2], rax; lpString2
0x180015fa6  mov     r8, rdi; lpString1
0x180015fa9  mov     edx, ebx; dwCmpFlags
0x180015fab  mov     ecx, 7Fh; Locale
0x180015fb0  call    cs:__imp_CompareStringA
0x180015fb6  cmp     eax, 2
0x180015fb9  jnz     short loc_180015FEE
0x180015fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fc2  lea     rax, WPP_GLOBAL_Control
0x180015fc9  cmp     rcx, rax
0x180015fcc  jz      short loc_18001604D
0x180015fce  test    dword ptr [rcx+1Ch], 40000h
0x180015fd5  jz      short loc_18001604D
0x180015fd7  mov     rcx, [rcx+10h]
0x180015fdb  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180015fe2  mov     edx, 31h ; '1'
0x180015fe7  call    WPP_SF_
0x180015fec  jmp     short loc_18001604D
0x180015fee  lea     rax, aSynchronize_0; "synchronize"
0x180015ff5  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180015ffa  mov     r9d, r14d; cchCount1
0x180015ffd  mov     [rsp+58h+lpString2], rax; lpString2
0x180016002  mov     r8, rdi; lpString1
0x180016005  mov     edx, ebx; dwCmpFlags
0x180016007  mov     ecx, 7Fh; Locale
0x18001600c  call    cs:__imp_CompareStringA
0x180016012  cmp     eax, 2
0x180016015  jnz     short loc_18001605D
0x180016017  mov     rcx, cs:WPP_GLOBAL_Control
0x18001601e  lea     rax, WPP_GLOBAL_Control
0x180016025  cmp     rcx, rax
0x180016028  jz      short loc_180016048
0x18001602a  test    dword ptr [rcx+1Ch], 40000h
0x180016031  jz      short loc_180016048
0x180016033  mov     rcx, [rcx+10h]
0x180016037  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x18001603e  mov     edx, 32h ; '2'
0x180016043  call    WPP_SF_
0x180016048  mov     ebx, 3
0x18001604d  mov     r8, rbx; unsigned __int64
0x180016050  mov     rdx, rsi; HWND
0x180016053  mov     rcx, rbp; this
0x180016056  call    ?_InvokeCommandByID@CContextMenuExt@@AEAAJPEAUHWND__@@_K@Z; CContextMenuExt::_InvokeCommandByID(HWND__ *,unsigned __int64)
0x18001605b  jmp     short loc_180016096
0x18001605d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016064  lea     rax, WPP_GLOBAL_Control
0x18001606b  cmp     rcx, rax
0x18001606e  jz      short loc_180016091
0x180016070  test    dword ptr [rcx+1Ch], 40000h
0x180016077  jz      short loc_180016091
0x180016079  mov     rcx, [rcx+10h]
0x18001607d  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180016084  mov     edx, 33h ; '3'
0x180016089  mov     r9, rdi
0x18001608c  call    WPP_SF_s
0x180016091  mov     eax, 80004005h
0x180016096  add     rsp, 30h
0x18001609a  pop     r14
0x18001609c  pop     rdi
0x18001609d  pop     rsi
0x18001609e  pop     rbp
0x18001609f  pop     rbx
0x1800160a0  retn
```
