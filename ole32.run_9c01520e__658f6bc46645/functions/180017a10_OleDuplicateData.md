# OleDuplicateData

- ea: `0x180017a10`
- end: `0x180017b7b`
- name: `OleDuplicateData`
- size: `363`
- prototype: `HANDLE __stdcall(HANDLE hSrc, CLIPFORMAT cfFormat, UINT uiFlags)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180018c70`
- `0x18003c1b8`
- `0x180070cf4`

## callees

- `0x180017a10`
- `0x180017b84`
- `0x18007ef8c`
- `0x1800aca50`
- `0x1800ad574`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180017b13`
- `KERNELBASE!GlobalFree` at `0x180017b13`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017adc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017b04`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017b4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017b5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017adc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017b04`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017b4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017b5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180017aae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180017aed`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180017aae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180017aed`
- `GDI32!CopyMetaFileW` at `0x180017b3b`
- `GDI32!CopyMetaFileW` at `0x180017b3b`
- `GDI32!CopyEnhMetaFileW` at `0x180017a83`
- `GDI32!CopyEnhMetaFileW` at `0x180017a83`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HANDLE __stdcall OleDuplicateData(HANDLE hSrc, CLIPFORMAT cfFormat, UINT uiFlags)
{
  UINT v5; // ebx
  void *v7; // rbx
  LPVOID v9; // rbp
  void *v10; // rax
  _QWORD *v11; // rax

  if ( !hSrc )
    return 0;
  v5 = 2;
  if ( cfFormat != 2 )
  {
    if ( cfFormat != 3 )
    {
      if ( cfFormat == 9 )
        return UtDupPalette((HPALETTE__ *)hSrc);
      if ( cfFormat == 14 )
        return CopyEnhMetaFileW((HENHMETAFILE)hSrc, 0);
      if ( uiFlags )
        v5 = uiFlags;
      return UtDupGlobal(hSrc, v5);
    }
    if ( VerifyStructFromHGlobal(3u, hSrc) >= 0 )
    {
      v9 = GlobalLock(hSrc);
      if ( v9 )
      {
        if ( uiFlags )
          v5 = uiFlags;
        v10 = UtDupGlobal(hSrc, v5);
        v7 = v10;
        if ( v10 )
        {
          v11 = GlobalLock(v10);
          if ( v11 )
          {
            *(_OWORD *)v11 = *(_OWORD *)v9;
            v11[2] = *((_QWORD *)v9 + 2);
            v11[2] = CopyMetaFileW(*((HMETAFILE *)v9 + 2), 0);
            GlobalUnlock(hSrc);
            GlobalUnlock(v7);
            return v7;
          }
          GlobalUnlock(hSrc);
          GlobalFree(v7);
        }
        else
        {
          GlobalUnlock(hSrc);
        }
      }
    }
    return 0;
  }
  return BmDuplicate((HBITMAP__ *)hSrc, (unsigned int *)cfFormat, (tagBITMAP *)cfFormat);
}

```

## disassembly

