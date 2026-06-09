# ShapingInterface::InitializeShapingData(void)

- ea: `0x1801d308c`
- end: `0x1801d3181`
- name: `?InitializeShapingData@ShapingInterface@@AEAAAEBV?$map@IUSlotData@ShapingCacheElement@@U?$less@I@std@@U?$allocator@U?$pair@$$CBIUSlotData@ShapingCacheElement@@@std@@@StackAllocator@@@std@@XZ`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801d2e44`

## callees

- `0x18013e870`
- `0x180167278`
- `0x1801d308c`
- `0x18020c0e0`
- `0x18020c320`

## import_xrefs

- `TextShaping!ShapingLoadScriptEngine` at `0x1801d30da`
- `TextShaping!ShapingLoadScriptEngine` at `0x1801d3154`
- `TextShaping!ShapingLoadScriptEngine` at `0x1801d30da`
- `TextShaping!ShapingLoadScriptEngine` at `0x1801d3154`
- `TextShaping!ShapingCreateFontCacheData` at `0x1801d30c1`
- `TextShaping!ShapingCreateFontCacheData` at `0x1801d30c1`

## pseudocode

```c
__int64 __fastcall ShapingInterface::InitializeShapingData(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int FontCacheData; // eax
  int v5; // ebp
  int ScriptEngine; // eax
  int v8; // eax
  int v9; // ecx
  ShapingException *v10; // rax
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]

  v2 = (a1 + 16) & -(__int64)(a1 != 0);
  v3 = (a1 + 8) & -(__int64)(a1 != 0);
  FontCacheData = ShapingCreateFontCacheData(a1, v3, v2, 0);
  v5 = FontCacheData;
  if ( FontCacheData )
  {
    v8 = ShapingException::HresultFromShapingError(FontCacheData);
    v9 = -2147467259;
    if ( v8 < 0 )
      v9 = v8;
    v11 = v9;
    CaptureStack(v8, 0);
    v12 = v5;
    LogAndThrow<ShapingException>(&v11, 0x656570616873LL, 372);
  }
  ScriptEngine = ShapingLoadScriptEngine(a1, v3, v2, *(unsigned int *)(a1 + 104));
  if ( ScriptEngine == -200 )
  {
    if ( !*(_DWORD *)(a1 + 104) )
    {
LABEL_10:
      v10 = ShapingException::ShapingException((ShapingException *)&v11, ScriptEngine);
      LogAndThrow<ShapingException>(v10, 0x656570616873LL, 390);
    }
    *(_DWORD *)(a1 + 104) = 0;
    ScriptEngine = ShapingLoadScriptEngine(a1, v3, v2, 0);
  }
  if ( ScriptEngine )
    goto LABEL_10;
  return a1 + 144;
}

```

## disassembly

```asm
0x1801d308c  push    rbx
0x1801d308e  push    rbp
0x1801d308f  push    rsi
0x1801d3090  push    rdi
0x1801d3091  sub     rsp, 28h
0x1801d3095  lea     rdx, [rcx+10h]
0x1801d3099  mov     rax, rcx
0x1801d309c  neg     rax
0x1801d309f  mov     rbx, rcx
0x1801d30a2  mov     rax, rcx
0x1801d30a5  sbb     rdi, rdi
0x1801d30a8  and     rdi, rdx
0x1801d30ab  lea     rdx, [rcx+8]
0x1801d30af  neg     rax
0x1801d30b2  mov     r8, rdi
0x1801d30b5  sbb     rsi, rsi
0x1801d30b8  xor     r9d, r9d
0x1801d30bb  and     rsi, rdx
0x1801d30be  mov     rdx, rsi
0x1801d30c1  call    cs:__imp_ShapingCreateFontCacheData
0x1801d30c7  mov     ebp, eax
0x1801d30c9  test    eax, eax
0x1801d30cb  jnz     short loc_1801D30FB
0x1801d30cd  mov     r9d, [rbx+68h]
0x1801d30d1  mov     r8, rdi
0x1801d30d4  mov     rdx, rsi
0x1801d30d7  mov     rcx, rbx
0x1801d30da  call    cs:__imp_ShapingLoadScriptEngine
0x1801d30e0  cmp     eax, 0FFFFFF38h
0x1801d30e5  jz      short loc_1801D313B
0x1801d30e7  test    eax, eax
0x1801d30e9  jnz     short loc_1801D315C
0x1801d30eb  lea     rax, [rbx+90h]
0x1801d30f2  add     rsp, 28h
0x1801d30f6  pop     rdi
0x1801d30f7  pop     rsi
0x1801d30f8  pop     rbp
0x1801d30f9  pop     rbx
0x1801d30fa  retn
0x1801d30fb  mov     ecx, ebp; int
0x1801d30fd  mov     rbx, 656570616873h
0x1801d3107  call    ?HresultFromShapingError@ShapingException@@SAJH@Z; ShapingException::HresultFromShapingError(int)
0x1801d310c  test    eax, eax
0x1801d310e  mov     ecx, 80004005h
0x1801d3113  cmovs   ecx, eax
0x1801d3116  xor     edx, edx; unsigned int
0x1801d3118  mov     [rsp+48h+arg_0], ecx
0x1801d311c  mov     ecx, eax; int
0x1801d311e  call    ?CaptureStack@@YAXJI@Z; CaptureStack(long,uint)
0x1801d3123  mov     r8d, 174h
0x1801d3129  mov     [rsp+48h+arg_4], ebp
0x1801d312d  mov     rdx, rbx
0x1801d3130  lea     rcx, [rsp+48h+arg_0]
0x1801d3135  call    ??$LogAndThrow@VShapingException@@@@YAXAEBVShapingException@@VEventTag@@I@Z; LogAndThrow<ShapingException>(ShapingException const &,EventTag,uint)
0x1801d313b  cmp     dword ptr [rbx+68h], 0
0x1801d313f  jz      short loc_1801D315C
0x1801d3141  xor     r9d, r9d
0x1801d3144  mov     dword ptr [rbx+68h], 0
0x1801d314b  mov     r8, rdi
0x1801d314e  mov     rdx, rsi
0x1801d3151  mov     rcx, rbx
0x1801d3154  call    cs:__imp_ShapingLoadScriptEngine
0x1801d315a  jmp     short loc_1801D30E7
0x1801d315c  mov     edx, eax; int
0x1801d315e  lea     rcx, [rsp+48h+arg_0]; this
0x1801d3163  call    ??0ShapingException@@QEAA@H@Z; ShapingException::ShapingException(int)
0x1801d3168  mov     rdx, 656570616873h
0x1801d3172  mov     r8d, 186h
0x1801d3178  mov     rcx, rax
0x1801d317b  call    ??$LogAndThrow@VShapingException@@@@YAXAEBVShapingException@@VEventTag@@I@Z; LogAndThrow<ShapingException>(ShapingException const &,EventTag,uint)
```
