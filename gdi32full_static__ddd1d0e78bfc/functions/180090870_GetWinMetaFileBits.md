# GetWinMetaFileBits

- ea: `0x180090870`
- end: `0x180090a67`
- name: `GetWinMetaFileBits`
- size: `503`
- prototype: `UINT __stdcall(HENHMETAFILE hemf, UINT cbData16, LPBYTE pData16, INT iMapMode, HDC hdcRef)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180075218`

## callees

- `0x18002c5a0`
- `0x18002e040`
- `0x18004d5f8`
- `0x180052630`
- `0x180062a14`
- `0x180090870`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800909dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800909dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800909f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800909f2`
- `GDI32!GdiSetLastError` at `0x180090996`
- `GDI32!GdiSetLastError` at `0x180090a57`
- `GDI32!GdiSetLastError` at `0x180090996`
- `GDI32!GdiSetLastError` at `0x180090a57`

## string_xrefs

- `0x1800909d3`: `mf3216.dll`

## pseudocode

```c
UINT __stdcall GetWinMetaFileBits(HENHMETAFILE hemf, UINT cbData16, LPBYTE pData16, INT iMapMode, HDC hdcRef)
{
  UINT v5; // ebp
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // r8
  unsigned int *v13; // rdi
  void *v14; // rdx
  MF *v15; // rcx
  unsigned int v16; // eax
  _DWORD *v17; // rbx
  unsigned int *v18; // rdx
  size_t v19; // r8
  int v20; // ebx
  __int64 (__fastcall *v21)(_QWORD, unsigned int *, _QWORD, LPBYTE, INT, HDC, int); // r10
  HMODULE Library; // rax

  v5 = 0;
  if ( gbDisableMetaFiles )
    return v5;
  if ( (unsigned int)(iMapMode - 1) <= 7 && ((unsigned int)hemf & 0x7F0000) == 0x460000 )
  {
    v10 = pvClientObjGet(hemf, 4587520);
    v11 = v10;
    if ( !v10 )
      return v5;
    v12 = *(_QWORD *)(v10 + 48);
    if ( !v12 )
      return v5;
    v13 = (unsigned int *)EMFContainer::ObtainPtr((EMFContainer *)(v10 + 40), 0, *(_DWORD *)(v12 + 48));
    if ( !v13 )
      return v5;
    **(_QWORD **)(v11 + 688) = hemf;
    if ( (unsigned int)MF::bValidBoundedSize((MF *)v11, v13, v13[1]) )
    {
      v16 = v13[1];
      if ( v16 + 36 >= v16 )
      {
        if ( (unsigned int)MF::bValidBoundedSize(v15, v14, v16 + 36) )
        {
          v17 = (unsigned int *)((char *)v13 + v13[1]);
          if ( (unsigned int)bIsEMRPublicComment(v17) && v17[4] == -2147483647 )
          {
            if ( iMapMode == 8 && ((v17[5] - 256) & 0xFFFFFDFF) == 0 && !v17[7] && !GetDWordCheckSum(v13[12], v18) )
            {
              v19 = (unsigned int)v17[8];
              if ( (unsigned __int64)v13 + *(_QWORD *)(v11 + 56) - (_QWORD)v17 - 36 >= v19 )
              {
                if ( pData16 )
                {
                  if ( cbData16 < (unsigned int)v19 )
                  {
                    GdiSetLastError(122);
                    goto LABEL_27;
                  }
                  memcpy_0(pData16, v17 + 9, v19);
                }
                v5 = v17[8];
                goto LABEL_27;
              }
            }
            v20 = 0;
          }
          else
          {
            v20 = 1;
          }
          v21 = (__int64 (__fastcall *)(_QWORD, unsigned int *, _QWORD, LPBYTE, INT, HDC, int))qword_1800FE7D0;
          if ( qword_1800FE7D0
            || (Library = LoadLibraryExW(L"mf3216.dll", 0, 0),
                qword_1800FE7D0 = (__int64)GetProcAddress(Library, "ConvertEmfToWmf"),
                (v21 = (__int64 (__fastcall *)(_QWORD, unsigned int *, _QWORD, LPBYTE, INT, HDC, int))qword_1800FE7D0) != 0) )
          {
            v5 = v21(*(_QWORD *)(v11 + 688), v13, cbData16, pData16, iMapMode, hdcRef, v20);
          }
        }
      }
    }
LABEL_27:
    --*(_DWORD *)(v11 + 40);
    return v5;
  }
  GdiSetLastError(87);
  return 0;
}

