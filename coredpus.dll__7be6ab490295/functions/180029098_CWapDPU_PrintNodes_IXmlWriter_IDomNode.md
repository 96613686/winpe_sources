# CWapDPU::PrintNodes(IXmlWriter *,IDomNode *)

- ea: `0x180029098`
- end: `0x180029232`
- name: `?PrintNodes@CWapDPU@@AEAAJPEAUIXmlWriter@@PEAUIDomNode@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CWapDPU *__hidden this, struct IXmlWriter *, struct IDomNode *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028b20`
- `0x180029098`

## callees

- `0x1800110bc`
- `0x180023b0c`
- `0x180029098`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWapDPU::PrintNodes(CWapDPU *this, struct IXmlWriter *a2, struct IDomNode *a3)
{
  int v6; // ebx
  unsigned int i; // r14d
  int v8; // eax
  int v9; // ecx
  struct IDomNode *v11[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+18h] BYREF
  int v13; // [rsp+68h] [rbp+20h]

  v12 = 0;
  v11[0] = 0;
  v6 = (*(__int64 (__fastcall **)(struct IDomNode *))(*(_QWORD *)a3 + 272LL))(a3);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IDomNode *, struct IXmlWriter *))(*(_QWORD *)a3 + 248LL))(a3, a2);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IDomNode *, unsigned int *))(*(_QWORD *)a3 + 200LL))(a3, &v12);
      if ( v6 >= 0 )
      {
        for ( i = 0; i < v12; ++i )
        {
          ATL::CComPtrBase<IDomNode>::Release(v11);
          v6 = (*(__int64 (__fastcall **)(struct IDomNode *, _QWORD, struct IDomNode **))(*(_QWORD *)a3 + 192LL))(
                 a3,
                 i,
                 v11);
          if ( v6 < 0 )
            goto LABEL_21;
          if ( !v11[0] )
          {
            v6 = -2147024882;
            goto LABEL_21;
          }
          v6 = CWapDPU::PrintNodes(this, a2, v11[0]);
          if ( v6 < 0 )
            goto LABEL_21;
        }
        v6 = (*(__int64 (__fastcall **)(struct IDomNode *, struct IXmlWriter *))(*(_QWORD *)a3 + 256LL))(a3, a2);
        if ( v6 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(struct IDomNode *))(*(_QWORD *)a3 + 32LL))(a3);
          v9 = *((_DWORD *)this + 10);
          if ( v8 >= 0 )
          {
            if ( v9 < 0 || v8 != 44761091 )
            {
LABEL_20:
              (*(void (__fastcall **)(struct IDomNode *, _QWORD))(*(_QWORD *)a3 + 128LL))(a3, 0);
              goto LABEL_21;
            }
            *((_DWORD *)this + 10) = 44761091;
          }
          else if ( v9 == -2046820347 )
          {
            *((_DWORD *)this + 10) = v8;
          }
          else if ( v9 >= 0 )
          {
            *((_DWORD *)this + 10) = 1;
          }
          try
          {
            (*(void (__fastcall **)(struct IDomNode *, char *))(*(_QWORD *)a3 + 80LL))(a3, (char *)this + 56);
          }
          catch ( std::bad_alloc )
          {
            v13 = -2147024882;
            v6 = -2147024882;
            goto LABEL_21;
          }
          goto LABEL_20;
        }
      }
    }
  }
