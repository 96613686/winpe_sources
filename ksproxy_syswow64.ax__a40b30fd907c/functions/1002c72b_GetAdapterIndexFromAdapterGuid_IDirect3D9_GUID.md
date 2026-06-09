# GetAdapterIndexFromAdapterGuid(IDirect3D9 *,_GUID *)

- ea: `0x1002c72b`
- end: `0x1002c8f1`
- name: `?GetAdapterIndexFromAdapterGuid@@YGIPAUIDirect3D9@@PAU_GUID@@@Z`
- size: `454`
- prototype: `unsigned int __fastcall(int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100188d0`

## callees

- `0x1002c72b`
- `0x1002d510`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1002c766`
- `KERNEL32!GetProcAddress` at `0x1002c77a`
- `KERNEL32!GetProcAddress` at `0x1002c766`
- `KERNEL32!GetProcAddress` at `0x1002c77a`
- `KERNEL32!FreeLibrary` at `0x1002c89f`
- `KERNEL32!FreeLibrary` at `0x1002c8d9`
- `KERNEL32!FreeLibrary` at `0x1002c89f`
- `KERNEL32!FreeLibrary` at `0x1002c8d9`
- `KERNEL32!LoadLibraryW` at `0x1002c750`
- `KERNEL32!LoadLibraryW` at `0x1002c750`
- `KERNEL32!MultiByteToWideChar` at `0x1002c7f7`
- `KERNEL32!MultiByteToWideChar` at `0x1002c7f7`
- `GDI32!CreateDCW` at `0x1002c807`
- `GDI32!CreateDCW` at `0x1002c807`
- `GDI32!DeleteDC` at `0x1002c898`
- `GDI32!DeleteDC` at `0x1002c8ae`
- `GDI32!DeleteDC` at `0x1002c898`
- `GDI32!DeleteDC` at `0x1002c8ae`

## string_xrefs

- `0x1002c743`: `gdi32.dll`
- `0x1002c760`: `D3DKMTOpenAdapterFromHdc`

## pseudocode

```c
unsigned int __fastcall GetAdapterIndexFromAdapterGuid(int *a1, int a2)
{
  HMODULE LibraryW; // eax
  HMODULE v4; // edi
  CD3DSurfaceAllocator *D3DKMTQueryAdapterInfo; // eax
  int v6; // eax
  unsigned int v7; // ecx
  HDC DCW; // esi
  int v9; // ecx
  int v11; // eax
  unsigned int v12; // eax
  _DWORD v13[5]; // [esp+Ch] [ebp-51Ch] BYREF
  _DWORD v14[4]; // [esp+20h] [ebp-508h] BYREF
  int v15; // [esp+30h] [ebp-4F8h]
  CD3DSurfaceAllocator *v16; // [esp+34h] [ebp-4F4h]
  CD3DSurfaceAllocator *D3DKMTOpenAdapterFromHdc; // [esp+38h] [ebp-4F0h]
  unsigned int v18; // [esp+3Ch] [ebp-4ECh]
  char v19[1024]; // [esp+40h] [ebp-4E8h] BYREF
  CHAR MultiByteStr[80]; // [esp+440h] [ebp-E8h] BYREF
  _DWORD v21[4]; // [esp+490h] [ebp-98h] BYREF
  WCHAR WideCharStr[66]; // [esp+4A0h] [ebp-88h] BYREF

  v15 = a2;
  LibraryW = LoadLibraryW(L"gdi32.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    D3DKMTOpenAdapterFromHdc = (CD3DSurfaceAllocator *)GetProcAddress(LibraryW, "D3DKMTOpenAdapterFromHdc");
    D3DKMTQueryAdapterInfo = (CD3DSurfaceAllocator *)GetProcAddress(v4, "D3DKMTQueryAdapterInfo");
    v16 = D3DKMTQueryAdapterInfo;
    if ( D3DKMTOpenAdapterFromHdc )
    {
      if ( D3DKMTQueryAdapterInfo )
      {
        v6 = *a1;
        v18 = 0;
        if ( (*(int (__thiscall **)(_DWORD, int *))(v6 + 16))(*(_DWORD *)(v6 + 16), a1) )
        {
          v7 = v18;
          while ( (*(int (__thiscall **)(_DWORD, int *, unsigned int, _DWORD, char *))(*a1 + 20))(
                    *(_DWORD *)(*a1 + 20),
                    a1,
                    v7,
                    0,
                    v19) >= 0 )
          {
            MultiByteToWideChar(0, 1u, MultiByteStr, -1, WideCharStr, 64);
            DCW = CreateDCW(0, WideCharStr, 0, 0);
            v13[0] = DCW;
            if ( ((int (__thiscall *)(CD3DSurfaceAllocator *, _DWORD *))D3DKMTOpenAdapterFromHdc)(
                   D3DKMTOpenAdapterFromHdc,
                   v13) >= 0 )
            {
              v14[0] = v13[1];
              v14[2] = v21;
              v14[1] = 4;
              v14[3] = 16;
              if ( ((int (__thiscall *)(CD3DSurfaceAllocator *, _DWORD *))v16)(v16, v14) >= 0 )
              {
                v9 = 0;
                while ( *(_DWORD *)(v15 + 4 * v9) == v21[v9] )
                {
                  if ( ++v9 == 4 )
                  {
                    DeleteDC(DCW);
                    FreeLibrary(v4);
                    return v18;
                  }
                }
              }
            }
            DeleteDC(DCW);
            v11 = *a1;
            ++v18;
            v12 = (*(int (__thiscall **)(_DWORD, int *))(v11 + 16))(*(_DWORD *)(v11 + 16), a1);
            v7 = v18;
            if ( v18 >= v12 )
              goto LABEL_14;
          }
        }
        else
        {
LABEL_14:
          FreeLibrary(v4);
        }
      }
    }
  }
  return -1;
}

