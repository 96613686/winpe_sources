# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)

- ea: `0x1800151c8`
- end: `0x1800152ff`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014f20`

## callees

- `0x1800151c8`
- `0x180015958`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800151f2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800151f2`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001521c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001521c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001520a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001520a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152df`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1)
{
  HMODULE v1; // rbx
  int v3; // ebp
  HRSRC Resource; // rax
  HGLOBAL v5; // rax
  _WORD *v6; // rcx
  int v7; // edx
  const unsigned __int16 *v8; // rsi
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r14
  _WORD *v11; // rdx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  _WORD *v14; // rcx

  v1 = g_hInstance;
  v3 = -2147467259;
  Resource = FindResourceExW(g_hInstance, (LPCWSTR)6, (LPCWSTR)0x13, 0);
  if ( Resource )
  {
    v5 = LoadResource(v1, Resource);
    if ( v5 )
    {
      v6 = LockResource(v5);
      if ( v6 )
      {
        v7 = 12;
        do
        {
          v6 += (unsigned __int16)*v6 + 1;
          --v7;
        }
        while ( v7 );
        v8 = v6 + 1;
        if ( !*v6 )
          v8 = &dword_1800684AC;
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( v8[v9] );
          v10 = (unsigned __int16)*v6;
          if ( v10 < v9 )
            v9 = (unsigned __int16)*v6;
          v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                 a1,
                 (unsigned __int16)*v6);
          if ( v3 >= 0 )
          {
            v11 = *(_WORD **)a1;
            if ( v9 <= 0x7FFFFFFE )
            {
              v12 = v9;
              v13 = v10 + 1;
              do
              {
                if ( !v12 )
                  break;
                if ( !*v8 )
                  break;
                *v11++ = *v8++;
                --v12;
                --v13;
              }
              while ( v13 );
              v14 = v11 - 1;
              if ( v13 )
                v14 = v11;
              *v14 = 0;
            }
            else
            {
              *v11 = 0;
            }
            *(_QWORD *)(a1 + 8) = v9;
          }
        }
        else
        {
          v3 = 0;
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
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800151c8  push    rbx
0x1800151ca  push    rbp
0x1800151cb  push    rsi
0x1800151cc  push    rdi
0x1800151cd  push    r14
0x1800151cf  push    r15
0x1800151d1  sub     rsp, 28h
0x1800151d5  mov     rbx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800151dc  xor     r9d, r9d; wLanguage
0x1800151df  mov     rdi, rcx
0x1800151e2  mov     ebp, 80004005h
0x1800151e7  mov     rcx, rbx; hModule
0x1800151ea  lea     edx, [r9+6]; lpType
0x1800151ee  lea     r8d, [r9+13h]; lpName
0x1800151f2  call    cs:__imp_FindResourceExW
0x1800151f8  xor     r15d, r15d
0x1800151fb  test    rax, rax
0x1800151fe  jz      loc_1800152F0
0x180015204  mov     rdx, rax; hResInfo
0x180015207  mov     rcx, rbx; hModule
0x18001520a  call    cs:__imp_LoadResource
0x180015210  test    rax, rax
0x180015213  jz      loc_1800152F0
0x180015219  mov     rcx, rax; hResData
0x18001521c  call    cs:__imp_LockResource
0x180015222  mov     rcx, rax
0x180015225  test    rax, rax
0x180015228  jz      loc_1800152F0
0x18001522e  lea     edx, [r15+0Ch]
0x180015232  movzx   eax, word ptr [rcx]
0x180015235  lea     rcx, [rcx+rax*2]
0x180015239  lea     rcx, [rcx+2]
0x18001523d  add     edx, 0FFFFFFFFh
0x180015240  jnz     short loc_180015232
0x180015242  lea     rsi, [rcx+2]
0x180015246  cmp     [rcx], r15w
0x18001524a  jnz     short loc_180015253
0x18001524c  lea     rsi, dword_1800684AC
0x180015253  test    rsi, rsi
0x180015256  jz      short loc_1800152D4
0x180015258  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001525c  inc     rbx
0x18001525f  cmp     [rsi+rbx*2], r15w
0x180015264  jnz     short loc_18001525C
0x180015266  movzx   r14d, word ptr [rcx]
0x18001526a  mov     rcx, rdi
0x18001526d  cmp     r14, rbx
0x180015270  mov     edx, r14d
0x180015273  cmovb   rbx, r14
0x180015277  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18001527c  mov     ebp, eax
0x18001527e  test    eax, eax
0x180015280  js      short loc_1800152F0
0x180015282  mov     rdx, [rdi]
0x180015285  cmp     rbx, 7FFFFFFEh
0x18001528c  jbe     short loc_180015294
0x18001528e  mov     [rdx], r15w
0x180015292  jmp     short loc_1800152CE
0x180015294  mov     rcx, rbx
0x180015297  lea     rax, [r14+1]
0x18001529b  test    rcx, rcx
0x18001529e  jz      short loc_1800152BF
0x1800152a0  movzx   r8d, word ptr [rsi]
0x1800152a4  test    r8w, r8w
0x1800152a8  jz      short loc_1800152BF
0x1800152aa  mov     [rdx], r8w
0x1800152ae  add     rsi, 2
0x1800152b2  add     rdx, 2
0x1800152b6  dec     rcx
0x1800152b9  sub     rax, 1
0x1800152bd  jnz     short loc_18001529B
0x1800152bf  test    rax, rax
0x1800152c2  lea     rcx, [rdx-2]
0x1800152c6  cmovnz  rcx, rdx
0x1800152ca  mov     [rcx], r15w
0x1800152ce  mov     [rdi+8], rbx
0x1800152d2  jmp     short loc_1800152F0
0x1800152d4  mov     rcx, [rdi]; pv
0x1800152d7  mov     ebp, r15d
0x1800152da  test    rcx, rcx
0x1800152dd  jz      short loc_1800152E8
0x1800152df  call    cs:__imp_CoTaskMemFree
0x1800152e5  mov     [rdi], r15
0x1800152e8  mov     [rdi+8], r15
0x1800152ec  mov     [rdi+10h], r15
0x1800152f0  mov     eax, ebp
0x1800152f2  add     rsp, 28h
0x1800152f6  pop     r15
0x1800152f8  pop     r14
0x1800152fa  pop     rdi
0x1800152fb  pop     rsi
0x1800152fc  pop     rbp
0x1800152fd  pop     rbx
0x1800152fe  retn
```
