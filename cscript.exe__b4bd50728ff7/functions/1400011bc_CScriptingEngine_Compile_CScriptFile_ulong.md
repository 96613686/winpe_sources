# CScriptingEngine::Compile(CScriptFile *,ulong)

- ea: `0x1400011bc`
- end: `0x140001295`
- name: `?Compile@CScriptingEngine@@QEAAJPEAVCScriptFile@@K@Z`
- size: `217`
- prototype: `__int64 __fastcall(struct CScriptBlock **this, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001090`

## callees

- `0x1400011bc`
- `0x140002820`
- `0x140010810`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::Compile(struct CScriptBlock **this, const unsigned __int16 **a2, unsigned int a3)
{
  __int64 result; // rax
  const unsigned __int16 **v7; // r14
  const unsigned __int16 *v8; // rcx

  if ( a3 )
  {
    result = CCodeSink::Emit((CCodeSink *)(this + 15), a2[9], a3);
    if ( (int)result < 0 )
      return result;
    v7 = (const unsigned __int16 **)(this + 18);
    result = CScriptBlock::Create((struct CScriptFile *)a2, (struct CScriptingEngine *)this, 0, a3, this + 18);
    if ( (int)result < 0 )
      return result;
    v8 = *v7;
    a2[14] = *v7;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  if ( !*((_DWORD *)this + 32) )
    return 0;
  result = (*(__int64 (__fastcall **)(struct CScriptBlock *, struct CScriptBlock *, _QWORD, _QWORD, _QWORD, _QWORD, int, int, _QWORD, _QWORD))(*(_QWORD *)this[13] + 40LL))(
             this[13],
             this[15],
             0,
             0,
             0,
             *((unsigned int *)this + 22),
             1,
             130,
             0,
             0);
  if ( (int)result >= 0 )
    return 0;
  if ( (_DWORD)result == -2147352319 )
    return 2147811327LL;
  return result;
}

```

## disassembly

```asm
0x1400011bc  push    rbx
0x1400011be  push    rbp
0x1400011bf  push    rsi
0x1400011c0  push    rdi
0x1400011c1  push    r14
0x1400011c3  sub     rsp, 60h
0x1400011c7  mov     esi, r8d
0x1400011ca  mov     rbp, rdx
0x1400011cd  mov     rbx, rcx
0x1400011d0  test    r8d, r8d
0x1400011d3  jz      short loc_14000121E
0x1400011d5  mov     rdx, [rdx+48h]; unsigned __int16 *
0x1400011d9  add     rcx, 78h ; 'x'; this
0x1400011dd  call    ?Emit@CCodeSink@@QEAAJPEBGK@Z; CCodeSink::Emit(ushort const *,ulong)
0x1400011e2  test    eax, eax
0x1400011e4  js      loc_14000128A
0x1400011ea  lea     r14, [rbx+90h]
0x1400011f1  mov     r9d, esi; unsigned int
0x1400011f4  xor     r8d, r8d; unsigned int
0x1400011f7  mov     [rsp+88h+var_68], r14; struct CScriptBlock **
0x1400011fc  mov     rdx, rbx; struct CScriptingEngine *
0x1400011ff  mov     rcx, rbp; struct CScriptFile *
0x140001202  call    ?Create@CScriptBlock@@SAJPEAVCScriptFile@@PEAVCScriptingEngine@@KKPEAPEAV1@@Z; CScriptBlock::Create(CScriptFile *,CScriptingEngine *,ulong,ulong,CScriptBlock * *)
0x140001207  test    eax, eax
0x140001209  js      short loc_14000128A
0x14000120b  mov     rcx, [r14]
0x14000120e  mov     [rbp+70h], rcx
0x140001212  mov     rax, [rcx]
0x140001215  mov     rax, [rax+8]
0x140001219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000121e  cmp     dword ptr [rbx+80h], 0
0x140001225  jz      short loc_140001288
0x140001227  mov     r8d, [rbx+58h]
0x14000122b  xor     r9d, r9d
0x14000122e  mov     rcx, [rbx+68h]
0x140001232  mov     rdx, [rbx+78h]
0x140001236  mov     [rsp+88h+var_40], 0
0x14000123f  mov     [rsp+88h+var_48], 0
0x140001248  mov     rax, [rcx]
0x14000124b  mov     [rsp+88h+var_50], 82h
0x140001253  mov     [rsp+88h+var_58], 1
0x14000125b  mov     [rsp+88h+var_60], r8
0x140001260  xor     r8d, r8d
0x140001263  mov     rax, [rax+28h]
0x140001267  mov     [rsp+88h+var_68], 0
0x140001270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001275  test    eax, eax
0x140001277  jns     short loc_140001288
0x140001279  cmp     eax, 80020101h
0x14000127e  mov     ecx, 8004FFFFh
0x140001283  cmovz   eax, ecx
0x140001286  jmp     short loc_14000128A
0x140001288  xor     eax, eax
0x14000128a  add     rsp, 60h
0x14000128e  pop     r14
0x140001290  pop     rdi
0x140001291  pop     rsi
0x140001292  pop     rbp
0x140001293  pop     rbx
0x140001294  retn
```
