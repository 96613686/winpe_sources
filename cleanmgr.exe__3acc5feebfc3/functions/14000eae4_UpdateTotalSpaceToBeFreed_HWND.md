# UpdateTotalSpaceToBeFreed(HWND__ *)

- ea: `0x14000eae4`
- end: `0x14000ebdc`
- name: `?UpdateTotalSpaceToBeFreed@@YAXPEAUHWND__@@@Z`
- size: `248`
- prototype: `void __fastcall(HWND hDlg)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000bd24`
- `0x14000c358`

## callees

- `0x1400029a0`
- `0x14000eae4`

## import_xrefs

- `USER32!LoadStringW` at `0x14000eb9d`
- `USER32!LoadStringW` at `0x14000eb9d`
- `USER32!SetDlgItemTextW` at `0x14000ebc3`
- `USER32!SetDlgItemTextW` at `0x14000ebc3`
- `USER32!GetWindowLongPtrW` at `0x14000eb09`
- `USER32!GetWindowLongPtrW` at `0x14000eb09`
- `SHLWAPI!StrFormatByteSizeW` at `0x14000ebb0`
- `SHLWAPI!StrFormatByteSizeW` at `0x14000ebb0`

## pseudocode

```c
void __fastcall UpdateTotalSpaceToBeFreed(HWND hDlg)
{
  LONG_PTR WindowLongPtrW; // rax
  int v3; // r9d
  int v4; // r8d
  LONGLONG v5; // rcx
  __int64 v6; // r10
  int i; // edx
  __int64 v8; // rax
  __int64 v9; // rax
  WCHAR Buffer[8]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v11; // [rsp+30h] [rbp-28h]
  int v12; // [rsp+40h] [rbp-18h]

  if ( hDlg )
  {
    WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
    if ( WindowLongPtrW )
    {
      if ( *(_DWORD *)WindowLongPtrW != 26 )
      {
        v3 = *(_DWORD *)(WindowLongPtrW + 1736);
        v4 = 0;
        v5 = 0;
        if ( v3 > 0 )
        {
          v6 = *(_QWORD *)(WindowLongPtrW + 1744);
          for ( i = 0; i < v3; ++i )
          {
            v8 = 616LL * (unsigned int)i;
            if ( *(_DWORD *)(v8 + v6 + 604) )
            {
              v9 = *(_QWORD *)(v8 + v6 + 592);
              if ( v9 == -1 )
                v4 = 1;
              else
                v5 += v9;
            }
          }
        }
        v12 = 0;
        *(_OWORD *)Buffer = 0;
        v11 = 0;
        if ( v5 || !v4 )
          StrFormatByteSizeW(v5, Buffer, 0x12u);
        else
          LoadStringW(g_hInstance, 0x1Du, Buffer, 18);
        SetDlgItemTextW(hDlg, 1026, Buffer);
      }
    }
  }
}

```

## disassembly

```asm
0x14000eae4  test    rcx, rcx
0x14000eae7  jz      locret_14000EBDB
0x14000eaed  push    rbx
0x14000eaee  sub     rsp, 50h
0x14000eaf2  mov     rax, cs:__security_cookie
0x14000eaf9  xor     rax, rsp
0x14000eafc  mov     [rsp+58h+var_10], rax
0x14000eb01  mov     edx, 10h; nIndex
0x14000eb06  mov     rbx, rcx
0x14000eb09  call    cs:__imp_GetWindowLongPtrW
0x14000eb0f  test    rax, rax
0x14000eb12  jz      loc_14000EBC9
0x14000eb18  cmp     dword ptr [rax], 1Ah
0x14000eb1b  jz      loc_14000EBC9
0x14000eb21  mov     r9d, [rax+6C8h]
0x14000eb28  xor     r8d, r8d
0x14000eb2b  xor     ecx, ecx
0x14000eb2d  test    r9d, r9d
0x14000eb30  jle     short loc_14000EB6D
0x14000eb32  mov     r10, [rax+6D0h]
0x14000eb39  xor     edx, edx
0x14000eb3b  mov     eax, edx
0x14000eb3d  imul    rax, 268h
0x14000eb44  cmp     dword ptr [rax+r10+25Ch], 0
0x14000eb4d  jz      short loc_14000EB66
0x14000eb4f  mov     rax, [rax+r10+250h]
0x14000eb57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000eb5b  jnz     short loc_14000EB63
0x14000eb5d  lea     r8d, [rax+2]
0x14000eb61  jmp     short loc_14000EB66
0x14000eb63  add     rcx, rax; qdw
0x14000eb66  inc     edx
0x14000eb68  cmp     edx, r9d
0x14000eb6b  jl      short loc_14000EB3B
0x14000eb6d  xor     eax, eax
0x14000eb6f  xorps   xmm0, xmm0
0x14000eb72  mov     [rsp+58h+var_18], eax
0x14000eb76  movups  xmmword ptr [rsp+58h+Buffer], xmm0
0x14000eb7b  movups  [rsp+58h+var_28], xmm0
0x14000eb80  test    rcx, rcx
0x14000eb83  jnz     short loc_14000EBA5
0x14000eb85  test    r8d, r8d
0x14000eb88  jz      short loc_14000EBA5
0x14000eb8a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14000eb91  lea     r9d, [rax+12h]; cchBufferMax
0x14000eb95  lea     r8, [rsp+58h+Buffer]; lpBuffer
0x14000eb9a  lea     edx, [rax+1Dh]; uID
0x14000eb9d  call    cs:__imp_LoadStringW
0x14000eba3  jmp     short loc_14000EBB6
0x14000eba5  mov     r8d, 12h; cchBuf
0x14000ebab  lea     rdx, [rsp+58h+Buffer]; pszBuf
0x14000ebb0  call    cs:__imp_StrFormatByteSizeW
0x14000ebb6  lea     r8, [rsp+58h+Buffer]; lpString
0x14000ebbb  mov     edx, 402h; nIDDlgItem
0x14000ebc0  mov     rcx, rbx; hDlg
0x14000ebc3  call    cs:__imp_SetDlgItemTextW
0x14000ebc9  mov     rcx, [rsp+58h+var_10]
0x14000ebce  xor     rcx, rsp; StackCookie
0x14000ebd1  call    __security_check_cookie
0x14000ebd6  add     rsp, 50h
0x14000ebda  pop     rbx
0x14000ebdb  retn
```
