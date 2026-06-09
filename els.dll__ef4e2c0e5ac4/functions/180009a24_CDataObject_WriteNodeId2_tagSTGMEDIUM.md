# CDataObject::_WriteNodeId2(tagSTGMEDIUM *)

- ea: `0x180009a24`
- end: `0x180009b8f`
- name: `?_WriteNodeId2@CDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(CDataObject *__hidden this, struct tagSTGMEDIUM *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180009580`
- `0x180009620`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x1800036a6`
- `0x18000513c`
- `0x180009a24`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180009ac9`
- `msvcrt!_wcsupr` at `0x180009ac9`
- `KERNEL32!GetLastError` at `0x180009b09`
- `KERNEL32!GetLastError` at `0x180009b09`
- `KERNEL32!GlobalFree` at `0x180009b22`
- `KERNEL32!GlobalFree` at `0x180009b22`
- `KERNEL32!GlobalAlloc` at `0x180009ae5`
- `KERNEL32!GlobalAlloc` at `0x180009ae5`
- `KERNEL32!GlobalLock` at `0x180009afe`
- `KERNEL32!GlobalLock` at `0x180009afe`
- `KERNEL32!GlobalUnlock` at `0x180009b57`
- `KERNEL32!GlobalUnlock` at `0x180009b57`

## pseudocode

```c
__int64 __fastcall CDataObject::_WriteNodeId2(CDataObject *this, struct tagSTGMEDIUM *a2)
{
  __int64 v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  wchar_t *v10; // rcx
  size_t v11; // rsi
  HBITMAP v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  _DWORD *v15; // rax
  signed int LastError; // eax
  wchar_t **v17; // rdx
  wchar_t *String[2]; // [rsp+20h] [rbp-30h] BYREF
  int v20; // [rsp+30h] [rbp-20h]
  unsigned __int64 v21; // [rsp+38h] [rbp-18h]

  std::wstring::wstring(String);
  v4 = *(_QWORD *)(v3 + 16);
  if ( v4 )
  {
    v5 = (v4 + 32) & -(__int64)(*(_WORD *)(v4 + 32) != 0);
    if ( v5 )
      std::wstring::assign(String, v5);
  }
  v6 = std::char_traits<unsigned short>::length(L"\\");
  std::wstring::append(String, v7, v6);
  if ( v4 && v4 != -554 )
  {
    v8 = std::char_traits<unsigned short>::length(v4 + 554);
    std::wstring::append(String, v9, v8);
  }
  v10 = (wchar_t *)String;
  if ( v21 >= 8 )
    v10 = String[0];
  _wcsupr(v10);
  v11 = (unsigned int)(2 * v20 + 2);
  v12 = (HBITMAP)GlobalAlloc(0x2000u, v11 + 12);
  a2->hBitmap = v12;
  if ( v12 )
  {
    v15 = GlobalLock(v12);
    if ( v15 )
    {
      v14 = 0;
      v15[1] = v11;
      *v15 = 0;
      v17 = String;
      if ( v21 >= 8 )
        v17 = (wchar_t **)String[0];
      memcpy_0(v15 + 2, v17, v11);
      GlobalUnlock(a2->hBitmap);
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      GlobalFree(a2->hBitmap);
      a2->hBitmap = 0;
    }
  }
  else
  {
    v14 = -2147024882;
  }
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(String, v13, 0);
  return v14;
}

```

## disassembly

