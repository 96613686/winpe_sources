# ScriptSite::GetObjectFromMoniker(ushort *,IUnknown * *)

- ea: `0x180225c24`
- end: `0x180225d4a`
- name: `?GetObjectFromMoniker@ScriptSite@@QEAAJPEAGPEAPEAUIUnknown@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(ScriptSite *__hidden this, unsigned __int16 *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180225b14`

## callees

- `0x180221514`
- `0x180225c24`
- `0x180364010`

## import_xrefs

- `ole32!BindMoniker` at `0x180225d0a`
- `ole32!BindMoniker` at `0x180225d0a`
- `ole32!CreateBindCtx` at `0x180225ca7`
- `ole32!CreateBindCtx` at `0x180225ca7`
- `ole32!MkParseDisplayName` at `0x180225ccb`
- `ole32!MkParseDisplayName` at `0x180225ccb`

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
0x180225c24  mov     rax, rsp
0x180225c27  mov     [rax+20h], rbx
0x180225c2b  mov     [rax+18h], r8
0x180225c2f  mov     [rax+10h], rdx
0x180225c33  mov     [rax+8], rcx
0x180225c37  push    rbp
0x180225c38  mov     rbp, rsp
0x180225c3b  sub     rsp, 40h
0x180225c3f  cmp     [rbp+szUserName], 0
0x180225c44  jnz     short loc_180225C50
0x180225c46  mov     eax, 800A000Dh
0x180225c4b  jmp     loc_180225D3E
0x180225c50  mov     rbx, [rbp+arg_0]
0x180225c54  xor     r8d, r8d; struct _GUID *
0x180225c57  mov     rdx, [rbx+8]
0x180225c5b  mov     edx, [rdx+39Ch]; unsigned int
0x180225c61  call    ?IsSafeMode@ScriptEngine@@QEAAHKPEBU_GUID@@@Z; ScriptEngine::IsSafeMode(ulong,_GUID const *)
0x180225c66  test    eax, eax
0x180225c68  jnz     loc_180225D39
0x180225c6e  mov     rax, [rbx+0A0h]
0x180225c75  cmp     dword ptr [rax+920h], 3
0x180225c7c  jge     loc_180225D39
0x180225c82  lea     rdx, [rbp+ppbc]; ppbc
0x180225c86  mov     [rbp+ppbc], 0
0x180225c8e  xor     ecx, ecx; reserved
0x180225c90  mov     [rbp+pchEaten], 0
0x180225c97  mov     [rbp+ppmk], 0
0x180225c9f  mov     [rbp+ppvResult], 0
0x180225ca7  call    cs:__imp_CreateBindCtx
0x180225cae  nop     dword ptr [rax+rax+00h]
0x180225cb3  test    eax, eax
0x180225cb5  js      loc_180225D3E
0x180225cbb  mov     rdx, [rbp+szUserName]; szUserName
0x180225cbf  lea     r9, [rbp+ppmk]; ppmk
0x180225cc3  mov     rcx, [rbp+ppbc]; pbc
0x180225cc7  lea     r8, [rbp+pchEaten]; pchEaten
0x180225ccb  call    cs:__imp_MkParseDisplayName
0x180225cd2  nop     dword ptr [rax+rax+00h]
0x180225cd7  mov     rcx, [rbp+ppbc]
0x180225cdb  mov     ebx, eax
0x180225cdd  mov     rdx, [rcx]
0x180225ce0  mov     rax, [rdx+10h]
0x180225ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225ce9  mov     [rbp+ppbc], 0
0x180225cf1  test    ebx, ebx
0x180225cf3  jns     short loc_180225CF9
0x180225cf5  mov     eax, ebx
0x180225cf7  jmp     short loc_180225D3E
0x180225cf9  mov     rcx, [rbp+ppmk]; pmk
0x180225cfd  lea     r9, [rbp+ppvResult]; ppvResult
0x180225d01  lea     r8, IID_IUnknown; iidResult
0x180225d08  xor     edx, edx; grfOpt
0x180225d0a  call    cs:__imp_BindMoniker
0x180225d11  nop     dword ptr [rax+rax+00h]
0x180225d16  test    eax, eax
0x180225d18  js      short loc_180225D3E
0x180225d1a  mov     rcx, [rbp+ppmk]
0x180225d1e  mov     rax, [rcx]
0x180225d21  mov     rax, [rax+10h]
0x180225d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225d2a  mov     rax, [rbp+ppvResult]
0x180225d2e  mov     rcx, [rbp+arg_10]
0x180225d32  mov     [rcx], rax
0x180225d35  xor     eax, eax
0x180225d37  jmp     short loc_180225D3E
0x180225d39  mov     eax, 800A01ADh
0x180225d3e  mov     rbx, [rsp+40h+arg_18]
0x180225d43  add     rsp, 40h
0x180225d47  pop     rbp
0x180225d48  retn
```
