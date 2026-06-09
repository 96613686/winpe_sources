# W3_CGI_HANDLER::CGIWriteResponseEntity(void)

- ea: `0x18000325c`
- end: `0x180003352`
- name: `?CGIWriteResponseEntity@W3_CGI_HANDLER@@AEAAJXZ`
- size: `246`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002d28`

## callees

- `0x18000325c`
- `0x180005914`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::CGIWriteResponseEntity(W3_CGI_HANDLER *this)
{
  __int64 v2; // rax
  unsigned int v3; // edx
  __int64 v4; // rdi
  unsigned int v5; // ecx
  unsigned int (__fastcall ***v6)(_QWORD); // rax
  int v7; // eax
  unsigned int v8; // ecx
  _QWORD v10[2]; // [rsp+40h] [rbp-28h] BYREF
  int v11; // [rsp+50h] [rbp-18h]
  __int64 v12; // [rsp+54h] [rbp-14h]
  int v13; // [rsp+5Ch] [rbp-Ch]

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
  v3 = *((_DWORD *)this + 2076);
  v4 = v2;
  v5 = *((_DWORD *)this + 14);
  if ( v5 > v3 )
  {
    *((_DWORD *)this + 14) = v5 - v3;
  }
  else
  {
    *((_DWORD *)this + 2076) = v5;
    *((_DWORD *)this + 14) = 0;
    W3_CGI_HANDLER::SetCgiStateDoneWithRequest(this);
  }
  v6 = (unsigned int (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
  if ( !v6 || !(**v6)(v6) )
    return 2147952454LL;
  v10[0] = 0;
  v10[1] = (char *)this + 64;
  v11 = *((_DWORD *)this + 2076);
  v12 = 0;
  v13 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int64, int, _QWORD, _QWORD))(*(_QWORD *)v4 + 168LL))(
         v4,
         v10,
         1,
         1,
         1,
         0,
         0);
  v8 = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return v8;
}

```

## disassembly

```asm
0x18000325c  mov     [rsp+arg_0], rbx
0x180003261  push    rdi
0x180003262  sub     rsp, 60h
0x180003266  mov     rbx, rcx
0x180003269  mov     rcx, [rcx+30h]
0x18000326d  mov     rax, [rcx]
0x180003270  mov     rax, [rax+20h]
0x180003274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003279  mov     edx, [rbx+2070h]
0x18000327f  mov     rdi, rax
0x180003282  mov     ecx, [rbx+38h]
0x180003285  cmp     ecx, edx
0x180003287  ja      short loc_1800032A0
0x180003289  mov     [rbx+2070h], ecx
0x18000328f  mov     rcx, rbx; this
0x180003292  mov     dword ptr [rbx+38h], 0
0x180003299  call    ?SetCgiStateDoneWithRequest@W3_CGI_HANDLER@@QEAAJXZ; W3_CGI_HANDLER::SetCgiStateDoneWithRequest(void)
0x18000329e  jmp     short loc_1800032A5
0x1800032a0  sub     ecx, edx
0x1800032a2  mov     [rbx+38h], ecx
0x1800032a5  mov     rcx, [rbx+30h]
0x1800032a9  mov     rax, [rcx]
0x1800032ac  mov     rax, [rax+10h]
0x1800032b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b5  mov     rdx, rax
0x1800032b8  test    rax, rax
0x1800032bb  jz      loc_180003342
0x1800032c1  mov     rcx, [rax]
0x1800032c4  mov     rax, [rcx]
0x1800032c7  mov     rcx, rdx
0x1800032ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032cf  test    eax, eax
0x1800032d1  jz      short loc_180003342
0x1800032d3  lea     rax, [rbx+40h]
0x1800032d7  mov     [rsp+68h+var_28], 0
0x1800032e0  mov     [rsp+68h+var_20], rax
0x1800032e5  lea     rdx, [rsp+68h+var_28]
0x1800032ea  mov     eax, [rbx+2070h]
0x1800032f0  mov     r8d, 1
0x1800032f6  mov     [rsp+68h+var_18], eax
0x1800032fa  mov     r9d, r8d
0x1800032fd  mov     [rsp+68h+var_14], 0
0x180003306  mov     rcx, rdi
0x180003309  mov     [rsp+68h+var_C], 0
0x180003311  mov     rax, [rdi]
0x180003314  mov     [rsp+68h+var_38], 0
0x18000331d  mov     [rsp+68h+var_40], 0
0x180003326  mov     [rsp+68h+var_48], r8d
0x18000332b  mov     rax, [rax+0A8h]
0x180003332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003337  xor     ecx, ecx
0x180003339  test    eax, eax
0x18000333b  cmovs   ecx, eax
0x18000333e  mov     eax, ecx
0x180003340  jmp     short loc_180003347
0x180003342  mov     eax, 80072746h
0x180003347  mov     rbx, [rsp+68h+arg_0]
0x18000334c  add     rsp, 60h
0x180003350  pop     rdi
0x180003351  retn
```
