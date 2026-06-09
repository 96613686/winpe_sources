# _OpenDSLFileInternal_::_1_::catch$1

- ea: `0x180081ffc`
- end: `0x1800821e1`
- name: `_OpenDSLFileInternal_::_1_::catch$1`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180029414`
- `0x18003c2e8`
- `0x18007e6ca`
- `0x180081ffc`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x1800820f3`
- `KERNEL32!GetLongPathNameW` at `0x1800820f3`
- `USER32!MessageBoxW` at `0x1800821c8`
- `USER32!MessageBoxW` at `0x1800821c8`
- `USER32!LoadStringW` at `0x18008209d`
- `USER32!LoadStringW` at `0x1800820bc`
- `USER32!LoadStringW` at `0x18008215c`
- `USER32!LoadStringW` at `0x1800821ac`
- `USER32!LoadStringW` at `0x18008209d`
- `USER32!LoadStringW` at `0x1800820bc`
- `USER32!LoadStringW` at `0x18008215c`
- `USER32!LoadStringW` at `0x1800821ac`

## pseudocode

```c
__int64 __fastcall OpenDSLFileInternal_::_1_::catch_1(__int64 a1, __int64 a2)
{
  int v3; // ebx
  UINT v4; // r9d
  const WCHAR *v5; // rdx
  UINT v6; // edx

  if ( (bidGblFlags & 2) != 0 && off_1800C8840[0] )
    bidTraceA(off_1800C83D0[0], 188416, off_1800C8840[0], 0);
  *(_WORD *)(a2 + 1728) = 0;
  memset_0((void *)(a2 + 1730), 0, 0x3FEu);
  *(_WORD *)(a2 + 176) = 0;
  memset_0((void *)(a2 + 178), 0, 0x3FEu);
  v3 = *(_DWORD *)(a2 + 80);
  if ( v3 != -2147286789 )
  {
    LoadStringW(hInstance, 0x59u, (LPWSTR)(a2 + 1728), 512);
    if ( *(_DWORD *)(a2 + 96) )
    {
      if ( v3 == -2147221164 )
      {
        v6 = 118;
LABEL_13:
        LoadStringW(hInstance, v6, (LPWSTR)(a2 + 176), 512);
        v4 = 8240;
        v5 = (const WCHAR *)(a2 + 176);
        goto LABEL_14;
      }
    }
    else if ( v3 == -2147221164 )
    {
      v6 = 49;
      goto LABEL_13;
    }
    v6 = 258;
    if ( v3 != -2147217887 )
      v6 = 90;
    goto LABEL_13;
  }
  LoadStringW(hInstance, 0xFFu, (LPWSTR)(a2 + 176), 512);
  LoadStringW(hInstance, 0x5Eu, (LPWSTR)(a2 + 1728), 512);
  *(_WORD *)(a2 + 1200) = 0;
  memset_0((void *)(a2 + 1202), 0, 0x206u);
  GetLongPathNameW(*(LPCWSTR *)(a2 + 160), (LPWSTR)(a2 + 1200), 0x104u);
  *(_WORD *)(a2 + 2752) = 0;
  memset_0((void *)(a2 + 2754), 0, 0x60Cu);
  StringCchPrintfW((unsigned __int16 *)(a2 + 2752), 0x307u, L"%s : %s", a2 + 1200, a2 + 176);
  v4 = 73744;
  v5 = (const WCHAR *)(a2 + 2752);
LABEL_14:
  MessageBoxW(0, v5, (LPCWSTR)(a2 + 1728), v4);
  return 0;
}

```

## disassembly

