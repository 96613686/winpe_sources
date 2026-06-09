# Js::DelayLoadWindowsGlobalization::Ensure(Js::DelayLoadWinRtString *)

- ea: `0x1801a57cc`
- end: `0x1801a5862`
- name: `?Ensure@DelayLoadWindowsGlobalization@Js@@QEAAXPEAVDelayLoadWinRtString@2@@Z`
- size: `150`
- prototype: `void __fastcall(Js::DelayLoadWindowsGlobalization *__hidden this, struct Js::DelayLoadWinRtString *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801a5754`

## callees

- `0x1801a57cc`
- `0x1802577dc`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801a5800`
- `KERNEL32!LoadLibraryExW` at `0x1801a5828`
- `KERNEL32!LoadLibraryExW` at `0x1801a5800`
- `KERNEL32!LoadLibraryExW` at `0x1801a5828`

## string_xrefs

- `0x1801a581b`: `jsIntl.dll`

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
0x1801a57cc  mov     [rsp+arg_8], rdx
0x1801a57d1  mov     [rsp+arg_0], rcx
0x1801a57d6  push    rbx
0x1801a57d7  sub     rsp, 20h
0x1801a57db  mov     rbx, [rsp+28h+arg_0]
0x1801a57e0  cmp     byte ptr [rbx+10h], 0
0x1801a57e4  jnz     short loc_1801A585B
0x1801a57e6  mov     rax, [rbx]
0x1801a57e9  mov     rcx, rbx
0x1801a57ec  mov     rax, [rax+8]
0x1801a57f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a57f5  mov     rcx, rax; lpLibFileName
0x1801a57f8  xor     edx, edx; hFile
0x1801a57fa  mov     r8d, 800h; dwFlags
0x1801a5800  call    cs:__imp_LoadLibraryExW
0x1801a5807  nop     dword ptr [rax+rax+00h]
0x1801a580c  mov     [rbx+8], rax
0x1801a5810  mov     byte ptr [rbx+10h], 1
0x1801a5814  test    rax, rax
0x1801a5817  jnz     short loc_1801A5838
0x1801a5819  xor     edx, edx; hFile
0x1801a581b  lea     rcx, aJsintlDll; "jsIntl.dll"
0x1801a5822  mov     r8d, 800h; dwFlags
0x1801a5828  call    cs:__imp_LoadLibraryExW
0x1801a582f  nop     dword ptr [rax+rax+00h]
0x1801a5834  mov     [rbx+8], rax
0x1801a5838  mov     rax, [rsp+28h+arg_8]
0x1801a583d  lea     rdx, aWindowsduplica; "WindowsDuplicateString"
0x1801a5844  mov     rcx, rbx; this
0x1801a5847  mov     [rbx+50h], rax
0x1801a584b  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x1801a5850  xor     ecx, ecx
0x1801a5852  test    rax, rax
0x1801a5855  setnz   cl
0x1801a5858  mov     [rbx+58h], ecx
0x1801a585b  add     rsp, 20h
0x1801a585f  pop     rbx
0x1801a5860  retn
```
