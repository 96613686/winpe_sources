# CBasePin::AttemptConnection(IPin *,CMediaType const *)

- ea: `0x180026608`
- end: `0x180026729`
- name: `?AttemptConnection@CBasePin@@IEAAJPEAUIPin@@PEBVCMediaType@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(CBasePin *__hidden this, struct IPin *, const struct CMediaType *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026394`

## callees

- `0x180026608`
- `0x180088750`

## pseudocode

```c
__int64 __fastcall CBasePin::AttemptConnection(CBasePin *this, struct IPin *a2, const struct CMediaType *a3)
{
  int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rcx

  v6 = (*(__int64 (__fastcall **)(CBasePin *))(*(_QWORD *)this + 80LL))(this);
  v7 = *(_QWORD *)this;
  if ( v6 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CBasePin *, const struct CMediaType *))(v7 + 64))(this, a3);
    v6 = v8;
    if ( v8 )
    {
      if ( v8 >= 0 || v8 == -2147467259 || v8 == -2147024809 )
        v6 = -2147220950;
    }
    else
    {
      *((_QWORD *)this + 6) = a2;
      ((void (__fastcall *)(struct IPin *))a2->lpVtbl->AddRef)(a2);
      v6 = (*(__int64 (__fastcall **)(CBasePin *, const struct CMediaType *))(*(_QWORD *)this + 72LL))(this, a3);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(struct IPin *, unsigned __int64, const struct CMediaType *))a2->lpVtbl->ReceiveConnection)(
               a2,
               ((unsigned __int64)this + 24) & -(__int64)(this != 0),
               a3);
        if ( v6 >= 0 )
        {
          result = (*(__int64 (__fastcall **)(CBasePin *, struct IPin *))(*(_QWORD *)this + 96LL))(this, a2);
          v6 = result;
          if ( (int)result >= 0 )
            return result;
          ((void (__fastcall *)(struct IPin *))a2->lpVtbl->Disconnect)(a2);
        }
      }
    }
    (*(void (__fastcall **)(CBasePin *))(*(_QWORD *)this + 88LL))(this);
    v10 = *((_QWORD *)this + 6);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 6) = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(CBasePin *))(v7 + 88))(this);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026608  push    rbx
0x18002660a  push    rbp
0x18002660b  push    rsi
0x18002660c  push    rdi
0x18002660d  sub     rsp, 28h
0x180026611  mov     rax, [rcx]
0x180026614  mov     rbp, r8
0x180026617  mov     rsi, rdx
0x18002661a  mov     rdi, rcx
0x18002661d  mov     rax, [rax+50h]
0x180026621  call    cs:__guard_dispatch_icall_fptr
0x180026627  mov     ebx, eax
0x180026629  mov     rcx, rdi
0x18002662c  mov     rax, [rdi]
0x18002662f  test    ebx, ebx
0x180026631  jns     short loc_180026642
0x180026633  mov     rax, [rax+58h]
0x180026637  call    cs:__guard_dispatch_icall_fptr
0x18002663d  jmp     loc_18002671D
0x180026642  mov     rax, [rax+40h]
0x180026646  mov     rdx, rbp
0x180026649  call    cs:__guard_dispatch_icall_fptr
0x18002664f  mov     ebx, eax
0x180026651  test    eax, eax
0x180026653  jnz     loc_1800266DA
0x180026659  mov     [rdi+30h], rsi
0x18002665d  mov     rcx, rsi
0x180026660  mov     rax, [rsi]
0x180026663  mov     rax, [rax+8]
0x180026667  call    cs:__guard_dispatch_icall_fptr
0x18002666d  mov     rax, [rdi]
0x180026670  mov     rdx, rbp
0x180026673  mov     rcx, rdi
0x180026676  mov     rax, [rax+48h]
0x18002667a  call    cs:__guard_dispatch_icall_fptr
0x180026680  mov     ebx, eax
0x180026682  test    eax, eax
0x180026684  js      short loc_1800266EF
0x180026686  mov     r9, [rsi]
0x180026689  lea     rcx, [rdi+18h]
0x18002668d  mov     rax, rdi
0x180026690  mov     r8, rbp
0x180026693  neg     rax
0x180026696  mov     rax, [r9+20h]
0x18002669a  sbb     rdx, rdx
0x18002669d  and     rdx, rcx
0x1800266a0  mov     rcx, rsi
0x1800266a3  call    cs:__guard_dispatch_icall_fptr
0x1800266a9  mov     ebx, eax
0x1800266ab  test    eax, eax
0x1800266ad  js      short loc_1800266EF
0x1800266af  mov     rax, [rdi]
0x1800266b2  mov     rdx, rsi
0x1800266b5  mov     rcx, rdi
0x1800266b8  mov     rax, [rax+60h]
0x1800266bc  call    cs:__guard_dispatch_icall_fptr
0x1800266c2  mov     ebx, eax
0x1800266c4  test    eax, eax
0x1800266c6  jns     short loc_18002671F
0x1800266c8  mov     rax, [rsi]
0x1800266cb  mov     rcx, rsi
0x1800266ce  mov     rax, [rax+28h]
0x1800266d2  call    cs:__guard_dispatch_icall_fptr
0x1800266d8  jmp     short loc_1800266EF
0x1800266da  jns     short loc_1800266EA
0x1800266dc  cmp     eax, 80004005h
0x1800266e1  jz      short loc_1800266EA
0x1800266e3  cmp     eax, 80070057h
0x1800266e8  jnz     short loc_1800266EF
0x1800266ea  mov     ebx, 8004022Ah
0x1800266ef  mov     rax, [rdi]
0x1800266f2  mov     rcx, rdi
0x1800266f5  mov     rax, [rax+58h]
0x1800266f9  call    cs:__guard_dispatch_icall_fptr
0x1800266ff  mov     rcx, [rdi+30h]
0x180026703  test    rcx, rcx
0x180026706  jz      short loc_18002671D
0x180026708  mov     rax, [rcx]
0x18002670b  mov     rax, [rax+10h]
0x18002670f  call    cs:__guard_dispatch_icall_fptr
0x180026715  mov     qword ptr [rdi+30h], 0
0x18002671d  mov     eax, ebx
0x18002671f  add     rsp, 28h
0x180026723  pop     rdi
0x180026724  pop     rsi
0x180026725  pop     rbp
0x180026726  pop     rbx
0x180026727  retn
```
