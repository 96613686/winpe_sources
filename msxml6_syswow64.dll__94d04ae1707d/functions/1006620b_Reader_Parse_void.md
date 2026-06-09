# Reader::Parse(void)

- ea: `0x1006620b`
- end: `0x10066357`
- name: `?Parse@Reader@@QAEJXZ`
- size: `332`
- prototype: `HRESULT __thiscall(Reader *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1004e820`
- `0x1004eb90`

## callees

- `0x1003c4e2`
- `0x10040dee`
- `0x1006620b`
- `0x10067bc0`
- `0x1006b8c3`
- `0x1006c080`
- `0x1007a8cb`
- `0x100eb231`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x10066258`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x10066258`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x10066268`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x10066268`

## string_xrefs

- `0x1006629f`: `max-xml-size`

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
0x1006620b  push    1Ch
0x1006620d  push    offset stru_10173D48
0x10066212  call    __SEH_prolog4
0x10066217  mov     eax, this
0x10066219  mov     [ebp+var_20], eax
0x1006621c  xor     ebx, ebx
0x1006621e  mov     [ebp+var_24], ebx
0x10066221  mov     [ebp+__hr], ebx
0x10066224  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x10066227  call    ?ParseDocument@Reader@@AAEXXZ; Reader::ParseDocument(void)
0x1006622c  jmp     loc_10066300
0x10066231  mov     this, [ebp+ms_exc.exc_ptr]; pExceptionPointers
0x10066234  mov     eax, [this]
0x10066236  mov     eax, [eax]
0x10066238  mov     [ebp+var_2C], eax
0x1006623b  lea     edx, [ebp+__hr]; phr
0x1006623e  call    ?MXRExceptionFilter@@YGJPAU_EXCEPTION_POINTERS@@PAJ@Z; MXRExceptionFilter(_EXCEPTION_POINTERS *,long *)
0x10066243  retn
0x10066244  mov     esp, [ebp+ms_exc.old_esp]
0x10066247  mov     esi, 0C00000FDh
0x1006624c  cmp     [ebp+var_2C], esi
0x1006624f  jnz     short loc_10066270
0x10066251  mov     [ebp+__hr], 800703E9h
0x10066258  call    ds:__imp___resetstkoflw
0x1006625e  xor     ebx, ebx
0x10066260  test    eax, eax
0x10066262  jnz     short loc_10066272
0x10066264  push    ebx; lpArguments
0x10066265  push    ebx; nNumberOfArguments
0x10066266  push    ebx; dwExceptionFlags
0x10066267  push    esi; dwExceptionCode
0x10066268  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x1006626e  jmp     short loc_10066272
0x10066270  xor     ebx, ebx
0x10066272  mov     this, [ebp+__hr]; hr
0x10066275  mov     [ebp+var_24], this
0x10066278  mov     [ebp+szMsg], ebx
0x1006627b  cmp     this, 0C00CE225h
0x10066281  jz      short loc_100662A6
0x10066283  cmp     this, 0C00CEE91h
0x10066289  jz      short loc_1006629F
0x1006628b  cmp     this, 0C00CEE92h
0x10066291  jnz     short loc_100662B7
0x10066293  mov     edx, offset ?maxElementDepth_pwh@CodeStringPtr@@2QBGB; "max-element-depth"
0x10066298  mov     this, 0C00CE5FFh
0x1006629d  jmp     short loc_100662B9
0x1006629f  mov     edx, offset ?maxXmlSize_pwh@CodeStringPtr@@2QBGB; "max-xml-size"
0x100662a4  jmp     short loc_10066298
0x100662a6  mov     eax, [ebp+var_20]
0x100662a9  cmp     byte ptr [eax+119h], 0
0x100662b0  jz      short loc_100662B7
0x100662b2  mov     [ebp+var_24], ebx
0x100662b5  jmp     short loc_10066300
0x100662b7  xor     edx, edx; s1
0x100662b9  lea     eax, [ebp+szMsg]
0x100662bc  push    eax; pszMsg
0x100662bd  call    ?FormatInternalMessage@@YGXJPBGPAPAG@Z; FormatInternalMessage(long,ushort const *,ushort * *)
0x100662c2  mov     edx, ?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x100662c8  cmp     [ebp+szMsg], 0
0x100662cc  cmovnz  edx, [ebp+szMsg]
0x100662d0  mov     this, [ebp+var_20]
0x100662d3  mov     this, [this+4F4h]
0x100662d9  mov     eax, [this]
0x100662db  mov     esi, [eax+10h]
0x100662de  mov     eax, [ebp+var_20]
0x100662e1  add     eax, 8
0x100662e4  push    [ebp+var_24]
0x100662e7  push    edx
0x100662e8  push    eax
0x100662e9  push    this
0x100662ea  mov     this, esi; this
0x100662ec  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100662f2  call    esi
0x100662f4  push    2; __formal
0x100662f6  push    [ebp+szMsg]; block
0x100662f9  call    ??3@YAXPAXABUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x100662fe  pop     this
0x100662ff  pop     this
0x10066300  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10066307  mov     esi, [ebp+var_20]
0x1006630a  mov     this, [esi+518h]; pv
0x10066310  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10066315  mov     [esi+518h], ebx
0x1006631b  mov     [esi+520h], ebx
0x10066321  mov     [esi+51Ch], ebx
0x10066327  mov     this, [esi+528h]; pv
0x1006632d  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10066332  mov     [esi+528h], ebx
0x10066338  mov     [esi+530h], ebx
0x1006633e  mov     [esi+52Ch], ebx
0x10066344  mov     eax, [ebp+var_24]
0x10066347  mov     this, [ebp+ms_exc.registration.Next]
0x1006634a  mov     large fs:0, this
0x10066351  pop     this
0x10066352  pop     edi
0x10066353  pop     esi
0x10066354  pop     ebx
0x10066355  leave
0x10066356  retn
```
