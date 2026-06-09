# Reader::Parse(void)

- ea: `0x1006616b`
- end: `0x100662b7`
- name: `?Parse@Reader@@QAEJXZ`
- size: `332`
- prototype: `HRESULT __thiscall(Reader *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1004e790`
- `0x1004eb00`

## callees

- `0x1003c452`
- `0x10040d5e`
- `0x1006616b`
- `0x10067b20`
- `0x1006b823`
- `0x1006bff0`
- `0x1007a90b`
- `0x100eb351`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x100661b8`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x100661b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100661c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100661c8`

## string_xrefs

- `0x100661ff`: `max-xml-size`

## pseudocode

```c
HRESULT __thiscall Reader::Parse(Reader *this)
{
  Reader::ParseDocument(this);
  MemFree(this->_parseElementStack._pStack);
  this->_parseElementStack._pStack = 0;
  this->_parseElementStack._lCapacity = 0;
  this->_parseElementStack._lSize = 0;
  MemFree(this->_parseElementNStack._pStack);
  this->_parseElementNStack._pStack = 0;
  this->_parseElementNStack._lCapacity = 0;
  this->_parseElementNStack._lSize = 0;
  return 0;
}

```

## disassembly

```asm
0x1006616b  push    1Ch
0x1006616d  push    offset stru_10173E38
0x10066172  call    __SEH_prolog4
0x10066177  mov     eax, this
0x10066179  mov     [ebp+var_20], eax
0x1006617c  xor     ebx, ebx
0x1006617e  mov     [ebp+var_24], ebx
0x10066181  mov     [ebp+__hr], ebx
0x10066184  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x10066187  call    ?ParseDocument@Reader@@AAEXXZ; Reader::ParseDocument(void)
0x1006618c  jmp     loc_10066260
0x10066191  mov     this, [ebp+ms_exc.exc_ptr]; pExceptionPointers
0x10066194  mov     eax, [this]
0x10066196  mov     eax, [eax]
0x10066198  mov     [ebp+var_2C], eax
0x1006619b  lea     edx, [ebp+__hr]; phr
0x1006619e  call    ?MXRExceptionFilter@@YGJPAU_EXCEPTION_POINTERS@@PAJ@Z; MXRExceptionFilter(_EXCEPTION_POINTERS *,long *)
0x100661a3  retn
0x100661a4  mov     esp, [ebp+ms_exc.old_esp]
0x100661a7  mov     esi, 0C00000FDh
0x100661ac  cmp     [ebp+var_2C], esi
0x100661af  jnz     short loc_100661D0
0x100661b1  mov     [ebp+__hr], 800703E9h
0x100661b8  call    ds:__imp___resetstkoflw
0x100661be  xor     ebx, ebx
0x100661c0  test    eax, eax
0x100661c2  jnz     short loc_100661D2
0x100661c4  push    ebx; lpArguments
0x100661c5  push    ebx; nNumberOfArguments
0x100661c6  push    ebx; dwExceptionFlags
0x100661c7  push    esi; dwExceptionCode
0x100661c8  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100661ce  jmp     short loc_100661D2
0x100661d0  xor     ebx, ebx
0x100661d2  mov     this, [ebp+__hr]; hr
0x100661d5  mov     [ebp+var_24], this
0x100661d8  mov     [ebp+szMsg], ebx
0x100661db  cmp     this, 0C00CE225h
0x100661e1  jz      short loc_10066206
0x100661e3  cmp     this, 0C00CEE91h
0x100661e9  jz      short loc_100661FF
0x100661eb  cmp     this, 0C00CEE92h
0x100661f1  jnz     short loc_10066217
0x100661f3  mov     edx, offset ?maxElementDepth_pwh@CodeStringPtr@@2QBGB; "max-element-depth"
0x100661f8  mov     this, 0C00CE5FFh
0x100661fd  jmp     short loc_10066219
0x100661ff  mov     edx, offset ?maxXmlSize_pwh@CodeStringPtr@@2QBGB; "max-xml-size"
0x10066204  jmp     short loc_100661F8
0x10066206  mov     eax, [ebp+var_20]
0x10066209  cmp     byte ptr [eax+119h], 0
0x10066210  jz      short loc_10066217
0x10066212  mov     [ebp+var_24], ebx
0x10066215  jmp     short loc_10066260
0x10066217  xor     edx, edx; s1
0x10066219  lea     eax, [ebp+szMsg]
0x1006621c  push    eax; pszMsg
0x1006621d  call    ?FormatInternalMessage@@YGXJPBGPAPAG@Z; FormatInternalMessage(long,ushort const *,ushort * *)
0x10066222  mov     edx, ?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x10066228  cmp     [ebp+szMsg], 0
0x1006622c  cmovnz  edx, [ebp+szMsg]
0x10066230  mov     this, [ebp+var_20]
0x10066233  mov     this, [this+4F4h]
0x10066239  mov     eax, [this]
0x1006623b  mov     esi, [eax+10h]
0x1006623e  mov     eax, [ebp+var_20]
0x10066241  add     eax, 8
0x10066244  push    [ebp+var_24]
0x10066247  push    edx
0x10066248  push    eax
0x10066249  push    this
0x1006624a  mov     this, esi; this
0x1006624c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10066252  call    esi
0x10066254  push    2; __formal
0x10066256  push    [ebp+szMsg]; block
0x10066259  call    ??3@YAXPAXABUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1006625e  pop     this
0x1006625f  pop     this
0x10066260  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10066267  mov     esi, [ebp+var_20]
0x1006626a  mov     this, [esi+518h]; pv
0x10066270  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10066275  mov     [esi+518h], ebx
0x1006627b  mov     [esi+520h], ebx
0x10066281  mov     [esi+51Ch], ebx
0x10066287  mov     this, [esi+528h]; pv
0x1006628d  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10066292  mov     [esi+528h], ebx
0x10066298  mov     [esi+530h], ebx
0x1006629e  mov     [esi+52Ch], ebx
0x100662a4  mov     eax, [ebp+var_24]
0x100662a7  mov     this, [ebp+ms_exc.registration.Next]
0x100662aa  mov     large fs:0, this
0x100662b1  pop     this
0x100662b2  pop     edi
0x100662b3  pop     esi
0x100662b4  pop     ebx
0x100662b5  leave
0x100662b6  retn
```
