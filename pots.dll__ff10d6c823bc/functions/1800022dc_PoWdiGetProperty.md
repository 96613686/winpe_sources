# PoWdiGetProperty

- ea: `0x1800022dc`
- end: `0x18000239e`
- name: `PoWdiGetProperty`
- size: `194`
- prototype: `TDHSTATUS __fastcall(PEVENT_RECORD pEvent, ULONGLONG, __int64, BYTE *, ULONG, ULONG *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f6c`
- `0x1800024e8`
- `0x1800032c0`
- `0x180003ae0`
- `0x180003d30`
- `0x180003e00`
- `0x180003eb0`
- `0x180004240`
- `0x180004330`

## callees

- `0x1800022dc`
- `0x180004930`

## import_xrefs

- `tdh!TdhGetPropertySize` at `0x18000233a`
- `tdh!TdhGetPropertySize` at `0x18000233a`
- `tdh!TdhGetProperty` at `0x18000237d`
- `tdh!TdhGetProperty` at `0x18000237d`

## pseudocode

```c
TDHSTATUS __fastcall PoWdiGetProperty(PEVENT_RECORD pEvent, ULONGLONG a2, __int64 a3, BYTE *a4, ULONG a5, ULONG *a6)
{
  TDHSTATUS result; // eax
  ULONG v9; // ecx
  ULONG BufferSize; // [rsp+40h] [rbp-38h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+48h] [rbp-30h] BYREF

  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = a2;
  BufferSize = 0;
  result = TdhGetPropertySize(pEvent, 0, 0, 1u, &pPropertyData, &BufferSize);
  if ( result )
  {
    v9 = 0;
  }
  else
  {
    v9 = BufferSize;
    if ( BufferSize <= a5 )
    {
      result = TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, BufferSize, a4);
      v9 = BufferSize;
    }
    else
    {
      result = 122;
    }
  }
  *a6 = v9;
  return result;
}

```

## disassembly

```asm
0x1800022dc  mov     r11, rsp
0x1800022df  push    rbx
0x1800022e0  push    rsi
0x1800022e1  push    rdi
0x1800022e2  sub     rsp, 60h
0x1800022e6  mov     rax, cs:__security_cookie
0x1800022ed  xor     rax, rsp
0x1800022f0  mov     [rsp+78h+var_20], rax
0x1800022f5  mov     rbx, [rsp+78h+arg_28]
0x1800022fd  lea     rax, [r11-38h]
0x180002301  mov     [r11-50h], rax
0x180002305  mov     rsi, r9
0x180002308  mov     [rsp+78h+var_30.Reserved], 0
0x180002310  lea     rax, [r11-30h]
0x180002314  mov     [rsp+78h+var_30.ArrayIndex], 0FFFFFFFFh
0x18000231c  mov     r9d, 1; PropertyDataCount
0x180002322  mov     [r11-30h], rdx
0x180002326  xor     r8d, r8d; pTdhContext
0x180002329  xor     edx, edx; TdhContextCount
0x18000232b  mov     [r11-58h], rax
0x18000232f  mov     rdi, rcx
0x180002332  mov     [rsp+78h+var_38], 0
0x18000233a  call    cs:__imp_TdhGetPropertySize
0x180002340  test    eax, eax
0x180002342  jz      short loc_180002348
0x180002344  xor     ecx, ecx
0x180002346  jmp     short loc_180002387
0x180002348  mov     ecx, [rsp+78h+var_38]
0x18000234c  cmp     ecx, [rsp+78h+arg_20]
0x180002353  jbe     short loc_18000235C
0x180002355  mov     eax, 7Ah ; 'z'
0x18000235a  jmp     short loc_180002387
0x18000235c  mov     [rsp+78h+pBuffer], rsi; pBuffer
0x180002361  lea     rax, [rsp+78h+var_30]
0x180002366  mov     [rsp+78h+BufferSize], ecx; BufferSize
0x18000236a  mov     r9d, 1; PropertyDataCount
0x180002370  mov     rcx, rdi; pEvent
0x180002373  mov     [rsp+78h+pPropertyData], rax; pPropertyData
0x180002378  xor     r8d, r8d; pTdhContext
0x18000237b  xor     edx, edx; TdhContextCount
0x18000237d  call    cs:__imp_TdhGetProperty
0x180002383  mov     ecx, [rsp+78h+var_38]
0x180002387  mov     [rbx], ecx
0x180002389  mov     rcx, [rsp+78h+var_20]
0x18000238e  xor     rcx, rsp; StackCookie
0x180002391  call    __security_check_cookie
0x180002396  add     rsp, 60h
0x18000239a  pop     rdi
0x18000239b  pop     rsi
0x18000239c  pop     rbx
0x18000239d  retn
```
