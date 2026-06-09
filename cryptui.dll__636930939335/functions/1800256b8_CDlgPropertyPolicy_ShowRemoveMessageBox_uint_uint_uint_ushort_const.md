# CDlgPropertyPolicy::ShowRemoveMessageBox(uint,uint,uint,ushort const *)

- ea: `0x1800256b8`
- end: `0x1800257c7`
- name: `?ShowRemoveMessageBox@CDlgPropertyPolicy@@AEAAHIIIPEBG@Z`
- size: `271`
- prototype: `int(CDlgPropertyPolicy *__hidden this, unsigned int, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002447c`
- `0x180024bb8`

## callees

- `0x1800256b8`
- `0x1800325ac`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002579c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002579c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002573c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002575d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002573c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002575d`
- `USER32!MessageBoxW` at `0x180025791`
- `USER32!MessageBoxW` at `0x180025791`

## pseudocode

```c
__int64 __fastcall CDlgPropertyPolicy::ShowRemoveMessageBox(
        HWND *this,
        UINT a2,
        UINT a3,
        UINT a4,
        const unsigned __int16 *a5)
{
  unsigned int v9; // ebx
  const WCHAR *v10; // rax
  WCHAR *v11; // rdi
  WCHAR Buffer; // [rsp+20h] [rbp-538h] BYREF
  _BYTE v14[254]; // [rsp+22h] [rbp-536h] BYREF
  WCHAR v15; // [rsp+120h] [rbp-438h] BYREF
  _BYTE v16[1022]; // [rsp+122h] [rbp-436h] BYREF

  Buffer = 0;
  memset_0(v14, 0, sizeof(v14));
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( !a5 || !LoadStringW(hInstance, a3, &Buffer, 128) || !LoadStringW(hInstance, a2, &v15, 512) )
    return 0xFFFFFFFFLL;
  v9 = -1;
  v10 = FormatMessageUnicodeString(&v15, a5);
  v11 = (WCHAR *)v10;
  if ( v10 )
  {
    v9 = MessageBoxW(this[1], v10, &Buffer, a4);
    LocalFree(v11);
  }
  return v9;
}

```

## disassembly

```asm
0x1800256b8  push    rbx
0x1800256ba  push    rbp
0x1800256bb  push    rsi
0x1800256bc  push    rdi
0x1800256bd  push    r14
0x1800256bf  sub     rsp, 530h
0x1800256c6  mov     rax, cs:__security_cookie
0x1800256cd  xor     rax, rsp
0x1800256d0  mov     [rsp+558h+var_38], rax
0x1800256d8  mov     rdi, [rsp+558h+arg_20]
0x1800256e0  mov     ebx, r8d
0x1800256e3  mov     esi, edx
0x1800256e5  mov     rbp, rcx
0x1800256e8  xor     eax, eax
0x1800256ea  lea     rcx, [rsp+558h+var_536]; void *
0x1800256ef  xor     edx, edx; Val
0x1800256f1  mov     [rsp+558h+Buffer], ax
0x1800256f6  mov     r8d, 0FEh; Size
0x1800256fc  mov     r14d, r9d
0x1800256ff  call    memset_0
0x180025704  xor     eax, eax
0x180025706  lea     rcx, [rsp+558h+var_436]; void *
0x18002570e  xor     edx, edx; Val
0x180025710  mov     [rsp+558h+var_438], ax
0x180025718  mov     r8d, 3FEh; Size
0x18002571e  call    memset_0
0x180025723  test    rdi, rdi
0x180025726  jz      short loc_1800257A6
0x180025728  mov     rcx, cs:hInstance; hInstance
0x18002572f  lea     r8, [rsp+558h+Buffer]; lpBuffer
0x180025734  mov     r9d, 80h; cchBufferMax
0x18002573a  mov     edx, ebx; uID
0x18002573c  call    cs:__imp_LoadStringW
0x180025742  test    eax, eax
0x180025744  jz      short loc_1800257A6
0x180025746  mov     rcx, cs:hInstance; hInstance
0x18002574d  lea     r8, [rsp+558h+var_438]; lpBuffer
0x180025755  mov     r9d, 200h; cchBufferMax
0x18002575b  mov     edx, esi; uID
0x18002575d  call    cs:__imp_LoadStringW
0x180025763  test    eax, eax
0x180025765  jz      short loc_1800257A6
0x180025767  mov     rdx, rdi
0x18002576a  lea     rcx, [rsp+558h+var_438]; unsigned __int16 *
0x180025772  or      ebx, 0FFFFFFFFh
0x180025775  call    ?FormatMessageUnicodeString@@YAPEAGPEAGZZ; FormatMessageUnicodeString(ushort *,...)
0x18002577a  mov     rdi, rax
0x18002577d  test    rax, rax
0x180025780  jz      short loc_1800257A2
0x180025782  mov     rcx, [rbp+8]; hWnd
0x180025786  lea     r8, [rsp+558h+Buffer]; lpCaption
0x18002578b  mov     r9d, r14d; uType
0x18002578e  mov     rdx, rax; lpText
0x180025791  call    cs:__imp_MessageBoxW
0x180025797  mov     ebx, eax
0x180025799  mov     rcx, rdi; hMem
0x18002579c  call    cs:__imp_LocalFree
0x1800257a2  mov     eax, ebx
0x1800257a4  jmp     short loc_1800257A9
0x1800257a6  or      eax, 0FFFFFFFFh
0x1800257a9  mov     rcx, [rsp+558h+var_38]
0x1800257b1  xor     rcx, rsp; StackCookie
0x1800257b4  call    __security_check_cookie
0x1800257b9  add     rsp, 530h
0x1800257c0  pop     r14
0x1800257c2  pop     rdi
0x1800257c3  pop     rsi
0x1800257c4  pop     rbp
0x1800257c5  pop     rbx
0x1800257c6  retn
```
