# CopySStreamToSStream(PSStream *,PSStream *)

- ea: `0x18006031c`
- end: `0x180060408`
- name: `?CopySStreamToSStream@@YAJPEAVPSStream@@0@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct PSStream *this, struct PSStream *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d070`
- `0x18004ab54`

## callees

- `0x180009d7c`
- `0x18000baf8`
- `0x180010cf0`
- `0x18002469c`
- `0x18006031c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800603ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800603ed`

## pseudocode

```c
__int64 __fastcall CopySStreamToSStream(struct PSStream *this, struct PSStream *a2)
{
  void *v4; // rsi
  int v5; // ebx
  unsigned __int64 i; // rdi
  unsigned __int64 v8[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v10; // [rsp+78h] [rbp+20h] BYREF

  v8[0] = 0;
  v9 = 0;
  v10 = 0;
  v4 = CoTaskMemAlloc(0x2000u);
  if ( v4 )
  {
    PSStream::GetSize(this, v8);
    v5 = PSStream::SetSize(a2, v8[0]);
    if ( v5 >= 0 )
    {
      for ( i = 0; ; i += v10 )
      {
        v5 = PSStream::ReadAt(this, i, v4, 0x2000u, &v9);
        if ( v5 < 0 )
          break;
        if ( !v9 )
          break;
        v5 = PSStream::WriteAt(a2, i, v4, v9, &v10);
        if ( v5 < 0 )
          break;
        if ( v9 != v10 )
        {
          v5 = -2147287011;
          break;
        }
      }
    }
    CoTaskMemFree(v4);
  }
  else
  {
    return (unsigned int)-2147287032;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006031c  mov     rax, rsp
0x18006031f  mov     [rax+8], rbx
0x180060323  mov     [rax+10h], rbp
0x180060327  push    rsi
0x180060328  push    rdi
0x180060329  push    r14
0x18006032b  sub     rsp, 40h
0x18006032f  mov     rbp, rcx
0x180060332  mov     qword ptr [rax-28h], 0
0x18006033a  mov     ecx, 2000h; cb
0x18006033f  mov     dword ptr [rax+18h], 0
0x180060346  mov     r14, rdx
0x180060349  mov     dword ptr [rax+20h], 0
0x180060350  call    cs:__imp_CoTaskMemAlloc
0x180060356  mov     rsi, rax
0x180060359  test    rax, rax
0x18006035c  jnz     short loc_180060368
0x18006035e  mov     ebx, 80030008h
0x180060363  jmp     loc_1800603F3
0x180060368  lea     rdx, [rsp+58h+var_28]; unsigned __int64 *
0x18006036d  mov     rcx, rbp; this
0x180060370  call    ?GetSize@PSStream@@QEAAXPEA_K@Z; PSStream::GetSize(unsigned __int64 *)
0x180060375  mov     rdx, [rsp+58h+var_28]; unsigned __int64
0x18006037a  mov     rcx, r14; this
0x18006037d  call    ?SetSize@PSStream@@QEAAJ_K@Z; PSStream::SetSize(unsigned __int64)
0x180060382  mov     ebx, eax
0x180060384  test    eax, eax
0x180060386  js      short loc_1800603EA
0x180060388  xor     edi, edi
0x18006038a  lea     rax, [rsp+58h+arg_10]
0x18006038f  mov     r9d, 2000h; unsigned int
0x180060395  mov     r8, rsi; void *
0x180060398  mov     [rsp+58h+var_38], rax; unsigned int *
0x18006039d  mov     rdx, rdi; unsigned __int64
0x1800603a0  mov     rcx, rbp; this
0x1800603a3  call    ?ReadAt@PSStream@@QEAAJ_KPEAXKPEAK@Z; PSStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x1800603a8  mov     ebx, eax
0x1800603aa  test    eax, eax
0x1800603ac  js      short loc_1800603EA
0x1800603ae  mov     r9d, [rsp+58h+arg_10]; unsigned int
0x1800603b3  test    r9d, r9d
0x1800603b6  jz      short loc_1800603EA
0x1800603b8  lea     rax, [rsp+58h+arg_18]
0x1800603bd  mov     r8, rsi; void *
0x1800603c0  mov     rdx, rdi; unsigned __int64
0x1800603c3  mov     [rsp+58h+var_38], rax; unsigned int *
0x1800603c8  mov     rcx, r14; this
0x1800603cb  call    ?WriteAt@PSStream@@QEAAJ_KPEBXKPEAK@Z; PSStream::WriteAt(unsigned __int64,void const *,ulong,ulong *)
0x1800603d0  mov     ebx, eax
0x1800603d2  test    eax, eax
0x1800603d4  js      short loc_1800603EA
0x1800603d6  mov     eax, [rsp+58h+arg_18]
0x1800603da  cmp     [rsp+58h+arg_10], eax
0x1800603de  jnz     short loc_1800603E5
0x1800603e0  add     rdi, rax
0x1800603e3  jmp     short loc_18006038A
0x1800603e5  mov     ebx, 8003001Dh
0x1800603ea  mov     rcx, rsi; pv
0x1800603ed  call    cs:__imp_CoTaskMemFree
0x1800603f3  mov     rbp, [rsp+58h+arg_8]
0x1800603f8  mov     eax, ebx
0x1800603fa  mov     rbx, [rsp+58h+arg_0]
0x1800603ff  add     rsp, 40h
0x180060403  pop     r14
0x180060405  pop     rdi
0x180060406  pop     rsi
0x180060407  retn
```