```

## disassembly

```asm
0x180090870  push    rbx
0x180090872  push    rbp
0x180090873  push    rsi
0x180090874  push    rdi
0x180090875  push    r12
0x180090877  push    r14
0x180090879  push    r15
0x18009087b  sub     rsp, 40h
0x18009087f  xor     ebp, ebp
0x180090881  mov     r14d, r9d
0x180090884  cmp     cs:gbDisableMetaFiles, ebp
0x18009088a  mov     r15, r8
0x18009088d  mov     r12d, edx
0x180090890  mov     rbx, rcx
0x180090893  jnz     loc_180090A40
0x180090899  lea     eax, [r9-1]
0x18009089d  cmp     eax, 7
0x1800908a0  ja      loc_180090A52
0x1800908a6  mov     eax, ebx
0x1800908a8  mov     edx, 460000h
0x1800908ad  and     eax, 7F0000h
0x1800908b2  cmp     eax, edx
0x1800908b4  jnz     loc_180090A52
0x1800908ba  call    pvClientObjGet
0x1800908bf  mov     rsi, rax
0x1800908c2  test    rax, rax
0x1800908c5  jz      loc_180090A40
0x1800908cb  lea     rcx, [rax+28h]; this
0x1800908cf  mov     r8, [rcx+8]
0x1800908d3  test    r8, r8
0x1800908d6  jz      loc_180090A40
0x1800908dc  mov     r8d, [r8+30h]; unsigned int
0x1800908e0  xor     edx, edx; unsigned int
0x1800908e2  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x1800908e7  mov     rdi, rax
0x1800908ea  test    rax, rax
0x1800908ed  jz      loc_180090A40
0x1800908f3  mov     rax, [rsi+2B0h]
0x1800908fa  mov     rdx, rdi; void *
0x1800908fd  mov     rcx, rsi; this
0x180090900  mov     [rax], rbx
0x180090903  mov     r8d, [rdi+4]; unsigned int
0x180090907  call    ?bValidBoundedSize@MF@@QEAAHPEAXK@Z; MF::bValidBoundedSize(void *,ulong)
0x18009090c  test    eax, eax
0x18009090e  jz      loc_180090A3D
0x180090914  mov     eax, [rdi+4]
0x180090917  lea     r8d, [rax+24h]; unsigned int
0x18009091b  cmp     r8d, eax
0x18009091e  jb      loc_180090A3D
0x180090924  call    ?bValidBoundedSize@MF@@QEAAHPEAXK@Z; MF::bValidBoundedSize(void *,ulong)
0x180090929  test    eax, eax
0x18009092b  jz      loc_180090A3D
0x180090931  mov     ebx, [rdi+4]
0x180090934  add     rbx, rdi
0x180090937  mov     rcx, rbx
0x18009093a  call    bIsEMRPublicComment
0x18009093f  test    eax, eax
0x180090941  jz      short loc_1800909BF
0x180090943  cmp     dword ptr [rbx+10h], 80000001h
0x18009094a  jnz     short loc_1800909BF
0x18009094c  cmp     r14d, 8
0x180090950  jnz     short loc_1800909BB
0x180090952  mov     eax, [rbx+14h]
0x180090955  sub     eax, 100h
0x18009095a  test    eax, 0FFFFFDFFh
0x18009095f  jnz     short loc_1800909BB
0x180090961  cmp     [rbx+1Ch], ebp
0x180090964  jnz     short loc_1800909BB
0x180090966  mov     ecx, [rdi+30h]; unsigned int
0x180090969  call    ?GetDWordCheckSum@@YAKIPEAK@Z; GetDWordCheckSum(uint,ulong *)
0x18009096e  test    eax, eax
0x180090970  jnz     short loc_1800909BB
0x180090972  mov     rax, [rsi+38h]
0x180090976  mov     r8d, [rbx+20h]; Size
0x18009097a  sub     rax, rbx
0x18009097d  add     rax, 0FFFFFFFFFFFFFFDCh
0x180090981  add     rax, rdi
0x180090984  cmp     rax, r8
0x180090987  jb      short loc_1800909BB
0x180090989  test    r15, r15
0x18009098c  jz      short loc_1800909B3
0x18009098e  cmp     r12d, r8d
0x180090991  jnb     short loc_1800909A7
0x180090993  lea     ecx, [rbp+7Ah]
0x180090996  call    cs:__imp_GdiSetLastError
0x18009099d  nop     dword ptr [rax+rax+00h]
0x1800909a2  jmp     loc_180090A3D
0x1800909a7  lea     rdx, [rbx+24h]; Src
0x1800909ab  mov     rcx, r15; void *
0x1800909ae  call    memcpy_0
0x1800909b3  mov     ebp, [rbx+20h]
0x1800909b6  jmp     loc_180090A3D
0x1800909bb  xor     ebx, ebx
0x1800909bd  jmp     short loc_1800909C4
0x1800909bf  mov     ebx, 1
0x1800909c4  mov     r10, cs:qword_1800FE7D0
0x1800909cb  test    r10, r10
0x1800909ce  jnz     short loc_180090A0D
0x1800909d0  xor     r8d, r8d; dwFlags
0x1800909d3  lea     rcx, aMf3216Dll; "mf3216.dll"
0x1800909da  xor     edx, edx; hFile
0x1800909dc  call    cs:__imp_LoadLibraryExW
0x1800909e3  nop     dword ptr [rax+rax+00h]
0x1800909e8  mov     rcx, rax; hModule
0x1800909eb  lea     rdx, aConvertemftowm; "ConvertEmfToWmf"
0x1800909f2  call    cs:__imp_GetProcAddress
0x1800909f9  nop     dword ptr [rax+rax+00h]
0x1800909fe  mov     cs:qword_1800FE7D0, rax
0x180090a05  mov     r10, rax
0x180090a08  test    rax, rax
0x180090a0b  jz      short loc_180090A3D
0x180090a0d  mov     rax, [rsp+78h+hdcRef]
0x180090a15  mov     r9, r15
0x180090a18  mov     rcx, [rsi+2B0h]
0x180090a1f  mov     r8d, r12d
0x180090a22  mov     [rsp+78h+var_48], ebx
0x180090a26  mov     rdx, rdi
0x180090a29  mov     [rsp+78h+var_50], rax
0x180090a2e  mov     rax, r10
0x180090a31  mov     [rsp+78h+var_58], r14d
0x180090a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090a3b  mov     ebp, eax
0x180090a3d  dec     dword ptr [rsi+28h]
0x180090a40  mov     eax, ebp
0x180090a42  add     rsp, 40h
0x180090a46  pop     r15
0x180090a48  pop     r14
0x180090a4a  pop     r12
0x180090a4c  pop     rdi
0x180090a4d  pop     rsi
0x180090a4e  pop     rbp
0x180090a4f  pop     rbx
0x180090a50  retn
0x180090a52  mov     ecx, 57h ; 'W'
0x180090a57  call    cs:__imp_GdiSetLastError
0x180090a5e  nop     dword ptr [rax+rax+00h]
0x180090a63  xor     eax, eax
0x180090a65  jmp     short loc_180090A42
```
