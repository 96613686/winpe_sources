# ATManager::GetAccommodations(void)

- ea: `0x14001d3ac`
- end: `0x14001d4e3`
- name: `?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001ed8c`
- `0x14002491c`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x14001d3ac`
- `0x14001d4ec`
- `0x14002180c`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x14001d4a9`
- `ADVAPI32!RegEnumKeyExW` at `0x14001d4a9`

## string_xrefs

- `0x14001d3ef`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATManager::GetAccommodations(__int64 a1)
{
  DWORD v2; // esi
  DWORD i; // edx
  __int64 v4; // rax
  __int64 *v5; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct Accommodation *v9; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[64]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)hKey,
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs",
                        0x20019u) )
  {
    v2 = 0;
    for ( i = 0; ; i = v2 )
    {
      cchName = 64;
      if ( RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0) == 259 )
        break;
      v9 = Accommodation::Open(Name);
      if ( v9 )
      {
        v4 = ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::NewNode(
               a1 + 304,
               &v9,
               *(_QWORD *)(a1 + 312));
        v5 = *(__int64 **)(a1 + 312);
        if ( v5 )
          *v5 = v4;
        else
          *(_QWORD *)(a1 + 304) = v4;
        *(_QWORD *)(a1 + 312) = v4;
      }
      ++v2;
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return a1 + 304;
}

```

## disassembly

```asm
0x14001d3ac  push    rbp
0x14001d3ae  push    rbx
0x14001d3af  push    rsi
0x14001d3b0  push    rdi
0x14001d3b1  lea     rbp, [rsp-8]
0x14001d3b6  sub     rsp, 108h
0x14001d3bd  mov     rax, cs:__security_cookie
0x14001d3c4  xor     rax, rsp
0x14001d3c7  mov     [rbp+20h+var_30], rax
0x14001d3cb  mov     rdi, rcx
0x14001d3ce  mov     [rsp+120h+hKey], 0
0x14001d3d7  mov     [rsp+120h+var_D0], 0
0x14001d3e0  mov     [rsp+120h+var_C8], 0
0x14001d3e9  mov     r9d, 20019h; unsigned int
0x14001d3ef  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001d3f6  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001d3fd  lea     rcx, [rsp+120h+hKey]; this
0x14001d402  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001d407  test    eax, eax
0x14001d409  jnz     loc_14001D4BA
0x14001d40f  xor     esi, esi
0x14001d411  mov     [rsp+120h+lpftLastWriteTime], rsi
0x14001d416  mov     [rsp+120h+lpcchClass], rsi
0x14001d41b  mov     [rsp+120h+lpClass], rsi
0x14001d420  mov     [rsp+120h+lpReserved], rsi
0x14001d425  xor     edx, edx
0x14001d427  jmp     short loc_14001D492
0x14001d429  lea     rcx, [rsp+120h+Name]; unsigned __int16 *
0x14001d42e  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14001d433  mov     [rsp+120h+var_C0], rax
0x14001d438  test    rax, rax
0x14001d43b  jz      short loc_14001D46A
0x14001d43d  lea     rbx, [rdi+130h]
0x14001d444  mov     r8, [rbx+8]
0x14001d448  lea     rdx, [rsp+120h+var_C0]
0x14001d44d  mov     rcx, rbx
0x14001d450  call    ?NewNode@?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAVAccommodation@@PEAV312@1@Z; ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::NewNode(Accommodation * const &,ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::CNode *,ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::CNode *)
0x14001d455  mov     rcx, [rbx+8]
0x14001d459  test    rcx, rcx
0x14001d45c  jz      short loc_14001D463
0x14001d45e  mov     [rcx], rax
0x14001d461  jmp     short loc_14001D466
0x14001d463  mov     [rbx], rax
0x14001d466  mov     [rbx+8], rax
0x14001d46a  inc     esi
0x14001d46c  mov     [rsp+120h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14001d475  mov     [rsp+120h+lpcchClass], 0; lpcchClass
0x14001d47e  mov     [rsp+120h+lpClass], 0; lpClass
0x14001d487  mov     [rsp+120h+lpReserved], 0; lpReserved
0x14001d490  mov     edx, esi; dwIndex
0x14001d492  mov     [rsp+120h+cchName], 40h ; '@'
0x14001d49a  lea     r9, [rsp+120h+cchName]; lpcchName
0x14001d49f  lea     r8, [rsp+120h+Name]; lpName
0x14001d4a4  mov     rcx, [rsp+120h+hKey]; hKey
0x14001d4a9  call    cs:__imp_RegEnumKeyExW
0x14001d4af  cmp     eax, 103h
0x14001d4b4  jnz     loc_14001D429
0x14001d4ba  lea     rcx, [rsp+120h+hKey]; this
0x14001d4bf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001d4c4  lea     rax, [rdi+130h]
0x14001d4cb  mov     rcx, [rbp+20h+var_30]
0x14001d4cf  xor     rcx, rsp; StackCookie
0x14001d4d2  call    __security_check_cookie
0x14001d4d7  add     rsp, 108h
0x14001d4de  pop     rdi
0x14001d4df  pop     rsi
0x14001d4e0  pop     rbx
0x14001d4e1  pop     rbp
0x14001d4e2  retn
```
