# GetExtensionProperties(char const *,DIRECTSR_EXT_PROPS *)

- ea: `0x18008d8c4`
- end: `0x18008d94e`
- name: `?GetExtensionProperties@@YAJPEBDPEAUDIRECTSR_EXT_PROPS@@@Z`
- size: `138`
- prototype: `int(const char *, struct DIRECTSR_EXT_PROPS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18006579c`
- `0x18008dbd8`

## callees

- `0x1800405a4`
- `0x180067d2c`
- `0x18008d8c4`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d907`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d8dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d8dd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008d8cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008d8cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetExtensionProperties(const char *a1, struct DIRECTSR_EXT_PROPS *a2)
{
  HMODULE LibraryA; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  FARPROC ProcAddress; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE v11; // [rsp+40h] [rbp+18h] BYREF

  LibraryA = LoadLibraryA(a1);
  v11 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "DSRExGetProperties");
    if ( ProcAddress )
    {
      ((void (__fastcall *)(struct DIRECTSR_EXT_PROPS *))ProcAddress)(a2);
      v5 = 0;
      goto LABEL_10;
    }
    v5 = -2147418113;
    v6 = 398;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 394;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
      (const char *)v5,
      v9);
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v11);
  return v5;
}

```

## disassembly

```asm
0x18008d8c4  push    rbx; int
0x18008d8c6  sub     rsp, 20h
0x18008d8ca  mov     rbx, rdx
0x18008d8cd  call    cs:__imp_LoadLibraryA
0x18008d8d3  mov     [rsp+28h+arg_10], rax
0x18008d8d8  test    rax, rax
0x18008d8db  jnz     short loc_18008D8FD
0x18008d8dd  call    cs:__imp_GetLastError
0x18008d8e3  mov     ebx, eax
0x18008d8e5  test    eax, eax
0x18008d8e7  jle     short loc_18008D8F2
0x18008d8e9  movzx   ebx, ax
0x18008d8ec  or      ebx, 80070000h
0x18008d8f2  test    ebx, ebx
0x18008d8f4  jns     short loc_18008D93C
0x18008d8f6  mov     edx, 18Ah
0x18008d8fb  jmp     short loc_18008D91C
0x18008d8fd  lea     rdx, aDsrexgetproper; "DSRExGetProperties"
0x18008d904  mov     rcx, rax; hModule
0x18008d907  call    cs:__imp_GetProcAddress
0x18008d90d  test    rax, rax
0x18008d910  jnz     short loc_18008D932
0x18008d912  mov     ebx, 8000FFFFh
0x18008d917  mov     edx, 18Eh; void *
0x18008d91c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008d923  mov     r9d, ebx; char *
0x18008d926  mov     rcx, [rsp+28h]; this
0x18008d92b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d930  jmp     short loc_18008D93C
0x18008d932  mov     rcx, rbx
0x18008d935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d93a  xor     ebx, ebx
0x18008d93c  lea     rcx, [rsp+28h+arg_10]
0x18008d941  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18008d946  mov     eax, ebx
0x18008d948  add     rsp, 20h
0x18008d94c  pop     rbx
0x18008d94d  retn
```
