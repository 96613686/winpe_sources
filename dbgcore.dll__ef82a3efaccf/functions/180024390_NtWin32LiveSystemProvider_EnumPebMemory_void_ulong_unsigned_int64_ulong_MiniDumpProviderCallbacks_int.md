# NtWin32LiveSystemProvider::EnumPebMemory(void *,ulong,unsigned __int64,ulong,MiniDumpProviderCallbacks *,int)

- ea: `0x180024390`
- end: `0x1800245de`
- name: `?EnumPebMemory@NtWin32LiveSystemProvider@@UEAAJPEAXK_KKPEAVMiniDumpProviderCallbacks@@H@Z`
- size: `590`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, void *, unsigned int, unsigned __int64, unsigned int, struct MiniDumpProviderCallbacks *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180024390`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::EnumPebMemory(
        NtWin32LiveSystemProvider *this,
        void *a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        struct MiniDumpProviderCallbacks *a6)
{
  unsigned int v9; // ebx
  __int64 result; // rax
  _BYTE v12[56]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v13; // [rsp+68h] [rbp-98h]
  __int64 v14; // [rsp+70h] [rbp-90h]
  unsigned __int16 v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+88h] [rbp-78h]
  unsigned __int16 v17; // [rsp+90h] [rbp-70h]
  __int64 v18; // [rsp+98h] [rbp-68h]
  unsigned __int16 v19; // [rsp+A0h] [rbp-60h]
  __int64 v20; // [rsp+A8h] [rbp-58h]
  __int64 v21; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v24; // [rsp+F0h] [rbp-10h]
  __int64 v25; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v26; // [rsp+100h] [rbp+0h]
  __int64 v27; // [rsp+108h] [rbp+8h]
  unsigned __int16 v28; // [rsp+110h] [rbp+10h]
  __int64 v29; // [rsp+118h] [rbp+18h]
  _BYTE v30[32]; // [rsp+480h] [rbp+380h] BYREF
  __int64 v31; // [rsp+4A0h] [rbp+3A0h]

  v9 = 2000;
  memset_0(v30, 0, 0x7D0u);
  if ( a5 <= 0x7D0 )
    v9 = a5;
  result = (*(__int64 (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, _BYTE *, unsigned int))(*(_QWORD *)this + 240LL))(
             this,
             a2,
             a4,
             v30,
             v9);
  if ( !(_DWORD)result )
  {
    if ( (a3 & 0x100000) == 0 )
    {
      memset_0(v12, 0, 0x450u);
      if ( v31 )
      {
        if ( !(*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, _BYTE *, int))(*(_QWORD *)this + 240LL))(
                this,
                a2,
                v31,
                v12,
                1104) )
        {
          (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, __int64))a6)(a6, v31, 1104);
          if ( v13 && v14 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v14, v13);
          if ( v15 && v16 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v16, v15);
          if ( v17 && v18 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v18, v17);
          if ( v19 && v20 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v20, v19);
          (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, __int64))a6)(a6, v21, 0x2000);
          if ( v22 && v23 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v23, v22);
          if ( v24 && v25 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v25, v24);
          if ( v26 && v27 )
            (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v27, v26);
          if ( v28 )
          {
            if ( v29 )
              (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, __int64, _QWORD))a6)(a6, v29, v28);
          }
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024390  push    rbp
0x180024392  push    rbx
0x180024393  push    rsi
0x180024394  push    rdi
0x180024395  push    r12
0x180024397  push    r14
0x180024399  push    r15
0x18002439b  lea     rbp, [rsp-0B60h]
0x1800243a3  sub     rsp, 0C60h
0x1800243aa  mov     rax, cs:__security_cookie
0x1800243b1  xor     rax, rsp
0x1800243b4  mov     [rbp+0B90h+var_40], rax
0x1800243bb  mov     rsi, [rbp+0B90h+arg_28]
0x1800243c2  mov     r15d, r8d
0x1800243c5  mov     r12, rdx
0x1800243c8  mov     r14, rcx
0x1800243cb  mov     ebx, 7D0h
0x1800243d0  lea     rcx, [rbp+0B90h+var_810]; void *
0x1800243d7  mov     r8d, ebx; Size
0x1800243da  xor     edx, edx; Val
0x1800243dc  mov     rdi, r9
0x1800243df  call    memset_0
0x1800243e4  mov     rax, [r14]
0x1800243e7  lea     r9, [rbp+0B90h+var_810]
0x1800243ee  cmp     [rbp+0B90h+arg_20], ebx
0x1800243f4  mov     r8, rdi
0x1800243f7  mov     rdx, r12
0x1800243fa  mov     rcx, r14
0x1800243fd  cmovbe  ebx, [rbp+0B90h+arg_20]
0x180024404  mov     rax, [rax+0F0h]
0x18002440b  mov     [rsp+0C90h+var_C70], ebx
0x18002440f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024414  test    eax, eax
0x180024416  jnz     loc_1800245BD
0x18002441c  bt      r15d, 14h
0x180024421  jb      loc_1800245BB
0x180024427  mov     edi, 450h
0x18002442c  lea     rcx, [rsp+0C90h+var_C60]; void *
0x180024431  mov     r8d, edi; Size
0x180024434  xor     edx, edx; Val
0x180024436  call    memset_0
0x18002443b  mov     r8, [rbp+0B90h+var_7F0]
0x180024442  test    r8, r8
0x180024445  jz      loc_1800245BB
0x18002444b  mov     rax, [r14]
0x18002444e  lea     r9, [rsp+0C90h+var_C60]
0x180024453  mov     rdx, r12
0x180024456  mov     [rsp+0C90h+var_C70], edi
0x18002445a  mov     rcx, r14
0x18002445d  mov     rax, [rax+0F0h]
0x180024464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024469  test    eax, eax
0x18002446b  jnz     loc_1800245BB
0x180024471  mov     rax, [rsi]
0x180024474  mov     r8d, edi
0x180024477  mov     rdx, [rbp+0B90h+var_7F0]
0x18002447e  mov     rcx, rsi
0x180024481  mov     rax, [rax]
0x180024484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024489  movzx   ecx, [rsp+0C90h+var_C28]
0x18002448e  test    cx, cx
0x180024491  jz      short loc_1800244AE
0x180024493  mov     rdx, [rsp+0C90h+var_C20]
0x180024498  test    rdx, rdx
0x18002449b  jz      short loc_1800244AE
0x18002449d  mov     rax, [rsi]
0x1800244a0  mov     r8d, ecx
0x1800244a3  mov     rcx, rsi
0x1800244a6  mov     rax, [rax]
0x1800244a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244ae  movzx   ecx, [rbp+0B90h+var_C10]
0x1800244b2  test    cx, cx
0x1800244b5  jz      short loc_1800244D1
0x1800244b7  mov     rdx, [rbp+0B90h+var_C08]
0x1800244bb  test    rdx, rdx
0x1800244be  jz      short loc_1800244D1
0x1800244c0  mov     rax, [rsi]
0x1800244c3  mov     r8d, ecx
0x1800244c6  mov     rcx, rsi
0x1800244c9  mov     rax, [rax]
0x1800244cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244d1  movzx   ecx, [rbp+0B90h+var_C00]
0x1800244d5  test    cx, cx
0x1800244d8  jz      short loc_1800244F4
0x1800244da  mov     rdx, [rbp+0B90h+var_BF8]
0x1800244de  test    rdx, rdx
0x1800244e1  jz      short loc_1800244F4
0x1800244e3  mov     rax, [rsi]
0x1800244e6  mov     r8d, ecx
0x1800244e9  mov     rcx, rsi
0x1800244ec  mov     rax, [rax]
0x1800244ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244f4  movzx   ecx, [rbp+0B90h+var_BF0]
0x1800244f8  test    cx, cx
0x1800244fb  jz      short loc_180024517
0x1800244fd  mov     rdx, [rbp+0B90h+var_BE8]
0x180024501  test    rdx, rdx
0x180024504  jz      short loc_180024517
0x180024506  mov     rax, [rsi]
0x180024509  mov     r8d, ecx
0x18002450c  mov     rcx, rsi
0x18002450f  mov     rax, [rax]
0x180024512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024517  mov     rax, [rsi]
0x18002451a  mov     r8d, 2000h
0x180024520  mov     rdx, [rbp+0B90h+var_BE0]
0x180024524  mov     rcx, rsi
0x180024527  mov     rax, [rax]
0x18002452a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002452f  movzx   ecx, [rbp+0B90h+var_BB0]
0x180024533  test    cx, cx
0x180024536  jz      short loc_180024552
0x180024538  mov     rdx, [rbp+0B90h+var_BA8]
0x18002453c  test    rdx, rdx
0x18002453f  jz      short loc_180024552
0x180024541  mov     rax, [rsi]
0x180024544  mov     r8d, ecx
0x180024547  mov     rcx, rsi
0x18002454a  mov     rax, [rax]
0x18002454d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024552  movzx   ecx, [rbp+0B90h+var_BA0]
0x180024556  test    cx, cx
0x180024559  jz      short loc_180024575
0x18002455b  mov     rdx, [rbp+0B90h+var_B98]
0x18002455f  test    rdx, rdx
0x180024562  jz      short loc_180024575
0x180024564  mov     rax, [rsi]
0x180024567  mov     r8d, ecx
0x18002456a  mov     rcx, rsi
0x18002456d  mov     rax, [rax]
0x180024570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024575  movzx   ecx, [rbp+0B90h+var_B90]
0x180024579  test    cx, cx
0x18002457c  jz      short loc_180024598
0x18002457e  mov     rdx, [rbp+0B90h+var_B88]
0x180024582  test    rdx, rdx
0x180024585  jz      short loc_180024598
0x180024587  mov     rax, [rsi]
0x18002458a  mov     r8d, ecx
0x18002458d  mov     rcx, rsi
0x180024590  mov     rax, [rax]
0x180024593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024598  movzx   ecx, [rbp+0B90h+var_B80]
0x18002459c  test    cx, cx
0x18002459f  jz      short loc_1800245BB
0x1800245a1  mov     rdx, [rbp+0B90h+var_B78]
0x1800245a5  test    rdx, rdx
0x1800245a8  jz      short loc_1800245BB
0x1800245aa  mov     rax, [rsi]
0x1800245ad  mov     r8d, ecx
0x1800245b0  mov     rcx, rsi
0x1800245b3  mov     rax, [rax]
0x1800245b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245bb  xor     eax, eax
0x1800245bd  mov     rcx, [rbp+0B90h+var_40]
0x1800245c4  xor     rcx, rsp; StackCookie
0x1800245c7  call    __security_check_cookie
0x1800245cc  add     rsp, 0C60h
0x1800245d3  pop     r15
0x1800245d5  pop     r14
0x1800245d7  pop     r12
0x1800245d9  pop     rdi
0x1800245da  pop     rsi
0x1800245db  pop     rbx
0x1800245dc  pop     rbp
0x1800245dd  retn
```
