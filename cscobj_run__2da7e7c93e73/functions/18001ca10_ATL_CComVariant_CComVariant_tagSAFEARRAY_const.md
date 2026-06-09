# ATL::CComVariant::CComVariant(tagSAFEARRAY const *)

- ea: `0x18001ca10`
- end: `0x18001ca8c`
- name: `??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CComVariant *__hidden this, const struct tagSAFEARRAY *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e100`
- `0x18001e9b8`
- `0x18001ec30`
- `0x18001f22c`
- `0x1800281bc`

## callees

- `0x18001886c`
- `0x18001ca10`
- `0x18001cfa0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ca36`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ca36`

## pseudocode

```c
ATL::CComVariant *__fastcall ATL::CComVariant::CComVariant(ATL::CComVariant *this, struct tagSAFEARRAY *a2)
{
  HRESULT v4; // eax
  SAFEARRAY *ppsaOut; // [rsp+38h] [rbp+10h] BYREF

  ppsaOut = 0;
  if ( a2 )
  {
    v4 = SafeArrayCopy(a2, &ppsaOut);
    if ( v4 < 0 || !ppsaOut )
    {
      *(_WORD *)this = 10;
      *((_DWORD *)this + 2) = v4;
      ATL::AtlThrowImpl(-2147024882);
    }
    ATL::AtlSafeArrayGetActualVartype(a2, (unsigned __int16 *)this);
    *(_WORD *)this |= 0x2000u;
    *((_QWORD *)this + 1) = ppsaOut;
  }
  else
  {
    *(_WORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18001ca10  mov     [rsp+arg_0], rbx
0x18001ca15  push    rdi
0x18001ca16  sub     rsp, 20h
0x18001ca1a  mov     [rsp+28h+ppsaOut], 0
0x18001ca23  mov     rdi, rdx
0x18001ca26  mov     rbx, rcx
0x18001ca29  test    rdx, rdx
0x18001ca2c  jz      short loc_18001CA79
0x18001ca2e  lea     rdx, [rsp+28h+ppsaOut]; ppsaOut
0x18001ca33  mov     rcx, rdi; psa
0x18001ca36  call    cs:__imp_SafeArrayCopy
0x18001ca3c  test    eax, eax
0x18001ca3e  js      short loc_18001CA66
0x18001ca40  cmp     [rsp+28h+ppsaOut], 0
0x18001ca46  jz      short loc_18001CA66
0x18001ca48  mov     rdx, rbx; unsigned __int16 *
0x18001ca4b  mov     rcx, rdi; struct tagSAFEARRAY *
0x18001ca4e  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18001ca53  mov     eax, 2000h
0x18001ca58  or      [rbx], ax
0x18001ca5b  mov     rax, [rsp+28h+ppsaOut]
0x18001ca60  mov     [rbx+8], rax
0x18001ca64  jmp     short loc_18001CA7E
0x18001ca66  mov     ecx, 8007000Eh; int
0x18001ca6b  mov     word ptr [rbx], 0Ah
0x18001ca70  mov     [rbx+8], eax
0x18001ca73  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ca79  xor     eax, eax
0x18001ca7b  mov     [rcx], ax
0x18001ca7e  mov     rax, rbx
0x18001ca81  mov     rbx, [rsp+28h+arg_0]
0x18001ca86  add     rsp, 20h
0x18001ca8a  pop     rdi
0x18001ca8b  retn
```