LABEL_21:
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180029098  mov     rax, rsp
0x18002909b  mov     [rax+8], rbx
0x18002909f  mov     [rax+10h], rsi
0x1800290a3  push    rdi
0x1800290a4  push    r14
0x1800290a6  push    r15
0x1800290a8  sub     rsp, 30h
0x1800290ac  mov     rdi, r8
0x1800290af  mov     r15, rdx
0x1800290b2  mov     rsi, rcx
0x1800290b5  mov     dword ptr [rax+18h], 0
0x1800290bc  mov     qword ptr [rax-28h], 0
0x1800290c4  mov     rax, [r8]
0x1800290c7  mov     rcx, r8
0x1800290ca  mov     rax, [rax+110h]
0x1800290d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290d6  mov     ebx, eax
0x1800290d8  test    eax, eax
0x1800290da  js      loc_18002920A
0x1800290e0  mov     rax, [rdi]
0x1800290e3  mov     rdx, r15
0x1800290e6  mov     rcx, rdi
0x1800290e9  mov     rax, [rax+0F8h]
0x1800290f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f5  mov     ebx, eax
0x1800290f7  test    eax, eax
0x1800290f9  js      loc_18002920A
0x1800290ff  mov     rax, [rdi]
0x180029102  lea     rdx, [rsp+48h+arg_10]
0x180029107  mov     rcx, rdi
0x18002910a  mov     rax, [rax+0C8h]
0x180029111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029116  mov     ebx, eax
0x180029118  test    eax, eax
0x18002911a  js      loc_18002920A
0x180029120  xor     r14d, r14d
0x180029123  cmp     r14d, [rsp+48h+arg_10]
0x180029128  jnb     short loc_180029186
0x18002912a  lea     rcx, [rsp+48h+var_28]
0x18002912f  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x180029134  mov     rax, [rdi]
0x180029137  lea     r8, [rsp+48h+var_28]
0x18002913c  mov     edx, r14d
0x18002913f  mov     rcx, rdi
0x180029142  mov     rax, [rax+0C0h]
0x180029149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002914e  mov     ebx, eax
0x180029150  test    eax, eax
0x180029152  js      loc_18002920A
0x180029158  mov     r8, [rsp+48h+var_28]; struct IDomNode *
0x18002915d  test    r8, r8
0x180029160  jz      short loc_18002917C
0x180029162  mov     rdx, r15; struct IXmlWriter *
0x180029165  mov     rcx, rsi; this
0x180029168  call    ?PrintNodes@CWapDPU@@AEAAJPEAUIXmlWriter@@PEAUIDomNode@@@Z; CWapDPU::PrintNodes(IXmlWriter *,IDomNode *)
0x18002916d  mov     ebx, eax
0x18002916f  test    eax, eax
0x180029171  js      loc_18002920A
0x180029177  inc     r14d
0x18002917a  jmp     short loc_180029123
0x18002917c  mov     ebx, 8007000Eh
0x180029181  jmp     loc_18002920A
0x180029186  mov     rax, [rdi]
0x180029189  mov     rdx, r15
0x18002918c  mov     rcx, rdi
0x18002918f  mov     rax, [rax+100h]
0x180029196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002919b  mov     ebx, eax
0x18002919d  test    eax, eax
0x18002919f  js      short loc_18002920A
0x1800291a1  mov     rax, [rdi]
0x1800291a4  mov     rcx, rdi
0x1800291a7  mov     rax, [rax+20h]
0x1800291ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291b0  mov     ecx, [rsi+28h]
0x1800291b3  test    eax, eax
0x1800291b5  jns     short loc_1800291D1
0x1800291b7  cmp     ecx, 86000005h
0x1800291bd  jnz     short loc_1800291C4
0x1800291bf  mov     [rsi+28h], eax
0x1800291c2  jmp     short loc_1800291E1
0x1800291c4  test    ecx, ecx
0x1800291c6  js      short loc_1800291E1
0x1800291c8  mov     dword ptr [rsi+28h], 1
0x1800291cf  jmp     short loc_1800291E1
0x1800291d1  test    ecx, ecx
0x1800291d3  js      short loc_1800291F5
0x1800291d5  mov     ecx, 2AB0003h
0x1800291da  cmp     eax, ecx
0x1800291dc  jnz     short loc_1800291F5
0x1800291de  mov     [rsi+28h], ecx
0x1800291e1  mov     rax, [rdi]
0x1800291e4  lea     rdx, [rsi+38h]
0x1800291e8  mov     rcx, rdi
0x1800291eb  mov     rax, [rax+50h]
0x1800291ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291f4  nop
0x1800291f5  mov     rax, [rdi]
0x1800291f8  xor     edx, edx
0x1800291fa  mov     rcx, rdi
0x1800291fd  mov     rax, [rax+80h]
0x180029204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029209  nop
0x18002920a  lea     rcx, [rsp+48h+var_28]
0x18002920f  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180029214  mov     eax, ebx
0x180029216  mov     rbx, [rsp+48h+arg_0]
0x18002921b  mov     rsi, [rsp+48h+arg_8]
0x180029220  add     rsp, 30h
0x180029224  pop     r15
0x180029226  pop     r14
0x180029228  pop     rdi
0x180029229  retn
0x18002922b  mov     ebx, [rsp+48h+arg_18]
0x18002922f  jmp     short loc_18002920A
```
