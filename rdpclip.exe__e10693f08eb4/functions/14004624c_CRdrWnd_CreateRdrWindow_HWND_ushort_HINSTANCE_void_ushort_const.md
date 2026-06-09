# CRdrWnd::CreateRdrWindow(HWND__ * *,ushort *,HINSTANCE__ *,void *,ushort const *)

- ea: `0x14004624c`
- end: `0x140046339`
- name: `?CreateRdrWindow@CRdrWnd@@SAJPEAPEAUHWND__@@PEAGPEAUHINSTANCE__@@PEAXPEBG@Z`
- size: `237`
- prototype: `static int(HWND *, unsigned __int16 *, HINSTANCE, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003a8c0`

## callees

- `0x140004b1c`
- `0x14000a640`
- `0x14004624c`

## import_xrefs

- `USER32!CreateWindowExW` at `0x140046305`
- `USER32!CreateWindowExW` at `0x140046305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046313`

## pseudocode

```c
int __fastcall CRdrWnd::CreateRdrWindow(HWND *a1, unsigned __int16 *a2, HINSTANCE a3, void *a4)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND Window; // rax
  int result; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_94f1a9989a403136c6c8e3ced4ea9262_Traceguids,
      CurrentThreadActivityIdPrefix,
      0);
  }
  Window = CreateWindowExW(4u, L"RdpClipRdrWindowClass", &WindowName, 0x80000000, 0, 0, 256, 100, 0, 0, a3, a4);
  *a1 = Window;
  if ( Window )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14004624c  mov     [rsp+arg_0], rbx
0x140046251  mov     [rsp+arg_8], rsi
0x140046256  push    rdi
0x140046257  sub     rsp, 60h
0x14004625b  mov     rbx, r9
0x14004625e  mov     rdi, r8
0x140046261  mov     rsi, rcx
0x140046264  mov     rax, cs:WPP_GLOBAL_Control
0x14004626b  lea     rcx, WPP_GLOBAL_Control
0x140046272  cmp     rax, rcx
0x140046275  jz      short loc_1400462B0
0x140046277  test    byte ptr [rax+1Ch], 1
0x14004627b  jz      short loc_1400462B0
0x14004627d  cmp     byte ptr [rax+19h], 5
0x140046281  jb      short loc_1400462B0
0x140046283  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046288  mov     rcx, cs:WPP_GLOBAL_Control
0x14004628f  lea     r8, WPP_94f1a9989a403136c6c8e3ced4ea9262_Traceguids
0x140046296  mov     edx, 0Ah
0x14004629b  mov     qword ptr [rsp+68h+X], 0
0x1400462a4  mov     r9d, eax
0x1400462a7  mov     rcx, [rcx+10h]
0x1400462ab  call    WPP_SF_DS
0x1400462b0  mov     [rsp+68h+lpParam], rbx; lpParam
0x1400462b5  lea     r8, WindowName; lpWindowName
0x1400462bc  mov     [rsp+68h+hInstance], rdi; hInstance
0x1400462c1  lea     rdx, aRdpcliprdrwind; "RdpClipRdrWindowClass"
0x1400462c8  mov     [rsp+68h+hMenu], 0; hMenu
0x1400462d1  mov     r9d, 80000000h; dwStyle
0x1400462d7  mov     [rsp+68h+hWndParent], 0; hWndParent
0x1400462e0  mov     ecx, 4; dwExStyle
0x1400462e5  mov     [rsp+68h+nHeight], 64h ; 'd'; nHeight
0x1400462ed  mov     [rsp+68h+nWidth], 100h; nWidth
0x1400462f5  mov     [rsp+68h+Y], 0; Y
0x1400462fd  mov     [rsp+68h+X], 0; X
0x140046305  call    cs:__imp_CreateWindowExW
0x14004630b  mov     [rsi], rax
0x14004630e  test    rax, rax
0x140046311  jnz     short loc_140046327
0x140046313  call    cs:__imp_GetLastError
0x140046319  test    eax, eax
0x14004631b  jle     short loc_140046329
0x14004631d  movzx   eax, ax
0x140046320  or      eax, 80070000h
0x140046325  jmp     short loc_140046329
0x140046327  xor     eax, eax
0x140046329  mov     rbx, [rsp+68h+arg_0]
0x14004632e  mov     rsi, [rsp+68h+arg_8]
0x140046333  add     rsp, 60h
0x140046337  pop     rdi
0x140046338  retn
```
