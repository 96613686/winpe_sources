# CSharePageWarn::_AddItem(CDPA<CResultItem,CTContainer_PolicyUnOwned<CResultItem>> &,IShellItem *,IShellItem *,ushort *)

- ea: `0x180070a2c`
- end: `0x180070d0c`
- name: `?_AddItem@CSharePageWarn@@AEAAJAEAV?$CDPA@VCResultItem@@V?$CTContainer_PolicyUnOwned@VCResultItem@@@@@@PEAUIShellItem@@1PEAG@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070d14`

## callees

- `0x1800098dc`
- `0x18000f720`
- `0x180013220`
- `0x1800132f0`
- `0x1800254e0`
- `0x1800259bc`
- `0x18006467c`
- `0x180065b00`
- `0x180070a2c`
- `0x180073528`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180070b98`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180070c75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180070b98`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180070c75`
- `SHELL32!SHGetFolderPathEx` at `0x180070ab9`
- `SHELL32!SHGetFolderPathEx` at `0x180070ab9`
- `SHELL32!__imp_PathIsEqualOrSubFolder` at `0x180070ad1`
- `SHELL32!__imp_PathIsEqualOrSubFolder` at `0x180070ad1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharePageWarn::_AddItem(
        __int64 a1,
        HDPA *a2,
        struct IShellItem *a3,
        struct IShellItem *a4,
        CResultItem *a5)
{
  int Error; // ebx
  int v9; // edi
  int v10; // esi
  struct _DPA *v11; // rcx
  int v12; // eax
  unsigned __int16 *Ptr; // r12
  int v14; // eax
  CResultItem *v15; // rax
  CResultItem *v16; // rdi
  unsigned int v17; // edx
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  CResultItem *v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[12]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[528]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v24[784]; // [rsp+280h] [rbp+180h] BYREF

  v20 = a5;
  v21 = 0;
  Error = ((__int64 (__fastcall *)(struct IShellItem *, __int64, __int64 *))a3->lpVtbl->GetDisplayName)(
            a3,
            2147844096LL,
            &v21);
  if ( Error >= 0
    && (int)SHGetFolderPathEx(&FOLDERID_Public, 0x4000, 0, v23, 260) >= 0
    && !(unsigned int)PathIsEqualOrSubFolder(v23, v21) )
  {
    v9 = 0;
    v10 = 0;
    while ( 1 )
    {
      if ( v9 )
        return (unsigned int)Error;
      v11 = *a2;
      if ( *a2 )
        v12 = *(_DWORD *)v11;
      else
        v12 = 0;
      if ( v10 >= v12 )
        goto LABEL_24;
      Ptr = (unsigned __int16 *)DPA_GetPtr(v11, v10);
      v19 = 0;
      Error = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, __int64, int *))a3->lpVtbl->Compare)(
                a3,
                *(_QWORD *)Ptr,
                0x10000000,
                &v19);
      if ( Error >= 0 )
      {
        v14 = v19;
        if ( !v19 )
        {
          if ( a4 )
          {
            Error = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, __int64, int *))a4->lpVtbl->Compare)(
                      a4,
                      *((_QWORD *)Ptr + 1),
                      0x10000000,
                      &v19);
            if ( Error < 0 )
              goto LABEL_22;
            v14 = v19;
          }
          if ( !v14 )
          {
            if ( LoadStringW(g_hInstance, 0xD19u, Buffer, 10) )
            {
              Error = 0;
LABEL_19:
              if ( (int)SHFormatMessageArg(1024, (unsigned int)Buffer, 0, 0, (__int64)v24) >= 0 )
                StringCchCopyW(Ptr + 12, 0x30Cu, v24);
              v9 = 1;
              goto LABEL_22;
            }
            Error = ResultFromKnownLastError();
            if ( Error >= 0 )
              goto LABEL_19;
          }
        }
      }
