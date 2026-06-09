# fv::GetPrintVerifierModule(void)

- ea: `0x140056478`
- end: `0x14005653c`
- name: `?GetPrintVerifierModule@fv@@YAPEAUHINSTANCE__@@XZ`
- size: `196`
- prototype: `HINSTANCE __fastcall(fv *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140056264`

## callees

- `0x140002070`
- `0x140002c68`
- `0x14000dc6c`
- `0x140045be4`
- `0x140056478`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140056517`
- `KERNEL32!GetModuleHandleW` at `0x140056517`
- `KERNEL32!GetSystemDirectoryW` at `0x1400564d0`
- `KERNEL32!GetSystemDirectoryW` at `0x1400564d0`

## string_xrefs

- `0x1400564b6`: `vfprint.dll`
- `0x1400564f8`: `vfprint.dll`

## pseudocode

```c
HINSTANCE __fastcall fv::GetPrintVerifierModule(fv *this)
{
  __int64 v1; // rbx
  unsigned __int64 SystemDirectoryW; // rdx
  unsigned __int64 v4; // [rsp+20h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  v1 = 0;
  memset_0(Buffer, 0, 0x208u);
  v4 = 0;
  if ( (int)StringCchLengthW(L"vfprint.dll", 0x103u, &v4) >= 0 )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( SystemDirectoryW - 1 <= 0x101 && SystemDirectoryW + v4 < 0x103 )
    {
      Buffer[SystemDirectoryW] = 92;
      if ( StringCchCatW(Buffer, SystemDirectoryW, L"vfprint.dll") >= 0 )
        return GetModuleHandleW(Buffer);
    }
  }
  return (HINSTANCE)v1;
}

```

## disassembly

```asm
0x140056478  push    rbx
0x14005647a  sub     rsp, 250h
0x140056481  mov     rax, cs:__security_cookie
0x140056488  xor     rax, rsp
0x14005648b  mov     [rsp+258h+var_18], rax
0x140056493  xor     edx, edx; Val
0x140056495  lea     rcx, [rsp+258h+Buffer]; void *
0x14005649a  mov     r8d, 208h; Size
0x1400564a0  xor     ebx, ebx
0x1400564a2  call    memset_0
0x1400564a7  lea     r8, [rsp+258h+var_238]; unsigned __int64 *
0x1400564ac  mov     [rsp+258h+var_238], rbx
0x1400564b1  mov     edx, 103h; unsigned __int64
0x1400564b6  lea     rcx, aVfprintDll; "vfprint.dll"
0x1400564bd  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1400564c2  test    eax, eax
0x1400564c4  js      short loc_140056520
0x1400564c6  mov     edx, 104h; uSize
0x1400564cb  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1400564d0  call    cs:__imp_GetSystemDirectoryW
0x1400564d6  mov     edx, eax; unsigned __int64
0x1400564d8  lea     rax, [rdx-1]
0x1400564dc  cmp     rax, 101h
0x1400564e2  ja      short loc_140056520
0x1400564e4  mov     rcx, [rsp+258h+var_238]
0x1400564e9  add     rcx, rdx
0x1400564ec  cmp     rcx, 103h
0x1400564f3  jnb     short loc_140056520
0x1400564f5  lea     eax, [rbx+5Ch]
0x1400564f8  lea     r8, aVfprintDll; "vfprint.dll"
0x1400564ff  mov     [rsp+rdx*2+258h+Buffer], ax
0x140056504  lea     rcx, [rsp+258h+Buffer]; wchar_t *
0x140056509  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14005650e  test    eax, eax
0x140056510  js      short loc_140056520
0x140056512  lea     rcx, [rsp+258h+Buffer]; lpModuleName
0x140056517  call    cs:__imp_GetModuleHandleW
0x14005651d  mov     rbx, rax
0x140056520  mov     rax, rbx
0x140056523  mov     rcx, [rsp+258h+var_18]
0x14005652b  xor     rcx, rsp; StackCookie
0x14005652e  call    __security_check_cookie
0x140056533  add     rsp, 250h
0x14005653a  pop     rbx
0x14005653b  retn
```
