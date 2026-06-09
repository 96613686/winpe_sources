# CFtpObj::_SetExtraData(tagFORMATETC const *,tagSTGMEDIUM const *,int)

- ea: `0x18001b2e0`
- end: `0x18001b3e3`
- name: `?_SetExtraData@CFtpObj@@IEAAJPEBUtagFORMATETC@@PEBUtagSTGMEDIUM@@H@Z`
- size: `259`
- prototype: `int(CFtpObj *__hidden this, const struct tagFORMATETC *, const struct tagSTGMEDIUM *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001a650`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001aec8`
- `0x18001b2e0`
- `0x180026c3c`
- `0x180026cf4`
- `0x180026d60`

## import_xrefs

- `ole32!ReleaseStgMedium` at `0x18001b397`
- `ole32!ReleaseStgMedium` at `0x18001b397`
- `urlmon!CopyStgMedium` at `0x18001b357`
- `urlmon!CopyStgMedium` at `0x18001b3a4`
- `urlmon!CopyStgMedium` at `0x18001b357`
- `urlmon!CopyStgMedium` at `0x18001b3a4`

## pseudocode

```c
__int64 __fastcall CFtpObj::_SetExtraData(HDSA *this, const struct tagFORMATETC *a2, const struct tagSTGMEDIUM *a3)
{
  int ExtraDataIndex; // esi
  __int128 v7; // xmm0
  DVTARGETDEVICE *ptd; // rax
  DVTARGETDEVICE v9; // xmm0
  HRESULT v10; // eax
  unsigned int v11; // ebx
  HRESULT v12; // eax
  DVTARGETDEVICE pitem; // [rsp+20h] [rbp-60h] BYREF
  __int64 v15; // [rsp+30h] [rbp-50h]
  DVTARGETDEVICE *p_pitem; // [rsp+38h] [rbp-48h]
  __int128 v17; // [rsp+40h] [rbp-40h]
  STGMEDIUM pstgmedDest; // [rsp+50h] [rbp-30h] BYREF

  ExtraDataIndex = CFtpObj::_FindExtraDataIndex((CFtpObj *)this, a2);
  if ( ExtraDataIndex == -1 )
  {
    memset_0(&pitem, 0, 0x48u);
    v7 = *(_OWORD *)&a2->dwAspect;
    v15 = *(_QWORD *)&a2->cfFormat;
    ptd = a2->ptd;
    p_pitem = ptd;
    v17 = v7;
    if ( ptd )
    {
      v9 = *ptd;
      p_pitem = &pitem;
      pitem = v9;
    }
    v10 = CopyStgMedium(a3, &pstgmedDest);
    pstgmedDest.pUnkForRelease = 0;
    v11 = v10;
    if ( v10 >= 0 )
      DSA_InsertItem(this[9], 0x7FFFFFFF, &pitem);
  }
  else
  {
    memset_0(&pitem, 0, 0x48u);
    DSA_GetItem(this[9], ExtraDataIndex, &pitem);
    ReleaseStgMedium(&pstgmedDest);
    v12 = CopyStgMedium(a3, &pstgmedDest);
    pstgmedDest.pUnkForRelease = 0;
    v11 = v12;
    if ( v12 >= 0 )
      DSA_SetItem(this[9], ExtraDataIndex, &pitem);
  }
  return v11;
}

```

## disassembly

```asm
0x18001b2e0  push    rbp
0x18001b2e2  push    rbx
0x18001b2e3  push    rsi
0x18001b2e4  push    rdi
0x18001b2e5  push    r14
0x18001b2e7  mov     rbp, rsp
0x18001b2ea  sub     rsp, 80h
0x18001b2f1  mov     rax, cs:__security_cookie
0x18001b2f8  xor     rax, rsp
0x18001b2fb  mov     [rbp+var_10], rax
0x18001b2ff  mov     r14, r8
0x18001b302  mov     rbx, rdx
0x18001b305  mov     rdi, rcx
0x18001b308  call    ?_FindExtraDataIndex@CFtpObj@@IEAAHPEBUtagFORMATETC@@@Z; CFtpObj::_FindExtraDataIndex(tagFORMATETC const *)
0x18001b30d  xor     edx, edx; Val
0x18001b30f  lea     rcx, [rbp+pitem]; void *
0x18001b313  mov     esi, eax
0x18001b315  lea     r8d, [rdx+48h]; Size
0x18001b319  cmp     eax, 0FFFFFFFFh
0x18001b31c  jnz     short loc_18001B37F
0x18001b31e  call    memset_0
0x18001b323  mov     rax, [rbx]
0x18001b326  movups  xmm0, xmmword ptr [rbx+10h]
0x18001b32a  mov     [rbp+var_50], rax
0x18001b32e  mov     rax, [rbx+8]
0x18001b332  mov     [rbp+var_48], rax
0x18001b336  movdqu  [rbp+var_40], xmm0
0x18001b33b  test    rax, rax
0x18001b33e  jz      short loc_18001B350
0x18001b340  movups  xmm0, xmmword ptr [rax]
0x18001b343  lea     rax, [rbp+pitem]
0x18001b347  mov     [rbp+var_48], rax
0x18001b34b  movdqu  [rbp+pitem], xmm0
0x18001b350  lea     rdx, [rbp+pstgmedDest]; pstgmedDest
0x18001b354  mov     rcx, r14; pcstgmedSrc
0x18001b357  call    cs:__imp_CopyStgMedium
0x18001b35d  mov     [rbp+pstgmedDest.pUnkForRelease], 0
0x18001b365  mov     ebx, eax
0x18001b367  test    eax, eax
0x18001b369  js      short loc_18001B3C7
0x18001b36b  mov     rcx, [rdi+48h]; hdsa
0x18001b36f  lea     r8, [rbp+pitem]; pitem
0x18001b373  mov     edx, 7FFFFFFFh; i
0x18001b378  call    DSA_InsertItem
0x18001b37d  jmp     short loc_18001B3C7
0x18001b37f  call    memset_0
0x18001b384  mov     rcx, [rdi+48h]; hdsa
0x18001b388  lea     r8, [rbp+pitem]; pitem
0x18001b38c  mov     edx, esi; i
0x18001b38e  call    DSA_GetItem
0x18001b393  lea     rcx, [rbp+pstgmedDest]; LPSTGMEDIUM
0x18001b397  call    cs:__imp_ReleaseStgMedium
0x18001b39d  lea     rdx, [rbp+pstgmedDest]; pstgmedDest
0x18001b3a1  mov     rcx, r14; pcstgmedSrc
0x18001b3a4  call    cs:__imp_CopyStgMedium
0x18001b3aa  mov     [rbp+pstgmedDest.pUnkForRelease], 0
0x18001b3b2  mov     ebx, eax
0x18001b3b4  test    eax, eax
0x18001b3b6  js      short loc_18001B3C7
0x18001b3b8  mov     rcx, [rdi+48h]; hdsa
0x18001b3bc  lea     r8, [rbp+pitem]; pitem
0x18001b3c0  mov     edx, esi; i
0x18001b3c2  call    DSA_SetItem
0x18001b3c7  mov     eax, ebx
0x18001b3c9  mov     rcx, [rbp+var_10]
0x18001b3cd  xor     rcx, rsp; StackCookie
0x18001b3d0  call    __security_check_cookie
0x18001b3d5  add     rsp, 80h
0x18001b3dc  pop     r14
0x18001b3de  pop     rdi
0x18001b3df  pop     rsi
0x18001b3e0  pop     rbx
0x18001b3e1  pop     rbp
0x18001b3e2  retn
```
