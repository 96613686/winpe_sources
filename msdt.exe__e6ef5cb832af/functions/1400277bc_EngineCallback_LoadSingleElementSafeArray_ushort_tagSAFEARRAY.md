# EngineCallback::LoadSingleElementSafeArray(ushort *,tagSAFEARRAY * *)

- ea: `0x1400277bc`
- end: `0x140027892`
- name: `?LoadSingleElementSafeArray@EngineCallback@@AEAAJPEAGPEAPEAUtagSAFEARRAY@@@Z`
- size: `214`
- prototype: `int(EngineCallback *__hidden this, unsigned __int16 *, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400274f0`
- `0x140027710`
- `0x140027898`

## callees

- `0x140020420`
- `0x1400277bc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400277f1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400277f1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002786e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002786e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140027837`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140027837`

## pseudocode

```c
__int64 __fastcall EngineCallback::LoadSingleElementSafeArray(
        EngineCallback *this,
        unsigned __int16 *a2,
        struct tagSAFEARRAY **a3)
{
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rdi
  unsigned int v7; // ebx
  HRESULT v8; // eax
  LONG rgIndices; // [rsp+40h] [rbp+8h] BYREF
  int v11; // [rsp+44h] [rbp+Ch]
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  v11 = HIDWORD(this);
  rgIndices = 0;
  v12 = 1;
  v5 = SafeArrayCreate(8u, 1u, (SAFEARRAYBOUND *)&v12);
  v6 = v5;
  if ( v5 )
  {
    v8 = SafeArrayPutElement(v5, &rgIndices, a2);
    v7 = v8;
    if ( v8 >= 0 )
    {
      *a3 = v6;
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EngineCallback::LoadSingleElementSafeArray", 1143, v8);
      SafeArrayDestroy(v6);
    }
  }
  else
  {
    v7 = -2147024882;
    SdpDebugPrint(
      1u,
      "Dwz ERROR: %s:%d - hr = 0x%08X\n",
      "EngineCallback::LoadSingleElementSafeArray",
      1137,
      -2147024882);
  }
  return v7;
}

```

## disassembly

```asm
0x1400277bc  mov     rax, rsp
0x1400277bf  mov     [rax+10h], rbx
0x1400277c3  mov     [rax+18h], rsi
0x1400277c7  mov     [rax+8], rcx
0x1400277cb  push    rdi
0x1400277cc  sub     rsp, 30h
0x1400277d0  mov     ecx, 8; vt
0x1400277d5  mov     dword ptr [rax+8], 0
0x1400277dc  mov     rsi, r8
0x1400277df  mov     qword ptr [rax+20h], 1
0x1400277e7  mov     rbx, rdx
0x1400277ea  lea     r8, [rax+20h]; rgsabound
0x1400277ee  lea     edx, [rcx-7]; cDims
0x1400277f1  call    cs:__imp_SafeArrayCreate
0x1400277f8  nop     dword ptr [rax+rax+00h]
0x1400277fd  mov     rdi, rax
0x140027800  test    rax, rax
0x140027803  jnz     short loc_14002782C
0x140027805  mov     ebx, 8007000Eh
0x14002780a  lea     r8, aEnginecallback_5; "EngineCallback::LoadSingleElementSafeAr"...
0x140027811  mov     r9d, 471h
0x140027817  mov     [rsp+38h+var_18], ebx
0x14002781b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140027822  lea     ecx, [rax+1]; Level
0x140027825  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002782a  jmp     short loc_14002787F
0x14002782c  mov     r8, rbx; pv
0x14002782f  lea     rdx, [rsp+38h+rgIndices]; rgIndices
0x140027834  mov     rcx, rdi; psa
0x140027837  call    cs:__imp_SafeArrayPutElement
0x14002783e  nop     dword ptr [rax+rax+00h]
0x140027843  mov     ebx, eax
0x140027845  test    eax, eax
0x140027847  jns     short loc_14002787C
0x140027849  mov     r9d, 477h
0x14002784f  mov     [rsp+38h+var_18], eax
0x140027853  lea     r8, aEnginecallback_5; "EngineCallback::LoadSingleElementSafeAr"...
0x14002785a  mov     ecx, 1; Level
0x14002785f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140027866  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002786b  mov     rcx, rdi; psa
0x14002786e  call    cs:__imp_SafeArrayDestroy
0x140027875  nop     dword ptr [rax+rax+00h]
0x14002787a  jmp     short loc_14002787F
0x14002787c  mov     [rsi], rdi
0x14002787f  mov     rsi, [rsp+38h+arg_10]
0x140027884  mov     eax, ebx
0x140027886  mov     rbx, [rsp+38h+arg_8]
0x14002788b  add     rsp, 30h
0x14002788f  pop     rdi
0x140027890  retn
```