```

## disassembly

```asm
0x1002c72b  mov     edi, edi
0x1002c72d  push    ebp
0x1002c72e  mov     ebp, esp
0x1002c730  sub     esp, 51Ch
0x1002c736  mov     eax, ___security_cookie
0x1002c73b  xor     eax, ebp
0x1002c73d  mov     [ebp+var_4], eax
0x1002c740  push    ebx
0x1002c741  push    esi
0x1002c742  push    edi
0x1002c743  push    offset LibFileName; "gdi32.dll"
0x1002c748  mov     [ebp+var_4F8], edx
0x1002c74e  mov     ebx, ecx
0x1002c750  call    ds:__imp__LoadLibraryW@4; LoadLibraryW(x)
0x1002c756  mov     edi, eax
0x1002c758  test    edi, edi
0x1002c75a  jz      loc_1002C8DF
0x1002c760  push    offset aD3dkmtopenadap; "D3DKMTOpenAdapterFromHdc"
0x1002c765  push    edi; hModule
0x1002c766  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1002c76c  push    offset aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x1002c771  mov     esi, eax
0x1002c773  push    edi; hModule
0x1002c774  mov     [ebp+var_4F0], esi
0x1002c77a  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1002c780  mov     [ebp+var_4F4], eax
0x1002c786  test    esi, esi
0x1002c788  jz      loc_1002C8DF
0x1002c78e  test    eax, eax
0x1002c790  jz      loc_1002C8DF
0x1002c796  mov     eax, [ebx]
0x1002c798  push    ebx
0x1002c799  mov     [ebp+var_4EC], 0
0x1002c7a3  mov     esi, [eax+10h]
0x1002c7a6  mov     ecx, esi; this
0x1002c7a8  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c7ae  call    esi
0x1002c7b0  test    eax, eax
0x1002c7b2  jz      loc_1002C8D8
0x1002c7b8  mov     ecx, [ebp+var_4EC]
0x1002c7be  mov     eax, [ebx]
0x1002c7c0  mov     esi, [eax+14h]
0x1002c7c3  lea     eax, [ebp+var_4E8]
0x1002c7c9  push    eax
0x1002c7ca  push    0
0x1002c7cc  push    ecx
0x1002c7cd  push    ebx
0x1002c7ce  mov     ecx, esi; this
0x1002c7d0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c7d6  call    esi
0x1002c7d8  test    eax, eax
0x1002c7da  js      loc_1002C8DF
0x1002c7e0  push    40h ; '@'; cchWideChar
0x1002c7e2  lea     eax, [ebp+WideCharStr]
0x1002c7e8  xor     esi, esi
0x1002c7ea  push    eax; lpWideCharStr
0x1002c7eb  push    0FFFFFFFFh; cbMultiByte
0x1002c7ed  lea     eax, [ebp+MultiByteStr]
0x1002c7f3  push    eax; lpMultiByteStr
0x1002c7f4  push    1; dwFlags
0x1002c7f6  push    esi; CodePage
0x1002c7f7  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1002c7fd  push    esi; pdm
0x1002c7fe  push    esi; pszPort
0x1002c7ff  lea     eax, [ebp+WideCharStr]
0x1002c805  push    eax; pwszDevice
0x1002c806  push    esi; pwszDriver
0x1002c807  call    ds:__imp__CreateDCW@16; CreateDCW(x,x,x,x)
0x1002c80d  mov     ecx, [ebp+var_4F0]; this
0x1002c813  mov     esi, eax
0x1002c815  lea     eax, [ebp+var_51C]
0x1002c81b  mov     [ebp+var_51C], esi
0x1002c821  push    eax
0x1002c822  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c828  call    [ebp+var_4F0]
0x1002c82e  test    eax, eax
0x1002c830  js      short loc_1002C8AD
0x1002c832  mov     eax, [ebp+var_518]
0x1002c838  mov     ecx, [ebp+var_4F4]; this
0x1002c83e  mov     [ebp+var_508], eax
0x1002c844  lea     eax, [ebp+var_98]
0x1002c84a  mov     [ebp+var_500], eax
0x1002c850  lea     eax, [ebp+var_508]
0x1002c856  push    eax
0x1002c857  mov     [ebp+var_504], 4
0x1002c861  mov     [ebp+var_4FC], 10h
0x1002c86b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c871  call    [ebp+var_4F4]
0x1002c877  test    eax, eax
0x1002c879  js      short loc_1002C8AD
0x1002c87b  lea     edx, [ebp+var_98]
0x1002c881  xor     ecx, ecx
0x1002c883  mov     eax, [ebp+var_4F8]
0x1002c889  mov     eax, [eax+ecx*4]
0x1002c88c  cmp     eax, [edx+ecx*4]
0x1002c88f  jnz     short loc_1002C8AD
0x1002c891  inc     ecx
0x1002c892  cmp     ecx, 4
0x1002c895  jnz     short loc_1002C883
0x1002c897  push    esi; hdc
0x1002c898  call    ds:__imp__DeleteDC@4; DeleteDC(x)
0x1002c89e  push    edi; hLibModule
0x1002c89f  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1002c8a5  mov     eax, [ebp+var_4EC]
0x1002c8ab  jmp     short loc_1002C8E2
0x1002c8ad  push    esi; hdc
0x1002c8ae  call    ds:__imp__DeleteDC@4; DeleteDC(x)
0x1002c8b4  mov     eax, [ebx]
0x1002c8b6  inc     [ebp+var_4EC]
0x1002c8bc  push    ebx
0x1002c8bd  mov     esi, [eax+10h]
0x1002c8c0  mov     ecx, esi; this
0x1002c8c2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c8c8  call    esi
0x1002c8ca  mov     ecx, [ebp+var_4EC]
0x1002c8d0  cmp     ecx, eax
0x1002c8d2  jb      loc_1002C7BE
0x1002c8d8  push    edi; hLibModule
0x1002c8d9  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1002c8df  or      eax, 0FFFFFFFFh
0x1002c8e2  mov     ecx, [ebp+var_4]
0x1002c8e5  pop     edi
0x1002c8e6  pop     esi
0x1002c8e7  xor     ecx, ebp; StackCookie
0x1002c8e9  pop     ebx
0x1002c8ea  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002c8ef  leave
0x1002c8f0  retn
```
