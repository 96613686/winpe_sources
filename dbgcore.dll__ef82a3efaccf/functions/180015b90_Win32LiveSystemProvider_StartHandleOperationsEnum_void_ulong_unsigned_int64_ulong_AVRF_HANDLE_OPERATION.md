# Win32LiveSystemProvider::StartHandleOperationsEnum(void *,ulong,unsigned __int64 *,ulong *,_AVRF_HANDLE_OPERATION * *)

- ea: `0x180015b90`
- end: `0x180015ce3`
- name: `?StartHandleOperationsEnum@Win32LiveSystemProvider@@UEAAJPEAXKPEA_KPEAKPEAPEAU_AVRF_HANDLE_OPERATION@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, void *, unsigned int, unsigned __int64 *, unsigned int *, struct _AVRF_HANDLE_OPERATION **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180015b90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180015c22`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180015c22`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180015bbf`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180015bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bdb`

## string_xrefs

- `0x180015bb6`: `verifier.dll`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::StartHandleOperationsEnum(
        Win32LiveSystemProvider *this,
        void *a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int *a5,
        struct _AVRF_HANDLE_OPERATION **a6)
{
  signed int result; // eax
  HMODULE Library; // rax
  __int64 (__fastcall *v11)(void *, _QWORD, __int64, unsigned int (__fastcall *)(void *, void *, unsigned int *), Win32LiveSystemProvider *); // rax
  unsigned __int64 v12; // rdx

  result = *((_DWORD *)this + 116);
  if ( result != 1 )
    goto LABEL_8;
  Library = LoadLibraryExA("verifier.dll", 0, 0);
  *((_QWORD *)this + 59) = Library;
  if ( !Library )
  {
    if ( GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
    }
    else
    {
      result = -2147467259;
    }
    *((_DWORD *)this + 116) = result;
LABEL_8:
    if ( result )
      return result;
    goto LABEL_9;
  }
  *((_QWORD *)this + 60) = GetProcAddress(Library, "VerifierEnumerateResource");
  *((_DWORD *)this + 116) = 0;
LABEL_9:
  v11 = (__int64 (__fastcall *)(void *, _QWORD, __int64, unsigned int (__fastcall *)(void *, void *, unsigned int *), Win32LiveSystemProvider *))*((_QWORD *)this + 60);
  if ( !v11 )
    return -2147467263;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_DWORD *)this + 182) = 0;
  result = v11(a2, 0, 1, Win32LiveSystemProvider::HandleOpCb, this);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v12 = *((_QWORD *)this + 90);
    if ( *((_DWORD *)this + 182) )
    {
      if ( v12 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
      return *((_DWORD *)this + 182);
    }
    else
    {
      *a4 = v12;
      *a5 = *((_DWORD *)this + 179);
      *a6 = (struct _AVRF_HANDLE_OPERATION *)*((_QWORD *)this + 90);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015b90  mov     [rsp+arg_0], rbx
0x180015b95  mov     [rsp+arg_8], rsi
0x180015b9a  push    rdi
0x180015b9b  sub     rsp, 30h
0x180015b9f  mov     eax, [rcx+1D0h]
0x180015ba5  mov     rdi, r9
0x180015ba8  mov     rsi, rdx
0x180015bab  mov     rbx, rcx
0x180015bae  cmp     eax, 1
0x180015bb1  jnz     short loc_180015BFA
0x180015bb3  xor     r8d, r8d; dwFlags
0x180015bb6  lea     rcx, aVerifierDll; "verifier.dll"
0x180015bbd  xor     edx, edx; hFile
0x180015bbf  call    cs:__imp_LoadLibraryExA
0x180015bc5  mov     [rbx+1D8h], rax
0x180015bcc  test    rax, rax
0x180015bcf  jnz     short loc_180015C18
0x180015bd1  call    cs:__imp_GetLastError
0x180015bd7  test    eax, eax
0x180015bd9  jz      short loc_180015BEF
0x180015bdb  call    cs:__imp_GetLastError
0x180015be1  test    eax, eax
0x180015be3  jle     short loc_180015BF4
0x180015be5  movzx   eax, ax
0x180015be8  or      eax, 80070000h
0x180015bed  jmp     short loc_180015BF4
0x180015bef  mov     eax, 80004005h
0x180015bf4  mov     [rbx+1D0h], eax
0x180015bfa  test    eax, eax
0x180015bfc  jnz     loc_180015CD3
0x180015c02  mov     rax, [rbx+1E0h]
0x180015c09  test    rax, rax
0x180015c0c  jnz     short loc_180015C3B
0x180015c0e  mov     eax, 80004001h
0x180015c13  jmp     loc_180015CD3
0x180015c18  lea     rdx, aVerifierenumer; "VerifierEnumerateResource"
0x180015c1f  mov     rcx, rax; hModule
0x180015c22  call    cs:__imp_GetProcAddress
0x180015c28  mov     [rbx+1E0h], rax
0x180015c2f  mov     dword ptr [rbx+1D0h], 0
0x180015c39  jmp     short loc_180015C02
0x180015c3b  xor     edx, edx
0x180015c3d  mov     qword ptr [rbx+2C8h], 0
0x180015c48  lea     r9, ?HandleOpCb@Win32LiveSystemProvider@@KAKPEAX0PEAK@Z; Win32LiveSystemProvider::HandleOpCb(void *,void *,ulong *)
0x180015c4f  mov     qword ptr [rbx+2D0h], 0
0x180015c5a  mov     rcx, rsi
0x180015c5d  mov     dword ptr [rbx+2D8h], 0
0x180015c67  mov     [rsp+38h+var_18], rbx
0x180015c6c  lea     r8d, [rdx+1]
0x180015c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c75  test    eax, eax
0x180015c77  jz      short loc_180015C85
0x180015c79  jle     short loc_180015CD3
0x180015c7b  movzx   eax, ax
0x180015c7e  or      eax, 80070000h
0x180015c83  jmp     short loc_180015CD3
0x180015c85  cmp     dword ptr [rbx+2D8h], 0
0x180015c8c  mov     rdx, [rbx+2D0h]
0x180015c93  jz      short loc_180015CB2
0x180015c95  test    rdx, rdx
0x180015c98  jz      short loc_180015CAA
0x180015c9a  mov     rcx, [rbx+30h]
0x180015c9e  mov     rax, [rcx]
0x180015ca1  mov     rax, [rax+18h]
0x180015ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015caa  mov     eax, [rbx+2D8h]
0x180015cb0  jmp     short loc_180015CD3
0x180015cb2  mov     rax, [rsp+38h+arg_20]
0x180015cb7  mov     [rdi], rdx
0x180015cba  mov     ecx, [rbx+2CCh]
0x180015cc0  mov     [rax], ecx
0x180015cc2  mov     rax, [rsp+38h+arg_28]
0x180015cc7  mov     rcx, [rbx+2D0h]
0x180015cce  mov     [rax], rcx
0x180015cd1  xor     eax, eax
0x180015cd3  mov     rbx, [rsp+38h+arg_0]
0x180015cd8  mov     rsi, [rsp+38h+arg_8]
0x180015cdd  add     rsp, 30h
0x180015ce1  pop     rdi
0x180015ce2  retn
```
