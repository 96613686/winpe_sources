# InstanceBookmarkWriter

- ea: `0x180028290`
- end: `0x1800283bb`
- name: `InstanceBookmarkWriter`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027f84`

## callees

- `0x180006ef8`
- `0x180007920`
- `0x180007c80`
- `0x180028290`
- `0x180045010`

## import_xrefs

- `msvcrt!_write` at `0x18002836a`
- `msvcrt!_write` at `0x18002838d`
- `msvcrt!_write` at `0x18002836a`
- `msvcrt!_write` at `0x18002838d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028301`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028301`

## string_xrefs

- `0x1800282f6`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall InstanceBookmarkWriter(__int64 a1, unsigned int a2, __int64 a3)
{
  _QWORD *v6; // rcx
  HMODULE ModuleHandleA; // rax
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rax
  LPVOID lpTlsValue; // [rsp+60h] [rbp+20h] BYREF
  int Buf; // [rsp+68h] [rbp+28h] BYREF

  if ( !a2 )
  {
    if ( *(_DWORD *)(a3 + 40) == 17 && (!*(_DWORD *)(a3 + 8) || *(_QWORD *)a3) )
    {
      v9 = *(_DWORD *)a1;
      Buf = *(_DWORD *)(a3 + 8);
      if ( _write(v9, &Buf, 4u) == 4 )
      {
        *(_QWORD *)(a1 + 8) += 4LL;
        if ( !Buf )
          return 0;
        v10 = _write(*(_DWORD *)a1, *(const void **)a3, *(_DWORD *)(a3 + 8));
        v11 = *(unsigned int *)(a3 + 8);
        if ( v10 == v11 )
        {
          *(_QWORD *)(a1 + 8) += v11;
          return 0;
        }
      }
    }
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_GetString_LoadString(ModuleHandleA, 2017);
    MI_ReportErrorDetails_ForCustomError(17, (int)L"BinaryLogger", 0, 0);
    return 1;
  }
  v6 = *(_QWORD **)a3;
  lpTlsValue = 0;
  if ( v6 && *v6 && !(*(unsigned int (__fastcall **)(_QWORD *, LPVOID *))*v6)(v6, &lpTlsValue) )
    ReportErrorDetails(lpTlsValue);
  return a2;
}

```

## disassembly

```asm
0x180028290  mov     [rsp-18h+arg_10], rbx
0x180028295  mov     [rsp-18h+arg_18], rsi
0x18002829a  push    rbp
0x18002829b  push    rdi
0x18002829c  push    r14
0x18002829e  mov     rbp, rsp
0x1800282a1  sub     rsp, 40h
0x1800282a5  xor     r14d, r14d
0x1800282a8  mov     rbx, r8
0x1800282ab  mov     esi, edx
0x1800282ad  mov     rdi, rcx
0x1800282b0  test    edx, edx
0x1800282b2  jz      short loc_1800282E8
0x1800282b4  mov     rcx, [r8]
0x1800282b7  mov     [rbp+lpTlsValue], r14
0x1800282bb  test    rcx, rcx
0x1800282be  jz      short loc_1800282E1
0x1800282c0  mov     rax, [rcx]
0x1800282c3  test    rax, rax
0x1800282c6  jz      short loc_1800282E1
0x1800282c8  mov     rax, [rax]
0x1800282cb  lea     rdx, [rbp+lpTlsValue]
0x1800282cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282d4  test    eax, eax
0x1800282d6  jnz     short loc_1800282E1
0x1800282d8  mov     rcx, [rbp+lpTlsValue]; lpTlsValue
0x1800282dc  call    ReportErrorDetails
0x1800282e1  mov     eax, esi
0x1800282e3  jmp     loc_1800283A8
0x1800282e8  mov     esi, 11h
0x1800282ed  cmp     [r8+28h], esi
0x1800282f1  jz      short loc_18002834E
0x1800282f3  xorps   xmm0, xmm0
0x1800282f6  lea     rcx, ModuleName; "mpunits.dll"
0x1800282fd  movups  [rbp+var_10], xmm0
0x180028301  call    cs:__imp_GetModuleHandleA
0x180028307  mov     rcx, rax
0x18002830a  mov     edx, 7E1h
0x18002830f  call    _Intlstr_GetString_LoadString
0x180028314  mov     qword ptr [rbp+var_10], rax
0x180028318  lea     r9, [rbp+var_10]
0x18002831c  mov     byte ptr [rbp+var_10+8], r14b
0x180028320  lea     rdx, aBinarylogger; "BinaryLogger"
0x180028327  movaps  xmm0, [rbp+var_10]
0x18002832b  mov     r8d, 17h
0x180028331  mov     [rsp+40h+var_18], r14; __int64
0x180028336  mov     ecx, esi; int
0x180028338  movdqa  [rbp+var_10], xmm0
0x18002833d  mov     [rsp+40h+var_20], r14; __int64
0x180028342  call    MI_ReportErrorDetails_ForCustomError
0x180028347  mov     eax, 1
0x18002834c  jmp     short loc_1800283A8
0x18002834e  mov     eax, [r8+8]
0x180028352  test    eax, eax
0x180028354  jz      short loc_18002835B
0x180028356  cmp     [r8], r14
0x180028359  jz      short loc_1800282F3
0x18002835b  mov     ecx, [rcx]; FileHandle
0x18002835d  lea     rdx, [rbp+Buf]; Buf
0x180028361  mov     r8d, 4; MaxCharCount
0x180028367  mov     [rbp+Buf], eax
0x18002836a  call    cs:__imp__write
0x180028370  cmp     eax, 4
0x180028373  jnz     loc_1800282F3
0x180028379  add     qword ptr [rdi+8], 4
0x18002837e  cmp     [rbp+Buf], r14d
0x180028382  jz      short loc_1800283A6
0x180028384  mov     r8d, [rbx+8]; MaxCharCount
0x180028388  mov     rdx, [rbx]; Buf
0x18002838b  mov     ecx, [rdi]; FileHandle
0x18002838d  call    cs:__imp__write
0x180028393  movsxd  rcx, eax
0x180028396  mov     eax, [rbx+8]
0x180028399  cmp     rcx, rax
0x18002839c  jnz     loc_1800282F3
0x1800283a2  add     [rdi+8], rax
0x1800283a6  xor     eax, eax
0x1800283a8  mov     rbx, [rsp+40h+arg_10]
0x1800283ad  mov     rsi, [rsp+40h+arg_18]
0x1800283b2  add     rsp, 40h
0x1800283b6  pop     r14
0x1800283b8  pop     rdi
0x1800283b9  pop     rbp
0x1800283ba  retn
```
