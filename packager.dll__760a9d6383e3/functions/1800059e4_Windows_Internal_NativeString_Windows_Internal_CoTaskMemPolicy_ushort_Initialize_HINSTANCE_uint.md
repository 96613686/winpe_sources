# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)

- ea: `0x1800059e4`
- end: `0x180005b35`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800050b0`

## callees

- `0x1800059e4`
- `0x1800066d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180005a4b`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180005a4b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005a39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005a39`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005a21`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005a21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b13`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  HMODULE v3; // rsi
  char v4; // bl
  int v6; // ebp
  HRSRC Resource; // rax
  HGLOBAL v8; // rax
  _WORD *v9; // rcx
  unsigned int v10; // edx
  unsigned int v11; // ebx
  __int64 *v12; // rsi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // r14
  _WORD *v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  _WORD *v18; // rcx

  v3 = g_hinst;
  v4 = a3;
  v6 = -2147467259;
  Resource = FindResourceExW(g_hinst, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), 0);
  if ( Resource )
  {
    v8 = LoadResource(v3, Resource);
    if ( v8 )
    {
      v9 = LockResource(v8);
      if ( v9 )
      {
        v10 = 0;
        v11 = v4 & 0xF;
        if ( v11 )
        {
          do
          {
            ++v10;
            v9 += (unsigned __int16)*v9 + 1;
          }
          while ( v10 < v11 );
        }
        v12 = (__int64 *)(v9 + 1);
        if ( !*v9 )
          v12 = &qword_180010440;
        if ( v12 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *((_WORD *)v12 + v13) );
          v14 = (unsigned __int16)*v9;
          if ( v14 < v13 )
            v13 = (unsigned __int16)*v9;
          v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                 a1,
                 (unsigned __int16)*v9);
          if ( v6 >= 0 )
          {
            v15 = *(_WORD **)a1;
            if ( v13 <= 0x7FFFFFFE )
            {
              v16 = v13;
              v17 = v14 + 1;
              do
              {
                if ( !v16 )
                  break;
                if ( !*(_WORD *)v12 )
                  break;
                *v15 = *(_WORD *)v12;
                v12 = (__int64 *)((char *)v12 + 2);
                ++v15;
                --v16;
                --v17;
              }
              while ( v17 );
              v18 = v15 - 1;
              if ( v17 )
                v18 = v15;
              *v18 = 0;
            }
            else
            {
              *v15 = 0;
            }
            *(_QWORD *)(a1 + 8) = v13;
          }
        }
        else
        {
          v6 = 0;
          if ( *(_QWORD *)a1 )
          {
            CoTaskMemFree(*(LPVOID *)a1);
            *(_QWORD *)a1 = 0;
          }
          *(_QWORD *)(a1 + 8) = 0;
          *(_QWORD *)(a1 + 16) = 0;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800059e4  push    rbx
0x1800059e6  push    rbp
0x1800059e7  push    rsi
0x1800059e8  push    rdi
0x1800059e9  push    r12
0x1800059eb  push    r14
0x1800059ed  push    r15
0x1800059ef  sub     rsp, 20h
0x1800059f3  mov     rsi, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x1800059fa  xor     r9d, r9d; wLanguage
0x1800059fd  mov     eax, r8d
0x180005a00  mov     ebx, r8d
0x180005a03  shr     eax, 4
0x180005a06  mov     rdi, rcx
0x180005a09  mov     rcx, rsi; hModule
0x180005a0c  mov     ebp, 80004005h
0x180005a11  lea     r12d, [r9+1]
0x180005a15  add     ax, r12w
0x180005a19  lea     edx, [r9+6]; lpType
0x180005a1d  movzx   r8d, ax; lpName
0x180005a21  call    cs:__imp_FindResourceExW
0x180005a27  xor     r15d, r15d
0x180005a2a  test    rax, rax
0x180005a2d  jz      loc_180005B24
0x180005a33  mov     rdx, rax; hResInfo
0x180005a36  mov     rcx, rsi; hModule
0x180005a39  call    cs:__imp_LoadResource
0x180005a3f  test    rax, rax
0x180005a42  jz      loc_180005B24
0x180005a48  mov     rcx, rax; hResData
0x180005a4b  call    cs:__imp_LockResource
0x180005a51  mov     rcx, rax
0x180005a54  test    rax, rax
0x180005a57  jz      loc_180005B24
0x180005a5d  mov     edx, r15d
0x180005a60  and     ebx, 0Fh
0x180005a63  jbe     short loc_180005A77
0x180005a65  movzx   eax, word ptr [rcx]
0x180005a68  add     edx, r12d
0x180005a6b  lea     rcx, [rcx+rax*2]
0x180005a6f  add     rcx, 2
0x180005a73  cmp     edx, ebx
0x180005a75  jb      short loc_180005A65
0x180005a77  lea     rsi, [rcx+2]
0x180005a7b  cmp     [rcx], r15w
0x180005a7f  jnz     short loc_180005A88
0x180005a81  lea     rsi, qword_180010440
0x180005a88  test    rsi, rsi
0x180005a8b  jz      short loc_180005B08
0x180005a8d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005a91  inc     rbx
0x180005a94  cmp     [rsi+rbx*2], r15w
0x180005a99  jnz     short loc_180005A91
0x180005a9b  movzx   r14d, word ptr [rcx]
0x180005a9f  mov     rcx, rdi
0x180005aa2  cmp     r14, rbx
0x180005aa5  mov     edx, r14d
0x180005aa8  cmovb   rbx, r14
0x180005aac  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180005ab1  mov     ebp, eax
0x180005ab3  test    eax, eax
0x180005ab5  js      short loc_180005B24
0x180005ab7  mov     rdx, [rdi]
0x180005aba  cmp     rbx, 7FFFFFFEh
0x180005ac1  jbe     short loc_180005AC9
0x180005ac3  mov     [rdx], r15w
0x180005ac7  jmp     short loc_180005B02
0x180005ac9  mov     rcx, rbx
0x180005acc  lea     rax, [r14+1]
0x180005ad0  test    rcx, rcx
0x180005ad3  jz      short loc_180005AF3
0x180005ad5  movzx   r8d, word ptr [rsi]
0x180005ad9  test    r8w, r8w
0x180005add  jz      short loc_180005AF3
0x180005adf  mov     [rdx], r8w
0x180005ae3  add     rsi, 2
0x180005ae7  add     rdx, 2
0x180005aeb  sub     rcx, r12
0x180005aee  sub     rax, r12
0x180005af1  jnz     short loc_180005AD0
0x180005af3  test    rax, rax
0x180005af6  lea     rcx, [rdx-2]
0x180005afa  cmovnz  rcx, rdx
0x180005afe  mov     [rcx], r15w
0x180005b02  mov     [rdi+8], rbx
0x180005b06  jmp     short loc_180005B24
0x180005b08  mov     rcx, [rdi]; pv
0x180005b0b  mov     ebp, r15d
0x180005b0e  test    rcx, rcx
0x180005b11  jz      short loc_180005B1C
0x180005b13  call    cs:__imp_CoTaskMemFree
0x180005b19  mov     [rdi], r15
0x180005b1c  mov     [rdi+8], r15
0x180005b20  mov     [rdi+10h], r15
0x180005b24  mov     eax, ebp
0x180005b26  add     rsp, 20h
0x180005b2a  pop     r15
0x180005b2c  pop     r14
0x180005b2e  pop     r12
0x180005b30  pop     rdi
0x180005b31  pop     rsi
0x180005b32  pop     rbp
0x180005b33  pop     rbx
0x180005b34  retn
```
