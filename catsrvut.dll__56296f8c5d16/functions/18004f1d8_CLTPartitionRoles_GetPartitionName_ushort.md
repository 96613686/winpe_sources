# CLTPartitionRoles::GetPartitionName(ushort * *)

- ea: `0x18004f1d8`
- end: `0x18004f35d`
- name: `?GetPartitionName@CLTPartitionRoles@@AEAAJPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(CLTPartitionRoles *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f780`

## callees

- `0x180001e60`
- `0x180015594`
- `0x18004f1d8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f31f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f31f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f2fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f2fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTPartitionRoles::GetPartitionName(CLTPartitionRoles *this, LPVOID *a2)
{
  int v3; // ebx
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rax
  _QWORD v7[2]; // [rsp+50h] [rbp-20h] BYREF
  int v8; // [rsp+60h] [rbp-10h]
  int v9; // [rsp+64h] [rbp-Ch]
  __int64 v10; // [rsp+80h] [rbp+10h] BYREF
  unsigned __int16 *v11; // [rsp+88h] [rbp+18h]

  v10 = 0;
  *a2 = 0;
  v7[0] = (char *)this + 64;
  v7[1] = 0;
  v8 = 72;
  v9 = 16;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(**((_QWORD **)this + 7) + 24LL))(
         *((_QWORD *)this + 7),
         &didCOMSERVICES,
         TID_LT_APPLICATIONPARTITION,
         v7,
         1,
         1,
         1,
         &v10);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10);
      if ( v3 >= 0 )
      {
        v11 = 0;
        v3 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, 1, 0);
        if ( v3 >= 0 )
        {
          if ( v11 )
          {
            v4 = safe_lstrlenW(v11) + 1;
            v5 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v4, 2u));
            *a2 = v5;
            if ( v5 )
            {
              v3 = StringCchCopyW(v5, v4, v11);
              if ( v3 < 0 )
              {
                CoTaskMemFree(*a2);
                *a2 = 0;
              }
            }
            else
            {
              v3 = -2147024882;
            }
          }
          else
          {
            v3 = -2147418113;
          }
        }
      }
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004f1d8  mov     r11, rsp
0x18004f1db  mov     [r11+18h], rbx
0x18004f1df  mov     [r11+20h], rdi
0x18004f1e3  push    rbp
0x18004f1e4  mov     rbp, rsp
0x18004f1e7  sub     rsp, 70h
0x18004f1eb  mov     rdi, rdx
0x18004f1ee  mov     [rbp+arg_0], 0
0x18004f1f6  mov     qword ptr [rdx], 0
0x18004f1fd  lea     rax, [rcx+40h]
0x18004f201  mov     [rbp+var_20], rax
0x18004f205  mov     [rbp+var_18], 0
0x18004f20d  mov     [rbp+var_10], 48h ; 'H'
0x18004f214  mov     [rbp+var_C], 10h
0x18004f21b  mov     rcx, [rcx+38h]
0x18004f21f  mov     rax, [rcx]
0x18004f222  lea     rdx, [rbp+arg_0]
0x18004f226  mov     [r11-40h], rdx
0x18004f22a  mov     [rsp+70h+var_40], 1
0x18004f232  mov     [rsp+70h+var_48], 1
0x18004f23a  mov     qword ptr [r11-58h], 1
0x18004f242  lea     r9, [rbp+var_20]
0x18004f246  lea     r8, TID_LT_APPLICATIONPARTITION
0x18004f24d  lea     rdx, didCOMSERVICES
0x18004f254  mov     rax, [rax+18h]
0x18004f258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f25d  mov     ebx, eax
0x18004f25f  test    eax, eax
0x18004f261  js      loc_18004F334
0x18004f267  mov     rcx, [rbp+arg_0]
0x18004f26b  mov     rax, [rcx]
0x18004f26e  mov     rax, [rax+18h]
0x18004f272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f277  mov     ebx, eax
0x18004f279  test    eax, eax
0x18004f27b  js      loc_18004F334
0x18004f281  mov     rcx, [rbp+arg_0]
0x18004f285  mov     rax, [rcx]
0x18004f288  mov     rax, [rax+28h]
0x18004f28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f291  mov     ebx, eax
0x18004f293  test    eax, eax
0x18004f295  js      loc_18004F334
0x18004f29b  mov     [rbp+arg_8], 0
0x18004f2a3  mov     rcx, [rbp+arg_0]
0x18004f2a7  mov     rax, [rcx]
0x18004f2aa  lea     rdx, [rbp+arg_8]
0x18004f2ae  mov     [rsp+70h+var_50], rdx
0x18004f2b3  xor     r9d, r9d
0x18004f2b6  xor     r8d, r8d
0x18004f2b9  lea     edx, [r9+1]
0x18004f2bd  mov     rax, [rax+40h]
0x18004f2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2c6  mov     ebx, eax
0x18004f2c8  test    eax, eax
0x18004f2ca  js      short loc_18004F334
0x18004f2cc  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x18004f2d0  test    rcx, rcx
0x18004f2d3  jnz     short loc_18004F2DC
0x18004f2d5  mov     ebx, 8000FFFFh
0x18004f2da  jmp     short loc_18004F334
0x18004f2dc  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004f2e1  lea     ebx, [rax+1]
0x18004f2e4  mov     eax, 2
0x18004f2e9  mul     rbx
0x18004f2ec  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f2f3  cmovb   rax, rcx
0x18004f2f7  mov     rcx, rax; cb
0x18004f2fa  call    cs:__imp_CoTaskMemAlloc
0x18004f300  mov     [rdi], rax
0x18004f303  test    rax, rax
0x18004f306  jz      short loc_18004F32F
0x18004f308  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x18004f30c  mov     edx, ebx; unsigned __int64
0x18004f30e  mov     rcx, rax; unsigned __int16 *
0x18004f311  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f316  mov     ebx, eax
0x18004f318  test    eax, eax
0x18004f31a  jns     short loc_18004F334
0x18004f31c  mov     rcx, [rdi]; pv
0x18004f31f  call    cs:__imp_CoTaskMemFree
0x18004f325  nop
0x18004f326  mov     qword ptr [rdi], 0
0x18004f32d  jmp     short loc_18004F334
0x18004f32f  mov     ebx, 8007000Eh
0x18004f334  mov     rcx, [rbp+arg_0]
0x18004f338  test    rcx, rcx
0x18004f33b  jz      short loc_18004F349
0x18004f33d  mov     rax, [rcx]
0x18004f340  mov     rax, [rax+10h]
0x18004f344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f349  mov     eax, ebx
0x18004f34b  lea     r11, [rsp+70h+var_s0]
0x18004f350  mov     rbx, [r11+20h]
0x18004f354  mov     rdi, [r11+28h]
0x18004f358  mov     rsp, r11
0x18004f35b  pop     rbp
0x18004f35c  retn
```
