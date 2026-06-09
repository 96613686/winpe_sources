# CAppImport::IsComPlusFile(ushort const *)

- ea: `0x18003d71c`
- end: `0x18003d7f3`
- name: `?IsComPlusFile@CAppImport@@AEAAHPEBG@Z`
- size: `215`
- prototype: `int(CAppImport *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ac0c`

## callees

- `0x18003d71c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003d72f`
- `msvcrt!_wcsicmp` at `0x18003d747`
- `msvcrt!_wcsicmp` at `0x18003d75f`
- `msvcrt!_wcsicmp` at `0x18003d773`
- `msvcrt!_wcsicmp` at `0x18003d787`
- `msvcrt!_wcsicmp` at `0x18003d79b`
- `msvcrt!_wcsicmp` at `0x18003d7af`
- `msvcrt!_wcsicmp` at `0x18003d7c3`
- `msvcrt!_wcsicmp` at `0x18003d7d7`
- `msvcrt!_wcsicmp` at `0x18003d72f`
- `msvcrt!_wcsicmp` at `0x18003d747`
- `msvcrt!_wcsicmp` at `0x18003d75f`
- `msvcrt!_wcsicmp` at `0x18003d773`
- `msvcrt!_wcsicmp` at `0x18003d787`
- `msvcrt!_wcsicmp` at `0x18003d79b`
- `msvcrt!_wcsicmp` at `0x18003d7af`
- `msvcrt!_wcsicmp` at `0x18003d7c3`
- `msvcrt!_wcsicmp` at `0x18003d7d7`

## string_xrefs

- `0x18003d755`: `catsrv.dll`
- `0x18003d725`: `comsvcs.dll`
- `0x18003d73d`: `clbcatq.dll`
- `0x18003d769`: `catsrvut.dll`
- `0x18003d77d`: `clbcatex.dll`
- `0x18003d791`: `stclient.dll`
- `0x18003d7a5`: `txflog.dll`
- `0x18003d7b9`: `es.dll`
- `0x18003d7cd`: `comuid.dll`

## pseudocode

```c
_BOOL8 __fastcall CAppImport::IsComPlusFile(CAppImport *this, const unsigned __int16 *a2)
{
  return !_wcsicmp(a2, L"comsvcs.dll")
      || !_wcsicmp(a2, L"clbcatq.dll")
      || !_wcsicmp(a2, L"catsrv.dll")
      || !_wcsicmp(a2, L"catsrvut.dll")
      || !_wcsicmp(a2, L"clbcatex.dll")
      || !_wcsicmp(a2, L"stclient.dll")
      || !_wcsicmp(a2, L"txflog.dll")
      || !_wcsicmp(a2, L"es.dll")
      || _wcsicmp(a2, L"comuid.dll") == 0;
}

```

## disassembly

```asm
0x18003d71c  push    rbx
0x18003d71e  sub     rsp, 20h
0x18003d722  mov     rbx, rdx
0x18003d725  lea     rdx, aComsvcsDll; "comsvcs.dll"
0x18003d72c  mov     rcx, rbx; String1
0x18003d72f  call    cs:__imp__wcsicmp
0x18003d735  test    eax, eax
0x18003d737  jz      loc_18003D7E8
0x18003d73d  lea     rdx, aClbcatqDll_1; "clbcatq.dll"
0x18003d744  mov     rcx, rbx; String1
0x18003d747  call    cs:__imp__wcsicmp
0x18003d74d  test    eax, eax
0x18003d74f  jz      loc_18003D7E8
0x18003d755  lea     rdx, aCatsrvDll_0; "catsrv.dll"
0x18003d75c  mov     rcx, rbx; String1
0x18003d75f  call    cs:__imp__wcsicmp
0x18003d765  test    eax, eax
0x18003d767  jz      short loc_18003D7E8
0x18003d769  lea     rdx, aCatsrvutDll; "catsrvut.dll"
0x18003d770  mov     rcx, rbx; String1
0x18003d773  call    cs:__imp__wcsicmp
0x18003d779  test    eax, eax
0x18003d77b  jz      short loc_18003D7E8
0x18003d77d  lea     rdx, aClbcatexDll; "clbcatex.dll"
0x18003d784  mov     rcx, rbx; String1
0x18003d787  call    cs:__imp__wcsicmp
0x18003d78d  test    eax, eax
0x18003d78f  jz      short loc_18003D7E8
0x18003d791  lea     rdx, aStclientDll; "stclient.dll"
0x18003d798  mov     rcx, rbx; String1
0x18003d79b  call    cs:__imp__wcsicmp
0x18003d7a1  test    eax, eax
0x18003d7a3  jz      short loc_18003D7E8
0x18003d7a5  lea     rdx, aTxflogDll; "txflog.dll"
0x18003d7ac  mov     rcx, rbx; String1
0x18003d7af  call    cs:__imp__wcsicmp
0x18003d7b5  test    eax, eax
0x18003d7b7  jz      short loc_18003D7E8
0x18003d7b9  lea     rdx, aEsDll; "es.dll"
0x18003d7c0  mov     rcx, rbx; String1
0x18003d7c3  call    cs:__imp__wcsicmp
0x18003d7c9  test    eax, eax
0x18003d7cb  jz      short loc_18003D7E8
0x18003d7cd  lea     rdx, aComuidDll; "comuid.dll"
0x18003d7d4  mov     rcx, rbx; String1
0x18003d7d7  call    cs:__imp__wcsicmp
0x18003d7dd  xor     ecx, ecx
0x18003d7df  test    eax, eax
0x18003d7e1  setz    cl
0x18003d7e4  mov     eax, ecx
0x18003d7e6  jmp     short loc_18003D7ED
0x18003d7e8  mov     eax, 1
0x18003d7ed  add     rsp, 20h
0x18003d7f1  pop     rbx
0x18003d7f2  retn
```
