# CCabFolder::EnumObjects(HWND__ *,ulong,IEnumIDList * *)

- ea: `0x18000dfa0`
- end: `0x18000e160`
- name: `?EnumObjects@CCabFolder@@UEAAJPEAUHWND__@@KPEAPEAUIEnumIDList@@@Z`
- size: `448`
- prototype: `int(CCabFolder *__hidden this, HWND, unsigned int, struct IEnumIDList **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180002620`
- `0x18000dfa0`
- `0x18000f3c4`
- `0x18000f5cc`
- `0x180011e00`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000e0fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000e117`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000e0fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000e117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e052`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e01e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e01e`
- `USER32!MessageBoxW` at `0x18000e136`
- `USER32!MessageBoxW` at `0x18000e136`

## pseudocode

```c
__int64 __fastcall CCabFolder::EnumObjects(LPCITEMIDLIST *this, HWND a2, int a3, struct IEnumIDList **a4)
{
  LPCITEMIDLIST *v4; // r15
  signed int v8; // edi
  HANDLE FileW; // rax
  void *v10; // rsi
  int v11; // ebx
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  unsigned int *dwCreationDisposition; // [rsp+20h] [rbp-698h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-678h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-468h] BYREF
  WCHAR Text[264]; // [rsp+460h] [rbp-258h] BYREF

  v4 = this - 1;
  *a4 = 0;
  v8 = SHGetNameAndFlagsW(this[5], 0x8000u, FileName, (unsigned int)a4, dwCreationDisposition);
  if ( v8 >= 0 )
  {
    FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
    v10 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v8 = -2147467259;
    }
    else
    {
      v11 = VerifyCabFile(FileW);
      v8 = v11 == 0 ? 0x8007000B : 0;
      CloseHandle(v10);
      if ( v11 )
      {
        v12 = operator new(0x20u);
        v13 = v12;
        if ( v12 )
        {
          v12[2] = 1;
          *(_QWORD *)v12 = &CEnumCabObjs::`vftable';
          *((_QWORD *)v12 + 2) = v4;
          v12[6] = 0;
          v12[7] = a3;
          _InterlockedIncrement(&g_cRefThisDll);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 2) + 8LL))(*((_QWORD *)v12 + 2));
          v8 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, struct IEnumIDList **))v13)(
                 v13,
                 &GUID_000214f2_0000_0000_c000_000000000046,
                 a4);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 16LL))(v13);
          if ( v8 >= 0 )
            return (unsigned int)v8;
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
    if ( a2 )
    {
      LoadStringW(g_hinst, 0xFu, Buffer, 260);
      LoadStringW(g_hinst, 0x47u, Text, 260);
      MessageBoxW(a2, Text, Buffer, 0x10u);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000dfa0  push    rbx
0x18000dfa2  push    rbp
0x18000dfa3  push    rsi
0x18000dfa4  push    rdi
0x18000dfa5  push    r12
0x18000dfa7  push    r14
0x18000dfa9  push    r15
0x18000dfab  sub     rsp, 680h
0x18000dfb2  mov     rax, cs:__security_cookie
0x18000dfb9  xor     rax, rsp
0x18000dfbc  mov     [rsp+6B8h+var_48], rax
0x18000dfc4  lea     r15, [rcx-8]
0x18000dfc8  mov     qword ptr [r9], 0
0x18000dfcf  mov     rcx, [r15+30h]; pidl
0x18000dfd3  mov     r12d, r8d
0x18000dfd6  mov     rbp, rdx
0x18000dfd9  lea     r8, [rsp+6B8h+FileName]; unsigned __int16 *
0x18000dfde  mov     edx, 8000h; unsigned int
0x18000dfe3  mov     r14, r9
0x18000dfe6  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x18000dfeb  mov     edi, eax
0x18000dfed  test    eax, eax
0x18000dfef  js      loc_18000E13C
0x18000dff5  mov     [rsp+6B8h+hTemplateFile], 0; hTemplateFile
0x18000dffe  lea     rcx, [rsp+6B8h+FileName]; lpFileName
0x18000e003  mov     r8d, 3; dwShareMode
0x18000e009  mov     [rsp+6B8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000e011  xor     r9d, r9d; lpSecurityAttributes
0x18000e014  mov     dword ptr [rsp+6B8h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000e019  mov     edx, 80000000h; dwDesiredAccess
0x18000e01e  call    cs:__imp_CreateFileW
0x18000e024  mov     rsi, rax
0x18000e027  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e02b  jnz     short loc_18000E037
0x18000e02d  mov     edi, 80004005h
0x18000e032  jmp     loc_18000E0D9
0x18000e037  mov     rcx, rsi; void *
0x18000e03a  call    ?VerifyCabFile@@YAHPEAX@Z; VerifyCabFile(void *)
0x18000e03f  mov     ecx, eax
0x18000e041  mov     ebx, eax
0x18000e043  neg     ecx
0x18000e045  mov     rcx, rsi; hObject
0x18000e048  sbb     edi, edi
0x18000e04a  not     edi
0x18000e04c  and     edi, 8007000Bh
0x18000e052  call    cs:__imp_CloseHandle
0x18000e058  test    ebx, ebx
0x18000e05a  jz      short loc_18000E0D9
0x18000e05c  mov     ecx, 20h ; ' '; unsigned __int64
0x18000e061  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e066  mov     rbx, rax
0x18000e069  test    rax, rax
0x18000e06c  jz      short loc_18000E0D4
0x18000e06e  lea     rax, ??_7CEnumCabObjs@@6B@; const CEnumCabObjs::`vftable'
0x18000e075  mov     dword ptr [rbx+8], 1
0x18000e07c  mov     [rbx], rax
0x18000e07f  mov     [rbx+10h], r15
0x18000e083  mov     dword ptr [rbx+18h], 0
0x18000e08a  mov     [rbx+1Ch], r12d
0x18000e08e  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000e095  mov     rcx, [rbx+10h]
0x18000e099  mov     rdx, [rcx]
0x18000e09c  mov     rax, [rdx+8]
0x18000e0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a5  mov     rax, [rbx]
0x18000e0a8  lea     rdx, _GUID_000214f2_0000_0000_c000_000000000046
0x18000e0af  mov     r8, r14
0x18000e0b2  mov     rcx, rbx
0x18000e0b5  mov     rax, [rax]
0x18000e0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bd  mov     edi, eax
0x18000e0bf  mov     rcx, rbx
0x18000e0c2  mov     rax, [rbx]
0x18000e0c5  mov     rax, [rax+10h]
0x18000e0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0ce  test    edi, edi
0x18000e0d0  jns     short loc_18000E13C
0x18000e0d2  jmp     short loc_18000E0D9
0x18000e0d4  mov     edi, 8007000Eh
0x18000e0d9  test    rbp, rbp
0x18000e0dc  jz      short loc_18000E13C
0x18000e0de  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000e0e5  lea     r8, [rsp+6B8h+Buffer]; lpBuffer
0x18000e0ed  mov     ebx, 104h
0x18000e0f2  mov     edx, 0Fh; uID
0x18000e0f7  mov     r9d, ebx; cchBufferMax
0x18000e0fa  call    cs:__imp_LoadStringW
0x18000e100  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000e107  lea     r8, [rsp+6B8h+Text]; lpBuffer
0x18000e10f  mov     r9d, ebx; cchBufferMax
0x18000e112  mov     edx, 47h ; 'G'; uID
0x18000e117  call    cs:__imp_LoadStringW
0x18000e11d  mov     r9d, 10h; uType
0x18000e123  lea     r8, [rsp+6B8h+Buffer]; lpCaption
0x18000e12b  lea     rdx, [rsp+6B8h+Text]; lpText
0x18000e133  mov     rcx, rbp; hWnd
0x18000e136  call    cs:__imp_MessageBoxW
0x18000e13c  mov     eax, edi
0x18000e13e  mov     rcx, [rsp+6B8h+var_48]
0x18000e146  xor     rcx, rsp; StackCookie
0x18000e149  call    __security_check_cookie
0x18000e14e  add     rsp, 680h
0x18000e155  pop     r15
0x18000e157  pop     r14
0x18000e159  pop     r12
0x18000e15b  pop     rdi
0x18000e15c  pop     rsi
0x18000e15d  pop     rbp
0x18000e15e  pop     rbx
0x18000e15f  retn
```
