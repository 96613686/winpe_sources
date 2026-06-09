# GetAdapterIndexFromAdapterGuid(IDirect3D9 *,_GUID *)

- ea: `0x18003b81c`
- end: `0x18003ba34`
- name: `?GetAdapterIndexFromAdapterGuid@@YAIPEAUIDirect3D9@@PEAU_GUID@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(struct IDirect3D9 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180029780`

## callees

- `0x18001f620`
- `0x18001ffb0`
- `0x18003b81c`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003b878`
- `KERNEL32!GetProcAddress` at `0x18003b891`
- `KERNEL32!GetProcAddress` at `0x18003b878`
- `KERNEL32!GetProcAddress` at `0x18003b891`
- `KERNEL32!FreeLibrary` at `0x18003b9ee`
- `KERNEL32!FreeLibrary` at `0x18003ba01`
- `KERNEL32!FreeLibrary` at `0x18003b9ee`
- `KERNEL32!FreeLibrary` at `0x18003ba01`
- `KERNEL32!LoadLibraryW` at `0x18003b856`
- `KERNEL32!LoadLibraryW` at `0x18003b856`
- `KERNEL32!MultiByteToWideChar` at `0x18003b932`
- `KERNEL32!MultiByteToWideChar` at `0x18003b932`
- `GDI32!CreateDCW` at `0x18003b94d`
- `GDI32!CreateDCW` at `0x18003b94d`
- `GDI32!DeleteDC` at `0x18003b9c9`
- `GDI32!DeleteDC` at `0x18003b9df`
- `GDI32!DeleteDC` at `0x18003b9c9`
- `GDI32!DeleteDC` at `0x18003b9df`

## string_xrefs

- `0x18003b84f`: `gdi32.dll`
- `0x18003b86e`: `D3DKMTOpenAdapterFromHdc`

## pseudocode

```c
__int64 __fastcall GetAdapterIndexFromAdapterGuid(struct IDirect3D9 *a1, struct _GUID *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // r13
  FARPROC v7; // rax
  int (__fastcall *v8)(_QWORD); // r12
  unsigned int i; // edi
  HDC DCW; // r14
  __int64 v11; // rax
  _DWORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 *v14; // [rsp+38h] [rbp-C8h]
  __int64 v15; // [rsp+40h] [rbp-C0h]
  __int128 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+60h] [rbp-A0h] BYREF
  CHAR v19[1024]; // [rsp+70h] [rbp-90h] BYREF
  CHAR MultiByteStr[80]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR WideCharStr[64]; // [rsp+4C0h] [rbp+3C0h] BYREF

  LibraryW = LoadLibraryW(L"gdi32.dll");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "D3DKMTOpenAdapterFromHdc");
    v7 = GetProcAddress(v5, "D3DKMTQueryAdapterInfo");
    v8 = (int (__fastcall *)(_QWORD))v7;
    if ( ProcAddress )
    {
      if ( v7 )
      {
        for ( i = 0; i < ((unsigned int (__fastcall *)(struct IDirect3D9 *))a1->lpVtbl->GetAdapterCount)(a1); ++i )
        {
          v17 = 0;
          v16 = 0;
          memset_0(v19, 0, 0x450u);
          if ( ((int (__fastcall *)(struct IDirect3D9 *, _QWORD, _QWORD, CHAR *))a1->lpVtbl->GetAdapterIdentifier)(
                 a1,
                 i,
                 0,
                 v19) < 0 )
            return 0xFFFFFFFFLL;
          MultiByteToWideChar(0, 1u, MultiByteStr, -1, WideCharStr, 64);
          DCW = CreateDCW(0, WideCharStr, 0, 0);
          *(_QWORD *)&v16 = DCW;
          if ( ((int (__fastcall *)(__int128 *))ProcAddress)(&v16) >= 0 )
          {
            v13[0] = DWORD2(v16);
            v15 = 16;
            v14 = &v18;
            v18 = 0;
            v13[1] = 4;
            if ( v8(v13) >= 0 )
            {
              v11 = *(_QWORD *)&a2->Data1 - v18;
              if ( *(_QWORD *)&a2->Data1 == (_QWORD)v18 )
                v11 = *(_QWORD *)a2->Data4 - *((_QWORD *)&v18 + 1);
              if ( !v11 )
              {
                DeleteDC(DCW);
                FreeLibrary(v5);
                return i;
              }
            }
          }
          DeleteDC(DCW);
        }
        FreeLibrary(v5);
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18003b81c  push    rbp
0x18003b81e  push    rbx
0x18003b81f  push    rsi
0x18003b820  push    rdi
0x18003b821  push    r12
0x18003b823  push    r13
0x18003b825  push    r14
0x18003b827  push    r15
0x18003b829  lea     rbp, [rsp-458h]
0x18003b831  sub     rsp, 558h
0x18003b838  mov     rax, cs:__security_cookie
0x18003b83f  xor     rax, rsp
0x18003b842  mov     [rbp+490h+var_50], rax
0x18003b849  mov     rsi, rcx
0x18003b84c  mov     r15, rdx
0x18003b84f  lea     rcx, LibFileName; "gdi32.dll"
0x18003b856  call    cs:__imp_LoadLibraryW
0x18003b85d  nop     dword ptr [rax+rax+00h]
0x18003b862  mov     rbx, rax
0x18003b865  test    rax, rax
0x18003b868  jz      loc_18003BA0D
0x18003b86e  lea     rdx, aD3dkmtopenadap; "D3DKMTOpenAdapterFromHdc"
0x18003b875  mov     rcx, rax; hModule
0x18003b878  call    cs:__imp_GetProcAddress
0x18003b87f  nop     dword ptr [rax+rax+00h]
0x18003b884  lea     rdx, aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x18003b88b  mov     rcx, rbx; hModule
0x18003b88e  mov     r13, rax
0x18003b891  call    cs:__imp_GetProcAddress
0x18003b898  nop     dword ptr [rax+rax+00h]
0x18003b89d  mov     r12, rax
0x18003b8a0  test    r13, r13
0x18003b8a3  jz      loc_18003BA0D
0x18003b8a9  test    rax, rax
0x18003b8ac  jz      loc_18003BA0D
0x18003b8b2  xor     edi, edi
0x18003b8b4  mov     rax, [rsi]
0x18003b8b7  mov     rcx, rsi
0x18003b8ba  mov     rax, [rax+20h]
0x18003b8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8c3  cmp     edi, eax
0x18003b8c5  jnb     loc_18003B9FE
0x18003b8cb  xorps   xmm0, xmm0
0x18003b8ce  lea     rcx, [rsp+590h+var_520]; void *
0x18003b8d3  xor     eax, eax
0x18003b8d5  xor     edx, edx; Val
0x18003b8d7  mov     r8d, 450h; Size
0x18003b8dd  mov     [rsp+590h+var_538], rax
0x18003b8e2  movups  [rsp+590h+var_548], xmm0
0x18003b8e7  call    memset_0
0x18003b8ec  mov     rax, [rsi]
0x18003b8ef  lea     r9, [rsp+590h+var_520]
0x18003b8f4  xor     r8d, r8d
0x18003b8f7  mov     edx, edi
0x18003b8f9  mov     rcx, rsi
0x18003b8fc  mov     rax, [rax+28h]
0x18003b900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b905  test    eax, eax
0x18003b907  js      loc_18003BA0D
0x18003b90d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003b911  mov     [rsp+590h+cchWideChar], 40h ; '@'; cchWideChar
0x18003b919  lea     rax, [rbp+490h+WideCharStr]
0x18003b920  xor     ecx, ecx; CodePage
0x18003b922  lea     r8, [rbp+490h+MultiByteStr]; lpMultiByteStr
0x18003b929  mov     [rsp+590h+lpWideCharStr], rax; lpWideCharStr
0x18003b92e  lea     edx, [r9+2]; dwFlags
0x18003b932  call    cs:__imp_MultiByteToWideChar
0x18003b939  nop     dword ptr [rax+rax+00h]
0x18003b93e  xor     r9d, r9d; pdm
0x18003b941  lea     rdx, [rbp+490h+WideCharStr]; pwszDevice
0x18003b948  xor     r8d, r8d; pszPort
0x18003b94b  xor     ecx, ecx; pwszDriver
0x18003b94d  call    cs:__imp_CreateDCW
0x18003b954  nop     dword ptr [rax+rax+00h]
0x18003b959  mov     r14, rax
0x18003b95c  mov     qword ptr [rsp+590h+var_548], rax
0x18003b961  mov     rax, r13
0x18003b964  lea     rcx, [rsp+590h+var_548]
0x18003b969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b96e  test    eax, eax
0x18003b970  js      short loc_18003B9C6
0x18003b972  mov     eax, dword ptr [rsp+590h+var_548+8]
0x18003b976  lea     rcx, [rsp+590h+var_560]
0x18003b97b  mov     [rsp+590h+var_560], eax
0x18003b97f  xorps   xmm0, xmm0
0x18003b982  lea     rax, [rsp+590h+var_530]
0x18003b987  mov     [rsp+590h+var_550], 10h
0x18003b990  mov     [rsp+590h+var_558], rax
0x18003b995  mov     rax, r12
0x18003b998  movups  [rsp+590h+var_530], xmm0
0x18003b99d  mov     [rsp+590h+var_55C], 4
0x18003b9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9aa  test    eax, eax
0x18003b9ac  js      short loc_18003B9C6
0x18003b9ae  mov     rax, [r15]
0x18003b9b1  sub     rax, qword ptr [rsp+590h+var_530]
0x18003b9b6  jnz     short loc_18003B9C1
0x18003b9b8  mov     rax, [r15+8]
0x18003b9bc  sub     rax, qword ptr [rsp+590h+var_530+8]
0x18003b9c1  test    rax, rax
0x18003b9c4  jz      short loc_18003B9DC
0x18003b9c6  mov     rcx, r14; hdc
0x18003b9c9  call    cs:__imp_DeleteDC
0x18003b9d0  nop     dword ptr [rax+rax+00h]
0x18003b9d5  inc     edi
0x18003b9d7  jmp     loc_18003B8B4
0x18003b9dc  mov     rcx, r14; hdc
0x18003b9df  call    cs:__imp_DeleteDC
0x18003b9e6  nop     dword ptr [rax+rax+00h]
0x18003b9eb  mov     rcx, rbx; hLibModule
0x18003b9ee  call    cs:__imp_FreeLibrary
0x18003b9f5  nop     dword ptr [rax+rax+00h]
0x18003b9fa  mov     eax, edi
0x18003b9fc  jmp     short loc_18003BA10
0x18003b9fe  mov     rcx, rbx; hLibModule
0x18003ba01  call    cs:__imp_FreeLibrary
0x18003ba08  nop     dword ptr [rax+rax+00h]
0x18003ba0d  or      eax, 0FFFFFFFFh
0x18003ba10  mov     rcx, [rbp+490h+var_50]
0x18003ba17  xor     rcx, rsp; StackCookie
0x18003ba1a  call    __security_check_cookie
0x18003ba1f  add     rsp, 558h
0x18003ba26  pop     r15
0x18003ba28  pop     r14
0x18003ba2a  pop     r13
0x18003ba2c  pop     r12
0x18003ba2e  pop     rdi
0x18003ba2f  pop     rsi
0x18003ba30  pop     rbx
0x18003ba31  pop     rbp
0x18003ba32  retn
```