```asm
0x180017a10  mov     [rsp+arg_0], rbx
0x180017a15  mov     [rsp+arg_8], rbp
0x180017a1a  mov     [rsp+arg_10], rsi
0x180017a1f  push    rdi
0x180017a20  sub     rsp, 20h
0x180017a24  mov     esi, uiFlags
0x180017a27  movzx   uiFlags, cfFormat; lpdwSize
0x180017a2b  mov     rdi, hSrc
0x180017a2e  test    hSrc, hSrc
0x180017a31  jz      short loc_180017A7D
0x180017a33  mov     ecx, uiFlags
0x180017a36  mov     ebx, 2
0x180017a3b  sub     ecx, ebx
0x180017a3d  jz      loc_180017B6E
0x180017a43  sub     ecx, 1
0x180017a46  jz      short loc_180017A9B
0x180017a48  sub     ecx, 6
0x180017a4b  jz      short loc_180017A91
0x180017a4d  cmp     ecx, 5
0x180017a50  mov     hSrc, rdi; hEnh
0x180017a53  jz      short loc_180017A81
0x180017a55  test    esi, esi
0x180017a57  cmovnz  ebx, esi
0x180017a5a  mov     edx, ebx; uiFlags
0x180017a5c  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x180017a61  mov     rbx, rax
0x180017a64  mov     rbp, [rsp+28h+arg_8]
0x180017a69  mov     rax, rbx
0x180017a6c  mov     rbx, [rsp+28h+arg_0]
0x180017a71  mov     rsi, [rsp+28h+arg_10]
0x180017a76  add     rsp, 20h
0x180017a7a  pop     rdi
0x180017a7b  retn
0x180017a7d  xor     ebx, ebx
0x180017a7f  jmp     short $errRtn_5
0x180017a81  xor     edx, edx; lpFileName
0x180017a83  call    cs:__imp_CopyEnhMetaFileW
0x180017a8a  nop     dword ptr [rax+rax+00h]
0x180017a8f  jmp     short loc_180017A61
0x180017a91  mov     hSrc, rdi; hpalette
0x180017a94  call    ?UtDupPalette@@YAPEAUHPALETTE__@@PEAU1@@Z; UtDupPalette(HPALETTE__ *)
0x180017a99  jmp     short loc_180017A61
0x180017a9b  mov     rdx, rdi; hGlobal
0x180017a9e  movzx   ecx, r8w; cfFormat
0x180017aa2  call    ?VerifyStructFromHGlobal@@YAJGPEAX@Z; VerifyStructFromHGlobal(ushort,void *)
0x180017aa7  test    eax, eax
0x180017aa9  js      short loc_180017A7D
0x180017aab  mov     hSrc, rdi; hMem
0x180017aae  call    cs:__imp_GlobalLock
0x180017ab5  nop     dword ptr [rax+rax+00h]
0x180017aba  mov     rbp, rax
0x180017abd  test    rax, rax
0x180017ac0  jz      short loc_180017A7D
0x180017ac2  test    esi, esi
0x180017ac4  mov     hSrc, rdi; hsrc
0x180017ac7  cmovnz  ebx, esi
0x180017aca  mov     edx, ebx; uiFlags
0x180017acc  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x180017ad1  mov     rbx, rax
0x180017ad4  test    rax, rax
0x180017ad7  jnz     short loc_180017AEA
0x180017ad9  mov     hSrc, rdi; hMem
0x180017adc  call    cs:__imp_GlobalUnlock
0x180017ae3  nop     dword ptr [rax+rax+00h]
0x180017ae8  jmp     short loc_180017A7D
0x180017aea  mov     hSrc, rbx; hMem
0x180017aed  call    cs:__imp_GlobalLock
0x180017af4  nop     dword ptr [rax+rax+00h]
0x180017af9  mov     rsi, rax
0x180017afc  test    rax, rax
0x180017aff  jnz     short loc_180017B24
0x180017b01  mov     hSrc, rdi; hMem
0x180017b04  call    cs:__imp_GlobalUnlock
0x180017b0b  nop     dword ptr [rax+rax+00h]
0x180017b10  mov     hSrc, rbx; hMem
0x180017b13  call    cs:__imp_GlobalFree
0x180017b1a  nop     dword ptr [rax+rax+00h]
0x180017b1f  jmp     loc_180017A7D
0x180017b24  movups  xmm0, xmmword ptr [rbp+0]
0x180017b28  xor     edx, edx; LPCWSTR
0x180017b2a  movups  xmmword ptr [rax], xmm0
0x180017b2d  movsd   xmm1, qword ptr [rbp+10h]
0x180017b32  movsd   qword ptr [rax+10h], xmm1
0x180017b37  mov     hSrc, [rbp+10h]; HMETAFILE
0x180017b3b  call    cs:__imp_CopyMetaFileW
0x180017b42  nop     dword ptr [rax+rax+00h]
0x180017b47  mov     hSrc, rdi; hMem
0x180017b4a  mov     [rsi+10h], rax
0x180017b4e  call    cs:__imp_GlobalUnlock
0x180017b55  nop     dword ptr [rax+rax+00h]
0x180017b5a  mov     hSrc, rbx; hMem
0x180017b5d  call    cs:__imp_GlobalUnlock
0x180017b64  nop     dword ptr [rax+rax+00h]
0x180017b69  jmp     $errRtn_5
0x180017b6e  mov     hSrc, rdi; hold
0x180017b71  call    ?BmDuplicate@@YAPEAUHBITMAP__@@PEAU1@PEAKPEAUtagBITMAP@@@Z; BmDuplicate(HBITMAP__ *,ulong *,tagBITMAP *)
0x180017b76  jmp     loc_180017A61
```
