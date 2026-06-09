# ScriptSite::GetObjectFromMoniker(ushort *,IUnknown * *)

- ea: `0x180221e90`
- end: `0x180221f9f`
- name: `?GetObjectFromMoniker@ScriptSite@@QEAAJPEAGPEAPEAUIUnknown@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(ScriptSite *__hidden this, unsigned __int16 *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180221d90`

## callees

- `0x18021d7e8`
- `0x180221e90`
- `0x18035e010`

## import_xrefs

- `ole32!BindMoniker` at `0x180221f66`
- `ole32!BindMoniker` at `0x180221f66`
- `ole32!CreateBindCtx` at `0x180221f13`
- `ole32!CreateBindCtx` at `0x180221f13`
- `ole32!MkParseDisplayName` at `0x180221f2d`
- `ole32!MkParseDisplayName` at `0x180221f2d`

## pseudocode

```c
HRESULT __fastcall ScriptSite::GetObjectFromMoniker(ScriptSite *this, unsigned __int16 *a2, LPVOID *a3)
{
  HRESULT result; // eax
  HRESULT v4; // ebx
  ULONG pchEaten; // [rsp+20h] [rbp-20h] BYREF
  LPBC ppbc; // [rsp+28h] [rbp-18h] BYREF
  LPMONIKER ppmk; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppvResult; // [rsp+38h] [rbp-8h] BYREF

  if ( !a2 )
    return -2146828275;
  if ( (unsigned int)ScriptEngine::IsSafeMode(this, *(_DWORD *)(*((_QWORD *)this + 1) + 924LL), 0)
    || *(int *)(*((_QWORD *)this + 20) + 2336LL) >= 3 )
  {
    return -2146827859;
  }
  ppbc = 0;
  pchEaten = 0;
  ppmk = 0;
  ppvResult = 0;
  result = CreateBindCtx(0, &ppbc);
  if ( result >= 0 )
  {
    v4 = MkParseDisplayName(ppbc, a2, &pchEaten, &ppmk);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    ppbc = 0;
    if ( v4 >= 0 )
    {
      result = BindMoniker(ppmk, 0, &IID_IUnknown, &ppvResult);
      if ( result >= 0 )
      {
        ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
        *a3 = ppvResult;
        return 0;
      }
    }
    else
    {
      return v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180221e90  mov     rax, rsp
0x180221e93  mov     [rax+20h], rbx
0x180221e97  mov     [rax+18h], r8
0x180221e9b  mov     [rax+10h], rdx
0x180221e9f  mov     [rax+8], rcx
0x180221ea3  push    rbp
0x180221ea4  mov     rbp, rsp
0x180221ea7  sub     rsp, 40h
0x180221eab  cmp     [rbp+szUserName], 0
0x180221eb0  jnz     short loc_180221EBC
0x180221eb2  mov     eax, 800A000Dh
0x180221eb7  jmp     loc_180221F94
0x180221ebc  mov     rbx, [rbp+arg_0]
0x180221ec0  xor     r8d, r8d; struct _GUID *
0x180221ec3  mov     rdx, [rbx+8]
0x180221ec7  mov     edx, [rdx+39Ch]; unsigned int
0x180221ecd  call    ?IsSafeMode@ScriptEngine@@QEAAHKPEBU_GUID@@@Z; ScriptEngine::IsSafeMode(ulong,_GUID const *)
0x180221ed2  test    eax, eax
0x180221ed4  jnz     loc_180221F8F
0x180221eda  mov     rax, [rbx+0A0h]
0x180221ee1  cmp     dword ptr [rax+920h], 3
0x180221ee8  jge     loc_180221F8F
0x180221eee  lea     rdx, [rbp+ppbc]; ppbc
0x180221ef2  mov     [rbp+ppbc], 0
0x180221efa  xor     ecx, ecx; reserved
0x180221efc  mov     [rbp+pchEaten], 0
0x180221f03  mov     [rbp+ppmk], 0
0x180221f0b  mov     [rbp+ppvResult], 0
0x180221f13  call    cs:__imp_CreateBindCtx
0x180221f19  test    eax, eax
0x180221f1b  js      short loc_180221F94
0x180221f1d  mov     rdx, [rbp+szUserName]; szUserName
0x180221f21  lea     r9, [rbp+ppmk]; ppmk
0x180221f25  mov     rcx, [rbp+ppbc]; pbc
0x180221f29  lea     r8, [rbp+pchEaten]; pchEaten
0x180221f2d  call    cs:__imp_MkParseDisplayName
0x180221f33  mov     rcx, [rbp+ppbc]
0x180221f37  mov     ebx, eax
0x180221f39  mov     rdx, [rcx]
0x180221f3c  mov     rax, [rdx+10h]
0x180221f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221f45  mov     [rbp+ppbc], 0
0x180221f4d  test    ebx, ebx
0x180221f4f  jns     short loc_180221F55
0x180221f51  mov     eax, ebx
0x180221f53  jmp     short loc_180221F94
0x180221f55  mov     rcx, [rbp+ppmk]; pmk
0x180221f59  lea     r9, [rbp+ppvResult]; ppvResult
0x180221f5d  lea     r8, IID_IUnknown; iidResult
0x180221f64  xor     edx, edx; grfOpt
0x180221f66  call    cs:__imp_BindMoniker
0x180221f6c  test    eax, eax
0x180221f6e  js      short loc_180221F94
0x180221f70  mov     rcx, [rbp+ppmk]
0x180221f74  mov     rax, [rcx]
0x180221f77  mov     rax, [rax+10h]
0x180221f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221f80  mov     rax, [rbp+ppvResult]
0x180221f84  mov     rcx, [rbp+arg_10]
0x180221f88  mov     [rcx], rax
0x180221f8b  xor     eax, eax
0x180221f8d  jmp     short loc_180221F94
0x180221f8f  mov     eax, 800A01ADh
0x180221f94  mov     rbx, [rsp+40h+arg_18]
0x180221f99  add     rsp, 40h
0x180221f9d  pop     rbp
0x180221f9e  retn
```
