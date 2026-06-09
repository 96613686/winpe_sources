# CFontCache::Init(HKEY__ *,char const *,ulong)

- ea: `0x18001c130`
- end: `0x18001c328`
- name: `?Init@CFontCache@@UEAAJPEAUHKEY__@@PEBDK@Z`
- size: `504`
- prototype: `__int64 __fastcall(CFontCache *__hidden this, HKEY, const char *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18001c130`
- `0x18001c330`
- `0x180023a48`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!IVoidPtrList_CreateInstance` at `0x18001c1c4`
- `MSOERT2!IVoidPtrList_CreateInstance` at `0x18001c1c4`
- `MSOERT2!IUnknownList_CreateInstance` at `0x18001c18e`
- `MSOERT2!IUnknownList_CreateInstance` at `0x18001c18e`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c29b`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c29b`
- `ADVAPI32!RegQueryValueExA` at `0x18001c2d9`
- `ADVAPI32!RegQueryValueExA` at `0x18001c2d9`
- `ADVAPI32!RegCloseKey` at `0x18001c2f4`
- `ADVAPI32!RegCloseKey` at `0x18001c2f4`
- `KERNEL32!LeaveCriticalSection` at `0x18001c306`
- `KERNEL32!LeaveCriticalSection` at `0x18001c30f`
- `KERNEL32!LeaveCriticalSection` at `0x18001c306`
- `KERNEL32!LeaveCriticalSection` at `0x18001c30f`
- `KERNEL32!EnterCriticalSection` at `0x18001c174`
- `KERNEL32!EnterCriticalSection` at `0x18001c184`
- `KERNEL32!EnterCriticalSection` at `0x18001c174`
- `KERNEL32!EnterCriticalSection` at `0x18001c184`

## pseudocode

```c
__int64 __fastcall CFontCache::Init(CFontCache *this, HKEY a2, char *a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // r15
  signed int Instance; // ebx
  char *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  char *v12; // rax
  LSTATUS v13; // eax
  int v14; // ecx
  BYTE Data[8]; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+8h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  if ( *((_QWORD *)this + 4) )
    return 2147549183LL;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1072);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1072));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1112));
  Instance = IUnknownList_CreateInstance((struct IUnknownList **)this + 2);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 24LL))(
                 *((_QWORD *)this + 2),
                 0,
                 0,
                 0);
    if ( Instance >= 0 )
    {
      Instance = IVoidPtrList_CreateInstance((struct IVoidPtrList **)this + 3);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 (__fastcall *)(struct FONTCACHEENTRY_tag *), _DWORD))(**((_QWORD **)this + 3) + 24LL))(
                     *((_QWORD *)this + 3),
                     0,
                     0,
                     FreeFontCacheEntry,
                     0);
        if ( Instance >= 0 )
        {
          Instance = CreateFontCacheEntry((struct FONTCACHEENTRY_tag **)this + 4);
          if ( Instance >= 0 )
          {
            Instance = CFontCache::InitSysFontEntry((CFontCache *)((char *)this - 32));
            if ( Instance >= 0 )
            {
              *((_QWORD *)this + 5) = a2;
              v9 = (char *)this + 48;
              v10 = 2147483646;
              v11 = 1024;
              do
              {
                if ( !v10 )
                  break;
                if ( !*a3 )
                  break;
                *v9++ = *a3++;
                --v10;
                --v11;
              }
              while ( v11 );
              v12 = v9 - 1;
              if ( v11 )
                v12 = v9;
              *v12 = 0;
              Instance = v11 == 0 ? 0x8007007A : 0;
              if ( v11 )
              {
                if ( RegOpenKeyExA(*((HKEY *)this + 5), (LPCSTR)this + 48, 0, 0x20019u, &hKey) )
                {
                  *((_DWORD *)this + 288) = 0;
                }
                else
                {
                  cbData = 4;
                  v13 = RegQueryValueExA(hKey, "JP_ISO_SIO_Control", 0, 0, Data, &cbData);
                  v14 = 0;
                  if ( !v13 )
                    v14 = *(_DWORD *)Data;
                  *((_DWORD *)this + 288) = v14;
                  RegCloseKey(hKey);
                }
              }
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1112));
  LeaveCriticalSection(v7);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001c130  mov     r11, rsp
0x18001c133  push    rbx
0x18001c134  push    rbp
0x18001c135  push    rsi
0x18001c136  push    rdi
0x18001c137  push    r12
0x18001c139  push    r13
0x18001c13b  push    r14
0x18001c13d  push    r15
0x18001c13f  sub     rsp, 48h
0x18001c143  xor     eax, eax
0x18001c145  mov     rsi, r8
0x18001c148  mov     r13, rdx
0x18001c14b  mov     rdi, rcx
0x18001c14e  mov     dword ptr [rsp+88h+Data], eax
0x18001c152  mov     [r11+8], eax
0x18001c156  mov     [r11-50h], rax
0x18001c15a  cmp     [rcx+20h], rax
0x18001c15e  jz      short loc_18001C16A
0x18001c160  mov     eax, 8000FFFFh
0x18001c165  jmp     loc_18001C317
0x18001c16a  lea     r15, [rcx+430h]
0x18001c171  mov     rcx, r15; lpCriticalSection
0x18001c174  call    cs:__imp_EnterCriticalSection
0x18001c17a  lea     r12, [rdi+458h]
0x18001c181  mov     rcx, r12; lpCriticalSection
0x18001c184  call    cs:__imp_EnterCriticalSection
0x18001c18a  lea     rcx, [rdi+10h]
0x18001c18e  call    cs:__imp_?IUnknownList_CreateInstance@@YAJPEAPEAUIUnknownList@@@Z; IUnknownList_CreateInstance(IUnknownList * *)
0x18001c194  mov     ebx, eax
0x18001c196  test    eax, eax
0x18001c198  js      loc_18001C303
0x18001c19e  mov     rcx, [rdi+10h]
0x18001c1a2  xor     r9d, r9d
0x18001c1a5  xor     r8d, r8d
0x18001c1a8  xor     edx, edx
0x18001c1aa  mov     rax, [rcx]
0x18001c1ad  mov     rax, [rax+18h]
0x18001c1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1b6  mov     ebx, eax
0x18001c1b8  test    eax, eax
0x18001c1ba  js      loc_18001C303
0x18001c1c0  lea     rcx, [rdi+18h]
0x18001c1c4  call    cs:__imp_?IVoidPtrList_CreateInstance@@YAJPEAPEAUIVoidPtrList@@@Z; IVoidPtrList_CreateInstance(IVoidPtrList * *)
0x18001c1ca  mov     ebx, eax
0x18001c1cc  test    eax, eax
0x18001c1ce  js      loc_18001C303
0x18001c1d4  mov     rcx, [rdi+18h]
0x18001c1d8  lea     r9, ?FreeFontCacheEntry@@YAJPEAUFONTCACHEENTRY_tag@@@Z; FreeFontCacheEntry(FONTCACHEENTRY_tag *)
0x18001c1df  xor     r14d, r14d
0x18001c1e2  xor     r8d, r8d
0x18001c1e5  xor     edx, edx
0x18001c1e7  mov     dword ptr [rsp+88h+phkResult], r14d
0x18001c1ec  mov     rax, [rcx]
0x18001c1ef  mov     rax, [rax+18h]
0x18001c1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1f8  mov     ebx, eax
0x18001c1fa  test    eax, eax
0x18001c1fc  js      loc_18001C303
0x18001c202  lea     rcx, [rdi+20h]; struct FONTCACHEENTRY_tag **
0x18001c206  call    ?CreateFontCacheEntry@@YAJPEAPEAUFONTCACHEENTRY_tag@@@Z; CreateFontCacheEntry(FONTCACHEENTRY_tag * *)
0x18001c20b  mov     ebx, eax
0x18001c20d  test    eax, eax
0x18001c20f  js      loc_18001C303
0x18001c215  lea     rcx, [rdi-20h]; this
0x18001c219  call    ?InitSysFontEntry@CFontCache@@AEAAJXZ; CFontCache::InitSysFontEntry(void)
0x18001c21e  mov     ebx, eax
0x18001c220  test    eax, eax
0x18001c222  js      loc_18001C303
0x18001c228  mov     [rdi+28h], r13
0x18001c22c  lea     rdx, [rdi+30h]
0x18001c230  mov     eax, 7FFFFFFEh
0x18001c235  mov     ecx, 400h
0x18001c23a  test    rax, rax
0x18001c23d  jz      short loc_18001C259
0x18001c23f  mov     r8b, [rsi]
0x18001c242  test    r8b, r8b
0x18001c245  jz      short loc_18001C259
0x18001c247  mov     [rdx], r8b
0x18001c24a  inc     rsi
0x18001c24d  inc     rdx
0x18001c250  dec     rax
0x18001c253  sub     rcx, 1
0x18001c257  jnz     short loc_18001C23A
0x18001c259  test    rcx, rcx
0x18001c25c  lea     rax, [rdx-1]
0x18001c260  cmovnz  rax, rdx
0x18001c264  mov     [rax], r14b
0x18001c267  mov     rax, rcx
0x18001c26a  neg     rax
0x18001c26d  sbb     ebx, ebx
0x18001c26f  not     ebx
0x18001c271  and     ebx, 8007007Ah
0x18001c277  test    rcx, rcx
0x18001c27a  jz      loc_18001C303
0x18001c280  mov     rcx, [rdi+28h]; hKey
0x18001c284  lea     rax, [rsp+88h+hKey]
0x18001c289  mov     r9d, 20019h; samDesired
0x18001c28f  mov     [rsp+88h+phkResult], rax; phkResult
0x18001c294  xor     r8d, r8d; ulOptions
0x18001c297  lea     rdx, [rdi+30h]; lpSubKey
0x18001c29b  call    cs:__imp_RegOpenKeyExA
0x18001c2a1  test    eax, eax
0x18001c2a3  jnz     short loc_18001C2FC
0x18001c2a5  mov     rcx, [rsp+88h+hKey]; hKey
0x18001c2aa  lea     rax, [rsp+88h+cbData]
0x18001c2b2  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18001c2b7  lea     rdx, c_szISO2022JPControl; "JP_ISO_SIO_Control"
0x18001c2be  lea     rax, [rsp+88h+Data]
0x18001c2c3  mov     [rsp+88h+cbData], 4
0x18001c2ce  xor     r9d, r9d; lpType
0x18001c2d1  mov     [rsp+88h+phkResult], rax; lpData
0x18001c2d6  xor     r8d, r8d; lpReserved
0x18001c2d9  call    cs:__imp_RegQueryValueExA
0x18001c2df  test    eax, eax
0x18001c2e1  mov     ecx, r14d
0x18001c2e4  cmovz   ecx, dword ptr [rsp+88h+Data]
0x18001c2e9  mov     [rdi+480h], ecx
0x18001c2ef  mov     rcx, [rsp+88h+hKey]; hKey
0x18001c2f4  call    cs:__imp_RegCloseKey
0x18001c2fa  jmp     short loc_18001C303
0x18001c2fc  mov     [rdi+480h], r14d
0x18001c303  mov     rcx, r12; lpCriticalSection
0x18001c306  call    cs:__imp_LeaveCriticalSection
0x18001c30c  mov     rcx, r15; lpCriticalSection
0x18001c30f  call    cs:__imp_LeaveCriticalSection
0x18001c315  mov     eax, ebx
0x18001c317  add     rsp, 48h
0x18001c31b  pop     r15
0x18001c31d  pop     r14
0x18001c31f  pop     r13
0x18001c321  pop     r12
0x18001c323  pop     rdi
0x18001c324  pop     rsi
0x18001c325  pop     rbp
0x18001c326  pop     rbx
0x18001c327  retn
```