LABEL_22:
      ++v10;
      if ( Error < 0 )
      {
        if ( v9 )
          return (unsigned int)Error;
LABEL_24:
        v15 = (CResultItem *)operator new(0x630u, (const struct std::nothrow_t *)std::nothrow);
        v20 = v15;
        if ( v15 )
          v16 = CResultItem::CResultItem(v15, a3, 0, a4);
        else
          v16 = 0;
        if ( v16 )
        {
          if ( LoadStringW(g_hInstance, 0xD18u, v24, 780) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              return (unsigned int)Error;
          }
          SHFormatMessageArg(1024, (unsigned int)v24, 0, 0, (__int64)v16 + 24);
          if ( DPA_InsertPtr(*a2, 0x7FFFFFFF, v16) == -1 )
            CResultItem::`scalar deleting destructor'(v16, v17);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
        return (unsigned int)Error;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180070a2c  mov     [rsp-8+arg_0], rbx
0x180070a31  push    rbp
0x180070a32  push    rsi
0x180070a33  push    rdi
0x180070a34  push    r12
0x180070a36  push    r13
0x180070a38  push    r14
0x180070a3a  push    r15
0x180070a3c  lea     rbp, [rsp-7B0h]
0x180070a44  sub     rsp, 8B0h
0x180070a4b  mov     rax, cs:__security_cookie
0x180070a52  xor     rax, rsp
0x180070a55  mov     [rbp+7E0h+var_40], rax
0x180070a5c  mov     r14, r9
0x180070a5f  mov     r15, r8
0x180070a62  mov     r13, rdx
0x180070a65  mov     r12, [rbp+7E0h+arg_20]
0x180070a6c  mov     [rsp+8E0h+var_898], r12
0x180070a71  mov     [rsp+8E0h+var_890], 0
0x180070a7a  mov     rax, [r8]
0x180070a7d  lea     r8, [rsp+8E0h+var_890]
0x180070a82  mov     edx, 80058000h
0x180070a87  mov     rcx, r15
0x180070a8a  mov     rax, [rax+28h]
0x180070a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a93  mov     ebx, eax
0x180070a95  test    eax, eax
0x180070a97  js      loc_180070CE0
0x180070a9d  mov     dword ptr [rsp+8E0h+var_8C0], 104h
0x180070aa5  lea     r9, [rsp+8E0h+var_870]
0x180070aaa  xor     r8d, r8d
0x180070aad  mov     edx, 4000h
0x180070ab2  lea     rcx, FOLDERID_Public
0x180070ab9  call    cs:__imp_SHGetFolderPathEx
0x180070abf  test    eax, eax
0x180070ac1  js      loc_180070CE0
0x180070ac7  mov     rdx, [rsp+8E0h+var_890]
0x180070acc  lea     rcx, [rsp+8E0h+var_870]
0x180070ad1  call    cs:__imp_PathIsEqualOrSubFolder
0x180070ad7  test    eax, eax
0x180070ad9  jnz     loc_180070CE0
0x180070adf  xor     edi, edi
0x180070ae1  xor     esi, esi
0x180070ae3  test    edi, edi
0x180070ae5  jnz     loc_180070CE0
0x180070aeb  mov     rcx, [r13+0]; hdpa
0x180070aef  test    rcx, rcx
0x180070af2  jz      short loc_180070AF8
0x180070af4  mov     eax, [rcx]
0x180070af6  jmp     short loc_180070AFA
0x180070af8  xor     eax, eax
0x180070afa  cmp     esi, eax
0x180070afc  jge     loc_180070C24
0x180070b02  movsxd  rdx, esi; i
0x180070b05  call    DPA_GetPtr
0x180070b0a  mov     r12, rax
0x180070b0d  mov     [rsp+8E0h+var_8A0], 0
0x180070b15  mov     rcx, [r15]
0x180070b18  mov     rax, [rcx+38h]
0x180070b1c  lea     r9, [rsp+8E0h+var_8A0]
0x180070b21  mov     r8d, 10000000h
0x180070b27  mov     rdx, [r12]
0x180070b2b  mov     rcx, r15
0x180070b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b33  mov     ebx, eax
0x180070b35  test    eax, eax
0x180070b37  js      loc_180070C0D
0x180070b3d  mov     eax, [rsp+8E0h+var_8A0]
0x180070b41  test    eax, eax
0x180070b43  jnz     loc_180070C0D
0x180070b49  test    r14, r14
0x180070b4c  jz      short loc_180070B7B
0x180070b4e  mov     rax, [r14]
0x180070b51  lea     r9, [rsp+8E0h+var_8A0]
0x180070b56  mov     r8d, 10000000h
0x180070b5c  mov     rdx, [r12+8]
0x180070b61  mov     rcx, r14
0x180070b64  mov     rax, [rax+38h]
0x180070b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b6d  mov     ebx, eax
0x180070b6f  test    eax, eax
0x180070b71  js      loc_180070C0D
0x180070b77  mov     eax, [rsp+8E0h+var_8A0]
0x180070b7b  test    eax, eax
0x180070b7d  jnz     loc_180070C0D
0x180070b83  lea     r9d, [rax+0Ah]; cchBufferMax
0x180070b87  lea     r8, [rsp+8E0h+Buffer]; lpBuffer
0x180070b8c  mov     edx, 0D19h; uID
0x180070b91  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180070b98  call    cs:__imp_LoadStringW
0x180070b9e  test    eax, eax
0x180070ba0  jz      short loc_180070BA6
0x180070ba2  xor     ebx, ebx
0x180070ba4  jmp     short loc_180070BB1
0x180070ba6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180070bab  mov     ebx, eax
0x180070bad  test    eax, eax
0x180070baf  js      short loc_180070C0D
0x180070bb1  lea     rdi, [r12+18h]
0x180070bb6  mov     r12, [rsp+8E0h+var_898]
0x180070bbb  mov     [rsp+8E0h+var_8A8], r12
0x180070bc0  mov     [rsp+8E0h+var_8B0], rdi
0x180070bc5  mov     [rsp+8E0h+var_8B8], 30Ch
0x180070bcd  lea     rax, [rbp+7E0h+var_660]
0x180070bd4  mov     [rsp+8E0h+var_8C0], rax
0x180070bd9  xor     r9d, r9d
0x180070bdc  xor     r8d, r8d
0x180070bdf  lea     rdx, [rsp+8E0h+Buffer]
0x180070be4  mov     ecx, 400h
0x180070be9  call    SHFormatMessageArg
0x180070bee  test    eax, eax
0x180070bf0  js      short loc_180070C06
0x180070bf2  lea     r8, [rbp+7E0h+var_660]; unsigned __int16 *
0x180070bf9  mov     edx, 30Ch; unsigned __int64
0x180070bfe  mov     rcx, rdi; unsigned __int16 *
0x180070c01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180070c06  mov     edi, 1
0x180070c0b  jmp     short loc_180070C12
0x180070c0d  mov     r12, [rsp+8E0h+var_898]
0x180070c12  inc     esi
0x180070c14  test    ebx, ebx
0x180070c16  jns     loc_180070AE3
0x180070c1c  test    edi, edi
0x180070c1e  jnz     loc_180070CE0
0x180070c24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180070c2b  mov     ecx, 630h; unsigned __int64
0x180070c30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180070c35  mov     [rsp+8E0h+var_898], rax
0x180070c3a  test    rax, rax
0x180070c3d  jz      short loc_180070C55
0x180070c3f  mov     r9, r14; struct IShellItem *
0x180070c42  xor     r8d, r8d; struct IShellItem *
0x180070c45  mov     rdx, r15; struct IShellItem *
0x180070c48  mov     rcx, rax; this
0x180070c4b  call    ??0CResultItem@@QEAA@PEAUIShellItem@@00@Z; CResultItem::CResultItem(IShellItem *,IShellItem *,IShellItem *)
0x180070c50  mov     rdi, rax
0x180070c53  jmp     short loc_180070C57
0x180070c55  xor     edi, edi
0x180070c57  test    rdi, rdi
0x180070c5a  jz      short loc_180070CDB
0x180070c5c  mov     r9d, 30Ch; cchBufferMax
0x180070c62  lea     r8, [rbp+7E0h+var_660]; lpBuffer
0x180070c69  mov     edx, 0D18h; uID
0x180070c6e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180070c75  call    cs:__imp_LoadStringW
0x180070c7b  test    eax, eax
0x180070c7d  jz      short loc_180070C83
0x180070c7f  xor     ebx, ebx
0x180070c81  jmp     short loc_180070C8E
0x180070c83  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180070c88  mov     ebx, eax
0x180070c8a  test    eax, eax
0x180070c8c  js      short loc_180070CE0
0x180070c8e  lea     rax, [rdi+18h]
0x180070c92  mov     [rsp+8E0h+var_8B0], r12
0x180070c97  mov     [rsp+8E0h+var_8B8], 30Ch
0x180070c9f  mov     [rsp+8E0h+var_8C0], rax
0x180070ca4  xor     r9d, r9d
0x180070ca7  xor     r8d, r8d
0x180070caa  lea     rdx, [rbp+7E0h+var_660]
0x180070cb1  mov     ecx, 400h
0x180070cb6  call    SHFormatMessageArg
0x180070cbb  mov     r8, rdi; p
0x180070cbe  mov     edx, 7FFFFFFFh; i
0x180070cc3  mov     rcx, [r13+0]; hdpa
0x180070cc7  call    DPA_InsertPtr
0x180070ccc  cmp     eax, 0FFFFFFFFh
0x180070ccf  jnz     short loc_180070CE0
0x180070cd1  mov     rcx, rdi; this
0x180070cd4  call    ??_GCResultItem@@QEAAPEAXI@Z; CResultItem::`scalar deleting destructor'(uint)
0x180070cd9  jmp     short loc_180070CE0
0x180070cdb  mov     ebx, 8007000Eh
0x180070ce0  mov     eax, ebx
0x180070ce2  mov     rcx, [rbp+7E0h+var_40]
0x180070ce9  xor     rcx, rsp; StackCookie
0x180070cec  call    __security_check_cookie
0x180070cf1  mov     rbx, [rsp+8E0h+arg_0]
0x180070cf9  add     rsp, 8B0h
0x180070d00  pop     r15
0x180070d02  pop     r14
0x180070d04  pop     r13
0x180070d06  pop     r12
0x180070d08  pop     rdi
0x180070d09  pop     rsi
0x180070d0a  pop     rbp
0x180070d0b  retn
```
