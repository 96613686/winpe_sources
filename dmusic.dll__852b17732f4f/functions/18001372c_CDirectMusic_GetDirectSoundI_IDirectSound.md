# CDirectMusic::GetDirectSoundI(IDirectSound * *)

- ea: `0x18001372c`
- end: `0x180013845`
- name: `?GetDirectSoundI@CDirectMusic@@QEAAJPEAPEAUIDirectSound@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(CDirectMusic *__hidden this, struct IDirectSound **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016390`
- `0x180017694`

## callees

- `0x18001372c`
- `0x180022010`

## import_xrefs

- `DSOUND!__imp_DirectSoundCreate8` at `0x180013779`
- `DSOUND!__imp_DirectSoundCreate8` at `0x180013779`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1800137d1`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1800137d1`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1800137df`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1800137df`

## pseudocode

```c
HRESULT __fastcall CDirectMusic::GetDirectSoundI(CDirectMusic *this, struct IDirectSound **a2)
{
  _QWORD *v4; // rdi
  HRESULT result; // eax
  int v6; // esi
  HWND ForegroundWindow; // rdx
  LPDIRECTSOUND8 ppDS8; // [rsp+50h] [rbp+8h] BYREF

  if ( _InterlockedIncrement((volatile signed __int32 *)this + 28) == 1 )
  {
    v4 = (_QWORD *)((char *)this + 120);
    *((_DWORD *)this + 27) = 0;
    if ( !*((_QWORD *)this + 15) )
    {
      ppDS8 = 0;
      result = DirectSoundCreate8(0, &ppDS8, 0);
      if ( result < 0 )
      {
        _InterlockedDecrement((volatile signed __int32 *)this + 28);
        return result;
      }
      v6 = ((__int64 (__fastcall *)(LPDIRECTSOUND8, GUID *, _QWORD *))ppDS8->lpVtbl->QueryInterface)(
             ppDS8,
             &IID_IDirectSound,
             v4);
      ((void (__fastcall *)(LPDIRECTSOUND8))ppDS8->lpVtbl->Release)(ppDS8);
      if ( v6 < 0 )
        goto LABEL_6;
      ForegroundWindow = (HWND)*((_QWORD *)this + 16);
      if ( !ForegroundWindow )
      {
        ForegroundWindow = GetForegroundWindow();
        if ( !ForegroundWindow )
          ForegroundWindow = GetDesktopWindow();
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD, HWND, __int64))(*(_QWORD *)*v4 + 48LL))(*v4, ForegroundWindow, 2);
      if ( v6 < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
        *v4 = 0;
LABEL_6:
        _InterlockedDecrement((volatile signed __int32 *)this + 28);
        return v6;
      }
      *((_DWORD *)this + 27) = 1;
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 8LL))(*((_QWORD *)this + 15));
  *a2 = (struct IDirectSound *)*((_QWORD *)this + 15);
  return 0;
}

```

## disassembly

```asm
0x18001372c  push    rbx
0x18001372e  push    rsi
0x18001372f  push    rdi
0x180013730  push    r14
0x180013732  sub     rsp, 28h
0x180013736  mov     r14, rdx
0x180013739  mov     rbx, rcx
0x18001373c  mov     eax, 1
0x180013741  lock xadd [rcx+70h], eax
0x180013746  inc     eax
0x180013748  cmp     eax, 1
0x18001374b  jnz     loc_180013822
0x180013751  lea     rdi, [rcx+78h]
0x180013755  mov     dword ptr [rcx+6Ch], 0
0x18001375c  cmp     qword ptr [rdi], 0
0x180013760  jnz     loc_180013822
0x180013766  xor     r8d, r8d; pUnkOuter
0x180013769  mov     [rsp+48h+ppDS8], 0
0x180013772  lea     rdx, [rsp+48h+ppDS8]; ppDS8
0x180013777  xor     ecx, ecx; pcGuidDevice
0x180013779  call    cs:__imp_DirectSoundCreate8
0x18001377f  test    eax, eax
0x180013781  jns     short loc_18001378C
0x180013783  lock dec dword ptr [rbx+70h]
0x180013787  jmp     loc_18001383B
0x18001378c  mov     rcx, [rsp+48h+ppDS8]
0x180013791  lea     rdx, IID_IDirectSound
0x180013798  mov     r8, rdi
0x18001379b  mov     rax, [rcx]
0x18001379e  mov     rax, [rax]
0x1800137a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137a6  mov     rcx, [rsp+48h+ppDS8]
0x1800137ab  mov     esi, eax
0x1800137ad  mov     rdx, [rcx]
0x1800137b0  mov     rax, [rdx+10h]
0x1800137b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137b9  test    esi, esi
0x1800137bb  jns     short loc_1800137C5
0x1800137bd  lock dec dword ptr [rbx+70h]
0x1800137c1  mov     eax, esi
0x1800137c3  jmp     short loc_18001383B
0x1800137c5  mov     rdx, [rbx+80h]
0x1800137cc  test    rdx, rdx
0x1800137cf  jnz     short loc_1800137E8
0x1800137d1  call    cs:__imp_GetForegroundWindow
0x1800137d7  mov     rdx, rax
0x1800137da  test    rax, rax
0x1800137dd  jnz     short loc_1800137E8
0x1800137df  call    cs:__imp_GetDesktopWindow
0x1800137e5  mov     rdx, rax
0x1800137e8  mov     rcx, [rdi]
0x1800137eb  mov     r8d, 2
0x1800137f1  mov     rax, [rcx]
0x1800137f4  mov     rax, [rax+30h]
0x1800137f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137fd  mov     esi, eax
0x1800137ff  test    eax, eax
0x180013801  jns     short loc_18001381B
0x180013803  mov     rcx, [rdi]
0x180013806  mov     rdx, [rcx]
0x180013809  mov     rax, [rdx+10h]
0x18001380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013812  mov     qword ptr [rdi], 0
0x180013819  jmp     short loc_1800137BD
0x18001381b  mov     dword ptr [rbx+6Ch], 1
0x180013822  mov     rcx, [rbx+78h]
0x180013826  mov     rax, [rcx]
0x180013829  mov     rax, [rax+8]
0x18001382d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013832  mov     rax, [rbx+78h]
0x180013836  mov     [r14], rax
0x180013839  xor     eax, eax
0x18001383b  add     rsp, 28h
0x18001383f  pop     r14
0x180013841  pop     rdi
0x180013842  pop     rsi
0x180013843  pop     rbx
0x180013844  retn
```
