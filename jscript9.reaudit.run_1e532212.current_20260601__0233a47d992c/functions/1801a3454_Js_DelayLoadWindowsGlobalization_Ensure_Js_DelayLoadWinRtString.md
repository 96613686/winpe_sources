# Js::DelayLoadWindowsGlobalization::Ensure(Js::DelayLoadWinRtString *)

- ea: `0x1801a3454`
- end: `0x1801a34dd`
- name: `?Ensure@DelayLoadWindowsGlobalization@Js@@QEAAXPEAVDelayLoadWinRtString@2@@Z`
- size: `137`
- prototype: `void __fastcall(Js::DelayLoadWindowsGlobalization *__hidden this, struct Js::DelayLoadWinRtString *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801a33e4`

## callees

- `0x1801a3454`
- `0x180253168`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801a3488`
- `KERNEL32!LoadLibraryExW` at `0x1801a34aa`
- `KERNEL32!LoadLibraryExW` at `0x1801a3488`
- `KERNEL32!LoadLibraryExW` at `0x1801a34aa`

## string_xrefs

- `0x1801a349d`: `jsIntl.dll`

## pseudocode

```c
void __fastcall Js::DelayLoadWindowsGlobalization::Ensure(
        Js::DelayLoadWindowsGlobalization *this,
        struct Js::DelayLoadWinRtString *a2)
{
  const WCHAR *v3; // rax
  HMODULE Library; // rax

  if ( !*((_BYTE *)this + 16) )
  {
    v3 = (const WCHAR *)(*(__int64 (__fastcall **)(Js::DelayLoadWindowsGlobalization *))(*(_QWORD *)this + 8LL))(this);
    Library = LoadLibraryExW(v3, 0, 0x800u);
    *((_QWORD *)this + 1) = Library;
    *((_BYTE *)this + 16) = 1;
    if ( !Library )
      *((_QWORD *)this + 1) = LoadLibraryExW(L"jsIntl.dll", 0, 0x800u);
    *((_QWORD *)this + 10) = a2;
    *((_DWORD *)this + 22) = DelayLoadLibrary::GetFunction(this, "WindowsDuplicateString") != 0;
  }
}

```

## disassembly

```asm
0x1801a3454  mov     [rsp+arg_8], rdx
0x1801a3459  mov     [rsp+arg_0], rcx
0x1801a345e  push    rbx
0x1801a345f  sub     rsp, 20h
0x1801a3463  mov     rbx, [rsp+28h+arg_0]
0x1801a3468  cmp     byte ptr [rbx+10h], 0
0x1801a346c  jnz     short loc_1801A34D7
0x1801a346e  mov     rax, [rbx]
0x1801a3471  mov     rcx, rbx
0x1801a3474  mov     rax, [rax+8]
0x1801a3478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a347d  mov     rcx, rax; lpLibFileName
0x1801a3480  xor     edx, edx; hFile
0x1801a3482  mov     r8d, 800h; dwFlags
0x1801a3488  call    cs:__imp_LoadLibraryExW
0x1801a348e  mov     [rbx+8], rax
0x1801a3492  mov     byte ptr [rbx+10h], 1
0x1801a3496  test    rax, rax
0x1801a3499  jnz     short loc_1801A34B4
0x1801a349b  xor     edx, edx; hFile
0x1801a349d  lea     rcx, aJsintlDll; "jsIntl.dll"
0x1801a34a4  mov     r8d, 800h; dwFlags
0x1801a34aa  call    cs:__imp_LoadLibraryExW
0x1801a34b0  mov     [rbx+8], rax
0x1801a34b4  mov     rax, [rsp+28h+arg_8]
0x1801a34b9  lea     rdx, aWindowsduplica; "WindowsDuplicateString"
0x1801a34c0  mov     rcx, rbx; this
0x1801a34c3  mov     [rbx+50h], rax
0x1801a34c7  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x1801a34cc  xor     ecx, ecx
0x1801a34ce  test    rax, rax
0x1801a34d1  setnz   cl
0x1801a34d4  mov     [rbx+58h], ecx
0x1801a34d7  add     rsp, 20h
0x1801a34db  pop     rbx
0x1801a34dc  retn
```
