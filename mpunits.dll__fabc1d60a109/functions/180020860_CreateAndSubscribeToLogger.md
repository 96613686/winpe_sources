# CreateAndSubscribeToLogger

- ea: `0x180020860`
- end: `0x1800209ff`
- name: `CreateAndSubscribeToLogger`
- size: `415`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021110`
- `0x1800213c0`
- `0x180021e90`

## callees

- `0x180020860`
- `0x1800292cc`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800208bc`
- `msvcrt!wcscpy_s` at `0x1800208bc`
- `msvcrt!wcscat_s` at `0x1800208e1`
- `msvcrt!wcscat_s` at `0x1800208e1`

## pseudocode

```c
__int64 __fastcall CreateAndSubscribeToLogger(__int64 a1, __int64 a2, _QWORD **a3)
{
  const wchar_t *v5; // r8
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v12; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall *v13)(); // [rsp+58h] [rbp-A8h]
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF

  v10 = 0;
  v5 = (const wchar_t *)a3[8];
  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( wcscpy_s(Destination, 0x104u, v5) || wcscat_s(Destination, 0x104u, L".bmil") )
  {
    return 4;
  }
  else
  {
    v7 = BinaryLogReader_shared((LPCWSTR)a3[11], Destination, 0, a2, 2, &v10);
    if ( !v7 )
    {
      *((_QWORD *)&v11 + 1) = SourceSelector_Log_OnNext;
      *(_QWORD *)&v12 = SourceSelector_Log_OnCompleted;
      *((_QWORD *)&v12 + 1) = SourceSelector_Log_OnError;
      *(_QWORD *)&v11 = a1;
      v13 = ObserverProtocol_Release;
      ((void (__fastcall *)(__int64))ObserverProtocol_AddRef)(a1);
      v8 = v10;
      *a3 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(v10 + 32))(v10, &v11, 0);
      if ( *(_QWORD *)v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v7 = ((__int64 (__fastcall *)(__int64, _QWORD))ObserverProtocol_TrackDisposable)(a1, *a3);
      if ( v7 )
      {
        if ( *a3 )
          ((void (__fastcall *)(_QWORD))(*a3)[1])(**a3);
        if ( *a3 )
          ((void (__fastcall *)(_QWORD))(*a3)[3])(**a3);
        *a3 = 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180020860  mov     [rsp-8+arg_18], rbx
0x180020865  push    rbp
0x180020866  push    rsi
0x180020867  push    rdi
0x180020868  lea     rbp, [rsp-180h]
0x180020870  sub     rsp, 280h
0x180020877  mov     rax, cs:__security_cookie
0x18002087e  xor     rax, rsp
0x180020881  mov     [rbp+190h+var_20], rax
0x180020888  xorps   xmm0, xmm0
0x18002088b  mov     [rsp+290h+var_260], 0
0x180020894  mov     rdi, r8
0x180020897  mov     rbx, rdx
0x18002089a  mov     r8, [r8+40h]; Source
0x18002089e  mov     rsi, rcx
0x1800208a1  xor     eax, eax
0x1800208a3  lea     rcx, [rsp+290h+Destination]; Destination
0x1800208a8  mov     edx, 104h; SizeInWords
0x1800208ad  mov     [rsp+290h+var_238], rax
0x1800208b2  movups  [rsp+290h+var_258], xmm0
0x1800208b7  movups  [rsp+290h+var_248], xmm0
0x1800208bc  call    cs:__imp_wcscpy_s
0x1800208c2  test    eax, eax
0x1800208c4  jz      short loc_1800208D0
0x1800208c6  mov     ebx, 4
0x1800208cb  jmp     loc_1800209DB
0x1800208d0  lea     r8, aBmil; ".bmil"
0x1800208d7  mov     edx, 104h; SizeInWords
0x1800208dc  lea     rcx, [rsp+290h+Destination]; Destination
0x1800208e1  call    cs:__imp_wcscat_s
0x1800208e7  test    eax, eax
0x1800208e9  jnz     short loc_1800208C6
0x1800208eb  mov     rcx, [rdi+58h]; lpSrc
0x1800208ef  lea     rax, [rsp+290h+var_260]
0x1800208f4  mov     [rsp+290h+var_268], rax; __int64
0x1800208f9  lea     rdx, [rsp+290h+Destination]; String
0x1800208fe  mov     r9, rbx
0x180020901  mov     [rsp+290h+var_270], 2; int
0x180020909  xor     r8d, r8d; wchar_t *
0x18002090c  call    BinaryLogReader_shared
0x180020911  mov     ebx, eax
0x180020913  test    eax, eax
0x180020915  jnz     loc_1800209DB
0x18002091b  mov     rcx, cs:off_180047BB0
0x180020922  lea     rax, SourceSelector_Log_OnNext
0x180020929  mov     qword ptr [rsp+290h+var_258+8], rax
0x18002092e  lea     rax, SourceSelector_Log_OnCompleted
0x180020935  mov     qword ptr [rsp+290h+var_248], rax
0x18002093a  lea     rax, SourceSelector_Log_OnError
0x180020941  mov     qword ptr [rsp+290h+var_248+8], rax
0x180020946  mov     qword ptr [rsp+290h+var_258], rsi
0x18002094b  mov     rax, [rcx+10h]
0x18002094f  mov     [rsp+290h+var_238], rax
0x180020954  mov     rax, [rcx+8]
0x180020958  mov     rcx, rsi
0x18002095b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020960  mov     rbx, [rsp+290h+var_260]
0x180020965  lea     rdx, [rsp+290h+var_258]
0x18002096a  xor     r8d, r8d
0x18002096d  mov     rcx, rbx
0x180020970  mov     rax, [rbx+20h]
0x180020974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020979  mov     [rdi], rax
0x18002097c  mov     rax, [rbx]
0x18002097f  test    rax, rax
0x180020982  jz      short loc_180020990
0x180020984  mov     rax, [rax+10h]
0x180020988  mov     rcx, rbx
0x18002098b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020990  mov     rax, cs:off_180047BB0
0x180020997  mov     rcx, rsi
0x18002099a  mov     rdx, [rdi]
0x18002099d  mov     rax, [rax+70h]
0x1800209a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209a6  mov     ebx, eax
0x1800209a8  test    eax, eax
0x1800209aa  jz      short loc_1800209DB
0x1800209ac  mov     rax, [rdi]
0x1800209af  test    rax, rax
0x1800209b2  jz      short loc_1800209C0
0x1800209b4  mov     rcx, [rax]
0x1800209b7  mov     rax, [rax+8]
0x1800209bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209c0  mov     rax, [rdi]
0x1800209c3  test    rax, rax
0x1800209c6  jz      short loc_1800209D4
0x1800209c8  mov     rcx, [rax]
0x1800209cb  mov     rax, [rax+18h]
0x1800209cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209d4  mov     qword ptr [rdi], 0
0x1800209db  mov     eax, ebx
0x1800209dd  mov     rcx, [rbp+190h+var_20]
0x1800209e4  xor     rcx, rsp; StackCookie
0x1800209e7  call    __security_check_cookie
0x1800209ec  mov     rbx, [rsp+290h+arg_18]
0x1800209f4  add     rsp, 280h
0x1800209fb  pop     rdi
0x1800209fc  pop     rsi
0x1800209fd  pop     rbp
0x1800209fe  retn
```