```asm
0x180081ffc  mov     [rsp+arg_8], rdx
0x180082001  push    rbx
0x180082002  push    rbp
0x180082003  sub     rsp, 58h
0x180082007  mov     rbp, rdx
0x18008200a  test    byte ptr cs:_bidGblFlags, 2
0x180082011  jz      short loc_18008203B
0x180082013  mov     rax, cs:off_1800C8840; "<OpenDSLFileInternal|CATCH|ALL> "
0x18008201a  test    rax, rax
0x18008201d  jz      short loc_18008203B
0x18008201f  xor     r9d, r9d
0x180082022  mov     r8, cs:off_1800C8840; "<OpenDSLFileInternal|CATCH|ALL> "
0x180082029  mov     edx, 2E000h
0x18008202e  mov     rcx, cs:off_1800C83D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180082035  call    _bidTraceA
0x18008203a  nop
0x18008203b  xor     eax, eax
0x18008203d  mov     [rbp+6C0h], ax
0x180082044  xor     edx, edx; Val
0x180082046  mov     r8d, 3FEh; Size
0x18008204c  lea     rcx, [rbp+6C2h]; void *
0x180082053  call    memset_0
0x180082058  xor     eax, eax
0x18008205a  mov     [rbp+0B0h], ax
0x180082061  xor     edx, edx; Val
0x180082063  mov     r8d, 3FEh; Size
0x180082069  lea     rcx, [rbp+0B2h]; void *
0x180082070  call    memset_0
0x180082075  mov     ebx, [rbp+50h]
0x180082078  mov     r9d, 200h; cchBufferMax
0x18008207e  mov     rcx, cs:hInstance; hInstance
0x180082085  cmp     ebx, 800300FBh
0x18008208b  jnz     loc_180082150
0x180082091  lea     r8, [rbp+0B0h]; lpBuffer
0x180082098  mov     edx, 0FFh; uID
0x18008209d  call    cs:__imp_LoadStringW
0x1800820a3  mov     r9d, 200h; cchBufferMax
0x1800820a9  lea     r8, [rbp+6C0h]; lpBuffer
0x1800820b0  mov     edx, 5Eh ; '^'; uID
0x1800820b5  mov     rcx, cs:hInstance; hInstance
0x1800820bc  call    cs:__imp_LoadStringW
0x1800820c2  xor     eax, eax
0x1800820c4  mov     [rbp+4B0h], ax
0x1800820cb  xor     edx, edx; Val
0x1800820cd  mov     r8d, 206h; Size
0x1800820d3  lea     rcx, [rbp+4B2h]; void *
0x1800820da  call    memset_0
0x1800820df  mov     r8d, 104h; cchBuffer
0x1800820e5  lea     rdx, [rbp+4B0h]; lpszLongPath
0x1800820ec  mov     rcx, [rbp+0A0h]; lpszShortPath
0x1800820f3  call    cs:__imp_GetLongPathNameW
0x1800820f9  xor     eax, eax
0x1800820fb  mov     [rbp+0AC0h], ax
0x180082102  xor     edx, edx; Val
0x180082104  mov     r8d, 60Ch; Size
0x18008210a  lea     rcx, [rbp+0AC2h]; void *
0x180082111  call    memset_0
0x180082116  lea     rax, [rbp+0B0h]
0x18008211d  mov     [rsp+68h+var_48], rax
0x180082122  lea     r9, [rbp+4B0h]
0x180082129  lea     r8, aSS; "%s : %s"
0x180082130  mov     edx, 307h; unsigned __int64
0x180082135  lea     rcx, [rbp+0AC0h]; unsigned __int16 *
0x18008213c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180082141  mov     r9d, 12010h
0x180082147  lea     rdx, [rbp+0AC0h]
0x18008214e  jmp     short loc_1800821BF
0x180082150  lea     r8, [rbp+6C0h]; lpBuffer
0x180082157  mov     edx, 59h ; 'Y'; uID
0x18008215c  call    cs:__imp_LoadStringW
0x180082162  cmp     dword ptr [rbp+60h], 0
0x180082166  jz      short loc_180082177
0x180082168  cmp     ebx, 80040154h
0x18008216e  jnz     short loc_180082186
0x180082170  mov     edx, 76h ; 'v'
0x180082175  jmp     short loc_180082198
0x180082177  cmp     ebx, 80040154h
0x18008217d  jnz     short loc_180082186
0x18008217f  mov     edx, 31h ; '1'
0x180082184  jmp     short loc_180082198
0x180082186  cmp     ebx, 80040E21h
0x18008218c  mov     edx, 102h
0x180082191  jz      short loc_180082198
0x180082193  mov     edx, 5Ah ; 'Z'; uID
0x180082198  mov     r9d, 200h; cchBufferMax
0x18008219e  lea     r8, [rbp+0B0h]; lpBuffer
0x1800821a5  mov     rcx, cs:hInstance; hInstance
0x1800821ac  call    cs:__imp_LoadStringW
0x1800821b2  mov     r9d, 2030h; uType
0x1800821b8  lea     rdx, [rbp+0B0h]; lpText
0x1800821bf  lea     r8, [rbp+6C0h]; lpCaption
0x1800821c6  xor     ecx, ecx; hWnd
0x1800821c8  call    cs:__imp_MessageBoxW
0x1800821ce  nop
0x1800821cf  mov     rax, 0
0x1800821d9  add     rsp, 58h
0x1800821dd  pop     rbp
0x1800821de  pop     rbx
0x1800821df  retn
```
