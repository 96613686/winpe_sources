# LegacyActivationShim::Util::GetMSCOREE(HINSTANCE__ * *)

- ea: `0x14006a450`
- end: `0x14006a4cd`
- name: `?GetMSCOREE@Util@LegacyActivationShim@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *__hidden this, HINSTANCE *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140069fb0`
- `0x14006a190`
- `0x14006aa20`

## callees

- `0x14006a450`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14006a46c`
- `KERNEL32!LoadLibraryW` at `0x14006a46c`
- `KERNEL32!FreeLibrary` at `0x14006a4b5`
- `KERNEL32!FreeLibrary` at `0x14006a4b5`
- `KERNEL32!GetLastError` at `0x14006a47a`
- `KERNEL32!GetLastError` at `0x14006a47a`

## string_xrefs

- `0x14006a465`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall LegacyActivationShim::Util::GetMSCOREE(LegacyActivationShim::Util *this, HINSTANCE *a2)
{
  HINSTANCE v2; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // ecx
  __int64 result; // rax

  v2 = LegacyActivationShim::Util::g_hModMscoree;
  if ( LegacyActivationShim::Util::g_hModMscoree )
    goto LABEL_9;
  LibraryW = LoadLibraryW(L"mscoree.dll");
  if ( LibraryW )
  {
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)&LegacyActivationShim::Util::g_hModMscoree,
           (signed __int64)LibraryW,
           0) )
    {
      FreeLibrary(LibraryW);
      v2 = LegacyActivationShim::Util::g_hModMscoree;
    }
    else
    {
      v2 = LegacyActivationShim::Util::g_hModMscoree;
      LegacyActivationShim::Util::g_hModMscoreeHolder = LegacyActivationShim::Util::g_hModMscoree;
      byte_14009D700 = 1;
    }
LABEL_9:
    *(_QWORD *)this = v2;
    return 0;
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x14006a450  push    rbx
0x14006a452  sub     rsp, 30h
0x14006a456  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x14006a45d  mov     rbx, rcx
0x14006a460  test    rax, rax
0x14006a463  jnz     short loc_14006A4C2
0x14006a465  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x14006a46c  call    cs:__imp_LoadLibraryW
0x14006a472  mov     rcx, rax; hLibModule
0x14006a475  test    rax, rax
0x14006a478  jnz     short loc_14006A491
0x14006a47a  call    cs:__imp_GetLastError
0x14006a480  mov     ecx, eax
0x14006a482  movzx   eax, ax
0x14006a485  or      eax, 80070000h
0x14006a48a  test    ecx, ecx
0x14006a48c  cmovle  eax, ecx
0x14006a48f  jmp     short loc_14006A4C7
0x14006a491  xor     eax, eax
0x14006a493  lock cmpxchg cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x14006a49c  jnz     short loc_14006A4B5
0x14006a49e  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x14006a4a5  mov     cs:?g_hModMscoreeHolder@Util@LegacyActivationShim@@3VZeroInitGlobalHMODULEHolder@12@A, rax; LegacyActivationShim::Util::ZeroInitGlobalHMODULEHolder LegacyActivationShim::Util::g_hModMscoreeHolder
0x14006a4ac  mov     cs:byte_14009D700, 1
0x14006a4b3  jmp     short loc_14006A4C2
0x14006a4b5  call    cs:__imp_FreeLibrary
0x14006a4bb  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x14006a4c2  mov     [rbx], rax
0x14006a4c5  xor     eax, eax
0x14006a4c7  add     rsp, 30h
0x14006a4cb  pop     rbx
0x14006a4cc  retn
```
