# MessageLoop(IPreviewHandler *,void *)

- ea: `0x140004588`
- end: `0x1400046d4`
- name: `?MessageLoop@@YAXPEAUIPreviewHandler@@PEAX@Z`
- size: `332`
- prototype: `void __fastcall(struct IPreviewHandler *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140005230`

## callees

- `0x140004588`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400045f4`
- `KERNEL32!GetLastError` at `0x1400045f4`
- `USER32!TranslateMessage` at `0x14000466e`
- `USER32!TranslateMessage` at `0x14000466e`
- `USER32!PeekMessageW` at `0x140004694`
- `USER32!PeekMessageW` at `0x140004694`
- `USER32!DispatchMessageW` at `0x140004679`
- `USER32!DispatchMessageW` at `0x140004679`
- `USER32!MsgWaitForMultipleObjects` at `0x1400045d5`
- `USER32!MsgWaitForMultipleObjects` at `0x1400045d5`

## pseudocode

```c
void __fastcall MessageLoop(struct IPreviewHandler *a1, void *a2)
{
  int v3; // edi
  signed int v4; // ebx
  DWORD v5; // eax
  signed int LastError; // eax
  int v7; // eax
  int v8; // ecx
  MSG Msg; // [rsp+30h] [rbp-38h] BYREF
  HANDLE pHandles; // [rsp+78h] [rbp+10h] BYREF

  pHandles = a2;
  v3 = 1;
  v4 = 0;
  do
  {
    if ( !v3 )
      break;
    ((void (__fastcall *)(struct IPreviewHandler *))a1->lpVtbl->AddRef)(a1);
    v5 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
    if ( v5 )
    {
      if ( v5 == 1 )
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message == 18 )
            goto LABEL_20;
          if ( Msg.message - 260 <= 2 || Msg.message - 256 <= 2 )
            ((void (__fastcall *)(struct IPreviewHandler *, MSG *))a1->lpVtbl->TranslateAcceleratorA)(a1, &Msg);
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      else if ( v5 == -1 )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
      }
      else
      {
        v4 = -2147418113;
      }
    }
    else
    {
LABEL_20:
      v3 = 0;
    }
    v7 = ((__int64 (__fastcall *)(struct IPreviewHandler *))a1->lpVtbl->Release)(a1);
    v8 = 0;
    if ( v7 )
      v8 = v3;
    v3 = v8;
  }
  while ( v4 >= 0 );
}

```

## disassembly

```asm
0x140004588  mov     [rsp+arg_0], rbx
0x14000458d  mov     [rsp+arg_10], rsi
0x140004592  mov     [rsp+pHandles], rdx
0x140004597  push    rdi
0x140004598  sub     rsp, 60h
0x14000459c  mov     rsi, rcx
0x14000459f  mov     edi, 1
0x1400045a4  xor     ebx, ebx
0x1400045a6  test    edi, edi
0x1400045a8  jz      loc_1400046C2
0x1400045ae  mov     rax, [rsi]
0x1400045b1  mov     rcx, rsi
0x1400045b4  mov     rax, [rax+8]
0x1400045b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045bd  xor     r8d, r8d; fWaitAll
0x1400045c0  mov     [rsp+68h+dwWakeMask], 1CFFh; dwWakeMask
0x1400045c8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400045cc  lea     rdx, [rsp+68h+pHandles]; pHandles
0x1400045d1  lea     ecx, [r8+1]; nCount
0x1400045d5  call    cs:__imp_MsgWaitForMultipleObjects
0x1400045db  test    eax, eax
0x1400045dd  jz      loc_1400046A0
0x1400045e3  cmp     eax, 1
0x1400045e6  jz      short loc_140004622
0x1400045e8  cmp     eax, 102h
0x1400045ed  jz      short loc_140004618
0x1400045ef  cmp     eax, 0FFFFFFFFh
0x1400045f2  jnz     short loc_140004618
0x1400045f4  call    cs:__imp_GetLastError
0x1400045fa  mov     ebx, eax
0x1400045fc  test    eax, eax
0x1400045fe  jle     short loc_140004609
0x140004600  movzx   ebx, ax
0x140004603  or      ebx, 80070000h
0x140004609  test    ebx, ebx
0x14000460b  mov     eax, 80004005h
0x140004610  cmovns  ebx, eax
0x140004613  jmp     loc_1400046A2
0x140004618  mov     ebx, 8000FFFFh
0x14000461d  jmp     loc_1400046A2
0x140004622  xorps   xmm0, xmm0
0x140004625  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x14000462a  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x14000462f  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x140004634  jmp     short loc_14000467F
0x140004636  mov     ecx, [rsp+68h+Msg.message]
0x14000463a  cmp     ecx, 12h
0x14000463d  jz      short loc_1400046A0
0x14000463f  lea     eax, [rcx-104h]
0x140004645  cmp     eax, 2
0x140004648  jbe     short loc_140004655
0x14000464a  lea     eax, [rcx-100h]
0x140004650  cmp     eax, 2
0x140004653  ja      short loc_140004669
0x140004655  mov     rax, [rsi]
0x140004658  lea     rdx, [rsp+68h+Msg]
0x14000465d  mov     rcx, rsi
0x140004660  mov     rax, [rax+48h]
0x140004664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004669  lea     rcx, [rsp+68h+Msg]; lpMsg
0x14000466e  call    cs:__imp_TranslateMessage
0x140004674  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140004679  call    cs:__imp_DispatchMessageW
0x14000467f  xor     r9d, r9d; wMsgFilterMax
0x140004682  mov     [rsp+68h+dwWakeMask], 1; wRemoveMsg
0x14000468a  xor     r8d, r8d; wMsgFilterMin
0x14000468d  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140004692  xor     edx, edx; hWnd
0x140004694  call    cs:__imp_PeekMessageW
0x14000469a  test    eax, eax
0x14000469c  jnz     short loc_140004636
0x14000469e  jmp     short loc_1400046A2
0x1400046a0  xor     edi, edi
0x1400046a2  mov     rax, [rsi]
0x1400046a5  mov     rcx, rsi
0x1400046a8  mov     rax, [rax+10h]
0x1400046ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046b1  xor     ecx, ecx
0x1400046b3  test    eax, eax
0x1400046b5  cmovnz  ecx, edi
0x1400046b8  mov     edi, ecx
0x1400046ba  test    ebx, ebx
0x1400046bc  jns     loc_1400045A6
0x1400046c2  lea     r11, [rsp+68h+var_8]
0x1400046c7  mov     rbx, [r11+10h]
0x1400046cb  mov     rsi, [r11+20h]
0x1400046cf  mov     rsp, r11
0x1400046d2  pop     rdi
0x1400046d3  retn
```
