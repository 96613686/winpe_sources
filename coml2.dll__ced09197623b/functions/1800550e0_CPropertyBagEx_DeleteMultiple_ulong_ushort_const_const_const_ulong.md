# CPropertyBagEx::DeleteMultiple(ulong,ushort const * const * const,ulong)

- ea: `0x1800550e0`
- end: `0x1800551f0`
- name: `?DeleteMultiple@CPropertyBagEx@@UEAAJKQEBQEBGK@Z`
- size: `272`
- prototype: `__int64 __fastcall(CPropertyBagEx *__hidden this, unsigned int, const unsigned __int16 *const *const, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003f5e8`
- `0x1800550e0`
- `0x180055bfc`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551c4`

## pseudocode

```c
__int64 __fastcall CPropertyBagEx::DeleteMultiple(
        CPropertyBagEx *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        int a4)
{
  __int64 v5; // rsi
  int v8; // ebx
  int v9; // eax
  _DWORD *v10; // rdi
  unsigned int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax

  v5 = a2;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 0xFFFFFFFFLL);
  if ( (unsigned int)v5 > 0x200000 )
    goto LABEL_2;
  v8 = ValidateInRGLPOLESTR(v5, a3);
  if ( v8 )
    goto LABEL_18;
  if ( a4 )
  {
LABEL_2:
    v8 = -2147286953;
  }
  else
  {
    v9 = CPropertyBagEx::OpenPropStg(this, 3u);
    v8 = v9;
    if ( v9 == -2147287038 )
    {
      v8 = 0;
    }
    else if ( v9 >= 0 )
    {
      if ( (unsigned __int64)(16 * v5) > 0xFFFFFFFF )
      {
        v8 = -2147024362;
      }
      else
      {
        v10 = CoTaskMemAlloc((unsigned int)(16 * v5));
        if ( v10 )
        {
          v11 = 0;
          if ( (_DWORD)v5 )
          {
            v12 = 0;
            do
            {
              ++v11;
              v13 = 2 * v12;
              v10[2 * v13] = 0;
              v14 = a3[v12++];
              *(_QWORD *)&v10[2 * v13 + 2] = v14;
            }
            while ( v11 < (unsigned int)v5 );
          }
          v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *))(**((_QWORD **)this + 4) + 40LL))(
                 *((_QWORD *)this + 4),
                 (unsigned int)v5,
                 v10);
          if ( v8 >= 0 )
            v8 = 0;
          CoTaskMemFree(v10);
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
  }
LABEL_18:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800550e0  push    rbx
0x1800550e2  push    rbp
0x1800550e3  push    rsi
0x1800550e4  push    rdi
0x1800550e5  push    r14
0x1800550e7  push    r15
0x1800550e9  sub     rsp, 28h
0x1800550ed  mov     rbp, rcx
0x1800550f0  mov     esi, edx
0x1800550f2  mov     rcx, [rcx+28h]
0x1800550f6  mov     r15d, 0FFFFFFFFh
0x1800550fc  mov     edx, r15d
0x1800550ff  mov     edi, r9d
0x180055102  mov     r14, r8
0x180055105  mov     rax, [rcx]
0x180055108  mov     rax, [rax+18h]
0x18005510c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055111  cmp     esi, 200000h
0x180055117  jbe     short loc_180055123
0x180055119  mov     ebx, 80030057h
0x18005511e  jmp     loc_1800551D1
0x180055123  mov     rdx, r14; unsigned __int16 **
0x180055126  mov     ecx, esi; unsigned int
0x180055128  call    ?ValidateInRGLPOLESTR@@YAJKQEBQEBG@Z; ValidateInRGLPOLESTR(ulong,ushort const * const * const)
0x18005512d  mov     ebx, eax
0x18005512f  test    eax, eax
0x180055131  jnz     loc_1800551D1
0x180055137  test    edi, edi
0x180055139  jnz     short loc_180055119
0x18005513b  lea     edx, [rax+3]; unsigned int
0x18005513e  mov     rcx, rbp; this
0x180055141  call    ?OpenPropStg@CPropertyBagEx@@AEAAJK@Z; CPropertyBagEx::OpenPropStg(ulong)
0x180055146  mov     ebx, eax
0x180055148  cmp     eax, 80030002h
0x18005514d  jnz     short loc_180055153
0x18005514f  xor     ebx, ebx
0x180055151  jmp     short loc_1800551D1
0x180055153  test    eax, eax
0x180055155  js      short loc_1800551D1
0x180055157  mov     rax, rsi
0x18005515a  shl     rax, 4
0x18005515e  cmp     rax, r15
0x180055161  ja      short loc_1800551CC
0x180055163  mov     ecx, eax; cb
0x180055165  call    cs:__imp_CoTaskMemAlloc
0x18005516b  mov     rdi, rax
0x18005516e  test    rax, rax
0x180055171  jnz     short loc_18005517A
0x180055173  mov     ebx, 8007000Eh
0x180055178  jmp     short loc_1800551D1
0x18005517a  xor     r8d, r8d
0x18005517d  test    esi, esi
0x18005517f  jz      short loc_1800551A4
0x180055181  xor     edx, edx
0x180055183  mov     rcx, rdx
0x180055186  inc     r8d
0x180055189  add     rcx, rcx
0x18005518c  mov     dword ptr [rdi+rcx*8], 0
0x180055193  mov     rax, [r14+rdx*8]
0x180055197  inc     rdx
0x18005519a  mov     [rdi+rcx*8+8], rax
0x18005519f  cmp     r8d, esi
0x1800551a2  jb      short loc_180055183
0x1800551a4  mov     rcx, [rbp+20h]
0x1800551a8  mov     r8, rdi
0x1800551ab  mov     edx, esi
0x1800551ad  mov     rax, [rcx]
0x1800551b0  mov     rax, [rax+28h]
0x1800551b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551b9  mov     ebx, eax
0x1800551bb  test    eax, eax
0x1800551bd  js      short loc_1800551C1
0x1800551bf  xor     ebx, ebx
0x1800551c1  mov     rcx, rdi; pv
0x1800551c4  call    cs:__imp_CoTaskMemFree
0x1800551ca  jmp     short loc_1800551D1
0x1800551cc  mov     ebx, 80070216h
0x1800551d1  mov     rcx, [rbp+28h]
0x1800551d5  mov     rax, [rcx]
0x1800551d8  mov     rax, [rax+20h]
0x1800551dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551e1  mov     eax, ebx
0x1800551e3  add     rsp, 28h
0x1800551e7  pop     r15
0x1800551e9  pop     r14
0x1800551eb  pop     rdi
0x1800551ec  pop     rsi
0x1800551ed  pop     rbp
0x1800551ee  pop     rbx
0x1800551ef  retn
```
