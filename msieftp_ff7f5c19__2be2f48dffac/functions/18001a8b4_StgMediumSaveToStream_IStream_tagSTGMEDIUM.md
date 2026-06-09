# StgMediumSaveToStream(IStream *,tagSTGMEDIUM *)

- ea: `0x18001a8b4`
- end: `0x18001a9ef`
- name: `?StgMediumSaveToStream@@YAJPEAUIStream@@PEAUtagSTGMEDIUM@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(struct IStream *pstm, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a4a0`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001a8b4`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IStream_Write` at `0x18001a98b`
- `SHLWAPI!__imp_IStream_Write` at `0x18001a98b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a939`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001a939`

## pseudocode

```c
__int64 __fastcall StgMediumSaveToStream(struct IStream *pstm, struct tagSTGMEDIUM *a2)
{
  HRESULT v3; // ebx
  DWORD tymed; // eax
  HBITMAP hBitmap; // rcx
  LPSTREAM ppstm; // [rsp+30h] [rbp-29h] BYREF
  __int128 pv; // [rsp+38h] [rbp-21h] BYREF
  __int64 v9; // [rsp+48h] [rbp-11h]
  _BYTE v10[16]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v11; // [rsp+60h] [rbp+7h]

  v3 = -2147024809;
  if ( pstm )
  {
    v9 = 0;
    tymed = a2->tymed;
    pv = 0;
    DWORD2(pv) = tymed;
    LODWORD(pv) = 1;
    if ( tymed == 1 )
    {
      hBitmap = a2->hBitmap;
      ppstm = 0;
      v3 = CreateStreamOnHGlobal(hBitmap, 0, &ppstm);
      if ( v3 >= 0 )
      {
        memset_0(v10, 0, 0x50u);
        v3 = (*(__int64 (__fastcall **)(LPSTREAM, _BYTE *, __int64))(*(_QWORD *)ppstm + 96LL))(ppstm, v10, 1);
        if ( v3 >= 0 )
        {
          DWORD1(pv) = v11;
          v3 = IStream_Write(pstm, &pv, 0x18u);
          if ( v3 >= 0 )
            v3 = (*(__int64 (__fastcall **)(LPSTREAM, struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 56LL))(
                   ppstm,
                   pstm,
                   v11,
                   0,
                   0);
        }
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      }
    }
    else
    {
      return (unsigned int)-2147467263;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a8b4  mov     [rsp-8+arg_10], rbx
0x18001a8b9  mov     [rsp-8+arg_18], rdi
0x18001a8be  push    rbp
0x18001a8bf  lea     rbp, [rsp-57h]
0x18001a8c4  sub     rsp, 0B0h
0x18001a8cb  mov     rax, cs:__security_cookie
0x18001a8d2  xor     rax, rsp
0x18001a8d5  mov     [rbp+57h+var_10], rax
0x18001a8d9  mov     r9, rdx
0x18001a8dc  mov     rdi, rcx
0x18001a8df  mov     ebx, 80070057h
0x18001a8e4  test    rcx, rcx
0x18001a8e7  jz      loc_18001A9CC
0x18001a8ed  xor     eax, eax
0x18001a8ef  xorps   xmm0, xmm0
0x18001a8f2  mov     [rbp+57h+var_68], rax
0x18001a8f6  mov     eax, [rdx]
0x18001a8f8  movups  [rbp+57h+pv], xmm0
0x18001a8fc  mov     dword ptr [rbp+57h+pv+8], eax
0x18001a8ff  mov     dword ptr [rbp+57h+pv], 1
0x18001a906  sub     eax, 1
0x18001a909  jz      short loc_18001A927
0x18001a90b  sub     eax, 1
0x18001a90e  jz      short loc_18001A91D
0x18001a910  sub     eax, 2
0x18001a913  jz      short loc_18001A91D
0x18001a915  sub     eax, 4
0x18001a918  jz      short loc_18001A91D
0x18001a91a  sub     eax, 8
0x18001a91d  mov     ebx, 80004001h
0x18001a922  jmp     loc_18001A9CC
0x18001a927  mov     rcx, [r9+8]; hGlobal
0x18001a92b  lea     r8, [rbp+57h+ppstm]; ppstm
0x18001a92f  xor     edx, edx; fDeleteOnRelease
0x18001a931  mov     [rbp+57h+ppstm], 0
0x18001a939  call    cs:__imp_CreateStreamOnHGlobal
0x18001a93f  mov     ebx, eax
0x18001a941  test    eax, eax
0x18001a943  js      loc_18001A9CC
0x18001a949  xor     edx, edx; Val
0x18001a94b  lea     rcx, [rbp+57h+var_60]; void *
0x18001a94f  lea     r8d, [rdx+50h]; Size
0x18001a953  call    memset_0
0x18001a958  mov     rcx, [rbp+57h+ppstm]
0x18001a95c  lea     rdx, [rbp+57h+var_60]
0x18001a960  mov     r8d, 1
0x18001a966  mov     rax, [rcx]
0x18001a969  mov     rax, [rax+60h]
0x18001a96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a972  mov     ebx, eax
0x18001a974  test    eax, eax
0x18001a976  js      short loc_18001A9BC
0x18001a978  mov     eax, dword ptr [rbp+57h+var_50]
0x18001a97b  lea     rdx, [rbp+57h+pv]; pv
0x18001a97f  mov     r8d, 18h; cb
0x18001a985  mov     dword ptr [rbp+57h+pv+4], eax
0x18001a988  mov     rcx, rdi; pstm
0x18001a98b  call    cs:__imp_IStream_Write
0x18001a991  mov     ebx, eax
0x18001a993  test    eax, eax
0x18001a995  js      short loc_18001A9BC
0x18001a997  mov     rcx, [rbp+57h+ppstm]
0x18001a99b  xor     r9d, r9d
0x18001a99e  mov     r8, [rbp+57h+var_50]
0x18001a9a2  mov     rdx, rdi
0x18001a9a5  mov     [rsp+0B0h+var_90], 0
0x18001a9ae  mov     rax, [rcx]
0x18001a9b1  mov     rax, [rax+38h]
0x18001a9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ba  mov     ebx, eax
0x18001a9bc  mov     rcx, [rbp+57h+ppstm]
0x18001a9c0  mov     rax, [rcx]
0x18001a9c3  mov     rax, [rax+10h]
0x18001a9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9cc  mov     eax, ebx
0x18001a9ce  mov     rcx, [rbp+57h+var_10]
0x18001a9d2  xor     rcx, rsp; StackCookie
0x18001a9d5  call    __security_check_cookie
0x18001a9da  lea     r11, [rsp+0B0h+var_s0]
0x18001a9e2  mov     rbx, [r11+20h]
0x18001a9e6  mov     rdi, [r11+28h]
0x18001a9ea  mov     rsp, r11
0x18001a9ed  pop     rbp
0x18001a9ee  retn
```
