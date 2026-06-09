# SchedUIErrorDialog(HWND__ *,int,long,uint)

- ea: `0x180017df4`
- end: `0x180017e87`
- name: `?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z`
- size: `147`
- prototype: `void __fastcall(HWND hWnd, UINT uID, int, UINT)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800116c0`
- `0x180011fc0`
- `0x180014620`
- `0x180014aa0`
- `0x180015570`
- `0x180015bb0`
- `0x180017130`
- `0x180017680`
- `0x180017c84`
- `0x180018edc`
- `0x1800192e0`
- `0x18001a1d4`

## callees

- `0x18000c02c`
- `0x180017df4`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017e47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e67`
- `USER32!MessageBoxW` at `0x180017e5e`
- `USER32!MessageBoxW` at `0x180017e5e`

## pseudocode

```c
void __fastcall SchedUIErrorDialog(HWND hWnd, UINT uID, DWORD a3, UINT a4)
{
  unsigned __int16 *v5; // rbx
  WCHAR Buffer[256]; // [rsp+20h] [rbp-228h] BYREF

  v5 = ComposeErrorMsg(uID, a3, a4);
  if ( v5 )
  {
    LoadStringW(g_hInstance, 0x43Du, Buffer, 256);
    MessageBoxW(hWnd, v5, Buffer, 0x30u);
    LocalFree(v5);
  }
}

```

## disassembly

```asm
0x180017df4  push    rbx
0x180017df6  push    rdi
0x180017df7  sub     rsp, 238h
0x180017dfe  mov     rax, cs:__security_cookie
0x180017e05  xor     rax, rsp
0x180017e08  mov     [rsp+248h+var_28], rax
0x180017e10  mov     r10d, r9d
0x180017e13  mov     eax, edx
0x180017e15  mov     r9d, r8d; int
0x180017e18  mov     rdi, rcx
0x180017e1b  mov     edx, r9d; dwMessageId
0x180017e1e  mov     r8d, r10d; UINT
0x180017e21  mov     ecx, eax; uID
0x180017e23  call    ?ComposeErrorMsg@@YAPEAGIKIH@Z; ComposeErrorMsg(uint,ulong,uint,int)
0x180017e28  mov     rbx, rax
0x180017e2b  test    rax, rax
0x180017e2e  jz      short loc_180017E6D
0x180017e30  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180017e37  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x180017e3c  mov     r9d, 100h; cchBufferMax
0x180017e42  mov     edx, 43Dh; uID
0x180017e47  call    cs:__imp_LoadStringW
0x180017e4d  mov     r9d, 30h ; '0'; uType
0x180017e53  lea     r8, [rsp+248h+Buffer]; lpCaption
0x180017e58  mov     rdx, rbx; lpText
0x180017e5b  mov     rcx, rdi; hWnd
0x180017e5e  call    cs:__imp_MessageBoxW
0x180017e64  mov     rcx, rbx; hMem
0x180017e67  call    cs:__imp_LocalFree
0x180017e6d  mov     rcx, [rsp+248h+var_28]
0x180017e75  xor     rcx, rsp; StackCookie
0x180017e78  call    __security_check_cookie
0x180017e7d  add     rsp, 238h
0x180017e84  pop     rdi
0x180017e85  pop     rbx
0x180017e86  retn
```