```asm
0x180009a24  mov     [rsp-18h+arg_10], rbx
0x180009a29  mov     [rsp-18h+arg_18], rsi
0x180009a2e  push    rbp
0x180009a2f  push    rdi
0x180009a30  push    r14
0x180009a32  mov     rbp, rsp
0x180009a35  sub     rsp, 50h
0x180009a39  mov     rax, cs:__security_cookie
0x180009a40  xor     rax, rsp
0x180009a43  mov     [rbp+var_10], rax
0x180009a47  mov     rdi, rdx
0x180009a4a  mov     r9, rcx
0x180009a4d  lea     rcx, [rbp+String]
0x180009a51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009a56  nop
0x180009a57  mov     rbx, [r9+10h]
0x180009a5b  test    rbx, rbx
0x180009a5e  jz      short loc_180009A7B
0x180009a60  lea     rcx, [rbx+20h]
0x180009a64  movzx   eax, word ptr [rcx]
0x180009a67  neg     ax
0x180009a6a  sbb     rdx, rdx
0x180009a6d  and     rdx, rcx
0x180009a70  jz      short loc_180009A7B
0x180009a72  lea     rcx, [rbp+String]
0x180009a76  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180009a7b  lea     rcx, SubBlock; "\\"
0x180009a82  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180009a87  mov     r8, rax
0x180009a8a  mov     rdx, rcx
0x180009a8d  lea     rcx, [rbp+String]
0x180009a91  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180009a96  test    rbx, rbx
0x180009a99  jz      short loc_180009ABB
0x180009a9b  lea     rcx, [rbx+22Ah]
0x180009aa2  test    rcx, rcx
0x180009aa5  jz      short loc_180009ABB
0x180009aa7  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180009aac  mov     r8, rax
0x180009aaf  mov     rdx, rcx
0x180009ab2  lea     rcx, [rbp+String]
0x180009ab6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180009abb  lea     rcx, [rbp+String]
0x180009abf  cmp     [rbp+var_18], 8
0x180009ac4  cmovnb  rcx, [rbp+String]; String
0x180009ac9  call    cs:__imp__wcsupr
0x180009acf  mov     eax, [rbp+var_20]
0x180009ad2  lea     esi, ds:2[rax*2]
0x180009ad9  mov     r14d, esi
0x180009adc  lea     rdx, [rsi+0Ch]; dwBytes
0x180009ae0  mov     ecx, 2000h; uFlags
0x180009ae5  call    cs:__imp_GlobalAlloc
0x180009aeb  mov     [rdi+8], rax
0x180009aef  test    rax, rax
0x180009af2  jnz     short loc_180009AFB
0x180009af4  mov     ebx, 8007000Eh
0x180009af9  jmp     short loc_180009B5E
0x180009afb  mov     rcx, rax; hMem
0x180009afe  call    cs:__imp_GlobalLock
0x180009b04  test    rax, rax
0x180009b07  jnz     short loc_180009B32
0x180009b09  call    cs:__imp_GetLastError
0x180009b0f  mov     ebx, eax
0x180009b11  test    eax, eax
0x180009b13  jle     short loc_180009B1E
0x180009b15  movzx   ebx, ax
0x180009b18  or      ebx, 80070000h
0x180009b1e  mov     rcx, [rdi+8]; hMem
0x180009b22  call    cs:__imp_GlobalFree
0x180009b28  mov     qword ptr [rdi+8], 0
0x180009b30  jmp     short loc_180009B5E
0x180009b32  xor     ebx, ebx
0x180009b34  mov     [rax+4], esi
0x180009b37  mov     [rax], ebx
0x180009b39  lea     rdx, [rbp+String]
0x180009b3d  cmp     [rbp+var_18], 8
0x180009b42  cmovnb  rdx, [rbp+String]; Src
0x180009b47  lea     rcx, [rax+8]; void *
0x180009b4b  mov     r8, r14; Size
0x180009b4e  call    memcpy_0
0x180009b53  mov     rcx, [rdi+8]; hMem
0x180009b57  call    cs:__imp_GlobalUnlock
0x180009b5d  nop
0x180009b5e  xor     r8d, r8d
0x180009b61  mov     dl, 1
0x180009b63  lea     rcx, [rbp+String]
0x180009b67  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009b6c  mov     eax, ebx
0x180009b6e  mov     rcx, [rbp+var_10]
0x180009b72  xor     rcx, rsp; StackCookie
0x180009b75  call    __security_check_cookie
0x180009b7a  lea     r11, [rsp+50h+var_s0]
0x180009b7f  mov     rbx, [r11+30h]
0x180009b83  mov     rsi, [r11+38h]
0x180009b87  mov     rsp, r11
0x180009b8a  pop     r14
0x180009b8c  pop     rdi
0x180009b8d  pop     rbp
0x180009b8e  retn
```
