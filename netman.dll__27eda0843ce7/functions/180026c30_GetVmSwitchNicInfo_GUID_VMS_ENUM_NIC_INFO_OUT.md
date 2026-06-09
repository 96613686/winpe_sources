# GetVmSwitchNicInfo(_GUID,_VMS_ENUM_NIC_INFO_OUT *)

- ea: `0x180026c30`
- end: `0x180026e66`
- name: `?GetVmSwitchNicInfo@@YAJU_GUID@@PEAU_VMS_ENUM_NIC_INFO_OUT@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct _GUID *Buf2, struct _VMS_ENUM_NIC_INFO_OUT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180026b0c`

## callees

- `0x180001710`
- `0x180002320`
- `0x180026c30`
- `0x180026ed8`
- `0x180034dfc`
- `0x180034e08`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180026cf5`
- `KERNEL32!FreeLibrary` at `0x180026cf5`
- `KERNEL32!GetProcAddress` at `0x180026d2a`
- `KERNEL32!GetProcAddress` at `0x180026d3d`
- `KERNEL32!GetProcAddress` at `0x180026d50`
- `KERNEL32!GetProcAddress` at `0x180026d63`
- `KERNEL32!GetProcAddress` at `0x180026d2a`
- `KERNEL32!GetProcAddress` at `0x180026d3d`
- `KERNEL32!GetProcAddress` at `0x180026d50`
- `KERNEL32!GetProcAddress` at `0x180026d63`
- `KERNEL32!LoadLibraryW` at `0x180026cad`
- `KERNEL32!LoadLibraryW` at `0x180026cad`

## string_xrefs

- `0x180026ca6`: `VMSIF.DLL`
- `0x180026d20`: `VmsIfDriverOpen`
- `0x180026d30`: `VmsIfNicEnumerateEx`
- `0x180026d43`: `VmsIfMemFree`
- `0x180026d56`: `VmsIfDriverClose`

## pseudocode

```c
__int64 __fastcall GetVmSwitchNicInfo(struct _GUID *Buf2, struct _VMS_ENUM_NIC_INFO_OUT *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rdi
  void (*v6)(void); // rsi
  void (*v7)(void); // r14
  unsigned int v8; // ebx
  FARPROC ProcAddress; // rbx
  FARPROC v11; // r15
  FARPROC v12; // rax
  _BYTE Src[772]; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+334h] [rbp+234h]
  unsigned __int16 v15[136]; // [rsp+960h] [rbp+860h] BYREF
  __int64 v16; // [rsp+A70h] [rbp+970h] BYREF
  __int64 v17; // [rsp+A78h] [rbp+978h] BYREF
  unsigned int v18; // [rsp+A80h] [rbp+980h] BYREF
  int v19; // [rsp+A88h] [rbp+988h] BYREF
  __int64 v20; // [rsp+A8Ch] [rbp+98Ch]
  struct _GUID Buf1; // [rsp+A98h] [rbp+998h] BYREF

  v17 = 0;
  v16 = 0;
  v19 = 2;
  v20 = 2612;
  v18 = 0;
  memset_0(a2, 0, 0xA34u);
  LibraryW = LoadLibraryW(L"VMSIF.DLL");
  v5 = LibraryW;
  if ( !LibraryW )
  {
    v6 = 0;
    v7 = 0;
LABEL_3:
    v8 = 3;
    goto LABEL_4;
  }
  ProcAddress = GetProcAddress(LibraryW, "VmsIfDriverOpen");
  v11 = GetProcAddress(v5, "VmsIfNicEnumerateEx");
  v6 = (void (*)(void))GetProcAddress(v5, "VmsIfMemFree");
  v12 = GetProcAddress(v5, "VmsIfDriverClose");
  v7 = (void (*)(void))v12;
  if ( !ProcAddress || !v11 || !v6 || !v12 )
    goto LABEL_3;
  v8 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v17);
  if ( !v8 )
  {
    v8 = ((__int64 (__fastcall *)(__int64, __int64 *, int *, unsigned int *))v11)(v17, &v16, &v19, &v18);
    if ( !v8 )
    {
      while ( v8 < v18 )
      {
        memcpy_0(Src, (const void *)(v16 + 2612LL * v8), 0xA34u);
        Buf1 = 0;
        if ( v14 == 1 )
        {
          ParseGuid(v15, &Buf1);
          if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
          {
            memcpy_0(a2, Src, 0xA34u);
            v8 = 0;
            goto LABEL_4;
          }
        }
        ++v8;
      }
      v8 = 2;
    }
  }
