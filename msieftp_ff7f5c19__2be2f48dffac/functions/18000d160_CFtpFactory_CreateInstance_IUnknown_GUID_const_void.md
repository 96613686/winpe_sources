# CFtpFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000d160`
- end: `0x18000d2a8`
- name: `?CreateInstance@CFtpFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(CFtpFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000d160`
- `0x180015bc8`
- `0x180019774`
- `0x180023adc`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d186`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d186`

## string_xrefs

- `0x18000d17f`: `msieftp.dll`

## pseudocode

```c
__int64 __fastcall CFtpFactory::CreateInstance(
        CFtpFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v8; // ebx
  CFtpFolder *v9; // rax
  CFtpFolder *v10; // rax
  CFtpFolder *v11; // rsi
  CFtpObj *v12; // rax
  CFtpObj *v13; // rax
  CFtpObj *v14; // rsi

  if ( !g_hInstanceThisLeak )
    g_hInstanceThisLeak = LoadLibraryW(L"msieftp.dll");
  if ( a2 )
  {
    v8 = -2147221232;
  }
  else
  {
    if ( *(_QWORD *)((char *)this + 12) == *(_QWORD *)&CLSID_FtpFolder.Data1
      && *(_QWORD *)((char *)this + 20) == *(_QWORD *)CLSID_FtpFolder.Data4 )
    {
      v8 = -2147024882;
      v9 = (CFtpFolder *)operator new(0xA0u);
      if ( v9 )
      {
        v10 = CFtpFolder::CFtpFolder(v9);
        *a4 = 0;
        v11 = v10;
        if ( v10 )
        {
          v8 = (**(__int64 (__fastcall ***)(CFtpFolder *, const struct _GUID *, void **))v10)(v10, a3, a4);
          (*(void (__fastcall **)(CFtpFolder *))(*(_QWORD *)v11 + 16LL))(v11);
        }
        goto LABEL_18;
      }
      goto LABEL_17;
    }
    v8 = -2147221164;
    if ( *(_QWORD *)((char *)this + 12) == *(_QWORD *)&CLSID_FtpDataObject.Data1
      && *(_QWORD *)((char *)this + 20) == *(_QWORD *)CLSID_FtpDataObject.Data4 )
    {
      v8 = -2147024882;
      v12 = (CFtpObj *)operator new(0x1D0u);
      if ( v12 )
      {
        v13 = CFtpObj::CFtpObj(v12);
        *a4 = 0;
        v14 = v13;
        if ( v13 )
        {
          if ( !*((_DWORD *)v13 + 20) )
            v8 = (**(__int64 (__fastcall ***)(CFtpObj *, const struct _GUID *, void **))v13)(v13, a3, a4);
          (*(void (__fastcall **)(CFtpObj *))(*(_QWORD *)v14 + 16LL))(v14);
        }
LABEL_18:
        if ( v8 >= 0 )
          return (unsigned int)v8;
        goto LABEL_21;
      }
LABEL_17:
      *a4 = 0;
      goto LABEL_18;
    }
  }
LABEL_21:
  if ( a4 )
    *a4 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d160  push    rbx
0x18000d162  push    rbp
0x18000d163  push    rsi
0x18000d164  push    rdi
0x18000d165  sub     rsp, 28h
0x18000d169  cmp     cs:?g_hInstanceThisLeak@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hInstanceThisLeak
0x18000d171  mov     rdi, r9
0x18000d174  mov     rbp, r8
0x18000d177  mov     rbx, rdx
0x18000d17a  mov     rsi, rcx
0x18000d17d  jnz     short loc_18000D193
0x18000d17f  lea     rcx, LibFileName; "msieftp.dll"
0x18000d186  call    cs:__imp_LoadLibraryW
0x18000d18c  mov     cs:?g_hInstanceThisLeak@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstanceThisLeak
0x18000d193  test    rbx, rbx
0x18000d196  jnz     loc_18000D28C
0x18000d19c  mov     rax, [rsi+0Ch]
0x18000d1a0  cmp     rax, qword ptr cs:CLSID_FtpFolder.Data1
0x18000d1a7  jnz     short loc_18000D208
0x18000d1a9  mov     rax, [rsi+14h]
0x18000d1ad  cmp     rax, qword ptr cs:CLSID_FtpFolder.Data4
0x18000d1b4  jnz     short loc_18000D208
0x18000d1b6  mov     ecx, 0A0h; unsigned __int64
0x18000d1bb  mov     ebx, 8007000Eh
0x18000d1c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d1c5  test    rax, rax
0x18000d1c8  jz      loc_18000D27F
0x18000d1ce  mov     rcx, rax; this
0x18000d1d1  call    ??0CFtpFolder@@QEAA@XZ; CFtpFolder::CFtpFolder(void)
0x18000d1d6  mov     qword ptr [rdi], 0
0x18000d1dd  mov     rsi, rax
0x18000d1e0  test    rax, rax
0x18000d1e3  jz      loc_18000D286
0x18000d1e9  mov     rcx, [rax]
0x18000d1ec  mov     r8, rdi
0x18000d1ef  mov     rdx, rbp
0x18000d1f2  mov     rax, [rcx]
0x18000d1f5  mov     rcx, rsi
0x18000d1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1fd  mov     rcx, [rsi]
0x18000d200  mov     ebx, eax
0x18000d202  mov     rax, [rcx+10h]
0x18000d206  jmp     short loc_18000D275
0x18000d208  mov     rax, [rsi+0Ch]
0x18000d20c  mov     ebx, 80040154h
0x18000d211  cmp     rax, qword ptr cs:?CLSID_FtpDataObject@@3U_GUID@@B.Data1; _GUID const CLSID_FtpDataObject ...
0x18000d218  jnz     short loc_18000D291
0x18000d21a  mov     rax, [rsi+14h]
0x18000d21e  cmp     rax, qword ptr cs:?CLSID_FtpDataObject@@3U_GUID@@B.Data4; _GUID const CLSID_FtpDataObject ...
0x18000d225  jnz     short loc_18000D291
0x18000d227  mov     ecx, 1D0h; unsigned __int64
0x18000d22c  mov     ebx, 8007000Eh
0x18000d231  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d236  test    rax, rax
0x18000d239  jz      short loc_18000D27F
0x18000d23b  mov     rcx, rax; this
0x18000d23e  call    ??0CFtpObj@@IEAA@XZ; CFtpObj::CFtpObj(void)
0x18000d243  mov     qword ptr [rdi], 0
0x18000d24a  mov     rsi, rax
0x18000d24d  test    rax, rax
0x18000d250  jz      short loc_18000D286
0x18000d252  cmp     dword ptr [rax+50h], 0
0x18000d256  jnz     short loc_18000D26E
0x18000d258  mov     rcx, [rax]
0x18000d25b  mov     r8, rdi
0x18000d25e  mov     rdx, rbp
0x18000d261  mov     rax, [rcx]
0x18000d264  mov     rcx, rsi
0x18000d267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d26c  mov     ebx, eax
0x18000d26e  mov     rax, [rsi]
0x18000d271  mov     rax, [rax+10h]
0x18000d275  mov     rcx, rsi
0x18000d278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d27d  jmp     short loc_18000D286
0x18000d27f  mov     qword ptr [rdi], 0
0x18000d286  test    ebx, ebx
0x18000d288  jns     short loc_18000D29D
0x18000d28a  jmp     short loc_18000D291
0x18000d28c  mov     ebx, 80040110h
0x18000d291  test    rdi, rdi
0x18000d294  jz      short loc_18000D29D
0x18000d296  mov     qword ptr [rdi], 0
0x18000d29d  mov     eax, ebx
0x18000d29f  add     rsp, 28h
0x18000d2a3  pop     rdi
0x18000d2a4  pop     rsi
0x18000d2a5  pop     rbp
0x18000d2a6  pop     rbx
0x18000d2a7  retn
```
