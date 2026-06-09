# IASVssWriter::DisableVssWriter(void)

- ea: `0x18000c2b0`
- end: `0x18000c331`
- name: `?DisableVssWriter@IASVssWriter@@UEAAJXZ`
- size: `129`
- prototype: `__int64 __fastcall(IASVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c110`

## callees

- `0x1800071ac`
- `0x18000c2b0`
- `0x18000d990`
- `0x180010010`

## string_xrefs

- `0x18000c2fa`: `CVssWriter::Unsubscribe() failed with %!hresult!`

## pseudocode

```c
__int64 __fastcall IASVssWriter::DisableVssWriter(IASVssWriter *this)
{
  __int64 v1; // rcx

  if ( !*((_DWORD *)this + 13) )
    return 0;
  v1 = *((_QWORD *)this - 1);
  if ( v1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 40LL))(v1);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("CVssWriter::Unsubscribe() failed with %!hresult!");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000c2b0  sub     rsp, 38h
0x18000c2b4  cmp     dword ptr [rcx+34h], 0
0x18000c2b8  jz      short loc_18000C2CF
0x18000c2ba  mov     rcx, [rcx-8]
0x18000c2be  test    rcx, rcx
0x18000c2c1  jz      short loc_18000C2D6
0x18000c2c3  mov     rax, [rcx]
0x18000c2c6  mov     rax, [rax+28h]
0x18000c2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2cf  xor     eax, eax
0x18000c2d1  add     rsp, 38h
0x18000c2d5  retn
0x18000c2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2dd  lea     rax, WPP_GLOBAL_Control
0x18000c2e4  cmp     rcx, rax
0x18000c2e7  jz      short loc_18000C32A
0x18000c2e9  cmp     byte ptr [rcx+19h], 2
0x18000c2ed  jb      short loc_18000C32A
0x18000c2ef  test    byte ptr [rcx+1Ch], 10h
0x18000c2f3  jz      short loc_18000C32A
0x18000c2f5  mov     edx, 80004005h
0x18000c2fa  lea     rcx, aCvsswriterUnsu; "CVssWriter::Unsubscribe() failed with %"...
0x18000c301  call    WppDbgPrint
0x18000c306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c30d  lea     r8, WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids
0x18000c314  mov     edx, 13h
0x18000c319  mov     [rsp+38h+var_18], 80004005h
0x18000c321  mov     rcx, [rcx+10h]
0x18000c325  call    WPP_SF_sd
0x18000c32a  mov     eax, 80004005h
0x18000c32f  jmp     short loc_18000C2D1
```
