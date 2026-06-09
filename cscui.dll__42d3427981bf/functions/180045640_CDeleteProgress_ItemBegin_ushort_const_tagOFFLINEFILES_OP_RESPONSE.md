# CDeleteProgress::ItemBegin(ushort const *,tagOFFLINEFILES_OP_RESPONSE *)

- ea: `0x180045640`
- end: `0x1800456b6`
- name: `?ItemBegin@CDeleteProgress@@UEAAJPEBGPEAW4tagOFFLINEFILES_OP_RESPONSE@@@Z`
- size: `118`
- prototype: `int(CDeleteProgress *__hidden this, const unsigned __int16 *, enum tagOFFLINEFILES_OP_RESPONSE *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003a90`
- `0x180003c20`
- `0x180045640`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18004566b`
- `SHLWAPI!PathFindFileNameW` at `0x18004566b`
- `USER32!SendMessageW` at `0x18004569e`
- `USER32!SendMessageW` at `0x18004569e`

## pseudocode

```c
__int64 __fastcall CDeleteProgress::ItemBegin(
        CDeleteProgress *this,
        const unsigned __int16 *a2,
        enum tagOFFLINEFILES_OP_RESPONSE *a3)
{
  LPWSTR FileNameW; // rax
  void *v5; // rdx
  LPARAM lParam; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 3) )
  {
    *a3 = OFFLINEFILES_OP_ABORT;
  }
  else
  {
    *a3 = OFFLINEFILES_OP_CONTINUE;
    lParam = 0;
    FileNameW = PathFindFileNameW(a2);
    if ( (int)CscUtil_FormatStringID((LPWSTR)&lParam, g_hInstance, *((_DWORD *)this + 9), FileNameW) >= 0 )
    {
      SendMessageW(*((HWND *)this + 2), 0x46Cu, 0, lParam);
      CscUtil_HeapFree((void *)lParam, v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180045640  push    rbx
0x180045642  sub     rsp, 20h
0x180045646  cmp     dword ptr [rcx+0Ch], 0
0x18004564a  mov     rbx, rcx
0x18004564d  jz      short loc_180045658
0x18004564f  mov     dword ptr [r8], 2
0x180045656  jmp     short loc_1800456AE
0x180045658  mov     rcx, rdx; pszPath
0x18004565b  mov     dword ptr [r8], 0
0x180045662  mov     [rsp+28h+lParam], 0
0x18004566b  call    cs:__imp_PathFindFileNameW
0x180045671  mov     r8d, [rbx+24h]; uID
0x180045675  lea     rcx, [rsp+28h+lParam]; lpBuffer
0x18004567a  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180045681  mov     r9, rax
0x180045684  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180045689  test    eax, eax
0x18004568b  js      short loc_1800456AE
0x18004568d  mov     r9, [rsp+28h+lParam]; lParam
0x180045692  xor     r8d, r8d; wParam
0x180045695  mov     rcx, [rbx+10h]; hWnd
0x180045699  mov     edx, 46Ch; Msg
0x18004569e  call    cs:__imp_SendMessageW
0x1800456a4  mov     rcx, [rsp+28h+lParam]; lpMem
0x1800456a9  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800456ae  xor     eax, eax
0x1800456b0  add     rsp, 20h
0x1800456b4  pop     rbx
0x1800456b5  retn
```