LABEL_4:
  if ( v16 )
    v6();
  if ( v17 )
    v7();
  if ( v5 )
    FreeLibrary(v5);
  return v8;
}

```

## disassembly

```asm
0x180026c30  push    rbp
0x180026c32  push    rbx
0x180026c33  push    rsi
0x180026c34  push    rdi
0x180026c35  push    r12
0x180026c37  push    r13
0x180026c39  push    r14
0x180026c3b  push    r15
0x180026c3d  lea     rbp, [rsp-9B8h]
0x180026c45  sub     rsp, 0AB8h
0x180026c4c  mov     rax, cs:__security_cookie
0x180026c53  xor     rax, rsp
0x180026c56  mov     [rbp+9F0h+var_48], rax
0x180026c5d  mov     r12, rdx
0x180026c60  mov     [rbp+9F0h+var_78], 0
0x180026c6b  mov     eax, 0A34h
0x180026c70  mov     [rbp+9F0h+var_80], 0
0x180026c7b  mov     r13, rcx
0x180026c7e  mov     [rbp+9F0h+var_68], 2
0x180026c88  mov     r8d, eax; Size
0x180026c8b  mov     [rbp+9F0h+var_64], rax
0x180026c92  mov     rcx, r12; void *
0x180026c95  mov     [rbp+9F0h+var_70], 0
0x180026c9f  xor     edx, edx; Val
0x180026ca1  call    memset_0
0x180026ca6  lea     rcx, aVmsifDll; "VMSIF.DLL"
0x180026cad  call    cs:__imp_LoadLibraryW
0x180026cb3  mov     rdi, rax
0x180026cb6  test    rax, rax
0x180026cb9  jnz     short loc_180026D20
0x180026cbb  xor     esi, esi
0x180026cbd  xor     r14d, r14d
0x180026cc0  mov     ebx, 3
0x180026cc5  mov     rcx, [rbp+9F0h+var_80]
0x180026ccc  test    rcx, rcx
0x180026ccf  jz      short loc_180026CD9
0x180026cd1  mov     rax, rsi
0x180026cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cd9  mov     rcx, [rbp+9F0h+var_78]
0x180026ce0  test    rcx, rcx
0x180026ce3  jz      short loc_180026CED
0x180026ce5  mov     rax, r14
0x180026ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ced  test    rdi, rdi
0x180026cf0  jz      short loc_180026CFB
0x180026cf2  mov     rcx, rdi; hLibModule
0x180026cf5  call    cs:__imp_FreeLibrary
0x180026cfb  mov     eax, ebx
0x180026cfd  mov     rcx, [rbp+9F0h+var_48]
0x180026d04  xor     rcx, rsp; StackCookie
0x180026d07  call    __security_check_cookie
0x180026d0c  add     rsp, 0AB8h
0x180026d13  pop     r15
0x180026d15  pop     r14
0x180026d17  pop     r13
0x180026d19  pop     r12
0x180026d1b  pop     rdi
0x180026d1c  pop     rsi
0x180026d1d  pop     rbx
0x180026d1e  pop     rbp
0x180026d1f  retn
0x180026d20  lea     rdx, aVmsifdriverope; "VmsIfDriverOpen"
0x180026d27  mov     rcx, rdi; hModule
0x180026d2a  call    cs:__imp_GetProcAddress
0x180026d30  lea     rdx, aVmsifnicenumer; "VmsIfNicEnumerateEx"
0x180026d37  mov     rcx, rdi; hModule
0x180026d3a  mov     rbx, rax
0x180026d3d  call    cs:__imp_GetProcAddress
0x180026d43  lea     rdx, aVmsifmemfree; "VmsIfMemFree"
0x180026d4a  mov     rcx, rdi; hModule
0x180026d4d  mov     r15, rax
0x180026d50  call    cs:__imp_GetProcAddress
0x180026d56  lea     rdx, aVmsifdriverclo; "VmsIfDriverClose"
0x180026d5d  mov     rcx, rdi; hModule
0x180026d60  mov     rsi, rax
0x180026d63  call    cs:__imp_GetProcAddress
0x180026d69  mov     r14, rax
0x180026d6c  test    rbx, rbx
0x180026d6f  jz      loc_180026CC0
0x180026d75  test    r15, r15
0x180026d78  jz      loc_180026CC0
0x180026d7e  test    rsi, rsi
0x180026d81  jz      loc_180026CC0
0x180026d87  test    rax, rax
0x180026d8a  jz      loc_180026CC0
0x180026d90  lea     rcx, [rbp+9F0h+var_78]
0x180026d97  mov     rax, rbx
0x180026d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d9f  mov     ebx, eax
0x180026da1  test    eax, eax
0x180026da3  jnz     loc_180026CC5
0x180026da9  mov     rcx, [rbp+9F0h+var_78]
0x180026db0  lea     r9, [rbp+9F0h+var_70]
0x180026db7  lea     r8, [rbp+9F0h+var_68]
0x180026dbe  mov     rax, r15
0x180026dc1  lea     rdx, [rbp+9F0h+var_80]
0x180026dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dcd  mov     ebx, eax
0x180026dcf  test    eax, eax
0x180026dd1  jnz     loc_180026CC5
0x180026dd7  mov     r15d, 0A34h
0x180026ddd  cmp     ebx, [rbp+9F0h+var_70]
0x180026de3  jnb     short loc_180026E5C
0x180026de5  mov     eax, ebx
0x180026de7  lea     rcx, [rsp+0AF0h+Src]; void *
0x180026dec  imul    rdx, rax, 0A34h
0x180026df3  mov     r8, r15; Size
0x180026df6  add     rdx, [rbp+9F0h+var_80]; Src
0x180026dfd  call    memcpy_0
0x180026e02  cmp     [rbp+9F0h+var_7BC], 1
0x180026e09  xorps   xmm0, xmm0
0x180026e0c  movups  [rbp+9F0h+Buf1], xmm0
0x180026e13  jnz     short loc_180026E41
0x180026e15  lea     rdx, [rbp+9F0h+Buf1]; struct _GUID *
0x180026e1c  lea     rcx, [rbp+9F0h+var_190]; unsigned __int16 *
0x180026e23  call    ?ParseGuid@@YAXPEBGAEAU_GUID@@@Z; ParseGuid(ushort const *,_GUID &)
0x180026e28  mov     r8d, 10h; Size
0x180026e2e  lea     rcx, [rbp+9F0h+Buf1]; Buf1
0x180026e35  mov     rdx, r13; Buf2
0x180026e38  call    memcmp_0
0x180026e3d  test    eax, eax
0x180026e3f  jz      short loc_180026E45
0x180026e41  inc     ebx
0x180026e43  jmp     short loc_180026DDD
0x180026e45  mov     rcx, r12; void *
0x180026e48  lea     rdx, [rsp+0AF0h+Src]; Src
0x180026e4d  mov     r8, r15; Size
0x180026e50  call    memcpy_0
0x180026e55  xor     ebx, ebx
0x180026e57  jmp     loc_180026CC5
0x180026e5c  mov     ebx, 2
0x180026e61  jmp     loc_180026CC5
```
