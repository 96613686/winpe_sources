# CreatePage

- ea: `0x18001adf0`
- end: `0x18001aeb5`
- name: `CreatePage`
- size: `197`
- prototype: `__int64 __fastcall(LPARAM dwInitParam, HWND hWndParent)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001adf0`
- `0x18001af4c`
- `0x18008e3b0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001ae9f`
- `KERNEL32!LocalFree` at `0x18001ae9f`
- `KERNEL32!LocalAlloc` at `0x18001ae4e`
- `KERNEL32!LocalAlloc` at `0x18001ae4e`
- `KERNEL32!FindResourceW` at `0x18001ae11`
- `KERNEL32!FindResourceW` at `0x18001ae11`
- `KERNEL32!LoadResource` at `0x18001ae2a`
- `KERNEL32!LoadResource` at `0x18001ae2a`
- `KERNEL32!SizeofResource` at `0x18001ae3f`
- `KERNEL32!SizeofResource` at `0x18001ae3f`
- `USER32!CreateDialogIndirectParamW` at `0x18001ae93`
- `USER32!CreateDialogIndirectParamW` at `0x18001ae93`

## pseudocode

```c
HWND __fastcall CreatePage(LPARAM dwInitParam, HWND hWndParent)
{
  HWND DialogIndirectParamW; // rsi
  HRSRC ResourceW; // rax
  HRSRC v6; // rdi
  HGLOBAL Resource; // rbp
  DWORD v8; // r14d
  DLGTEMPLATE *v9; // rax
  DLGTEMPLATE *v10; // rdi
  char v12; // [rsp+70h] [rbp+8h] BYREF

  DialogIndirectParamW = 0;
  ResourceW = FindResourceW(*(HMODULE *)(dwInitParam + 24), *(LPCWSTR *)(dwInitParam + 32), (LPCWSTR)5);
  v6 = ResourceW;
  if ( ResourceW )
  {
    Resource = LoadResource(*(HMODULE *)(dwInitParam + 24), ResourceW);
    if ( Resource )
    {
      v8 = SizeofResource(*(HMODULE *)(dwInitParam + 24), v6);
      v9 = (DLGTEMPLATE *)LocalAlloc(0x40u, (int)v8);
      v10 = v9;
      if ( v9 )
      {
        memmove(v9, Resource, v8);
        if ( EditPropSheetTemplate(v10, &v12, 32) )
          DialogIndirectParamW = CreateDialogIndirectParamW(
                                   *(HINSTANCE *)(dwInitParam + 24),
                                   v10,
                                   hWndParent,
                                   *(DLGPROC *)(dwInitParam + 56),
                                   dwInitParam);
        LocalFree(v10);
      }
    }
  }
  return DialogIndirectParamW;
}

```

## disassembly

```asm
0x18001adf0  push    rbx
0x18001adf2  push    rbp
0x18001adf3  push    rsi
0x18001adf4  push    rdi
0x18001adf5  push    r14
0x18001adf7  push    r15
0x18001adf9  sub     rsp, 38h
0x18001adfd  mov     r15, rdx
0x18001ae00  mov     rbx, rcx
0x18001ae03  mov     rdx, [rcx+20h]; lpName
0x18001ae07  xor     esi, esi
0x18001ae09  mov     rcx, [rcx+18h]; hModule
0x18001ae0d  lea     r8d, [rsi+5]; lpType
0x18001ae11  call    cs:__imp_FindResourceW
0x18001ae17  mov     rdi, rax
0x18001ae1a  test    rax, rax
0x18001ae1d  jz      loc_18001AEA5
0x18001ae23  mov     rcx, [rbx+18h]; hModule
0x18001ae27  mov     rdx, rax; hResInfo
0x18001ae2a  call    cs:__imp_LoadResource
0x18001ae30  mov     rbp, rax
0x18001ae33  test    rax, rax
0x18001ae36  jz      short loc_18001AEA5
0x18001ae38  mov     rcx, [rbx+18h]; hModule
0x18001ae3c  mov     rdx, rdi; hResInfo
0x18001ae3f  call    cs:__imp_SizeofResource
0x18001ae45  movsxd  rdx, eax; uBytes
0x18001ae48  lea     ecx, [rsi+40h]; uFlags
0x18001ae4b  mov     r14d, eax
0x18001ae4e  call    cs:__imp_LocalAlloc
0x18001ae54  mov     rdi, rax
0x18001ae57  test    rax, rax
0x18001ae5a  jz      short loc_18001AEA5
0x18001ae5c  mov     r8d, r14d; Size
0x18001ae5f  mov     rdx, rbp; Src
0x18001ae62  mov     rcx, rax; void *
0x18001ae65  call    memmove
0x18001ae6a  lea     r8d, [rsi+20h]
0x18001ae6e  mov     rcx, rdi
0x18001ae71  lea     rdx, [rsp+68h+arg_0]
0x18001ae76  call    EditPropSheetTemplate
0x18001ae7b  test    rax, rax
0x18001ae7e  jz      short loc_18001AE9C
0x18001ae80  mov     r9, [rbx+38h]; lpDialogFunc
0x18001ae84  mov     r8, r15; hWndParent
0x18001ae87  mov     rcx, [rbx+18h]; hInstance
0x18001ae8b  mov     rdx, rdi; lpTemplate
0x18001ae8e  mov     [rsp+68h+dwInitParam], rbx; dwInitParam
0x18001ae93  call    cs:__imp_CreateDialogIndirectParamW
0x18001ae99  mov     rsi, rax
0x18001ae9c  mov     rcx, rdi; hMem
0x18001ae9f  call    cs:__imp_LocalFree
0x18001aea5  mov     rax, rsi
0x18001aea8  add     rsp, 38h
0x18001aeac  pop     r15
0x18001aeae  pop     r14
0x18001aeb0  pop     rdi
0x18001aeb1  pop     rsi
0x18001aeb2  pop     rbp
0x18001aeb3  pop     rbx
0x18001aeb4  retn
```
