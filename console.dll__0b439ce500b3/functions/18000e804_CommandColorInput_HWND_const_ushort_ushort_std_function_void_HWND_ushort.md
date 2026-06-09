# _CommandColorInput(HWND__ * const,ushort,ushort,std::function<void (HWND__ *,ushort)>)

- ea: `0x18000e804`
- end: `0x18000e8aa`
- name: `?_CommandColorInput@@YA_NQEAUHWND__@@GGV?$function@$$A6AXPEAUHWND__@@G@Z@std@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(HWND wParam)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e15c`

## callees

- `0x18000705c`
- `0x18000e804`
- `0x18001a010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000e845`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000e845`

## pseudocode

```c
char __fastcall _CommandColorInput(HWND wParam, __int64 a2, __int16 a3, __int64 a4)
{
  char v6; // di
  __int64 v7; // rcx
  __int64 v8; // rcx
  HWND v10[3]; // [rsp+20h] [rbp-18h] BYREF
  __int16 v11; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 == 768 || (v6 = 0, a3 == 1024) )
  {
    v11 = a2;
    v10[0] = wParam;
    v7 = *(_QWORD *)(a4 + 56);
    if ( !v7 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64, HWND *, __int16 *))(*(_QWORD *)v7 + 16LL))(v7, v10, &v11);
    v6 = 1;
    UpdateApplyButton(wParam);
  }
  v8 = *(_QWORD *)(a4 + 56);
  if ( v8 )
  {
    LOBYTE(a2) = v8 != a4;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, a2);
    *(_QWORD *)(a4 + 56) = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000e804  mov     [rsp+arg_0], rbx
0x18000e809  mov     [rsp+arg_8], rsi
0x18000e80e  push    rdi
0x18000e80f  sub     rsp, 30h
0x18000e813  mov     rbx, r9
0x18000e816  mov     rsi, rcx
0x18000e819  mov     eax, 300h
0x18000e81e  cmp     r8w, ax
0x18000e822  jz      short loc_18000E832
0x18000e824  xor     dil, dil
0x18000e827  mov     eax, 400h
0x18000e82c  cmp     r8w, ax
0x18000e830  jnz     short loc_18000E873
0x18000e832  mov     [rsp+38h+arg_10], dx
0x18000e837  mov     [rsp+38h+var_18], rsi
0x18000e83c  mov     rcx, [r9+38h]
0x18000e840  test    rcx, rcx
0x18000e843  jnz     short loc_18000E852
0x18000e845  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000e84c  nop     dword ptr [rax+rax+00h]
0x18000e851  int     3; Trap to Debugger
0x18000e852  mov     rax, [rcx]
0x18000e855  lea     r8, [rsp+38h+arg_10]
0x18000e85a  lea     rdx, [rsp+38h+var_18]
0x18000e85f  mov     rax, [rax+10h]
0x18000e863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e868  mov     dil, 1
0x18000e86b  mov     rcx, rsi; wParam
0x18000e86e  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x18000e873  mov     rcx, [rbx+38h]
0x18000e877  test    rcx, rcx
0x18000e87a  jz      short loc_18000E896
0x18000e87c  mov     r8, [rcx]
0x18000e87f  cmp     rcx, rbx
0x18000e882  setnz   dl
0x18000e885  mov     rax, [r8+20h]
0x18000e889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e88e  mov     qword ptr [rbx+38h], 0
0x18000e896  mov     al, dil
0x18000e899  mov     rbx, [rsp+38h+arg_0]
0x18000e89e  mov     rsi, [rsp+38h+arg_8]
0x18000e8a3  add     rsp, 30h
0x18000e8a7  pop     rdi
0x18000e8a8  retn
```
